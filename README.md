# Tomcat JMX metrics with datadog

# Steps

Docker commands

```
docker compose up -d --build
```
```
docker compose logs -f
```
```
docker compose exec dd-agent agent check tomcat
```

Connect web server

```
curl localhost:8080
```

Use jmxterm as jmx client

```
java -jar jmxterm-1.0.2-uber.jar 
$>open localhost:9012
$>domains
$>domain Catalina
$>beans
$>bean Catalina:name=http-8080,type=GlobalRequestProcessor
$>info
$>get *
$>bye
```

# Links

* https://www.softwareyoga.com/docker-tomact-tutorial/
* https://github.com/nxnarbais/datadog-sandbox
* https://github.com/jiaqi/jmxterm/releases
* https://qiita.com/xacknack/items/0fee0e1a02d52deac9b9
* https://docs.datadoghq.com/ja/containers/guide/autodiscovery-with-jmx/?tab=%E3%82%B3%E3%83%B3%E3%83%86%E3%83%8Aagent
* https://docs.datadoghq.com/ja/containers/guide/ad_identifiers/?tab=docker%E3%83%A9%E3%83%99%E3%83%AB
* https://docs.datadoghq.com/ja/containers/docker/integrations/?tab=dockeradv2
* https://docs.datadoghq.com/ja/getting_started/tagging/unified_service_tagging/?tab=docker
* https://blog.vtryo.me/entry/datadog-docker-auto-discovery
* https://www.softwareyoga.com/docker-tomact-tutorial/