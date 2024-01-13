FROM linux/amd64:stable

COPY . . 

WORKDIR /app

# ARG applist1=nmap

RUN apt update && apt install iputils-ping -y

ARG RUNTIME_PACKAGES="\
  # General utils
  curl \
  # Docker specific
#  gosu \
  # Timezones support
#  tzdata \
  # fonts for text file thumbnail generation
#  fonts-liberation \
#  gettext \
#  ghostscript \
#  gnupg \
#  icc-profiles-free \
#  imagemagick \
  # PostgreSQL
#  libpq5 \
#  postgresql-client \
  # MySQL / MariaDB
#  mariadb-client \
  # OCRmyPDF dependencies
#  tesseract-ocr \
#  tesseract-ocr-eng \
#  tesseract-ocr-deu \
#  tesseract-ocr-fra \
#  tesseract-ocr-ita \
#  tesseract-ocr-spa \
#  unpaper \
#  pngquant \
#  jbig2dec \
  # lxml
#  libxml2 \
#  libxslt1.1 \
  # itself
#  qpdf \
  # Mime type detection
#  file \
#  libmagic1 \
#  media-types \
#  zlib1g \
  # Barcode splitter
#  libzbar0 \
#  poppler-utils"

UN set -eux \
  echo "Installing system packages" \
    && apt-get update \
    && apt-get install --yes --quiet --no-install-recommends ${RUNTIME_PACKAGES} \
#    && echo "Installing pre-built updates" \
#      && echo "Installing qpdf ${QPDF_VERSION}" \
#        && curl --fail --silent --show-error --location \
#          --output libqpdf29_${QPDF_VERSION}-1_${TARGETARCH}.deb \
#          https://github.com/paperless-ngx/builder/releases/download/qpdf-${QPDF_VERSION}/libqpdf29_${QPDF_VERSION}-1_${TARGETARCH}.deb \
#        && curl --fail --silent --show-error --location \
#          --output qpdf_${QPDF_VERSION}-1_${TARGETARCH}.deb \
#          https://github.com/paperless-ngx/builder/releases/download/qpdf-${QPDF_VERSION}/qpdf_${QPDF_VERSION}-1_${TARGETARCH}.deb \
#        && dpkg --install ./libqpdf29_${QPDF_VERSION}-1_${TARGETARCH}.deb \
#        && dpkg --install ./qpdf_${QPDF_VERSION}-1_${TARGETARCH}.deb \
#      && echo "Installing Ghostscript ${GS_VERSION}" \
#        && curl --fail --silent --show-error --location \
#          --output libgs10_${GS_VERSION}.dfsg-2_${TARGETARCH}.deb \
#          https://github.com/paperless-ngx/builder/releases/download/ghostscript-${GS_VERSION}/libgs10_${GS_VERSION}.dfsg-1_${TARGETARCH}.deb \
#        && curl --fail --silent --show-error --location \
#          --output ghostscript_${GS_VERSION}.dfsg-2_${TARGETARCH}.deb \
#          https://github.com/paperless-ngx/builder/releases/download/ghostscript-${GS_VERSION}/ghostscript_${GS_VERSION}.dfsg-1_${TARGETARCH}.deb \
#        && curl --fail --silent --show-error --location \
#          --output libgs10-common_${GS_VERSION}.dfsg-2_all.deb \
#          https://github.com/paperless-ngx/builder/releases/download/ghostscript-${GS_VERSION}/libgs10-common_${GS_VERSION}.dfsg-1_all.deb \
#        && dpkg --install ./libgs10-common_${GS_VERSION}.dfsg-2_all.deb \
#        && dpkg --install ./libgs10_${GS_VERSION}.dfsg-2_${TARGETARCH}.deb \
#        && dpkg --install ./ghostscript_${GS_VERSION}.dfsg-2_${TARGETARCH}.deb \
#      && echo "Installing jbig2enc" \
#        && curl --fail --silent --show-error --location \
#          --output jbig2enc_${JBIG2ENC_VERSION}-1_${TARGETARCH}.deb \
#          https://github.com/paperless-ngx/builder/releases/download/jbig2enc-${JBIG2ENC_VERSION}/jbig2enc_${JBIG2ENC_VERSION}-1_${TARGETARCH}.deb \
#        && dpkg --install ./jbig2enc_${JBIG2ENC_VERSION}-1_${TARGETARCH}.deb \
#      && echo "Cleaning up image layer" \
#        && rm --force --verbose *.deb \
#    && rm --recursive --force --verbose /var/lib/apt/lists/* \
#  && echo "Installing supervisor" \
#    && python3 -m pip install --default-timeout=1000 --upgrade --no-cache-dir supervisor==4.2.5

# EXPOSE 8000


#RUN set -eux \
#  && echo "Setting up user/group" \
#    && addgroup --gid 1000 paperless \
#    && useradd --uid 1000 --gid paperless --home-dir /usr/src/paperless paperless \
#  && echo "Creating volume directories" \
#    && mkdir --parents --verbose /usr/src/paperless/data \
#    && mkdir --parents --verbose /usr/src/paperless/media \
#    && mkdir --parents --verbose /usr/src/paperless/consume \
#    && mkdir --parents --verbose /usr/src/paperless/export \
#  && echo "Adjusting all permissions" \
#    && chown --from root:root --changes --recursive paperless:paperless /usr/src/paperless \
#  && echo "Collecting static files" \
#    && gosu paperless python3 manage.py collectstatic --clear --no-input --link \
#    && gosu paperless python3 manage.py compilemessages

# VOLUME ["/usr/src/paperless/data", \
#         "/usr/src/paperless/media", \
#         "/usr/src/paperless/consume", \
#         "/usr/src/paperless/export"]
