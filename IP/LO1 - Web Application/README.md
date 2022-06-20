# LO1 - Web Application
Voor LO1 heb ik gewerkt aan mijn project "Actionlogger". Dit is een programma waarmee binnnen een bedrijf bijgehouden kan worden waar aan gewerkt wordt.

### Backend
Om de backend te maken heb ik gekozen voor de volgende technieken/tools
- .NET 6 - Framework gemaakt voor C#
- ASP.NET - Web framework voor .NET
- Keycloak - Dit is mijn identity provider gebruikt voor authentication.
- OpenAPI - De specificatie waar mijn API aan moet voldoen, dit is zo dat ik automatisch documentatie voor mijn api kan laten genereren.
- Entity Framework Core - Mijn keuze voor ORM, deze integreert goed met de rest van .NET 6.
- Docker - Voor delivery van de microservices
- Github Actions - voor automatisch builden, testen en deployen

[Backend Repo](https://github.com/TychoVI/ActionloggerBackend)

### Backend Design

![Application Diagram](https://user-images.githubusercontent.com/23315996/174515473-c3c26cd4-8168-407a-9be4-e9e6ccb53c61.png)

### Frontend
Voor mijn backend heb ik de volgende technieken/tools gekozen
- Vuejs - Javascript framework
- Cloudflare pages - Voor automatische building/deployment

[Frontend Repo](https://github.com/TychoVI/ActionloggerFrontend)