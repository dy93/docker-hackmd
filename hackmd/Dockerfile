FROM node:boron
ENV DEBIAN_FRONTEND noninteractive
RUN apt-get update && apt-get install -y git build-essential sqlite3

# source
ADD https://raw.githubusercontent.com/dy93/hackmd/master/package.json /tmp/package.json
RUN cd /tmp && npm install

RUN mkdir /hackmd
WORKDIR /hackmd
RUN git clone https://github.com/dy93/hackmd.git /hackmd
RUN mv /tmp/node_modules /hackmd

# add config
ADD config.json /hackmd/config.json
ADD .sequelizerc /hackmd/.sequelizerc
ADD docker-entrypoint.sh /hackmd/docker-entrypoint.sh
RUN chmod +x /hackmd/docker-entrypoint.sh

# build front-end bundle
RUN npm run build

# remove dev dependencies
RUN npm prune --production

# remove build dependencies
RUN apt-get remove -y --auto-remove build-essential && \
	apt-get clean && apt-get purge && rm -r /var/lib/apt/lists/*

EXPOSE 3000

CMD ["/bin/bash", "-c", "/hackmd/docker-entrypoint.sh"]
