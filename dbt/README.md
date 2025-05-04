# Airflow DBT Snowflake Analytics Project

## Overview
This project provides a comprehensive analytics framework for pharmaceutical sales data using dbt (data build tool) with Snowflake as the data warehouse. It is designed to be orchestrated by Airflow for automated data pipelines and transformations.

## Project Structure
The data transformation logic follows the standard dbt project structure with a multi-layered approach:

### Sources
Raw data from operational systems loaded into Snowflake:
- Healthcare professionals (HCPs)
- Prescriptions
- Medical representatives
- Products
- Territories
- HCP visits
- Daily sales

### Models
The project follows a layered transformation approach:

#### Staging (`models/staging/`)
- Basic transformations and standardizations of source data
- One-to-one mappings with source tables
- Data cleaning and type casting

#### Intermediate (`models/intermediate/`)
- Combines and transforms staging models
- Creates enriched entities with business logic
- Prepares data for the marts layer

#### Marts (`models/marts/`)
- Business-focused models for analytics and reporting
- Fact tables: `fct_prescriptions`, `fct_visits`
- Dimension tables: `dim_hcp`

### Seeds
Reference data loaded directly into the data warehouse:
- Products catalog
- HCP master data
- Territory definitions

## Data Lineage

```
Sources                 Staging                  Intermediate               Marts
---------               --------                 -------------              -----
public.hcp_master   --> stg_hcp              --> int_hcp_enriched      --> dim_hcp
public.territories  --> stg_territories      --↗
                                                ↘
public.hcp_visits   --> stg_hcp_visits       --> int_hcp_visits_enriched --> fct_visits
public.medical_reps --> stg_medical_reps     --↗
                                                 
public.prescriptions --> stg_prescriptions   --> int_prescriptions_enriched --> fct_prescriptions
public.products     --> stg_products         --↗
```

## Key Metrics and KPIs
- Prescription volume by HCP, product, territory
- Estimated revenue and performance against targets
- HCP visit frequency and engagement scores
- Territory performance analysis
- HCP segmentation and targeting

## Getting Started

### Prerequisites
- Snowflake account
- Python 3.8 or higher
- dbt CLI or dbt Cloud

### Setup
1. Clone this repository
2. Configure the profile in `profiles.yml` with your Snowflake credentials
3. Install dependencies with `dbt deps`
4. Run the models with `dbt run`
5. Generate documentation with `dbt docs generate`
6. View documentation with `dbt docs serve`

### Profiles Configuration
The project requires the following Snowflake connection parameters:
- account
- user
- password
- role
- database
- warehouse
- schema

## Execution Flow
1. Run seeds: `dbt seed`
2. Run models: `dbt run`
3. Run tests: `dbt test`
4. Generate docs: `dbt docs generate`

## Using with Airflow
This project is designed to be orchestrated with Airflow. A typical DAG structure would:
1. Load raw data to Snowflake
2. Run dbt seeds if needed
3. Run dbt models
4. Run dbt tests
5. Generate documentation
6. Send notifications of successful runs

## Documentation
Comprehensive documentation is generated using dbt's built-in documentation capabilities:
- Table and column descriptions
- Data lineage visualization
- Model code
- Test coverage

## Project Owners and Stakeholders
- Data Engineering: Responsible for pipeline maintenance and optimization
- Sales Operations: Primary users of visit analytics
- Commercial Analytics: Primary users of prescription and revenue metrics
- Master Data Management: Responsible for HCP and territory data quality

## License
This project is licensed under the MIT License - see the LICENSE file for details. 