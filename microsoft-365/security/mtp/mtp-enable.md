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
ms.openlocfilehash: f1c616a3d752324b8db5fdd5069904989a25eade
ms.sourcegitcommit: b57d597edbff5ab6cff8c2b04d27c15b0024776f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/01/2020
ms.locfileid: "43997520"
---
# <a name="turn-on-microsoft-threat-protection"></a><span data-ttu-id="17800-104">Aktivera Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="17800-104">Turn on Microsoft Threat Protection</span></span>

<span data-ttu-id="17800-105">**Gäller:**</span><span class="sxs-lookup"><span data-stu-id="17800-105">**Applies to:**</span></span>
- <span data-ttu-id="17800-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="17800-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="17800-107">Microsoft Threat Protection förenar din incidentsvarsprocess genom att integrera nyckelfunktioner i Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security och Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="17800-107">Microsoft Threat Protection unifies your incident response process by integrating key capabilities across Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="17800-108">Den här enhetliga upplevelsen ger dig kraftfulla funktioner som du kan komma åt i Microsoft 365-säkerhetscentret.</span><span class="sxs-lookup"><span data-stu-id="17800-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="17800-109">För att få bästa möjliga skydd och optimera Microsofts hotskydd rekommenderar vi att du distribuerar alla tillämpliga tjänster som stöds i nätverket.</span><span class="sxs-lookup"><span data-stu-id="17800-109">To get the best protection and optimize Microsoft Threat Protection, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="17800-110">Mer information [finns i om hur du distribuerar tjänster som stöds](deploy-supported-services.md).</span><span class="sxs-lookup"><span data-stu-id="17800-110">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="17800-111">Kontrollera behörighet för licenser och nödvändiga behörigheter</span><span class="sxs-lookup"><span data-stu-id="17800-111">Check license eligibility and required permissions</span></span>
<span data-ttu-id="17800-112">En Microsoft 365 E5-, E5 Security-, A5- eller A5-säkerhetslicens eller en giltig kombination av licenser ger åtkomst till tjänster som stöds och ger dig rätt att använda Microsoft Threat Protection i Microsoft 365-säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="17800-112">A Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses provides access to supported services and entitles you to use Microsoft Threat Protection in Microsoft 365 security center.</span></span>

