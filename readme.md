# Pizzaria Roma

Sistema de cardápio, carrinho de compras e acompanhamento de pedidos para uma pizzaria, desenvolvido em Python com Django.

## Visão geral

A aplicação permite:

- visualizar o cardápio por categoria;
- adicionar produtos ao carrinho;
- remover itens do carrinho;
- finalizar pedidos com dados do cliente;
- acompanhar o status do pedido;
- gerenciar produtos e categorias pelo Django Admin;
- armazenar imagens dos produtos.

## Tecnologias utilizadas

- Python 3.11+
- Django 5
- PostgreSQL / Supabase
- Pillow
- python-dotenv
- HTML, CSS e JavaScript

## Estrutura do projeto

```text
pizzaria_roma/
├── config/                 # configurações do projeto Django
│   ├── __init__.py
│   ├── settings.py
│   ├── urls.py
│   ├── wsgi.py
│   └── asgi.py
├── pedidos/                # app principal do sistema
│   ├── migrations/
│   ├── templates/
│   ├── admin.py
│   ├── apps.py
│   ├── models.py
│   ├── urls.py
│   ├── views.py
│   └── tests.py
├── static/                 # arquivos estáticos (CSS/JS)
├── media/                  # imagens enviadas para os produtos
├── templates/              # templates globais do projeto
├── manage.py
├── package.json            # dependências front-end (caso use o projeto em integrações)
├── readme.md
└── .env                    # arquivo de configuração local (não versionado)
```

## Funcionalidades

### Cardápio
O catálogo exibe produtos agrupados por categoria, com nome, descrição, preço e imagem.

### Carrinho
Os itens são armazenados na sessão do usuário e podem ser ajustados antes da finalização do pedido.

### Finalização do pedido
O cliente informa:

- nome;
- telefone;
- endereço de entrega;

Ao confirmar, o pedido é salvo no banco e os itens são registrados.

### Acompanhamento
O sistema permite consultar o status de um pedido pelo ID informado.

## Requisitos

Antes de iniciar, certifique-se de ter instalado:

- Python 3.11+
- pip
- PostgreSQL ou uma instância do Supabase
- Git

## Instalação

1. Clone o repositório:

```bash
git clone https://github.com/seu-usuario/pizzaria_roma.git
cd pizzaria_roma
```

2. Crie um ambiente virtual:

No Windows:

```powershell
py -m venv .venv
.\.venv\Scripts\Activate.ps1
```

3. Instale as dependências:

```bash
pip install -r requirements.txt
```

> Caso o ambiente do projeto esteja estruturado dentro da pasta `pizzaria_roma`, use também o arquivo `pizzaria_roma/requeriments.txt` conforme a organização do repositório.

4. Configure as variáveis de ambiente criando um arquivo `.env` na raiz do projeto com o seguinte conteúdo:

```env
SECRET_KEY=sua_chave_secreta
DEBUG=True
SUPABASE_DB_NAME=nome_do_banco
SUPABASE_DB_USER=usuario
SUPABASE_DB_PASSWORD=senha
SUPABASE_DB_HOST=host
SUPABASE_DB_PORT=5432
```

5. Execute as migrações:

```bash
python manage.py migrate
```

6. Crie um usuário administrativo:

```bash
python manage.py createsuperuser
```

7. Inicie o servidor:

```bash
python manage.py runserver
```

Acesse no navegador:

```text
http://127.0.0.1:8000
```

## Acesso administrativo

Para acessar o painel do Django:

```text
http://127.0.0.1:8000/admin/
```

Use o usuário criado com `createsuperuser`.

## Deploy

O projeto já inclui uma estrutura preparada para deploy em plataformas como Vercel e outras que suportam Django, além de estar configurado para uso com PostgreSQL/Supabase.

## Observações

- O arquivo `.env` deve ser mantido fora do controle de versão.
- Imagens dos produtos ficam na pasta `media/produtos`.
- Em produção, configure `DEBUG=False` e use uma `SECRET_KEY` forte.

## Licença

Este projeto está disponível para fins educacionais e de desenvolvimento local.

## Autor

Pizzaria Roma
