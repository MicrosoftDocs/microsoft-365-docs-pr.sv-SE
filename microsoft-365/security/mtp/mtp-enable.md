---
title: Aktivera Microsoft Threat Protection i Microsoft 365-säkerhetscentret
description: Lär dig hur du aktiverar Microsoft Threat Protection och börjar integrera din säkerhetsincident och ditt säkerhetssvar.
keywords: komma igång, aktivera MTP, Microsoft Threat Protection, M365, säkerhet, dataplats, nödvändiga behörigheter, licensberättigande, inställningssida
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
ms.openlocfilehash: b6ac30f7e32bbec80952ad4f2104032886b11503
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/01/2020
ms.locfileid: "45016349"
---
# <a name="turn-on-microsoft-threat-protection"></a><span data-ttu-id="0e90d-104">Aktivera Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="0e90d-104">Turn on Microsoft Threat Protection</span></span>

<span data-ttu-id="0e90d-105">**Gäller:**</span><span class="sxs-lookup"><span data-stu-id="0e90d-105">**Applies to:**</span></span>
- <span data-ttu-id="0e90d-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="0e90d-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="0e90d-107">[Microsoft Threat Protection](microsoft-threat-protection.md) förenar din incidentsvarsprocess genom att integrera viktiga funktioner i Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security och Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="0e90d-107">[Microsoft Threat Protection](microsoft-threat-protection.md) unifies your incident response process by integrating key capabilities across Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="0e90d-108">Den här enhetliga upplevelsen ger dig kraftfulla funktioner som du kan komma åt i Microsoft 365-säkerhetscentret.</span><span class="sxs-lookup"><span data-stu-id="0e90d-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="0e90d-109">Microsoft Threat Protection aktiveras automatiskt när berättigade kunder med de behörigheter som krävs besöker Microsoft 365-säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="0e90d-109">Microsoft Threat Protection automatically turns on when eligible customers with the required permissions visit Microsoft 365 security center.</span></span> <span data-ttu-id="0e90d-110">Läs den här artikeln om du vill förstå olika förutsättningar och hur Microsoft Threat Protection etableras.</span><span class="sxs-lookup"><span data-stu-id="0e90d-110">Read this article to understand various prerequisites and how Microsoft Threat Protection is provisioned.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="0e90d-111">Kontrollera behörighet för licenser och nödvändiga behörigheter</span><span class="sxs-lookup"><span data-stu-id="0e90d-111">Check license eligibility and required permissions</span></span>
<span data-ttu-id="0e90d-112">En licens till en Microsoft 365-säkerhetsprodukt ger dig i allmänhet rätt att använda Microsoft Threat Protection i Microsoft 365-säkerhetscenter utan extra licenskostnader.</span><span class="sxs-lookup"><span data-stu-id="0e90d-112">A license to a Microsoft 365 security product generally entitles you to use Microsoft Threat Protection in Microsoft 365 security center without additional licensing cost.</span></span> <span data-ttu-id="0e90d-113">Vi rekommenderar att du skaffar en Microsoft 365 E5-, E5 Security-, A5- eller A5-säkerhetslicens eller en giltig kombination av licenser som ger åtkomst till alla tjänster som stöds.</span><span class="sxs-lookup"><span data-stu-id="0e90d-113">We do recommend getting a Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses that provides access to all supported services.</span></span>

