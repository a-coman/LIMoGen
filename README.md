# instagen

Code for the paper "LLM-based Generation of Diverse and Realistic Domain Model Instances". [ArXiv Preprint](https://arxiv.org/pdf/2604.10350)

In order to maintain coomit history, reproducibilty and ease of maintenance, the project is organized in different tools and repositories as follows:

## llm-instancer

[https://github.com/a-coman/llm-instancer](https://github.com/a-coman/llm-instancer)

Generates `.soil` instances of a UML class diagram. Simple prompting asks the model for one instance from the diagram. Chain-of-thought prompting analyzes the diagram, writes a list of scenarios, and instantiates each scenario. USE checks syntax and conformance, and failed checks go back to the model.

Requires Java 21, Maven, and the USE 7.1.1 binaries in `src/main/resources/use-7.1.1`. Download them from the [USE 7.1.1 release](https://github.com/useocl/use/releases/tag/v7.1.1). Put API keys in a `.env` file in the project root. Generation reads `OPENROUTER_API_KEY`, or `OPENAI_KEY`, or `DEEPSEEK_KEY`, or `GEMINI_KEY`, depending on the model selected in `Main`. Movie and address API realism checks also read `OMDB_KEY` and `GEOAPIFY_KEY`.

PDF export from the CLI needs a modified USE 7.1.1. Stock USE cannot run `export --hierarchical` with auto-layout. For that, download the build from [a-coman/use-mod](https://github.com/a-coman/use-mod) and put those binaries in `src/main/resources/use-7.1.1` instead of the stock release. We intend to contribute this change upstream. Until that lands, the fork is the build that writes the PDFs.

Set the model, strategy, domain, and repetition count in `src/main/java/es/uma/Main.java`, then run:

```bash
mvn -q compile org.codehaus.mojo:exec-maven-plugin:3.5.0:java -Dexec.mainClass=es.uma.Main
```

Instances are written under `src/main/resources/instances/`.

## llm-evaluator

[https://github.com/a-coman/llm-evaluator](https://github.com/a-coman/llm-evaluator)

Scores the instances produced by llm-instancer. Put a dataset at `src/main/resources/dataset/<model>/`, with `Simple` and `CoT` folders underneath.

It computes five families of metrics.

- Similarity. Exact match and Levenshtein distance on attribute values, inside one instance and across a run.
- Shannon entropy of those attribute values.
- Coverage of classes, associations, and attributes against the class diagram.
- Embedding distance on a hand-picked set of attributes per domain, such as `Address.city` or `Movie.title`. Gemini embeds the values and cosine distance says how far apart their meanings are.
- An LLM judge that scores whether an instance describes a realistic scenario.

Requires Java 21 and Maven. The judge and the semantic checks need `GEMINI_KEY` and `OPENROUTER_API_KEY` in a `.env` file. `es.uma.Main` runs similarity, Shannon entropy, coverage, and semantics on the `GPT_5_2` dataset.

```bash
mvn -q compile org.codehaus.mojo:exec-maven-plugin:3.5.0:java -Dexec.mainClass=es.uma.Main
```

Markdown reports are written next to the metric classes and inside the dataset folder.

## ged

[https://github.com/a-coman/ged](https://github.com/a-coman/ged)

Bounds the labeled graph edit distance between object diagrams. Each SOIL file becomes an undirected labeled multigraph. Objects are nodes labeled by class. Links are edges labeled by association. Exact graph edit distance is NP-hard on this data, so the tool returns a certified interval. The upper bound is a bipartite assignment refined by IPFP and a local search. The lower bound is the BRANCH relaxation plus a label-multiset bound. The reported distance is the upper bound. A diversity score divides that distance by the cost of deleting one graph and building the other. Identical graphs score 0, and the score stays between 0 and 1.

Requires [uv](https://docs.astral.sh/uv/) and Python 3.13.

```bash
uv run main.py --dataset-root /path/to/dataset
```

The dataset root must contain directories laid out as `llm/experiment/system/time/genN`. Repeat `--llm` and `--system` to keep a subset. You can also set `GED_DATASET_ROOT`. Each experiment gets `ged_v2.md` and `ged_v2.json`.

```bash
uv run pytest -q
```

## graphdiff

[https://github.com/a-coman/graphdiff](https://github.com/a-coman/graphdiff)

Converts SOIL instances to labeled graphs and compares them with the Weisfeiler-Lehman subtree kernel from GraKeL. Each experiment directory receives a `grakel.md` file with a normalized similarity matrix and a dissimilarity matrix. Dissimilarity is the square root of one minus the similarity.

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

## Order of use

Run llm-instancer first. Copy the SOIL files into the dataset layout expected by llm-evaluator, ged, and graphdiff, then run those three on the same instances. Open llm-viewer to read the reports next to the diagrams.
