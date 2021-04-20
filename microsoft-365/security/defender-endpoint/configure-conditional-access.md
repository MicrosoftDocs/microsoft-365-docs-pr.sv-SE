---
title: Konfigurera villkorsstyrd åtkomst i Microsoft Defender för Slutpunkt
description: Läs mer om steg som du måste göra i Intune, Microsoft Defender Säkerhetscenter och Azure för att implementera villkorsstyrd åtkomst
keywords: villkorsstyrd åtkomst, villkorsstyrd, åtkomst, enhetsrisk, risknivå, integrering, intune-integrering
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
ms.openlocfilehash: 482f86d4a0a181b72a0a33eeb1a857dce0664584
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893655"
---
# <a name="configure-conditional-access-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="410bd-104">Konfigurera villkorsstyrd åtkomst i Microsoft Defender för Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="410bd-104">Configure Conditional Access in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="410bd-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="410bd-105">**Applies to:**</span></span>
- [<span data-ttu-id="410bd-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="410bd-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="410bd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="410bd-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="410bd-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="410bd-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="410bd-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="410bd-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="410bd-110">I det här avsnittet får du vägledning genom alla steg du behöver vidta för att implementera villkorsstyrd åtkomst på rätt sätt.</span><span class="sxs-lookup"><span data-stu-id="410bd-110">This section guides you through all the steps you need to take to properly implement Conditional Access.</span></span>

### <a name="before-you-begin"></a><span data-ttu-id="410bd-111">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="410bd-111">Before you begin</span></span>
>[!WARNING]
><span data-ttu-id="410bd-112">Det är viktigt att observera att registrerade Azure AD-enheter inte stöds i det här scenariot.</span><span class="sxs-lookup"><span data-stu-id="410bd-112">It's important to note that Azure AD registered devices is not supported in this scenario.</span></span></br>
><span data-ttu-id="410bd-113">Endast registrerade Intune-enheter stöds.</span><span class="sxs-lookup"><span data-stu-id="410bd-113">Only Intune enrolled devices are supported.</span></span>


<span data-ttu-id="410bd-114">Du måste se till att alla dina enheter är registrerade i Intune.</span><span class="sxs-lookup"><span data-stu-id="410bd-114">You need to make sure that all your devices are enrolled in Intune.</span></span> <span data-ttu-id="410bd-115">Du kan använda något av följande alternativ för att registrera enheter i Intune:</span><span class="sxs-lookup"><span data-stu-id="410bd-115">You can use any of the following options to enroll devices in Intune:</span></span>


- <span data-ttu-id="410bd-116">IT-administratör: Mer information om hur du aktiverar automatisk registrering finns i [Windows-registrering](https://docs.microsoft.com/intune/windows-enroll#enable-windows-10-automatic-enrollment)</span><span class="sxs-lookup"><span data-stu-id="410bd-116">IT Admin: For more information on how to enabling auto-enrollment, see [Windows Enrollment](https://docs.microsoft.com/intune/windows-enroll#enable-windows-10-automatic-enrollment)</span></span>
- <span data-ttu-id="410bd-117">Slutanvändare: Mer information om hur du registrerar din Windows 10-enhet i Intune finns i Registrera din [Windows 10-enhet i Intune](https://docs.microsoft.com/intune/quickstart-enroll-windows-device)</span><span class="sxs-lookup"><span data-stu-id="410bd-117">End-user: For more information on how to enroll your Windows 10 device in Intune, see [Enroll your Windows 10 device in Intune](https://docs.microsoft.com/intune/quickstart-enroll-windows-device)</span></span>
- <span data-ttu-id="410bd-118">Alternativ för slutanvändare: Mer information om hur du ansluter till en Azure AD-domän finns i Så här gör du: Planera din implementering av [Azure AD-koppling.](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan)</span><span class="sxs-lookup"><span data-stu-id="410bd-118">End-user alternative: For more information on joining an Azure AD domain, see [How to: Plan your Azure AD join implementation](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan).</span></span>



<span data-ttu-id="410bd-119">Det finns åtgärder du måste vidta i Microsoft Defender Säkerhetscenter, Intune-portalen och Azure AD-portalen.</span><span class="sxs-lookup"><span data-stu-id="410bd-119">There are steps you'll need to take in Microsoft Defender Security Center, the Intune portal, and Azure AD portal.</span></span>

<span data-ttu-id="410bd-120">Det är viktigt att observera de roller som krävs för att komma åt dessa portaler och implementera villkorsstyrd åtkomst:</span><span class="sxs-lookup"><span data-stu-id="410bd-120">It's important to note the required roles to access these portals and implement Conditional access:</span></span>
- <span data-ttu-id="410bd-121">**Microsoft Defender Säkerhetscenter** – Du måste logga in på portalen med en global administratörsroll för att aktivera integreringen.</span><span class="sxs-lookup"><span data-stu-id="410bd-121">**Microsoft Defender Security Center** - You'll need to sign into the portal with a global administrator role to turn on the integration.</span></span>
- <span data-ttu-id="410bd-122">**Intune** – Du måste logga in på portalen med behörigheten säkerhetsadministratör med hanteringsbehörighet.</span><span class="sxs-lookup"><span data-stu-id="410bd-122">**Intune** - You'll need to sign in to the portal with security administrator rights with management permissions.</span></span> 
- <span data-ttu-id="410bd-123">**Azure AD-portal** – Du måste logga in som global administratör, säkerhetsadministratör eller villkorsstyrd åtkomstadministratör.</span><span class="sxs-lookup"><span data-stu-id="410bd-123">**Azure AD portal** - You'll need to sign in as a global administrator, security administrator, or Conditional Access administrator.</span></span>


> [!NOTE]
> <span data-ttu-id="410bd-124">Du behöver en Microsoft Intune-miljö med Intune hanterad och Azure AD-anslutna Windows 10-enheter.</span><span class="sxs-lookup"><span data-stu-id="410bd-124">You'll need a Microsoft Intune environment, with Intune managed and Azure AD joined Windows 10 devices.</span></span>

<span data-ttu-id="410bd-125">Gör följande för att aktivera villkorsstyrd åtkomst:</span><span class="sxs-lookup"><span data-stu-id="410bd-125">Take the following steps to enable Conditional Access:</span></span>
- <span data-ttu-id="410bd-126">Steg 1: Aktivera Microsoft Intune-anslutningen från Microsoft Defender Säkerhetscenter</span><span class="sxs-lookup"><span data-stu-id="410bd-126">Step 1: Turn on the Microsoft Intune connection from Microsoft Defender Security Center</span></span>
- <span data-ttu-id="410bd-127">Steg 2: Aktivera Defender för slutpunktsintegrering i Intune</span><span class="sxs-lookup"><span data-stu-id="410bd-127">Step 2: Turn on the Defender for Endpoint integration in Intune</span></span>
- <span data-ttu-id="410bd-128">Steg 3: Skapa efterlevnadsprincipen i Intune</span><span class="sxs-lookup"><span data-stu-id="410bd-128">Step 3: Create the compliance policy in Intune</span></span>
- <span data-ttu-id="410bd-129">Steg 4: Tilldela principen</span><span class="sxs-lookup"><span data-stu-id="410bd-129">Step 4: Assign the policy</span></span> 
- <span data-ttu-id="410bd-130">Steg 5: Skapa en villkorsbaserad åtkomstprincip i Azure AD</span><span class="sxs-lookup"><span data-stu-id="410bd-130">Step 5: Create an Azure AD Conditional Access policy</span></span>


### <a name="step-1-turn-on-the-microsoft-intune-connection"></a><span data-ttu-id="410bd-131">Steg 1: Aktivera Microsoft Intune-anslutningen</span><span class="sxs-lookup"><span data-stu-id="410bd-131">Step 1: Turn on the Microsoft Intune connection</span></span>
1. <span data-ttu-id="410bd-132">I navigeringsfönstret väljer du Inställningar  >  **Avancerade funktioner** Microsoft  >  **Intune-anslutning**.</span><span class="sxs-lookup"><span data-stu-id="410bd-132">In the navigation pane, select **Settings** > **Advanced features** > **Microsoft Intune connection**.</span></span>
2. <span data-ttu-id="410bd-133">Ändra Microsoft Intune-inställningen till **På**.</span><span class="sxs-lookup"><span data-stu-id="410bd-133">Toggle the Microsoft Intune setting to **On**.</span></span>
3. <span data-ttu-id="410bd-134">Klicka **på Spara inställningar.**</span><span class="sxs-lookup"><span data-stu-id="410bd-134">Click **Save preferences**.</span></span>


### <a name="step-2-turn-on-the-defender-for-endpoint-integration-in-intune"></a><span data-ttu-id="410bd-135">Steg 2: Aktivera Defender för slutpunktsintegrering i Intune</span><span class="sxs-lookup"><span data-stu-id="410bd-135">Step 2: Turn on the Defender for Endpoint integration in Intune</span></span>
1. <span data-ttu-id="410bd-136">Logga in på [Azure-portalen](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="410bd-136">Sign in to the [Azure portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="410bd-137">Välj **Enhetsefterlevnad**  >  **Microsoft Defender ATP**.</span><span class="sxs-lookup"><span data-stu-id="410bd-137">Select **Device compliance** > **Microsoft Defender ATP**.</span></span>
3. <span data-ttu-id="410bd-138">Ställ **in Anslut Windows 10.0.15063-enheter till Microsoft Defender Avancerat skydd** på **På.**</span><span class="sxs-lookup"><span data-stu-id="410bd-138">Set **Connect Windows 10.0.15063+ devices to Microsoft Defender Advanced Threat Protection** to **On**.</span></span>
4. <span data-ttu-id="410bd-139">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="410bd-139">Click **Save**.</span></span>


### <a name="step-3-create-the-compliance-policy-in-intune"></a><span data-ttu-id="410bd-140">Steg 3: Skapa efterlevnadsprincipen i Intune</span><span class="sxs-lookup"><span data-stu-id="410bd-140">Step 3: Create the compliance policy in Intune</span></span>
1. <span data-ttu-id="410bd-141">I [Azure-portalen](https://portal.azure.com)väljer du **Alla tjänster**, filtrera på **Intune** och sedan **Microsoft Intune.**</span><span class="sxs-lookup"><span data-stu-id="410bd-141">In the [Azure portal](https://portal.azure.com), select **All services**, filter on **Intune**, and select **Microsoft Intune**.</span></span>
2. <span data-ttu-id="410bd-142">Välj **Principer för**  >  **enhetsefterlevnad**  >  **Skapa princip**.</span><span class="sxs-lookup"><span data-stu-id="410bd-142">Select **Device compliance** > **Policies** > **Create policy**.</span></span>
3. <span data-ttu-id="410bd-143">Ange namn **och** **beskrivning.**</span><span class="sxs-lookup"><span data-stu-id="410bd-143">Enter a **Name** and **Description**.</span></span>
4. <span data-ttu-id="410bd-144">I **Plattform** väljer du **Windows 10 och senare**.</span><span class="sxs-lookup"><span data-stu-id="410bd-144">In **Platform**, select **Windows 10 and later**.</span></span>
5. <span data-ttu-id="410bd-145">I inställningarna **för Enhetshälsa** ställer du **in Kräv att enheten är på eller under enhetshotsnivån till** önskad nivå:</span><span class="sxs-lookup"><span data-stu-id="410bd-145">In the **Device Health** settings, set **Require the device to be at or under the Device Threat Level** to your preferred level:</span></span>

   - <span data-ttu-id="410bd-146">**Skyddad:** Den här nivån är den säkraste.</span><span class="sxs-lookup"><span data-stu-id="410bd-146">**Secured**: This level is the most secure.</span></span> <span data-ttu-id="410bd-147">Enheten kan inte ha befintliga hot och får fortfarande åtkomst till företagets resurser.</span><span class="sxs-lookup"><span data-stu-id="410bd-147">The device cannot have any existing threats and still access company resources.</span></span> <span data-ttu-id="410bd-148">Om några hot hittas utvärderas enheten som icke-kompatibel.</span><span class="sxs-lookup"><span data-stu-id="410bd-148">If any threats are found, the device is evaluated as noncompliant.</span></span>
   - <span data-ttu-id="410bd-149">**Låg:** Enheten är kompatibel om det bara finns hot på låg nivå.</span><span class="sxs-lookup"><span data-stu-id="410bd-149">**Low**: The device is compliant if only low-level threats exist.</span></span> <span data-ttu-id="410bd-150">Enheter med medelhöga eller höga hotnivåer följer inte kraven.</span><span class="sxs-lookup"><span data-stu-id="410bd-150">Devices with medium or high threat levels are not compliant.</span></span>
   - <span data-ttu-id="410bd-151">**Medel:** Enheten är kompatibel om hoten som finns på enheten är låga eller medelstora.</span><span class="sxs-lookup"><span data-stu-id="410bd-151">**Medium**: The device is compliant if the threats found on the device are low or medium.</span></span> <span data-ttu-id="410bd-152">Om hot på hög nivå upptäcks identifieras enheten som icke-kompatibel.</span><span class="sxs-lookup"><span data-stu-id="410bd-152">If high-level threats are detected, the device is determined as noncompliant.</span></span>
   - <span data-ttu-id="410bd-153">**Hög:** Den här nivån är den minst säkra och tillåter alla hotnivåer.</span><span class="sxs-lookup"><span data-stu-id="410bd-153">**High**: This level is the least secure, and allows all threat levels.</span></span> <span data-ttu-id="410bd-154">Enheter med höga, medelhöga eller låga hotnivåer anses därför vara kompatibla.</span><span class="sxs-lookup"><span data-stu-id="410bd-154">So devices that with high, medium or low threat levels are considered compliant.</span></span>

6. <span data-ttu-id="410bd-155">Välj **OK** och skapa **för** att spara ändringarna (och skapa principen).</span><span class="sxs-lookup"><span data-stu-id="410bd-155">Select **OK**, and **Create** to save your changes (and create the policy).</span></span>

### <a name="step-4-assign-the-policy"></a><span data-ttu-id="410bd-156">Steg 4: Tilldela principen</span><span class="sxs-lookup"><span data-stu-id="410bd-156">Step 4: Assign the policy</span></span>
1. <span data-ttu-id="410bd-157">I [Azure-portalen](https://portal.azure.com)väljer du **Alla tjänster**, filtrera på **Intune** och sedan **Microsoft Intune.**</span><span class="sxs-lookup"><span data-stu-id="410bd-157">In the [Azure portal](https://portal.azure.com), select **All services**, filter on **Intune**, and select **Microsoft Intune**.</span></span>
2. <span data-ttu-id="410bd-158">Välj **Policyer**  >  **för enhetsefterlevnad**> välj din Microsoft Defender ATP-efterlevnadsprincip.</span><span class="sxs-lookup"><span data-stu-id="410bd-158">Select **Device compliance** > **Policies**> select your Microsoft Defender ATP compliance policy.</span></span>
3. <span data-ttu-id="410bd-159">Välj **Uppgifter**.</span><span class="sxs-lookup"><span data-stu-id="410bd-159">Select **Assignments**.</span></span>
4. <span data-ttu-id="410bd-160">Inkludera eller exkludera dina Azure AD-grupper för att tilldela dem principen.</span><span class="sxs-lookup"><span data-stu-id="410bd-160">Include or exclude your Azure AD groups to assign them the policy.</span></span>
5. <span data-ttu-id="410bd-161">Välj Spara om du vill distribuera principen till **grupperna.**</span><span class="sxs-lookup"><span data-stu-id="410bd-161">To deploy the policy to the groups, select **Save**.</span></span> <span data-ttu-id="410bd-162">Användarenheterna som principen riktar sig till utvärderas för efterlevnad.</span><span class="sxs-lookup"><span data-stu-id="410bd-162">The user devices targeted by the policy are evaluated for compliance.</span></span>

### <a name="step-5-create-an-azure-ad-conditional-access-policy"></a><span data-ttu-id="410bd-163">Steg 5: Skapa en villkorsbaserad åtkomstprincip i Azure AD</span><span class="sxs-lookup"><span data-stu-id="410bd-163">Step 5: Create an Azure AD Conditional Access policy</span></span>
1. <span data-ttu-id="410bd-164">Öppna Ny [princip för villkorsstyrd](https://portal.azure.com) **åtkomst i Azure Active Directory**  >    >  **i Azure-portalen.**</span><span class="sxs-lookup"><span data-stu-id="410bd-164">In the [Azure portal](https://portal.azure.com), open **Azure Active Directory** > **Conditional Access** > **New policy**.</span></span>
2. <span data-ttu-id="410bd-165">Ange ett **principnamn** och välj **Användare och grupper.**</span><span class="sxs-lookup"><span data-stu-id="410bd-165">Enter a policy **Name**, and select **Users and groups**.</span></span> <span data-ttu-id="410bd-166">Använd alternativen Inkludera eller Exkludera för att lägga till grupper för principen och välj **Klar**.</span><span class="sxs-lookup"><span data-stu-id="410bd-166">Use the Include or Exclude options to add your groups for the policy, and select **Done**.</span></span>
3. <span data-ttu-id="410bd-167">Välj **Molnappar** och välj vilka appar du vill skydda.</span><span class="sxs-lookup"><span data-stu-id="410bd-167">Select **Cloud apps**, and choose which apps to protect.</span></span> <span data-ttu-id="410bd-168">Välj till exempel Välj **appar** och välj **Office 365 SharePoint Online** och Office **365 Exchange Online.**</span><span class="sxs-lookup"><span data-stu-id="410bd-168">For example, choose **Select apps**, and select **Office 365 SharePoint Online** and **Office 365 Exchange Online**.</span></span> <span data-ttu-id="410bd-169">Spara **ändringarna** genom att välja Klar.</span><span class="sxs-lookup"><span data-stu-id="410bd-169">Select **Done** to save your changes.</span></span>

4. <span data-ttu-id="410bd-170">Välj **Villkor**  >  **Klientappar för** att tillämpa principen för appar och webbläsare.</span><span class="sxs-lookup"><span data-stu-id="410bd-170">Select **Conditions** > **Client apps** to apply the policy to apps and browsers.</span></span> <span data-ttu-id="410bd-171">Välj till exempel Ja **och** aktivera sedan **Webbläsar- och** **mobilprogram och skrivbordsklienter**.</span><span class="sxs-lookup"><span data-stu-id="410bd-171">For example, select **Yes**, and then enable **Browser** and **Mobile apps and desktop clients**.</span></span> <span data-ttu-id="410bd-172">Spara **ändringarna** genom att välja Klar.</span><span class="sxs-lookup"><span data-stu-id="410bd-172">Select **Done** to save your changes.</span></span>

5. <span data-ttu-id="410bd-173">Välj **Bevilja för** att använda villkorsstyrd åtkomst baserat på enhetsefterlevnad.</span><span class="sxs-lookup"><span data-stu-id="410bd-173">Select **Grant** to apply Conditional Access based on device compliance.</span></span> <span data-ttu-id="410bd-174">Välj till exempel **Bevilja åtkomst**  >  **Kräv att enheten markeras som kompatibel.**</span><span class="sxs-lookup"><span data-stu-id="410bd-174">For example, select **Grant access** > **Require device to be marked as compliant**.</span></span> <span data-ttu-id="410bd-175">Spara **ändringarna** genom att välja Välj.</span><span class="sxs-lookup"><span data-stu-id="410bd-175">Choose **Select** to save your changes.</span></span>

6. <span data-ttu-id="410bd-176">Välj **Aktivera princip** och sedan Skapa **för** att spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="410bd-176">Select **Enable policy**, and then **Create** to save your changes.</span></span>

<span data-ttu-id="410bd-177">Mer information finns i Aktivera [Microsoft Defender ATP med villkorsstyrd åtkomst i Intune.](https://docs.microsoft.com/intune/advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="410bd-177">For more information, see [Enable Microsoft Defender ATP with Conditional Access in Intune](https://docs.microsoft.com/intune/advanced-threat-protection).</span></span>

><span data-ttu-id="410bd-178">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="410bd-178">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="410bd-179">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="410bd-179">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-conditionalaccess-belowfoldlink)
