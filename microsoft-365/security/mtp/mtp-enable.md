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
ms.openlocfilehash: 9a57929e42f08db8abda170c889441d3a50ade72
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209253"
---
# <a name="turn-on-microsoft-threat-protection"></a><span data-ttu-id="b228f-104">Aktivera Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="b228f-104">Turn on Microsoft Threat Protection</span></span>

<span data-ttu-id="b228f-105">**Gäller:**</span><span class="sxs-lookup"><span data-stu-id="b228f-105">**Applies to:**</span></span>
- <span data-ttu-id="b228f-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="b228f-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="b228f-107">Microsoft Threat Protection förenar din incidentsvarsprocess genom att integrera nyckelfunktioner i Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security och Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="b228f-107">Microsoft Threat Protection unifies your incident response process by integrating key capabilities across Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="b228f-108">Den här enhetliga upplevelsen ger dig kraftfulla funktioner som du kan komma åt i Microsoft 365-säkerhetscentret.</span><span class="sxs-lookup"><span data-stu-id="b228f-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="b228f-109">För att få bästa möjliga skydd och optimera Microsofts hotskydd rekommenderar vi att du distribuerar alla tillämpliga tjänster som stöds i nätverket.</span><span class="sxs-lookup"><span data-stu-id="b228f-109">To get the best protection and optimize Microsoft Threat Protection, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="b228f-110">Mer information [finns i om hur du distribuerar tjänster som stöds](deploy-supported-services.md).</span><span class="sxs-lookup"><span data-stu-id="b228f-110">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="b228f-111">Kontrollera behörighet för licenser och nödvändiga behörigheter</span><span class="sxs-lookup"><span data-stu-id="b228f-111">Check license eligibility and required permissions</span></span>
<span data-ttu-id="b228f-112">En Microsoft 365 E5-, E5 Security-, A5- eller A5-säkerhetslicens eller en giltig kombination av licenser ger åtkomst till tjänster som stöds och ger dig rätt att använda Microsoft Threat Protection i Microsoft 365-säkerhetscenter utan ytterligare licenskostnader.</span><span class="sxs-lookup"><span data-stu-id="b228f-112">A Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses provides access to supported services and entitles you to use Microsoft Threat Protection in Microsoft 365 security center without additional licensing cost.</span></span>

