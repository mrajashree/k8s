# k8s
Setting up k8s cluster from scratch

From -> https://kubernetes.io/docs/getting-started-guides/fedora/fedora_manual_config/
https://kubernetes.io/docs/getting-started-guides/fedora/flannel_multi_node_cluster/
https://kubernetes.io/docs/tasks/access-application-cluster/web-ui-dashboard/

On both setups (Fedora 26 VMs)

```
dnf config-manager --set-enabled updates-testing (Get k8s 1.7)
dnf install -y kubernetes
```
Edit /etc/kubernetes/config on both </br>
Edit /etc/kubernetes/apiserver on master </br>
Edit /etc/kubernetes/kubelet on node </br>

Setup flannel networking following https://kubernetes.io/docs/getting-started-guides/fedora/flannel_multi_node_cluster/

If https://rawgit.com/kubernetes/dashboard/master/src/deploy/kubernetes-dashboard.yaml provided in web-ui setup link does not work with the default args, provide
--apiserver-host param pointing to master IP

Check if dashboard pod is running, access it on masterIP:8080/ui </br>
Start another pod, check ping from within the pod works 