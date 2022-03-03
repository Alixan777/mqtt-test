FROM alpine

RUN apk add --update --no-cache openssh
RUN apk add --update --no-cache curl
RUN apk add --update --no-cache mosquitto-clients

CMD mosquitto_sub -h server -u ali -P alixan22 -t chat/topic