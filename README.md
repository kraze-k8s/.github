# 🛰️ Kraze — Kubernetes Rules for Access Zone Enforcement

**Kraze** is an open-source system for continuously validating **network accessibility** across **zones** in a Kubernetes-native environment.

It helps platform teams ensure that **ingress points are reachable (or restricted) as intended**, from specific parts of the infrastructure — with policy-as-code, automated checks, and intuitive observability.



## 🔍 Why Kraze?

Modern cloud-native applications depend on assumptions about **network reachability** — from internal services, cloud regions, or edge zones. Kraze makes those assumptions **explicit**, **enforceable**, and **monitorable**.

No more silent misconfigurations. No more "it worked from staging, but not from prod."


## 🧩 Architecture Overview

Kraze is composed of three main components:

### 1. **Operator**
- Defines and manages **network zones** and **connectivity rules** via Kubernetes **CRDs**.
- Coordinates agents and orchestrates rule evaluation.
- Exposes configuration and status to the Web UI.

### 2. **Agent**
- Deployed in each **network zone** (e.g., namespace, cluster, cloud region).
- Executes **HTTP/S checks** to ingress targets, according to assigned rules.
- Verifies zone identity (e.g., via IP/CIDR match).
- Reports results to the Operator.

### 3. **Web UI**
- Central dashboard to monitor **rule status**, **zone reachability**, and **violations**.
- Supports read-only mode for compliance-safe visibility.


## 🚀 Getting Started

Each component has its own repository:

- [`kraze-operator`](https://github.com/kraze/kraze-operator)
- [`kraze-agent`](https://github.com/kraze/kraze-agent)
- [`kraze-webui`](https://github.com/kraze/kraze-webui)

See the respective READMEs for deployment instructions and configuration details.


## 📦 Example Use Cases

- Verify that internal admin endpoints are not reachable from public zones.
- Detect unexpected exposure of services across environments.
- Simple uptime monitoring


## 🛡️ Built for Security & Scalability

- Policy-as-code via CRDs
- Secure agent/operator communication
- Designed for multi-zone setups


## 📝 License

Kraze is open-source and licensed under the [GNU AGPL v3.0 License](https://www.gnu.org/licenses/agpl-3.0.html).
