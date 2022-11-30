# kenobi-setup
Timestamped JSON Document Ingestion and auto visualization toolkit

## How to setup
1. Take a linux environment of your choice (with public IP/LB as VM_IP).
* If choosing a cloud provider, use a 4GB RAM, 2 vcpu machine, equivalent to t2.medium in AWS with 24GB of storage) and open the following ports:
** 8082 - for connecting from your application
** 5601 - for connecting to the dashboards
* Alternatively, you can run it on your local computer if it has minimum of 8GB RAM and a dual-core processor and 16GB storage.

2. Install docker & docker-compose
3. Run this command in your choice of directory:<br>
`` wget https://raw.githubusercontent.com/DrDroidLab/kenobi-setup/main/docker-compose.yaml `` <br>
`` docker-compose up -d ``
4. Install the Doctor Droid instrumentation & data forwarding package in your application environment using pip or pip3 (only supports >=3.6)<br>
`` pip install pycodemarker `` <br>
See here for instructions on how to instrument your code -> https://docs.drdroid.io/docs/installation-steps

5. Run this to setup the host for your just setup toolkit <br>
`` export DRDROID_HOST=VM_IP``

6. Once your application starts taking traffic, visit ``http://VM_IP:5601/app/dashboards/`` for seeing metadata about all you have instrumented. 
* For credentials, use username -> admin, password -> admin
* When logging in for the first time, choose 'Private' as the tenant. 
