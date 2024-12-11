ARG MARIADB_VERSION
FROM mariadb:${MARIADB_VERSION}

# Init scripts to seed database
COPY init/* /docker-entrypoint-initdb.d/

# Config overrides
COPY conf.d/* /etc/mysql/conf.d/
      
# This allows us to run mysqldump without having to enter a password at the command line
# We have to create this entry here in the docker build phase, because environment variables
# are not interpolated inside of the cfg files.
ARG MARIADB_ROOT_PASSWORD
RUN echo "[mysql]\nuser=root\npassword=$MARIADB_ROOT_PASSWORD\n\n[mysqldump]\nuser=root\npassword=$MARIADB_ROOT_PASSWORD" > ~/.my.cnf