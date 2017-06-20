
# Deployment procedure 

## Repository. 

De live versie van een project staat in de `master` branch. En alle ontwikkeling worden doorgevoerd in de `develop` branch.
Zodat het duidelijk is via een Pull Request welke wijzigen er moeten geployed worden. 

Bij de start van een deployment word de Pull Request gemerged. En word er een tag gemaakt die als beschrijving het volgende heeft. 
`Server Deployment {nummer}`. Deze tags zijn nodig voor het geval het stevig mis loopt in de productie omgeving. Dat we als noodplan
vorige tag kunnen downloaden en deployen.

## Deployment Pull Request ticket. 

Voor elke deployment zou een ticket moeten worden opgemaakt in de project repository of Internals. Dit ticket documenteerd. Wie verantwoordelijk is voor de deployment. 
Tijdspanne van de deployment, Wijzigingen aan het project, De uren dat gebruikers last kunnen ondervinden op het platform, Wie de goedkeuring tot deployment heeft gegeven en
last but not least de datum van deployment en aanvraag tot deployment.

**INFO:** Dit mag ook staan als beschrijving in de pull request van `develop` naar `master`

## Assets domein. 

Activisme_BE gebruikt op de server een asset domain. Een voorbehouden domein voor de assets zoals CSS, JS en foto bestanden. De hirarchie bedraagt als volgt. 

```
http://www.assets.activisme.be/{project}/{type}/{bestand}
```

Deze conventie zou gerespecteerd moeten worden doorheen de projecten op de server. De assets worden geplaatst op dit domein. Om de load 
te verlichten op het project domein. Bij elke deployment zou de `assets` map naar de cdn geplaatsts moeten worden. 

## Database 

### 1. Het nemen van back-ups 

Uit voorzorg zou voor elke wijziging van de database een backup getrokken moeten worden getrokken worden van de betreffende database. 
Dit kan met het volgende commando door een SSH terminal uit te voeren. 

```shell 
$ mysqldump -u {naam} -p {database naam} > {naam bestand}.
```

### 2. Wijzigen 

Elke repo bevat een SQL bestand genaamd `Changes.sql` in deze file worden alle SQL queries geplaatst per project om de database in onderhoud 
duidelijk en transparant te beheren. Als de wijzigingen zijn doorgevoerd, Moet de `Changes.sql` Leeg gemaakt worden. En weer gecommit worden
in de project repository.
