# Exercice Kubernetes [minikube]

Crée un `DaemonSet` qui générera un index.html contenant la date actuelle et se mettra à jour toutes les minutes et sera ensuite transmis par un `ReplicaSet` (3) serveurs hhtpd qui pourra etre lu par l'user (NodePort) à l'aide d'un `Service`

## Commandes

- Lancer la: `kubectl apply -f .`


> Si jamais il y a un problème d'ip (serveur introuvable ou non autorisé), c'est qu'il y a un conflit au niveau de l'adresse IP, ne pas hésiter à relancer une nouvelle VM `minikube delete` puis `minikube start` et recommencer.

> Si vous voulez tout réinitialiser (pods/services/replicaset/etc.) car il y a des erreurs, ou que vous voulez simplement vous amusez à changer les fichiers YAML, faites: `kubectl delete all --all -A`

## Résultat final

Entrer la commande:`curl <ip_node>:<ip_nodePort>`

- Dans le cas de minikube, on a qu'un node soit: `minikube ip`-> qui retournera l'ip du node
- Ici, le <ip_nodePort> vaut `30000`

Résultat: `Fri Mar 19 23:16:37 UTC 2021`.

A refaire toutes les minutes, la date sera mise à jour.