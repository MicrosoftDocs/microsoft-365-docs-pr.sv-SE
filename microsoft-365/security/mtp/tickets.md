---
title: Skapa och spåra biljetter via ServiceNow
description: Microsoft 365 security center förbättras med möjlighet att skapa och spåra biljetter i ServiceNow. Säkerhetsadministratörer kan skicka en rekommendation om säker poäng direkt till ServiceNow och skapa en biljett.
keywords: säkerhet, Microsoft 365, M365, säker poäng, säkerhetscenter, ServiceNow, biljetter, uppgifter
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: eb6af6b11d2d932f3bd2165aa3f597c14feb5ae8
ms.sourcegitcommit: b6c4b514b2cb6739af949780d7e2a5a5c8dcc161
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/27/2020
ms.locfileid: "43901028"
---
# <a name="manage-tickets-through-servicenow"></a>Hantera biljetter via ServiceNow

ServiceNow är en populär molnbaserad datorplattform som hjälper företag att hantera digitala arbetsflöden för företagsverksamhet. Deras Now-plattform har IT-arbetsflöden, medarbetararbetsflöden och kundarbetsflöden. Microsoft samarbetar med ServiceNow för att göra det enklare för IT-administratörer att hantera sina biljetter och uppgifter på båda plattformarna. [Läs mer om ServiceNow](https://www.servicenow.com/)

Microsoft 365 security center utökas nu med möjlighet att skapa och spåra biljetter i ServiceNow. Säkerhetsadministratörer kan skicka en förbättringsåtgärd för [Microsoft Secure Score](microsoft-secure-score.md) direkt till ServiceNow och skapa en biljett. Både incidenthantering och ändringshanteringsbiljetter kan skapas. De kan sedan spåras på startsidan för Microsofts säkerhetscenter och ServiceNow.

## <a name="prerequisites"></a>Förutsättningar

Ha tillgång till Microsoft 365-säkerhetscentret och en ServiceNow-instans med:  

* Kingston eller högre version
* Har administratör HI-autentiseringsuppgifter
* Ha administratörsbehörighet för din målleverantörsinstans

ServiceNow rekommenderar att användarna behåller standardinställningarna i din ServiceNow-instans. Om du har anpassningar kan det orsaka fel när du slutför installationschecklistan och integreringen med säkerhetscentret Microsoft 365.

## <a name="data-exchange"></a>Utbyte av uppgifter

När du ansluter Microsoft 365-säkerhetscentret till ServiceNow tar Microsoft emot följande ytterligare data:

* Instansnamn för ServiceNow
* ServiceNow-klient-ID
* ServiceNow-klienthemlighet
* ServiceNow-åtkomst & uppdateringstoken

När du skapar en ServiceNow-biljett från Microsoft 365-säkerhetscentret skickas följande data till ServiceNow:

* Användar-ID som initierar skapandet av biljetten
* Uppgiftsnamn
* Beskrivning av uppgift
* Priority
* Förfallodatum
* Rekommendationskälla (Användarrekommendation eller Microsoft-rekommendation)
* Kategorin Rekommendation (enheter, data, appar, identitet, infrastruktur)

## <a name="connect-microsoft-365-security-center-to-servicenow"></a>Ansluta Microsoft 365-säkerhetscenter till ServiceNow

Gå till startsidan för Microsoft 365-säkerhetscentret för att se ServiceNow-anslutningskortet.

![Använder du ServiceNow](../../media/do-you-use-servicenow-250.png)

Välj "Anslut till ServiceNow" för att gå till inställningssidan för ServiceNow. Följ instruktionerna för att auktorisera Microsoft 365 Connector-appen.

> [!NOTE]
> Innan du godkänner anslutningen mellan Microsoft 365 security center och ServiceNow ska du se till att du använder den användarinloggning och lösenord för integrering som du skapade i installationsstegen. Använd inte dina personliga inloggningsuppgifter.

När du har följt anvisningarna och auktoriserat anslutningen kan du visa anslutningsstatusen på både anslutningssidan för Microsoft 365-säkerhetscenter och i ServiceNow Microsoft 365 Ticketing Connector App-upplevelsen. Nu är du redo att börja skapa uppgifter!

## <a name="create-a-task-and-share-it-to-servicenow"></a>Skapa en uppgift och dela den till ServiceNow

När integreringen har konfigurerats skapar du ServiceNow-uppgifter baserat på specifika microsoft secure score-förbättringsåtgärder. Gå till alla förbättringsåtgärder i Secure Score i Microsoft 365 security center-portalen och välj ikonen "dela". Ett av listrutan är ServiceNow.

![ServiceNow-delning i Secure Score](../../media/servicenow-share.png)

En aktivitet genereras där du kan ange prioritet och redigera namn, beskrivning eller förfallodatum. När alla obligatoriska fält har fyllts i skickar du uppgiften till ServiceNow.

Uppgiften visas i ServiceNow som en Microsoft 365-begäran om säkerhet och konfigurationsändring.

## <a name="track-tickets"></a>Spåra biljetter

När ServiceNow-biljetter för ändringshantering och incidenthantering har skapats visas de på kort på startsidan för Microsoft 365-säkerhetscentret. Från dessa kort kan du skapa en biljett, visa alla biljetter eller hantera ServiceNow-konfigurationen.

![ServiceNow ändringshanteringsbiljetter](../../media/change-management-375.png)  ![ServiceNow incidenthanteringsbiljetter](../../media/incident-management-375.png)

Om du vill återetablera eller hantera din ServiceNow-integrering i Microsoft 365-säkerhetscentret väljer du **Hantera ServiceNow-konfiguration** på något av korten. Därifrån tar du bort den aktuella ServiceNow-anslutningen och anpassar biljetttillståndsnamn.

Med ServiceNow-biljetter synliga i Microsoft 365-säkerhetscentret bor dina uppgifter på en plats där de kan spåras och hanteras tillsammans med dina andra säkerhetsinstrumentpanelobjekt.

## <a name="troubleshooting"></a>Felsökning

### <a name="you-receive-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a>Ett felmeddelande visas i det första steget i installationschecklistan (OAuth creation)

**Felmeddelande:** Läs åtgärder mot "oauth_entity" från scopet "x_mioms_m365ticket" har avslagits på grund av tabellens åtkomstprincip för korsförfattning

Appen förutsätter att alla administratörer i TjänstenNow-instansen kan skapa och läsa OAuth-entiteter. Det här felet kan bero på en anpassning på din instans av ServiceNow, vilket begränsar vem som kan skapa/läsa OAuth-entiteter.

**ServiceNow rekommenderar att användarna behåller standardfunktionerna.**

Ange tabellkonfigurationerna "programregister" till standard:

* Etikett = Programregister
* Namn = oauth_entity
* Tillgänglig från = Alla programomfattningar
* Kan läsa = kryssrutan markerad

### <a name="how-to-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a>Validera oauth-entiteten som skapats för Microsoft 365 Security & Compliance-anslutningsappen

Gå till tabellen programregister (**Meny > System OAuth > Application Registry)** i ServiceNow och leta reda på den OAuth-entitet som skapats av dig, med det namn som du har tilldelat den.

### <a name="logging-in-as-the-integration-user"></a>Logga in som integrationsanvändare

Innan du godkänner anslutningen mellan Microsoft 365 security center och ServiceNow ska du se till att du använder den användarinloggning och lösenord för integrering som du skapade i installationsstegen. Använd inte dina personliga inloggningsuppgifter.

1. Gå till auktoriseringssidan i ServiceNow.
2. Om du är inloggad med dina personliga autentiseringsuppgifter väljer du länken **Inte du** i det övre högra hörnet.
3. Logga in på ServiceNow som integrationsanvändare som du skapade tidigare från installationschecklistan.  
4. Välj **Tillåt** på sidan ServiceNow som frågar om Security + Compliance Connector kan ansluta till ditt ServiceNow-konto.
5. Fortsätt med installationsstegen.

### <a name="how-to-validate-the-integration-user-created-with-the-installation-checklist-for-microsoft-365-security--compliance-connector"></a>Validerar integreringsanvändaren som skapats med installationschecklistan för Microsoft 365 Security & Compliance connector

Gå till Användartabell **(Meny > Användaradministration > Användare)** i ServiceNow och hitta integrationsanvändaren som skapats av dig, med det namn som du har tilldelat den.

### <a name="your-company-has-single-sign-on-enabled-which-prevents-you-from-connecting-to-servicenow-through-the-microsoft-365-security-center"></a>Ditt företag har enkel inloggning aktiverad som hindrar dig från att ansluta till ServiceNow via Microsoft 365-säkerhetscentret

Om ditt företag har aktiverat enkel inloggning och du får ett felmeddelande eller inloggning misslyckas, följ en av de två lösningarna.

#### <a name="log-into-servicenow-as-the-integration-user"></a>Logga in på ServiceNow som integrationsanvändare

1. Navigera tillbaka till auktoriseringssidan i ServiceNow.
2. Välj länken **Inte du** i det övre högra hörnet.
3. Logga in på ServiceNow som integrationsanvändare som du skapade tidigare från installationschecklistan.  
4. Välj **Tillåt** på sidan ServiceNow som frågar om Security + Compliance Connector kan ansluta till ditt ServiceNow-konto.
5. Fortsätt med installationsstegen.

#### <a name="create-a-security-admin-user"></a>Skapa en användare av säkerhetsadministratörer

1. Skapa en användare med behörighet för säkerhetsadministratörer i Azure Active Directory. Användaren måste ha samma namn och e-postadress som den integrationsanvändare som du skapade från installationschecklistan. Du kan ta bort säkerhetsadministratörsrollen när inloggningen och anslutningen har slutförts.
2. Logga in på Microsoft 365-säkerhetscentret som den här användaren och följ installationsstegen.

### <a name="ip-filtering"></a>IP-filtrering

Om du har aktiverat IP-filtrering kan du behöva uttryckligen tillåta IP-adresser. Se [IP-adressåtkomstkontroll](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) för information om hur du tillåter IP-intervall i ServiceNow. Se [Azure IP Ranges and Service Tags - Public Cloud](https://www.microsoft.com/en-us/download/details.aspx?id=56519) för en lista över IP-adresser som ska tillåtas.

### <a name="installation-is-complete-but-dont-see-tickets-and-cant-share"></a>Installationen är klar men ser inte biljetter och kan inte dela

Om installations- och installationsstegen har slutförts, men du inte ser ServiceNow-korten på startsidan och inte kan dela till https://security.microsoft.com/ticketProvisioningServiceNow från Microsoft Secure Score, kontrollerar du statusen för etableringssidan på . Välj **Auktorisera** och gå tillbaka till startsidan. Korten ska visas.

