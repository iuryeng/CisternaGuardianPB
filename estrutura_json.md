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
      "item": "1.00",
      "descricao": "Serviços Preeliminares",
      "unidade": "",
      "quantidade": "",
      "preco_unitario": "",
      "preco_total": "541.61",
      "primeira_medicao": {
        "porcentagem_executada": "100.00%",
        "valor": "541.61"
      },
      "segunda_medicao": {
        "porcentagem_executada": "0.00%",
        "valor": "-"
      },
      "acumulado": {
        "porcentagem_executada": "100.00%",
        "valor": "541.61"
      }
    },
    {
      "item": "1.01",
      "descricao": "Licenças e taxas",
      "unidade": "unid.",
      "quantidade": "1.00",
      "preco_unitario": "312.00",
      "preco_total": "312.00",
      "primeira_medicao": {
        "porcentagem_executada": "100.00%",
        "valor": "312.00"
      },
      "segunda_medicao": {
        "porcentagem_executada": "0.00%",
        "valor": "0.00"
      },
      "acumulado": {
        "porcentagem_executada": "100.00%",
        "valor": "312.00"
      }
    },
    // outros itens omitidos por brevidade
  ],
  "total": {
    "valor_total": "7366.90",
    "porcentagem_executada": "85.42%",
    "valor_executado": "6292.82"
  },
  "total_bdi": {
    "valor_total": "8840.28",
    "porcentagem_executada": "85.42%",
    "valor_executado": "7551.39"
  }
}


```
