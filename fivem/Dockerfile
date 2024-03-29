FROM debian:bullseye

RUN apt-get update && \
    DEBIAN_FRONTEND=noninteractive apt-get install -y \
    curl \
    unzip \
    apache2 \
    php \
    php-cli \
    php-mysql \
    php-gd \
    php-json \
    php-curl \
    mysql-server \
    phpmyadmin \
    && rm -rf /var/lib/apt/lists/*

ENV PHPMYADMIN_PORT 80

RUN useradd -ms /bin/bash fivemuser

WORKDIR /fivem
RUN chown -R fivemuser:fivemuser /fivem

COPY phpmyadmin.conf /etc/apache2/sites-available/phpmyadmin.conf
COPY config-db.php /etc/phpmyadmin/config-db.php
RUN ln -s /etc/phpmyadmin/apache.conf /etc/apache2/conf-available/phpmyadmin.conf && \
    a2enconf phpmyadmin

USER fivemuser
RUN curl -sSL https://runtime.fivem.net/artifacts/fivem/build_proot_linux/master/ | \
    grep -o '<a [^>]\+' | grep -o '[^"]\+\.tar\.xz' | head -n 1 | \
    xargs -I {} curl -sSL -o fivem-server.tar.xz https://runtime.fivem.net/artifacts/fivem/build_proot_linux/master/{} && \
    tar -xf fivem-server.tar.xz -C /fivem/server

EXPOSE 30120 $PHPMYADMIN_PORT

# Starte Apache und MySQL
CMD service apache2 start && service mysql start && /bin/bash
