# 🧾 Boletín de exercicios sobre Git e GitHub (con solucións)

---

## 1. Configuración inicial de Git
```bash
git config --global user.name "Nome Apelido"
git config --global user.email "usuario@example.com"
git config --global core.editor nano
git config --global core.autocrlf input
git config --list
```

---

## 2. Creación dun novo repositorio local
```bash
mkdir proxecto1
cd proxecto1
git init
echo "Proxecto inicial" > README.md
git add README.md
git commit -m "Primeiro commit"
```

---

## 3. Seguimento de cambios
```bash
echo "Nova liña" >> README.md
git status
git diff
git add README.md
git commit -m "Engadida nova liña ao README"
git log --oneline
```

---

## 4. Traballo con ramas
```bash
git branch feature-1
git checkout feature-1
echo "Nota temporal" > nota.txt
git add nota.txt
git commit -m "Engadido ficheiro nota.txt"
git checkout main
ls
git merge feature-1
git branch -d feature-1
```

---

## 5. Clonación dun repositorio remoto
```bash
git clone https://github.com/usuario/practica1.git
cd practica1
echo "Autor: Nome Apelido" > autor.txt
git add autor.txt
git commit -m "Engadido ficheiro autor.txt"
git push origin main
```

---

## 6. Subida dun proxecto local a GitHub
```bash
git remote add origin https://github.com/usuario/proxecto1.git
git branch -M main
git push -u origin main
```

---

## 7. Desfacer cambios e restaurar versións
```bash
echo "Cambio incorrecto" >> README.md
git restore README.md
echo "Commit erróneo" >> README.md
git add README.md
git commit -m "Erro tipográfico"
git commit --amend -m "Corrixido erro tipográfico"
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

## 9. Traballo colaborativo con ramas
```bash
git branch correccion-bug
git checkout correccion-bug
echo "Corrección menor" >> README.md
git add README.md
git commit -m "Corrección menor no README"
git checkout main
git merge correccion-bug
git branch -d correccion-bug
```

---

## 10. Creación dun fork e *pull request*
```bash
# (1) Realizar o fork desde GitHub
git clone https://github.com/usuario/repositorio-fork.git
cd repositorio-fork
git branch mellora-docs
git checkout mellora-docs
echo "Mellora na documentación" >> README.md
git add README.md
git commit -m "Engadida mellora na documentación"
git push origin mellora-docs
# (2) Crear o Pull Request desde a web de GitHub
```