<span data-ttu-id="0e90d-114">Detaljerad licensinformation [finns i licenskraven](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="0e90d-114">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="0e90d-115">Kontrollera din roll</span><span class="sxs-lookup"><span data-stu-id="0e90d-115">Check your role</span></span>
<span data-ttu-id="0e90d-116">Du måste vara **global administratör** eller **säkerhetsadministratör** i Azure Active Directory för att kunna aktivera Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="0e90d-116">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft Threat Protection.</span></span> [<span data-ttu-id="0e90d-117">Visa dina roller i Azure AD</span><span class="sxs-lookup"><span data-stu-id="0e90d-117">View your roles in Azure AD</span></span>](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a><span data-ttu-id="0e90d-118">Tjänster som stöds</span><span class="sxs-lookup"><span data-stu-id="0e90d-118">Supported services</span></span>
<span data-ttu-id="0e90d-119">Microsoft Threat Protection sammanställer data från de olika tjänster som stöds som du redan har distribuerat.</span><span class="sxs-lookup"><span data-stu-id="0e90d-119">Microsoft Threat Protection aggregates data from the various supported services that you've already deployed.</span></span> <span data-ttu-id="0e90d-120">Det kommer att bearbeta och lagra data centralt för att identifiera nya insikter och göra centraliserade svarsarbetsflöden möjliga.</span><span class="sxs-lookup"><span data-stu-id="0e90d-120">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span> <span data-ttu-id="0e90d-121">Det gör detta utan att påverka befintliga distributioner, inställningar eller data som är associerade med de integrerade tjänsterna.</span><span class="sxs-lookup"><span data-stu-id="0e90d-121">It does this without affecting existing deployments, settings, or data associated with the integrated services.</span></span>

<span data-ttu-id="0e90d-122">För att få bästa möjliga skydd och optimera Microsoft Threat Protection rekommenderar vi att du distribuerar alla tillämpliga tjänster som stöds i nätverket.</span><span class="sxs-lookup"><span data-stu-id="0e90d-122">To get the best protection and optimize Microsoft Threat Protection, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="0e90d-123">Mer information [finns i om hur du distribuerar tjänster som stöds](deploy-supported-services.md).</span><span class="sxs-lookup"><span data-stu-id="0e90d-123">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="before-starting-the-service"></a><span data-ttu-id="0e90d-124">Innan du påbörjar tjänsten</span><span class="sxs-lookup"><span data-stu-id="0e90d-124">Before starting the service</span></span>
<span data-ttu-id="0e90d-125">Innan du aktiverar tjänsten visar Microsoft 365-säkerhetscentret ([security.microsoft.com](https://security.microsoft.com)) sidan Microsoft Threat Protection-inställning när du väljer **Incidenter,** **Åtgärdscenter**eller **Jakt** i navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="0e90d-125">Before you turn on the service, the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) shows the Microsoft Threat Protection settings page when you select **Incidents**, **Action center**, or **Hunting** from the navigation pane.</span></span> <span data-ttu-id="0e90d-126">Dessa navigeringsobjekt visas inte om du inte kan använda Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="0e90d-126">These navigation items are not shown if you are not eligible to use Microsoft Threat Protection.</span></span>

<span data-ttu-id="0e90d-127">![Bild av inställningssidan för Microsoft Threat Protection som visas om Microsoft Threat Protection inte har aktiverats i ](../../media/mtp-enable/mtp-settings.png)
 *Microsoft Threat Protection-inställningarna i Microsoft 365-säkerhetscenter*</span><span class="sxs-lookup"><span data-stu-id="0e90d-127">![Image of the Microsoft Threat Protection settings page shown if Microsoft Threat Protection has not been turned on](../../media/mtp-enable/mtp-settings.png)
*Microsoft Threat Protection settings in Microsoft 365 security center*</span></span>

## <a name="starting-the-service"></a><span data-ttu-id="0e90d-128">Starta tjänsten</span><span class="sxs-lookup"><span data-stu-id="0e90d-128">Starting the service</span></span>
<span data-ttu-id="0e90d-129">Om du vill aktivera Microsoft Threat Protection väljer du Aktivera **Microsoft Threat Protection** och tillämpar ändringen.</span><span class="sxs-lookup"><span data-stu-id="0e90d-129">To turn on Microsoft Threat Protection, simply select **Turn on Microsoft Threat Protection** and apply the change.</span></span> <span data-ttu-id="0e90d-130">Du kan också komma åt det här alternativet genom att välja **Inställningar** ([security.microsoft.com/settings](https://security.microsoft.com/settings)) i navigeringsfönstret och sedan välja **Microsoft Threat Protection**.</span><span class="sxs-lookup"><span data-stu-id="0e90d-130">You can also access this option by selecting **Settings** ([security.microsoft.com/settings](https://security.microsoft.com/settings)) in the navigation pane and then selecting **Microsoft Threat Protection**.</span></span>

>[!NOTE]
><span data-ttu-id="0e90d-131">Om du inte ser **Inställningar** i navigeringsfönstret eller inte kunde komma åt sidan kontrollerar du dina behörigheter och licenser.</span><span class="sxs-lookup"><span data-stu-id="0e90d-131">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>

### <a name="data-center-location"></a><span data-ttu-id="0e90d-132">Plats för datacenter</span><span class="sxs-lookup"><span data-stu-id="0e90d-132">Data center location</span></span>
<span data-ttu-id="0e90d-133">Microsoft Threat Protection lagrar och bearbetar data på [samma plats som används av Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span><span class="sxs-lookup"><span data-stu-id="0e90d-133">Microsoft Threat Protection will store and process data in the [same location used by Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="0e90d-134">Om du inte har Microsoft Defender ATP väljs en ny datacenterplats automatiskt baserat på platsen för aktiva Microsoft 365-säkerhetstjänster.</span><span class="sxs-lookup"><span data-stu-id="0e90d-134">If you don't have Microsoft Defender ATP, a new data center location is automatically selected based on the location of active Microsoft 365 security services.</span></span> <span data-ttu-id="0e90d-135">Den valda datacenterplatsen visas på skärmen.</span><span class="sxs-lookup"><span data-stu-id="0e90d-135">The selected data center location is shown in the screen.</span></span> 

<span data-ttu-id="0e90d-136">Välj **Behöver du hjälp?** i Microsoft 365-säkerhetscentret för att kontakta Microsoft-supporten om etablering av Microsoft Threat Protection på en annan datacenterplats.</span><span class="sxs-lookup"><span data-stu-id="0e90d-136">Select **Need help?** in the Microsoft 365 security center to contact Microsoft support about provisioning Microsoft Threat Protection in a different data center location.</span></span> 

>[!NOTE]
><span data-ttu-id="0e90d-137">Microsoft Defender ATP etablerar automatiskt bestämmelser i EU-datacenter när de aktiveras via Azure Security Center.</span><span class="sxs-lookup"><span data-stu-id="0e90d-137">Microsoft Defender ATP automatically provisions in European Union (EU) data centers when turned on through Azure Security Center.</span></span> <span data-ttu-id="0e90d-138">Microsoft Threat Protection etableras automatiskt i samma EU-datacenter för kunder som har etablerat Microsoft Defender ATP på det här sättet.</span><span class="sxs-lookup"><span data-stu-id="0e90d-138">Microsoft Threat Protection will automatically provision in the same EU data center for customers who have provisioned Microsoft Defender ATP in this manner.</span></span> 

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="0e90d-139">Bekräfta att tjänsten är aktiverad</span><span class="sxs-lookup"><span data-stu-id="0e90d-139">Confirm that the service is on</span></span>
<span data-ttu-id="0e90d-140">När tjänsten har etablerats läggs den till:</span><span class="sxs-lookup"><span data-stu-id="0e90d-140">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="0e90d-141">Hantering av incidenter</span><span class="sxs-lookup"><span data-stu-id="0e90d-141">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="0e90d-142">Ett åtgärdscenter för hantering av [automatisk undersökning och svar](mtp-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="0e90d-142">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="0e90d-143">[Avancerad jaktkapacitet](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="0e90d-143">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>

<span data-ttu-id="0e90d-144">![Bild av navigeringsfönstret i Microsoft 365 security center med Microsoft Threat Protection-funktioner ](../../media/mtp-enable/mtp-on.png)
 *i Microsoft 365-säkerhetscenter med incidenthantering och andra funktioner för Microsoft Threat Protection*</span><span class="sxs-lookup"><span data-stu-id="0e90d-144">![Image of Microsoft 365 security center navigation pane with Microsoft Threat Protection features](../../media/mtp-enable/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft Threat Protection capabilities*</span></span>

### <a name="getting-azure-atp-data"></a><span data-ttu-id="0e90d-145">Hämta Azure ATP-data</span><span class="sxs-lookup"><span data-stu-id="0e90d-145">Getting Azure ATP data</span></span>
<span data-ttu-id="0e90d-146">Om du vill dela Azure ATP-data med Microsoft Threat Protection kontrollerar du att Microsoft Cloud App Security och Azure ATP-integrering är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="0e90d-146">To share Azure ATP data with Microsoft Threat Protection, ensure that Microsoft Cloud App Security and Azure ATP integration is turned on.</span></span> [<span data-ttu-id="0e90d-147">Läs mer om den här integrationen</span><span class="sxs-lookup"><span data-stu-id="0e90d-147">Learn more about this integration</span></span>](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a><span data-ttu-id="0e90d-148">Inaktivera Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="0e90d-148">Turn off Microsoft Threat Protection</span></span>
<span data-ttu-id="0e90d-149">Om du vill sluta använda Microsoft Threat Protection går du till **Inställningar**  >  **microsoft threat protection**  >  **opt-in / opt-out** i Microsoft 365 security center.</span><span class="sxs-lookup"><span data-stu-id="0e90d-149">To stop using Microsoft Threat Protection, go to **Settings** > **Microsoft Threat Protection** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="0e90d-150">Avmarkera **Aktivera Microsoft Threat Protection** och tillämpa ändringarna.</span><span class="sxs-lookup"><span data-stu-id="0e90d-150">Unselect **Turn on Microsoft Threat Protection** and apply the changes.</span></span>

<span data-ttu-id="0e90d-151">Motsvarande funktioner kommer att tas bort från Microsoft 365 säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="0e90d-151">Corresponding features will be removed from the Microsoft 365 security center.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="0e90d-152">Få hjälp</span><span class="sxs-lookup"><span data-stu-id="0e90d-152">Get assistance</span></span>

<span data-ttu-id="0e90d-153">Om du vill ha svar på de vanligaste frågorna om hur du aktiverar Microsoft Threat Protection [läser du vanliga frågor och svar](mtp-enable-faq.md).</span><span class="sxs-lookup"><span data-stu-id="0e90d-153">To get answers to the most commonly asked questions about turning on Microsoft Threat Protection, [read the FAQ](mtp-enable-faq.md).</span></span>

<span data-ttu-id="0e90d-154">Microsofts supportpersonal kan hjälpa till att etablera eller avetablera tjänsten och relaterade resurser på din klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="0e90d-154">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="0e90d-155">Om du behöver hjälp väljer du **Behöver du hjälp?**</span><span class="sxs-lookup"><span data-stu-id="0e90d-155">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="0e90d-156">NÃ¤s Ã¤n ã¤nder du support nÃ¤nder du Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="0e90d-156">When contacting support, mention Microsoft Threat Protection.</span></span>

## <a name="related-topics"></a><span data-ttu-id="0e90d-157">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="0e90d-157">Related topics</span></span>

- [<span data-ttu-id="0e90d-158">Vanliga frågor och svar</span><span class="sxs-lookup"><span data-stu-id="0e90d-158">Frequently asked questions</span></span>](mtp-enable-faq.md)
- [<span data-ttu-id="0e90d-159">Licenskrav och andra förutsättningar</span><span class="sxs-lookup"><span data-stu-id="0e90d-159">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="0e90d-160">Distribuera tjänster som stöds</span><span class="sxs-lookup"><span data-stu-id="0e90d-160">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="0e90d-161">Översikt över Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="0e90d-161">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="0e90d-162">Översikt över Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="0e90d-162">Microsoft Defender ATP overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="0e90d-163">Översikt över Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="0e90d-163">Office 365 ATP overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="0e90d-164">Översikt över Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="0e90d-164">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="0e90d-165">Översikt över Azure ATP</span><span class="sxs-lookup"><span data-stu-id="0e90d-165">Azure ATP overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="0e90d-166">Microsoft Defender ATP-datalagring</span><span class="sxs-lookup"><span data-stu-id="0e90d-166">Microsoft Defender ATP data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)