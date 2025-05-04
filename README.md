# Pharmaceutical Sales Analytics dbt Documentation

This repository contains a dbt (data build tool) project for pharmaceutical sales analytics with enhanced documentation.

## Overview

This dbt project provides a comprehensive analytics framework for pharmaceutical sales data. It transforms raw data from operational systems into analytical models that enable insights into healthcare professional (HCP) engagement, prescription patterns, and sales performance.

## Project Structure

The data transformation logic follows a multi-layered approach:

- **Sources**: Raw data from operational systems loaded into Snowflake
- **Staging Models**: Clean and standardized representations of source data
- **Intermediate Models**: Enriched entities combining data from multiple sources
- **Marts Models**: Business-oriented analytics models for reporting

## Documentation Features

This project demonstrates several advanced dbt documentation techniques:

1. **Custom Homepage**: A detailed homepage that provides project context and links to resources
2. **DRY Documentation**: Reusable documentation blocks using `doc()` macros
3. **Rich Metadata**: Detailed metadata for all models including ownership, update frequency, etc.
4. **Color-Coded Visualization**: Different colors for each model layer in the DAG
5. **Enhanced Seed Documentation**: Comprehensive documentation for seed files with business context

## Getting Started

### Prerequisites
- Snowflake account
- Python 3.8 or higher
- dbt CLI or dbt Cloud

### Setup
1. Clone this repository
2. Configure the profile in `profiles.yml` with your Snowflake credentials
3. Install dependencies: `pip install -r requirements.txt`
4. Install dbt packages: `dbt deps`
5. Generate documentation: `dbt docs generate`
6. View documentation: `dbt docs serve`

## Key Models

- **Fact Tables**: `fct_prescriptions`, `fct_visits`
- **Dimension Tables**: `dim_hcp`
- **Seeds**: Reference data for HCPs, products, territories, etc.

## Contact

For questions or support, contact data-analytics@your-company.com. 