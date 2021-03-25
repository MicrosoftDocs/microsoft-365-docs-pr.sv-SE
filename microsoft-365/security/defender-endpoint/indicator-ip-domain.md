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
ms.openlocfilehash: d468a77d2c1ab4f1b363e2e91b6e8507a5390d93
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198491"
---
# <a name="create-indicators-for-ips-and-urlsdomains"></a><span data-ttu-id="567bd-104">Skapa indikatorer för IP-adresser och URL:er/domäner</span><span class="sxs-lookup"><span data-stu-id="567bd-104">Create indicators for IPs and URLs/domains</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="567bd-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="567bd-105">**Applies to:**</span></span>
- [<span data-ttu-id="567bd-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="567bd-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="567bd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="567bd-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)



> [!TIP]
> <span data-ttu-id="567bd-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="567bd-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="567bd-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="567bd-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)


<span data-ttu-id="567bd-110">Defender för Endpoint kan blockera vad Microsoft bedömer som skadliga IP-adresser/URL-adresser, via Windows Defender SmartScreen för Microsoft-webbläsare och via Nätverksskydd för webbläsare som inte är Microsoft eller samtal som görs utanför en webbläsare.</span><span class="sxs-lookup"><span data-stu-id="567bd-110">Defender for Endpoint can block what Microsoft deems as malicious IPs/URLs, through Windows Defender SmartScreen for Microsoft browsers, and through Network Protection for non-Microsoft browsers or calls made outside of a browser.</span></span>

<span data-ttu-id="567bd-111">Datauppsättningen för hotinformation för detta har hanterats av Microsoft.</span><span class="sxs-lookup"><span data-stu-id="567bd-111">The threat intelligence data set for this has been managed by Microsoft.</span></span>

<span data-ttu-id="567bd-112">Genom att skapa indikatorer för IP-adresser och URL:er eller domäner kan du nu tillåta eller blockera IP-adresser, URL:er eller domäner baserat på din egen hotinformation.</span><span class="sxs-lookup"><span data-stu-id="567bd-112">By creating indicators for IPs and URLs or domains, you can now allow or block IPs, URLs, or domains based on your own threat intelligence.</span></span> <span data-ttu-id="567bd-113">Det kan du göra via inställningssidan eller efter datorgrupper om du anser att vissa grupper är mer eller mindre riskerade än andra.</span><span class="sxs-lookup"><span data-stu-id="567bd-113">You can do this through the settings page or by machine groups if you deem certain groups to be more or less at risk than others.</span></span>

> [!NOTE]
> <span data-ttu-id="567bd-114">Classless Inter-Domain Routing (CIDR) notation for IP addresses is not supported.</span><span class="sxs-lookup"><span data-stu-id="567bd-114">Classless Inter-Domain Routing (CIDR) notation for IP addresses is not supported.</span></span> 

