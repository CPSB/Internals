# Databanken tijdens ontwikkeling. 

Omdat we op het netwerk van ActivismeBE data groeperen. En plaatsen in verschillende gekoppelde databanken.
Is dit referentie document opgezet. Om overzicht te bieden en een korte handleiding voor het opzetten van de databanken lokaal. 

## De nodige databanken 

We verdelen onze databanken in 2 groepen. Die gaan door het leven met de volgende prefixes: `ACTB_testing`, 'ACTB_prod'. 


`ACTB_testing` = De groep die word gebruikt voor de integratie testen van de applicaties. 
`ACTB_prod`	   = De groep die word gebruikt voor de productie data op de server. 

**Let wel op:** De databanken hebben identiek dezelfde opbouw. Maar verschillen van naam omdat we niet willen dat de productie data
gemengd word met test data. 


## Overzicht benamingen van de databanken. 

- `ACTB_prod_csam`    = Alle productie data omtrent ACL, gebruikers en support. 
- `ACTB_testing_csam` = Alle testing data omtrent ACL, gebruikers en support.

- `ACTB_prod_armoede` = Alle productie data omtrent armoede bestrijding. 
- `ACTB_testing_armoede` = Alle testing data omtrent armoede bestrijding. 

- `ACTB_prod_resources` = Alle productie data die in de csam, armoede bestrijding en activisme van toepassing is. 
- `ACTB_testing_resources` = Alle testing data die in de csam, armoede bestrijding en activisme van toepassing is. 

- `ACTB_prod_activisme` = Alle productie data omtrent het activisme luik. 
- `ACTB_testing_resources` =  Alle testing data omtrent het activisme luik. 

## [OPTIONEEL]: Het aanmaken van de bevoegde gebruiker. 

Persoonlijk raden we als organisatiàe aan om een centrale gebruiker aan te maken voor de databank cluster: 
Men kan dit doen met de volgende commado's: 

```sql
CREATE USER '<uw gebruikersnaam>'@'<uw host>' IDENTIFIED BY '<uw wachtwoord>';
GRANT ALL PRIVILEGES ON  `ACTB\_%` . * TO  '<uw gebruikersnaam>'@'<uw host>';
FLUSH PRIVILEGES;
```

## Vragen tijdens ontwikkeling. 

Indien men vragen heeft tijdens het ontwikkelen of bij opzetten. Aarzel dan niet om aanvraag te doen
