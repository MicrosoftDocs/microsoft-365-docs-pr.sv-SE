---
title: Integrera ServiceNow-biljetter i Microsoft 365-säkerhetscentret och efterlevnadscentret
description: Lär dig hur du skapar och spårar biljetter i ServiceNow från Säkerhetscentret för Microsoft 365 och efterlevnadscenter.
keywords: säkerhet, Microsoft 365, M365, efterlevnad, efterlevnadscenter, säkerhetscenter, ServiceNow, biljetter, uppgifter, SNOW, anslutning
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
ms.custom:
- seo-marvel-apr2020
ms.openlocfilehash: d258bf3ec4c04eafd22e850329ca925b4c974e94
ms.sourcegitcommit: 41bc923bb31598cea8f02923792c1cd786e39616
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086673"
---
# <a name="integrate-servicenow-tickets-into-the-microsoft-365-security-center-and-compliance-center"></a>Integrera ServiceNow-biljetter i Microsoft 365-säkerhetscentret och efterlevnadscentret

[!include[Prerelease information](../includes/prerelease.md)]

ServiceNow är en populär molnbaserad datorplattform som hjälper företag att hantera digitala arbetsflöden för företagsverksamhet. Deras Now-plattform har IT-arbetsflöden, medarbetararbetsflöden och kundarbetsflöden. [Läs mer om ServiceNow](https://www.servicenow.com/)

Microsoft samarbetar med ServiceNow för att göra det enklare för IT-administratörer att hantera sina biljetter och uppgifter på båda plattformarna. [Microsoft 365 security center](overview-security-center.md) och [Microsoft 365 compliance center](https://docs.microsoft.commicrosoft-365/compliance/microsoft-365-compliance-center) förbättras med möjligheten att skapa och spåra biljetter i ServiceNow.

- [**Hantera ServiceNow-biljetter i säkerhetscentret**](tickets-security-center.md)
- **Hantera ServiceNow-biljetter i efterlevnadscentret** (kommer snart)

## <a name="prerequisites"></a>Förutsättningar

Ha tillgång till Microsoft 365-säkerhetscentret eller efterlevnadscentret och en ServiceNow-instans med:  

* Kingston eller högre version
* Har administratör HI-autentiseringsuppgifter
* Ha administratörsbehörighet för din målleverantörsinstans

ServiceNow rekommenderar att användarna behåller standardinställningarna i din ServiceNow-instans. Om du har anpassningar kan det orsaka fel när du slutför installationschecklistan och integreringen med säkerhetscentret Microsoft 365.

## <a name="data-exchange"></a>Utbyte av uppgifter

När du ansluter Microsoft 365-säkerhetscentret eller efterlevnadscentret till ServiceNow tar Microsoft emot följande ytterligare data:

* Instansnamn för ServiceNow
* ServiceNow-klient-ID
* ServiceNow-klienthemlighet
* ServiceNow-åtkomst & uppdateringstoken

När du skapar en ServiceNow-biljett från Microsoft 365-säkerhetscentret eller efterlevnadscentret skickas följande data till ServiceNow:

* Användar-ID som initierar skapandet av biljetten
* Uppgiftsnamn
* Beskrivning av uppgift
* Prioritet
* Förfallodatum
* Rekommendationskälla (Användarrekommendation eller Microsoft-rekommendation)
* Kategorin Rekommendation (enheter, data, appar, identitet, infrastruktur)

## <a name="connect-to-servicenow"></a>Anslut till ServiceNow

Gå till [Skapa och spåra ServiceNow-biljetter i Microsoft 365-säkerhetscentret](tickets-security-center.md) för att lära dig hur du ansluter till ServiceNow. Anslutningen från Microsoft 365 compliance center kommer snart.

## <a name="troubleshooting"></a>Felsökning

### <a name="you-receive-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a>Ett felmeddelande visas i det första steget i installationschecklistan (OAuth creation)

**Felmeddelande:** Läs åtgärder mot "oauth_entity" från scopet "x_mioms_m365ticket" har avslagits på grund av tabellens åtkomstprincip för korsförfattning

Appen förutsätter att alla administratörer i ServiceNow-instansen kan skapa och läsa OAuth-entiteter. Det här felet kan orsakas på grund av en anpassning på din instans av ServiceNow, vilket begränsar vem som kan skapa/läsa OAuth-entiteter.

**ServiceNow rekommenderar att användarna behåller standardfunktionerna.**

Ange tabellkonfigurationerna "programregister" till standard:

* Etikett = Programregister
* Namn = oauth_entity
* Tillgänglig från = Alla programomfattningar
* Kan läsa = kryssrutan markerad

### <a name="how-to-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a>Validera oauth-entiteten som skapats för Microsoft 365 Security & Compliance-anslutningsappen

Gå till tabellen programregister (**Meny > System OAuth > Application Registry)** i ServiceNow och leta reda på den OAuth-entitet som skapats av dig, med det namn som du tilldelade den.

### <a name="logging-in-as-the-integration-user"></a>Logga in som integrationsanvändare

Innan du godkänner anslutningen mellan Microsoft 365 security center och ServiceNow ska du se till att du använder den användarinloggning och lösenord för integrering som du skapade i installationsstegen. Använd inte dina personliga inloggningsuppgifter.

1. Gå till auktoriseringssidan i ServiceNow.
2. Om du är inloggad med dina personliga inloggningsuppgifter väljer du länken **Inte du** i det övre högra hörnet.
3. Logga in på ServiceNow som integrationsanvändare som du skapade tidigare från installationschecklistan.  
4. Välj **Tillåt** på sidan ServiceNow som frågar om Security + Compliance Connector kan ansluta till ditt ServiceNow-konto.
5. Fortsätt med installationsstegen.

### <a name="how-to-validate-the-integration-user-created-with-the-installation-checklist-for-microsoft-365-security--compliance-connector"></a>Validera integreringsanvändaren som skapats med installationschecklistan för Microsoft 365 Security & Compliance connector

Gå till Användartabell **(Meny > Användaradministration > Användare)** i ServiceNow och hitta den integrationsanvändare som skapats av dig, med det namn som du har tilldelat den.

### <a name="your-company-has-single-sign-on-enabled-which-prevents-you-from-connecting-to-servicenow-through-the-microsoft-365-security-center"></a>Ditt företag har enkel inloggning aktiverad som hindrar dig från att ansluta till ServiceNow via Microsoft 365-säkerhetscentret

Om ditt företag har aktiverat enkel inloggning och du får ett felmeddelande eller inloggning misslyckas, följ en av de två lösningarna.

#### <a name="log-into-servicenow-as-the-integration-user"></a>Logga in på ServiceNow som integrationsanvändare

1. Navigera tillbaka till auktoriseringssidan i ServiceNow.
2. Välj länken **Inte du** i det övre högra hörnet.
3. Logga in på ServiceNow som integrationsanvändare som du skapade tidigare från installationschecklistan.  
4. Välj **Tillåt** på sidan ServiceNow som frågar om Security + Compliance Connector kan ansluta till ditt ServiceNow-konto.
5. Fortsätt med installationsstegen.

#### <a name="create-a-security-admin-user"></a>Skapa en användare av säkerhetsadministratörer

1. Skapa en användare med behörighet för säkerhetsadministratörer i Azure Active Directory. Användaren måste ha samma namn och e-postadress som den integrationsanvändare som du skapade från installationschecklistan. Du kan ta bort rollen säkerhetsadministratör när inloggningen och anslutningen har slutförts.
2. Logga in på Microsoft 365-säkerhetscentret som den här användaren och följ installationsstegen.

### <a name="ip-filtering"></a>IP-filtrering

Om du har aktiverat IP-filtrering kan du behöva uttryckligen tillåta IP-adresser. Se [IP-adressåtkomstkontroll](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) för information om hur du tillåter IP-intervall i ServiceNow. Se [Azure IP Ranges and Service Tags - Public Cloud](https://www.microsoft.com/en-us/download/details.aspx?id=56519) för en lista över IP-adresser som ska tillåtas.

### <a name="installation-is-complete-but-dont-see-tickets-and-cant-share"></a>Installationen är klar men ser inte biljetter och kan inte dela

Om installations- och installationsstegen har slutförts, men du inte ser ServiceNow-korten på startsidan och inte kan dela till ServiceNow från Microsoft Secure Score, kontrollerar du statusen för etableringssidan på https://security.microsoft.com/ticketProvisioning . Välj **Auktorisera** och gå tillbaka till startsidan. Korten ska visas.

## <a name="resources"></a>Resurser

- [Hantera ServiceNow-biljetter i säkerhetscentret](tickets-security-center.md)