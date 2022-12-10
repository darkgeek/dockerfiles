# Pull base image
FROM riscv64/debian:unstable

# Copy binaries into image
COPY ./rqlite /usr/bin/
COPY ./rqlited /usr/bin/
COPY ./rqbench /usr/bin/

# Define mountable directories.
VOLUME ["/data"]

# Define working directory.
WORKDIR /data

# Start rqlite server daemon
CMD ["rqlited", "/data/node"]

# Expose ports.
EXPOSE 4001 
EXPOSE 4002 
