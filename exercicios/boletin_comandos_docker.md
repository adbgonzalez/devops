# 🧾 Boletín de exercicios prácticos de Docker (20 tarefas)

---

## 1️⃣ Verificación inicial
**Obxectivo:** Comprobar que Docker está correctamente instalado.  
**Instrucións:**
1. Mostra a versión do motor Docker e do cliente.
2. Lista información xeral do sistema Docker.
3. Executa o contedor de proba oficial para comprobar que todo funciona.

---

## 2️⃣ Buscar imaxes en Docker Hub
**Obxectivo:** Practicar o comando `docker search`.  
**Instrucións:**
- Busca imaxes oficiais de **nginx** e **mysql**.
- Busca tamén imaxes do usuario `adbgonzalez`.
- Filtra só as oficiais e as que teñan máis de 20 estrelas.

---

## 3️⃣ Descargar imaxes
**Obxectivo:** Usar `docker pull` para obter imaxes locais.  
**Instrucións:**
- Descarga as imaxes: `nginx`, `httpd`, `mysql:5.7`.
- Comproba que están dispoñibles co comando `docker images`.

---

## 4️⃣ Crear un contedor web básico
**Obxectivo:** Executar o teu primeiro contedor web.  
**Instrucións:**
- Usa a imaxe `nginx`.
- O contedor debe chamarse `web1`.
- Executa en modo interactivo e en segundo plano.
- Mapea o porto `8080` do host co `80` do contedor.

---

## 5️⃣ Parar e eliminar contedores
**Obxectivo:** Controlar a execución e limpeza de contedores.  
**Instrucións:**
- Detén o contedor `web1`.
- Elimínao do sistema.
- Comproba que xa non aparece na lista.

---

## 6️⃣ Executar un contedor Apache con nome e porto
**Obxectivo:** Crear un contedor de Apache accesible dende o host.  
**Instrucións:**
- Usa a imaxe `httpd`.
- Nomea o contedor `apache1`.
- Mapea o porto `8081` ao `80`.

---

## 7️⃣ Consultar logs e procesos
**Obxectivo:** Inspeccionar a actividade dun contedor.  
**Instrucións:**
- Mostra os logs do contedor `apache1`.
- Lista os procesos en execución dentro do contedor.

---

## 8️⃣ Acceder á consola dun contedor
**Obxectivo:** Entrar no sistema interno dun contedor.  
**Instrucións:**
- Accede á shell do contedor `apache1`.
- Lista o contido do directorio `/usr/local/apache2/htdocs`.
- Sae da shell.

---

## 9️⃣ Crear un contedor MySQL configurado
**Obxectivo:** Probar o uso de variables de entorno.  
**Instrucións:**
- Usa a imaxe `mysql:5.7`.
- Nomea o contedor `bd1`.
- Engade a variable `MYSQL_ROOT_PASSWORD=1234`.

---

## 🔟 Inspeccionar contedores e imaxes
**Obxectivo:** Consultar detalles técnicos.  
**Instrucións:**
- Inspecciona o contedor `apache1`.
- Inspecciona a imaxe `nginx`.

---

## 11️⃣ Crear unha imaxe personalizada a partir dun contedor
**Obxectivo:** Xerar unha nova imaxe.  
**Instrucións:**
- A partir do contedor `apache1`, crea unha nova imaxe chamada `apache-personal`.
- Lista as imaxes para comprobar que se creou.

---

## 12️⃣ Eliminar e restaurar unha imaxe
**Obxectivo:** Practicar copia e restauración de imaxes.  
**Instrucións:**
- Garda a imaxe `apache-personal` nun ficheiro `apache.tar`.
- Elimínaa.
- Recupéraa co comando `docker load`.

---

## 13️⃣ Crear un contedor con volume local
**Obxectivo:** Probar montaxes de directorios.  
**Instrucións:**
- Crea o directorio `/web` no host.
- Crea dentro un ficheiro `index.html` cun texto.
- Executa un contedor `apache-vol` baseado en `httpd` montando `/web` en `/usr/local/apache2/htdocs`.
- Mapea o porto `8082`.

---

## 14️⃣ Crear un volume nomeado e empregalo
**Obxectivo:** Empregar volumes xestionados por Docker.  
**Instrucións:**
- Crea un volume chamado `datosapp`.
- Usa ese volume nun contedor `web2` baseado en `nginx`.

---

## 15️⃣ Comprobar información dun volume
**Obxectivo:** Usar o comando `docker volume inspect`.  
**Instrucións:**
- Inspecciona o volume `datosapp`.
- Accede ao contedor `web2` e comproba a montaxe.

---

## 16️⃣ Limitar recursos dun contedor
**Obxectivo:** Controlar consumo de memoria.  
**Instrucións:**
- Crea un contedor `apache-limit` con `httpd`.
- Limita a 256MB de RAM e desactiva o swap.

---

## 17️⃣ Configurar reinicio automático
**Obxectivo:** Probar políticas de reinicio.  
**Instrucións:**
- Crea un contedor `nginx-auto` que se reinicie automaticamente salvo que o detés explicitamente.

---

## 18️⃣ Exposición automática de portos
**Obxectivo:** Empregar o parámetro `-P`.  
**Instrucións:**
- Lanza un contedor `apache-auto` con `httpd` e o parámetro `-P`.
- Mostra os portos publicados.

---

## 19️⃣ Etiquetar unha imaxe personalizada
**Obxectivo:** Aprender o uso de `docker tag`.  
**Instrucións:**
- Etiqueta a imaxe `apache-personal` co nome `usuario/apache-lab:v1`.
- Lista as imaxes dispoñibles.

---

## 20️⃣ Subir unha imaxe a Docker Hub
**Obxectivo:** Publicar a imaxe creada.  
**Instrucións:**
- Inicia sesión co teu usuario de Docker Hub.
- Sube a imaxe `usuario/apache-lab:v1`.
- Pecha sesión.
