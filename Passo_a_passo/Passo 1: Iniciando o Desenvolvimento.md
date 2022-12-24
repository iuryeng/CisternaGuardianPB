# Passo 1: Iniciando o Desenvolvimento

Para construir o ambiente de desenvolvimento do sistema CisternaGuardianPB, siga os seguintes passos:

- [ ] Instale o Java, baixando e instalando a última versão disponível em https://www.java.com/pt_BR/download/.
- [ ] Instale o Spring Boot, seguindo as instruções em https://spring.io/projects/spring-boot.
- [ ] Instale o servidor MongoDB, baixando e instalando a última versão disponível em https://www.mongodb.com/download-center/community.
- [ ] Configure o MongoDB para iniciar automaticamente no boot do sistema e inicie o servidor.
- [ ] Crie um novo projeto Spring Boot usando a ferramenta de linha de comando "Spring Initializr" ou utilizando a interface web em https://start.spring.io/. Selecione o módulo "MongoDB" na aba "Dependencies".
- [ ] Configurar as informações de conexão do MongoDB no arquivo application.properties 
- [ ] Importe o projeto criado em sua IDE de preferência (Eclipse, IntelliJ, etc).


Dependencias iniciais usadas no projeto Spring Initializr:

- Spring Web: Essa dependência é utilizada para desenvolver aplicações web com o Spring. Ela inclui os componentes necessários para criar controllers, gerenciar requisições HTTP e configurar o mapeamento de rotas.

- Lombok: Essa biblioteca é utilizada para simplificar a escrita de código Java, fornecendo anotações que geram automaticamente código boilerplate como getters, setters e construtores. Ela é especialmente útil para projetos com muitas entidades e evita a repetição de código.

- Spring Data MongoDB: Essa dependência fornece integração com o banco de dados MongoDB, permitindo a criação de repositórios que facilitam o acesso aos dados. Ela também inclui o suporte para o uso de consultas personalizadas com a linguagem de consultas do MongoDB (query language).

- Springfox Swagger: Essa biblioteca é utilizada para gerar documentação da API em formato Swagger, o que facilita o entendimento e o teste das rotas da API pelos desenvolvedores. Ela também gera uma interface web para visualização da documentação.

- Springfox Swagger UI: Essa dependência é utilizada para fornecer a interface web de visualização da documentação gerada pelo Springfox Swagger. Ela é importante para que os desenvolvedores possam visualizar e testar as rotas da API de forma mais intuitiva.


