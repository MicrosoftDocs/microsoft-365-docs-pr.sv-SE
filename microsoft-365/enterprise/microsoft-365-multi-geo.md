---
title: Microsoft 365 Multi-Geo
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.custom: seo-marvel-apr2020
ms.collection: Strat_SP_gtc
localization_priority: Normal
f1.keywords:
- NOCSH
description: I den här artikeln får du lära dig hur du utökar Microsoft 365-närvaron till flera geografiska områden med Microsoft 365 Multi-Geo.
ms.openlocfilehash: 2805470f1a35bb5978f3d25c30aa07523ad21afb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909556"
---
# <a name="microsoft-365-multi-geo"></a>Microsoft 365 Multi-Geo

Med Microsoft 365 Multi-Geo kan organisationen utöka sin Microsoft 365-närvaro till flera geografiska regioner och/eller länder inom din befintliga klientorganisation. Kontakta ditt Microsoft-kontoteam och registrera ditt Multi-National Company för Microsoft 365 Multi-Geo.
  
Med Microsoft 365 Multi-Geo kan du tillhandahålla och lagra data i vila på de geoplatser som du har valt att uppfylla krav för datalagring och samtidigt låsa upp den globala delen av den moderna produktivitetsupplevelsen för arbetsstyrkan.

En videointroduktion till Microsoft 365 Multi-Geo finns i SharePoint Online och [OneDrive Multi-Geo](https://www.youtube.com/watch?v=Do9U3JuROhk)där du kan styra var dina data finns.

## <a name="multi-geo-architecture"></a>Multi-Geo-arkitektur

I en Multi-Geo-miljö består Microsoft 365-klientorganisationen av en central plats (där Microsoft 365-prenumerationen ursprungligen skapades) och en eller flera satellitplatser. I en flera geoklienter kan du hantera information om geografiska platser, grupper och användarinformation i Azure Active Directory (Azure AD). Eftersom din information om klientorganisationen är centraliserad och synkroniserad till varje geoplats, delning och upplevelser som innefattar alla på ditt företag är globala medvetenheten.

![Skärmbild av en multigeokarta från administrationscentret för SharePoint](../media/multi-geo-world-map.png)

Observera att Microsoft 365 Multi-Geo inte är avsett för prestandaoptimering, utan har utformats för att uppfylla krav på datalagring. Mer information om prestandaoptimering för Microsoft 365 finns i Nätverksplanering och prestandajustering för [Microsoft 365](https://support.office.com/article/e5f1228c-da3c-4654-bf16-d163daee8848) eller kontakta supportgruppen.

## <a name="terminology"></a>Terminologi

Här är de viktigaste termer som används i beskrivningen av Microsoft 365 Multi-Geo:

- **Central plats** – den geoplats där klientorganisationen ursprungligen skapades.
- **Geoadministratör** – En administratör som kan administrera en eller flera angivna satellitplatser.
- **Geokod** – en kod på tre bokstäver för en viss geoplats.
- **Geoplats** – En geografisk plats som kan användas i en geoklient för flera platser för att lagra data, inklusive Exchange-postlådor och OneDrive- och SharePoint-webbplatser.
- **Önskad dataplats (PDL) –** En användaregenskap som anges av administratören som anger var den geoplats där användarnas Exchange-postlåda och OneDrive ska etableras. PDL avgör också var SharePoint-webbplatser som skapas av användaren etableras.
- **Satellitplats** – De geoplatser där Microsoft 365-arbetsbelastningen (SharePoint, OneDrive och Exchange) är aktiverade i en multigeoklient.
- **Klientorganisation** – En organisations representation i Microsoft 365 som normalt har en eller flera domäner kopplade till den (till exempel contoso.com).

## <a name="licensing"></a>Licensiering

Microsoft 365 Multi-Geo är tillgänglig som ett tillägg till följande Microsoft 365-abonnemang för Enterprise Agreement-kunder med minst 250 Microsoft 365-platser i klientorganisationen och minst 5 % av dessa platser med multi-geo. Användarprenumerationslicenser måste ha samma Enterprise-avtal som multi-geo services-licenser. Kontakta ditt Microsoft-kontoteam om du vill ha mer information.

- Microsoft 365 F1, F3, E3 eller E5
- Office 365 F3, E1, E3 eller E5
- Exchange Online, abonnemang 1 eller abonnemang 2
- OneDrive för företag-abonnemang 1 eller abonnemang 2
- SharePoint Online (abonnemang 1 eller abonnemang 2)

## <a name="microsoft-365-multi-geo-availability"></a>Microsoft 365 Multi-Geo-tillgänglighet

Microsoft 365 Multi-Geo erbjuds för närvarande i dessa regioner och länder:

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

## <a name="getting-started"></a>Komma igång

Följ de här anvisningarna för att komma igång med multi-geo:

1. Arbeta med kontoteamet och lägg till _Multi-Geo Capabilities i Microsoft 365-tjänstabonnemanget._ Du får hjälp med att lägga till det antal licenser som behövs. Multi-Geo-funktionen är tillgänglig för EA-kunder med minst 250 Microsoft 365-prenumerationer.

   Innan du kan börja använda Microsoft 365 Multi-Geo måste Microsoft konfigurera Exchange Online-klienten för multi-geo support. Den här konfigurationen krävs en gång när du beställer *Multi-Geo Capabilities i Microsoft 365-tjänstabonnemanget* och licenserna visas i din klientorganisation. Du får meddelanden om arbetsbelastningsspecifika meddelanden i [Microsoft 365-meddelandecentret](https://support.office.com/article/38FB3333-BFCC-4340-A37B-DEDA509C2093) när klientorganisationen har slutfört konfigurationsprocessen för varje arbetsbelastning, och sedan kan du börja konfigurera och använda dina Microsoft 365 Multi-Geo-funktioner. Tiden som krävs för att konfigurera en klientorganisation för Multi-Geo-support varierar från klientorganisation till klientorganisation, men de flesta klientorganisationen slutförs inom en månad efter att du fått funktionslicenserna. Större eller mer komplexa klientorganisationen kan behöva mer tid för att slutföra konfigurationsprocessen. Kontakta ditt kontoteam för mer information om din specifika klientorganisation om du skulle behöva den.

2. Läs [Planera din multigeobaserade miljö](plan-for-multi-geo.md).

3. Lär dig [hur du administrerar en miljö med flera](administering-a-multi-geo-environment.md) geografiska miljöer och hur användarna upplever [miljön.](multi-geo-user-experience.md)

4. När du är redo att konfigurera Microsoft 365 Multi-Geo konfigurerar [du klientorganisationen för multi-geo.](multi-geo-tenant-configuration.md)

5. [Konfigurera sökning](configure-search-for-multi-geo.md).

## <a name="see-also"></a>Se även

[Multi-Geo i Exchange Online och OneDrive](https://Aka.ms/GoMultiGeo)

[Multi-Geo Capabilities i OneDrive och SharePoint Online](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)

[Multi-Geo Capabilities i Exchange Online](multi-geo-capabilities-in-exchange-online.md)

[Teams-upplevelse i en geomiljö med flera miljöer](/microsoftteams/teams-experience-o365odb-spo-multi-geo)