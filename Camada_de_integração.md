# CisternaGuardianPB

A integração do sistema será fetia atraves de um API Rest escrita em Java utilizando o framework SpringBoot. A estrutura da API Rest do sistema CisternaGuardianPB inclue os seguintes módulos ou funcionalidades:

- Autenticação e autorização: esta funcionalidade é responsável por garantir que apenas usuários autorizados tenham acesso às funcionalidades da API. Ela pode ser implementada utilizando técnicas de autenticação, como o uso de tokens de acesso ou credenciais de usuário.

- Gerenciamento de usuários: esta funcionalidade é responsável por permitir que os usuários sejam criados, atualizados, excluídos e consultados na base de dados. Ela pode ser implementada através de rotas HTTP como POST, GET, PUT e DELETE.

- Gerenciamento de obras: esta funcionalidade é responsável por permitir que as obras de cisternas sejam criadas, atualizadas, excluídas e consultadas na base de dados. Ela também deve permitir acompanhar o progresso das obras e identificar problemas ou atrasos.

- Gerenciamento de beneficiários: esta funcionalidade é responsável por permitir que os beneficiários das cisternas sejam cadastrados, atualizados, excluídos e consultados na base de dados. Ela também deve permitir acompanhar as necessidades da comunidade beneficiada pelas cisternas e garantir que elas sejam atendidas de maneira adequada.

- Gerenciamento de documentos: esta funcionalidade é responsável por permitir que os documentos relevantes para o projeto sejam armazenados e gerenciados, incluindo contratos, relatórios técnicos e outros documentos.

- Notificações: esta funcionalidade é responsável por enviar notificações por e-mail ou outros meios para os usuários relevantes sobre alterações no progresso da obra, alertas de segurança e outras informações importantes.


# Rotas da API REST:

1. Progresso da Obra:  

Uma possível rota da API REST para monitoramento do progresso da obra poderia ser:

`GET /api/obras/{id}/progresso`

Essa rota poderia ser utilizada para consultar o progresso atual de uma obra específica, identificada pelo ID da obra. Ela retornaria um objeto JSON com informações sobre o progresso da obra, como porcentagem de conclusão, data prevista de término, problemas encontrados e outros dados relevantes.

Diagrama UML:

![Nome da Imagem](/Assets/progresso_uml_json.svg)

Por exemplo, a seguinte requisição HTTP:
O objeto JSON retornado pela rota de monitoramento do progresso da obra poderia incluir os seguintes campos:

| Propriedade          | Tipo             | Descrição                                              |
| -------------------- | ---------------- | ------------------------------------------------------ |
| id                   | número inteiro   | ID do projeto                                         |
| progresso            | número inteiro   | Progresso atual do projeto (em %)                     |
| data_prevista_termino | string           | Data prevista para o término do projeto (formato YYYY-MM-DD) |
| dias_restantes       | número inteiro   | Número de dias restantes para o término do projeto   |
| fase_atual           | string           | Fase atual do projeto                                 |
| fases_concluidas     | array de strings | Fases concluídas do projeto                           |
| fases_pendentes      | array de strings | Fases pendentes do projeto                            |
| problemas_encontrados | array de strings | Problemas encontrados no projeto                      |
| status_atual         | string           | Status atual do projeto                               |
| tipos_status_possiveis | array de strings | Tipos de status possíveis para o projeto              |
| visitas_feitas       | número inteiro   | Número de visitas realizadas no projeto              |
| data_visitas         | array de strings | Datas das visitas realizadas no projeto (formato YYYY-MM-DD) |
| arquivos             | array de objetos | Arquivos relacionados ao projeto                     |


Abaixo segue um exemplo de uma resposta HTTP para a requisição GET na rota /api/obras/123/progresso:


``` lang-js

HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8

{
  "id": 123,
  "progresso": 75,
  "data_prevista_termino": "2022-12-31",
  "dias_restantes": 60,
  "fase_atual": "escavação",
  "fases_concluidas": [
    "projeto",
    "licenciamento",
    "escavação"
  ],
  "fases_pendentes": [
    "fundação",
    "estrutura",
    "acabamento"
  ],
  "problemas_encontrados": [
    "Atraso na entrega de materiais",
    "Falta de mão de obra qualificada"
  ],
  "status_atual": "em andamento",
  "tipos_status_possiveis": [
    "iniciado",
    "paralisado",
    "em andamento",
    "concluido"
  ],
  "visitas_feitas": 3,
  "data_visitas": [
    "2022-01-15",
    "2022-03-01",
    "2022-05-20"
  ],
  "arquivos": [
    {
      "nome": "foto_obra_1.jpg",
      "tipo": "image/jpeg",
      "url": "https://meuservidor.com/arquivos/foto_obra_1.jpg"
    },
    {
      "nome": "video_obra_1.mp4",
      "tipo": "video/mp4",
      "url": "https://meuservidor.com/arquivos/video_obra_1.mp4"
    }
  ]

}


```

sucesso e os dados foram retornados no corpo da resposta, no formato JSON. A propriedade Content-Type informa o tipo de conteúdo retornado, que no caso é aplicação/JSON.

Além disso, no corpo da resposta são retornados os dados da obra solicitada, conforme descrito na tabela .md anteriormente. São informações como o ID da obra, o progresso, a data prevista para o término, o status atual, os problemas encontrados, os comentários adicionais, as visitas realizadas, as datas das visitas, o técnico responsável e os arquivos anexados ao registro do progresso da obra.

Esses dados podem ser utilizados para monitorar o progresso da obra e garantir que ela esteja sendo realizada de acordo com o planejado, além de permitir a fiscalização da execução da obra pelas entidades responsáveis.




