---
title: Skydda din organisation mot webbhot
description: Läs mer om webbskydd i Microsoft Defender ATP och hur du kan skydda din organisation.
keywords: webbskydd, skydd mot webbhot, surfning, säkerhet, nätfiske, skadlig kod, sårbarhet, webbplatser, nätverksskydd, Edge, Internet Explorer, Chrome, Firefox, webbläsare
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 3376308988213b84bc7badb96ebacdf706d1ca5f
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071673"
---
# <a name="protect-your-organization-against-web-threats"></a>Skydda din organisation mot webbhot

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

Skydd mot webbhot är en del [av webbskyddet](web-protection-overview.md) i Defender för Endpoint. Den använder [nätverksskydd](network-protection.md) för att skydda dina enheter mot webbhot. Genom att integrera med Microsoft Edge och populära webbläsare från tredje part, som Chrome och Firefox, stoppar webbhotskydd webbhot utan webbproxy och kan skydda enheter när de är borta eller lokalt. Skydd mot webbhot hindrar åtkomst till nätfiskewebbplatser, skadlig programvara, sårbarhetswebbplatser, icke betrodda eller ryktesbaserade webbplatser samt webbplatser som du har blockerat i din anpassade [indikatorlista.](manage-indicators.md)

>[!Note]
>Det kan ta upp till en timme innan enheter får nya kundindikatorer.

## <a name="prerequisites"></a>Förutsättningar
Webbskydd använder nätverksskydd för att tillhandahålla surfsäkerhet i Microsoft Edge och webbläsare från tredje part.

Så här aktiverar du nätverksskydd på dina enheter:
- Redigera säkerhetsbaslinjen för Defender för slutpunkt under **Web & Network Protection** för att aktivera nätverksskydd innan du distribuerar eller distribuerar om det. [Läs mer om att granska och tilldela Säkerhetsbaslinje för Defender för slutpunkt](configure-machines-security-baseline.md#review-and-assign-the-microsoft-defender-for-endpoint-security-baseline)
- Aktivera nätverksskyddet med hjälp av Intune-enhetskonfiguration, SCCM, Grupprincip eller DIN MDM-lösning. [Läs mer om hur du aktiverar nätverksskydd](enable-network-protection.md)  

>[!Note]
>Om du anger endast nätverksskydd **som Granskning är** blockeringen otillgänglig. Du kan också identifiera och logga försök att komma åt skadliga och oönskade webbplatser endast på Microsoft Edge.

## <a name="related-topics"></a>Relaterade ämnen

- [Översikt över webbskydd](web-protection-overview.md)
- [Skydd mot webbhot](web-threat-protection.md)
- [Övervaka webbsäkerhet](web-protection-monitoring.md)
- [Svara på webbhot](web-protection-response.md)
- [Nätverksskydd](network-protection.md)
