# Gemini API Cookbook

[![Website](https://img.shields.io/website?url=https://fallendeity.github.io/gemini-ts-cookbook/)](https://fallendeity.github.io/gemini-ts-cookbook/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-F37626?logo=jupyter&logoColor=white)](https://jupyter.org/)

A comprehensive collection of tutorials, examples, and practical demonstrations for working with Google's Gemini API. This cookbook provides structured learning paths from basic concepts to advanced implementations using TypeScript and JavaScript.

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Project Structure](#project-structure)
- [Quick Start](#quick-start)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
- [Available Tasks](#available-tasks)
- [Notebooks](#notebooks)
- [Building the Site](#building-the-site)
- [Contributing](#contributing)
- [License](#license)
- [Related Resources](#related-resources)

## Overview

This cookbook serves as a comprehensive guide for developers looking to integrate Google's Gemini API into their applications. It covers everything from basic API usage to advanced features like multimodal interactions, function calling, embeddings, and real-time capabilities.

**Live Documentation:** [https://fallendeity.github.io/gemini-ts-cookbook](https://fallendeity.github.io/gemini-ts-cookbook)

## Features

- **Quick Start Guides**: Step-by-step tutorials for getting started with Gemini API
- **Practical Examples**: Real-world use cases and implementations
- **TypeScript Support**: Full TypeScript integration with proper type definitions
- **Interactive Notebooks**: Jupyter notebooks with executable code examples
- **Modern Tooling**: ESLint, Prettier, and automated formatting
- **Static Site Generation**: Quarto-powered documentation website
- **CI/CD Integration**: Automated testing and deployment workflows

## Project Structure

```text
gemini-ts-cookbook/
├── examples/              # Practical use case implementations
│   ├── Agents_Function_Calling_Barista_Bot.ipynb
│   ├── Analyze_a_Video_*.ipynb
│   ├── Browser_as_a_tool.ipynb
│   ├── Entity_Extraction.ipynb
│   └── ... (25+ example notebooks)
├── quickstarts/          # Step-by-step learning guides
│   ├── Get_started.ipynb    # Main getting started guide
│   ├── Audio.ipynb
│   ├── Embeddings.ipynb
│   ├── Function_calling.ipynb
│   └── ... (25+ quickstart notebooks)
├── assets/               # Resources and sample files
│   ├── audio.mp3
│   ├── california_housing.csv
│   ├── sample PDFs and images
│   └── ... (various sample assets)
├── scripts/              # Build and maintenance scripts
├── build/                # Generated static site
├── package.json          # Dependencies and scripts
├── Taskfile.yml          # Task automation
├── _quarto.yml           # Site configuration
├── tsconfig.json         # TypeScript configuration
└── eslint.config.mjs     # Linting configuration
```

## Quick Start

1. **Clone the repository**:

   ```bash
   git clone https://github.com/FallenDeity/gemini-ts-cookbook
   cd gemini-ts-cookbook
   ```

2. **Install dependencies**:

   ```bash
   yarn install
   ```

3. **Set up environment**:

   ```bash
   cp .env.example .env
   # Add your Gemini API key to .env file
   ```

4. **Start exploring**:

   Open `quickstarts/Get_started.ipynb` in Vs Code, or any Jupyter-compatible environment and select the TypeScript kernel.

## Prerequisites

- **Node.js** 18+ and yarn
- **Python** 3.8+ (for Jupyter and scripts)
- **tslab** (TypeScript Jupyter kernel) - [Installation Guide](https://github.com/yunabe/tslab)
- **Gemini API Key** from [Google AI Studio](https://aistudio.google.com/app/apikey)
- **Task** (optional, for task automation) - [Installation Guide](https://taskfile.dev/installation/)

## Installation

### 1. Install Node.js Dependencies

```bash
yarn install
```

### 2. Install TypeScript Jupyter Kernel

```bash
# Make sure you have Jupyter Notebook or Jupyter Lab installed
npm install -g tslab
tslab install
```

#### 2.1. Verify Installation

You can verify if the kernel is installed correctly by running:

```bash
jupyter kernelspec list
```

### 3. Install Python Dependencies (for tooling)

```bash
python3 -m venv venv
source venv/bin/activate  # On Windows use `venv\Scripts\activate`
pip install -r scripts/requirements.txt
pre-commit install # Install pre-commit hooks
```

### 4. Install Task Runner (Optional)

```bash
# macOS
brew install go-task

# Linux
sh -c "$(curl --location https://taskfile.dev/install.sh)" -- -d -b ~/.local/bin

# Windows
choco install go-task
```

### 5. Set Up Environment Variables

Create a `.env` file in the root directory and add your Gemini API key:

```bash
GEMINI_API_KEY=your_gemini_api_key_here
```

## Usage

### Running Notebooks

Open the notebooks in your preferred Jupyter environment (e.g., Jupyter Lab, Vs Code with Jupyter extension) and select the TypeScript kernel. You can execute the cells interactively.

### Key Notebooks to Start With

| Notebook                             | Description                           |
| ------------------------------------ | ------------------------------------- |
| `quickstarts/Get_started.ipynb`      | Essential first steps with Gemini API |
| `quickstarts/Function_calling.ipynb` | Learn to create AI agents with tools  |
| `quickstarts/Embeddings.ipynb`       | Text similarity and semantic search   |
| `examples/Browser_as_a_tool.ipynb`   | Web automation with AI                |
| `examples/Voice_memos.ipynb`         | Audio processing and transcription    |

## Available Tasks

This project uses [Task](https://taskfile.dev/) for automation. Here are the key commands:

### Notebook Operations

```bash
task format_notebooks        # Format all notebooks with Prettier
task lint_notebooks          # Lint TypeScript code in notebooks
task notebooks               # Format and lint notebooks
task compile_notebooks_check # Compile TS cells to check for errors
```

### Development Tasks

```bash
task format_scripts         # Format Python scripts
task lint_scripts           # Lint Python scripts
```

### Differential Operations

```bash
task format_notebooks -- --diff    # Format only changed notebooks
task lint_notebooks -- --diff      # Lint only changed notebooks
```

## Notebooks

### Quickstarts (Learning Path)

| Category        | Notebooks                                               |
| --------------- | ------------------------------------------------------- |
| **Basics**      | Get_started, Models, Prompting, System_instructions     |
| **Multimodal**  | Audio, Video_understanding, Spatial_understanding       |
| **Advanced**    | Function_calling, Embeddings, Code_Execution, Streaming |
| **Specialized** | LiveAPI, TTS, Grounding, Safety                         |

### Examples (Practical Applications)

| Use Case                | Notebooks                                                     |
| ----------------------- | ------------------------------------------------------------- |
| **AI Agents**           | Agents_Function_Calling_Barista_Bot, Browser_as_a_tool        |
| **Data Analysis**       | Anomaly_detection_with_embeddings, Working_with_Charts_Graphs |
| **Content Creation**    | Story_Writing_with_Prompt_Chaining, Market_a_Jet_Backpack     |
| **Document Processing** | Pdf_structured_outputs, Talk_to_documents_with_embeddings     |
| **Search & Research**   | Search_Wikipedia_using_ReAct, Opossum_search                  |

## Building the Site

The project uses [Quarto](https://quarto.org/) to generate a static documentation website:

### Install Quarto

```bash
# Install Quarto
# Visit https://quarto.org/docs/get-started/ for installation instructions
```

### Build Process

```bash
# Build the static site
quarto render

# Preview locally
quarto preview

# The built site will be in the build/ directory
```

### Deployment

The site is automatically deployed to GitHub Pages when changes are pushed to the main branch. You can view the live documentation at: [https://fallendeity.github.io/gemini-ts-cookbook](https://fallendeity.github.io/gemini-ts-cookbook)

## Contributing

We welcome contributions! Here's how you can help:

### Adding New Examples

1. Create a new notebook in the appropriate directory (`quickstarts/` or `examples/`)
2. Follow the existing naming convention
3. Include proper documentation and comments
4. Test your code thoroughly
5. Format and lint your notebooks and run all relevant checks:

   ```bash
   pre-commit run --all-files
   ```

### Submitting Changes

1. Fork the repository
2. Create a feature branch: `git checkout -b feature-name`
3. Make your changes and test thoroughly
4. Run formatting and linting and other checks: `pre-commit run --all-files`
5. Commit with clear messages
6. Push and create a Pull Request

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Related Resources

- [Gemini API Documentation](https://ai.google.dev/gemini-api/docs)
- [Google AI Studio](https://aistudio.google.com/)
- [TypeScript Documentation](https://www.typescriptlang.org/docs/)
- [Jupyter Notebook Documentation](https://jupyter-notebook.readthedocs.io/)
