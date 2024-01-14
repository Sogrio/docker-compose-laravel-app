# Utiliser l'image Nginx officielle
FROM nginx:latest

# Supprimer la configuration par défaut de Nginx
RUN rm /etc/nginx/conf.d/default.conf

# Copier la configuration spécifique pour l'application Laravel
COPY default.conf /etc/nginx/conf.d/

# Exposer le port 80
EXPOSE 80

# Commande par défaut pour démarrer Nginx
CMD ["nginx", "-g", "daemon off;"]

