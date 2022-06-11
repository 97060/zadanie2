---
# Sprawozdanie - zadanie 2
### Autor: Michał Grabowiec 
---
**Zadanie zostało wykonane na podstawie otrzymanego na laboratorium przykładu.**
Jedyne zmiany zostały poczynione w kodzie [workera](../main/worker/index.js)

```js
const a1 = 3;
const q = 3;

function geometricProgression(n) {
  return a1 * Math.pow(q, n-1);
}

sub.on('message', (channel, message) => {
  redisClient.hset('values', message, geometricProgression(parseInt(message)));
});
```
Zostały dodane 2 stałe oraz funkcja do obliczania zadanego elementu ciągu geometrycznego.

### Budowanie obrazów
Obrazy zostały zbudowane oraz dodane na repozytorium [dockerHub](https://hub.docker.com/u/97060).
![image](https://user-images.githubusercontent.com/103126350/173197201-897e3b46-5819-458a-a144-dbb28ed72595.png)

### Uruchomienie testowe z użyciem docker compose
Na potrzeby testowe projekt może zostać uruchomiony z użyciem `docker compose`
![image](https://user-images.githubusercontent.com/103126350/173197321-0474daf8-3221-4330-9c1d-1df64189bd61.png)

Aplikacja testowa działa prawidłowo
![image](https://user-images.githubusercontent.com/103126350/173197474-ad101113-22e9-4ed6-92d1-fe1636f67adf.png)

### Uruchomienie z użyciem docker swarm
Do uruchomienia projetku z użyciem docker swarm używany jest nowo utworzony plik konfikuracyjny [docker-swarm.yml](../main/docker-swarm.yml) oparty na pliku do testowania na docker compose (używane są obrazy z dockerhub).

Najpierw wykonujemy polecenie `docker swarm init`
![image](https://user-images.githubusercontent.com/103126350/173197504-2ca66742-1e21-4ba8-b5ac-f353f298adca.png)

Następne wykonujemy deploy na cluster.
![image](https://user-images.githubusercontent.com/103126350/173197696-ba007dd5-a652-49f7-82ab-56dd3e3ddf9a.png)

Aplikacja działa prawidłowo
![image](https://user-images.githubusercontent.com/103126350/173197719-a09b3f4f-6a99-4e08-85e4-c47c43b87211.png)

---
