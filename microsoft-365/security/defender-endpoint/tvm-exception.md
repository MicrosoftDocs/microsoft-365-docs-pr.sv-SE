---
title: Skapa och visa undantag för säkerhetsrekommendationer – hantering av hot och sårbarhet
description: Skapa och övervaka undantag för säkerhetsrekommendationer i hantering av hot och sårbarhet.
keywords: microsoft defender atp tvm remediation, mdatp tvm, threat and vulnerability management, threat & vulnerability management, threat & vulnerability management remediation, tvm remediation intune, tvm remediation sccm
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: c8ad69930ce4faecbffbc6d2fab59bbe2cac06fa
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071802"
---
# <a name="create-and-view-exceptions-for-security-recommendations---threat-and-vulnerability-management"></a><span data-ttu-id="cbdaa-104">Skapa och visa undantag för säkerhetsrekommendationer – hantering av hot och sårbarhet</span><span class="sxs-lookup"><span data-stu-id="cbdaa-104">Create and view exceptions for security recommendations - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="cbdaa-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="cbdaa-105">**Applies to:**</span></span>

- [<span data-ttu-id="cbdaa-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="cbdaa-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="cbdaa-107">Hantering av hot och sårbarhet</span><span class="sxs-lookup"><span data-stu-id="cbdaa-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="cbdaa-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cbdaa-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="cbdaa-109">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="cbdaa-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="cbdaa-110">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="cbdaa-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="cbdaa-111">Som ett alternativ till en begäran om åtgärd när en rekommendation inte är relevant för tillfället kan du skapa undantag för rekommendationer.</span><span class="sxs-lookup"><span data-stu-id="cbdaa-111">As an alternative to a remediation request when a recommendation is not relevant at the moment, you can create exceptions for recommendations.</span></span> <span data-ttu-id="cbdaa-112">Om din organisation har enhetsgrupper kan du begränsa undantaget till specifika enhetsgrupper.</span><span class="sxs-lookup"><span data-stu-id="cbdaa-112">If your organization has device groups, you will be able to scope the exception to specific device groups.</span></span> <span data-ttu-id="cbdaa-113">Undantag kan antingen skapas för valda enhetsgrupper eller för alla enhetsgrupper som är tidigare och finns.</span><span class="sxs-lookup"><span data-stu-id="cbdaa-113">Exceptions can either be created for selected device groups, or for all device groups past and present.</span></span>  

<span data-ttu-id="cbdaa-114">När ett undantag skapas för en rekommendation är rekommendationen inte aktiv förrän undantagets varaktighet är slut.</span><span class="sxs-lookup"><span data-stu-id="cbdaa-114">When an exception is created for a recommendation, the recommendation will not be active until the end of the exception duration.</span></span> <span data-ttu-id="cbdaa-115">Rekommendationstillståndet ändras till **Fullständigt undantag eller** Delvis **undantag** (efter enhetsgrupp).</span><span class="sxs-lookup"><span data-stu-id="cbdaa-115">The recommendation state will change to **Full exception** or **Partial exception** (by device group).</span></span>

## <a name="permissions"></a><span data-ttu-id="cbdaa-116">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="cbdaa-116">Permissions</span></span>

<span data-ttu-id="cbdaa-117">Endast användare med behörigheten "undantagshantering" kan hantera undantag (till exempel att skapa eller avbryta).</span><span class="sxs-lookup"><span data-stu-id="cbdaa-117">Only users with “exceptions handling” permissions can manage exceptions (including creating or canceling).</span></span> <span data-ttu-id="cbdaa-118">[Läs mer om RBAC-roller.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="cbdaa-118">[Learn more about RBAC roles](user-roles.md).</span></span>

![Vy över behörighet för undantagshantering.](images/tvm-exception-permissions.png)

## <a name="create-an-exception"></a><span data-ttu-id="cbdaa-120">Skapa ett undantag</span><span class="sxs-lookup"><span data-stu-id="cbdaa-120">Create an exception</span></span>

<span data-ttu-id="cbdaa-121">Välj en säkerhetsrekommendationer som du vill skapa ett undantag för och välj sedan **Alternativ för undantag** och fyll i formuläret.</span><span class="sxs-lookup"><span data-stu-id="cbdaa-121">Select a security recommendation you would like create an exception for, and then select **Exception options** and fill out the form.</span></span>  

![Visar var knappen för "undantagsalternativ" är platsen i en utfällsalternativ för säkerhetsrekommendationer.](images/tvm-exception-options.png)

### <a name="exception-by-device-group"></a><span data-ttu-id="cbdaa-123">Undantag efter enhetsgrupp</span><span class="sxs-lookup"><span data-stu-id="cbdaa-123">Exception by device group</span></span>

<span data-ttu-id="cbdaa-124">Använd undantaget för alla aktuella enhetsgrupper eller välj specifika enhetsgrupper.</span><span class="sxs-lookup"><span data-stu-id="cbdaa-124">Apply the exception to all current device groups or choose specific device groups.</span></span> <span data-ttu-id="cbdaa-125">Framtida enhetsgrupper inkluderas inte i undantaget.</span><span class="sxs-lookup"><span data-stu-id="cbdaa-125">Future device groups won't be included in the exception.</span></span> <span data-ttu-id="cbdaa-126">Enhetsgrupper som redan har ett undantag visas inte i listan.</span><span class="sxs-lookup"><span data-stu-id="cbdaa-126">Device groups that already have an exception will not be displayed in the list.</span></span> <span data-ttu-id="cbdaa-127">Om du bara väljer vissa enhetsgrupper ändras rekommendationstillståndet från "aktiv" till "delvis undantag".</span><span class="sxs-lookup"><span data-stu-id="cbdaa-127">If you only select certain device groups, the recommendation state will change from “active” to “partial exception.”</span></span> <span data-ttu-id="cbdaa-128">Statusen ändras till "fullständigt undantag" om du markerar alla enhetsgrupper.</span><span class="sxs-lookup"><span data-stu-id="cbdaa-128">The state will change to “full exception” if you select all the device groups.</span></span>

![Visar listrutan enhetsgrupp.](images/tvm-exception-device-group-500.png)

#### <a name="filtered-views"></a><span data-ttu-id="cbdaa-130">Filtrerade vyer</span><span class="sxs-lookup"><span data-stu-id="cbdaa-130">Filtered views</span></span>

<span data-ttu-id="cbdaa-131">Om du har filtrerat efter enhetsgrupp på någon av sidorna för hot och sårbarhetshantering visas bara de filtrerade enhetsgrupper som alternativ.</span><span class="sxs-lookup"><span data-stu-id="cbdaa-131">If you have filtered by device group on any of the threat and vulnerability management pages, only your filtered device groups will appear as options.</span></span>

<span data-ttu-id="cbdaa-132">Det här är knappen för att filtrera efter enhetsgrupp på någon av sidorna för hot och sårbarhetshantering:</span><span class="sxs-lookup"><span data-stu-id="cbdaa-132">This is the button to filter by device group on any of the threat and vulnerability management pages:</span></span> 

![Visar filter för valda enhetsgrupper.](images/tvm-selected-device-groups.png)

<span data-ttu-id="cbdaa-134">Undantagsvy med filtrerade enhetsgrupper:</span><span class="sxs-lookup"><span data-stu-id="cbdaa-134">Exception view with filtered device groups:</span></span>

![Visar listrutan Filtrerad enhetsgrupp.](images/tvm-exception-device-filter500.png)

#### <a name="large-number-of-device-groups"></a><span data-ttu-id="cbdaa-136">Stort antal enhetsgrupper</span><span class="sxs-lookup"><span data-stu-id="cbdaa-136">Large number of device groups</span></span>

<span data-ttu-id="cbdaa-137">Om din organisation har fler än 20 enhetsgrupper väljer **du Redigera** bredvid alternativet för filtrerad enhetsgrupp.</span><span class="sxs-lookup"><span data-stu-id="cbdaa-137">If your organization has more than 20 device groups, select **Edit** next to the filtered device group option.</span></span>

![Visar hur du redigerar ett stort antal grupper.](images/tvm-exception-edit-groups.png)

<span data-ttu-id="cbdaa-139">En utfälling visas där du kan söka efter och välja enhetsgrupper som du vill ta med.</span><span class="sxs-lookup"><span data-stu-id="cbdaa-139">A flyout will appear where you can search and choose device groups you want included.</span></span> <span data-ttu-id="cbdaa-140">Markera bockikonen under Sök för att markera/avmarkera alla.</span><span class="sxs-lookup"><span data-stu-id="cbdaa-140">Select the check mark icon below Search to check/uncheck all.</span></span>

![Visar den stora utfälloenheten för enhetsgrupp.](images/tvm-exception-device-group-flyout-400.png)

### <a name="global-exceptions"></a><span data-ttu-id="cbdaa-142">Globala undantag</span><span class="sxs-lookup"><span data-stu-id="cbdaa-142">Global exceptions</span></span>

<span data-ttu-id="cbdaa-143">Om du har global administratörsbehörighet (som kallas Microsoft Defender ATP-administratör) kan du skapa och avbryta ett globalt undantag.</span><span class="sxs-lookup"><span data-stu-id="cbdaa-143">If you have global administrator permissions (called Microsoft Defender ATP administrator), you will be able to create and cancel a global exception.</span></span> <span data-ttu-id="cbdaa-144">Det påverkar **alla** nuvarande och framtida enhetsgrupper i organisationen, och endast en användare med liknande behörighet skulle kunna ändra den.</span><span class="sxs-lookup"><span data-stu-id="cbdaa-144">It affects **all** current and future device groups in your organization, and only a user with similar permission would be able to change it.</span></span> <span data-ttu-id="cbdaa-145">Rekommendationstillståndet ändras från "aktiv" till "fullständigt undantag".</span><span class="sxs-lookup"><span data-stu-id="cbdaa-145">The recommendation state will change from “active” to “full exception.”</span></span>

![Visar alternativet globalt undantag.](images/tvm-exception-global.png)

<span data-ttu-id="cbdaa-147">Några saker att tänka på:</span><span class="sxs-lookup"><span data-stu-id="cbdaa-147">Some things to keep in mind:</span></span>

- <span data-ttu-id="cbdaa-148">Om en rekommendation ligger under globalt undantag inaktiveras de nyligen skapade undantagen för enhetsgrupper tills det globala undantaget har upphört att gälla eller avbrutits.</span><span class="sxs-lookup"><span data-stu-id="cbdaa-148">If a recommendation is under global exception, then newly created exceptions for device groups will be suspended until the global exception has expired or been cancelled.</span></span> <span data-ttu-id="cbdaa-149">Därefter börjar de nya enhetsgruppundantagen att gälla tills de upphör att gälla.</span><span class="sxs-lookup"><span data-stu-id="cbdaa-149">After that point, the new device group exceptions will go into effect until they expire.</span></span>
- <span data-ttu-id="cbdaa-150">Om en rekommendation redan har undantag för vissa enhetsgrupper och ett globalt undantag skapas inaktiveras enhetsgruppundantaget tills det upphör att gälla eller tills det globala undantaget avbryts innan det förfaller.</span><span class="sxs-lookup"><span data-stu-id="cbdaa-150">If a recommendation already has exceptions for specific device groups and a global exception is created, then the device group exception will be suspended until it expires or the global exception is cancelled before it expires.</span></span>

### <a name="justification"></a><span data-ttu-id="cbdaa-151">Justering</span><span class="sxs-lookup"><span data-stu-id="cbdaa-151">Justification</span></span>

<span data-ttu-id="cbdaa-152">Välj justeringen för det undantag du behöver spara i stället för att åtgärda den säkerhetsrekommendationer som gäller.</span><span class="sxs-lookup"><span data-stu-id="cbdaa-152">Select your justification for the exception you need to file instead of remediating the security recommendation in question.</span></span> <span data-ttu-id="cbdaa-153">Fyll i justeringskontexten och ange sedan varaktighet för undantaget.</span><span class="sxs-lookup"><span data-stu-id="cbdaa-153">Fill out the justification context, then set the exception duration.</span></span>

<span data-ttu-id="cbdaa-154">I följande lista visas detaljerad information om justeringarna bakom undantagsalternativen:</span><span class="sxs-lookup"><span data-stu-id="cbdaa-154">The following list details the justifications behind the exception options:</span></span>

- <span data-ttu-id="cbdaa-155">**Kontroll från tredje part** – en produkt eller programvara från tredje part som redan tar den här rekommendationen – Om du väljer den här justeringstypen sänks exponeringsresultatet och det säkra resultatet ökar eftersom risken minskar</span><span class="sxs-lookup"><span data-stu-id="cbdaa-155">**Third party control** - A third party product or software already addresses this recommendation       - Choosing this justification type will lower your exposure score and increase your secure score because your risk is reduced</span></span>
- <span data-ttu-id="cbdaa-156">**Alternativ minskning** – Ett internt verktyg behandlar redan den här rekommendationen – Om du väljer den här justeringstypen sänks exponeringsresultatet och det säkra resultatet ökar eftersom risken minskar</span><span class="sxs-lookup"><span data-stu-id="cbdaa-156">**Alternate mitigation** - An internal tool already addresses this recommendation       - Choosing this justification type will lower your exposure score and increase your secure score because your risk is reduced</span></span>
- <span data-ttu-id="cbdaa-157">**Accepterad** risk – Det kan vara en låg risk och/eller att implementera rekommendationen är för dyr</span><span class="sxs-lookup"><span data-stu-id="cbdaa-157">**Risk accepted** - Poses low risk and/or implementing the recommendation is too expensive</span></span>
- <span data-ttu-id="cbdaa-158">**Planerad åtgärd (respit) –** Redan planerat, men väntar på körning eller auktorisering</span><span class="sxs-lookup"><span data-stu-id="cbdaa-158">**Planned remediation (grace)** - Already planned but is awaiting execution or authorization</span></span>

## <a name="view-all-exceptions"></a><span data-ttu-id="cbdaa-159">Visa alla undantag</span><span class="sxs-lookup"><span data-stu-id="cbdaa-159">View all exceptions</span></span>

<span data-ttu-id="cbdaa-160">Gå till **fliken** Undantag **på sidan** Åtgärd.</span><span class="sxs-lookup"><span data-stu-id="cbdaa-160">Navigate to the **Exceptions** tab in the **Remediation** page.</span></span> <span data-ttu-id="cbdaa-161">Du kan filtrera efter justering, typ och status.</span><span class="sxs-lookup"><span data-stu-id="cbdaa-161">You can filter by justification, type, and status.</span></span>

 <span data-ttu-id="cbdaa-162">Välj ett undantag för att öppna en utfällblad med mer information.</span><span class="sxs-lookup"><span data-stu-id="cbdaa-162">Select an exception to open a flyout with more details.</span></span> <span data-ttu-id="cbdaa-163">Undantag per enhetsgrupp har en lista över alla enhetsgrupper som undantaget omfattar, som du kan exportera.</span><span class="sxs-lookup"><span data-stu-id="cbdaa-163">Exceptions per devices group will have a list of every device group the exception covers, which you can export.</span></span> <span data-ttu-id="cbdaa-164">Du kan också visa den relaterade rekommendationen eller avbryta undantaget.</span><span class="sxs-lookup"><span data-stu-id="cbdaa-164">You can also view the related recommendation or cancel the exception.</span></span>

![Visar fliken "Undantag" på sidan Åtgärd.](images/tvm-exception-view.png)

## <a name="how-to-cancel-an-exception"></a><span data-ttu-id="cbdaa-166">Avbryta ett undantag</span><span class="sxs-lookup"><span data-stu-id="cbdaa-166">How to cancel an exception</span></span>

<span data-ttu-id="cbdaa-167">Om du vill avbryta ett undantag går **du till** fliken Undantag **på sidan** Åtgärd.</span><span class="sxs-lookup"><span data-stu-id="cbdaa-167">To cancel an exception, navigate to the **Exceptions** tab in the **Remediation** page.</span></span> <span data-ttu-id="cbdaa-168">Markera undantaget.</span><span class="sxs-lookup"><span data-stu-id="cbdaa-168">Select the exception.</span></span>

<span data-ttu-id="cbdaa-169">Om du vill avbryta undantaget för alla enhetsgrupper eller för ett globalt undantag väljer du **knappen Avbryt undantag för alla enhetsgrupper.**</span><span class="sxs-lookup"><span data-stu-id="cbdaa-169">To cancel the exception for all device groups or for a global exception, select the **Cancel exception for all device groups** button.</span></span> <span data-ttu-id="cbdaa-170">Du kan bara avbryta undantag för enhetsgrupper som du har behörighet för.</span><span class="sxs-lookup"><span data-stu-id="cbdaa-170">You will only be able to cancel exceptions for device groups you have permissions for.</span></span>

![Knappen Avbryt.](images/tvm-exception-cancel.png)

### <a name="cancel-the-exception-for-a-specific-device-group"></a><span data-ttu-id="cbdaa-172">Avbryta undantaget för en viss enhetsgrupp</span><span class="sxs-lookup"><span data-stu-id="cbdaa-172">Cancel the exception for a specific device group</span></span>

<span data-ttu-id="cbdaa-173">Markera den specifika enhetsgruppen om du vill avbryta undantaget för den.</span><span class="sxs-lookup"><span data-stu-id="cbdaa-173">Select the specific device group to cancel the exception for it.</span></span> <span data-ttu-id="cbdaa-174">En utfälling visas för enhetsgruppen och du kan välja **Avbryt undantag**.</span><span class="sxs-lookup"><span data-stu-id="cbdaa-174">A flyout will appear for the device group, and you can select **Cancel exception**.</span></span>

![Visar hur du väljer en specifik enhetsgrupp.](images/tvm-exception-device-group-hover.png)

## <a name="view-impact-after-exceptions-are-applied"></a><span data-ttu-id="cbdaa-176">Visa påverkan efter att undantag har tillämpats</span><span class="sxs-lookup"><span data-stu-id="cbdaa-176">View impact after exceptions are applied</span></span>

<span data-ttu-id="cbdaa-177">På sidan Säkerhetsrekommendationer väljer du **Anpassa kolumner** och markerar kryssrutorna för exponerade enheter **(efter undantag)** **och Påverkan (efter undantag).**</span><span class="sxs-lookup"><span data-stu-id="cbdaa-177">In the Security Recommendations page, select **Customize columns** and check the boxes for **Exposed devices (after exceptions)** and **Impact (after exceptions)**.</span></span>

![Visar alternativ för anpassa kolumner.](images/tvm-after-exceptions.png)

<span data-ttu-id="cbdaa-179">I kolumnen exponerade enheter (efter undantag) visas återstående enheter som fortfarande exponeras för säkerhetsproblem när undantag tillämpas.</span><span class="sxs-lookup"><span data-stu-id="cbdaa-179">The exposed devices (after exceptions) column shows the remaining devices that are still exposed to vulnerabilities after exceptions are applied.</span></span> <span data-ttu-id="cbdaa-180">Justering av undantag som påverkar exponering inkluderar "kontroll från tredje part" och "alternativ minskning".</span><span class="sxs-lookup"><span data-stu-id="cbdaa-180">Exception justifications that affect the exposure include ‘third party control’ and ‘alternate mitigation’.</span></span> <span data-ttu-id="cbdaa-181">Andra justeringar minskar inte exponering av en enhet och de anses fortfarande vara exponerade.</span><span class="sxs-lookup"><span data-stu-id="cbdaa-181">Other justifications do not reduce the exposure of a device, and they are still considered exposed.</span></span>

<span data-ttu-id="cbdaa-182">Effekterna (efter undantag) visar återstående påverkan på exponeringsresultat eller säker poäng efter att undantag har tillämpats.</span><span class="sxs-lookup"><span data-stu-id="cbdaa-182">The impact (after exceptions) shows remaining impact to exposure score or secure score after exceptions are applied.</span></span> <span data-ttu-id="cbdaa-183">Justering av undantag som påverkar resultat är bland annat "kontroll från tredje part" och "alternativ minskning".</span><span class="sxs-lookup"><span data-stu-id="cbdaa-183">Exception justifications that affect the scores include ‘third party control’ and ‘alternate mitigation.’</span></span> <span data-ttu-id="cbdaa-184">Andra justeringar minskar inte exponeringen för en enhet och därför ändras inte exponeringsresultatet och det säkra resultatet.</span><span class="sxs-lookup"><span data-stu-id="cbdaa-184">Other justifications do not reduce the exposure of a device, and so the exposure score and secure score do not change.</span></span>

![Visar kolumnerna i tabellen.](images/tvm-after-exceptions-table.png)

## <a name="related-topics"></a><span data-ttu-id="cbdaa-186">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="cbdaa-186">Related topics</span></span>

- [<span data-ttu-id="cbdaa-187">Översikt över hot- och sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="cbdaa-187">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="cbdaa-188">Åtgärda säkerhetsproblem</span><span class="sxs-lookup"><span data-stu-id="cbdaa-188">Remediate vulnerabilities</span></span>](tvm-remediation.md)
- [<span data-ttu-id="cbdaa-189">Säkerhetsrekommendationer</span><span class="sxs-lookup"><span data-stu-id="cbdaa-189">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="cbdaa-190">Exponeringsresultat</span><span class="sxs-lookup"><span data-stu-id="cbdaa-190">Exposure score</span></span>](tvm-exposure-score.md)
- [<span data-ttu-id="cbdaa-191">Microsoft Secure Score för enheter</span><span class="sxs-lookup"><span data-stu-id="cbdaa-191">Microsoft Secure Score for Devices</span></span>](tvm-microsoft-secure-score-devices.md)
