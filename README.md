
# Projeto Backend Capyba

Este é um projeto básico criado com o framework Django, contendo três aplicações principais: **Polls**, **Accounts**, e **Contacts**. Ele foi desenvolvido com o intuito de aprender e explorar as funcionalidades do Django.

## Aplicações

### 1. **Polls**
- Uma aplicação de enquetes e votações, acessível através de `/polls`.
- Os usuários podem ver uma lista de enquetes e votar em suas opções favoritas.

### 2. **Accounts**
- Aplicação responsável por login e logout.
- Acesso via `/accounts/login`.
- Após o login bem-sucedido, o usuário pode acessar outras áreas do sistema.

### 3. **Contacts**
- Um ambiente para criação de mensagens, onde os usuários podem enviar mensagens de contato.
- A aplicação só pode ser acessada por usuários autenticados.
- Exibe uma mensagem de agradecimento após o envio.

## Recursos Utilizados

- **Django Forms**: Utilizados para criar e gerenciar formulários de entrada de dados nas aplicações.
- **pytest**: Utilizado para testes automatizados e validação do comportamento das aplicações.

## Requisitos do Sistema

- Python 3.10+
- Django 5.1.1
- [Poetry](https://python-poetry.org/) para gerenciamento de dependências

## Instalação e Configuração

1. Clone o repositório:
   ```bash
   git clone https://github.com/Nycolas-Gabriel/backend-em-django
   cd backend-em-django
   ```

2. Instale as dependências usando o Poetry:
   ```bash
   poetry install
   ```

3. Rode as migrações do banco de dados:
   ```bash
   poetry run python manage.py migrate
   ```

4. Colete os arquivos estáticos:
   ```bash
   poetry run python manage.py collectstatic
   ```

## Executando o Projeto Localmente

Você pode rodar o projeto localmente com o servidor de desenvolvimento do Django:

```bash
poetry run python manage.py runserver
```

Ou, em produção, com o `waitress`:

```bash
poetry run waitress-serve --port=8000 mysite.wsgi:application
```

## Deploy no Render.com

Para o deploy em plataformas como o Render, siga estas etapas:

1. Configure o arquivo `pyproject.toml` com todas as dependências necessárias.
2. Adicione a seguinte linha no script de execução do servidor em produção:

   ```bash
   poetry run waitress-serve --port=$PORT mysite.wsgi:application
   ```

3. Garanta que suas variáveis de ambiente (como `DATABASE_URL` e `SECRET_KEY`) estejam configuradas corretamente no painel do Render.

## Tecnologias Utilizadas

- Django 5.1.1
- Python 3.10+
- Whitenoise para servir arquivos estáticos
- Waitress como servidor WSGI para produção

## Licença

Este projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.
