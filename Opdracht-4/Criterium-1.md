## Test Plan

### Case 1: Inloggen met geldige referenties

**Testscenario:**
- Open de inlogpagina.
- Voer een geldige gebruikersnaam en wachtwoord in.
- Klik op de inlogknop.

**Testgegevens:**
- Gebruikersnaam: voorbeeld_gebruiker
- Wachtwoord: voorbeeld_wachtwoord

**Verwacht resultaat:**
- De gebruiker zou moeten inloggen en doorgestuurd worden naar de indexpagina.
- Het dashboard of de startpagina van de gebruiker zou getoond moeten worden met hun projecten.

### Case 2: Een nieuw project aanmaken

**Testscenario:**
- Open de pagina voor het aanmaken van een nieuw project.
- Voer een geldige projectnaam en beschrijving in.
- Klik op de knop 'aanmaken'.

**Testgegevens:**
- Projectnaam: Nieuw Project
- Projectbeschrijving: Dit is een testproject.

**Verwacht resultaat:**
- Het project zou succesvol aangemaakt moeten worden en toegevoegd worden aan de lijst van projecten van de gebruiker.
- De gebruiker zou doorgestuurd moeten worden naar de indexpagina waar het nieuwe project getoond wordt.

### Case 3: Een bestaand project bewerken

**Testscenario:**
- Open de indexpagina.
- Zoek een bestaand project om te bewerken.
- Klik op de bewerkknop voor het geselecteerde project.
- Bewerk de projectnaam of beschrijving.
- Klik op de knop 'wijzigingen opslaan'.

**Testgegevens:**
- Projectnaam: Bijgewerkt Project
- Projectbeschrijving: Dit is de bijgewerkte beschrijving voor het project.

**Verwacht resultaat:**
- De projectdetails zouden succesvol bijgewerkt moeten worden.
- De bijgewerkte projectinformatie zou getoond moeten worden op de indexpagina.
- Eventuele wijzigingen zouden in de database opgeslagen moeten worden.

## Test Rapportage

### Uitvoeringsstappen:
1. Open de applicatie.
2. Navigeer naar de aangegeven pagina's voor elk testgeval.
3. Voer de verstrekte testgegevens in.
4. Voer de handelingen uit zoals beschreven in de testscenario's.
5. Controleer de werkelijke resultaten ten opzichte van de verwachte resultaten.

### Gevonden Problemen:
- Er zijn geen problemen gevonden tijdens de uitvoering van de testgevallen.

## Conclusie

De testgevallen zijn succesvol uitgevoerd en alle verwachte resultaten zijn behaald zonder enige problemen te tegenkomen. De applicatie lijkt correct te functioneren op basis van de gedefinieerde testscenario's.

Verdere testen kunnen nodig zijn om aanvullende functionaliteiten of uitzonderingsgevallen te dekken. Echter, gebaseerd op de huidige testresultaten, lijkt de applicatie stabiel en gereed voor implementatie.
