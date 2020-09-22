---
title: Microsoft 365 nätverks anslutningar (för hands version)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 nätverks anslutningar (för hands version)
ms.openlocfilehash: f2ab872f67eca70ab2791d3ad6fe1396b009cc18
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200787"
---
# <a name="microsoft-365-network-connectivity-location-services-preview"></a>Microsoft 365 nätverks anslutningar (för hands version)

Administrations centret för Microsoft 365 visar nu **nätverks insikter och prestanda rekommendationer**, som är real tids värden som samlas in från din Microsoft 365-klient organisation och som endast kan visas av administrativa användare i din klient organisation. Organisatoriska nätverks anslutningar är utformat per Office-plats via ett nätverks utgångs läge till Internet. Microsoft 365-klienten använder den vägen och sedan via Internet till Microsofts tjänst front dörr Server. Att identifiera Office-platsen är viktig för att kunna visa dessa nätverks insikter.

## <a name="location-in-network-measurements"></a>Plats i nätverks mått

En organisations administratör kan välja plats att ingå i nätverks måtten som används av den här funktionen. Detta aktiverar automatisk identifiering av staden där varje kontor finns. Plats informationen är inte exakt och är Obfuscated till 300 m och kategoriseras efter ort. När platsen sparas på en Windows-enhet kommer den att visa en ikon för **användning i** verktyget och administratören kanske vill meddela användarna om det. Med den här behandlingen behandlas platsen som organisationens Office-plats och inte till platsen för en person eller enhet. Nätverks insikter kan visas på dessa upptäckta Office-städer. Om du vill ha större rekommendationer kan administratören ange specifika Office-adresser och nätverks insikter aggregeras till dem i stället. Office-platserna kan inte aggregeras mer nära 300 meter.

## <a name="location-in-the-microsoft-365-admin-center"></a>Plats i administrations centret för Microsoft 365

I Microsoft 365 Admin Center används kart kart kontroller för att visa var organisationens Office-platser finns och för att Visa nätverkstopologi för en vald Office-plats. När en administratör lägger till specifik adress information för Office-platser används Bing Maps också för att föreslå adresser för att under lätta data inmatningen.

## <a name="terms-of-use"></a>Användnings villkor

Allt innehåll som tillhandahålls via Bing Maps, inklusive koder, kan endast användas inom den produkt som innehåller innehållet. Användning av plats tjänster för administrations Center för Microsoft 365, som drivs av Bing Maps, regleras av _slut användar användnings villkoren för Bing Maps_ <https://go.microsoft.com/?linkid=9710837> och _Microsofts sekretess policy_ finns på <https://go.microsoft.com/fwlink/?LinkID=248686.>

Den här funktionen, som tillhandahålls genom Bing Maps, stöds också av denna **teknik**. Så här fungerar Bing Maps-tjänster som tillhandahålls av denna teknik regleras av den _här teknik tjänst villkoren_ på <https://legal.here.com/en-gb/terms> .

## <a name="related-topics"></a>Relaterade ämnen

[Nätverks anslutning i Microsoft 365 Admin Center (för hands version)](office-365-network-mac-perf-overview.md)

[Microsoft 365 nätverks prestanda (för hands version)](office-365-network-mac-perf-insights.md)

[Microsoft 365 Network Assessment (för hands version)](office-365-network-mac-perf-score.md)

[Microsoft 365 anslutnings test i M365 administrations Center (för hands version)](office-365-network-mac-perf-onboarding-tool.md)
