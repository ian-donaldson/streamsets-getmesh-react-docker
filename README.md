# streamsets-getmesh-react-docker
This repository contains a docker file to spin up an open source graph DB headless CMS (Getmesh or Gentics Mesh) supported by an open source middleware (Streamsets) for the business and integration logic and powering a React Web App (eventually PWA).  All of these items are required in the same docker container in order to reduce network traffic between these elements.

React App frontend <-> Getmesh CMS <-> Streamsets middleware <-> Required data integrations (including front-end custom API functions)

The entire docker container is designed to be scalable for high demand websites.  Since not all business logic and integrations needs to be multiplied at scale and isn't required on every container, a separate Backend node container is intended to be used when designed in the future.

The Getmesh CMS utilises a GraphDB (OrientDB) and this will be separated from these containers so that the database is a separately scalable entity that is connected to the CMS in each container.  Getmesh also has Neo4j graph database on it's roadmap which would be preferred due to it's ability to attach data to relationships as well as nodes in the graph.  For now, OrientDB will do fine.  Both OrientDB and Neo4j can be accessed directly by Streamsets using the JDBC connector.

