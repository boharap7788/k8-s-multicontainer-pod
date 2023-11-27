# k8-s-multicontainer-pod

A sidecar container is a secondary container that runs alongside the main application container within the same pod. The main purpose of a sidecar container is to extend or enhance the functionality of the primary container.

Here are some common use cases for sidecar containers:

    Logging/monitoring:
    A sidecar container can be used to collect logs or metrics from the main container and send them to a centralized logging or monitoring system. This separation allows the main application to focus on its primary functionality without being concerned with logging or monitoring details.

    Data synchronization:
    Sidecar containers can be employed to synchronize or cache data for the main application. For example, a sidecar might be responsible for fetching configuration files from a remote source and updating them in a shared volume that the main application reads from.

    Security/encryption:
    A sidecar container might handle tasks such as encrypting or decrypting communication for the main application. This can be useful in scenarios where the application itself doesn't need to deal with the complexities of encryption.

    Proxying or routing:
    Sidecar containers can act as proxies or routers, handling network requests and forwarding them to the main application container. This is often used in service mesh architectures for handling traffic between microservices.
    
# Command to execute side container 
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
kubectl apply -f pod-with-sidecar.yaml

kubectl get pods
kubectl logs pod-with-sidecar -c main-container
kubectl logs pod-with-sidecar -c sidecar-container

# how to check how many container inside pod
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
kubectl get pod <pod-name> -o jsonpath='{.spec.containers[*].name}'

kubectl describe pod <pod-name>

