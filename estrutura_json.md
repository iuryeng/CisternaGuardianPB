# obra


```json
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
  ],
  "progresso_atual": {
    "percentual_execucao": 50,
    "data_ultima_medicao": "2023-03-20",
    "observacoes": "A obra está atrasada em relação ao cronograma previsto devido a problemas com o fornecimento de materiais."
  }
}

```


# progresso da obra

```json
{
  "id_obra": "12345",
  "gerencia_regional": "SOUSA",
  "data": "03/09/2021",
  "municipio": "NAZAREZINHO",
  "responsavel_tecnico": "KLEBER DE SOUSA BATSITA",
  "associacao": "ASSOCIAÇÃO COMUNITÁRIA UNIDOS SOMOS MAIS FORTES",
  "empreiteria": "CONSÓRCIO NOVA PARAÍBA",
  "beneficiario": "FRANCISCO BEZERRA DE ALBUQUERQUE",
  "itens": [
    {
      "numero": "1",
      "descricao": "Serviços Preliminares",
      "unidade": "m²",
      "quantidade": 150,
      "preco_unitario": 10.5,
      "valor_total": 1575,
      "subitens": [
        {
          "numero": "1.1",
          "descricao": "Locação de Obra",
          "unidade": "m²",
          "quantidade": 150,
          "preco_unitario": 2.5,
          "valor_total": 375
        },
        {
          "numero": "1.2",
          "descricao": "Placa de obra",
          "unidade": "un",
          "quantidade": 1,
          "preco_unitario": 120,
          "valor_total": 120
        },
        {
          "numero": "1.3",
          "descricao": "Cerca de Obra",
          "unidade": "m²",
          "quantidade": 150,
          "preco_unitario": 4,
          "valor_total": 600
        }
      ]
    },
    {
      "numero": "2",
      "descricao": "Serviços de Terraplanagem",
      "unidade": "m³",
      "quantidade": 300,
      "preco_unitario": 8.5,
      "valor_total": 2550,
      "subitens": [
        {
          "numero": "2.1",
          "descricao": "Corte de terreno",
          "unidade": "m³",
          "quantidade": 100,
          "preco_unitario": 5,
          "valor_total": 500
        },
        {
          "numero": "2.2",
          "descricao": "Aterro Compactado",
          "unidade": "m³",
          "quantidade": 200,
          "preco_unitario": 12,
          "valor_total": 2400
        }
      ]
    }
  ],
  "total": {
    "valor_total_itens": 4125,
    "descontos": 0,
    "acrescimos": 0,
    "valor_total": 4125
  },
  "total_bdi": {
    "valor_total_itens": 4125,
    "descontos": 0,
    "acrescimos": 0,
    "valor_total": 4125,
    "bdi": 10,
    "valor_total_bdi": 4537.5
  }
}



```
