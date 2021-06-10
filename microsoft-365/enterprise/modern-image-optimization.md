---
title: Optimera bilder i SharePoint sidor för moderna webbplatser online
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
description: Lär dig hur du använder verktygen i SharePoint Online för att optimera bilder på SharePoint moderna webbsidor online.
ms.openlocfilehash: a4f2def86e1378a9fb76ae9ecbe6a55da75ecffc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923022"
---
# <a name="optimize-images-in-sharepoint-online-modern-site-pages"></a>Optimera bilder i SharePoint sidor för moderna webbplatser online

Den här artikeln hjälper dig att förstå hur du optimerar bilder i SharePoint sidor med modern webbplats online.

Information om hur du optimerar bilder i klassiska publiceringswebbplatser finns [i SharePoint Online.](image-optimization-for-sharepoint-online.md)

>[!NOTE]
>Mer information om prestanda i SharePoint moderna portaler finns i [Prestanda i det moderna SharePoint upplevelse.](/sharepoint/modern-experience-performance)

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-image-optimization"></a>Använda siddiagnostik för det SharePoint verktyget för att analysera bildoptimering

Siddiagnostik för SharePoint är ett webbläsartillägg för nya Microsoft Edge ( och Chrome-webbläsare som analyserar både moderna SharePoint Online-portalen och klassiska https://www.microsoft.com/edge) publiceringswebbplatssidor. Verktyget innehåller en rapport för varje analyserad sida som visar hur sidan fungerar mot en definierad uppsättning prestandavillkor. Om du vill installera och lära dig mer SharePoint siddiagnostikverktyget går du till Använda [verktyget Siddiagnostik för SharePoint Online.](page-diagnostics-for-spo.md)

>[!NOTE]
>Verktyget Siddiagnostik fungerar bara för SharePoint Online och kan inte användas på en SharePoint systemsida.

När du analyserar SharePoint webbplats med siddiagnostik för SharePoint kan du se information om stora bilder i _fönstret Diagnostiktest._

Möjliga resultat är:

- **Obs!** Obligatoriskt (rött): Sidan **innehåller en eller flera** bilder som är större än 300 KB
- **Ingen åtgärd krävs** (grön): Sidan innehåller inga bilder större än 300 KB

Om det **upptäckta resultatet för stora** bilder visas **i** avsnittet Kräver uppmärksamhet i resultatet kan du klicka på resultatet för att visa ytterligare information.

![Resultat av verktyget Siddiagnostik](../media/modern-portal-optimization/pagediag-large-images.png)

## <a name="remediate-large-image-issues"></a>Åtgärda stora bildproblem

Om en sida innehåller bilder större än 300 kB väljer du resultatet För stora bilder som upptäckts kan du se vilka bilder som är för stora.  På moderna SharePoint onlinesidor tillhandahålls återgivningar av bilder automatiskt och deras storlek beroende på storleken på webbläsarfönstret och klientskärmens upplösning. Du bör alltid optimera bilder för webbanvändning innan du laddar upp till SharePoint Online. Mycket stora bilder minskar automatiskt i storlek och upplösning, vilket kan resultera i oväntade renderingsegenskaper.

Innan du gör sidändringar för att åtgärda prestandaproblem bör du anteckna inläsningstiden för sidan i analysresultatet. Kör verktyget igen efter ändringen för att se om det nya resultatet ligger inom baslinjestandarden och kontrollera inläsningstiden för den nya sidan för att se om det finns en förbättring.

![Inläsningstid för sida](../media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
>Sidinläsningstiden kan variera beroende på en mängd faktorer, till exempel nätverksbelastning, tid på dagen och andra tillfälliga villkor. Du bör testa inläsningstiden några gånger före och efter ändringarna för att beräkna medelvärdet för resultatet.

## <a name="related-topics"></a>Relaterade ämnen

[Justera SharePoint onlineprestanda](tune-sharepoint-online-performance.md)

[Justera Office 365 prestanda](tune-microsoft-365-performance.md)

[Prestanda i den moderna SharePoint upplevelsen](/sharepoint/modern-experience-performance)

[Nätverk för innehållsleverans](content-delivery-networks.md)

[Använda Office 365 Content Delivery Network (CDN) med SharePoint Online](use-microsoft-365-cdn-with-spo.md)