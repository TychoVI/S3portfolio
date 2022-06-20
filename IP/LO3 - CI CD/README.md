# LO3 - CI/CD
Voor mijn CI/CD heb ik de volgende technieken/tools gebruikt.
- Docker
- Github Actions
- Cloudflare pages

### Docker
Alle microservices worden via een dockerfile gebuild naar hun eigen docker image. Deze kan je vervolgens makkelijk opstarten waar je maar wilt.

### Github actions
Deze gebruik ik om de docker images te builden. Ook sonarqube en de tests draaien via github actions.

[Workflow files](https://github.com/TychoVI/ActionloggerBackend/tree/staging/.github/workflows)

### Cloudflare pages
Mijn frontend wordt gebuild en gedeployed via cloudflare pages. Deze doet dit bij elke push naar de master en naar de staging branch. Deze zijn vervolgens ook te bereiken via aparte endpoints.