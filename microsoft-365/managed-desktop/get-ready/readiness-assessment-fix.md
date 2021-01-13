---
title: Åtgärda problem som hittats av verktyget för bedömning av beredskap
description: Detaljerade åtgärder att vidta för varje problem som verktyget hittar
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: ada6bb8ef66e3414a375a151b45d4871e306e825
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841077"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a><span data-ttu-id="16aaa-104">Åtgärda problem som hittats av verktyget för bedömning av beredskap</span><span class="sxs-lookup"><span data-stu-id="16aaa-104">Fix issues found by the readiness assessment tool</span></span>

<span data-ttu-id="16aaa-105">För varje kontroll rapporteras ett av fyra möjliga resultat:</span><span class="sxs-lookup"><span data-stu-id="16aaa-105">For each check, the tool will report one of four possible results:</span></span>


|<span data-ttu-id="16aaa-106">Resultat</span><span class="sxs-lookup"><span data-stu-id="16aaa-106">Result</span></span>  |<span data-ttu-id="16aaa-107">Betydelse</span><span class="sxs-lookup"><span data-stu-id="16aaa-107">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="16aaa-108">Förbereder</span><span class="sxs-lookup"><span data-stu-id="16aaa-108">Ready</span></span>     | <span data-ttu-id="16aaa-109">Ingen åtgärd krävs innan du slutför registreringen.</span><span class="sxs-lookup"><span data-stu-id="16aaa-109">No action is required before completing enrollment.</span></span>        |
|<span data-ttu-id="16aaa-110">Rådgivare</span><span class="sxs-lookup"><span data-stu-id="16aaa-110">Advisory</span></span>    | <span data-ttu-id="16aaa-111">Följ stegen i verktyget eller den här artikeln för att få bästa möjliga upplevelse av registrering och användare.</span><span class="sxs-lookup"><span data-stu-id="16aaa-111">Follow the steps in the tool or this article for the best experience with enrollment and for users.</span></span> <span data-ttu-id="16aaa-112">Du *kan* slutföra registreringen, men du måste åtgärda dessa problem innan du distribuerar den första enheten.</span><span class="sxs-lookup"><span data-stu-id="16aaa-112">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="16aaa-113">Inte klart</span><span class="sxs-lookup"><span data-stu-id="16aaa-113">Not ready</span></span> | <span data-ttu-id="16aaa-114">*Registreringen Miss lyckas om du inte åtgärdar dessa problem.*</span><span class="sxs-lookup"><span data-stu-id="16aaa-114">*Enrollment will fail if you don't fix these issues.*</span></span> <span data-ttu-id="16aaa-115">Följ stegen i verktyget eller den här artikeln för att åtgärda dem.</span><span class="sxs-lookup"><span data-stu-id="16aaa-115">Follow the steps in the tool or this article to resolve them.</span></span>        |
|<span data-ttu-id="16aaa-116">Fel</span><span class="sxs-lookup"><span data-stu-id="16aaa-116">Error</span></span> | <span data-ttu-id="16aaa-117">Azure Active Director (AD)-rollen som du använder har inte tillräcklig behörighet för att köra den här kontrollen.</span><span class="sxs-lookup"><span data-stu-id="16aaa-117">The Azure Active Director (AD) role you're using doesn't have sufficient permission to run this check.</span></span> |

> [!NOTE]
> <span data-ttu-id="16aaa-118">Resultaten som rapporteras med det här verktyget visar endast statusen för dina inställningar vid den specifika tidpunkt då du körde det.</span><span class="sxs-lookup"><span data-stu-id="16aaa-118">The results reported by this tool reflect the status of your settings only at the specific point in time that you ran it.</span></span> <span data-ttu-id="16aaa-119">Om du senare ändrar principer i Microsoft Intune, Azure Active Directory eller Microsoft 365 kan objekt som "Ready" bli "inte klara".</span><span class="sxs-lookup"><span data-stu-id="16aaa-119">If you later make any changes to policies in Microsoft Intune, Azure Active Directory, or Microsoft 365, items that were "Ready" can become "Not ready."</span></span> <span data-ttu-id="16aaa-120">För att undvika problem med Microsoft Managed Station ära datorer kontrollerar du de specifika inställningar som beskrivs i den här artikeln innan du ändrar några principer.</span><span class="sxs-lookup"><span data-stu-id="16aaa-120">To avoid problems with Microsoft Managed Desktop operations, check the specific settings described in this article before you change any policies.</span></span>

## <a name="microsoft-intune-settings"></a><span data-ttu-id="16aaa-121">Microsoft Intune-inställningar</span><span class="sxs-lookup"><span data-stu-id="16aaa-121">Microsoft Intune settings</span></span>

