---
title: Använda Office 365 innehålls leverans nätverk (CDN) med SharePoint Online
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
description: Lär dig hur du använder Office 365 Content Delivery Network (CDN) för att påskynda leveransen av dina SharePoint Online-till gångar.
ms.openlocfilehash: 0ef7922f4e8881065f97a5fdeb4f21242c2b6467
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694341"
---
# <a name="use-the-office-365-content-delivery-network-cdn-with-sharepoint-online"></a><span data-ttu-id="bbc66-103">Använda Office 365-innehålls leverans nätverk (CDN) med SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="bbc66-103">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>

<span data-ttu-id="bbc66-104">Du kan använda det inbyggda Office-365 innehålls leverans nätverk (CDN) för att hantera statiska till gångar för bättre prestanda för SharePoint Online-sidorna.</span><span class="sxs-lookup"><span data-stu-id="bbc66-104">You can use the built-in Office 365 Content Delivery Network (CDN) to host static assets to provide better performance for your SharePoint Online pages.</span></span> <span data-ttu-id="bbc66-105">Office 365 CDN förbättrar prestandan genom att cachelagra statiska till gångar i webbläsare som begär dem, vilket hjälper dig att påskynda nedladdningen och minska svars tiden.</span><span class="sxs-lookup"><span data-stu-id="bbc66-105">The Office 365 CDN improves performance by caching static assets closer to the browsers requesting them, which helps to speed up downloads and reduce latency.</span></span> <span data-ttu-id="bbc66-106">Dessutom använder Office 365 CDN [http/2](https://en.wikipedia.org/wiki/HTTP/2) för förbättrad komprimering och http-försäljning.</span><span class="sxs-lookup"><span data-stu-id="bbc66-106">Also, the Office 365 CDN uses the [HTTP/2 protocol](https://en.wikipedia.org/wiki/HTTP/2) for improved compression and HTTP pipelining.</span></span> <span data-ttu-id="bbc66-107">Office 365 CDN-tjänsten är inkluderad som en del av SharePoint Online-prenumerationen.</span><span class="sxs-lookup"><span data-stu-id="bbc66-107">The Office 365 CDN service is included as part of your SharePoint Online subscription.</span></span>

> [!NOTE]
> <span data-ttu-id="bbc66-108">Office 365 CDN är bara tillgängligt för klient organisationer i **produktions** -molnet (världen över).</span><span class="sxs-lookup"><span data-stu-id="bbc66-108">The Office 365 CDN is only available to tenants in the **Production** (worldwide) cloud.</span></span> <span data-ttu-id="bbc66-109">Klient organisationer i Förenta staternas myndigheter, Kina och Tyskland stöder för närvarande inte Office 365 CDN.</span><span class="sxs-lookup"><span data-stu-id="bbc66-109">Tenants in the US Government, China and Germany clouds do not currently support the Office 365 CDN.</span></span>

<span data-ttu-id="bbc66-110">Office 365 CDN består av flera CDN som låter dig hantera fasta till gångar på flera platser, eller _ursprung_, och betjäna dem från globala nätverk med snabb hastighet.</span><span class="sxs-lookup"><span data-stu-id="bbc66-110">The Office 365 CDN is composed of multiple CDNs that allow you to host static assets in multiple locations, or _origins_, and serve them from global high-speed networks.</span></span> <span data-ttu-id="bbc66-111">Beroende på vilken typ av innehåll du vill ha i Office 365 CDN kan du lägga till **offentliga** ursprung, **privata** ursprung eller båda.</span><span class="sxs-lookup"><span data-stu-id="bbc66-111">Depending on the kind of content you want to host in the Office 365 CDN, you can add **public** origins, **private** origins or both.</span></span> <span data-ttu-id="bbc66-112">Se [välja om varje ursprung ska vara offentligt eller privat](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) för mer information om skillnaden mellan offentliga och privata ursprung.</span><span class="sxs-lookup"><span data-stu-id="bbc66-112">See [Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) for more information on the difference between public and private origins.</span></span>

<span data-ttu-id="bbc66-113">![Office 365 CDN-koncept diagram](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 CDN-koncept diagram")</span><span class="sxs-lookup"><span data-stu-id="bbc66-113">![Office 365 CDN conceptual diagram](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 CDN conceptual diagram")</span></span>

<span data-ttu-id="bbc66-114">Om du redan är bekant med hur CDN fungerar behöver du bara utföra några steg för att aktivera Office 365 CDN för din klient organisation.</span><span class="sxs-lookup"><span data-stu-id="bbc66-114">If you are already familiar with the way that CDNs work, you only need to complete a few steps to enable the Office 365 CDN for your tenant.</span></span> <span data-ttu-id="bbc66-115">I det här avsnittet beskrivs hur.</span><span class="sxs-lookup"><span data-stu-id="bbc66-115">This topic describes how.</span></span> <span data-ttu-id="bbc66-116">Läs mer om hur du kommer igång med dina statiska till gångar.</span><span class="sxs-lookup"><span data-stu-id="bbc66-116">Read on for information about how to get started hosting your static assets.</span></span>

> [!TIP]
> <span data-ttu-id="bbc66-117">Det finns andra Microsoft-värdbaserade CDN som kan användas med Office 365 för specialiserade användnings scenarier, men diskuteras inte i det här avsnittet eftersom de ligger utanför omfattningen av Office 365 CDN.</span><span class="sxs-lookup"><span data-stu-id="bbc66-117">There are other Microsoft-hosted CDNs that can be used with Office 365 for specialized usage scenarios, but are not discussed in this topic because they fall outside the scope of the Office 365 CDN.</span></span> <span data-ttu-id="bbc66-118">Mer information finns i [andra Microsoft-CDN](content-delivery-networks.md#other-microsoft-cdns).</span><span class="sxs-lookup"><span data-stu-id="bbc66-118">For more information, see [Other Microsoft CDNs](content-delivery-networks.md#other-microsoft-cdns).</span></span>

 <span data-ttu-id="bbc66-119">**Gå tillbaka till [nätverks planering och prestanda justering för Office 365](https://aka.ms/tune).**</span><span class="sxs-lookup"><span data-stu-id="bbc66-119">**Head back to [Network planning and performance tuning for Office 365](https://aka.ms/tune).**</span></span>

## <a name="overview-of-working-with-the-office-365-cdn-in-sharepoint-online"></a><span data-ttu-id="bbc66-120">Översikt över hur du arbetar med Office 365 CDN i SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="bbc66-120">Overview of working with the Office 365 CDN in SharePoint Online</span></span>

<span data-ttu-id="bbc66-121">Följ de här grundläggande stegen för att konfigurera Office 365 CDN för din organisation:</span><span class="sxs-lookup"><span data-stu-id="bbc66-121">To set up the Office 365 CDN for your organization, you follow these basic steps:</span></span>

+ [<span data-ttu-id="bbc66-122">Planera för distribution av Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="bbc66-122">Plan for deployment of the Office 365 CDN</span></span>](use-microsoft-365-cdn-with-spo.md#plan-for-deployment-of-the-office-365-cdn)

  + <span data-ttu-id="bbc66-123">[Avgöra vilka statiska till gångar som du vill använda i CDN](use-microsoft-365-cdn-with-spo.md#CDNAssets).</span><span class="sxs-lookup"><span data-stu-id="bbc66-123">[Determine which static assets you want to host on the CDN](use-microsoft-365-cdn-with-spo.md#CDNAssets).</span></span>
  + <span data-ttu-id="bbc66-124">[Bestäm var du vill lagra dina till gångar](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets).</span><span class="sxs-lookup"><span data-stu-id="bbc66-124">[Determine where you want to store your assets](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets).</span></span> <span data-ttu-id="bbc66-125">Denna plats kan vara en SharePoint-webbplats, ett bibliotek eller en mapp och kallas för ett _ursprung_.</span><span class="sxs-lookup"><span data-stu-id="bbc66-125">This location can be a SharePoint site, library or folder and is called an _origin_.</span></span>
  + <span data-ttu-id="bbc66-126">[Välj om varje ursprung ska vara offentligt eller privat](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate).</span><span class="sxs-lookup"><span data-stu-id="bbc66-126">[Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate).</span></span> <span data-ttu-id="bbc66-127">Du kan lägga till flera ursprung för både offentliga och privata typer.</span><span class="sxs-lookup"><span data-stu-id="bbc66-127">You can add multiple origins of both public and private types.</span></span>

+ <span data-ttu-id="bbc66-128">Konfigurera och konfigurera CDN med antingen PowerShell eller SharePoint Online-CLI</span><span class="sxs-lookup"><span data-stu-id="bbc66-128">Set up and configure the CDN, using either PowerShell or the SharePoint Online CLI</span></span>

  + [<span data-ttu-id="bbc66-129">Konfigurera och konfigurera CDN genom att använda SharePoint Online Management Shell</span><span class="sxs-lookup"><span data-stu-id="bbc66-129">Set up and configure the CDN by using the SharePoint Online Management Shell</span></span>](use-microsoft-365-cdn-with-spo.md#CDNSetupinPShell)
  + [<span data-ttu-id="bbc66-130">Konfigurera och konfigurera CDN med hjälp av PnP PowerShell</span><span class="sxs-lookup"><span data-stu-id="bbc66-130">Set up and configure the CDN by using PnP PowerShell</span></span>](use-microsoft-365-cdn-with-spo.md#CDNSetupinPnPPosh)
  + [<span data-ttu-id="bbc66-131">Konfigurera och konfigurera CDN med hjälp av Office 365-CLI</span><span class="sxs-lookup"><span data-stu-id="bbc66-131">Set up and configure the CDN by using the Office 365 CLI</span></span>](use-microsoft-365-cdn-with-spo.md#CDNSetupinCLI)

  <span data-ttu-id="bbc66-132">När du är klar med det här steget har du:</span><span class="sxs-lookup"><span data-stu-id="bbc66-132">When you complete this step, you will have:</span></span>

  + <span data-ttu-id="bbc66-133">Aktiverat CDN för din organisation.</span><span class="sxs-lookup"><span data-stu-id="bbc66-133">Enabled the CDN for your organization.</span></span>
  + <span data-ttu-id="bbc66-134">Lade till dina ursprung och identifierar varje ursprung som offentligt eller privat.</span><span class="sxs-lookup"><span data-stu-id="bbc66-134">Added your origins, identifying each origin as public or private.</span></span>

<span data-ttu-id="bbc66-135">När du är klar med konfigurationen kan du [Hantera Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNManage) över tiden genom att:</span><span class="sxs-lookup"><span data-stu-id="bbc66-135">Once you're done with setup, you can [Manage the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNManage) over time by:</span></span>
  
+ <span data-ttu-id="bbc66-136">Lägga till, uppdatera och ta bort till gångar</span><span class="sxs-lookup"><span data-stu-id="bbc66-136">Adding, updating, and removing assets</span></span>
+ <span data-ttu-id="bbc66-137">Lägga till och ta bort ursprung</span><span class="sxs-lookup"><span data-stu-id="bbc66-137">Adding and removing origins</span></span>
+ <span data-ttu-id="bbc66-138">Konfigurera CDN-principer</span><span class="sxs-lookup"><span data-stu-id="bbc66-138">Configuring CDN policies</span></span>
+ <span data-ttu-id="bbc66-139">Vid behov kan du avaktivera CDN</span><span class="sxs-lookup"><span data-stu-id="bbc66-139">If necessary, disabling the CDN</span></span>

<span data-ttu-id="bbc66-140">Slutligen kan du läsa om hur du [använder CDN-till](use-microsoft-365-cdn-with-spo.md#using-your-cdn-assets) gångar från både offentliga och privata ursprung.</span><span class="sxs-lookup"><span data-stu-id="bbc66-140">Finally, see [Using your CDN assets](use-microsoft-365-cdn-with-spo.md#using-your-cdn-assets) to learn about accessing your CDN assets from both public and private origins.</span></span>

<span data-ttu-id="bbc66-141">Se [fel sökning av Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) för vägledning för lösning av vanliga problem.</span><span class="sxs-lookup"><span data-stu-id="bbc66-141">See [Troubleshooting the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) for guidance on resolving common issues.</span></span>

## <a name="plan-for-deployment-of-the-office-365-cdn"></a><span data-ttu-id="bbc66-142">Planera för distribution av Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="bbc66-142">Plan for deployment of the Office 365 CDN</span></span>

<span data-ttu-id="bbc66-143">Innan du distribuerar Office 365 CDN för din Office 365-klient bör du tänka på följande faktorer som en del av planerings processen.</span><span class="sxs-lookup"><span data-stu-id="bbc66-143">Before you deploy the Office 365 CDN for your Office 365 tenant, you should consider the following factors as part of your planning process.</span></span>

  + [<span data-ttu-id="bbc66-144">Avgöra vilka statiska till gångar som du vill använda i CDN</span><span class="sxs-lookup"><span data-stu-id="bbc66-144">Determine which static assets you want to host on the CDN</span></span>](use-microsoft-365-cdn-with-spo.md#CDNAssets)
  + [<span data-ttu-id="bbc66-145">Bestämma var du vill spara till gångarna</span><span class="sxs-lookup"><span data-stu-id="bbc66-145">Determine where you want to store your assets</span></span>](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets)
  + [<span data-ttu-id="bbc66-146">Välja om varje ursprung ska vara offentligt eller privat</span><span class="sxs-lookup"><span data-stu-id="bbc66-146">Choose whether each origin should be public or private</span></span>](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)

<span data-ttu-id="bbc66-147"><a name="CDNAssets"> </a></span><span class="sxs-lookup"><span data-stu-id="bbc66-147"><a name="CDNAssets"> </a></span></span>
### <a name="determine-which-static-assets-you-want-to-host-on-the-cdn"></a><span data-ttu-id="bbc66-148">Avgöra vilka statiska till gångar som du vill använda i CDN</span><span class="sxs-lookup"><span data-stu-id="bbc66-148">Determine which static assets you want to host on the CDN</span></span>

<span data-ttu-id="bbc66-149">I allmänhet är CDN mest effektiva för att vara värd för _fasta till gångar_eller till gångar som inte ändras ofta.</span><span class="sxs-lookup"><span data-stu-id="bbc66-149">In general, CDNs are most effective for hosting _static assets_, or assets that don't change very often.</span></span> <span data-ttu-id="bbc66-150">En bra tumregel är att identifiera filer som uppfyller vissa eller samtliga av dessa villkor:</span><span class="sxs-lookup"><span data-stu-id="bbc66-150">A good rule of thumb is to identify files that meet some or all of these conditions:</span></span>

+ <span data-ttu-id="bbc66-151">Statiska filer som bäddats in på en sida (till exempel skript och bilder) som kan ha avsevärda effekter på sid inläsnings tider</span><span class="sxs-lookup"><span data-stu-id="bbc66-151">Static files embedded in a page (like scripts and images) that may have a significant incremental impact on page load times</span></span>
+ <span data-ttu-id="bbc66-152">Stora filer, till exempel körbara filer och installationsfiler</span><span class="sxs-lookup"><span data-stu-id="bbc66-152">Large files like executables and installation files</span></span>
+ <span data-ttu-id="bbc66-153">Resurs bibliotek med stöd för klientbaserade koder</span><span class="sxs-lookup"><span data-stu-id="bbc66-153">Resource libraries that support client-side code</span></span>

<span data-ttu-id="bbc66-154">Till exempel kan små filer som är upprepade gånger begärda med webbplats bilder och skript förbättra prestandan för webbplats åter givningen och inkrementellt minska belastningen på SharePoint Online-webbplatserna när du lägger till dem i ett CDN-ursprung.</span><span class="sxs-lookup"><span data-stu-id="bbc66-154">For example, small files that are repeatedly requested like site images and scripts can significantly improve site rendering performance and incrementally reduce the load on your SharePoint Online sites when you add them to a CDN origin.</span></span> <span data-ttu-id="bbc66-155">Större filer, till exempel körbara installations program, kan hämtas från CDN och ger en positiv effekt som påverkar belastningen på SharePoint Online-webbplatsen även om de inte är tillgängliga så ofta.</span><span class="sxs-lookup"><span data-stu-id="bbc66-155">Larger files such as installation executables can be downloaded from the CDN, delivering a positive performance impact and subsequent reduction of the load on your SharePoint Online site, even if they are not accessed as often.</span></span>

<span data-ttu-id="bbc66-156">Förbättring av prestanda på en fil är beroende av många faktorer, inklusive klientens närhet till närmaste CDN-slutpunkt, tillfälliga förhållanden i det lokala nätverket.</span><span class="sxs-lookup"><span data-stu-id="bbc66-156">Performance improvement on a per-file basis is dependent on many factors, including the client's proximity to the nearest CDN endpoint, transient conditions on the local network, and so forth.</span></span> <span data-ttu-id="bbc66-157">Många statiska filer är ganska små och kan laddas ned från Office 365 på mindre än en sekund.</span><span class="sxs-lookup"><span data-stu-id="bbc66-157">Many static files are quite small, and can be downloaded from Office 365 in less than a second.</span></span> <span data-ttu-id="bbc66-158">En webb sida kan innehålla många inbäddade filer med en kumulativ nedladdnings tid på flera sekunder.</span><span class="sxs-lookup"><span data-stu-id="bbc66-158">However, a web page may contain many embedded files with a cumulative download time of several seconds.</span></span> <span data-ttu-id="bbc66-159">Om du betjänar dessa filer från CDN kan det avsevärt minska sid inläsnings tiden.</span><span class="sxs-lookup"><span data-stu-id="bbc66-159">Serving these files from the CDN can significantly reduce the overall page load time.</span></span> <span data-ttu-id="bbc66-160">Se [vilka resultat vinster ett CDN tillhandahåller?](content-delivery-networks.md#what-performance-gains-does-a-cdn-provide) för ett exempel.</span><span class="sxs-lookup"><span data-stu-id="bbc66-160">See [What performance gains does a CDN provide?](content-delivery-networks.md#what-performance-gains-does-a-cdn-provide) for an example.</span></span>

<span data-ttu-id="bbc66-161"><a name="CDNStoreAssets"> </a></span><span class="sxs-lookup"><span data-stu-id="bbc66-161"><a name="CDNStoreAssets"> </a></span></span>
### <a name="determine-where-you-want-to-store-your-assets"></a><span data-ttu-id="bbc66-162">Bestämma var du vill spara till gångarna</span><span class="sxs-lookup"><span data-stu-id="bbc66-162">Determine where you want to store your assets</span></span>

<span data-ttu-id="bbc66-163">CDN hämtar dina till gångar från en plats som kallas _ursprung_.</span><span class="sxs-lookup"><span data-stu-id="bbc66-163">The CDN fetches your assets from a location called an _origin_.</span></span> <span data-ttu-id="bbc66-164">Ett ursprung kan vara en SharePoint-webbplats, ett dokument bibliotek eller en mapp som är tillgänglig via en URL-adress.</span><span class="sxs-lookup"><span data-stu-id="bbc66-164">An origin can be a SharePoint site, document library or folder that is accessible by a URL.</span></span> <span data-ttu-id="bbc66-165">Du har stor flexibilitet när du anger ursprung för din organisation.</span><span class="sxs-lookup"><span data-stu-id="bbc66-165">You have great flexibility when you specify origins for your organization.</span></span> <span data-ttu-id="bbc66-166">Du kan till exempel ange flera ursprung eller ett enda ursprung där du vill lägga till alla dina CDN-till gångar.</span><span class="sxs-lookup"><span data-stu-id="bbc66-166">For example, you can specify multiple origins or a single origin where you want to put all your CDN assets.</span></span> <span data-ttu-id="bbc66-167">Du kan välja att ha både offentliga eller privata ursprung för organisationen.</span><span class="sxs-lookup"><span data-stu-id="bbc66-167">You can choose to have both public or private origins for your organization.</span></span> <span data-ttu-id="bbc66-168">De flesta organisationer väljer att implementera en kombination av båda.</span><span class="sxs-lookup"><span data-stu-id="bbc66-168">Most organizations will choose to implement a combination of the two.</span></span>

<span data-ttu-id="bbc66-169">Du kan skapa en ny behållare för dina ursprung, till exempel mappar eller dokument bibliotek, och lägga till filer som du vill göra tillgängliga från CDN.</span><span class="sxs-lookup"><span data-stu-id="bbc66-169">You can create new container for your origins such as folders or document libraries, and add files you want to make available from the CDN.</span></span> <span data-ttu-id="bbc66-170">Det här är en bra metod om du har en specifik uppsättning till till gångar som du vill ska vara tillgängliga från CDN och bara vill begränsa uppsättningen av CDN-till gångar till filerna i behållaren.</span><span class="sxs-lookup"><span data-stu-id="bbc66-170">This is a good approach if you have a specific set of assets you want to be available from the CDN, and want to restrict the set of CDN assets to only those files in the container.</span></span>

<span data-ttu-id="bbc66-171">Du kan också konfigurera en befintlig webbplats samling, en webbplats, ett bibliotek eller en mapp som ursprung, som gör alla godkända till gångar i behållaren tillgängliga från CDN.</span><span class="sxs-lookup"><span data-stu-id="bbc66-171">You can also configure an existing site collection, site, library or folder as an origin, which will make all eligible assets in the container available from the CDN.</span></span> <span data-ttu-id="bbc66-172">Innan du lägger till en befintlig behållare som ett ursprung är det viktigt att se till att du är medveten om dess innehåll och behörigheter så att du inte oavsiktligt exponerar till gångar för anonym åtkomst eller obehöriga användare.</span><span class="sxs-lookup"><span data-stu-id="bbc66-172">Before you add an existing container as an origin, it's important to make sure you are aware of its contents and permissions so you do not inadvertently expose assets to anonymous access or unauthorized users.</span></span>

<span data-ttu-id="bbc66-173">Du kan definiera _CDN-principer_ för att exkludera innehåll i ursprungen från CDN.</span><span class="sxs-lookup"><span data-stu-id="bbc66-173">You can define _CDN policies_ to exclude content in your origins from the CDN.</span></span> <span data-ttu-id="bbc66-174">CDN-principer exkluderar till gångar i offentliga eller privata ursprung utifrån attribut som _filtyp_ och _webbplats klassificering_och tillämpas på alla ursprung i CdnType (privat eller offentlig) som du anger i principen.</span><span class="sxs-lookup"><span data-stu-id="bbc66-174">CDN policies exclude assets in public or private origins by attributes such as _file type_ and _site classification_, and are applied to all origins of the CdnType (private or public) you specify in the policy.</span></span> <span data-ttu-id="bbc66-175">Om du till exempel lägger till ett privat ursprung som består av en webbplats som innehåller flera under webbplatser kan du definiera en princip som utesluter webbplatser som är markerade som **hemliga** så att innehållet från webbplatser med den klassificeringen inte kommer att betjänas från CDN.</span><span class="sxs-lookup"><span data-stu-id="bbc66-175">For example, if you add a private origin consisting of a site that contains multiple subsites, you can define a policy to exclude sites marked as **Confidential** so content from sites with that classification applied will not be served from the CDN.</span></span> <span data-ttu-id="bbc66-176">Policyn gäller för innehåll från _alla_ privata ursprung som du har lagt till i CDN.</span><span class="sxs-lookup"><span data-stu-id="bbc66-176">The policy will apply to content from _all_ private origins you have added to the CDN.</span></span>
  
<span data-ttu-id="bbc66-177">Kom ihåg att det större antalet ursprung, desto större är effekten på den tid det tar för CDN-tjänsten att bearbeta förfrågningar.</span><span class="sxs-lookup"><span data-stu-id="bbc66-177">Keep in mind that the greater the number of origins, the greater the impact on the time it takes the CDN service to process requests.</span></span> <span data-ttu-id="bbc66-178">Vi rekommenderar att du begränsar antalet ursprung så mycket som möjligt.</span><span class="sxs-lookup"><span data-stu-id="bbc66-178">We recommend that you limit the number of origins as much as possible.</span></span>
  
<span data-ttu-id="bbc66-179"><a name="CDNOriginChoosePublicPrivate"> </a></span><span class="sxs-lookup"><span data-stu-id="bbc66-179"><a name="CDNOriginChoosePublicPrivate"> </a></span></span>
### <a name="choose-whether-each-origin-should-be-public-or-private"></a><span data-ttu-id="bbc66-180">Välja om varje ursprung ska vara offentligt eller privat</span><span class="sxs-lookup"><span data-stu-id="bbc66-180">Choose whether each origin should be public or private</span></span>

<span data-ttu-id="bbc66-181">När du identifierar ett ursprung anger du om det ska göras _offentligt_ eller _privat_.</span><span class="sxs-lookup"><span data-stu-id="bbc66-181">When you identify an origin, you specify whether it should be made _public_ or _private_.</span></span> <span data-ttu-id="bbc66-182">Åtkomst till CDN-till gångar i offentliga ursprung är anonymt och CDN-innehåll i privata ursprung skyddas genom dynamiskt genererade token för ökad säkerhet.</span><span class="sxs-lookup"><span data-stu-id="bbc66-182">Access to CDN assets in public origins is anonymous, and CDN content in private origins is secured by dynamically generated tokens for greater security.</span></span> <span data-ttu-id="bbc66-183">Oavsett vilket alternativ du väljer gör Microsoft all den tungan när det gäller administrationen av själva CDN.</span><span class="sxs-lookup"><span data-stu-id="bbc66-183">Regardless of which option you choose, Microsoft does all the heavy lifting for you when it comes to administration of the CDN itself.</span></span> <span data-ttu-id="bbc66-184">Du kan också ändra dina tankar senare, efter att du har konfigurerat CDN och identifierat dina ursprung.</span><span class="sxs-lookup"><span data-stu-id="bbc66-184">Also, you can change your mind later, after you've set up the CDN and identified your origins.</span></span>

<span data-ttu-id="bbc66-185">Både offentliga och privata alternativ ger liknande prestanda vinster men alla har unika attribut och fördelar.</span><span class="sxs-lookup"><span data-stu-id="bbc66-185">Both public and private options provide similar performance gains, but each has unique attributes and advantages.</span></span>

<span data-ttu-id="bbc66-186">**Offentliga** ursprung i Office 365 CDN är tillgängliga anonymt och värdbaserade till gångar kan nås av alla som har URL-adressen till till gången.</span><span class="sxs-lookup"><span data-stu-id="bbc66-186">**Public** origins within the Office 365 CDN are accessible anonymously, and hosted assets can be accessed by anyone who has the URL to the asset.</span></span> <span data-ttu-id="bbc66-187">Eftersom åtkomsten till innehåll i offentliga ursprung är anonym bör du endast använda dem för att cachelagra icke-känsligt allmänt innehåll, till exempel JavaScript-filer, skript, ikoner och bilder.</span><span class="sxs-lookup"><span data-stu-id="bbc66-187">Because access to content in public origins is anonymous, you should only use them to cache non-sensitive generic content such as javascript files, scripts, icons and images.</span></span>

<span data-ttu-id="bbc66-188">**Privata** ursprung i Office 365 CDN ger privat åtkomst till användar innehåll som SharePoint Online-dokumentbibliotek, webbplatser och grafik.</span><span class="sxs-lookup"><span data-stu-id="bbc66-188">**Private** origins within the Office 365 CDN provide private access to user content such as SharePoint Online document libraries, sites and proprietary images.</span></span> <span data-ttu-id="bbc66-189">Åtkomst till innehåll i privata ursprung skyddas genom dynamiskt genererade token så att användare som har behörighet till det ursprungliga dokument biblioteket eller lagrings platsen endast kan komma åt det.</span><span class="sxs-lookup"><span data-stu-id="bbc66-189">Access to content in private origins is secured by dynamically generated tokens so it can only be accessed by users with permissions to the original document library or storage location.</span></span> <span data-ttu-id="bbc66-190">Privata ursprung i Office 365 CDN kan endast användas till till gångar i privata ursprung genom omdirigering från din SharePoint Online-klient.</span><span class="sxs-lookup"><span data-stu-id="bbc66-190">Private origins in the Office 365 CDN can only be used for SharePoint Online content, and you can only access assets in private origins through redirection from your SharePoint Online tenant.</span></span>

<span data-ttu-id="bbc66-191">Du kan läsa mer om hur CDN får åtkomst till till gångar i ett privat ursprung i [använda till gångar i privata ursprung](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins).</span><span class="sxs-lookup"><span data-stu-id="bbc66-191">You can read more about how CDN access to assets in a private origin works in [Using assets in private origins](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins).</span></span>

#### <a name="attributes-and-advantages-of-hosting-assets-in-public-origins"></a><span data-ttu-id="bbc66-192">Attribut och fördelar med att låta till gångar i offentliga ursprung</span><span class="sxs-lookup"><span data-stu-id="bbc66-192">Attributes and advantages of hosting assets in public origins</span></span>
  
+ <span data-ttu-id="bbc66-193">Till gångar som är utsatta med offentligt ursprung är tillgängliga för alla anonymt.</span><span class="sxs-lookup"><span data-stu-id="bbc66-193">Assets exposed in a public origin are accessible by everyone anonymously.</span></span>
    > [!IMPORTANT]
    > <span data-ttu-id="bbc66-194">Du bör aldrig placera resurser som innehåller användar information eller anses vara känsliga för organisationen i ett offentligt ursprung.</span><span class="sxs-lookup"><span data-stu-id="bbc66-194">You should never place resources that contain user information or are considered sensitive to your organization in a public origin.</span></span>
+ <span data-ttu-id="bbc66-195">Om du tar bort en till gång från ett offentligt ursprung kan till gången fortsätta vara tillgänglig i upp till 30 dagar från cachen; Vi kommer inte att validera länkar till till gången i CDN inom 15 minuter.</span><span class="sxs-lookup"><span data-stu-id="bbc66-195">If you remove an asset from a public origin, the asset may continue to be available for up to 30 days from the cache; however, we will invalidate links to the asset in the CDN within 15 minutes.</span></span>
+ <span data-ttu-id="bbc66-196">När du är värd för formatmallar (CSS-filer) i ett offentligt ursprung kan du använda relativa sökvägar och URI: er i koden.</span><span class="sxs-lookup"><span data-stu-id="bbc66-196">When you host style sheets (CSS files) in a public origin, you can use relative paths and URIs within the code.</span></span> <span data-ttu-id="bbc66-197">Det innebär att du kan referera till platsen för bakgrunds bilder och andra objekt i förhållande till den plats där den som ringer till till gången finns.</span><span class="sxs-lookup"><span data-stu-id="bbc66-197">This means that you can reference the location of background images and other objects relative to the location of the asset that's calling it.</span></span>
+ <span data-ttu-id="bbc66-198">Vi rekommenderar inte att du använder en fast kod för ett offentligt ursprung.</span><span class="sxs-lookup"><span data-stu-id="bbc66-198">While you can hard code a public origin's URL, doing so is not recommended.</span></span> <span data-ttu-id="bbc66-199">Anledningen till detta är att om åtkomsten till CDN inte är tillgänglig kommer URL-adressen inte automatiskt att lösas till din organisation i SharePoint Online och kan leda till felaktiga länkar och andra fel.</span><span class="sxs-lookup"><span data-stu-id="bbc66-199">The reason for this is that if access to the CDN becomes unavailable, the URL will not automatically resolve to your organization in SharePoint Online and might result in broken links and other errors.</span></span>
+ <span data-ttu-id="bbc66-200">De standard fil typer som ingår i offentliga ursprung är. CSS,. EOT,. gif,. ico,. jpeg,. jpg,. js,. map,. png,. SVG,. ttf,. WOFF och. woff2.</span><span class="sxs-lookup"><span data-stu-id="bbc66-200">The default file types that are included for public origins are .css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff and .woff2.</span></span> <span data-ttu-id="bbc66-201">Du kan ange Ytterligare filtyper.</span><span class="sxs-lookup"><span data-stu-id="bbc66-201">You can specify additional file types.</span></span>
+ <span data-ttu-id="bbc66-202">Du kan konfigurera en princip för att exkludera till gångar som identifieras av webbplats klassificeringar som du anger.</span><span class="sxs-lookup"><span data-stu-id="bbc66-202">You can configure a policy to exclude assets that have been identified by site classifications that you specify.</span></span> <span data-ttu-id="bbc66-203">Du kan till exempel välja att exkludera alla till gångar som är markerade som "konfidentiella" eller "begränsade" även om de är en tillåten filtyp och är placerade i ett offentligt ursprung.</span><span class="sxs-lookup"><span data-stu-id="bbc66-203">For example, you can choose to exclude all assets that are marked as "confidential" or "restricted" even if they are an allowed file type and are located in a public origin.</span></span>

#### <a name="attributes-and-advantages-of-hosting-assets-in-private-origins"></a><span data-ttu-id="bbc66-204">Attribut och fördelar med att vara värd för till gångar i privata ursprung</span><span class="sxs-lookup"><span data-stu-id="bbc66-204">Attributes and advantages of hosting assets in private origins</span></span>

+ <span data-ttu-id="bbc66-205">Privata ursprung kan endast användas för SharePoint Online-till gångar.</span><span class="sxs-lookup"><span data-stu-id="bbc66-205">Private origins can only be used for SharePoint Online assets.</span></span>
+ <span data-ttu-id="bbc66-206">Användare kan bara komma åt till gångar från ett privat ursprung om de har behörighet att komma åt behållaren.</span><span class="sxs-lookup"><span data-stu-id="bbc66-206">Users can only access the assets from a private origin if they have permissions to access the container.</span></span> <span data-ttu-id="bbc66-207">Anonym åtkomst till dessa till gångar förhindras.</span><span class="sxs-lookup"><span data-stu-id="bbc66-207">Anonymous access to these assets is prevented.</span></span>
+ <span data-ttu-id="bbc66-208">Till gångar i privata ursprung måste hänvisas till i SharePoint Online-klient organisationen.</span><span class="sxs-lookup"><span data-stu-id="bbc66-208">Assets in private origins must be referred from the SharePoint Online tenant.</span></span> <span data-ttu-id="bbc66-209">Direkt åtkomst till privata CDN-objekt fungerar inte.</span><span class="sxs-lookup"><span data-stu-id="bbc66-209">Direct access to private CDN assets does not work.</span></span>
+ <span data-ttu-id="bbc66-210">Om du tar bort en till gång från privat ursprung kan till gången fortsätta vara tillgänglig för upp till en timme från cachen; Vi kommer att validera länkar till till gången i CDN inom 15 minuter efter det att du har avlägsnat den.</span><span class="sxs-lookup"><span data-stu-id="bbc66-210">If you remove an asset from the private origin, the asset may continue to be available for up to an hour from the cache; however, we will invalidate links to the asset in the CDN within 15 minutes of the asset's removal.</span></span>
+ <span data-ttu-id="bbc66-211">De standard fil typer som ingår i privata ursprung är. gif,. ico,. jpeg,. jpg,. js och. png.</span><span class="sxs-lookup"><span data-stu-id="bbc66-211">The default file types that are included for private origins are .gif, .ico, .jpeg, .jpg, .js, and .png.</span></span> <span data-ttu-id="bbc66-212">Du kan ange Ytterligare filtyper.</span><span class="sxs-lookup"><span data-stu-id="bbc66-212">You can specify additional file types.</span></span>
+ <span data-ttu-id="bbc66-213">Precis som med offentliga ursprung kan du konfigurera en princip för att exkludera till gångar som identifieras av webbplats klassificeringar som du anger även om du använder jokertecken för att inkludera alla till gångar i en mapp eller ett dokument bibliotek.</span><span class="sxs-lookup"><span data-stu-id="bbc66-213">Just like with public origins, you can configure a policy to exclude assets that have been identified by site classifications that you specify even if you use wildcards to include all assets within a folder or document library.</span></span>

<span data-ttu-id="bbc66-214">Mer information om varför du ska använda Office 365 CDN, allmänna CDN-begreppen och andra Microsoft-CDN som du kan använda med Office 365-klient organisationen finns i avsnittet [innehålls leverans nätverk](content-delivery-networks.md).</span><span class="sxs-lookup"><span data-stu-id="bbc66-214">For more information about why to use the Office 365 CDN, general CDN concepts, and other Microsoft CDNs you can use with your Office 365 tenant, see [Content Delivery Networks](content-delivery-networks.md).</span></span>

### <a name="default-cdn-origins"></a><span data-ttu-id="bbc66-215">Standard ursprung för CDN</span><span class="sxs-lookup"><span data-stu-id="bbc66-215">Default CDN origins</span></span>

<span data-ttu-id="bbc66-216">Om du inte anger något annat kommer Office 365 att ställa in vissa standard ursprung när du aktiverar Office 365 CDN.</span><span class="sxs-lookup"><span data-stu-id="bbc66-216">Unless you specify otherwise, Office 365 sets up some default origins for you when you enable the Office 365 CDN.</span></span> <span data-ttu-id="bbc66-217">Om du inte har avaktiverat dem kan du lägga till dessa ursprung när du har slutfört installationen.</span><span class="sxs-lookup"><span data-stu-id="bbc66-217">If you initially opt not to provision them, you can add these origins after you complete setup.</span></span> <span data-ttu-id="bbc66-218">Om du inte förstår följderna av att hoppa över inställningen av standard ursprung och har särskilda skäl för att göra det, bör du tillåta att dessa skapas när du aktiverar CDN.</span><span class="sxs-lookup"><span data-stu-id="bbc66-218">Unless you understand the consequences of skipping the setup of default origins and have a specific reason for doing so, you should allow them to be created when you enable the CDN.</span></span>
  
<span data-ttu-id="bbc66-219">Standard privata CDN-ursprung:</span><span class="sxs-lookup"><span data-stu-id="bbc66-219">Default private CDN origins:</span></span>
  
+ <span data-ttu-id="bbc66-220">\*/userphoto.aspx</span><span class="sxs-lookup"><span data-stu-id="bbc66-220">\*/userphoto.aspx</span></span>
+ <span data-ttu-id="bbc66-221">\*/siteassets</span><span class="sxs-lookup"><span data-stu-id="bbc66-221">\*/siteassets</span></span>

<span data-ttu-id="bbc66-222">Standard allmänna CDN-ursprung:</span><span class="sxs-lookup"><span data-stu-id="bbc66-222">Default public CDN origins:</span></span>
  
+ <span data-ttu-id="bbc66-223">\*/masterpage</span><span class="sxs-lookup"><span data-stu-id="bbc66-223">\*/masterpage</span></span>
+ <span data-ttu-id="bbc66-224">\*/Style-bibliotek</span><span class="sxs-lookup"><span data-stu-id="bbc66-224">\*/style library</span></span>
+ <span data-ttu-id="bbc66-225">\*/clientsideassets</span><span class="sxs-lookup"><span data-stu-id="bbc66-225">\*/clientsideassets</span></span>

> [!NOTE]
> <span data-ttu-id="bbc66-226">_clientsideassets_ är ett offentligt standard ursprung som lagts till i Office 365 CDN-tjänsten i december 2017.</span><span class="sxs-lookup"><span data-stu-id="bbc66-226">_clientsideassets_ is a default public origin that was added to the Office 365 CDN service in December 2017.</span></span> <span data-ttu-id="bbc66-227">Detta måste finnas för att SharePoint Framework-lösningarna i CDN ska fungera.</span><span class="sxs-lookup"><span data-stu-id="bbc66-227">This origin must be present in order for SharePoint Framework solutions in the CDN to work.</span></span> <span data-ttu-id="bbc66-228">Om du har aktiverat Office 365 CDN före den 2017 december, eller om du hoppat över installationen av standard ursprung när du aktiverade CDN, kan du manuellt lägga till det här ursprunget.</span><span class="sxs-lookup"><span data-stu-id="bbc66-228">If you enabled the Office 365 CDN prior to December 2017, or if you skipped setup of default origins when you enabled the CDN, you can manually add this origin.</span></span> <span data-ttu-id="bbc66-229">Mer information finns i min webbdel för [klient-eller SharePoint-ramverk fungerar inte](use-microsoft-365-cdn-with-spo.md#my-client-side-web-part-or-sharepoint-framework-solution-isnt-working).</span><span class="sxs-lookup"><span data-stu-id="bbc66-229">For more information, see [My client-side web part or SharePoint Framework solution isn't working](use-microsoft-365-cdn-with-spo.md#my-client-side-web-part-or-sharepoint-framework-solution-isnt-working).</span></span>

<span data-ttu-id="bbc66-230"><a name="CDNSetupinPShell"> </a></span><span class="sxs-lookup"><span data-stu-id="bbc66-230"><a name="CDNSetupinPShell"> </a></span></span>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell"></a><span data-ttu-id="bbc66-231">Konfigurera och konfigurera Office 365 CDN med hjälp av SharePoint Online Management Shell</span><span class="sxs-lookup"><span data-stu-id="bbc66-231">Set up and configure the Office 365 CDN by using the SharePoint Online Management Shell</span></span>

<span data-ttu-id="bbc66-232">Procedurerna i det här avsnittet kräver att du använder SharePoint Online Management Shell för att ansluta till SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="bbc66-232">The procedures in this section require you to use the SharePoint Online Management Shell to connect to SharePoint Online.</span></span> <span data-ttu-id="bbc66-233">Anvisningar finns i [ansluta till SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span><span class="sxs-lookup"><span data-stu-id="bbc66-233">For instructions, see [Connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

<span data-ttu-id="bbc66-234">Utför de här stegen för att konfigurera och konfigurera CDN så att dina till gångar i SharePoint Online används med SharePoint Online Management Shell.</span><span class="sxs-lookup"><span data-stu-id="bbc66-234">Complete these steps to set up and configure the CDN to host your assets in SharePoint Online using the SharePoint Online Management Shell.</span></span>

<details>
  <summary><span data-ttu-id="bbc66-235">Klicka för att Visa</span><span class="sxs-lookup"><span data-stu-id="bbc66-235">Click to expand</span></span></summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a><span data-ttu-id="bbc66-236">Aktivera din organisation för att använda Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="bbc66-236">Enable your organization to use the Office 365 CDN</span></span>

<span data-ttu-id="bbc66-237">Innan du ändrar status för klient organisationen måste du hämta den aktuella statusen för privat CDN-konfigurationen i Office 365-klient organisationen.</span><span class="sxs-lookup"><span data-stu-id="bbc66-237">Before you make changes to the tenant CDN settings, you should retrieve the current status of the private CDN configuration in your Office 365 tenant.</span></span> <span data-ttu-id="bbc66-238">Anslut till klient organisationen med SharePoint Online Management Shell:</span><span class="sxs-lookup"><span data-stu-id="bbc66-238">Connect to your tenant using the SharePoint Online Management Shell:</span></span>

``` powershell
Connect-SPOService -Url https://contoso-admin.sharepoint.com
```

<span data-ttu-id="bbc66-239">Använd cmdleten **Get-SPOTenantCdnEnabled** för att hämta status inställningar för CDN från klient organisationen:</span><span class="sxs-lookup"><span data-stu-id="bbc66-239">Now use the **Get-SPOTenantCdnEnabled** cmdlet to retrieve the CDN status settings from the tenant:</span></span>

``` powershell
Get-SPOTenantCdnEnabled -CdnType <Public | Private>
```

<span data-ttu-id="bbc66-240">Statusen för CDN för angiven CdnType kommer att matas ut till skärmen.</span><span class="sxs-lookup"><span data-stu-id="bbc66-240">The status of the CDN for the specified CdnType will output to the screen.</span></span>

<span data-ttu-id="bbc66-241">Använd cmdleten **set-SPOTenantCdnEnabled** för att göra det möjligt för organisationen att använda Office 365 CDN.</span><span class="sxs-lookup"><span data-stu-id="bbc66-241">Use the **Set-SPOTenantCdnEnabled** cmdlet to enable your organization to use the Office 365 CDN.</span></span> <span data-ttu-id="bbc66-242">Du kan göra det möjligt för organisationen att använda offentliga ursprung, privata ursprung eller båda samtidigt.</span><span class="sxs-lookup"><span data-stu-id="bbc66-242">You can enable your organization to use public origins, private origins, or both at once.</span></span> <span data-ttu-id="bbc66-243">Du kan också konfigurera CDN för att hoppa över inställningen av standard ursprung när du aktiverar det.</span><span class="sxs-lookup"><span data-stu-id="bbc66-243">You can also configure the CDN to skip the setup of default origins when you enable it.</span></span> <span data-ttu-id="bbc66-244">Du kan alltid lägga till dessa ursprung senare enligt beskrivningen i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="bbc66-244">You can always add these origins later as described in this topic.</span></span>
  
<span data-ttu-id="bbc66-245">I Windows PowerShell för SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="bbc66-245">In Windows Powershell for SharePoint Online:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

<span data-ttu-id="bbc66-246">Om du till exempel vill aktivera organisationen att använda både offentliga och privata ursprung skriver du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="bbc66-246">For example, to enable your organization to use both public and private origins, type the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

<span data-ttu-id="bbc66-247">Om du vill göra det möjligt för organisationen att använda både offentliga och privata ursprung men hoppa till standard ursprungen skriver du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="bbc66-247">To enable your organization to use both public and private origins but skip setting up the default origins, type the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

<span data-ttu-id="bbc66-248">Se [standard ursprung för CDN](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) för information om ursprung som är etablerade som standard när du aktiverar Office 365 CDN och den potentiella effekten av att hoppa över inställningen av standard ursprung.</span><span class="sxs-lookup"><span data-stu-id="bbc66-248">See [Default CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) for information about the origins that are provisioned by default when you enable the Office 365 CDN, and the potential impact of skipping the setup of default origins.</span></span>

<span data-ttu-id="bbc66-249">Om du vill aktivera organisationen att använda offentliga ursprung skriver du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="bbc66-249">To enable your organization to use public origins, type the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $true
```

<span data-ttu-id="bbc66-250">Om du vill aktivera din organisation att använda privata ursprung skriver du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="bbc66-250">To enable your organization to use private origins, type the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $true
```

<span data-ttu-id="bbc66-251">Mer information om den här cmdleten finns i [set-SPOTenantCdnEnabled](https://technet.microsoft.com/library/mt790765.aspx).</span><span class="sxs-lookup"><span data-stu-id="bbc66-251">For more information about this cmdlet, see [Set-SPOTenantCdnEnabled](https://technet.microsoft.com/library/mt790765.aspx).</span></span>

<span data-ttu-id="bbc66-252"><a name="Office365CDNforSPOFileType"> </a></span><span class="sxs-lookup"><span data-stu-id="bbc66-252"><a name="Office365CDNforSPOFileType"> </a></span></span>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a><span data-ttu-id="bbc66-253">Ändra listan över filtyper som ska ingå i Office 365 CDN (valfritt)</span><span class="sxs-lookup"><span data-stu-id="bbc66-253">Change the list of file types to include in the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="bbc66-254">När du definierar filtyper med hjälp av cmdleten **set-SPOTenantCdnPolicy** skriver du över den för tillfället definierade listan.</span><span class="sxs-lookup"><span data-stu-id="bbc66-254">When you define file types by using the **Set-SPOTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="bbc66-255">Om du vill lägga till fler filtyper i listan kan du använda cmdleten först för att ta reda på vilka filtyper som redan är tillåtna och lägga till dem i listan tillsammans med nya filer.</span><span class="sxs-lookup"><span data-stu-id="bbc66-255">If you want to add additional file types to the list, use the cmdlet first to find out what file types are already allowed and include them in the list along with your new ones.</span></span>
  
<span data-ttu-id="bbc66-256">Använd cmdleten **set-SPOTenantCdnPolicy** för att definiera statiska filtyper som kan hanteras av offentliga och privata ursprung i CDN.</span><span class="sxs-lookup"><span data-stu-id="bbc66-256">Use the **Set-SPOTenantCdnPolicy** cmdlet to define static file types that can be hosted by public and private origins in the CDN.</span></span> <span data-ttu-id="bbc66-257">Som standard tillåts vanliga typer av till gångar, till exempel. CSS,. gif,. jpg och. js.</span><span class="sxs-lookup"><span data-stu-id="bbc66-257">By default, common asset types are allowed, for example .css, .gif, .jpg, and .js.</span></span>

<span data-ttu-id="bbc66-258">I Windows PowerShell för SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="bbc66-258">In Windows PowerShell for SharePoint Online:</span></span>

``` powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

<span data-ttu-id="bbc66-259">Om du till exempel vill aktivera CDN som Host. CSS-och. png-filer anger du kommandot:</span><span class="sxs-lookup"><span data-stu-id="bbc66-259">For example, to enable the CDN to host .css and .png files, you would enter the command:</span></span>

``` powershell
Set-SPOTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

<span data-ttu-id="bbc66-260">Använd cmdleten **Get-SPOTenantCdnPolicies** för att se vilka filtyper som för närvarande tillåts av CDN:</span><span class="sxs-lookup"><span data-stu-id="bbc66-260">To see what file types are currently allowed by the CDN, use the **Get-SPOTenantCdnPolicies** cmdlet:</span></span>

``` powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="bbc66-261">Mer information om dessa cmdletar finns i [set-SPOTenantCdnPolicy](https://technet.microsoft.com/library/mt800839.aspx) and [Get-SPOTenantCdnPolicies](https://technet.microsoft.com/library/mt800838.aspx).</span><span class="sxs-lookup"><span data-stu-id="bbc66-261">For more information about these cmdlets, see [Set-SPOTenantCdnPolicy](https://technet.microsoft.com/library/mt800839.aspx) and [Get-SPOTenantCdnPolicies](https://technet.microsoft.com/library/mt800838.aspx).</span></span>

<span data-ttu-id="bbc66-262"><a name="Office365CDNforSPOSiteClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="bbc66-262"><a name="Office365CDNforSPOSiteClassification"> </a></span></span>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a><span data-ttu-id="bbc66-263">Ändra listan över webbplats klassificeringar som du vill undanta från Office 365 CDN (valfritt)</span><span class="sxs-lookup"><span data-stu-id="bbc66-263">Change the list of site classifications you want to exclude from the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="bbc66-264">När du undantar webbplats klassificeringar med cmdleten **set-SPOTenantCdnPolicy** skriver du över den för tillfället definierade listan.</span><span class="sxs-lookup"><span data-stu-id="bbc66-264">When you exclude site classifications by using the **Set-SPOTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="bbc66-265">Om du vill undanta ytterligare webbplats klassificeringar kan du använda cmdleten först för att ta reda på vilka klassificeringar som redan är undantagna och sedan lägga till dem tillsammans med dina nya.</span><span class="sxs-lookup"><span data-stu-id="bbc66-265">If you want to exclude additional site classifications, use the cmdlet first to find out what classifications are already excluded and then add them along with your new ones.</span></span>

<span data-ttu-id="bbc66-266">Använd cmdleten **set-SPOTenantCdnPolicy** för att undanta webbplats klassificeringar som du inte vill göra tillgängliga via CDN.</span><span class="sxs-lookup"><span data-stu-id="bbc66-266">Use the **Set-SPOTenantCdnPolicy** cmdlet to exclude site classifications that you do not want to make available over the CDN.</span></span> <span data-ttu-id="bbc66-267">Som standard utesluts inga webbplats klassificeringar.</span><span class="sxs-lookup"><span data-stu-id="bbc66-267">By default, no site classifications are excluded.</span></span>

<span data-ttu-id="bbc66-268">I Windows PowerShell för SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="bbc66-268">In Windows PowerShell for SharePoint Online:</span></span>

``` powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications >"
```

<span data-ttu-id="bbc66-269">Om du vill se vilka webbplats klassificeringar som är begränsade använder du cmdleten **Get-SPOTenantCdnPolicies** :</span><span class="sxs-lookup"><span data-stu-id="bbc66-269">To see what site classifications are currently restricted, use the **Get-SPOTenantCdnPolicies** cmdlet:</span></span>

``` powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="bbc66-270">De egenskaper som kommer att returneras är _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ och _ExcludeIfNoScriptDisabled_.</span><span class="sxs-lookup"><span data-stu-id="bbc66-270">The properties that will be returned are _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ and _ExcludeIfNoScriptDisabled_.</span></span>

<span data-ttu-id="bbc66-271">Egenskapen _IncludeFileExtensions_ innehåller en lista över fil namns tillägg som kommer att betjänas från CDN.</span><span class="sxs-lookup"><span data-stu-id="bbc66-271">The _IncludeFileExtensions_ property contains the list of file extensions that will be served from the CDN.</span></span>

> [!NOTE]
> <span data-ttu-id="bbc66-272">Standard fil namns tilläggen skiljer sig mellan offentliga och privata.</span><span class="sxs-lookup"><span data-stu-id="bbc66-272">The default file extensions are different between public and private.</span></span>

<span data-ttu-id="bbc66-273">Egenskapen _ExcludeRestrictedSiteClassifications_ innehåller de webbplats klassificeringar som du vill undanta från CDN.</span><span class="sxs-lookup"><span data-stu-id="bbc66-273">The _ExcludeRestrictedSiteClassifications_ property contains the site classifications that you want to exclude from the CDN.</span></span> <span data-ttu-id="bbc66-274">Du kan till exempel utesluta webbplatser som marker ATS som **konfidentiella** så att innehållet från webbplatser med den klassificeringen inte kommer att betjänas från CDN.</span><span class="sxs-lookup"><span data-stu-id="bbc66-274">For example, you can exclude sites marked as **Confidential** so content from sites with that classification applied will not be served from the CDN.</span></span>

<span data-ttu-id="bbc66-275">Egenskapen _ExcludeIfNoScriptDisabled_ exkluderar innehåll från CDN baserat på Inställningar för _NoScript_ på webbplats nivå.</span><span class="sxs-lookup"><span data-stu-id="bbc66-275">The _ExcludeIfNoScriptDisabled_ property excludes content from the CDN based on the site-level _NoScript_ attribute settings.</span></span> <span data-ttu-id="bbc66-276">Som standard är attributet _NoScript_ **aktiverat** för _moderna_ webbplatser och är **inaktiverat** för _klassiska_ webbplatser.</span><span class="sxs-lookup"><span data-stu-id="bbc66-276">By default, the _NoScript_ attribute is set to **Enabled** for _Modern_ sites and **Disabled** for _Classic_ sites.</span></span> <span data-ttu-id="bbc66-277">Detta beror på klientens inställningar.</span><span class="sxs-lookup"><span data-stu-id="bbc66-277">This depends on your tenant settings.</span></span>

<span data-ttu-id="bbc66-278">Mer information om dessa cmdletar finns i [set-SPOTenantCdnPolicy](https://technet.microsoft.com/library/mt800839.aspx) and [Get-SPOTenantCdnPolicies](https://technet.microsoft.com/library/mt800838.aspx).</span><span class="sxs-lookup"><span data-stu-id="bbc66-278">For more information about these cmdlets, see [Set-SPOTenantCdnPolicy](https://technet.microsoft.com/library/mt800839.aspx) and [Get-SPOTenantCdnPolicies](https://technet.microsoft.com/library/mt800838.aspx).</span></span>

<span data-ttu-id="bbc66-279"><a name="Office365CDNforSPOOriginPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="bbc66-279"><a name="Office365CDNforSPOOriginPosh"> </a></span></span>
### <a name="add-an-origin-for-your-assets"></a><span data-ttu-id="bbc66-280">Lägga till ett ursprung för dina till gångar</span><span class="sxs-lookup"><span data-stu-id="bbc66-280">Add an origin for your assets</span></span>

<span data-ttu-id="bbc66-281">Använd cmdleten **Add-SPOTenantCdnOrigin** för att definiera ett ursprung.</span><span class="sxs-lookup"><span data-stu-id="bbc66-281">Use the **Add-SPOTenantCdnOrigin** cmdlet to define an origin.</span></span> <span data-ttu-id="bbc66-282">Du kan definiera flera ursprung.</span><span class="sxs-lookup"><span data-stu-id="bbc66-282">You can define multiple origins.</span></span> <span data-ttu-id="bbc66-283">Origo är en URL som pekar på ett SharePoint-bibliotek eller en mapp som innehåller de objekt som du vill ska hanteras av CDN.</span><span class="sxs-lookup"><span data-stu-id="bbc66-283">The origin is a URL that points to a SharePoint library or folder that contains the assets that you want to be hosted by the CDN.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="bbc66-284">Du bör aldrig placera resurser som innehåller användar information eller anses vara känsliga för organisationen i ett offentligt ursprung.</span><span class="sxs-lookup"><span data-stu-id="bbc66-284">You should never place resources that contain user information or are considered sensitive to your organization in a public origin.</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

<span data-ttu-id="bbc66-285">Värdet för _Path_ är den relativa sökvägen till det bibliotek eller den mapp som innehåller till gångarna.</span><span class="sxs-lookup"><span data-stu-id="bbc66-285">The value of _path_ is the relative path to the library or folder that contains the assets.</span></span> <span data-ttu-id="bbc66-286">Du kan använda jokertecken utöver relativa sökvägar.</span><span class="sxs-lookup"><span data-stu-id="bbc66-286">You can use wildcards in addition to relative paths.</span></span> <span data-ttu-id="bbc66-287">Ursprung stöd för jokertecken läggs till till URL-adressen.</span><span class="sxs-lookup"><span data-stu-id="bbc66-287">Origins support wildcards prepended to the URL.</span></span> <span data-ttu-id="bbc66-288">Det gör att du kan skapa ursprung som sträcker sig över flera webbplatser.</span><span class="sxs-lookup"><span data-stu-id="bbc66-288">This allows you to create origins that span multiple sites.</span></span> <span data-ttu-id="bbc66-289">Om du till exempel vill ta med alla till gångar i masterpages-mappen för alla webbplatser som ett offentligt ursprung i CDN skriver du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="bbc66-289">For example, to include all of the assets in the masterpages folder for all of your sites as a public origin within the CDN, type the following command:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ <span data-ttu-id="bbc66-290">Jokertecknet \* **/** kan bara användas i början av sökvägen och matchar alla URL-segment under den angivna URL-adressen.</span><span class="sxs-lookup"><span data-stu-id="bbc66-290">The wildcard modifier \***/** can only be used at the beginning of the path, and will match all URL segments under the specified URL.</span></span>
+ <span data-ttu-id="bbc66-291">Sökvägen kan peka på ett dokument bibliotek, en mapp eller en webbplats.</span><span class="sxs-lookup"><span data-stu-id="bbc66-291">The path can point to a document library, folder or site.</span></span> <span data-ttu-id="bbc66-292">Till exempel matchar sökvägen _\*/site1_ alla dokument bibliotek under webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="bbc66-292">For example, the path _\*/site1_ will match all the document libraries under the site.</span></span>

<span data-ttu-id="bbc66-293">Du kan lägga till ett ursprung med en specifik relativ sökväg.</span><span class="sxs-lookup"><span data-stu-id="bbc66-293">You can add an origin with a specific relative path.</span></span> <span data-ttu-id="bbc66-294">Du kan inte lägga till ett ursprung med den fullständiga sökvägen.</span><span class="sxs-lookup"><span data-stu-id="bbc66-294">You cannot add an origin using the full path.</span></span>

<span data-ttu-id="bbc66-295">I det här exemplet läggs ett privat ursprung för siteassets-biblioteket till på en specifik webbplats:</span><span class="sxs-lookup"><span data-stu-id="bbc66-295">This example adds a private origin of the siteassets library on a specific site:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="bbc66-296">Det här exemplet lägger till ett privat ursprung i mappen _Mapp1_ i webbplats samlingens webbplats till gångar-bibliotek:</span><span class="sxs-lookup"><span data-stu-id="bbc66-296">This example adds a private origin of the _folder1_ folder in the site collection's site assets library:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

<span data-ttu-id="bbc66-297">Om det finns ett blank steg i sökvägen kan du antingen omge vägen med citat tecken eller ersätta blank steget med URL-kodningen %20.</span><span class="sxs-lookup"><span data-stu-id="bbc66-297">If there is a space in the path, you can either surround the path in double quotes or replace the space with the URL encoding %20.</span></span> <span data-ttu-id="bbc66-298">Följande exempel lägger till ett privat ursprung för _mappen 1_ i webbplats samlingens webbplats till gångar-bibliotek:</span><span class="sxs-lookup"><span data-stu-id="bbc66-298">The following examples add a private origin of the _folder 1_ folder in the site collection's site assets library:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

<span data-ttu-id="bbc66-299">Mer information om det här kommandot och dess syntax finns i [Add-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790772.aspx).</span><span class="sxs-lookup"><span data-stu-id="bbc66-299">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790772.aspx).</span></span>

> [!NOTE]
> <span data-ttu-id="bbc66-300">I privata ursprung måste till gångar som delas från ett ursprung ha en huvud version publicerad innan de kan nås från CDN.</span><span class="sxs-lookup"><span data-stu-id="bbc66-300">In private origins, assets being shared from an origin must have a major version published before they can be accessed from the CDN.</span></span>
  
<span data-ttu-id="bbc66-301">När du har kört kommandot synkroniseras konfigurationen via data Center.</span><span class="sxs-lookup"><span data-stu-id="bbc66-301">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="bbc66-302">Det kan ta upp till 15 minuter.</span><span class="sxs-lookup"><span data-stu-id="bbc66-302">This can take up to 15 minutes.</span></span>

<span data-ttu-id="bbc66-303"><a name="ExamplePublicOrigin"> </a></span><span class="sxs-lookup"><span data-stu-id="bbc66-303"><a name="ExamplePublicOrigin"> </a></span></span>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a><span data-ttu-id="bbc66-304">Exempel: Konfigurera ett offentligt ursprung för huvud sidorna och för format biblioteket för SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="bbc66-304">Example: Configure a public origin for your master pages and for your style library for SharePoint Online</span></span>

<span data-ttu-id="bbc66-305">Vanligt vis är dessa ursprung för dig som standard när du aktiverar Office 365 CDN.</span><span class="sxs-lookup"><span data-stu-id="bbc66-305">Normally, these origins are set up for you by default when you enable the Office 365 CDN.</span></span> <span data-ttu-id="bbc66-306">Om du vill aktivera dem manuellt följer du de här stegen.</span><span class="sxs-lookup"><span data-stu-id="bbc66-306">However, if you want to enable them manually, follow these steps.</span></span>
  
+ <span data-ttu-id="bbc66-307">Använd cmdleten **Add-SPOTenantCdnOrigin** för att definiera format biblioteket som ett offentligt ursprung.</span><span class="sxs-lookup"><span data-stu-id="bbc66-307">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the style library as a public origin.</span></span>

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ <span data-ttu-id="bbc66-308">Använd cmdleten **Add-SPOTenantCdnOrigin** för att definiera huvud sidorna som ett offentligt ursprung.</span><span class="sxs-lookup"><span data-stu-id="bbc66-308">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the master pages as a public origin.</span></span>

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

<span data-ttu-id="bbc66-309">Mer information om det här kommandot och dess syntax finns i [Add-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790772.aspx).</span><span class="sxs-lookup"><span data-stu-id="bbc66-309">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790772.aspx).</span></span>

<span data-ttu-id="bbc66-310">När du har kört kommandot synkroniseras konfigurationen via data Center.</span><span class="sxs-lookup"><span data-stu-id="bbc66-310">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="bbc66-311">Det kan ta upp till 15 minuter.</span><span class="sxs-lookup"><span data-stu-id="bbc66-311">This can take up to 15 minutes.</span></span>

<span data-ttu-id="bbc66-312"><a name="ExamplePrivateOrigin"> </a></span><span class="sxs-lookup"><span data-stu-id="bbc66-312"><a name="ExamplePrivateOrigin"> </a></span></span>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a><span data-ttu-id="bbc66-313">Exempel: Konfigurera ett privat ursprung för webbplats till gångar, webbplats sidor och publicerings bilder för SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="bbc66-313">Example: Configure a private origin for your site assets, site pages, and publishing images for SharePoint Online</span></span>

+ <span data-ttu-id="bbc66-314">Använd cmdleten **Add-SPOTenantCdnOrigin** för att definiera mappen för webbplats till gångar som ett privat ursprung.</span><span class="sxs-lookup"><span data-stu-id="bbc66-314">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the site assets folder as a private origin.</span></span>

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ <span data-ttu-id="bbc66-315">Använd cmdleten **Add-SPOTenantCdnOrigin** för att definiera mappen för webbplats sidor som ett privat ursprung.</span><span class="sxs-lookup"><span data-stu-id="bbc66-315">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the site pages folder as a private origin.</span></span>

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ <span data-ttu-id="bbc66-316">Använd cmdleten **Add-SPOTenantCdnOrigin** för att definiera mappen för publicerings bilder som ett privat ursprung.</span><span class="sxs-lookup"><span data-stu-id="bbc66-316">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the publishing images folder as a private origin.</span></span>

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

<span data-ttu-id="bbc66-317">Mer information om det här kommandot och dess syntax finns i [Add-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790772.aspx).</span><span class="sxs-lookup"><span data-stu-id="bbc66-317">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790772.aspx).</span></span>

<span data-ttu-id="bbc66-318">När du har kört kommandot synkroniseras konfigurationen via data Center.</span><span class="sxs-lookup"><span data-stu-id="bbc66-318">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="bbc66-319">Det kan ta upp till 15 minuter.</span><span class="sxs-lookup"><span data-stu-id="bbc66-319">This can take up to 15 minutes.</span></span>

<span data-ttu-id="bbc66-320"><a name="ExamplePrivateOriginSiteCollection"> </a></span><span class="sxs-lookup"><span data-stu-id="bbc66-320"><a name="ExamplePrivateOriginSiteCollection"> </a></span></span>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a><span data-ttu-id="bbc66-321">Exempel: Konfigurera ett privat ursprung för en webbplats samling för SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="bbc66-321">Example: Configure a private origin for a site collection for SharePoint Online</span></span>

<span data-ttu-id="bbc66-322">Använd cmdleten **Add-SPOTenantCdnOrigin** för att definiera en webbplats samling som ett privat ursprung.</span><span class="sxs-lookup"><span data-stu-id="bbc66-322">Use the **Add-SPOTenantCdnOrigin** cmdlet to define a site collection as a private origin.</span></span> <span data-ttu-id="bbc66-323">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="bbc66-323">For example:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="bbc66-324">Mer information om det här kommandot och dess syntax finns i [Add-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790772.aspx).</span><span class="sxs-lookup"><span data-stu-id="bbc66-324">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790772.aspx).</span></span>
  
<span data-ttu-id="bbc66-325">När du har kört kommandot synkroniseras konfigurationen via data Center.</span><span class="sxs-lookup"><span data-stu-id="bbc66-325">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="bbc66-326">Du kan se ett meddelande om _väntande konfiguration_ som förväntas som en SharePoint Online-klient ansluter till CDN-tjänsten.</span><span class="sxs-lookup"><span data-stu-id="bbc66-326">You may see a _Configuration pending_ message which is expected as the SharePoint Online tenant connects to the CDN service.</span></span> <span data-ttu-id="bbc66-327">Det kan ta upp till 15 minuter.</span><span class="sxs-lookup"><span data-stu-id="bbc66-327">This can take up to 15 minutes.</span></span>

<span data-ttu-id="bbc66-328"><a name="CDNManage"> </a></span><span class="sxs-lookup"><span data-stu-id="bbc66-328"><a name="CDNManage"> </a></span></span>
### <a name="manage-the-office-365-cdn"></a><span data-ttu-id="bbc66-329">Hantera Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="bbc66-329">Manage the Office 365 CDN</span></span>

<span data-ttu-id="bbc66-330">När du har konfigurerat CDN kan du göra ändringar i konfigurationen när du uppdaterar innehåll eller när dina behov ändras, enligt beskrivningen i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="bbc66-330">Once you've set up the CDN, you can make changes to your configuration as you update content or as your needs change, as described in this section.</span></span>
  
<span data-ttu-id="bbc66-331"><a name="Office365CDNforSPOaddremoveasset"> </a></span><span class="sxs-lookup"><span data-stu-id="bbc66-331"><a name="Office365CDNforSPOaddremoveasset"> </a></span></span>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a><span data-ttu-id="bbc66-332">Lägga till, uppdatera eller ta bort till gångar från Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="bbc66-332">Add, update, or remove assets from the Office 365 CDN</span></span>

<span data-ttu-id="bbc66-333">När du har slutfört konfigurations stegen kan du lägga till nya till gångar och uppdatera eller ta bort befintliga till gångar när du vill.</span><span class="sxs-lookup"><span data-stu-id="bbc66-333">Once you've completed the setup steps, you can add new assets, and update or remove existing assets whenever you want.</span></span> <span data-ttu-id="bbc66-334">Gör dina ändringar i till gångarna i den mapp eller det SharePoint-bibliotek som du angav som ursprung.</span><span class="sxs-lookup"><span data-stu-id="bbc66-334">Just make your changes to the assets in the folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="bbc66-335">Om du lägger till en ny till gång är den tillgänglig via CDN omedelbart.</span><span class="sxs-lookup"><span data-stu-id="bbc66-335">If you add a new asset, it is available through the CDN immediately.</span></span> <span data-ttu-id="bbc66-336">Men om du uppdaterar till gången tar det upp till 15 minuter innan den nya kopian sprids och blir tillgänglig i CDN.</span><span class="sxs-lookup"><span data-stu-id="bbc66-336">However, if you update the asset, it will take up to 15 minutes for the new copy to propagate and become available in the CDN.</span></span>
  
<span data-ttu-id="bbc66-337">Om du behöver hämta plats för ursprunget kan du använda cmdleten **Get-SPOTenantCdnOrigins** .</span><span class="sxs-lookup"><span data-stu-id="bbc66-337">If you need to retrieve the location of the origin, you can use the **Get-SPOTenantCdnOrigins** cmdlet.</span></span> <span data-ttu-id="bbc66-338">Information om hur du använder denna cmdlet finns i [Get-SPOTenantCdnOrigins](https://technet.microsoft.com/library/mt790770.aspx).</span><span class="sxs-lookup"><span data-stu-id="bbc66-338">For information on how to use this cmdlet, see [Get-SPOTenantCdnOrigins](https://technet.microsoft.com/library/mt790770.aspx).</span></span>

<span data-ttu-id="bbc66-339"><a name="Office365CDNforSPORemoveOriginPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="bbc66-339"><a name="Office365CDNforSPORemoveOriginPosh"> </a></span></span>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a><span data-ttu-id="bbc66-340">Ta bort ett ursprung från Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="bbc66-340">Remove an origin from the Office 365 CDN</span></span>

<span data-ttu-id="bbc66-341">Du kan ta bort åtkomst till en mapp eller ett SharePoint-bibliotek som du har identifierat som ett ursprung.</span><span class="sxs-lookup"><span data-stu-id="bbc66-341">You can remove access to a folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="bbc66-342">För att göra det, Använd cmdleten **Remove-SPOTenantCdnOrigin** .</span><span class="sxs-lookup"><span data-stu-id="bbc66-342">To do this, use the **Remove-SPOTenantCdnOrigin** cmdlet.</span></span>

``` powershell
Remove-SPOTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

<span data-ttu-id="bbc66-343">Information om hur du använder den här cmdleten finns i [Remove-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790761.aspx).</span><span class="sxs-lookup"><span data-stu-id="bbc66-343">For information on how to use this cmdlet, see [Remove-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790761.aspx).</span></span>

<span data-ttu-id="bbc66-344"><a name="Office365CDNforSPOModifyOrigin"> </a></span><span class="sxs-lookup"><span data-stu-id="bbc66-344"><a name="Office365CDNforSPOModifyOrigin"> </a></span></span>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a><span data-ttu-id="bbc66-345">Ändra ett ursprung i Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="bbc66-345">Modify an origin in the Office 365 CDN</span></span>

<span data-ttu-id="bbc66-346">Du kan inte ändra ett ursprung som du har skapat.</span><span class="sxs-lookup"><span data-stu-id="bbc66-346">You cannot modify an origin you've created.</span></span> <span data-ttu-id="bbc66-347">I stället kan du ta bort Origo och sedan lägga till ett nytt.</span><span class="sxs-lookup"><span data-stu-id="bbc66-347">Instead, remove the origin and then add a new one.</span></span> <span data-ttu-id="bbc66-348">Mer information finns i [så här tar du bort ett ursprung från Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPosh) och hur [du lägger till till gångar](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPosh).</span><span class="sxs-lookup"><span data-stu-id="bbc66-348">For more information, see [To remove an origin from the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPosh) and [To add an origin for your assets](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPosh).</span></span>

<span data-ttu-id="bbc66-349"><a name="Office365CDNforSPODisable"> </a></span><span class="sxs-lookup"><span data-stu-id="bbc66-349"><a name="Office365CDNforSPODisable"> </a></span></span>
#### <a name="disable-the-office-365-cdn"></a><span data-ttu-id="bbc66-350">Inaktivera Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="bbc66-350">Disable the Office 365 CDN</span></span>

<span data-ttu-id="bbc66-351">Använd cmdleten **set-SPOTenantCdnEnabled** för att inaktivera CDN för organisationen.</span><span class="sxs-lookup"><span data-stu-id="bbc66-351">Use the **Set-SPOTenantCdnEnabled** cmdlet to disable the CDN for your organization.</span></span> <span data-ttu-id="bbc66-352">Om både offentliga och privata ursprung är aktiverade för CDN måste du köra cmdleten två gånger enligt följande exempel.</span><span class="sxs-lookup"><span data-stu-id="bbc66-352">If you have both the public and private origins enabled for the CDN, you need to run the cmdlet twice as shown in the following examples.</span></span>
  
<span data-ttu-id="bbc66-353">Om du vill inaktivera användning av offentliga ursprung i CDN skriver du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="bbc66-353">To disable use of public origins in the CDN, enter the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $false
```

<span data-ttu-id="bbc66-354">Om du vill inaktivera användningen av de privata ursprungen i CDN skriver du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="bbc66-354">To disable use of the private origins in the CDN, enter the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $false
```

<span data-ttu-id="bbc66-355">Mer information om den här cmdleten finns i [set-SPOTenantCdnEnabled](https://technet.microsoft.com/library/mt790765.aspx).</span><span class="sxs-lookup"><span data-stu-id="bbc66-355">For more information about this cmdlet, see [Set-SPOTenantCdnEnabled](https://technet.microsoft.com/library/mt790765.aspx).</span></span>

</details>

<span data-ttu-id="bbc66-356"><a name="CDNSetupinPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="bbc66-356"><a name="CDNSetupinPnPPosh"> </a></span></span>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-pnp-powershell"></a><span data-ttu-id="bbc66-357">Konfigurera och konfigurera Office 365 CDN med PnP PowerShell</span><span class="sxs-lookup"><span data-stu-id="bbc66-357">Set up and configure the Office 365 CDN by using PnP PowerShell</span></span>

<span data-ttu-id="bbc66-358">Procedurerna i det här avsnittet kräver att du använder PnP PowerShell för att ansluta till SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="bbc66-358">The procedures in this section require you to use PnP PowerShell to connect to SharePoint Online.</span></span> <span data-ttu-id="bbc66-359">Anvisningar finns i [komma igång med PnP PowerShell](https://github.com/SharePoint/PnP-PowerShell#getting-started).</span><span class="sxs-lookup"><span data-stu-id="bbc66-359">For instructions, see [Getting started with PnP PowerShell](https://github.com/SharePoint/PnP-PowerShell#getting-started).</span></span>

<span data-ttu-id="bbc66-360">Utför de här stegen för att konfigurera och konfigurera CDN för att hantera dina till gångar i SharePoint Online med hjälp av PnP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bbc66-360">Complete these steps to set up and configure the CDN to host your assets in SharePoint Online using PnP PowerShell.</span></span>

<details>
  <summary><span data-ttu-id="bbc66-361">Klicka för att Visa</span><span class="sxs-lookup"><span data-stu-id="bbc66-361">Click to expand</span></span></summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a><span data-ttu-id="bbc66-362">Aktivera din organisation för att använda Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="bbc66-362">Enable your organization to use the Office 365 CDN</span></span>

<span data-ttu-id="bbc66-363">Innan du ändrar status för klient organisationen måste du hämta den aktuella statusen för privat CDN-konfigurationen i Office 365-klient organisationen.</span><span class="sxs-lookup"><span data-stu-id="bbc66-363">Before you make changes to the tenant CDN settings, you should retrieve the current status of the private CDN configuration in your Office 365 tenant.</span></span> <span data-ttu-id="bbc66-364">Ansluta till klient organisationen med PnP PowerShell:</span><span class="sxs-lookup"><span data-stu-id="bbc66-364">Connect to your tenant using PnP PowerShell:</span></span>

``` powershell
Connect-PnPOnline -Url https://contoso-admin.sharepoint.com -UseWebLogin
```

<span data-ttu-id="bbc66-365">Använd cmdleten **Get-PnPTenantCdnEnabled** för att hämta status inställningar för CDN från klient organisationen:</span><span class="sxs-lookup"><span data-stu-id="bbc66-365">Now use the **Get-PnPTenantCdnEnabled** cmdlet to retrieve the CDN status settings from the tenant:</span></span>

``` powershell
Get-PnPTenantCdnEnabled -CdnType <Public | Private>
```

<span data-ttu-id="bbc66-366">Statusen för CDN för angiven CdnType kommer att matas ut till skärmen.</span><span class="sxs-lookup"><span data-stu-id="bbc66-366">The status of the CDN for the specified CdnType will output to the screen.</span></span>

<span data-ttu-id="bbc66-367">Använd cmdleten **set-PnPTenantCdnEnabled** för att göra det möjligt för organisationen att använda Office 365 CDN.</span><span class="sxs-lookup"><span data-stu-id="bbc66-367">Use the **Set-PnPTenantCdnEnabled** cmdlet to enable your organization to use the Office 365 CDN.</span></span> <span data-ttu-id="bbc66-368">Du kan göra det möjligt för organisationen att använda offentliga ursprung, privata ursprung eller båda samtidigt.</span><span class="sxs-lookup"><span data-stu-id="bbc66-368">You can enable your organization to use public origins, private origins, or both at at the same time.</span></span> <span data-ttu-id="bbc66-369">Du kan också konfigurera CDN för att hoppa över inställningen av standard ursprung när du aktiverar det.</span><span class="sxs-lookup"><span data-stu-id="bbc66-369">You can also configure the CDN to skip the setup of default origins when you enable it.</span></span> <span data-ttu-id="bbc66-370">Du kan alltid lägga till dessa ursprung senare enligt beskrivningen i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="bbc66-370">You can always add these origins later as described in this topic.</span></span>
  
<span data-ttu-id="bbc66-371">I PnP PowerShell:</span><span class="sxs-lookup"><span data-stu-id="bbc66-371">In PnP PowerShell:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

<span data-ttu-id="bbc66-372">Om du till exempel vill aktivera organisationen att använda både offentliga och privata ursprung skriver du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="bbc66-372">For example, to enable your organization to use both public and private origins, type the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true
```

<span data-ttu-id="bbc66-373">Om du vill göra det möjligt för organisationen att använda både offentliga och privata ursprung men hoppa till standard ursprungen skriver du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="bbc66-373">To enable your organization to use both public and private origins but skip setting up the default origins, type the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

<span data-ttu-id="bbc66-374">Se [standard ursprung för CDN](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) för information om ursprung som är etablerade som standard när du aktiverar Office 365 CDN och den potentiella effekten av att hoppa över inställningen av standard ursprung.</span><span class="sxs-lookup"><span data-stu-id="bbc66-374">See [Default CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) for information about the origins that are provisioned by default when you enable the Office 365 CDN, and the potential impact of skipping the setup of default origins.</span></span>

<span data-ttu-id="bbc66-375">Om du vill aktivera organisationen att använda offentliga ursprung skriver du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="bbc66-375">To enable your organization to use public origins, type the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $true
```

<span data-ttu-id="bbc66-376">Om du vill aktivera din organisation att använda privata ursprung skriver du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="bbc66-376">To enable your organization to use private origins, type the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $true
```

<span data-ttu-id="bbc66-377">Mer information om den här cmdleten finns i [set-PnPTenantCdnEnabled](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).</span><span class="sxs-lookup"><span data-stu-id="bbc66-377">For more information about this cmdlet, see [Set-PnPTenantCdnEnabled](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).</span></span>

<span data-ttu-id="bbc66-378"><a name="Office365CDNforPnPPoshFileType"> </a></span><span class="sxs-lookup"><span data-stu-id="bbc66-378"><a name="Office365CDNforPnPPoshFileType"> </a></span></span>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a><span data-ttu-id="bbc66-379">Ändra listan över filtyper som ska ingå i Office 365 CDN (valfritt)</span><span class="sxs-lookup"><span data-stu-id="bbc66-379">Change the list of file types to include in the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="bbc66-380">När du definierar filtyper med hjälp av cmdleten **set-PnPTenantCdnPolicy** skriver du över den för tillfället definierade listan.</span><span class="sxs-lookup"><span data-stu-id="bbc66-380">When you define file types by using the **Set-PnPTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="bbc66-381">Om du vill lägga till fler filtyper i listan kan du använda cmdleten först för att ta reda på vilka filtyper som redan är tillåtna och lägga till dem i listan tillsammans med nya filer.</span><span class="sxs-lookup"><span data-stu-id="bbc66-381">If you want to add additional file types to the list, use the cmdlet first to find out what file types are already allowed and include them in the list along with your new ones.</span></span>
  
<span data-ttu-id="bbc66-382">Använd cmdleten **set-PnPTenantCdnPolicy** för att definiera statiska filtyper som kan hanteras av offentliga och privata ursprung i CDN.</span><span class="sxs-lookup"><span data-stu-id="bbc66-382">Use the **Set-PnPTenantCdnPolicy** cmdlet to define static file types that can be hosted by public and private origins in the CDN.</span></span> <span data-ttu-id="bbc66-383">Som standard tillåts vanliga typer av till gångar, till exempel. CSS,. gif,. jpg och. js.</span><span class="sxs-lookup"><span data-stu-id="bbc66-383">By default, common asset types are allowed, for example .css, .gif, .jpg, and .js.</span></span>

<span data-ttu-id="bbc66-384">I PnP PowerShell:</span><span class="sxs-lookup"><span data-stu-id="bbc66-384">In PnP PowerShell:</span></span>

``` powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

<span data-ttu-id="bbc66-385">Om du till exempel vill aktivera CDN som Host. CSS-och. png-filer anger du kommandot:</span><span class="sxs-lookup"><span data-stu-id="bbc66-385">For example, to enable the CDN to host .css and .png files, you would enter the command:</span></span>

``` powershell
Set-PnPTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

<span data-ttu-id="bbc66-386">Använd cmdleten **Get-PnPTenantCdnPolicies** för att se vilka filtyper som för närvarande tillåts av CDN:</span><span class="sxs-lookup"><span data-stu-id="bbc66-386">To see what file types are currently allowed by the CDN, use the **Get-PnPTenantCdnPolicies** cmdlet:</span></span>

``` powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="bbc66-387">Mer information om dessa cmdletar finns i [set-PnPTenantCdnPolicy](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) and [Get-PnPTenantCdnPolicies](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).</span><span class="sxs-lookup"><span data-stu-id="bbc66-387">For more information about these cmdlets, see [Set-PnPTenantCdnPolicy](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) and [Get-PnPTenantCdnPolicies](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).</span></span>

<span data-ttu-id="bbc66-388"><a name="Office365CDNforPnPPoshSiteClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="bbc66-388"><a name="Office365CDNforPnPPoshSiteClassification"> </a></span></span>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a><span data-ttu-id="bbc66-389">Ändra listan över webbplats klassificeringar som du vill undanta från Office 365 CDN (valfritt)</span><span class="sxs-lookup"><span data-stu-id="bbc66-389">Change the list of site classifications you want to exclude from the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="bbc66-390">När du undantar webbplats klassificeringar med cmdleten **set-PnPTenantCdnPolicy** skriver du över den för tillfället definierade listan.</span><span class="sxs-lookup"><span data-stu-id="bbc66-390">When you exclude site classifications by using the **Set-PnPTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="bbc66-391">Om du vill undanta ytterligare webbplats klassificeringar kan du använda cmdleten först för att ta reda på vilka klassificeringar som redan är undantagna och sedan lägga till dem tillsammans med dina nya.</span><span class="sxs-lookup"><span data-stu-id="bbc66-391">If you want to exclude additional site classifications, use the cmdlet first to find out what classifications are already excluded and then add them along with your new ones.</span></span>

<span data-ttu-id="bbc66-392">Använd cmdleten **set-PnPTenantCdnPolicy** för att undanta webbplats klassificeringar som du inte vill göra tillgängliga via CDN.</span><span class="sxs-lookup"><span data-stu-id="bbc66-392">Use the **Set-PnPTenantCdnPolicy** cmdlet to exclude site classifications that you do not want to make available over the CDN.</span></span> <span data-ttu-id="bbc66-393">Som standard utesluts inga webbplats klassificeringar.</span><span class="sxs-lookup"><span data-stu-id="bbc66-393">By default, no site classifications are excluded.</span></span>

<span data-ttu-id="bbc66-394">I PnP PowerShell:</span><span class="sxs-lookup"><span data-stu-id="bbc66-394">In PnP PowerShell:</span></span>

``` powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications>"
```

<span data-ttu-id="bbc66-395">Om du vill se vilka webbplats klassificeringar som är begränsade använder du cmdleten **Get-PnPTenantCdnPolicies** :</span><span class="sxs-lookup"><span data-stu-id="bbc66-395">To see what site classifications are currently restricted, use the **Get-PnPTenantCdnPolicies** cmdlet:</span></span>

``` powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="bbc66-396">De egenskaper som kommer att returneras är _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ och _ExcludeIfNoScriptDisabled_.</span><span class="sxs-lookup"><span data-stu-id="bbc66-396">The properties that will be returned are _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ and _ExcludeIfNoScriptDisabled_.</span></span>

<span data-ttu-id="bbc66-397">Egenskapen _IncludeFileExtensions_ innehåller en lista över fil namns tillägg som kommer att betjänas från CDN.</span><span class="sxs-lookup"><span data-stu-id="bbc66-397">The _IncludeFileExtensions_ property contains the list of file extensions that will be served from the CDN.</span></span>

> [!NOTE]
> <span data-ttu-id="bbc66-398">Standard fil namns tilläggen skiljer sig mellan offentliga och privata.</span><span class="sxs-lookup"><span data-stu-id="bbc66-398">The default file extensions are different between public and private.</span></span>

<span data-ttu-id="bbc66-399">Egenskapen _ExcludeRestrictedSiteClassifications_ innehåller de webbplats klassificeringar som du vill undanta från CDN.</span><span class="sxs-lookup"><span data-stu-id="bbc66-399">The _ExcludeRestrictedSiteClassifications_ property contains the site classifications that you want to exclude from the CDN.</span></span> <span data-ttu-id="bbc66-400">Du kan till exempel utesluta webbplatser som marker ATS som **konfidentiella** så att innehållet från webbplatser med den klassificeringen inte kommer att betjänas från CDN.</span><span class="sxs-lookup"><span data-stu-id="bbc66-400">For example, you can exclude sites marked as **Confidential** so content from sites with that classification applied will not be served from the CDN.</span></span>

<span data-ttu-id="bbc66-401">Egenskapen _ExcludeIfNoScriptDisabled_ exkluderar innehåll från CDN baserat på Inställningar för _NoScript_ på webbplats nivå.</span><span class="sxs-lookup"><span data-stu-id="bbc66-401">The _ExcludeIfNoScriptDisabled_ property excludes content from the CDN based on the site-level _NoScript_ attribute settings.</span></span> <span data-ttu-id="bbc66-402">Som standard är attributet _NoScript_ **aktiverat** för _moderna_ webbplatser och är **inaktiverat** för _klassiska_ webbplatser.</span><span class="sxs-lookup"><span data-stu-id="bbc66-402">By default, the _NoScript_ attribute is set to **Enabled** for _Modern_ sites and **Disabled** for _Classic_ sites.</span></span> <span data-ttu-id="bbc66-403">Detta beror på klientens inställningar.</span><span class="sxs-lookup"><span data-stu-id="bbc66-403">This depends on your tenant settings.</span></span>

<span data-ttu-id="bbc66-404">Mer information om dessa cmdletar finns i [set-PnPTenantCdnPolicy](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) and [Get-PnPTenantCdnPolicies](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).</span><span class="sxs-lookup"><span data-stu-id="bbc66-404">For more information about these cmdlets, see [Set-PnPTenantCdnPolicy](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) and [Get-PnPTenantCdnPolicies](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).</span></span>

<span data-ttu-id="bbc66-405"><a name="Office365CDNforSPOOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="bbc66-405"><a name="Office365CDNforSPOOriginPnPPosh"> </a></span></span>
### <a name="add-an-origin-for-your-assets"></a><span data-ttu-id="bbc66-406">Lägga till ett ursprung för dina till gångar</span><span class="sxs-lookup"><span data-stu-id="bbc66-406">Add an origin for your assets</span></span>

<span data-ttu-id="bbc66-407">Använd cmdleten **Add-PnPTenantCdnOrigin** för att definiera ett ursprung.</span><span class="sxs-lookup"><span data-stu-id="bbc66-407">Use the **Add-PnPTenantCdnOrigin** cmdlet to define an origin.</span></span> <span data-ttu-id="bbc66-408">Du kan definiera flera ursprung.</span><span class="sxs-lookup"><span data-stu-id="bbc66-408">You can define multiple origins.</span></span> <span data-ttu-id="bbc66-409">Origo är en URL som pekar på ett SharePoint-bibliotek eller en mapp som innehåller de objekt som du vill ska hanteras av CDN.</span><span class="sxs-lookup"><span data-stu-id="bbc66-409">The origin is a URL that points to a SharePoint library or folder that contains the assets that you want to be hosted by the CDN.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="bbc66-410">Du bör aldrig placera resurser som innehåller användar information eller anses vara känsliga för organisationen i ett offentligt ursprung.</span><span class="sxs-lookup"><span data-stu-id="bbc66-410">You should never place resources that contain user information or are considered sensitive to your organization in a public origin.</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

<span data-ttu-id="bbc66-411">Värdet för _Path_ är den relativa sökvägen till det bibliotek eller den mapp som innehåller till gångarna.</span><span class="sxs-lookup"><span data-stu-id="bbc66-411">The value of _path_ is the relative path to the library or folder that contains the assets.</span></span> <span data-ttu-id="bbc66-412">Du kan använda jokertecken utöver relativa sökvägar.</span><span class="sxs-lookup"><span data-stu-id="bbc66-412">You can use wildcards in addition to relative paths.</span></span> <span data-ttu-id="bbc66-413">Ursprung stöd för jokertecken läggs till till URL-adressen.</span><span class="sxs-lookup"><span data-stu-id="bbc66-413">Origins support wildcards prepended to the URL.</span></span> <span data-ttu-id="bbc66-414">Det gör att du kan skapa ursprung som sträcker sig över flera webbplatser.</span><span class="sxs-lookup"><span data-stu-id="bbc66-414">This allows you to create origins that span multiple sites.</span></span> <span data-ttu-id="bbc66-415">Om du till exempel vill ta med alla till gångar i masterpages-mappen för alla webbplatser som ett offentligt ursprung i CDN skriver du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="bbc66-415">For example, to include all of the assets in the masterpages folder for all of your sites as a public origin within the CDN, type the following command:</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ <span data-ttu-id="bbc66-416">Jokertecknet \* **/** kan bara användas i början av sökvägen och matchar alla URL-segment under den angivna URL-adressen.</span><span class="sxs-lookup"><span data-stu-id="bbc66-416">The wildcard modifier \***/** can only be used at the beginning of the path, and will match all URL segments under the specified URL.</span></span>
+ <span data-ttu-id="bbc66-417">Sökvägen kan peka på ett dokument bibliotek, en mapp eller en webbplats.</span><span class="sxs-lookup"><span data-stu-id="bbc66-417">The path can point to a document library, folder or site.</span></span> <span data-ttu-id="bbc66-418">Till exempel matchar sökvägen _\*/site1_ alla dokument bibliotek under webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="bbc66-418">For example, the path _\*/site1_ will match all the document libraries under the site.</span></span>

<span data-ttu-id="bbc66-419">Du kan lägga till ett ursprung med en specifik relativ sökväg.</span><span class="sxs-lookup"><span data-stu-id="bbc66-419">You can add an origin with a specific relative path.</span></span> <span data-ttu-id="bbc66-420">Du kan inte lägga till ett ursprung med den fullständiga sökvägen.</span><span class="sxs-lookup"><span data-stu-id="bbc66-420">You cannot add an origin using the full path.</span></span>

<span data-ttu-id="bbc66-421">I det här exemplet läggs biblioteket webbplats till gångar till på en specifik webbplats:</span><span class="sxs-lookup"><span data-stu-id="bbc66-421">This example adds a private origin of the site assets library on a specific site:</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="bbc66-422">Det här exemplet lägger till ett privat ursprung i mappen _Mapp1_ i webbplats samlingens webbplats till gångar-bibliotek:</span><span class="sxs-lookup"><span data-stu-id="bbc66-422">This example adds a private origin of the _folder1_ folder in the site collection's site assets library:</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

<span data-ttu-id="bbc66-423">Om det finns ett blank steg i sökvägen kan du antingen omge vägen med citat tecken eller ersätta blank steget med URL-kodningen %20.</span><span class="sxs-lookup"><span data-stu-id="bbc66-423">If there is a space in the path, you can either surround the path in double quotes or replace the space with the URL encoding %20.</span></span> <span data-ttu-id="bbc66-424">Följande exempel lägger till ett privat ursprung för _mappen 1_ i webbplats samlingens webbplats till gångar-bibliotek:</span><span class="sxs-lookup"><span data-stu-id="bbc66-424">The following examples add a private origin of the _folder 1_ folder in the site collection's site assets library:</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

<span data-ttu-id="bbc66-425">Mer information om det här kommandot och dess syntax finns i [Add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span><span class="sxs-lookup"><span data-stu-id="bbc66-425">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

> [!NOTE]
> <span data-ttu-id="bbc66-426">I privata ursprung måste till gångar som delas från ett ursprung ha en huvud version publicerad innan de kan nås från CDN.</span><span class="sxs-lookup"><span data-stu-id="bbc66-426">In private origins, assets being shared from an origin must have a major version published before they can be accessed from the CDN.</span></span>
  
<span data-ttu-id="bbc66-427">När du har kört kommandot synkroniseras konfigurationen via data Center.</span><span class="sxs-lookup"><span data-stu-id="bbc66-427">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="bbc66-428">Det kan ta upp till 15 minuter.</span><span class="sxs-lookup"><span data-stu-id="bbc66-428">This can take up to 15 minutes.</span></span>

<span data-ttu-id="bbc66-429"><a name="ExamplePublicOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="bbc66-429"><a name="ExamplePublicOriginPnPPosh"> </a></span></span>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a><span data-ttu-id="bbc66-430">Exempel: Konfigurera ett offentligt ursprung för huvud sidorna och för format biblioteket för SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="bbc66-430">Example: Configure a public origin for your master pages and for your style library for SharePoint Online</span></span>

<span data-ttu-id="bbc66-431">Vanligt vis är dessa ursprung för dig som standard när du aktiverar Office 365 CDN.</span><span class="sxs-lookup"><span data-stu-id="bbc66-431">Normally, these origins are set up for you by default when you enable the Office 365 CDN.</span></span> <span data-ttu-id="bbc66-432">Om du vill aktivera dem manuellt följer du de här stegen.</span><span class="sxs-lookup"><span data-stu-id="bbc66-432">However, if you want to enable them manually, follow these steps.</span></span>
  
+ <span data-ttu-id="bbc66-433">Använd cmdleten **Add-PnPTenantCdnOrigin** för att definiera format biblioteket som ett offentligt ursprung.</span><span class="sxs-lookup"><span data-stu-id="bbc66-433">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the style library as a public origin.</span></span>

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ <span data-ttu-id="bbc66-434">Använd cmdleten **Add-PnPTenantCdnOrigin** för att definiera huvud sidorna som ett offentligt ursprung.</span><span class="sxs-lookup"><span data-stu-id="bbc66-434">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the master pages as a public origin.</span></span>

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

<span data-ttu-id="bbc66-435">Mer information om det här kommandot och dess syntax finns i [Add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span><span class="sxs-lookup"><span data-stu-id="bbc66-435">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

<span data-ttu-id="bbc66-436">När du har kört kommandot synkroniseras konfigurationen via data Center.</span><span class="sxs-lookup"><span data-stu-id="bbc66-436">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="bbc66-437">Det kan ta upp till 15 minuter.</span><span class="sxs-lookup"><span data-stu-id="bbc66-437">This can take up to 15 minutes.</span></span>

<span data-ttu-id="bbc66-438"><a name="ExamplePrivateOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="bbc66-438"><a name="ExamplePrivateOriginPnPPosh"> </a></span></span>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a><span data-ttu-id="bbc66-439">Exempel: Konfigurera ett privat ursprung för webbplats till gångar, webbplats sidor och publicerings bilder för SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="bbc66-439">Example: Configure a private origin for your site assets, site pages, and publishing images for SharePoint Online</span></span>

+ <span data-ttu-id="bbc66-440">Använd cmdleten **Add-PnPTenantCdnOrigin** för att definiera mappen för webbplats till gångar som ett privat ursprung.</span><span class="sxs-lookup"><span data-stu-id="bbc66-440">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the site assets folder as a private origin.</span></span>

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ <span data-ttu-id="bbc66-441">Använd cmdleten **Add-PnPTenantCdnOrigin** för att definiera mappen för webbplats sidor som ett privat ursprung.</span><span class="sxs-lookup"><span data-stu-id="bbc66-441">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the site pages folder as a private origin.</span></span>

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ <span data-ttu-id="bbc66-442">Använd cmdleten **Add-PnPTenantCdnOrigin** för att definiera mappen för publicerings bilder som ett privat ursprung.</span><span class="sxs-lookup"><span data-stu-id="bbc66-442">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the publishing images folder as a private origin.</span></span>

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

<span data-ttu-id="bbc66-443">Mer information om det här kommandot och dess syntax finns i [Add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span><span class="sxs-lookup"><span data-stu-id="bbc66-443">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

<span data-ttu-id="bbc66-444">När du har kört kommandot synkroniseras konfigurationen via data Center.</span><span class="sxs-lookup"><span data-stu-id="bbc66-444">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="bbc66-445">Det kan ta upp till 15 minuter.</span><span class="sxs-lookup"><span data-stu-id="bbc66-445">This can take up to 15 minutes.</span></span>

<span data-ttu-id="bbc66-446"><a name="ExamplePrivateOriginSiteCollectionPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="bbc66-446"><a name="ExamplePrivateOriginSiteCollectionPnPPosh"> </a></span></span>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a><span data-ttu-id="bbc66-447">Exempel: Konfigurera ett privat ursprung för en webbplats samling för SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="bbc66-447">Example: Configure a private origin for a site collection for SharePoint Online</span></span>

<span data-ttu-id="bbc66-448">Använd cmdleten **Add-PnPTenantCdnOrigin** för att definiera en webbplats samling som ett privat ursprung.</span><span class="sxs-lookup"><span data-stu-id="bbc66-448">Use the **Add-PnPTenantCdnOrigin** cmdlet to define a site collection as a private origin.</span></span> <span data-ttu-id="bbc66-449">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="bbc66-449">For example:</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="bbc66-450">Mer information om det här kommandot och dess syntax finns i [Add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span><span class="sxs-lookup"><span data-stu-id="bbc66-450">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>
  
<span data-ttu-id="bbc66-451">När du har kört kommandot synkroniseras konfigurationen via data Center.</span><span class="sxs-lookup"><span data-stu-id="bbc66-451">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="bbc66-452">Du kan se ett meddelande om _väntande konfiguration_ som förväntas som en SharePoint Online-klient ansluter till CDN-tjänsten.</span><span class="sxs-lookup"><span data-stu-id="bbc66-452">You may see a _Configuration pending_ message which is expected as the SharePoint Online tenant connects to the CDN service.</span></span> <span data-ttu-id="bbc66-453">Det kan ta upp till 15 minuter.</span><span class="sxs-lookup"><span data-stu-id="bbc66-453">This can take up to 15 minutes.</span></span>

<span data-ttu-id="bbc66-454"><a name="CDNManagePnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="bbc66-454"><a name="CDNManagePnPPosh"> </a></span></span>
### <a name="manage-the-office-365-cdn"></a><span data-ttu-id="bbc66-455">Hantera Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="bbc66-455">Manage the Office 365 CDN</span></span>

<span data-ttu-id="bbc66-456">När du har konfigurerat CDN kan du göra ändringar i konfigurationen när du uppdaterar innehåll eller när dina behov ändras, enligt beskrivningen i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="bbc66-456">Once you've set up the CDN, you can make changes to your configuration as you update content or as your needs change, as described in this section.</span></span>
  
<span data-ttu-id="bbc66-457"><a name="Office365CDNforSPOaddremoveassetPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="bbc66-457"><a name="Office365CDNforSPOaddremoveassetPnPPosh"> </a></span></span>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a><span data-ttu-id="bbc66-458">Lägga till, uppdatera eller ta bort till gångar från Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="bbc66-458">Add, update, or remove assets from the Office 365 CDN</span></span>

<span data-ttu-id="bbc66-459">När du har slutfört konfigurations stegen kan du lägga till nya till gångar och uppdatera eller ta bort befintliga till gångar när du vill.</span><span class="sxs-lookup"><span data-stu-id="bbc66-459">Once you've completed the setup steps, you can add new assets, and update or remove existing assets whenever you want.</span></span> <span data-ttu-id="bbc66-460">Gör dina ändringar i till gångarna i den mapp eller det SharePoint-bibliotek som du angav som ursprung.</span><span class="sxs-lookup"><span data-stu-id="bbc66-460">Just make your changes to the assets in the folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="bbc66-461">Om du lägger till en ny till gång är den tillgänglig via CDN omedelbart.</span><span class="sxs-lookup"><span data-stu-id="bbc66-461">If you add a new asset, it is available through the CDN immediately.</span></span> <span data-ttu-id="bbc66-462">Men om du uppdaterar till gången tar det upp till 15 minuter innan den nya kopian sprids och blir tillgänglig i CDN.</span><span class="sxs-lookup"><span data-stu-id="bbc66-462">However, if you update the asset, it will take up to 15 minutes for the new copy to propagate and become available in the CDN.</span></span>
  
<span data-ttu-id="bbc66-463">Om du behöver hämta plats för ursprunget kan du använda cmdleten **Get-PnPTenantCdnOrigin** .</span><span class="sxs-lookup"><span data-stu-id="bbc66-463">If you need to retrieve the location of the origin, you can use the **Get-PnPTenantCdnOrigin** cmdlet.</span></span> <span data-ttu-id="bbc66-464">Information om hur du använder denna cmdlet finns i [Get-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnorigin).</span><span class="sxs-lookup"><span data-stu-id="bbc66-464">For information on how to use this cmdlet, see [Get-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnorigin).</span></span>

<span data-ttu-id="bbc66-465"><a name="Office365CDNforSPORemoveOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="bbc66-465"><a name="Office365CDNforSPORemoveOriginPnPPosh"> </a></span></span>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a><span data-ttu-id="bbc66-466">Ta bort ett ursprung från Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="bbc66-466">Remove an origin from the Office 365 CDN</span></span>

<span data-ttu-id="bbc66-467">Du kan ta bort åtkomst till en mapp eller ett SharePoint-bibliotek som du har identifierat som ett ursprung.</span><span class="sxs-lookup"><span data-stu-id="bbc66-467">You can remove access to a folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="bbc66-468">För att göra det, Använd cmdleten **Remove-PnPTenantCdnOrigin** .</span><span class="sxs-lookup"><span data-stu-id="bbc66-468">To do this, use the **Remove-PnPTenantCdnOrigin** cmdlet.</span></span>

``` powershell
Remove-PnPTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

<span data-ttu-id="bbc66-469">Information om hur du använder den här cmdleten finns i [Remove-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/remove-pnptenantcdnorigin).</span><span class="sxs-lookup"><span data-stu-id="bbc66-469">For information on how to use this cmdlet, see [Remove-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/remove-pnptenantcdnorigin).</span></span>

<span data-ttu-id="bbc66-470"><a name="Office365CDNforSPOModifyOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="bbc66-470"><a name="Office365CDNforSPOModifyOriginPnPPosh"> </a></span></span>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a><span data-ttu-id="bbc66-471">Ändra ett ursprung i Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="bbc66-471">Modify an origin in the Office 365 CDN</span></span>

<span data-ttu-id="bbc66-472">Du kan inte ändra ett ursprung som du har skapat.</span><span class="sxs-lookup"><span data-stu-id="bbc66-472">You cannot modify an origin you've created.</span></span> <span data-ttu-id="bbc66-473">I stället kan du ta bort Origo och sedan lägga till ett nytt.</span><span class="sxs-lookup"><span data-stu-id="bbc66-473">Instead, remove the origin and then add a new one.</span></span> <span data-ttu-id="bbc66-474">Mer information finns i [så här tar du bort ett ursprung från Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPnPPosh) och hur [du lägger till till gångar](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPnPPosh).</span><span class="sxs-lookup"><span data-stu-id="bbc66-474">For more information, see [To remove an origin from the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPnPPosh) and [To add an origin for your assets](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPnPPosh).</span></span>

<span data-ttu-id="bbc66-475"><a name="Office365CDNforSPODisable"> </a></span><span class="sxs-lookup"><span data-stu-id="bbc66-475"><a name="Office365CDNforSPODisable"> </a></span></span>
#### <a name="disable-the-office-365-cdn"></a><span data-ttu-id="bbc66-476">Inaktivera Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="bbc66-476">Disable the Office 365 CDN</span></span>

<span data-ttu-id="bbc66-477">Använd cmdleten **set-PnPTenantCdnEnabled** för att inaktivera CDN för organisationen.</span><span class="sxs-lookup"><span data-stu-id="bbc66-477">Use the **Set-PnPTenantCdnEnabled** cmdlet to disable the CDN for your organization.</span></span> <span data-ttu-id="bbc66-478">Om både offentliga och privata ursprung är aktiverade för CDN måste du köra cmdleten två gånger enligt följande exempel.</span><span class="sxs-lookup"><span data-stu-id="bbc66-478">If you have both the public and private origins enabled for the CDN, you need to run the cmdlet twice as shown in the following examples.</span></span>
  
<span data-ttu-id="bbc66-479">Om du vill inaktivera användning av offentliga ursprung i CDN skriver du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="bbc66-479">To disable use of public origins in the CDN, enter the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $false
```

<span data-ttu-id="bbc66-480">Om du vill inaktivera användningen av de privata ursprungen i CDN skriver du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="bbc66-480">To disable use of the private origins in the CDN, enter the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $false
```

<span data-ttu-id="bbc66-481">Mer information om den här cmdleten finns i [set-PnPTenantCdnEnabled](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).</span><span class="sxs-lookup"><span data-stu-id="bbc66-481">For more information about this cmdlet, see [Set-PnPTenantCdnEnabled](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).</span></span>

</details>

<span data-ttu-id="bbc66-482"><a name="CDNSetupinCLI"> </a></span><span class="sxs-lookup"><span data-stu-id="bbc66-482"><a name="CDNSetupinCLI"> </a></span></span>
## <a name="set-up-and-configure-the-office-365-cdn-using-the-office-365-cli"></a><span data-ttu-id="bbc66-483">Konfigurera och konfigurera Office 365 CDN med Office 365-CLI</span><span class="sxs-lookup"><span data-stu-id="bbc66-483">Set up and configure the Office 365 CDN using the Office 365 CLI</span></span>

<span data-ttu-id="bbc66-484">Procedurerna i det här avsnittet kräver att du har installerat [Office 365-CLI](https://aka.ms/o365cli).</span><span class="sxs-lookup"><span data-stu-id="bbc66-484">The procedures in this section require that you have installed the [Office 365 CLI](https://aka.ms/o365cli).</span></span> <span data-ttu-id="bbc66-485">Anslut sedan till Office 365-klient organisationen med kommandot [Logga in](https://pnp.github.io/office365-cli/cmd/login/) .</span><span class="sxs-lookup"><span data-stu-id="bbc66-485">Next, connect to your Office 365 tenant using the [login](https://pnp.github.io/office365-cli/cmd/login/) command.</span></span>

<span data-ttu-id="bbc66-486">Utför de här stegen för att konfigurera och konfigurera CDN så att du kan vara värd för dina till gångar i SharePoint Online med hjälp av Office 365-CLI.</span><span class="sxs-lookup"><span data-stu-id="bbc66-486">Complete these steps to set up and configure the CDN to host your assets in SharePoint Online using the Office 365 CLI.</span></span>

<details>
  <summary><span data-ttu-id="bbc66-487">Klicka för att Visa</span><span class="sxs-lookup"><span data-stu-id="bbc66-487">Click to expand</span></span></summary>

### <a name="enable-the-office-365-cdn"></a><span data-ttu-id="bbc66-488">Aktivera Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="bbc66-488">Enable the Office 365 CDN</span></span>

<span data-ttu-id="bbc66-489">Du kan hantera statusen för Office 365 CDN i klient organisationen med kommandot [SPO CDN set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-set/) .</span><span class="sxs-lookup"><span data-stu-id="bbc66-489">You can manage the state of the Office 365 CDN in your tenant using the [spo cdn set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-set/) command.</span></span>

<span data-ttu-id="bbc66-490">Så här aktiverar du Office 365 Public CDN i klient organisationen:</span><span class="sxs-lookup"><span data-stu-id="bbc66-490">To enable the Office 365 Public CDN in your tenant execute:</span></span>

```sh
spo cdn set --type Public --enabled true
```

<span data-ttu-id="bbc66-491">Aktivera Office 365 SharePoint CDN genom att köra:</span><span class="sxs-lookup"><span data-stu-id="bbc66-491">To enable the Office 365 SharePoint CDN, execute:</span></span>

```sh
spo cdn set --type Private --enabled true
```

#### <a name="view-the-current-status-of-the-office-365-cdn"></a><span data-ttu-id="bbc66-492">Visa aktuell status för Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="bbc66-492">View the current status of the Office 365 CDN</span></span>

<span data-ttu-id="bbc66-493">Om du vill kontrol lera om den särskilda typen av Office 365 CDN är aktiverat eller inaktive rad använder du kommandot [SPO CDN get](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-get/) .</span><span class="sxs-lookup"><span data-stu-id="bbc66-493">To check if the particular type of Office 365 CDN is enabled or disabled, use the [spo cdn get](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-get/) command.</span></span>

<span data-ttu-id="bbc66-494">Så här kontrollerar du om Office 365 Public CDN är aktiverat:</span><span class="sxs-lookup"><span data-stu-id="bbc66-494">To check if the Office 365 Public CDN is enabled, execute:</span></span>

```sh
spo cdn get --type Public
```

### <a name="view-the-office-365-cdn-origins"></a><span data-ttu-id="bbc66-495">Visa Office 365 CDN-ursprung</span><span class="sxs-lookup"><span data-stu-id="bbc66-495">View the Office 365 CDN origins</span></span>

<span data-ttu-id="bbc66-496">Så här visar du de aktuella konfigurerade Office 365 Public CDN-ursprungen kör:</span><span class="sxs-lookup"><span data-stu-id="bbc66-496">To view the currently configured Office 365 Public CDN origins execute:</span></span>

```sh
spo cdn origin list --type Public
```

<span data-ttu-id="bbc66-497">Se [standard ursprung för CDN](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) för information om ursprung som är etablerade som standard när du aktiverar Office 365 CDN.</span><span class="sxs-lookup"><span data-stu-id="bbc66-497">See [Default CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) for information about the origins that are provisioned by default when you enable the Office 365 CDN.</span></span>

### <a name="add-an-office-365-cdn-origin"></a><span data-ttu-id="bbc66-498">Lägga till ett Office 365 CDN-ursprung</span><span class="sxs-lookup"><span data-stu-id="bbc66-498">Add an Office 365 CDN origin</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bbc66-499">Du bör aldrig placera resurser som anses vara känsliga för organisationen i ett SharePoint-dokumentbibliotek som är konfigurerat som ett offentligt ursprung.</span><span class="sxs-lookup"><span data-stu-id="bbc66-499">You should never place resources that are considered sensitive to your organization in a SharePoint document library configured as a public origin.</span></span>

<span data-ttu-id="bbc66-500">Använd kommandot [SPO CDN Origin Add](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-add/) för att definiera ett CDN-ursprung.</span><span class="sxs-lookup"><span data-stu-id="bbc66-500">Use the [spo cdn origin add](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-add/) command to define a CDN origin.</span></span> <span data-ttu-id="bbc66-501">Du kan definiera flera ursprung.</span><span class="sxs-lookup"><span data-stu-id="bbc66-501">You can define multiple origins.</span></span> <span data-ttu-id="bbc66-502">Origo är en URL som pekar på ett SharePoint-bibliotek eller en mapp som innehåller de objekt som du vill ska hanteras av CDN.</span><span class="sxs-lookup"><span data-stu-id="bbc66-502">The origin is a URL that points to a SharePoint library or folder that contains the assets that you want to be hosted by the CDN.</span></span>

```sh
spo cdn origin add --type [Public | Private] --origin <path>
```

<span data-ttu-id="bbc66-503">Var `path` finns den relativa sökvägen till mappen som innehåller till gångarna.</span><span class="sxs-lookup"><span data-stu-id="bbc66-503">Where `path` is the relative path to the folder that contains the assets.</span></span> <span data-ttu-id="bbc66-504">Du kan använda jokertecken utöver relativa sökvägar.</span><span class="sxs-lookup"><span data-stu-id="bbc66-504">You can use wildcards in addition to relative paths.</span></span>

<span data-ttu-id="bbc66-505">Om du vill inkludera alla till gångar i **huvud sid galleriet** på alla webbplatser som ett offentligt ursprung kör du:</span><span class="sxs-lookup"><span data-stu-id="bbc66-505">To include all assets in the **Master Page Gallery** of all sites as a public origin, execute:</span></span>

```sh
spo cdn origin add --type Public --origin */masterpage
```

<span data-ttu-id="bbc66-506">Om du vill konfigurera ett privat ursprung för en viss webbplats samling kör du:</span><span class="sxs-lookup"><span data-stu-id="bbc66-506">To configure a private origin for a specific site collection, execute:</span></span>

```sh
spo cdn origin add --type Private --origin sites/site1/siteassets
```

> [!NOTE]
> <span data-ttu-id="bbc66-507">När du har lagt till ett CDN-ursprung kan det ta upp till 15 minuter innan du kan hämta filer via CDN-tjänsten.</span><span class="sxs-lookup"><span data-stu-id="bbc66-507">After adding a CDN origin, it might take up to 15 minutes for you to be able to retrieve files via the CDN service.</span></span> <span data-ttu-id="bbc66-508">Du kan kontrol lera om det specifika ursprungs ursprunget redan har Aktiver ATS med kommandot [SPO CDN Origin](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) .</span><span class="sxs-lookup"><span data-stu-id="bbc66-508">You can verify if the particular origin has already been enabled using the [spo cdn origin list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) command.</span></span>

### <a name="remove-an-office-365-cdn-origin"></a><span data-ttu-id="bbc66-509">Ta bort ett Office 365 CDN-ursprung</span><span class="sxs-lookup"><span data-stu-id="bbc66-509">Remove an Office 365 CDN origin</span></span>

<span data-ttu-id="bbc66-510">Använd kommandot [SPO CDN Origin ta bort](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-remove/) om du vill ta bort ett CDN-ursprung för den angivna CDN-typen.</span><span class="sxs-lookup"><span data-stu-id="bbc66-510">Use the [spo cdn origin remove](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-remove/) command to remove a CDN origin for the specified CDN type.</span></span>

<span data-ttu-id="bbc66-511">Om du vill ta bort ett offentligt ursprung från CDN-konfigurationen kör du:</span><span class="sxs-lookup"><span data-stu-id="bbc66-511">To remove a public origin from the CDN configuration, execute:</span></span>

```sh
spo cdn origin remove --type Public --origin */masterpage
```

> [!NOTE]
> <span data-ttu-id="bbc66-512">Om du tar bort ett CDN-ursprung påverkas inte filerna som lagras i ett dokument bibliotek som matchar ursprunget.</span><span class="sxs-lookup"><span data-stu-id="bbc66-512">Removing a CDN origin doesn't affect the files stored in any document library matching that origin.</span></span> <span data-ttu-id="bbc66-513">Om de här till gångarna har refererats till med deras SharePoint-URL växlar SharePoint automatiskt tillbaka till den ursprungliga URL-adressen som pekar på dokument biblioteket.</span><span class="sxs-lookup"><span data-stu-id="bbc66-513">If these assets have been referenced using their SharePoint URL, SharePoint will automatically switch back to the original URL pointing to the document library.</span></span> <span data-ttu-id="bbc66-514">Om till gångar har refererats till med en offentlig CDN-URL kommer länken att brytas och du måste ändra dem manuellt.</span><span class="sxs-lookup"><span data-stu-id="bbc66-514">If, however, assets have been referenced using a public CDN URL, then removing the origin will break the link and you will need to manually change them.</span></span>

### <a name="modify-an-office-365-cdn-origin"></a><span data-ttu-id="bbc66-515">Ändra ett Office 365 CDN-ursprung</span><span class="sxs-lookup"><span data-stu-id="bbc66-515">Modify an Office 365 CDN origin</span></span>

<span data-ttu-id="bbc66-516">Det går inte att ändra ett befintligt CDN-ursprung.</span><span class="sxs-lookup"><span data-stu-id="bbc66-516">It's not possible to modify an existing CDN origin.</span></span> <span data-ttu-id="bbc66-517">I stället bör du ta bort det tidigare definierade CDN-ursprunget med `spo cdn origin remove` kommandot och lägga till ett nytt med `spo cdn origin add` kommandot.</span><span class="sxs-lookup"><span data-stu-id="bbc66-517">Instead, you should remove the previously defined CDN origin using the `spo cdn origin remove` command and add a new one using the `spo cdn origin add` command.</span></span>

### <a name="change-the-types-of-files-to-include-in-the-office-365-cdn"></a><span data-ttu-id="bbc66-518">Ändra vilka typer av filer som ska ingå i Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="bbc66-518">Change the types of files to include in the Office 365 CDN</span></span>

<span data-ttu-id="bbc66-519">Följande filtyper ingår som standard i CDN: _. CSS,. EOT,. gif,. ico,. jpeg,. jpg,. js,. map,. png,. SVG,. ttf,. WOFF och. woff2_.</span><span class="sxs-lookup"><span data-stu-id="bbc66-519">By default, the following file types are included in the CDN: _.css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff and .woff2_.</span></span> <span data-ttu-id="bbc66-520">Om du behöver ta med fler filtyper i CDN kan du ändra CDN-konfigurationen med hjälp av [SPO CDN-princip uppsättning](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) .</span><span class="sxs-lookup"><span data-stu-id="bbc66-520">If you need to include additional file types in the CDN, you can change the CDN configuration using the [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) command.</span></span>

> [!NOTE]
> <span data-ttu-id="bbc66-521">När du ändrar listan med filtyper skriver du över den för tillfället definierade listan.</span><span class="sxs-lookup"><span data-stu-id="bbc66-521">When changing the list of file types, you overwrite the currently defined list.</span></span> <span data-ttu-id="bbc66-522">Om du vill inkludera fler filtyper måste du först använda kommandot [SPO CDN policy List](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) för att ta reda på vilka filtyper som är konfigurerade för tillfället.</span><span class="sxs-lookup"><span data-stu-id="bbc66-522">If you want to include additional file types, first use the [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) command to find out which file types are currently configured.</span></span>

<span data-ttu-id="bbc66-523">Om du vill lägga till _JSON_ -filtypen i standard listan med filtyper som ingår i Public CDN kör du:</span><span class="sxs-lookup"><span data-stu-id="bbc66-523">To add the _JSON_ file type to the default list of file types included in the public CDN, execute:</span></span>

```sh
spo cdn policy set --type Public --policy IncludeFileExtensions --value "CSS,EOT,GIF,ICO,JPEG,JPG,JS,MAP,PNG,SVG,TTF,WOFF,JSON"
```

### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn"></a><span data-ttu-id="bbc66-524">Ändra listan över webbplats klassificeringar som du vill undanta från Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="bbc66-524">Change the list of site classifications you want to exclude from the Office 365 CDN</span></span>

<span data-ttu-id="bbc66-525">Använd kommandot [SPO CDN-princip uppsättning](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) för att undanta webbplats klassificeringar som du inte vill göra tillgängliga via CDN.</span><span class="sxs-lookup"><span data-stu-id="bbc66-525">Use the [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) command to exclude site classifications that you do not want to make available over the CDN.</span></span> <span data-ttu-id="bbc66-526">Som standard utesluts inga webbplats klassificeringar.</span><span class="sxs-lookup"><span data-stu-id="bbc66-526">By default, no site classifications are excluded.</span></span>

> [!NOTE]
> <span data-ttu-id="bbc66-527">När du ändrar listan med undantagna webbplats klassificeringar skriver du över den för tillfället definierade listan.</span><span class="sxs-lookup"><span data-stu-id="bbc66-527">When changing the list of excluded site classifications, you overwrite the currently defined list.</span></span> <span data-ttu-id="bbc66-528">Om du vill undanta ytterligare klassificeringar bör du först använda kommandot [SPO CDN policy List](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-list/) för att ta reda på vilka klassificeringar som för tillfället är konfigurerade.</span><span class="sxs-lookup"><span data-stu-id="bbc66-528">If you want to exclude additional classifications, first use the [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-list/) command to find out which classifications are currently configured.</span></span>

<span data-ttu-id="bbc66-529">Om du vill undanta webbplatser som klassificerats som _HBI_ från Public CDN kör du</span><span class="sxs-lookup"><span data-stu-id="bbc66-529">To exclude sites classified as _HBI_ from the public CDN, execute</span></span>

```sh
spo cdn policy set --type Public --policy ExcludeRestrictedSiteClassifications --value "HBI"
```

### <a name="disable-the-office-365-cdn"></a><span data-ttu-id="bbc66-530">Inaktivera Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="bbc66-530">Disable the Office 365 CDN</span></span>

<span data-ttu-id="bbc66-531">Så här inaktiverar du Office 365 CDN Använd `spo cdn set` kommandot, till exempel:</span><span class="sxs-lookup"><span data-stu-id="bbc66-531">To disable the Office 365 CDN use the `spo cdn set` command, for example:</span></span>

```sh
spo cdn set --type Public --enabled false
```

</details>

## <a name="using-your-cdn-assets"></a><span data-ttu-id="bbc66-532">Använda dina CDN-till gångar</span><span class="sxs-lookup"><span data-stu-id="bbc66-532">Using your CDN assets</span></span>

<span data-ttu-id="bbc66-533">Nu när du har aktiverat CDN och konfigurerat ursprung och policy kan du börja använda dina CDN-till gångar.</span><span class="sxs-lookup"><span data-stu-id="bbc66-533">Now that you have enabled the CDN and configured origins and policies, you can begin using your CDN assets.</span></span>

<span data-ttu-id="bbc66-534">I det här avsnittet får du lära dig hur du använder CDN-URL: er på dina SharePoint-sidor och-innehåll så att SharePoint dirigerar om förfrågningar till till gångar i både offentliga och privata ursprung till CDN.</span><span class="sxs-lookup"><span data-stu-id="bbc66-534">This section will help you understand how to use CDN URLs in your SharePoint pages and content so that SharePoint redirects requests for assets in both public and private origins to the CDN.</span></span>

+ [<span data-ttu-id="bbc66-535">Uppdatera länkar till CDN-till gångar</span><span class="sxs-lookup"><span data-stu-id="bbc66-535">Updating links to CDN assets</span></span>](use-microsoft-365-cdn-with-spo.md#updating-links-to-cdn-assets)
+ [<span data-ttu-id="bbc66-536">Använda till gångar i offentliga ursprung</span><span class="sxs-lookup"><span data-stu-id="bbc66-536">Using assets in public origins</span></span>](use-microsoft-365-cdn-with-spo.md#using-assets-in-public-origins)
+ [<span data-ttu-id="bbc66-537">Använda till gångar i privata ursprung</span><span class="sxs-lookup"><span data-stu-id="bbc66-537">Using assets in private origins</span></span>](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)

<span data-ttu-id="bbc66-538">Information om hur du använder CDN för att vara värd för klient webb delar finns i artikeln värd för [klient sidan från Office 365 CDN (Hej världen 4)](https://docs.microsoft.com/sharepoint/dev/spfx/web-parts/get-started/hosting-webpart-from-office-365-cdn).</span><span class="sxs-lookup"><span data-stu-id="bbc66-538">For information on how to use the CDN for hosting client-side web parts, see the topic [Host your client-side web part from Office 365 CDN (Hello World part 4)](https://docs.microsoft.com/sharepoint/dev/spfx/web-parts/get-started/hosting-webpart-from-office-365-cdn).</span></span>

> [!NOTE]
> <span data-ttu-id="bbc66-539">Om du lägger till mappen _ClientSideAssets_ i listan **privata** CDN-ursprung går det inte att rendera CDN-anpassade webb delar.</span><span class="sxs-lookup"><span data-stu-id="bbc66-539">If you add the _ClientSideAssets_ folder to the **private** CDN origins list, CDN-hosted custom web parts will fail to render.</span></span> <span data-ttu-id="bbc66-540">Filer som används av SPFX webb delar kan bara använda det offentliga CDN och ClientSideAssets-mappen är ett standard ursprung för offentlig CDN.</span><span class="sxs-lookup"><span data-stu-id="bbc66-540">Files used by SPFX web parts can only utilize the public CDN and the ClientSideAssets folder is a default origin for public CDN.</span></span> 

### <a name="updating-links-to-cdn-assets"></a><span data-ttu-id="bbc66-541">Uppdatera länkar till CDN-till gångar</span><span class="sxs-lookup"><span data-stu-id="bbc66-541">Updating links to CDN assets</span></span>

<span data-ttu-id="bbc66-542">Om du vill använda till gångar som du har lagt till i ett ursprung uppdaterar du bara länkar till den ursprungliga filen med sökvägen till filen i origo.</span><span class="sxs-lookup"><span data-stu-id="bbc66-542">To use assets that you have added to an origin, you simply update links to the original file with the path to the file in the origin.</span></span>

+ <span data-ttu-id="bbc66-543">Redigera sidan eller innehållet som innehåller länkar till till gångar som du har lagt till i ett ursprung.</span><span class="sxs-lookup"><span data-stu-id="bbc66-543">Edit the page or content that contains links to assets you have added to an origin.</span></span> <span data-ttu-id="bbc66-544">Du kan också använda en av flera metoder för att globalt söka och ersätta länkar på en webbplats eller webbplats samling om du vill uppdatera länken till en viss till gång överallt där den visas.</span><span class="sxs-lookup"><span data-stu-id="bbc66-544">You can also use one of several methods to globally search and replace links across an enter site or site collection if you want to update the link to a given asset everywhere it appears.</span></span>
+ <span data-ttu-id="bbc66-545">För varje länk till en till gång i ett ursprung ersätter du sökvägen med sökvägen till filen i CDNs ursprung.</span><span class="sxs-lookup"><span data-stu-id="bbc66-545">For each link to an asset in an origin, replace the path with the path to the file in the CDN origin.</span></span> <span data-ttu-id="bbc66-546">Du kan använda relativa sökvägar.</span><span class="sxs-lookup"><span data-stu-id="bbc66-546">You can use relative paths.</span></span>
+ <span data-ttu-id="bbc66-547">Spara sidan eller innehållet.</span><span class="sxs-lookup"><span data-stu-id="bbc66-547">Save the page or content.</span></span>

<span data-ttu-id="bbc66-548">Titta exempelvis på bild _/site/SiteAssets/images/image.png_som du har kopierat till mappen dokument bibliotek _/Site/CDN_origins/Public/_.</span><span class="sxs-lookup"><span data-stu-id="bbc66-548">For example, consider the image _/site/SiteAssets/images/image.png_, which you have copied to the document library folder _/site/CDN_origins/public/_.</span></span> <span data-ttu-id="bbc66-549">Om du vill använda CDN-resursen ersätter du den ursprungliga sökvägen till bild filens plats med sökvägen till origo för att skapa den nya URL-adressen _/site/CDN_origins/public/image.png_.</span><span class="sxs-lookup"><span data-stu-id="bbc66-549">To use the CDN asset, replace the original path to the image file location with the path to the origin to make the new URL _/site/CDN_origins/public/image.png_.</span></span>

<span data-ttu-id="bbc66-550">Om du vill använda den fullständiga URL-adressen till resursen i stället för en relativ sökväg skapar du länken så här:</span><span class="sxs-lookup"><span data-stu-id="bbc66-550">If you want to use the full URL to the asset instead of a relative path, construct the link like so:</span></span>

`https://<TenantHostName>.sharepoint.com/sites/site/CDN_origins/public/image.png`

> [!NOTE]
> <span data-ttu-id="bbc66-551">I allmänhet ska du inte hardcode URL-adresser direkt till till gångar i CDN.</span><span class="sxs-lookup"><span data-stu-id="bbc66-551">In general, you should not hardcode URLs directly to assets in the CDN.</span></span> <span data-ttu-id="bbc66-552">Du kan dock manuellt skapa URL-adresser till till gångar i offentliga ursprung om det behövs.</span><span class="sxs-lookup"><span data-stu-id="bbc66-552">However, you can manually construct URLs for assets in public origins if needed.</span></span> <span data-ttu-id="bbc66-553">Mer information finns i [HARDCODING CDN URL: er för offentliga till gångar](use-microsoft-365-cdn-with-spo.md#hardcoding-cdn-urls-for-public-assets).</span><span class="sxs-lookup"><span data-stu-id="bbc66-553">For more information, see [Hardcoding CDN URLs for public assets](use-microsoft-365-cdn-with-spo.md#hardcoding-cdn-urls-for-public-assets).</span></span>

<span data-ttu-id="bbc66-554">Om du vill veta mer om hur du kontrollerar att till gångar bearbetas från CDN kan [du läsa Hur kontrollerar jag att till gångar betjänas av CDN?](use-microsoft-365-cdn-with-spo.md#CDNConfirm) i [fel sökning i avsnittet Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) .</span><span class="sxs-lookup"><span data-stu-id="bbc66-554">To learn about how to verify that assets are being served from the CDN, see [How do I confirm that assets are being served by the CDN?](use-microsoft-365-cdn-with-spo.md#CDNConfirm) in the [Troubleshooting the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) section.</span></span>

### <a name="using-assets-in-public-origins"></a><span data-ttu-id="bbc66-555">Använda till gångar i offentliga ursprung</span><span class="sxs-lookup"><span data-stu-id="bbc66-555">Using assets in public origins</span></span>

<span data-ttu-id="bbc66-556">Med **publicerings funktionen** i SharePoint Online skrivs automatiskt om URL-adresser till till gångar som lagras i offentliga ursprung till deras CDN-motsvarigheter, så att till gångar behandlas från CDN-tjänsten i stället för SharePoint.</span><span class="sxs-lookup"><span data-stu-id="bbc66-556">The **Publishing feature** in SharePoint Online automatically rewrites URLs of assets stored in public origins to their CDN equivalents so that assets are served from the CDN service instead of SharePoint.</span></span>

<span data-ttu-id="bbc66-557">Om ditt ursprung finns på en webbplats där publicerings funktionen är aktive rad och de till gångar som du vill ladda in till CDN finns i någon av följande kategorier, skrivs URL-adresser automatiskt om till till gångar i ursprungslandet, förutsatt att till gången inte har uteslutits av en CDN policy.</span><span class="sxs-lookup"><span data-stu-id="bbc66-557">If your origin is in a site with the Publishing feature enabled, and the assets you want to offload to the CDN are in one of the following categories, SharePoint will automatically rewrite URLs for assets in the origin, provided that the asset has not been excluded by a CDN policy.</span></span>

<span data-ttu-id="bbc66-558">Här följer en översikt över vilka länkar som automatiskt skrivs om av publicerings funktionen för SharePoint:</span><span class="sxs-lookup"><span data-stu-id="bbc66-558">The following is an overview of which links are automatically rewritten by the SharePoint Publishing feature:</span></span>

+ <span data-ttu-id="bbc66-559">IMG/LINK/CSS URL-adresser i klassisk publicerings sida HTML-svar</span><span class="sxs-lookup"><span data-stu-id="bbc66-559">IMG/LINK/CSS URLs in classic publishing page HTML responses</span></span>
  + <span data-ttu-id="bbc66-560">Här ingår bilder som lagts till av författare i HTML-innehåll på en sida</span><span class="sxs-lookup"><span data-stu-id="bbc66-560">This includes images added by authors within the HTML content of a page</span></span>
+ <span data-ttu-id="bbc66-561">Bild-URL: er för bild bibliotek</span><span class="sxs-lookup"><span data-stu-id="bbc66-561">Picture Library SlideShow webpart image URLs</span></span>
+ <span data-ttu-id="bbc66-562">Bildfält i RenderListDataAsStream-resultat (SPList REST API)</span><span class="sxs-lookup"><span data-stu-id="bbc66-562">Image fields in SPList REST API (RenderListDataAsStream) results</span></span>
  + <span data-ttu-id="bbc66-563">Använd den nya egenskapen _ImageFieldsToTryRewriteToCdnUrls_ för att ange en kommaseparerad lista med fält</span><span class="sxs-lookup"><span data-stu-id="bbc66-563">Use the new property _ImageFieldsToTryRewriteToCdnUrls_ to provide a comma separated list of fields</span></span>
  + <span data-ttu-id="bbc66-564">Stöd för hyperlänkfält och PublishingImage-fält</span><span class="sxs-lookup"><span data-stu-id="bbc66-564">Supports hyperlink fields and PublishingImage fields</span></span>
+ <span data-ttu-id="bbc66-565">Bild åter givningar för SharePoint</span><span class="sxs-lookup"><span data-stu-id="bbc66-565">SharePoint image renditions</span></span>

<span data-ttu-id="bbc66-566">I följande diagram visas arbets flödet när SharePoint tar emot en begäran om en sida som innehåller till gångar från ett offentligt ursprung.</span><span class="sxs-lookup"><span data-stu-id="bbc66-566">The following diagram illustrates the workflow when SharePoint receives a request for a page containing assets from a public origin.</span></span>

<span data-ttu-id="bbc66-567">![Arbets flödes diagram: Hämta Office 365 CDN-till gångar från ett offentligt ursprung](../media/O365-CDN/o365-cdn-public-steps-transparent.svg "Arbets flöde: Hämta Office 365 CDN-till gångar från ett offentligt ursprung")</span><span class="sxs-lookup"><span data-stu-id="bbc66-567">![Workflow diagram: Retrieving Office 365 CDN assets from a public origin](../media/O365-CDN/o365-cdn-public-steps-transparent.svg "Workflow: Retrieving Office 365 CDN assets from a public origin")</span></span>

> [!TIP]
> <span data-ttu-id="bbc66-568">Om du vill inaktivera automatisk omskrivning för specifika URL-adresser på en sida kan du checka ut sidan och lägga till parametern frågesträng **? NoAutoReWrites = sant** till slutet av varje länk som du vill inaktivera.</span><span class="sxs-lookup"><span data-stu-id="bbc66-568">If you want to disable auto-rewriting for specific URLs on a page, you can check out the page and add the query string parameter **?NoAutoReWrites=true** to the end of each link you want to disable.</span></span>

#### <a name="hardcoding-cdn-urls-for-public-assets"></a><span data-ttu-id="bbc66-569">Hardcoding CDN-URL: er för offentliga till gångar</span><span class="sxs-lookup"><span data-stu-id="bbc66-569">Hardcoding CDN URLs for public assets</span></span>

<span data-ttu-id="bbc66-570">Om _publicerings_ funktionen inte är aktive rad för ett offentligt ursprung, eller om till gången inte är en av de länk typer som stöds av funktionen automatisk omskrivning i CDN-tjänsten, kan du skapa URL-adresser till till GÅNGARnas CDN-plats och använda dessa URL-adresser i innehållet.</span><span class="sxs-lookup"><span data-stu-id="bbc66-570">If the _Publishing_ feature is not enabled for a public origin, or the asset is not one of the link types supported by the auto-rewrite feature of the CDN service, you can manually construct URLs to the CDN location of the assets and use these URLs in your content.</span></span>

> [!NOTE]
> <span data-ttu-id="bbc66-571">Du kan inte hardcode CDN-URL: er till till gångar i ett privat ursprung eftersom den nödvändiga åtkomsttoken som utgör den sista delen av URL-adressen genereras när resursen begärs.</span><span class="sxs-lookup"><span data-stu-id="bbc66-571">You cannot hardcode CDN URLs to assets in a private origin because the required access token that forms the last section of the URL is generated at the time the resource is requested.</span></span>

<span data-ttu-id="bbc66-572">För offentliga CDN-till gångar ser URL-formatet ut så här:</span><span class="sxs-lookup"><span data-stu-id="bbc66-572">For public CDN assets, the URL format will look like the following:</span></span>

``` html
https://publiccdn.sharepointonline.com/<TenantHostName>/sites/site/library/asset.png
```

<span data-ttu-id="bbc66-573">Ersätt **TenantHostName** med klient namnet.</span><span class="sxs-lookup"><span data-stu-id="bbc66-573">Replace **TenantHostName** with your tenant name.</span></span> <span data-ttu-id="bbc66-574">Exempel:</span><span class="sxs-lookup"><span data-stu-id="bbc66-574">Example:</span></span>

``` html
https://publiccdn.sharepointonline.com/contoso.sharepoint.com/sites/site/library/asset.png
```

### <a name="using-assets-in-private-origins"></a><span data-ttu-id="bbc66-575">Använda till gångar i privata ursprung</span><span class="sxs-lookup"><span data-stu-id="bbc66-575">Using assets in private origins</span></span>

<span data-ttu-id="bbc66-576">Ingen ytterligare konfiguration krävs för att använda till gångar i privata ursprung.</span><span class="sxs-lookup"><span data-stu-id="bbc66-576">No additional configuration is required to use assets in private origins.</span></span> <span data-ttu-id="bbc66-577">I SharePoint Online skrivs URL-adresser automatiskt om för till gångar i privata ursprung så att begär Anden för dessa till gångar alltid kommer från CDN.</span><span class="sxs-lookup"><span data-stu-id="bbc66-577">SharePoint Online automatically rewrites URLs for assets in private origins so requests for those assets will always be served from the CDN.</span></span> <span data-ttu-id="bbc66-578">Du kan inte skapa URL: er till CDN-till gångar manuellt i privata ursprung eftersom dessa URL: er innehåller tokens som måste genereras automatiskt av SharePoint Online när du begär till gången.</span><span class="sxs-lookup"><span data-stu-id="bbc66-578">You cannot manually build URLs to CDN assets in private origins because these URLs contain tokens that must be auto-generated by SharePoint Online at the time the asset is requested.</span></span>

<span data-ttu-id="bbc66-579">Åtkomst till till gångar i privata ursprung skyddas av dynamiskt genererade token baserat på användar behörigheter till ursprung, med de villkor som beskrivs i följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="bbc66-579">Access to assets in private origins is protected by dynamically generated tokens based on user permissions to the origin, with the caveats described in the following sections.</span></span> <span data-ttu-id="bbc66-580">Användare måste minst ha **Läs** behörighet till ursprungen för att det ska gå att rendera innehållet.</span><span class="sxs-lookup"><span data-stu-id="bbc66-580">Users must have at least **read** access to the origins for the CDN to render content.</span></span>

<span data-ttu-id="bbc66-581">I följande diagram visas arbets flödet när SharePoint tar emot en begäran om en sida som innehåller till gångar från ett privat ursprung.</span><span class="sxs-lookup"><span data-stu-id="bbc66-581">The following diagram illustrates the workflow when SharePoint receives a request for a page containing assets from a private origin.</span></span>

<span data-ttu-id="bbc66-582">![Arbets flödes diagram: Hämta Office 365 CDN-till gångar från ett privat ursprung](../media/O365-CDN/o365-cdn-private-steps-transparent.svg "Arbets flöde: Hämta Office 365 CDN-till gångar från ett privat ursprung")</span><span class="sxs-lookup"><span data-stu-id="bbc66-582">![Workflow diagram: Retrieving Office 365 CDN assets from a private origin](../media/O365-CDN/o365-cdn-private-steps-transparent.svg "Workflow: Retrieving Office 365 CDN assets from a private origin")</span></span>

#### <a name="token-based-authorization-in-private-origins"></a><span data-ttu-id="bbc66-583">Token-baserad auktorisering i privata ursprung</span><span class="sxs-lookup"><span data-stu-id="bbc66-583">Token-based authorization in private origins</span></span>

<span data-ttu-id="bbc66-584">Åtkomst till till gångar i privata ursprung i Office 365 CDN beviljas av tokens som genererats av SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="bbc66-584">Access to assets in private origins in the Office 365 CDN is granted by tokens generated by SharePoint Online.</span></span> <span data-ttu-id="bbc66-585">Användare som redan har behörighet att komma åt mappen eller biblioteket som anges av ursprunget beviljas automatiskt token som gör att användaren kan komma åt filen baserat på deras behörighets nivå.</span><span class="sxs-lookup"><span data-stu-id="bbc66-585">Users who already have permission to access to the folder or library designated by the origin are automatically granted tokens that permit the user to access the file based on their permission level.</span></span> <span data-ttu-id="bbc66-586">Dessa åtkomsttoken är giltiga i 30 till 90 minuter efter att de genererats för att förhindra repetition av token.</span><span class="sxs-lookup"><span data-stu-id="bbc66-586">These access tokens are valid for 30 to 90 minutes after they are generated to help prevent token replay attacks.</span></span>

<span data-ttu-id="bbc66-587">När Access-token har genererats returnerar SharePoint Online en anpassad URI till klienten med två verifierings _Parametrar:_ dela (Edge Authorization token) och _OAT_ (ursprunglig Authorization token).</span><span class="sxs-lookup"><span data-stu-id="bbc66-587">Once the access token is generated, SharePoint Online returns a custom URI to the client containing two authorization parameters _eat_ (edge authorization token) and _oat_ (origin authorization token).</span></span> <span data-ttu-id="bbc66-588">Strukturen för varje token är _< "förfallo tid i test perioden" >__< "säker signatur" >_.</span><span class="sxs-lookup"><span data-stu-id="bbc66-588">The structure of each token is _<'expiration time in Epoch time format'>__<'secure signature'>_.</span></span> <span data-ttu-id="bbc66-589">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="bbc66-589">For example:</span></span>

``` html
https://privatecdn.sharepointonline.com/contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg?eat=1486154359_cc59042c5c55c90b26a2775323c7c8112718431228fe84d568a3795a63912840&oat=1486154359_7d73c2e3ba4b7b1f97242332900616db0d4ffb04312
```

> [!NOTE]
> <span data-ttu-id="bbc66-590">Alla som har ett token kan komma åt resursen i CDN.</span><span class="sxs-lookup"><span data-stu-id="bbc66-590">Anyone in possession of the token can access the resource in the CDN.</span></span> <span data-ttu-id="bbc66-591">URL-adresser med dessa åtkomsttoken delas bara över HTTPS, så såvida inte URL: en uttryckligen delas av en slutanvändare innan token går ut är till gången inte tillgänglig för obehöriga användare.</span><span class="sxs-lookup"><span data-stu-id="bbc66-591">However, URLs containing these access tokens are only shared over HTTPS, so unless the URL is explicitly shared by an end user before the token expires, the asset won't be accessible to unauthorized users.</span></span>

#### <a name="item-level-permissions-are-not-supported-for-assets-in-private-origins"></a><span data-ttu-id="bbc66-592">Behörigheter på objekt nivå stöds inte för till gångar i privata ursprung</span><span class="sxs-lookup"><span data-stu-id="bbc66-592">Item-level permissions are not supported for assets in private origins</span></span>

<span data-ttu-id="bbc66-593">Det är viktigt att du är medveten om att SharePoint Online inte hanterar behörigheter på objekt nivå för till gångar i privata ursprung.</span><span class="sxs-lookup"><span data-stu-id="bbc66-593">It is important to note that SharePoint Online does not support item-level permissions for assets in private origins.</span></span> <span data-ttu-id="bbc66-594">Användare har till exempel en `https://contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg` effektiv åtkomst till filen med följande villkor:</span><span class="sxs-lookup"><span data-stu-id="bbc66-594">For example, for a file located at `https://contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg`, users have effective access to the file given the following conditions:</span></span>

|<span data-ttu-id="bbc66-595">Användare</span><span class="sxs-lookup"><span data-stu-id="bbc66-595">User</span></span>  |<span data-ttu-id="bbc66-596">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="bbc66-596">Permissions</span></span>  |<span data-ttu-id="bbc66-597">Effektiv åtkomst</span><span class="sxs-lookup"><span data-stu-id="bbc66-597">Effective access</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="bbc66-598">Användare 1</span><span class="sxs-lookup"><span data-stu-id="bbc66-598">User 1</span></span>     |<span data-ttu-id="bbc66-599">Har åtkomst till Mapp1</span><span class="sxs-lookup"><span data-stu-id="bbc66-599">Has access to folder1</span></span>         |<span data-ttu-id="bbc66-600">Kan komma åt image1.jpg från CDN</span><span class="sxs-lookup"><span data-stu-id="bbc66-600">Can access image1.jpg from the CDN</span></span>         |
|<span data-ttu-id="bbc66-601">Användare 2</span><span class="sxs-lookup"><span data-stu-id="bbc66-601">User 2</span></span>     |<span data-ttu-id="bbc66-602">Har inte åtkomst till Mapp1</span><span class="sxs-lookup"><span data-stu-id="bbc66-602">Does not have access to folder1</span></span>         |<span data-ttu-id="bbc66-603">Det går inte att komma åt image1.jpg från CDN</span><span class="sxs-lookup"><span data-stu-id="bbc66-603">Cannot access image1.jpg from the CDN</span></span>         |
|<span data-ttu-id="bbc66-604">Användare 3</span><span class="sxs-lookup"><span data-stu-id="bbc66-604">User 3</span></span>     |<span data-ttu-id="bbc66-605">Har inte åtkomst till Mapp1, men har uttryckligen tillåtelse att komma åt image1.jpg i SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="bbc66-605">Does not have access to folder1, but is granted explicit permission to access image1.jpg in SharePoint Online</span></span>         |<span data-ttu-id="bbc66-606">Kan komma åt till gången image1.jpg direkt från SharePoint Online, men inte från CDN</span><span class="sxs-lookup"><span data-stu-id="bbc66-606">Can access the asset image1.jpg directly from SharePoint Online, but not from the CDN</span></span>         |
|<span data-ttu-id="bbc66-607">Användare 4</span><span class="sxs-lookup"><span data-stu-id="bbc66-607">User 4</span></span>     |<span data-ttu-id="bbc66-608">Har åtkomst till Mapp1, men har uttryckligen nekats åtkomst till image1.jpg i SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="bbc66-608">Has access to folder1, but has been explicitly denied access to image1.jpg in SharePoint Online</span></span>         |<span data-ttu-id="bbc66-609">Det går inte att komma åt till gången från SharePoint Online men kan komma åt till gången från CDN trots att den nekas åtkomst till filen i SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="bbc66-609">Cannot access the asset from SharePoint Online, but can access the asset from the CDN despite being denied access to the file in SharePoint Online</span></span>         |

<span data-ttu-id="bbc66-610"><a name="CDNTroubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="bbc66-610"><a name="CDNTroubleshooting"> </a></span></span>
## <a name="troubleshooting-the-office-365-cdn"></a><span data-ttu-id="bbc66-611">Felsöka Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="bbc66-611">Troubleshooting the Office 365 CDN</span></span>

<span data-ttu-id="bbc66-612"><a name="CDNConfirm"> </a></span><span class="sxs-lookup"><span data-stu-id="bbc66-612"><a name="CDNConfirm"> </a></span></span>
### <a name="how-do-i-confirm-that-assets-are-being-served-by-the-cdn"></a><span data-ttu-id="bbc66-613">Hur bekräftar jag att till gångar betjänas av CDN?</span><span class="sxs-lookup"><span data-stu-id="bbc66-613">How do I confirm that assets are being served by the CDN?</span></span>

<span data-ttu-id="bbc66-614">När du har lagt till länkar till CDN-till gångar på en sida kan du bekräfta att till gången betjänas från CDN genom att bläddra till sidan och högerklicka på bilden när den har Render ATS och granska bild-URL: en.</span><span class="sxs-lookup"><span data-stu-id="bbc66-614">Once you have added links to CDN assets to a page, you can confirm that the asset is being served from the CDN by browsing to the page, right clicking on the image once it has rendered and reviewing the image URL.</span></span>

<span data-ttu-id="bbc66-615">Du kan också använda din webbläsares utvecklingsverktyg för att Visa webb adressen för varje objekt på en sida eller använda en tredjepartsleverantör för nätverks spårning.</span><span class="sxs-lookup"><span data-stu-id="bbc66-615">You can also use your browser's developer tools to view the URL for each asset on a page, or use a third party network trace tool.</span></span>

> [!NOTE]
> <span data-ttu-id="bbc66-616">Om du använder ett nätverks verktyg som/Fiddler-loggar för att testa dina till gångar från en SharePoint-sida, måste du lägga till referens rubriken "referering: `https://yourdomain.sharepoint.com` " till GET-begäran där URL-adressen är rot-URL för SharePoint Online-klienten.</span><span class="sxs-lookup"><span data-stu-id="bbc66-616">If you use a network tool such as Fiddler to test your assets outside of rendering the asset from a SharePoint page, you must manually add the referer header "Referer: `https://yourdomain.sharepoint.com`" to the GET request where the URL is the root URL of your SharePoint Online tenant.</span></span>

<span data-ttu-id="bbc66-617">Du kan inte testa CDN-adresser direkt i en webbläsare eftersom det finns en refererare från SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="bbc66-617">You cannot test CDN URLs directly in a web browser because you must have a referer coming from SharePoint Online.</span></span> <span data-ttu-id="bbc66-618">Om du däremot lägger till URL-adressen till till gången på en SharePoint-sida och sedan öppnar sidan i en webbläsare visas CDN-resursen som återges på sidan.</span><span class="sxs-lookup"><span data-stu-id="bbc66-618">However, if you add the CDN asset URL to a SharePoint page and then open the page in a browser, you will see the CDN asset rendered on the page.</span></span>

<span data-ttu-id="bbc66-619">Mer information om hur du använder utvecklingsverktygen i webbläsaren Microsoft Edge finns i [Microsoft Edge Developer Tools](https://docs.microsoft.com/microsoft-edge/devtools-guide).</span><span class="sxs-lookup"><span data-stu-id="bbc66-619">For more information on using the developer tools in the Microsoft Edge browser, see [Microsoft Edge Developer Tools](https://docs.microsoft.com/microsoft-edge/devtools-guide).</span></span>

<span data-ttu-id="bbc66-620">Om du vill titta på en kort video som finns i [SharePoint-utvecklingsverktygen och Practices YouTube-kanalen](https://aka.ms/sppnp-videos) som visar hur du kontrollerar att CDN fungerar, se [Verifiera ditt CDN-bruk och säkerställa optimal nätverks anslutning](https://www.youtube.com/watch?v=ClCtBAtGjE8&list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA&index=5).</span><span class="sxs-lookup"><span data-stu-id="bbc66-620">To watch a short video hosted in the [SharePoint Developer Patterns and Practices YouTube channel](https://aka.ms/sppnp-videos) demonstrating how to verify that your CDN is working, please see [Verifying your CDN usage and ensuring optimal network connectivity](https://www.youtube.com/watch?v=ClCtBAtGjE8&list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA&index=5).</span></span>

### <a name="why-are-assets-from-a-new-origin-unavailable"></a><span data-ttu-id="bbc66-621">Varför är inte till gångar från ett nytt ursprungs ursprung?</span><span class="sxs-lookup"><span data-stu-id="bbc66-621">Why are assets from a new origin unavailable?</span></span>
<span data-ttu-id="bbc66-622">Till gångar i nya ursprung är inte omedelbart tillgängliga för användning, eftersom det tar tid för registreringen att sprida sig genom CDN och för till gångar att laddas upp från origo till CDN-lagring.</span><span class="sxs-lookup"><span data-stu-id="bbc66-622">Assets in new origins will not immediately be available for use, as it takes time for the registration to propagate through the CDN and for the assets to be uploaded from the origin to CDN storage.</span></span> <span data-ttu-id="bbc66-623">Den tid som krävs för att till gångar ska vara tillgänglig i CDN beror på hur många till gångar och filernas storlek.</span><span class="sxs-lookup"><span data-stu-id="bbc66-623">The time required for assets to be available in the CDN depends on how many assets and the files sizes.</span></span>

### <a name="my-client-side-web-part-or-sharepoint-framework-solution-isnt-working"></a><span data-ttu-id="bbc66-624">Min webb dels klient eller SharePoint Framework-lösning fungerar inte</span><span class="sxs-lookup"><span data-stu-id="bbc66-624">My client-side web part or SharePoint Framework solution isn't working</span></span>

<span data-ttu-id="bbc66-625">När du aktiverar Office 365 CDN för offentliga ursprung, skapar CDN-tjänsten automatiskt dessa standard ursprung:</span><span class="sxs-lookup"><span data-stu-id="bbc66-625">When you enable the Office 365 CDN for public origins, the CDN service automatically creates these default origins:</span></span>

+ <span data-ttu-id="bbc66-626">\*/MASTERPAGE</span><span class="sxs-lookup"><span data-stu-id="bbc66-626">\*/MASTERPAGE</span></span>
+ <span data-ttu-id="bbc66-627">\*/STYLE-BIBLIOTEK</span><span class="sxs-lookup"><span data-stu-id="bbc66-627">\*/STYLE LIBRARY</span></span>
+ <span data-ttu-id="bbc66-628">\*/CLIENTSIDEASSETS</span><span class="sxs-lookup"><span data-stu-id="bbc66-628">\*/CLIENTSIDEASSETS</span></span>

<span data-ttu-id="bbc66-629">Om \*/clientsideassets-Origo saknas Miss lyckas SharePoint Framework-lösningar och ingen varnings-eller fel meddelanden genereras.</span><span class="sxs-lookup"><span data-stu-id="bbc66-629">If the \*/clientsideassets origin is missing, SharePoint Framework solutions will fail, and no warning or error messages are generated.</span></span> <span data-ttu-id="bbc66-630">Detta ursprung kan saknas antingen på grund av att CDN aktiverades med parametern _-NoDefaultOrigins_ inställd på **$True**, eller på grund av att origo togs bort manuellt.</span><span class="sxs-lookup"><span data-stu-id="bbc66-630">This origin may be missing either because the CDN was enabled with the _-NoDefaultOrigins_ parameter set to **$true**, or because the origin was manually deleted.</span></span>

<span data-ttu-id="bbc66-631">Du kan kontrol lera vilka ursprung som finns med följande PowerShell-kommando:</span><span class="sxs-lookup"><span data-stu-id="bbc66-631">You can check to see which origins are present with the following PowerShell command:</span></span>

``` powershell
Get-SPOTenantCdnOrigins -CdnType Public
```

<span data-ttu-id="bbc66-632">Eller så kan du kontrol lera med Office 365-CLI:</span><span class="sxs-lookup"><span data-stu-id="bbc66-632">Or you can check with the Office 365 CLI:</span></span>

``` powershell
spo cdn origin list
```

<span data-ttu-id="bbc66-633">Så här lägger du till ursprung i PowerShell:</span><span class="sxs-lookup"><span data-stu-id="bbc66-633">To add the origin in PowerShell:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */CLIENTSIDEASSETS
```

<span data-ttu-id="bbc66-634">Så här lägger du till ursprunget i Office 365-CLI:</span><span class="sxs-lookup"><span data-stu-id="bbc66-634">To add the origin in the Office 365 CLI:</span></span>

``` powershell
spo cdn origin add --origin */CLIENTSIDEASSETS
```

### <a name="what-powershell-modules-and-cli-shells-do-i-need-to-work-with-the-office-365-cdn"></a><span data-ttu-id="bbc66-635">Vilka PowerShell-moduler och CLI-gränssnitt behöver jag för att arbeta med Office 365 CDN?</span><span class="sxs-lookup"><span data-stu-id="bbc66-635">What PowerShell modules and CLI shells do I need to work with the Office 365 CDN?</span></span>

<span data-ttu-id="bbc66-636">Du kan välja att arbeta med Office 365 CDN med antingen **SharePoint Online Management Shell** PowerShell-modulen eller **Office 365-CLI**.</span><span class="sxs-lookup"><span data-stu-id="bbc66-636">You can choose to work with the Office 365 CDN using either the **SharePoint Online Management Shell** PowerShell module or the **Office 365 CLI**.</span></span>

+ [<span data-ttu-id="bbc66-637">Komma igång med SharePoint Online Management Shell</span><span class="sxs-lookup"><span data-stu-id="bbc66-637">Getting started with SharePoint Online Management Shell</span></span>](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)
+ [<span data-ttu-id="bbc66-638">Installera Office 365-CLI</span><span class="sxs-lookup"><span data-stu-id="bbc66-638">Installing the Office 365 CLI</span></span>](https://pnp.github.io/office365-cli/user-guide/installing-cli/)

## <a name="see-also"></a><span data-ttu-id="bbc66-639">Se även</span><span class="sxs-lookup"><span data-stu-id="bbc66-639">See also</span></span>

[<span data-ttu-id="bbc66-640">Nätverk för innehålls leverans</span><span class="sxs-lookup"><span data-stu-id="bbc66-640">Content Delivery Networks</span></span>](https://aka.ms/o365cdns)

[<span data-ttu-id="bbc66-641">Network planning and performance tuning for Office 365</span><span class="sxs-lookup"><span data-stu-id="bbc66-641">Network planning and performance tuning for Office 365</span></span>](https://aka.ms/tune)

[<span data-ttu-id="bbc66-642">SharePoint-prestandaräknare – Office 365 CDN-videoserie</span><span class="sxs-lookup"><span data-stu-id="bbc66-642">SharePoint Performance Series - Office 365 CDN video series</span></span>](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)
