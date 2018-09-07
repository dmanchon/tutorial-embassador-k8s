- Start minikube:
  `$  minikube start --vm-driver kvm2`
- Apply the manifests:
  ```
  $ kubectl  apply -f ambassador-rbac.yaml
  $ kubectl  apply -f homework.yaml -n homework
  ```
- Get the address of the services
  `$ minikube service list`

- The wp address is the ambassador url service, ie. http://192.168.39.100:30102
- When the PVC is deleted the PV stays since its defined as Retain policy
  For the PVC to claim it again we need to manually delete the claimRef on the PV
