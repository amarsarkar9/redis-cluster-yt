FROM redis:7.0.11
 
ARG CLUSTER_ANNOUNCE_IP
ENV CLUSTER_ANNOUNCE_IP=$CLUSTER_ANNOUNCE_IP
COPY redis.conf /usr/local/etc/redis/redis.conf
RUN echo "The CLUSTER_ANNOUNCE_IP variable value is $CLUSTER_ANNOUNCE_IP"
RUN sed -i "s/CLUSTER_ANNOUNCE_IP/$CLUSTER_ANNOUNCE_IP/g" /usr/local/etc/redis/redis.conf
RUN mkdir -p /var/log/redis
RUN chmod -R a+rw /var/log/redis/
RUN echo 'vm.overcommit_memory = 1' > /etc/sysctl.conf

CMD [ "redis-server", "/usr/local/etc/redis/redis.conf" ]

