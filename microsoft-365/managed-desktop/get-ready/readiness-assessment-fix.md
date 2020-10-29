---
title: Åtgärda problem som upptäckts av verktyget för bedömning av beredskap
description: Detaljerade åtgärder att vidta för varje problem som verktyget hittar
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: a6dec9473ee632b74bb79e50156cedff53a3cba3
ms.sourcegitcommit: fa26da0be667d4be0121c52b05488dc76c5d626c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/29/2020
ms.locfileid: "48795123"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a><span data-ttu-id="ef933-104">Åtgärda problem som upptäckts av verktyget för bedömning av beredskap</span><span class="sxs-lookup"><span data-stu-id="ef933-104">Fix issues found by the readiness assessment tool</span></span>

<span data-ttu-id="ef933-105">För varje kontroll rapporteras ett av fyra möjliga resultat:</span><span class="sxs-lookup"><span data-stu-id="ef933-105">For each check, the tool will report one of four possible results:</span></span>


|<span data-ttu-id="ef933-106">Resultat</span><span class="sxs-lookup"><span data-stu-id="ef933-106">Result</span></span>  |<span data-ttu-id="ef933-107">Betydelse</span><span class="sxs-lookup"><span data-stu-id="ef933-107">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="ef933-108">Förbereder</span><span class="sxs-lookup"><span data-stu-id="ef933-108">Ready</span></span>     | <span data-ttu-id="ef933-109">Ingen åtgärd krävs innan du slutför registreringen.</span><span class="sxs-lookup"><span data-stu-id="ef933-109">No action is required before completing enrollment.</span></span>        |
|<span data-ttu-id="ef933-110">Rådgivare</span><span class="sxs-lookup"><span data-stu-id="ef933-110">Advisory</span></span>    | <span data-ttu-id="ef933-111">Följ stegen i verktyget eller den här artikeln för att få bästa möjliga upplevelse av registrering och användare.</span><span class="sxs-lookup"><span data-stu-id="ef933-111">Follow the steps in the tool or this article for the best experience with enrollment and for users.</span></span> <span data-ttu-id="ef933-112">Du *kan* slutföra registreringen, men du måste åtgärda dessa problem innan du distribuerar den första enheten.</span><span class="sxs-lookup"><span data-stu-id="ef933-112">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="ef933-113">Inte klart</span><span class="sxs-lookup"><span data-stu-id="ef933-113">Not ready</span></span> | <span data-ttu-id="ef933-114">*Registreringen Miss lyckas om du inte åtgärdar dessa problem.*</span><span class="sxs-lookup"><span data-stu-id="ef933-114">*Enrollment will fail if you don't fix these issues.*</span></span> <span data-ttu-id="ef933-115">Följ stegen i verktyget eller den här artikeln för att åtgärda dem.</span><span class="sxs-lookup"><span data-stu-id="ef933-115">Follow the steps in the tool or this article to resolve them.</span></span>        |
|<span data-ttu-id="ef933-116">Fel</span><span class="sxs-lookup"><span data-stu-id="ef933-116">Error</span></span> | <span data-ttu-id="ef933-117">Azure Active Director (AD)-rollen som du använder har inte tillräcklig behörighet för att köra den här kontrollen.</span><span class="sxs-lookup"><span data-stu-id="ef933-117">The Azure Active Director (AD) role you're using doesn't have sufficient permission to run this check.</span></span> |

## <a name="microsoft-intune-settings"></a><span data-ttu-id="ef933-118">Microsoft Intune-inställningar</span><span class="sxs-lookup"><span data-stu-id="ef933-118">Microsoft Intune settings</span></span>

### <a name="autopilot-deployment-profile"></a><span data-ttu-id="ef933-119">Distributions profil för autopilot</span><span class="sxs-lookup"><span data-stu-id="ef933-119">Autopilot deployment profile</span></span>

<span data-ttu-id="ef933-120">Du bör inte ha några befintliga autopilot-profiler som riktar sig till tilldelade eller dynamiska grupper som används av Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="ef933-120">You shouldn't have any existing Autopilot profiles that target assigned or dynamic groups used by Microsoft Managed Desktop.</span></span> <span data-ttu-id="ef933-121">Microsoft Managed Desktop använder autopilot för att etablera nya enheter.</span><span class="sxs-lookup"><span data-stu-id="ef933-121">Microsoft Managed Desktop uses Autopilot to provision new devices.</span></span>

<span data-ttu-id="ef933-122">**Inte klart**</span><span class="sxs-lookup"><span data-stu-id="ef933-122">**Not ready**</span></span>

