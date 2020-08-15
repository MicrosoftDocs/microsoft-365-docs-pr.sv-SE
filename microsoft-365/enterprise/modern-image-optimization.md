---
title: Optimera bilder i SharePoint Online-sidor med moderna webbplatser
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 03/11/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.reviewer: sstewart
search.appverid:
- MET150
description: Lär dig hur du använder verktygen i SharePoint Online för att optimera bilder i SharePoint Online-moderna webbplats sidor.
ms.openlocfilehash: 09122dfd0bc832cf9a09cfb05bf0540e323797d9
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694810"
---
# <a name="optimize-images-in-sharepoint-online-modern-site-pages"></a>Optimera bilder i SharePoint Online-sidor med moderna webbplatser

Den här artikeln hjälper dig att förstå hur du optimerar bilder i SharePoint Online-moderna webbplats sidor.

Information om hur du optimerar bilder i klassiska publicerings webbplatser finns i [bild optimering för SharePoint Online](image-optimization-for-sharepoint-online.md)..

>[!NOTE]
>Mer information om prestanda i SharePoint Online-moderna portaler finns i [prestanda i den moderna SharePoint-upplevelsen](https://docs.microsoft.com/sharepoint/modern-experience-performance).

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-image-optimization"></a>Använd verktyget för nätverksdiagnostik för SharePoint för att analysera bild optimering

Verktyget för nätverksdiagnostik för SharePoint är ett webb läsar tillägg för de nya Microsoft Edge- https://www.microsoft.com/edge) webbläsarna (och Chrome som analyserar både SharePoint Online moderna Portal och klassisk publicerings webbplats sidor. Verktyget visar en rapport för varje sida som visar hur sidan fungerar mot en viss uppsättning prestanda villkor. Om du vill installera och läsa mer om verktyget för nätverksdiagnostik för SharePoint kan du gå till [använda diagnostikverktyget för SharePoint Online](page-diagnostics-for-spo.md).

>[!NOTE]
>Verktyget för nätverksdiagnostik fungerar bara för SharePoint Online och kan inte användas på en SharePoint-Systemsida.

När du analyserar en modern SharePoint-webbplats med verktyget för SharePoint-diagnostik kan du se information om stora bilder i fönstret _diagnos test_ .

Möjliga resultat:

- **Åtgärd krävs** (röd): Sidan innehåller **en eller flera** bilder över 300KB storlek
- **Ingen åtgärd krävs** (grön): Sidan innehåller inga bilder över 300KB storlek

Om resultatet som **identifieras** visas i det **underskrivna underavsnittet** i resultatet kan du klicka på resultatet för att visa ytterligare information.

![Resultat för verktyget Nätverksdiagnostik](../media/modern-portal-optimization/pagediag-large-images.png)

## <a name="remediate-large-image-issues"></a>Åtgärda stora problem med bilden

Om en sida innehåller bilder över 300KB väljer du de **stora bilderna som identifieras** och visar vilka bilder som är för stora. På moderna SharePoint Online-sidor visas åter givningar av bilder automatiskt och storlek beroende på webbläsarens fönster och upplösningen för klient övervakaren. Du bör alltid optimera bilder för webb användning innan du laddar upp till SharePoint Online. Mycket stora bilder kommer automatiskt att minskas till storlek och upplösning, vilket kan leda till oväntade åter givnings egenskaper.

Innan du gör sid ändringar för att åtgärda prestanda problem ska du anteckna sid inläsnings tiden i analys resultaten. Kör verktyget igen efter ändringen för att se om det nya resultatet är inom bas linje standarden och kontrol lera den nya sid inläsnings tiden för att se om det gjorts en förbättring.

![Tids resultat för sid inläsning](../media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
>Sid inläsnings tiden kan variera beroende på en mängd olika faktorer, till exempel nätverks belastning, tidpunkt och andra tillfälliga förhållanden. Testa sid inläsnings tid ett par gånger innan och efter det att du har gjort ändringar för att få hjälp med medelvärdet.

## <a name="related-topics"></a>Relaterade ämnen

[Justera SharePoint Online-prestanda](tune-sharepoint-online-performance.md)

[Justera Office 365-prestanda](tune-microsoft-365-performance.md)

[Prestanda i den moderna SharePoint-upplevelsen](https://docs.microsoft.com/sharepoint/modern-experience-performance)

[Nätverk för innehålls leverans](content-delivery-networks.md)

[Använda Office 365-innehålls leverans nätverk (CDN) med SharePoint Online](use-microsoft-365-cdn-with-spo.md)
