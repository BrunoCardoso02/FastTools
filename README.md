<!-- Nome do projeto -->
# FastTools
# Loja virtual de ferramentas <!--Descrição do projeto -->


## Endpoints 
- Cadastro de ferramentas
- Visualizar ferramentas
- Listar ferramentas
- Adcionar saldo
- Visualizar saldo

---

### Cadastro de despesa 
<!-- Endereço do recurso -->
`POST` fasttools/api/v1/ferramentas


**Exemplo de Entrada** 
```js
{
    "ferramenta_nome": 'marreta',
    "ferramenta_id": 1,
    "ferramenta_valor": 100,
    "data": '2023-01-01',
    "quantidade": 100

}
```

**Campos da Requisição**


| Campo | Obrigatório | Tipo  | Descrição |
|-------|:-------------:|-------|-----------|
|ferramenta_nome|sim|texto|O nome da ferramenta
|ferramenta_id|sim|int| O id da ferramenta
|ferramenta_valor |sim          |decimal|O valor da ferramenta
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
    "ferramenta_nome": 'marreta',
    "ferramenta_valor": 100,
    "quantidade": 100,
}
```

**Códigos da Resposta**

|código|descrição
|-|-
200 | os dados da ferramenta foram fornecidos
404 | não existe nenhuma ferramenta com o ID informado

_ _ _

## Adcionar saldo na conta  
`POST` fasttools/api/v1/adcionar-saldo

**Exemplo de Resposta** 
```js
{
    "usuario_id": 1,
    "usuario_nome": 'Carlos',
    "valor_adcionar": 100,
}
```
**Campos da Requisição**


| Campo | Obrigatório | Tipo  | Descrição |
|-------|:-------------:|-------|-----------|
|usuario_id |sim|int|O id da conta do usuário
|usuario_nome|sim|texto| O username do usuario 
|valor_adcionar|sim|decimal|O valor que será adcionado

**Códigos da Resposta**
|código|descrição
|-|-
200 | Valor de saldo adcionado 
404 | Valor inválido
_ _ _

## Visualizar saldo na conta  


`GET` fasttools/api/v1/saldo
**Exemplo de Resposta** 
```js
{
    "usuario_id": 1,
    "usuario_nome": 'Carlos',
    "saldo_disponivel": 100,
}
```
**Códigos da Resposta**

|código|descrição
|-|-
200 | Saldo disponivel informado
404 | Sem informações disponiveis
