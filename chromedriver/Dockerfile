FROM selenium/standalone-chrome-debug
COPY test.png /app/test/spec/test.png
ADD https://archive.apache.org/dist/jmeter/binaries/apache-jmeter-3.0.tgz .
RUN tar -xvzf ./apache-jmeter-3.0.tgz
COPY check-proxy.jmx .
ADD https://www.browserstack.com/browserstack-local/BrowserStackLocal-linux-x64.zip .
RUN unzip BrowserStackLocal-linux-x64.zip

# startup
COPY ./docker-entrypoint.sh /
RUN chmod +x /docker-entrypoint.sh
EXPOSE 3000
CMD ["/docker-entrypoint.sh"]

