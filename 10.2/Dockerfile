FROM bitnami/minideb-extras:jessie-r95
LABEL maintainer "Bitnami <containers@bitnami.com>"

ENV BITNAMI_PKG_CHMOD="-R g+rwX" \
    BITNAMI_PKG_EXTRA_DIRS="/bitnami/mariadb/conf" \
    HOME="/"

# Install required system packages and dependencies
RUN install_packages libaio1 libc6 libgcc1 libjemalloc1 libncurses5 libssl1.0.0 libstdc++6 libtinfo5 zlib1g
RUN bitnami-pkg unpack mariadb-10.2.16-1 --checksum d896462896f4b5be21b286e7797427443a0afb75f5714890e96ad21427ded707

COPY rootfs /
ENV ALLOW_EMPTY_PASSWORD="no" \
    BITNAMI_APP_NAME="mariadb" \
    BITNAMI_IMAGE_VERSION="10.2.16-r4" \
    MARIADB_DATABASE="" \
    MARIADB_MASTER_HOST="" \
    MARIADB_MASTER_PORT_NUMBER="" \
    MARIADB_MASTER_ROOT_PASSWORD="" \
    MARIADB_MASTER_ROOT_USER="" \
    MARIADB_PASSWORD="" \
    MARIADB_PORT_NUMBER="3306" \
    MARIADB_REPLICATION_MODE="" \
    MARIADB_REPLICATION_PASSWORD="" \
    MARIADB_REPLICATION_USER="" \
    MARIADB_ROOT_PASSWORD="" \
    MARIADB_ROOT_USER="root" \
    MARIADB_USER="" \
    PATH="/opt/bitnami/mariadb/bin:/opt/bitnami/mariadb/sbin:$PATH"

EXPOSE 3306

USER 1001
ENTRYPOINT ["/app-entrypoint.sh"]
CMD ["/run.sh"]
