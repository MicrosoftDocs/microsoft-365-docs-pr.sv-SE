---
title: Aktivera skydd mot Microsoft Threat i säkerhets Center för Microsoft 365
description: Lär dig hur du aktiverar skydd mot Microsoft Threats och hur du integrerar dina säkerhets tillbud och svar.
keywords: komma igång, aktivera MTP, Microsoft Threat Protection, M365, säkerhet, data plats, behörigheter, licens kvalificering, sidan Inställningar
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 65e3a2609bc41ddeda95134874e5873e184a2a54
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201165"
---
# <a name="turn-on-microsoft-threat-protection"></a><span data-ttu-id="9495b-104">Aktivera Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="9495b-104">Turn on Microsoft Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9495b-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="9495b-105">**Applies to:**</span></span>
- <span data-ttu-id="9495b-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="9495b-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="9495b-107">[Skydd mot Microsoft-hotet](microsoft-threat-protection.md) interagerar med att integrera viktiga funktioner i Microsoft Defender Avancerat skydd (ATP), Office 365 ATP, Microsoft Cloud App Security och Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="9495b-107">[Microsoft Threat Protection](microsoft-threat-protection.md) unifies your incident response process by integrating key capabilities across Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="9495b-108">Denna enhetliga upplevelse lägger till kraftfulla funktioner som du kan komma åt i Microsoft 365 Security Center.</span><span class="sxs-lookup"><span data-stu-id="9495b-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="9495b-109">Skydd mot Microsoft Threat aktive ras automatiskt när berättigade kunder med nödvändig behörighet gå till Microsoft 365 säkerhets Center.</span><span class="sxs-lookup"><span data-stu-id="9495b-109">Microsoft Threat Protection automatically turns on when eligible customers with the required permissions visit Microsoft 365 security center.</span></span> <span data-ttu-id="9495b-110">Läs den här artikeln för att förstå olika förutsättningar och hur Microsoft Threat Protection etableras.</span><span class="sxs-lookup"><span data-stu-id="9495b-110">Read this article to understand various prerequisites and how Microsoft Threat Protection is provisioned.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="9495b-111">Kontrol lera licens krav och nödvändiga behörigheter</span><span class="sxs-lookup"><span data-stu-id="9495b-111">Check license eligibility and required permissions</span></span>
<span data-ttu-id="9495b-112">En licens till en Microsoft 365-säkerhetsprodukt ger generellt rätt att använda Microsoft Threat Protection i Microsoft 365 säkerhets Center utan extra licens kostnad.</span><span class="sxs-lookup"><span data-stu-id="9495b-112">A license to a Microsoft 365 security product generally entitles you to use Microsoft Threat Protection in Microsoft 365 security center without additional licensing cost.</span></span> <span data-ttu-id="9495b-113">Vi rekommenderar att få en Microsoft 365 E5-, E5-säkerhet, A5-eller A5-säkerhetslicens eller en giltig kombination av licenser som ger till gång till alla tjänster som stöds.</span><span class="sxs-lookup"><span data-stu-id="9495b-113">We do recommend getting a Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses that provides access to all supported services.</span></span>

