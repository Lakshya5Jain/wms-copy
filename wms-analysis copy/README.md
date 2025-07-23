# WMS Analysis Project for Look Optic Eyewear

## Overview
This project performs comprehensive warehouse management system (WMS) analysis for **Look Optic**, an eyewear company specializing in progressive glasses, reading glasses, blue-light blocking glasses, and eyewear accessories. The analysis uses advanced data science and machine learning techniques to optimize inventory management, understand sales patterns, and provide actionable business insights for the eyewear retail operation.

## Business Context: Look Optic
Look Optic is an eyewear retailer offering a diverse catalog of prescription and non-prescription glasses including:
- **Progressive Lenses**: Multi-focal glasses for presbyopia correction
- **Reading Glasses**: Single-vision magnification glasses for close-up work
- **Blue-Light Glasses**: Computer and digital device protection eyewear
- **Eyewear Accessories**: Cases, cleaning cloths, catalogs, and related products

The company operates with 1,267 unique SKUs across multiple brands (Cosmo, Laurel, Muse, Abbey, Summit, etc.) with various color combinations, prescription strengths, and lens types.

## Dataset Description

### Core Business Data Files (Required)
1. **`products.csv`** (1,267 products) - Complete product catalog with SKU names, IDs, and specifications
2. **`inventory.csv`** (1,267 records) - Real-time inventory levels including on-hand, committed, fulfillable quantities
3. **`orders.csv`** (135,011 orders) - Complete order transaction history from Oct 2023 - July 2024
4. **`orders_line_items.csv`** (192,616 line items) - Individual product-level order details with quantities and pricing
5. **`inbound_shipments.csv`** (31 shipments) - Inbound inventory receipts and replenishment records
6. **`shipping_methods.csv`** (297 methods) - Available shipping and fulfillment options
7. **`suppliers.csv`** (4 suppliers) - Supplier and vendor information

### Generated Analysis Files
- **`sku_data.pkl`** - Enriched SKU dataset with 34+ calculated metrics (saved as pickle for faster loading)
- **`sku_name_embeddings.pkl`** - Pre-computed semantic embeddings for product names using OpenAI embeddings

## Main Analysis Workflow

### 1. **`PrepareData.ipynb`** - Data Preparation for AI Analysis
**Purpose**: Advanced data engineering and feature engineering to create a comprehensive dataset optimized for machine learning and AI analysis.

**Key Features**:
- **34 Sophisticated Metrics**: Including inventory intelligence, sales velocity engineering, and sales pattern analysis
- **Historical Inventory Reconstruction**: Calculates inventory levels 3 and 6 months ago using sales and receipt data
- **Sales Velocity Calculations**: Multiple velocity metrics (30d, 90d, overall) for demand forecasting
- **Sales Pattern Analysis**: Time to first sale, latest sale age, max/min daily sales, and detailed order history
- **Data Structure Optimization**: Logical column reordering and robust error handling

**Output**: `sku_data.pkl` - A comprehensive, analysis-ready dataset with 1,267 SKUs and 34 engineered features.

### 2. **`AiAnalysis.ipynb`** - **MAIN AUTOMATED AI WORKFLOW** (Generalized & Fully Automated)
**Purpose**: The primary automated AI analysis pipeline that combines multiple machine learning techniques into a unified, generalized workflow for comprehensive product intelligence and business optimization.

**Key Features**:
- **Fully Automated Execution**: Complete end-to-end analysis requiring minimal manual intervention
- **Hierarchical Clustering Analysis**: Multi-level product categorization using advanced clustering algorithms
- **GPT-Powered Product Attribute Extraction**: Automated extraction of product attributes from text descriptions
- **Multi-Modal Feature Engineering**: Combines semantic embeddings, numerical features, and extracted attributes
- **Automated Business Intelligence**: Smart inventory recommendations, predictive analytics, and anomaly detection
- **Cross-Domain Applicability**: Designed to work with any retail/e-commerce dataset beyond Look Optic

**Output**: Comprehensive automated analysis including product clusters, performance predictions, inventory recommendations, and strategic business insights.

## Supporting Analysis Files
- **`EDA.ipynb`**: Basic exploratory data analysis on Look Optic sales and inventory patterns
- **`EmbeddingsAnalysis.ipynb`**: Manual clustering analysis using semantic embeddings and K-means
- **`ReadData.ipynb`**: Data loading and initial processing with date parsing and validation

## Key Business Insights

### Top Performing Products
- **CO70PTPE15** (Cosmo Progressives Taupe 1.5) - 4,859 units sold - Top revenue generator
- **CO70PTPE20** (Cosmo Progressives Taupe 2) - 3,391 units - Strong prescription demand
- **LA40PTOR15** (Laurel Progressives Tortoise 1.5) - 3,198 units - Classic color popularity

### Product Performance Patterns
- **Progressives**: Dominate sales volume, representing Look Optic's core competency
- **Popular Colors**: Tortoise, Champagne, Taupe showing strongest market preference
- **Prescription Strengths**: 1.5 and 2.0 strength showing highest demand
- **Brand Performance**: Cosmo and Laurel brands leading in sales volume

## Running the Analysis

### Prerequisites
```bash
# Install dependencies
pip install -r requirements.txt

# Set up OpenAI API key for AI analysis
export OPENAI_API_KEY="your-api-key-here"
```

### Main Workflow (Recommended)
1. **Data Setup**: Place all CSV files in the project root directory
2. **Data Preparation**: Run `PrepareData.ipynb` to generate enriched dataset
3. **AI Analysis**: Run `AiAnalysis.ipynb` for comprehensive automated analysis

### Full Analysis (Optional)
For additional exploratory analysis, you can also run:
- `EDA.ipynb` for basic data exploration
- `EmbeddingsAnalysis.ipynb` for manual clustering analysis

### Output Files
- **`sku_data.pkl`**: Comprehensive dataset with all calculated metrics
- **`sku_name_embeddings.pkl`**: Semantic embeddings for product names
- **Analysis Results**: Automated cluster assignments, performance metrics, and business recommendations

## Technical Stack
- **Data Processing**: pandas, numpy for data manipulation
- **Machine Learning**: scikit-learn, sentence-transformers for clustering and embeddings
- **AI/NLP**: openai, transformers for advanced language processing
- **Visualization**: matplotlib, seaborn, plotly for data visualization
- **Environment**: Jupyter notebooks with Python 3.12+ in virtual environment

## Business Applications
- **Inventory Optimization**: Data-driven reorder points and stock level recommendations
- **Product Strategy**: Performance-based product portfolio optimization
- **Sales Forecasting**: Velocity-based demand prediction and planning
- **Operational Efficiency**: Automated analysis pipeline for continuous business intelligence

---

**Note**: This analysis provides Look Optic with actionable insights for inventory optimization, product strategy, and operational efficiency in the competitive eyewear market. The combination of traditional business analytics with modern AI techniques offers a comprehensive view of business performance and opportunities.