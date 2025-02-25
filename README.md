## Repository Structure

.
├── README.md
├── charts
│   └── <chart_name> 
│       ├── Chart.yaml
│       ├── templates
│       │   ├── NOTES.txt
│       │   ├── _helpers.tpl
│       │   ├── deployment.yaml
│       │   ├── hpa.yaml
│       │   ├── ingress.yaml
│       │   ├── service.yaml
│       │   ├── serviceaccount.yaml
│       └── values.yaml
└── values
    ├── defaults.yaml # Default overall values
    └── <env> # Environment 
        ├── defaults.yaml #ENV Overall defaults
        └── <namespace> # NS
            ├── defaults.yaml # namespace defaults
            └── app_name.yaml # app specific values   
```

Application installation template:

`helm upgrade --install <application-name> <chart-name> -f values/default-values.yaml -f values/<environment>/<environment>-values.yaml -f values/<environment>/<namespace>/<namespace>-values.yaml -f values/<environment>/<namespace>/<application-name>-values.yaml`

Example:

`helm upgrade --install app1 java-microservice -f values/default-values.yaml -f values/test/test-values.yaml -f values/test/athena/athena-values.yaml -f values/test/athena/app1-values.yaml`
