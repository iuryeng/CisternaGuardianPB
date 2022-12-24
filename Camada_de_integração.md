# CisternaGuardianPB

A integração do sistema será fetia atraves de um API Rest escrita em Java utilizando o framework SpringBoot. A estrutura da API Rest do sistema CisternaGuardianPB inclue os seguintes módulos ou funcionalidades:

- Autenticação e autorização: esta funcionalidade é responsável por garantir que apenas usuários autorizados tenham acesso às funcionalidades da API. Ela pode ser implementada utilizando técnicas de autenticação, como o uso de tokens de acesso ou credenciais de usuário.

- Gerenciamento de usuários: esta funcionalidade é responsável por permitir que os usuários sejam criados, atualizados, excluídos e consultados na base de dados. Ela pode ser implementada através de rotas HTTP como POST, GET, PUT e DELETE.

- Gerenciamento de obras: esta funcionalidade é responsável por permitir que as obras de cisternas sejam criadas, atualizadas, excluídas e consultadas na base de dados. Ela também deve permitir acompanhar o progresso das obras e identificar problemas ou atrasos.

- Gerenciamento de beneficiários: esta funcionalidade é responsável por permitir que os beneficiários das cisternas sejam cadastrados, atualizados, excluídos e consultados na base de dados. Ela também deve permitir acompanhar as necessidades da comunidade beneficiada pelas cisternas e garantir que elas sejam atendidas de maneira adequada.

- Gerenciamento de documentos: esta funcionalidade é responsável por permitir que os documentos relevantes para o projeto sejam armazenados e gerenciados, incluindo contratos, relatórios técnicos e outros documentos.

- Notificações: esta funcionalidade é responsável por enviar notificações por e-mail ou outros meios para os usuários relevantes sobre alterações no progresso da obra, alertas de segurança e outras informações importantes.


# Rotas da API REST:

## Obra:
Para obter os detalhes de uma obra específica, é necessário enviar uma requisição HTTP GET para a rota /api/obras/{id}.

Exemplo de requisição:

Requisição
Método: GET

URL: https://meuservidor.com/obra/123

Resposta
Status: 200 OK

Corpo da resposta:

`GET /api/obra/{id}/`

Diagrama UML:

![Nome da Imagem](/Assets/Obra_uml_json.svg)

| Propriedade          | Tipo             | Descrição                                               |
| -------------------- | ---------------- | ------------------------------------------------------ |
|  id	                 |  int	            |  O ID da obra                                           |  
|  beneficiario_id	   |  int	            |  O ID do beneficiário associado à obra                  |  
|  associacao_id	     |  int	            |  O ID da associação associada à obra                    |  
|  cisterna_id	       |  int	            |  O ID da cisterna associada à obra                      |  
|  progresso_id        |  int             |  O ID do progresso da obra                              |  
|  data_inicio	       |  date	          |  A data de início da obra                               |  
|  data_prevista_termino	|  date	        |  A data prevista para o término da obra                 |  
|  valor_previsto	        |  float	      |  O valor previsto para a conclusão da obra              |   
|  tecnico_responsavel    |  string	      |  O técnico encarregado da empresa responsável pela obra |  
|  arquivos	              |  array	      |  Uma lista de arquivos anexados à obra                  |  
|  endereco	              |  string	      |  O endereço da obra                                     |  
|  municipio	            |  string	      |  O município da obra                                    |  
|  comunidade	            |  string	      |  A comunidade da obra                                   |  
|  contrato	              |  string	      |  O número do contrato da obra                           |  
|  empresa	              |  string	      |  A empresa responsável pela execução da obra            |  
|  lote	                  |  string	      |  O lote da obra                                         |  
|  encarregado_tecnico	  |  string	      |  O encarregado técnico da empresa                       | 
|  tecnicos_cooperar	    |   array	      |  Uma lista de técnicos do Cooperar envolvidos na obra   |  
|  documentos	            |  array	      |  Uma lista de documentos e arquivos importantes da obra |  

Abaixo segue um exemplo de uma resposta HTTP para a requisição GET na rota /api/obra/123

``` lang-js

HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8

{
  "id": 1,
  "beneficiario_id": 123,
  "associacao_id": 456,
  "cisterna_id": 789,
  "progresso_id": 123,
  "data_inicio": "2022-01-01",
  "data_prevista_termino": "2022-12-31",
  "valor_previsto": 10000,
  "endereco": {
    "municipio": "Município A",
    "comunidade": "Comunidade B"
  },
  "contrato": "12345/2022",
  "empresa": "Empresa X",
  "lote": "Lote 123",
  "gerencia": "Gerencia de Água e Saneamento",
  "documentacao": {
    "contrato": {
      "numero": "12345/2022",
      "data_assinatura": "2022-01-01",
      "prazo_execucao": "12 meses",
      "valor": 10000
    },
    "licitacao": {
      "numero": "54321/2021",
      "data_abertura": "2021-12-31",
      "empresa_vencedora": "Empresa X"
    }
  },
  "encarregado_tecnico_empresa": "João da Silva",
  "tecnicos_cooperar": [
    "Maria Rodrigues",
    "José Souza"
  ],
  "artefatos_documentais": [
    {
      "nome": "Plano de Trabalho",
      "tipo": "PDF",
      "url": "https://example.com/obras/1/artefatos/plano-de-trabalho.pdf"
    },
    {
      "nome": "Foto da Obra",
      "tipo": "JPG",
      "url": "https://example.com/obras/1/artefatos/foto-obra.jpg"
    }
  ]
}


 ```

## Progresso da Obra:  

Uma possível rota da API REST para monitoramento do progresso da obra poderia ser:

Requisição
Método: GET

URL: https://meuservidor.com/obra/123/progresso

Resposta
Status: 200 OK

Corpo da requisção:

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

Esses dados podem ser utilizados para monitorar o progresso da obra e garantir que ela esteja sendo realizada de acordo com o planejado, além de permitir a fiscalização da execução da obra pelas entidades responsáveis.

URL: https://meuservidor.com/obra/123/cisterna

``` lang-js

HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8
{
  "id": 1,
  "lote_id": 123,
  "beneficiario_id": 456,
  "capacidade": 10000,
  "diametro": 2.5,
  "altura": 3.5,
  "data_inicio": "2022-01-01",
  "data_conclusao": "2022-12-31",
  "status": "em execução",
  "problemas_encontrados": [],
  "comentarios": "",
  "checklist_fiscalizacao": [
    {
      "id": 1,
      "etapa": "Licenças e taxas",
      "descricao": "Verificação de todas as licenças e taxas necessárias para a construção da cisterna",
      "documento_comprovante": "https://example.com/comprovante.pdf",
      "check": true
    },
    {
      "id": 2,
      "etapa": "Instalação do canteiro de obra",
      "descricao": "Verificação da instalação do canteiro de obra, incluindo a presença de barracas, banheiros e área de alimentação",
      "documento_comprovante": "https://example.com/comprovante.pdf",
      "check": true
    },
    {
      "id": 3,
      "etapa": "Limpeza do terreno",
      "descricao": "Verificação da limpeza do terreno, remoção de obstáculos e preparação para a escavação",
      "documento_comprovante": "https://example.com/comprovante.pdf",
      "check": true
    },
    ...
  ]
}

```









