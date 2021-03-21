---
title: Optimera sidsamtal i moderna och klassiska publiceringswebbplatssidor i SharePoint Online
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
ms.custom: Adm_O365
ms.reviewer: sstewart
search.appverid:
- MET150
description: Lär dig hur du optimerar moderna och klassiska publiceringswebbplatssidor i SharePoint Online genom att begränsa antalet samtal till SharePoint Online-tjänstslutpunkter.
ms.openlocfilehash: cab0f6a020bd1148a0e852b5a393a6ad907f9771
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921624"
---
# <a name="optimize-page-calls-in-sharepoint-online-modern-and-classic-publishing-site-pages"></a>Optimera sidsamtal i moderna och klassiska publiceringswebbplatssidor i SharePoint Online

Både moderna och klassiska publiceringswebbplatser i SharePoint Online innehåller länkar som laddar in data från (eller ringer samtal till) SharePoint-funktioner och CDN. Ju fler samtal en sida ringer, desto längre tid tar det att läsa in sidan. Detta kallas för att **slutanvändaren uppfattas som fördröjning** eller **EUPL.**

Den här artikeln hjälper dig att förstå hur du fastställer antal och påverkan på samtal till externa slutpunkter från dina moderna och klassiska publiceringswebbplatssidor och hur du kan begränsa effekten på slutanvändarens uppfattas svarstid.

>[!NOTE]
>Mer information om prestanda i moderna Portaler i SharePoint Online finns i [Prestanda i det moderna SharePoint-programmet.](/sharepoint/modern-experience-performance)

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-page-calls"></a>Använda siddiagnostik för SharePoint-verktyget för att analysera sidsamtal

Verktyget Siddiagnostik för SharePoint är ett webbläsartillägg för nya Microsoft Edge ( och Chrome-webbläsare som analyserar både moderna portaler för SharePoint Online och https://www.microsoft.com/edge) klassiska publiceringswebbplatssidor. Verktyget innehåller en rapport för varje analyserad sida som visar hur sidan fungerar mot en definierad uppsättning prestandavillkor. Om du vill installera och lära dig mer om verktyget Siddiagnostik för SharePoint går du [till Använda verktyget Siddiagnostik för SharePoint Online.](page-diagnostics-for-spo.md)

>[!NOTE]
>Verktyget Siddiagnostik fungerar bara för SharePoint Online och kan inte användas på en SharePoint-systemsida.

När du analyserar en SharePoint-webbplatssida med verktyget Siddiagnostik för SharePoint kan du se information om externa samtal i begäran om **SharePoint-resultat** i _fönstret Diagnostiktest._ Linjen visas i grönt om webbplatssidan innehåller färre än baslinjenumret och röd om sidan överskrider baslinjenumret. Baslinjenumret skiljer sig för moderna och klassiska sidor eftersom klassiska webbplatssidor använder HTTP1.1 och moderna sidor använder HTTP2.0:

- Moderna webbplatssidor får inte innehålla fler än **25** samtal
- Klassiska publiceringssidor får innehålla högst **6** samtal

Möjliga resultat är:

- **Obs!** Obligatoriskt (rött): Sidan överskrider baslinjenumret för samtal
- **Ingen åtgärd krävs** (grön): Sidan innehåller färre än originalantalet samtal

Om resultatet **Begäranden till SharePoint** visas i avsnittet Åtgärder som krävs kan du klicka på resultatet för mer information, inklusive det totala antalet samtal på sidan och en lista med URL-adresser. 

![Förfrågningar om SharePoint-resultat](../media/modern-portal-optimization/pagediag-requests.png)

## <a name="remediate-performance-issues-related-to-too-many-calls-on-a-page"></a>Åtgärda prestandaproblem som är relaterade till för många samtal på en sida

Om en sida innehåller för många samtal kan du använda listan med URL-adresser i Begäran om **SharePoint-resultat** för att avgöra om det finns några upprepade samtal, samtal som ska batchas eller samtal som returnerar data som ska cachelagras.

**Att batcha REST-samtal** kan minska prestandan. Mer information om API-anropsbatchning finns [i Göra batchbegäranden med REST-API:er.](/sharepoint/dev/sp-add-ins/make-batch-requests-with-the-rest-apis)

**Om du** använder en cache för att lagra resultaten av ett API-anrop kan du förbättra prestandan för en uppvärmningsbegäran genom att låta klienten använda cachelagrade data i stället för att ringa ytterligare ett samtal för varje efterföljande sidinläsning. Det finns flera sätt att hantera den här lösningen beroende på affärsbehovet. Vanligtvis om data är samma för alla användare är en cachelagringstjänst på mellannivå som [ _Azure Redis-cache_](https://azure.microsoft.com/services/cache/) ett bra alternativ för att avsevärt minska API-trafiken mot en webbplats eftersom användarna skulle begära data från cachelagringstjänsten i stället för direkt från SPO. De enda SPO-anrop som behövs är att uppdatera cachen på mittnivån. Om data fluktuerar för enskilda användare kan det vara bäst att implementera en klientbaserad cache, som LocalStorage eller till och med en cookie. Det här kommer fortfarande att minska samtalsvolymerna genom att du eliminerar efterföljande förfrågningar som görs av samma användare under cachelängden, men kommer att vara mindre effektivt än en dedikerad cachelagringstjänst. Med PnP kan du använda LocalStorage med lite ytterligare utveckling som krävs.

Innan du gör sidändringar för att åtgärda prestandaproblem bör du anteckna inläsningstiden för sidan i analysresultatet. Kör verktyget igen efter ändringen för att se om det nya resultatet ligger inom baslinjestandarden och kontrollera inläsningstiden för den nya sidan för att se om det finns en förbättring.

![Inläsningstid för sida](../media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
>Sidinläsningstiden kan variera beroende på en mängd faktorer, till exempel nätverksbelastning, tid på dagen och andra tillfälliga villkor. Du bör testa inläsningstiden några gånger före och efter ändringarna för att beräkna medelvärdet för resultatet.

## <a name="related-topics"></a>Relaterade ämnen

[Justera SharePoint Online-prestanda](tune-sharepoint-online-performance.md)

[Justera Office 365-prestanda](tune-microsoft-365-performance.md)

[Prestanda i det moderna SharePoint-programmet](/sharepoint/modern-experience-performance)

[Nätverk för innehållsleverans](content-delivery-networks.md)

[Använda Office 365 Content Delivery Network (CDN) med SharePoint Online](use-microsoft-365-cdn-with-spo.md)