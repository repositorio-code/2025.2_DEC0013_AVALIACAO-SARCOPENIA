# 📘 Guia Completo: Rodando o Sarcopenia App
Este tutorial explica passo a passo como preparar o ambiente, baixar e rodar a aplicação **Sarcopenia App**.

---

## 1. Instalar o Docker
Antes de tudo, é necessário ter o motor do Docker rodando no seu computador.

1. Acesse o site oficial: [https://www.docker.com/products/docker-desktop/](https://www.docker.com/products/docker-desktop/)
2. Clique no botão **Download** correspondente ao seu sistema (Windows, Mac ou Linux).
3. Instale o programa (seguindo o padrão "Next, Next, Finish").
4. **Importante:** Após instalar, abra o aplicativo **Docker Desktop** e aguarde ele iniciar completamente.

---

## 2. Instalar a Imagem
**Verfique que o seu Docker está aberto!**
Agora, vamos instalar e rodar a imagem.
1. Abra o seu terminal (Prompt de Comando, PowerShell ou Terminal do Mac/Linux).
2. Digite o comando abaixo para baixar a versão mais recente:

```bash
docker pull mfkaner/sarcopenia-pi-25-2
```
3. Para rodar a imagem:
```
docker run -d -p 8080:8000 --name sarcopenia-app mfkaner/sarcopenia-pi-25-2
```
Explicações:
- -d : Essa flag libera o seu terminal para utilizá-lo mesmo quando a imagem está rodando. 
- -p : Essa flag mapeia a porta do seu computador para a porta nativa da imagem do docker. Essa configuração é personalizável: [Porta do seu PC]:[Porta do Docker (no caso, sempre será 8000]
- --name : O nome também é personalizável, mas recomendamos fortemente que você mantenha o nome sarcopenia-app, pois continuaremos o tutorial com ele. 

4. Verifique que a imagem está rodando pelo comando:
```
docker ps
```
A única imagem que deveria estar aparecendo é a sarcopenia-app.

5. Para acessar o sistema, inicie seu navegador de prefência e digite: localhost:8080 (ou qualquer outra porta que você colocou)

## 3. Pós-instalação
- Para finalizar a aplicação:
```
docker stop sarcopenia-app
```
- Reiniciar:
```
docker start sarcopenia-app
```
- Remover completamente:
```
docker rm -f sarcopenia-app
```
