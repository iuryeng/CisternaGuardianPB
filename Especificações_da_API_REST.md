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

- Camada de apresentação: é responsável por receber as solicitações dos usuários e apresentar os resultados. Pode ser implementada como uma interface web ou aplicativo móvel.

- Camada de negócio: é onde são implementadas as regras de negócio e lógica do sistema. Pode ser desenvolvida com o framework Java Spring Boot, que oferece diversas ferramentas e bibliotecas para facilitar o desenvolvimento de aplicações web.

- Camada de dados: é responsável por armazenar e recuperar os dados do sistema. Pode ser implementada com um banco de dados NoSQL, como o MongoDB, que é especialmente adequado para aplicações que lidam com grandes quantidades de dados não estruturados.


# Implementação das rotas e operações:

# Testes e validação: 

# Publicação e documentação:
