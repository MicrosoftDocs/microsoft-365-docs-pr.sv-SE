---
title: Skapa indikatorer för IP-adresser och URL:er/domäner
ms.reviewer: ''
description: Skapa indikatorer för IP-adresser och URL:er/domäner som definierar identifiering, skydd och undantag för enheter.
keywords: ip, url, domän, hantera, tillåten, blockerad, blockera, rensa, skadlig, filshashar, ip-adress, url:er, domän
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 0196148c9dbf3ec769594d714524a3fd9e4d18fd
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185963"
---
# <a name="create-indicators-for-ips-and-urlsdomains"></a><span data-ttu-id="86060-104">Skapa indikatorer för IP-adresser och URL:er/domäner</span><span class="sxs-lookup"><span data-stu-id="86060-104">Create indicators for IPs and URLs/domains</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="86060-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="86060-105">**Applies to:**</span></span>
- [<span data-ttu-id="86060-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="86060-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="86060-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="86060-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)



><span data-ttu-id="86060-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="86060-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="86060-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="86060-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)


<span data-ttu-id="86060-110">Defender för Endpoint kan blockera vad Microsoft bedömer som skadliga IP-adresser/URL-adresser, via Windows Defender SmartScreen för Microsoft-webbläsare och via Nätverksskydd för webbläsare som inte är Microsoft eller samtal som görs utanför en webbläsare.</span><span class="sxs-lookup"><span data-stu-id="86060-110">Defender for Endpoint can block what Microsoft deems as malicious IPs/URLs, through Windows Defender SmartScreen for Microsoft browsers, and through Network Protection for non-Microsoft browsers or calls made outside of a browser.</span></span>

<span data-ttu-id="86060-111">Datauppsättningen för hotinformation för detta har hanterats av Microsoft.</span><span class="sxs-lookup"><span data-stu-id="86060-111">The threat intelligence data set for this has been managed by Microsoft.</span></span>

<span data-ttu-id="86060-112">Genom att skapa indikatorer för IP-adresser och URL:er eller domäner kan du nu tillåta eller blockera IP-adresser, URL:er eller domäner baserat på din egen hotinformation.</span><span class="sxs-lookup"><span data-stu-id="86060-112">By creating indicators for IPs and URLs or domains, you can now allow or block IPs, URLs, or domains based on your own threat intelligence.</span></span> <span data-ttu-id="86060-113">Det kan du göra via inställningssidan eller efter datorgrupper om du anser att vissa grupper är mer eller mindre riskerade än andra.</span><span class="sxs-lookup"><span data-stu-id="86060-113">You can do this through the settings page or by machine groups if you deem certain groups to be more or less at risk than others.</span></span>

> [!NOTE]
> <span data-ttu-id="86060-114">Classless Inter-Domain Routing (CIDR) notation for IP addresses is not supported.</span><span class="sxs-lookup"><span data-stu-id="86060-114">Classless Inter-Domain Routing (CIDR) notation for IP addresses is not supported.</span></span> 

