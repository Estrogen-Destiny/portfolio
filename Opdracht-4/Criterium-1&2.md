## Test Plan

### Case 1: Account maken

**Testscenario:**
- Open de registerpagina.
- Voer verschillende combinaties van gebruikersnamen, e-mails en wachtwoorden in.
- Klik op de register knop.

**Testgegevens:**
1. - Gebruikersnaam: voorbeel
    - Email: test@example.com
    - Wachtwoord: voorbeeld_wachtwoord
2. - Gebruikersnaam: ,test,
    - Email: test2@example.com
    - Wachtwoord: test
3. - Gebruikersnaam: voorbeeld_gebruiker
    - Email: test3@example.com
    - Wachtwoord: voorbeeld_wachtwoord
4. - Gebruikersnaam: speciale ```<svg/onload=alert('XSS Attack')>```
    - Email: test4@example.com
    - Wachtwoord: passwith"XSS"
5. - Gebruikersnaam: testuser
    - Email: test5@example.com
    - Wachtwoord: ```<script>alert('XSS Attack!');</script>```
6. - Gebruikersnaam: testusers
    - Email: test5@example.com
    - Wachtwoord: biepboepboep

**Verwacht resultaat:**
- Voor alle geldige combinaties met een wachtwoord van minimaal 6 characters zou de gebruiker moeten kunnen registreren en doorgestuurd worden naar de indexpagina.
- xss is mogelijk om in de database te stoppen hierdoor is het erg onveilig en heeft een hacker makkelijk toegang to data en de mogelijkheid om dingen aan te passen.

### Case 2: Een nieuw project aanmaken

**Testscenario:**
- Open de pagina voor het aanmaken van een nieuw project.
- Voer verschillende projectnamen en beschrijvingen in.
- Klik op de knop 'aanmaken'.

**Testgegevens:**
1. - Projectnaam: Nieuw Project 1
    - Projectbeschrijving: Dit is een testproject 1.
2. - Projectnaam: Project 2
    - Projectbeschrijving: Beschrijving met speciale tekens: ```<img src="x" onerror="alert('XSS Attack!')" />```
3. - Projectnaam: XSS Project
    - Projectbeschrijving: Dit is een project met een XSS-aanval: ```<script>alert('XSS Attack!');</script>```

**Verwacht resultaat:**
- Alle projecten zouden succesvol moeten worden aangemaakt en toegevoegd worden aan de lijst van projecten van de gebruiker.
- De gebruiker zou doorgestuurd moeten worden naar de indexpagina waar de nieuwe projecten getoond worden.
- xss is mogelijk om in de database te stoppen hierdoor is het erg onveilig en heeft een hacker makkelijk toegang to data en de mogelijkheid om dingen aan te passen.

### Case 3: Een bestaand project bewerken

**Testscenario:**
- Open de indexpagina.
- Zoek een bestaand project om te bewerken.
- Bewerk de projectnaam en beschrijving met verschillende waarden.
- Klik op de knop 'wijzigingen opslaan'.

**Testgegevens:**
1. - Projectnaam: Bijgewerkt Project 1
    - Projectbeschrijving: Dit is de bijgewerkte beschrijving voor project 1.
2. - Projectnaam: Project 2 ```<img src="x" onerror="alert('XSS Attack!')" />```
    - Projectbeschrijving: Beschrijving met XSS-aanval: ```<script>alert('XSS Attack!');</script>```
3. - Projectnaam: XSS Bewerkt Project
    - Projectbeschrijving: Beschrijving met XSS-aanval: ```<img src="x" onerror="alert('XSS Attack!')" />```

**Verwacht resultaat:**
- Alle wijzigingen aan de projectdetails zouden succesvol moeten zijn.
- De bijgewerkte projectinformatie zou getoond moeten worden op de indexpagina.
- Eventuele wijzigingen zouden in de database opgeslagen moeten worden.
- xss is mogelijk om in de database te stoppen hierdoor is het erg onveilig en heeft een hacker makkelijk toegang to data en de mogelijkheid om dingen aan te passen.

Door het toevoegen van speciale tekens en mogelijke XSS-aanvallen in de testgegevens, kunnen we het systeem testen op kwetsbaarheden en potentiële verbeterpunten identificeren.
