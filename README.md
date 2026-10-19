# Oracle to Snowflake Streaming Data Pipeline

A hands-on data engineering project demonstrating near-real-time change data capture (CDC) from Oracle AI Database 26ai Free to Snowflake using Snowflake Openflow, subject to source compatibility and licensing validation.

## Objectives

- Generate continuous sales transactions in Oracle.
- Capture inserts, updates, and deletes through a supported CDC mechanism.
- Deliver source changes to Snowflake with seconds-level freshness as a target SLO.
- Build landing, staging, and curated data layers.
- Validate data quality, reconciliation, monitoring, and recovery.

## Architecture

Oracle AI Database 26ai Free → XStream CDC → Snowflake Openflow → Snowflake landing → staging → curated sales data.

The architecture depends on confirming Oracle Free/XStream eligibility, licensing, connector prerequisites, and secure network connectivity before enabling CDC.

## Technology Stack

- Oracle AI Database 26ai Free
- Python 3.12
- uv
- python-oracledb
- Snowflake
- Snowflake Openflow Connector for Oracle
- SQL
- pytest
- Git and GitHub

## Repository Structure

- `docs/` — Architecture, setup, monitoring, and recovery documentation
- `oracle/` — Oracle schema, setup, and validation scripts
- `generator/` — Synthetic sales transaction generator
- `snowflake/landing/` — Landing-layer configuration and scripts
- `snowflake/staging/` — Data preparation and deduplication
- `snowflake/curated/` — Business-ready sales data
- `snowflake/validation/` — Source-to-target reconciliation
- `tests/` — Automated tests

## Implementation Status

1. [x] Repository initialized
2. [x] Python environment initialized
3. [ ] Oracle schema and source inventory verified
4. [ ] CDC licensing and compatibility validated
5. [ ] Synthetic sales workload tested
6. [ ] Openflow connectivity configured
7. [ ] Initial snapshot and continuous CDC validated
8. [ ] Reconciliation, latency, and recovery tests completed

## Safety and Cost Controls

- Do not commit passwords, tokens, private keys, or connection secrets.
- Do not expose Oracle directly to the public internet.
- Do not provision Snowflake resources or start billable services without explicit approval.
- Treat seconds-level freshness as a measured objective, not a guarantee.

## Development Environment

Create and activate the virtual environment:

```bash
uv venv
source .venv/bin/activate
uv add oracledb
uv add --dev pytest
```

## Project Goal

Build a reproducible, observable, and recoverable Oracle-to-Snowflake streaming pipeline that demonstrates practical CDC and production-oriented data engineering principles.
