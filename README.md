# Awesome Geospatial AutoML [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> Automated model selection, algorithm discovery and evaluation for spatial and Earth-observation data.

A curated list of papers, repositories, datasets and benchmarks for geospatial AutoML. It also covers geospatial agents and the cloud-native data tools that support repeatable modelling workflows. Each resource has a primary-source link and a short description of its role.

Curated by **James Edward Ball**. **100 resources**. Sources checked **14 October 2026**.

## Contents

- [Start here](#start-here)
- [Direct geospatial AutoML](#direct-geospatial-automl)
- [Geospatial agents](#geospatial-agents)
- [AutoML and search engines](#automl-and-search-engines)
- [Algorithm discovery and research loops](#algorithm-discovery-and-research-loops)
- [Geospatial modelling software](#geospatial-modelling-software)
- [Foundation models and embeddings](#foundation-models-and-embeddings)
- [Agent benchmarks](#agent-benchmarks)
- [Model benchmarks](#model-benchmarks)
- [Datasets](#datasets)
- [Cloud-native geospatial](#cloud-native-geospatial)
- [Data access and catalogues](#data-access-and-catalogues)
- [Spatial validation and interpretation](#spatial-validation-and-interpretation)
- [Books and surveys](#books-and-surveys)
- [Related awesome lists](#related-awesome-lists)
- [Evaluation and reproducibility](#evaluation-and-reproducibility)
- [Source notes](#source-notes)

## Start here

| Aim | Starting resources |
| --- | --- |
| Discover geospatial algorithms | [GeoEvolve](https://arxiv.org/abs/2509.21593) and [algorithm-discovery frameworks](#algorithm-discovery-and-research-loops). |
| Select spatially varying tabular models | [PyGALAX](https://github.com/Pingping9/PyGALAX), [AutoML engines](#automl-and-search-engines) and [spatial validation](#spatial-validation-and-interpretation). |
| Compare Earth-observation models | [TorchGeo](https://github.com/torchgeo/torchgeo), [TerraTorch](https://github.com/torchgeo/terratorch) and [GEO-Bench-2](https://github.com/The-AI-Alliance/GEO-Bench-2). |
| Evaluate geospatial agents | [GeoBenchX](https://github.com/Solirinai/GeoBenchX), [ThinkGeo](https://github.com/mbzuai-oryx/ThinkGeo) and [agent benchmarks](#agent-benchmarks). |
| Study disaster-response workflows | [DORA](https://arxiv.org/abs/2605.11633), with task data such as [xBD](https://xview2.org/dataset) and [Sen1Floods11](https://github.com/cloudtostreet/Sen1Floods11). |
| Build repeatable data pipelines | [STAC](https://stacspec.org/en/), [the CNG formats guide](https://guide.cloudnativegeo.org/) and [Apache Sedona](https://sedona.apache.org/latest/). |

## Direct geospatial AutoML

Geospatial model selection, spatially varying prediction and algorithm or architecture search.

- [GeoEvolve](https://arxiv.org/abs/2509.21593) - Evolves geospatial algorithms using a code-search loop and retrieved geographical knowledge. Evaluates spatial interpolation and uncertainty estimation. Luo et al., 2025; [PyPI package](https://pypi.org/project/geoevolve/). The PyPI package names the paper authors; a canonical source repository was not confirmed.
- [PyGALAX](https://github.com/Pingping9/PyGALAX) - Combines geographically weighted modelling, automated model selection and local SHAP explanations. A focused starting point for spatially varying tabular prediction. [Paper: Wang et al., 2026](https://arxiv.org/abs/2602.00907).
- [GALAX](https://github.com/Pingping9/GALAX-aaag) - Original Geospatial Analysis Leveraging AutoML and eXplainable AI implementation. Provides a reference for local models and comparison with geographically weighted regression. [Published paper](https://doi.org/10.1080/24694452.2025.2591684).
- [ArcGIS Train Using AutoML](https://doc.esri.com/en/arcgis-pro/latest/tool-reference/geoai/train-using-automl.html) - Automates feature engineering, model selection and tuning for spatial prediction inside ArcGIS Pro. Provides trained model packages and an HTML comparison report. Commercial software; raster explanatory variables require a Spatial Analyst licence.
- [Landscape of Neural Architecture Search Across Sensors](https://isprs-annals.copernicus.org/articles/V-3-2022/217/2022/) - Studies architecture-search landscapes across remote-sensing sensors and sensor fusion. Useful for defining a sensor-aware search space. [Paper: primary source](https://doi.org/10.5194/isprs-annals-V-3-2022-217-2022).

## Geospatial agents

Systems that plan and execute GIS or Earth-observation workflows. Their evaluations concern tool use and analysis outputs.

- [LLM-Geo](https://github.com/gladcolor/LLM-Geo) - Generates and executes spatial-analysis workflows from natural-language requests. An early reference implementation of Autonomous GIS. [Paper: Li and Ning, 2023](https://arxiv.org/abs/2305.06453).
- [GIS Copilot](https://github.com/Teakinboyewa/SpatialAnalysisAgent) - Uses a QGIS plugin to plan spatial analysis and call existing processing tools. Useful for studying grounded tool use in a desktop GIS. [Paper: Akinboyewa et al., 2024](https://arxiv.org/abs/2411.03205).
- [GeoAgent](https://arxiv.org/abs/2410.18792) - Combines code execution, static analysis and retrieval with search to automate geospatial data analysis. Useful for studying planning and code checking. Chen et al., 2024. Paper reference; official code release was not confirmed.
- [GeoFlow](https://arxiv.org/abs/2508.04719) - Agentic workflow automation for geospatial tasks. Useful for studying how a language model plans and composes analysis operations. Bhattaram et al., 2025. Paper reference; official code release was not confirmed.
- [Earth-Agent](https://github.com/opendatalab/Earth-Agent) - Agent framework and benchmark for long-horizon Earth-observation workflows. Supports research on composing tools over multiple analysis steps. [Paper: Feng et al., 2025](https://arxiv.org/abs/2509.23141).
- [OpenEarthAgent](https://github.com/mbzuai-oryx/OpenEarthAgent) - Open agent research for reasoning and tool use with Earth-observation data. Provides a reference implementation and associated research paper. [Paper: Shabbir et al., 2026](https://arxiv.org/abs/2602.17665).
- [Change-Agent](https://github.com/Chen-Yang-Liu/Change-Agent) - Combines remote-sensing change interpretation with conversational interaction and tool use. Useful for temporal analysis and change-reporting workflows. [Paper: Liu et al., 2024](https://arxiv.org/abs/2403.19646).
- [AWS Sample Geospatial Agent](https://github.com/aws-samples/sample-geospatial-agent-on-aws) - Reference implementation for a geospatial agent on AWS. Useful for understanding cloud service integration and deployment patterns.

## AutoML and search engines

General search tools that can support geospatial experiments with suitable spatial or temporal validation.

- [AutoGluon](https://github.com/autogluon/autogluon) - General AutoML for predictive modelling, including tabular ensembles. Useful for baselines on spatial features and frozen Earth-observation embeddings. [Paper: Erickson et al., 2020](https://arxiv.org/abs/2003.06505).
- [FLAML](https://github.com/microsoft/FLAML) - Cost-aware automated model and hyperparameter search. Useful for comparing tabular geospatial baselines under a fixed compute budget. [Paper: Wang et al., 2019](https://arxiv.org/abs/1911.04706).
- [H2O AutoML](https://github.com/h2oai/h2o-3) - Automates tabular model training and ensemble comparison. Useful for geospatial covariates, exposure models and regression baselines.
- [TPOT](https://github.com/EpistasisLab/tpot) - Searches machine-learning pipelines with genetic programming. Useful for exploring preprocessing and estimator combinations on spatial tabular data.
- [Optuna](https://github.com/optuna/optuna) - Hyperparameter optimisation with pruning and configurable search spaces. Useful for tuning a geospatial training or adaptation pipeline. [Published paper](https://doi.org/10.1145/3292500.3330701).
- [Ray Tune](https://github.com/ray-project/ray) - Distributed experiment search and trial scheduling. Useful when geospatial tuning requires parallel GPU or CPU jobs. [Paper: Liaw et al., 2018](https://arxiv.org/abs/1807.05118).
- [SMAC3](https://github.com/automl/SMAC3) - Sequential model-based algorithm configuration. Useful for expensive geospatial pipeline objectives and conditional search spaces. [Paper: Lindauer et al., 2021](https://arxiv.org/abs/2109.09831); [Published JMLR paper](https://jmlr.org/papers/v23/21-0888.html).

## Algorithm discovery and research loops

Code-search and experiment-loop frameworks that can use a geospatial evaluator.

- [AlphaEvolve](https://deepmind.google/blog/alphaevolve-a-gemini-powered-coding-agent-for-designing-advanced-algorithms/) - Language-model-driven evolutionary algorithm discovery. Provides methodological context for GeoEvolve and evaluator-guided code search.
- [OpenEvolve](https://github.com/algorithmicsuperintelligence/openevolve) - Open implementation of language-model-guided evolutionary code search. Can serve as a general search harness for geospatial objectives.
- [ShinkaEvolve](https://github.com/SakanaAI/ShinkaEvolve) - Research framework for language-model-guided programme evolution. Useful for testing automated discovery with a custom spatial evaluator. [Paper: Lange et al., 2025](https://arxiv.org/abs/2509.19349).
- [autoresearch](https://github.com/karpathy/autoresearch) - Small automated research loop that edits training code and compares experiment results. Useful as a reference for controlled iterative model experiments.

## Geospatial modelling software

Libraries for data preparation, training and spatial analysis.

- [TorchGeo](https://github.com/torchgeo/torchgeo) - Geospatial datasets, samplers, transforms and training components for PyTorch. Supports reproducible baselines across remote-sensing tasks. [Paper: Stewart et al., 2021](https://arxiv.org/abs/2111.08872).
- [TerraTorch](https://github.com/torchgeo/terratorch) - Toolkit for adapting geospatial foundation models to downstream tasks. Useful for controlled comparisons of encoders and task heads. [Paper: Gomes et al., 2025](https://arxiv.org/abs/2503.20563).
- [Raster Vision](https://github.com/azavea/raster-vision) - Configurable deep-learning pipelines for satellite and aerial imagery. Useful for repeatable chip generation, training and prediction.
- [eo-learn](https://github.com/sentinel-hub/eo-learn) - Composable Earth-observation processing tasks for preprocessing and feature extraction. Useful for building repeatable data pipelines before model search.
- [GeoAI](https://github.com/opengeos/geoai) - Geospatial AI library with training, inference and data-processing workflows. Useful for assembling applied image-analysis pipelines.
- [Segment Geospatial](https://github.com/opengeos/segment-geospatial) - Geospatial workflows around segmentation foundation models. Useful for interactive labels and candidate segmentation baselines.
- [GeoPandas](https://github.com/geopandas/geopandas) - Vector geometry operations and spatial joins in Python. Useful for preparing spatial covariates and checking agent outputs.
- [Rasterio](https://github.com/rasterio/rasterio) - Raster reading, writing and georeferencing. Useful for preserving spatial metadata through model input and output pipelines.
- [Xarray](https://github.com/pydata/xarray) - Labelled multidimensional arrays for gridded and temporal data. Useful for aligning Earth-observation inputs across bands and dates.
- [Apache Sedona](https://github.com/apache/sedona) - Spatial SQL, joins and raster/vector processing, with distributed execution on Spark and Flink. Useful for preparing large datasets and spatial features before model search. [Documentation](https://sedona.apache.org/latest/).

## Foundation models and embeddings

Reusable model families for adaptation and model-selection experiments.

- [Prithvi-EO](https://github.com/NASA-IMPACT/Prithvi-EO-2.0) - Open Earth-observation foundation-model family for downstream adaptation. A reusable encoder candidate for model-selection experiments. [Paper: Szwarcman et al., 2024](https://arxiv.org/abs/2412.02732).
- [Clay](https://github.com/Clay-foundation/model) - Open geospatial foundation model and embeddings workflow. Useful for testing frozen representations against end-to-end fine-tuning.
- [TerraMind](https://github.com/IBM/terramind) - Multimodal Earth-observation foundation model. Useful for studying modality choice and adaptation in automated pipelines. [Paper: Jakubik et al., 2025](https://arxiv.org/abs/2504.11171).
- [Presto](https://github.com/nasaharvest/presto) - Lightweight pretrained transformer for remote-sensing time series. Useful for resource-constrained temporal prediction and embedding baselines. [Paper: Tseng et al., 2023](https://arxiv.org/abs/2304.14065).
- [SatMAE](https://github.com/sustainlab-group/SatMAE) - Masked autoencoding for temporal and multispectral satellite imagery. Provides a research baseline for pretrained representation comparison. [Paper: Cong et al., 2022](https://arxiv.org/abs/2207.08051).
- [CROMA](https://github.com/antofuller/CROMA) - Contrastive radar-optical masked autoencoding. Useful for comparing optical-only and combined SAR-optical representations. [Paper: Fuller et al., 2023](https://arxiv.org/abs/2311.00566).

## Agent benchmarks

Evaluation of multi-step workflows, tool arguments and output correctness.

- [DORA](https://arxiv.org/abs/2605.11633) - Disaster Operational Response Agent benchmark for multi-step emergency operations over heterogeneous geospatial data. Evaluates tool orchestration and operational reasoning. Wang et al., 2026. Paper reference; official public code and dataset release locations were not confirmed.
- [GeoBenchX](https://github.com/Solirinai/GeoBenchX) - Multi-step GIS task benchmark with geospatial tools, reference outputs and an evaluation framework. Useful for testing workflow completion and task rejection. [Paper: Krechetova and Kochedykov, 2025](https://arxiv.org/abs/2503.18129); [Published paper](https://doi.org/10.1145/3764915.3770721). Pin the benchmark revision and judge configuration.
- [ThinkGeo](https://github.com/mbzuai-oryx/ThinkGeo) - Tool-augmented remote-sensing agent benchmark with expert-checked task trajectories. Evaluates answer quality and tool use on imagery-grounded tasks. [Paper: Shabbir et al., 2025](https://arxiv.org/abs/2505.23752).
- [GeoAgentBench](https://github.com/GeoX-Lab/GABench) - Dynamic execution benchmark for GIS agents. Useful for assessing atomic tool composition, parameter selection and error recovery. [Paper: Yu et al., 2026](https://arxiv.org/abs/2604.13888).
- [GISAgentBench](https://arxiv.org/abs/2608.01645) - Practitioner-sourced GIS benchmark for evaluating language-model agents on realistic analysis workflows. Complements imagery-focused evaluations. Pothuri et al., 2026. Paper reference; executable task release was not confirmed.

## Model benchmarks

Evaluation of prediction, model adaptation and geographic or sensor transfer.

- [GEO-Bench-2](https://github.com/The-AI-Alliance/GEO-Bench-2) - Capability-based evaluation of geospatial foundation models across multiple tasks, modalities and temporal settings. A useful backbone for model-selection experiments. [Paper: Simumba et al., 2025](https://arxiv.org/abs/2511.15658).
- [PANGAEA](https://github.com/VMarsocci/pangaea-bench) - Geospatial foundation-model benchmark covering diverse tasks and sensing conditions. Useful for testing whether selected models transfer beyond one dataset. [Paper: Marsocci et al., 2024](https://arxiv.org/abs/2412.04204). This model benchmark is separate from the PANGAEA environmental data publisher.
- [Copernicus-Bench](https://github.com/zhu-xlab/Copernicus-FM/tree/main/Copernicus-Bench) - Benchmark across Copernicus Sentinel missions and downstream tasks. Useful for evaluating sensor coverage and model adaptation. [Paper: Wang et al., 2025](https://arxiv.org/abs/2503.11849).
- [WILDS](https://github.com/p-lambda/wilds) - Distribution-shift benchmark suite, including satellite-related tasks such as FMoW and poverty mapping. Useful for geographic generalisation tests. [Paper: Koh et al., 2020](https://arxiv.org/abs/2012.07421).
- [SustainBench](https://sustainlab-group.github.io/sustainbench/) - Benchmark tasks for monitoring sustainable-development indicators. Useful for evaluating applied models on environmental and socioeconomic targets. [Paper: Yeh et al., 2021](https://arxiv.org/abs/2111.04724); [Source repository](https://github.com/sustainlab-group/sustainbench).

## Datasets

Data for supervised learning, pretraining and independent evaluation.

- [BigEarthNet v2](https://bigearth.net/) - Paired Sentinel-1 and Sentinel-2 patches with land-cover reference information. Useful for multimodal classification and representation baselines. [Paper: Clasen et al., 2024](https://arxiv.org/abs/2407.03653).
- [EuroSAT](https://github.com/phelber/EuroSAT) - Sentinel-2 land-use and land-cover image classification dataset. Useful for a small smoke test before larger model-search experiments. [Paper: Helber et al., 2017](https://arxiv.org/abs/1709.00029).
- [SEN12MS](https://github.com/schmitt-muc/SEN12MS) - Paired SAR and multispectral imagery with land-cover information. Useful for sensor-fusion and representation-learning experiments. [Paper: Schmitt et al., 2019](https://arxiv.org/abs/1906.07789).
- [SSL4EO-S12](https://github.com/zhu-xlab/SSL4EO-S12) - Large multimodal, multiseasonal Sentinel-1/2 pretraining dataset. Useful for self-supervised model and input-modality comparisons. [Paper: Wang et al., 2022](https://arxiv.org/abs/2211.07044); [Version 1.1 dataset](https://huggingface.co/datasets/embed2scale/SSL4EO-S12-v1.1).
- [Functional Map of the World](https://github.com/fMoW/dataset) - Satellite image dataset for classifying functional land-use categories. Useful for temporal and metadata-aware classification baselines. [Paper: Christie et al., 2017](https://arxiv.org/abs/1711.07846).
- [SpaceNet](https://spacenet.ai/datasets/) - Satellite imagery challenges for building footprints, roads and related mapping tasks. Useful for structured extraction and downstream spatial-analysis evaluation.
- [xBD / xView2](https://xview2.org/dataset) - Pre-event and post-event imagery with building-damage labels. Useful for disaster-assessment baselines and input data for operational workflows. [Paper: Gupta et al., 2019](https://arxiv.org/abs/1911.09296).
- [Sen1Floods11](https://github.com/cloudtostreet/Sen1Floods11) - Sentinel-1 flood dataset with labelled flood observations. Useful for SAR flood-segmentation baselines and robustness checks.
- [PASTIS](https://github.com/VSainteuf/pastis-benchmark) - Satellite image time series for agricultural parcel segmentation. Useful for temporal model selection and parcel-based evaluation. [Paper: Garnot and Landrieu, 2021](https://arxiv.org/abs/2107.07933).
- [FLAIR](https://github.com/IGNF/FLAIR) - IGN land-cover datasets combining aerial imagery and other observation sources. Useful for segmentation, modality comparison and regional transfer. [Paper: Garioud et al., 2023](https://arxiv.org/abs/2310.13336).
- [LoveDA](https://github.com/Junjue-Wang/LoveDA) - Urban and rural remote-sensing semantic-segmentation dataset. Useful for domain-adaptation and spatial transfer experiments. [Paper: Wang et al., 2021](https://arxiv.org/abs/2110.08733).
- [DOTA](https://captain-whu.github.io/DOTA/) - Aerial image dataset for oriented object detection. Useful for evaluating a detection pipeline with orientation-sensitive labels. [Paper: Xia et al., 2017](https://arxiv.org/abs/1711.10398).

## Cloud-native geospatial

Resources from the Cloud-Native Geospatial Forum and the wider ecosystem for discovery, selective access and reproducible inputs. [Apache Sedona](https://github.com/apache/sedona), listed above, adds spatial processing at scale.

- [STAC](https://stacspec.org/en/) - SpatioTemporal Asset Catalog specification for machine-readable geospatial discovery. Useful for recording the exact data assets used by an automated pipeline. [Source repository](https://github.com/radiantearth/stac-spec).
- [PySTAC Client](https://github.com/stac-utils/pystac-client) - Python client for STAC API discovery and search. Useful for reproducible spatial and temporal input queries.
- [StackSTAC](https://github.com/gjoseph92/stackstac) - Builds labelled, lazy image stacks from STAC items. Useful for repeatable raster preprocessing and temporal input assembly.
- [Cloud-Native Geospatial Forum](https://cloudnativegeo.org/) - Community initiative for cloud-native geospatial data and tools. Useful for technical discussions, learning resources and geospatial-embedding evaluation work. [Geo-embeddings sprint and benchmarking](https://cloudnativegeo.org/blog/2026/07/announcing-geo-embedding-sprint-zurich/).
- [Cloud-Optimized Geospatial Formats Guide](https://guide.cloudnativegeo.org/) - CNG community guide with format comparisons, cookbooks and executable examples. Useful for choosing data layouts that support repeatable model input access. [Source repository](https://github.com/cloudnativegeo/cloud-optimized-geospatial-formats-guide).
- [STAC API](https://github.com/radiantearth/stac-api-spec) - API specification for searching and retrieving STAC records. Supports repeatable queries by location, acquisition time and available asset metadata.
- [PySTAC](https://github.com/stac-utils/pystac) - Python library for creating, reading and validating STAC catalogues. Useful for publishing a reproducible record of training and evaluation assets.
- [STAC-GeoParquet](https://github.com/stac-utils/stac-geoparquet) - Tools for converting STAC items to GeoParquet and other catalogue backends. Useful for bulk metadata filtering and large experiment manifests.
- [Cloud Optimized GeoTIFF](https://cogeo.org/) - Raster layout that supports reading selected image regions over HTTP range requests. Useful for loading training chips and spatial subsets from object storage.
- [rio-cogeo](https://github.com/cogeotiff/rio-cogeo) - Creates and validates Cloud Optimized GeoTIFFs. Useful for preparing raster outputs and input assets with documented spatial metadata.
- [GeoParquet](https://geoparquet.org/) - Specification for geospatial vector data in Parquet. Useful for reusable labels, spatial features and column-based access to large vector datasets. [Source repository](https://github.com/opengeospatial/geoparquet).
- [Zarr](https://zarr.dev/) - Chunked array storage with implementations for distributed and cloud access. Useful for multispectral and temporal model inputs. [Source repository](https://github.com/zarr-developers/zarr-python).
- [kerchunk](https://fsspec.github.io/kerchunk/) - Reference-based access to existing array files through a virtual Zarr representation. Useful for reusing NetCDF or HDF archives in a model-input pipeline. [Source repository](https://github.com/fsspec/kerchunk).
- [Cloud Optimized Point Cloud](https://copc.io/) - Point-cloud specification with a spatial hierarchy for selecting subsets. Useful for LiDAR inputs and elevation-related modelling.
- [FlatGeobuf](https://flatgeobuf.org/) - Binary vector format with an optional spatial index and support for range-based access. Useful for spatially selective access to labels and reference features. [Source repository](https://github.com/flatgeobuf/flatgeobuf).
- [PMTiles](https://docs.protomaps.com/pmtiles/) - Single-file archive for map tiles that supports range-based reading. Useful for publishing and reviewing model outputs as maps. [Source repository](https://github.com/protomaps/PMTiles). Retain the analytical output files alongside display tiles.
- [DuckDB Spatial](https://github.com/duckdb/duckdb-spatial) - Spatial SQL extension for an analytical database. Useful for extracting covariates, checking geometry and querying GeoParquet data.
- [Dask](https://docs.dask.org/en/stable/) - Parallel and distributed task execution for Python arrays and dataframes. Useful with Xarray and Zarr for repeatable preprocessing across large image collections. [Source repository](https://github.com/dask/dask).

## Data access and catalogues

Primary data providers and catalogues for building versioned model inputs.

- [Microsoft Planetary Computer](https://planetarycomputer.microsoft.com/docs/overview/about/) - STAC catalogue and access tooling for environmental datasets. Useful for reproducible discovery of satellite and climate inputs.
- [Google Earth Engine](https://developers.google.com/earth-engine) - Cloud catalogue and processing environment for geospatial analysis. Useful for collecting covariates and running repeatable preprocessing.
- [Copernicus Data Space Ecosystem](https://dataspace.copernicus.eu/) - Official access ecosystem for Copernicus data. Useful for obtaining Sentinel products and tracking product provenance.
- [Source Cooperative](https://source.coop/) - Publishing platform for open datasets. Useful for finding documented geospatial data and model-derived products.
- [OpenStreetMap](https://www.openstreetmap.org/about) - Community-maintained vector data for roads, buildings and other map features. Useful for network analysis and spatial context in agent tasks.
- [Overture Maps](https://docs.overturemaps.org/) - Open map datasets distributed in GeoParquet. Useful for building, transport and place features in geospatial modelling and agent evaluation.

## Spatial validation and interpretation

Methods for checking spatial dependence, geographic transfer and model behaviour.

- [blockCV](https://github.com/rvalavi/blockCV) - Spatial and environmental cross-validation tools in R. Useful for testing model selection against geographically separated validation data. [Published paper](https://doi.org/10.1111/2041-210X.13107).
- [spatialCV](https://github.com/geoai-lab/spatialCV) - Spatial cross-validation reference code for GeoAI. Useful for comparing validation strategies and understanding spatial dependence.
- [GeoShapley](https://github.com/Ziqi-Li/geoshapley) - Measures location effects and feature-location interactions in predictive models. Useful for inspecting spatial model behaviour after AutoML selection. [Paper: Li, 2023](https://arxiv.org/abs/2312.03675); [Published paper](https://doi.org/10.1080/24694452.2024.2350982).
- [PySAL](https://github.com/pysal/pysal) - Spatial-analysis libraries for dependence, regression and exploratory diagnostics. Useful for checking residual spatial structure and baseline assumptions.
- [Cross-validation for structured data](https://doi.org/10.1111/ecog.02881) - Methodological paper on cross-validation for spatial, temporal and hierarchical data. Provides a basis for validation choices in automated geospatial modelling.

## Books and surveys

References for defining search spaces and understanding model and agent families.

- [Automated Machine Learning: Methods, Systems, Challenges](https://www.automl.org/book/) - Open-access book covering model selection, optimisation and AutoML systems. Useful for defining what an automated geospatial experiment actually searches.
- [Neural Architecture Search: A Survey](https://jmlr.org/papers/v20/18-598.html) - Survey of search spaces, search strategies and performance estimation. Useful for designing an architecture-search experiment with a clear scope.
- [Foundation Models for Remote Sensing and Earth Observation: A Survey](https://arxiv.org/abs/2410.16602) - Survey of remote-sensing foundation models. Useful for understanding input modalities, adaptation methods and model families before selecting candidates. Xiao et al., 2024.
- [Agentic AI in Remote Sensing: Foundations, Taxonomy, and Emerging Systems](https://arxiv.org/abs/2601.01891) - Survey and taxonomy of remote-sensing agents. Useful for distinguishing perception, workflow automation and research agents. Talemi et al., 2026; [Published workshop paper](https://openaccess.thecvf.com/content/WACV2026W/GeoCV/papers/Talemi_Agentic_AI_in_Remote_Sensing_Foundations_Taxonomy_and_Emerging_Systems_WACVW_2026_paper.pdf).

## Related awesome lists

Wider discovery resources with links to primary research and implementations.

- [Awesome Geospatial](https://github.com/sacridini/Awesome-Geospatial) - Broad geospatial software and resource index. Use it for tools beyond this list's automated-modelling scope.
- [Awesome Earth Observation Code](https://github.com/acgeospatial/awesome-earthobservation-code) - Earth-observation code and learning resources. Useful for discovering processing tools and practical examples.
- [Awesome Agentic AI for Earth Observation](https://github.com/rasid-ai/awesome-agentic-ai-for-earth-observation) - Focused list of remote-sensing agent papers and repositories. Useful for discovering related agent systems and surveys.
- [Awesome Remote Sensing Foundation Models](https://github.com/xiaoaoran/awesome-RSFMs) - Survey-linked model and paper collection. Useful for tracking model families and following primary research links.
- [Satellite Image Deep Learning Datasets](https://github.com/satellite-image-deep-learning/datasets) - Task-organised index of satellite-imagery datasets. Useful for discovering task-specific data beyond the core selection.

## Evaluation and reproducibility

Choose validation data that represent the intended prediction setting: within an observed area, in a new region, at a later date or from a different sensor. Spatial dependence can bias model selection. [Roberts et al.](https://doi.org/10.1111/ecog.02881) discuss validation for structured data; [blockCV](https://doi.org/10.1111/2041-210X.13107) provides spatial and environmental fold construction.

Keep training, model selection and final test data separate. Fit preprocessing inside the training folds. Record dataset and model versions, geographic splits, bands, normalisation, coordinate reference systems, search budgets and failed trials. Compare selected models with simple baselines under the same conditions.

For agent workflows, record the tool environment, execution trajectories and produced files. Use deterministic numeric, file and geometry checks where the task supports them. Evaluate final output correctness separately from resemblance to a reference tool sequence.

## Source notes

Resources were selected for their relevance, primary-source documentation and identifiable method or implementation. General AutoML engines and cloud-native tools have an enabling role. Agent benchmarks assess workflow execution; model-discovery claims require a search experiment with an appropriate validation protocol.

The two verified seed papers are [GeoEvolve - Luo et al., 2025](https://arxiv.org/abs/2509.21593) and [DORA - Wang et al., 2026](https://arxiv.org/abs/2605.11633). The user-supplied [SSRN reference 6753201](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=6753201) remains pending: access returned HTTP 403, so its title and authors are unverified.

Paper links identify arXiv records or published versions where available. Years beside arXiv links use the initial submission year. Check the source for its preferred current citation. Source review covers documentation and bibliographic metadata; software execution, dataset downloads and experiment replication require separate checks. Code, model weights and datasets can have different licences.

The [CNG formats guide](https://guide.cloudnativegeo.org/) credits Aimee Barciauskas, Alex Mandel, Kyle Barron and Zac Deziel and uses CC BY 4.0. All linked resources retain their source authorship and terms.

The structure follows the [Awesome manifesto](https://github.com/sindresorhus/awesome/blob/main/awesome.md) and the related lists above: a clear scope, annotated entries, primary links and practical categories. The badge identifies the list format.

Contributions are welcome. Suggest a primary source, explain its specific role and state the version and access conditions. This is an initial curated selection, reviewed with AI assistance.

Original list content is dedicated under [CC0 1.0 Universal](https://creativecommons.org/publicdomain/zero/1.0/). Linked resources retain their own terms.
