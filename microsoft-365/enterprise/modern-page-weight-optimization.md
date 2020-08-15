---
title: Optimera sid tjock leken i sidor i SharePoint Online
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
description: Lär dig hur du kan använda verktyget för att optimera sid tjock leken i sidor med moderna webbplatser i SharePoint Online.
ms.openlocfilehash: 64fb3c90db78a23c7f1c3fcfe604c8ef58703be0
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694369"
---
# <a name="optimize-page-weight-in-sharepoint-online-modern-site-pages"></a>Optimera sid tjock leken i sidor i SharePoint Online

Moderna webbplats sidor för SharePoint Online innehåller serialiserad kod som krävs för att återge sidans innehåll, inklusive bilder, text, objekt i innehålls området under navigering/kommando fält och annan HTML-kod som utgör ramverket för sidan. Sid tjock leken är en mätning av den här HTML-koden och bör begränsas för att säkerställa optimal sid inläsnings tid.

Den här artikeln hjälper dig att förstå hur du kan minska sid tjock leken på dina sidor.

>[!NOTE]
>Mer information om prestanda i SharePoint Online-moderna portaler finns i [prestanda i den moderna SharePoint-upplevelsen](https://docs.microsoft.com/sharepoint/modern-experience-performance).

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-page-weight"></a>Använd verktyget för nätverksdiagnostik för SharePoint för att analysera sid tjock leken

Verktyget för nätverksdiagnostik för SharePoint är ett webb läsar tillägg för de nya Microsoft Edge- https://www.microsoft.com/edge) webbläsarna (och Chrome som analyserar både SharePoint Online moderna Portal och klassisk publicerings webbplats sidor. Verktyget visar en rapport för varje sida som visar hur sidan fungerar mot en viss uppsättning prestanda villkor. Om du vill installera och läsa mer om verktyget för nätverksdiagnostik för SharePoint kan du gå till [använda diagnostikverktyget för SharePoint Online](page-diagnostics-for-spo.md).

>[!NOTE]
>Verktyget för nätverksdiagnostik fungerar bara för SharePoint Online och kan inte användas på en SharePoint-Systemsida.

När du analyserar en SharePoint-webbplats med Page Diagnostics för SharePoint-verktyget kan du Visa information om sidan i **sid vikten under 500KB** resultat. _Diagnostic tests_ Resultatet visas i grönt om sid tjock leken är under bas linjens värde och sedan rött om sid bredden överskrider bas linjens värde.

Möjliga resultat:

- **Åtgärd krävs** (röd): sid bredden överskrider 500KB
- **Ingen åtgärd krävs** (grön): sid tjock leken är under 500KB

Om **sid tjock leken under 500KB** resultat visas i avsnittet **åtgärdat måste** du klicka på resultatet för mer information.

![Förfrågningar till SharePoint-resultat](../media/modern-portal-optimization/pagediag-page-weight.png)

## <a name="remediate-page-weight-issues"></a>Åtgärda problem med sidans vikt

Om sid tjock leken överskrider 500KB kan du förbättra den allmänna sid inläsnings tiden genom att minska antalet webb delar och begränsa sid innehållet till en lämplig grad.

Allmänna rikt linjer för att minska sid vikten inkluderar:

- Begränsa sid innehållet till ett rimligt belopp och Använd flera sidor för relaterat innehåll.
- Minimera användningen av webb delar som har stora egenskaps uppsättningar.
- Använd icke-interaktiva upplyft vy när så är möjligt.
- Optimera bild storlekarna genom att använda komprimerade bild format och se till att de hämtas från ett CDN.

Du hittar ytterligare vägledning om hur du begränsar sid tjock leken i följande artikel:

- [Optimera sid prestanda i SharePoint](https://docs.microsoft.com/sharepoint/dev/general-development/optimize-page-performance-in-sharepoint)

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
