---
title: Skapa och spåra ServiceNow biljetter i säkerhets Center för Microsoft 365
description: Lär dig hur du skapar och spårar biljetter i ServiceNow från Microsoft 365 Security Center.
keywords: säkerhet, Microsoft 365, M365, säker poäng, säkerhets Center, ServiceNow, biljetter, uppgifter
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
ms.openlocfilehash: 8992efdd79295b6b56b8f033bd97b10f59a7a4d5
ms.sourcegitcommit: bd36c88e731e3fee2a3a5cb3564fdc94f11bab94
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769681"
---
# <a name="create-and-track-servicenow-tickets-in-the-microsoft-365-security-center"></a>Skapa och spåra ServiceNow biljetter i säkerhets Center för Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

>[!CAUTION]
>**Förhands gransknings perioden för ServiceNow-kopplingen slutar**<br>
>Denna funktion kommer inte längre att vara tillgänglig i slutet av november 2020. Tack för din feedback och fortsatta support medan vi bestämmer nästa steg.

[Säkerhets Center för Microsoft 365](overview-security-center.md) har förbättrats med möjligheten att skapa och spåra biljetter i ServiceNow. [Lär dig mer om ServiceNow](https://www.servicenow.com/)

I säkerhets Center kan säkerhets administratörer skicka en åtgärd för [säker Poäng](microsoft-secure-score.md) förbättring direkt till ServiceNow och skapa en biljett. Både hantering av problem och hantering av ändringar kan skapas. Spåra biljetter i säkerhets centrets start sida och ServiceNow.

- [**Läs mer om förutsättningar, data utbyte och fel sökning**](tickets.md)
- **Hantera ServiceNow biljetter i överensstämmelse Center** (ej tillgängligt)

## <a name="connect-microsoft-365-security-center-to-servicenow"></a>Ansluta Microsoft 365 säkerhets Center till ServiceNow

Gå till start sidan för Microsoft 365 säkerhets Center för att se ServiceNow-anslutnings kortet.

![Använder du ServiceNow](../../media/do-you-use-servicenow-250.png)

Välj "Anslut till ServiceNow" för att gå till sidan för inställning av ServiceNow. Följ instruktionerna för att auktorisera Microsoft 365 Connector-appen.

> [!NOTE]
> Innan du godkänner anslutningen mellan Microsoft 365 säkerhets Center och ServiceNow bör du kontrol lera att du använder den inloggning och det lösen ord som du skapade i installations stegen. Använd inte dina personliga autentiseringsuppgifter.

När du har följt anvisningarna och godkänt anslutningen kan du Visa anslutnings statusen på sidan för Microsoft 365 Security Centre-anslutningen och i ServiceNow Microsoft 365 Ticking Connector. Nu är du redo att börja skapa aktiviteter.

### <a name="troubleshooting"></a>Felsökning

Lär dig mer om vanliga fel som kan komma att visas i anslutnings processen och hur du minskar dem i [avsnittet fel sökning](tickets.md#troubleshooting).

## <a name="create-a-task-and-share-it-to-servicenow"></a>Skapa en uppgift och dela den med ServiceNow

När integrationen är aktive rad kan du skapa ServiceNow uppgifter baserat på specifika åtgärder för [säker Poäng](microsoft-secure-score.md) förbättring. Gå till alla åtgärder för säker Poäng förbättring i säkerhets Center för Microsoft 365 och välj **dela** . Ett av de nedrullningsbara alternativen är ServiceNow.

En aktivitet skapas där du kan ange prioritet och redigera namn, beskrivning eller förfallo datum. När alla obligatoriska fält är ifyllda skickar du uppgiften till ServiceNow.

Aktiviteten visas i ServiceNow som en begäran om ändring av en Microsoft 365-säkerhet och-konfiguration.

## <a name="track-tickets"></a>Spåra biljetter

När ServiceNow för hantering av ändringar har skapats visas de på kort på Start sidan för Microsoft 365 säkerhets Center. Från dessa kort kan du skapa en biljett, Visa alla biljetter eller hantera ServiceNow-konfigurationen.

![ServiceNow för ändrings hantering](../../media/change-management-375.png)  ![ServiceNow ärende hantering biljetter](../../media/incident-management-375.png)

Om du vill etablera eller hantera din ServiceNow-integrering i säkerhets Center för Microsoft 365 väljer du **Hantera ServiceNow-konfiguration** på något av korten. Därifrån kan du ta bort den aktuella ServiceNow-anslutningen och anpassa namn på biljett status.

Med ServiceNow biljetter som visas i Microsoft 365 Security Center är dina uppgifter aktiva på en plats där de kan spåras och behandlas på andra säkerhets instrument paneler.

## <a name="resources"></a>Resurser

- [Läs mer om förutsättningar, data utbyte och fel sökning](tickets.md)
- [Microsoft Secure Score](microsoft-secure-score.md)
