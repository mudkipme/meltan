FROM postgres:15

ENV BACKUP_TARGET mudkip-backup-web/database
ENV RCLONE_CONFIG_BACKUP_TYPE b2
ENV POSTGRES_HOST postgres
ENV POSTGRES_PORT 5432

RUN apt-get update && apt-get install -y zip curl man-db
RUN curl https://rclone.org/install.sh | bash

COPY entrypoint.sh /entrypoint.sh

ENTRYPOINT ["/entrypoint.sh"]