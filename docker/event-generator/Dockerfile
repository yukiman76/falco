FROM alpine:latest
RUN apk add --no-cache bash g++
COPY ./event_generator.cpp /usr/local/bin
RUN mkdir -p /var/lib/rpm
RUN g++ --std=c++0x /usr/local/bin/event_generator.cpp -o /usr/local/bin/event_generator

# Copy event_generator to a more innocuous name ftest. This is useful
# if you want to use the event_generator image for demos but don't
# want a completely obvious name like "event_generator" causing all
# the suspicious activity.
RUN cp /usr/local/bin/event_generator /usr/local/bin/ftest
CMD ["/usr/local/bin/event_generator"]
