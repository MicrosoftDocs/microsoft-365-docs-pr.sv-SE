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
ms.openlocfilehash: 2c9638dc7b8c6d095b87cf81114f3812c8362597
ms.sourcegitcommit: 3b1bd8aa1430bc9565743a446bbc27b199f30f73
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/22/2020
ms.locfileid: "48656157"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a><span data-ttu-id="88879-104">Åtgärda problem som upptäckts av verktyget för bedömning av beredskap</span><span class="sxs-lookup"><span data-stu-id="88879-104">Fix issues found by the readiness assessment tool</span></span>

<span data-ttu-id="88879-105">För varje kontroll rapporteras ett av tre möjliga resultat:</span><span class="sxs-lookup"><span data-stu-id="88879-105">For each check, the tool will report one of three possible results:</span></span>


|<span data-ttu-id="88879-106">Resultat</span><span class="sxs-lookup"><span data-stu-id="88879-106">Result</span></span>  |<span data-ttu-id="88879-107">Betydelse</span><span class="sxs-lookup"><span data-stu-id="88879-107">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="88879-108">Förbereder</span><span class="sxs-lookup"><span data-stu-id="88879-108">Ready</span></span>     | <span data-ttu-id="88879-109">Ingen åtgärd krävs innan du slutför registreringen.</span><span class="sxs-lookup"><span data-stu-id="88879-109">No action is required before completing enrollment.</span></span>        |
|<span data-ttu-id="88879-110">Rådgivare</span><span class="sxs-lookup"><span data-stu-id="88879-110">Advisory</span></span>    | <span data-ttu-id="88879-111">Följ stegen i verktyget eller den här artikeln för att få bästa möjliga upplevelse av registrering och användare.</span><span class="sxs-lookup"><span data-stu-id="88879-111">Follow the steps in the tool or this article for the best experience with enrollment and for users.</span></span> <span data-ttu-id="88879-112">Du *kan* slutföra registreringen, men du måste åtgärda dessa problem innan du distribuerar den första enheten.</span><span class="sxs-lookup"><span data-stu-id="88879-112">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="88879-113">Inte klart</span><span class="sxs-lookup"><span data-stu-id="88879-113">Not ready</span></span> | <span data-ttu-id="88879-114">*Registreringen Miss lyckas om du inte åtgärdar dessa problem.*</span><span class="sxs-lookup"><span data-stu-id="88879-114">*Enrollment will fail if you don't fix these issues.*</span></span> <span data-ttu-id="88879-115">Följ stegen i verktyget eller den här artikeln för att åtgärda dem.</span><span class="sxs-lookup"><span data-stu-id="88879-115">Follow the steps in the tool or this article to resolve them.</span></span>        |

## <a name="microsoft-intune-settings"></a><span data-ttu-id="88879-116">Microsoft Intune-inställningar</span><span class="sxs-lookup"><span data-stu-id="88879-116">Microsoft Intune settings</span></span>

### <a name="autopilot-deployment-profile"></a><span data-ttu-id="88879-117">Distributions profil för autopilot</span><span class="sxs-lookup"><span data-stu-id="88879-117">Autopilot deployment profile</span></span>

<span data-ttu-id="88879-118">Du bör inte ha några befintliga autopilot-profiler som riktar sig till tilldelade eller dynamiska grupper som används av Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="88879-118">You shouldn't have any existing Autopilot profiles that target assigned or dynamic groups used by Microsoft Managed Desktop.</span></span> <span data-ttu-id="88879-119">Microsoft Managed Desktop använder autopilot för att etablera nya enheter.</span><span class="sxs-lookup"><span data-stu-id="88879-119">Microsoft Managed Desktop uses Autopilot to provision new devices.</span></span>

<span data-ttu-id="88879-120">**Inte klart**</span><span class="sxs-lookup"><span data-stu-id="88879-120">**Not ready**</span></span>

