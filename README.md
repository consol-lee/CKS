# Certified Kubernetes Security Specialist

- [Udemy](https://www.udemy.com/course/certified-kubernetes-security-specialist/)
- Kubernetes v1.24

## Cluster Setup 10%
- Primarily involves the ability to configure network security policies that enforce pod access levels and restrictions.
- Tests the ability to utilize the CIS benchmark tool that scans the Kubernetes cluster and provides a list of recommended configurations for different components of the cluster.
- Tests the ability to configure the ingress component to apply different URL settings and securely route traffic to services within the Kubernetes cluster.
- Tests the ability to verify the authenticity of downloaded binaries of Kubernetes packages before installing and deploying them to your infrastructure.
- The ability to protect node metadata and endpoints.

## Cluster Hardening 15%
- Configure levels of restrictions to the Kubernetes API.
- Tests the ability to manage Role Based Access Controls (RBAC) to limit access of different users within the cluster.
- Tests the ability to manage service accounts and the awareness of namespaced access with just the proper permissions.
- The ability to perform version upgrades for the components and the cluster itself.

## System Hardening 15%
- Tests the ability to apply the Least Privilege Principle to users at the Operating System Level to minimize attack entries.
- Manage Identity and Access Management (IAM).
- Tests the ability to manage firewalls and identify network port activities.
- Tests knowledge using tools like AppArmor and seccomp and its integration to the Kubernetes cluster.

## Minimize Microservice Vulnerabilities 20%
- Set up appropriate OS-level security domains, e.g., using PSP, OPA, security contexts.
- Tests the ability to manage different types of Kubernetes secrets and configure them into pods.
- Tests the ability to use container runtime sandboxes like gvisor and kata containers for improved container isolation and security.
- Implement pod-to-pod communication security using encryption like SSL and mTLS.

## Supply Chain Security 20%
- Tests the knowledge of building containers that are small, efficient, and have fewer components (to reduce attack surface).
- Manage restrictions in image registries, whether public or private. Cryptographically sign container images. Verify signatures to ensure image authenticity before deployment.
- Tests knowledge using tools like kubesec that scans and scores images based on security and performance.
- Tests knowledge in vulnerability scanning tools for container images like Trivy.

## Monitoring, Logging, and Runtime Security 20%
- Tests the ability to identify potentially malicious activities in syscall processes.
- Detect threats within a physical infrastructure, apps, networks, data, users, and workloads
- Tests the knowledge in detecting all possible attack phases and areas to stop their spread.
- Perform deep analytical investigation and identification of bad actors within the environment.
- Ensure immutability of containers at runtime by limiting read/write access to root filesystems.
- Tests the knowledge in enabling audit logs in the cluster and using them.