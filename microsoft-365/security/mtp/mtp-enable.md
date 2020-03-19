---
title: Aktivera Microsoft Threat Protection i Microsoft 365-säkerhetscentret
description: Läs om hur du aktiverar Microsoft Threat Protection och börjar integrera säkerhetsincidenten och säkerhetssvaret.
keywords: komma igång, aktivera MTP, Microsoft Threat Protection, M365, säkerhet, dataplats, obligatoriska behörigheter, licensbehörighet, inställningssida
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
ms.openlocfilehash: fa970b28939ad43bf6a2717e603013277bc9130f
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/13/2020
ms.locfileid: "42806482"
---
# <a name="turn-on-microsoft-threat-protection"></a><span data-ttu-id="c22a0-104">Aktivera Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c22a0-104">Turn on Microsoft Threat Protection</span></span>

<span data-ttu-id="c22a0-105">**Gäller:**</span><span class="sxs-lookup"><span data-stu-id="c22a0-105">**Applies to:**</span></span>
- <span data-ttu-id="c22a0-106">Skydd av Hot mot Microsoft</span><span class="sxs-lookup"><span data-stu-id="c22a0-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="c22a0-107">Microsoft Threat Protection förenar din incidentsvarsprocess genom att integrera nyckelfunktioner i Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security och Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="c22a0-107">Microsoft Threat Protection unifies your incident response process by integrating key capabilities across Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="c22a0-108">Den här enhetliga upplevelsen lägger till kraftfulla funktioner som du kan komma åt i Säkerhetscentret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c22a0-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="c22a0-109">För att få bästa möjliga skydd och optimera Microsoft Threat Protection rekommenderar vi att du distribuerar alla tillämpliga tjänster som stöds i nätverket.</span><span class="sxs-lookup"><span data-stu-id="c22a0-109">To get the best protection and optimize Microsoft Threat Protection, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="c22a0-110">Mer information [finns i om hur du distribuerar tjänster som stöds](deploy-supported-services.md).</span><span class="sxs-lookup"><span data-stu-id="c22a0-110">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="c22a0-111">Kontrollera licensbehörighet och obligatoriska behörigheter</span><span class="sxs-lookup"><span data-stu-id="c22a0-111">Check license eligibility and required permissions</span></span>
<span data-ttu-id="c22a0-112">En Microsoft 365 E5-, E5-säkerhets- eller A5-licens eller en giltig kombination av licenser ger åtkomst till tjänster som stöds och ger dig rätt att använda Microsoft Threat Protection i Microsoft 365 security center.</span><span class="sxs-lookup"><span data-stu-id="c22a0-112">A Microsoft 365 E5, E5 Security, or A5 license or a valid combination of licenses provides access to supported services and entitles you to use Microsoft Threat Protection in Microsoft 365 security center.</span></span>

