---
title: Office 365 innehålls leverans nätverk (CDN) snabb start
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
- M365initiative-CoreDeploy
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- SPO160
description: Office 365 innehålls leverans nätverk (CDN) snabb start
ms.openlocfilehash: e9975721b5cfaaed2c9ad7562c47f12c7a5a5bc3
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326895"
---
# <a name="office-365-content-delivery-network-cdn-quickstart"></a>Office 365 innehålls leverans nätverk (CDN) snabb start

Du kan använda det inbyggda Office- **365 innehålls leverans nätverk (CDN)** för att hantera statiska till gångar (bilder, Java Script, formatmallar, WOFF-filer) för bättre prestanda för SharePoint Online-sidor. Office 365 CDN förbättrar prestandan genom att cachelagra statiska till gångar i webbläsare som begär dem, vilket hjälper dig att påskynda nedladdningen och minska svars tiden. Dessutom använder Office 365 CDN HTTP/2 för förbättrad komprimering och HTTP-försäljning. Office 365 CDN-tjänsten är inkluderad som en del av SharePoint Online-prenumerationen.

Mer detaljerad information finns i [använda Office 365 Content Delivery Network (CDN) med SharePoint Online](use-microsoft-365-cdn-with-spo.md).

>[!NOTE]
>Office 365 CDN är bara tillgängligt för klient organisationer i produktions-molnet (världen över). Klient organisationer i Förenta staternas myndigheter, Kina och Tyskland stöder för närvarande inte Office 365 CDN.

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-identify-items-not-in-cdn"></a>Använd verktyget för nätverksdiagnostik för SharePoint för att identifiera objekt som inte är i CDN

Du kan använda webb läsar tillägget **för** att enkelt Visa till gångar på SharePoint Online-sidor som kan läggas till i ett CDN-ursprung.

**Verktyget för nätverksdiagnostik för SharePoint** är ett webb läsar tillägg för de nya Microsoft Edge- https://www.microsoft.com/edge) webbläsarna (och Chrome som analyserar både SharePoint Online moderna Portal och klassisk publicerings webbplats sidor. Verktyget visar en rapport för varje sida som visar hur sidan fungerar mot en viss uppsättning prestanda villkor. Om du vill installera och läsa mer om verktyget för nätverksdiagnostik för SharePoint kan du gå till [använda diagnostikverktyget för SharePoint Online](https://aka.ms/perftool).

När du kör verktyget för nätverksdiagnostik för SharePoint på en SharePoint Online-sida kan du klicka på fliken **diagnostiska test** för att se en lista med till gångar som inte hanteras av CDN. Dessa till gångar visas under rubriken rubrik för **leverans av innehåll (CDN)** enligt skärm bilden nedan.

![Nätverksdiagnostik](../media/page-diagnostics-for-spo/pagediag-results-general.PNG)

>[!NOTE]
>Verktyget för nätverksdiagnostik fungerar bara för SharePoint Online och kan inte användas på en SharePoint-Systemsida.

## <a name="cdn-overview"></a>Översikt över CDN

Office 365 CDN är utformat för att optimera prestanda för användare genom att distribuera ofta använda objekt, till exempel bilder och JavaScript-filer via ett höghastighets-globalt nätverk, för att minska sid inläsnings tiden och ge till gång till värdbaserat objekt så nära som möjligt för användaren. CDN hämtar dina till gångar från en plats som kallas _ursprung_. Ett ursprung kan vara en SharePoint-webbplats, ett dokument bibliotek eller en mapp som är tillgänglig via en URL-adress.

Office 365 CDN är indelat i två grundläggande typer:

- **Offentlig CDN** är utformat för att användas för JS (Java Script), CSS (formatmallar), webb teckensnitt (WOFF, WOFF2) och icke-patentskyddade bilder, till exempel företags logo typer.
- **Privata CDN** är utformat för bilder (png, jpg, JPEG etc.).

Du kan välja att ha både offentliga eller privata ursprung för organisationen. De flesta organisationer väljer att implementera en kombination av båda. Både offentliga och privata alternativ ger liknande prestanda vinster men alla har unika attribut och fördelar. Få reda på mer om offentliga och privata CDN-ursprung i [välja om varje ursprung ska vara offentlig eller privat](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate).

## <a name="how-to-enable-public-and-private-cdn-with-the-default-configuration"></a>Så här aktiverar du public och Private CDN med standard konfigurationen
Innan du gör ändringar i inställningarna för klient-CDN bör du kontrol lera att de uppfyller organisationens efterlevnad, säkerhet och sekretess policy.

Om du vill ha mer detaljerade konfigurations inställningar, eller om du redan har aktiverat CDN och vill lägga till ytterligare platser, kan du läsa avsnittet Konfigurera [och konfigurera Office 365 CDn genom att använda SharePoint Online Management Shell](use-microsoft-365-cdn-with-spo.md#set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell)

Anslut till klient organisationen med SharePoint Online Management Shell:

```PowerShell
Connect-SPOService -Url https://<YourTenantName>-admin.sharepoint.com
```

Om du vill aktivera organisationen att använda både offentliga och privata ursprung med standard konfigurationen skriver du följande kommando:

```PowerShell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

Utdata från dessa cmdletar bör se ut så här:

![Utdata av Set-SPOTenantCdnEnabled](../media/O365-CDN/o365-cdn-enable-output.png)

## <a name="see-also"></a>Se även

[Använda verktyget för nätverksdiagnostik för SharePoint Online](https://aka.ms/perftool)

[Använda Office 365-innehålls leverans nätverk (CDN) med SharePoint Online](use-microsoft-365-cdn-with-spo.md)

[Nätverk för innehållsleverans (CDN)](https://aka.ms/o365cdns)

[Network planning and performance tuning for Office 365](https://aka.ms/tune)

[SharePoint-prestandaräknare – Office 365 CDN-videoserie](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)
