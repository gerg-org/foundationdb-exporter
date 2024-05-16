FROM node:bullseye-slim as builder

# install FoundationDB client library
RUN wget -q https://github.com/apple/foundationdb/releases/download/7.1.43/foundationdb-clients_7.1.43-1_amd64.deb && \
    dpkg -i foundationdb-clients_7.1.43-1_amd64.deb \
    && rm foundationdb-clients_7.1.43-1_amd64.deb

WORKDIR /app

COPY package.json yarn.lock ./
RUN yarn --prod

ENTRYPOINT ["node", "build/index.js"]
