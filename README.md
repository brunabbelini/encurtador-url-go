# Encurtador de URL em Go 

Este é um encurtador de URL desenvolvido em Go (Golang) utilizando apenas a biblioteca padrão da linguagem.

O projeto foi criado pensando em situações onde uma URL é muito extensa e pode não caber em determinados campos ou sistemas.
A aplicação resolve esse problema de forma simples, direta e eficiente, sem depender de frameworks externos.

Projeto focado em aprofundar conhecimentos sobre HTTP, validação de parâmetros e geração de identificadores curtos em Go.

## Tecnologias Utilizadas
- [Go](https://golang.org/dl/): The Go programming language.
- Biblioteca padrão do Go (standard library)

##  Funcionalidades
- Endpoint para encurtamento de URLs:
 ```
GET /shorten?url=https://www.google.com
 ```
```
curl localhost:8080/shorten?url=https://www.google.com
 ```
- Validação obrigatória do protocolo:
  
    ❌ www.google.com → Retorna erro
  
    ✅ http:// ou https:// → Aceito

- Geração de identificador curto para cada URL
- A URL encurtada pode ser acessada diretamente no navegador
- Validação via curl para verificar se a URL encurtada existe -> Retorno de erro caso o identificador não seja encontrado

## 📁 Estrutura Principal
 ```
encurtador-url-go/
├── main.go        # Arquivo principal
├── go.mod         # Módulo Go
└── README.md
 ```

## Demonstrações da Aplicação
[Assistir vídeo](LINK_DA_RELEASE)

## Exemplos de Uso
❌ URL inválida (sem protocolo)
 ```
curl "http://localhost:8080/shorten?url=www.google.com"
Retorno: Erro: a URL deve começar com http:// ou https://
 ```

✅ URL válida
 ```
curl "http://localhost:8080/shorten?url=https://www.google.com"
Retorno: http://localhost:8080/abc123
 ```

🔁 Acessando URL encurtada
 ```
curl "http://localhost:8080/abc123"
Retorno: <a href="https://www.google.com">Found</a>. ou erro caso não seja encontrada
 ```

## 🔧 Como rodar o projeto localmente
1. Clone o repositório:
```
git clone https://github.com/brunabbelini/encurtador-url-go.git
cd encurtador-url-go
```
2. Execute o servidor:
 ```
go run main.go
 ```

3. O servidor estará disponível em:
 ```
http://localhost:8080
 ```
4. Teste utilizando o navegador ou curl


## 📝 Licença

Este projeto está sob a licença MIT.
