---
title: Aktivera Microsoft 365 Defender i Microsoft 365 säkerhetscenter
description: Lär dig hur du aktiverar Microsoft 365 Defender och börjar integrera dina säkerhetstillbud och -åtgärder.
keywords: komma igång, aktivera Microsoft 365 Defender, Microsoft 365 Defender, M365, säkerhet, dataplats, obligatoriska behörigheter, behörighet för licens, inställningssidan
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 102666834562d0576920c746842582c2870b3738
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007615"
---
# <a name="turn-on-microsoft-365-defender"></a><span data-ttu-id="ab465-104">Aktivera Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ab465-104">Turn on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="ab465-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="ab465-105">**Applies to:**</span></span>
- <span data-ttu-id="ab465-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ab465-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="ab465-107">[Microsoft 365 Defender](microsoft-365-defender.md) en enhetlig incidentsvarsprocess genom att integrera nyckelfunktioner i Microsoft Defender för Slutpunkt, Microsoft Defender för Office 365, Microsoft Cloud App Security och Microsoft Defender för identitet.</span><span class="sxs-lookup"><span data-stu-id="ab465-107">[Microsoft 365 Defender](microsoft-365-defender.md) unifies your incident response process by integrating key capabilities across Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="ab465-108">Den här enhetliga upplevelsen lägger till kraftfulla funktioner som du kan komma åt Microsoft 365 säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="ab465-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="ab465-109">Microsoft 365 Defender aktiveras automatiskt när berättigade kunder med behörighet besöker säkerhetscentret Microsoft 365 behörighet.</span><span class="sxs-lookup"><span data-stu-id="ab465-109">Microsoft 365 Defender automatically turns on when eligible customers with the required permissions visit Microsoft 365 security center.</span></span> <span data-ttu-id="ab465-110">Läs den här artikeln för att förstå olika krav och hur Microsoft 365 Defender är etablerat.</span><span class="sxs-lookup"><span data-stu-id="ab465-110">Read this article to understand various prerequisites and how Microsoft 365 Defender is provisioned.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="ab465-111">Kontrollera behörigheten för licensen och vilka behörigheter som krävs</span><span class="sxs-lookup"><span data-stu-id="ab465-111">Check license eligibility and required permissions</span></span>

<span data-ttu-id="ab465-112">En licens till en Microsoft 365-säkerhetsprodukt ger vanligtvis dig rätt att använda Microsoft 365 Defender i Microsoft 365 säkerhetscenter utan ytterligare licenskostnad.</span><span class="sxs-lookup"><span data-stu-id="ab465-112">A license to a Microsoft 365 security product generally entitles you to use Microsoft 365 Defender in Microsoft 365 security center without additional licensing cost.</span></span> <span data-ttu-id="ab465-113">Vi rekommenderar att du skaffar en Microsoft 365 E5, E5-säkerhet, A5- eller A5-säkerhetslicens eller en giltig kombination av licenser som ger åtkomst till alla tjänster som stöds.</span><span class="sxs-lookup"><span data-stu-id="ab465-113">We do recommend getting a Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses that provides access to all supported services.</span></span>

