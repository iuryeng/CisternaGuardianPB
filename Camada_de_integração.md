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

Por exemplo, a seguinte requisição HTTP:
O objeto JSON retornado pela rota de monitoramento do progresso da obra poderia incluir os seguintes campos:

| Campo          | Tipo    | Descrição                                                                                                                   |
|----------------|---------|-----------------------------------------------------------------------------------------------------------------------------|
| `id`           | Integer | O ID da obra.                                                                                                              |
| `progresso`    | Integer | A porcentagem de conclusão da obra, em formato inteiro (por exemplo, 50 para 50%).                                        |
| `data_prevista_termino` | Date   | A data prevista para o término da obra, no formato "YYYY-MM-DD".                                                     |
| `status`       | Enum    | O status atual da obra, que pode ser "não iniciada", "em execução", "paralisada" ou "concluída".                           |
| `problemas_encontrados` | Array  | Uma lista de problemas encontrados durante a execução da obra, se houver.                                             |
| `comentarios`  | String  | Um campo de texto livre para comentários adicionais sobre o progresso da obra.                                            |
| `visitas_feitas` | Integer | O número de visitas realizadas à obra.                                                                                   |
| `data_visitas` | Array   | Uma lista com as datas das visitas realizadas à obra.                                                                      |
| `tecnico_responsavel` | String | O nome do técnico responsável pelas visitas à obra.                                                                     |
| `arquivos`     | Array   | Uma lista de arquivos anexados ao registro do progresso da obra, como fotos, vídeos ou relatórios técnicos. Cada item da lista pode conter informações sobre o arquivo, como nome, tipo e URL de download. |


Abaixo segue um exemplo de uma resposta HTTP para a requisição GET na rota /api/obras/123/progresso:


``` lang-js

HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8

{
  "id": 123,
  "progresso": 75,
  "data_prevista_termino": "2022-12-31",
  "status": "em execução",
  "problemas_encontrados": [
    "Atraso na entrega de materiais",
    "Falta de mão de obra qualificada"
  ],
  "comentarios": "Obra progredindo de acordo com o planejado, mas enfrentando alguns problemas logísticos e de recursos humanos.",
  "visitas_feitas": 3,
  "data_visitas": [
    "2022-01-15",
    "2022-03-01",
    "2022-05-20"
  ],
  "tecnico_responsavel": "João da Silva",
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




