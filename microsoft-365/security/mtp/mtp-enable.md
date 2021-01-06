---
title: Aktivera Microsoft 365 Defender i Microsoft 365 säkerhets Center
description: Lär dig hur du aktiverar Microsoft 365 Defender och hur du integrerar dina säkerhets tillbud och svar.
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
ms.openlocfilehash: b052f70c1b618adef12c4f70c2b3fe55741697d5
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760512"
---
# <a name="turn-on-microsoft-365-defender"></a><span data-ttu-id="31887-104">Aktivera Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="31887-104">Turn on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="31887-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="31887-105">**Applies to:**</span></span>
- <span data-ttu-id="31887-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="31887-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="31887-107">Med [microsoft 365 Defender](microsoft-threat-protection.md) interagerar samtals processen med att integrera viktiga funktioner i Microsoft Defender för slut punkt, Microsoft Defender för Office 365, Microsoft Cloud App Security och Microsoft Defender för identiteten.</span><span class="sxs-lookup"><span data-stu-id="31887-107">[Microsoft 365 Defender](microsoft-threat-protection.md) unifies your incident response process by integrating key capabilities across Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="31887-108">Denna enhetliga upplevelse lägger till kraftfulla funktioner som du kan komma åt i Microsoft 365 Security Center.</span><span class="sxs-lookup"><span data-stu-id="31887-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="31887-109">Microsoft 365 Defender aktive ras automatiskt när berättigade kunder med nödvändig behörighet gå till Microsoft 365 säkerhets Center.</span><span class="sxs-lookup"><span data-stu-id="31887-109">Microsoft 365 Defender automatically turns on when eligible customers with the required permissions visit Microsoft 365 security center.</span></span> <span data-ttu-id="31887-110">Läs den här artikeln för att förstå olika förutsättningar och hur Microsoft 365 Defender etableras.</span><span class="sxs-lookup"><span data-stu-id="31887-110">Read this article to understand various prerequisites and how Microsoft 365 Defender is provisioned.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="31887-111">Kontrol lera licens krav och nödvändiga behörigheter</span><span class="sxs-lookup"><span data-stu-id="31887-111">Check license eligibility and required permissions</span></span>

<span data-ttu-id="31887-112">Med en licens till en Microsoft 365-säkerhetsprodukt får du i allmänhet rätt att använda Microsoft 365 Defender i Microsoft 365 säkerhets Center utan extra licens kostnad.</span><span class="sxs-lookup"><span data-stu-id="31887-112">A license to a Microsoft 365 security product generally entitles you to use Microsoft 365 Defender in Microsoft 365 security center without additional licensing cost.</span></span> <span data-ttu-id="31887-113">Vi rekommenderar att få en Microsoft 365 E5-, E5-säkerhet, A5-eller A5-säkerhetslicens eller en giltig kombination av licenser som ger till gång till alla tjänster som stöds.</span><span class="sxs-lookup"><span data-stu-id="31887-113">We do recommend getting a Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses that provides access to all supported services.</span></span>

