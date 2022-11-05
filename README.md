<h1> Utilizando Docker Compose para executar uma aplicação HTML em um Container Apache (Arch linux)</h1>
🔸 <strong>1.</strong> Abra o terminal e atualize repositorios e sitema operacional (arch) :

```
sudo pacman -Syyuu 
```

🔸 <strong>2.</strong> Para instalar o Docker e Docker compose :</em>

```
sudo pacman -S docker docker-compose
```

🔸 <strong>3.</strong> Criar o arquivo compose.yml :

```
version: '3.9'
services:
apache:
image: httpd:latest
container_name: my-apache-app
ports:
-'80:80'
volumes:
- ./website:/usr/local/apache2/htdocs
```

🔸<strong>4.</strong> Criar diretorio para aplicação html :
```
mkdir website
cd website
```

🔸​<strong>4.1</strong> Criar arquivo index.html :

```
<html>
<h1> Meu Primeiro Projeto Docker !!!</h1>
</html>
```

​🔸<strong>5</strong> Iniciar docker em segundo plano

```
systemctl start docker
```
​🔸<strong>5.1</strong> Rodar script docker compose (-d é para rodar em segundo plano,caso queira ver os logs basta remove-lo)

```
docker-compose up -d
```
🔸​<strong>6</strong> Parar aplicação 

```
docker-compose down
```
