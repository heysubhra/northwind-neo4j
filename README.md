
# Northwind Recommendations using Neo4j

## Project Description

This project aims to demonstrate how to leverage Neo4j and Graph Analytics to create a product recommendation system. The project consists of the following steps:

**1. Setting up of Northwind GraphQL API**: Importing [Northwind Dataset](#dataset-source) to Postgres and exposing GraphQL API's using [Hasura](https://hasura.io/).

**2. Exporting data from GraphQL API**: Building REST APIs in [Hasura](https://hasura.io/) using GraphQL queries to respond Nodes and Edges.

**3. Creating CSV Nodes and Edges from GraphQL endpoints**: Creating CSVs from the above responses and saving them to disk using [Pandas](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.to_csv.html).

**4. Import Nodes and Edges** into Neo4j: Importing the Nodes and Edges CSV using Cypher’s LOAD CSV

**5. Create Product Ratings (Edge)**: Creating product ratings from order history of a client using Cypher 

**6. Creating Similarity** among Customers: Once product ratings are assigned, the next step is to create similarity among customers. This can be done using Neo4j's [Graph Data Science plugin](https://neo4j.com/product/graph-data-science/).

**7. Recommending Product** to a customer based on similarity search.

Please use **Python version 3.9**

// To fight writers block and to finish this description section I used a LLM : ) 



## Details about Files in the repository:
    
1. [docker-compose.yaml](./docker-compose.yml) - Docker Compose file that includes the Image names , Port and Environment details to set up the environment in Mac.

2. [northwind_pg.sql](./sql/northwind_pg.sql) - Creates the table structure  and populates the Northwind Dataset for more details please refer to [Dataset Source](#dataset-source)

3. [hasura_metadata.json](./hasura_metadata.json) - Contains metadata for [Hasura](https://hasura.io/), it creates the required relationships to query Edges in Graphql, For more details refer  

4. [query.graphql](./query.graphql) - Contains the GraphQL queries to obtain Nodes and Edges from the Database

5. [ETL Notebook](./northwind_neo4j_graphql_etl.ipynb) - Contains Scripts for Extracting Nodes and Edges using GraphQL queries

6. [Recommendations Notebook](./northwind_neo4j_recommendation.ipynb) - Contains Scripts for finding similarities among customers and recommending products based on purchases of neighbours.

## Dataset Source:

- [Database Examples/Northwind/PostgreSQL - Wikiversity](https://en.wikiversity.org/wiki/Database_Examples/Northwind/PostgreSQL)



## References:

1. [Tutorial: Import Relational Data Into Neo4j - Developer Guides](https://neo4j.com/developer/guide-importing-data-and-etl/) 

2. [Northwind Recommendation Engine - graphgists](https://neo4j.com/graphgists/northwind-recommendation-engine/)


3. [Node Similarity - Neo4j Graph Data Science](https://neo4j.com/docs/graph-data-science/current/algorithms/node-similarity/)  

4. [K-Nearest Neighbors - Neo4j Graph Data Science](https://neo4j.com/docs/graph-data-science/current/algorithms/knn/)

5. [FastRP and kNN example - Neo4j Graph Data Science](https://neo4j.com/docs/graph-data-science/current/end-to-end-examples/fastrp-knn-example/)



