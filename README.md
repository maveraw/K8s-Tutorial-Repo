# Kubernetes Tutorial Repository

## Introduction
This repository provides a structured learning path for Kubernetes based on the YouTube playlist [Learn Kubernetes | A Comprehensive Guide](https://www.youtube.com/playlist?list=PLnKy4XevqUM8fWHuvpcgHwA8tmmvd5WLZ). It covers setting up a Kubernetes cluster, deploying applications, and understanding core Kubernetes concepts.

## Repository Structure
```
/kubernetes-tutorial
│── /tutorials           # Step-by-step guides
│── /scripts             # Automation and setup scripts
│── /resources           # Reference materials, diagrams, and links
│── README.md            # Overview and learning path
```

## Getting Started
### Prerequisites
- A system with a compatible OS (e.g., Ubuntu 20.04)
- Installed Docker (for container runtime)
- Installed Kubernetes tools: `kubectl`, `kubeadm`, `kubelet`

### Setting Up a Basic Kubernetes Cluster
1. **Initialize the Control Plane**
   ```bash
   sudo kubeadm init
   ```
2. **Configure kubectl**
   ```bash
   mkdir -p $HOME/.kube
   sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
   sudo chown $(id -u):$(id -g) $HOME/.kube/config
   ```
3. **Deploy a Network Add-on (Calico)**
   ```bash
   kubectl apply -f https://docs.projectcalico.org/manifests/calico.yaml
   ```
4. **Join Worker Nodes**
   ```bash
   kubeadm token create --print-join-command
   ```
   Run the output command on each worker node.

5. **Verify the Cluster**
   ```bash
   kubectl get nodes
   ```

## Next Steps
- Follow the tutorials in `/tutorials` to learn more advanced topics.
- Explore automation scripts in `/scripts` to simplify Kubernetes management.

## Contributing
Feel free to contribute by adding improvements, issues, or new tutorials!

