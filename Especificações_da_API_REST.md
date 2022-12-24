# Definição do objetivo e escopo da API

O objetivo da API do sistema CisternaGuardianPB é fornecer uma interface de programação de aplicativos (API) para 
permitir que terceiros acessem e manipulem os dados do sistema de maneira segura e controlada.
O escopo da API inclui a exposição de dados relacionados a obras, cisternas, beneficiários, fiscalizações e outras entidades relevantes do sistema, bem como a disponibilização de funcionalidades para a realização de operações de cadastro, consulta, 
atualização e exclusão desses dados. A API também deve prover autenticação e autorização de acesso para garantir que somente os usuários autorizados 
tenham acesso aos dados e funcionalidades permitidas. . A API também deve permitir o upload e download de arquivos, como fotos e relatórios técnicos, e fornecer mecanismos de autenticação e autorização para garantir a segurança dos dados.


# Escolha da linguagem e framework

Spring Boot é um framework para o desenvolvimento de aplicações Java com configuração automatizada e sem a necessidade de um arquivo de configuração complexo. Ele oferece uma série de recursos úteis para o desenvolvimento de APIs REST, como gerenciamento de dependências, configuração de rotas e endpoints, integração com banco de dados e validação de entrada de dados.

Algumas vantagens de utilizar Java com Spring Boot para desenvolver a API do CisternaGuardianPB são:

- Facilidade de aprendizado: Java é uma linguagem de programação de alto nível e de fácil aprendizado, especialmente para desenvolvedores que já possuem experiência em outras linguagens orientadas a objetos.

- Grande comunidade: Como Java é uma linguagem muito popular, existe uma grande comunidade de desenvolvedores que podem ajudar a resolver problemas e oferecer suporte.

- Vasta gama de bibliotecas: Java possui uma ampla gama de bibliotecas disponíveis, o que facilita a integração com outras ferramentas e sistemas.

- Configuração automatizada: Spring Boot simplifica a configuração da aplicação, permitindo que o desenvolvedor se concentre no desenvolvimento da lógica da aplicação em vez de se preocupar com a configuração complexa.

- Recursos úteis para o desenvolvimento de APIs: Spring Boot oferece vários recursos úteis para o desenvolvimento de APIs REST, como gerenciamento de dependências, configuração de rotas e endpoints, integração com banco de dados e validação de entrada de dados.


# Definição da arquitetura:

A arquitetura do CisternaGuardianPB pode ser dividida em três camadas principais:

Camada de Entidade: nesta camada, são definidas as classes de entidade que representam os objetos do sistema. Por exemplo, podemos ter uma classe Obra que representa uma obra de cisterna, uma classe Beneficiario que representa um beneficiário de cisterna, etc. As classes de entidade são anotadas com @Entity e são persistidas no banco de dados através de um repositório de acesso a dados, como o MongoDBRepository.

Camada de Serviço: nesta camada, são definidos os serviços que realizam as operações lógicas do sistema. Por exemplo, podemos ter um serviço ObraService que realiza operações de CRUD (criação, leitura, atualização e exclusão) de obras de cisterna, um serviço BeneficiarioService que realiza operações de CRUD de beneficiários, etc. Os serviços são anotados com @Service e são responsáveis por realizar as operações lógicas do sistema, como validações, regras de negócio, etc.

Camada de Controlador: nesta camada, são definidos os controladores que expõem a API REST do sistema. Por exemplo, podemos ter um controlador ObraController que expõe rotas para criar, ler, atualizar e excluir obras de cisterna, um controlador BeneficiarioController que expõe rotas para criar, ler, atualizar e excluir beneficiários, etc. Os controladores são anotados com @Controller e são responsáveis por receber as requisições HTTP, chamar os serviços adequados para realizar as operações lógicas e retornar a resposta ao cliente.


# Implementação das rotas e operações:

A implementação das rotas e operações do sistema CisternaGuardianPB será realizada através da camada de controllers. Cada controller será responsável por gerenciar as requisições HTTP para uma determinada entidade do sistema, como obras, cisternas, beneficiários, etc.

As rotas serão implementadas seguindo o padrão REST, com os métodos HTTP GET, POST, PUT e DELETE para realizar as operações de listagem, cadastro, atualização e exclusão, respectivamente. Além disso, serão incluídos métodos adicionais, como o GET para obter detalhes de uma entidade específica, por exemplo.

Cada controller conterá os métodos necessários para atender às requisições HTTP para a respectiva entidade, fazendo uso dos serviços da camada de service para realizar as operações de negócio e da camada de repository para acessar o banco de dados.

As respostas das operações serão devolvidas ao cliente no formato JSON, contendo os dados solicitados ou mensagens de erro em caso de falha. Serão tratados os possíveis erros e exceções para garantir a consistência e integridade dos dados.

Guia para implementação: 

Para implementar as rotas e operações do sistema CisternaGuardianPB, é necessário seguir os seguintes passos:

Defina as entidades que serão utilizadas na API. Cada entidade deve ter um conjunto de atributos que serão utilizados para armazenar os dados da API. Alguns exemplos de entidades que poderão ser utilizadas no sistema são:

- Obra: armazena os dados de uma obra de construção de cisterna, como o ID, o beneficiário, a associação, a cisterna, as datas de início e término previsto, o valor previsto, o status e os problemas encontrados.

- Fiscalização: armazena os dados de uma fiscalização de uma obra de cisterna, como o ID, o ID da obra, a data da fiscalização, os itens verificados e os documentos comprovativos.

- Beneficiário: armazena os dados de um beneficiário de uma cisterna, como o ID, o nome, o CPF, o contato, a associação, a escolaridade, o gênero, a renda e a quantidade de membros na família.


## Rotas Obras

GET /api/obras: lista todas as obras cadastradas no sistema.

POST /api/obras: cadastra uma nova obra no sistema.

GET /api/obras/{id}: obtém os detalhes de uma obra específica, pelo seu ID.

PUT /api/obras/{id}: atualiza os dados de uma obra específica, pelo seu ID.

DELETE /api/obras/{id}: exclui uma obra específica, pelo seu ID.

Defina as operações que serão realizadas em cada rota. Cada operação deve corresponder a uma função específica, como listar todas as obras, cadastrar uma nova obra, obter os detalhes de uma obra específica, atualizar os dados de uma obra ou excluir uma obra. Alguns exemplos de operações que poderão ser realizadas no sistema são:

listar obras: retorna uma lista com todas. Para listar todas as obras cadastradas no sistema, será criada a rota GET /obras. Essa rota retornará uma lista de objetos Obra, com todas as informações cadastradas para cada uma delas.

Para cadastrar uma nova obra, será utilizada a rota POST /obras, enviando no corpo da requisição um objeto Obra com todas as informações necessárias para o cadastro. Essa rota deverá retornar o objeto Obra cadastrado, com o ID gerado pelo banco de dados.

Para obter os detalhes de uma obra específica, será utilizada a rota GET /obras/{id}, onde o ID é o identificador da obra desejada. Essa rota deverá retornar um objeto Obra com as informações da obra desejada.

Para atualizar os dados de uma obra específica, será utilizada a rota PUT /obras/{id}, enviando no corpo da requisição um objeto Obra com as informações atualizadas. Essa rota deverá retornar o objeto Obra atualizado.

Para excluir uma obra específica, será utilizada a rota DELETE /obras/{id}, onde o ID é o identificador da obra desejada. Essa rota não deverá retornar nenhum dado.



# Testes e validação: 

# Publicação e documentação:
