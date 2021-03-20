---
title: Optimera sid vikt i moderna webbplatssidor i SharePoint Online
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
description: Lär dig hur du använder verktyget Siddiagnostik för att optimera sidvikten på sidor med modern webbplats i SharePoint Online.
ms.openlocfilehash: 780d8ca0debbc5efb834f8f3543b9a5a8d168108
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907450"
---
# <a name="optimize-page-weight-in-sharepoint-online-modern-site-pages"></a>Optimera sid vikt i moderna webbplatssidor i SharePoint Online

SharePoint Online moderna webbplatssidor innehåller serialiserad kod som krävs för att återge sidans innehåll, inklusive bilder, text, objekt i innehållsområdet under navigerings-/kommandofält och annan HTML-kod som utgör ramen för sidan. Sidvikt är ett mått på den här HTML-koden och bör vara begränsat för optimala inläsningstider för sidor.

Den här artikeln hjälper dig att förstå hur du minskar sidvikten på moderna webbplatssidor.

>[!NOTE]
>Mer information om prestanda i moderna Portaler i SharePoint Online finns i [Prestanda i det moderna SharePoint-programmet.](/sharepoint/modern-experience-performance)

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-page-weight"></a>Använda verktyget Siddiagnostik för SharePoint för att analysera sidvikt

Verktyget Siddiagnostik för SharePoint är ett webbläsartillägg för nya Microsoft Edge ( och Chrome-webbläsare som analyserar både moderna portaler för SharePoint Online och https://www.microsoft.com/edge) klassiska publiceringswebbplatssidor. Verktyget innehåller en rapport för varje analyserad sida som visar hur sidan fungerar mot en definierad uppsättning prestandavillkor. Om du vill installera och lära dig mer om verktyget Siddiagnostik för SharePoint går du [till Använda verktyget Siddiagnostik för SharePoint Online.](page-diagnostics-for-spo.md)

>[!NOTE]
>Verktyget Siddiagnostik fungerar bara för SharePoint Online och kan inte användas på en SharePoint-systemsida.

När du analyserar en SharePoint-webbplatssida med siddiagnostik för SharePoint-verktyget kan du se information om sidan i sidvikten **under 500 kB** resultatet av fönstret _Diagnostiktest._ Resultatet visas i grönt om sidvikten är under baslinjevärdet och röd om sidvikten överskrider baslinjevärdet.

Möjliga resultat är:

- **Obs!** Krävs (rött): Sid vikt överskrider 500 KB
- **Ingen åtgärd krävs** (grön): Sidvikt är under 500 KB

Om **Sidvikt under 500 kB visas** i avsnittet Åtgärder **krävs** kan du klicka på resultatet för mer information.

![Förfrågningar om SharePoint-resultat](../media/modern-portal-optimization/pagediag-page-weight.png)

## <a name="remediate-page-weight-issues"></a>Åtgärda problem med sidvikt

Om sidvikten överskrider 500 KB kan du förbättra inläsningstiden för den övergripande sidan genom att minska antalet webbdelar och begränsa sidinnehållet till lämplig grad.

Allmän vägledning för att minska sidvikten omfattar:

- Begränsa sidinnehållet till ett rimligt belopp och använd flera sidor för relaterat innehåll.
- Minimera användningen av webbdelar som har stora egenskapsskatter.
- Använd icke-interaktiva uppslagsvyer när det är möjligt.
- Optimera bildstorlekar genom att ändra storlek på bilderna på ett lämpligt sätt, med komprimerat bildformat och se till att de laddas ned från ett CDN.

Ytterligare anvisningar om hur du begränsar sidvikten finns i följande artikel:

- [Optimera sidprestanda i SharePoint](/sharepoint/dev/general-development/optimize-page-performance-in-sharepoint)

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