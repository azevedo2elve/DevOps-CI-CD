<p align="center">
  <a href="http://nestjs.com/" target="blank"><img src="https://nestjs.com/img/logo-small.svg" width="200" alt="Nest Logo" /></a>
</p>

[circleci-image]: https://img.shields.io/circleci/build/github/nestjs/nest/master?token=abc123def456
[circleci-url]: https://circleci.com/gh/nestjs/nest

  <p align="center">A progressive <a href="http://nodejs.org" target="_blank">Node.js</a> framework for building efficient and scalable server-side applications.</p>
    <p align="center">
<a href="https://www.npmjs.com/~nestjscore" target="_blank"><img src="https://img.shields.io/npm/v/@nestjs/core.svg" alt="NPM Version" /></a>
<a href="https://www.npmjs.com/~nestjscore" target="_blank"><img src="https://img.shields.io/npm/l/@nestjs/core.svg" alt="Package License" /></a>
<a href="https://www.npmjs.com/~nestjscore" target="_blank"><img src="https://img.shields.io/npm/dm/@nestjs/common.svg" alt="NPM Downloads" /></a>
<a href="https://circleci.com/gh/nestjs/nest" target="_blank"><img src="https://img.shields.io/circleci/build/github/nestjs/nest/master" alt="CircleCI" /></a>
<a href="https://coveralls.io/github/nestjs/nest?branch=master" target="_blank"><img src="https://coveralls.io/repos/github/nestjs/nest/badge.svg?branch=master#9" alt="Coverage" /></a>
<a href="https://discord.gg/G7Qnnhy" target="_blank"><img src="https://img.shields.io/badge/discord-online-brightgreen.svg" alt="Discord"/></a>
<a href="https://opencollective.com/nest#backer" target="_blank"><img src="https://opencollective.com/nest/backers/badge.svg" alt="Backers on Open Collective" /></a>
<a href="https://opencollective.com/nest#sponsor" target="_blank"><img src="https://opencollective.com/nest/sponsors/badge.svg" alt="Sponsors on Open Collective" /></a>
  <a href="https://paypal.me/kamilmysliwiec" target="_blank"><img src="https://img.shields.io/badge/Donate-PayPal-ff3f59.svg"/></a>
    <a href="https://opencollective.com/nest#sponsor"  target="_blank"><img src="https://img.shields.io/badge/Support%20us-Open%20Collective-41B883.svg" alt="Support us"></a>
  <a href="https://twitter.com/nestframework" target="_blank"><img src="https://img.shields.io/twitter/follow/nestframework.svg?style=social&label=Follow"></a>
</p>
  <!--[![Backers on Open Collective](https://opencollective.com/nest/backers/badge.svg)](https://opencollective.com/nest#backer)
  [![Sponsors on Open Collective](https://opencollective.com/nest/sponsors/badge.svg)](https://opencollective.com/nest#sponsor)-->

## Description

[Nest](https://github.com/nestjs/nest) framework TypeScript starter repository.

## Installation

```bash
$ npm install
```

## Running the app

```bash
# development
$ npm run start

# watch mode
$ npm run start:dev

# production mode
$ npm run start:prod
```

## Test

```bash
# unit tests
$ npm run test

# e2e tests
$ npm run test:e2e

# test coverage
$ npm run test:cov
```

## Support

Nest is an MIT-licensed open source project. It can grow thanks to the sponsors and support by the amazing backers. If you'd like to join them, please [read more here](https://docs.nestjs.com/support).

## Stay in touch

- Author - [Kamil Myśliwiec](https://kamilmysliwiec.com)
- Website - [https://nestjs.com](https://nestjs.com/)
- Twitter - [@nestframework](https://twitter.com/nestframework)

## License

Nest is [MIT licensed](LICENSE).

## Docker

Este projeto está configurado para ser executado em containers Docker, facilitando o deployment e garantindo consistência entre ambientes.

### Pré-requisitos

- Docker instalado na máquina ([Download Docker](https://www.docker.com/get-started))
- Porta 3000 disponível no host

### Estrutura do Dockerfile

O `Dockerfile` utiliza uma imagem Alpine do Node.js 20, otimizando o tamanho da imagem final:

- **Base**: `node:20-alpine`
- **Build**: Instala dependências e compila o projeto TypeScript
- **Runtime**: Executa a aplicação em modo produção
- **Porta**: Expõe a porta 3000

### Comandos Docker

#### Build da Imagem

Cria a imagem Docker com o nome `dnc-backend`:

```bash
docker build . -t dnc-backend
```

#### Executar o Container

Inicia o container em modo detached (background) mapeando a porta 3000:

```bash
docker run -d --name dnc-backend -p 3000:3000 dnc-backend
```

**Parâmetros:**
- `-d`: Executa em background (detached mode)
- `--name dnc-backend`: Define o nome do container
- `-p 3000:3000`: Mapeia a porta 3000 do container para a porta 3000 do host

#### Outros Comandos Úteis

```bash
# Ver containers em execução
docker ps

# Ver logs do container
docker logs dnc-backend

# Parar o container
docker stop dnc-backend

# Iniciar o container novamente
docker start dnc-backend

# Remover o container
docker rm dnc-backend

# Remover a imagem
docker rmi dnc-backend

# Acessar o shell do container
docker exec -it dnc-backend sh
```

### Testando a Aplicação

Após iniciar o container, acesse a aplicação em:

```
http://localhost:3000
```

### Troubleshooting

- **Porta 3000 em uso**: Altere o mapeamento de porta usando `-p 3001:3000`
- **Erros de build**: Verifique se todas as dependências estão listadas no `package.json`
- **Container não inicia**: Verifique os logs com `docker logs dnc-backend`