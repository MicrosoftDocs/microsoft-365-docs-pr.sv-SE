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
# <a name="office-365-content-delivery-network-cdn-quickstart"></a><span data-ttu-id="5ccc9-103">Office 365 Content Delivery Network (CDN) Snabbstart</span><span class="sxs-lookup"><span data-stu-id="5ccc9-103">Office 365 Content Delivery Network (CDN) Quickstart</span></span>

<span data-ttu-id="5ccc9-104">Du kan använda de inbyggda **Office 365 Content Delivery Network (CDN)** för statiska tillgångar (bilder, JavaScript, Formatmallar, WOFF-filer) för att ge bättre prestanda för dina SharePoint Online-sidor.</span><span class="sxs-lookup"><span data-stu-id="5ccc9-104">You can use the built-in **Office 365 Content Delivery Network (CDN)** to host static assets (images, JavaScript, Stylesheets, WOFF files) to provide better performance for your SharePoint Online pages.</span></span> <span data-ttu-id="5ccc9-105">Med Office 365 CDN prestanda genom cachelagring av statiska tillgångar närmare de webbläsare som begär dem, vilket hjälper till att snabba på hämtningar och minska svarstiden.</span><span class="sxs-lookup"><span data-stu-id="5ccc9-105">The Office 365 CDN improves performance by caching static assets closer to the browsers requesting them, which helps to speed up downloads and reduce latency.</span></span> <span data-ttu-id="5ccc9-106">Dessutom Office 365 CDN HTTP/2-protokollet för förbättrad komprimering och HTTP-pipelining.</span><span class="sxs-lookup"><span data-stu-id="5ccc9-106">Also, the Office 365 CDN uses the HTTP/2 protocol for improved compression and HTTP pipelining.</span></span> <span data-ttu-id="5ccc9-107">Tjänsten Office 365 CDN ingår som en del av din prenumeration SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="5ccc9-107">The Office 365 CDN service is included as part of your SharePoint Online subscription.</span></span>

<span data-ttu-id="5ccc9-108">Mer detaljerad information finns i [Använda Office 365 Content Delivery Network (CDN) med SharePoint Online.](use-microsoft-365-cdn-with-spo.md)</span><span class="sxs-lookup"><span data-stu-id="5ccc9-108">For more detailed information guidance see [Use the Office 365 Content Delivery Network (CDN) with SharePoint Online](use-microsoft-365-cdn-with-spo.md).</span></span>

>[!NOTE]
><span data-ttu-id="5ccc9-109">Data Office 365 CDN bara tillgänglig för klientorganisationen i produktionsmoln (globalt).</span><span class="sxs-lookup"><span data-stu-id="5ccc9-109">The Office 365 CDN is only available to tenants in the production (worldwide) cloud.</span></span> <span data-ttu-id="5ccc9-110">Klientorganisationen i molnen för myndigheter i USA, Kina och Tyskland stöder för närvarande inte Office 365 CDN.</span><span class="sxs-lookup"><span data-stu-id="5ccc9-110">Tenants in the US Government, China and Germany clouds do not currently support the Office 365 CDN.</span></span>

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-identify-items-not-in-cdn"></a><span data-ttu-id="5ccc9-111">Använd siddiagnostikverktyget för SharePoint för att identifiera objekt som inte finns CDN</span><span class="sxs-lookup"><span data-stu-id="5ccc9-111">Use the Page Diagnostics for SharePoint tool to identify items not in CDN</span></span>

<span data-ttu-id="5ccc9-112">Du kan använda **Siddiagnostik** för SharePoint för webbläsaren för att enkelt visa tillgångar på dina SharePoint Online-sidor som kan läggas till i ett CDN ursprung.</span><span class="sxs-lookup"><span data-stu-id="5ccc9-112">You can use the **Page Diagnostics for SharePoint tool** browser extension to easily list assets in your SharePoint Online pages that can be added to a CDN origin.</span></span>

