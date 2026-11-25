# Imagem de desenvolvimento (usada pela API e pela aplicação)
FROM node:22-alpine

WORKDIR /app

# instala as dependências primeiro para aproveitar o cache do Docker
COPY package*.json ./
RUN npm install

COPY . .

EXPOSE 5173 3001

CMD ["npm", "run", "dev", "--", "--host", "0.0.0.0"]
