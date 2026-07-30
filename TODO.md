## explorer

tester modele fallback
tester message vocal
ajouter une commande pour:

- google/gemini 2.5 : 5 par minute
- ollama minimax-m2.5
  ou en fallback

LLM Wiki
Knowledge-base observability

## bugs

le port de l'agent ne répond pas

## models

ok :
OpenRouter nvidia/nemotron-3-super-120b-a12b:free
OpenRouter openrouter/owl-alpha
openrouter google/gemma-4-31b-it:free
google google/gemini-2.5-flash limité à 10 par minute
nvidia nvidia/nemotron-3-super-120b-a12b:free
ollama minimax-m2.5:cloud

model_aliases:
fav:
model: claude-sonnet-4.6
provider: anthropic
grok:
model: grok-4
provider: x-ai

## idées

utiliser opencode pour faire une appli avec des fonctionnalités de rendu
utiliser opencode pour avoir un accès gratuit à des modèles de qualité : mapper opencode -x à une requete openAI

## gateway

ne lit pas les .md
/health ko
dahsboard montre que la gateway est down
la gateway est un service natif

8788 ? - "127.0.0.1:8642:8642" ?
n'est pas dans s6 c'est pour ça qu'on la voit pas
✓ main-hermes: up
✓ dashboard: up
✓ Per-profile gateways: 0/1 supervised up (default)

## Dashboard

chat du dokcer ko alors que ok pour webui
gateway affichée stopped : its gateway-liveness detection requires a shared PID namespace with the gateway process. y a un pb de lock ? aussi dans http://localhost:8787/ profile default alors que system status donne ok
restart non ok
update ne foncitonne pas en docker
chat : ws passe pas, pip install 'hermes-agent[web,pty]'

si traefik devant : dashboard:
public_url: "https://dashboard.example.com/hermes"

/tasks : /background Organize the photos
ou kanban

## Dockers

pour plusieurs dockers, si on partage le meme volume agent-src, ca va faire des conflits
ne pas le monter pour odin ?

ajouter dans le path ~/.local/bin/hermes

⚠ No GITHUB_TOKEN (60 req/hr rate limit — set in /opt/data/.env for better rates)

## Architecture

Faire un ODIN séparé. de pluton