<span data-ttu-id="88879-121">Du har en autopilot-profil som kopplats till alla enheter.</span><span class="sxs-lookup"><span data-stu-id="88879-121">You have an Autopilot profile that is assigned to all devices.</span></span> <span data-ttu-id="88879-122">Anvisningar finns i [registrera Windows-enheter i Intune med hjälp av Windows autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span><span class="sxs-lookup"><span data-stu-id="88879-122">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="88879-123">Efter Microsoft Managed Desktop-registrering ställer du in autopilot-principen så att den **moderna arbets ytan visas-alla** Azure AD-grupper.</span><span class="sxs-lookup"><span data-stu-id="88879-123">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>

<span data-ttu-id="88879-124">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="88879-124">**Advisory**</span></span>

<span data-ttu-id="88879-125">Se till att dina autopilot-profiler är riktade till en tilldelad eller dynamisk Azure AD-grupp som inte innehåller Microsoft Managed Station ära enheter som kommer att skapas vid registrering.</span><span class="sxs-lookup"><span data-stu-id="88879-125">Make sure that your Autopilot profiles target an assigned or dynamic Azure AD group that doesn't include Microsoft Managed Desktop devices that will be created at enrollment.</span></span> <span data-ttu-id="88879-126">Anvisningar finns i [registrera Windows-enheter i Intune med hjälp av Windows autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span><span class="sxs-lookup"><span data-stu-id="88879-126">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="88879-127">Efter Microsoft Managed Desktop-registrering ställer du in autopilot-principen så att den **moderna arbets ytan visas-alla** Azure AD-grupper.</span><span class="sxs-lookup"><span data-stu-id="88879-127">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>


### <a name="certificate-connectors"></a><span data-ttu-id="88879-128">Certifikat anslutningar</span><span class="sxs-lookup"><span data-stu-id="88879-128">Certificate connectors</span></span>

<span data-ttu-id="88879-129">Om du har några certifikat anslutningar som används av de enheter som du vill registrera på Microsoft Managed Desktop kan de inte ha några fel.</span><span class="sxs-lookup"><span data-stu-id="88879-129">If you have any certificate connectors used by the devices you want to enroll in Microsoft Managed Desktop, the connectors cannot have any errors.</span></span> <span data-ttu-id="88879-130">Endast en av följande rådgivare kommer att gälla för din situation, så kolla dem noggrant.</span><span class="sxs-lookup"><span data-stu-id="88879-130">Only one of the following advisories will apply to your situation, so check them carefully.</span></span>

<span data-ttu-id="88879-131">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="88879-131">**Advisory**</span></span>

<span data-ttu-id="88879-132">Det finns inga certifikat kopplingar.</span><span class="sxs-lookup"><span data-stu-id="88879-132">No certificate connectors are present.</span></span> <span data-ttu-id="88879-133">Det är möjligt att du inte behöver några kopplingar, men du bör utvärdera om du kan behöva vissa för nätverks anslutningen till Microsoft Managed Station ära datorer.</span><span class="sxs-lookup"><span data-stu-id="88879-133">It's possible you don't need any connectors, but you should evaluate whether you might need some for network connectivity to Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="88879-134">Mer information finns i [förbereda certifikat och nätverks profiler för Microsoft Managed Desktop](certs-wifi-lan.md).</span><span class="sxs-lookup"><span data-stu-id="88879-134">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

<span data-ttu-id="88879-135">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="88879-135">**Advisory**</span></span>

<span data-ttu-id="88879-136">Minst ett certifikat har ett fel.</span><span class="sxs-lookup"><span data-stu-id="88879-136">At least one certificate connector has an error.</span></span> <span data-ttu-id="88879-137">Om du behöver den här kopplingen för anslutning till Microsoft-hanterade Skriv bords enheter måste du lösa problemet.</span><span class="sxs-lookup"><span data-stu-id="88879-137">If you need this connector for connectivity to Microsoft Managed Desktop devices, you must resolve the error.</span></span> <span data-ttu-id="88879-138">Mer information finns i [förbereda certifikat och nätverks profiler för Microsoft Managed Desktop](certs-wifi-lan.md).</span><span class="sxs-lookup"><span data-stu-id="88879-138">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


<span data-ttu-id="88879-139">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="88879-139">**Advisory**</span></span>

<span data-ttu-id="88879-140">Du har minst en certifikatanslutningsappen och inga fel rapporteras.</span><span class="sxs-lookup"><span data-stu-id="88879-140">You have at least one certificate connector and no errors are reported.</span></span> <span data-ttu-id="88879-141">Men det kan hända att du måste skapa en profil för att återanvända Connector för Microsoft-hanterade Station ära datorer.</span><span class="sxs-lookup"><span data-stu-id="88879-141">However, you might need to create a profile to reuse the connector for Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="88879-142">Mer information finns i [förbereda certifikat och nätverks profiler för Microsoft Managed Desktop](certs-wifi-lan.md).</span><span class="sxs-lookup"><span data-stu-id="88879-142">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


### <a name="conditional-access-policies"></a><span data-ttu-id="88879-143">Principer för villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="88879-143">Conditional access policies</span></span>

<span data-ttu-id="88879-144">Principer för villkorsstyrd åtkomst i din Azure AD-organisation får inte vara riktade till Microsoft Manage Desktop-användare.</span><span class="sxs-lookup"><span data-stu-id="88879-144">Conditional access policies in your Azure AD organization must not target any Microsoft Manage Desktop users.</span></span>

<span data-ttu-id="88879-145">**Inte klart**</span><span class="sxs-lookup"><span data-stu-id="88879-145">**Not ready**</span></span>

<span data-ttu-id="88879-146">Du har minst en princip för villkorsstyrd åtkomst som är riktad till alla användare.</span><span class="sxs-lookup"><span data-stu-id="88879-146">You have at least one conditional access policy that targets all users.</span></span> <span data-ttu-id="88879-147">Återställ principen för en viss Azure AD-grupp som inte innehåller Azure AD-gruppen av Microsoft Managed Desktop Service-konton som kommer att skapas vid registrering.</span><span class="sxs-lookup"><span data-stu-id="88879-147">Reset the policy to target a specific Azure AD group that does not include the Azure AD group of Microsoft Managed Desktop service accounts that will be created at enrollment.</span></span> <span data-ttu-id="88879-148">Anvisningar finns i [villkorlig åtkomst: användare och grupper](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span><span class="sxs-lookup"><span data-stu-id="88879-148">For steps, see [Conditional Access: Users and groups](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span></span>

<span data-ttu-id="88879-149">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="88879-149">**Advisory**</span></span>

<span data-ttu-id="88879-150">Se till att alla principer för villkorsstyrd åtkomst du har exkluderar den **moderna arbets plats tjänstens konton** Azure AD-grupp.</span><span class="sxs-lookup"><span data-stu-id="88879-150">Make sure that any conditional access policies you have exclude the **Modern Workplace Service Accounts** Azure AD group.</span></span> <span data-ttu-id="88879-151">Anvisningar finns i [Justera villkorlig åtkomst](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access).</span><span class="sxs-lookup"><span data-stu-id="88879-151">For steps, see [Adjust conditional access](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access).</span></span> <span data-ttu-id="88879-152">Den **moderna arbets plats tjänsten** är en dynamisk grupp som vi skapar för tjänsten när du registrerar dig.</span><span class="sxs-lookup"><span data-stu-id="88879-152">The **Modern Workplace Service Accounts** Azure AD group is a dynamic group that we create for the service when you enroll.</span></span> <span data-ttu-id="88879-153">Du måste komma tillbaka för att utesluta den här gruppen efter registreringen.</span><span class="sxs-lookup"><span data-stu-id="88879-153">You'll have to come back to exclude this group after enrollment.</span></span> <span data-ttu-id="88879-154">Mer information om dessa tjänst konton finns i [vanliga rutiner](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span><span class="sxs-lookup"><span data-stu-id="88879-154">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>


### <a name="device-compliance-policies"></a><span data-ttu-id="88879-155">Principer för enhetskompatibilitet</span><span class="sxs-lookup"><span data-stu-id="88879-155">Device Compliance policies</span></span>

<span data-ttu-id="88879-156">Principer för hantering av efterlevnadsprinciper i din Azure AD-organisation får inte uppfylla alla hanterade Microsoft-användare.</span><span class="sxs-lookup"><span data-stu-id="88879-156">Intune Device Compliance policies in your Azure AD organization must not target any Microsoft Managed Desktop users.</span></span>

<span data-ttu-id="88879-157">**Inte klart**</span><span class="sxs-lookup"><span data-stu-id="88879-157">**Not ready**</span></span>

<span data-ttu-id="88879-158">Du har minst en efterlevnadsprincip som är riktad till alla användare.</span><span class="sxs-lookup"><span data-stu-id="88879-158">You have at least one compliance policy that targets all users.</span></span> <span data-ttu-id="88879-159">Återställ principen för en viss Azure AD-grupp som inte innehåller några hanterade Microsoft-användare.</span><span class="sxs-lookup"><span data-stu-id="88879-159">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="88879-160">Anvisningar finns i [skapa en policy för efterlevnad i Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span><span class="sxs-lookup"><span data-stu-id="88879-160">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>

<span data-ttu-id="88879-161">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="88879-161">**Advisory**</span></span>

<span data-ttu-id="88879-162">Se till att eventuella efterlevnadsprinciper som du inte har Microsoft-hanterade Skriv bords användare.</span><span class="sxs-lookup"><span data-stu-id="88879-162">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="88879-163">Anvisningar finns i [skapa en policy för efterlevnad i Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span><span class="sxs-lookup"><span data-stu-id="88879-163">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>



### <a name="device-configuration-policies"></a><span data-ttu-id="88879-164">Konfigurations principer för enheter</span><span class="sxs-lookup"><span data-stu-id="88879-164">Device Configuration policies</span></span>

<span data-ttu-id="88879-165">Konfigurations principer för Intune-enheter i din Azure AD-organisation får inte vara riktade till Microsoft Manage Station ära enheter eller användare.</span><span class="sxs-lookup"><span data-stu-id="88879-165">Intune Device Configuration policies in your Azure AD organization must not target any Microsoft Manage Desktop devices or users.</span></span>

<span data-ttu-id="88879-166">**Inte klart**</span><span class="sxs-lookup"><span data-stu-id="88879-166">**Not ready**</span></span>

<span data-ttu-id="88879-167">Du har minst en konfigurations princip som är riktad till alla användare, alla enheter eller både och.</span><span class="sxs-lookup"><span data-stu-id="88879-167">You have at least one configuration policy that targets all users, all devices, or both.</span></span> <span data-ttu-id="88879-168">Återställ principen för en viss Azure AD-grupp som inte innehåller några Microsoft-hanterade Skriv bords enheter.</span><span class="sxs-lookup"><span data-stu-id="88879-168">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="88879-169">Anvisningar finns i [skapa en policy för efterlevnad i Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span><span class="sxs-lookup"><span data-stu-id="88879-169">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>

<span data-ttu-id="88879-170">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="88879-170">**Advisory**</span></span>

<span data-ttu-id="88879-171">Se till att eventuella efterlevnadsprinciper som du inte har Microsoft-hanterade Skriv bords enheter eller-användare.</span><span class="sxs-lookup"><span data-stu-id="88879-171">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop devices or users.</span></span> <span data-ttu-id="88879-172">Anvisningar finns i [skapa en policy för efterlevnad i Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span><span class="sxs-lookup"><span data-stu-id="88879-172">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>



### <a name="device-type-restrictions"></a><span data-ttu-id="88879-173">Begränsningar för enhets typer</span><span class="sxs-lookup"><span data-stu-id="88879-173">Device type restrictions</span></span>

<span data-ttu-id="88879-174">Microsoft Managed Station ära datorer måste tillåtas att registrera i Intune.</span><span class="sxs-lookup"><span data-stu-id="88879-174">Microsoft Managed Desktop devices must be allowed to enroll in Intune.</span></span>

<span data-ttu-id="88879-175">**Inte klart**</span><span class="sxs-lookup"><span data-stu-id="88879-175">**Not ready**</span></span>

<span data-ttu-id="88879-176">Följ stegen i [Ange registrerings begränsningar](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) för att ändra inställningen till **Tillåt**.</span><span class="sxs-lookup"><span data-stu-id="88879-176">Follow the steps in [Set enrollment restrictions](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) to change the setting to **Allow**.</span></span>


### <a name="enrollment-status-page"></a><span data-ttu-id="88879-177">Sidan registrerings status</span><span class="sxs-lookup"><span data-stu-id="88879-177">Enrollment Status Page</span></span>

<span data-ttu-id="88879-178">Du har för närvarande sidan registrerings status (ESP) aktive rad.</span><span class="sxs-lookup"><span data-stu-id="88879-178">You currently have the Enrollment Status Page (ESP) enabled.</span></span> <span data-ttu-id="88879-179">Om du deltar i den offentliga för hands versionen av den här funktionen kan du ignorera det här objektet.</span><span class="sxs-lookup"><span data-stu-id="88879-179">If you are participating in the public preview of this feature, you can ignore this item.</span></span> <span data-ttu-id="88879-180">Mer information finns i förstagångskörningen [med autopilot och sidan registrerings status](../get-started/esp-first-run.md).</span><span class="sxs-lookup"><span data-stu-id="88879-180">For more information, see [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span></span>

<span data-ttu-id="88879-181">**Inte klart**</span><span class="sxs-lookup"><span data-stu-id="88879-181">**Not ready**</span></span>

<span data-ttu-id="88879-182">Du har aktiverat ESP-standardprofilen för att **Visa konfigurations förlopp för appar och profiler**.</span><span class="sxs-lookup"><span data-stu-id="88879-182">You have the ESP default profile set to **Show app and profile configuration progress**.</span></span> <span data-ttu-id="88879-183">Inaktivera den här inställningen genom att följa anvisningarna i [Konfigurera sidan registrerings status](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span><span class="sxs-lookup"><span data-stu-id="88879-183">Disable this setting by following the steps in [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

<span data-ttu-id="88879-184">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="88879-184">**Advisory**</span></span>

<span data-ttu-id="88879-185">Kontrol lera att alla profiler som har **statusen Visa program-och profil konfiguration** inte är tilldelade någon Azure AD-grupp som innehåller Microsoft Managed Station ära enheter.</span><span class="sxs-lookup"><span data-stu-id="88879-185">Make sure that any profiles that have the **Show app and profile configuration progress** setting are not assigned to any Azure AD group that includes Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="88879-186">Mer information finns i [Konfigurera sidan registrerings status](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span><span class="sxs-lookup"><span data-stu-id="88879-186">For more information, see [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

### <a name="intune-enrollment"></a><span data-ttu-id="88879-187">Intune-registrering</span><span class="sxs-lookup"><span data-stu-id="88879-187">Intune enrollment</span></span>

<span data-ttu-id="88879-188">Windows 10-enheter i din Azure AD-organisation måste registreras automatiskt i Intune.</span><span class="sxs-lookup"><span data-stu-id="88879-188">Windows 10 devices in your Azure AD organization must be automatically enrolled in Intune.</span></span>

<span data-ttu-id="88879-189">**Inte klart**</span><span class="sxs-lookup"><span data-stu-id="88879-189">**Not ready**</span></span>

<span data-ttu-id="88879-190">Användare i din Azure AD-organisation registreras inte automatiskt i Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="88879-190">Users in your Azure AD organization aren't automatically enrolled in Microsoft Intune.</span></span> <span data-ttu-id="88879-191">Ändra omfattningen för MDM-användare till **vissa** eller **alla**.</span><span class="sxs-lookup"><span data-stu-id="88879-191">Change the MDM User scope to **Some** or **All**.</span></span> <span data-ttu-id="88879-192">Om du väljer.</span><span class="sxs-lookup"><span data-stu-id="88879-192">If you choose.</span></span> <span data-ttu-id="88879-193">Lite \* \*, kom tillbaka efter registreringen och välj den **moderna arbets platsen – alla** Azure AD-grupper för **grupper**.</span><span class="sxs-lookup"><span data-stu-id="88879-193">Some\*\*, come back after enrollment and select the **Modern Workplace -All** Azure AD group for **Groups**.</span></span>


### <a name="microsoft-store-for-business"></a><span data-ttu-id="88879-194">Microsoft Store för företag</span><span class="sxs-lookup"><span data-stu-id="88879-194">Microsoft Store for Business</span></span>

<span data-ttu-id="88879-195">Vi använder Microsoft Store för företag så att du kan ladda ned företags Portal för att distribuera vissa program, till exempel Microsoft Project och Microsoft Visio.</span><span class="sxs-lookup"><span data-stu-id="88879-195">We use Microsoft Store for Business so that you can download Company Portal to deploy some apps, such as Microsoft Project and Microsoft Visio.</span></span>

<span data-ttu-id="88879-196">**Inte klart**</span><span class="sxs-lookup"><span data-stu-id="88879-196">**Not ready**</span></span>

<span data-ttu-id="88879-197">Microsoft Store för företag är antingen inte aktiverat eller synkroniseras inte med Intune.</span><span class="sxs-lookup"><span data-stu-id="88879-197">Microsoft Store for Business either isn't enabled or isn't synced with Intune.</span></span> <span data-ttu-id="88879-198">Mer information finns i [så här hanterar du volym köps program från Microsoft Store för företag med Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) och [Installera Intune företags Portal på enheter](../get-started/company-portal.md).</span><span class="sxs-lookup"><span data-stu-id="88879-198">For more information, see [How to manage volume purchased apps from the Microsoft Store for Business with Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) and [Install Intune Company Portal on on devices](../get-started/company-portal.md).</span></span>

### <a name="multi-factor-authentication"></a><span data-ttu-id="88879-199">Multifaktorautentisering</span><span class="sxs-lookup"><span data-stu-id="88879-199">Multi-factor authentication</span></span>

<span data-ttu-id="88879-200">Multifaktorautentisering får inte på ett oavsiktligt sätt tillämpas på Microsoft Managed Desktop Service-konton.</span><span class="sxs-lookup"><span data-stu-id="88879-200">Multi-factor authentication must not accidentally be applied to Microsoft Managed Desktop service accounts.</span></span>


<span data-ttu-id="88879-201">**Inte klart**</span><span class="sxs-lookup"><span data-stu-id="88879-201">**Not ready**</span></span>

<span data-ttu-id="88879-202">Du har vissa principer för multifaktorautentisering (MFA) inställda som "obligatoriskt" för principer för villkorsstyrd åtkomst som är tilldelade till alla användare.</span><span class="sxs-lookup"><span data-stu-id="88879-202">You have some multi-factor authentication (MFA) policies set as "required" for conditional access policies that are assigned to all users.</span></span> <span data-ttu-id="88879-203">Ändra principen för att använda en tilldelning som är riktad till en viss Azure AD-grupp som inte innehåller Microsoft hanterade Station ära datorer.</span><span class="sxs-lookup"><span data-stu-id="88879-203">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="88879-204">Mer information finns i [principer för villkorsstyrd åtkomst](#conditional-access-policies) och [villkorsstyrd åtkomst: Kräv MFA för alla användare](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span><span class="sxs-lookup"><span data-stu-id="88879-204">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span>

<span data-ttu-id="88879-205">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="88879-205">**Advisory**</span></span>

<span data-ttu-id="88879-206">Se till att alla villkorsstyrda åtkomst principer som kräver MFA exkluderar den **moderna arbets platsen – alla** Azure AD-grupper.</span><span class="sxs-lookup"><span data-stu-id="88879-206">Make sure that any conditional access policies that require MFA exclude the **Modern Workplace -All** Azure AD group.</span></span> <span data-ttu-id="88879-207">Mer information finns i [principer för villkorsstyrd åtkomst](#conditional-access-policies) och [villkorsstyrd åtkomst: Kräv MFA för alla användare](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span><span class="sxs-lookup"><span data-stu-id="88879-207">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span> <span data-ttu-id="88879-208">Den **moderna arbets platsen – alla** Azure AD-grupper är en dynamisk grupp som vi skapar när du registrerar dig på Microsoft Managed Desktop, så att du måste komma tillbaka till den här gruppen efter registrering.</span><span class="sxs-lookup"><span data-stu-id="88879-208">The **Modern Workplace -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>



### <a name="powershell-scripts"></a><span data-ttu-id="88879-209">PowerShell-skript</span><span class="sxs-lookup"><span data-stu-id="88879-209">PowerShell scripts</span></span>

<span data-ttu-id="88879-210">Windows PowerShell-skript kan inte tilldelas på ett sätt som riktar sig till Microsoft Managed Station ära enheter.</span><span class="sxs-lookup"><span data-stu-id="88879-210">Windows PowerShell scripts can't be assigned in a way that would target Microsoft Managed Desktop devices.</span></span>  

<span data-ttu-id="88879-211">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="88879-211">**Advisory**</span></span>

<span data-ttu-id="88879-212">Kontrol lera att Windows PowerShell-skript i din Azure AD-organisation inte har några Microsoft-hanterings enheter eller användare.</span><span class="sxs-lookup"><span data-stu-id="88879-212">Make sure that Windows PowerShell scripts in your Azure AD organization don't target any Microsoft Manage Desktop devices or users.</span></span> <span data-ttu-id="88879-213">Mer information finns i [använda PowerShell-skript på Windows 10-enheter i Intune](https://docs.microsoft.com/mem/intune/apps/intune-management-extension).</span><span class="sxs-lookup"><span data-stu-id="88879-213">For more information, see [Use PowerShell scripts on Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/apps/intune-management-extension).</span></span>

### <a name="region"></a><span data-ttu-id="88879-214">Region</span><span class="sxs-lookup"><span data-stu-id="88879-214">Region</span></span>

<span data-ttu-id="88879-215">Din region måste vara kompatibel med Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="88879-215">Your region must be supported by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="88879-216">**Inte klart**</span><span class="sxs-lookup"><span data-stu-id="88879-216">**Not ready**</span></span>

<span data-ttu-id="88879-217">Din organisations region för Azure AD stöds för närvarande inte av Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="88879-217">Your Azure AD organization region isn't currently supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="88879-218">Mer information finns i [regioner och språk som stöds i Microsoft hanterade skriv bord](../service-description/regions-languages.md).</span><span class="sxs-lookup"><span data-stu-id="88879-218">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>

<span data-ttu-id="88879-219">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="88879-219">**Advisory**</span></span>

<span data-ttu-id="88879-220">Ett eller flera av de länder där din Azure AD-organisation finns stöds inte av Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="88879-220">One or more of the countries where your Azure AD organization is located isn't supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="88879-221">Mer information finns i [regioner och språk som stöds i Microsoft hanterade skriv bord](../service-description/regions-languages.md).</span><span class="sxs-lookup"><span data-stu-id="88879-221">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>


### <a name="security-baselines"></a><span data-ttu-id="88879-222">Säkerhets bas linjer</span><span class="sxs-lookup"><span data-stu-id="88879-222">Security baselines</span></span>

<span data-ttu-id="88879-223">Principer för säkerhets rikt linjer ska inte vara riktade till enheter som hanteras av Microsoft.</span><span class="sxs-lookup"><span data-stu-id="88879-223">Security baseline policies should not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="88879-224">**Inte klart**</span><span class="sxs-lookup"><span data-stu-id="88879-224">**Not ready**</span></span>

<span data-ttu-id="88879-225">Du har en säkerhets bas profil som är riktad till alla användare, alla enheter eller både och.</span><span class="sxs-lookup"><span data-stu-id="88879-225">You have a security baseline profile that targets all users, all devices or both.</span></span> <span data-ttu-id="88879-226">Ändra principen för att använda en tilldelning som är riktad till en viss Azure AD-grupp som inte innehåller Microsoft hanterade Station ära datorer.</span><span class="sxs-lookup"><span data-stu-id="88879-226">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="88879-227">Anvisningar finns i [använda säkerhets bas linjer för att konfigurera Windows 10-enheter i Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span><span class="sxs-lookup"><span data-stu-id="88879-227">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span>

<span data-ttu-id="88879-228">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="88879-228">**Advisory**</span></span>

<span data-ttu-id="88879-229">Se till att alla principer för säkerhets rikt linjer du har exkluderar Microsoft Managed Station ära enheter.</span><span class="sxs-lookup"><span data-stu-id="88879-229">Make sure that any security baseline policies you have exclude Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="88879-230">Anvisningar finns i [använda säkerhets bas linjer för att konfigurera Windows 10-enheter i Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span><span class="sxs-lookup"><span data-stu-id="88879-230">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span> <span data-ttu-id="88879-231">**Moderna arbets plats enheter-alla** Azure AD-grupper är en dynamisk grupp som vi skapar när du registrerar dig på Microsoft Managed Desktop, så att du måste komma tillbaka till den här gruppen efter registrering.</span><span class="sxs-lookup"><span data-stu-id="88879-231">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


### <a name="windows-apps"></a><span data-ttu-id="88879-232">Windows-appar</span><span class="sxs-lookup"><span data-stu-id="88879-232">Windows apps</span></span>

<span data-ttu-id="88879-233">Granska de program du vill att Microsoft Managed Desktop-användarna ska ha.</span><span class="sxs-lookup"><span data-stu-id="88879-233">Review apps you want your Microsoft Managed Desktop users to have.</span></span>

<span data-ttu-id="88879-234">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="88879-234">**Advisory**</span></span>

<span data-ttu-id="88879-235">Du bör förbereda en inventering av de program som du vill att Microsoft Managed Desktop-användarna ska ha.</span><span class="sxs-lookup"><span data-stu-id="88879-235">You should prepare an inventory of the apps that you want your Microsoft Managed Desktop users to have.</span></span> <span data-ttu-id="88879-236">Kontrol lera att dessa appar kan distribueras av Intune.</span><span class="sxs-lookup"><span data-stu-id="88879-236">Make sure these apps can be deployed by Intune.</span></span> <span data-ttu-id="88879-237">Mer information finns i [program på Microsoft Managed Desktop](apps.md).</span><span class="sxs-lookup"><span data-stu-id="88879-237">For more information, see [Apps in Microsoft Managed Desktop](apps.md).</span></span>

<span data-ttu-id="88879-238">Du kan be din Microsoft-representant om en fråga i Microsoft Endpoint Configuration Manager att identifiera de program som är redo att migreras till Intune eller behöver justeras.</span><span class="sxs-lookup"><span data-stu-id="88879-238">You can ask your Microsoft account representative for a query in Microsoft Endpoint Configuration Manager to identify those apps that are ready to migrate to Intune or need adjustment.</span></span>


### <a name="windows-hello-for-business"></a><span data-ttu-id="88879-239">Windows Hello för företag</span><span class="sxs-lookup"><span data-stu-id="88879-239">Windows Hello for Business</span></span>

<span data-ttu-id="88879-240">Microsoft Managed Desktop kräver att Windows Hello för företag aktive ras.</span><span class="sxs-lookup"><span data-stu-id="88879-240">Microsoft Managed Desktop requires Windows Hello for Business to be enabled.</span></span>

<span data-ttu-id="88879-241">**Inte klart**</span><span class="sxs-lookup"><span data-stu-id="88879-241">**Not ready**</span></span>

<span data-ttu-id="88879-242">Windows Hello för företag är inaktiverat.</span><span class="sxs-lookup"><span data-stu-id="88879-242">Windows Hello for Business is disabled.</span></span> <span data-ttu-id="88879-243">Aktivera den genom att följa anvisningarna i [skapa en Windows Hello för företag-princip](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span><span class="sxs-lookup"><span data-stu-id="88879-243">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span></span>

<span data-ttu-id="88879-244">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="88879-244">**Advisory**</span></span>

<span data-ttu-id="88879-245">Windows Hello för företag är inte konfigurerat.</span><span class="sxs-lookup"><span data-stu-id="88879-245">Windows Hello for Business is not set up.</span></span> <span data-ttu-id="88879-246">Aktivera den genom att följa anvisningarna i [skapa en Windows Hello för företag-policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).</span><span class="sxs-lookup"><span data-stu-id="88879-246">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).</span></span>


### <a name="windows-10-update-rings"></a><span data-ttu-id="88879-247">Windows 10-uppdaterings ringar</span><span class="sxs-lookup"><span data-stu-id="88879-247">Windows 10 update rings</span></span>

<span data-ttu-id="88879-248">Din "Windows 10 Update ring"-princip i Intune får inte uppfylla alla hanterade Microsoft-enheter.</span><span class="sxs-lookup"><span data-stu-id="88879-248">Your "Windows 10 update ring" policy in Intune must not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="88879-249">**Inte klart**</span><span class="sxs-lookup"><span data-stu-id="88879-249">**Not ready**</span></span>

<span data-ttu-id="88879-250">Du har en "uppdatera ring"-princip som är riktad till alla enheter, alla användare eller både och.</span><span class="sxs-lookup"><span data-stu-id="88879-250">You have an "update ring" policy that targets all devices, all users, or both.</span></span> <span data-ttu-id="88879-251">Ändra principen för att använda en tilldelning som är riktad till en viss Azure AD-grupp som inte innehåller Microsoft hanterade Station ära datorer.</span><span class="sxs-lookup"><span data-stu-id="88879-251">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="88879-252">Anvisningar finns i [hantera program uppdateringar för Windows 10 i Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span><span class="sxs-lookup"><span data-stu-id="88879-252">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span>

<span data-ttu-id="88879-253">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="88879-253">**Advisory**</span></span>

<span data-ttu-id="88879-254">Se till att eventuella uppdaterings rings principer du har exkluderar den **moderna arbets platsen – alla** Azure AD-grupper.</span><span class="sxs-lookup"><span data-stu-id="88879-254">Make sure that any update ring policies you have exclude the **Modern Workplace -All** Azure AD group.</span></span> <span data-ttu-id="88879-255">Anvisningar finns i [hantera program uppdateringar för Windows 10 i Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span><span class="sxs-lookup"><span data-stu-id="88879-255">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span> <span data-ttu-id="88879-256">**Moderna arbets plats enheter-alla** Azure AD-grupper är en dynamisk grupp som vi skapar när du registrerar dig på Microsoft Managed Desktop, så att du måste komma tillbaka till den här gruppen efter registrering.</span><span class="sxs-lookup"><span data-stu-id="88879-256">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


## <a name="azure-active-directory-settings"></a><span data-ttu-id="88879-257">Azure Active Directory-inställningar</span><span class="sxs-lookup"><span data-stu-id="88879-257">Azure Active Directory settings</span></span>


### <a name="ad-hoc-subscriptions"></a><span data-ttu-id="88879-258">Ad hoc-abonnemang</span><span class="sxs-lookup"><span data-stu-id="88879-258">Ad hoc subscriptions</span></span>

<span data-ttu-id="88879-259">Här beskrivs hur du kontrollerar en inställning som (om värdet är "falskt") kan hindra företags tillstånd från att fungera korrekt.</span><span class="sxs-lookup"><span data-stu-id="88879-259">Advises how to check a setting that (if set to "false") might prevent Enterprise State Roaming from working correctly.</span></span>

<span data-ttu-id="88879-260">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="88879-260">**Advisory**</span></span>

<span data-ttu-id="88879-261">Kontrol lera att **AllowAdHocSubscriptions** är inställt på **True**.</span><span class="sxs-lookup"><span data-stu-id="88879-261">Ensure that **AllowAdHocSubscriptions** is set to **True**.</span></span> <span data-ttu-id="88879-262">I annat fall kanske företags statusen roaming inte fungerar.</span><span class="sxs-lookup"><span data-stu-id="88879-262">Otherwise, Enterprise State Roaming might not work.</span></span> <span data-ttu-id="88879-263">Mer information finns i [set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="88879-263">For more information, see [Set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).</span></span>


### <a name="enterprise-state-roaming"></a><span data-ttu-id="88879-264">Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="88879-264">Enterprise State Roaming</span></span>

<span data-ttu-id="88879-265">Roaming för företags status bör vara aktiverat.</span><span class="sxs-lookup"><span data-stu-id="88879-265">Enterprise State Roaming should be enabled.</span></span>

<span data-ttu-id="88879-266">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="88879-266">**Advisory**</span></span>

<span data-ttu-id="88879-267">Kontrol lera att organisationens centrala nätverks tillstånd är aktiverat för **alla** eller för **markerade** grupper.</span><span class="sxs-lookup"><span data-stu-id="88879-267">Make sure that Enterprise State Roaming is enabled for **All** or for **Selected** groups.</span></span> <span data-ttu-id="88879-268">Mer information finns i [Aktivera roaming för företags tillstånd i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable).</span><span class="sxs-lookup"><span data-stu-id="88879-268">For more information, see [Enable Enterprise State Roaming in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable).</span></span>

### <a name="licenses"></a><span data-ttu-id="88879-269">Licenser</span><span class="sxs-lookup"><span data-stu-id="88879-269">Licenses</span></span>

<span data-ttu-id="88879-270">Det krävs flera olika licenser för att använda Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="88879-270">A number of licenses are required to use Microsoft Managed Desktop.</span></span>

<span data-ttu-id="88879-271">**Inte klart**</span><span class="sxs-lookup"><span data-stu-id="88879-271">**Not Ready**</span></span>

<span data-ttu-id="88879-272">Du har inte alla licenser som du behöver för att använda Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="88879-272">You don't have all the licenses you need to use Microsoft Managed Desktop.</span></span> <span data-ttu-id="88879-273">Mer information finns i [Microsoft hanterad Skriv bords teknik](../intro/technologies.md) och [mer om licenser](prerequisites.md#more-about-licenses).</span><span class="sxs-lookup"><span data-stu-id="88879-273">For more information, see [Microsoft Managed Desktop technologies](../intro/technologies.md) and [More about licenses](prerequisites.md#more-about-licenses).</span></span>


### <a name="security-account-names"></a><span data-ttu-id="88879-274">Namn på säkerhets konton</span><span class="sxs-lookup"><span data-stu-id="88879-274">Security account names</span></span>

<span data-ttu-id="88879-275">Vissa namn på säkerhets konton kan vara i konflikt med dem som har skapats av Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="88879-275">Certain security account names could conflict with ones created by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="88879-276">**Inte klart**</span><span class="sxs-lookup"><span data-stu-id="88879-276">**Not ready**</span></span>

<span data-ttu-id="88879-277">Du har minst ett konto namn som är oförenliga med dem som skapas av Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="88879-277">You have at least one account name that will conflict with ones created by Microsoft Managed Desktop.</span></span> <span data-ttu-id="88879-278">Arbeta med ditt Microsoft-konto för att utesluta dessa konto namn.</span><span class="sxs-lookup"><span data-stu-id="88879-278">Work with your Microsoft account representative to exclude these account names.</span></span>


### <a name="security-administrator-roles"></a><span data-ttu-id="88879-279">Säkerhets administratörs roller</span><span class="sxs-lookup"><span data-stu-id="88879-279">Security administrator roles</span></span>

<span data-ttu-id="88879-280">Användare med vissa säkerhets roller måste ha kopplade till dem i Microsoft Defender för slut punkter.</span><span class="sxs-lookup"><span data-stu-id="88879-280">Users with certain security roles must have those assigned in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="88879-281">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="88879-281">**Advisory**</span></span>

<span data-ttu-id="88879-282">Om du har någon av de här rollerna i din Azure AD-organisation kontrollerar du att de också har tilldelats dessa roller i Microsoft Defender för slut punkter.</span><span class="sxs-lookup"><span data-stu-id="88879-282">If you have any of these roles assigned in your Azure AD organization, make sure they also have these roles assigned in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="88879-283">Annars kommer administratörer med dessa roller inte att kunna använda administrations portalen.</span><span class="sxs-lookup"><span data-stu-id="88879-283">Otherwise, administrators with these roles won't be able to access the Admin portal.</span></span>

- <span data-ttu-id="88879-284">Säkerhets läsare</span><span class="sxs-lookup"><span data-stu-id="88879-284">Security Reader</span></span>
- <span data-ttu-id="88879-285">Säkerhets ansvarig</span><span class="sxs-lookup"><span data-stu-id="88879-285">Security Operator</span></span>
- <span data-ttu-id="88879-286">Global läsare</span><span class="sxs-lookup"><span data-stu-id="88879-286">Global Reader</span></span>

<span data-ttu-id="88879-287">Mer information finns i [skapa och hantera roller för rollbaserad åtkomst kontroll](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles).</span><span class="sxs-lookup"><span data-stu-id="88879-287">For more information, see [Create and manage roles for role-based access control](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles).</span></span>


### <a name="security-default"></a><span data-ttu-id="88879-288">Säkerhets standard</span><span class="sxs-lookup"><span data-stu-id="88879-288">Security default</span></span>

<span data-ttu-id="88879-289">Säkerhets inställningar i Azure Active Directory kommer inte att hantera dina enheter på Microsoft.</span><span class="sxs-lookup"><span data-stu-id="88879-289">Security defaults in Azure Active Directory will prevent Microsoft Managed Desktop from managing your devices.</span></span>

<span data-ttu-id="88879-290">**Inte klart**</span><span class="sxs-lookup"><span data-stu-id="88879-290">**Not ready**</span></span>

<span data-ttu-id="88879-291">Säkerhets inställningarna är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="88879-291">You have Security defaults turned on.</span></span> <span data-ttu-id="88879-292">Inaktivera säkerhets standarder och konfigurera villkorsstyrda åtkomst principer.</span><span class="sxs-lookup"><span data-stu-id="88879-292">Turn off Security defaults and set up conditional access policies.</span></span> <span data-ttu-id="88879-293">Mer information finns i [vanliga principer för villkorsstyrd åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span><span class="sxs-lookup"><span data-stu-id="88879-293">For more information, see [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span></span>

### <a name="self-service-password-reset"></a><span data-ttu-id="88879-294">Självbetjäning för återställning av lösen ord</span><span class="sxs-lookup"><span data-stu-id="88879-294">Self-service Password Reset</span></span>

<span data-ttu-id="88879-295">Självbetjäning för återställning av lösen ord (SSPR) måste aktive ras.</span><span class="sxs-lookup"><span data-stu-id="88879-295">Self-service Password Reset (SSPR) must be enabled.</span></span>

<span data-ttu-id="88879-296">**Inte klart**</span><span class="sxs-lookup"><span data-stu-id="88879-296">**Not ready**</span></span>

<span data-ttu-id="88879-297">SSPR måste vara aktiverat för alla användare.</span><span class="sxs-lookup"><span data-stu-id="88879-297">SSPR must be enabled for all users.</span></span> <span data-ttu-id="88879-298">Om det inte är det kan inte Microsoft Managed Desktop-tjänsten fungera.</span><span class="sxs-lookup"><span data-stu-id="88879-298">If it isn't, the Microsoft Managed Desktop service accounts can't work.</span></span> <span data-ttu-id="88879-299">Mer information finns i [själv studie kursen: Låt användare låsa upp sina konton eller återställa lösen ord med hjälp av återställning av Azure Active Directory Self-Service](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span><span class="sxs-lookup"><span data-stu-id="88879-299">For more information, see [Tutorial: Enable users to unlock their account or reset passwords using Azure Active Directory self-service password reset](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span></span>

<span data-ttu-id="88879-300">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="88879-300">**Advisory**</span></span>

<span data-ttu-id="88879-301">Kontrol lera att SSPR **valda** inställningar innehåller Microsoft Managed Station ära datorer.</span><span class="sxs-lookup"><span data-stu-id="88879-301">Make sure that the SSPR **Selected** setting includes Microsoft Managed Desktop devices.</span></span>

### <a name="standard-user-role"></a><span data-ttu-id="88879-302">Standard användar roll</span><span class="sxs-lookup"><span data-stu-id="88879-302">Standard user role</span></span>

<span data-ttu-id="88879-303">Microsoft Managed Desktop-användare ska vara vanliga användare utan lokala administratörs behörigheter.</span><span class="sxs-lookup"><span data-stu-id="88879-303">Microsoft Managed Desktop users should be standard users without local administrator privileges.</span></span> <span data-ttu-id="88879-304">De tilldelas en standard användar roll när de startar sin Microsoft-hanterade Station.</span><span class="sxs-lookup"><span data-stu-id="88879-304">They'll be assigned a standard user role when they start their Microsoft Managed Desktop device.</span></span>

<span data-ttu-id="88879-305">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="88879-305">**Advisory**</span></span>

<span data-ttu-id="88879-306">Microsoft Managed Station ära datorer bör inte ha lokala administratörs behörigheter innan de registreras.</span><span class="sxs-lookup"><span data-stu-id="88879-306">Microsoft Managed Desktop users shouldn't have local administrator privileges prior to enrolling.</span></span>

## <a name="microsoft-365-apps-for-enterprise"></a><span data-ttu-id="88879-307">Microsoft 365-appar för företag</span><span class="sxs-lookup"><span data-stu-id="88879-307">Microsoft 365 Apps for enterprise</span></span>

### <a name="onedrive-for-business"></a><span data-ttu-id="88879-308">OneDrive för företag</span><span class="sxs-lookup"><span data-stu-id="88879-308">OneDrive for Business</span></span>

<span data-ttu-id="88879-309">Inställningen **Tillåt synkronisering endast på datorer som är anslutna till vissa domäner** visas i konflikt med Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="88879-309">The **Allow syncing only on PCs joined to specific domains** setting will conflict with Microsoft Managed Desktop.</span></span>

<span data-ttu-id="88879-310">**Rådgivare**</span><span class="sxs-lookup"><span data-stu-id="88879-310">**Advisory**</span></span>

<span data-ttu-id="88879-311">Du använder alternativet **Tillåt synkronisering endast på datorer som är anslutna till vissa domän** inställningar.</span><span class="sxs-lookup"><span data-stu-id="88879-311">You're using the **Allow syncing only on PCs joined to specific domains** setting.</span></span> <span data-ttu-id="88879-312">Den här inställningen fungerar inte med Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="88879-312">This setting won't work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="88879-313">Inaktivera den här inställningen och konfigurera i stället OneDrive för företag för användning av villkorsstyrd åtkomst policy.</span><span class="sxs-lookup"><span data-stu-id="88879-313">Disable this setting, and instead set up OneDrive for Business to use a conditional access policy.</span></span> <span data-ttu-id="88879-314">Se [Planera en distribution för villkorlig åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) för hjälp.</span><span class="sxs-lookup"><span data-stu-id="88879-314">See [Plan a Conditional Access deployment](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) for help.</span></span>

