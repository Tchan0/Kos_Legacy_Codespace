# Stage 1
FROM tchan0/dcchain:legacy as build

# Installing prerequisites
#UN apk add \
#        gcc \
#        libelf-dev

# Add Kos
RUN git clone https://github.com/KallistiOS/KallistiOS.git /opt/toolchains/dc/kos \
    && cd /opt/toolchains/dc/kos \
    && cp ./doc/environ.sh.sample ./environ.sh \
    && source environ.sh \
    && make

# Add Kos-ports
#RUN git clone --recursive git://git.code.sf.net/p/cadcdev/kos-ports /opt/toolchains/dc/kos-ports
#    source /opt/toolchains/dc/kos/environ.sh
#    cd /opt/toolchains/dc/kos-ports/utils
#    ./build-all.sh
    
# Add dcloadip 
RUN git clone https://github.com/sizious/dcload-ip.git /opt/toolchains/dc/dcloadip \
   && cd /opt/toolchains/dc/dcloadip \
   && source /opt/toolchains/dc/kos/environ.sh \
   && make \
   && make install