### <a name="before-you-begin"></a><span data-ttu-id="567bd-115">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="567bd-115">Before you begin</span></span>
<span data-ttu-id="567bd-116">Det är viktigt att förstå följande förutsättningar innan du skapar indikatorer för IPS, URL:er eller domäner:</span><span class="sxs-lookup"><span data-stu-id="567bd-116">It's important to understand the following prerequisites prior to creating indicators for IPS, URLs, or domains:</span></span>
- <span data-ttu-id="567bd-117">Tillåt och blockera URL/IP förlitar sig på att Defender för Endpoint-komponenten Nätverksskydd aktiveras i blockeringsläge.</span><span class="sxs-lookup"><span data-stu-id="567bd-117">URL/IP allow and block relies on the Defender for Endpoint component Network Protection to be enabled in block mode.</span></span> <span data-ttu-id="567bd-118">Mer information om nätverksskydd och konfigurationsanvisningar finns [i Aktivera nätverksskydd.](enable-network-protection.md)</span><span class="sxs-lookup"><span data-stu-id="567bd-118">For more information on Network Protection and configuration instructions, see [Enable network protection](enable-network-protection.md).</span></span>
- <span data-ttu-id="567bd-119">Klientversionen av Antimalware måste vara 4.18.1906.x eller senare.</span><span class="sxs-lookup"><span data-stu-id="567bd-119">The Antimalware client version must be 4.18.1906.x or later.</span></span> 
- <span data-ttu-id="567bd-120">Stöds på datorer med Windows 10, version 1709 eller senare.</span><span class="sxs-lookup"><span data-stu-id="567bd-120">Supported on machines on Windows 10, version 1709 or later.</span></span> 
- <span data-ttu-id="567bd-121">Kontrollera att **indikatorerna för anpassade** nätverk är aktiverade **i Microsoft Defender Säkerhetscenter > inställningar > Avancerade funktioner.**</span><span class="sxs-lookup"><span data-stu-id="567bd-121">Ensure that **Custom network indicators** is enabled in **Microsoft Defender Security Center > Settings > Advanced features**.</span></span> <span data-ttu-id="567bd-122">Mer information finns i [Avancerade funktioner.](advanced-features.md)</span><span class="sxs-lookup"><span data-stu-id="567bd-122">For more information, see [Advanced features](advanced-features.md).</span></span>
- <span data-ttu-id="567bd-123">Information om stöd för indikatorer i iOS finns i [Konfigurera anpassade indikatorer.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/ios-configure-features#configure-custom-indicators)</span><span class="sxs-lookup"><span data-stu-id="567bd-123">For support of indicators on iOS, see [Configure custom indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/ios-configure-features#configure-custom-indicators).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="567bd-124">Endast externa IP-adresser kan läggas till i indikatorlistan.</span><span class="sxs-lookup"><span data-stu-id="567bd-124">Only external IPs can be added to the indicator list.</span></span> <span data-ttu-id="567bd-125">Indikatorer kan inte skapas för interna IP-adresser.</span><span class="sxs-lookup"><span data-stu-id="567bd-125">Indicators cannot be created for internal IPs.</span></span>
> <span data-ttu-id="567bd-126">För webbskyddsscenarier rekommenderar vi att du använder de inbyggda funktionerna i Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="567bd-126">For web protection scenarios, we recommend using the built-in capabilities in Microsoft Edge.</span></span> <span data-ttu-id="567bd-127">Microsoft Edge inspekterar [nätverkstrafik med](network-protection.md) hjälp av Nätverksskydd och tillåter block för TCP, HTTP och HTTPS (TLS).</span><span class="sxs-lookup"><span data-stu-id="567bd-127">Microsoft Edge leverages [Network Protection](network-protection.md) to inspect network traffic and allows blocks for TCP, HTTP, and HTTPS (TLS).</span></span> <span data-ttu-id="567bd-128">Om det finns URL-indikatorprinciper som är i konflikt tillämpas den längre sökvägen.</span><span class="sxs-lookup"><span data-stu-id="567bd-128">If there are conflicting URL indicator policies, the longer path is applied.</span></span> <span data-ttu-id="567bd-129">URL-indikatorprincipen har `https:\\support.microsoft.com/en-us/office` till exempel företräde framför URL-indikatorprincipen. `https:\\support.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="567bd-129">For example, the URL indicator policy `https:\\support.microsoft.com/en-us/office` takes precedence over the URL indicator policy `https:\\support.microsoft.com`.</span></span>

> [!NOTE]
> <span data-ttu-id="567bd-130">För alla andra processer använder webbskyddsscenarier Nätverksskydd för kontroll och tillämpning:</span><span class="sxs-lookup"><span data-stu-id="567bd-130">For all other processes, web protection scenarios leverage Network Protection for inspection and enforcement:</span></span> 
> - <span data-ttu-id="567bd-131">IP stöds för alla tre protokollen</span><span class="sxs-lookup"><span data-stu-id="567bd-131">IP is supported for all three protocols</span></span>
> - <span data-ttu-id="567bd-132">Endast enskilda IP-adresser stöds (inga CIDR-block eller IP-intervall)</span><span class="sxs-lookup"><span data-stu-id="567bd-132">Only single IP addresses are supported (no CIDR blocks or IP ranges)</span></span>
> - <span data-ttu-id="567bd-133">Krypterade URL:er (fullständig sökväg) kan endast blockeras i webbläsare från första part (Internet Explorer, Edge)</span><span class="sxs-lookup"><span data-stu-id="567bd-133">Encrypted URLs (full path) can only be blocked on first party browsers (Internet Explorer, Edge)</span></span>
> - <span data-ttu-id="567bd-134">Krypterade URL:er (endast FQDN) kan blockeras utanför webbläsare från första part (Internet Explorer, Edge)</span><span class="sxs-lookup"><span data-stu-id="567bd-134">Encrypted URLS (FQDN only) can be blocked outside of first party browsers (Internet Explorer, Edge)</span></span>
> - <span data-ttu-id="567bd-135">Fullständiga URL-sökvägsblock kan tillämpas på domännivån och alla okrypterade URL:er</span><span class="sxs-lookup"><span data-stu-id="567bd-135">Full URL path blocks can be applied on the domain level and all unencrypted URLs</span></span>
 
> [!NOTE]
> <span data-ttu-id="567bd-136">Det kan finnas upp till två timmars svarstid (vanligtvis mindre) mellan den tid åtgärden vidtas och URL:en och IP blockeras.</span><span class="sxs-lookup"><span data-stu-id="567bd-136">There may be up to 2 hours of latency (usually less) between the time the action is taken, and the URL and IP being blocked.</span></span> 

### <a name="create-an-indicator-for-ips-urls-or-domains-from-the-settings-page"></a><span data-ttu-id="567bd-137">Skapa en indikator för IP-adresser, URL:er eller domäner från inställningssidan</span><span class="sxs-lookup"><span data-stu-id="567bd-137">Create an indicator for IPs, URLs, or domains from the settings page</span></span>

1. <span data-ttu-id="567bd-138">Välj Inställningar Indikatorer i  >  **navigeringsfönstret.**</span><span class="sxs-lookup"><span data-stu-id="567bd-138">In the navigation pane, select **Settings** > **Indicators**.</span></span>  

2. <span data-ttu-id="567bd-139">Välj **fliken IP-adresser eller URL:er/Domäner.**</span><span class="sxs-lookup"><span data-stu-id="567bd-139">Select the **IP addresses or URLs/Domains** tab.</span></span>

3. <span data-ttu-id="567bd-140">Välj **Lägg till objekt.**</span><span class="sxs-lookup"><span data-stu-id="567bd-140">Select **Add item**.</span></span>

4. <span data-ttu-id="567bd-141">Ange följande information:</span><span class="sxs-lookup"><span data-stu-id="567bd-141">Specify the following details:</span></span>
   - <span data-ttu-id="567bd-142">Indikator – Ange entitetsinformation och definiera indikatorns förfallotid.</span><span class="sxs-lookup"><span data-stu-id="567bd-142">Indicator - Specify the entity details and define the expiration of the indicator.</span></span>
   - <span data-ttu-id="567bd-143">Åtgärd – Ange vilken åtgärd som ska vidtas och ange en beskrivning.</span><span class="sxs-lookup"><span data-stu-id="567bd-143">Action - Specify the action to be taken and provide a description.</span></span>
   - <span data-ttu-id="567bd-144">Omfattning – Definiera datorgruppens omfattning.</span><span class="sxs-lookup"><span data-stu-id="567bd-144">Scope - Define the scope of the machine group.</span></span>

5. <span data-ttu-id="567bd-145">Granska informationen på fliken Sammanfattning och klicka sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="567bd-145">Review the details in the Summary tab, then click **Save**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="567bd-146">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="567bd-146">Related topics</span></span>
- [<span data-ttu-id="567bd-147">Skapa indikatorer</span><span class="sxs-lookup"><span data-stu-id="567bd-147">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="567bd-148">Skapa indikatorer för filer</span><span class="sxs-lookup"><span data-stu-id="567bd-148">Create indicators for files</span></span>](indicator-file.md)
- [<span data-ttu-id="567bd-149">Skapa indikatorer baserade på certifikat</span><span class="sxs-lookup"><span data-stu-id="567bd-149">Create indicators based on certificates</span></span>](indicator-certificates.md)
- [<span data-ttu-id="567bd-150">Hantera indikatorer</span><span class="sxs-lookup"><span data-stu-id="567bd-150">Manage indicators</span></span>](indicator-manage.md)
