
FROM nginx:latest

# Modifier le contenu par défaut de la page d'accueil de Nginx
RUN sed -i 's/nginx/xavki/g' /usr/share/nginx/html/index.html

# Exposer le port 80
EXPOSE 80

# Lancer Nginx en premier plan
CMD ["nginx", "-g", "daemon off;"]
