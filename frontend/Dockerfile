
# Stage 1: Compilazione (Builder)

FROM node:20-alpine AS builder

WORKDIR /app

# Copia e installa le dipendenze
COPY package*.json ./
RUN npm install

# Copia il sorgente ed esegue la build di produzione
COPY . .
RUN npm run build -- --configuration production
# Stage 2: Runtime di Produzione (Nginx)

FROM nginx:alpine

# Pulizia dei file di default di Nginx
RUN rm -rf /usr/share/nginx/html/*

# Copia i file statici dalla sottocartella /browser/ generata da Angular
COPY --from=builder /app/dist/SomeBankingFrontend/browser/ /usr/share/nginx/html/

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]