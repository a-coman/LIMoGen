# instagen

**Paper**: "LLM-based Generation of Realistic and Diverse Domain Model Instances". [ArXiv Preprint](https://arxiv.org/pdf/2604.10350)

In order to maintain commit history, reproducibilty and ease of maintenance, the project is organized in different tools and repositories as follows:

## docs

Its the main documentation for the project. For easy access it contains:
- The 10 domain models used for the generation in the `models` folder.
- The instances generated with `llm-instancer`, and the metrics computed with `llm-evaluator`, `ged` and `graphdiff` in the `instances` folder from various experiments (two experiments with GPT 4o and different prompts (GPT 4o_old), and the one from the paper with GPT 5.2).
- The prompts in .txt format used for the generation and llm-as-a-judge evaluation in the `prompts` folder. 
- The expert evaluation of the judge reasoning and constraints added to each model in `experts-judge-eval.xlsx`
- The new domain models with the 48 OCL constraints added from `experts-judge-eval.xlsx` evaluation in the .use class diagrams in the `models-with-ocl` folder.

## llm-instancer

[https://github.com/a-coman/llm-instancer](https://github.com/a-coman/llm-instancer)

Generates `.soil` instances of a UML class diagram. Simple prompting asks the model for one instance from the diagram. Chain-of-thought prompting analyzes the diagram, writes a list of scenarios, and instantiates each scenario. USE checks syntax and conformance while generating, and failed checks go back to the model. Scoring the finished instances is done by llm-evaluator.

Requires Java 21 and Maven. Put API keys in a `.env` file in the project root. Generation reads `OPENROUTER_API_KEY`, or `OPENAI_KEY`, or `DEEPSEEK_KEY`, or `GEMINI_KEY`, depending on the model selected in `Main`.

Set the model, strategy, domain, repetition count, and model set in `src/main/java/es/uma/Main.java`, then run:

```bash
mvn -q compile org.codehaus.mojo:exec-maven-plugin:3.5.0:java -Dexec.mainClass=es.uma.Main
```

The model set picks the class diagrams: `MODELS` reads `src/main/resources/models`, and `MODELS_WITH_OCL` reads `src/main/resources/models-with-ocl`. They are copies of `docs/models` and `docs/experts-judge/models-with-ocl`.

Instances are written to `src/main/resources/instances/<model>/<Simple|CoT>/<domain>/<time>/gen<N>/`, the same layout as `docs/instances`. Runs against `models-with-ocl` get an `-ocl` suffix on the time folder.

## llm-evaluator

[https://github.com/a-coman/llm-evaluator](https://github.com/a-coman/llm-evaluator)

Evaluate the instances produced by llm-instancer. It reads datasets from `src/main/resources/dataset/<model>/`, with `Simple` and `CoT` folders underneath, the same layout as `docs/instances`. Reports are written inside the dataset they were computed from.

It computes these families of metrics.

- Well-formedness and conformance. USE checks the syntax, multiplicities, and invariants of every instance.
- Realism. Domain-specific checks on attribute values, such as valid IBANs and BICs, or movies and addresses that exist (OMDB and Geoapify).
- Similarity. Exact match and Levenshtein distance on attribute values, inside one instance and across a run.
- Shannon entropy of those attribute values.
- Coverage of classes, associations, and attributes against the class diagram.
- Embedding distance on a hand-picked set of attributes per domain, such as `Address.city` or `Movie.title`. Gemini embeds the values and cosine distance says how far apart their meanings are.
- An LLM judge that scores whether an instance describes a realistic scenario.

It also renders every instance as a PDF object diagram, and `es.uma.JudgeAnalysis` compares the judge against the formal checks and the human evaluation.

Requires Java 21 and Maven. The judge and the semantic checks need `GEMINI_KEY` and `OPENROUTER_API_KEY` in a `.env` file, and the movie and address realism checks need `OMDB_KEY` and `GEOAPIFY_KEY`. `es.uma.Main` runs all of the metrics and the PDF export on the `GPT_5_2` dataset.

```bash
mvn -q compile org.codehaus.mojo:exec-maven-plugin:3.5.0:java -Dexec.mainClass=es.uma.Main
```

Class diagrams are read from `src/main/resources/models` and `src/main/resources/models-with-ocl`, the same copies llm-instancer uses.

## use

llm-instancer and llm-evaluator both run a modified build of [USE](https://github.com/useocl/use) 7.5.0. It is not an official release. It adds a headless `export` command, which writes an object diagram to PDF with auto-layout (`export --hierarchical`) and no GUI dialogs, so the stock USE releases cannot replace it. The source is at [a-coman/use](https://github.com/a-coman/use), cloned in `use`. We intend to contribute this change upstream.

Each tool uses `src/main/resources/use-7.5.0` in its own folder. If it is not there, the tool downloads the [v7.5.0-export release](https://github.com/a-coman/use/releases/tag/v7.5.0-export) and unzips it into that folder.

## ged

[https://github.com/a-coman/ged](https://github.com/a-coman/ged)

Bounds the labeled graph edit distance between object diagrams. Each SOIL file becomes an undirected labeled multigraph. Objects are nodes labeled by class. Links are edges labeled by association. Exact graph edit distance is NP-hard on this data, so the tool returns a certified interval. The upper bound is a bipartite assignment refined by IPFP and a local search. The lower bound is the BRANCH relaxation plus a label-multiset bound. The reported distance is the upper bound. A diversity score divides that distance by the cost of deleting one graph and building the other. Identical graphs score 0, and the score stays between 0 and 1.

Requires [uv](https://docs.astral.sh/uv/) and Python 3.13.

```bash
uv run main.py --dataset-root /path/to/dataset
```

The dataset root must contain directories laid out as `llm/experiment/system/time/genN` (same as docs or llm-instancer layout). Use `--llm` and `--system` to keep a subset. You can also set `GED_DATASET_ROOT`. Each experiment gets `ged_v2.md` and `ged_v2.json`.

```bash
uv run pytest -q
```

## graphdiff

[https://github.com/a-coman/graphdiff](https://github.com/a-coman/graphdiff)

An alternative to GED. Converts SOIL instances to labeled graphs and compares them with the Weisfeiler-Lehman subtree kernel from GraKeL. Each experiment directory receives a `grakel.md` file with a normalized similarity matrix and a dissimilarity matrix. Dissimilarity is the square root of one minus the similarity.

GraKeL in this repository requires Python 2.7.18. [pyenv](https://github.com/pyenv/pyenv) is the straightforward way to get it.

```bash
pyenv install 2.7.18
pyenv virtualenv 2.7.18 graphdiff
pyenv activate graphdiff
pip install -r requirements.txt
python main.py --dataset /path/to/dataset
```

## llm-viewer

[https://github.com/a-coman/llm-viewer](https://github.com/a-coman/llm-viewer)

Static site for reading the generated instances next to the metrics from the tools above. 

Requires Node.js. The dataset lives in `public/data/dataset`.

```bash
npm install
npm run dev
```

The dev server listens at `http://localhost:4321`. `npm run build` writes the site to `dist/`. 

The page is availible online at: https://viewer.a-coman.dev/gpt_5_2/

## License
**instagen** is licensed under the **MIT License** (see `LICENSE`). llm-instancer, llm-evaluator, ged, graphdiff, and llm-viewer are also MIT-licensed, each with its own `LICENSE` file. USE keeps its own license, the GNU GPL v2 (see `use/COPYING`), and so does each third-party library the tools depend on.
