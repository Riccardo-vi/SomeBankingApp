
# Stage 1: Compilazione (Builder)

FROM node AS builder

WORKDIR /app

# Copia il sorgente ed esegue la build di produzione
RUN git clone https://github.com/Riccardo-vi/SomeBankingFrontend.git .
RUN npm install 
RUN npm run build -- --configuration production

# Stage 2: Runtime di Produzione (Nginx)
FROM nginx:alpine

# Pulizia dei file di default di Nginx
RUN rm -rf /usr/share/nginx/html/*

# Copia i file statici dalla sottocartella /browser/ generata da Angular
COPY --from=builder /app/dist/SomeBankingFrontend/browser/ /usr/share/nginx/html/

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]