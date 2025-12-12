**1. Purpose & Scope**

### **Purpose**

The purpose of this project is to design and analyze a PostgreSQL-based sales data warehouse in order to generate reliable, reproducible business insights from raw transactional data.

### **In Scope**

- Ingesting raw sales data into PostgreSQL
- Designing a structured schema using a layered approach (staging → core → analytics)
- Applying data quality checks, validations, and basic constraints
- Producing SQL-based analytical queries
- Analyzing data using Python for exploratory analysis, statistics, and visualisation
- Applying basic statistical methods to support and validate business insights
- Building a lightweight analytical application (e.g. Streamlit) for interactive data exploration
- Automating repeatable analysis and data refresh tasks using Python scripts
- Defining and calculating core business metrics such as revenue, order volume, average order value, and customer value
- Supporting downstream reporting and dashboards
- Documenting modeling, analytical, security, and design decisions

### **Out of Scope**

- Real-time or streaming data pipelines
- Enterprise-scale orchestration (e.g. Airflow)
- Cloud production infrastructure and managed data platforms
- High-availability or SLA-driven systems
- Customer-facing production applications
- Advanced cloud data platforms and transformation frameworks (addressed in separate, dedicated projects)

### **Non-Goals**

This project does not aim to optimise for maximum performance, scale, or cost efficiency beyond what is required for correct and reliable analysis.

---

## **2. Business Questions**

This project aims to answer business-relevant questions such as:

- How do sales, revenue, and order volume evolve over time?
- Which customers and products generate the most value?
- How does performance vary by geography and product category?
- What trends or seasonality patterns are present in the data?
- Where do data quality or completeness issues impact analytical confidence?

---

## **3. Stakeholders & Users**

- **Primary user:** Data Analyst / Analytics Engineer (project owner)
- **Secondary users:** Business stakeholders (Sales, Operations, Management)
- **External audience:** Recruiters and hiring managers reviewing the portfolio project

---

## **4. Data Sources**

- Raw transactional sales data provided as CSV files
- Supporting reference datasets such as customers, products, and geographic information

All data is treated as **non-production, educational data**.

---

## **5. Data Modeling Approach**

The database follows a layered warehouse-style structure:

- **Staging layer:**
    
    1:1 copies of raw source tables, preserving original structure and values.
    
- **Core layer:**
    
    Cleaned, validated, and normalized business entities with clearly defined keys and relationships.
    
- **Analytics layer:**
    
    Denormalized, analysis-ready tables optimized for querying and reporting.
    

Modeling decisions prioritize:

- Clarity and correctness
- Analytical usability
- Reproducibility over premature optimization

All transformations are implemented using **version-controlled SQL and scripts**, ensuring the entire database can be recreated from raw data in a repeatable and auditable way.

---

## **6. Tooling & Technology**

- **Database:** PostgreSQL
- **SQL Interface:** psql (CLI)
- **Development Environment:** VS Code
- **Database Inspection:** DBeaver
- **Analysis & Automation:** Python
- **Version Control:** Git + GitHub
- **Project Management & Documentation:** Notion

Version control is used to track **schema changes, analytical logic, and documentation updates** throughout the project.

Additional tools (e.g. Power BI, Streamlit) are added only when they are actively used and documented accordingly.

---

## **7. Data Quality & Validation**

The project includes:

- Basic data profiling and exploratory checks
- Validation of primary and foreign keys where appropriate
- Null and range checks on critical fields
- Explicit documentation of known data limitations and assumptions

---

## **8. Security & GDPR Considerations**

- No real personal data is processed
- All data is treated as potentially sensitive by default
- Access is restricted to the local development environment
- Credentials and secrets are never committed to version control

GDPR-aligned principles applied:

- Data minimization
- Purpose limitation
- Documentation of assumptions and safeguards

---

## **9. Success Criteria**

The project is considered successful when:

- The database schema is clearly structured and fully documented
- Analytical queries return consistent, explainable results
- Core business metrics can be calculated reliably
- The full pipeline can be recreated from raw data using documented steps
- All major technical and analytical decisions are documented
- A third party can understand and review the project end-to-end

The project is expected to evolve iteratively as new questions arise, with changes documented and version-controlled.

---

## **10. Assumptions & Risks**

### **Assumptions**

- Source data is representative of typical sales workflows
- Data volume is suitable for local PostgreSQL analysis

### **Risks**

- Incomplete or inconsistent source data
- Over-engineering beyond analytical requirements

These risks are mitigated through scoped design, documentation, and reproducible workflows.