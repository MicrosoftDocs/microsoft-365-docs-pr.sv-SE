---
title: Microsoft 365 Nätverksplatstjänster
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
description: Microsoft 365 Nätverksplatstjänster
ms.openlocfilehash: ed78d7ba48cd9666ce1aae1af5478e3b7536e1e1
ms.sourcegitcommit: fb6c5e04ade1e82b26b2f911577b5ac721f1c544
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/13/2021
ms.locfileid: "52470454"
---
# <a name="microsoft-365-network-connectivity-location-services"></a>Microsoft 365 Nätverksplatstjänster

I Microsoft 365 Administrationscenter visas nu Nätverksinsikter och prestandarekommendationer, som är prestandamätvärden i realtid som samlas in från Microsoft 365 klientorganisation. De här måtten kan endast visas av administrativa användare i klientorganisationen. Organisationsnätverksanslutningen är utformad per kontorsplats genom en utgående nätverksplats till Internet. Microsoft 365 en klientanslutning använder den vägen och sedan via Internet till Microsofts serviceservrar. Att identifiera kontor är avgörande för att kunna visa dessa nätverksinsikter.

## <a name="location-in-network-measurements"></a>Plats i nätverksmått

Organisationens administratör kan registrera sig för att inkludera plats i nätverksmåtten som används av den här funktionen. På så sätt kan du automatiskt identifiera den stad där varje kontor ligger. Platsinformationen är inte exakt och är obfuscated till 300m och kategoriseras efter ort. Vid den tidpunkt då platsen fångas på en Windows enhet  visas ikonen Plats i användning i verktygsfältet. Administratörer kan vilja meddela användarna om ikonens utseende. Med denna bearbetning behandlas platsen som organisationens kontorsplats och inte som plats för en person eller en enhet. Nätverksinsikter kan visas i dessa identifierade städer på kontor. Om du vill ha högre precision i rekommendationerna kan du ange specifika kontorsadresser. I stället aggregeras nätverksinsikter till de platserna. Office kan inte aggregeras närmare än 300 meter.

## <a name="location-in-the-microsoft-365-admin-center"></a>Plats i Microsoft 365 Administrationscenter

I Microsoft 365 administrationscentret används Bing för att visa var organisationens kontor finns. Kontrollerna visar även nätverks perimetertopologi för en vald kontorsplats. När en administratör lägger till specifik adressinformation för kontorsplatser används Bing-kartor för att föreslå adresser för att göra det lättare att lägga till data.

## <a name="terms-of-use"></a>Användningsvillkor

Allt innehåll som Bing-kartor via e-post, inklusive geokoder, kan endast användas i den produkt som innehållet tillhandahålls från. Kundens användning av platstjänster i Microsoft 365 Admin Center, som drivs av Bing-kartor, styrs av de användningsvillkor _för Bing-kartor End-User_ som finns tillgängliga på och <https://go.microsoft.com/?linkid=9710837> [Microsofts sekretesspolicy.](https://go.microsoft.com/fwlink/?LinkID=248686)

Den här funktionen, som Bing-kartor, stöds också av **TomTom.** Mer information om TomToms produkter och tjänster finns på [https://www.tomtom.com/legal](https://www.tomtom.com/legal) .

## <a name="related-topics"></a>Relaterade ämnen

[Nätverksanslutningen i Microsoft 365 (förhandsversion)](office-365-network-mac-perf-overview.md)

[Microsoft 365 nätverksprestandainsikter (förhandsversion)](office-365-network-mac-perf-insights.md)

[Microsoft 365 nätverksutvärdering (förhandsversion)](office-365-network-mac-perf-score.md)

[Microsoft 365 anslutningstest i Microsoft 365 (förhandsversion)](office-365-network-mac-perf-onboarding-tool.md)
