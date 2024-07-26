# Documentação da API Health&Med

Esta documentação fornece uma visão geral dos endpoints da API Health&Med e seu uso.

## URL Base

```
https://pikwe9lct4.execute-api.us-east-1.amazonaws.com/prod
```

## Autenticação

Para acessar os endpoints da API, você precisa incluir um token de portador no cabeçalho `Authorization` das suas requisições. O token pode ser obtido fazendo uma requisição GET para o endpoint de autenticação apropriado:

- Para médicos: `/token/medico`
- Para pacientes: `/token/paciente`

## Endpoints

### Usuários
#### Obter todos os usuários

- Método: GET
- Endpoint: /users
- Autenticação: Token de portador do paciente ou médico

#### Obter um usuário por ID

- Método: GET
- Endpoint: /users/{id}
- Autenticação: Token de portador do paciente ou médico

#### Excluir um usuário

- Método: DELETE
- Endpoint: /users/{id}
- Autenticação: Token de portador do paciente ou médico

#### Atualizar um usuário

- Método: PUT
- Endpoint: /users
- Autenticação: Token de portador do paciente ou médico
Corpo da requisição:
```
{
  "fullname": "Nome Completo",
  "tipo": "medico/paciente",
  "crm": "crm0123",
  "cpf": "000.000.000-00",
  "especialidade": "Clinico Geral"
}
```

## Autenticação

### Autenticação do Médico

- Método: `GET`
- Endpoint: `/token/medico`
- Corpo da requisição:
  ```json
  {
    "crm": "12345sp",
    "password": "12345Abc@@@"
  }
  ```

### Autenticação do Paciente

- Método: `GET`
- Endpoint: `/token/paciente`
- Corpo da requisição:
  ```json
  {
    "cpf": "22496741839",
    "email": "22496741839@teste.com",
    "password": "Teste@22496741839"
  }
  ```

Espero que esta documentação seja útil para entender e utilizar a API Health&Med. Se você tiver alguma dúvida adicional, não hesite em perguntar.