<span data-ttu-id="17800-113">Detaljerad licensinformation [finns i licenskraven](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="17800-113">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="17800-114">Kontrollera din roll</span><span class="sxs-lookup"><span data-stu-id="17800-114">Check your role</span></span>
<span data-ttu-id="17800-115">Du måste vara **global administratör** eller **säkerhetsadministratör** i Azure Active Directory för att kunna aktivera Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="17800-115">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft Threat Protection.</span></span> [<span data-ttu-id="17800-116">Visa dina roller i Azure AD</span><span class="sxs-lookup"><span data-stu-id="17800-116">View your roles in Azure AD</span></span>](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="start-using-the-service"></a><span data-ttu-id="17800-117">Börja använda tjänsten</span><span class="sxs-lookup"><span data-stu-id="17800-117">Start using the service</span></span>
<span data-ttu-id="17800-118">Microsoft Threat Protection sammanställer data från de olika integrerade tjänsterna.</span><span class="sxs-lookup"><span data-stu-id="17800-118">Microsoft Threat Protection aggregates data from the various integrated services.</span></span> <span data-ttu-id="17800-119">Det kommer att bearbeta och lagra data centralt för att identifiera nya insikter och göra centraliserade svarsarbetsflöden möjliga.</span><span class="sxs-lookup"><span data-stu-id="17800-119">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span>

<span data-ttu-id="17800-120">Innan du aktiverar tjänsten visar Microsoft 365-säkerhetscentret ([security.microsoft.com](https://security.microsoft.com)) välkomstsidan för Microsoft Threat Protection när du väljer **Incidenter,** **Åtgärdscenter**eller **Jakt** i navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="17800-120">Before you turn on the service, the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) shows the Microsoft Threat Protection welcome page when you select **Incidents**, **Action center**, or **Hunting** from the navigation pane.</span></span> <span data-ttu-id="17800-121">Dessa navigeringsalternativ visas inte om du inte kan använda Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="17800-121">These navigation options are not shown if you are not eligible to use Microsoft Threat Protection.</span></span>

<span data-ttu-id="17800-122">![Bild av välkomstsidan för Microsoft Threat Protection som visas](../../media/mtp-welcome.png)
om Microsoft Threat Protection inte har aktiverats på*välkomstsidan för Microsoft Threat Protection i Microsoft 365-säkerhetscenter*</span><span class="sxs-lookup"><span data-stu-id="17800-122">![Image of the Microsoft Threat Protection welcome page shown if Microsoft Threat Protection has not been turned on](../../media/mtp-welcome.png)
*Microsoft Threat Protection welcome page in Microsoft 365 security center*</span></span>

<span data-ttu-id="17800-123">Om du vill aktivera Microsoft Threat Protection slutför du helt enkelt processen från välkomstsidan.</span><span class="sxs-lookup"><span data-stu-id="17800-123">To turn on Microsoft Threat Protection, simply complete the process from the welcome page.</span></span> <span data-ttu-id="17800-124">Du kan också aktivera Microsoft Threat Protection genom att komma åt **Inställningar** ([security.microsoft.com/settings](https://security.microsoft.com/settings)) i navigeringsfönstret och välja **Microsoft Threat Protection**.</span><span class="sxs-lookup"><span data-stu-id="17800-124">You can also turn on Microsoft Threat Protection by accessing **Settings** ([security.microsoft.com/settings](https://security.microsoft.com/settings)) in the navigation pane and selecting **Microsoft Threat Protection**.</span></span> <span data-ttu-id="17800-125">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="17800-125">Click **Save**.</span></span>

>[!NOTE]
><span data-ttu-id="17800-126">Om du inte ser **Inställningar** i navigeringsfönstret eller inte kunde komma åt sidan kontrollerar du dina behörigheter och licenser.</span><span class="sxs-lookup"><span data-stu-id="17800-126">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>

### <a name="select-data-center-location"></a><span data-ttu-id="17800-127">Välj datacenterplats</span><span class="sxs-lookup"><span data-stu-id="17800-127">Select data center location</span></span>
<span data-ttu-id="17800-128">Om Microsoft Defender ATP har etablerats för din organisation lagras och bearbetas data på samma datacenterplats som du har valt för [microsoft Defender ATP-data](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span><span class="sxs-lookup"><span data-stu-id="17800-128">If Microsoft Defender ATP has been provisioned for your organization, data will be stored and processed in the same data center location you have selected for [your Microsoft Defender ATP data](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="17800-129">Om du inte har Microsoft Defender ATP blir du ombedd att välja en ny datacenterplats specifikt för Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="17800-129">If you don't have Microsoft Defender ATP, you will be asked to choose a new data center location specifically for Microsoft Threat Protection.</span></span> 

<span data-ttu-id="17800-130">Du måste ge ditt samtycke innan data delas mellan tjänster och aggregeras.</span><span class="sxs-lookup"><span data-stu-id="17800-130">You need to provide consent before data is shared between services and aggregated.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="17800-131">Bekräfta att tjänsten är aktiverad</span><span class="sxs-lookup"><span data-stu-id="17800-131">Confirm that the service is on</span></span>
<span data-ttu-id="17800-132">När tjänsten har etablerats läggs följande till:</span><span class="sxs-lookup"><span data-stu-id="17800-132">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="17800-133">Hantering av incidenter</span><span class="sxs-lookup"><span data-stu-id="17800-133">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="17800-134">Ett åtgärdscenter för hantering av [automatisk undersökning och svar](mtp-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="17800-134">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="17800-135">[Avancerad jaktkapacitet](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="17800-135">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>

<span data-ttu-id="17800-136">![Bild av navigeringsfönstret i Microsoft 365](../../media/mtp-on.png)
security center med Microsoft Threat Protection-funktioner*i Microsoft 365-säkerhetscenter med incidenthantering och andra funktioner för Microsoft Threat Protection*</span><span class="sxs-lookup"><span data-stu-id="17800-136">![Image of Microsoft 365 security center navigation pane with Microsoft Threat Protection features](../../media/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft Threat Protection capabilities*</span></span>

### <a name="getting-azure-atp-data"></a><span data-ttu-id="17800-137">Hämta Azure ATP-data</span><span class="sxs-lookup"><span data-stu-id="17800-137">Getting Azure ATP data</span></span>
<span data-ttu-id="17800-138">Om du vill dela Azure ATP-data med Microsoft Threat Protection kontrollerar du att Microsoft Cloud App Security och Azure ATP-integrering är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="17800-138">To share Azure ATP data with Microsoft Threat Protection, ensure that Microsoft Cloud App Security and Azure ATP integration is turned on.</span></span> [<span data-ttu-id="17800-139">Läs mer om den här integrationen</span><span class="sxs-lookup"><span data-stu-id="17800-139">Learn more about this integration</span></span>](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a><span data-ttu-id="17800-140">Inaktivera Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="17800-140">Turn off Microsoft Threat Protection</span></span>
<span data-ttu-id="17800-141">Om du vill sluta använda Microsoft Threat Protection går du till **Inställningar** > **microsoft threat protection** > **opt-in / opt-out** i Microsoft 365 security center.</span><span class="sxs-lookup"><span data-stu-id="17800-141">To stop using Microsoft Threat Protection, go to **Settings** > **Microsoft Threat Protection** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="17800-142">Avmarkera **Aktivera Microsoft Threat Protection** och spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="17800-142">Unselect **Turn on Microsoft Threat Protection** and save the changes.</span></span>

<span data-ttu-id="17800-143">Motsvarande funktioner tas bort från Microsoft 365-säkerhetscentret.</span><span class="sxs-lookup"><span data-stu-id="17800-143">Corresponding features will be removed from the Microsoft 365 security center.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="17800-144">Få hjälp</span><span class="sxs-lookup"><span data-stu-id="17800-144">Get assistance</span></span>

<span data-ttu-id="17800-145">Microsofts supportpersonal kan hjälpa till att etablera eller avetablera tjänsten och relaterade resurser på din klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="17800-145">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="17800-146">Om du behöver hjälp väljer du **Behöver du hjälp?**</span><span class="sxs-lookup"><span data-stu-id="17800-146">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="17800-147">NÃ¤s ã¤nder du support nÃ¤nder du Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="17800-147">When contacting support, mention Microsoft Threat Protection.</span></span>

## <a name="related-topics"></a><span data-ttu-id="17800-148">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="17800-148">Related topics</span></span>

- [<span data-ttu-id="17800-149">Översikt över Microsofts hotskydd</span><span class="sxs-lookup"><span data-stu-id="17800-149">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="17800-150">Licenskrav och andra förutsättningar</span><span class="sxs-lookup"><span data-stu-id="17800-150">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="17800-151">Distribuera tjänster som stöds</span><span class="sxs-lookup"><span data-stu-id="17800-151">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="17800-152">Översikt över Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="17800-152">Microsoft Defender ATP overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="17800-153">Översikt över Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="17800-153">Office 365 ATP overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="17800-154">Översikt över Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="17800-154">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="17800-155">Översikt över Azure ATP</span><span class="sxs-lookup"><span data-stu-id="17800-155">Azure ATP overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="17800-156">Microsoft Defender ATP-datalagring</span><span class="sxs-lookup"><span data-stu-id="17800-156">Microsoft Defender ATP data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
