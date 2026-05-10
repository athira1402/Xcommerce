# 🛒 Multi-Portal XCommerce

A semantic web–based e-commerce integration project that unifies product data from multiple partner portals (e.g., Amazon, Flipkart, Myntra) into a single queryable knowledge graph using **RDF, OWL ontologies, Fuseki, and SPARQL**.

---

## 🚀 Features
- **Unified Ontology**: Core schema (`multi-portal-xcommerce`) defines `Product`, `Seller`, `Offer`, `Furniture`, `Electronics`, etc.
- **Partner Integration**: Partner RDF files are mapped to the unified schema using `owl:equivalentClass` and `owl:equivalentProperty`.
- **SPARQL Search API**: Spring Boot controller builds dynamic SPARQL queries based on category, sub-category, and attributes.
- **Attribute Filtering**: Supports filters like brand, color, material, battery life, RAM, display size, etc.
- **Offer Handling**: Queries include active offers with start/end dates and discounts.
- **Extensible**: New categories and attributes can be added via ontology and mapping files.

---

## 🧩 Architecture
1. **Ontology Layer**  
   - Unified schema (`multi-portal-xcommerce.owl`)  
   - Mapping ontologies align partner vocabularies (`owl:equivalentClass`, `owl:equivalentProperty`)

2. **Data Layer**  
   - Partner RDF files uploaded to Fuseki  
   - Stored in named graphs (`urn:partner:<id>`)

3. **Reasoning Layer**  
   - OWL reasoner can be plugged in for:  
     - Consistency checking  
     - Subclass inference  
     - Equivalence resolution  

4. **Application Layer**  
   - Spring Boot REST API (`ProductsController`)  
   - Endpoints:
     - `/products/search` → search products with filters  
     - `/products/filter-options` → get available filter values  

---

## 📦 Tech Stack
- **Java 17 + Spring Boot**
- **Apache Jena Fuseki** (SPARQL endpoint)
- **OWL Ontologies** (semantic schema + mappings)
- **H2 Database** (in-memory, demo setup)
- **SPARQL** (query language for RDF)

---

## ⚙️ Installation & Access

1. **Clone the repository**:
   ```bash
   git clone https://github.com/<your-repo>/multi-portal-xcommerce.git

2. **Search Products**
   Go to: http://localhost:8080
   
3. **Query Apache Jena Fuseki**
   Go to: http://localhost:3030
