# Pull base image
FROM riscv64/debian:unstable

# Install Redis from repo
RUN \
        apt update -y && \
        apt upgrade -y && \
        apt install -y redis && \
        sed -i 's/^\(bind .*\)$/# \1/' /etc/redis/redis.conf && \
        sed -i 's/^\(daemonize .*\)$/# \1/' /etc/redis/redis.conf && \
        sed -i 's/^\(dir .*\)$/# \1\ndir \/data/' /etc/redis/redis.conf && \
        sed -i 's/^\(logfile .*\)$/# \1/' /etc/redis/redis.conf

# Define mountable directories.
VOLUME ["/data"]

# Define working directory.
WORKDIR /data

# Define default command.
CMD ["redis-server", "/etc/redis/redis.conf"]

# Expose ports.
EXPOSE 6379

