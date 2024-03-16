FROM mysql:8.0.33
LABEL "project"="Vprofile"
LABEL "Author"="vinoth"

ENV MYSQL_ROOT_PASSWORD="password"
ENV MYSQL_DATABASE="ACCOUNTS"

ADD db_backup.sql docker-entrypoint-init.d/db_backup.sql