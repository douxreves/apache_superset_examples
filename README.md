# apache_superset_examples
## Archlinux Apache Superset Notes, Examples, etc

# Install Anaconda/etc

# Create a virtualenv for apache_superset
conda create -y --name apache_superset python=3.9

# Activate it
conda activate apache_superset

# Install Apache Superset
pip install apache-superset

# Follow the Apache Superset instructions here with some modifications
https://superset.apache.org/docs/installation/installing-superset-from-scratch/

#Install older versions of flask , werkzeug, and jinja2
pip install flask==2.0.3 werkzeug==2.0.3 jinja2==3.0.1

# Create an admin user in your metadata database (use `admin` as username to be able to load the examples)
export FLASK_APP=superset
superset fab create-admin

# Load some data to play with
superset load_examples

# Create default roles and permissions
superset init

# To start a development web server on port 8088, use -p to bind to another port
superset run -p 8088 --with-threads --reload --debugger

# Add the export from above to your ~/.xinitrc to start with X
export FLASK_APP=superset & 