---
title: Undersöka ett användarkonto i Microsoft Defender för Endpoint
description: Undersök ett användarkonto för möjliga komprometterade autentiseringsuppgifter eller pivotera på det associerade användarkontot under en undersökning.
keywords: undersöker, konto, användare, användar entitet, avisering, Microsoft Defender för slutpunkt
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: e98142e4076c5e695f16eb06c062bc69d3d7dd55
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935071"
---
# <a name="investigate-a-user-account-in-microsoft-defender-for-endpoint"></a>Undersöka ett användarkonto i Microsoft Defender för Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatgeuser-abovefoldlink)

## <a name="investigate-user-account-entities"></a>Undersöka enheter för användarkonton

Identifiera användarkonton med de mest aktiva aviseringarna (visas på instrumentpanelen som "Användare på risk") och undersöker fall av potentiella komprometterade autentiseringsuppgifter, eller pivotera på det associerade användarkontot när du undersöker en avisering eller enhet för att identifiera möjlig mobil rörelse mellan enheter med det användarkontot.

Användarkontoinformationen finns i följande vyer:

- Instrumentpanelen
- Aviseringskö
- Sidan Enhetsinformation

I de här vyerna finns det en klickbar länk till användarkontots informationssida där mer information om användarkontot visas.

När du undersöker en användarkontotitet visas:

- Användarkontoinformation, Microsoft Defender för identitetsaviseringar och inloggad på enheter, roll, inloggningstyp och annan information
- Översikt över incidenter och användarens enheter
- Aviseringar relaterade till den här användaren
- Observerad i organisationen (enheter som är inloggade)

![Bild på informationssidan för användarkontot](images/atp-user-details-view.png)

### <a name="user-details"></a>Användarinformation

I  fönstret Användarinformation till vänster finns information om användaren, till exempel relaterade öppna incidenter, aktiva aviseringar, SAM-namn, SID, Microsoft Defender för identitetsaviseringar, antalet enheter som användaren är inloggad på, när användaren sågs för första och sista gången, roll och inloggning. Beroende på vilka integrationsfunktioner du har aktiverat visas annan information. Om du till exempel aktiverar Skype för företag-integrering kommer du att kunna kontakta användaren från portalen. Avsnittet **Azure ATP-aviseringar** innehåller en länk som tar dig till sidan Microsoft Defender för identitet om du har aktiverat Microsoft Defender för identitetsfunktionen och det finns aviseringar relaterade till användaren. På sidan Microsoft Defender för identitet hittar du mer information om aviseringarna.

>[!NOTE]
>Du måste aktivera integreringen på både Microsoft Defender för identitet och Defender för Endpoint om du vill använda den här funktionen. I Defender för Slutpunkt kan du aktivera den här funktionen i avancerade funktioner. Mer information om hur du aktiverar avancerade funktioner finns i [Aktivera avancerade funktioner.](advanced-features.md)

Översikt, aviseringar och observerade i organisationen är olika flikar som visar olika attribut om användarkontot.

### <a name="overview"></a>Översikt

På **fliken** Översikt visas incidentinformation och en lista med de enheter som användaren har loggat in på. Du kan expandera dessa om du vill se information om inloggningshändelserna för varje enhet.

### <a name="alerts"></a>Varningar

På **fliken** Aviseringar finns en lista med aviseringar som är kopplade till användarkontot. Den här listan är en [](alerts-queue.md)filtrerad vy av aviseringskön och visar aviseringar där användarkontexten är det valda användarkontot, datumet när den senaste aktiviteten upptäcktes, en kort beskrivning av aviseringen, enheten som är kopplad till aviseringen, aviseringens allvarlighetsgrad, aviseringens status i kön och vem som har tilldelats aviseringen.

### <a name="observed-in-organization"></a>Observerad i organisationen

På  fliken Observerad på organisation kan du ange ett datumintervall för att visa en lista över enheter där användaren har varit inloggad, det vanligaste och minst frekventa inloggade användarkontot för var och en av dessa enheter samt totalt antal observerade användare på varje enhet.

Om du markerar ett objekt i organisationstabellen Observerat utökas objektet och mer information om enheten visas. Om du direkt markerar en länk i ett objekt skickas du till motsvarande sida.

## <a name="search-for-specific-user-accounts"></a>Söka efter specifika användarkonton

1. Välj **Användare** i **sökfältets** nedrullningsbar meny.
2. Ange användarkontot i **sökfältet.**
3. Klicka på sökikonen eller tryck på **Retur.**

En lista med användare som matchar frågetexten visas. Du ser användarkontots domän och namn, när användarkontot senast sågs och det totala antalet enheter som det observerades loggade in på under de senaste 30 dagarna.

Du kan filtrera resultatet efter följande tidsperioder:

- 1 dag
- 3 dagar
- 7 dagar
- 30 dagar
- 6 månader

## <a name="related-topics"></a>Relaterade ämnen

- [Visa och ordna kön Microsoft Defender för slutpunktsaviseringar](alerts-queue.md)
- [Hantera Microsoft Defender för slutpunktsaviseringar](manage-alerts.md)
- [Undersöka Microsoft Defender för slutpunktsaviseringar](investigate-alerts.md)
- [Undersöka en fil som är kopplad till en Defender för slutpunktsavisering](investigate-files.md)
- [Undersök enheter i listan Defender för slutpunktsenheter](investigate-machines.md)
- [Undersöka en IP-adress som är kopplad till en Defender för Slutpunktsavisering](investigate-ip.md)
- [Undersöka en domän som är kopplad till en Defender för slutpunktsavisering](investigate-domain.md)
