---
title: Skapa och spåra ServiceNow-biljetter i Microsoft 365-säkerhetscentret
description: Lär dig hur du skapar och spårar biljetter i ServiceNow från Microsoft 365-säkerhetscenter.
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
ms.custom:
- seo-marvel-apr2020
ms.openlocfilehash: 48512cf2fff802509ebaa14ca69d3ca02908902e
ms.sourcegitcommit: 41bc923bb31598cea8f02923792c1cd786e39616
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/09/2020
ms.locfileid: "45087939"
---
# <a name="create-and-track-servicenow-tickets-in-the-microsoft-365-security-center"></a>Skapa och spåra ServiceNow-biljetter i Microsoft 365-säkerhetscentret

[Microsoft 365-säkerhetscentret](overview-security-center.md) har förbättrats med möjligheten att skapa och spåra biljetter i ServiceNow. [Läs mer om ServiceNow](https://www.servicenow.com/)

I säkerhetscentret kan säkerhetsadministratörer skicka en förbättringsåtgärd för [Microsoft Secure Score](microsoft-secure-score.md) direkt till ServiceNow och skapa en biljett. Både incidenthantering och ändringshanteringsbiljetter kan skapas. De kan sedan spåras på säkerhetscentrets startsida och ServiceNow.

- [**Läs mer om förutsättningar, datautbyte och felsökning**](tickets.md)
- **Hantera ServiceNow-biljetter i efterlevnadscentret** (kommer snart)

## <a name="connect-microsoft-365-security-center-to-servicenow"></a>Ansluta Microsoft 365-säkerhetscenter till ServiceNow

Gå till startsidan för Microsoft 365-säkerhetscentret för att se ServiceNow-anslutningskortet.

![Använder du ServiceNow](../../media/do-you-use-servicenow-250.png)

Välj "Anslut till ServiceNow" för att gå till servicenow-inställningssidan. Följ instruktionerna för att auktorisera Microsoft 365 Connector-appen.

> [!NOTE]
> Innan du godkänner anslutningen mellan Microsoft 365 security center och ServiceNow ska du se till att du använder den användarinloggning och lösenord för integrering som du skapade i installationsstegen. Använd inte dina personliga inloggningsuppgifter.

När du har följt anvisningarna och auktoriserat anslutningen kan du visa anslutningsstatusen på både microsoft 365-säkerhetscentrets anslutningssida och i ServiceNow Microsoft 365 Ticketing Connector App-upplevelsen. Nu är du redo att börja skapa uppgifter!

### <a name="troubleshooting"></a>Felsökning

Lär dig vanliga fel som kan uppstå i anslutningsprocessen och hur du kan minska dem i [felsökningsavsnittet](tickets.md#troubleshooting).

## <a name="create-a-task-and-share-it-to-servicenow"></a>Skapa en uppgift och dela den till ServiceNow

När integreringen har konfigurerats skapar du ServiceNow-uppgifter baserat på specifika microsoft secure score-förbättringsåtgärder. Gå till alla förbättringsåtgärder i Secure Score i Microsoft 365 security center-portalen och välj ikonen "dela". Ett av listrutan är ServiceNow.

![ServiceNow-delning i Secure Score](../../media/servicenow-share.png)

En aktivitet genereras där du kan ange prioritet och redigera namn, beskrivning eller förfallodatum. När alla obligatoriska fält har fyllts i skickar du uppgiften till ServiceNow.

Uppgiften visas i ServiceNow som en microsoft 365-begäran om säkerhet och konfigurationsändring.

## <a name="track-tickets"></a>Spåra biljetter

När ServiceNow-biljetter för ändringshantering och incidenthantering har skapats visas de på kort på startsidan för Microsoft 365-säkerhetscentret. Från dessa kort kan du skapa en biljett, visa alla biljetter eller hantera ServiceNow-konfigurationen.

![ServiceNow ändringshanteringsbiljetter](../../media/change-management-375.png)  ![ServiceNow incidenthanteringsbiljetter](../../media/incident-management-375.png)

Om du vill återupprätta eller hantera din ServiceNow-integrering i Microsoft 365-säkerhetscentret väljer du **Hantera ServiceNow-konfiguration** på något av korten. Därifrån tar du bort den aktuella ServiceNow-anslutningen och anpassar biljetttillståndsnamn.

Med ServiceNow-biljetter synliga i Microsoft 365-säkerhetscentret bor dina uppgifter på en plats där de kan spåras och hanteras tillsammans med dina andra säkerhetsinstrumentpanelobjekt.

## <a name="resources"></a>Resurser

- [Läs mer om förutsättningar, datautbyte och felsökning](tickets.md)
- [Microsoft Secure Score](microsoft-secure-score.md)