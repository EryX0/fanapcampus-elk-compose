# Elastic and Kibana Dockerized Deployment

**I used [this elastic blog guide](https://www.elastic.co/blog/getting-started-with-the-elastic-stack-and-docker-compose) as a base refrence.**

## Deployment

1. Clone the repository and cd:

   ``` git
   git clone https://github.com/EryX0/fanapcampus-elk-compose.git && cd fanapcampus-elk-compose.git
   ```

2. Copy the env template provided

   ``` bash
   cp .env.template .env
   ```

3. Change contents of the `.env` file, the default is:

   ```env
    # Project namespace (defaults to the current folder name if not set)
    #COMPOSE_PROJECT_NAME=myproject
    
    
    # Password for the 'elastic' user (at least 6 characters)
    ELASTIC_PASSWORD=sampleelasticpass
    
    
    # Password for the 'kibana_system' user (at least 6 characters)
    KIBANA_PASSWORD=samplekibanapass
    
    
    # Version of Elastic products
    STACK_VERSION=8.0.1
    
    
    # Set the cluster name
    CLUSTER_NAME=docker-cluster
    
    
    # Set to 'basic' or 'trial' to automatically start the 30-day trial
    LICENSE=basic
    #LICENSE=trial
    
    
    # Port to expose Elasticsearch HTTP API to the host
    ES_PORT=9200
    
    
    # Port to expose Kibana to the host
    KIBANA_PORT=5601
    
    
    # # Increase or decrease based on the available host memory (in bytes)
    # ES_MEM_LIMIT=1073741824
    # KB_MEM_LIMIT=1073741824
    # LS_MEM_LIMIT=1073741824
    
    
    # SAMPLE Predefined Key only to be used in POC environments
    ENCRYPTION_KEY=c34d38b3a14956121ff2170e5030b471551370178f43e5626eec58b     04a30fae2
   ```

4. Run the Compose and wait for the magick. (usually takes 2~5 minutes to get up fully)

   ```Docker
   Docker compose up -d
   ```

5. Go to your browser and type this in the address bar:

   ```link
   localhost:5601
   ```

   then login with the **elastic** user and your specified **.env password**
