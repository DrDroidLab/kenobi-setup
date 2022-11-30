# Kenobi (by [Doctor Droid](https://drdroid.io))
Timestamped JSON Document Ingestion and auto visualization toolkit based on OpenSearch

## How to setup
Take a linux environment of your choice (Need to be accessible for HTTP traffic for accessing from browser on PUBLIC_IP) <br>
* If choosing a cloud provider, use a 4GB RAM, 2 vcpu machine, equivalent to t2.medium in AWS with 24GB of storage) and open the following ports: <br>
   - 8082: for accepting data from your application <br>
   - 5601: for connecting to the dashboards on your browser <br>
* Alternatively, you can run it on your local computer if it has minimum of 8GB RAM, a dual-core processor and 16GB storage.

### In your setup environment:
1. Install docker & docker-compose

2. Run this command in your choice of directory:<br>
``` wget https://raw.githubusercontent.com/DrDroidLab/kenobi-setup/main/docker-compose.yaml```

3. Setup kenobi by using docker compose <br>
``` docker-compose up -d ```

### In your application:
1. Install the Doctor Droid instrumentation & data forwarding package in your application environment using pip or pip3 (only supports >=3.6). See here for instructions on how to instrument your code -> https://docs.drdroid.io/docs/installation-steps<br>
`` pip install pycodemarker `` <br>

2. Run this to setup the host for your just setup toolkit <br>
`` export DRDROID_HOST=PUBLIC_IP``

3. Once your application starts taking traffic, visit ``http://PUBLIC_IP:5601/app/dashboards/`` for seeing metadata about all you have instrumented. Wait for a few minutes while kenobi understands your data and sets up the visualizations.
   - For credentials, use username -> admin, password -> admin
   - When logging in for the first time, choose 'Private' as the tenant. 
