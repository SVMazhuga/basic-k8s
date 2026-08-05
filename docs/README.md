# Basic Kubernetes

## Part 1. Ready-made manifest

### Task

1. Run a Kubernetes environment with 4 GB of memory.

2. Apply the manifest from the `/src/example` directory to the created Kubernetes environment.

3. Run the standard Kubernetes control panel with the command `minikube dashboard`.

4. Create tunnels to access the deployed services with the command `minikube service`.

5. Check that the deployed application is working by opening the application page in a browser (Apache service).

## Part 2. Your own manifest

### Task 

1. Create your own YAML files or manifests for the application from the first project (`/src/services`), implementing the following:
   - a configuration map with values for database hosts and services;
   - secrets containing the database password, login information, and cross-service authorization keys (found in the `application.properties` files);
   - pods and services for all application modules: PostgreSQL, RabbitMQ, and seven application services. Use a single replica for all services.

2. Run the application by sequentially applying manifests with the command: `kubectl apply -f <manifest>.yaml`.

3. Use the command `kubectl get <object_type> <object_name>` and `kubectl describe <object_type> <object_name>` to check the status of created objects (secrets, configuration maps, pods, and services) in the cluster. Add the results to the report.

4. Check the secret values by applying the command: `kubectl get secret my-secret -o jsonpath='{.data.password}' | base64 --decode` to decode the secret.

5. Check the logs of the application running in the cluster using the command: `kubectl logs <container_name>`. Add a screenshot to the report.

6. Create tunnels to access the gateway and session services.

7. Run the Postman functional tests to ensure that the application is working properly.

8. Run the standard Kubernetes control panel with the command `minikube dashboard`. Include screenshots from the dashboard in the report showing the current state of the cluster nodes, a list of running Pods, and other metrics such as CPU and memory utilization, Pod logs, and Pod configurations and secrets.

9. Update the application by adding a new dependency to the POM file and rebuild the application using the following deployment strategies. Measure the application redeployment time for each case and note the results in the report:
   - Recreate,
   - Rolling.
