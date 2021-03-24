---
title: Skapa indikatorer
ms.reviewer: ''
description: Skapa indikatorer för en filhash, IP-adress, URL:er eller domäner som definierar identifiering, skydd och undantag för enheter.
keywords: hantera, tillåtna, blockerade, blockera, rensa, skadliga, filshashar, ip-adress, url:er, domän
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: fc3bce7130dbdcec76a67df70eb1a6c72474013e
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072089"
---
# <a name="create-indicators"></a>Skapa indikatorer

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

Indikator på kompromettering (IoCs) är en viktig funktion i varje lösning för slutpunktsskydd. Den här funktionen ger SekOps möjlighet att ange en lista över indikatorer för identifiering och blockering (skydd och svar).

Skapa indikatorer som definierar identifiering, skydd och undantag för enheter. Du kan definiera vilken åtgärd som ska vidtas samt varaktigheten för när åtgärden ska tillämpas samt omfattningen av enhetsgruppen som den ska tillämpas på.

Källor som stöds för närvarande är molnidentifieringsmotorn i Defender för Endpoint, den automatiska undersöknings- och åtgärdsmotorn och slutpunktsskyddsmotorn (Microsoft Defender AV).

**Motor för molnidentifiering**<br>
Molnidentifieringsmotorn i Defender för Endpoint söker regelbundet igenom insamlade data och försöker matcha de indikatorer du anger. När det finns en matchning vidtas åtgärden enligt de inställningar du har angett för IoC.

**Slutpunktsskyddsmotor**<br>
Samma lista över indikatorer används av agenten för förebyggande åtgärder. Om Microsoft Defender AV är den primära av-konfigurerade av-appen kommer de matchade indikatorerna att hanteras i enlighet med inställningarna. Om åtgärden till exempel är "Avisering och Blockera" förhindras filkörningar (blockering och åtgärd) av Microsoft Defender AV, och en motsvarande avisering höjs. Å andra sidan, om åtgärden är inställd på "Tillåt" kommer Microsoft Defender AV inte att identifiera eller blockera filen från att köras.

**Motor för automatisk undersökning och åtgärder**<BR>
Automatisk undersökning och åtgärd fungerar på samma sätt. Om en indikator är inställd på "Tillåt" ignorerar automatiserad undersökning och åtgärd en "dålig" bedömning för den. Om denna anges till "Block" behandlas automatisk undersökning och åtgärd som "dåligt".


De aktuella åtgärderna som stöds är:
- Tillåt
- Endast avisering
- Avisering och blockering


Du kan skapa en indikator för:
- [Filer](indicator-file.md)
- [IP-adresser, URL:er/domäner](indicator-ip-domain.md)
- [Certifikat](indicator-certificates.md)


>[!NOTE]
>Det finns en gräns på 15 000 indikatorer per klientorganisation.


## <a name="related-topics"></a>Relaterade ämnen

- [Skapa sammanhangsberoende IoC](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file)
- [Använda API:t För slutpunktsindikatorer i Microsoft Defender](ti-indicator.md)
- [Använda partnerintegrerade lösningar](partner-applications.md)
