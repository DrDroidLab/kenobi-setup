# kenobi-setup
Timestamped JSON Document Ingestion and auto visualization toolkit

## How to setup
1. Take a VM from your choice of cloud provider (with public IP/LB as VM_IP) and open following ports:
* 8082 - for connecting from your application
* 5601 - for connecting to the dashboards
2. Install docker & docker-compose
3. Run this command in your choice of directory:<br>
`` wget https://raw.githubusercontent.com/DrDroidLab/kenobi-setup/main/docker-compose.yaml `` <br>
`` docker-compose up -d ``
4. Run this command in your python environment where your application is running <br>
`` pip install pycodemarker ``

5. Run this to setup the host for your just setup toolkit <br>
`` export DRDROID_HOST=VM_IP``

6. Once your application starts taking traffic, visit ``http://VM_IP:5601/app/dashboards/`` for seeing metadata about all you have instrumented. 
