# Secrets

- Used to store sensitive info (e.g. username, passwords)
- Similar to config maps BUT **Encrypted**

### How to use Secrets

- Imperative

  - `k create secret generic <secret-name> --from-literal=<key>=<value>`
  - `k create secret generic <secret-name> --from-file=<path-to-file>`

- Declarative
  - ![alt text](./images/image_10.png)
- Encode
- ![alt text](./images/image_11.png)
- Decode
- ![alt text](./images/image_12.png)
- Using the secrets in pods
- ![alt text](./images/image_13.png)
- Secrets in Pods as Volumes
- ![alt text](./images/image_14.png)

- Note:
  - Secrets are not encrypted, only encoded
  - Secrets are not encrypted in ETCD
  - Configure least-privilege access to secrets - RBAC(Role base access control)
  - Consider third-party secrets store providers
