# Despregue dunha Arquitectura Web Sinxela en Kubernetes

Este documento describe como despregar unha aplicación web sinxela en Kubernetes con tres compoñentes:

- Frontend en Nginx (HTML estático)
- Backend en Flask (API Python)
- Base de datos MySQL (opcional neste exemplo)

---

## Estrutura do proxecto

```
proxecto-simple/
├── backend/
│   ├── app.py
│   ├── requirements.txt
│   └── Dockerfile
├── frontend/
│   ├── index.html
│   └── Dockerfile
├── mysql.yaml
├── backend.yaml
├── frontend.yaml

```

---

## Paso 1: Construír as imaxes Docker

```bash
# Backend
docker build -t backend-image ./backend

# Frontend
docker build -t frontend-image ./frontend
```

Se estás usando Minikube, activa o contorno Docker dentro del **antes de construir as imaxes**:

```bash
eval $(minikube docker-env)
```

---

## Paso 2: Despregue en Kubernetes

```bash
# Despregamos a base de datos (opcional)
kubectl apply -f proxecto-simple/mysql.yaml

# Despregamos o backend Flask
kubectl apply -f proxecto-simple/backend.yaml

# Despregamos o frontend en Nginx
kubectl apply -f proxecto-simple/frontend.yaml
```

---

## Paso 3: Verificar que todo funciona

```bash
kubectl get pods
kubectl get services
```

Deberías ver os tres Pods correndo e os seus Servizos asociados.

---

## Paso 4: Acceder á aplicación web

Usando Minikube:

```bash
minikube service frontend
```

Ou manualmente:

```bash
minikube ip
```

Abre no navegador:

```
http://<IP>:30080
```

---

## Probas rápidas

- O navegador debería mostrar unha páxina HTML cunha mensaxe do backend.
- A consola do navegador debería mostrar a resposta da API.

---

## Limpando o entorno

```bash
kubectl delete -f proxecto-simple/frontend.yaml
kubectl delete -f proxecto-simple/backend.yaml
kubectl delete -f proxecto-simple/mysql.yaml
```

---

## Notas adicionais

- Este exemplo usa Pods simples en lugar de Deployments para simplificar o despregue.
- Os contedores non teñen volumes nin probes.
- As conexións entre frontend e backend usan DNS interno de Kubernetes (ex: http://backend:5000).
