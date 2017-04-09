FROM nginx

RUN apt-get update \
    && apt-get install -y git \
    && git clone https://github.com/dom-mel/dishwasher-ui.git \
    && mv dishwasher-ui/* /usr/share/nginx/html

