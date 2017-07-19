Questionamentos:

Preciso deixar o método construtor como private?
Posso usar uma Simple Factory para instanciar um objeto de uma outra classe?
Como o teste unitário fica?
O método que o client da Simple Factory vai usar pode ser static?


## Estrutura
```php
class SimpleFactory
{
    private function __construct()
    {

    }

    public function create()
    {

    }
}
```

## Exemplo - Classe de Conexão com Banco de Dados
```
class DatabaseConnectionFactory
{
    private function __construct($host, $port, $user, $pass)
    {
        $this->host = $host;
        $this->port = $port;
        $this->user = $user;
        $this->pass = $pass;
    }

    public function create()
    {
        $host = $this->getHost();
        $port = $this->getPort();
        $user = $this->getUser();
        $pass = $this->getPassword();
    }

    private function getHost()
    {}

    private function getPort()
    {}

    private function getUser()
    {}

    private function getPassword()
    {}
}
```
