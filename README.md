<!-- Nome do projeto -->
# FastTools
# Loja virtual de ferramentas <!--Descrição do projeto -->


## Endpoints 
- Cadastro de ferramentas
- Visualizar ferramentas
- Listar ferramentas
- Editar ferramentas

---

### Cadastro de despesa 
<!-- Endereço do recurso -->
`POST` fasttools/api/v1/ferramentas


**Exemplo de Entrada** 
```js
{
    "ferramenta_nome": 'marreta',
    "ferramenta_id": 1,
    "usuario_id": 1,
    "valor_ferramenta": 100,
    "data": '2023-01-01',
    "quantidade": 100

}
```

**Campos da Requisição**


| Campo | Obrigatório | Tipo  | Descrição |
|-------|:-------------:|-------|-----------|
|ferramenta_nome|sim|texto|O nome da ferramenta
|ferramenta_id|sim|int| O id da ferramenta
|valor_ferramenta  |sim          |decimal|O valor da ferramenta
|data|sim|data| a data do cadastro da ferramenta
|descricao|não|texto|  descrição especificando a ferramenta com no máximo 200 digitos

**Códigos da Resposta**

|código|descrição
|-|-
201 | a ferramenta foi computada com sucesso
400 | os dados não são validos

---

### visualizar ferramenta

`GET` fasttools/api/v1/ferramenta/{id}

**Exemplo de Resposta** 
```js
{
    "ferramenta_id": 1,
    "nome": 'marreta',
    "valor": 100,
    "quantidade": 100,
}
```

**Códigos da Resposta**

|código|descrição
|-|-
200 | os dados da ferramenta foram fornecidos
404 | não existe nenhuma ferramenta com o ID informado