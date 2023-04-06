# MyController
Good references: 
+ https://tangxusc.github.io/blog/2019/05/code-generator%E4%BD%BF%E7%94%A8/
+ https://xieys.club/code-generator-crd/

## client-go 

+ go mod vendor && chmod -R 777 vendor/
+ cd hack && ./update-codegen.sh
+ kubectl apply -f artifacts/crd-status-subresource.yaml
(enable status subresource, otherwise UpdateStatus will return an error)
    > The CRD in crd-status-subresource.yaml enables the /status subresource for custom resources. This means that UpdateStatus can be used by the controller to update only the status part of the custom resource.
    To understand why only the status part of the custom resource should be updated, please refer to the Kubernetes API conventions.
