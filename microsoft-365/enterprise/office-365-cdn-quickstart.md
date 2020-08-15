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
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- SPO160
description: Office 365 innehålls leverans nätverk (CDN) snabb start
ms.openlocfilehash: 8a8152c749306ed5247e92d4bc2c6a58e7a1c6cd
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46696666"
---
# <a name="office-365-content-delivery-network-cdn-quickstart"></a><span data-ttu-id="8a68b-103">Office 365 innehålls leverans nätverk (CDN) snabb start</span><span class="sxs-lookup"><span data-stu-id="8a68b-103">Office 365 Content Delivery Network (CDN) Quickstart</span></span>

<span data-ttu-id="8a68b-104">Du kan använda det inbyggda Office- **365 innehålls leverans nätverk (CDN)** för att hantera statiska till gångar (bilder, Java Script, formatmallar, WOFF-filer) för bättre prestanda för SharePoint Online-sidor.</span><span class="sxs-lookup"><span data-stu-id="8a68b-104">You can use the built-in **Office 365 Content Delivery Network (CDN)** to host static assets (images, JavaScript, Stylesheets, WOFF files) to provide better performance for your SharePoint Online pages.</span></span> <span data-ttu-id="8a68b-105">Office 365 CDN förbättrar prestandan genom att cachelagra statiska till gångar i webbläsare som begär dem, vilket hjälper dig att påskynda nedladdningen och minska svars tiden.</span><span class="sxs-lookup"><span data-stu-id="8a68b-105">The Office 365 CDN improves performance by caching static assets closer to the browsers requesting them, which helps to speed up downloads and reduce latency.</span></span> <span data-ttu-id="8a68b-106">Dessutom använder Office 365 CDN HTTP/2 för förbättrad komprimering och HTTP-försäljning.</span><span class="sxs-lookup"><span data-stu-id="8a68b-106">Also, the Office 365 CDN uses the HTTP/2 protocol for improved compression and HTTP pipelining.</span></span> <span data-ttu-id="8a68b-107">Office 365 CDN-tjänsten är inkluderad som en del av SharePoint Online-prenumerationen.</span><span class="sxs-lookup"><span data-stu-id="8a68b-107">The Office 365 CDN service is included as part of your SharePoint Online subscription.</span></span>

<span data-ttu-id="8a68b-108">Mer detaljerad information finns i [använda Office 365 Content Delivery Network (CDN) med SharePoint Online](use-microsoft-365-cdn-with-spo.md).</span><span class="sxs-lookup"><span data-stu-id="8a68b-108">For more detailed information guidance see [Use the Office 365 Content Delivery Network (CDN) with SharePoint Online](use-microsoft-365-cdn-with-spo.md).</span></span>

>[!NOTE]
><span data-ttu-id="8a68b-109">Office 365 CDN är bara tillgängligt för klient organisationer i produktions-molnet (världen över).</span><span class="sxs-lookup"><span data-stu-id="8a68b-109">The Office 365 CDN is only available to tenants in the production (worldwide) cloud.</span></span> <span data-ttu-id="8a68b-110">Klient organisationer i Förenta staternas myndigheter, Kina och Tyskland stöder för närvarande inte Office 365 CDN.</span><span class="sxs-lookup"><span data-stu-id="8a68b-110">Tenants in the US Government, China and Germany clouds do not currently support the Office 365 CDN.</span></span>

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-identify-items-not-in-cdn"></a><span data-ttu-id="8a68b-111">Använd verktyget för nätverksdiagnostik för SharePoint för att identifiera objekt som inte är i CDN</span><span class="sxs-lookup"><span data-stu-id="8a68b-111">Use the Page Diagnostics for SharePoint tool to identify items not in CDN</span></span>

<span data-ttu-id="8a68b-112">Du kan använda webb läsar tillägget **för** att enkelt Visa till gångar på SharePoint Online-sidor som kan läggas till i ett CDN-ursprung.</span><span class="sxs-lookup"><span data-stu-id="8a68b-112">You can use the **Page Diagnostics for SharePoint tool** browser extension to easily list assets in your SharePoint Online pages that can be added to a CDN origin.</span></span>

