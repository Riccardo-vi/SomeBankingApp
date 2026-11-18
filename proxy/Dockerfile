# Immagine leggera ufficiale di Nginx
FROM nginx:alpine

# Sostituisce il file di configurazione principale di Nginx con il tuo
COPY nginx.conf /etc/nginx/nginx.conf

# Espone la porta 80
EXPOSE 80

# Avvia Nginx in primo piano
CMD ["nginx", "-g", "daemon off;"]