<span data-ttu-id="ab465-114">Mer detaljerad licensinformation finns [i licenskraven.](prerequisites.md#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="ab465-114">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="ab465-115">Kontrollera din roll</span><span class="sxs-lookup"><span data-stu-id="ab465-115">Check your role</span></span>

<span data-ttu-id="ab465-116">Du måste vara **global administratör eller** **säkerhetsadministratör i Azure Active Directory** kunna aktivera Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="ab465-116">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> [<span data-ttu-id="ab465-117">Visa dina roller i Azure AD</span><span class="sxs-lookup"><span data-stu-id="ab465-117">View your roles in Azure AD</span></span>](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a><span data-ttu-id="ab465-118">Tjänster som stöds</span><span class="sxs-lookup"><span data-stu-id="ab465-118">Supported services</span></span>

<span data-ttu-id="ab465-119">Microsoft 365 Defender sammanställer data från de olika tjänster som stöds som du redan har distribuerat.</span><span class="sxs-lookup"><span data-stu-id="ab465-119">Microsoft 365 Defender aggregates data from the various supported services that you've already deployed.</span></span> <span data-ttu-id="ab465-120">Den bearbetar och lagrar data centralt för att identifiera nya insikter och göra centraliserade svarsarbetsflöden möjliga.</span><span class="sxs-lookup"><span data-stu-id="ab465-120">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span> <span data-ttu-id="ab465-121">Det gör detta utan att befintliga distributioner, inställningar eller data som är kopplade till de integrerade tjänsterna påverkas.</span><span class="sxs-lookup"><span data-stu-id="ab465-121">It does this without affecting existing deployments, settings, or data associated with the integrated services.</span></span>

<span data-ttu-id="ab465-122">För att få bästa skydd och Microsoft 365 Defender rekommenderar vi att du distribuerar alla tillämpliga tjänster som stöds i nätverket.</span><span class="sxs-lookup"><span data-stu-id="ab465-122">To get the best protection and optimize Microsoft 365 Defender, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="ab465-123">Mer information finns [i distribuera tjänster som stöds.](deploy-supported-services.md)</span><span class="sxs-lookup"><span data-stu-id="ab465-123">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="onboard-to-the-service"></a><span data-ttu-id="ab465-124">Introducera till tjänsten</span><span class="sxs-lookup"><span data-stu-id="ab465-124">Onboard to the service</span></span>
<span data-ttu-id="ab465-125">Registrering för Microsoft 365 Defender är enkelt.</span><span class="sxs-lookup"><span data-stu-id="ab465-125">Onboarding to Microsoft 365 Defender is simple.</span></span> <span data-ttu-id="ab465-126">I navigeringsmenyn väljer du ett objekt, till exempel **incidenter & postmeddelanden,** Omrering, Åtgärdscenter eller Hotanalys för att påbörja onboarding-processen.   </span><span class="sxs-lookup"><span data-stu-id="ab465-126">From the navigation menu, select any item, such as **Incidents & alerts**, **Hunting**, **Action center**, or **Threat analytics** to initiate the onboarding process.</span></span> 

### <a name="data-center-location"></a><span data-ttu-id="ab465-127">Datacenterplats</span><span class="sxs-lookup"><span data-stu-id="ab465-127">Data center location</span></span>

<span data-ttu-id="ab465-128">Microsoft 365 Defender lagra och bearbeta data på samma [plats som används av Microsoft Defender för Slutpunkt](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span><span class="sxs-lookup"><span data-stu-id="ab465-128">Microsoft 365 Defender will store and process data in the [same location used by Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="ab465-129">Om du inte har Microsoft Defender för Endpoint väljs en ny datacenterplats automatiskt baserat på platsen för aktiva Microsoft 365 säkerhetstjänster.</span><span class="sxs-lookup"><span data-stu-id="ab465-129">If you don't have Microsoft Defender for Endpoint, a new data center location is automatically selected based on the location of active Microsoft 365 security services.</span></span> <span data-ttu-id="ab465-130">Den valda platsen för datacenter visas på skärmen.</span><span class="sxs-lookup"><span data-stu-id="ab465-130">The selected data center location is shown in the screen.</span></span>

<span data-ttu-id="ab465-131">Välj **Behöver du hjälp?** på Microsoft 365 om du vill kontakta Microsofts support om etablering Microsoft 365 Defender ett annat datacenter.</span><span class="sxs-lookup"><span data-stu-id="ab465-131">Select **Need help?** in the Microsoft 365 security center to contact Microsoft support about provisioning Microsoft 365 Defender in a different data center location.</span></span>

> [!NOTE]
> <span data-ttu-id="ab465-132">Tidigare etableras Microsoft Defender för Slutpunkt automatiskt i Europeiska unionen (EU) datacenter när det aktiverats via Azure Defender.</span><span class="sxs-lookup"><span data-stu-id="ab465-132">In the past, Microsoft Defender for Endpoint automatically provisioned in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="ab465-133">Microsoft 365 Defender tillhandahålla automatiskt i samma datacenter i EU för kunder som har etablerat Defender för Slutpunkt på det här sättet tidigare.</span><span class="sxs-lookup"><span data-stu-id="ab465-133">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Defender for Endpoint in this manner in the past.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="ab465-134">Bekräfta att tjänsten är på</span><span class="sxs-lookup"><span data-stu-id="ab465-134">Confirm that the service is on</span></span>

<span data-ttu-id="ab465-135">När tjänsten har etablerats läggs följande till:</span><span class="sxs-lookup"><span data-stu-id="ab465-135">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="ab465-136">Incidenthantering</span><span class="sxs-lookup"><span data-stu-id="ab465-136">Incidents management</span></span>](incidents-overview.md)
- [<span data-ttu-id="ab465-137">Varningskö</span><span class="sxs-lookup"><span data-stu-id="ab465-137">Alerts queue</span></span>](investigate-alerts.md)
- <span data-ttu-id="ab465-138">Ett åtgärdscenter för hantering [av automatiserad undersökning och svar](m365d-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="ab465-138">An action center for managing [automated investigation and response](m365d-autoir.md)</span></span>
- <span data-ttu-id="ab465-139">[Avancerade sökfunktioner](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="ab465-139">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>
- <span data-ttu-id="ab465-140">Analys av hot</span><span class="sxs-lookup"><span data-stu-id="ab465-140">Threat analytics</span></span>

<span data-ttu-id="ab465-141">![Bild av Microsoft 365 säkerhetscenter-navigeringsfönstret med Microsoft 365 Defender funktioner Microsoft 365 säkerhetscenter med ](../../media/overview-incident.png)
 *incidenthantering och andra Microsoft 365 Defender funktioner*</span><span class="sxs-lookup"><span data-stu-id="ab465-141">![Image of Microsoft 365 security center navigation pane with Microsoft 365 Defender features](../../media/overview-incident.png)
*Microsoft 365 security center with incidents management and other Microsoft 365 Defender capabilities*</span></span>

### <a name="getting-microsoft-defender-for-identity-data"></a><span data-ttu-id="ab465-142">Hämta Microsoft Defender för identitetsdata</span><span class="sxs-lookup"><span data-stu-id="ab465-142">Getting Microsoft Defender for Identity data</span></span> 
<span data-ttu-id="ab465-143">Om du vill aktivera Microsoft Cloud App Security måste du logga in på Microsoft Cloud App Security minst en gång.</span><span class="sxs-lookup"><span data-stu-id="ab465-143">To enable the integration with Microsoft Cloud App Security, you'll need to login to the Microsoft Cloud App Security at least once.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="ab465-144">Få hjälp</span><span class="sxs-lookup"><span data-stu-id="ab465-144">Get assistance</span></span>

<span data-ttu-id="ab465-145">Läs vanliga frågor och svar om hur du Microsoft 365 Defender svar [på vanliga frågor och svar.](m365d-enable-faq.md)</span><span class="sxs-lookup"><span data-stu-id="ab465-145">To get answers to the most commonly asked questions about turning on Microsoft 365 Defender, [read the FAQ](m365d-enable-faq.md).</span></span>

<span data-ttu-id="ab465-146">Microsofts supportpersonal kan hjälpa dig med att tillhandahålla eller återkalla tjänsten och relaterade resurser i klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="ab465-146">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="ab465-147">Om du behöver hjälp väljer du Behöver du **hjälp?** Microsoft 365 säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="ab465-147">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="ab465-148">När du kontaktar supporten kan du Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="ab465-148">When contacting support, mention Microsoft 365 Defender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ab465-149">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="ab465-149">Related topics</span></span>

- [<span data-ttu-id="ab465-150">Vanliga frågor och svar</span><span class="sxs-lookup"><span data-stu-id="ab465-150">Frequently asked questions</span></span>](m365d-enable-faq.md)
- [<span data-ttu-id="ab465-151">Licenskrav och andra krav</span><span class="sxs-lookup"><span data-stu-id="ab465-151">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="ab465-152">Distribuera tjänster som stöds</span><span class="sxs-lookup"><span data-stu-id="ab465-152">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="ab465-153">Microsoft 365 Defender översikt</span><span class="sxs-lookup"><span data-stu-id="ab465-153">Microsoft 365 Defender overview</span></span>](microsoft-365-defender.md)
- [<span data-ttu-id="ab465-154">Översikt över Microsoft Defender för slutpunkt</span><span class="sxs-lookup"><span data-stu-id="ab465-154">Microsoft Defender for Endpoint overview</span></span>](../defender-endpoint/microsoft-defender-endpoint.md)
- [<span data-ttu-id="ab465-155">Översikt över Office 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ab465-155">Defender for Office 365 overview</span></span>](../office-365-security/defender-for-office-365.md)
- [<span data-ttu-id="ab465-156">Microsoft Cloud App Security översikt</span><span class="sxs-lookup"><span data-stu-id="ab465-156">Microsoft Cloud App Security overview</span></span>](/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="ab465-157">Översikt över Microsoft Defender för identitet</span><span class="sxs-lookup"><span data-stu-id="ab465-157">Microsoft Defender for Identity overview</span></span>](/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="ab465-158">Microsoft Defender för slutpunktsdatalagring</span><span class="sxs-lookup"><span data-stu-id="ab465-158">Microsoft Defender for Endpoint data storage</span></span>](../defender-endpoint/data-storage-privacy.md)
