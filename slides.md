---
# try also 'default' to start simple
theme: apple-basic
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://source.unsplash.com/collection/94734566/1920x1080
# apply any windi css classes to the current slide
class: 'text-center'
# https://sli.dev/custom/highlighters.html
highlighter: shiki
layout: intro
# some information about the slides, markdown enabled
info: |
  ## Kubernetes spiegato a mia zia
---

# Kubernetes explained to my aunt

stay cool: if you tried everything and only this remains you've got nothing to lose

<div class="absolute bottom-10">
  <span class="font-700">
    by Alessio Biancalana
  </span>
</div>


---
layout: statement
---

# Disclaimer: no ~~financial~~ professional advice
I have some of this stuff in production, but it's on my own and I'll eventually pay the price


---
layout: statement
---

# Think about it!
![Meme about k8s fatigue](k8s-meme-stress.jpg)

---
layout: statement
---

# Kubernetes is a platform


---
layout: image
image: 'k8s-schematics.jpg'
---


---
layout: default
---
# Fundamentals

- Ingress
- Services
- Deployments/StatfulSets
- Pods


---
layout: statement
---
# Ingress Controller
Think of it like a router: where should this request go?


---
layout: statement
---
# Service
If you need some real reference, that's your friendly neighborhood reverse proxy


---
layout: statement
---
# Deployments
A declarative way to tell your cluster "I want that container, I want it now, and I want it bound on that port / those ports"


---
layout: statement
---
# StatefulSets
Like a deployment, _but_ it maintains ordering and uniqueness of Pods inside.

What the hell does this even mean? It means we can use StatefulSets to deploy stateful services or databases


---
layout: statement
---
# Pods
The smallest computing unit that Kubernetes can manage.

Composed by:

- 1 container (mandatory)
- sidecar containers (optional)
- init containers (optional)


---
layout: statement
---
# How to deploy your own single-node cluster using k3s
K3s is very cool!

```sh
$ curl -sfL https://get.k3s.io | sh -
$ cat /etc/rancher/k3s/k3s.yaml
```

---
layout: default
---
# Kubeconfig's anatomy

```yaml
apiVersion: v1
clusters:
- cluster:
    certificate-authority-data: LS0tLS1CRUdJTiBDRV...
    server: https://127.0.0.1:6443
  name: default
contexts:
- context:
    cluster: default
    user: default
  name: default
current-context: default
kind: Config
preferences: {}
users:
- name: default
  user:
    client-certificate-data: LS0tLS1CRUdJTiBDRVJUS...
    client-key-data: LS0tLS1CRUdJTiBFQyBQUklWQVRFI...

```


---
layout: statement
---
# Who wants a bold opinion?
This is way better than Ansible when it comes to standards and it even makes more sense when you have to scale


---
layout: intro-image-right
image: kubernetes-burgers.jpg
---
# Another meme because reasons

---
layout: center
class: text-center
---

# Alessio Biancalana

Senior Software Engineer @ Prima.it

@dottorblaster
