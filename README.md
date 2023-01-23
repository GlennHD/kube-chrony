# kube-chrony
Chrony Alpine NTP Server for Kubernetes via Helm
# Usage
```bash
git clone https://github.com/GlennHD/kube-chrony.git                  # Download the chart
cd kube-chrony                                              # Navigate to the folder
nano values.yaml                                            # Adjust the values.yaml
helm install -f values.yaml kube-chrony ./                  # Install the chart
```
# Other Usage
```bash
cd kube-chrony
helm upgrade -f values.yaml kube-chrony ./                  # Update the config
helm uninstall kube-chrony                                  # Uninstall the chart
kubectl describe pod kube-chrony                            # See whats going on in the pod
kubectl get svc -w kube-chrony                              # See whats going on with the service
```
# NOTES
- Adjust NodeSelector in values.yaml as needed. If you do not wish to use it, just replace with `nodeSelector: {}`
