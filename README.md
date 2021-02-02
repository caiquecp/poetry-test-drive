# Poetry test drive

## TODO

- instalação de dependências OK
- atualização de dependências OK
- lock OK
- configuração do projeto OK
- interação com ambientes virtuais e versões do python OK
- interação com ci/cd OK
- resolução das dependências
- gestão de virtualenv OK
- utilização em produção OK
- plus: build (substitui setup.py/setuptools) e publicação OK
- facilita uso de repositório privado (configura uma vez)

## Setup

Quando se cria um projeto com Poetry através dos comandos new ou init, um dos artefatos mais importante é o arquivo pyproject.toml. Contém informações do projeto, versão do Python requerida, dependências e muito mais (além de servir para outras bibliotecas e recursos também).

### Ambiente virtual

O Poetry se responsabiliza pela criação do ambiente virtual. É possível configurar o Poetry para utilizar um diretório padrão para todos os venvs, ou até usar o diretório do próprio projeto - o que eu prefiro, por ser mais fácil de manter e configurar nas IDE - para armazenar as dependências (venv).

### CI e ambientes além do dev

Há duas alternativas: instalação e uso do Poetry, ou exportação das dependências para um arquivo requirements.txt. A segunda alternativa é muito mais fácil e funciona perfeitamente.

### Bibliotecas

O Poetry fornece comandos para construir (build) bibliotecas, substituindo o setuptools (setup.py), e publicar o pacote em repositórios públicos e privados. 

## Comandos

Criar novo diretório/projeto com os arquivos de configuração do ambiente.

```
poetry new <project-name>
```

Iniciar o Poetry em um projeto já existente. 

```
poetry init
```

Adicionar dependências.

```
# add uma dependências
poetry add <dep1> <dep2> <dep3>==<version>

# add N dependências
poetry add <dep1> <dep2> <dep3>

# add dependências especificando versão
poetry add <dep1>==<version>
```

Atualizar dependências considerando constraints de versão.

```
# atualiza todas as dependências
poetry update

# atualiza N dependências
poetry update <dep1>
```

Atualizar dependências para versões além das constraints de versão.

```
poetry add <dep1>==<version>
```

Criar/atualizar arquivo de lock pra versão das dependências.

```
poetry lock
```

Exportar dependências para arquivo requirements.txt.

```
poetry export -o requirements.txt
```

Ativar venv.

```
poetry shell
```

[Poetry documentation](https://python-poetry.org/docs).
