<h1 align="center">Encurtador de Links API</h1>
<p>
  Esta é uma API simples de encurtador de links escrita em Go. A API permite que você crie URLs curtas para redirecionar para URLs completas.
</p>


<strong>
Tecnologias Utilizadas  
</strong>

- Go
- Chi - Router leve para Go.
- Chi Middleware - Middleware para Chi.
- Slog - Logger estruturado.
- Rand - Gerador de números aleatórios.

Endpoints
1. Encurtar `URL`
- URL: `/api/shorten`
- Método: POST
- Descrição: Encurta uma URL fornecida e retorna um código único para acessá-la.
- Corpo da Requisição:
- `url`: A URL completa que será encurtada.

```json
{
  "url": "https://example.com"
}
```

- Resposta:
  - data: O código gerado que pode ser usado para acessar a URL encurtada.
```json
{
  "data": "a1b2c3d4"
}

```


- Códigos de Status:
  - `201 Created`: `URL` encurtada com sucesso.
  - `400 Bad Request`: URL inválida fornecida.
  - `422 Unprocessable Entity`: JSON inválido fornecido.
 
2. Redirecionar para URL Completa
- URL: `/{code}`
- Método: `GET`
- Descrição: Redireciona para a URL completa associada ao código encurtado.
- Parâmetros da URL
  - `code`: O código gerado para a URL encurtada.
- Respostas:
  - Redireciona para a URL completa.
  - `404` Not Found: Código encurtado não encontrado.

