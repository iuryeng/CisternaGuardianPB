# Passo 1: Iniciando o Desenvolvimento

Para construir o ambiente de desenvolvimento do sistema CisternaGuardianPB, siga os seguintes passos:

- Instale o Java, baixando e instalando a última versão disponível em https://www.java.com/pt_BR/download/.
- Instale o Spring Boot, seguindo as instruções em https://spring.io/projects/spring-boot.
- Instale o servidor MongoDB, baixando e instalando a última versão disponível em https://www.mongodb.com/download-center/community.
- Configure o MongoDB para iniciar automaticamente no boot do sistema e inicie o servidor.
- Crie um novo projeto Spring Boot usando a ferramenta de linha de comando "Spring Initializr" ou utilizando a interface web em https://start.spring.io/. Selecione o módulo "MongoDB" na aba "Dependencies".
- Importe o projeto criado em sua IDE de preferência (Eclipse, IntelliJ, etc).
- Crie a entidade Obra, utilizando as anotações @Document e @Id para mapear a entidade para uma coleção no banco de dados. Defina os demais atributos da entidade, utilizando as anotações @Field para mapeá-los para os campos do documento no banco de dados.
- Crie o repositório da entidade Obra, extendendo a interface MongoRepository e especificando a entidade e o tipo do ID.
- Crie o service da entidade Obra, injetando o repositório e implementando as operações de CRUD (create, read, update, delete).
- Crie o controller da entidade Obra, injetando o service e expondo as rotas para as operações de CRUD. Utilize as anotações @RestController, @RequestMapping e os verbos HTTP (GET, POST, PUT, DELETE) para mapear as rotas e operações.
- Teste as rotas criadas, utilizando a ferramenta de testes de API de sua preferência (Postman, cURL, etc).
- Implemente os demais controllers, services e repositórios de acordo com a necessidade do sistema.