<span data-ttu-id="c22a0-113">För detaljerad [licensinformation, läs licenskraven](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="c22a0-113">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="c22a0-114">Kontrollera din roll</span><span class="sxs-lookup"><span data-stu-id="c22a0-114">Check your role</span></span>
<span data-ttu-id="c22a0-115">Du måste vara en **global administratör** eller **säkerhetsadministratör** i Azure Active Directory för att aktivera Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="c22a0-115">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft Threat Protection.</span></span> [<span data-ttu-id="c22a0-116">Visa dina roller i Azure AD</span><span class="sxs-lookup"><span data-stu-id="c22a0-116">View your roles in Azure AD</span></span>](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="start-using-the-service"></a><span data-ttu-id="c22a0-117">Börja använda tjänsten</span><span class="sxs-lookup"><span data-stu-id="c22a0-117">Start using the service</span></span>
<span data-ttu-id="c22a0-118">Microsoft Threat Protection sammanställer data från de olika integrerade tjänsterna.</span><span class="sxs-lookup"><span data-stu-id="c22a0-118">Microsoft Threat Protection aggregates data from the various integrated services.</span></span> <span data-ttu-id="c22a0-119">Det kommer att bearbeta och lagra data centralt för att identifiera nya insikter och göra centraliserade svararbetsflöden möjliga.</span><span class="sxs-lookup"><span data-stu-id="c22a0-119">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span>

<span data-ttu-id="c22a0-120">Innan du aktiverar tjänsten visas välkomstsidan för Microsoft 365[(security.microsoft.com](https://security.microsoft.com)) välkomstsidan för Microsoft Threat Protection när du väljer **Incidenter,** **Åtgärdscenter**eller **Jakt** från navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="c22a0-120">Before you turn on the service, the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) shows the Microsoft Threat Protection welcome page when you select **Incidents**, **Action center**, or **Hunting** from the navigation pane.</span></span> <span data-ttu-id="c22a0-121">Dessa navigeringsalternativ visas inte om du inte är berättigad att använda Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="c22a0-121">These navigation options are not shown if you are not eligible to use Microsoft Threat Protection.</span></span>

<span data-ttu-id="c22a0-122">![Bild på välkomstsidan för Microsoft Threat Protection som visas](../../media/mtp-welcome.png)
om Microsoft Threat Protection inte har aktiverats på välkomstsidan för*Microsoft Threat Protection i Microsoft 365 security center*</span><span class="sxs-lookup"><span data-stu-id="c22a0-122">![Image of the Microsoft Threat Protection welcome page shown if Microsoft Threat Protection has not been turned on](../../media/mtp-welcome.png)
*Microsoft Threat Protection welcome page in Microsoft 365 security center*</span></span>

<span data-ttu-id="c22a0-123">Om du vill aktivera Microsoft Threat Protection slutför du bara processen från välkomstsidan.</span><span class="sxs-lookup"><span data-stu-id="c22a0-123">To turn on Microsoft Threat Protection, simply complete the process from the welcome page.</span></span> <span data-ttu-id="c22a0-124">Du kan också aktivera Microsoft Threat Protection genom att komma åt **Inställningar** [(security.microsoft.com/settings)](https://security.microsoft.com/settings)i navigeringsfönstret och välja **Microsoft Threat Protection**.</span><span class="sxs-lookup"><span data-stu-id="c22a0-124">You can also turn on Microsoft Threat Protection by accessing **Settings** ([security.microsoft.com/settings](https://security.microsoft.com/settings)) in the navigation pane and selecting **Microsoft Threat Protection**.</span></span>

>[!NOTE]
><span data-ttu-id="c22a0-125">Om du inte ser **Inställningar** i navigeringsfönstret eller inte kunde komma åt sidan kontrollerar du dina behörigheter och licenser.</span><span class="sxs-lookup"><span data-stu-id="c22a0-125">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>

### <a name="select-data-center-location"></a><span data-ttu-id="c22a0-126">Välj datacenterplats</span><span class="sxs-lookup"><span data-stu-id="c22a0-126">Select data center location</span></span>
<span data-ttu-id="c22a0-127">Om Microsoft Defender ATP har etablerats för din organisation lagras och bearbetas data på samma datacenterplats som du har valt för [dina Microsoft Defender ATP-data](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span><span class="sxs-lookup"><span data-stu-id="c22a0-127">If Microsoft Defender ATP has been provisioned for your organization, data will be stored and processed in the same data center location you have selected for [your Microsoft Defender ATP data](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="c22a0-128">Om du inte har Microsoft Defender ATP blir du ombedd att välja en ny datacenterplats specifikt för Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="c22a0-128">If you don't have Microsoft Defender ATP, you will be asked to choose a new data center location specifically for Microsoft Threat Protection.</span></span> 

<span data-ttu-id="c22a0-129">Du måste ge samtycke innan data delas mellan tjänster och aggregeras.</span><span class="sxs-lookup"><span data-stu-id="c22a0-129">You need to provide consent before data is shared between services and aggregated.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="c22a0-130">Bekräfta att tjänsten är på</span><span class="sxs-lookup"><span data-stu-id="c22a0-130">Confirm that the service is on</span></span>
<span data-ttu-id="c22a0-131">När tjänsten har etablerats, lägger den till:</span><span class="sxs-lookup"><span data-stu-id="c22a0-131">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="c22a0-132">Hantering av incidenter</span><span class="sxs-lookup"><span data-stu-id="c22a0-132">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="c22a0-133">Ett åtgärdscenter för hantering av [automatiserad utredning och svar](mtp-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="c22a0-133">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="c22a0-134">[Avancerad jaktkapacitet](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="c22a0-134">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>

<span data-ttu-id="c22a0-135">![Bild av navigeringsfönstret i Microsoft 365](../../media/mtp-on.png)
security center med Microsoft Threat Protection har*Microsoft 365 security center med incidenthantering och andra Funktioner för Microsoft Threat Protection*</span><span class="sxs-lookup"><span data-stu-id="c22a0-135">![Image of Microsoft 365 security center navigation pane with Microsoft Threat Protection features](../../media/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft Threat Protection capabilities*</span></span>

### <a name="getting-azure-atp-data"></a><span data-ttu-id="c22a0-136">Hämta Azure ATP-data</span><span class="sxs-lookup"><span data-stu-id="c22a0-136">Getting Azure ATP data</span></span>
<span data-ttu-id="c22a0-137">Om du vill dela Azure ATP-data med Microsoft Threat Protection kontrollerar du att Microsoft Cloud App Security och Azure ATP-integrering är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="c22a0-137">To share Azure ATP data with Microsoft Threat Protection, ensure that Microsoft Cloud App Security and Azure ATP integration is turned on.</span></span> [<span data-ttu-id="c22a0-138">Läs mer om den här integrationen</span><span class="sxs-lookup"><span data-stu-id="c22a0-138">Learn more about this integration</span></span>](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a><span data-ttu-id="c22a0-139">Inaktivera Microsoft threat protection</span><span class="sxs-lookup"><span data-stu-id="c22a0-139">Turn off Microsoft Threat Protection</span></span>
<span data-ttu-id="c22a0-140">Om du vill sluta använda Microsoft Threat Protection går du till **Inställningar** > **Microsoft Threat Protection** > **Opt-in / Opt-out** i Microsoft 365 security center.</span><span class="sxs-lookup"><span data-stu-id="c22a0-140">To stop using Microsoft Threat Protection, go to **Settings** > **Microsoft Threat Protection** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="c22a0-141">Avmarkera **Aktivera Microsoft Threat Protection** och spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="c22a0-141">Unselect **Turn on Microsoft Threat Protection** and save the changes.</span></span>

<span data-ttu-id="c22a0-142">Motsvarande funktioner tas bort från Microsoft 365 security center.</span><span class="sxs-lookup"><span data-stu-id="c22a0-142">Corresponding features will be removed from the Microsoft 365 security center.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="c22a0-143">Få hjälp</span><span class="sxs-lookup"><span data-stu-id="c22a0-143">Get assistance</span></span>

<span data-ttu-id="c22a0-144">Microsofts supportpersonal kan hjälpa till att etablera eller avetablera tjänsten och relaterade resurser på din klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="c22a0-144">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="c22a0-145">Om du vill ha hjälp väljer du **Behöver du hjälp?**</span><span class="sxs-lookup"><span data-stu-id="c22a0-145">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="c22a0-146">När du kontaktar supporten bör du nämna Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="c22a0-146">When contacting support, mention Microsoft Threat Protection.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c22a0-147">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="c22a0-147">Related topics</span></span>

- [<span data-ttu-id="c22a0-148">Översikt över Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c22a0-148">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="c22a0-149">Licenskrav och andra förutsättningar</span><span class="sxs-lookup"><span data-stu-id="c22a0-149">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="c22a0-150">Distribuera tjänster som stöds</span><span class="sxs-lookup"><span data-stu-id="c22a0-150">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="c22a0-151">Översikt över Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="c22a0-151">Microsoft Defender ATP overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="c22a0-152">Översikt över Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="c22a0-152">Office 365 ATP overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="c22a0-153">Översikt över Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="c22a0-153">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="c22a0-154">Azure ATP-översikt</span><span class="sxs-lookup"><span data-stu-id="c22a0-154">Azure ATP overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="c22a0-155">Microsoft Defender ATP-datalagring</span><span class="sxs-lookup"><span data-stu-id="c22a0-155">Microsoft Defender ATP data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
