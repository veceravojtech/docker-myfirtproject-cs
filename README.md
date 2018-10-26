For non CS people -> sorry for CS language in code...

Docker -- testovací prostředí
==============
Toto je kompletní balíček pro běh webové aplikace v dockeru.. Obsahuje nginx, php, mysql a další potřebné části.

Prvně je ale potřeba Docker mít..
=================================
Jako první nainstaluj Docker CE: 
https://docs.docker.com/install/linux/docker-ce/ubuntu/
https://store.docker.com/editions/community/docker-ce-desktop-windows

Doinstaluj docker-compose:
https://docs.docker.com/compose/install/#prerequisites

Pokud nemáš, doinstaluj MySQL server, ale nic nekonfiguruj.. stačí funkční příkazy pro MySQL.




# Instalace
nainstaluj proxy

`docker run -d -p 80:80 -v /var/run/docker.sock:/tmp/docker.sock:ro --restart=always jwilder/nginx-proxy`


Nezapomeň přidat `mujprojekt.test` do `/etc/hosts` souboru. Ve Windows `C:\windows\system32\drivers\etc\hosts`.


Potom spusť:

```bash
$ docker-compose up
```

# Spuštění

Hotovo! Nyní přejdi na svůj web: `http://mujprojekt.test`

_Note :_ Můžeš re-buildnout veškeré kontejnery tímto příkazem:

```bash
$ docker-compose build
```