### <a name="before-you-begin"></a><span data-ttu-id="86060-115">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="86060-115">Before you begin</span></span>
<span data-ttu-id="86060-116">Det är viktigt att förstå följande förutsättningar innan du skapar indikatorer för IPS, URL:er eller domäner:</span><span class="sxs-lookup"><span data-stu-id="86060-116">It's important to understand the following prerequisites prior to creating indicators for IPS, URLs, or domains:</span></span>
- <span data-ttu-id="86060-117">Tillåt och blockera URL/IP förlitar sig på att Defender för Endpoint-komponenten Nätverksskydd aktiveras i blockeringsläge.</span><span class="sxs-lookup"><span data-stu-id="86060-117">URL/IP allow and block relies on the Defender for Endpoint component Network Protection to be enabled in block mode.</span></span> <span data-ttu-id="86060-118">Mer information om nätverksskydd och konfigurationsanvisningar finns [i Aktivera nätverksskydd.](enable-network-protection.md)</span><span class="sxs-lookup"><span data-stu-id="86060-118">For more information on Network Protection and configuration instructions, see [Enable network protection](enable-network-protection.md).</span></span>
- <span data-ttu-id="86060-119">Klientversionen av Antimalware måste vara 4.18.1906.x eller senare.</span><span class="sxs-lookup"><span data-stu-id="86060-119">The Antimalware client version must be 4.18.1906.x or later.</span></span> 
- <span data-ttu-id="86060-120">Stöds på datorer med Windows 10, version 1709 eller senare.</span><span class="sxs-lookup"><span data-stu-id="86060-120">Supported on machines on Windows 10, version 1709 or later.</span></span> 
- <span data-ttu-id="86060-121">Kontrollera att **indikatorerna för anpassade** nätverk är aktiverade **i Microsoft Defender Säkerhetscenter > inställningar > Avancerade funktioner.**</span><span class="sxs-lookup"><span data-stu-id="86060-121">Ensure that **Custom network indicators** is enabled in **Microsoft Defender Security Center > Settings > Advanced features**.</span></span> <span data-ttu-id="86060-122">Mer information finns i [Avancerade funktioner.](advanced-features.md)</span><span class="sxs-lookup"><span data-stu-id="86060-122">For more information, see [Advanced features](advanced-features.md).</span></span>
- <span data-ttu-id="86060-123">Information om stöd för indikatorer i iOS finns i [Konfigurera anpassade indikatorer.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/ios-configure-features#configure-custom-indicators)</span><span class="sxs-lookup"><span data-stu-id="86060-123">For support of indicators on iOS, see [Configure custom indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/ios-configure-features#configure-custom-indicators).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="86060-124">Endast externa IP-adresser kan läggas till i indikatorlistan.</span><span class="sxs-lookup"><span data-stu-id="86060-124">Only external IPs can be added to the indicator list.</span></span> <span data-ttu-id="86060-125">Indikatorer kan inte skapas för interna IP-adresser.</span><span class="sxs-lookup"><span data-stu-id="86060-125">Indicators cannot be created for internal IPs.</span></span>
> <span data-ttu-id="86060-126">För webbskyddsscenarier rekommenderar vi att du använder de inbyggda funktionerna i Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="86060-126">For web protection scenarios, we recommend using the built-in capabilities in Microsoft Edge.</span></span> <span data-ttu-id="86060-127">Microsoft Edge inspekterar [nätverkstrafik med](network-protection.md) hjälp av Nätverksskydd och tillåter block för TCP, HTTP och HTTPS (TLS).</span><span class="sxs-lookup"><span data-stu-id="86060-127">Microsoft Edge leverages [Network Protection](network-protection.md) to inspect network traffic and allows blocks for TCP, HTTP, and HTTPS (TLS).</span></span> <span data-ttu-id="86060-128">För alla andra processer använder webbskyddsscenarier Nätverksskydd för kontroll och tillämpning:</span><span class="sxs-lookup"><span data-stu-id="86060-128">For all other processes, web protection scenarios leverage Network Protection for inspection and enforcement:</span></span> <br>
> <span data-ttu-id="86060-129">OBS!</span><span class="sxs-lookup"><span data-stu-id="86060-129">NOTE:</span></span>
> - <span data-ttu-id="86060-130">IP stöds för alla tre protokollen</span><span class="sxs-lookup"><span data-stu-id="86060-130">IP is supported for all three protocols</span></span>
> - <span data-ttu-id="86060-131">Endast enskilda IP-adresser stöds (inga CIDR-block eller IP-intervall)</span><span class="sxs-lookup"><span data-stu-id="86060-131">Only single IP addresses are supported (no CIDR blocks or IP ranges)</span></span>
> - <span data-ttu-id="86060-132">Krypterade URL:er (fullständig sökväg) kan endast blockeras i webbläsare från första part (Internet Explorer, Edge)</span><span class="sxs-lookup"><span data-stu-id="86060-132">Encrypted URLs (full path) can only be blocked on first party browsers (Internet Explorer, Edge)</span></span>
> - <span data-ttu-id="86060-133">Krypterade URL:er (endast FQDN) kan blockeras utanför webbläsare från första part (Internet Explorer, Edge)</span><span class="sxs-lookup"><span data-stu-id="86060-133">Encrypted URLS (FQDN only) can be blocked outside of first party browsers (Internet Explorer, Edge)</span></span>
> - <span data-ttu-id="86060-134">Fullständiga URL-sökvägsblock kan tillämpas på domännivån och alla okrypterade URL:er</span><span class="sxs-lookup"><span data-stu-id="86060-134">Full URL path blocks can be applied on the domain level and all unencrypted URLs</span></span>
 
> [!NOTE]
> <span data-ttu-id="86060-135">Det kan finnas upp till två timmars svarstid (vanligtvis mindre) mellan den tid åtgärden vidtas och URL:en och IP blockeras.</span><span class="sxs-lookup"><span data-stu-id="86060-135">There may be up to 2 hours of latency (usually less) between the time the action is taken, and the URL and IP being blocked.</span></span> 

### <a name="create-an-indicator-for-ips-urls-or-domains-from-the-settings-page"></a><span data-ttu-id="86060-136">Skapa en indikator för IP-adresser, URL:er eller domäner från inställningssidan</span><span class="sxs-lookup"><span data-stu-id="86060-136">Create an indicator for IPs, URLs, or domains from the settings page</span></span>

1. <span data-ttu-id="86060-137">Välj Inställningar Indikatorer i  >  **navigeringsfönstret.**</span><span class="sxs-lookup"><span data-stu-id="86060-137">In the navigation pane, select **Settings** > **Indicators**.</span></span>  

2. <span data-ttu-id="86060-138">Välj **fliken IP-adresser eller URL:er/Domäner.**</span><span class="sxs-lookup"><span data-stu-id="86060-138">Select the **IP addresses or URLs/Domains** tab.</span></span>

3. <span data-ttu-id="86060-139">Välj **Lägg till objekt.**</span><span class="sxs-lookup"><span data-stu-id="86060-139">Select **Add item**.</span></span>

4. <span data-ttu-id="86060-140">Ange följande information:</span><span class="sxs-lookup"><span data-stu-id="86060-140">Specify the following details:</span></span>
   - <span data-ttu-id="86060-141">Indikator – Ange entitetsinformation och definiera indikatorns förfallotid.</span><span class="sxs-lookup"><span data-stu-id="86060-141">Indicator - Specify the entity details and define the expiration of the indicator.</span></span>
   - <span data-ttu-id="86060-142">Åtgärd – Ange vilken åtgärd som ska vidtas och ange en beskrivning.</span><span class="sxs-lookup"><span data-stu-id="86060-142">Action - Specify the action to be taken and provide a description.</span></span>
   - <span data-ttu-id="86060-143">Omfattning – Definiera datorgruppens omfattning.</span><span class="sxs-lookup"><span data-stu-id="86060-143">Scope - Define the scope of the machine group.</span></span>

5. <span data-ttu-id="86060-144">Granska informationen på fliken Sammanfattning och klicka sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="86060-144">Review the details in the Summary tab, then click **Save**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="86060-145">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="86060-145">Related topics</span></span>
- [<span data-ttu-id="86060-146">Skapa indikatorer</span><span class="sxs-lookup"><span data-stu-id="86060-146">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="86060-147">Skapa indikatorer för filer</span><span class="sxs-lookup"><span data-stu-id="86060-147">Create indicators for files</span></span>](indicator-file.md)
- [<span data-ttu-id="86060-148">Skapa indikatorer baserade på certifikat</span><span class="sxs-lookup"><span data-stu-id="86060-148">Create indicators based on certificates</span></span>](indicator-certificates.md)
- [<span data-ttu-id="86060-149">Hantera indikatorer</span><span class="sxs-lookup"><span data-stu-id="86060-149">Manage indicators</span></span>](indicator-manage.md)
