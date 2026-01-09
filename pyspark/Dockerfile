FROM apache/spark:3.5.7-python3

USER root

# Define exact versions for 2026 stability
ENV ICEBERG_VERSION=1.10.1
ENV AWS_SDK_VERSION=2.20.160

# Correct syntax requires https:// and full /maven2/ paths
RUN curl -s -L "https://repo1.maven.org/maven2/org/apache/iceberg/iceberg-spark-runtime-3.5_2.12/${ICEBERG_VERSION}/iceberg-spark-runtime-3.5_2.12-${ICEBERG_VERSION}.jar" \
    -o /opt/spark/jars/iceberg-spark-runtime.jar && \
    curl -s -L "https://repo1.maven.org/maven2/software/amazon/awssdk/bundle/${AWS_SDK_VERSION}/bundle-${AWS_SDK_VERSION}.jar" \
    -o /opt/spark/jars/aws-sdk-bundle.jar && \
    pip install pyspark && \
    echo "Installed pyspark"

# Standard tail bash command to keep container alive
ENTRYPOINT ["tail", "-f", "/dev/null"]
