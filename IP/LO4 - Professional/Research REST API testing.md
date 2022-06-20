# REST API testing Research

---

## Inleiding

Ik ben bezig met een project waar meerdere microservices een onderdeel van uitmaken. Ik wil graag de software quality van deze microservices consistent verbeteren.

---

## Onderzoeksvraag

Al de microservices in mijn project bestaan uit REST api's. Ik wil graag een systeem die automatisch deze microservices test om bugs te voorkomen.
Daarom is mijn onderzoeksvraag:

**Wat is een goede manier om mijn REST API-microservices automatisch te testen?**

### Deelvragen:

1. Welke tools zijn er om mijn REST api's te testen? En welke hiervan past het beste bij mijn project?
2. Hoe kan ik runnen van de tests automatiseren?
3. Kan ik het maken van deze test automatiseren?

---

## 1. Welke tools zijn er om mijn REST api's te testen?

Na wat zoeken op google heb ik de volgende lijst kunnen samenstellen
- [SoapUI](https://www.soapui.org/)
- [Postman](https://www.postman.com/)
- [Jmeter](https://jmeter.apache.org/)

### SoapUI

SoapUI is een open source web service testing applicatie voor SOAP en REST api's. Je kan er requests mee maken, api's ontwikkelen, mock api's opzetten en mee testen.
Het testdeel is wat nodig heb om mijn REST api te kunnen testen. Echter toen ik SoapUI ging uitproberen liep ik tegen wat bugs in de UI aan waardoor het programma onbruikbaar werdt.
Hierdoor heb ik niet verder kunnen kijken of ik SoapUI kan gebruiken om mijn REST api te testen.

### Postman

Postman is wat ze zelf noemen een "API platform" het is een dienst waar je api's kan designen, testen en delen.
In postman kan je collections met requests maken, per request kan je instellen wat je terug verwacht en dan geeft postman aan of de request gelukt of mislukt is.
Ook bieden ze een CLI aan die je kan gebruiken om de collections makkelijk te runnen.
Hierdoor denk ik dat postman een goede optie zou zijn voor mijn API tests.

### JMeter

JMeter is een open source applicatie ontworpen om veel verschillende type applicaties te testen met de nadruk op performance testing.
Hierdoor is het een stuk ingewikkelder om mee te starten, omdat er een heleboel opties zijn die je niet nodig voor het testen van een REST api.
Ik heb geprobeerd om een simpele request naar mijn api te maken om JMeter uit te testen, dit is uiteindelijk gelukt maar er zijn heel veel stappen binnnen je test nodig om dit voor elkaar te krijgen.
Hierdoor ben ik tot de conclusie gekomen dat JMeter niet geschikt is voor mijn doeleinden.

### Conclusie

Ik ga verder met Postman aangezien ik denk dat dit het meest geschikte programma zal zijn om mijn doel te bereiken.

---

## 2. Hoe kan ik het runnen van de tests automatiseren?

Postman biedt een tool genaamd Newman aan, hiermee kan je je postman collections gemakkelijk runnen op verschillende plekken.
Aangezien ik voor het CD deel van mijn applicatie al github actions gebruik wilde ik graag kijken of ik de API tests daar ook via kan draaien.
Ze hebben een [pre-made github action](https://github.com/marketplace/actions/newman-action) beschikbaar die ik kon gebruiken.
Deze kan de collection met API tests direct ophalen uit mijn postman account, dit maakt het bijhouden van tests een stuk makkelijker aangezien ik niet elke keer mijn hele postman collectie hoef te exporteren en bij te werken in mijn git repo.
Buiten newman om heb je de mogelijkheid om de testen handmatig op te starten waarna ze wel allemaal automatisch runnen. Dit is echter niet waar ik naar zocht.

### Conclusie

Ik kan via Postman gemakkelijk mijn API tests automatisch laten runnen.

---

## 3. Kan ik het maken van deze tests automatiseren?

Het liefst zou ik zo min mogelijk tijd willen besteden aan het schrijven van de tests,
daarom wil ik kijken of ik het maken er van (deels) kan automatiseren. 
Postman heeft de optie om een OpenAPI specification importeren. Ik maak in mijn project gebruik van swaggergen, deze genereert dit bestand voor me.
Deze kan ik importeren om alle routes en verwachte outputs uit mijn api in postman te zetten.
Hierna moet ik helaas wel nog zelf de condities waarop de test slaagt of faalt specificeren, dit is echter wel een stuk minder werk.

### Conclusie

Ik kan groot deel van mijn testen automatisch laten genereren door postman zelf. Dit scheelt mij veel tijd tijdens development.

---

## Conclusie

Postman en github actions is een goede manier om mijn REST api makkelijk te testen.
omdat ik al gebruik maak van swaggergen in mijn applicatie kan ik ook veel tijd besparen tijdens het schrijven van de testen.

---

## Sources

- [Postman writing tests](https://learning.postman.com/docs/writing-scripts/test-scripts/)
- [Github actions Newman](https://github.com/marketplace/actions/newman-action)
- [Postman info](https://en.wikipedia.org/wiki/Postman_(software))
- [SoapUI info](https://en.wikipedia.org/wiki/SoapUI)
- [JMeter info](https://jmeter.apache.org/)