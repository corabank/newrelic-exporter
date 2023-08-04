# NewRelic Exporter Helm Installation
This Helm Chart will deploy the NewRelic Exporter.

## Configuration parameters
Value                       | Description                                            | Default
----------------------------|--------------------------------------------------------|-------------------
imagePullSecrets            | Image Pull Secret                                      | ""
containerName               | The name of the container                              | newrelic-exporter
image.registry              | The image registry: default docker hub                 | coraopensource
image.image                 | The image name                                         | newrelic-exporter
image.tag                   | The image tag                                          | v1.0.0
image.pullPolicy            | The image policy                                       | IfNotPresent
service.port                | The service and deployment port                        | 9126
nrApiKey                    | NewRelic API Key                                       | ""
nrServer                    | API location.                                          | https://api.newrelic.com
nrPeriod                    | Period of data to request, in seconds                  | Defaults to 60.
nrTimeout                   | Period of time to wait for an API response in seconds  | 5s
nrAppsListCacheTime         | Length of time to cache list of available applications | 1m
nrMetricNamesCacheTime      | Length of time to cache names of metrics (not values)  | 0
nrService                   | Define section of API to limit requests to (applications, mobile, etc) | applications
nrIncludeApps               | List of applications to query (optional)               | ""
nrUseOnlySummary            | If you only use the summary metrics, set it to true    | false
nrIncludeMetricFilters      | List of metric groups to filter by to reduce number of API calls (optional) | ""
nrIncludeValues             | List of values to filter by to reduce number of API calls (optional) | ""
nrTelemetryPath             | Path under which to expose metrics                     | /metrics
nrDebug                     | If you want to start debug server                      | false
nrDebugProxyAddress         | Proxy settings for debugging                           | https://localhost:8888
extraEnvs                   | Extra environments                                     | []
labels                      | Deployment labels                                      | {}
commonLabels                | Deployment commons labels                              | {}
podLabels                   | Pod labels                                             | {}
annotations                 | Deployment annotations                                 | {}
resources                   | Deployment resources (cpu and memory)                  | limits: 100m, 128Mi, resources: 50m, 64Mi
tolerations                 | Deployment tolerations                                 | []
nodeSelector                | Deployment nodeselector                                | {}
