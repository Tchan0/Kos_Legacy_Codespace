# Stage 1
FROM tchan0/dcchain:legacy as build

# Add Kos
RUN git clone https://github.com/KallistiOS/KallistiOS.git /opt/toolchains/dc/kos \
    && cd /opt/toolchains/dc/kos \
    && cp ./doc/environ.sh.sample ./environ.sh \
    && source environ.sh \
    && make

# Add Kos-ports, but don't compile, as it takes a couple of minutes
RUN git clone --recursive https://github.com/KallistiOS/kos-ports.git /opt/toolchains/dc/kos-ports
    
# Add dcloadip 
RUN git clone https://github.com/sizious/dcload-ip.git /opt/toolchains/dc/dcloadip \
   && cd /opt/toolchains/dc/dcloadip \
   && source /opt/toolchains/dc/kos/environ.sh \
   && make \
   && make install