<span data-ttu-id="9495b-114">Mer detaljerad information om licensiering finns [i licens kraven](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="9495b-114">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="9495b-115">Kontrol lera din roll</span><span class="sxs-lookup"><span data-stu-id="9495b-115">Check your role</span></span>
<span data-ttu-id="9495b-116">Du måste vara **Global administratör** eller **säkerhets administratör** i Azure Active Directory för att aktivera skydd mot Microsoft Threat.</span><span class="sxs-lookup"><span data-stu-id="9495b-116">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft Threat Protection.</span></span> [<span data-ttu-id="9495b-117">Visa dina roller i Azure AD</span><span class="sxs-lookup"><span data-stu-id="9495b-117">View your roles in Azure AD</span></span>](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a><span data-ttu-id="9495b-118">Tjänster som stöds</span><span class="sxs-lookup"><span data-stu-id="9495b-118">Supported services</span></span>
<span data-ttu-id="9495b-119">Microsoft Threat Protection samlar data från olika tjänster som du redan har distribuerat.</span><span class="sxs-lookup"><span data-stu-id="9495b-119">Microsoft Threat Protection aggregates data from the various supported services that you've already deployed.</span></span> <span data-ttu-id="9495b-120">Den bearbetar och lagrar data centralt för att identifiera nya insikter och göra centraliserade arbets flöden möjligt.</span><span class="sxs-lookup"><span data-stu-id="9495b-120">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span> <span data-ttu-id="9495b-121">Det gör det utan att befintliga distributioner, inställningar eller data som är kopplade till de integrerade tjänsterna påverkas.</span><span class="sxs-lookup"><span data-stu-id="9495b-121">It does this without affecting existing deployments, settings, or data associated with the integrated services.</span></span>

<span data-ttu-id="9495b-122">För att få bästa möjliga skydd och optimera Microsoft Threat Protection rekommenderar vi att du distribuerar alla tillämpliga tjänster som stöds på ditt nätverk.</span><span class="sxs-lookup"><span data-stu-id="9495b-122">To get the best protection and optimize Microsoft Threat Protection, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="9495b-123">Mer information finns i [om att distribuera tjänster som stöds](deploy-supported-services.md).</span><span class="sxs-lookup"><span data-stu-id="9495b-123">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="before-starting-the-service"></a><span data-ttu-id="9495b-124">Innan tjänsten startas</span><span class="sxs-lookup"><span data-stu-id="9495b-124">Before starting the service</span></span>
<span data-ttu-id="9495b-125">Innan du aktiverar tjänsten visar Microsoft 365 säkerhets Center ([Security.Microsoft.com](https://security.microsoft.com)) Sidan skydds inställningar för Microsoft Threat när du väljer **händelser**, **Åtgärds Center**eller **jakt** från navigerings fönstret.</span><span class="sxs-lookup"><span data-stu-id="9495b-125">Before you turn on the service, the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) shows the Microsoft Threat Protection settings page when you select **Incidents**, **Action center**, or **Hunting** from the navigation pane.</span></span> <span data-ttu-id="9495b-126">Dessa navigerings objekt visas inte om du inte är behörig att använda skydd mot Microsoft Threat.</span><span class="sxs-lookup"><span data-stu-id="9495b-126">These navigation items are not shown if you are not eligible to use Microsoft Threat Protection.</span></span>

<span data-ttu-id="9495b-127">![Bild av sidan Microsoft Threat Protection Settings som visas om Microsoft Threat Protection inte har Aktiver ATS för ](../../media/mtp-enable/mtp-settings.png)
 *Microsoft Threat Protection-inställningar i Microsoft 365 Security Center*</span><span class="sxs-lookup"><span data-stu-id="9495b-127">![Image of the Microsoft Threat Protection settings page shown if Microsoft Threat Protection has not been turned on](../../media/mtp-enable/mtp-settings.png)
*Microsoft Threat Protection settings in Microsoft 365 security center*</span></span>

## <a name="starting-the-service"></a><span data-ttu-id="9495b-128">Startar tjänsten</span><span class="sxs-lookup"><span data-stu-id="9495b-128">Starting the service</span></span>
<span data-ttu-id="9495b-129">Om du vill aktivera skyddet mot Microsoft Threats väljer du **aktivera Microsoft Threat Protection** och tillämpa ändringen.</span><span class="sxs-lookup"><span data-stu-id="9495b-129">To turn on Microsoft Threat Protection, simply select **Turn on Microsoft Threat Protection** and apply the change.</span></span> <span data-ttu-id="9495b-130">Du kan också komma åt det här alternativet genom att välja **Inställningar** ([Security.Microsoft.com/settings](https://security.microsoft.com/settings)) i navigerings fönstret och sedan välja **Microsoft Threat Protection**.</span><span class="sxs-lookup"><span data-stu-id="9495b-130">You can also access this option by selecting **Settings** ([security.microsoft.com/settings](https://security.microsoft.com/settings)) in the navigation pane and then selecting **Microsoft Threat Protection**.</span></span>

>[!NOTE]
><span data-ttu-id="9495b-131">Om du inte ser **Inställningar** i navigerings fönstret eller inte har åtkomst till sidan kontrollerar du dina behörigheter och licenser.</span><span class="sxs-lookup"><span data-stu-id="9495b-131">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>

### <a name="data-center-location"></a><span data-ttu-id="9495b-132">Plats för data Center</span><span class="sxs-lookup"><span data-stu-id="9495b-132">Data center location</span></span>
<span data-ttu-id="9495b-133">Microsoft Threat Protection lagrar och bearbetar data på [samma plats som Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span><span class="sxs-lookup"><span data-stu-id="9495b-133">Microsoft Threat Protection will store and process data in the [same location used by Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="9495b-134">Om du inte har Microsoft Defender ATP, väljs automatiskt en ny data Center plats som baseras på platsen för den aktiva Microsoft 365-säkerhetstjänsten.</span><span class="sxs-lookup"><span data-stu-id="9495b-134">If you don't have Microsoft Defender ATP, a new data center location is automatically selected based on the location of active Microsoft 365 security services.</span></span> <span data-ttu-id="9495b-135">Den valda data Center platsen visas på skärmen.</span><span class="sxs-lookup"><span data-stu-id="9495b-135">The selected data center location is shown in the screen.</span></span> 

<span data-ttu-id="9495b-136">Välj **behöver du hjälp?** i Microsoft 365 säkerhets Center kan du kontakta Microsoft support om att tillhandahålla Microsoft Threat Protection på en annan plats i data centret.</span><span class="sxs-lookup"><span data-stu-id="9495b-136">Select **Need help?** in the Microsoft 365 security center to contact Microsoft support about provisioning Microsoft Threat Protection in a different data center location.</span></span> 

>[!NOTE]
><span data-ttu-id="9495b-137">Microsoft Defender ATP tillhandahåller automatiskt bestämmelser i EU-datacenter när de aktive ras via Azure Security Center.</span><span class="sxs-lookup"><span data-stu-id="9495b-137">Microsoft Defender ATP automatically provisions in European Union (EU) data centers when turned on through Azure Security Center.</span></span> <span data-ttu-id="9495b-138">Microsoft Threat Protection tillhandahåller automatiskt samma EU-datacenter för kunder som har etablerat Microsoft Defender ATP på det här sättet.</span><span class="sxs-lookup"><span data-stu-id="9495b-138">Microsoft Threat Protection will automatically provision in the same EU data center for customers who have provisioned Microsoft Defender ATP in this manner.</span></span> 

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="9495b-139">Kontrol lera att tjänsten är på</span><span class="sxs-lookup"><span data-stu-id="9495b-139">Confirm that the service is on</span></span>
<span data-ttu-id="9495b-140">När tjänsten har etablerats lägger den till:</span><span class="sxs-lookup"><span data-stu-id="9495b-140">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="9495b-141">Hantering av incidenter</span><span class="sxs-lookup"><span data-stu-id="9495b-141">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="9495b-142">Ett åtgärds Center för att hantera [Automatisk undersökning och svar](mtp-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="9495b-142">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="9495b-143">[Avancerade jakt](advanced-hunting-overview.md) funktioner</span><span class="sxs-lookup"><span data-stu-id="9495b-143">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>

<span data-ttu-id="9495b-144">![Bild av navigerings fönstret i Microsoft 365 säkerhets Center med Microsoft Threat Protection ](../../media/mtp-enable/mtp-on.png)
 *, Microsoft 365 säkerhets Center med problem hantering och andra hot Protection-funktioner från Microsoft*</span><span class="sxs-lookup"><span data-stu-id="9495b-144">![Image of Microsoft 365 security center navigation pane with Microsoft Threat Protection features](../../media/mtp-enable/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft Threat Protection capabilities*</span></span>

### <a name="getting-azure-atp-data"></a><span data-ttu-id="9495b-145">Hämta data för Azure ATP</span><span class="sxs-lookup"><span data-stu-id="9495b-145">Getting Azure ATP data</span></span>
<span data-ttu-id="9495b-146">Om du vill dela Azure ATP-data med Microsoft Threat Protection kontrollerar du att Microsoft Cloud App Security och Azure ATP-integreringen är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="9495b-146">To share Azure ATP data with Microsoft Threat Protection, ensure that Microsoft Cloud App Security and Azure ATP integration is turned on.</span></span> [<span data-ttu-id="9495b-147">Läs mer om denna integrering</span><span class="sxs-lookup"><span data-stu-id="9495b-147">Learn more about this integration</span></span>](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a><span data-ttu-id="9495b-148">Inaktivera skydd mot Microsoft Threat</span><span class="sxs-lookup"><span data-stu-id="9495b-148">Turn off Microsoft Threat Protection</span></span>
<span data-ttu-id="9495b-149">Om du vill sluta använda skydd mot Microsoft kan du gå till **Inställningar**  >  **Microsoft Threat Protection**  >  **och välja bort** Microsoft 365 säkerhets Center.</span><span class="sxs-lookup"><span data-stu-id="9495b-149">To stop using Microsoft Threat Protection, go to **Settings** > **Microsoft Threat Protection** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="9495b-150">Avmarkera **aktivera Microsoft Threat Protection** och tillämpa ändringarna.</span><span class="sxs-lookup"><span data-stu-id="9495b-150">Unselect **Turn on Microsoft Threat Protection** and apply the changes.</span></span>

<span data-ttu-id="9495b-151">Motsvarande funktioner tas bort från Microsoft 365 säkerhets Center.</span><span class="sxs-lookup"><span data-stu-id="9495b-151">Corresponding features will be removed from the Microsoft 365 security center.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="9495b-152">Få hjälp</span><span class="sxs-lookup"><span data-stu-id="9495b-152">Get assistance</span></span>

<span data-ttu-id="9495b-153">Om du vill få svar på de vanligaste frågorna om att aktivera skydd mot Microsoft Threat kan du [läsa vanliga frågor och svar](mtp-enable-faq.md).</span><span class="sxs-lookup"><span data-stu-id="9495b-153">To get answers to the most commonly asked questions about turning on Microsoft Threat Protection, [read the FAQ](mtp-enable-faq.md).</span></span>

<span data-ttu-id="9495b-154">Microsofts support personal kan tillhandahålla eller avetablera tjänsten och relaterade resurser för din klient organisation.</span><span class="sxs-lookup"><span data-stu-id="9495b-154">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="9495b-155">För mer information, Välj **behöver du hjälp?** i Microsoft 365 Security Center.</span><span class="sxs-lookup"><span data-stu-id="9495b-155">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="9495b-156">När du kontaktar supporten kan du nämna Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="9495b-156">When contacting support, mention Microsoft Threat Protection.</span></span>

## <a name="related-topics"></a><span data-ttu-id="9495b-157">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="9495b-157">Related topics</span></span>

- [<span data-ttu-id="9495b-158">Vanliga frågor och svar</span><span class="sxs-lookup"><span data-stu-id="9495b-158">Frequently asked questions</span></span>](mtp-enable-faq.md)
- [<span data-ttu-id="9495b-159">Licens krav och andra förutsättningar</span><span class="sxs-lookup"><span data-stu-id="9495b-159">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="9495b-160">Distribuera tjänster som stöds</span><span class="sxs-lookup"><span data-stu-id="9495b-160">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="9495b-161">Microsoft Threat Protection-översikt</span><span class="sxs-lookup"><span data-stu-id="9495b-161">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="9495b-162">Översikt över Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="9495b-162">Microsoft Defender ATP overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="9495b-163">Office 365 ATP-översikt</span><span class="sxs-lookup"><span data-stu-id="9495b-163">Office 365 ATP overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="9495b-164">Säkerhets översikt för Microsoft Cloud App</span><span class="sxs-lookup"><span data-stu-id="9495b-164">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="9495b-165">Översikt över Azure ATP</span><span class="sxs-lookup"><span data-stu-id="9495b-165">Azure ATP overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="9495b-166">Microsoft Defender ATP-data lagring</span><span class="sxs-lookup"><span data-stu-id="9495b-166">Microsoft Defender ATP data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
