# Containerisation et mise en production back + front projet final
### Pablo Huys

## <u>1. Test en local</u>

Dans un premier temps, afin de tester la communication entre le front et le back-end,
j'ai du ouvrir 2 terminaux sur chacune des parties. Pour initialiser les projets node,
j'ai utilisé la commande:
```
npm init
```

Côté back, j'ai aussi du initialiser la **BDD** avec les commandes:
```
npx prisma generate dev
npx prisma migrate dev
```
Une fois ces deux choses de fait, je pouvais accéder au front et me connecter avec un
compte de test en lançant les deux projets avec ``npm run start et npm run dev``

![connexion](./images/connect.PNG)

## <u>2. Création des containers</u>

Pour la création des containers, j'ai ajouté un **Dockerfile** dans le front et dans le back,
ces fichiers se chargent de copier le front et le back dans des containers, d'initialiser la BDD
et d'exposer les ports puis finalement lancer les applications.

Le docker compose lui se charge de créer les services à partir des docker files et de les rassembler dans le 
même network.

![connexion](./images/containers.PNG)

Pour ce qui est des images, le front-end est assez light mais le back-end est lourd même
sous version alpine. Je n'ai pas trouvé comment optimiser d'avantages.

![connexion](./images/images.PNG)

## <u>1. Déploiement avec **Railway**</u>