# LO2 - Software Quality
Om mijn software quality te gebruiken heb ik de volgende technieken/tools gebruikt.

- Staging branch
- Automatisch testen
- Sonarqube

### Staging branch
Om de kans op bugs een stuk kleiner te maken heb ik de backend repo zo ingesteld dat je eerst je commits moet mergen met de staging branch, hierop worden vervolgens autmostiche test op gedraaid en ook kan je hem zelf testen. Pas als je dit gedaan hebt kan je hem mergen met de master branch.

### Automatisch testen
Bij elke pull request worden automatisch tests gerunned, hieraan kan je snel zien of er iets mis is met de nieuwe commits.

### Sonarqube
Ik gebruik sonarqube voor static code analysis, als sonarqube onveilige code of teveel onhandige code ziet zal je dat kunnen zien in de github repo en moet je deze problemen oplossen voordat je kan mergen.