<span data-ttu-id="5ccc9-113">**Siddiagnostik för SharePoint är** ett webbläsartillägg för nya Microsoft Edge ( och Chrome-webbläsare som analyserar både moderna SharePoint Online-portalen och klassiska https://www.microsoft.com/edge) publiceringswebbplatssidor.</span><span class="sxs-lookup"><span data-stu-id="5ccc9-113">The **Page Diagnostics for SharePoint tool** is a browser extension for the new Microsoft Edge (https://www.microsoft.com/edge) and Chrome browsers that analyzes both SharePoint Online modern portal and classic publishing site pages.</span></span> <span data-ttu-id="5ccc9-114">Verktyget innehåller en rapport för varje analyserad sida som visar hur sidan fungerar mot en definierad uppsättning prestandavillkor.</span><span class="sxs-lookup"><span data-stu-id="5ccc9-114">The tool provides a report for each analyzed page showing how the page performs against a defined set of performance criteria.</span></span> <span data-ttu-id="5ccc9-115">Om du vill installera och lära dig mer SharePoint siddiagnostikverktyget går du till Använda [verktyget Siddiagnostik för SharePoint Online.](./page-diagnostics-for-spo.md)</span><span class="sxs-lookup"><span data-stu-id="5ccc9-115">To install and learn about the Page Diagnostics for SharePoint tool, visit [Use the Page Diagnostics tool for SharePoint Online](./page-diagnostics-for-spo.md).</span></span>

<span data-ttu-id="5ccc9-116">När du kör siddiagnostik för SharePoint-verktyget på en SharePoint Online-sida  kan du klicka på fliken Diagnostiktest för att visa en lista över tillgångar som inte CDN.</span><span class="sxs-lookup"><span data-stu-id="5ccc9-116">When you run the Page Diagnostics for SharePoint tool on a SharePoint Online page, you can click the **Diagnostic Tests** tab to see a list of assets not being hosted by the CDN.</span></span> <span data-ttu-id="5ccc9-117">De här tillgångarna visas under rubriken för **Content Delivery Network (CDN) kontrollera** enligt skärmbilden nedan.</span><span class="sxs-lookup"><span data-stu-id="5ccc9-117">These assets will be listed under the heading **Content Delivery Network (CDN) check** as shown in the screenshot below.</span></span>

![Siddiagnostik](../media/page-diagnostics-for-spo/pagediag-results-general.PNG)

>[!NOTE]
><span data-ttu-id="5ccc9-119">Verktyget Siddiagnostik fungerar bara för SharePoint Online och kan inte användas på en SharePoint systemsida.</span><span class="sxs-lookup"><span data-stu-id="5ccc9-119">The Page Diagnostics tool only works for SharePoint Online, and cannot be used on a SharePoint system page.</span></span>

## <a name="cdn-overview"></a><span data-ttu-id="5ccc9-120">CDN Översikt</span><span class="sxs-lookup"><span data-stu-id="5ccc9-120">CDN Overview</span></span>

<span data-ttu-id="5ccc9-121">Programmet Office 365 CDN har utformats för att optimera prestanda för användare genom att distribuera objekt som används ofta, till exempel bilder och javascript, över ett globalt nätverk med hög hastighet, vilket minskar inläsningstiden för sidor och ger åtkomst till värdbaserade objekt så nära användaren som möjligt.</span><span class="sxs-lookup"><span data-stu-id="5ccc9-121">The Office 365 CDN is designed to optimize performance for users by distributing frequently accessed objects like images and javascript files over a high-speed global network, reducing page load time and providing access to hosted objects as close as possible to the user.</span></span> <span data-ttu-id="5ccc9-122">Data CDN dina tillgångar från en plats som kallas för _ursprung_.</span><span class="sxs-lookup"><span data-stu-id="5ccc9-122">The CDN fetches your assets from a location called an _origin_.</span></span> <span data-ttu-id="5ccc9-123">Ursprunget kan vara en SharePoint, ett dokumentbibliotek eller en mapp som kan nås via en URL.</span><span class="sxs-lookup"><span data-stu-id="5ccc9-123">An origin can be a SharePoint site, document library or folder that is accessible by a URL.</span></span>

<span data-ttu-id="5ccc9-124">Datatyperna Office 365 CDN indelade i två grundläggande typer:</span><span class="sxs-lookup"><span data-stu-id="5ccc9-124">The Office 365 CDN is separated into two basic types:</span></span>

- <span data-ttu-id="5ccc9-125">**Den offentliga CDN** är utformad för att användas för JS (JavaScript), CSS (StyleSheets), Web Font File (WOFF, WOFF2) och icke-ägandeliknande bilder som företagslogotyp.</span><span class="sxs-lookup"><span data-stu-id="5ccc9-125">**Public CDN** is designed to be used for JS (JavaScript), CSS (StyleSheets), Web Font File (WOFF, WOFF2) and non-proprietary images like company logos.</span></span>
- <span data-ttu-id="5ccc9-126">**Den CDN** är utformad för att användas för bilder (PNG, JPG, JPEG osv.).</span><span class="sxs-lookup"><span data-stu-id="5ccc9-126">**Private CDN** is designed to be used for images (PNG, JPG, JPEG, etc.).</span></span>

<span data-ttu-id="5ccc9-127">Du kan välja att ha både offentliga och privata ursprung för organisationen.</span><span class="sxs-lookup"><span data-stu-id="5ccc9-127">You can choose to have both public or private origins for your organization.</span></span> <span data-ttu-id="5ccc9-128">De flesta organisationer väljer att implementera en kombination av de två.</span><span class="sxs-lookup"><span data-stu-id="5ccc9-128">Most organizations will choose to implement a combination of the two.</span></span> <span data-ttu-id="5ccc9-129">Både offentliga och privata alternativ ger liknande prestandaförbättringar, men var och en har unika attribut och fördelar.</span><span class="sxs-lookup"><span data-stu-id="5ccc9-129">Both public and private options provide similar performance gains, but each has unique attributes and advantages.</span></span> <span data-ttu-id="5ccc9-130">Mer information om offentliga och privata CDN ursprung finns i [Välja om varje ursprung ska vara offentligt eller privat.](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)</span><span class="sxs-lookup"><span data-stu-id="5ccc9-130">For more information about public and private CDN origins, see [Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate).</span></span>

## <a name="how-to-enable-public-and-private-cdn-with-the-default-configuration"></a><span data-ttu-id="5ccc9-131">Aktivera offentliga och privata CDN med standardkonfigurationen</span><span class="sxs-lookup"><span data-stu-id="5ccc9-131">How to enable Public and Private CDN with the default configuration</span></span>
<span data-ttu-id="5ccc9-132">Innan du ändrar klientorganisationens inställningar CDN du kontrollera att den uppfyller organisationens efterlevnads-, säkerhets- och sekretesspolicy.</span><span class="sxs-lookup"><span data-stu-id="5ccc9-132">Before you make changes to the tenant CDN settings, you should verify that it meets compliance, security and privacy policies of your organization.</span></span>

<span data-ttu-id="5ccc9-133">Mer detaljerade konfigurationsinställningar, eller om du redan har aktiverat CDN och vill lägga till ytterligare platser (ursprung), finns i avsnittet Konfigurera och konfigurera Office 365 CDN med hjälp av [SharePoint Online Management Shell](use-microsoft-365-cdn-with-spo.md#set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell)</span><span class="sxs-lookup"><span data-stu-id="5ccc9-133">For more detailed configuration settings, or if you have already enabled CDN and want to add additional locations (origins), please see the section [Set up and configure the Office 365 CDN by using the SharePoint Online Management Shell](use-microsoft-365-cdn-with-spo.md#set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell)</span></span>

<span data-ttu-id="5ccc9-134">Anslut till klientorganisationen med hjälp SharePoint Online Management Shell:</span><span class="sxs-lookup"><span data-stu-id="5ccc9-134">Connect to your tenant using the SharePoint Online Management Shell:</span></span>

```PowerShell
Connect-SPOService -Url https://<YourTenantName>-admin.sharepoint.com
```

<span data-ttu-id="5ccc9-135">Om du vill aktivera organisationen för att använda både offentliga och privata ursprung med standardkonfigurationen skriver du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="5ccc9-135">To enable your organization to use both public and private origins with the default configuration, type the following command:</span></span>

```PowerShell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

<span data-ttu-id="5ccc9-136">Utdata från dessa cmdlets bör se ut så här:</span><span class="sxs-lookup"><span data-stu-id="5ccc9-136">Output of these cmdlets should look like the following:</span></span>

![Utdata från Set-SPOTenantCdnEnabled](../media/O365-CDN/o365-cdn-enable-output.png)

## <a name="see-also"></a><span data-ttu-id="5ccc9-138">Se även</span><span class="sxs-lookup"><span data-stu-id="5ccc9-138">See also</span></span>

[<span data-ttu-id="5ccc9-139">Använda verktyget Siddiagnostik för SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="5ccc9-139">Use the Page Diagnostics tool for SharePoint Online</span></span>](./page-diagnostics-for-spo.md)

[<span data-ttu-id="5ccc9-140">Använda Office 365 Content Delivery Network (CDN) med SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="5ccc9-140">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)

[<span data-ttu-id="5ccc9-141">Nätverk för innehållsleverans (CDN)</span><span class="sxs-lookup"><span data-stu-id="5ccc9-141">Content Delivery Networks</span></span>](./content-delivery-networks.md)

[<span data-ttu-id="5ccc9-142">Network planning and performance tuning for Office 365</span><span class="sxs-lookup"><span data-stu-id="5ccc9-142">Network planning and performance tuning for Office 365</span></span>](./network-planning-and-performance.md)

[<span data-ttu-id="5ccc9-143">SharePoint Performance Series – Office 365 CDN videoserie</span><span class="sxs-lookup"><span data-stu-id="5ccc9-143">SharePoint Performance Series - Office 365 CDN video series</span></span>](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)