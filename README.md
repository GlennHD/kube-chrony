# kube-chrony
Chrony Alpine NTP Server for Kubernetes via Helm
# Usage
```bash
git clone https://github.com/GlennHD/kube-chrony.git        # Download the chart
cd kube-chrony                                              # Navigate to the folder
nano values.yaml                                            # Adjust the values.yaml
helm install -n jh -f values.yaml kube-chrony ./            # Install the chart
```
# Other Usage
```bash
cd kube-chrony
helm upgrade -f values.yaml kube-chrony ./                  # Update the config
helm uninstall kube-chrony                                  # Uninstall the chart
kubectl describe pod kube-chrony                            # See whats going on in the pod
kubectl get svc -w kube-chrony                              # See whats going on with the service
ntpdate -q 10.0.8.222                                       # test ntp query against load balancer <IP>:123
```
# NOTES
- Adjust NodeSelector in values.yaml as needed. If you do not wish to use it, just replace with `nodeSelector: {}`. Otherwise, add a label to a node for ntp:ntp.
- Change IP addres '10.0.8.222' to an IP address within your Load Balancer IP pool range.
- Change 'jh' to whatever namespace you want.
- Spin up/down replicaCount as you see fit.
- Modify ntpServers using your favorite time servers.