<span data-ttu-id="8a68b-113">**Verktyget för nätverksdiagnostik för SharePoint** är ett webb läsar tillägg för de nya Microsoft Edge- https://www.microsoft.com/edge) webbläsarna (och Chrome som analyserar både SharePoint Online moderna Portal och klassisk publicerings webbplats sidor.</span><span class="sxs-lookup"><span data-stu-id="8a68b-113">The **Page Diagnostics for SharePoint tool** is a browser extension for the new Microsoft Edge (https://www.microsoft.com/edge) and Chrome browsers that analyzes both SharePoint Online modern portal and classic publishing site pages.</span></span> <span data-ttu-id="8a68b-114">Verktyget visar en rapport för varje sida som visar hur sidan fungerar mot en viss uppsättning prestanda villkor.</span><span class="sxs-lookup"><span data-stu-id="8a68b-114">The tool provides a report for each analyzed page showing how the page performs against a defined set of performance criteria.</span></span> <span data-ttu-id="8a68b-115">Om du vill installera och läsa mer om verktyget för nätverksdiagnostik för SharePoint kan du gå till [använda diagnostikverktyget för SharePoint Online](https://aka.ms/perftool).</span><span class="sxs-lookup"><span data-stu-id="8a68b-115">To install and learn about the Page Diagnostics for SharePoint tool, visit [Use the Page Diagnostics tool for SharePoint Online](https://aka.ms/perftool).</span></span>

<span data-ttu-id="8a68b-116">När du kör verktyget för nätverksdiagnostik för SharePoint på en SharePoint Online-sida kan du klicka på fliken **diagnostiska test** för att se en lista med till gångar som inte hanteras av CDN.</span><span class="sxs-lookup"><span data-stu-id="8a68b-116">When you run the Page Diagnostics for SharePoint tool on a SharePoint Online page, you can click the **Diagnostic Tests** tab to see a list of assets not being hosted by the CDN.</span></span> <span data-ttu-id="8a68b-117">Dessa till gångar visas under rubriken rubrik för **leverans av innehåll (CDN)** enligt skärm bilden nedan.</span><span class="sxs-lookup"><span data-stu-id="8a68b-117">These assets will be listed under the heading **Content Delivery Network (CDN) check** as shown in the screenshot below.</span></span>

![Nätverksdiagnostik](../media/page-diagnostics-for-spo/pagediag-results-general.PNG)

>[!NOTE]
><span data-ttu-id="8a68b-119">Verktyget för nätverksdiagnostik fungerar bara för SharePoint Online och kan inte användas på en SharePoint-Systemsida.</span><span class="sxs-lookup"><span data-stu-id="8a68b-119">The Page Diagnostics tool only works for SharePoint Online, and cannot be used on a SharePoint system page.</span></span>

## <a name="cdn-overview"></a><span data-ttu-id="8a68b-120">Översikt över CDN</span><span class="sxs-lookup"><span data-stu-id="8a68b-120">CDN Overview</span></span>

<span data-ttu-id="8a68b-121">Office 365 CDN är utformat för att optimera prestanda för användare genom att distribuera ofta använda objekt, till exempel bilder och JavaScript-filer via ett höghastighets-globalt nätverk, för att minska sid inläsnings tiden och ge till gång till värdbaserat objekt så nära som möjligt för användaren.</span><span class="sxs-lookup"><span data-stu-id="8a68b-121">The Office 365 CDN is designed to optimize performance for users by distributing frequently accessed objects like images and javascript files over a high-speed global network, reducing page load time and providing access to hosted objects as close as possible to the user.</span></span> <span data-ttu-id="8a68b-122">CDN hämtar dina till gångar från en plats som kallas _ursprung_.</span><span class="sxs-lookup"><span data-stu-id="8a68b-122">The CDN fetches your assets from a location called an _origin_.</span></span> <span data-ttu-id="8a68b-123">Ett ursprung kan vara en SharePoint-webbplats, ett dokument bibliotek eller en mapp som är tillgänglig via en URL-adress.</span><span class="sxs-lookup"><span data-stu-id="8a68b-123">An origin can be a SharePoint site, document library or folder that is accessible by a URL.</span></span>

<span data-ttu-id="8a68b-124">Office 365 CDN är indelat i två grundläggande typer:</span><span class="sxs-lookup"><span data-stu-id="8a68b-124">The Office 365 CDN is separated into two basic types:</span></span>

- <span data-ttu-id="8a68b-125">**Offentlig CDN** är utformat för att användas för JS (Java Script), CSS (formatmallar), webb teckensnitt (WOFF, WOFF2) och icke-patentskyddade bilder, till exempel företags logo typer.</span><span class="sxs-lookup"><span data-stu-id="8a68b-125">**Public CDN** is designed to be used for JS (JavaScript), CSS (StyleSheets), Web Font File (WOFF, WOFF2) and non-proprietary images like company logos.</span></span>
- <span data-ttu-id="8a68b-126">**Privata CDN** är utformat för bilder (png, jpg, JPEG etc.).</span><span class="sxs-lookup"><span data-stu-id="8a68b-126">**Private CDN** is designed to be used for images (PNG, JPG, JPEG, etc.).</span></span>

