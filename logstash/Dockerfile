FROM logstash

RUN /usr/share/logstash/bin/logstash-plugin install logstash-input-beats
COPY logstash.conf /logstash.conf

CMD ["-f", "/logstash.conf"]
