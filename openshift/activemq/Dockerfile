FROM apache/activemq-classic:6.2.0

ENV POSTGRES_JDBC_DRIVER_VERSION=9.4.1212

# Download the postgres JDBC driver to the activemq lib directory, keeping previous functionality
RUN curl -o /opt/apache-activemq/lib/optional/postgresql-$POSTGRES_JDBC_DRIVER_VERSION.jar \
    https://jdbc.postgresql.org/download/postgresql-$POSTGRES_JDBC_DRIVER_VERSION.jar


# Provide backward compatibility for anyone expecting /opt/activemq
RUN ln -s /opt/apache-activemq /opt/activemq

# Fix permissions for OpenShift random UID execution
RUN chown -R :0 /opt/apache-activemq && \
    chmod -R g+rwX /opt/apache-activemq

WORKDIR /opt/apache-activemq
