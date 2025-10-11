# Boletín de exercicios de Dockerfile (enunciados)

## 1. Comando básico de bash dentro dun contedor
Obxectivo: crear unha imaxe mínima que execute un comando de shell ao iniciar.
Instrucións:
1) Emprega a imaxe base `alpine:3.20`.
2) Fai que o contedor execute un comando que liste o contido do directorio raíz e, a continuación, amose os procesos en execución.
3) Constrúe a imaxe co nome `bash-mini:ls-ps` e execútaa.

## 2. Servidor web con Nginx
Obxectivo: servir un HTML estático.
Instrucións:
1) Usa a imaxe base `nginx:alpine`.
2) Crea un `index.html` con o texto “Benvido a Nginx en Docker” e cópiao a `/usr/share/nginx/html/` no contedor.
3) Expón o porto `80` no Dockerfile.
4) Constrúe a imaxe `web:nginx` e lánzaa mapeando o porto `8080:80` do host.

## 3. Aplicación Flask con requirements.txt
Obxectivo: levantar un pequeno servidor Flask.
Instrucións:
1) Crea `requirements.txt` cunha dependencia: `Flask==3.0.0`.
2) Crea `app.py` cun endpoint raíz que devolva “Ola desde Flask e Docker!”.
3) No Dockerfile: usa `python:3.12-slim`, copia e instala `requirements.txt`, copia o código, expón `5000` e define `CMD` para executar a app.
4) Constrúe a imaxe `flask:web` e execútaa mapeando `5000:5000`.

## 4. Versión avanzada con script de inicio, usuario non root e HEALTHCHECK
Obxectivo: integrar boas prácticas.
Instrucións:
1) Base: `python:3.12-slim`.
2) Crea `start.sh` que mostre unha mensaxe e execute o comando recibido.
3) Engade un usuario `appuser` e executa a app con el.
4) Instala dependencias desde `requirements.txt` (podes reutilizar o do exercicio 3).
5) Engade un `HEALTHCHECK` que faga unha petición HTTP ao porto da app cada 30s.
6) Constrúe a imaxe `flask:secure` e execútaa en segundo plano mapeando `8000:8000`.
