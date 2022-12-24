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

- id: o ID da obra.
- progresso: a porcentagem de conclusão da obra, em formato inteiro (por exemplo, 50 para 50%).
- data_prevista_termino: a data prevista para o término da obra, no formato "YYYY-MM-DD".
- status: o status atual da obra, que pode ser "não iniciada", "em execução", "paralisada" ou "concluída".
- problemas_encontrados: uma lista de problemas encontrados durante a execução da obra, se houver.
- comentarios: um campo de texto livre para comentários adicionais sobre o progresso da obra.
- arquivos: uma lista de arquivos anexados ao registro do progresso da obra, como fotos, vídeos ou relatórios técnicos. Cada item da lista pode conter informações sobre o arquivo, como nome, tipo e URL de download.
