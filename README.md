# CursoDocker-01

## Exercício Inicial: Gerenciamento de Contêineres com Docker

### Objetivo
Neste exercício, você aprenderá a puxar uma imagem do Docker Hub e criar dois contêineres distintos a partir dessa imagem. Este é um passo fundamental para entender como o Docker funciona e como você pode gerenciar contêineres de maneira eficiente.

#### Pré-requisitos
- Docker instalado em sua máquina. [Instruções de instalação](https://docs.docker.com/get-docker/).

### Passos do Exercício

1. **Puxando uma Imagem do Docker Hub**

   A primeira tarefa é escolher uma imagem disponível no Docker Hub e puxá-la para sua máquina local. Vamos usar a imagem do nginx como exemplo. Use a tag latest.

   ```bash
   docker pull nginx:latest
   ```

   Após executar este comando, o Docker fará o download da imagem do Nginx do Docker Hub para sua máquina local.

2. **Verificando as Imagens Baixadas**

   Verifique se a imagem foi baixada com sucesso, listando as imagens disponíveis na sua máquina.

   ```bash
   docker images
   ```

   Você deve ver a imagem do Nginx na lista.

3. **Criando o Primeiro Contêiner**

   Agora, vamos criar o primeiro contêiner a partir da imagem do Nginx. Este contêiner será executado em segundo plano (modo detached) e estará mapeado para a porta 8080 do seu host.

   ```bash
   docker run -d -p 8080:80 --name meu_nginx1 nginx
   ```

   - `-d`: Executa o contêiner em modo detached.
   - `-p 8080:80`: Mapeia a porta 8080 do host para a porta 80 do contêiner.
   - `--name meu_nginx1`: Nomeia o contêiner como `meu_nginx1`.

4. **Criando o Segundo Contêiner**

   Agora, crie um segundo contêiner a partir da mesma imagem do Nginx. Este contêiner será executado em modo interativo (foreground) e estará mapeado para a porta 8081 do seu host.

   ```bash
   docker run -p 8081:80 --name meu_nginx2 nginx
   ```

   - `-p 8081:80`: Mapeia a porta 8081 do host para a porta 80 do contêiner.
   - `--name meu_nginx2`: Nomeia o contêiner como `meu_nginx2`.

5. **Verificando os Contêineres em Execução**

   Liste os contêineres em execução para verificar se ambos foram iniciados corretamente.

   ```bash
   docker ps
   ```

   Você deve ver dois contêineres em execução, `meu_nginx1` e `meu_nginx2`.

6. **Acessando os Serviços Nginx**

   Para verificar se os contêineres estão funcionando corretamente, abra um navegador da web e acesse as seguintes URLs:

   - Para o primeiro contêiner: `http://localhost:8080`
   - Para o segundo contêiner: `http://localhost:8081`

   Você deve ver a página padrão do Nginx em ambos os endereços.

#### Conclusão

Parabéns! Você puxou uma imagem do Docker Hub e criou dois contêineres diferentes a partir dessa imagem. Este exercício básico é essencial para entender como o Docker gerencia imagens e contêineres. No próximo exercício, exploraremos como personalizar contêineres e trabalhar com Dockerfiles.
