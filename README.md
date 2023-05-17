# SGP-API
O sistema de gerenciamento de projetos é uma api que desenvolvi para o meu Trabalho de conclusão de curso de sistemas para internet. Inicialmente deveria ser um sistema de gestão de projetos, mas passou a ser um sistema para gerenciamento de feiras de ciências e avaliação de projetos.

## Rodar o projeto
Para rodar o projeto em sua máquina, você precisa ter instalado o [Docker](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-compose-on-ubuntu-20-04) e o [docker-compose](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-compose-on-ubuntu-20-04)

Caso você use windows, consulte a [documentação do laravel](https://laravel.com/docs/10.x/installation#getting-started-on-windows).

[//]: # (se usar windows, atualize a documentação!)

Após isso, você executa o script `install-sail.sh` na pasta `script`. Ele vai, inicialmente criar um pequeno container docker para poder fazer a instalação das dependências do composer, o que vai incluir o laravel sail, nosso gerenciador de containers.
```bash
bash ./script/install-sail.sh
```

Depois da execução do arquivo, você deve configurar o alias do sail, caso use [zsh](https://linuxhint.com/configure-use-aliases-zsh/) e caso use [bash (padrão do linux)](https://linuxize.com/post/how-to-create-bash-aliases/)
```bash
alias sail='[ -f sail ] && bash sail || bash vendor/bin/sail'
```


Depois disso, para subir os containers, é só usar o comando (dentro da pasta do projeto)
```bash
sail up
```

Para interromper a execução, basta dar `Ctrl + C` ou usar o comando
```bash
sail down
```

## Criando o banco de dados

Para criar o banco de dados, basta rodar:
```bash
sail artisan migrate
```

Caso ache que seja necessário refazer o banco, é só rodar:
```bash
sail artisan migrate:fresh
```

Caso queira rodar os testes unitários:
```bash
sail test
```
