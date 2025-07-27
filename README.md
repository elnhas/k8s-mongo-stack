# K8s Mongo Stack 🚀

This project demonstrates how to deploy **MongoDB** (with persistence) and **Mongo Express** (a web-based admin UI) on a Kubernetes cluster.  
It uses **StatefulSets**, **Secrets**, **ConfigMaps**, and **OpenEBS StorageClass** to create a complete, production-like setup.

---

## 📦 Features
✅ **MongoDB StatefulSet** – Ensures stable network identity & persistent data.  
✅ **Mongo Express Deployment** – A lightweight admin UI for MongoDB.  
✅ **Secrets Management** – Stores sensitive credentials securely.  
✅ **ConfigMap Usage** – Keeps service URLs configurable.  
✅ **Headless & ClusterIP Services** – Supports both internal and external communication.  
✅ **OpenEBS StorageClass** – Handles local persistent volumes.

---

## 🏗️ Kubernetes Components
- **MongoDB StatefulSet** – Deploys MongoDB with persistent storage.
- **Mongo Express Deployment** – Provides the web interface.
- **Secrets** – Stores admin usernames & passwords (Base64 encoded).
- **ConfigMap** – Defines the MongoDB URL for Mongo Express.
- **Services** – 
  - `mongodb-headless`: Headless service for MongoDB pods
  - `mongodb-clusterip`: Internal access for apps
  - `mongo-express-lb`: LoadBalancer for Mongo Express UI
- **StorageClass** – Uses `openebs-local` for PV provisioning.

---

## 📂 Project Structure

├── mongoDB-stateful.yaml
├── mongoEXP-debloyment.yaml
├── secrets.yaml
├── configmap.yaml
├── services.yaml
├── storageclass.yaml


---

## 🚀 How to Deploy
1️⃣ **Apply the StorageClass**

```bash
kubectl apply -f storageclass.yaml
kubectl apply -f secrets.yaml
kubectl apply -f configmap.yaml
kubectl apply -f mongoDB-stateful.yaml



## 🚀 Access Mongo Express
## Once deployed, Mongo Express is accessible via the LoadBalancer service:

http://<your-node-ip>:<LoadBalancer-Port>



## Why this project?

This setup is ideal for:

Learning Kubernetes StatefulSets vs Deployments

Understanding Persistent Volumes & StorageClasses

Managing Secrets & ConfigMaps

Exposing apps via ClusterIP & LoadBalancer

