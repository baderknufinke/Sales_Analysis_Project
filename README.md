README.md 
## Reproducibility & Local Setup

📄 Practical clone-and-run instructions are documented in [REMOTE_REPO_SETUP.md](REMOTE_REPO_SETUP.md).


This project is fully reproducible. Internal developer notes covering local setup, daily restart, and database rebuild steps are documented separately and kept outside recruiter-facing documentation.

## Project Design Decisions

### Orchestration
This project intentionally avoids automated orchestration to prioritise transparency, reproducibility, and debuggability, while keeping all transformations fully script-based and ready for future automation.

## Documentation Overview

This project separates **execution documentation** from **reasoning and planning documentation** to ensure clarity, reproducibility, and professional reviewability.

### Core Repository Documentation

- **README.md**  
  Project overview, scope, architecture, and key design decisions. Serves as the primary entry point for reviewers.

- **BDR (Business & Data Requirements)**  
  Defines the business questions, success criteria, constraints, and data requirements before implementation.

- **data_dictionary.md**  
  Technical reference of database tables, columns, data types, primary keys, and relationships. Source of truth for the physical schema.

- **setup.sql**  
  Executable SQL script used to deterministically recreate schemas, tables, and core database structures.

- **NOTES.md**  
  Development log capturing decisions, trade-offs, assumptions, and implementation notes made during the project.

- **Version Control (Git)**  
  Provides traceability and auditability through incremental, documented commits.

### Notion Documentation

- **Business Data Dictionary**  
  Business definitions, metrics logic, assumptions, and analytical meaning of the data. Complements the technical schema without duplicating it.

- **Architecture**  
  High-level system design and data flow across layers (raw → staging → core → analytics).

- **Reproducibility & Developer Notes**  
  Step-by-step instructions to rebuild the environment and rerun the project from raw data to analytics outputs.

- **Security & GDPR Notes**  
  Documentation of data protection measures, access controls, anonymisation decisions, and compliance considerations.

- **Project Management (Notion Board)**  
  Planning, progress tracking, and task management across project phases.

> **Note:** The repository serves as the source of truth for execution, while Notion serves as the source of truth for reasoning and decision-making.

## Project Scope & Intentional Exclusions

This flagship project intentionally focuses on data modeling, reproducibility, and analytical correctness.

To keep the data layer auditable and the scope controlled, the following capabilities are deliberately out of scope for this project:
- User authentication and role-based UI in the application
- Complex DAX measures or BI-side business logic in Power BI

These capabilities are intentionally deferred to later projects (PostgreSQL app extension and Snowflake + dbt + Power BI) where they can be demonstrated without duplicating or obscuring core data logic.

### Analytics Extensions

The following analytical extensions build on the same Olist data warehouse and core models, demonstrating reuse, scalability, and analytical depth without additional data ingestion.

- **Customer Segmentation**  
  RFM analysis, cohort analysis, retention, and customer lifetime value proxies.

- **Forecasting & Time-Series Analysis**  
  Demand forecasting, seasonality analysis, and trend decomposition on orders and revenue.

- **Pricing & Product Category Performance**  
  Price sensitivity proxies, category-level profitability, and margin trends.

- **Customer Funnel & Marketing Effectiveness (Proxy-Based)**  
  Funnel analysis, retention and reactivation patterns, cohort-based marketing effectiveness, and engagement proxies derived from transactional and behavioral data in the absence of raw campaign data.

### Metric Modeling Approach

Key business metrics are intentionally modeled upstream in SQL analytics tables rather than calculated ad hoc in the BI or application layer. This requires more upfront effort but ensures consistent definitions, auditability, reproducibility, and reuse across dashboards and downstream applications.

- Ensures a single source of truth for all business metrics  
- Prevents duplication and drift between dashboards and applications  
- Makes transformations auditable and version-controlled  
- Improves reproducibility and debugging  
- Keeps BI and application layers intentionally thin and portable