<span data-ttu-id="8a68b-127">Du kan välja att ha både offentliga eller privata ursprung för organisationen.</span><span class="sxs-lookup"><span data-stu-id="8a68b-127">You can choose to have both public or private origins for your organization.</span></span> <span data-ttu-id="8a68b-128">De flesta organisationer väljer att implementera en kombination av båda.</span><span class="sxs-lookup"><span data-stu-id="8a68b-128">Most organizations will choose to implement a combination of the two.</span></span> <span data-ttu-id="8a68b-129">Både offentliga och privata alternativ ger liknande prestanda vinster men alla har unika attribut och fördelar.</span><span class="sxs-lookup"><span data-stu-id="8a68b-129">Both public and private options provide similar performance gains, but each has unique attributes and advantages.</span></span> <span data-ttu-id="8a68b-130">Få reda på mer om offentliga och privata CDN-ursprung i [välja om varje ursprung ska vara offentlig eller privat](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate).</span><span class="sxs-lookup"><span data-stu-id="8a68b-130">For more information about public and private CDN origins, see [Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate).</span></span>

## <a name="how-to-enable-public-and-private-cdn-with-the-default-configuration"></a><span data-ttu-id="8a68b-131">Så här aktiverar du public och Private CDN med standard konfigurationen</span><span class="sxs-lookup"><span data-stu-id="8a68b-131">How to enable Public and Private CDN with the default configuration</span></span>
<span data-ttu-id="8a68b-132">Innan du gör ändringar i inställningarna för klient-CDN bör du kontrol lera att de uppfyller organisationens efterlevnad, säkerhet och sekretess policy.</span><span class="sxs-lookup"><span data-stu-id="8a68b-132">Before you make changes to the tenant CDN settings, you should verify that it meets compliance, security and privacy policies of your organization.</span></span>

<span data-ttu-id="8a68b-133">Om du vill ha mer detaljerade konfigurations inställningar, eller om du redan har aktiverat CDN och vill lägga till ytterligare platser, kan du läsa avsnittet Konfigurera [och konfigurera Office 365 CDn genom att använda SharePoint Online Management Shell](use-microsoft-365-cdn-with-spo.md#set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell)</span><span class="sxs-lookup"><span data-stu-id="8a68b-133">For more detailed configuration settings, or if you have already enabled CDN and want to add additional locations (origins), please see the section [Set up and configure the Office 365 CDN by using the SharePoint Online Management Shell](use-microsoft-365-cdn-with-spo.md#set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell)</span></span>

<span data-ttu-id="8a68b-134">Anslut till klient organisationen med SharePoint Online Management Shell:</span><span class="sxs-lookup"><span data-stu-id="8a68b-134">Connect to your tenant using the SharePoint Online Management Shell:</span></span>

```PowerShell
Connect-SPOService -Url https://<YourTenantName>-admin.sharepoint.com
```

<span data-ttu-id="8a68b-135">Om du vill aktivera organisationen att använda både offentliga och privata ursprung med standard konfigurationen skriver du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="8a68b-135">To enable your organization to use both public and private origins with the default configuration, type the following command:</span></span>

```PowerShell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

<span data-ttu-id="8a68b-136">Utdata från dessa cmdletar bör se ut så här:</span><span class="sxs-lookup"><span data-stu-id="8a68b-136">Output of these cmdlets should look like the following:</span></span>

![Utdata av Set-SPOTenantCdnEnabled](../media/O365-CDN/o365-cdn-enable-output.png)

## <a name="see-also"></a><span data-ttu-id="8a68b-138">Se även</span><span class="sxs-lookup"><span data-stu-id="8a68b-138">See also</span></span>

[<span data-ttu-id="8a68b-139">Använda verktyget för nätverksdiagnostik för SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="8a68b-139">Use the Page Diagnostics tool for SharePoint Online</span></span>](https://aka.ms/perftool)

[<span data-ttu-id="8a68b-140">Använda Office 365-innehålls leverans nätverk (CDN) med SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="8a68b-140">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)

[<span data-ttu-id="8a68b-141">Nätverk för innehålls leverans</span><span class="sxs-lookup"><span data-stu-id="8a68b-141">Content Delivery Networks</span></span>](https://aka.ms/o365cdns)

[<span data-ttu-id="8a68b-142">Network planning and performance tuning for Office 365</span><span class="sxs-lookup"><span data-stu-id="8a68b-142">Network planning and performance tuning for Office 365</span></span>](https://aka.ms/tune)

[<span data-ttu-id="8a68b-143">SharePoint-prestandaräknare – Office 365 CDN-videoserie</span><span class="sxs-lookup"><span data-stu-id="8a68b-143">SharePoint Performance Series - Office 365 CDN video series</span></span>](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)
