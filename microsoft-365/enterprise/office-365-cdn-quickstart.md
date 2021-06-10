---
title: Office 365 Content Delivery Network (CDN) Snabbstart
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/04/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
- m365initiative-coredeploy
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- SPO160
description: Office 365 Content Delivery Network (CDN) Snabbstart
ms.openlocfilehash: 3539ad1f11b27c60b5641976ae66a1480ef4be98
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921600"
---
# <a name="office-365-content-delivery-network-cdn-quickstart"></a>Office 365 Content Delivery Network (CDN) Snabbstart

Du kan använda de inbyggda **Office 365 Content Delivery Network (CDN)** för statiska tillgångar (bilder, JavaScript, Formatmallar, WOFF-filer) för att ge bättre prestanda för dina SharePoint Online-sidor. Med Office 365 CDN prestanda genom cachelagring av statiska tillgångar närmare de webbläsare som begär dem, vilket hjälper till att snabba på hämtningar och minska svarstiden. Dessutom Office 365 CDN HTTP/2-protokollet för förbättrad komprimering och HTTP-pipelining. Tjänsten Office 365 CDN ingår som en del av din prenumeration SharePoint Online.

Mer detaljerad information finns i [Använda Office 365 Content Delivery Network (CDN) med SharePoint Online.](use-microsoft-365-cdn-with-spo.md)

>[!NOTE]
>Data Office 365 CDN bara tillgänglig för klientorganisationen i produktionsmoln (globalt). Klientorganisationen i molnen för myndigheter i USA, Kina och Tyskland stöder för närvarande inte Office 365 CDN.

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-identify-items-not-in-cdn"></a>Använd siddiagnostikverktyget för SharePoint för att identifiera objekt som inte finns CDN

Du kan använda **Siddiagnostik** för SharePoint för webbläsaren för att enkelt visa tillgångar på dina SharePoint Online-sidor som kan läggas till i ett CDN ursprung.

**Siddiagnostik för SharePoint är** ett webbläsartillägg för nya Microsoft Edge ( och Chrome-webbläsare som analyserar både moderna SharePoint Online-portalen och klassiska https://www.microsoft.com/edge) publiceringswebbplatssidor. Verktyget innehåller en rapport för varje analyserad sida som visar hur sidan fungerar mot en definierad uppsättning prestandavillkor. Om du vill installera och lära dig mer SharePoint siddiagnostikverktyget går du till Använda [verktyget Siddiagnostik för SharePoint Online.](./page-diagnostics-for-spo.md)

När du kör siddiagnostik för SharePoint-verktyget på en SharePoint Online-sida  kan du klicka på fliken Diagnostiktest för att visa en lista över tillgångar som inte CDN. De här tillgångarna visas under rubriken för **Content Delivery Network (CDN) kontrollera** enligt skärmbilden nedan.

![Siddiagnostik](../media/page-diagnostics-for-spo/pagediag-results-general.PNG)

>[!NOTE]
>Verktyget Siddiagnostik fungerar bara för SharePoint Online och kan inte användas på en SharePoint systemsida.

## <a name="cdn-overview"></a>CDN Översikt

Programmet Office 365 CDN har utformats för att optimera prestanda för användare genom att distribuera objekt som används ofta, till exempel bilder och javascript, över ett globalt nätverk med hög hastighet, vilket minskar inläsningstiden för sidor och ger åtkomst till värdbaserade objekt så nära användaren som möjligt. Data CDN dina tillgångar från en plats som kallas för _ursprung_. Ursprunget kan vara en SharePoint, ett dokumentbibliotek eller en mapp som kan nås via en URL.

Datatyperna Office 365 CDN indelade i två grundläggande typer:

- **Den offentliga CDN** är utformad för att användas för JS (JavaScript), CSS (StyleSheets), Web Font File (WOFF, WOFF2) och icke-ägandeliknande bilder som företagslogotyp.
- **Den CDN** är utformad för att användas för bilder (PNG, JPG, JPEG osv.).

Du kan välja att ha både offentliga och privata ursprung för organisationen. De flesta organisationer väljer att implementera en kombination av de två. Både offentliga och privata alternativ ger liknande prestandaförbättringar, men var och en har unika attribut och fördelar. Mer information om offentliga och privata CDN ursprung finns i [Välja om varje ursprung ska vara offentligt eller privat.](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)

## <a name="how-to-enable-public-and-private-cdn-with-the-default-configuration"></a>Aktivera offentliga och privata CDN med standardkonfigurationen
Innan du ändrar klientorganisationens inställningar CDN du kontrollera att den uppfyller organisationens efterlevnads-, säkerhets- och sekretesspolicy.

Mer detaljerade konfigurationsinställningar, eller om du redan har aktiverat CDN och vill lägga till ytterligare platser (ursprung), finns i avsnittet Konfigurera och konfigurera Office 365 CDN med hjälp av [SharePoint Online Management Shell](use-microsoft-365-cdn-with-spo.md#set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell)

Anslut till klientorganisationen med hjälp SharePoint Online Management Shell:

```PowerShell
Connect-SPOService -Url https://<YourTenantName>-admin.sharepoint.com
```

Om du vill aktivera organisationen för att använda både offentliga och privata ursprung med standardkonfigurationen skriver du följande kommando:

```PowerShell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

Utdata från dessa cmdlets bör se ut så här:

![Utdata från Set-SPOTenantCdnEnabled](../media/O365-CDN/o365-cdn-enable-output.png)

## <a name="see-also"></a>Se även

[Använda verktyget Siddiagnostik för SharePoint Online](./page-diagnostics-for-spo.md)

[Använda Office 365 Content Delivery Network (CDN) med SharePoint Online](use-microsoft-365-cdn-with-spo.md)

[Nätverk för innehållsleverans (CDN)](./content-delivery-networks.md)

[Network planning and performance tuning for Office 365](./network-planning-and-performance.md)

[SharePoint Performance Series – Office 365 CDN videoserie](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)