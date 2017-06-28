# GKE Toolbox

## Introduction

The GKE Toolbox is a Helm chart that installs and configures useful tools into your Container Engine Clusters

## Tools

### Enabled by Default
- [Prometheus](https://prometheus.io/) -> Kubernetes native monitoring and alerting of your nodes, pods, services, and controller states
- [Grafana](https://grafana.com/) -> Flexible Dashboards for Kubernetes 
- [Nginx Ingress](https://github.com/kubernetes/ingress/tree/master/controllers/nginx) -> Allows you to use Nginx as an ingress controller which can be more flexible than the Google HTTP(S) load balancer
- [Kube Lego](https://github.com/jetstack/kube-lego) -> Automatically get TLS certificates for your ingresses
- [External DNS](https://github.com/kubernetes-incubator/external-dns) -> Map your service and ingress IPs to DNS records in Cloud DNS

### Disabled by Default
- [Spinnaker](https://www.spinnaker.io/) -> Continuous Delivery solution for Kubernetes workloads
- [Istio](https://istio.io) -> Kubernetes native service mesh

## Prerequisites
1. Credentials to a Container Engine cluster with at least 3 cores and 8GB or RAM
1. For external-dns, a cluster with the following scope enabled at creation: `https://www.googleapis.com/auth/ndev.clouddns.readwrite`

## Getting Started

1. Clone this repository

        git clone https://github.com/viglesiasce/gke-toolbox

1. Change directories to the repo

        cd gke-toolbox

1. [Install Helm](https://github.com/kubernetes/helm/blob/master/docs/install.md#installing-the-helm-client)
1. Initialize Helm

        helm init

1. Install this Chart

        helm install -n toolbox .