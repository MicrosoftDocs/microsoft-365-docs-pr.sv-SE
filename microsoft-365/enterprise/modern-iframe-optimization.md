---
title: Optimera iFrames i SharePoint moderna och klassiska publiceringswebbplatssidor
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
description: Lär dig hur du optimerar prestanda för iFrames i SharePoint moderna och klassiska publiceringswebbplatssidor.
ms.openlocfilehash: d6e9aefa23972589c752540959b17f5d20ed0889
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923070"
---
# <a name="optimize-iframes-in-sharepoint-online-modern-and-classic-publishing-site-pages"></a>Optimera iFrames i SharePoint moderna och klassiska publiceringswebbplatssidor

iFrames kan vara användbart för att förhandsgranska innehållsrika innehåll som videor eller andra media. Men eftersom iFrames läser in en separat sida inom sidan SharePoint-webbplatsen kan innehåll som läses in i iFrame innehålla stora bilder, videor eller andra element som kan bidra till inläsningstider för sidan och som du inte kan styra över på sidan. Den här artikeln hjälper dig att förstå hur iFrames på sidorna påverkar användarens uppfattas fördröjning och hur du åtgärdar vanliga problem.

>[!NOTE]
>Mer information om prestanda i SharePoint moderna webbplatser online finns i [Prestanda i det moderna SharePoint upplevelsen.](/sharepoint/modern-experience-performance)

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-web-parts-using-iframes"></a>Använd Siddiagnostik för SharePoint för att analysera webbdelar med iFrames

Siddiagnostik för SharePoint är ett webbläsartillägg för nya Microsoft Edge ( och Chrome-webbläsare som analyserar både moderna SharePoint Online-portalen och klassiska https://www.microsoft.com/edge) publiceringswebbplatssidor. Verktyget innehåller en rapport för varje analyserad sida som visar hur sidan fungerar mot en definierad uppsättning prestandavillkor. Om du vill installera och lära dig mer SharePoint siddiagnostikverktyget går du till Använda [verktyget Siddiagnostik för SharePoint Online.](page-diagnostics-for-spo.md)

>[!NOTE]
>Verktyget Siddiagnostik fungerar bara för SharePoint Online och kan inte användas på en SharePoint systemsida.

När du analyserar SharePoint webbplatssida med verktyget Siddiagnostik för SharePoint kan du se information om webbdelar som innehåller iFrames i _fönstret Diagnostiktest._ Baslinjemåttet är detsamma för moderna och klassiska sidor.

Möjliga resultat är:

- **Obs!** (röd): Sidan innehåller tre **eller fler webbdelar** med iFrames
- **Förbättringsmöjligheter** (gul): Sidan innehåller **en eller två webbdelar** med iFrames
- **Ingen åtgärd krävs** (grön): Sidan innehåller inga webbdelar med iFrames

Om de webbdelar som använder **iFrames**  upptäckta resultat visas i antingen resultatavsnittet Förbättringsmöjligheter eller Åtgärder **krävs)** kan du klicka på resultatet för att se de webbdelar som innehåller iFrames.

![Resultat av verktyget Siddiagnostik](../media/modern-portal-optimization/pagediag-iframe-yellow.png)

## <a name="remediate-iframe-performance-issues"></a>Åtgärda prestandaproblem i iFrame

Använda **webbdelarna med iFrames** upptäckt resultat i verktyget Siddiagnostik för att avgöra vilka webbdelar som innehåller iFrames och kan bidra till långsam sidinläsning.

iFrames är mycket långsamt eftersom de läser in en separat extern sida med allt associerat innehåll, till exempel javascript, CSS och framework-element, som potentiellt ökar kostnaderna för webbplatsens sida av en faktor för två eller fler.

Följ vägledning nedan för optimal användning av iFrames.

- Använd bilder i stället för iFrames om förhandsgranskningen är liten att börja med eller icke-interaktiva.
- Om iFrames måste användas minimerar du numret och/eller flyttar dem från visningsområdet.
- Inbäddade Office filer som Word, Excel och PowerPoint är interaktiva, men tar lång tid att läsa in. Miniatyrbilder med en länk till det fullständiga dokumentet fungerar ofta bättre.
- Inbäddade YouTube-videor och Twitter-feeds presterar ofta bättre i iFrames, men använder dessa typer av inbäddningar på ett bra sätt.
- Isolerade webbdelar är ett rimligt undantag, men minimera deras nummer och placering i visningsområdet.
- Om en iFrame är placerad utanför visningsområdet kan du använda en _IntersectionObserver_ för att fördröja rendering av iFrame tills den visas.

Innan du gör sidändringar för att åtgärda prestandaproblem bör du anteckna inläsningstiden för sidan i analysresultatet. Kör verktyget igen efter ändringen för att se om det nya resultatet ligger inom baslinjestandarden och kontrollera inläsningstiden för den nya sidan för att se om det finns en förbättring.

![Inläsningstid för sida](../media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
>Sidinläsningstiden kan variera beroende på en mängd faktorer, till exempel nätverksbelastning, tid på dagen och andra tillfälliga villkor. Du bör testa inläsningstiden några gånger före och efter ändringarna för att beräkna medelvärdet för resultatet.

## <a name="related-topics"></a>Relaterade ämnen

[Justera SharePoint onlineprestanda](tune-sharepoint-online-performance.md)

[Justera Office 365 prestanda](tune-microsoft-365-performance.md)

[Prestanda i den moderna SharePoint upplevelsen](/sharepoint/modern-experience-performance)