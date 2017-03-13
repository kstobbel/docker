FROM streamsets/datacollector:2.3.0.1
MAINTAINER Kevin Stobbelaar <kevin.stobbelaar@ae.be>

ENV SDC_USER=sdc

ENV SDC_VERSION ${SDC_VERSION:-2.3.0.1}
ENV SDC_DIST="/opt/streamsets-datacollector-${SDC_VERSION}"
ENV STREAMSETS_LIBRARIES_EXTRA_DIR="${SDC_DIST}/libs-common-lib"

# Set permissions on shared libs folder
USER root
RUN chown -R "${SDC_USER}:${SDC_USER}" "${STREAMSETS_LIBRARIES_EXTRA_DIR}"
USER ${SDC_USER}

# Move oracle driver and set the appropriate permissions
COPY ojdbc7.jar "${STREAMSETS_LIBRARIES_EXTRA_DIR}"
USER root
RUN chown -R "${SDC_USER}:${SDC_USER}" "${STREAMSETS_LIBRARIES_EXTRA_DIR}/ojdbc7.jar"


# Move MSSQL JDBC driver and set the appropriate permissions
COPY sqljdbc41.jar "${STREAMSETS_LIBRARIES_EXTRA_DIR}"
USER root
RUN chown -R "${SDC_USER}:${SDC_USER}" "${STREAMSETS_LIBRARIES_EXTRA_DIR}/sqljdbc41.jar"

# Move Streamsets datacollector java sdk 2.2.0.0 and set the appropriate permissions
COPY streamsets-datacollector-sdk-2.2.0.0.jar "${STREAMSETS_LIBRARIES_EXTRA_DIR}"
USER root
RUN chown -R "${SDC_USER}:${SDC_USER}" "${STREAMSETS_LIBRARIES_EXTRA_DIR}/streamsets-datacollector-sdk-2.2.0.0.jar"

# USER ${SDC_USER}
