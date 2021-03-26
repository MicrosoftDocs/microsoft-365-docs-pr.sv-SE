---
title: Använda Office 365 Content Delivery Network (CDN) med SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 2/19/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- SPO160
ms.assetid: bebb285f-1d54-4f79-90a5-94985afc6af8
description: Lär dig hur du använder Nätverket för innehållsleverans i Office 365 (CDN) för att snabba på leveransen av dina SharePoint Online-tillgångar.
ms.openlocfilehash: 17c80b8718ea46c9dfba9f803093974e8ce3e706
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222689"
---
# <a name="use-the-office-365-content-delivery-network-cdn-with-sharepoint-online"></a><span data-ttu-id="1918c-103">Använda Office 365 Content Delivery Network (CDN) med SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="1918c-103">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>

<span data-ttu-id="1918c-104">Du kan använda det inbyggda nätverket för innehållsleverans i Office 365 (CDN) för statiska tillgångar för att få bättre prestanda för dina SharePoint Online-sidor.</span><span class="sxs-lookup"><span data-stu-id="1918c-104">You can use the built-in Office 365 Content Delivery Network (CDN) to host static assets to provide better performance for your SharePoint Online pages.</span></span> <span data-ttu-id="1918c-105">Office 365 CDN förbättrar prestandan genom att cachelagra statiska tillgångar närmare de webbläsare som begär dem, vilket hjälper till att snabba på hämtningar och minska svarstiden.</span><span class="sxs-lookup"><span data-stu-id="1918c-105">The Office 365 CDN improves performance by caching static assets closer to the browsers requesting them, which helps to speed up downloads and reduce latency.</span></span> <span data-ttu-id="1918c-106">Office 365 CDN använder också [HTTP/2-protokollet](https://en.wikipedia.org/wiki/HTTP/2) för förbättrad komprimering och HTTP-pipelining.</span><span class="sxs-lookup"><span data-stu-id="1918c-106">Also, the Office 365 CDN uses the [HTTP/2 protocol](https://en.wikipedia.org/wiki/HTTP/2) for improved compression and HTTP pipelining.</span></span> <span data-ttu-id="1918c-107">Office 365 CDN-tjänsten ingår som en del av din SharePoint Online-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="1918c-107">The Office 365 CDN service is included as part of your SharePoint Online subscription.</span></span>

> [!NOTE]
> <span data-ttu-id="1918c-108">Office 365 CDN är bara tillgängligt för innehavare i molnet **För** produktion (globalt).</span><span class="sxs-lookup"><span data-stu-id="1918c-108">The Office 365 CDN is only available to tenants in the **Production** (worldwide) cloud.</span></span> <span data-ttu-id="1918c-109">Klientorganisationen i molnen för myndigheter i USA, Kina och Tyskland stöder för närvarande inte Office 365 CDN.</span><span class="sxs-lookup"><span data-stu-id="1918c-109">Tenants in the US Government, China and Germany clouds do not currently support the Office 365 CDN.</span></span>

<span data-ttu-id="1918c-110">Office 365 CDN består av flera CDN-nätverk som gör att du kan lagra statiska tillgångar på flera platser, eller ursprung _,_ och hantera dem från globala nätverk med hög hastighet.</span><span class="sxs-lookup"><span data-stu-id="1918c-110">The Office 365 CDN is composed of multiple CDNs that allow you to host static assets in multiple locations, or _origins_, and serve them from global high-speed networks.</span></span> <span data-ttu-id="1918c-111">Beroende på vilken typ av innehåll du vill ha i Office 365 CDN kan du lägga till offentliga **ursprung,** privata ursprung eller båda. </span><span class="sxs-lookup"><span data-stu-id="1918c-111">Depending on the kind of content you want to host in the Office 365 CDN, you can add **public** origins, **private** origins or both.</span></span> <span data-ttu-id="1918c-112">Se [Välj om varje ursprung ska vara offentligt eller](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) privat för mer information om skillnaden mellan offentliga och privata ursprung.</span><span class="sxs-lookup"><span data-stu-id="1918c-112">See [Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) for more information on the difference between public and private origins.</span></span>

<span data-ttu-id="1918c-113">![Konceptuellt diagram för Office 365 CDN](../media/O365-CDN/o365-cdn-flow-transparent.svg "Konceptuellt diagram för Office 365 CDN")</span><span class="sxs-lookup"><span data-stu-id="1918c-113">![Office 365 CDN conceptual diagram](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 CDN conceptual diagram")</span></span>

<span data-ttu-id="1918c-114">Om du redan är bekant med hur CDNs fungerar behöver du bara utföra några få steg för att aktivera Office 365 CDN för din klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="1918c-114">If you are already familiar with the way that CDNs work, you only need to complete a few steps to enable the Office 365 CDN for your tenant.</span></span> <span data-ttu-id="1918c-115">I det här avsnittet beskrivs hur du gör.</span><span class="sxs-lookup"><span data-stu-id="1918c-115">This topic describes how.</span></span> <span data-ttu-id="1918c-116">Läs vidare för information om hur du kommer igång med värdskap för dina statiska tillgångar.</span><span class="sxs-lookup"><span data-stu-id="1918c-116">Read on for information about how to get started hosting your static assets.</span></span>

> [!TIP]
> <span data-ttu-id="1918c-117">Det finns andra CDN med Microsoft-värd som kan användas med Office 365 för särskilda användningsscenarier, men som inte diskuteras i det här avsnittet eftersom de faller utanför Office 365 CDN.</span><span class="sxs-lookup"><span data-stu-id="1918c-117">There are other Microsoft-hosted CDNs that can be used with Office 365 for specialized usage scenarios, but are not discussed in this topic because they fall outside the scope of the Office 365 CDN.</span></span> <span data-ttu-id="1918c-118">Mer information finns i Andra [Microsoft CDN.](content-delivery-networks.md#other-microsoft-cdns)</span><span class="sxs-lookup"><span data-stu-id="1918c-118">For more information, see [Other Microsoft CDNs](content-delivery-networks.md#other-microsoft-cdns).</span></span>

 <span data-ttu-id="1918c-119">**Gå tillbaka till [Nätverksplanering och prestandajustering för Office 365.](./network-planning-and-performance.md)**</span><span class="sxs-lookup"><span data-stu-id="1918c-119">**Head back to [Network planning and performance tuning for Office 365](./network-planning-and-performance.md).**</span></span>

## <a name="overview-of-working-with-the-office-365-cdn-in-sharepoint-online"></a><span data-ttu-id="1918c-120">Översikt över hur du arbetar med Office 365 CDN i SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="1918c-120">Overview of working with the Office 365 CDN in SharePoint Online</span></span>

<span data-ttu-id="1918c-121">Om du vill konfigurera Office 365 CDN för organisationen följer du de här grundläggande stegen:</span><span class="sxs-lookup"><span data-stu-id="1918c-121">To set up the Office 365 CDN for your organization, you follow these basic steps:</span></span>

+ [<span data-ttu-id="1918c-122">Planera för distribution av Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="1918c-122">Plan for deployment of the Office 365 CDN</span></span>](use-microsoft-365-cdn-with-spo.md#plan-for-deployment-of-the-office-365-cdn)

  + <span data-ttu-id="1918c-123">[Bestäm vilka statiska tillgångar du vill ha på CDN.](use-microsoft-365-cdn-with-spo.md#CDNAssets)</span><span class="sxs-lookup"><span data-stu-id="1918c-123">[Determine which static assets you want to host on the CDN](use-microsoft-365-cdn-with-spo.md#CDNAssets).</span></span>
  + <span data-ttu-id="1918c-124">[Bestäm var du vill lagra tillgångarna](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets).</span><span class="sxs-lookup"><span data-stu-id="1918c-124">[Determine where you want to store your assets](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets).</span></span> <span data-ttu-id="1918c-125">Platsen kan vara en webbplats, ett bibliotek eller en mapp i SharePoint och kallas _ursprung._</span><span class="sxs-lookup"><span data-stu-id="1918c-125">This location can be a SharePoint site, library or folder and is called an _origin_.</span></span>
  + <span data-ttu-id="1918c-126">[Välj om varje ursprung ska vara offentligt eller privat.](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)</span><span class="sxs-lookup"><span data-stu-id="1918c-126">[Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate).</span></span> <span data-ttu-id="1918c-127">Du kan lägga till flera ursprung för både offentliga och privata typer.</span><span class="sxs-lookup"><span data-stu-id="1918c-127">You can add multiple origins of both public and private types.</span></span>

+ <span data-ttu-id="1918c-128">Konfigurera och konfigurera CDN med hjälp av antingen PowerShell eller SharePoint Online CLI</span><span class="sxs-lookup"><span data-stu-id="1918c-128">Set up and configure the CDN, using either PowerShell or the SharePoint Online CLI</span></span>

  + [<span data-ttu-id="1918c-129">Konfigurera och konfigurera CDN med hjälp av SharePoint Online Management Shell</span><span class="sxs-lookup"><span data-stu-id="1918c-129">Set up and configure the CDN by using the SharePoint Online Management Shell</span></span>](use-microsoft-365-cdn-with-spo.md#CDNSetupinPShell)
  + [<span data-ttu-id="1918c-130">Konfigurera och konfigurera CDN med hjälp av PnP PowerShell</span><span class="sxs-lookup"><span data-stu-id="1918c-130">Set up and configure the CDN by using PnP PowerShell</span></span>](use-microsoft-365-cdn-with-spo.md#CDNSetupinPnPPosh)
  + [<span data-ttu-id="1918c-131">Konfigurera och konfigurera CDN med hjälp av Office 365 CLI</span><span class="sxs-lookup"><span data-stu-id="1918c-131">Set up and configure the CDN by using the Office 365 CLI</span></span>](use-microsoft-365-cdn-with-spo.md#CDNSetupinCLI)

  <span data-ttu-id="1918c-132">När du slutför det här steget har du:</span><span class="sxs-lookup"><span data-stu-id="1918c-132">When you complete this step, you will have:</span></span>

  + <span data-ttu-id="1918c-133">Aktiverat CDN för organisationen.</span><span class="sxs-lookup"><span data-stu-id="1918c-133">Enabled the CDN for your organization.</span></span>
  + <span data-ttu-id="1918c-134">Lagt till ursprungen och identifierar varje ursprung som offentligt eller privat.</span><span class="sxs-lookup"><span data-stu-id="1918c-134">Added your origins, identifying each origin as public or private.</span></span>

<span data-ttu-id="1918c-135">När du är klar med konfigurationen kan du hantera [Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNManage) över tid genom att:</span><span class="sxs-lookup"><span data-stu-id="1918c-135">Once you're done with setup, you can [Manage the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNManage) over time by:</span></span>
  
+ <span data-ttu-id="1918c-136">Lägga till, uppdatera och ta bort tillgångar</span><span class="sxs-lookup"><span data-stu-id="1918c-136">Adding, updating, and removing assets</span></span>
+ <span data-ttu-id="1918c-137">Lägga till och ta bort ursprung</span><span class="sxs-lookup"><span data-stu-id="1918c-137">Adding and removing origins</span></span>
+ <span data-ttu-id="1918c-138">Konfigurera CDN-principer</span><span class="sxs-lookup"><span data-stu-id="1918c-138">Configuring CDN policies</span></span>
+ <span data-ttu-id="1918c-139">Inaktivera CDN om det behövs</span><span class="sxs-lookup"><span data-stu-id="1918c-139">If necessary, disabling the CDN</span></span>

<span data-ttu-id="1918c-140">Slutligen kan du läsa [Använda dina CDN-tillgångar för](use-microsoft-365-cdn-with-spo.md#using-your-cdn-assets) att lära dig mer om hur du kommer åt dina CDN-tillgångar från både offentliga och privata ursprung.</span><span class="sxs-lookup"><span data-stu-id="1918c-140">Finally, see [Using your CDN assets](use-microsoft-365-cdn-with-spo.md#using-your-cdn-assets) to learn about accessing your CDN assets from both public and private origins.</span></span>

<span data-ttu-id="1918c-141">Mer information om hur du löser vanliga problem finns i Felsöka [Office 365 CDN.](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting)</span><span class="sxs-lookup"><span data-stu-id="1918c-141">See [Troubleshooting the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) for guidance on resolving common issues.</span></span>

## <a name="plan-for-deployment-of-the-office-365-cdn"></a><span data-ttu-id="1918c-142">Planera för distribution av Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="1918c-142">Plan for deployment of the Office 365 CDN</span></span>

<span data-ttu-id="1918c-143">Innan du distribuerar Office 365 CDN för Office 365-klienten bör du tänka på följande faktorer som en del av planeringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="1918c-143">Before you deploy the Office 365 CDN for your Office 365 tenant, you should consider the following factors as part of your planning process.</span></span>

  + [<span data-ttu-id="1918c-144">Bestäm vilka statiska tillgångar du vill ha på CDN</span><span class="sxs-lookup"><span data-stu-id="1918c-144">Determine which static assets you want to host on the CDN</span></span>](use-microsoft-365-cdn-with-spo.md#CDNAssets)
  + [<span data-ttu-id="1918c-145">Bestäm var du vill lagra tillgångarna</span><span class="sxs-lookup"><span data-stu-id="1918c-145">Determine where you want to store your assets</span></span>](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets)
  + [<span data-ttu-id="1918c-146">Välj om varje ursprung ska vara offentligt eller privat</span><span class="sxs-lookup"><span data-stu-id="1918c-146">Choose whether each origin should be public or private</span></span>](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)

<span data-ttu-id="1918c-147"><a name="CDNAssets"> </a></span><span class="sxs-lookup"><span data-stu-id="1918c-147"><a name="CDNAssets"> </a></span></span>
### <a name="determine-which-static-assets-you-want-to-host-on-the-cdn"></a><span data-ttu-id="1918c-148">Bestäm vilka statiska tillgångar du vill ha på CDN</span><span class="sxs-lookup"><span data-stu-id="1918c-148">Determine which static assets you want to host on the CDN</span></span>

<span data-ttu-id="1918c-149">I allmänhet är CDN mest effektiva för värd _för statiska_ tillgångar , eller tillgångar som inte ändras så ofta.</span><span class="sxs-lookup"><span data-stu-id="1918c-149">In general, CDNs are most effective for hosting _static assets_, or assets that don't change very often.</span></span> <span data-ttu-id="1918c-150">En bra tumregel är att identifiera filer som uppfyller vissa eller alla dessa villkor:</span><span class="sxs-lookup"><span data-stu-id="1918c-150">A good rule of thumb is to identify files that meet some or all of these conditions:</span></span>

+ <span data-ttu-id="1918c-151">Statiska filer som är inbäddade i en sida (till exempel skript och bilder) som kan ha en betydande stegvis inverkan på sidornas inläsningstider</span><span class="sxs-lookup"><span data-stu-id="1918c-151">Static files embedded in a page (like scripts and images) that may have a significant incremental impact on page load times</span></span>
+ <span data-ttu-id="1918c-152">Stora filer som körbara filer och installationsfiler</span><span class="sxs-lookup"><span data-stu-id="1918c-152">Large files like executables and installation files</span></span>
+ <span data-ttu-id="1918c-153">Resursbibliotek med stöd för klientkod</span><span class="sxs-lookup"><span data-stu-id="1918c-153">Resource libraries that support client-side code</span></span>

<span data-ttu-id="1918c-154">Till exempel kan små filer som upprepade gånger efterfrågas, t.ex. webbplatsbilder och skript, avsevärt förbättra prestanda för webbplatsåtergivning och stegvis minska belastningen på SharePoint Online-webbplatser när du lägger till dem i ett CDN-ursprung.</span><span class="sxs-lookup"><span data-stu-id="1918c-154">For example, small files that are repeatedly requested like site images and scripts can significantly improve site rendering performance and incrementally reduce the load on your SharePoint Online sites when you add them to a CDN origin.</span></span> <span data-ttu-id="1918c-155">Större filer, till exempel körbara installationsfiler, kan laddas ned från CDN, vilket ger positiv prestanda påverkan och därefter en minskning av belastningen på SharePoint Online-webbplatsen, även om de inte används så ofta.</span><span class="sxs-lookup"><span data-stu-id="1918c-155">Larger files such as installation executables can be downloaded from the CDN, delivering a positive performance impact and subsequent reduction of the load on your SharePoint Online site, even if they are not accessed as often.</span></span>

<span data-ttu-id="1918c-156">Prestandaförbättringar per fil beror på många faktorer, inklusive klientens närhet till närmaste CDN-slutpunkt, tillfälliga villkor i det lokala nätverket och så vidare.</span><span class="sxs-lookup"><span data-stu-id="1918c-156">Performance improvement on a per-file basis is dependent on many factors, including the client's proximity to the nearest CDN endpoint, transient conditions on the local network, and so forth.</span></span> <span data-ttu-id="1918c-157">Många statiska filer är ganska små och kan laddas ned från Office 365 på mindre än en sekund.</span><span class="sxs-lookup"><span data-stu-id="1918c-157">Many static files are quite small, and can be downloaded from Office 365 in less than a second.</span></span> <span data-ttu-id="1918c-158">En webbsida kan emellertid innehålla många inbäddade filer med en kumulativ nedladdningstid på flera sekunder.</span><span class="sxs-lookup"><span data-stu-id="1918c-158">However, a web page may contain many embedded files with a cumulative download time of several seconds.</span></span> <span data-ttu-id="1918c-159">Att använda dessa filer från CDN kan avsevärt minska inläsningstiden för sidan.</span><span class="sxs-lookup"><span data-stu-id="1918c-159">Serving these files from the CDN can significantly reduce the overall page load time.</span></span> <span data-ttu-id="1918c-160">Se [Vilka prestandaförbättringar tillhandahåller ett CDN?](content-delivery-networks.md#what-performance-gains-does-a-cdn-provide) i ett exempel.</span><span class="sxs-lookup"><span data-stu-id="1918c-160">See [What performance gains does a CDN provide?](content-delivery-networks.md#what-performance-gains-does-a-cdn-provide) for an example.</span></span>

<span data-ttu-id="1918c-161"><a name="CDNStoreAssets"> </a></span><span class="sxs-lookup"><span data-stu-id="1918c-161"><a name="CDNStoreAssets"> </a></span></span>
### <a name="determine-where-you-want-to-store-your-assets"></a><span data-ttu-id="1918c-162">Bestäm var du vill lagra tillgångarna</span><span class="sxs-lookup"><span data-stu-id="1918c-162">Determine where you want to store your assets</span></span>

<span data-ttu-id="1918c-163">CDN hämtar dina tillgångar från en plats som kallas för _ursprung._</span><span class="sxs-lookup"><span data-stu-id="1918c-163">The CDN fetches your assets from a location called an _origin_.</span></span> <span data-ttu-id="1918c-164">Ett ursprung kan vara en SharePoint-webbplats, ett dokumentbibliotek eller en mapp som kan nås via en URL.</span><span class="sxs-lookup"><span data-stu-id="1918c-164">An origin can be a SharePoint site, document library or folder that is accessible by a URL.</span></span> <span data-ttu-id="1918c-165">Du har stor flexibilitet när du anger ursprung för organisationen.</span><span class="sxs-lookup"><span data-stu-id="1918c-165">You have great flexibility when you specify origins for your organization.</span></span> <span data-ttu-id="1918c-166">Du kan till exempel ange flera ursprung eller ett enda ursprung där du vill placera alla CDN-tillgångar.</span><span class="sxs-lookup"><span data-stu-id="1918c-166">For example, you can specify multiple origins or a single origin where you want to put all your CDN assets.</span></span> <span data-ttu-id="1918c-167">Du kan välja att ha både offentliga och privata ursprung för organisationen.</span><span class="sxs-lookup"><span data-stu-id="1918c-167">You can choose to have both public or private origins for your organization.</span></span> <span data-ttu-id="1918c-168">De flesta organisationer väljer att implementera en kombination av de två.</span><span class="sxs-lookup"><span data-stu-id="1918c-168">Most organizations will choose to implement a combination of the two.</span></span>

<span data-ttu-id="1918c-169">Du kan skapa en ny behållare för ursprungen, till exempel mappar eller dokumentbibliotek, och lägga till filer som du vill göra tillgängliga från CDN.</span><span class="sxs-lookup"><span data-stu-id="1918c-169">You can create new container for your origins such as folders or document libraries, and add files you want to make available from the CDN.</span></span> <span data-ttu-id="1918c-170">Det här är ett bra sätt om du har en särskild uppsättning tillgångar som du vill ska vara tillgänglig från CDN, och vill begränsa uppsättningen CDN-tillgångar till endast de filerna i behållaren.</span><span class="sxs-lookup"><span data-stu-id="1918c-170">This is a good approach if you have a specific set of assets you want to be available from the CDN, and want to restrict the set of CDN assets to only those files in the container.</span></span>

<span data-ttu-id="1918c-171">Du kan också konfigurera en befintlig webbplatssamling, webbplats, bibliotek eller mapp som ursprung, vilket gör alla kvalificerade tillgångar i behållaren tillgänglig från CDN.</span><span class="sxs-lookup"><span data-stu-id="1918c-171">You can also configure an existing site collection, site, library or folder as an origin, which will make all eligible assets in the container available from the CDN.</span></span> <span data-ttu-id="1918c-172">Innan du lägger till en befintlig behållare som ursprung är det viktigt att du är medveten om dess innehåll och behörigheter så att du inte oavsiktligt visar tillgångar för anonym åtkomst eller obehöriga användare.</span><span class="sxs-lookup"><span data-stu-id="1918c-172">Before you add an existing container as an origin, it's important to make sure you are aware of its contents and permissions so you do not inadvertently expose assets to anonymous access or unauthorized users.</span></span>

<span data-ttu-id="1918c-173">Du kan definiera _CDN-principer_ för att utesluta innehåll i dina ursprung från CDN.</span><span class="sxs-lookup"><span data-stu-id="1918c-173">You can define _CDN policies_ to exclude content in your origins from the CDN.</span></span> <span data-ttu-id="1918c-174">CDN-principer utesluter tillgångar i offentliga eller  privata ursprung efter attribut, till exempel filtyp och webbplatsklassificering, och tillämpas på alla ursprung för den CdnType (privat eller offentlig) du anger i principen.</span><span class="sxs-lookup"><span data-stu-id="1918c-174">CDN policies exclude assets in public or private origins by attributes such as _file type_ and _site classification_, and are applied to all origins of the CdnType (private or public) you specify in the policy.</span></span> <span data-ttu-id="1918c-175">Om du till exempel lägger till ett privat ursprung som består av en webbplats som  innehåller flera underwebbplatser kan du definiera en princip för att utesluta webbplatser som markerats som konfidentiellt, så att innehåll från webbplatser med den klassificering som tillämpas inte kommer att användas från CDN.</span><span class="sxs-lookup"><span data-stu-id="1918c-175">For example, if you add a private origin consisting of a site that contains multiple subsites, you can define a policy to exclude sites marked as **Confidential** so content from sites with that classification applied will not be served from the CDN.</span></span> <span data-ttu-id="1918c-176">Principen gäller för innehåll från alla _privata ursprung_ som du har lagt till i CDN.</span><span class="sxs-lookup"><span data-stu-id="1918c-176">The policy will apply to content from _all_ private origins you have added to the CDN.</span></span>
  
<span data-ttu-id="1918c-177">Tänk på att ju större antal ursprung, desto större inverkan på tiden det tar CDN-tjänsten att bearbeta begäranden.</span><span class="sxs-lookup"><span data-stu-id="1918c-177">Keep in mind that the greater the number of origins, the greater the impact on the time it takes the CDN service to process requests.</span></span> <span data-ttu-id="1918c-178">Vi rekommenderar att du så mycket som möjligt begränsar antalet ursprung.</span><span class="sxs-lookup"><span data-stu-id="1918c-178">We recommend that you limit the number of origins as much as possible.</span></span>
  
<span data-ttu-id="1918c-179"><a name="CDNOriginChoosePublicPrivate"> </a></span><span class="sxs-lookup"><span data-stu-id="1918c-179"><a name="CDNOriginChoosePublicPrivate"> </a></span></span>
### <a name="choose-whether-each-origin-should-be-public-or-private"></a><span data-ttu-id="1918c-180">Välj om varje ursprung ska vara offentligt eller privat</span><span class="sxs-lookup"><span data-stu-id="1918c-180">Choose whether each origin should be public or private</span></span>

<span data-ttu-id="1918c-181">När du identifierar ett ursprung anger du om det ska göras _offentligt eller_ _privat._</span><span class="sxs-lookup"><span data-stu-id="1918c-181">When you identify an origin, you specify whether it should be made _public_ or _private_.</span></span> <span data-ttu-id="1918c-182">Åtkomst till CDN-tillgångar i offentliga ursprung är anonym och CDN-innehåll i privata ursprung skyddas av dynamiskt genererade token för större säkerhet.</span><span class="sxs-lookup"><span data-stu-id="1918c-182">Access to CDN assets in public origins is anonymous, and CDN content in private origins is secured by dynamically generated tokens for greater security.</span></span> <span data-ttu-id="1918c-183">Oavsett vilket alternativ du väljer gör Microsoft allt grovjobb åt dig när det gäller administration av själva CDN.</span><span class="sxs-lookup"><span data-stu-id="1918c-183">Regardless of which option you choose, Microsoft does all the heavy lifting for you when it comes to administration of the CDN itself.</span></span> <span data-ttu-id="1918c-184">Du kan också ändra dig senare, när du har konfigurerat CDN och identifierat dina ursprung.</span><span class="sxs-lookup"><span data-stu-id="1918c-184">Also, you can change your mind later, after you've set up the CDN and identified your origins.</span></span>

<span data-ttu-id="1918c-185">Både offentliga och privata alternativ ger liknande prestandaförbättringar, men var och en har unika attribut och fördelar.</span><span class="sxs-lookup"><span data-stu-id="1918c-185">Both public and private options provide similar performance gains, but each has unique attributes and advantages.</span></span>

<span data-ttu-id="1918c-186">**Offentliga** ursprung i Office 365 CDN är anonymt tillgängliga och värdtillgångar kan nås av alla som har URL-adressen till tillgången.</span><span class="sxs-lookup"><span data-stu-id="1918c-186">**Public** origins within the Office 365 CDN are accessible anonymously, and hosted assets can be accessed by anyone who has the URL to the asset.</span></span> <span data-ttu-id="1918c-187">Eftersom åtkomsten till innehåll i offentliga ursprung är anonym bör du bara använda dem för att cachelagra icke-känsligt allmänt innehåll som javascript-filer, skript, ikoner och bilder.</span><span class="sxs-lookup"><span data-stu-id="1918c-187">Because access to content in public origins is anonymous, you should only use them to cache non-sensitive generic content such as javascript files, scripts, icons and images.</span></span>

<span data-ttu-id="1918c-188">**Privata** ursprung i Office 365 CDN ger privat åtkomst till användarinnehåll, till exempel dokumentbibliotek, webbplatser och egna bilder i SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="1918c-188">**Private** origins within the Office 365 CDN provide private access to user content such as SharePoint Online document libraries, sites and proprietary images.</span></span> <span data-ttu-id="1918c-189">Åtkomst till innehåll i privata ursprung skyddas av dynamiskt genererade tokens så att användare med behörighet till det ursprungliga dokumentbiblioteket eller lagringsplatsen endast kan komma åt det.</span><span class="sxs-lookup"><span data-stu-id="1918c-189">Access to content in private origins is secured by dynamically generated tokens so it can only be accessed by users with permissions to the original document library or storage location.</span></span> <span data-ttu-id="1918c-190">Privata ursprung i Office 365 CDN kan endast användas för SharePoint Online-innehåll och du kan bara komma åt tillgångar i privata ursprung genom omdirigering från SharePoint Online-klienten.</span><span class="sxs-lookup"><span data-stu-id="1918c-190">Private origins in the Office 365 CDN can only be used for SharePoint Online content, and you can only access assets in private origins through redirection from your SharePoint Online tenant.</span></span>

<span data-ttu-id="1918c-191">Du kan läsa mer om hur CDN-åtkomst till tillgångar i ett privat ursprung fungerar i [Använda tillgångar i privata ursprung.](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)</span><span class="sxs-lookup"><span data-stu-id="1918c-191">You can read more about how CDN access to assets in a private origin works in [Using assets in private origins](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins).</span></span>

#### <a name="attributes-and-advantages-of-hosting-assets-in-public-origins"></a><span data-ttu-id="1918c-192">Attribut och fördelar med att ha tillgångar i offentliga ursprung</span><span class="sxs-lookup"><span data-stu-id="1918c-192">Attributes and advantages of hosting assets in public origins</span></span>
  
+ <span data-ttu-id="1918c-193">Tillgångar som exponeras i en offentlig tillgång är åtkomliga för alla anonymt.</span><span class="sxs-lookup"><span data-stu-id="1918c-193">Assets exposed in a public origin are accessible by everyone anonymously.</span></span>
    > [!IMPORTANT]
    > <span data-ttu-id="1918c-194">Du ska aldrig placera resurser som innehåller användarinformation eller som anses vara känsliga för organisationen i ett offentligt ursprung.</span><span class="sxs-lookup"><span data-stu-id="1918c-194">You should never place resources that contain user information or are considered sensitive to your organization in a public origin.</span></span>
+ <span data-ttu-id="1918c-195">Om du tar bort en tillgång från ett offentligt ursprung kan tillgången fortsätta att vara tillgänglig i upp till 30 dagar från cachen. Länkar till tillgången blir ogiltiga i CDN inom 15 minuter.</span><span class="sxs-lookup"><span data-stu-id="1918c-195">If you remove an asset from a public origin, the asset may continue to be available for up to 30 days from the cache; however, we will invalidate links to the asset in the CDN within 15 minutes.</span></span>
+ <span data-ttu-id="1918c-196">När du är värd för formatmallar (CSS-filer) i ett offentligt ursprung kan du använda relativa sökvägar och URI:er i koden.</span><span class="sxs-lookup"><span data-stu-id="1918c-196">When you host style sheets (CSS files) in a public origin, you can use relative paths and URIs within the code.</span></span> <span data-ttu-id="1918c-197">Det innebär att du kan referera till platsen för bakgrundsbilder och andra objekt i förhållande till platsen för tillgången som anropar den.</span><span class="sxs-lookup"><span data-stu-id="1918c-197">This means that you can reference the location of background images and other objects relative to the location of the asset that's calling it.</span></span>
+ <span data-ttu-id="1918c-198">Du kan skapa URL-adressen för ett offentligt ursprung, men du bör vara försiktig och se till att du använder sidkontextegenskapen och följer instruktionerna för att göra det.</span><span class="sxs-lookup"><span data-stu-id="1918c-198">While you can construct a public origin's URL, you should proceed with caution and ensure you utilize the page context property and follow the guidance for doing so.</span></span> <span data-ttu-id="1918c-199">Anledningen är att om åtkomsten till CDN blir otillgänglig matchas inte URL-adressen automatiskt med din organisation i SharePoint Online och kan leda till brutna länkar och andra fel.</span><span class="sxs-lookup"><span data-stu-id="1918c-199">The reason for this is that if access to the CDN becomes unavailable, the URL will not automatically resolve to your organization in SharePoint Online and might result in broken links and other errors.</span></span> <span data-ttu-id="1918c-200">URL:en kan också komma att ändras. Det är därför den inte bara ska vara hårdkodad till sitt nuvarande värde.</span><span class="sxs-lookup"><span data-stu-id="1918c-200">The URL is also subject to change wich is why it should not just be hard coded to its current value.</span></span>
+ <span data-ttu-id="1918c-201">Standardfiltyperna som ingår för offentliga ursprung är .css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff och .woff2.</span><span class="sxs-lookup"><span data-stu-id="1918c-201">The default file types that are included for public origins are .css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff and .woff2.</span></span> <span data-ttu-id="1918c-202">Du kan ange ytterligare filtyper.</span><span class="sxs-lookup"><span data-stu-id="1918c-202">You can specify additional file types.</span></span>
+ <span data-ttu-id="1918c-203">Du kan konfigurera en princip för att utesluta tillgångar som har identifierats av webbplatsklassificeringarna som du anger.</span><span class="sxs-lookup"><span data-stu-id="1918c-203">You can configure a policy to exclude assets that have been identified by site classifications that you specify.</span></span> <span data-ttu-id="1918c-204">Du kan till exempel välja att utesluta alla tillgångar som markeras som "konfidentiell" eller "begränsad" även om de är en tillåten filtyp och finns i ett offentligt ursprung.</span><span class="sxs-lookup"><span data-stu-id="1918c-204">For example, you can choose to exclude all assets that are marked as "confidential" or "restricted" even if they are an allowed file type and are located in a public origin.</span></span>

#### <a name="attributes-and-advantages-of-hosting-assets-in-private-origins"></a><span data-ttu-id="1918c-205">Attribut och fördelar med att ha tillgångar i privata ursprung</span><span class="sxs-lookup"><span data-stu-id="1918c-205">Attributes and advantages of hosting assets in private origins</span></span>

+ <span data-ttu-id="1918c-206">Privata ursprung kan endast användas för SharePoint Online-tillgångar.</span><span class="sxs-lookup"><span data-stu-id="1918c-206">Private origins can only be used for SharePoint Online assets.</span></span>
+ <span data-ttu-id="1918c-207">Användare kan bara komma åt tillgångarna från ett privat ursprung om de har behörighet att komma åt behållaren.</span><span class="sxs-lookup"><span data-stu-id="1918c-207">Users can only access the assets from a private origin if they have permissions to access the container.</span></span> <span data-ttu-id="1918c-208">Anonym åtkomst till tillgångarna förhindras.</span><span class="sxs-lookup"><span data-stu-id="1918c-208">Anonymous access to these assets is prevented.</span></span>
+ <span data-ttu-id="1918c-209">Tillgångar i privata ursprung måste hänvisas från SharePoint Online-klienten.</span><span class="sxs-lookup"><span data-stu-id="1918c-209">Assets in private origins must be referred from the SharePoint Online tenant.</span></span> <span data-ttu-id="1918c-210">Direkt åtkomst till privata CDN-tillgångar fungerar inte.</span><span class="sxs-lookup"><span data-stu-id="1918c-210">Direct access to private CDN assets does not work.</span></span>
+ <span data-ttu-id="1918c-211">Om du tar bort en tillgång från det privata ursprunget kan tillgången fortsätta att vara tillgänglig i upp till en timme från cachen. Länkarna till tillgången blir ogiltiga i CDN inom 15 minuter efter att tillgången tas bort.</span><span class="sxs-lookup"><span data-stu-id="1918c-211">If you remove an asset from the private origin, the asset may continue to be available for up to an hour from the cache; however, we will invalidate links to the asset in the CDN within 15 minutes of the asset's removal.</span></span>
+ <span data-ttu-id="1918c-212">Standardfiltyperna som ingår för privata ursprung är .gif, .ico, .jpeg, .jpg, .js och .png.</span><span class="sxs-lookup"><span data-stu-id="1918c-212">The default file types that are included for private origins are .gif, .ico, .jpeg, .jpg, .js, and .png.</span></span> <span data-ttu-id="1918c-213">Du kan ange ytterligare filtyper.</span><span class="sxs-lookup"><span data-stu-id="1918c-213">You can specify additional file types.</span></span>
+ <span data-ttu-id="1918c-214">Precis som för offentliga ursprung kan du konfigurera en princip för att utesluta tillgångar som har identifierats av webbplatsklassificeringarna som du anger även om du använder jokertecken för att inkludera alla tillgångar i en mapp eller ett dokumentbibliotek.</span><span class="sxs-lookup"><span data-stu-id="1918c-214">Just like with public origins, you can configure a policy to exclude assets that have been identified by site classifications that you specify even if you use wildcards to include all assets within a folder or document library.</span></span>

<span data-ttu-id="1918c-215">Mer information om varför du använder Office 365 CDN, allmänna CDN-begrepp och andra Microsoft CDN-namn som du kan använda med din Office 365-klientorganisation finns i [Nätverk](content-delivery-networks.md)för innehållsleverans.</span><span class="sxs-lookup"><span data-stu-id="1918c-215">For more information about why to use the Office 365 CDN, general CDN concepts, and other Microsoft CDNs you can use with your Office 365 tenant, see [Content Delivery Networks](content-delivery-networks.md).</span></span>

### <a name="default-cdn-origins"></a><span data-ttu-id="1918c-216">Standard-CDN-ursprung</span><span class="sxs-lookup"><span data-stu-id="1918c-216">Default CDN origins</span></span>

<span data-ttu-id="1918c-217">Om du inte anger något annat uppsättningar Office 365 några standard ursprung åt dig när du aktiverar Office 365 CDN.</span><span class="sxs-lookup"><span data-stu-id="1918c-217">Unless you specify otherwise, Office 365 sets up some default origins for you when you enable the Office 365 CDN.</span></span> <span data-ttu-id="1918c-218">Om du först väljer att inte tillhandahålla dem kan du lägga till dessa ursprung när du har slutfört konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="1918c-218">If you initially opt not to provision them, you can add these origins after you complete setup.</span></span> <span data-ttu-id="1918c-219">Om du inte förstår konsekvenserna av att hoppa över konfigurationen av standard ursprung och har en särskild orsak till att göra det, bör du tillåta att de skapas när du aktiverar CDN.</span><span class="sxs-lookup"><span data-stu-id="1918c-219">Unless you understand the consequences of skipping the setup of default origins and have a specific reason for doing so, you should allow them to be created when you enable the CDN.</span></span>
  
<span data-ttu-id="1918c-220">Privata CDN-standardsprung:</span><span class="sxs-lookup"><span data-stu-id="1918c-220">Default private CDN origins:</span></span>
  
+ <span data-ttu-id="1918c-221">\*/userphoto.aspx</span><span class="sxs-lookup"><span data-stu-id="1918c-221">\*/userphoto.aspx</span></span>
+ <span data-ttu-id="1918c-222">\*/siteassets</span><span class="sxs-lookup"><span data-stu-id="1918c-222">\*/siteassets</span></span>

<span data-ttu-id="1918c-223">Offentliga CDN-standardsprung:</span><span class="sxs-lookup"><span data-stu-id="1918c-223">Default public CDN origins:</span></span>
  
+ <span data-ttu-id="1918c-224">\*/masterpage</span><span class="sxs-lookup"><span data-stu-id="1918c-224">\*/masterpage</span></span>
+ <span data-ttu-id="1918c-225">\*/style library</span><span class="sxs-lookup"><span data-stu-id="1918c-225">\*/style library</span></span>
+ <span data-ttu-id="1918c-226">\*/clientsideassets</span><span class="sxs-lookup"><span data-stu-id="1918c-226">\*/clientsideassets</span></span>

> [!NOTE]
> <span data-ttu-id="1918c-227">_clientsideassets_ är ett offentligt standard ursprung som lades till i Office 365 CDN-tjänsten i december 2017.</span><span class="sxs-lookup"><span data-stu-id="1918c-227">_clientsideassets_ is a default public origin that was added to the Office 365 CDN service in December 2017.</span></span> <span data-ttu-id="1918c-228">Det här ursprunget måste finnas för att SharePoint Framework-lösningar i CDN ska fungera.</span><span class="sxs-lookup"><span data-stu-id="1918c-228">This origin must be present in order for SharePoint Framework solutions in the CDN to work.</span></span> <span data-ttu-id="1918c-229">Om du aktiverade Office 365 CDN innan december 2017, eller om du hoppade över konfigurationen av standard ursprung när du aktiverade CDN, kan du manuellt lägga till det här ursprunget.</span><span class="sxs-lookup"><span data-stu-id="1918c-229">If you enabled the Office 365 CDN prior to December 2017, or if you skipped setup of default origins when you enabled the CDN, you can manually add this origin.</span></span> <span data-ttu-id="1918c-230">Mer information finns i [Min klientwebbdel eller SharePoint Framework-lösning fungerar inte.](use-microsoft-365-cdn-with-spo.md#my-client-side-web-part-or-sharepoint-framework-solution-isnt-working)</span><span class="sxs-lookup"><span data-stu-id="1918c-230">For more information, see [My client-side web part or SharePoint Framework solution isn't working](use-microsoft-365-cdn-with-spo.md#my-client-side-web-part-or-sharepoint-framework-solution-isnt-working).</span></span>

<span data-ttu-id="1918c-231"><a name="CDNSetupinPShell"> </a></span><span class="sxs-lookup"><span data-stu-id="1918c-231"><a name="CDNSetupinPShell"> </a></span></span>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell"></a><span data-ttu-id="1918c-232">Konfigurera och konfigurera Office 365 CDN med hjälp av SharePoint Online Management Shell</span><span class="sxs-lookup"><span data-stu-id="1918c-232">Set up and configure the Office 365 CDN by using the SharePoint Online Management Shell</span></span>

<span data-ttu-id="1918c-233">Procedurerna i det här avsnittet kräver att du använder SharePoint Online Management Shell för att ansluta till SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="1918c-233">The procedures in this section require you to use the SharePoint Online Management Shell to connect to SharePoint Online.</span></span> <span data-ttu-id="1918c-234">Instruktioner finns i [Ansluta till SharePoint Online PowerShell.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="1918c-234">For instructions, see [Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

<span data-ttu-id="1918c-235">Utför de här stegen för att konfigurera och konfigurera CDN som värd för dina tillgångar i SharePoint Online med SharePoint Online Management Shell.</span><span class="sxs-lookup"><span data-stu-id="1918c-235">Complete these steps to set up and configure the CDN to host your assets in SharePoint Online using the SharePoint Online Management Shell.</span></span>

<details>
  <summary><span data-ttu-id="1918c-236">Klicka för att Visa</span><span class="sxs-lookup"><span data-stu-id="1918c-236">Click to expand</span></span></summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a><span data-ttu-id="1918c-237">Aktivera organisationen för att använda Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="1918c-237">Enable your organization to use the Office 365 CDN</span></span>

<span data-ttu-id="1918c-238">Innan du gör ändringar i klientorganisationens CDN-inställningar bör du hämta aktuell status för den privata CDN-konfigurationen i Office 365-klienten.</span><span class="sxs-lookup"><span data-stu-id="1918c-238">Before you make changes to the tenant CDN settings, you should retrieve the current status of the private CDN configuration in your Office 365 tenant.</span></span> <span data-ttu-id="1918c-239">Ansluta till klientorganisationen med SharePoint Online Management Shell:</span><span class="sxs-lookup"><span data-stu-id="1918c-239">Connect to your tenant using the SharePoint Online Management Shell:</span></span>

``` powershell
Connect-SPOService -Url https://contoso-admin.sharepoint.com
```

<span data-ttu-id="1918c-240">Använd nu cmdleten **Get-SPOTenantCdnEnabled** till att hämta CDN-statusinställningarna från klientorganisationen:</span><span class="sxs-lookup"><span data-stu-id="1918c-240">Now use the **Get-SPOTenantCdnEnabled** cmdlet to retrieve the CDN status settings from the tenant:</span></span>

``` powershell
Get-SPOTenantCdnEnabled -CdnType <Public | Private>
```

<span data-ttu-id="1918c-241">Status för CDN för den angivna CdnType matas ut på skärmen.</span><span class="sxs-lookup"><span data-stu-id="1918c-241">The status of the CDN for the specified CdnType will output to the screen.</span></span>

<span data-ttu-id="1918c-242">Använd cmdleten **Set-SPOTenantCdnEnabled** till att aktivera organisationen för att använda Office 365 CDN.</span><span class="sxs-lookup"><span data-stu-id="1918c-242">Use the **Set-SPOTenantCdnEnabled** cmdlet to enable your organization to use the Office 365 CDN.</span></span> <span data-ttu-id="1918c-243">Du kan aktivera organisationen för att använda offentliga ursprung, privata ursprung eller båda samtidigt.</span><span class="sxs-lookup"><span data-stu-id="1918c-243">You can enable your organization to use public origins, private origins, or both at once.</span></span> <span data-ttu-id="1918c-244">Du kan också konfigurera CDN att hoppa över konfigurationen av standard ursprung när du aktiverar det.</span><span class="sxs-lookup"><span data-stu-id="1918c-244">You can also configure the CDN to skip the setup of default origins when you enable it.</span></span> <span data-ttu-id="1918c-245">Du kan alltid lägga till dessa ursprung senare enligt beskrivningen i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="1918c-245">You can always add these origins later as described in this topic.</span></span>
  
<span data-ttu-id="1918c-246">I Windows Powershell för SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="1918c-246">In Windows Powershell for SharePoint Online:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

<span data-ttu-id="1918c-247">Om du till exempel vill aktivera organisationen för att använda både offentliga och privata ursprung skriver du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="1918c-247">For example, to enable your organization to use both public and private origins, type the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

<span data-ttu-id="1918c-248">Om du vill aktivera organisationen för att använda både offentliga och privata ursprung men hoppa över att konfigurera standard ursprung skriver du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="1918c-248">To enable your organization to use both public and private origins but skip setting up the default origins, type the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

<span data-ttu-id="1918c-249">Mer information [om ursprung som etableras](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) som standard när du aktiverar Office 365 CDN finns i Standard-CDN-ursprung och eventuell inverkan med att hoppa över konfigurationen av standard ursprung.</span><span class="sxs-lookup"><span data-stu-id="1918c-249">See [Default CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) for information about the origins that are provisioned by default when you enable the Office 365 CDN, and the potential impact of skipping the setup of default origins.</span></span>

<span data-ttu-id="1918c-250">Om du vill aktivera organisationen för att använda offentliga ursprung skriver du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="1918c-250">To enable your organization to use public origins, type the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $true
```

<span data-ttu-id="1918c-251">Om du vill aktivera din organisation för att använda privata ursprung skriver du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="1918c-251">To enable your organization to use private origins, type the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $true
```

<span data-ttu-id="1918c-252">Mer information om den här cmdleten finns [i Set-SPOTenantCdnEnabled](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled).</span><span class="sxs-lookup"><span data-stu-id="1918c-252">For more information about this cmdlet, see [Set-SPOTenantCdnEnabled](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled).</span></span>

<span data-ttu-id="1918c-253"><a name="Office365CDNforSPOFileType"> </a></span><span class="sxs-lookup"><span data-stu-id="1918c-253"><a name="Office365CDNforSPOFileType"> </a></span></span>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a><span data-ttu-id="1918c-254">Ändra listan över filtyper som ska ingå i Office 365 CDN (valfritt)</span><span class="sxs-lookup"><span data-stu-id="1918c-254">Change the list of file types to include in the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="1918c-255">När du definierar filtyper med hjälp av cmdleten **Set-SPOTenantCdnPolicy** skriver du över den aktuella definierade listan.</span><span class="sxs-lookup"><span data-stu-id="1918c-255">When you define file types by using the **Set-SPOTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="1918c-256">Om du vill lägga till ytterligare filtyper i listan använder du först cmdleten för att ta reda på vilka filtyper som redan är tillåtna och inkludera dem i listan tillsammans med dina nya.</span><span class="sxs-lookup"><span data-stu-id="1918c-256">If you want to add additional file types to the list, use the cmdlet first to find out what file types are already allowed and include them in the list along with your new ones.</span></span>
  
<span data-ttu-id="1918c-257">Använd cmdleten **Set-SPOTenantCdnPolicy** till att definiera statiska filtyper som kan lagras av offentliga och privata ursprung i CDN.</span><span class="sxs-lookup"><span data-stu-id="1918c-257">Use the **Set-SPOTenantCdnPolicy** cmdlet to define static file types that can be hosted by public and private origins in the CDN.</span></span> <span data-ttu-id="1918c-258">Som standard tillåts vanliga tillgångstyper, till exempel .css, .gif, .jpg och .js.</span><span class="sxs-lookup"><span data-stu-id="1918c-258">By default, common asset types are allowed, for example .css, .gif, .jpg, and .js.</span></span>

<span data-ttu-id="1918c-259">I Windows PowerShell för SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="1918c-259">In Windows PowerShell for SharePoint Online:</span></span>

``` powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

<span data-ttu-id="1918c-260">Om du till exempel vill aktivera CDN som värd för .css- och .png-filer anger du kommandot:</span><span class="sxs-lookup"><span data-stu-id="1918c-260">For example, to enable the CDN to host .css and .png files, you would enter the command:</span></span>

``` powershell
Set-SPOTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

<span data-ttu-id="1918c-261">Om du vill se vilka filtyper som tillåts av CDN använder du cmdleten **Get-SPOTenantCdnPolicies:**</span><span class="sxs-lookup"><span data-stu-id="1918c-261">To see what file types are currently allowed by the CDN, use the **Get-SPOTenantCdnPolicies** cmdlet:</span></span>

``` powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="1918c-262">Mer information om dessa cmdlets finns i [Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) och [Get-SPOTenantCdnPolicies.](/powershell/module/sharepoint-online/)</span><span class="sxs-lookup"><span data-stu-id="1918c-262">For more information about these cmdlets, see [Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) and [Get-SPOTenantCdnPolicies](/powershell/module/sharepoint-online/).</span></span>

<span data-ttu-id="1918c-263"><a name="Office365CDNforSPOSiteClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="1918c-263"><a name="Office365CDNforSPOSiteClassification"> </a></span></span>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a><span data-ttu-id="1918c-264">Ändra listan över webbplatsklassificeringarna som du vill utesluta från Office 365 CDN (valfritt)</span><span class="sxs-lookup"><span data-stu-id="1918c-264">Change the list of site classifications you want to exclude from the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="1918c-265">När du utesluter webbplatsklassificeringarna med hjälp av cmdleten **Set-SPOTenantCdnPolicy** skriver du över den aktuella definierade listan.</span><span class="sxs-lookup"><span data-stu-id="1918c-265">When you exclude site classifications by using the **Set-SPOTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="1918c-266">Om du vill utesluta ytterligare webbplatsklassificeringarna använder du cmdleten först för att ta reda på vilka klassificeringar som redan har uteslutits och sedan lägga till dem tillsammans med dina nya.</span><span class="sxs-lookup"><span data-stu-id="1918c-266">If you want to exclude additional site classifications, use the cmdlet first to find out what classifications are already excluded and then add them along with your new ones.</span></span>

<span data-ttu-id="1918c-267">Använd **cmdleten Set-SPOTenantCdnPolicy** till att utesluta webbplatsklassificering som du inte vill ska vara tillgängliga via CDN.</span><span class="sxs-lookup"><span data-stu-id="1918c-267">Use the **Set-SPOTenantCdnPolicy** cmdlet to exclude site classifications that you do not want to make available over the CDN.</span></span> <span data-ttu-id="1918c-268">Som standard utesluts inga webbplatsklassificeringar.</span><span class="sxs-lookup"><span data-stu-id="1918c-268">By default, no site classifications are excluded.</span></span>

<span data-ttu-id="1918c-269">I Windows PowerShell för SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="1918c-269">In Windows PowerShell for SharePoint Online:</span></span>

``` powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications >"
```

<span data-ttu-id="1918c-270">Om du vill se vilka webbplatsklassificeringarna som är begränsade använder du cmdleten **Get-SPOTenantCdnPolicies:**</span><span class="sxs-lookup"><span data-stu-id="1918c-270">To see what site classifications are currently restricted, use the **Get-SPOTenantCdnPolicies** cmdlet:</span></span>

``` powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="1918c-271">Egenskaperna som returneras är _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ _och ExcludeIfNoScriptDisabled._</span><span class="sxs-lookup"><span data-stu-id="1918c-271">The properties that will be returned are _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ and _ExcludeIfNoScriptDisabled_.</span></span>

<span data-ttu-id="1918c-272">Egenskapen _IncludeFileExtensions_ innehåller listan över filnamnstillägg som kan användas i CDN.</span><span class="sxs-lookup"><span data-stu-id="1918c-272">The _IncludeFileExtensions_ property contains the list of file extensions that will be served from the CDN.</span></span>

> [!NOTE]
> <span data-ttu-id="1918c-273">Standardtilläggen för filer skiljer sig åt mellan offentliga och privata.</span><span class="sxs-lookup"><span data-stu-id="1918c-273">The default file extensions are different between public and private.</span></span>

<span data-ttu-id="1918c-274">Egenskapen _ExcludeRestrictedSiteClassifications_ innehåller webbplatsklassificeringarna som du vill utesluta från CDN.</span><span class="sxs-lookup"><span data-stu-id="1918c-274">The _ExcludeRestrictedSiteClassifications_ property contains the site classifications that you want to exclude from the CDN.</span></span> <span data-ttu-id="1918c-275">Du kan till exempel utesluta webbplatser som markerats som **konfidentiella** så att innehåll från webbplatser med den klassificering som tillämpas inte kommer att användas från CDN.</span><span class="sxs-lookup"><span data-stu-id="1918c-275">For example, you can exclude sites marked as **Confidential** so content from sites with that classification applied will not be served from the CDN.</span></span>

<span data-ttu-id="1918c-276">Egenskapen _ExcludeIfNoScriptDisabled_ utesluter innehåll från CDN baserat på inställningar för _NoScript-attribut_ på webbplatsnivå.</span><span class="sxs-lookup"><span data-stu-id="1918c-276">The _ExcludeIfNoScriptDisabled_ property excludes content from the CDN based on the site-level _NoScript_ attribute settings.</span></span> <span data-ttu-id="1918c-277">Som standard är _attributet NoScript_ inställt på **Aktiverad för** _moderna_ webbplatser och **Inaktiverat** för _klassiska_ webbplatser.</span><span class="sxs-lookup"><span data-stu-id="1918c-277">By default, the _NoScript_ attribute is set to **Enabled** for _Modern_ sites and **Disabled** for _Classic_ sites.</span></span> <span data-ttu-id="1918c-278">Det beror på klientorganisationens inställningar.</span><span class="sxs-lookup"><span data-stu-id="1918c-278">This depends on your tenant settings.</span></span>

<span data-ttu-id="1918c-279">Mer information om dessa cmdlets finns i [Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) och [Get-SPOTenantCdnPolicies.](/powershell/module/sharepoint-online/)</span><span class="sxs-lookup"><span data-stu-id="1918c-279">For more information about these cmdlets, see [Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) and [Get-SPOTenantCdnPolicies](/powershell/module/sharepoint-online/).</span></span>

<span data-ttu-id="1918c-280"><a name="Office365CDNforSPOOriginPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="1918c-280"><a name="Office365CDNforSPOOriginPosh"> </a></span></span>
### <a name="add-an-origin-for-your-assets"></a><span data-ttu-id="1918c-281">Lägga till ett ursprung för dina tillgångar</span><span class="sxs-lookup"><span data-stu-id="1918c-281">Add an origin for your assets</span></span>

<span data-ttu-id="1918c-282">Definiera ett **ursprung med cmdleten Add-SPOTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="1918c-282">Use the **Add-SPOTenantCdnOrigin** cmdlet to define an origin.</span></span> <span data-ttu-id="1918c-283">Du kan definiera flera ursprung.</span><span class="sxs-lookup"><span data-stu-id="1918c-283">You can define multiple origins.</span></span> <span data-ttu-id="1918c-284">Ursprunget är en URL-adress som pekar på ett bibliotek eller en mapp i SharePoint som innehåller tillgångarna du vill ska lagras av CDN.</span><span class="sxs-lookup"><span data-stu-id="1918c-284">The origin is a URL that points to a SharePoint library or folder that contains the assets that you want to be hosted by the CDN.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1918c-285">Du ska aldrig placera resurser som innehåller användarinformation eller som anses vara känsliga för organisationen i ett offentligt ursprung.</span><span class="sxs-lookup"><span data-stu-id="1918c-285">You should never place resources that contain user information or are considered sensitive to your organization in a public origin.</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

<span data-ttu-id="1918c-286">Värdet på _sökvägen_ är den relativa sökvägen till biblioteket eller mappen som innehåller tillgångarna.</span><span class="sxs-lookup"><span data-stu-id="1918c-286">The value of _path_ is the relative path to the library or folder that contains the assets.</span></span> <span data-ttu-id="1918c-287">Du kan använda jokertecken utöver relativa sökvägar.</span><span class="sxs-lookup"><span data-stu-id="1918c-287">You can use wildcards in addition to relative paths.</span></span> <span data-ttu-id="1918c-288">Ursprung stöder jokertecken som finns i url-adressen.</span><span class="sxs-lookup"><span data-stu-id="1918c-288">Origins support wildcards prepended to the URL.</span></span> <span data-ttu-id="1918c-289">På så sätt kan du skapa ursprung som spänner över flera webbplatser.</span><span class="sxs-lookup"><span data-stu-id="1918c-289">This allows you to create origins that span multiple sites.</span></span> <span data-ttu-id="1918c-290">Om du till exempel vill ta med alla tillgångar i mappen masterpages för alla dina webbplatser som ett offentligt ursprung i CDN skriver du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="1918c-290">For example, to include all of the assets in the masterpages folder for all of your sites as a public origin within the CDN, type the following command:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ <span data-ttu-id="1918c-291">Jokertecknet \* kan bara användas i början av sökvägen och matchar **/** alla URL-segment under den angivna URL:en.</span><span class="sxs-lookup"><span data-stu-id="1918c-291">The wildcard modifier \***/** can only be used at the beginning of the path, and will match all URL segments under the specified URL.</span></span>
+ <span data-ttu-id="1918c-292">Sökvägen kan peka på ett dokumentbibliotek, en mapp eller en webbplats.</span><span class="sxs-lookup"><span data-stu-id="1918c-292">The path can point to a document library, folder or site.</span></span> <span data-ttu-id="1918c-293">Sökvägen _\*/webbplats1_ matchar till exempel alla dokumentbibliotek under webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="1918c-293">For example, the path _\*/site1_ will match all the document libraries under the site.</span></span>

<span data-ttu-id="1918c-294">Du kan lägga till ett ursprung med en viss relativ sökväg.</span><span class="sxs-lookup"><span data-stu-id="1918c-294">You can add an origin with a specific relative path.</span></span> <span data-ttu-id="1918c-295">Du kan inte lägga till ett ursprung med den fullständiga sökvägen.</span><span class="sxs-lookup"><span data-stu-id="1918c-295">You cannot add an origin using the full path.</span></span>

<span data-ttu-id="1918c-296">I det här exemplet läggs ett privat ursprung till webbplatssamlingsbiblioteket på en viss webbplats:</span><span class="sxs-lookup"><span data-stu-id="1918c-296">This example adds a private origin of the siteassets library on a specific site:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="1918c-297">Det här exemplet lägger till ett privat ursprung _för mappen mapp1_ i webbplatssamlingens bibliotek för webbplatstillgångar:</span><span class="sxs-lookup"><span data-stu-id="1918c-297">This example adds a private origin of the _folder1_ folder in the site collection's site assets library:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

<span data-ttu-id="1918c-298">Om det finns ett blanksteg i sökvägen kan du antingen omge sökvägen med dubbla citattecken eller ersätta blanksteget med URL-kodningen %20.</span><span class="sxs-lookup"><span data-stu-id="1918c-298">If there is a space in the path, you can either surround the path in double quotes or replace the space with the URL encoding %20.</span></span> <span data-ttu-id="1918c-299">Följande exempel lägger till ett privat ursprung för _mappen mapp 1_ i webbplatssamlingens bibliotek för webbplatstillgångar:</span><span class="sxs-lookup"><span data-stu-id="1918c-299">The following examples add a private origin of the _folder 1_ folder in the site collection's site assets library:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

<span data-ttu-id="1918c-300">Mer information om kommandot och dess syntax finns i [Add-SPOTenantCdnOrigin.](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin)</span><span class="sxs-lookup"><span data-stu-id="1918c-300">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span></span>

> [!NOTE]
> <span data-ttu-id="1918c-301">I privata ursprung måste tillgångar som delas från ett ursprung ha en huvudversion publicerad innan de kan nås från CDN.</span><span class="sxs-lookup"><span data-stu-id="1918c-301">In private origins, assets being shared from an origin must have a major version published before they can be accessed from the CDN.</span></span>
  
<span data-ttu-id="1918c-302">När du har kört kommandot synkroniserar systemet konfigurationen i datacentret.</span><span class="sxs-lookup"><span data-stu-id="1918c-302">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="1918c-303">Det kan ta upp till 15 minuter.</span><span class="sxs-lookup"><span data-stu-id="1918c-303">This can take up to 15 minutes.</span></span>

<span data-ttu-id="1918c-304"><a name="ExamplePublicOrigin"> </a></span><span class="sxs-lookup"><span data-stu-id="1918c-304"><a name="ExamplePublicOrigin"> </a></span></span>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a><span data-ttu-id="1918c-305">Exempel: Konfigurera ett offentligt ursprung för huvudsidorna och för formatbiblioteket för SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="1918c-305">Example: Configure a public origin for your master pages and for your style library for SharePoint Online</span></span>

<span data-ttu-id="1918c-306">Normalt konfigureras dessa ursprung åt dig som standard när du aktiverar Office 365 CDN.</span><span class="sxs-lookup"><span data-stu-id="1918c-306">Normally, these origins are set up for you by default when you enable the Office 365 CDN.</span></span> <span data-ttu-id="1918c-307">Men om du vill aktivera dem manuellt följer du de här stegen.</span><span class="sxs-lookup"><span data-stu-id="1918c-307">However, if you want to enable them manually, follow these steps.</span></span>
  
+ <span data-ttu-id="1918c-308">Använd **cmdleten Add-SPOTenantCdnOrigin** till att definiera formatbiblioteket som ett offentligt ursprung.</span><span class="sxs-lookup"><span data-stu-id="1918c-308">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the style library as a public origin.</span></span>

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ <span data-ttu-id="1918c-309">Använd **cmdleten Add-SPOTenantCdnOrigin** till att definiera huvudsidorna som ett offentligt ursprung.</span><span class="sxs-lookup"><span data-stu-id="1918c-309">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the master pages as a public origin.</span></span>

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

<span data-ttu-id="1918c-310">Mer information om kommandot och dess syntax finns i [Add-SPOTenantCdnOrigin.](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin)</span><span class="sxs-lookup"><span data-stu-id="1918c-310">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span></span>

<span data-ttu-id="1918c-311">När du har kört kommandot synkroniserar systemet konfigurationen i datacentret.</span><span class="sxs-lookup"><span data-stu-id="1918c-311">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="1918c-312">Det kan ta upp till 15 minuter.</span><span class="sxs-lookup"><span data-stu-id="1918c-312">This can take up to 15 minutes.</span></span>

<span data-ttu-id="1918c-313"><a name="ExamplePrivateOrigin"> </a></span><span class="sxs-lookup"><span data-stu-id="1918c-313"><a name="ExamplePrivateOrigin"> </a></span></span>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a><span data-ttu-id="1918c-314">Exempel: Konfigurera ett privat ursprung för dina webbplatstillgångar, webbplatssidor och publiceringsbilder för SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="1918c-314">Example: Configure a private origin for your site assets, site pages, and publishing images for SharePoint Online</span></span>

+ <span data-ttu-id="1918c-315">Använd **cmdleten Add-SPOTenantCdnOrigin** till att definiera mappen för webbplatstillgångar som ett privat ursprung.</span><span class="sxs-lookup"><span data-stu-id="1918c-315">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the site assets folder as a private origin.</span></span>

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ <span data-ttu-id="1918c-316">Använd **cmdleten Add-SPOTenantCdnOrigin** till att definiera mappen för webbplatssidor som ett privat ursprung.</span><span class="sxs-lookup"><span data-stu-id="1918c-316">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the site pages folder as a private origin.</span></span>

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ <span data-ttu-id="1918c-317">Använd **cmdleten Add-SPOTenantCdnOrigin** till att definiera mappen för publiceringsbilder som ett privat ursprung.</span><span class="sxs-lookup"><span data-stu-id="1918c-317">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the publishing images folder as a private origin.</span></span>

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

<span data-ttu-id="1918c-318">Mer information om kommandot och dess syntax finns i [Add-SPOTenantCdnOrigin.](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin)</span><span class="sxs-lookup"><span data-stu-id="1918c-318">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span></span>

<span data-ttu-id="1918c-319">När du har kört kommandot synkroniserar systemet konfigurationen i datacentret.</span><span class="sxs-lookup"><span data-stu-id="1918c-319">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="1918c-320">Det kan ta upp till 15 minuter.</span><span class="sxs-lookup"><span data-stu-id="1918c-320">This can take up to 15 minutes.</span></span>

<span data-ttu-id="1918c-321"><a name="ExamplePrivateOriginSiteCollection"> </a></span><span class="sxs-lookup"><span data-stu-id="1918c-321"><a name="ExamplePrivateOriginSiteCollection"> </a></span></span>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a><span data-ttu-id="1918c-322">Exempel: Konfigurera ett privat ursprung för en webbplatssamling för SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="1918c-322">Example: Configure a private origin for a site collection for SharePoint Online</span></span>

<span data-ttu-id="1918c-323">Använd **cmdleten Add-SPOTenantCdnOrigin** till att definiera en webbplatssamling som ett privat ursprung.</span><span class="sxs-lookup"><span data-stu-id="1918c-323">Use the **Add-SPOTenantCdnOrigin** cmdlet to define a site collection as a private origin.</span></span> <span data-ttu-id="1918c-324">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="1918c-324">For example:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="1918c-325">Mer information om kommandot och dess syntax finns i [Add-SPOTenantCdnOrigin.](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin)</span><span class="sxs-lookup"><span data-stu-id="1918c-325">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span></span>
  
<span data-ttu-id="1918c-326">När du har kört kommandot synkroniserar systemet konfigurationen i datacentret.</span><span class="sxs-lookup"><span data-stu-id="1918c-326">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="1918c-327">Du kanske ser ett _meddelande om väntande_ konfiguration som förväntas när SharePoint Online-klienten ansluter till CDN-tjänsten.</span><span class="sxs-lookup"><span data-stu-id="1918c-327">You may see a _Configuration pending_ message which is expected as the SharePoint Online tenant connects to the CDN service.</span></span> <span data-ttu-id="1918c-328">Det kan ta upp till 15 minuter.</span><span class="sxs-lookup"><span data-stu-id="1918c-328">This can take up to 15 minutes.</span></span>

<span data-ttu-id="1918c-329"><a name="CDNManage"> </a></span><span class="sxs-lookup"><span data-stu-id="1918c-329"><a name="CDNManage"> </a></span></span>
### <a name="manage-the-office-365-cdn"></a><span data-ttu-id="1918c-330">Hantera Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="1918c-330">Manage the Office 365 CDN</span></span>

<span data-ttu-id="1918c-331">När du har ställt in CDN kan du göra ändringar i konfigurationen när du uppdaterar innehåll eller när dina behov ändras, enligt beskrivningen i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="1918c-331">Once you've set up the CDN, you can make changes to your configuration as you update content or as your needs change, as described in this section.</span></span>
  
<span data-ttu-id="1918c-332"><a name="Office365CDNforSPOaddremoveasset"> </a></span><span class="sxs-lookup"><span data-stu-id="1918c-332"><a name="Office365CDNforSPOaddremoveasset"> </a></span></span>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a><span data-ttu-id="1918c-333">Lägga till, uppdatera eller ta bort tillgångar från Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="1918c-333">Add, update, or remove assets from the Office 365 CDN</span></span>

<span data-ttu-id="1918c-334">När du har slutfört konfigurationsstegen kan du lägga till nya tillgångar och uppdatera eller ta bort befintliga tillgångar när du vill.</span><span class="sxs-lookup"><span data-stu-id="1918c-334">Once you've completed the setup steps, you can add new assets, and update or remove existing assets whenever you want.</span></span> <span data-ttu-id="1918c-335">Gör bara ändringar av tillgångarna i den mapp eller det SharePoint-bibliotek som du har identifierat som ursprung.</span><span class="sxs-lookup"><span data-stu-id="1918c-335">Just make your changes to the assets in the folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="1918c-336">Om du lägger till en ny tillgång är den tillgänglig via CDN direkt.</span><span class="sxs-lookup"><span data-stu-id="1918c-336">If you add a new asset, it is available through the CDN immediately.</span></span> <span data-ttu-id="1918c-337">Men om du uppdaterar tillgången tar det upp till 15 minuter för den nya kopian av spridas och bli tillgänglig i CDN.</span><span class="sxs-lookup"><span data-stu-id="1918c-337">However, if you update the asset, it will take up to 15 minutes for the new copy to propagate and become available in the CDN.</span></span>
  
<span data-ttu-id="1918c-338">Om du behöver hämta platsen för ursprunget kan du använda cmdleten **Get-SPOTenantCdnOrigins.**</span><span class="sxs-lookup"><span data-stu-id="1918c-338">If you need to retrieve the location of the origin, you can use the **Get-SPOTenantCdnOrigins** cmdlet.</span></span> <span data-ttu-id="1918c-339">Information om hur du använder denna cmdlet finns i [Get-SPOTenantCdnOrigins.](/powershell/module/sharepoint-online/Get-SPOTenantCdnOrigins)</span><span class="sxs-lookup"><span data-stu-id="1918c-339">For information on how to use this cmdlet, see [Get-SPOTenantCdnOrigins](/powershell/module/sharepoint-online/Get-SPOTenantCdnOrigins).</span></span>

<span data-ttu-id="1918c-340"><a name="Office365CDNforSPORemoveOriginPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="1918c-340"><a name="Office365CDNforSPORemoveOriginPosh"> </a></span></span>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a><span data-ttu-id="1918c-341">Ta bort ett ursprung från Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="1918c-341">Remove an origin from the Office 365 CDN</span></span>

<span data-ttu-id="1918c-342">Du kan ta bort åtkomst till en mapp eller ett SharePoint-bibliotek som du har identifierat som ursprung.</span><span class="sxs-lookup"><span data-stu-id="1918c-342">You can remove access to a folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="1918c-343">Det gör du med cmdleten **Remove-SPOTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="1918c-343">To do this, use the **Remove-SPOTenantCdnOrigin** cmdlet.</span></span>

``` powershell
Remove-SPOTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

<span data-ttu-id="1918c-344">Information om hur du använder denna cmdlet finns [i Remove-SPOTenantCdnOrigin.](/powershell/module/sharepoint-online/Remove-SPOTenantCdnOrigin)</span><span class="sxs-lookup"><span data-stu-id="1918c-344">For information on how to use this cmdlet, see [Remove-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Remove-SPOTenantCdnOrigin).</span></span>

<span data-ttu-id="1918c-345"><a name="Office365CDNforSPOModifyOrigin"> </a></span><span class="sxs-lookup"><span data-stu-id="1918c-345"><a name="Office365CDNforSPOModifyOrigin"> </a></span></span>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a><span data-ttu-id="1918c-346">Ändra ett ursprung i Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="1918c-346">Modify an origin in the Office 365 CDN</span></span>

<span data-ttu-id="1918c-347">Du kan inte ändra ett ursprung som du har skapat.</span><span class="sxs-lookup"><span data-stu-id="1918c-347">You cannot modify an origin you've created.</span></span> <span data-ttu-id="1918c-348">Ta istället bort ursprunget och lägg sedan till ett nytt.</span><span class="sxs-lookup"><span data-stu-id="1918c-348">Instead, remove the origin and then add a new one.</span></span> <span data-ttu-id="1918c-349">Mer information finns i Ta [bort ett ursprung från Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPosh) och Lägga till ett ursprung för dina [tillgångar.](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPosh)</span><span class="sxs-lookup"><span data-stu-id="1918c-349">For more information, see [To remove an origin from the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPosh) and [To add an origin for your assets](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPosh).</span></span>

<span data-ttu-id="1918c-350"><a name="Office365CDNforSPODisable"> </a></span><span class="sxs-lookup"><span data-stu-id="1918c-350"><a name="Office365CDNforSPODisable"> </a></span></span>
#### <a name="disable-the-office-365-cdn"></a><span data-ttu-id="1918c-351">Inaktivera Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="1918c-351">Disable the Office 365 CDN</span></span>

<span data-ttu-id="1918c-352">Använd **cmdleten Set-SPOTenantCdnEnabled** till att inaktivera CDN för organisationen.</span><span class="sxs-lookup"><span data-stu-id="1918c-352">Use the **Set-SPOTenantCdnEnabled** cmdlet to disable the CDN for your organization.</span></span> <span data-ttu-id="1918c-353">Om du har aktiverat både offentliga och privata ursprung för CDN måste du köra cmdleten två gånger enligt följande exempel.</span><span class="sxs-lookup"><span data-stu-id="1918c-353">If you have both the public and private origins enabled for the CDN, you need to run the cmdlet twice as shown in the following examples.</span></span>
  
<span data-ttu-id="1918c-354">Inaktivera användningen av offentliga ursprung i CDN genom att ange följande kommando:</span><span class="sxs-lookup"><span data-stu-id="1918c-354">To disable use of public origins in the CDN, enter the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $false
```

<span data-ttu-id="1918c-355">Inaktivera användningen av privata ursprung i CDN genom att ange följande kommando:</span><span class="sxs-lookup"><span data-stu-id="1918c-355">To disable use of the private origins in the CDN, enter the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $false
```

<span data-ttu-id="1918c-356">Mer information om den här cmdleten finns [i Set-SPOTenantCdnEnabled](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled).</span><span class="sxs-lookup"><span data-stu-id="1918c-356">For more information about this cmdlet, see [Set-SPOTenantCdnEnabled](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled).</span></span>

</details>

<span data-ttu-id="1918c-357"><a name="CDNSetupinPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="1918c-357"><a name="CDNSetupinPnPPosh"> </a></span></span>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-pnp-powershell"></a><span data-ttu-id="1918c-358">Konfigurera och konfigurera Office 365 CDN med PnP PowerShell</span><span class="sxs-lookup"><span data-stu-id="1918c-358">Set up and configure the Office 365 CDN by using PnP PowerShell</span></span>

<span data-ttu-id="1918c-359">Procedurerna i det här avsnittet kräver att du använder PnP PowerShell för att ansluta till SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="1918c-359">The procedures in this section require you to use PnP PowerShell to connect to SharePoint Online.</span></span> <span data-ttu-id="1918c-360">Anvisningar finns i [Komma igång med PnP PowerShell.](https://github.com/SharePoint/PnP-PowerShell#getting-started)</span><span class="sxs-lookup"><span data-stu-id="1918c-360">For instructions, see [Getting started with PnP PowerShell](https://github.com/SharePoint/PnP-PowerShell#getting-started).</span></span>

<span data-ttu-id="1918c-361">Utför de här stegen för att konfigurera och konfigurera CDN som värd för dina tillgångar i SharePoint Online med PnP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1918c-361">Complete these steps to set up and configure the CDN to host your assets in SharePoint Online using PnP PowerShell.</span></span>

<details>
  <summary><span data-ttu-id="1918c-362">Klicka för att Visa</span><span class="sxs-lookup"><span data-stu-id="1918c-362">Click to expand</span></span></summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a><span data-ttu-id="1918c-363">Aktivera organisationen för att använda Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="1918c-363">Enable your organization to use the Office 365 CDN</span></span>

<span data-ttu-id="1918c-364">Innan du gör ändringar i klientorganisationens CDN-inställningar bör du hämta aktuell status för den privata CDN-konfigurationen i Office 365-klienten.</span><span class="sxs-lookup"><span data-stu-id="1918c-364">Before you make changes to the tenant CDN settings, you should retrieve the current status of the private CDN configuration in your Office 365 tenant.</span></span> <span data-ttu-id="1918c-365">Anslut till klientorganisationen med PnP PowerShell:</span><span class="sxs-lookup"><span data-stu-id="1918c-365">Connect to your tenant using PnP PowerShell:</span></span>

``` powershell
Connect-PnPOnline -Url https://contoso-admin.sharepoint.com -UseWebLogin
```

<span data-ttu-id="1918c-366">Använd nu cmdleten **Get-PnPTenantCdnEnabled** för att hämta CDN-statusinställningarna från klientorganisationen:</span><span class="sxs-lookup"><span data-stu-id="1918c-366">Now use the **Get-PnPTenantCdnEnabled** cmdlet to retrieve the CDN status settings from the tenant:</span></span>

``` powershell
Get-PnPTenantCdnEnabled -CdnType <Public | Private>
```

<span data-ttu-id="1918c-367">Status för CDN för den angivna CdnType matas ut på skärmen.</span><span class="sxs-lookup"><span data-stu-id="1918c-367">The status of the CDN for the specified CdnType will output to the screen.</span></span>

<span data-ttu-id="1918c-368">Använd **cmdleten Set-PnPTenantCdnEnabled** till att aktivera organisationen för att använda Office 365 CDN.</span><span class="sxs-lookup"><span data-stu-id="1918c-368">Use the **Set-PnPTenantCdnEnabled** cmdlet to enable your organization to use the Office 365 CDN.</span></span> <span data-ttu-id="1918c-369">Du kan aktivera organisationen för att använda offentliga ursprung, privata ursprung eller båda samtidigt.</span><span class="sxs-lookup"><span data-stu-id="1918c-369">You can enable your organization to use public origins, private origins, or both at at the same time.</span></span> <span data-ttu-id="1918c-370">Du kan också konfigurera CDN att hoppa över konfigurationen av standard ursprung när du aktiverar det.</span><span class="sxs-lookup"><span data-stu-id="1918c-370">You can also configure the CDN to skip the setup of default origins when you enable it.</span></span> <span data-ttu-id="1918c-371">Du kan alltid lägga till dessa ursprung senare enligt beskrivningen i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="1918c-371">You can always add these origins later as described in this topic.</span></span>
  
<span data-ttu-id="1918c-372">I PnP PowerShell:</span><span class="sxs-lookup"><span data-stu-id="1918c-372">In PnP PowerShell:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

<span data-ttu-id="1918c-373">Om du till exempel vill aktivera organisationen för att använda både offentliga och privata ursprung skriver du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="1918c-373">For example, to enable your organization to use both public and private origins, type the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true
```

<span data-ttu-id="1918c-374">Om du vill aktivera organisationen för att använda både offentliga och privata ursprung men hoppa över att konfigurera standard ursprung skriver du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="1918c-374">To enable your organization to use both public and private origins but skip setting up the default origins, type the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

<span data-ttu-id="1918c-375">Mer information [om ursprung som etableras](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) som standard när du aktiverar Office 365 CDN finns i Standard-CDN-ursprung och eventuell inverkan med att hoppa över konfigurationen av standard ursprung.</span><span class="sxs-lookup"><span data-stu-id="1918c-375">See [Default CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) for information about the origins that are provisioned by default when you enable the Office 365 CDN, and the potential impact of skipping the setup of default origins.</span></span>

<span data-ttu-id="1918c-376">Om du vill aktivera organisationen för att använda offentliga ursprung skriver du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="1918c-376">To enable your organization to use public origins, type the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $true
```

<span data-ttu-id="1918c-377">Om du vill aktivera din organisation för att använda privata ursprung skriver du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="1918c-377">To enable your organization to use private origins, type the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $true
```

<span data-ttu-id="1918c-378">Mer information om den här cmdleten finns [i Set-PnPTenantCdnEnabled](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).</span><span class="sxs-lookup"><span data-stu-id="1918c-378">For more information about this cmdlet, see [Set-PnPTenantCdnEnabled](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).</span></span>

<span data-ttu-id="1918c-379"><a name="Office365CDNforPnPPoshFileType"> </a></span><span class="sxs-lookup"><span data-stu-id="1918c-379"><a name="Office365CDNforPnPPoshFileType"> </a></span></span>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a><span data-ttu-id="1918c-380">Ändra listan över filtyper som ska ingå i Office 365 CDN (valfritt)</span><span class="sxs-lookup"><span data-stu-id="1918c-380">Change the list of file types to include in the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="1918c-381">När du definierar filtyper med hjälp av cmdleten **Set-PnPTenantCdnPolicy** skriver du över den aktuella definierade listan.</span><span class="sxs-lookup"><span data-stu-id="1918c-381">When you define file types by using the **Set-PnPTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="1918c-382">Om du vill lägga till ytterligare filtyper i listan använder du först cmdleten för att ta reda på vilka filtyper som redan är tillåtna och inkludera dem i listan tillsammans med dina nya.</span><span class="sxs-lookup"><span data-stu-id="1918c-382">If you want to add additional file types to the list, use the cmdlet first to find out what file types are already allowed and include them in the list along with your new ones.</span></span>
  
<span data-ttu-id="1918c-383">Använd **cmdleten Set-PnPTenantCdnPolicy** till att definiera statiska filtyper som kan lagras av offentliga och privata ursprung i CDN.</span><span class="sxs-lookup"><span data-stu-id="1918c-383">Use the **Set-PnPTenantCdnPolicy** cmdlet to define static file types that can be hosted by public and private origins in the CDN.</span></span> <span data-ttu-id="1918c-384">Som standard tillåts vanliga tillgångstyper, till exempel .css, .gif, .jpg och .js.</span><span class="sxs-lookup"><span data-stu-id="1918c-384">By default, common asset types are allowed, for example .css, .gif, .jpg, and .js.</span></span>

<span data-ttu-id="1918c-385">I PnP PowerShell:</span><span class="sxs-lookup"><span data-stu-id="1918c-385">In PnP PowerShell:</span></span>

``` powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

<span data-ttu-id="1918c-386">Om du till exempel vill aktivera CDN som värd för .css- och .png-filer anger du kommandot:</span><span class="sxs-lookup"><span data-stu-id="1918c-386">For example, to enable the CDN to host .css and .png files, you would enter the command:</span></span>

``` powershell
Set-PnPTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

<span data-ttu-id="1918c-387">Om du vill se vilka filtyper som tillåts av CDN använder du cmdleten **Get-PnPTenantCdnPolicies:**</span><span class="sxs-lookup"><span data-stu-id="1918c-387">To see what file types are currently allowed by the CDN, use the **Get-PnPTenantCdnPolicies** cmdlet:</span></span>

``` powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="1918c-388">Mer information om dessa cmdlets finns i [Set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) och [Get-PnPTenantCdnPolicies.](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies)</span><span class="sxs-lookup"><span data-stu-id="1918c-388">For more information about these cmdlets, see [Set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) and [Get-PnPTenantCdnPolicies](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).</span></span>

<span data-ttu-id="1918c-389"><a name="Office365CDNforPnPPoshSiteClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="1918c-389"><a name="Office365CDNforPnPPoshSiteClassification"> </a></span></span>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a><span data-ttu-id="1918c-390">Ändra listan över webbplatsklassificeringarna som du vill utesluta från Office 365 CDN (valfritt)</span><span class="sxs-lookup"><span data-stu-id="1918c-390">Change the list of site classifications you want to exclude from the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="1918c-391">När du utesluter webbplatsklassificeringarna med hjälp av cmdleten **Set-PnPTenantCdnPolicy** skriver du över den aktuella definierade listan.</span><span class="sxs-lookup"><span data-stu-id="1918c-391">When you exclude site classifications by using the **Set-PnPTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="1918c-392">Om du vill utesluta ytterligare webbplatsklassificeringarna använder du cmdleten först för att ta reda på vilka klassificeringar som redan har uteslutits och sedan lägga till dem tillsammans med dina nya.</span><span class="sxs-lookup"><span data-stu-id="1918c-392">If you want to exclude additional site classifications, use the cmdlet first to find out what classifications are already excluded and then add them along with your new ones.</span></span>

<span data-ttu-id="1918c-393">Använd **cmdleten Set-PnPTenantCdnPolicy** till att utesluta webbplatsklassificeringarna som du inte vill ska vara tillgängliga via CDN.</span><span class="sxs-lookup"><span data-stu-id="1918c-393">Use the **Set-PnPTenantCdnPolicy** cmdlet to exclude site classifications that you do not want to make available over the CDN.</span></span> <span data-ttu-id="1918c-394">Som standard utesluts inga webbplatsklassificeringar.</span><span class="sxs-lookup"><span data-stu-id="1918c-394">By default, no site classifications are excluded.</span></span>

<span data-ttu-id="1918c-395">I PnP PowerShell:</span><span class="sxs-lookup"><span data-stu-id="1918c-395">In PnP PowerShell:</span></span>

``` powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications>"
```

<span data-ttu-id="1918c-396">Om du vill se vilka webbplatsklassificeringarna är begränsade använder du cmdleten **Get-PnPTenantCdnPolicies:**</span><span class="sxs-lookup"><span data-stu-id="1918c-396">To see what site classifications are currently restricted, use the **Get-PnPTenantCdnPolicies** cmdlet:</span></span>

``` powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="1918c-397">Egenskaperna som returneras är _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ _och ExcludeIfNoScriptDisabled._</span><span class="sxs-lookup"><span data-stu-id="1918c-397">The properties that will be returned are _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ and _ExcludeIfNoScriptDisabled_.</span></span>

<span data-ttu-id="1918c-398">Egenskapen _IncludeFileExtensions_ innehåller listan över filnamnstillägg som kan användas i CDN.</span><span class="sxs-lookup"><span data-stu-id="1918c-398">The _IncludeFileExtensions_ property contains the list of file extensions that will be served from the CDN.</span></span>

> [!NOTE]
> <span data-ttu-id="1918c-399">Standardtilläggen för filer skiljer sig åt mellan offentliga och privata.</span><span class="sxs-lookup"><span data-stu-id="1918c-399">The default file extensions are different between public and private.</span></span>

<span data-ttu-id="1918c-400">Egenskapen _ExcludeRestrictedSiteClassifications_ innehåller webbplatsklassificeringarna som du vill utesluta från CDN.</span><span class="sxs-lookup"><span data-stu-id="1918c-400">The _ExcludeRestrictedSiteClassifications_ property contains the site classifications that you want to exclude from the CDN.</span></span> <span data-ttu-id="1918c-401">Du kan till exempel utesluta webbplatser som markerats som **konfidentiella** så att innehåll från webbplatser med den klassificering som tillämpas inte kommer att användas från CDN.</span><span class="sxs-lookup"><span data-stu-id="1918c-401">For example, you can exclude sites marked as **Confidential** so content from sites with that classification applied will not be served from the CDN.</span></span>

<span data-ttu-id="1918c-402">Egenskapen _ExcludeIfNoScriptDisabled_ utesluter innehåll från CDN baserat på inställningar för _NoScript-attribut_ på webbplatsnivå.</span><span class="sxs-lookup"><span data-stu-id="1918c-402">The _ExcludeIfNoScriptDisabled_ property excludes content from the CDN based on the site-level _NoScript_ attribute settings.</span></span> <span data-ttu-id="1918c-403">Som standard är _attributet NoScript_ inställt på **Aktiverad för** _moderna_ webbplatser och **Inaktiverat** för _klassiska_ webbplatser.</span><span class="sxs-lookup"><span data-stu-id="1918c-403">By default, the _NoScript_ attribute is set to **Enabled** for _Modern_ sites and **Disabled** for _Classic_ sites.</span></span> <span data-ttu-id="1918c-404">Det beror på klientorganisationens inställningar.</span><span class="sxs-lookup"><span data-stu-id="1918c-404">This depends on your tenant settings.</span></span>

<span data-ttu-id="1918c-405">Mer information om dessa cmdlets finns i [Set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) och [Get-PnPTenantCdnPolicies.](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies)</span><span class="sxs-lookup"><span data-stu-id="1918c-405">For more information about these cmdlets, see [Set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) and [Get-PnPTenantCdnPolicies](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).</span></span>

<span data-ttu-id="1918c-406"><a name="Office365CDNforSPOOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="1918c-406"><a name="Office365CDNforSPOOriginPnPPosh"> </a></span></span>
### <a name="add-an-origin-for-your-assets"></a><span data-ttu-id="1918c-407">Lägga till ett ursprung för dina tillgångar</span><span class="sxs-lookup"><span data-stu-id="1918c-407">Add an origin for your assets</span></span>

<span data-ttu-id="1918c-408">Definiera ett **ursprung med cmdleten Add-PnPTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="1918c-408">Use the **Add-PnPTenantCdnOrigin** cmdlet to define an origin.</span></span> <span data-ttu-id="1918c-409">Du kan definiera flera ursprung.</span><span class="sxs-lookup"><span data-stu-id="1918c-409">You can define multiple origins.</span></span> <span data-ttu-id="1918c-410">Ursprunget är en URL-adress som pekar på ett bibliotek eller en mapp i SharePoint som innehåller tillgångarna du vill ska lagras av CDN.</span><span class="sxs-lookup"><span data-stu-id="1918c-410">The origin is a URL that points to a SharePoint library or folder that contains the assets that you want to be hosted by the CDN.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1918c-411">Du ska aldrig placera resurser som innehåller användarinformation eller som anses vara känsliga för organisationen i ett offentligt ursprung.</span><span class="sxs-lookup"><span data-stu-id="1918c-411">You should never place resources that contain user information or are considered sensitive to your organization in a public origin.</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

<span data-ttu-id="1918c-412">Värdet på _sökvägen_ är den relativa sökvägen till biblioteket eller mappen som innehåller tillgångarna.</span><span class="sxs-lookup"><span data-stu-id="1918c-412">The value of _path_ is the relative path to the library or folder that contains the assets.</span></span> <span data-ttu-id="1918c-413">Du kan använda jokertecken utöver relativa sökvägar.</span><span class="sxs-lookup"><span data-stu-id="1918c-413">You can use wildcards in addition to relative paths.</span></span> <span data-ttu-id="1918c-414">Ursprung stöder jokertecken som finns i url-adressen.</span><span class="sxs-lookup"><span data-stu-id="1918c-414">Origins support wildcards prepended to the URL.</span></span> <span data-ttu-id="1918c-415">På så sätt kan du skapa ursprung som spänner över flera webbplatser.</span><span class="sxs-lookup"><span data-stu-id="1918c-415">This allows you to create origins that span multiple sites.</span></span> <span data-ttu-id="1918c-416">Om du till exempel vill ta med alla tillgångar i mappen masterpages för alla dina webbplatser som ett offentligt ursprung i CDN skriver du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="1918c-416">For example, to include all of the assets in the masterpages folder for all of your sites as a public origin within the CDN, type the following command:</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ <span data-ttu-id="1918c-417">Jokertecknet \* kan bara användas i början av sökvägen och matchar **/** alla URL-segment under den angivna URL:en.</span><span class="sxs-lookup"><span data-stu-id="1918c-417">The wildcard modifier \***/** can only be used at the beginning of the path, and will match all URL segments under the specified URL.</span></span>
+ <span data-ttu-id="1918c-418">Sökvägen kan peka på ett dokumentbibliotek, en mapp eller en webbplats.</span><span class="sxs-lookup"><span data-stu-id="1918c-418">The path can point to a document library, folder or site.</span></span> <span data-ttu-id="1918c-419">Sökvägen _\*/webbplats1_ matchar till exempel alla dokumentbibliotek under webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="1918c-419">For example, the path _\*/site1_ will match all the document libraries under the site.</span></span>

<span data-ttu-id="1918c-420">Du kan lägga till ett ursprung med en viss relativ sökväg.</span><span class="sxs-lookup"><span data-stu-id="1918c-420">You can add an origin with a specific relative path.</span></span> <span data-ttu-id="1918c-421">Du kan inte lägga till ett ursprung med den fullständiga sökvägen.</span><span class="sxs-lookup"><span data-stu-id="1918c-421">You cannot add an origin using the full path.</span></span>

<span data-ttu-id="1918c-422">I det här exemplet läggs ett privat ursprung till biblioteket med webbplatstillgångar till på en viss webbplats:</span><span class="sxs-lookup"><span data-stu-id="1918c-422">This example adds a private origin of the site assets library on a specific site:</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="1918c-423">Det här exemplet lägger till ett privat ursprung _för mappen mapp1_ i webbplatssamlingens bibliotek för webbplatstillgångar:</span><span class="sxs-lookup"><span data-stu-id="1918c-423">This example adds a private origin of the _folder1_ folder in the site collection's site assets library:</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

<span data-ttu-id="1918c-424">Om det finns ett blanksteg i sökvägen kan du antingen omge sökvägen med dubbla citattecken eller ersätta blanksteget med URL-kodningen %20.</span><span class="sxs-lookup"><span data-stu-id="1918c-424">If there is a space in the path, you can either surround the path in double quotes or replace the space with the URL encoding %20.</span></span> <span data-ttu-id="1918c-425">Följande exempel lägger till ett privat ursprung för _mappen mapp 1_ i webbplatssamlingens bibliotek för webbplatstillgångar:</span><span class="sxs-lookup"><span data-stu-id="1918c-425">The following examples add a private origin of the _folder 1_ folder in the site collection's site assets library:</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

<span data-ttu-id="1918c-426">Mer information om kommandot och dess syntax finns i [Add-PnPTenantCdnOrigin.](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)</span><span class="sxs-lookup"><span data-stu-id="1918c-426">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

> [!NOTE]
> <span data-ttu-id="1918c-427">I privata ursprung måste tillgångar som delas från ett ursprung ha en huvudversion publicerad innan de kan nås från CDN.</span><span class="sxs-lookup"><span data-stu-id="1918c-427">In private origins, assets being shared from an origin must have a major version published before they can be accessed from the CDN.</span></span>
  
<span data-ttu-id="1918c-428">När du har kört kommandot synkroniserar systemet konfigurationen i datacentret.</span><span class="sxs-lookup"><span data-stu-id="1918c-428">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="1918c-429">Det kan ta upp till 15 minuter.</span><span class="sxs-lookup"><span data-stu-id="1918c-429">This can take up to 15 minutes.</span></span>

<span data-ttu-id="1918c-430"><a name="ExamplePublicOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="1918c-430"><a name="ExamplePublicOriginPnPPosh"> </a></span></span>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a><span data-ttu-id="1918c-431">Exempel: Konfigurera ett offentligt ursprung för huvudsidorna och för formatbiblioteket för SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="1918c-431">Example: Configure a public origin for your master pages and for your style library for SharePoint Online</span></span>

<span data-ttu-id="1918c-432">Normalt konfigureras dessa ursprung åt dig som standard när du aktiverar Office 365 CDN.</span><span class="sxs-lookup"><span data-stu-id="1918c-432">Normally, these origins are set up for you by default when you enable the Office 365 CDN.</span></span> <span data-ttu-id="1918c-433">Men om du vill aktivera dem manuellt följer du de här stegen.</span><span class="sxs-lookup"><span data-stu-id="1918c-433">However, if you want to enable them manually, follow these steps.</span></span>
  
+ <span data-ttu-id="1918c-434">Använd **cmdleten Add-PnPTenantCdnOrigin** till att definiera formatbiblioteket som ett offentligt ursprung.</span><span class="sxs-lookup"><span data-stu-id="1918c-434">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the style library as a public origin.</span></span>

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ <span data-ttu-id="1918c-435">Använd **cmdleten Add-PnPTenantCdnOrigin** till att definiera huvudsidorna som ett offentligt ursprung.</span><span class="sxs-lookup"><span data-stu-id="1918c-435">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the master pages as a public origin.</span></span>

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

<span data-ttu-id="1918c-436">Mer information om kommandot och dess syntax finns i [Add-PnPTenantCdnOrigin.](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)</span><span class="sxs-lookup"><span data-stu-id="1918c-436">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

<span data-ttu-id="1918c-437">När du har kört kommandot synkroniserar systemet konfigurationen i datacentret.</span><span class="sxs-lookup"><span data-stu-id="1918c-437">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="1918c-438">Det kan ta upp till 15 minuter.</span><span class="sxs-lookup"><span data-stu-id="1918c-438">This can take up to 15 minutes.</span></span>

<span data-ttu-id="1918c-439"><a name="ExamplePrivateOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="1918c-439"><a name="ExamplePrivateOriginPnPPosh"> </a></span></span>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a><span data-ttu-id="1918c-440">Exempel: Konfigurera ett privat ursprung för dina webbplatstillgångar, webbplatssidor och publiceringsbilder för SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="1918c-440">Example: Configure a private origin for your site assets, site pages, and publishing images for SharePoint Online</span></span>

+ <span data-ttu-id="1918c-441">Använd **cmdleten Add-PnPTenantCdnOrigin** till att definiera mappen för webbplatstillgångar som ett privat ursprung.</span><span class="sxs-lookup"><span data-stu-id="1918c-441">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the site assets folder as a private origin.</span></span>

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ <span data-ttu-id="1918c-442">Använd **cmdleten Add-PnPTenantCdnOrigin** till att definiera mappen för webbplatssidor som ett privat ursprung.</span><span class="sxs-lookup"><span data-stu-id="1918c-442">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the site pages folder as a private origin.</span></span>

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ <span data-ttu-id="1918c-443">Använd **cmdleten Add-PnPTenantCdnOrigin** till att definiera mappen för publiceringsbilder som ett privat ursprung.</span><span class="sxs-lookup"><span data-stu-id="1918c-443">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the publishing images folder as a private origin.</span></span>

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

<span data-ttu-id="1918c-444">Mer information om kommandot och dess syntax finns i [Add-PnPTenantCdnOrigin.](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)</span><span class="sxs-lookup"><span data-stu-id="1918c-444">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

<span data-ttu-id="1918c-445">När du har kört kommandot synkroniserar systemet konfigurationen i datacentret.</span><span class="sxs-lookup"><span data-stu-id="1918c-445">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="1918c-446">Det kan ta upp till 15 minuter.</span><span class="sxs-lookup"><span data-stu-id="1918c-446">This can take up to 15 minutes.</span></span>

<span data-ttu-id="1918c-447"><a name="ExamplePrivateOriginSiteCollectionPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="1918c-447"><a name="ExamplePrivateOriginSiteCollectionPnPPosh"> </a></span></span>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a><span data-ttu-id="1918c-448">Exempel: Konfigurera ett privat ursprung för en webbplatssamling för SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="1918c-448">Example: Configure a private origin for a site collection for SharePoint Online</span></span>

<span data-ttu-id="1918c-449">Använd **cmdleten Add-PnPTenantCdnOrigin** till att definiera en webbplatssamling som ett privat ursprung.</span><span class="sxs-lookup"><span data-stu-id="1918c-449">Use the **Add-PnPTenantCdnOrigin** cmdlet to define a site collection as a private origin.</span></span> <span data-ttu-id="1918c-450">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="1918c-450">For example:</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="1918c-451">Mer information om kommandot och dess syntax finns i [Add-PnPTenantCdnOrigin.](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)</span><span class="sxs-lookup"><span data-stu-id="1918c-451">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>
  
<span data-ttu-id="1918c-452">När du har kört kommandot synkroniserar systemet konfigurationen i datacentret.</span><span class="sxs-lookup"><span data-stu-id="1918c-452">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="1918c-453">Du kanske ser ett _meddelande om väntande_ konfiguration som förväntas när SharePoint Online-klienten ansluter till CDN-tjänsten.</span><span class="sxs-lookup"><span data-stu-id="1918c-453">You may see a _Configuration pending_ message which is expected as the SharePoint Online tenant connects to the CDN service.</span></span> <span data-ttu-id="1918c-454">Det kan ta upp till 15 minuter.</span><span class="sxs-lookup"><span data-stu-id="1918c-454">This can take up to 15 minutes.</span></span>

<span data-ttu-id="1918c-455"><a name="CDNManagePnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="1918c-455"><a name="CDNManagePnPPosh"> </a></span></span>
### <a name="manage-the-office-365-cdn"></a><span data-ttu-id="1918c-456">Hantera Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="1918c-456">Manage the Office 365 CDN</span></span>

<span data-ttu-id="1918c-457">När du har ställt in CDN kan du göra ändringar i konfigurationen när du uppdaterar innehåll eller när dina behov ändras, enligt beskrivningen i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="1918c-457">Once you've set up the CDN, you can make changes to your configuration as you update content or as your needs change, as described in this section.</span></span>
  
<span data-ttu-id="1918c-458"><a name="Office365CDNforSPOaddremoveassetPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="1918c-458"><a name="Office365CDNforSPOaddremoveassetPnPPosh"> </a></span></span>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a><span data-ttu-id="1918c-459">Lägga till, uppdatera eller ta bort tillgångar från Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="1918c-459">Add, update, or remove assets from the Office 365 CDN</span></span>

<span data-ttu-id="1918c-460">När du har slutfört konfigurationsstegen kan du lägga till nya tillgångar och uppdatera eller ta bort befintliga tillgångar när du vill.</span><span class="sxs-lookup"><span data-stu-id="1918c-460">Once you've completed the setup steps, you can add new assets, and update or remove existing assets whenever you want.</span></span> <span data-ttu-id="1918c-461">Gör bara ändringar av tillgångarna i den mapp eller det SharePoint-bibliotek som du har identifierat som ursprung.</span><span class="sxs-lookup"><span data-stu-id="1918c-461">Just make your changes to the assets in the folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="1918c-462">Om du lägger till en ny tillgång är den tillgänglig via CDN direkt.</span><span class="sxs-lookup"><span data-stu-id="1918c-462">If you add a new asset, it is available through the CDN immediately.</span></span> <span data-ttu-id="1918c-463">Men om du uppdaterar tillgången tar det upp till 15 minuter för den nya kopian av spridas och bli tillgänglig i CDN.</span><span class="sxs-lookup"><span data-stu-id="1918c-463">However, if you update the asset, it will take up to 15 minutes for the new copy to propagate and become available in the CDN.</span></span>
  
<span data-ttu-id="1918c-464">Om du behöver hämta platsen för ursprunget kan du använda cmdleten **Get-PnPTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="1918c-464">If you need to retrieve the location of the origin, you can use the **Get-PnPTenantCdnOrigin** cmdlet.</span></span> <span data-ttu-id="1918c-465">Information om hur du använder denna cmdlet finns i [Get-PnPTenantCdnOrigin.](/powershell/module/sharepoint-pnp/get-pnptenantcdnorigin)</span><span class="sxs-lookup"><span data-stu-id="1918c-465">For information on how to use this cmdlet, see [Get-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/get-pnptenantcdnorigin).</span></span>

<span data-ttu-id="1918c-466"><a name="Office365CDNforSPORemoveOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="1918c-466"><a name="Office365CDNforSPORemoveOriginPnPPosh"> </a></span></span>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a><span data-ttu-id="1918c-467">Ta bort ett ursprung från Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="1918c-467">Remove an origin from the Office 365 CDN</span></span>

<span data-ttu-id="1918c-468">Du kan ta bort åtkomst till en mapp eller ett SharePoint-bibliotek som du har identifierat som ursprung.</span><span class="sxs-lookup"><span data-stu-id="1918c-468">You can remove access to a folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="1918c-469">Det gör du med cmdleten **Remove-PnPTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="1918c-469">To do this, use the **Remove-PnPTenantCdnOrigin** cmdlet.</span></span>

``` powershell
Remove-PnPTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

<span data-ttu-id="1918c-470">Information om hur du använder denna cmdlet finns [i Remove-PnPTenantCdnOrigin.](/powershell/module/sharepoint-pnp/remove-pnptenantcdnorigin)</span><span class="sxs-lookup"><span data-stu-id="1918c-470">For information on how to use this cmdlet, see [Remove-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/remove-pnptenantcdnorigin).</span></span>

<span data-ttu-id="1918c-471"><a name="Office365CDNforSPOModifyOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="1918c-471"><a name="Office365CDNforSPOModifyOriginPnPPosh"> </a></span></span>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a><span data-ttu-id="1918c-472">Ändra ett ursprung i Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="1918c-472">Modify an origin in the Office 365 CDN</span></span>

<span data-ttu-id="1918c-473">Du kan inte ändra ett ursprung som du har skapat.</span><span class="sxs-lookup"><span data-stu-id="1918c-473">You cannot modify an origin you've created.</span></span> <span data-ttu-id="1918c-474">Ta istället bort ursprunget och lägg sedan till ett nytt.</span><span class="sxs-lookup"><span data-stu-id="1918c-474">Instead, remove the origin and then add a new one.</span></span> <span data-ttu-id="1918c-475">Mer information finns i Ta [bort ett ursprung från Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPnPPosh) och Lägga till ett ursprung för dina [tillgångar.](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPnPPosh)</span><span class="sxs-lookup"><span data-stu-id="1918c-475">For more information, see [To remove an origin from the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPnPPosh) and [To add an origin for your assets](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPnPPosh).</span></span>

<span data-ttu-id="1918c-476"><a name="Office365CDNforSPODisable"> </a></span><span class="sxs-lookup"><span data-stu-id="1918c-476"><a name="Office365CDNforSPODisable"> </a></span></span>
#### <a name="disable-the-office-365-cdn"></a><span data-ttu-id="1918c-477">Inaktivera Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="1918c-477">Disable the Office 365 CDN</span></span>

<span data-ttu-id="1918c-478">Använd **cmdleten Set-PnPTenantCdnEnabled** till att inaktivera CDN för organisationen.</span><span class="sxs-lookup"><span data-stu-id="1918c-478">Use the **Set-PnPTenantCdnEnabled** cmdlet to disable the CDN for your organization.</span></span> <span data-ttu-id="1918c-479">Om du har aktiverat både offentliga och privata ursprung för CDN måste du köra cmdleten två gånger enligt följande exempel.</span><span class="sxs-lookup"><span data-stu-id="1918c-479">If you have both the public and private origins enabled for the CDN, you need to run the cmdlet twice as shown in the following examples.</span></span>
  
<span data-ttu-id="1918c-480">Inaktivera användningen av offentliga ursprung i CDN genom att ange följande kommando:</span><span class="sxs-lookup"><span data-stu-id="1918c-480">To disable use of public origins in the CDN, enter the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $false
```

<span data-ttu-id="1918c-481">Inaktivera användningen av privata ursprung i CDN genom att ange följande kommando:</span><span class="sxs-lookup"><span data-stu-id="1918c-481">To disable use of the private origins in the CDN, enter the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $false
```

<span data-ttu-id="1918c-482">Mer information om den här cmdleten finns [i Set-PnPTenantCdnEnabled](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).</span><span class="sxs-lookup"><span data-stu-id="1918c-482">For more information about this cmdlet, see [Set-PnPTenantCdnEnabled](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).</span></span>

</details>

<span data-ttu-id="1918c-483"><a name="CDNSetupinCLI"> </a></span><span class="sxs-lookup"><span data-stu-id="1918c-483"><a name="CDNSetupinCLI"> </a></span></span>
## <a name="set-up-and-configure-the-office-365-cdn-using-the-office-365-cli"></a><span data-ttu-id="1918c-484">Konfigurera och konfigurera Office 365 CDN med hjälp av Office 365 CLI</span><span class="sxs-lookup"><span data-stu-id="1918c-484">Set up and configure the Office 365 CDN using the Office 365 CLI</span></span>

<span data-ttu-id="1918c-485">Procedurerna i det här avsnittet kräver att du har installerat [Office 365 CLI.](https://aka.ms/o365cli)</span><span class="sxs-lookup"><span data-stu-id="1918c-485">The procedures in this section require that you have installed the [Office 365 CLI](https://aka.ms/o365cli).</span></span> <span data-ttu-id="1918c-486">Anslut sedan till Din Office 365-klientorganisation med hjälp av [kommandot för](https://pnp.github.io/office365-cli/cmd/login/) inloggning.</span><span class="sxs-lookup"><span data-stu-id="1918c-486">Next, connect to your Office 365 tenant using the [login](https://pnp.github.io/office365-cli/cmd/login/) command.</span></span>

<span data-ttu-id="1918c-487">Utför de här stegen för att konfigurera och konfigurera CDN som värd för dina tillgångar i SharePoint Online med Office 365 CLI.</span><span class="sxs-lookup"><span data-stu-id="1918c-487">Complete these steps to set up and configure the CDN to host your assets in SharePoint Online using the Office 365 CLI.</span></span>

<details>
  <summary><span data-ttu-id="1918c-488">Klicka för att Visa</span><span class="sxs-lookup"><span data-stu-id="1918c-488">Click to expand</span></span></summary>

### <a name="enable-the-office-365-cdn"></a><span data-ttu-id="1918c-489">Aktivera Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="1918c-489">Enable the Office 365 CDN</span></span>

<span data-ttu-id="1918c-490">Du kan hantera statusen för Office 365 CDN i klientorganisationen med hjälp av [kommandot för spo cdn-uppsättningen.](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-set/)</span><span class="sxs-lookup"><span data-stu-id="1918c-490">You can manage the state of the Office 365 CDN in your tenant using the [spo cdn set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-set/) command.</span></span>

<span data-ttu-id="1918c-491">Så här aktiverar du det offentliga Office 365 CDN i klientorganisationen:</span><span class="sxs-lookup"><span data-stu-id="1918c-491">To enable the Office 365 Public CDN in your tenant execute:</span></span>

```sh
spo cdn set --type Public --enabled true
```

<span data-ttu-id="1918c-492">Om du vill aktivera Office 365 SharePoint CDN kör du:</span><span class="sxs-lookup"><span data-stu-id="1918c-492">To enable the Office 365 SharePoint CDN, execute:</span></span>

```sh
spo cdn set --type Private --enabled true
```

#### <a name="view-the-current-status-of-the-office-365-cdn"></a><span data-ttu-id="1918c-493">Visa aktuell status för Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="1918c-493">View the current status of the Office 365 CDN</span></span>

<span data-ttu-id="1918c-494">Använd kommandot [spo cdn get](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-get/) om du vill kontrollera om den specifika typen av Office 365 CDN är aktiverad eller inaktiverad.</span><span class="sxs-lookup"><span data-stu-id="1918c-494">To check if the particular type of Office 365 CDN is enabled or disabled, use the [spo cdn get](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-get/) command.</span></span>

<span data-ttu-id="1918c-495">För att kontrollera om den offentliga Office 365 CDN är aktiverad kör du:</span><span class="sxs-lookup"><span data-stu-id="1918c-495">To check if the Office 365 Public CDN is enabled, execute:</span></span>

```sh
spo cdn get --type Public
```

### <a name="view-the-office-365-cdn-origins"></a><span data-ttu-id="1918c-496">Visa Office 365 CDN-ursprung</span><span class="sxs-lookup"><span data-stu-id="1918c-496">View the Office 365 CDN origins</span></span>

<span data-ttu-id="1918c-497">Så här visar du de konfigurerade offentliga Office 365 CDN-ursprungen:</span><span class="sxs-lookup"><span data-stu-id="1918c-497">To view the currently configured Office 365 Public CDN origins execute:</span></span>

```sh
spo cdn origin list --type Public
```

<span data-ttu-id="1918c-498">Se [Standard-CDN-ursprung](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) för information om ursprung som etableras som standard när du aktiverar Office 365 CDN.</span><span class="sxs-lookup"><span data-stu-id="1918c-498">See [Default CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) for information about the origins that are provisioned by default when you enable the Office 365 CDN.</span></span>

### <a name="add-an-office-365-cdn-origin"></a><span data-ttu-id="1918c-499">Lägga till ett Office 365 CDN-ursprung</span><span class="sxs-lookup"><span data-stu-id="1918c-499">Add an Office 365 CDN origin</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1918c-500">Du ska aldrig placera resurser som anses vara känsliga för organisationen i ett SharePoint-dokumentbibliotek som konfigurerats som ett offentligt ursprung.</span><span class="sxs-lookup"><span data-stu-id="1918c-500">You should never place resources that are considered sensitive to your organization in a SharePoint document library configured as a public origin.</span></span>

<span data-ttu-id="1918c-501">Använd lägg till [ett spo cdn-ursprung för](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-add/) att definiera ett CDN-ursprung.</span><span class="sxs-lookup"><span data-stu-id="1918c-501">Use the [spo cdn origin add](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-add/) command to define a CDN origin.</span></span> <span data-ttu-id="1918c-502">Du kan definiera flera ursprung.</span><span class="sxs-lookup"><span data-stu-id="1918c-502">You can define multiple origins.</span></span> <span data-ttu-id="1918c-503">Ursprunget är en URL-adress som pekar på ett bibliotek eller en mapp i SharePoint som innehåller tillgångarna du vill ska lagras av CDN.</span><span class="sxs-lookup"><span data-stu-id="1918c-503">The origin is a URL that points to a SharePoint library or folder that contains the assets that you want to be hosted by the CDN.</span></span>

```sh
spo cdn origin add --type [Public | Private] --origin <path>
```

<span data-ttu-id="1918c-504">Var `path` finns den relativa sökvägen till mappen som innehåller tillgångarna.</span><span class="sxs-lookup"><span data-stu-id="1918c-504">Where `path` is the relative path to the folder that contains the assets.</span></span> <span data-ttu-id="1918c-505">Du kan använda jokertecken utöver relativa sökvägar.</span><span class="sxs-lookup"><span data-stu-id="1918c-505">You can use wildcards in addition to relative paths.</span></span>

<span data-ttu-id="1918c-506">Om du vill ta med alla tillgångar **i huvudsidesgalleriet** för alla webbplatser som ett offentligt ursprung kör du:</span><span class="sxs-lookup"><span data-stu-id="1918c-506">To include all assets in the **Master Page Gallery** of all sites as a public origin, execute:</span></span>

```sh
spo cdn origin add --type Public --origin */masterpage
```

<span data-ttu-id="1918c-507">Om du vill konfigurera ett privat ursprung för en viss webbplatssamling kör du:</span><span class="sxs-lookup"><span data-stu-id="1918c-507">To configure a private origin for a specific site collection, execute:</span></span>

```sh
spo cdn origin add --type Private --origin sites/site1/siteassets
```

> [!NOTE]
> <span data-ttu-id="1918c-508">När du har lagt till ett CDN-ursprung kan det ta upp till 15 minuter innan du kan hämta filer via CDN-tjänsten.</span><span class="sxs-lookup"><span data-stu-id="1918c-508">After adding a CDN origin, it might take up to 15 minutes for you to be able to retrieve files via the CDN service.</span></span> <span data-ttu-id="1918c-509">Du kan kontrollera om det specifika ursprunget redan har aktiverats med hjälp av [kommandot för spo cdn-ursprung.](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/)</span><span class="sxs-lookup"><span data-stu-id="1918c-509">You can verify if the particular origin has already been enabled using the [spo cdn origin list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) command.</span></span>

### <a name="remove-an-office-365-cdn-origin"></a><span data-ttu-id="1918c-510">Ta bort ett Office 365 CDN-ursprung</span><span class="sxs-lookup"><span data-stu-id="1918c-510">Remove an Office 365 CDN origin</span></span>

<span data-ttu-id="1918c-511">Använd kommandot [ta bort spo cdn-ursprung](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-remove/) för att ta bort ett CDN-ursprung för den angivna CDN-typen.</span><span class="sxs-lookup"><span data-stu-id="1918c-511">Use the [spo cdn origin remove](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-remove/) command to remove a CDN origin for the specified CDN type.</span></span>

<span data-ttu-id="1918c-512">Om du vill ta bort ett offentligt ursprung från CDN-konfigurationen kör du:</span><span class="sxs-lookup"><span data-stu-id="1918c-512">To remove a public origin from the CDN configuration, execute:</span></span>

```sh
spo cdn origin remove --type Public --origin */masterpage
```

> [!NOTE]
> <span data-ttu-id="1918c-513">När du tar bort ett CDN-ursprung påverkar det inte de filer som lagrats i något dokumentbibliotek som matchar ursprunget.</span><span class="sxs-lookup"><span data-stu-id="1918c-513">Removing a CDN origin doesn't affect the files stored in any document library matching that origin.</span></span> <span data-ttu-id="1918c-514">Om tillgångarna har refererats med hjälp av deras SharePoint-URL kommer SharePoint automatiskt att växla tillbaka till den ursprungliga URL-adressen som pekar till dokumentbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="1918c-514">If these assets have been referenced using their SharePoint URL, SharePoint will automatically switch back to the original URL pointing to the document library.</span></span> <span data-ttu-id="1918c-515">Om tillgångar har refererats med en offentlig CDN-URL bryter borttagningen länken och du måste ändra dem manuellt.</span><span class="sxs-lookup"><span data-stu-id="1918c-515">If, however, assets have been referenced using a public CDN URL, then removing the origin will break the link and you will need to manually change them.</span></span>

### <a name="modify-an-office-365-cdn-origin"></a><span data-ttu-id="1918c-516">Ändra ett Office 365 CDN-ursprung</span><span class="sxs-lookup"><span data-stu-id="1918c-516">Modify an Office 365 CDN origin</span></span>

<span data-ttu-id="1918c-517">Det går inte att ändra ett befintligt CDN-ursprung.</span><span class="sxs-lookup"><span data-stu-id="1918c-517">It's not possible to modify an existing CDN origin.</span></span> <span data-ttu-id="1918c-518">I stället bör du ta bort det tidigare definierade CDN-ursprunget med `spo cdn origin remove` kommandot och lägga till ett nytt med `spo cdn origin add` kommandot.</span><span class="sxs-lookup"><span data-stu-id="1918c-518">Instead, you should remove the previously defined CDN origin using the `spo cdn origin remove` command and add a new one using the `spo cdn origin add` command.</span></span>

### <a name="change-the-types-of-files-to-include-in-the-office-365-cdn"></a><span data-ttu-id="1918c-519">Ändra vilka typer av filer som ska ingå i Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="1918c-519">Change the types of files to include in the Office 365 CDN</span></span>

<span data-ttu-id="1918c-520">Som standard ingår följande filtyper i CDN: _.css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff och .woff2_.</span><span class="sxs-lookup"><span data-stu-id="1918c-520">By default, the following file types are included in the CDN: _.css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff and .woff2_.</span></span> <span data-ttu-id="1918c-521">Om du behöver ta med ytterligare filtyper i CDN kan du ändra CDN-konfigurationen med hjälp av [kommandot för spo cdn-principen.](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/)</span><span class="sxs-lookup"><span data-stu-id="1918c-521">If you need to include additional file types in the CDN, you can change the CDN configuration using the [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) command.</span></span>

> [!NOTE]
> <span data-ttu-id="1918c-522">När du ändrar listan över filtyper skriver du över den definierade listan.</span><span class="sxs-lookup"><span data-stu-id="1918c-522">When changing the list of file types, you overwrite the currently defined list.</span></span> <span data-ttu-id="1918c-523">Om du vill ta med ytterligare filtyper använder du först [spo cdn-principlistan](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) för att ta reda på vilka filtyper som är konfigurerade.</span><span class="sxs-lookup"><span data-stu-id="1918c-523">If you want to include additional file types, first use the [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) command to find out which file types are currently configured.</span></span>

<span data-ttu-id="1918c-524">Om du vill _lägga till JSON-filtypen_ i standardlistan över filtyper som ingår i det offentliga CDN kör du:</span><span class="sxs-lookup"><span data-stu-id="1918c-524">To add the _JSON_ file type to the default list of file types included in the public CDN, execute:</span></span>

```sh
spo cdn policy set --type Public --policy IncludeFileExtensions --value "CSS,EOT,GIF,ICO,JPEG,JPG,JS,MAP,PNG,SVG,TTF,WOFF,JSON"
```

### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn"></a><span data-ttu-id="1918c-525">Ändra listan över webbplatsklassificeringarna som du vill utesluta från Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="1918c-525">Change the list of site classifications you want to exclude from the Office 365 CDN</span></span>

<span data-ttu-id="1918c-526">Använd kommandot [för SPO CDN-principuppsättning](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) till att utesluta webbplatsklassificeringarna som du inte vill ska vara tillgängliga via CDN.</span><span class="sxs-lookup"><span data-stu-id="1918c-526">Use the [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) command to exclude site classifications that you do not want to make available over the CDN.</span></span> <span data-ttu-id="1918c-527">Som standard utesluts inga webbplatsklassificeringar.</span><span class="sxs-lookup"><span data-stu-id="1918c-527">By default, no site classifications are excluded.</span></span>

> [!NOTE]
> <span data-ttu-id="1918c-528">När du ändrar listan med undantagna webbplatsklassificeringar skriver du över den definierade listan.</span><span class="sxs-lookup"><span data-stu-id="1918c-528">When changing the list of excluded site classifications, you overwrite the currently defined list.</span></span> <span data-ttu-id="1918c-529">Om du vill utesluta ytterligare klassificeringar använder du först [listkommandot för spo cdn-principen](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-list/) för att ta reda på vilka klassificeringar som är konfigurerade.</span><span class="sxs-lookup"><span data-stu-id="1918c-529">If you want to exclude additional classifications, first use the [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-list/) command to find out which classifications are currently configured.</span></span>

<span data-ttu-id="1918c-530">Om du vill utesluta webbplatser som klassificerats som _HBI_ från den offentliga CDN kör du</span><span class="sxs-lookup"><span data-stu-id="1918c-530">To exclude sites classified as _HBI_ from the public CDN, execute</span></span>

```sh
spo cdn policy set --type Public --policy ExcludeRestrictedSiteClassifications --value "HBI"
```

### <a name="disable-the-office-365-cdn"></a><span data-ttu-id="1918c-531">Inaktivera Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="1918c-531">Disable the Office 365 CDN</span></span>

<span data-ttu-id="1918c-532">Om du vill inaktivera Office 365 CDN använder `spo cdn set` du kommandot, till exempel:</span><span class="sxs-lookup"><span data-stu-id="1918c-532">To disable the Office 365 CDN use the `spo cdn set` command, for example:</span></span>

```sh
spo cdn set --type Public --enabled false
```

</details>

## <a name="using-your-cdn-assets"></a><span data-ttu-id="1918c-533">Använda dina CDN-tillgångar</span><span class="sxs-lookup"><span data-stu-id="1918c-533">Using your CDN assets</span></span>

<span data-ttu-id="1918c-534">Nu när du har aktiverat CDN och konfigurerade ursprung och principer kan du börja använda dina CDN-tillgångar.</span><span class="sxs-lookup"><span data-stu-id="1918c-534">Now that you have enabled the CDN and configured origins and policies, you can begin using your CDN assets.</span></span>

<span data-ttu-id="1918c-535">Det här avsnittet hjälper dig att förstå hur du använder CDN-URL:er i dina SharePoint-sidor och innehåll så att SharePoint omdirigerar förfrågningar för tillgångar i både offentliga och privata ursprung till CDN.</span><span class="sxs-lookup"><span data-stu-id="1918c-535">This section will help you understand how to use CDN URLs in your SharePoint pages and content so that SharePoint redirects requests for assets in both public and private origins to the CDN.</span></span>

+ [<span data-ttu-id="1918c-536">Uppdatera länkar till CDN-tillgångar</span><span class="sxs-lookup"><span data-stu-id="1918c-536">Updating links to CDN assets</span></span>](use-microsoft-365-cdn-with-spo.md#updating-links-to-cdn-assets)
+ [<span data-ttu-id="1918c-537">Använda tillgångar i offentliga ursprung</span><span class="sxs-lookup"><span data-stu-id="1918c-537">Using assets in public origins</span></span>](use-microsoft-365-cdn-with-spo.md#using-assets-in-public-origins)
+ [<span data-ttu-id="1918c-538">Använda tillgångar i privata ursprung</span><span class="sxs-lookup"><span data-stu-id="1918c-538">Using assets in private origins</span></span>](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)

<span data-ttu-id="1918c-539">Information om hur du använder CDN för värd för klientwebbdelar finns i avsnittet Vara värd för din klientwebbdel från [Office 365 CDN (Hello World del 4).](/sharepoint/dev/spfx/web-parts/get-started/hosting-webpart-from-office-365-cdn)</span><span class="sxs-lookup"><span data-stu-id="1918c-539">For information on how to use the CDN for hosting client-side web parts, see the topic [Host your client-side web part from Office 365 CDN (Hello World part 4)](/sharepoint/dev/spfx/web-parts/get-started/hosting-webpart-from-office-365-cdn).</span></span>

> [!NOTE]
> <span data-ttu-id="1918c-540">Om du lägger till _mappen ClientSideAssets_ i den privata CDN-ursprungslistan går det inte att återge CDN-värdbaserade anpassade webbdelar. </span><span class="sxs-lookup"><span data-stu-id="1918c-540">If you add the _ClientSideAssets_ folder to the **private** CDN origins list, CDN-hosted custom web parts will fail to render.</span></span> <span data-ttu-id="1918c-541">Filer som används av SPFX-webbdelar kan endast använda den offentliga CDN och mappen ClientSideAssets är ett standard ursprung för offentlig CDN.</span><span class="sxs-lookup"><span data-stu-id="1918c-541">Files used by SPFX web parts can only utilize the public CDN and the ClientSideAssets folder is a default origin for public CDN.</span></span> 

### <a name="updating-links-to-cdn-assets"></a><span data-ttu-id="1918c-542">Uppdatera länkar till CDN-tillgångar</span><span class="sxs-lookup"><span data-stu-id="1918c-542">Updating links to CDN assets</span></span>

<span data-ttu-id="1918c-543">Om du vill använda tillgångar som du har lagt till i ett ursprung uppdaterar du bara länkar till den ursprungliga filen med sökvägen till filen i ursprunget.</span><span class="sxs-lookup"><span data-stu-id="1918c-543">To use assets that you have added to an origin, you simply update links to the original file with the path to the file in the origin.</span></span>

+ <span data-ttu-id="1918c-544">Redigera sidan eller innehållet som innehåller länkar till tillgångar som du har lagt till i ett ursprung.</span><span class="sxs-lookup"><span data-stu-id="1918c-544">Edit the page or content that contains links to assets you have added to an origin.</span></span> <span data-ttu-id="1918c-545">Du kan också använda en av flera metoder för att globalt söka och ersätta länkar över en ange webbplats eller webbplatssamling om du vill uppdatera länken till en viss tillgång överallt där den visas.</span><span class="sxs-lookup"><span data-stu-id="1918c-545">You can also use one of several methods to globally search and replace links across an enter site or site collection if you want to update the link to a given asset everywhere it appears.</span></span>
+ <span data-ttu-id="1918c-546">För varje länk till en tillgång i ett ursprung ersätter du sökvägen med sökvägen till filen i CDN-ursprunget.</span><span class="sxs-lookup"><span data-stu-id="1918c-546">For each link to an asset in an origin, replace the path with the path to the file in the CDN origin.</span></span> <span data-ttu-id="1918c-547">Du kan använda relativa sökvägar.</span><span class="sxs-lookup"><span data-stu-id="1918c-547">You can use relative paths.</span></span>
+ <span data-ttu-id="1918c-548">Spara sidan eller innehållet.</span><span class="sxs-lookup"><span data-stu-id="1918c-548">Save the page or content.</span></span>

<span data-ttu-id="1918c-549">Överväg till exempel bilden _/site/SiteAssets/images/image.png_, som du har kopierat till dokumentbiblioteksmappen _/site/CDN_origins/public/_.</span><span class="sxs-lookup"><span data-stu-id="1918c-549">For example, consider the image _/site/SiteAssets/images/image.png_, which you have copied to the document library folder _/site/CDN_origins/public/_.</span></span> <span data-ttu-id="1918c-550">Om du vill använda CDN-tillgången ersätter du den ursprungliga sökvägen till bildfilens plats med sökvägen till ursprunget för att göra den nya _URL:en /webbplats/CDN_origins/offentlig/image.png_.</span><span class="sxs-lookup"><span data-stu-id="1918c-550">To use the CDN asset, replace the original path to the image file location with the path to the origin to make the new URL _/site/CDN_origins/public/image.png_.</span></span>

<span data-ttu-id="1918c-551">Om du vill använda den fullständiga URL:en till tillgången i stället för en relativ sökväg skapar du länken så här:</span><span class="sxs-lookup"><span data-stu-id="1918c-551">If you want to use the full URL to the asset instead of a relative path, construct the link like so:</span></span>

`https://<TenantHostName>.sharepoint.com/sites/site/CDN_origins/public/image.png`

> [!NOTE]
> <span data-ttu-id="1918c-552">I allmänhet bör du inte hårdkoda URL-adresser direkt till tillgångar i CDN.</span><span class="sxs-lookup"><span data-stu-id="1918c-552">In general, you should not hardcode URLs directly to assets in the CDN.</span></span> <span data-ttu-id="1918c-553">Du kan dock manuellt skapa URL-adresser för tillgångar i offentliga ursprung om det behövs.</span><span class="sxs-lookup"><span data-stu-id="1918c-553">However, you can manually construct URLs for assets in public origins if needed.</span></span> <span data-ttu-id="1918c-554">Mer information finns i [Hardcoding CDN URL:er för offentliga tillgångar.](use-microsoft-365-cdn-with-spo.md)</span><span class="sxs-lookup"><span data-stu-id="1918c-554">For more information, see [Hardcoding CDN URLs for public assets](use-microsoft-365-cdn-with-spo.md).</span></span>

<span data-ttu-id="1918c-555">Mer information om hur du verifierar att tillgångar kommer från CDN finns i Hur bekräftar jag att tillgångar används i [CDN?](use-microsoft-365-cdn-with-spo.md#CDNConfirm) i avsnittet Felsökning av [Office 365 CDN.](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting)</span><span class="sxs-lookup"><span data-stu-id="1918c-555">To learn about how to verify that assets are being served from the CDN, see [How do I confirm that assets are being served by the CDN?](use-microsoft-365-cdn-with-spo.md#CDNConfirm) in the [Troubleshooting the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) section.</span></span>

### <a name="using-assets-in-public-origins"></a><span data-ttu-id="1918c-556">Använda tillgångar i offentliga ursprung</span><span class="sxs-lookup"><span data-stu-id="1918c-556">Using assets in public origins</span></span>

<span data-ttu-id="1918c-557">Publiceringsfunktionen **i** SharePoint Online skriver automatiskt om URL-adresser för tillgångar som lagras i offentliga ursprung till sina CDN-motsvarigheter så att tillgångar hämtas från CDN-tjänsten i stället för från SharePoint.</span><span class="sxs-lookup"><span data-stu-id="1918c-557">The **Publishing feature** in SharePoint Online automatically rewrites URLs of assets stored in public origins to their CDN equivalents so that assets are served from the CDN service instead of SharePoint.</span></span>

<span data-ttu-id="1918c-558">Om ditt ursprung är på en webbplats där publiceringsfunktionen är aktiverad och tillgångarna du vill lägga i för tillgångar till CDN finns i någon av följande kategorier, skriver SharePoint automatiskt om URL-adresser för tillgångar i ursprunget, förutsatt att tillgången inte har uteslutits av en CDN-princip.</span><span class="sxs-lookup"><span data-stu-id="1918c-558">If your origin is in a site with the Publishing feature enabled, and the assets you want to offload to the CDN are in one of the following categories, SharePoint will automatically rewrite URLs for assets in the origin, provided that the asset has not been excluded by a CDN policy.</span></span>

<span data-ttu-id="1918c-559">Nedan följer en översikt över vilka länkar som automatiskt skrivs om av funktionen för SharePoint-publicering:</span><span class="sxs-lookup"><span data-stu-id="1918c-559">The following is an overview of which links are automatically rewritten by the SharePoint Publishing feature:</span></span>

+ <span data-ttu-id="1918c-560">HTML-svar för IMG/LINK/CSS</span><span class="sxs-lookup"><span data-stu-id="1918c-560">IMG/LINK/CSS URLs in classic publishing page HTML responses</span></span>
  + <span data-ttu-id="1918c-561">Det omfattar bilder som har lagts till av författare i HTML-innehåll på en sida</span><span class="sxs-lookup"><span data-stu-id="1918c-561">This includes images added by authors within the HTML content of a page</span></span>
+ <span data-ttu-id="1918c-562">URL-adresser för webbdelen Bildspel för bildbibliotek</span><span class="sxs-lookup"><span data-stu-id="1918c-562">Picture Library SlideShow webpart image URLs</span></span>
+ <span data-ttu-id="1918c-563">Bildfält i SPList REST API-resultat (RenderListDataAsStream)</span><span class="sxs-lookup"><span data-stu-id="1918c-563">Image fields in SPList REST API (RenderListDataAsStream) results</span></span>
  + <span data-ttu-id="1918c-564">Använda den nya egenskapen _ImageFieldsToTryRewriteToCdnUrls_ till att ange en kommaavgränsad lista med fält</span><span class="sxs-lookup"><span data-stu-id="1918c-564">Use the new property _ImageFieldsToTryRewriteToCdnUrls_ to provide a comma separated list of fields</span></span>
  + <span data-ttu-id="1918c-565">Stöd för hyperlänkfält och publiceringsbildfält</span><span class="sxs-lookup"><span data-stu-id="1918c-565">Supports hyperlink fields and PublishingImage fields</span></span>
+ <span data-ttu-id="1918c-566">SharePoint-bildåtergivningar</span><span class="sxs-lookup"><span data-stu-id="1918c-566">SharePoint image renditions</span></span>

<span data-ttu-id="1918c-567">I följande diagram visas arbetsflödet när SharePoint tar emot en begäran om en sida som innehåller tillgångar från ett offentligt ursprung.</span><span class="sxs-lookup"><span data-stu-id="1918c-567">The following diagram illustrates the workflow when SharePoint receives a request for a page containing assets from a public origin.</span></span>

<span data-ttu-id="1918c-568">![Arbetsflödesdiagram: Hämta Office 365 CDN-tillgångar från ett offentligt ursprung](../media/O365-CDN/o365-cdn-public-steps-transparent.svg "Arbetsflöde: Hämta Office 365 CDN-tillgångar från ett offentligt ursprung")</span><span class="sxs-lookup"><span data-stu-id="1918c-568">![Workflow diagram: Retrieving Office 365 CDN assets from a public origin](../media/O365-CDN/o365-cdn-public-steps-transparent.svg "Workflow: Retrieving Office 365 CDN assets from a public origin")</span></span>

> [!TIP]
> <span data-ttu-id="1918c-569">Om du vill inaktivera automatisk omskrivning av specifika URL:er på en sida kan du gå till sidan och lägga till frågesträngparametern **? NoAutoReWrites=true** i slutet av varje länk du vill inaktivera.</span><span class="sxs-lookup"><span data-stu-id="1918c-569">If you want to disable auto-rewriting for specific URLs on a page, you can check out the page and add the query string parameter **?NoAutoReWrites=true** to the end of each link you want to disable.</span></span>

#### <a name="constructing-cdn-urls-for-public-assets"></a><span data-ttu-id="1918c-570">Konstruera CDN-URL:er för offentliga tillgångar</span><span class="sxs-lookup"><span data-stu-id="1918c-570">Constructing CDN URLs for public assets</span></span>

<span data-ttu-id="1918c-571">Om funktionen _Publicera_ inte är aktiverad för ett offentligt ursprung, eller om tillgången inte är en av länktyperna som stöds av funktionen för automatisk omskrivning i CDN-tjänsten, kan du manuellt skapa URL:er till CDN-platsen för tillgångarna och använda url:erna i innehållet.</span><span class="sxs-lookup"><span data-stu-id="1918c-571">If the _Publishing_ feature is not enabled for a public origin, or the asset is not one of the link types supported by the auto-rewrite feature of the CDN service, you can manually construct URLs to the CDN location of the assets and use these URLs in your content.</span></span>

> [!NOTE]
> <span data-ttu-id="1918c-572">Du kan inte hårdkoda eller skapa CDN-URL:er till tillgångar i ett privat ursprung eftersom den obligatoriska åtkomsttoken som utgör url-adressens sista avsnitt genereras när resursen begärs.</span><span class="sxs-lookup"><span data-stu-id="1918c-572">You cannot hardcode or construct CDN URLs to assets in a private origin because the required access token that forms the last section of the URL is generated at the time the resource is requested.</span></span> <span data-ttu-id="1918c-573">Du kan skapa URL-adressen för offentlig CDN och URL-adressen ska inte vara hårdkodad eftersom den kan komma att ändras.</span><span class="sxs-lookup"><span data-stu-id="1918c-573">You can construct the URL for Public CDN and the URL should not be hard coded as it is subject to change.</span></span>

<span data-ttu-id="1918c-574">För offentliga CDN-tillgångar ser URL-formatet ut så här:</span><span class="sxs-lookup"><span data-stu-id="1918c-574">For public CDN assets, the URL format will look like the following:</span></span>

``` html
https://publiccdn.sharepointonline.com/<TenantHostName>/sites/site/library/asset.png
```

<span data-ttu-id="1918c-575">Ersätt **TenantHostName** med ditt klientnamn.</span><span class="sxs-lookup"><span data-stu-id="1918c-575">Replace **TenantHostName** with your tenant name.</span></span> <span data-ttu-id="1918c-576">Exempel:</span><span class="sxs-lookup"><span data-stu-id="1918c-576">Example:</span></span>

``` html
https://publiccdn.sharepointonline.com/contoso.sharepoint.com/sites/site/library/asset.png
```
> [!NOTE]
> <span data-ttu-id="1918c-577">Sidsammanhangsegenskapen ska användas för att skapa prefixet i stället för hårdkodning " https://publiccdn.sharepointonline.com ".</span><span class="sxs-lookup"><span data-stu-id="1918c-577">The page context property should be used to construct the prefix instead of hard coding "https://publiccdn.sharepointonline.com".</span></span> <span data-ttu-id="1918c-578">URL-adressen kan komma att ändras och ska inte vara hårdkodad.</span><span class="sxs-lookup"><span data-stu-id="1918c-578">The URL is subject to change and should not be hard coded.</span></span> <span data-ttu-id="1918c-579">Om du använder visningsmallar med klassiska SharePoint Online kan du använda egenskapen "window._spPageContextInfo.publicCdnBaseUrl" i visningsmallen för prefixet på URL-adressen.</span><span class="sxs-lookup"><span data-stu-id="1918c-579">If you are using display templates with Classic SharePoint Online then you can use the property "window._spPageContextInfo.publicCdnBaseUrl" in your display template for the prefix of the URL.</span></span> <span data-ttu-id="1918c-580">Om du är SPFx-webbdelar för moderna och klassiska SharePoint kan du använda egenskapen "this.context.pageContext.legacyPageContext.publicCdnBaseUrl".</span><span class="sxs-lookup"><span data-stu-id="1918c-580">If you are SPFx web parts for modern and classic SharePoint the you can utilize the property "this.context.pageContext.legacyPageContext.publicCdnBaseUrl".</span></span> <span data-ttu-id="1918c-581">Det ger prefixet så att din implementering uppdateras med den om den ändras.</span><span class="sxs-lookup"><span data-stu-id="1918c-581">This will provide the prefix so that if it is changed then your implementation will update with it.</span></span> <span data-ttu-id="1918c-582">Som exempel för SPFx kan URL-adressen skapas med egenskapen "this.context.pageContext.legacyPageContext.publicCdnBaseUrl" + "/" + "host" + "/" + "relativeURL för objektet".</span><span class="sxs-lookup"><span data-stu-id="1918c-582">As an example for SPFx, the URL can be constructed using the property "this.context.pageContext.legacyPageContext.publicCdnBaseUrl" + "/" + "host" + "/" + "relativeURL for the item".</span></span> <span data-ttu-id="1918c-583">Se [Använda CDN i Klientkod som är](https://youtu.be/IH1RbQlbhIA) en del av prestandaserien [för säsong 1](https://aka.ms/sppnp-perfvideos)</span><span class="sxs-lookup"><span data-stu-id="1918c-583">Please see [Using CDN in Client-side code](https://youtu.be/IH1RbQlbhIA) which is part of the [season 1 performance series](https://aka.ms/sppnp-perfvideos)</span></span>


### <a name="using-assets-in-private-origins"></a><span data-ttu-id="1918c-584">Använda tillgångar i privata ursprung</span><span class="sxs-lookup"><span data-stu-id="1918c-584">Using assets in private origins</span></span>

<span data-ttu-id="1918c-585">Ingen ytterligare konfiguration krävs för att använda tillgångar i privata ursprung.</span><span class="sxs-lookup"><span data-stu-id="1918c-585">No additional configuration is required to use assets in private origins.</span></span> <span data-ttu-id="1918c-586">SharePoint Online skriver automatiskt om URL-adresser för tillgångar i privata ursprung så att förfrågningar om dessa tillgångar alltid kommer att hämtas från CDN.</span><span class="sxs-lookup"><span data-stu-id="1918c-586">SharePoint Online automatically rewrites URLs for assets in private origins so requests for those assets will always be served from the CDN.</span></span> <span data-ttu-id="1918c-587">Du kan inte skapa URL-adresser till CDN-tillgångar manuellt i privata ursprung eftersom dessa URL:er innehåller token som måste skapas automatiskt av SharePoint Online när tillgången begärs.</span><span class="sxs-lookup"><span data-stu-id="1918c-587">You cannot manually build URLs to CDN assets in private origins because these URLs contain tokens that must be auto-generated by SharePoint Online at the time the asset is requested.</span></span>

<span data-ttu-id="1918c-588">Åtkomst till tillgångar i privata ursprung skyddas av dynamiskt genererade token baserat på användarbehörigheter till ursprunget, med de varningar som beskrivs i följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="1918c-588">Access to assets in private origins is protected by dynamically generated tokens based on user permissions to the origin, with the caveats described in the following sections.</span></span> <span data-ttu-id="1918c-589">Användarna måste ha minst **läsbehörighet** till ursprungen för att CDN ska kunna återge innehåll.</span><span class="sxs-lookup"><span data-stu-id="1918c-589">Users must have at least **read** access to the origins for the CDN to render content.</span></span>

<span data-ttu-id="1918c-590">Följande diagram visar arbetsflödet när SharePoint tar emot en begäran om en sida som innehåller tillgångar från ett privat ursprung.</span><span class="sxs-lookup"><span data-stu-id="1918c-590">The following diagram illustrates the workflow when SharePoint receives a request for a page containing assets from a private origin.</span></span>

<span data-ttu-id="1918c-591">![Arbetsflödesdiagram: Hämta Office 365 CDN-tillgångar från ett privat ursprung](../media/O365-CDN/o365-cdn-private-steps-transparent.svg "Arbetsflöde: Hämta Office 365 CDN-tillgångar från ett privat ursprung")</span><span class="sxs-lookup"><span data-stu-id="1918c-591">![Workflow diagram: Retrieving Office 365 CDN assets from a private origin](../media/O365-CDN/o365-cdn-private-steps-transparent.svg "Workflow: Retrieving Office 365 CDN assets from a private origin")</span></span>

#### <a name="token-based-authorization-in-private-origins"></a><span data-ttu-id="1918c-592">Tokenbaserad auktorisering i privata ursprung</span><span class="sxs-lookup"><span data-stu-id="1918c-592">Token-based authorization in private origins</span></span>

<span data-ttu-id="1918c-593">Åtkomst till tillgångar i privata ursprung i Office 365 CDN tilldelas med token som genereras av SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="1918c-593">Access to assets in private origins in the Office 365 CDN is granted by tokens generated by SharePoint Online.</span></span> <span data-ttu-id="1918c-594">Användare som redan har åtkomst till mappen eller biblioteket som anges av ursprunget tilldelas automatiskt token som tillåter användaren att komma åt filen baserat på deras behörighetsnivå.</span><span class="sxs-lookup"><span data-stu-id="1918c-594">Users who already have permission to access to the folder or library designated by the origin are automatically granted tokens that permit the user to access the file based on their permission level.</span></span> <span data-ttu-id="1918c-595">De här åtkomsttoken är giltiga i 30 till 90 minuter efter att de har skapats för att förhindra attacker vid tokenuppspelning.</span><span class="sxs-lookup"><span data-stu-id="1918c-595">These access tokens are valid for 30 to 90 minutes after they are generated to help prevent token replay attacks.</span></span>

<span data-ttu-id="1918c-596">När åtkomsttoken har genererats returnerar SharePoint Online en anpassad  URI till klienten som innehåller två auktoriseringsparametrar äter (edge-auktoriseringstoken) och _oat_ (origin authorization token).</span><span class="sxs-lookup"><span data-stu-id="1918c-596">Once the access token is generated, SharePoint Online returns a custom URI to the client containing two authorization parameters _eat_ (edge authorization token) and _oat_ (origin authorization token).</span></span> <span data-ttu-id="1918c-597">Strukturen för varje token _är< förfallotid i Epoch-tidsformatet som >__< säkra signaturens >._</span><span class="sxs-lookup"><span data-stu-id="1918c-597">The structure of each token is _<'expiration time in Epoch time format'>__<'secure signature'>_.</span></span> <span data-ttu-id="1918c-598">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="1918c-598">For example:</span></span>

``` html
https://privatecdn.sharepointonline.com/contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg?eat=1486154359_cc59042c5c55c90b26a2775323c7c8112718431228fe84d568a3795a63912840&oat=1486154359_7d73c2e3ba4b7b1f97242332900616db0d4ffb04312
```

> [!NOTE]
> <span data-ttu-id="1918c-599">Alla som äger token kan komma åt resursen i CDN.</span><span class="sxs-lookup"><span data-stu-id="1918c-599">Anyone in possession of the token can access the resource in the CDN.</span></span> <span data-ttu-id="1918c-600">Url-adresser som innehåller dessa åtkomsttoken delas däremot bara över HTTPS, så om inte URL:en uttryckligen delas av en slutanvändare innan tokenen löper ut kommer tillgången inte att vara tillgänglig för obehöriga användare.</span><span class="sxs-lookup"><span data-stu-id="1918c-600">However, URLs containing these access tokens are only shared over HTTPS, so unless the URL is explicitly shared by an end user before the token expires, the asset won't be accessible to unauthorized users.</span></span>

#### <a name="item-level-permissions-are-not-supported-for-assets-in-private-origins"></a><span data-ttu-id="1918c-601">Behörigheter på objektnivå stöds inte för tillgångar i privata ursprung</span><span class="sxs-lookup"><span data-stu-id="1918c-601">Item-level permissions are not supported for assets in private origins</span></span>

<span data-ttu-id="1918c-602">Det är viktigt att observera att SharePoint Online inte stöder behörigheter på objektnivå för tillgångar i privata ursprung.</span><span class="sxs-lookup"><span data-stu-id="1918c-602">It is important to note that SharePoint Online does not support item-level permissions for assets in private origins.</span></span> <span data-ttu-id="1918c-603">För en fil som finns på `https://contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg` , har användarna till exempel effektiv åtkomst till filen enligt följande villkor:</span><span class="sxs-lookup"><span data-stu-id="1918c-603">For example, for a file located at `https://contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg`, users have effective access to the file given the following conditions:</span></span>

|<span data-ttu-id="1918c-604">Användare</span><span class="sxs-lookup"><span data-stu-id="1918c-604">User</span></span>  |<span data-ttu-id="1918c-605">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="1918c-605">Permissions</span></span>  |<span data-ttu-id="1918c-606">Effektiv åtkomst</span><span class="sxs-lookup"><span data-stu-id="1918c-606">Effective access</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="1918c-607">Användare 1</span><span class="sxs-lookup"><span data-stu-id="1918c-607">User 1</span></span>     |<span data-ttu-id="1918c-608">Har åtkomst till mapp1</span><span class="sxs-lookup"><span data-stu-id="1918c-608">Has access to folder1</span></span>         |<span data-ttu-id="1918c-609">Kan komma image1.jpg från CDN</span><span class="sxs-lookup"><span data-stu-id="1918c-609">Can access image1.jpg from the CDN</span></span>         |
|<span data-ttu-id="1918c-610">Användare 2</span><span class="sxs-lookup"><span data-stu-id="1918c-610">User 2</span></span>     |<span data-ttu-id="1918c-611">Har inte åtkomst till mapp1</span><span class="sxs-lookup"><span data-stu-id="1918c-611">Does not have access to folder1</span></span>         |<span data-ttu-id="1918c-612">Kan inte image1.jpg från CDN</span><span class="sxs-lookup"><span data-stu-id="1918c-612">Cannot access image1.jpg from the CDN</span></span>         |
|<span data-ttu-id="1918c-613">Användare 3</span><span class="sxs-lookup"><span data-stu-id="1918c-613">User 3</span></span>     |<span data-ttu-id="1918c-614">Har inte åtkomst till mapp1, men tilldelas uttrycklig åtkomstbehörighet för image1.jpg i SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="1918c-614">Does not have access to folder1, but is granted explicit permission to access image1.jpg in SharePoint Online</span></span>         |<span data-ttu-id="1918c-615">Kan komma åt image1.jpg direkt från SharePoint Online, men inte från CDN</span><span class="sxs-lookup"><span data-stu-id="1918c-615">Can access the asset image1.jpg directly from SharePoint Online, but not from the CDN</span></span>         |
|<span data-ttu-id="1918c-616">Användare 4</span><span class="sxs-lookup"><span data-stu-id="1918c-616">User 4</span></span>     |<span data-ttu-id="1918c-617">Har åtkomst till mapp1, men har uttryckligen nekats åtkomst till image1.jpg i SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="1918c-617">Has access to folder1, but has been explicitly denied access to image1.jpg in SharePoint Online</span></span>         |<span data-ttu-id="1918c-618">Kan inte komma åt tillgången från SharePoint Online, men kan komma åt tillgången från CDN trots att åtkomst till filen nekas i SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="1918c-618">Cannot access the asset from SharePoint Online, but can access the asset from the CDN despite being denied access to the file in SharePoint Online</span></span>         |

<span data-ttu-id="1918c-619"><a name="CDNTroubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="1918c-619"><a name="CDNTroubleshooting"> </a></span></span>
## <a name="troubleshooting-the-office-365-cdn"></a><span data-ttu-id="1918c-620">Felsöka Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="1918c-620">Troubleshooting the Office 365 CDN</span></span>

<span data-ttu-id="1918c-621"><a name="CDNConfirm"> </a></span><span class="sxs-lookup"><span data-stu-id="1918c-621"><a name="CDNConfirm"> </a></span></span>
### <a name="how-do-i-confirm-that-assets-are-being-served-by-the-cdn"></a><span data-ttu-id="1918c-622">Hur bekräftar jag att tillgångar används av CDN?</span><span class="sxs-lookup"><span data-stu-id="1918c-622">How do I confirm that assets are being served by the CDN?</span></span>

<span data-ttu-id="1918c-623">När du har lagt till länkar till CDN-tillgångar på en sida kan du bekräfta att tillgången kommer från CDN genom att gå till sidan, högerklicka på bilden när den har visats och granskat bild-URL:en.</span><span class="sxs-lookup"><span data-stu-id="1918c-623">Once you have added links to CDN assets to a page, you can confirm that the asset is being served from the CDN by browsing to the page, right clicking on the image once it has rendered and reviewing the image URL.</span></span>

<span data-ttu-id="1918c-624">Du kan också använda webbläsarens utvecklarverktyg för att visa URL-adressen för varje tillgång på en sida, eller använda ett nätverksspårningsverktyg från tredje part.</span><span class="sxs-lookup"><span data-stu-id="1918c-624">You can also use your browser's developer tools to view the URL for each asset on a page, or use a third party network trace tool.</span></span>

> [!NOTE]
> <span data-ttu-id="1918c-625">Om du använder ett nätverksverktyg, till exempel Fiddler, för att testa dina tillgångar utanför att återge tillgången från en SharePoint-sida, måste du manuellt lägga till refererhuvudet "Referer: " i GET-begäran där URL:en är rot-URL:en för `https://yourdomain.sharepoint.com` SharePoint Online-klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="1918c-625">If you use a network tool such as Fiddler to test your assets outside of rendering the asset from a SharePoint page, you must manually add the referer header "Referer: `https://yourdomain.sharepoint.com`" to the GET request where the URL is the root URL of your SharePoint Online tenant.</span></span>

<span data-ttu-id="1918c-626">Du kan inte testa CDN-URL:er direkt i en webbläsare eftersom du måste ha en referent från SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="1918c-626">You cannot test CDN URLs directly in a web browser because you must have a referer coming from SharePoint Online.</span></span> <span data-ttu-id="1918c-627">Men om du lägger till CDN-resurs-URL:en på en SharePoint-sida och sedan öppnar sidan i en webbläsare, ser du CDN-tillgången återges på sidan.</span><span class="sxs-lookup"><span data-stu-id="1918c-627">However, if you add the CDN asset URL to a SharePoint page and then open the page in a browser, you will see the CDN asset rendered on the page.</span></span>

<span data-ttu-id="1918c-628">Mer information om hur du använder utvecklarverktygen i webbläsaren Microsoft Edge finns i [Utvecklarverktyg för Microsoft Edge.](/microsoft-edge/devtools-guide)</span><span class="sxs-lookup"><span data-stu-id="1918c-628">For more information on using the developer tools in the Microsoft Edge browser, see [Microsoft Edge Developer Tools](/microsoft-edge/devtools-guide).</span></span>

<span data-ttu-id="1918c-629">Om du vill titta på en kort video som finns i [YouTube-kanalen SharePoint Developer Patterns and Practices](https://aka.ms/sppnp-videos) och visa hur du verifierar att CDN fungerar kan du gå till Verifiera din CDN-användning och säkerställa [optimal nätverksanslutning.](https://www.youtube.com/watch?v=ClCtBAtGjE8&list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA&index=5)</span><span class="sxs-lookup"><span data-stu-id="1918c-629">To watch a short video hosted in the [SharePoint Developer Patterns and Practices YouTube channel](https://aka.ms/sppnp-videos) demonstrating how to verify that your CDN is working, please see [Verifying your CDN usage and ensuring optimal network connectivity](https://www.youtube.com/watch?v=ClCtBAtGjE8&list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA&index=5).</span></span>

### <a name="why-are-assets-from-a-new-origin-unavailable"></a><span data-ttu-id="1918c-630">Varför är tillgångar från ett nytt ursprung inte tillgängliga?</span><span class="sxs-lookup"><span data-stu-id="1918c-630">Why are assets from a new origin unavailable?</span></span>
<span data-ttu-id="1918c-631">Tillgångar i nya ursprung blir inte omedelbart tillgängliga för användning eftersom det tar tid för registreringen att spridas via CDN och för tillgångar som ska laddas upp från ursprunget till CDN-lagringen.</span><span class="sxs-lookup"><span data-stu-id="1918c-631">Assets in new origins will not immediately be available for use, as it takes time for the registration to propagate through the CDN and for the assets to be uploaded from the origin to CDN storage.</span></span> <span data-ttu-id="1918c-632">Hur lång tid som krävs för att tillgångar ska vara tillgänglig i CDN beror på hur många tillgångar och filstorlekar som krävs.</span><span class="sxs-lookup"><span data-stu-id="1918c-632">The time required for assets to be available in the CDN depends on how many assets and the files sizes.</span></span>

### <a name="my-client-side-web-part-or-sharepoint-framework-solution-isnt-working"></a><span data-ttu-id="1918c-633">Min klientwebbdel eller SharePoint Framework-lösning fungerar inte</span><span class="sxs-lookup"><span data-stu-id="1918c-633">My client-side web part or SharePoint Framework solution isn't working</span></span>

<span data-ttu-id="1918c-634">När du aktiverar Office 365 CDN för offentliga ursprung skapar CDN-tjänsten automatiskt följande standard origins:</span><span class="sxs-lookup"><span data-stu-id="1918c-634">When you enable the Office 365 CDN for public origins, the CDN service automatically creates these default origins:</span></span>

+ <span data-ttu-id="1918c-635">\*/MASTERPAGE</span><span class="sxs-lookup"><span data-stu-id="1918c-635">\*/MASTERPAGE</span></span>
+ <span data-ttu-id="1918c-636">\*/STYLE LIBRARY</span><span class="sxs-lookup"><span data-stu-id="1918c-636">\*/STYLE LIBRARY</span></span>
+ <span data-ttu-id="1918c-637">\*/CLIENTSIDEASSETS</span><span class="sxs-lookup"><span data-stu-id="1918c-637">\*/CLIENTSIDEASSETS</span></span>

<span data-ttu-id="1918c-638">Om ursprunget \*/clientsideassets saknas kommer SharePoint Framework-lösningar att misslyckas och inga varningar eller felmeddelanden skapas.</span><span class="sxs-lookup"><span data-stu-id="1918c-638">If the \*/clientsideassets origin is missing, SharePoint Framework solutions will fail, and no warning or error messages are generated.</span></span> <span data-ttu-id="1918c-639">Det här ursprunget kanske saknas antingen eftersom CDN aktiverades med parametern _-NoDefaultOrigins_ inställd **på $true**, eller eftersom ursprunget togs bort manuellt.</span><span class="sxs-lookup"><span data-stu-id="1918c-639">This origin may be missing either because the CDN was enabled with the _-NoDefaultOrigins_ parameter set to **$true**, or because the origin was manually deleted.</span></span>

<span data-ttu-id="1918c-640">Du kan kontrollera vilka ursprung som finns med följande PowerShell-kommando:</span><span class="sxs-lookup"><span data-stu-id="1918c-640">You can check to see which origins are present with the following PowerShell command:</span></span>

``` powershell
Get-SPOTenantCdnOrigins -CdnType Public
```

<span data-ttu-id="1918c-641">Eller så kan du kontrollera med Office 365 CLI:</span><span class="sxs-lookup"><span data-stu-id="1918c-641">Or you can check with the Office 365 CLI:</span></span>

``` powershell
spo cdn origin list
```

<span data-ttu-id="1918c-642">Så här lägger du till ursprunget i PowerShell:</span><span class="sxs-lookup"><span data-stu-id="1918c-642">To add the origin in PowerShell:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */CLIENTSIDEASSETS
```

<span data-ttu-id="1918c-643">Så här lägger du till ursprunget i Office 365 CLI:</span><span class="sxs-lookup"><span data-stu-id="1918c-643">To add the origin in the Office 365 CLI:</span></span>

``` powershell
spo cdn origin add --origin */CLIENTSIDEASSETS
```

### <a name="what-powershell-modules-and-cli-shells-do-i-need-to-work-with-the-office-365-cdn"></a><span data-ttu-id="1918c-644">Vilka PowerShell-moduler och CLI-gränssnitt behöver jag arbeta med Office 365 CDN?</span><span class="sxs-lookup"><span data-stu-id="1918c-644">What PowerShell modules and CLI shells do I need to work with the Office 365 CDN?</span></span>

<span data-ttu-id="1918c-645">Du kan välja att arbeta med Office 365 CDN med hjälp av **antingen SharePoint Online Management Shell** PowerShell-modulen eller **Office 365 CLI.**</span><span class="sxs-lookup"><span data-stu-id="1918c-645">You can choose to work with the Office 365 CDN using either the **SharePoint Online Management Shell** PowerShell module or the **Office 365 CLI**.</span></span>

+ [<span data-ttu-id="1918c-646">Komma igång med SharePoint Online Management Shell</span><span class="sxs-lookup"><span data-stu-id="1918c-646">Getting started with SharePoint Online Management Shell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)
+ [<span data-ttu-id="1918c-647">Installera Office 365 CLI</span><span class="sxs-lookup"><span data-stu-id="1918c-647">Installing the Office 365 CLI</span></span>](https://pnp.github.io/office365-cli/user-guide/installing-cli/)

## <a name="see-also"></a><span data-ttu-id="1918c-648">Se även</span><span class="sxs-lookup"><span data-stu-id="1918c-648">See also</span></span>

[<span data-ttu-id="1918c-649">Nätverk för innehållsleverans (CDN)</span><span class="sxs-lookup"><span data-stu-id="1918c-649">Content Delivery Networks</span></span>](./content-delivery-networks.md)

[<span data-ttu-id="1918c-650">Network planning and performance tuning for Office 365</span><span class="sxs-lookup"><span data-stu-id="1918c-650">Network planning and performance tuning for Office 365</span></span>](./network-planning-and-performance.md)

[<span data-ttu-id="1918c-651">SharePoint Performance Series – Office 365 CDN-videoserie</span><span class="sxs-lookup"><span data-stu-id="1918c-651">SharePoint Performance Series - Office 365 CDN video series</span></span>](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)