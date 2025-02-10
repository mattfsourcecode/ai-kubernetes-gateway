# Kubernetes with Rust, MicroK8s, cert-manager, and Gateway API

This project demonstrates a [**Kubernetes**](https://kubernetes.io/) cluster managed with [**MicroK8s**](https://microk8s.io/) and integrates a [**Rust**](https://www.rust-lang.org/) application that interacts with the Kubernetes API using [**Tokio**](https://tokio.rs/) and the [**kube**](https://kube.rs/) crate. The setup showcases modern Kubernetes networking using the [Gateway API](https://gateway-api.sigs.k8s.io/), with [**cert-manager**](https://cert-manager.io/) handling TLS certificates and includes [**LocalAI**](https://localai.io/) for efficient, self-hosted AI capabilities. By leveraging MicroK8s as a Kubernetes environment, this project provides a streamlined, lightweight solution for developing and testing Kubernetes-integrated applications with a focus on modern networking patterns and AI integration.

## Gateway API Implementation

This project implements the Kubernetes Gateway API, which represents the next evolution in Kubernetes service networking. Unlike the traditional Ingress resource, the Gateway API provides:

- **Enhanced Traffic Management**: Using HTTPRoute resources for more granular traffic control
- **Improved Security**: Integrated TLS termination with cert-manager for automated certificate management
- **Better Separation of Concerns**: Clear distinction between infrastructure concerns (Gateway) and application routing (HTTPRoute)
- **Future-Proof Architecture**: Built on an extensible, role-oriented design that supports modern deployment patterns

The implementation includes:

- A Gateway resource that serves as the entry point for HTTPS traffic
- HTTPRoute definitions for URL-based routing
- Integration with cert-manager for automated TLS certificate management
- Self-signed certificates for development and testing

## Core Rust Application

The Rust app connects to the Kubernetes cluster and lists all Pods in the default namespace. This application serves as a foundation that can be extended with various capabilities:

- **Pod Management**: Create, delete, or monitor Pods programmatically.
- **Log Streaming**: Fetch and stream logs from running Pods for debugging.
- **Resource Management**: Manage ConfigMaps, Secrets, Deployments, Services, and Gateway resources dynamically.
- **Metrics and Observability**: Collect and aggregate resource usage metrics (CPU, memory) and monitor the health of workloads and cluster events.
- **Automated Scaling**: Implement Horizontal Pod Autoscaling or Cluster Autoscaling based on real-time load.
- **Security Auditing**: Monitor Role-Based Access Control (RBAC), enforce policies, and rotate Secrets.
- **Custom Resource Management**: Extend Kubernetes with Custom Resource Definitions (CRDs) and automate tasks with Operators.
- **Event-Driven Automation**: Trigger app actions based on Kubernetes events or webhooks.
- **Advanced Routing Features**: Implement sophisticated traffic management using Gateway API features like request matching, filtering, and traffic splitting.
- **Downtime Recovery**: Automate resource backups and implement recovery mechanisms for downtime scenarios.
- **Multi-Tenancy Support**: Manage namespaces, set quotas, and isolate resources for different teams or applications.

## LocalAI Integration

The project leverages LocalAI to offer self-hosted AI features within the Kubernetes cluster. This integration offers several advantages:

- **Self-Hosted AI**: Enables running AI models locally within your Kubernetes cluster, helping enhance data privacy and potentially reducing latency
- **Resource Efficiency**: Aimed at running on local infrastructure with configurable resource allocation
- **API Compatibility**: Designed to work with several common AI API formats, facilitating integration with existing applications
- **Customizable Models**: Support for selected AI models that may be tailored to specific use cases
- **Scalability**: Kubernetes-native scaling features to help manage varying workloads
- **Cost-Effective**: Reduce dependency on cloud API costs by running models locally
- **Private Infrastructure**: Help manage sensitive data on your preferred infrastructure while leveraging AI features
