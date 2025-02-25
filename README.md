Application installation template:

`helm upgrade --install <application-name> <chart-name> -f values/default-values.yaml -f values/<environment>/<environment>-values.yaml -f values/<environment>/<namespace>/<namespace>-values.yaml -f values/<environment>/<namespace>/<application-name>-values.yaml`

Example:

`helm upgrade --install app2 java-microservice -f values/default-values.yaml -f values/test/test-values.yaml -f values/test/athena/athena-values.yaml -f values/test/athena/app2-values.yaml`