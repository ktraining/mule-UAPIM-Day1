# Cheatsheet for MuleSoft Flex Gateway

## Install & Run the Container
```docker pull mulesoft/flex-gateway:latest```

Repository for docker image: https://hub.docker.com/r/mulesoft/flex-gateway/tags

## Location of Logs
```/var/tmp/mulesoft/flex-gateway/logs```

Tracing ID header is **X-Request-ID**

More info: https://www.envoyproxy.io/docs/envoy/latest/intro/arch_overview/observability/tracing

## Key Config folders

```/usr/local/share/mulesoft/flex-gateway/conf.d```

```/etc/mulesoft/flex-gateway/fluent```

```/etc/mulesoft/flex-gateway/conf.d```

```/var/tmp/mulesoft/flex-gateway```

## Useful Commands

List the images and versions, filtered by Flex

```docker images mulesoft/flex-gateway```

Connect to the container through the terminal

```docker exec -it bbca9200bb8b73a2297da99da4fea7bc66fbe0de3db5f3339aaba950c6e0cc9f bash```

List the files in the config folder, from the outside of the container

```docker exec a6eb04b7d994 ls /usr/local/share/mulesoft/flex-gateway/conf.d/```

Run the docker container in detached mode (-d)

```docker run -d --rm -v $(pwd):/usr/local/share/mulesoft/flex-gateway/conf.d -p 8083:8081 mulesoft/flex-gateway```

### References
- https://docs.docker.com/engine/reference/commandline/pull/
- https://docs.docker.com/engine/reference/commandline/run/ 
- https://www.envoyproxy.io/docs/envoy/latest/configuration/observability/access_log/usage
- https://docs.docker.com/config/containers/container-networking/
- Release Notes: https://docs.mulesoft.com/release-notes/flex-gateway/flex-gateway-release-notes