<span data-ttu-id="b228f-113">Detaljerad licensinformation [finns i licenskraven](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="b228f-113">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="b228f-114">Kontrollera din roll</span><span class="sxs-lookup"><span data-stu-id="b228f-114">Check your role</span></span>
<span data-ttu-id="b228f-115">Du måste vara **global administratör** eller **säkerhetsadministratör** i Azure Active Directory för att kunna aktivera Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="b228f-115">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft Threat Protection.</span></span> [<span data-ttu-id="b228f-116">Visa dina roller i Azure AD</span><span class="sxs-lookup"><span data-stu-id="b228f-116">View your roles in Azure AD</span></span>](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="start-using-the-service"></a><span data-ttu-id="b228f-117">Börja använda tjänsten</span><span class="sxs-lookup"><span data-stu-id="b228f-117">Start using the service</span></span>

>[!IMPORTANT]
><span data-ttu-id="b228f-118">Från och med den 12 maj 2020 kommer Microsoft gradvis att lansera nya, optimerade upplevelser kring [licenskrav](prerequisites.md#licensing-requirements) och aktivera Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="b228f-118">Starting May 12, 2020, Microsoft will gradually roll out new, optimized experiences around [licensing requirements](prerequisites.md#licensing-requirements) and turning on Microsoft Threat Protection.</span></span> <span data-ttu-id="b228f-119">Under flera veckor under denna period kommer vissa kunder att börja se ändringar i sina portalupplevelser.</span><span class="sxs-lookup"><span data-stu-id="b228f-119">For several weeks during this period, some customers will start to see changes to their portal experiences.</span></span> <span data-ttu-id="b228f-120">Information om de nya upplevelserna markeras **Ny upplevelse** i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="b228f-120">Information about the new experiences are marked **New experience** in this article.</span></span>

<span data-ttu-id="b228f-121">Microsoft Threat Protection sammanställer data från de olika integrerade tjänsterna.</span><span class="sxs-lookup"><span data-stu-id="b228f-121">Microsoft Threat Protection aggregates data from the various integrated services.</span></span> <span data-ttu-id="b228f-122">Det kommer att bearbeta och lagra data centralt för att identifiera nya insikter och göra centraliserade svarsarbetsflöden möjliga.</span><span class="sxs-lookup"><span data-stu-id="b228f-122">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span> <span data-ttu-id="b228f-123">Det gör detta utan att påverka befintliga distributioner, inställningar eller data som är associerade med de integrerade tjänsterna.</span><span class="sxs-lookup"><span data-stu-id="b228f-123">It does this without affecting existing deployments, settings, or data associated with the integrated services.</span></span>

<span data-ttu-id="b228f-124">Innan du aktiverar tjänsten visar Microsoft 365-säkerhetscentret ([security.microsoft.com](https://security.microsoft.com)) välkomstsidan för Microsoft Threat Protection när du väljer **Incidenter,** **Åtgärdscenter**eller **Jakt** i navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="b228f-124">Before you turn on the service, the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) shows the Microsoft Threat Protection welcome page when you select **Incidents**, **Action center**, or **Hunting** from the navigation pane.</span></span> <span data-ttu-id="b228f-125">Dessa navigeringsalternativ visas inte om du inte kan använda Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="b228f-125">These navigation options are not shown if you are not eligible to use Microsoft Threat Protection.</span></span>

<span data-ttu-id="b228f-126">![Bild av välkomstsidan för Microsoft Threat Protection som visas om Microsoft Threat Protection inte har aktiverats på ](../../media/mtp-welcome.png)
 *välkomstsidan för Microsoft Threat Protection i Microsoft 365-säkerhetscenter*</span><span class="sxs-lookup"><span data-stu-id="b228f-126">![Image of the Microsoft Threat Protection welcome page shown if Microsoft Threat Protection has not been turned on](../../media/mtp-welcome.png)
*Microsoft Threat Protection welcome page in Microsoft 365 security center*</span></span>

<span data-ttu-id="b228f-127">Om du vill aktivera Microsoft Threat Protection slutför du helt enkelt processen från välkomstsidan.</span><span class="sxs-lookup"><span data-stu-id="b228f-127">To turn on Microsoft Threat Protection, simply complete the process from the welcome page.</span></span> <span data-ttu-id="b228f-128">Du kan också aktivera Microsoft Threat Protection genom att komma åt **Inställningar** ([security.microsoft.com/settings](https://security.microsoft.com/settings)) i navigeringsfönstret och välja **Microsoft Threat Protection**.</span><span class="sxs-lookup"><span data-stu-id="b228f-128">You can also turn on Microsoft Threat Protection by accessing **Settings** ([security.microsoft.com/settings](https://security.microsoft.com/settings)) in the navigation pane and selecting **Microsoft Threat Protection**.</span></span>

>[!NOTE]
><span data-ttu-id="b228f-129">Om du inte ser **Inställningar** i navigeringsfönstret eller inte kunde komma åt sidan kontrollerar du dina behörigheter och licenser.</span><span class="sxs-lookup"><span data-stu-id="b228f-129">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>

### <a name="select-data-center-location"></a><span data-ttu-id="b228f-130">Välj datacenterplats</span><span class="sxs-lookup"><span data-stu-id="b228f-130">Select data center location</span></span>
<span data-ttu-id="b228f-131">Om Microsoft Defender ATP har etablerats för din organisation lagras och bearbetas data på samma datacenterplats som du har valt för [microsoft Defender ATP-data](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span><span class="sxs-lookup"><span data-stu-id="b228f-131">If Microsoft Defender ATP has been provisioned for your organization, data will be stored and processed in the same data center location you have selected for [your Microsoft Defender ATP data](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="b228f-132">Om du inte har Microsoft Defender ATP blir du ombedd att välja en ny datacenterplats specifikt för Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="b228f-132">If you don't have Microsoft Defender ATP, you will be asked to choose a new data center location specifically for Microsoft Threat Protection.</span></span> 
 
<span data-ttu-id="b228f-133">Du måste ge ditt samtycke innan data delas mellan tjänster och aggregeras.</span><span class="sxs-lookup"><span data-stu-id="b228f-133">You need to provide consent before data is shared between services and aggregated.</span></span>

<span data-ttu-id="b228f-134">**Ny erfarenhet:** Från och med den 12 maj 2020 kommer kunderna gradvis att få ändringar i den här upplevelsen.</span><span class="sxs-lookup"><span data-stu-id="b228f-134">**New experience:** Starting May 12, 2020, customers will gradually receive changes to this experience.</span></span> <span data-ttu-id="b228f-135">För dem med den nya upplevelsen väljer tjänsten automatiskt den optimala datacenterplatsen för dina aggregerade data baserat på dina befintliga Microsoft 365-säkerhetstjänster.</span><span class="sxs-lookup"><span data-stu-id="b228f-135">For those with the new experience, the service automatically selects the optimal data center location for your aggregated data based on your existing Microsoft 365 security services.</span></span> <span data-ttu-id="b228f-136">Den valda datacenterplatsen visas på skärmen.</span><span class="sxs-lookup"><span data-stu-id="b228f-136">The selected data center location is shown in the screen.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="b228f-137">Bekräfta att tjänsten är aktiverad</span><span class="sxs-lookup"><span data-stu-id="b228f-137">Confirm that the service is on</span></span>
<span data-ttu-id="b228f-138">När tjänsten har etablerats läggs följande till:</span><span class="sxs-lookup"><span data-stu-id="b228f-138">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="b228f-139">Hantering av incidenter</span><span class="sxs-lookup"><span data-stu-id="b228f-139">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="b228f-140">Ett åtgärdscenter för hantering av [automatisk undersökning och svar](mtp-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="b228f-140">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="b228f-141">[Avancerad jaktkapacitet](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="b228f-141">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>

<span data-ttu-id="b228f-142">![Bild av navigeringsfönstret i Microsoft 365 security center med Microsoft Threat Protection-funktioner ](../../media/mtp-on.png)
 *i Microsoft 365-säkerhetscenter med incidenthantering och andra funktioner för Microsoft Threat Protection*</span><span class="sxs-lookup"><span data-stu-id="b228f-142">![Image of Microsoft 365 security center navigation pane with Microsoft Threat Protection features](../../media/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft Threat Protection capabilities*</span></span>

### <a name="getting-azure-atp-data"></a><span data-ttu-id="b228f-143">Hämta Azure ATP-data</span><span class="sxs-lookup"><span data-stu-id="b228f-143">Getting Azure ATP data</span></span>
<span data-ttu-id="b228f-144">Om du vill dela Azure ATP-data med Microsoft Threat Protection kontrollerar du att Microsoft Cloud App Security och Azure ATP-integrering är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="b228f-144">To share Azure ATP data with Microsoft Threat Protection, ensure that Microsoft Cloud App Security and Azure ATP integration is turned on.</span></span> [<span data-ttu-id="b228f-145">Läs mer om den här integrationen</span><span class="sxs-lookup"><span data-stu-id="b228f-145">Learn more about this integration</span></span>](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a><span data-ttu-id="b228f-146">Inaktivera Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b228f-146">Turn off Microsoft Threat Protection</span></span>
<span data-ttu-id="b228f-147">Om du vill sluta använda Microsoft Threat Protection går du till **Inställningar**  >  **microsoft threat protection**  >  **opt-in / opt-out** i Microsoft 365 security center.</span><span class="sxs-lookup"><span data-stu-id="b228f-147">To stop using Microsoft Threat Protection, go to **Settings** > **Microsoft Threat Protection** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="b228f-148">Avmarkera **Aktivera Microsoft Threat Protection** och spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="b228f-148">Unselect **Turn on Microsoft Threat Protection** and save the changes.</span></span>

<span data-ttu-id="b228f-149">Motsvarande funktioner tas bort från Microsoft 365-säkerhetscentret.</span><span class="sxs-lookup"><span data-stu-id="b228f-149">Corresponding features will be removed from the Microsoft 365 security center.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="b228f-150">Få hjälp</span><span class="sxs-lookup"><span data-stu-id="b228f-150">Get assistance</span></span>

<span data-ttu-id="b228f-151">Microsofts supportpersonal kan hjälpa till att etablera eller avetablera tjänsten och relaterade resurser på din klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="b228f-151">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="b228f-152">Om du behöver hjälp väljer du **Behöver du hjälp?**</span><span class="sxs-lookup"><span data-stu-id="b228f-152">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="b228f-153">NÃ¤s ã¤nder du support nÃ¤nder du Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="b228f-153">When contacting support, mention Microsoft Threat Protection.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b228f-154">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="b228f-154">Related topics</span></span>

- [<span data-ttu-id="b228f-155">Översikt över Microsofts hotskydd</span><span class="sxs-lookup"><span data-stu-id="b228f-155">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="b228f-156">Licenskrav och andra förutsättningar</span><span class="sxs-lookup"><span data-stu-id="b228f-156">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="b228f-157">Distribuera tjänster som stöds</span><span class="sxs-lookup"><span data-stu-id="b228f-157">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="b228f-158">Översikt över Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="b228f-158">Microsoft Defender ATP overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="b228f-159">Översikt över Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="b228f-159">Office 365 ATP overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="b228f-160">Översikt över Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="b228f-160">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="b228f-161">Översikt över Azure ATP</span><span class="sxs-lookup"><span data-stu-id="b228f-161">Azure ATP overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="b228f-162">Microsoft Defender ATP-datalagring</span><span class="sxs-lookup"><span data-stu-id="b228f-162">Microsoft Defender ATP data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)