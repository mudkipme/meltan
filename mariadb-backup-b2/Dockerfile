FROM mariadb:10.9

ENV B2_TARGET mudkip-backup-web/database
ENV RCLONE_CONFIG_B2_TYPE b2
ENV MYSQL_HOST mysql
ENV MYSQLDUMP_OPT="--ignore-table=52poke_wiki.objectcache"

RUN apt-get update && apt-get install -y zip curl man-db
RUN curl https://rclone.org/install.sh | bash

COPY entrypoint.sh /entrypoint.sh

ENTRYPOINT ["/entrypoint.sh"]