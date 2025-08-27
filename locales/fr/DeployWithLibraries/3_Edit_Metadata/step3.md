La propriété Deploy dans sampleContract.json contient tout ce dont vous avez besoin pour indiquer à Remix IDE l'adresse de la bibliothèque pour un réseau spécifique.

- <address> contient l'adresse de la bibliothèque déjà déployée. Vous devez spécifier cette adresse pour chaque réseau.
- autoDeployLib est un booléen et indique à Remix IDE s'il doit déployer automatiquement la bibliothèque avant de déployer le contrat.

En gros, si autoDeployLib est vrai, le <address> ne sera pas utilisé et Remix déploiera automatiquement la bibliothèque avant de déployer le contrat.

Pour les besoins de cette démonstration, nous simulons une situation où la bibliothèque a déjà été déployée, car c'est une situation plus courante.

Définissez donc autoDeploy à faux, pour l'entrée VM:-.

Passez à l'étape suivante.
