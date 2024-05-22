# Test Plan

## Testplan: Account aanmaken

### Hoofdscenario: Succesvolle registratie
**Testscenario:**
1. Open de registerpagina.
2. Voer een geldige combinatie van gebruikersnaam, e-mail en wachtwoord in.
3. Klik op de register knop.

**Testgegevens:**
- Gebruikersnaam: voorbeeldgebruiker
- Email: voorbeeld@example.com
- Wachtwoord: geldig_wachtwoord123

**Verwacht resultaat:**
- De gebruiker wordt succesvol geregistreerd.
- De gebruiker wordt doorgestuurd naar de indexpagina.
- Een bevestigingsbericht wordt weergegeven met "Registratie succesvol".

### Alternatief scenario 1: Gebruikersnaam al in gebruik
**Testscenario:**
1. Open de registerpagina.
2. Voer een gebruikersnaam in die al in gebruik is.
3. Klik op de register knop.

**Testgegevens:**
- Gebruikersnaam: reedsbestaandegebruiker
- Email: nieuwe@example.com
- Wachtwoord: nieuw_wachtwoord123

**Verwacht resultaat:**
- De registratie mislukt.
- Een foutmelding wordt weergegeven met "Gebruikersnaam al in gebruik, kies een andere gebruikersnaam".

### Alternatief scenario 2: Ongeldige e-mail
**Testscenario:**
1. Open de registerpagina.
2. Voer een ongeldige e-mail in.
3. Klik op de register knop.

**Testgegevens:**
- Gebruikersnaam: nieuwegebruiker
- Email: ongeldigemailformaat
- Wachtwoord: geldig_wachtwoord123

**Verwacht resultaat:**
- De registratie mislukt.
- Een foutmelding wordt weergegeven met "Ongeldig e-mailformaat, voer een geldige e-mail in".

## Case 2: Een nieuw project aanmaken

### Hoofdscenario: Succesvol project aanmaken
**Testscenario:**
1. Open de pagina voor het aanmaken van een nieuw project.
2. Voer een geldige projectnaam en beschrijving in.
3. Klik op de knop 'aanmaken'.

**Testgegevens:**
- Projectnaam: Nieuw Project
- Projectbeschrijving: Dit is een testproject.

**Verwacht resultaat:**
- Het project wordt succesvol aangemaakt.
- De gebruiker wordt doorgestuurd naar de indexpagina.
- Het nieuwe project wordt in de lijst van projecten getoond.

### Alternatief scenario 1: Projectnaam al in gebruik
**Testscenario:**
1. Open de pagina voor het aanmaken van een nieuw project.
2. Voer een projectnaam in die al in gebruik is.
3. Klik op de knop 'aanmaken'.

**Testgegevens:**
- Projectnaam: Bestaand Project
- Projectbeschrijving: Dit is een testproject met een bestaande naam.

**Verwacht resultaat:**
- Het project wordt niet aangemaakt.
- Een foutmelding wordt weergegeven met "Projectnaam al in gebruik, kies een andere naam".

### Alternatief scenario 2: XSS-aanval in beschrijving
**Testscenario:**
1. Open de pagina voor het aanmaken van een nieuw project.
2. Voer een projectnaam en een beschrijving met een XSS-aanval in.
3. Klik op de knop 'aanmaken'.

**Testgegevens:**
- Projectnaam: Veilig Project
- Projectbeschrijving: `<script>alert('XSS Attack!');</script>`

**Verwacht resultaat:**
- Het project wordt niet aangemaakt.
- Een foutmelding wordt weergegeven met "Ongeldige invoer, speciale tekens zijn niet toegestaan".

## Case 3: Een bestaand project bewerken

### Hoofdscenario: Succesvolle bewerking
**Testscenario:**
1. Open de indexpagina.
2. Zoek een bestaand project om te bewerken.
3. Bewerk de projectnaam en beschrijving met geldige waarden.
4. Klik op de knop 'wijzigingen opslaan'.

**Testgegevens:**
- Projectnaam: Bijgewerkt Project
- Projectbeschrijving: Dit is de bijgewerkte beschrijving.

**Verwacht resultaat:**
- De wijzigingen worden succesvol opgeslagen.
- De bijgewerkte projectinformatie wordt op de indexpagina getoond.
- Een bevestigingsbericht wordt weergegeven met "Wijzigingen succesvol opgeslagen".

### Alternatief scenario 1: Ongeldige projectnaam
**Testscenario:**
1. Open de indexpagina.
2. Zoek een bestaand project om te bewerken.
3. Bewerk de projectnaam met een ongeldige naam.
4. Klik op de knop 'wijzigingen opslaan'.

**Testgegevens:**
- Projectnaam: `<img src="x" onerror="alert('XSS Attack!')" />`
- Projectbeschrijving: Geldige beschrijving.

**Verwacht resultaat:**
- De wijzigingen worden niet opgeslagen.
- Een foutmelding wordt weergegeven met "Ongeldige projectnaam, speciale tekens zijn niet toegestaan".

### Alternatief scenario 2: XSS-aanval in beschrijving
**Testscenario:**
1. Open de indexpagina.
2. Zoek een bestaand project om te bewerken.
3. Bewerk de projectbeschrijving met een XSS-aanval.
4. Klik op de knop 'wijzigingen opslaan'.

**Testgegevens:**
- Projectnaam: Geldige Naam
- Projectbeschrijving: `<script>alert('XSS Attack!');</script>`

**Verwacht resultaat:**
- De wijzigingen worden niet opgeslagen.
- Een foutmelding wordt weergegeven met "Ongeldige invoer, speciale tekens zijn niet toegestaan".

---

Met deze testplannen kunnen we niet alleen de functionaliteit van de applicatie valideren, maar ook potentiële beveiligingsrisico's identificeren, zoals XSS-aanvallen. Het testen van verschillende scenario's zorgt ervoor dat de applicatie robuust en veilig blijft.
