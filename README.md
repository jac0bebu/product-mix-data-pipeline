# Product Mix & Clustering: SSIS Data Warehouse ETL Pipeline

This project demonstrates how to build a **Data Warehouse ETL pipeline** using **SQL Server Integration Services (SSIS)**.  
It focuses on analyzing **Product Mix**, which includes 3 dimensions of product by extracting data, transforming it, and loading it into a **Star Schema** Data Warehouse.

---

## **Overview**

The goal of this project is to execute a full **ETL (Extract, Transform, Load)** process for data mining and reporting.  
Data is loaded from multiple sources, cleaned in SSIS, and stored in **Fact** and **Dimension** tables to support:
* **Product Mix Analysis:** Understanding product contribution to revenue.
* **Clustering:** Grouping markets based on behavior.

---

## **Architecture**

The solution follows four main layers:

1.  **Source Layer** – Raw data from flat files (`.csv`) and OLTP databases.
2.  **Staging Layer** – Temporary area for initial data load and cleanup.
3.  **Data Warehouse Layer** – Transformed data organized into Facts (e.g., `FactProductMarket`) and Dimensions.
4.  **Presentation Layer** – Visualization in  Power BI.

---

## **ETL Process**

1.  **Extract:** Load raw data from transaction databases CompanyX.
2.  **Transform:** * Apply cleaning and business rules.
    * Perform Data Mining/Clustering logic.
3.  **Load:** Insert data into the warehouse tables using SSIS packages (e.g., `Monthly_Load.dtsx`).

---

## **Project Structure**

```text
product-mix-and-clustering/
│
├── data-warehouse/             # .bak backup files of the Datawarehouse
│   └── ProductMixDWH.bak
│
├── product-mix-and-clustering/ # Main SSIS Solution files
│   ├── Monthly_Load.dtsx       # Data loading package
│   ├── Package.dtsx            # Main ETL workflow
│   ├── data-mining/            # Extract data for data mining process
│   └── market-cluster/         # Data mining result
│
├── report/                     # Project documentation and analysis reports
│
├── .gitignore                  # Git ignore rules
└── README.md                   # Project documentation
