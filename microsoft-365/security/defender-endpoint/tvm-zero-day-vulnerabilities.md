---
title: Minimera svagheter utan dag – Hantering av hot och säkerhetsrisker
description: Lär dig hur du kan hitta och minimera svagheter under nolldagar i din miljö Hantering av hot och säkerhetsrisker.
keywords: Microsoft Defender för slutpunkt tvm noll dagars säkerhetsproblem, tvm, hot & hantering av säkerhetsrisker, noll dag, 0-dagars, minimera 0 dagars säkerhetsproblem, sårbar CVE
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ec8dd97a563edc487008d028a7cdc9f6ef3d17c1
ms.sourcegitcommit: 82a4d74020cd93ba444006317cfecc178c6d41dc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689091"
---
# <a name="mitigate-zero-day-vulnerabilities---threat-and-vulnerability-management"></a><span data-ttu-id="6b359-104">Minimera svagheter utan dag – Hantering av hot och säkerhetsrisker</span><span class="sxs-lookup"><span data-stu-id="6b359-104">Mitigate zero-day vulnerabilities - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6b359-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="6b359-105">**Applies to:**</span></span>

- [<span data-ttu-id="6b359-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="6b359-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="6b359-107">Hot och hantering av säkerhetsrisker</span><span class="sxs-lookup"><span data-stu-id="6b359-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="6b359-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6b359-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="6b359-109">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="6b359-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6b359-110">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="6b359-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="6b359-111">Ett nolldagarshål är ett offentligt avslöjat säkerhetshål där inga officiella korrigeringar eller säkerhetsuppdateringar har släppts.</span><span class="sxs-lookup"><span data-stu-id="6b359-111">A zero-day vulnerability is a publicly disclosed vulnerability for which no official patches or security updates have been released.</span></span> <span data-ttu-id="6b359-112">Nolldagarsbrister har ofta hög allvarlighetsnivå och utnyttjas aktivt.</span><span class="sxs-lookup"><span data-stu-id="6b359-112">Zero-day vulnerabilities often have high severity levels and are actively exploited.</span></span>

<span data-ttu-id="6b359-113">Hot och hantering av säkerhetsrisker bara visar svagheter som inte har någon dag.</span><span class="sxs-lookup"><span data-stu-id="6b359-113">Threat and vulnerability management will only display zero-day vulnerabilities it has information about.</span></span>

## <a name="find-information-about-zero-day-vulnerabilities"></a><span data-ttu-id="6b359-114">Hitta information om svagheter utan dag</span><span class="sxs-lookup"><span data-stu-id="6b359-114">Find information about zero-day vulnerabilities</span></span>

<span data-ttu-id="6b359-115">När en nolldagarsrisk har hittats kommer information om den att förmedlas genom följande upplevelser i Microsoft Defender Säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="6b359-115">Once a zero-day vulnerability has been found, information about it will be conveyed through the following experiences in the Microsoft Defender Security Center.</span></span>

>[!NOTE]
> <span data-ttu-id="6b359-116">0-dagars sårbarhet är för närvarande endast tillgängligt för Windows produkter.</span><span class="sxs-lookup"><span data-stu-id="6b359-116">0-day vulnerability capability is currently available only for Windows products.</span></span>

### <a name="threat-and-vulnerability-management-dashboard"></a><span data-ttu-id="6b359-117">Hot och hantering av säkerhetsrisker instrumentpanel</span><span class="sxs-lookup"><span data-stu-id="6b359-117">Threat and vulnerability management dashboard</span></span>

<span data-ttu-id="6b359-118">Leta efter rekommendationer med en nolldagarstagg i kortet "Bästa säkerhetsrekommendationer".</span><span class="sxs-lookup"><span data-stu-id="6b359-118">Look for recommendations with a zero-day tag in the “Top security recommendations” card.</span></span>

![Bästa rekommendationerna med en nolldagarstagg.](images/tvm-zero-day-top-security-recommendations.png)

<span data-ttu-id="6b359-120">Hitta den bästa programvaran med nolldagarstaggen på kortet "Mest sårbar programvara".</span><span class="sxs-lookup"><span data-stu-id="6b359-120">Find top software with the zero-day tag in the "Top vulnerable software" card.</span></span>

![Mest sårbar programvara med en nolldagarstagg.](images/tvm-zero-day-top-software.png)

### <a name="weaknesses-page"></a><span data-ttu-id="6b359-122">Sida för svagheter</span><span class="sxs-lookup"><span data-stu-id="6b359-122">Weaknesses page</span></span>

<span data-ttu-id="6b359-123">Leta efter det namngivna nolldagarsproblemet tillsammans med en beskrivning och information.</span><span class="sxs-lookup"><span data-stu-id="6b359-123">Look for the named zero-day vulnerability along with a description and details.</span></span>

- <span data-ttu-id="6b359-124">Om problemet har ett CVE-ID tilldelat ser du nolldagarsetiketten bredvid CVE-namnet.</span><span class="sxs-lookup"><span data-stu-id="6b359-124">If this vulnerability has a CVE-ID assigned, you’ll see the zero-day label next to the CVE name.</span></span>

- <span data-ttu-id="6b359-125">Om det här problemet inte har något CVE-ID tilldelat hittar du det under ett internt, tillfälligt namn som ser ut som "TVM-XXXX-XXXX".</span><span class="sxs-lookup"><span data-stu-id="6b359-125">If this vulnerability has no CVE-ID assigned, you'll find it under an internal, temporary name that looks like “TVM-XXXX-XXXX”.</span></span> <span data-ttu-id="6b359-126">Namnet uppdateras när en officiell CVE-ID har tilldelats, men det tidigare interna namnet är fortfarande sökbart och finns i sidopanelen.</span><span class="sxs-lookup"><span data-stu-id="6b359-126">The name will be updated once an official CVE-ID has been assigned, but the previous internal name will still be searchable and found in the side-panel.</span></span>

![Exempel på nolldag för CVE-2020-17087 i svagheter.](images/tvm-zero-day-weakness-name.png)

### <a name="software-inventory-page"></a><span data-ttu-id="6b359-128">Sidan För programvaruinventering</span><span class="sxs-lookup"><span data-stu-id="6b359-128">Software inventory page</span></span>

<span data-ttu-id="6b359-129">Leta efter programvara med nolldagarstaggen.</span><span class="sxs-lookup"><span data-stu-id="6b359-129">Look for software with the zero-day tag.</span></span> <span data-ttu-id="6b359-130">Filtrera efter "nolldagars"-taggen för att endast se säkerhetsproblem med programvara utan dag.</span><span class="sxs-lookup"><span data-stu-id="6b359-130">Filter by the "zero day" tag to only see software with zero-day vulnerabilities.</span></span>

![Noll dagars exempel på Windows Server 2016 visas på sidan för programvaruinventering.](images/tvm-zero-day-software-inventory.png)

### <a name="software-page"></a><span data-ttu-id="6b359-132">Sidan Programvara</span><span class="sxs-lookup"><span data-stu-id="6b359-132">Software page</span></span>

<span data-ttu-id="6b359-133">Leta efter en nolldagarstagg för varje programvara som har påverkats av den nolldagars sårbarheten.</span><span class="sxs-lookup"><span data-stu-id="6b359-133">Look for a zero-day tag for each software that has been affected by the zero–day vulnerability.</span></span>

![Exempel på nolldag för Windows Server 2016 programvara.](images/tvm-zero-day-software-page.png)

### <a name="security-recommendations-page"></a><span data-ttu-id="6b359-135">Sidan Säkerhetsrekommendationer</span><span class="sxs-lookup"><span data-stu-id="6b359-135">Security recommendations page</span></span>

<span data-ttu-id="6b359-136">Visa tydliga förslag om åtgärder och åtgärder, inklusive lösningar om de finns.</span><span class="sxs-lookup"><span data-stu-id="6b359-136">View clear suggestions about remediation and mitigation options, including workarounds if they exist.</span></span> <span data-ttu-id="6b359-137">Filtrera efter "nolldagars"-taggen för att endast se säkerhetsrekommendationer om svagheter utan dag.</span><span class="sxs-lookup"><span data-stu-id="6b359-137">Filter by the "zero day" tag to only see security recommendations addressing zero-day vulnerabilities.</span></span>

<span data-ttu-id="6b359-138">Om det finns programvara med ett nolldagars sårbarhet och ytterligare säkerhetsproblem att ta itu med får du en rekommendation om alla säkerhetsproblem.</span><span class="sxs-lookup"><span data-stu-id="6b359-138">If there's software with a zero-day vulnerability and additional vulnerabilities to address, you'll get one recommendation about all vulnerabilities.</span></span>

![Nolldagarsexempel för Windows Server 2016 på sidan med säkerhetsrekommendationer.](images/tvm-zero-day-security-recommendation.png)

## <a name="addressing-zero-day-vulnerabilities"></a><span data-ttu-id="6b359-140">Åtgärda svagheter utan dag</span><span class="sxs-lookup"><span data-stu-id="6b359-140">Addressing zero-day vulnerabilities</span></span>

<span data-ttu-id="6b359-141">Gå till sidan med säkerhetsrekommendationer och välj en rekommendation om en nolldag.</span><span class="sxs-lookup"><span data-stu-id="6b359-141">Go to the security recommendation page and select a recommendation with a zero-day.</span></span> <span data-ttu-id="6b359-142">En utfällbarhet öppnas med information om nolldagar och andra säkerhetsproblem för programvaran.</span><span class="sxs-lookup"><span data-stu-id="6b359-142">A flyout will open with information about the zero-day and other vulnerabilities for that software.</span></span>

<span data-ttu-id="6b359-143">Om det finns en länk till åtgärder och lösningar finns det en länk.</span><span class="sxs-lookup"><span data-stu-id="6b359-143">There will be a link to mitigation options and workarounds if they are available.</span></span> <span data-ttu-id="6b359-144">Lösningar kan minska risken som kan uppstå med den här nolldagarsproblemet tills en korrigering eller säkerhetsuppdatering kan distribueras.</span><span class="sxs-lookup"><span data-stu-id="6b359-144">Workarounds may help reduce the risk posed by this zero-day vulnerability until a patch or security update can be deployed.</span></span>

<span data-ttu-id="6b359-145">Öppna alternativ för åtgärder och välj åtgärdstyp.</span><span class="sxs-lookup"><span data-stu-id="6b359-145">Open remediation options and choose the attention type.</span></span> <span data-ttu-id="6b359-146">Åtgärdsalternativet "åtgärd krävs" rekommenderas för säkerhetsproblem med nolldagar, eftersom ingen uppdatering har släppts än.</span><span class="sxs-lookup"><span data-stu-id="6b359-146">An "attention required" remediation option is recommended for the zero-day vulnerabilities, since an update hasn't been released yet.</span></span> <span data-ttu-id="6b359-147">Du kan inte välja ett förfallodatum eftersom det inte finns någon specifik åtgärd att utföra.</span><span class="sxs-lookup"><span data-stu-id="6b359-147">You won't be able to select a due date, since there's no specific action to perform.</span></span> <span data-ttu-id="6b359-148">Om det finns äldre säkerhetsproblem för den här programvaran som du vill åtgärda kan du åsidosätta alternativet "åtgärd som krävs" och välja "uppdatera".</span><span class="sxs-lookup"><span data-stu-id="6b359-148">If there are older vulnerabilities for this software you wish to remediation, you can override the "attention required" remediation option and choose “update.”</span></span>

![Utfällfingrigt nolldag Windows Server 2016 på sidan med säkerhetsrekommendationer.](images/tvm-zero-day-recommendation-flyout400.png)

## <a name="track-zero-day-remediation-activities"></a><span data-ttu-id="6b359-150">Spåra aktiviteter för nolldagarsreparation</span><span class="sxs-lookup"><span data-stu-id="6b359-150">Track zero-day remediation activities</span></span>

<span data-ttu-id="6b359-151">Gå till Hantering av hot och säkerhetsrisker [åtgärdssidan](tvm-remediation.md) för att visa objektet för åtgärdsaktiviteten.</span><span class="sxs-lookup"><span data-stu-id="6b359-151">Go to the threat and vulnerability management [Remediation](tvm-remediation.md) page to view the remediation activity item.</span></span> <span data-ttu-id="6b359-152">Om du väljer åtgärdsalternativet "åtgärd krävs" finns det ingen förloppsstapel, status för biljett eller förfallodatum eftersom det inte finns någon verklig åtgärd vi kan övervaka.</span><span class="sxs-lookup"><span data-stu-id="6b359-152">If you chose the "attention required" remediation option, there will be no progress bar, ticket status, or due date since there's no actual action we can monitor.</span></span> <span data-ttu-id="6b359-153">Du kan filtrera efter åtgärdstyp, till exempel "programuppdatering" eller "åtgärd krävs", för att se alla aktivitetsobjekt i samma kategori.</span><span class="sxs-lookup"><span data-stu-id="6b359-153">You can filter by remediation type, such as "software update" or "attention required," to see all activity items in the same category.</span></span>

## <a name="patching-zero-day-vulnerabilities"></a><span data-ttu-id="6b359-154">Korrigera säkerhetsproblem med nolldagar</span><span class="sxs-lookup"><span data-stu-id="6b359-154">Patching zero-day vulnerabilities</span></span>

<span data-ttu-id="6b359-155">När en korrigering släpps för nolldagen ändras rekommendationen till "Uppdatering" och en blå etikett bredvid den där det står "Ny säkerhetsuppdatering för noll dag".</span><span class="sxs-lookup"><span data-stu-id="6b359-155">When a patch is released for the zero-day, the recommendation will be changed to “Update” and a blue label next to it that says “New security update for zero day.”</span></span> <span data-ttu-id="6b359-156">Den kommer inte längre att ses som en nolldag, nolldagarstaggen tas bort från alla sidor.</span><span class="sxs-lookup"><span data-stu-id="6b359-156">It will no longer consider as a zero-day, the zero-day tag will be removed from all pages.</span></span>

![Rekommendation för "Uppdatera Microsoft Windows 10" med ny korrigeringsetikett.](images/tvm-zero-day-patch.jpg)

## <a name="related-articles"></a><span data-ttu-id="6b359-158">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="6b359-158">Related articles</span></span>

- [<span data-ttu-id="6b359-159">Översikt över hantering av säkerhetsrisker hot och hot</span><span class="sxs-lookup"><span data-stu-id="6b359-159">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="6b359-160">Instrumentpanelen</span><span class="sxs-lookup"><span data-stu-id="6b359-160">Dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="6b359-161">Säkerhetsrekommendationer</span><span class="sxs-lookup"><span data-stu-id="6b359-161">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="6b359-162">Programvaruinventering</span><span class="sxs-lookup"><span data-stu-id="6b359-162">Software inventory</span></span>](tvm-software-inventory.md)
- [<span data-ttu-id="6b359-163">Sårbarhet i min organisation</span><span class="sxs-lookup"><span data-stu-id="6b359-163">Vulnerabilities in my organization</span></span>](tvm-weaknesses.md)
