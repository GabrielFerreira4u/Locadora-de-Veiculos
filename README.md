# Locadora de Veículos

**Aluno:** _Gabriel Ferreira Lima_

Sistema web para gerenciar uma locadora de veículos: frota, clientes e todo o ciclo
de locação (retirada, vistorias, pagamentos, devolução e nota fiscal).

**Tecnologias:** React · TypeScript · Vite · React Router · Bootstrap · JSON Server · Axios

## Como executar
### Com Docker

```bash
cd locadora-veiculos
docker compose up --build
docker compose down
```

- Aplicação: http://localhost:5173
- API (JSON Server): http://localhost:3001

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

## Funcionalidades

- **Cadastros (RF01–RF06):** marcas, categorias (com valor da diária), modelos, veículos, manutenções (com histórico por veículo) e clientes. CPF, CNH, placa e chassi não se repetem.
- **Locação (RF07–RF13):** registro com cliente, veículo disponível e datas; valor previsto calculado automaticamente (nº de diárias × diária da categoria); contrato gerado automaticamente; vistoria de retirada; devolução com vistoria, recálculo do valor total e atualização do km do veículo; pagamentos múltiplos; nota fiscal para locações finalizadas.
- **Consultas (RF14–RF16):** lista de locações filtrada por status e cliente; tela de detalhes (cliente, veículo, contrato, vistorias, pagamentos e nota fiscal); situação de cada veículo (disponível, locado ou em manutenção).
- **Regras de negócio (RN01–RN06):** veículo com locação aberta não pode ser locado; devolução prevista posterior à retirada; CNH vencida bloqueia a locação; km de devolução não pode ser menor que o de retirada; nota fiscal só para locação finalizada; registros com dependentes não podem ser excluídos.

### Observações

- Um veículo aparece como **Em manutenção** quando tem manutenção com data de hoje ou futura, e como **Locado** quando tem locação aberta.
- Para testar a RN03, use a cliente *Carla Mendes* (CNH vencida) do `db.json`.
- Para testar a RN06, tente excluir a marca *Volkswagen* (tem o modelo Gol).

## Prints das telas

_(adicione aqui os prints das principais telas)_
