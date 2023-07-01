| Código                                             | Uso                                               |
|----------------------------------------------------|---------------------------------------------------|
| `kubectl -n kube-system get pods`                   | Ver los pods                                      |
| `kubectl -n kube-system get pods -o`                | Ver los pods pero con más detalles                |
| `kubectl -n kube-system delete pod "Nombre del pod"`| Eliminar el pod que deseamos                      |
| `kubectl apply -f "Nombre de manifiesto.yml"`       | Aplicar el manifiesto que queramos                 |
| `kubectl exec -it "nombre pod" -sh`                 | Correr comandos desde el propio pod                |
| `kubectl get all`                                  | Muestra información detallada sobre todos los      |
|                                                    | recursos del clúster como pods, servicios,         |
|                                                    | replicas, deployments, statefulset, etc.           |
| `kubectl get "Tipo de elemento que queremos ver"`   | Muestra información sobre el elemento              |
| `curl http://"ip del elemento":"puerto"`            | Para mostrar los pods vinculados a ese puerto      |
| `kubectl logs nombre-del-pod[-c <nombre-del-contenedor>]` | Ver los logs                                      |