<span data-ttu-id="ef933-123">Du har en autopilot-profil som kopplats till alla enheter.</span><span class="sxs-lookup"><span data-stu-id="ef933-123">You have an Autopilot profile that is assigned to all devices.</span></span> <span data-ttu-id="ef933-124">Anvisningar finns i [registrera Windows-enheter i Intune med hjälp av Windows autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span><span class="sxs-lookup"><span data-stu-id="ef933-124">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="ef933-125">Efter Microsoft Managed Desktop-registrering ställer du in autopilot-principen så att den **moderna arbets ytan visas-alla** Azure AD-grupper.</span><span class="sxs-lookup"><span data-stu-id="ef933-125">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>

<span data-ttu-id="ef933-126">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="ef933-126">**Advisory**</span></span>

<span data-ttu-id="ef933-127">Se till att dina autopilot-profiler är riktade till en tilldelad eller dynamisk Azure AD-grupp som inte innehåller Microsoft Managed Station ära enheter som kommer att skapas vid registrering.</span><span class="sxs-lookup"><span data-stu-id="ef933-127">Make sure that your Autopilot profiles target an assigned or dynamic Azure AD group that doesn't include Microsoft Managed Desktop devices that will be created at enrollment.</span></span> <span data-ttu-id="ef933-128">Anvisningar finns i [registrera Windows-enheter i Intune med hjälp av Windows autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span><span class="sxs-lookup"><span data-stu-id="ef933-128">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="ef933-129">Efter Microsoft Managed Desktop-registrering ställer du in autopilot-principen så att den **moderna arbets ytan visas-alla** Azure AD-grupper.</span><span class="sxs-lookup"><span data-stu-id="ef933-129">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>


### <a name="certificate-connectors"></a><span data-ttu-id="ef933-130">Certifikat anslutningar</span><span class="sxs-lookup"><span data-stu-id="ef933-130">Certificate connectors</span></span>

<span data-ttu-id="ef933-131">Om du har några certifikat anslutningar som används av de enheter som du vill registrera på Microsoft Managed Desktop kan de inte ha några fel.</span><span class="sxs-lookup"><span data-stu-id="ef933-131">If you have any certificate connectors used by the devices you want to enroll in Microsoft Managed Desktop, the connectors cannot have any errors.</span></span> <span data-ttu-id="ef933-132">Endast en av följande rådgivare kommer att gälla för din situation, så kolla dem noggrant.</span><span class="sxs-lookup"><span data-stu-id="ef933-132">Only one of the following advisories will apply to your situation, so check them carefully.</span></span>

<span data-ttu-id="ef933-133">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="ef933-133">**Advisory**</span></span>

<span data-ttu-id="ef933-134">Det finns inga certifikat kopplingar.</span><span class="sxs-lookup"><span data-stu-id="ef933-134">No certificate connectors are present.</span></span> <span data-ttu-id="ef933-135">Det är möjligt att du inte behöver några kopplingar, men du bör utvärdera om du kan behöva vissa för nätverks anslutningen till Microsoft Managed Station ära datorer.</span><span class="sxs-lookup"><span data-stu-id="ef933-135">It's possible you don't need any connectors, but you should evaluate whether you might need some for network connectivity to Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="ef933-136">Mer information finns i [förbereda certifikat och nätverks profiler för Microsoft Managed Desktop](certs-wifi-lan.md).</span><span class="sxs-lookup"><span data-stu-id="ef933-136">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

<span data-ttu-id="ef933-137">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="ef933-137">**Advisory**</span></span>

<span data-ttu-id="ef933-138">Minst ett certifikat har ett fel.</span><span class="sxs-lookup"><span data-stu-id="ef933-138">At least one certificate connector has an error.</span></span> <span data-ttu-id="ef933-139">Om du behöver den här kopplingen för anslutning till Microsoft-hanterade Skriv bords enheter måste du lösa problemet.</span><span class="sxs-lookup"><span data-stu-id="ef933-139">If you need this connector for connectivity to Microsoft Managed Desktop devices, you must resolve the error.</span></span> <span data-ttu-id="ef933-140">Mer information finns i [förbereda certifikat och nätverks profiler för Microsoft Managed Desktop](certs-wifi-lan.md).</span><span class="sxs-lookup"><span data-stu-id="ef933-140">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


<span data-ttu-id="ef933-141">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="ef933-141">**Advisory**</span></span>

<span data-ttu-id="ef933-142">Du har minst en certifikatanslutningsappen och inga fel rapporteras.</span><span class="sxs-lookup"><span data-stu-id="ef933-142">You have at least one certificate connector and no errors are reported.</span></span> <span data-ttu-id="ef933-143">Men det kan hända att du måste skapa en profil för att återanvända Connector för Microsoft-hanterade Station ära datorer.</span><span class="sxs-lookup"><span data-stu-id="ef933-143">However, you might need to create a profile to reuse the connector for Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="ef933-144">Mer information finns i [förbereda certifikat och nätverks profiler för Microsoft Managed Desktop](certs-wifi-lan.md).</span><span class="sxs-lookup"><span data-stu-id="ef933-144">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


### <a name="conditional-access-policies"></a><span data-ttu-id="ef933-145">Principer för villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="ef933-145">Conditional access policies</span></span>

<span data-ttu-id="ef933-146">Principer för villkorsstyrd åtkomst i din Azure AD-organisation får inte vara riktade till Microsoft Manage Desktop-användare.</span><span class="sxs-lookup"><span data-stu-id="ef933-146">Conditional access policies in your Azure AD organization must not target any Microsoft Manage Desktop users.</span></span>

<span data-ttu-id="ef933-147">**Inte klart**</span><span class="sxs-lookup"><span data-stu-id="ef933-147">**Not ready**</span></span>

<span data-ttu-id="ef933-148">Du har minst en princip för villkorsstyrd åtkomst som är riktad till alla användare.</span><span class="sxs-lookup"><span data-stu-id="ef933-148">You have at least one conditional access policy that targets all users.</span></span> <span data-ttu-id="ef933-149">Återställ principen för en viss Azure AD-grupp som inte innehåller Azure AD-gruppen av Microsoft Managed Desktop Service-konton som kommer att skapas vid registrering.</span><span class="sxs-lookup"><span data-stu-id="ef933-149">Reset the policy to target a specific Azure AD group that does not include the Azure AD group of Microsoft Managed Desktop service accounts that will be created at enrollment.</span></span> <span data-ttu-id="ef933-150">Anvisningar finns i [villkorlig åtkomst: användare och grupper](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span><span class="sxs-lookup"><span data-stu-id="ef933-150">For steps, see [Conditional Access: Users and groups](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span></span>

<span data-ttu-id="ef933-151">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="ef933-151">**Advisory**</span></span>

<span data-ttu-id="ef933-152">Se till att alla principer för villkorsstyrd åtkomst du har exkluderar den **moderna arbets plats tjänstens konton** Azure AD-grupp.</span><span class="sxs-lookup"><span data-stu-id="ef933-152">Make sure that any conditional access policies you have exclude the **Modern Workplace Service Accounts** Azure AD group.</span></span> <span data-ttu-id="ef933-153">Anvisningar finns i [Justera villkorlig åtkomst](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access).</span><span class="sxs-lookup"><span data-stu-id="ef933-153">For steps, see [Adjust conditional access](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access).</span></span> <span data-ttu-id="ef933-154">Den **moderna arbets plats tjänsten** är en dynamisk grupp som vi skapar för tjänsten när du registrerar dig.</span><span class="sxs-lookup"><span data-stu-id="ef933-154">The **Modern Workplace Service Accounts** Azure AD group is a dynamic group that we create for the service when you enroll.</span></span> <span data-ttu-id="ef933-155">Du måste komma tillbaka för att utesluta den här gruppen efter registreringen.</span><span class="sxs-lookup"><span data-stu-id="ef933-155">You'll have to come back to exclude this group after enrollment.</span></span> <span data-ttu-id="ef933-156">Mer information om dessa tjänst konton finns i [vanliga rutiner](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span><span class="sxs-lookup"><span data-stu-id="ef933-156">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="ef933-157">**Fel**</span><span class="sxs-lookup"><span data-stu-id="ef933-157">**Error**</span></span>

<span data-ttu-id="ef933-158">Rollen Intune-administratör har inte tillräcklig behörighet för den här kontrollen.</span><span class="sxs-lookup"><span data-stu-id="ef933-158">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="ef933-159">Du behöver också några av de här Azure AD-rollerna för att köra den här kontrollen:</span><span class="sxs-lookup"><span data-stu-id="ef933-159">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="ef933-160">Säkerhets läsare</span><span class="sxs-lookup"><span data-stu-id="ef933-160">Security Reader</span></span>
- <span data-ttu-id="ef933-161">Säkerhets administratör</span><span class="sxs-lookup"><span data-stu-id="ef933-161">Security Administrator</span></span>
- <span data-ttu-id="ef933-162">Administratör för villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="ef933-162">Conditional Access Administrator</span></span>
- <span data-ttu-id="ef933-163">Global läsare</span><span class="sxs-lookup"><span data-stu-id="ef933-163">Global Reader</span></span>
- <span data-ttu-id="ef933-164">Enheter-administratör</span><span class="sxs-lookup"><span data-stu-id="ef933-164">Devices Administrator</span></span>


### <a name="device-compliance-policies"></a><span data-ttu-id="ef933-165">Principer för enhetskompatibilitet</span><span class="sxs-lookup"><span data-stu-id="ef933-165">Device Compliance policies</span></span>

<span data-ttu-id="ef933-166">Principer för hantering av efterlevnadsprinciper i din Azure AD-organisation får inte uppfylla alla hanterade Microsoft-användare.</span><span class="sxs-lookup"><span data-stu-id="ef933-166">Intune Device Compliance policies in your Azure AD organization must not target any Microsoft Managed Desktop users.</span></span>

<span data-ttu-id="ef933-167">**Inte klart**</span><span class="sxs-lookup"><span data-stu-id="ef933-167">**Not ready**</span></span>

<span data-ttu-id="ef933-168">Du har minst en efterlevnadsprincip som är riktad till alla användare.</span><span class="sxs-lookup"><span data-stu-id="ef933-168">You have at least one compliance policy that targets all users.</span></span> <span data-ttu-id="ef933-169">Återställ principen för en viss Azure AD-grupp som inte innehåller några hanterade Microsoft-användare.</span><span class="sxs-lookup"><span data-stu-id="ef933-169">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="ef933-170">Anvisningar finns i [skapa en policy för efterlevnad i Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span><span class="sxs-lookup"><span data-stu-id="ef933-170">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>

<span data-ttu-id="ef933-171">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="ef933-171">**Advisory**</span></span>

<span data-ttu-id="ef933-172">Se till att eventuella efterlevnadsprinciper som du inte har Microsoft-hanterade Skriv bords användare.</span><span class="sxs-lookup"><span data-stu-id="ef933-172">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="ef933-173">Anvisningar finns i [skapa en policy för efterlevnad i Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span><span class="sxs-lookup"><span data-stu-id="ef933-173">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>



### <a name="device-configuration-policies"></a><span data-ttu-id="ef933-174">Konfigurations principer för enheter</span><span class="sxs-lookup"><span data-stu-id="ef933-174">Device Configuration policies</span></span>

<span data-ttu-id="ef933-175">Konfigurations principer för Intune-enheter i din Azure AD-organisation får inte vara riktade till Microsoft Manage Station ära enheter eller användare.</span><span class="sxs-lookup"><span data-stu-id="ef933-175">Intune Device Configuration policies in your Azure AD organization must not target any Microsoft Manage Desktop devices or users.</span></span>

<span data-ttu-id="ef933-176">**Inte klart**</span><span class="sxs-lookup"><span data-stu-id="ef933-176">**Not ready**</span></span>

<span data-ttu-id="ef933-177">Du har minst en konfigurations princip som är riktad till alla användare, alla enheter eller både och.</span><span class="sxs-lookup"><span data-stu-id="ef933-177">You have at least one configuration policy that targets all users, all devices, or both.</span></span> <span data-ttu-id="ef933-178">Återställ principen för en viss Azure AD-grupp som inte innehåller några Microsoft-hanterade Skriv bords enheter.</span><span class="sxs-lookup"><span data-stu-id="ef933-178">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="ef933-179">Anvisningar finns i [skapa en policy för efterlevnad i Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span><span class="sxs-lookup"><span data-stu-id="ef933-179">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>

<span data-ttu-id="ef933-180">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="ef933-180">**Advisory**</span></span>

<span data-ttu-id="ef933-181">Se till att eventuella efterlevnadsprinciper som du inte har Microsoft-hanterade Skriv bords enheter eller-användare.</span><span class="sxs-lookup"><span data-stu-id="ef933-181">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop devices or users.</span></span> <span data-ttu-id="ef933-182">Anvisningar finns i [skapa en policy för efterlevnad i Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span><span class="sxs-lookup"><span data-stu-id="ef933-182">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>



### <a name="device-type-restrictions"></a><span data-ttu-id="ef933-183">Begränsningar för enhets typer</span><span class="sxs-lookup"><span data-stu-id="ef933-183">Device type restrictions</span></span>

<span data-ttu-id="ef933-184">Microsoft Managed Station ära datorer måste tillåtas att registrera i Intune.</span><span class="sxs-lookup"><span data-stu-id="ef933-184">Microsoft Managed Desktop devices must be allowed to enroll in Intune.</span></span>

<span data-ttu-id="ef933-185">**Inte klart**</span><span class="sxs-lookup"><span data-stu-id="ef933-185">**Not ready**</span></span>

<span data-ttu-id="ef933-186">Följ stegen i [Ange registrerings begränsningar](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) för att ändra inställningen till **Tillåt** .</span><span class="sxs-lookup"><span data-stu-id="ef933-186">Follow the steps in [Set enrollment restrictions](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) to change the setting to **Allow** .</span></span>


### <a name="enrollment-status-page"></a><span data-ttu-id="ef933-187">Sidan registrerings status</span><span class="sxs-lookup"><span data-stu-id="ef933-187">Enrollment Status Page</span></span>

<span data-ttu-id="ef933-188">Du har för närvarande sidan registrerings status (ESP) aktive rad.</span><span class="sxs-lookup"><span data-stu-id="ef933-188">You currently have the Enrollment Status Page (ESP) enabled.</span></span> <span data-ttu-id="ef933-189">Om du deltar i den offentliga för hands versionen av den här funktionen kan du ignorera det här objektet.</span><span class="sxs-lookup"><span data-stu-id="ef933-189">If you are participating in the public preview of this feature, you can ignore this item.</span></span> <span data-ttu-id="ef933-190">Mer information finns i förstagångskörningen [med autopilot och sidan registrerings status](../get-started/esp-first-run.md).</span><span class="sxs-lookup"><span data-stu-id="ef933-190">For more information, see [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span></span>

<span data-ttu-id="ef933-191">**Inte klart**</span><span class="sxs-lookup"><span data-stu-id="ef933-191">**Not ready**</span></span>

<span data-ttu-id="ef933-192">Du har aktiverat ESP-standardprofilen för att **Visa konfigurations förlopp för appar och profiler** .</span><span class="sxs-lookup"><span data-stu-id="ef933-192">You have the ESP default profile set to **Show app and profile configuration progress** .</span></span> <span data-ttu-id="ef933-193">Inaktivera den här inställningen genom att följa anvisningarna i [Konfigurera sidan registrerings status](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span><span class="sxs-lookup"><span data-stu-id="ef933-193">Disable this setting by following the steps in [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

<span data-ttu-id="ef933-194">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="ef933-194">**Advisory**</span></span>

<span data-ttu-id="ef933-195">Kontrol lera att alla profiler som har **statusen Visa program-och profil konfiguration** inte är tilldelade någon Azure AD-grupp som innehåller Microsoft Managed Station ära enheter.</span><span class="sxs-lookup"><span data-stu-id="ef933-195">Make sure that any profiles that have the **Show app and profile configuration progress** setting are not assigned to any Azure AD group that includes Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="ef933-196">Mer information finns i [Konfigurera sidan registrerings status](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span><span class="sxs-lookup"><span data-stu-id="ef933-196">For more information, see [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

### <a name="intune-enrollment"></a><span data-ttu-id="ef933-197">Intune-registrering</span><span class="sxs-lookup"><span data-stu-id="ef933-197">Intune enrollment</span></span>

<span data-ttu-id="ef933-198">Windows 10-enheter i din Azure AD-organisation måste registreras automatiskt i Intune.</span><span class="sxs-lookup"><span data-stu-id="ef933-198">Windows 10 devices in your Azure AD organization must be automatically enrolled in Intune.</span></span>

<span data-ttu-id="ef933-199">**Inte klart**</span><span class="sxs-lookup"><span data-stu-id="ef933-199">**Not ready**</span></span>

<span data-ttu-id="ef933-200">Användare i din Azure AD-organisation registreras inte automatiskt i Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="ef933-200">Users in your Azure AD organization aren't automatically enrolled in Microsoft Intune.</span></span> <span data-ttu-id="ef933-201">Ändra omfattningen för MDM-användare till **vissa** eller **alla** .</span><span class="sxs-lookup"><span data-stu-id="ef933-201">Change the MDM User scope to **Some** or **All** .</span></span> <span data-ttu-id="ef933-202">Om du väljer **lite** , kom tillbaka efter registreringen och väljer den **moderna arbets platsen – alla** Azure AD-grupper för **grupper** .</span><span class="sxs-lookup"><span data-stu-id="ef933-202">If you choose **Some** , come back after enrollment and select the **Modern Workplace -All** Azure AD group for **Groups** .</span></span>


### <a name="microsoft-store-for-business"></a><span data-ttu-id="ef933-203">Microsoft Store för företag</span><span class="sxs-lookup"><span data-stu-id="ef933-203">Microsoft Store for Business</span></span>

<span data-ttu-id="ef933-204">Vi använder Microsoft Store för företag så att du kan ladda ned företags Portal för att distribuera vissa program, till exempel Microsoft Project och Microsoft Visio.</span><span class="sxs-lookup"><span data-stu-id="ef933-204">We use Microsoft Store for Business so that you can download Company Portal to deploy some apps, such as Microsoft Project and Microsoft Visio.</span></span>

<span data-ttu-id="ef933-205">**Inte klart**</span><span class="sxs-lookup"><span data-stu-id="ef933-205">**Not ready**</span></span>

<span data-ttu-id="ef933-206">Microsoft Store för företag är antingen inte aktiverat eller synkroniseras inte med Intune.</span><span class="sxs-lookup"><span data-stu-id="ef933-206">Microsoft Store for Business either isn't enabled or isn't synced with Intune.</span></span> <span data-ttu-id="ef933-207">Mer information finns i [så här hanterar du volym köps program från Microsoft Store för företag med Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) och [Installera Intune företags Portal på enheter](../get-started/company-portal.md).</span><span class="sxs-lookup"><span data-stu-id="ef933-207">For more information, see [How to manage volume purchased apps from the Microsoft Store for Business with Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) and [Install Intune Company Portal on on devices](../get-started/company-portal.md).</span></span>

### <a name="multi-factor-authentication"></a><span data-ttu-id="ef933-208">Multifaktorautentisering</span><span class="sxs-lookup"><span data-stu-id="ef933-208">Multi-factor authentication</span></span>

<span data-ttu-id="ef933-209">Multifaktorautentisering får inte på ett oavsiktligt sätt tillämpas på Microsoft Managed Desktop Service-konton.</span><span class="sxs-lookup"><span data-stu-id="ef933-209">Multi-factor authentication must not accidentally be applied to Microsoft Managed Desktop service accounts.</span></span>


<span data-ttu-id="ef933-210">**Inte klart**</span><span class="sxs-lookup"><span data-stu-id="ef933-210">**Not ready**</span></span>

<span data-ttu-id="ef933-211">Du har vissa principer för multifaktorautentisering (MFA) inställda som "obligatoriskt" för principer för villkorsstyrd åtkomst som är tilldelade till alla användare.</span><span class="sxs-lookup"><span data-stu-id="ef933-211">You have some multi-factor authentication (MFA) policies set as "required" for conditional access policies that are assigned to all users.</span></span> <span data-ttu-id="ef933-212">Ändra principen för att använda en tilldelning som är riktad till en viss Azure AD-grupp som inte innehåller Microsoft hanterade Station ära datorer.</span><span class="sxs-lookup"><span data-stu-id="ef933-212">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="ef933-213">Mer information finns i [principer för villkorsstyrd åtkomst](#conditional-access-policies) och [villkorsstyrd åtkomst: Kräv MFA för alla användare](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span><span class="sxs-lookup"><span data-stu-id="ef933-213">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span>

<span data-ttu-id="ef933-214">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="ef933-214">**Advisory**</span></span>

<span data-ttu-id="ef933-215">Se till att alla villkorsstyrda åtkomst principer som kräver MFA exkluderar den **moderna arbets platsen – alla** Azure AD-grupper.</span><span class="sxs-lookup"><span data-stu-id="ef933-215">Make sure that any conditional access policies that require MFA exclude the **Modern Workplace -All** Azure AD group.</span></span> <span data-ttu-id="ef933-216">Mer information finns i [principer för villkorsstyrd åtkomst](#conditional-access-policies) och [villkorsstyrd åtkomst: Kräv MFA för alla användare](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span><span class="sxs-lookup"><span data-stu-id="ef933-216">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span> <span data-ttu-id="ef933-217">Den **moderna arbets platsen – alla** Azure AD-grupper är en dynamisk grupp som vi skapar när du registrerar dig på Microsoft Managed Desktop, så att du måste komma tillbaka till den här gruppen efter registrering.</span><span class="sxs-lookup"><span data-stu-id="ef933-217">The **Modern Workplace -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>

<span data-ttu-id="ef933-218">**Fel**</span><span class="sxs-lookup"><span data-stu-id="ef933-218">**Error**</span></span>

<span data-ttu-id="ef933-219">Rollen Intune-administratör har inte tillräcklig behörighet för den här kontrollen.</span><span class="sxs-lookup"><span data-stu-id="ef933-219">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="ef933-220">Du behöver också några av de här Azure AD-rollerna för att köra den här kontrollen:</span><span class="sxs-lookup"><span data-stu-id="ef933-220">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="ef933-221">Säkerhets läsare</span><span class="sxs-lookup"><span data-stu-id="ef933-221">Security Reader</span></span>
- <span data-ttu-id="ef933-222">Säkerhets administratör</span><span class="sxs-lookup"><span data-stu-id="ef933-222">Security Administrator</span></span>
- <span data-ttu-id="ef933-223">Administratör för villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="ef933-223">Conditional Access Administrator</span></span>
- <span data-ttu-id="ef933-224">Global läsare</span><span class="sxs-lookup"><span data-stu-id="ef933-224">Global Reader</span></span>
- <span data-ttu-id="ef933-225">Enheter-administratör</span><span class="sxs-lookup"><span data-stu-id="ef933-225">Devices Administrator</span></span>


### <a name="powershell-scripts"></a><span data-ttu-id="ef933-226">PowerShell-skript</span><span class="sxs-lookup"><span data-stu-id="ef933-226">PowerShell scripts</span></span>

<span data-ttu-id="ef933-227">Windows PowerShell-skript kan inte tilldelas på ett sätt som riktar sig till Microsoft Managed Station ära enheter.</span><span class="sxs-lookup"><span data-stu-id="ef933-227">Windows PowerShell scripts can't be assigned in a way that would target Microsoft Managed Desktop devices.</span></span>  

<span data-ttu-id="ef933-228">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="ef933-228">**Advisory**</span></span>

<span data-ttu-id="ef933-229">Kontrol lera att Windows PowerShell-skript i din Azure AD-organisation inte har några Microsoft-hanterings enheter eller användare.</span><span class="sxs-lookup"><span data-stu-id="ef933-229">Make sure that Windows PowerShell scripts in your Azure AD organization don't target any Microsoft Manage Desktop devices or users.</span></span> <span data-ttu-id="ef933-230">Mer information finns i [använda PowerShell-skript på Windows 10-enheter i Intune](https://docs.microsoft.com/mem/intune/apps/intune-management-extension).</span><span class="sxs-lookup"><span data-stu-id="ef933-230">For more information, see [Use PowerShell scripts on Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/apps/intune-management-extension).</span></span>

### <a name="region"></a><span data-ttu-id="ef933-231">Region</span><span class="sxs-lookup"><span data-stu-id="ef933-231">Region</span></span>

<span data-ttu-id="ef933-232">Din region måste vara kompatibel med Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="ef933-232">Your region must be supported by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="ef933-233">**Inte klart**</span><span class="sxs-lookup"><span data-stu-id="ef933-233">**Not ready**</span></span>

<span data-ttu-id="ef933-234">Din organisations region för Azure AD stöds för närvarande inte av Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="ef933-234">Your Azure AD organization region isn't currently supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="ef933-235">Mer information finns i [regioner och språk som stöds i Microsoft hanterade skriv bord](../service-description/regions-languages.md).</span><span class="sxs-lookup"><span data-stu-id="ef933-235">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>

<span data-ttu-id="ef933-236">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="ef933-236">**Advisory**</span></span>

<span data-ttu-id="ef933-237">Ett eller flera av de länder där din Azure AD-organisation finns stöds inte av Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="ef933-237">One or more of the countries where your Azure AD organization is located isn't supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="ef933-238">Mer information finns i [regioner och språk som stöds i Microsoft hanterade skriv bord](../service-description/regions-languages.md).</span><span class="sxs-lookup"><span data-stu-id="ef933-238">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>


### <a name="security-baselines"></a><span data-ttu-id="ef933-239">Säkerhets bas linjer</span><span class="sxs-lookup"><span data-stu-id="ef933-239">Security baselines</span></span>

<span data-ttu-id="ef933-240">Principer för säkerhets rikt linjer ska inte vara riktade till enheter som hanteras av Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ef933-240">Security baseline policies should not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="ef933-241">**Inte klart**</span><span class="sxs-lookup"><span data-stu-id="ef933-241">**Not ready**</span></span>

<span data-ttu-id="ef933-242">Du har en säkerhets bas profil som är riktad till alla användare, alla enheter eller både och.</span><span class="sxs-lookup"><span data-stu-id="ef933-242">You have a security baseline profile that targets all users, all devices or both.</span></span> <span data-ttu-id="ef933-243">Ändra principen för att använda en tilldelning som är riktad till en viss Azure AD-grupp som inte innehåller Microsoft hanterade Station ära datorer.</span><span class="sxs-lookup"><span data-stu-id="ef933-243">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="ef933-244">Anvisningar finns i [använda säkerhets bas linjer för att konfigurera Windows 10-enheter i Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span><span class="sxs-lookup"><span data-stu-id="ef933-244">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span>

<span data-ttu-id="ef933-245">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="ef933-245">**Advisory**</span></span>

<span data-ttu-id="ef933-246">Se till att alla principer för säkerhets rikt linjer du har exkluderar Microsoft Managed Station ära enheter.</span><span class="sxs-lookup"><span data-stu-id="ef933-246">Make sure that any security baseline policies you have exclude Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="ef933-247">Anvisningar finns i [använda säkerhets bas linjer för att konfigurera Windows 10-enheter i Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span><span class="sxs-lookup"><span data-stu-id="ef933-247">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span> <span data-ttu-id="ef933-248">**Moderna arbets plats enheter-alla** Azure AD-grupper är en dynamisk grupp som vi skapar när du registrerar dig på Microsoft Managed Desktop, så att du måste komma tillbaka till den här gruppen efter registrering.</span><span class="sxs-lookup"><span data-stu-id="ef933-248">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


### <a name="windows-apps"></a><span data-ttu-id="ef933-249">Windows-appar</span><span class="sxs-lookup"><span data-stu-id="ef933-249">Windows apps</span></span>

<span data-ttu-id="ef933-250">Granska de program du vill att Microsoft Managed Desktop-användarna ska ha.</span><span class="sxs-lookup"><span data-stu-id="ef933-250">Review apps you want your Microsoft Managed Desktop users to have.</span></span>

<span data-ttu-id="ef933-251">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="ef933-251">**Advisory**</span></span>

<span data-ttu-id="ef933-252">Du bör förbereda en inventering av de program som du vill att Microsoft Managed Desktop-användarna ska ha.</span><span class="sxs-lookup"><span data-stu-id="ef933-252">You should prepare an inventory of the apps that you want your Microsoft Managed Desktop users to have.</span></span> <span data-ttu-id="ef933-253">Kontrol lera att dessa appar kan distribueras av Intune.</span><span class="sxs-lookup"><span data-stu-id="ef933-253">Make sure these apps can be deployed by Intune.</span></span> <span data-ttu-id="ef933-254">Mer information finns i [program på Microsoft Managed Desktop](apps.md).</span><span class="sxs-lookup"><span data-stu-id="ef933-254">For more information, see [Apps in Microsoft Managed Desktop](apps.md).</span></span>

<span data-ttu-id="ef933-255">Du kan be din Microsoft-representant om en fråga i Microsoft Endpoint Configuration Manager att identifiera de program som är redo att migreras till Intune eller behöver justeras.</span><span class="sxs-lookup"><span data-stu-id="ef933-255">You can ask your Microsoft account representative for a query in Microsoft Endpoint Configuration Manager to identify those apps that are ready to migrate to Intune or need adjustment.</span></span>


### <a name="windows-hello-for-business"></a><span data-ttu-id="ef933-256">Windows Hello för företag</span><span class="sxs-lookup"><span data-stu-id="ef933-256">Windows Hello for Business</span></span>

<span data-ttu-id="ef933-257">Microsoft Managed Desktop kräver att Windows Hello för företag aktive ras.</span><span class="sxs-lookup"><span data-stu-id="ef933-257">Microsoft Managed Desktop requires Windows Hello for Business to be enabled.</span></span>

<span data-ttu-id="ef933-258">**Inte klart**</span><span class="sxs-lookup"><span data-stu-id="ef933-258">**Not ready**</span></span>

<span data-ttu-id="ef933-259">Windows Hello för företag är inaktiverat.</span><span class="sxs-lookup"><span data-stu-id="ef933-259">Windows Hello for Business is disabled.</span></span> <span data-ttu-id="ef933-260">Aktivera den genom att följa anvisningarna i [skapa en Windows Hello för företag-princip](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span><span class="sxs-lookup"><span data-stu-id="ef933-260">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span></span>

<span data-ttu-id="ef933-261">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="ef933-261">**Advisory**</span></span>

<span data-ttu-id="ef933-262">Windows Hello för företag är inte konfigurerat.</span><span class="sxs-lookup"><span data-stu-id="ef933-262">Windows Hello for Business is not set up.</span></span> <span data-ttu-id="ef933-263">Aktivera den genom att följa anvisningarna i [skapa en Windows Hello för företag-policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).</span><span class="sxs-lookup"><span data-stu-id="ef933-263">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).</span></span>


### <a name="windows-10-update-rings"></a><span data-ttu-id="ef933-264">Windows 10-uppdaterings ringar</span><span class="sxs-lookup"><span data-stu-id="ef933-264">Windows 10 update rings</span></span>

<span data-ttu-id="ef933-265">Din "Windows 10 Update ring"-princip i Intune får inte uppfylla alla hanterade Microsoft-enheter.</span><span class="sxs-lookup"><span data-stu-id="ef933-265">Your "Windows 10 update ring" policy in Intune must not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="ef933-266">**Inte klart**</span><span class="sxs-lookup"><span data-stu-id="ef933-266">**Not ready**</span></span>

<span data-ttu-id="ef933-267">Du har en "uppdatera ring"-princip som är riktad till alla enheter, alla användare eller både och.</span><span class="sxs-lookup"><span data-stu-id="ef933-267">You have an "update ring" policy that targets all devices, all users, or both.</span></span> <span data-ttu-id="ef933-268">Ändra principen för att använda en tilldelning som är riktad till en viss Azure AD-grupp som inte innehåller Microsoft hanterade Station ära datorer.</span><span class="sxs-lookup"><span data-stu-id="ef933-268">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="ef933-269">Anvisningar finns i [hantera program uppdateringar för Windows 10 i Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span><span class="sxs-lookup"><span data-stu-id="ef933-269">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span>

<span data-ttu-id="ef933-270">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="ef933-270">**Advisory**</span></span>

<span data-ttu-id="ef933-271">Se till att eventuella uppdaterings rings principer du har exkluderar den **moderna arbets platsen – alla** Azure AD-grupper.</span><span class="sxs-lookup"><span data-stu-id="ef933-271">Make sure that any update ring policies you have exclude the **Modern Workplace -All** Azure AD group.</span></span> <span data-ttu-id="ef933-272">Anvisningar finns i [hantera program uppdateringar för Windows 10 i Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span><span class="sxs-lookup"><span data-stu-id="ef933-272">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span> <span data-ttu-id="ef933-273">**Moderna arbets plats enheter-alla** Azure AD-grupper är en dynamisk grupp som vi skapar när du registrerar dig på Microsoft Managed Desktop, så att du måste komma tillbaka till den här gruppen efter registrering.</span><span class="sxs-lookup"><span data-stu-id="ef933-273">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


## <a name="azure-active-directory-settings"></a><span data-ttu-id="ef933-274">Azure Active Directory-inställningar</span><span class="sxs-lookup"><span data-stu-id="ef933-274">Azure Active Directory settings</span></span>


### <a name="ad-hoc-subscriptions"></a><span data-ttu-id="ef933-275">Ad hoc-abonnemang</span><span class="sxs-lookup"><span data-stu-id="ef933-275">Ad hoc subscriptions</span></span>

<span data-ttu-id="ef933-276">Här beskrivs hur du kontrollerar en inställning som (om värdet är "falskt") kan hindra företags tillstånd från att fungera korrekt.</span><span class="sxs-lookup"><span data-stu-id="ef933-276">Advises how to check a setting that (if set to "false") might prevent Enterprise State Roaming from working correctly.</span></span>

<span data-ttu-id="ef933-277">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="ef933-277">**Advisory**</span></span>

<span data-ttu-id="ef933-278">Kontrol lera att **AllowAdHocSubscriptions** är inställt på **True** .</span><span class="sxs-lookup"><span data-stu-id="ef933-278">Ensure that **AllowAdHocSubscriptions** is set to **True** .</span></span> <span data-ttu-id="ef933-279">I annat fall kanske företags statusen roaming inte fungerar.</span><span class="sxs-lookup"><span data-stu-id="ef933-279">Otherwise, Enterprise State Roaming might not work.</span></span> <span data-ttu-id="ef933-280">Mer information finns i [set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="ef933-280">For more information, see [Set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).</span></span>


### <a name="enterprise-state-roaming"></a><span data-ttu-id="ef933-281">Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="ef933-281">Enterprise State Roaming</span></span>

<span data-ttu-id="ef933-282">Roaming för företags status bör vara aktiverat.</span><span class="sxs-lookup"><span data-stu-id="ef933-282">Enterprise State Roaming should be enabled.</span></span>

<span data-ttu-id="ef933-283">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="ef933-283">**Advisory**</span></span>

<span data-ttu-id="ef933-284">Kontrol lera att organisationens centrala nätverks tillstånd är aktiverat för **alla** eller för **markerade** grupper.</span><span class="sxs-lookup"><span data-stu-id="ef933-284">Make sure that Enterprise State Roaming is enabled for **All** or for **Selected** groups.</span></span> <span data-ttu-id="ef933-285">Mer information finns i [Aktivera roaming för företags tillstånd i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable).</span><span class="sxs-lookup"><span data-stu-id="ef933-285">For more information, see [Enable Enterprise State Roaming in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable).</span></span>

### <a name="licenses"></a><span data-ttu-id="ef933-286">Licenser</span><span class="sxs-lookup"><span data-stu-id="ef933-286">Licenses</span></span>

<span data-ttu-id="ef933-287">Det krävs flera olika licenser för att använda Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="ef933-287">A number of licenses are required to use Microsoft Managed Desktop.</span></span>

<span data-ttu-id="ef933-288">**Inte klart**</span><span class="sxs-lookup"><span data-stu-id="ef933-288">**Not Ready**</span></span>

<span data-ttu-id="ef933-289">Du har inte alla licenser som du behöver för att använda Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="ef933-289">You don't have all the licenses you need to use Microsoft Managed Desktop.</span></span> <span data-ttu-id="ef933-290">Mer information finns i [Microsoft hanterad Skriv bords teknik](../intro/technologies.md) och [mer om licenser](prerequisites.md#more-about-licenses).</span><span class="sxs-lookup"><span data-stu-id="ef933-290">For more information, see [Microsoft Managed Desktop technologies](../intro/technologies.md) and [More about licenses](prerequisites.md#more-about-licenses).</span></span>


### <a name="security-account-names"></a><span data-ttu-id="ef933-291">Namn på säkerhets konton</span><span class="sxs-lookup"><span data-stu-id="ef933-291">Security account names</span></span>

<span data-ttu-id="ef933-292">Vissa namn på säkerhets konton kan vara i konflikt med dem som har skapats av Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="ef933-292">Certain security account names could conflict with ones created by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="ef933-293">**Inte klart**</span><span class="sxs-lookup"><span data-stu-id="ef933-293">**Not ready**</span></span>

<span data-ttu-id="ef933-294">Du har minst ett konto namn som är oförenliga med dem som skapas av Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="ef933-294">You have at least one account name that will conflict with ones created by Microsoft Managed Desktop.</span></span> <span data-ttu-id="ef933-295">Arbeta med ditt Microsoft-konto för att utesluta dessa konto namn.</span><span class="sxs-lookup"><span data-stu-id="ef933-295">Work with your Microsoft account representative to exclude these account names.</span></span>


### <a name="security-administrator-roles"></a><span data-ttu-id="ef933-296">Säkerhets administratörs roller</span><span class="sxs-lookup"><span data-stu-id="ef933-296">Security administrator roles</span></span>

<span data-ttu-id="ef933-297">Användare med vissa säkerhets roller måste ha kopplade till dem i Microsoft Defender för slut punkter.</span><span class="sxs-lookup"><span data-stu-id="ef933-297">Users with certain security roles must have those assigned in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="ef933-298">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="ef933-298">**Advisory**</span></span>

<span data-ttu-id="ef933-299">Om du har någon av de här rollerna i din Azure AD-organisation kontrollerar du att de också har tilldelats dessa roller i Microsoft Defender för slut punkter.</span><span class="sxs-lookup"><span data-stu-id="ef933-299">If you have any of these roles assigned in your Azure AD organization, make sure they also have these roles assigned in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="ef933-300">Annars kommer administratörer med dessa roller inte att kunna använda administrations portalen.</span><span class="sxs-lookup"><span data-stu-id="ef933-300">Otherwise, administrators with these roles won't be able to access the Admin portal.</span></span>

- <span data-ttu-id="ef933-301">Säkerhets läsare</span><span class="sxs-lookup"><span data-stu-id="ef933-301">Security Reader</span></span>
- <span data-ttu-id="ef933-302">Säkerhets ansvarig</span><span class="sxs-lookup"><span data-stu-id="ef933-302">Security Operator</span></span>
- <span data-ttu-id="ef933-303">Global läsare</span><span class="sxs-lookup"><span data-stu-id="ef933-303">Global Reader</span></span>

<span data-ttu-id="ef933-304">Mer information finns i [skapa och hantera roller för rollbaserad åtkomst kontroll](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles).</span><span class="sxs-lookup"><span data-stu-id="ef933-304">For more information, see [Create and manage roles for role-based access control](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles).</span></span>


### <a name="security-default"></a><span data-ttu-id="ef933-305">Säkerhets standard</span><span class="sxs-lookup"><span data-stu-id="ef933-305">Security default</span></span>

<span data-ttu-id="ef933-306">Säkerhets inställningar i Azure Active Directory kommer inte att hantera dina enheter på Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ef933-306">Security defaults in Azure Active Directory will prevent Microsoft Managed Desktop from managing your devices.</span></span>

<span data-ttu-id="ef933-307">**Inte klart**</span><span class="sxs-lookup"><span data-stu-id="ef933-307">**Not ready**</span></span>

<span data-ttu-id="ef933-308">Säkerhets inställningarna är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="ef933-308">You have Security defaults turned on.</span></span> <span data-ttu-id="ef933-309">Inaktivera säkerhets standarder och konfigurera villkorsstyrda åtkomst principer.</span><span class="sxs-lookup"><span data-stu-id="ef933-309">Turn off Security defaults and set up conditional access policies.</span></span> <span data-ttu-id="ef933-310">Mer information finns i [vanliga principer för villkorsstyrd åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span><span class="sxs-lookup"><span data-stu-id="ef933-310">For more information, see [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span></span>

### <a name="self-service-password-reset"></a><span data-ttu-id="ef933-311">Självbetjäning för återställning av lösen ord</span><span class="sxs-lookup"><span data-stu-id="ef933-311">Self-service Password Reset</span></span>

<span data-ttu-id="ef933-312">Självbetjäning för återställning av lösen ord (SSPR) måste aktive ras.</span><span class="sxs-lookup"><span data-stu-id="ef933-312">Self-service Password Reset (SSPR) must be enabled.</span></span>

<span data-ttu-id="ef933-313">**Inte klart**</span><span class="sxs-lookup"><span data-stu-id="ef933-313">**Not ready**</span></span>

<span data-ttu-id="ef933-314">SSPR måste vara aktiverat för alla användare.</span><span class="sxs-lookup"><span data-stu-id="ef933-314">SSPR must be enabled for all users.</span></span> <span data-ttu-id="ef933-315">Om det inte är det kan inte Microsoft Managed Desktop-tjänsten fungera.</span><span class="sxs-lookup"><span data-stu-id="ef933-315">If it isn't, the Microsoft Managed Desktop service accounts can't work.</span></span> <span data-ttu-id="ef933-316">Mer information finns i [själv studie kursen: Låt användare låsa upp sina konton eller återställa lösen ord med hjälp av återställning av Azure Active Directory Self-Service](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span><span class="sxs-lookup"><span data-stu-id="ef933-316">For more information, see [Tutorial: Enable users to unlock their account or reset passwords using Azure Active Directory self-service password reset](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span></span>

<span data-ttu-id="ef933-317">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="ef933-317">**Advisory**</span></span>

<span data-ttu-id="ef933-318">Kontrol lera att SSPR **valda** inställningar innehåller Microsoft Managed Station ära datorer.</span><span class="sxs-lookup"><span data-stu-id="ef933-318">Make sure that the SSPR **Selected** setting includes Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="ef933-319">**Fel**</span><span class="sxs-lookup"><span data-stu-id="ef933-319">**Error**</span></span>

<span data-ttu-id="ef933-320">Rollen Intune-administratör har inte tillräcklig behörighet för den här kontrollen.</span><span class="sxs-lookup"><span data-stu-id="ef933-320">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="ef933-321">Du behöver också ha den rapport läsare i Azure AD-rollen som tilldelats för att köra den här kontrollen.</span><span class="sxs-lookup"><span data-stu-id="ef933-321">You'll also need the Reports Reader Azure AD role assigned to run this check.</span></span>


### <a name="standard-user-role"></a><span data-ttu-id="ef933-322">Standard användar roll</span><span class="sxs-lookup"><span data-stu-id="ef933-322">Standard user role</span></span>

<span data-ttu-id="ef933-323">Microsoft Managed Desktop-användare ska vara vanliga användare utan lokala administratörs behörigheter.</span><span class="sxs-lookup"><span data-stu-id="ef933-323">Microsoft Managed Desktop users should be standard users without local administrator privileges.</span></span> <span data-ttu-id="ef933-324">De tilldelas en standard användar roll när de startar sin Microsoft-hanterade Station.</span><span class="sxs-lookup"><span data-stu-id="ef933-324">They'll be assigned a standard user role when they start their Microsoft Managed Desktop device.</span></span>

<span data-ttu-id="ef933-325">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="ef933-325">**Advisory**</span></span>

<span data-ttu-id="ef933-326">Microsoft Managed Station ära datorer bör inte ha lokala administratörs behörigheter innan de registreras.</span><span class="sxs-lookup"><span data-stu-id="ef933-326">Microsoft Managed Desktop users shouldn't have local administrator privileges prior to enrolling.</span></span>

## <a name="microsoft-365-apps-for-enterprise"></a><span data-ttu-id="ef933-327"> Microsoft 365 Apps för företag</span><span class="sxs-lookup"><span data-stu-id="ef933-327">Microsoft 365 Apps for enterprise</span></span>

### <a name="onedrive-for-business"></a><span data-ttu-id="ef933-328">OneDrive för företag</span><span class="sxs-lookup"><span data-stu-id="ef933-328">OneDrive for Business</span></span>

<span data-ttu-id="ef933-329">Inställningen **Tillåt synkronisering endast på datorer som är anslutna till vissa domäner** visas i konflikt med Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="ef933-329">The **Allow syncing only on PCs joined to specific domains** setting will conflict with Microsoft Managed Desktop.</span></span>

<span data-ttu-id="ef933-330">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="ef933-330">**Advisory**</span></span>

<span data-ttu-id="ef933-331">Du använder alternativet **Tillåt synkronisering endast på datorer som är anslutna till vissa domän** inställningar.</span><span class="sxs-lookup"><span data-stu-id="ef933-331">You're using the **Allow syncing only on PCs joined to specific domains** setting.</span></span> <span data-ttu-id="ef933-332">Den här inställningen fungerar inte med Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="ef933-332">This setting won't work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="ef933-333">Inaktivera den här inställningen och konfigurera i stället OneDrive för företag för användning av villkorsstyrd åtkomst policy.</span><span class="sxs-lookup"><span data-stu-id="ef933-333">Disable this setting, and instead set up OneDrive for Business to use a conditional access policy.</span></span> <span data-ttu-id="ef933-334">Se [Planera en distribution för villkorlig åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) för hjälp.</span><span class="sxs-lookup"><span data-stu-id="ef933-334">See [Plan a Conditional Access deployment](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) for help.</span></span>

