1. Context
- You have access to multiple clusters from your main terminal through kubectl contexts. Write all those context names into /opt/course/1/contexts.
  - $ kubectl config get-contexts -o name 
- Next write a command to display the current context into /opt/course/1/context_default_kubectl.sh, the command should use kubectl.
  - $ kubectl config current-context
- Finally write a second command doing the same thing into /opt/course/1/context_default_no_kubectl.sh, but without the use of kubectl.
  - $ cat ~/.kube/config | grep current

2. Schedule Pod on Master Node
- Create a single Pod of image httpd:2.4.41-alpine in Namespace default. The Pod should be named pod1 and the container should be named pod1-container. This Pod should only be scheduled on a master node, do not add new labels any nodes.
  - $ kubectl run pod1 --image=httpd:2.4.41-alpine --dry-run=client -o yaml
---
apiVersion: v1
kind: Pod
metadata:
  creationTimestamp: null
  labels:
    run: pod1
  name: pod1
spec:
  tolerations:
  - effect: NoSchedule
    key: node-role.kubernetes.io/master
  nodeSelector:
    node-role.kubernetes.io/master: ""
  containers:
  - image: httpd:2.4.41-alpine
    name: pod1
    resources: {}
  dnsPolicy: ClusterFirst
  restartPolicy: Always
status: {}
---
- Shortly write the reason on why Pods are by default not scheduled on master nodes into /opt/course/2/master_schedule_reason .
  - $ kubectl describe pod pod1
    - master nodes usually have a taint defined

3. Scale down StatefulSet
- There are two Pods named o3db-* in Namespace project-c13. C13 management asked you to scale the Pods down to one replica to save resources. Record the action.
  - $ kubectl -n project-c13 scale sts o3db --replicas 1 --record

4. Pod Ready if Service is reachable
- Do the following in Namespace default. Create a single Pod named ready-if-service-ready of image nginx:1.16.1-alpine. Configure a LivenessProbe which simply runs true. Also configure a ReadinessProbe which does check if the url http://service-am-i-ready:80 is reachable, you can use wget -T2 -O- http://service-am-i-ready:80 for this. Start the Pod and confirm it isn't ready because of the ReadinessProbe. Create a second Pod named am-i-ready of image nginx:1.16.1-alpine with label id: cross-server-ready. The already existing Service service-am-i-ready should now have that second Pod as endpoint. Now the first Pod should be in ready state, confirm that.