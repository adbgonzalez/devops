# 🧾 Boletín de ejercicios sobre Git y GitHub (con soluciones)

---

## 1. Configuración inicial de Git
```bash
git config --global user.name "Nombre Apellido"
git config --global user.email "usuario@example.com"
git config --global core.editor nano
git config --global core.autocrlf input
git config --list
```

---

## 2. Creación de un nuevo repositorio local
```bash
mkdir proyecto1
cd proyecto1
git init
echo "Proyecto inicial" > README.md
git add README.md
git commit -m "Primer commit"
```

---

## 3. Seguimiento de cambios
```bash
echo "Nueva línea" >> README.md
git status
git diff
git add README.md
git commit -m "Añadida nueva línea al README"
git log --oneline
```

---

## 4. Trabajo con ramas
```bash
git branch feature-1
git checkout feature-1
echo "Nota temporal" > nota.txt
git add nota.txt
git commit -m "Añadido archivo nota.txt"
git checkout main
ls
git merge feature-1
git branch -d feature-1
```

---

## 5. Clonación de un repositorio remoto
```bash
git clone https://github.com/usuario/practica1.git
cd practica1
echo "Autor: Nombre Apellido" > autor.txt
git add autor.txt
git commit -m "Añadido archivo autor.txt"
git push origin main
```

---

## 6. Subida de un proyecto local a GitHub
```bash
git remote add origin https://github.com/usuario/proyecto1.git
git branch -M main
git push -u origin main
```

---

## 7. Deshacer cambios y restaurar versiones
```bash
echo "Cambio incorrecto" >> README.md
git restore README.md
echo "Commit erróneo" >> README.md
git add README.md
git commit -m "Error tipográfico"
git commit --amend -m "Corregido error tipográfico"
git reset --hard HEAD~1
```

---

## 8. Uso de etiquetas (tags)
```bash
git tag v1.0
git tag
git push origin v1.0
git tag v1.1
git tag -d v1.1
```

---

## 9. Trabajo colaborativo con ramas
```bash
git branch correccion-bug
git checkout correccion-bug
echo "Corrección menor" >> README.md
git add README.md
git commit -m "Corrección menor en el README"
git checkout main
git merge correccion-bug
git branch -d correccion-bug
```

---

## 10. Creación de un fork y *pull request*
```bash
# (1) Realizar el fork desde GitHub
git clone https://github.com/usuario/repositorio-fork.git
cd repositorio-fork
git branch mejora-docs
git checkout mejora-docs
echo "Mejora en la documentación" >> README.md
git add README.md
git commit -m "Añadida mejora en la documentación"
git push origin mejora-docs
# (2) Crear el Pull Request desde la web de GitHub
```
