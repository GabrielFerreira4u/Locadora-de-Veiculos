# Locadora de Veículos

**Aluno(a):** _(coloque seu nome aqui)_

Sistema web para gerenciar uma locadora de veículos: frota, clientes e todo o ciclo
de locação (retirada, vistorias, pagamentos, devolução e nota fiscal).

**Tecnologias:** React · TypeScript · Vite · React Router · Bootstrap · JSON Server · Axios

## Como executar

### Com Docker (recomendado)

```bash
docker compose up --build
```

- Aplicação: http://localhost:5173
- API (JSON Server): http://localhost:3001

Serviços do `docker-compose.yml`: `api` (JSON Server) e `web` (Vite). O código local é
montado dentro dos containers, então as alterações aparecem sem rebuild e o `db.json`
continua sendo salvo na pasta do projeto. Para parar: `Ctrl+C` e `docker compose down`.

### Sem Docker

```bash
npm install
npm run server   # API em http://localhost:3001 (JSON Server)
npm run dev      # aplicação em http://localhost:5173
```

Rode os dois comandos em terminais separados.

## Estrutura

```
db.json           dados de exemplo (uma coleção por entidade do MER)
Dockerfile        imagem de desenvolvimento (Node 22)
docker-compose.yml  serviços api (JSON Server) e web (Vite)
src/
├── components/   componentes reutilizáveis de interface
├── models/       interfaces e tipos das entidades do MER
├── pages/        telas da aplicação
├── service/      comunicação com a API
├── App.tsx
└── main.tsx
```

## Andamento

- [x] Parte 1 – projeto base, models, serviços e `db.json`
- [x] Parte 2 – componentes reutilizáveis, rotas e Marcas
- [ ] Parte 3 – Categorias, Modelos e Veículos
- [ ] Parte 4 – Manutenções e Clientes
- [ ] Parte 5 – Locação (registro, contrato e vistoria de retirada)
- [ ] Parte 6 – Devolução, pagamentos, nota fiscal, consultas e regras de negócio

## Prints das telas

_(serão adicionados ao final)_
