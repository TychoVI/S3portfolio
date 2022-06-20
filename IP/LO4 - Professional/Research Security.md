# Security Research - Broken Access Control

---

## Inleiding

Microservices vormen tegenwoordig de basis van veel webapplicaties. Veel van deze applicaties werken met privacygevoelige informatie. Hoe zorg je ervoor dat alleen de mensen die toegang moeten hebben toegang krijgen?

---

## Onderzoeksvraag

**Hoe kan je de data van je gebruikers effectief beveiligen?**

### Deelvragen
1. Wat zijn de stappen die we moeten uitvoeren?
2. Hoe kan je iemand authenticaten?
3. Hoe kan je iets authorizen?

---

## 1. Wat zijn de stappen die we moeten uitvoeren?

Eerst moeten we weten wie iemand is. Dit noemen we "Authentication"

Daarna moeten we weten waar diegene toegang tot heeft. Dit noemen we "Authorization"

## 2. Hoe kan je iemand authenticaten?

Dit ging vroeger eigenlijk altijd via een gebruikernaam + wachtwoord combinatie. Tegenwoordig heb je er ook opties zoals "Magic link" (je vult je email adres in en krijgt een linkje om in te loggen) of externe identity providers (zoals google of facebook).

Ik heb gezocht naar producten/diensten die dit aanbieden en heb er een paar op een rijtje gezet.

- **Auth0**
    - Cloud-hosted
    - Betaald met free-tier beschikbaar
    - SDK libraries voor meeste programmeerplatformen
    - Ondersteunt OpenID Connect
- **Keycloak**
    - Self-Hosted
    - Open source community edition
    - Ondersteunt OpenID Connect
- **Onelogin**
    - Cloud-hosted
    - Betaald
    - SDK libraries voor veel programmeerplatformen
    - Ondersteunt OpenID Connect
- **Azure Active Directory B2C**
    - Cloud-hosted
    - Betaald met free-tier beschikbaar
    - SDK libraries voor kleine set programmeerplatformen
    - Ondersteunt OpenID Connect
- **SuperTokens**
    - Self-Hosted of Cloud-Hosted
    - Open source
    - SDK libraries voor kleine set programmeerplatformen

Zoals je kan zien ondersteunen bijna alle identity provider opties "OpenID Connect" Dit is een laagje bovenop OAuth 2 dat authentication er aan toe voegt. OAuth 2 is een protocol dat je applicatie (meestal de client) zich laat authorizen bij je API.
OpenID zorgt ervoor dat je API makkelijk bij een zogenoemde "Authorization server" kan opvragen of de inloggegevens kloppen.

## 3. Hoe kan je iets authorizen

Dit gaat via het bovengenoemde OAuth2 protocol. Dit werkt via "Json web tokens". Deze stuurt de client zelf mee, de API's weten of een JWT echt omdat hij gesigned is met een private key door je authorization server. Hierdoor hoeft een API niet verbinding te maken met een extern systeem om te weten of de JWT legitiem is.

---

## Conclusie

Ik kan via een identity provider de toegang tot mijn API's regelen. Mijn voorkeur gaat uit naar eentje die OpenID ondersteunt aangezien dit een standaard is. Dit zorgt er voor dat ik niet mijn hele applicatie hoef om te bouwen als ik wil switchen naar een andere. Ook is het een veilige optie aangezien OpenID connect op het populaire en goed geteste OAuth2 protocol is gebaseerd.

---

## Sources

[OpenID Connect info](https://openid.net/connect/)
[Oauth2 info](https://auth0.com/intro-to-iam/what-is-oauth-2/)