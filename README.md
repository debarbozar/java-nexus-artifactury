# Java + Maven + Sonatype Nexus + GitHub Actions

Este projeto demonstra como configurar um ambiente de integração contínua (CI/CD) utilizando Java, Maven, Sonatype Nexus e GitHub Actions.

## O que é NEXUS?

É um gerenciador de repositórios que permite armazenar, gerenciar e distribuir artefatos de software. Ele é útil para:

- Manter bibliotecas privadas centralizadas.
- Servir como proxy para repositórios públicos (ex: Maven Central, Docker Hub).
- Gerenciar versões e dependências de forma organizada.
- Melhorar a segurança e rastreabilidade dos pacotes utilizados.

## Estrutura do Projeto

```
/java-ci
│── .github/workflows/ci.yml
│── src/main/java/App.java
│── pom.xml
```

## Instalação e Configurações Windows

### Maven
- Baixe o Apache Maven.
- Extraia o arquivo e configure as variáveis de ambiente
- Adicione C:\apache-maven\bin ao PATH.
- Configure MAVEN_HOME apontando para C:\apache-maven.

Verificar se o maven está instalado 
```
mvn -version
```

### Nexus
- Baixe o Nexus: https://www.sonatype.com/products/nexus-repository.
- Extraia o arquivo e inicie o servidor:
```
./bin/nexus.exe run
```
- Caso queria instalar o serviço
```
./bin/nexus.exe /install Nexus-Repository-Service
```
- Acesse no navegador: http://localhost:8081.
- O login padrão é admin, e a senha está em sonatype-work/nexus3/admin.password.

## Configurar projeto Maven
```
mvn archetype:generate -DgroupId=com.example -DartifactId=java-nexus-ci -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false
```

- Cria um novo projeto Maven chamado java-nexus-ci.
- Define o groupId como com.example (identificação do projeto na organização).
- Utiliza o archetype maven-archetype-quickstart, que gera um projeto básico com estrutura de diretórios e código inicial.
- O parâmetro -DinteractiveMode=false evita perguntas interativas durante a criação do projeto.
