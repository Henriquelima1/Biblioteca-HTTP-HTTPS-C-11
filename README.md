
# Biblioteca HTTP/HTTPS C++11 (Baseada na cpp-httplib)

Esta é uma biblioteca HTTP/HTTPS multiplataforma, baseada na versão 14.3 da [cpp-httplib](https://github.com/yhirose/cpp-httplib), modificada para funcionar com o compilador GCC 4.8 e C++11 em ambientes Ubuntu 14.

## Notas Importantes

- **E/S de Soquete com Bloqueio**: Esta biblioteca utiliza E/S de soquete com "bloqueio". Isso significa que ela aguarda enquanto espera por dados, bloqueando o fluxo de execução. Se você estiver procurando uma biblioteca que use E/S de soquete "sem bloqueio" (non-blocking I/O), esta não é a biblioteca ideal para você.
- **Compatibilidade de Ambiente**: A biblioteca foi otimizada para funcionar com o compilador GCC 4.8 e C++11, especificamente em ambientes Ubuntu 14.

## Como Usar

### 1. Baixar a Biblioteca

Baixe o arquivo de cabeçalho `httplib.h` e adicione-o ao seu projeto.

### 2. Incluir no Seu Código

Para usar a biblioteca, basta incluir o arquivo `httplib.h` no seu código C++:

```cpp
#include "httplib.h"
```

### 3. Exemplo de Uso

Aqui está um exemplo simples de como criar um servidor HTTP com a biblioteca:

```cpp
#include "httplib.h"

int main() {
    httplib::Server svr;

    svr.Get("/", [](const httplib::Request& req, httplib::Response& res) {
        res.set_content("Hello, world!", "text/plain");
    });

    svr.listen("localhost", 8080);
}
```

### 4. Consultar o Repositório Original

Para mais detalhes e opções avançadas, consulte o repositório original da biblioteca cpp-httplib na versão 0.14.3: [cpp-httplib v0.14.3 README](https://github.com/yhirose/cpp-httplib/blob/v0.14.3/README.md).


