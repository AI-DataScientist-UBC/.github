# AI-DataScientist-UBC
Welcome to the AI-DataScientist-UBC GitHub organization.

This `docs/README.md` is the organization-level entry point for the AI Data Scientist workspace. The codebase is split into two repositories that are developed together: a user-facing interface and orchestration layer, and a Python MCP backend that executes data-science operations.

The goal of this document is to explain how the two repos fit together without repeating the repo-specific setup details, environment tables, or internal file maps that already live in each repository README.

## Repository Map

| Repository | Purpose | Owns |
| --- | --- | --- |
| [`AI-DataScientist-Interface`](https://github.com/AI-DataScientist-UBC/AI-DataScientist-Interface) | Frontend application and orchestration layer | Chat experience, project and dataset workflows, LLM-driven orchestration, insight presentation |
| [`DATA-SCIENCE-MCP`](https://github.com/AI-DataScientist-UBC/DATA-SCIENCE-MCP) | MCP backend for data-science execution | Data cleaning, aggregation, preprocessing, feature engineering, model training, and MCP tool exposure |

## How the System Fits Together

1. A user interacts with the platform through the interface in [`AI-DataScientist-Interface`](https://github.com/AI-DataScientist-UBC/AI-DataScientist-Interface).
2. The interface collects the prompt, project context, and dataset information.
3. The orchestration layer decides what work needs to be done and calls the MCP backend.
4. [`DATA-SCIENCE-MCP`](https://github.com/AI-DataScientist-UBC/DATA-SCIENCE-MCP) executes the requested data-science tools and returns structured results.
5. The interface turns those results into chat responses, tables, charts, and prediction explanations for the user.

At a high level, the interface is responsible for experience and coordination, while the MCP repo is responsible for reliable execution of the underlying analytics and modeling tasks.

## Shared Platform Dependencies

- **MongoDB** is used for persisted project and dataset state.
- **An LLM provider** powers the natural-language orchestration experience in the interface.
- **MCP over HTTP/JSON-RPC** is the contract between the interface and the backend.

## Working Across the Repositories

If you are contributing to this workspace, use this rule of thumb:

- Work in [`AI-DataScientist-Interface`](https://github.com/AI-DataScientist-UBC/AI-DataScientist-Interface) when the change affects UI, user workflows, orchestration behavior, or presentation of results.
- Work in [`DATA-SCIENCE-MCP`](https://github.com/AI-DataScientist-UBC/DATA-SCIENCE-MCP) when the change affects data processing, tool behavior, modeling, or MCP server capabilities.
- Touch both when a user-facing feature requires new backend tool support or a change to the interface-backend contract.

For detailed setup, scripts, and environment variables, use the repo-level READMEs:

- [`AI-DataScientist-Interface/README.md`](https://github.com/AI-DataScientist-UBC/AI-DataScientist-Interface/blob/main/README.md)
- [`DATA-SCIENCE-MCP/README.md`](https://github.com/AI-DataScientist-UBC/DATA-SCIENCE-MCP/blob/main/README.md)

## Quick Start

The two repos are intended to run together:

1. Start the MCP backend from [`DATA-SCIENCE-MCP`](https://github.com/AI-DataScientist-UBC/DATA-SCIENCE-MCP).
2. Start the frontend from [`AI-DataScientist-Interface`](https://github.com/AI-DataScientist-UBC/AI-DataScientist-Interface).
3. Open `http://localhost:3000` and use the interface against the backend endpoint exposed at `http://localhost:9000/mcp`.

Follow the README in each repo for exact install and environment setup steps.

## Demo Video


https://github.com/user-attachments/assets/5ae5e8e2-88c0-4990-9a3e-de8f7061cd70



