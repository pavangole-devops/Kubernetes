```sh 
Script started on 2022-09-01 09:23:21+0530
(base) ]0;vaibhavgole@Vank: ~[01;32mvaibhavgole@Vank[00m:[01;34m~[00m$ minikube start
😄  minikube v1.16.0 on Linuxmint 19.3
✨  Using the vmware driver based on existing profile
👍  Starting control plane node minikube in cluster minikube
🏃  Updating the running vmware "minikube" VM ...
🌐  Found network options:
    ▪ NO_PROXY=localhost,127.0.0.0/8,::1
    ▪ no_proxy=localhost,127.0.0.0/8,::1
🐳  Preparing Kubernetes v1.20.0 on Docker 20.10.0 ...| WW[K[K/ WW[K[K- WW[K[K\ WW[K[K
    ▪ env NO_PROXY=localhost,127.0.0.0/8,::1
🔎  Verifying Kubernetes components...
🌟  Enabled addons: storage-provisioner, default-storageclass
🏄  Done! kubectl is now configured to use "minikube" cluster and "default" namespace by default
(base) ]0;vaibhavgole@Vank: ~[01;32mvaibhavgole@Vank[00m:[01;34m~[00m$ kubectl get pds[K[Kods
No resources found in default namespace.
(base) ]0;vaibhavgole@Vank: ~[01;32mvaibhavgole@Vank[00m:[01;34m~[00m$ kub[K[K[Kkubectl create [K[K[K[K[K[K[Kcreate[K[K[K[K[K[K[K[K[K[K[K[K[K[Kkubeclrt [K[K[K[K[K[K[K[K[Kkubectl run apache [K[K[K[K[K[K[Kapache --image=httpd
pod/apache created
(base) ]0;vaibhavgole@Vank: ~[01;32mvaibhavgole@Vank[00m:[01;34m~[00m$ kubectl get pods
NAME     READY   STATUS              RESTARTS   AGE
apache   0/1     ContainerCreating   0          4s
(base) ]0;vaibhavgole@Vank: ~[01;32mvaibhavgole@Vank[00m:[01;34m~[00m$ kubectl get pods
NAME     READY   STATUS              RESTARTS   AGE
apache   0/1     ContainerCreating   0          7s
(base) ]0;vaibhavgole@Vank: ~[01;32mvaibhavgole@Vank[00m:[01;34m~[00m$ kubectl get pods
NAME     READY   STATUS              RESTARTS   AGE
apache   0/1     ContainerCreating   0          9s
(base) ]0;vaibhavgole@Vank: ~[01;32mvaibhavgole@Vank[00m:[01;34m~[00m$ kubectl get pods
NAME     READY   STATUS    RESTARTS   AGE
apache   1/1     Running   0          10s
(base) ]0;vaibhavgole@Vank: ~[01;32mvaibhavgole@Vank[00m:[01;34m~[00m$ kubectl dres[K[K[Kescrible pod apache
Error: unknown command "describle" for "kubectl"

Did you mean this?
	describe

Run 'kubectl --help' for usage.
(base) ]0;vaibhavgole@Vank: ~[01;32mvaibhavgole@Vank[00m:[01;34m~[00m$ kubectl describle pod apache[1P
Name:         apache
Namespace:    default
Priority:     0
Node:         minikube/172.16.33.128
Start Time:   Thu, 01 Sep 2022 09:25:52 +0530
Labels:       run=apache
Annotations:  <none>
Status:       Running
IP:           172.17.0.3
IPs:
  IP:  172.17.0.3
Containers:
  apache:
    Container ID:   docker://c68b05d9b7e2359abbfceb00222689181686212c16f851c3f092464977be8560
    Image:          httpd
    Image ID:       docker-pullable://httpd@sha256:70999c4a17c796dd28f86f9c847b30f28abaed6ef1fd72a44282b1c941238804
    Port:           <none>
    Host Port:      <none>
    State:          Running
      Started:      Thu, 01 Sep 2022 09:26:00 +0530
    Ready:          True
    Restart Count:  0
    Environment:    <none>
    Mounts:
      /var/run/secrets/kubernetes.io/serviceaccount from default-token-tdx8n (ro)
Conditions:
  Type              Status
  Initialized       True 
  Ready             True 
  ContainersReady   True 
  PodScheduled      True 
Volumes:
  default-token-tdx8n:
    Type:        Secret (a volume populated by a Secret)
    SecretName:  default-token-tdx8n
    Optional:    false
QoS Class:       BestEffort
Node-Selectors:  <none>
Tolerations:     node.kubernetes.io/not-ready:NoExecute op=Exists for 300s
                 node.kubernetes.io/unreachable:NoExecute op=Exists for 300s
Events:
  Type    Reason     Age   From               Message
  ----    ------     ----  ----               -------
  Normal  Scheduled  30s   default-scheduler  Successfully assigned default/apache to minikube
  Normal  Pulling    29s   kubelet            Pulling image "httpd"
  Normal  Pulled     22s   kubelet            Successfully pulled image "httpd" in 7.068138875s
  Normal  Created    22s   kubelet            Created container apache
  Normal  Started    22s   kubelet            Started container apache
(base) ]0;vaibhavgole@Vank: ~[01;32mvaibhavgole@Vank[00m:[01;34m~[00m$ kubectl [K[K[K[K[K[K[K[Kcr[Kurl http://172.17.0.3
^C
(base) ]0;vaibhavgole@Vank: ~[01;32mvaibhavgole@Vank[00m:[01;34m~[00m$ mii[Knikube ssh
                         _             _            
            _         _ ( )           ( )           
  ___ ___  (_)  ___  (_)| |/')  _   _ | |_      __  
/' _ ` _ `\| |/' _ `\| || , <  ( ) ( )| '_`\  /'__`\
| ( ) ( ) || || ( ) || || |\`\ | (_) || |_) )(  ___/
(_) (_) (_)(_)(_) (_)(_)(_) (_)`\___/'(_,__/'`\____)

$ curl http://172.17.0.3
<html><body><h1>It works!</h1></body></html>
$ curl http://172.17.0.3
<html><body><h1>It works!</h1></body></html>
$ exit
logout
(base) ]0;vaibhavgole@Vank: ~[01;32mvaibhavgole@Vank[00m:[01;34m~[00m$ kubeclt del[K[K[K[K[K[K[K[K[K[K[Kkubectl delete pod apache
pod "apache" deleted
kubet ctl get (base) ]0;vaibhavgole@Vank: ~[01;32mvaibhavgole@Vank[00m:[01;34m~[00m$ kubectl get pods
No resources found in default namespace.
(base) ]0;vaibhavgole@Vank: ~[01;32mvaibhavgole@Vank[00m:[01;34m~[00m$ kubet[K[K[K[K[Kkue[Kbevctl[K[K[K[Kctl create deploye[Kmnent[K[K[K[K[Kmnt [K[K[K[K[K[K[K[K[K[K[K[K[K[K[K[K[K[K[K[K[K[K[K[K[Kkubecftl [K[K[K[K[K[K[K[K[Kkubectl dc[K[Kcreate depol[K[Kloyment apache-production --image=apache
deployment.apps/apache-production created
(base) ]0;vaibhavgole@Vank: ~[01;32mvaibhavgole@Vank[00m:[01;34m~[00m$ kubectl get pods
NAME                                 READY   STATUS         RESTARTS   AGE
apache-production-54df47b584-jfh9w   0/1     ErrImagePull   0          7s
(base) ]0;vaibhavgole@Vank: ~[01;32mvaibhavgole@Vank[00m:[01;34m~[00m$ kubectl get pods
NAME                                 READY   STATUS             RESTARTS   AGE
apache-production-54df47b584-jfh9w   0/1     ImagePullBackOff   0          24s
(base) ]0;vaibhavgole@Vank: ~[01;32mvaibhavgole@Vank[00m:[01;34m~[00m$ kubectl get pods
NAME                                 READY   STATUS             RESTARTS   AGE
apache-production-54df47b584-jfh9w   0/1     ImagePullBackOff   0          26s
(base) ]0;vaibhavgole@Vank: ~[01;32mvaibhavgole@Vank[00m:[01;34m~[00m$ kubectl get pods
NAME                                 READY   STATUS             RESTARTS   AGE
apache-production-54df47b584-jfh9w   0/1     ImagePullBackOff   0          27s
(base) ]0;vaibhavgole@Vank: ~[01;32mvaibhavgole@Vank[00m:[01;34m~[00m$ kubectl delel[Kte deployment apache-prodcu[K[Kuction
deployment.apps "apache-production" deleted
(base) ]0;vaibhavgole@Vank: ~[01;32mvaibhavgole@Vank[00m:[01;34m~[00m$ kubectl delete deployment apache-productionget pods[Kcreate deployment apache-production --image=apache[K[K[K[K[K[Khttpd
deployment.apps/apache-production created
(base) ]0;vaibhavgole@Vank: ~[01;32mvaibhavgole@Vank[00m:[01;34m~[00m$ kubectl get pods
NAME                                 READY   STATUS              RESTARTS   AGE
apache-production-54df47b584-jfh9w   0/1     Terminating         0          51s
apache-production-fff56bb66-gvlbn    0/1     ContainerCreating   0          3s
(base) ]0;vaibhavgole@Vank: ~[01;32mvaibhavgole@Vank[00m:[01;34m~[00m$ kubectl get pods
NAME                                 READY   STATUS        RESTARTS   AGE
apache-production-54df47b584-jfh9w   0/1     Terminating   0          54s
apache-production-fff56bb66-gvlbn    1/1     Running       0          6s
(base) ]0;vaibhavgole@Vank: ~[01;32mvaibhavgole@Vank[00m:[01;34m~[00m$ kubectl get pods
NAME                                 READY   STATUS        RESTARTS   AGE
apache-production-54df47b584-jfh9w   0/1     Terminating   0          57s
apache-production-fff56bb66-gvlbn    1/1     Running       0          9s
(base) ]0;vaibhavgole@Vank: ~[01;32mvaibhavgole@Vank[00m:[01;34m~[00m$ kubectl get pods
NAME                                 READY   STATUS        RESTARTS   AGE
apache-production-54df47b584-jfh9w   0/1     Terminating   0          58s
apache-production-fff56bb66-gvlbn    1/1     Running       0          10s
(base) ]0;vaibhavgole@Vank: ~[01;32mvaibhavgole@Vank[00m:[01;34m~[00m$ kubectl get pods
NAME                                 READY   STATUS        RESTARTS   AGE
apache-production-54df47b584-jfh9w   0/1     Terminating   0          59s
apache-production-fff56bb66-gvlbn    1/1     Running       0          11s
(base) ]0;vaibhavgole@Vank: ~[01;32mvaibhavgole@Vank[00m:[01;34m~[00m$ kubectl get deployment
NAME                READY   UP-TO-DATE   AVAILABLE   AGE
apache-production   1/1     1            1           17s
(base) ]0;vaibhavgole@Vank: ~[01;32mvaibhavgole@Vank[00m:[01;34m~[00m$ kubectl get deployments
NAME                READY   UP-TO-DATE   AVAILABLE   AGE
apache-production   1/1     1            1           20s
(base) ]0;vaibhavgole@Vank: ~[01;32mvaibhavgole@Vank[00m:[01;34m~[00m$ kubet=[K[K[K[K[K[Kkubectl [K[K[K[K[K[K[K[Kkubectl export deployjment[K[K[K[K[Kment [K[K[K[K[K[K[K[K[K[K[K[K[K[K[K[K[K[K[K[K[K[K[K[K[K[Kkubec tl[K[K[K[Kctl export [K[K[Kse deployment ap[K[Kapache-rp[K[Kprd[Kodcut[K[K[Kuction --prt=[K[K[Kort=80 --typ 
e=NodePort
service/apache-production exposed
(base) ]0;vaibhavgole@Vank: ~[01;32mvaibhavgole@Vank[00m:[01;34m~[00m$ kubectl get p[Ksvc
NAME                TYPE        CLUSTER-IP      EXTERNAL-IP   PORT(S)        AGE
apache-production   NodePort    10.100.64.176   <none>        80:31196/TCP   7s
kubernetes          ClusterIP   10.96.0.1       <none>        443/TCP        18h
(base) ]0;vaibhavgole@Vank: ~[01;32mvaibhavgole@Vank[00m:[01;34m~[00m$ mii[Knikbe [K[K[K[K[K[K[K[Kminikube service apache -[K[K-prodc[Kut[Kction -- [Kurl
http://172.16.33.128:31196
(base) ]0;vaibhavgole@Vank: ~[01;32mvaibhavgole@Vank[00m:[01;34m~[00m$ curl http://172.[K[K[K[K[K[K[K[K[K[K[K[K[K[K[K[Kcurl http://172.16.33.128:31196
<html><body><h1>It works!</h1></body></html>
(base) ]0;vaibhavgole@Vank: ~[01;32mvaibhavgole@Vank[00m:[01;34m~[00m$ curl http://172.16.33.128:31196
<html><body><h1>It works!</h1></body></html>
(base) ]0;vaibhavgole@Vank: ~[01;32mvaibhavgole@Vank[00m:[01;34m~[00m$ 
(base) ]0;vaibhavgole@Vank: ~[01;32mvaibhavgole@Vank[00m:[01;34m~[00m$ c[Kkubectl extend
Error: unknown command "extend" for "kubectl"
Run 'kubectl --help' for usage.
(base) ]0;vaibhavgole@Vank: ~[01;32mvaibhavgole@Vank[00m:[01;34m~[00m$ kubectl --help
kubectl controls the Kubernetes cluster manager.

 Find more information at:
https://kubernetes.io/docs/reference/kubectl/overview/

Basic Commands (Beginner):
  create        Create a resource from a file or from stdin.
  expose        Take a replication controller, service, deployment or pod and
expose it as a new Kubernetes Service
  run           Run a particular image on the cluster
  set           Set specific features on objects

Basic Commands (Intermediate):
  explain       Documentation of resources
  get           Display one or many resources
  edit          Edit a resource on the server
  delete        Delete resources by filenames, stdin, resources and names, or by
resources and label selector

Deploy Commands:
  rollout       Manage the rollout of a resource
  scale         Set a new size for a Deployment, ReplicaSet or Replication
Controller
  autoscale     Auto-scale a Deployment, ReplicaSet, or ReplicationController

Cluster Management Commands:
  certificate   Modify certificate resources.
  cluster-info  Display cluster info
  top           Display Resource (CPU/Memory/Storage) usage.
  cordon        Mark node as unschedulable
  uncordon      Mark node as schedulable
  drain         Drain node in preparation for maintenance
  taint         Update the taints on one or more nodes

Troubleshooting and Debugging Commands:
  describe      Show details of a specific resource or group of resources
  logs          Print the logs for a container in a pod
  attach        Attach to a running container
  exec          Execute a command in a container
  port-forward  Forward one or more local ports to a pod
  proxy         Run a proxy to the Kubernetes API server
  cp            Copy files and directories to and from containers.
  auth          Inspect authorization
  debug         Create debugging sessions for troubleshooting workloads and
nodes

Advanced Commands:
  diff          Diff live version against would-be applied version
  apply         Apply a configuration to a resource by filename or stdin
  patch         Update field(s) of a resource
  replace       Replace a resource by filename or stdin
  wait          Experimental: Wait for a specific condition on one or many
resources.
  kustomize     Build a kustomization target from a directory or a remote url.

Settings Commands:
  label         Update the labels on a resource
  annotate      Update the annotations on a resource
  completion    Output shell completion code for the specified shell (bash or
zsh)

Other Commands:
  api-resources Print the supported API resources on the server
  api-versions  Print the supported API versions on the server, in the form of
"group/version"
  config        Modify kubeconfig files
  plugin        Provides utilities for interacting with plugins.
  version       Print the client and server version information

Usage:
  kubectl [flags] [options]

Use "kubectl <command> --help" for more information about a given command.
Use "kubectl options" for a list of global command-line options (applies to all
commands).
(base) ]0;vaibhavgole@Vank: ~[01;32mvaibhavgole@Vank[00m:[01;34m~[00m$ kubeclt scale deployment apache-proudctio[K[K[K[K[K[Kduction --[K[K--replica=3
kubeclt: command not found
(base) ]0;vaibhavgole@Vank: ~[01;32mvaibhavgole@Vank[00m:[01;34m~[00m$ kubeclt scale deployment apache-production --replica=3[2@^[[2~scale deployment apache-production --replica=3 [A
(base) ]0;vaibhavgole@Vank: ~[01;32mvaibhavgole@Vank[00m:[01;34m~[00m$ [C[C[C[C[C[C[C[C[C[C[C[C[C^Cscale deployment apache-production --replica=
=3[A
(base) ]0;vaibhavgole@Vank: ~[01;32mvaibhavgole@Vank[00m:[01;34m~[00m$ [C[C[C[C[C[C[C[C[C[C[C[C[C[C[Cscale deployment apache-production --replica=3 
[K[A[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[1P

[K[A[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[1P[1P[2P[1P[1P[1P[1P[1@c[1@t[1@l[1@ 
Error: unknown flag: --replica
See 'kubectl scale --help' for usage.
(base) ]0;vaibhavgole@Vank: ~[01;32mvaibhavgole@Vank[00m:[01;34m~[00m$ kubectl scale =[K[K-- [K[K[K --he[Kelp
Set a new size for a Deployment, ReplicaSet, Replication Controller, or
StatefulSet.

 Scale also allows users to specify one or more preconditions for the scale
action.

 If --current-replicas or --resource-version is specified, it is validated
before the scale is attempted, and it is guaranteed that the precondition holds
true when the scale is sent to the server.

Examples:
  # Scale a replicaset named 'foo' to 3.
  kubectl scale --replicas=3 rs/foo
  
  # Scale a resource identified by type and name specified in "foo.yaml" to 3.
  kubectl scale --replicas=3 -f foo.yaml
  
  # If the deployment named mysql's current size is 2, scale mysql to 3.
  kubectl scale --current-replicas=2 --replicas=3 deployment/mysql
  
  # Scale multiple replication controllers.
  kubectl scale --replicas=5 rc/foo rc/bar rc/baz
  
  # Scale statefulset named 'web' to 3.
  kubectl scale --replicas=3 statefulset/web

Options:
      --all=false: Select all resources in the namespace of the specified
resource types
      --allow-missing-template-keys=true: If true, ignore any errors in
templates when a field or map key is missing in the template. Only applies to
golang and jsonpath output formats.
      --current-replicas=-1: Precondition for current size. Requires that the
current size of the resource match this value in order to scale.
      --dry-run='none': Must be "none", "server", or "client". If client
strategy, only print the object that would be sent, without sending it. If
server strategy, submit server-side request without persisting the resource.
  -f, --filename=[]: Filename, directory, or URL to files identifying the
resource to set a new size
  -k, --kustomize='': Process the kustomization directory. This flag can't be
used together with -f or -R.
  -o, --output='': Output format. One of:
json|yaml|name|go-template|go-template-file|template|templatefile|jsonpath|jsonpath-as-json|jsonpath-file.
      --record=false: Record current kubectl command in the resource annotation.
If set to false, do not record the command. If set to true, record the command.
If not set, default to updating the existing annotation value only if one
already exists.
  -R, --recursive=false: Process the directory used in -f, --filename
recursively. Useful when you want to manage related manifests organized within
the same directory.
      --replicas=0: The new desired number of replicas. Required.
      --resource-version='': Precondition for resource version. Requires that
the current resource version match this value in order to scale.
  -l, --selector='': Selector (label query) to filter on, supports '=', '==',
and '!='.(e.g. -l key1=value1,key2=value2)
      --template='': Template string or path to template file to use when
-o=go-template, -o=go-template-file. The template format is golang templates
[http://golang.org/pkg/text/template/#pkg-overview].
      --timeout=0s: The length of time to wait before giving up on a scale
operation, zero means don't wait. Any other values should contain a
corresponding time unit (e.g. 1s, 2m, 3h).

Usage:
  kubectl scale [--resource-version=version] [--current-replicas=count]
--replicas=COUNT (-f FILENAME | TYPE NAME) [options]

Use "kubectl options" for a list of global command-line options (applies to all
commands).
(base) ]0;vaibhavgole@Vank: ~[01;32mvaibhavgole@Vank[00m:[01;34m~[00m$ kubectl scale --helpdeployment apache-production --replica=3s=3
deployment.apps/apache-production scaled
(base) ]0;vaibhavgole@Vank: ~[01;32mvaibhavgole@Vank[00m:[01;34m~[00m$ kubecgtl [K[K[K[K[Kctl ge [Kt pods
NAME                                READY   STATUS    RESTARTS   AGE
apache-production-fff56bb66-gvlbn   1/1     Running   0          6m37s
apache-production-fff56bb66-pcc7v   1/1     Running   0          13s
apache-production-fff56bb66-tlpwc   1/1     Running   0          13s
(base) ]0;vaibhavgole@Vank: ~[01;32mvaibhavgole@Vank[00m:[01;34m~[00m$ kubectl get deployment 
NAME                READY   UP-TO-DATE   AVAILABLE   AGE
apache-production   3/3     3            3           6m43s
(base) ]0;vaibhavgole@Vank: ~[01;32mvaibhavgole@Vank[00m:[01;34m~[00m$ kubecgtl [K[K[K[Ktl get svc
NAME                TYPE        CLUSTER-IP      EXTERNAL-IP   PORT(S)        AGE
apache-production   NodePort    10.100.64.176   <none>        80:31196/TCP   5m12s
kubernetes          ClusterIP   10.96.0.1       <none>        443/TCP        18h
(base) ]0;vaibhavgole@Vank: ~[01;32mvaibhavgole@Vank[00m:[01;34m~[00m$ 
(base) ]0;vaibhavgole@Vank: ~[01;32mvaibhavgole@Vank[00m:[01;34m~[00m$ u[Kkubectl dlete[K[K[K[Kelete deployment apache-production
deployment.apps "apache-production" deleted
(base) ]0;vaibhavgole@Vank: ~[01;32mvaibhavgole@Vank[00m:[01;34m~[00m$ kub[K[K[Kkubectl get pods
NAME                                READY   STATUS        RESTARTS   AGE
apache-production-fff56bb66-gvlbn   0/1     Terminating   0          7m8s
apache-production-fff56bb66-pcc7v   0/1     Terminating   0          44s
apache-production-fff56bb66-tlpwc   0/1     Terminating   0          44s
(base) ]0;vaibhavgole@Vank: ~[01;32mvaibhavgole@Vank[00m:[01;34m~[00m$ kubectl get svc
NAME                TYPE        CLUSTER-IP      EXTERNAL-IP   PORT(S)        AGE
apache-production   NodePort    10.100.64.176   <none>        80:31196/TCP   5m36s
kubernetes          ClusterIP   10.96.0.1       <none>        443/TCP        18h
(base) ]0;vaibhavgole@Vank: ~[01;32mvaibhavgole@Vank[00m:[01;34m~[00m$ kubect get pods
kubect: command not found
(base) ]0;vaibhavgole@Vank: ~[01;32mvaibhavgole@Vank[00m:[01;34m~[00m$ kbu[K[Kubectl get pods
No resources found in default namespace.
(base) ]0;vaibhavgole@Vank: ~[01;32mvaibhavgole@Vank[00m:[01;34m~[00m$ k[Kkubectl get svc
NAME                TYPE        CLUSTER-IP      EXTERNAL-IP   PORT(S)        AGE
apache-production   NodePort    10.100.64.176   <none>        80:31196/TCP   6m7s
kubernetes          ClusterIP   10.96.0.1       <none>        443/TCP        18h
(base) ]0;vaibhavgole@Vank: ~[01;32mvaibhavgole@Vank[00m:[01;34m~[00m$ kubectl delte[Ke[K[Kelet[K[K[Kte svc app[Kache-rp[K[Kr[Kproduction
service "apache-production" deleted
(base) ]0;vaibhavgole@Vank: ~[01;32mvaibhavgole@Vank[00m:[01;34m~[00m$ 
(base) ]0;vaibhavgole@Vank: ~[01;32mvaibhavgole@Vank[00m:[01;34m~[00m$ kubectl get pods
No resources found in default namespace.
(base) ]0;vaibhavgole@Vank: ~[01;32mvaibhavgole@Vank[00m:[01;34m~[00m$ minikbe [K[K[Kube svc [K[K[Kervice kubernetes --url
😿  service default/kubernetes has no node port
(base) ]0;vaibhavgole@Vank: ~[01;32mvaibhavgole@Vank[00m:[01;34m~[00m$ exit
exit
```

Script done on 2022-09-01 09:38:21+0530
