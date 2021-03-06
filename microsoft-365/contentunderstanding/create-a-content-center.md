---
title: Skapa ett innehållscenter i Microsoft SharePoint Syntex
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Lär dig att skapa ett innehållscenter.
ms.openlocfilehash: 34ba45cd62214743e5a6784893e0f24e9815fdfb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905830"
---
# <a name="create-a-content-center-in-microsoft-sharepoint-syntex"></a>Skapa ett innehållscenter i Microsoft SharePoint Syntex


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CPSF]

</br>

Om du vill skapa och hantera modeller för dokumenttolkning måste du först ha ett innehållscenter. Innehållscentret är gränssnittet för skapande av modeller och innehåller även information om vilka dokumentbibliotek som publicerade modeller använts på.</br>

   ![Välj ett dokumentbibliotek](../media/content-understanding/content-center-page.png)</br>

Du skapar ett standardinnehållscenter under [konfiguration](set-up-content-understanding.md). Men en SharePoint-administratör kan också välja att skapa fler center efter behov. Även om det kan vara bra att skapa ett enda innehållscenter för miljöer där du vill samla alla modellaktiviteter kanske du vill ha ytterligare center för olika avdelningar i organisationen, som kan ha olika behov och behörighetskrav för sina modeller.

> [!NOTE]
> I en [Microsoft 365 Multi-Geo-miljö](../enterprise/microsoft-365-multi-geo.md)kan du, om du har ett enda standardinnehållscenter på den centrala platsen, endast tillhandahålla en sammanslagning av modellaktivitet från denna plats. För närvarande kan du inte få en sammanslagning av modellaktivitet över servergruppsgränser i Multi-Geo-miljö. 


## <a name="create-a-content-center"></a>Skapa ett innehållscenter

En SharePoint-administratör kan skapa en webbplats för innehållscentret precis som de [skapar andra SharePoint-webbplatser](/sharepoint/create-site-collection) via administrationscentrets panel för webbplatsetablering.

För att skapa ett nytt innehållscenter:

1. Gå till administrationscenter för SharePoint i administrationscenter för Microsoft 365.

2. I administrationscentret för SharePoint, under **Webbplatser**, väljer du **Aktiva webbplatser**.

3. På sidan **Aktiva webbplatser** klickar du på **Skapa** och väljer **Andra alternativ**.

4. Välj **Innehållscenter** i menyn **Välj en mall**.

5. Ange **Webbplatsnamn**, **primär administratör** och **Språk** för den nya webbplatsen.</br>

   > [!NOTE] 
   > Du kan välja en webbplats för innehållscenter i något av de tillgängliga språken, men observera att modeller för närvarande endast kan skapas för engelska filer. Observera också att precis som med andra webbplatsmallar kan standardwebbplatsens språk inte redigeras när webbplatsen har skapats.</br>

6. Välj **Färdig**.
 
När du har skapat en webbplats för innehållscentret visas den på sidan **Aktiva webbplatser** i administrationscenter för SharePoint. 

### <a name="give-access-to-additional-users"></a>Ge behörighet till ytterligare användare
 
När du har skapat webbplatsen kan du ge fler användare åtkomst till den via standard[modellen för SharePoint-webbplatsbehörigheter](/sharepoint/modern-experience-sharing-permissions).

## <a name="see-also"></a>Se även
[Skapa en klassificerare](create-a-classifier.md)

[Skapa en extraktor](create-an-extractor.md)

[Skapa ett innehållscenter](create-a-content-center.md)

[Översikt av dokumenttolkning](document-understanding-overview.md)

[Skapa en modell för formulärbearbetning](create-a-form-processing-model.md)

[Använda en modell](apply-a-model.md)