FROM node:18-alpine
WORKDIR /docker-exercise
# Instalar apenas as dependências de produção primeiro
COPY package*.json ./
RUN npm ci --only=production
# Depois instalar as dependências de desenvolvimento
RUN npm install --only=development
# Instalar nodemon globalmente com uma versão específica
RUN npm install -g nodemon@2.0.22
COPY . .
# Otimizar para desenvolvimento
ENV NODE_ENV=development
ENV npm_config_cache=/docker-exercise/.npm
EXPOSE 3000
CMD ["nodemon", "--polling", "--delay", "0"]
