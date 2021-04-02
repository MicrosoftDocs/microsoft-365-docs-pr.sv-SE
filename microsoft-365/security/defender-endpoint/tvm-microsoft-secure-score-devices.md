---
title: Microsoft Secure Score för enheter
description: Poängen för enheter visar den samlade säkerhetskonfigurationstillståndet för dina enheter i olika program, operativsystem, nätverk, konton och säkerhetskontroller.
keywords: Microsoft Secure Score för enheter, mdatp Microsoft Secure Score för enheter, secure score, konfigurationsresultat, hantering av hot och sårbarhet, säkerhetskontroller, förbättringsmöjligheter, poäng för säkerhetskonfiguration över tid, säkerhetskonfigurationsresultat, baslinje
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: fcf33b309045b9ca763b0d3cabc44fb13505ee0b
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500058"
---
# <a name="microsoft-secure-score-for-devices"></a><span data-ttu-id="485da-104">Microsoft Secure Score för enheter</span><span class="sxs-lookup"><span data-stu-id="485da-104">Microsoft Secure Score for Devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="485da-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="485da-105">**Applies to:**</span></span>

- [<span data-ttu-id="485da-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="485da-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="485da-107">Hantering av hot och sårbarhet</span><span class="sxs-lookup"><span data-stu-id="485da-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="485da-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="485da-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="485da-109">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="485da-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="485da-110">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="485da-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


>[!NOTE]
> <span data-ttu-id="485da-111">Konfigurationsresultat är nu en del av hantering av hot och problem som Microsoft Secure Score för enheter.</span><span class="sxs-lookup"><span data-stu-id="485da-111">Configuration score is now part of threat and vulnerability management as Microsoft Secure Score for Devices.</span></span>

<span data-ttu-id="485da-112">Din poäng för enheter är synlig i instrumentpanelen [för hantering av hot och sårbarhet](tvm-dashboard-insights.md) i Microsoft Defender Säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="485da-112">Your score for devices is visible in the [threat and vulnerability management dashboard](tvm-dashboard-insights.md) of the Microsoft Defender Security Center.</span></span> <span data-ttu-id="485da-113">Ett högre Microsoft Secure Score för enheter innebär att dina slutpunkter är mer flexibel mot attacker mot hot om cyberhot.</span><span class="sxs-lookup"><span data-stu-id="485da-113">A higher Microsoft Secure Score for Devices means your endpoints are more resilient from cybersecurity threat attacks.</span></span> <span data-ttu-id="485da-114">Den återspeglar den kollektiva säkerhetskonfigurationstillståndet för dina enheter i följande kategorier:</span><span class="sxs-lookup"><span data-stu-id="485da-114">It reflects the collective security configuration state of your devices across the following categories:</span></span>

- <span data-ttu-id="485da-115">Program</span><span class="sxs-lookup"><span data-stu-id="485da-115">Application</span></span>
- <span data-ttu-id="485da-116">Operativsystem</span><span class="sxs-lookup"><span data-stu-id="485da-116">Operating system</span></span>
- <span data-ttu-id="485da-117">Nätverk</span><span class="sxs-lookup"><span data-stu-id="485da-117">Network</span></span>
- <span data-ttu-id="485da-118">Konton</span><span class="sxs-lookup"><span data-stu-id="485da-118">Accounts</span></span>
- <span data-ttu-id="485da-119">Säkerhetskontroller</span><span class="sxs-lookup"><span data-stu-id="485da-119">Security controls</span></span>

<span data-ttu-id="485da-120">Välj en kategori för att gå till sidan [**Säkerhetsrekommendationer**](tvm-security-recommendation.md) och visa relevanta rekommendationer.</span><span class="sxs-lookup"><span data-stu-id="485da-120">Select a category to go to the [**Security recommendations**](tvm-security-recommendation.md) page and view the relevant recommendations.</span></span>

## <a name="turn-on-the-microsoft-secure-score-connector"></a><span data-ttu-id="485da-121">Aktivera Microsoft Secure Score-kopplingen</span><span class="sxs-lookup"><span data-stu-id="485da-121">Turn on the Microsoft Secure Score connector</span></span>

<span data-ttu-id="485da-122">Vidarebefordra Microsoft Defender för Endpoint-signaler och ge Microsoft Secure Score insyn i enhetssäkerhet.</span><span class="sxs-lookup"><span data-stu-id="485da-122">Forward Microsoft Defender for Endpoint signals, giving Microsoft Secure Score visibility into the device security posture.</span></span> <span data-ttu-id="485da-123">Vidarebefordrade data lagras och bearbetas på samma plats som dina Microsoft Secure Score-data.</span><span class="sxs-lookup"><span data-stu-id="485da-123">Forwarded data is stored and processed in the same location as your Microsoft Secure Score data.</span></span>

<span data-ttu-id="485da-124">Det kan ta några timmar innan ändringarna har återspeglas i instrumentpanelen.</span><span class="sxs-lookup"><span data-stu-id="485da-124">Changes might take up to a few hours to reflect in the dashboard.</span></span>

1. <span data-ttu-id="485da-125">I navigeringsfönstret går du till **Avancerade**  >  **inställningar**</span><span class="sxs-lookup"><span data-stu-id="485da-125">In the navigation pane, go to **Settings** > **Advanced features**</span></span> 

2. <span data-ttu-id="485da-126">Rulla ned till **Microsoft Secure Score** och ändra inställningen till **På**.</span><span class="sxs-lookup"><span data-stu-id="485da-126">Scroll down to **Microsoft Secure Score** and toggle the setting to **On**.</span></span>

3. <span data-ttu-id="485da-127">Välj **Spara inställningar**.</span><span class="sxs-lookup"><span data-stu-id="485da-127">Select **Save preferences**.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="485da-128">Så här fungerar det</span><span class="sxs-lookup"><span data-stu-id="485da-128">How it works</span></span>

>[!NOTE]
> <span data-ttu-id="485da-129">Microsoft Secure Score för enheter stöder för närvarande konfigurationer som har ställts in via Grupprincip.</span><span class="sxs-lookup"><span data-stu-id="485da-129">Microsoft Secure Score for Devices currently supports configurations set via Group Policy.</span></span> <span data-ttu-id="485da-130">På grund av det aktuella stödet för Intune kan konfigurationer som har konfigurerats via Intune visas som felkonfigurerade.</span><span class="sxs-lookup"><span data-stu-id="485da-130">Due to the current partial Intune support, configurations which might have been set through Intune might show up as misconfigured.</span></span> <span data-ttu-id="485da-131">Kontakta IT-administratören för att kontrollera den faktiska konfigurationsstatusen om din organisation använder Intune för säker konfigurationshantering.</span><span class="sxs-lookup"><span data-stu-id="485da-131">Contact your IT Administrator to verify the actual configuration status in case your organization is using Intune for secure configuration management.</span></span>

<span data-ttu-id="485da-132">Data i kortet Microsoft Secure Score för enheter är produkten av noggrann och pågående sårbarhetsidentifieringsprocess.</span><span class="sxs-lookup"><span data-stu-id="485da-132">The data in the Microsoft Secure Score for Devices card is the product of meticulous and ongoing vulnerability discovery process.</span></span> <span data-ttu-id="485da-133">Den sammanställs med kontinuerliga konfigurationsidentifieringsutvärderingar:</span><span class="sxs-lookup"><span data-stu-id="485da-133">It is aggregated with configuration discovery assessments that continuously:</span></span>

- <span data-ttu-id="485da-134">Jämför insamlade konfigurationer med insamlade riktmärken för att upptäcka felkonfigurerade tillgångar</span><span class="sxs-lookup"><span data-stu-id="485da-134">Compare collected configurations to the collected benchmarks to discover misconfigured assets</span></span>
- <span data-ttu-id="485da-135">Mappa konfigurationer till säkerhetsproblem som kan åtgärdas eller delvis åtgärdas (riskminskning)</span><span class="sxs-lookup"><span data-stu-id="485da-135">Map configurations to vulnerabilities that can be remediated or partially remediated (risk reduction)</span></span>
- <span data-ttu-id="485da-136">Samla in och underhålla bästa möjliga prestanda vid konfigurationer (leverantörer, säkerhetsflöden, interna forskningsteam)</span><span class="sxs-lookup"><span data-stu-id="485da-136">Collect and maintain best practice configuration benchmarks (vendors, security feeds, internal research teams)</span></span>
- <span data-ttu-id="485da-137">Samla in och övervaka ändringar av konfigurationstillståndet för säkerhetskontroller för alla tillgångar</span><span class="sxs-lookup"><span data-stu-id="485da-137">Collect and monitor changes of security control configuration state from all assets</span></span>

## <a name="improve-your-security-configuration"></a><span data-ttu-id="485da-138">Förbättra din säkerhetskonfiguration</span><span class="sxs-lookup"><span data-stu-id="485da-138">Improve your security configuration</span></span>

<span data-ttu-id="485da-139">Förbättra säkerhetskonfigurationen genom att åtgärda problem från listan med säkerhetsrekommendationer.</span><span class="sxs-lookup"><span data-stu-id="485da-139">Improve your security configuration by remediating issues from the security recommendations list.</span></span> <span data-ttu-id="485da-140">Samtidigt som du gör det förbättras ditt Microsoft Secure Score för enheter och din organisation blir mer flexibel mot hot och säkerhetsproblem mot cybersäkerhet.</span><span class="sxs-lookup"><span data-stu-id="485da-140">As you do so, your Microsoft Secure Score for Devices improves and your organization becomes more resilient against cybersecurity threats and vulnerabilities.</span></span>

1. <span data-ttu-id="485da-141">Från kortet Microsoft Secure Score för enheter med instrumentpanelen för hot och sårbarhetshantering väljer du en av kategorierna.</span><span class="sxs-lookup"><span data-stu-id="485da-141">From the Microsoft Secure Score for Devices card in the threat and vulnerability management dashboard, select the one of the categories.</span></span> <span data-ttu-id="485da-142">Du ser en lista med rekommendationer för den kategorin.</span><span class="sxs-lookup"><span data-stu-id="485da-142">You'll view the list of recommendations related to that category.</span></span> <span data-ttu-id="485da-143">Du kommer då till sidan [**Säkerhetsrekommendationer.**](tvm-security-recommendation.md)</span><span class="sxs-lookup"><span data-stu-id="485da-143">It will take you to the [**Security recommendations**](tvm-security-recommendation.md) page.</span></span> <span data-ttu-id="485da-144">Om du vill se alla säkerhetsrekommendationer rensar du sökfältet när du kommer till sidan Säkerhetsrekommendationer.</span><span class="sxs-lookup"><span data-stu-id="485da-144">If you want to see all security recommendations, once you get to the Security recommendations page, clear the search field.</span></span>

2. <span data-ttu-id="485da-145">Markera ett objekt i listan.</span><span class="sxs-lookup"><span data-stu-id="485da-145">Select an item on the list.</span></span> <span data-ttu-id="485da-146">Den utfällna panelen öppnas med information om rekommendationen.</span><span class="sxs-lookup"><span data-stu-id="485da-146">The flyout panel will open with details related to the recommendation.</span></span> <span data-ttu-id="485da-147">Välj **Alternativ för åtgärder.**</span><span class="sxs-lookup"><span data-stu-id="485da-147">Select **Remediation options**.</span></span>

   ![Säkerhetskontroller relaterade rekommendationer om säkerhet](images/tvm_security_controls.png)

3. <span data-ttu-id="485da-149">Läs beskrivningen för att förstå kontexten för problemet och vad du ska göra härnäst.</span><span class="sxs-lookup"><span data-stu-id="485da-149">Read the description to understand the context of the issue and what to do next.</span></span> <span data-ttu-id="485da-150">Välj ett förfallodatum, lägg till anteckningar och välj Exportera alla åtgärdsaktivitetsdata i **CSV** så att du kan bifoga dem i ett e-postmeddelande för uppföljning.</span><span class="sxs-lookup"><span data-stu-id="485da-150">Select a due date, add notes, and select **Export all remediation activity data to CSV** so you can attach it to an email for follow-up.</span></span>

4. <span data-ttu-id="485da-151">**Skicka begäran**.</span><span class="sxs-lookup"><span data-stu-id="485da-151">**Submit request**.</span></span> <span data-ttu-id="485da-152">Ett bekräftelsemeddelande visas om att åtgärden har skapats.</span><span class="sxs-lookup"><span data-stu-id="485da-152">You'll see a confirmation message that the remediation task has been created.</span></span>
   <span data-ttu-id="485da-153">![Bekräftelse för att åtgärd har skapats](images/tvm_remediation_task_created.png)</span><span class="sxs-lookup"><span data-stu-id="485da-153">![Remediation task creation confirmation](images/tvm_remediation_task_created.png)</span></span>

5. <span data-ttu-id="485da-154">Spara CSV-filen.</span><span class="sxs-lookup"><span data-stu-id="485da-154">Save your CSV file.</span></span>
   <span data-ttu-id="485da-155">![Spara CSV-fil](images/tvm_save_csv_file.png)</span><span class="sxs-lookup"><span data-stu-id="485da-155">![Save csv file](images/tvm_save_csv_file.png)</span></span>

6. <span data-ttu-id="485da-156">Skicka ett uppföljande e-postmeddelande till IT-administratören och tillåt den tid som du har tilldelats för åtgärd för att spridas i systemet.</span><span class="sxs-lookup"><span data-stu-id="485da-156">Send a follow-up email to your IT Administrator and allow the time that you've allotted for the remediation to propagate in the system.</span></span>

7. <span data-ttu-id="485da-157">Gå tillbaka **till kortet Microsoft Secure Score för enheter** på instrumentpanelen.</span><span class="sxs-lookup"><span data-stu-id="485da-157">Review the **Microsoft Secure Score for Devices** card again on the dashboard.</span></span> <span data-ttu-id="485da-158">Antalet rekommendationer om säkerhetskontroller kommer att minska.</span><span class="sxs-lookup"><span data-stu-id="485da-158">The number of security controls recommendations will decrease.</span></span> <span data-ttu-id="485da-159">När du **väljer Säkerhetskontroller** för  att gå tillbaka till sidan Säkerhetsrekommendationer visas inte objektet som du har adresserat längre.</span><span class="sxs-lookup"><span data-stu-id="485da-159">When you select **Security controls** to go back to the **Security recommendations** page, the item that you've addressed won't be listed there anymore.</span></span> <span data-ttu-id="485da-160">Ditt Microsoft Secure Score för enheter bör öka.</span><span class="sxs-lookup"><span data-stu-id="485da-160">Your Microsoft Secure Score for Devices should increase.</span></span>

>[!IMPORTANT]
><span data-ttu-id="485da-161">Du kan förbättra utvärderingsfrekvensen för sårbarhet genom att ladda ned följande obligatoriska säkerhetsuppdateringar och distribuera dem i nätverket:</span><span class="sxs-lookup"><span data-stu-id="485da-161">To boost your vulnerability assessment detection rates, download the following mandatory security updates and deploy them in your network:</span></span>
>- <span data-ttu-id="485da-162">19H1-kunder | [KB 4512941](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)</span><span class="sxs-lookup"><span data-stu-id="485da-162">19H1 customers | [KB 4512941](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)</span></span>
>- <span data-ttu-id="485da-163">RS5 customers | [KB 4516077](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)</span><span class="sxs-lookup"><span data-stu-id="485da-163">RS5 customers | [KB 4516077](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)</span></span>
>- <span data-ttu-id="485da-164">RS4 customers | [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)</span><span class="sxs-lookup"><span data-stu-id="485da-164">RS4 customers | [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)</span></span>
>- <span data-ttu-id="485da-165">RS3-| [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)</span><span class="sxs-lookup"><span data-stu-id="485da-165">RS3 customers | [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)</span></span>
>
><span data-ttu-id="485da-166">Så här laddar du ned säkerhetsuppdateringarna:</span><span class="sxs-lookup"><span data-stu-id="485da-166">To download the security updates:</span></span>
>1. <span data-ttu-id="485da-167">Gå till [Microsoft Update-katalogen.](https://www.catalog.update.microsoft.com/home.aspx)</span><span class="sxs-lookup"><span data-stu-id="485da-167">Go to [Microsoft Update Catalog](https://www.catalog.update.microsoft.com/home.aspx).</span></span>
>2. <span data-ttu-id="485da-168">Key-in the security update KB number that you need to download, then click **Search**.</span><span class="sxs-lookup"><span data-stu-id="485da-168">Key-in the security update KB number that you need to download, then click **Search**.</span></span>  

## <a name="related-topics"></a><span data-ttu-id="485da-169">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="485da-169">Related topics</span></span>

- [<span data-ttu-id="485da-170">Översikt över hot- och sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="485da-170">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="485da-171">Instrumentpanelen</span><span class="sxs-lookup"><span data-stu-id="485da-171">Dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="485da-172">Exponeringsvärde</span><span class="sxs-lookup"><span data-stu-id="485da-172">Exposure score</span></span>](tvm-exposure-score.md)
- [<span data-ttu-id="485da-173">Säkerhetsrekommendationer</span><span class="sxs-lookup"><span data-stu-id="485da-173">Security recommendations</span></span>](tvm-security-recommendation.md)
