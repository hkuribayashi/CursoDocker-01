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
   docker images ls
   ```
   Você deve ver a imagem do Nginx na lista. Confirme se a imagem é aquela que foi feita o pull.

3. **Criando o Primeiro Contêiner**

   Agora, vamos criar o primeiro contêiner a partir da imagem do nginx. Este contêiner será executado em segundo plano (modo detached).

   ```bash
   docker run -d --name meu_nginx1 nginx
   ```

   - `-d`: Executa o contêiner em modo detached.
   - `--name meu_nginx1`: Nomeia o contêiner como `meu_nginx1`.

4. **Criando o Segundo Contêiner**

   Agora, crie um segundo contêiner a partir da mesma imagem do nginx. Este contêiner também será executado em segundo plano (modo detached).

   ```bash
   docker run -d --name meu_nginx2 nginx
   ```

   - `--name meu_nginx2`: Nomeia o contêiner como `meu_nginx2`.

5. **Verificando os Contêineres em Execução**

   Liste os contêineres em execução para verificar se ambos foram iniciados corretamente.

   ```bash
   docker ps
   ```

   Você deve ver dois contêineres em execução, `meu_nginx1` e `meu_nginx2`.

6. **Acessando os Serviços Nginx**

   Por padrão todos os contêineres são isolados. E assim não estamos conseguindo acesso ao conteúdo/serviços oferecidos por cada container. Neste caso, consulte uma alternativa na [documentação oficial](https://docs.docker.com/guides/get-started/) do docker para resolver este problema.

#### Conclusão

Parabéns! Você puxou uma imagem do Docker Hub e criou dois contêineres diferentes a partir dessa imagem. Este exercício básico é essencial para entender como o Docker gerencia imagens e contêineres. No próximo exercício, exploraremos como personalizar contêineres e trabalhar com Dockerfiles.