<span data-ttu-id="31887-114">Mer detaljerad information om licensiering finns [i licens kraven](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="31887-114">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="31887-115">Kontrol lera din roll</span><span class="sxs-lookup"><span data-stu-id="31887-115">Check your role</span></span>

<span data-ttu-id="31887-116">Du måste vara **Global administratör** eller **säkerhets administratör** i Azure Active Directory för att aktivera Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="31887-116">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> [<span data-ttu-id="31887-117">Visa dina roller i Azure AD</span><span class="sxs-lookup"><span data-stu-id="31887-117">View your roles in Azure AD</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a><span data-ttu-id="31887-118">Tjänster som stöds</span><span class="sxs-lookup"><span data-stu-id="31887-118">Supported services</span></span>

<span data-ttu-id="31887-119">Microsoft 365 Defender sammanställer data från de tjänster som du redan har distribuerat.</span><span class="sxs-lookup"><span data-stu-id="31887-119">Microsoft 365 Defender aggregates data from the various supported services that you've already deployed.</span></span> <span data-ttu-id="31887-120">Den bearbetar och lagrar data centralt för att identifiera nya insikter och göra centraliserade arbets flöden möjligt.</span><span class="sxs-lookup"><span data-stu-id="31887-120">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span> <span data-ttu-id="31887-121">Det gör det utan att befintliga distributioner, inställningar eller data som är kopplade till de integrerade tjänsterna påverkas.</span><span class="sxs-lookup"><span data-stu-id="31887-121">It does this without affecting existing deployments, settings, or data associated with the integrated services.</span></span>

<span data-ttu-id="31887-122">För att få bästa möjliga skydd och optimera Microsoft 365 Defender rekommenderar vi att du distribuerar alla tillämpliga tjänster som stöds i ditt nätverk.</span><span class="sxs-lookup"><span data-stu-id="31887-122">To get the best protection and optimize Microsoft 365 Defender, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="31887-123">Mer information finns i [om att distribuera tjänster som stöds](deploy-supported-services.md).</span><span class="sxs-lookup"><span data-stu-id="31887-123">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="before-starting-the-service"></a><span data-ttu-id="31887-124">Innan tjänsten startas</span><span class="sxs-lookup"><span data-stu-id="31887-124">Before starting the service</span></span>

<span data-ttu-id="31887-125">Innan du aktiverar tjänsten visar Microsoft 365 säkerhets Center ([Security.Microsoft.com](https://security.microsoft.com)) sidan Microsoft 365 Defender-inställningar när du väljer **händelser**, **Åtgärds Center** eller **jakt** från navigerings fönstret.</span><span class="sxs-lookup"><span data-stu-id="31887-125">Before you turn on the service, the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) shows the Microsoft 365 Defender settings page when you select **Incidents**, **Action center**, or **Hunting** from the navigation pane.</span></span> <span data-ttu-id="31887-126">Dessa navigerings objekt visas inte om du inte är berättigad att använda Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="31887-126">These navigation items are not shown if you are not eligible to use Microsoft 365 Defender.</span></span>

<span data-ttu-id="31887-127">![Bild av sidan Microsoft 365 Defender-inställningar som visas om Microsoft 365 Defender inte har Aktiver ATS på ](../../media/mtp-enable/mtp-settings.png)
 *Microsoft 365 Defender-inställningar i Microsoft 365 säkerhets Center*</span><span class="sxs-lookup"><span data-stu-id="31887-127">![Image of the Microsoft 365 Defender settings page shown if Microsoft 365 Defender has not been turned on](../../media/mtp-enable/mtp-settings.png)
*Microsoft 365 Defender settings in Microsoft 365 security center*</span></span>

## <a name="starting-the-service"></a><span data-ttu-id="31887-128">Startar tjänsten</span><span class="sxs-lookup"><span data-stu-id="31887-128">Starting the service</span></span>

<span data-ttu-id="31887-129">För att aktivera Microsoft 365 Defender väljer du **Aktivera microsoft 365 Defender** och gör ändringarna.</span><span class="sxs-lookup"><span data-stu-id="31887-129">To turn on Microsoft 365 Defender, simply select **Turn on Microsoft 365 Defender** and apply the change.</span></span> <span data-ttu-id="31887-130">Du kan också komma åt det här alternativet genom att välja **Inställningar** ([Security.Microsoft.com/settings](https://security.microsoft.com/settings)) i navigerings fönstret och sedan välja **Microsoft 365 Defender**.</span><span class="sxs-lookup"><span data-stu-id="31887-130">You can also access this option by selecting **Settings** ([security.microsoft.com/settings](https://security.microsoft.com/settings)) in the navigation pane and then selecting **Microsoft 365 Defender**.</span></span>

> [!NOTE]
> <span data-ttu-id="31887-131">Om du inte ser **Inställningar** i navigerings fönstret eller inte har åtkomst till sidan kontrollerar du dina behörigheter och licenser.</span><span class="sxs-lookup"><span data-stu-id="31887-131">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>

### <a name="data-center-location"></a><span data-ttu-id="31887-132">Plats för data Center</span><span class="sxs-lookup"><span data-stu-id="31887-132">Data center location</span></span>

<span data-ttu-id="31887-133">Microsoft 365 Defender lagrar och bearbetar data på [samma plats som Microsoft Defender för slut punkten](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span><span class="sxs-lookup"><span data-stu-id="31887-133">Microsoft 365 Defender will store and process data in the [same location used by Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="31887-134">Om du inte har Microsoft Defender för slut punkt väljs en ny data Center-plats automatiskt baserat på platsen för Active Microsoft 365-säkerhetstjänster.</span><span class="sxs-lookup"><span data-stu-id="31887-134">If you don't have Microsoft Defender for Endpoint, a new data center location is automatically selected based on the location of active Microsoft 365 security services.</span></span> <span data-ttu-id="31887-135">Den valda data Center platsen visas på skärmen.</span><span class="sxs-lookup"><span data-stu-id="31887-135">The selected data center location is shown in the screen.</span></span>

<span data-ttu-id="31887-136">Välj **behöver du hjälp?** i Microsoft 365 Security Center kan du kontakta Microsoft support om hur du konfigurerar Microsoft 365 Defender på en annan plats i data centret.</span><span class="sxs-lookup"><span data-stu-id="31887-136">Select **Need help?** in the Microsoft 365 security center to contact Microsoft support about provisioning Microsoft 365 Defender in a different data center location.</span></span>

> [!NOTE]
> <span data-ttu-id="31887-137">Microsoft Defender för slut punkt tillhandahåller automatiskt bestämmelser i EU-datacenter när de aktive ras via Azure Defender.</span><span class="sxs-lookup"><span data-stu-id="31887-137">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="31887-138">Microsoft 365 Defender tillhandahåller automatiskt samma EU-datacentertjänster för kunder som har etablerat Defender för slut punkt på det här sättet.</span><span class="sxs-lookup"><span data-stu-id="31887-138">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Defender for Endpoint in this manner.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="31887-139">Kontrol lera att tjänsten är på</span><span class="sxs-lookup"><span data-stu-id="31887-139">Confirm that the service is on</span></span>

<span data-ttu-id="31887-140">När tjänsten har etablerats lägger den till:</span><span class="sxs-lookup"><span data-stu-id="31887-140">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="31887-141">Hantering av incidenter</span><span class="sxs-lookup"><span data-stu-id="31887-141">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="31887-142">Ett åtgärds Center för att hantera [Automatisk undersökning och svar](mtp-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="31887-142">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="31887-143">[Avancerade jakt](advanced-hunting-overview.md) funktioner</span><span class="sxs-lookup"><span data-stu-id="31887-143">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>

<span data-ttu-id="31887-144">![Bild av navigerings fönstret i Microsoft 365 säkerhets Center med Microsoft 365 Defender funktioner ](../../media/mtp-enable/mtp-on.png)
 *Microsoft 365 säkerhets Center med problem hantering och andra Microsoft 365 Defender-funktioner*</span><span class="sxs-lookup"><span data-stu-id="31887-144">![Image of Microsoft 365 security center navigation pane with Microsoft 365 Defender features](../../media/mtp-enable/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft 365 Defender capabilities*</span></span>

### <a name="getting-microsoft-defender-for-identity-data"></a><span data-ttu-id="31887-145">Microsoft Defender för identitets data</span><span class="sxs-lookup"><span data-stu-id="31887-145">Getting Microsoft Defender for Identity data</span></span>

<span data-ttu-id="31887-146">Om du vill dela Microsoft Defender för identitets data med Microsoft 365 Defender kontrollerar du att säkerhet för Microsoft Cloud App och Microsoft Defender för identitets integrering är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="31887-146">To share Microsoft Defender for Identity data with Microsoft 365 Defender, ensure that Microsoft Cloud App Security and Microsoft Defender for Identity integration is turned on.</span></span> <span data-ttu-id="31887-147">[Läs mer om denna integrering](https://docs.microsoft.com/cloud-app-security/mdi-integration).</span><span class="sxs-lookup"><span data-stu-id="31887-147">[Learn more about this integration](https://docs.microsoft.com/cloud-app-security/mdi-integration).</span></span>

## <a name="get-assistance"></a><span data-ttu-id="31887-148">Få hjälp</span><span class="sxs-lookup"><span data-stu-id="31887-148">Get assistance</span></span>

<span data-ttu-id="31887-149">Om du vill få svar på de vanligaste frågorna om att aktivera Microsoft 365 Defender [läser du vanliga frågor och svar](mtp-enable-faq.md).</span><span class="sxs-lookup"><span data-stu-id="31887-149">To get answers to the most commonly asked questions about turning on Microsoft 365 Defender, [read the FAQ](mtp-enable-faq.md).</span></span>

<span data-ttu-id="31887-150">Microsofts support personal kan tillhandahålla eller avetablera tjänsten och relaterade resurser för din klient organisation.</span><span class="sxs-lookup"><span data-stu-id="31887-150">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="31887-151">För mer information, Välj **behöver du hjälp?** i Microsoft 365 Security Center.</span><span class="sxs-lookup"><span data-stu-id="31887-151">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="31887-152">När du kontaktar supporten, omnämnande Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="31887-152">When contacting support, mention Microsoft 365 Defender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="31887-153">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="31887-153">Related topics</span></span>

- [<span data-ttu-id="31887-154">Vanliga frågor och svar</span><span class="sxs-lookup"><span data-stu-id="31887-154">Frequently asked questions</span></span>](mtp-enable-faq.md)
- [<span data-ttu-id="31887-155">Licens krav och andra förutsättningar</span><span class="sxs-lookup"><span data-stu-id="31887-155">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="31887-156">Distribuera tjänster som stöds</span><span class="sxs-lookup"><span data-stu-id="31887-156">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="31887-157">Översikt över Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="31887-157">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="31887-158">Översikt över Microsoft Defender för slut punkter</span><span class="sxs-lookup"><span data-stu-id="31887-158">Microsoft Defender for Endpoint overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="31887-159">Översikt över Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="31887-159">Defender for Office 365 overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="31887-160">Säkerhets översikt för Microsoft Cloud App</span><span class="sxs-lookup"><span data-stu-id="31887-160">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="31887-161">Microsoft Defender för identitets översikt</span><span class="sxs-lookup"><span data-stu-id="31887-161">Microsoft Defender for Identity overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="31887-162">Microsoft Defender för slut punkts data lagring</span><span class="sxs-lookup"><span data-stu-id="31887-162">Microsoft Defender for Endpoint data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