<span data-ttu-id="16aaa-122">Du kan komma åt Intune-inställningar i [administrations centret](https://endpoint.microsoft.com)för Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="16aaa-122">You can access Intune settings at the Microsoft Endpoint Manager [admin center](https://endpoint.microsoft.com).</span></span>

### <a name="autopilot-deployment-profile"></a><span data-ttu-id="16aaa-123">Distributions profil för autopilot</span><span class="sxs-lookup"><span data-stu-id="16aaa-123">Autopilot deployment profile</span></span>

<span data-ttu-id="16aaa-124">Du bör inte ha några befintliga autopilot-profiler som riktar sig till tilldelade eller dynamiska grupper som används av Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="16aaa-124">You shouldn't have any existing Autopilot profiles that target assigned or dynamic groups used by Microsoft Managed Desktop.</span></span> <span data-ttu-id="16aaa-125">Microsoft Managed Desktop använder autopilot för att etablera nya enheter.</span><span class="sxs-lookup"><span data-stu-id="16aaa-125">Microsoft Managed Desktop uses Autopilot to provision new devices.</span></span>

<span data-ttu-id="16aaa-126">**Inte klart**</span><span class="sxs-lookup"><span data-stu-id="16aaa-126">**Not ready**</span></span>

<span data-ttu-id="16aaa-127">Du har en autopilot-profil som kopplats till alla enheter.</span><span class="sxs-lookup"><span data-stu-id="16aaa-127">You have an Autopilot profile that is assigned to all devices.</span></span> <span data-ttu-id="16aaa-128">Anvisningar finns i [registrera Windows-enheter i Intune med hjälp av Windows autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span><span class="sxs-lookup"><span data-stu-id="16aaa-128">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="16aaa-129">Efter Microsoft Managed Desktop-registrering ställer du in autopilot-principen så att den **moderna arbets ytan visas-alla** Azure AD-grupper.</span><span class="sxs-lookup"><span data-stu-id="16aaa-129">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>

<span data-ttu-id="16aaa-130">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="16aaa-130">**Advisory**</span></span>

<span data-ttu-id="16aaa-131">Se till att dina autopilot-profiler är riktade till en tilldelad eller dynamisk Azure AD-grupp som inte innehåller Microsoft Managed Station ära enheter som kommer att skapas vid registrering.</span><span class="sxs-lookup"><span data-stu-id="16aaa-131">Make sure that your Autopilot profiles target an assigned or dynamic Azure AD group that doesn't include Microsoft Managed Desktop devices that will be created at enrollment.</span></span> <span data-ttu-id="16aaa-132">Anvisningar finns i [registrera Windows-enheter i Intune med hjälp av Windows autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span><span class="sxs-lookup"><span data-stu-id="16aaa-132">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="16aaa-133">Efter Microsoft Managed Desktop-registrering ställer du in autopilot-principen så att den **moderna arbets ytan visas-alla** Azure AD-grupper.</span><span class="sxs-lookup"><span data-stu-id="16aaa-133">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>


### <a name="certificate-connectors"></a><span data-ttu-id="16aaa-134">Certifikat anslutningar</span><span class="sxs-lookup"><span data-stu-id="16aaa-134">Certificate connectors</span></span>

<span data-ttu-id="16aaa-135">Om du har några certifikat anslutningar som används av de enheter som du vill registrera på Microsoft Managed Desktop kan de inte ha några fel.</span><span class="sxs-lookup"><span data-stu-id="16aaa-135">If you have any certificate connectors used by the devices you want to enroll in Microsoft Managed Desktop, the connectors cannot have any errors.</span></span> <span data-ttu-id="16aaa-136">Endast en av följande rådgivare kommer att gälla för din situation, så kolla dem noggrant.</span><span class="sxs-lookup"><span data-stu-id="16aaa-136">Only one of the following advisories will apply to your situation, so check them carefully.</span></span>

<span data-ttu-id="16aaa-137">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="16aaa-137">**Advisory**</span></span>

<span data-ttu-id="16aaa-138">Det finns inga certifikat kopplingar.</span><span class="sxs-lookup"><span data-stu-id="16aaa-138">No certificate connectors are present.</span></span> <span data-ttu-id="16aaa-139">Det är möjligt att du inte behöver några kopplingar, men du bör utvärdera om du kan behöva vissa för nätverks anslutningen till Microsoft Managed Station ära datorer.</span><span class="sxs-lookup"><span data-stu-id="16aaa-139">It's possible you don't need any connectors, but you should evaluate whether you might need some for network connectivity to Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="16aaa-140">Mer information finns i [förbereda certifikat och nätverks profiler för Microsoft Managed Desktop](certs-wifi-lan.md).</span><span class="sxs-lookup"><span data-stu-id="16aaa-140">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

<span data-ttu-id="16aaa-141">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="16aaa-141">**Advisory**</span></span>

<span data-ttu-id="16aaa-142">Minst ett certifikat har ett fel.</span><span class="sxs-lookup"><span data-stu-id="16aaa-142">At least one certificate connector has an error.</span></span> <span data-ttu-id="16aaa-143">Om du behöver den här kopplingen för anslutning till Microsoft-hanterade Skriv bords enheter måste du lösa problemet.</span><span class="sxs-lookup"><span data-stu-id="16aaa-143">If you need this connector for connectivity to Microsoft Managed Desktop devices, you must resolve the error.</span></span> <span data-ttu-id="16aaa-144">Mer information finns i [förbereda certifikat och nätverks profiler för Microsoft Managed Desktop](certs-wifi-lan.md).</span><span class="sxs-lookup"><span data-stu-id="16aaa-144">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


<span data-ttu-id="16aaa-145">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="16aaa-145">**Advisory**</span></span>

<span data-ttu-id="16aaa-146">Du har minst en certifikatanslutningsappen och inga fel rapporteras.</span><span class="sxs-lookup"><span data-stu-id="16aaa-146">You have at least one certificate connector and no errors are reported.</span></span> <span data-ttu-id="16aaa-147">Men det kan hända att du måste skapa en profil för att återanvända Connector för Microsoft-hanterade Station ära datorer.</span><span class="sxs-lookup"><span data-stu-id="16aaa-147">However, you might need to create a profile to reuse the connector for Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="16aaa-148">Mer information finns i [förbereda certifikat och nätverks profiler för Microsoft Managed Desktop](certs-wifi-lan.md).</span><span class="sxs-lookup"><span data-stu-id="16aaa-148">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


### <a name="conditional-access-policies"></a><span data-ttu-id="16aaa-149">Principer för villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="16aaa-149">Conditional access policies</span></span>

<span data-ttu-id="16aaa-150">Principer för villkorsstyrd åtkomst i din Azure AD-organisation får inte vara riktade till Microsoft Manage Desktop-användare.</span><span class="sxs-lookup"><span data-stu-id="16aaa-150">Conditional access policies in your Azure AD organization must not target any Microsoft Manage Desktop users.</span></span>

<span data-ttu-id="16aaa-151">**Inte klart**</span><span class="sxs-lookup"><span data-stu-id="16aaa-151">**Not ready**</span></span>

<span data-ttu-id="16aaa-152">Du har minst en princip för villkorsstyrd åtkomst som är riktad till alla användare.</span><span class="sxs-lookup"><span data-stu-id="16aaa-152">You have at least one conditional access policy that targets all users.</span></span> <span data-ttu-id="16aaa-153">Återställ principen för en viss Azure AD-grupp som inte innehåller Azure AD-gruppen av Microsoft Managed Desktop Service-konton som kommer att skapas vid registrering.</span><span class="sxs-lookup"><span data-stu-id="16aaa-153">Reset the policy to target a specific Azure AD group that does not include the Azure AD group of Microsoft Managed Desktop service accounts that will be created at enrollment.</span></span> <span data-ttu-id="16aaa-154">Anvisningar finns i [villkorlig åtkomst: användare och grupper](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span><span class="sxs-lookup"><span data-stu-id="16aaa-154">For steps, see [Conditional Access: Users and groups](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span></span>

<span data-ttu-id="16aaa-155">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="16aaa-155">**Advisory**</span></span>

<span data-ttu-id="16aaa-156">Se till att alla principer för villkorsstyrd åtkomst du har exkluderar den **moderna arbets plats tjänstens konton** Azure AD-grupp.</span><span class="sxs-lookup"><span data-stu-id="16aaa-156">Make sure that any conditional access policies you have exclude the **Modern Workplace Service Accounts** Azure AD group.</span></span> <span data-ttu-id="16aaa-157">Anvisningar finns i [Justera villkorlig åtkomst](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access).</span><span class="sxs-lookup"><span data-stu-id="16aaa-157">For steps, see [Adjust conditional access](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access).</span></span> <span data-ttu-id="16aaa-158">Den **moderna arbets plats tjänsten** är en dynamisk grupp som vi skapar för tjänsten när du registrerar dig.</span><span class="sxs-lookup"><span data-stu-id="16aaa-158">The **Modern Workplace Service Accounts** Azure AD group is a dynamic group that we create for the service when you enroll.</span></span> <span data-ttu-id="16aaa-159">Du måste komma tillbaka för att utesluta den här gruppen efter registreringen.</span><span class="sxs-lookup"><span data-stu-id="16aaa-159">You'll have to come back to exclude this group after enrollment.</span></span> <span data-ttu-id="16aaa-160">Mer information om dessa tjänst konton finns i [vanliga rutiner](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span><span class="sxs-lookup"><span data-stu-id="16aaa-160">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="16aaa-161">**Fel**</span><span class="sxs-lookup"><span data-stu-id="16aaa-161">**Error**</span></span>

<span data-ttu-id="16aaa-162">Rollen Intune-administratör har inte tillräcklig behörighet för den här kontrollen.</span><span class="sxs-lookup"><span data-stu-id="16aaa-162">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="16aaa-163">Du behöver också några av de här Azure AD-rollerna för att köra den här kontrollen:</span><span class="sxs-lookup"><span data-stu-id="16aaa-163">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="16aaa-164">Säkerhets läsare</span><span class="sxs-lookup"><span data-stu-id="16aaa-164">Security Reader</span></span>
- <span data-ttu-id="16aaa-165">Säkerhets administratör</span><span class="sxs-lookup"><span data-stu-id="16aaa-165">Security Administrator</span></span>
- <span data-ttu-id="16aaa-166">Administratör för villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="16aaa-166">Conditional Access Administrator</span></span>
- <span data-ttu-id="16aaa-167">Global läsare</span><span class="sxs-lookup"><span data-stu-id="16aaa-167">Global Reader</span></span>
- <span data-ttu-id="16aaa-168">Enheter-administratör</span><span class="sxs-lookup"><span data-stu-id="16aaa-168">Devices Administrator</span></span>


### <a name="device-compliance-policies"></a><span data-ttu-id="16aaa-169">Principer för enhetskompatibilitet</span><span class="sxs-lookup"><span data-stu-id="16aaa-169">Device Compliance policies</span></span>

<span data-ttu-id="16aaa-170">Principer för hantering av efterlevnadsprinciper i din Azure AD-organisation får inte uppfylla alla hanterade Microsoft-användare.</span><span class="sxs-lookup"><span data-stu-id="16aaa-170">Intune Device Compliance policies in your Azure AD organization must not target any Microsoft Managed Desktop users.</span></span>

<span data-ttu-id="16aaa-171">**Inte klart**</span><span class="sxs-lookup"><span data-stu-id="16aaa-171">**Not ready**</span></span>

<span data-ttu-id="16aaa-172">Du har minst en efterlevnadsprincip som är riktad till alla användare.</span><span class="sxs-lookup"><span data-stu-id="16aaa-172">You have at least one compliance policy that targets all users.</span></span> <span data-ttu-id="16aaa-173">Återställ principen för en viss Azure AD-grupp som inte innehåller några hanterade Microsoft-användare.</span><span class="sxs-lookup"><span data-stu-id="16aaa-173">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="16aaa-174">Anvisningar finns i [skapa en policy för efterlevnad i Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span><span class="sxs-lookup"><span data-stu-id="16aaa-174">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>

<span data-ttu-id="16aaa-175">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="16aaa-175">**Advisory**</span></span>

<span data-ttu-id="16aaa-176">Se till att eventuella efterlevnadsprinciper som du inte har Microsoft-hanterade Skriv bords användare.</span><span class="sxs-lookup"><span data-stu-id="16aaa-176">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="16aaa-177">Anvisningar finns i [skapa en policy för efterlevnad i Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span><span class="sxs-lookup"><span data-stu-id="16aaa-177">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>



### <a name="device-configuration-policies"></a><span data-ttu-id="16aaa-178">Konfigurations principer för enheter</span><span class="sxs-lookup"><span data-stu-id="16aaa-178">Device Configuration policies</span></span>

<span data-ttu-id="16aaa-179">Konfigurations principer för Intune-enheter i din Azure AD-organisation får inte vara riktade till Microsoft Manage Station ära enheter eller användare.</span><span class="sxs-lookup"><span data-stu-id="16aaa-179">Intune Device Configuration policies in your Azure AD organization must not target any Microsoft Manage Desktop devices or users.</span></span>

<span data-ttu-id="16aaa-180">**Inte klart**</span><span class="sxs-lookup"><span data-stu-id="16aaa-180">**Not ready**</span></span>

<span data-ttu-id="16aaa-181">Du har minst en konfigurations princip som är riktad till alla användare, alla enheter eller både och.</span><span class="sxs-lookup"><span data-stu-id="16aaa-181">You have at least one configuration policy that targets all users, all devices, or both.</span></span> <span data-ttu-id="16aaa-182">Återställ principen för en viss Azure AD-grupp som inte innehåller några Microsoft-hanterade Skriv bords enheter.</span><span class="sxs-lookup"><span data-stu-id="16aaa-182">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="16aaa-183">Anvisningar finns i [skapa en policy för efterlevnad i Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span><span class="sxs-lookup"><span data-stu-id="16aaa-183">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>

<span data-ttu-id="16aaa-184">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="16aaa-184">**Advisory**</span></span>

<span data-ttu-id="16aaa-185">Se till att eventuella efterlevnadsprinciper som du inte har Microsoft-hanterade Skriv bords enheter eller-användare.</span><span class="sxs-lookup"><span data-stu-id="16aaa-185">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop devices or users.</span></span> <span data-ttu-id="16aaa-186">Anvisningar finns i [skapa en policy för efterlevnad i Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span><span class="sxs-lookup"><span data-stu-id="16aaa-186">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>



### <a name="device-type-restrictions"></a><span data-ttu-id="16aaa-187">Begränsningar för enhets typer</span><span class="sxs-lookup"><span data-stu-id="16aaa-187">Device type restrictions</span></span>

<span data-ttu-id="16aaa-188">Microsoft Managed Station ära datorer måste tillåtas att registrera i Intune.</span><span class="sxs-lookup"><span data-stu-id="16aaa-188">Microsoft Managed Desktop devices must be allowed to enroll in Intune.</span></span>

<span data-ttu-id="16aaa-189">**Inte klart**</span><span class="sxs-lookup"><span data-stu-id="16aaa-189">**Not ready**</span></span>

<span data-ttu-id="16aaa-190">Följ stegen i [Ange registrerings begränsningar](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) för att ändra inställningen till **Tillåt**.</span><span class="sxs-lookup"><span data-stu-id="16aaa-190">Follow the steps in [Set enrollment restrictions](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) to change the setting to **Allow**.</span></span>


### <a name="enrollment-status-page"></a><span data-ttu-id="16aaa-191">Sidan registrerings status</span><span class="sxs-lookup"><span data-stu-id="16aaa-191">Enrollment Status Page</span></span>

<span data-ttu-id="16aaa-192">Du har för närvarande sidan registrerings status (ESP) aktive rad.</span><span class="sxs-lookup"><span data-stu-id="16aaa-192">You currently have the Enrollment Status Page (ESP) enabled.</span></span> <span data-ttu-id="16aaa-193">Om du deltar i den offentliga för hands versionen av den här funktionen kan du ignorera det här objektet.</span><span class="sxs-lookup"><span data-stu-id="16aaa-193">If you are participating in the public preview of this feature, you can ignore this item.</span></span> <span data-ttu-id="16aaa-194">Mer information finns i förstagångskörningen [med autopilot och sidan registrerings status](../get-started/esp-first-run.md).</span><span class="sxs-lookup"><span data-stu-id="16aaa-194">For more information, see [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span></span>

<span data-ttu-id="16aaa-195">**Inte klart**</span><span class="sxs-lookup"><span data-stu-id="16aaa-195">**Not ready**</span></span>

<span data-ttu-id="16aaa-196">Du har aktiverat ESP-standardprofilen för att **Visa konfigurations förlopp för appar och profiler**.</span><span class="sxs-lookup"><span data-stu-id="16aaa-196">You have the ESP default profile set to **Show app and profile configuration progress**.</span></span> <span data-ttu-id="16aaa-197">Inaktivera den här inställningen eller se till att uppgifter till vilken Azure AD-grupp som helst inte innehåller Microsoft hanterade Skriv bords enheter genom att följa anvisningarna i [Konfigurera sidan registrerings status](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span><span class="sxs-lookup"><span data-stu-id="16aaa-197">Disable this setting or make sure that assignments to any Azure AD group do not include Microsoft Managed Desktop devices by following the steps in [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

<span data-ttu-id="16aaa-198">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="16aaa-198">**Advisory**</span></span>

<span data-ttu-id="16aaa-199">Kontrol lera att alla profiler som har **statusen Visa program-och profil konfiguration** inte är tilldelade någon Azure AD-grupp som innehåller Microsoft Managed Station ära enheter.</span><span class="sxs-lookup"><span data-stu-id="16aaa-199">Make sure that any profiles that have the **Show app and profile configuration progress** setting are not assigned to any Azure AD group that includes Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="16aaa-200">Mer information finns i [Konfigurera sidan registrerings status](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span><span class="sxs-lookup"><span data-stu-id="16aaa-200">For more information, see [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

### <a name="intune-enrollment"></a><span data-ttu-id="16aaa-201">Intune-registrering</span><span class="sxs-lookup"><span data-stu-id="16aaa-201">Intune enrollment</span></span>

<span data-ttu-id="16aaa-202">Windows 10-enheter i din Azure AD-organisation måste registreras automatiskt i Intune.</span><span class="sxs-lookup"><span data-stu-id="16aaa-202">Windows 10 devices in your Azure AD organization must be automatically enrolled in Intune.</span></span>

<span data-ttu-id="16aaa-203">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="16aaa-203">**Advisory**</span></span>

<span data-ttu-id="16aaa-204">Kontrol lera att webområdet för MDM är inställt på **vissa** eller **alla**, inte **inga**.</span><span class="sxs-lookup"><span data-stu-id="16aaa-204">Make sure the MDM User scope is set to **Some** or **All**, not **None**.</span></span> <span data-ttu-id="16aaa-205">Om du väljer **lite**, kom tillbaka efter registreringen och väljer den **moderna arbets platsen – alla** Azure AD-grupper för **grupper**.</span><span class="sxs-lookup"><span data-stu-id="16aaa-205">If you choose **Some**, come back after enrollment and select the **Modern Workplace -All** Azure AD group for **Groups**.</span></span>


### <a name="microsoft-store-for-business"></a><span data-ttu-id="16aaa-206">Microsoft Store för företag</span><span class="sxs-lookup"><span data-stu-id="16aaa-206">Microsoft Store for Business</span></span>

<span data-ttu-id="16aaa-207">Vi använder Microsoft Store för företag så att du kan ladda ned företags Portal för att distribuera vissa program, till exempel Microsoft Project och Microsoft Visio.</span><span class="sxs-lookup"><span data-stu-id="16aaa-207">We use Microsoft Store for Business so that you can download Company Portal to deploy some apps, such as Microsoft Project and Microsoft Visio.</span></span>

<span data-ttu-id="16aaa-208">**Inte klart**</span><span class="sxs-lookup"><span data-stu-id="16aaa-208">**Not ready**</span></span>

<span data-ttu-id="16aaa-209">Microsoft Store för företag är antingen inte aktiverat eller synkroniseras inte med Intune.</span><span class="sxs-lookup"><span data-stu-id="16aaa-209">Microsoft Store for Business either isn't enabled or isn't synced with Intune.</span></span> <span data-ttu-id="16aaa-210">Mer information finns i [så här hanterar du volym köps program från Microsoft Store för företag med Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) och [Installera Intune företags Portal på enheter](../get-started/company-portal.md).</span><span class="sxs-lookup"><span data-stu-id="16aaa-210">For more information, see [How to manage volume purchased apps from the Microsoft Store for Business with Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) and [Install Intune Company Portal on on devices](../get-started/company-portal.md).</span></span>

### <a name="multifactor-authentication"></a><span data-ttu-id="16aaa-211">Multifaktorautentisering</span><span class="sxs-lookup"><span data-stu-id="16aaa-211">Multifactor authentication</span></span>

<span data-ttu-id="16aaa-212">Multifaktorautentisering får inte oavsiktligt användas på Microsoft Managed Desktop Service-konton.</span><span class="sxs-lookup"><span data-stu-id="16aaa-212">Multifactor authentication must not accidentally be applied to Microsoft Managed Desktop service accounts.</span></span>


<span data-ttu-id="16aaa-213">**Inte klart**</span><span class="sxs-lookup"><span data-stu-id="16aaa-213">**Not ready**</span></span>

<span data-ttu-id="16aaa-214">Du har vissa principer för multifaktorautentisering (MFA) inställda som "obligatoriskt" för principer för villkorsstyrd åtkomst som är tilldelade till alla användare.</span><span class="sxs-lookup"><span data-stu-id="16aaa-214">You have some multifactor authentication (MFA) policies set as "required" for conditional access policies that are assigned to all users.</span></span> <span data-ttu-id="16aaa-215">Ändra principen för att använda en tilldelning som är riktad till en viss Azure AD-grupp som inte innehåller Microsoft hanterade Station ära datorer.</span><span class="sxs-lookup"><span data-stu-id="16aaa-215">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="16aaa-216">Mer information finns i [principer för villkorsstyrd åtkomst](#conditional-access-policies) och [villkorsstyrd åtkomst: Kräv MFA för alla användare](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span><span class="sxs-lookup"><span data-stu-id="16aaa-216">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span>

<span data-ttu-id="16aaa-217">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="16aaa-217">**Advisory**</span></span>

<span data-ttu-id="16aaa-218">Se till att alla villkorsstyrda åtkomst principer som kräver MFA exkluderar den **moderna arbets platsen – alla** Azure AD-grupper.</span><span class="sxs-lookup"><span data-stu-id="16aaa-218">Make sure that any conditional access policies that require MFA exclude the **Modern Workplace -All** Azure AD group.</span></span> <span data-ttu-id="16aaa-219">Mer information finns i [principer för villkorsstyrd åtkomst](#conditional-access-policies) och [villkorsstyrd åtkomst: Kräv MFA för alla användare](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span><span class="sxs-lookup"><span data-stu-id="16aaa-219">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span> <span data-ttu-id="16aaa-220">Den **moderna arbets platsen – alla** Azure AD-grupper är en dynamisk grupp som vi skapar när du registrerar dig på Microsoft Managed Desktop, så att du måste komma tillbaka till den här gruppen efter registrering.</span><span class="sxs-lookup"><span data-stu-id="16aaa-220">The **Modern Workplace -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>

<span data-ttu-id="16aaa-221">**Fel**</span><span class="sxs-lookup"><span data-stu-id="16aaa-221">**Error**</span></span>

<span data-ttu-id="16aaa-222">Rollen Intune-administratör har inte tillräcklig behörighet för den här kontrollen.</span><span class="sxs-lookup"><span data-stu-id="16aaa-222">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="16aaa-223">Du behöver också några av de här Azure AD-rollerna för att köra den här kontrollen:</span><span class="sxs-lookup"><span data-stu-id="16aaa-223">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="16aaa-224">Säkerhets läsare</span><span class="sxs-lookup"><span data-stu-id="16aaa-224">Security Reader</span></span>
- <span data-ttu-id="16aaa-225">Säkerhets administratör</span><span class="sxs-lookup"><span data-stu-id="16aaa-225">Security Administrator</span></span>
- <span data-ttu-id="16aaa-226">Administratör för villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="16aaa-226">Conditional Access Administrator</span></span>
- <span data-ttu-id="16aaa-227">Global läsare</span><span class="sxs-lookup"><span data-stu-id="16aaa-227">Global Reader</span></span>
- <span data-ttu-id="16aaa-228">Enheter-administratör</span><span class="sxs-lookup"><span data-stu-id="16aaa-228">Devices Administrator</span></span>


### <a name="powershell-scripts"></a><span data-ttu-id="16aaa-229">PowerShell-skript</span><span class="sxs-lookup"><span data-stu-id="16aaa-229">PowerShell scripts</span></span>

<span data-ttu-id="16aaa-230">Windows PowerShell-skript kan inte tilldelas på ett sätt som riktar sig till Microsoft Managed Station ära enheter.</span><span class="sxs-lookup"><span data-stu-id="16aaa-230">Windows PowerShell scripts can't be assigned in a way that would target Microsoft Managed Desktop devices.</span></span>  

<span data-ttu-id="16aaa-231">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="16aaa-231">**Advisory**</span></span>

<span data-ttu-id="16aaa-232">Kontrol lera att Windows PowerShell-skript i din Azure AD-organisation inte har några Microsoft-hanterings enheter eller användare.</span><span class="sxs-lookup"><span data-stu-id="16aaa-232">Make sure that Windows PowerShell scripts in your Azure AD organization don't target any Microsoft Manage Desktop devices or users.</span></span> <span data-ttu-id="16aaa-233">Koppla inte ett PowerShell-skript till alla användare, alla enheter eller både och.</span><span class="sxs-lookup"><span data-stu-id="16aaa-233">Do not assign a PowerShell script to target all users, all devices, or both.</span></span> <span data-ttu-id="16aaa-234">Ändra principen för att använda en tilldelning som är riktad till en viss Azure AD-grupp som inte innehåller Microsoft hanterade Station ära datorer.</span><span class="sxs-lookup"><span data-stu-id="16aaa-234">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="16aaa-235">Mer information finns i [använda PowerShell-skript på Windows 10-enheter i Intune](https://docs.microsoft.com/mem/intune/apps/intune-management-extension).</span><span class="sxs-lookup"><span data-stu-id="16aaa-235">For more information, see [Use PowerShell scripts on Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/apps/intune-management-extension).</span></span>

### <a name="region"></a><span data-ttu-id="16aaa-236">Region</span><span class="sxs-lookup"><span data-stu-id="16aaa-236">Region</span></span>

<span data-ttu-id="16aaa-237">Din region måste vara kompatibel med Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="16aaa-237">Your region must be supported by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="16aaa-238">**Inte klart**</span><span class="sxs-lookup"><span data-stu-id="16aaa-238">**Not ready**</span></span>

<span data-ttu-id="16aaa-239">Din organisations region för Azure AD stöds för närvarande inte av Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="16aaa-239">Your Azure AD organization region isn't currently supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="16aaa-240">Mer information finns i [regioner och språk som stöds i Microsoft hanterade skriv bord](../service-description/regions-languages.md).</span><span class="sxs-lookup"><span data-stu-id="16aaa-240">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>

<span data-ttu-id="16aaa-241">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="16aaa-241">**Advisory**</span></span>

<span data-ttu-id="16aaa-242">Ett eller flera av de länder där din Azure AD-organisation finns stöds inte av Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="16aaa-242">One or more of the countries where your Azure AD organization is located isn't supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="16aaa-243">Mer information finns i [regioner och språk som stöds i Microsoft hanterade skriv bord](../service-description/regions-languages.md).</span><span class="sxs-lookup"><span data-stu-id="16aaa-243">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>


### <a name="security-baselines"></a><span data-ttu-id="16aaa-244">Säkerhets bas linjer</span><span class="sxs-lookup"><span data-stu-id="16aaa-244">Security baselines</span></span>

<span data-ttu-id="16aaa-245">Principer för säkerhets rikt linjer ska inte vara riktade till enheter som hanteras av Microsoft.</span><span class="sxs-lookup"><span data-stu-id="16aaa-245">Security baseline policies should not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="16aaa-246">**Inte klart**</span><span class="sxs-lookup"><span data-stu-id="16aaa-246">**Not ready**</span></span>

<span data-ttu-id="16aaa-247">Du har en säkerhets bas profil som är riktad till alla användare, alla enheter eller både och.</span><span class="sxs-lookup"><span data-stu-id="16aaa-247">You have a security baseline profile that targets all users, all devices or both.</span></span> <span data-ttu-id="16aaa-248">Ändra principen för att använda en tilldelning som är riktad till en viss Azure AD-grupp som inte innehåller Microsoft hanterade Station ära datorer.</span><span class="sxs-lookup"><span data-stu-id="16aaa-248">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="16aaa-249">Anvisningar finns i [använda säkerhets bas linjer för att konfigurera Windows 10-enheter i Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span><span class="sxs-lookup"><span data-stu-id="16aaa-249">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span>

<span data-ttu-id="16aaa-250">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="16aaa-250">**Advisory**</span></span>

<span data-ttu-id="16aaa-251">Se till att alla principer för säkerhets rikt linjer du har exkluderar Microsoft Managed Station ära enheter.</span><span class="sxs-lookup"><span data-stu-id="16aaa-251">Make sure that any security baseline policies you have exclude Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="16aaa-252">Anvisningar finns i [använda säkerhets bas linjer för att konfigurera Windows 10-enheter i Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span><span class="sxs-lookup"><span data-stu-id="16aaa-252">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span> <span data-ttu-id="16aaa-253">**Moderna arbets plats enheter-alla** Azure AD-grupper är en dynamisk grupp som vi skapar när du registrerar dig på Microsoft Managed Desktop, så att du måste komma tillbaka till den här gruppen efter registrering.</span><span class="sxs-lookup"><span data-stu-id="16aaa-253">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


### <a name="windows-apps"></a><span data-ttu-id="16aaa-254">Windows-appar</span><span class="sxs-lookup"><span data-stu-id="16aaa-254">Windows apps</span></span>

<span data-ttu-id="16aaa-255">Granska de program du vill att Microsoft Managed Desktop-användarna ska ha.</span><span class="sxs-lookup"><span data-stu-id="16aaa-255">Review apps you want your Microsoft Managed Desktop users to have.</span></span>

<span data-ttu-id="16aaa-256">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="16aaa-256">**Advisory**</span></span>

<span data-ttu-id="16aaa-257">Du bör förbereda en inventering av de program som du vill att Microsoft Managed Desktop-användarna ska ha.</span><span class="sxs-lookup"><span data-stu-id="16aaa-257">You should prepare an inventory of the apps that you want your Microsoft Managed Desktop users to have.</span></span> <span data-ttu-id="16aaa-258">Eftersom dessa appar måste distribueras av Intune kan du utvärdera igen befintliga Intune-appar.</span><span class="sxs-lookup"><span data-stu-id="16aaa-258">Since these apps must be deployed by Intune, evaluate reusing existing Intune apps.</span></span> <span data-ttu-id="16aaa-259">Överväg att använda företags portalen (se [Installera Intune företags Portal på enheter](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/company-portal) och registrerings status sida (ESP) för att distribuera program till användarna.</span><span class="sxs-lookup"><span data-stu-id="16aaa-259">Consider using Company Portal (see [Install Intune Company Portal on devices](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/company-portal) and Enrollment Status Page (ESP) to distribute apps to your users.</span></span> <span data-ttu-id="16aaa-260">Mer information finns i [program på Microsoft Managed Desktop](apps.md) och förstagångskörningen [med autopilot och sidan registrerings status](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/esp-first-run).</span><span class="sxs-lookup"><span data-stu-id="16aaa-260">For more information, see [Apps in Microsoft Managed Desktop](apps.md) and [First-run experience with Autopilot and the Enrollment Status Page](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/esp-first-run).</span></span>

<span data-ttu-id="16aaa-261">Du kan be din Microsoft-representant om en fråga i Microsoft Endpoint Configuration Manager att identifiera de program som är redo att migreras till Intune eller behöver justeras.</span><span class="sxs-lookup"><span data-stu-id="16aaa-261">You can ask your Microsoft account representative for a query in Microsoft Endpoint Configuration Manager to identify those apps that are ready to migrate to Intune or need adjustment.</span></span>


### <a name="windows-hello-for-business"></a><span data-ttu-id="16aaa-262">Windows Hello för företag</span><span class="sxs-lookup"><span data-stu-id="16aaa-262">Windows Hello for Business</span></span>

<span data-ttu-id="16aaa-263">Microsoft Managed Desktop kräver att Windows Hello för företag aktive ras.</span><span class="sxs-lookup"><span data-stu-id="16aaa-263">Microsoft Managed Desktop requires Windows Hello for Business to be enabled.</span></span>

<span data-ttu-id="16aaa-264">**Inte klart**</span><span class="sxs-lookup"><span data-stu-id="16aaa-264">**Not ready**</span></span>

<span data-ttu-id="16aaa-265">Windows Hello för företag är inaktiverat.</span><span class="sxs-lookup"><span data-stu-id="16aaa-265">Windows Hello for Business is disabled.</span></span> <span data-ttu-id="16aaa-266">Aktivera den genom att följa anvisningarna i [skapa en Windows Hello för företag-princip](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span><span class="sxs-lookup"><span data-stu-id="16aaa-266">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span></span>

<span data-ttu-id="16aaa-267">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="16aaa-267">**Advisory**</span></span>

<span data-ttu-id="16aaa-268">Windows Hello för företag är inte konfigurerat.</span><span class="sxs-lookup"><span data-stu-id="16aaa-268">Windows Hello for Business is not set up.</span></span> <span data-ttu-id="16aaa-269">Aktivera den genom att följa anvisningarna i [skapa en Windows Hello för företag-policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).</span><span class="sxs-lookup"><span data-stu-id="16aaa-269">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).</span></span>


### <a name="windows-10-update-rings"></a><span data-ttu-id="16aaa-270">Windows 10-uppdaterings ringar</span><span class="sxs-lookup"><span data-stu-id="16aaa-270">Windows 10 update rings</span></span>

<span data-ttu-id="16aaa-271">Din "Windows 10 Update ring"-princip i Intune får inte uppfylla alla hanterade Microsoft-enheter.</span><span class="sxs-lookup"><span data-stu-id="16aaa-271">Your "Windows 10 update ring" policy in Intune must not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="16aaa-272">**Inte klart**</span><span class="sxs-lookup"><span data-stu-id="16aaa-272">**Not ready**</span></span>

<span data-ttu-id="16aaa-273">Du har en "uppdatera ring"-princip som är riktad till alla enheter, alla användare eller både och.</span><span class="sxs-lookup"><span data-stu-id="16aaa-273">You have an "update ring" policy that targets all devices, all users, or both.</span></span> <span data-ttu-id="16aaa-274">Ändra principen för att använda en tilldelning som är riktad till en viss Azure AD-grupp som inte innehåller Microsoft hanterade Station ära datorer.</span><span class="sxs-lookup"><span data-stu-id="16aaa-274">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="16aaa-275">Anvisningar finns i [hantera program uppdateringar för Windows 10 i Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span><span class="sxs-lookup"><span data-stu-id="16aaa-275">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span>

<span data-ttu-id="16aaa-276">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="16aaa-276">**Advisory**</span></span>

<span data-ttu-id="16aaa-277">Se till att eventuella uppdaterings rings principer du har exkluderar den **moderna arbets ytans enheter-alla** Azure AD-grupper.</span><span class="sxs-lookup"><span data-stu-id="16aaa-277">Make sure that any update ring policies you have exclude the **Modern Workplace Devices -All** Azure AD group.</span></span> <span data-ttu-id="16aaa-278">Om du har tilldelat Azure AD-gruppgruppen till dessa principer kontrollerar du att eventuella uppdaterings rings principer du även har exkluderat den **moderna arbets platsen – alla** Azure AD-grupper som innehåller hanterade Microsoft-användare.</span><span class="sxs-lookup"><span data-stu-id="16aaa-278">If you have assigned Azure AD user group to these policies, make sure that any update ring policies you have also excluded the **Modern Workplace -All** Azure AD group that includes your Microsoft Managed Desktop users.</span></span> <span data-ttu-id="16aaa-279">Anvisningar finns i [hantera program uppdateringar för Windows 10 i Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span><span class="sxs-lookup"><span data-stu-id="16aaa-279">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span> <span data-ttu-id="16aaa-280">Både den **moderna arbets ytan-alla** och **moderna arbets platser – alla** Azure AD-grupper tilldelas grupper som vi skapar när du registrerar dig på Microsoft Managed Desktop, så att du måste komma tillbaka till den här gruppen efter registreringen.</span><span class="sxs-lookup"><span data-stu-id="16aaa-280">Both the **Modern Workplace Devices -All** and **Modern Workplace -All** Azure AD groups are assigned groups that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


## <a name="azure-active-directory-settings"></a><span data-ttu-id="16aaa-281">Azure Active Directory-inställningar</span><span class="sxs-lookup"><span data-stu-id="16aaa-281">Azure Active Directory settings</span></span>

<span data-ttu-id="16aaa-282">Du kan komma åt Azure Active Directory-inställningar i [Azure-portalen](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="16aaa-282">You can access Azure Active Directory settings at the [Azure portal](https://portal.azure.com).</span></span>

### <a name="ad-hoc-subscriptions"></a><span data-ttu-id="16aaa-283">Ad hoc-abonnemang</span><span class="sxs-lookup"><span data-stu-id="16aaa-283">Ad hoc subscriptions</span></span>

<span data-ttu-id="16aaa-284">Här beskrivs hur du kontrollerar en inställning som (om värdet är "falskt") kan hindra företags tillstånd från att fungera korrekt.</span><span class="sxs-lookup"><span data-stu-id="16aaa-284">Advises how to check a setting that (if set to "false") might prevent Enterprise State Roaming from working correctly.</span></span>

<span data-ttu-id="16aaa-285">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="16aaa-285">**Advisory**</span></span>

<span data-ttu-id="16aaa-286">Kontrol lera att **AllowAdHocSubscriptions** är inställt på **True**.</span><span class="sxs-lookup"><span data-stu-id="16aaa-286">Ensure that **AllowAdHocSubscriptions** is set to **True**.</span></span> <span data-ttu-id="16aaa-287">I annat fall kanske företags statusen roaming inte fungerar.</span><span class="sxs-lookup"><span data-stu-id="16aaa-287">Otherwise, Enterprise State Roaming might not work.</span></span> <span data-ttu-id="16aaa-288">Mer information finns i [set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="16aaa-288">For more information, see [Set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).</span></span>


### <a name="enterprise-state-roaming"></a><span data-ttu-id="16aaa-289">Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="16aaa-289">Enterprise State Roaming</span></span>

<span data-ttu-id="16aaa-290">Roaming för företags status bör vara aktiverat.</span><span class="sxs-lookup"><span data-stu-id="16aaa-290">Enterprise State Roaming should be enabled.</span></span>

<span data-ttu-id="16aaa-291">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="16aaa-291">**Advisory**</span></span>

<span data-ttu-id="16aaa-292">Kontrol lera att organisationens centrala nätverks tillstånd är aktiverat för **alla** eller för **markerade** grupper.</span><span class="sxs-lookup"><span data-stu-id="16aaa-292">Make sure that Enterprise State Roaming is enabled for **All** or for **Selected** groups.</span></span> <span data-ttu-id="16aaa-293">Mer information finns i [Aktivera roaming för företags tillstånd i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable).</span><span class="sxs-lookup"><span data-stu-id="16aaa-293">For more information, see [Enable Enterprise State Roaming in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable).</span></span>

### <a name="licenses"></a><span data-ttu-id="16aaa-294">Licenser</span><span class="sxs-lookup"><span data-stu-id="16aaa-294">Licenses</span></span>

<span data-ttu-id="16aaa-295">Det krävs flera olika licenser för att använda Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="16aaa-295">A number of licenses are required to use Microsoft Managed Desktop.</span></span>

<span data-ttu-id="16aaa-296">**Inte klart**</span><span class="sxs-lookup"><span data-stu-id="16aaa-296">**Not Ready**</span></span>

<span data-ttu-id="16aaa-297">Du har inte alla licenser som du behöver för att använda Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="16aaa-297">You don't have all the licenses you need to use Microsoft Managed Desktop.</span></span> <span data-ttu-id="16aaa-298">Mer information finns i [Microsoft hanterad Skriv bords teknik](../intro/technologies.md) och [mer om licenser](prerequisites.md#more-about-licenses).</span><span class="sxs-lookup"><span data-stu-id="16aaa-298">For more information, see [Microsoft Managed Desktop technologies](../intro/technologies.md) and [More about licenses](prerequisites.md#more-about-licenses).</span></span>


### <a name="security-account-names"></a><span data-ttu-id="16aaa-299">Namn på säkerhets konton</span><span class="sxs-lookup"><span data-stu-id="16aaa-299">Security account names</span></span>

<span data-ttu-id="16aaa-300">Vissa namn på säkerhets konton kan vara i konflikt med dem som har skapats av Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="16aaa-300">Certain security account names could conflict with ones created by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="16aaa-301">**Inte klart**</span><span class="sxs-lookup"><span data-stu-id="16aaa-301">**Not ready**</span></span>

<span data-ttu-id="16aaa-302">Du har minst ett konto namn som är oförenliga med dem som skapas av Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="16aaa-302">You have at least one account name that will conflict with ones created by Microsoft Managed Desktop.</span></span> <span data-ttu-id="16aaa-303">Arbeta med ditt Microsoft-konto för att utesluta dessa konto namn.</span><span class="sxs-lookup"><span data-stu-id="16aaa-303">Work with your Microsoft account representative to exclude these account names.</span></span>


### <a name="security-administrator-roles"></a><span data-ttu-id="16aaa-304">Säkerhets administratörs roller</span><span class="sxs-lookup"><span data-stu-id="16aaa-304">Security administrator roles</span></span>

<span data-ttu-id="16aaa-305">Användare med vissa säkerhets roller måste ha de roller som är kopplade till Microsoft Defender för slut punkter.</span><span class="sxs-lookup"><span data-stu-id="16aaa-305">Users with certain security roles must have those roles assigned in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="16aaa-306">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="16aaa-306">**Advisory**</span></span>

<span data-ttu-id="16aaa-307">Om du har användare tilldelade till någon av dessa roller i din Azure AD-organisation kontrollerar du att de också har tilldelats dessa roller i Microsoft Defender för slut punkter.</span><span class="sxs-lookup"><span data-stu-id="16aaa-307">If you have users assigned to any of these roles in your Azure AD organization, make sure they also have these roles assigned in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="16aaa-308">Annars kommer administratörer med dessa roller inte att kunna använda administrations portalen.</span><span class="sxs-lookup"><span data-stu-id="16aaa-308">Otherwise, administrators with these roles won't be able to access the Admin portal.</span></span>

- <span data-ttu-id="16aaa-309">Säkerhets ansvarig</span><span class="sxs-lookup"><span data-stu-id="16aaa-309">Security Operator</span></span>
- <span data-ttu-id="16aaa-310">Global läsare</span><span class="sxs-lookup"><span data-stu-id="16aaa-310">Global Reader</span></span>

<span data-ttu-id="16aaa-311">Mer information finns i [skapa och hantera roller för rollbaserad åtkomst kontroll](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles).</span><span class="sxs-lookup"><span data-stu-id="16aaa-311">For more information, see [Create and manage roles for role-based access control](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles).</span></span>


### <a name="security-default"></a><span data-ttu-id="16aaa-312">Säkerhets standard</span><span class="sxs-lookup"><span data-stu-id="16aaa-312">Security default</span></span>

<span data-ttu-id="16aaa-313">Säkerhets inställningar i Azure Active Directory kommer inte att hantera dina enheter på Microsoft.</span><span class="sxs-lookup"><span data-stu-id="16aaa-313">Security defaults in Azure Active Directory will prevent Microsoft Managed Desktop from managing your devices.</span></span>

<span data-ttu-id="16aaa-314">**Inte klart**</span><span class="sxs-lookup"><span data-stu-id="16aaa-314">**Not ready**</span></span>

<span data-ttu-id="16aaa-315">Säkerhets inställningarna är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="16aaa-315">You have Security defaults turned on.</span></span> <span data-ttu-id="16aaa-316">Inaktivera säkerhets standarder och konfigurera villkorsstyrda åtkomst principer.</span><span class="sxs-lookup"><span data-stu-id="16aaa-316">Turn off Security defaults and set up conditional access policies.</span></span> <span data-ttu-id="16aaa-317">Mer information finns i [vanliga principer för villkorsstyrd åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span><span class="sxs-lookup"><span data-stu-id="16aaa-317">For more information, see [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span></span>

### <a name="self-service-password-reset"></a><span data-ttu-id="16aaa-318">Självbetjäning för återställning av lösen ord</span><span class="sxs-lookup"><span data-stu-id="16aaa-318">Self-service Password Reset</span></span>

<span data-ttu-id="16aaa-319">Självbetjäning för återställning av lösen ord (SSPR) ska aktive ras för alla hanterade Microsoft-användare utom Microsoft Managed Desktop Service-konton.</span><span class="sxs-lookup"><span data-stu-id="16aaa-319">Self-service Password Reset (SSPR) should be enabled for all Microsoft Managed Desktop users excluding Microsoft Managed Desktop service accounts.</span></span> <span data-ttu-id="16aaa-320">Mer information finns i [själv studie kursen: Låt användare låsa upp sina konton eller återställa lösen ord med hjälp av återställning av Azure Active Directory Self-Service](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span><span class="sxs-lookup"><span data-stu-id="16aaa-320">For more information, see [Tutorial: Enable users to unlock their account or reset passwords using Azure Active Directory self-service password reset](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span></span>

<span data-ttu-id="16aaa-321">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="16aaa-321">**Advisory**</span></span>

<span data-ttu-id="16aaa-322">Kontrol lera att den SSPR **valda** inställningen innehåller Microsoft hanterade Skriv bords enheter men inte Microsoft Managed Desktop Service accounts.</span><span class="sxs-lookup"><span data-stu-id="16aaa-322">Make sure that the SSPR **Selected** setting includes Microsoft Managed Desktop devices but excludes Microsoft Managed Desktop service accounts.</span></span> <span data-ttu-id="16aaa-323">Microsoft Managed Desktop Service-konton kan inte fungera som förväntat när SSPR är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="16aaa-323">Microsoft Managed Desktop service accounts cannot work as expected when SSPR is enabled.</span></span>  


### <a name="standard-user-role"></a><span data-ttu-id="16aaa-324">Standard användar roll</span><span class="sxs-lookup"><span data-stu-id="16aaa-324">Standard user role</span></span>

<span data-ttu-id="16aaa-325">Förutom de användare som har tilldelats Azure AD-roller av global administratör och enhets administratör kommer Microsoft Managed Desktop-användare att vara vanliga användare utan lokala administratörs privilegier.</span><span class="sxs-lookup"><span data-stu-id="16aaa-325">Other than those users who are assigned Azure AD roles of Global administrator and Device administrator, Microsoft Managed Desktop users will be standard users without local administrator privileges.</span></span> <span data-ttu-id="16aaa-326">Alla andra användare tilldelas en standard användar roll när de startar sin Microsoft-hanterade Station.</span><span class="sxs-lookup"><span data-stu-id="16aaa-326">All other users will be assigned a standard user role when they start their Microsoft Managed Desktop device.</span></span>

<span data-ttu-id="16aaa-327">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="16aaa-327">**Advisory**</span></span>

<span data-ttu-id="16aaa-328">Microsoft Managed Desktop-användare kommer inte att ha lokala administratörs privilegier på sina Microsoft Managed Station ära enheter efter registrering.</span><span class="sxs-lookup"><span data-stu-id="16aaa-328">Microsoft Managed Desktop users will not have local administrator privileges on their Microsoft Managed Desktop devices after enrolling.</span></span>

## <a name="microsoft-365-apps-for-enterprise"></a><span data-ttu-id="16aaa-329"> Microsoft 365 Apps för företag</span><span class="sxs-lookup"><span data-stu-id="16aaa-329">Microsoft 365 Apps for enterprise</span></span>

### <a name="onedrive"></a><span data-ttu-id="16aaa-330">OneDrive</span><span class="sxs-lookup"><span data-stu-id="16aaa-330">OneDrive</span></span>

<span data-ttu-id="16aaa-331">Inställningen **Tillåt synkronisering endast på datorer som är anslutna till vissa domäner** visas i konflikt med Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="16aaa-331">The **Allow syncing only on PCs joined to specific domains** setting will conflict with Microsoft Managed Desktop.</span></span> <span data-ttu-id="16aaa-332">Du kan komma åt OneDrive-inställningar i [administrations centret](https://admin.onedrive.com)för OneDrive.</span><span class="sxs-lookup"><span data-stu-id="16aaa-332">You can access OneDrive settings at the OneDrive [admin center](https://admin.onedrive.com).</span></span>

<span data-ttu-id="16aaa-333">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="16aaa-333">**Advisory**</span></span>

<span data-ttu-id="16aaa-334">Du använder alternativet **Tillåt synkronisering endast på datorer som är anslutna till vissa domän** inställningar.</span><span class="sxs-lookup"><span data-stu-id="16aaa-334">You're using the **Allow syncing only on PCs joined to specific domains** setting.</span></span> <span data-ttu-id="16aaa-335">Den här inställningen fungerar inte med Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="16aaa-335">This setting won't work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="16aaa-336">Inaktivera den här inställningen och konfigurera i stället OneDrive för att använda en princip för villkorsstyrd åtkomst.</span><span class="sxs-lookup"><span data-stu-id="16aaa-336">Disable this setting, and instead set up OneDrive to use a conditional access policy.</span></span> <span data-ttu-id="16aaa-337">Se [Planera en distribution för villkorlig åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) för hjälp.</span><span class="sxs-lookup"><span data-stu-id="16aaa-337">See [Plan a Conditional Access deployment](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) for help.</span></span>

