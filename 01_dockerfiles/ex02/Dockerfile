Vous allez créer votre premier Dockerfile containerisateur d’application Rails. Ce Dockerfile
sera un peu spécial car il sera générique et devra être appelé dans un autre
Dockerfile, qui devrait ressembler un peu à ça :

FROM ft-rails:on-build
EXPOSE 3000
CMD ["rails", "s", "-b", "0.0.0.0", "-p" ,"3000"]

Votre container générique devra, depuis un container ruby, installer toutes les dépendances
nécessaires, puis copier votre application rails dans le dossier /opt/app
de votre container.
Au build, Docker doit faire l’installation des gems spécifiques, ainsi
que les migrations et la population de la db de votre application. Le Dockerfile-fils devra
exposer les bons ports et lancer le serveur de rails (voir exemple ci-dessus).

https://docs.docker.com/develop/develop-images/dockerfile_best-practices/#user
https://docs.docker.com/engine/reference/builder/#from
https://rubyonrails.org/
