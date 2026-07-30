# Pluton

sert de base aux agents hermes

## commandes

/nemo , /alpha : quick commands qui n'utilisent pas le llm pour changer de modèle.
nécessite que hermes soit executable dans docker (.venv/bin dans le chemin PATH du docker)
attention, les quick commands n'apparaissent pas dans le dashboard/config ni dans le chat completion mais elles fonctionnent bien.

## architecture

chaque agent est un docker qui lance les services suivants :

- hermes-agent
- dashboard : Il permet de faire un chat et voir les logs
- gateway (listening on 8642) : Il reçoit les requetes du de télégram

la base du docker est nous/hermes:latest. Ensuite on a un volume qui contient l'install (.venv) /opt/hermes et unvolume qui contient les données de l'agent /opt/data. Seul /opt/data est gitté.

J'ai du faire chmod 755 /root car il stocke ou cherche à lire des fichiers dans /root alors que /opt/hermes est le working dir et /opt/data est hermes home.

ajout d'un docker webui pour avoir une autre vision de l'agent.

## Webui

localhost:8788 ok

## Upgrade docker image

supprimer le disque qui contient /opt/hermes et builder la nouvelle image. Ensuite, ça monte correctement.
