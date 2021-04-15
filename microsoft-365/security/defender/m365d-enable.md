---
title: Aktivera Microsoft 365 Defender i Säkerhetscenter för Microsoft 365
description: Lär dig hur du aktiverar Microsoft 365 Defender och börjar integrera dina säkerhetstillbud och -svar.
keywords: komma igång, aktivera MTP, Microsoft Threat Protection, M365, säkerhet, dataplats, nödvändiga behörigheter, licensberättigande, inställningssidan
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
ms.openlocfilehash: bf8fdb2a8a42ef7b70b744cbbb5663e6afe51989
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764392"
---
# <a name="turn-on-microsoft-365-defender"></a><span data-ttu-id="65abe-104">Aktivera Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="65abe-104">Turn on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="65abe-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="65abe-105">**Applies to:**</span></span>
- <span data-ttu-id="65abe-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="65abe-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="65abe-107">[Microsoft 365 Defender](microsoft-365-defender.md) ger en enhetlig svarsprocess för incidenter genom att integrera nyckelfunktioner i Microsoft Defender för slutpunkt, Microsoft Defender för Office 365, Microsoft Cloud App Security och Microsoft Defender för identitet.</span><span class="sxs-lookup"><span data-stu-id="65abe-107">[Microsoft 365 Defender](microsoft-365-defender.md) unifies your incident response process by integrating key capabilities across Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="65abe-108">I den här enhetliga upplevelsen läggs kraftfulla funktioner som du kan komma åt i Säkerhetscenter för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="65abe-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="65abe-109">Microsoft 365 Defender aktiveras automatiskt när berättigade kunder med behörighet besöker Säkerhetscenter för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="65abe-109">Microsoft 365 Defender automatically turns on when eligible customers with the required permissions visit Microsoft 365 security center.</span></span> <span data-ttu-id="65abe-110">Läs den här artikeln om du vill förstå olika krav och hur Microsoft 365 Defender är etablerat.</span><span class="sxs-lookup"><span data-stu-id="65abe-110">Read this article to understand various prerequisites and how Microsoft 365 Defender is provisioned.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="65abe-111">Kontrollera behörigheten för licensen och vilka behörigheter som krävs</span><span class="sxs-lookup"><span data-stu-id="65abe-111">Check license eligibility and required permissions</span></span>

<span data-ttu-id="65abe-112">En licens till en Microsoft 365-säkerhetsprodukt ger vanligtvis dig rätt att använda Microsoft 365 Defender i Microsoft 365 säkerhetscenter utan ytterligare licenskostnad.</span><span class="sxs-lookup"><span data-stu-id="65abe-112">A license to a Microsoft 365 security product generally entitles you to use Microsoft 365 Defender in Microsoft 365 security center without additional licensing cost.</span></span> <span data-ttu-id="65abe-113">Vi rekommenderar att du skaffar en Microsoft 365 E5-, E5-säkerhetslicens, A5- eller A5-säkerhetslicens eller en giltig kombination av licenser som ger åtkomst till alla tjänster som stöds.</span><span class="sxs-lookup"><span data-stu-id="65abe-113">We do recommend getting a Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses that provides access to all supported services.</span></span>

<span data-ttu-id="65abe-114">Mer detaljerad licensinformation finns [i licenskraven.](prerequisites.md#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="65abe-114">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="65abe-115">Kontrollera din roll</span><span class="sxs-lookup"><span data-stu-id="65abe-115">Check your role</span></span>

<span data-ttu-id="65abe-116">Du måste vara **global administratör eller** **säkerhetsadministratör i** Azure Active Directory för att kunna aktivera Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="65abe-116">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> [<span data-ttu-id="65abe-117">Visa dina roller i Azure AD</span><span class="sxs-lookup"><span data-stu-id="65abe-117">View your roles in Azure AD</span></span>](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a><span data-ttu-id="65abe-118">Tjänster som stöds</span><span class="sxs-lookup"><span data-stu-id="65abe-118">Supported services</span></span>

<span data-ttu-id="65abe-119">Microsoft 365 Defender sammanställer data från de olika tjänster som stöds och som du redan har distribuerat.</span><span class="sxs-lookup"><span data-stu-id="65abe-119">Microsoft 365 Defender aggregates data from the various supported services that you've already deployed.</span></span> <span data-ttu-id="65abe-120">Den bearbetar och lagrar data centralt för att identifiera nya insikter och göra centraliserade svarsarbetsflöden möjliga.</span><span class="sxs-lookup"><span data-stu-id="65abe-120">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span> <span data-ttu-id="65abe-121">Det gör detta utan att befintliga distributioner, inställningar eller data som är kopplade till de integrerade tjänsterna påverkas.</span><span class="sxs-lookup"><span data-stu-id="65abe-121">It does this without affecting existing deployments, settings, or data associated with the integrated services.</span></span>

<span data-ttu-id="65abe-122">För att få bästa skydd och optimera Microsoft 365 Defender rekommenderar vi att du distribuerar alla tillämpliga tjänster som stöds i nätverket.</span><span class="sxs-lookup"><span data-stu-id="65abe-122">To get the best protection and optimize Microsoft 365 Defender, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="65abe-123">Mer information finns [i distribuera tjänster som stöds.](deploy-supported-services.md)</span><span class="sxs-lookup"><span data-stu-id="65abe-123">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="onboard-to-the-service"></a><span data-ttu-id="65abe-124">Introducera till tjänsten</span><span class="sxs-lookup"><span data-stu-id="65abe-124">Onboard to the service</span></span>
<span data-ttu-id="65abe-125">Det är enkelt att komma igång med Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="65abe-125">Onboarding to Microsoft 365 Defender is simple.</span></span> <span data-ttu-id="65abe-126">I navigeringsmenyn väljer du ett objekt under avsnittet Slutpunkter, till exempel Incidenter, Ärenden, Säkerhetscenter eller Hotanalys för att påbörja onboarding-processen.</span><span class="sxs-lookup"><span data-stu-id="65abe-126">From the navigation menu, select any item under the Endpoints section, such as Incidents, Hunting, Action center, or Threat analytics to initiate the onboarding process.</span></span> 

### <a name="data-center-location"></a><span data-ttu-id="65abe-127">Datacenterplats</span><span class="sxs-lookup"><span data-stu-id="65abe-127">Data center location</span></span>

<span data-ttu-id="65abe-128">Microsoft 365 Defender lagrar och bearbetar data på samma [plats som används av Microsoft Defender för slutpunkt.](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)</span><span class="sxs-lookup"><span data-stu-id="65abe-128">Microsoft 365 Defender will store and process data in the [same location used by Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="65abe-129">Om du inte har Microsoft Defender för Endpoint väljs en ny datacenterplats automatiskt baserat på platsen för aktiva Microsoft 365-säkerhetstjänster.</span><span class="sxs-lookup"><span data-stu-id="65abe-129">If you don't have Microsoft Defender for Endpoint, a new data center location is automatically selected based on the location of active Microsoft 365 security services.</span></span> <span data-ttu-id="65abe-130">Den valda platsen för datacenter visas på skärmen.</span><span class="sxs-lookup"><span data-stu-id="65abe-130">The selected data center location is shown in the screen.</span></span>

<span data-ttu-id="65abe-131">Välj **Behöver du hjälp?** på Säkerhetscenter i Microsoft 365 om du vill kontakta Microsoft Support om etableringen av Microsoft 365 Defender på en annan datacenterplats.</span><span class="sxs-lookup"><span data-stu-id="65abe-131">Select **Need help?** in the Microsoft 365 security center to contact Microsoft support about provisioning Microsoft 365 Defender in a different data center location.</span></span>

> [!NOTE]
> <span data-ttu-id="65abe-132">Microsoft Defender för Slutpunkt tillhandahåller automatiskt datacenter i Europeiska unionen (EU) när det aktiveras via Azure Defender.</span><span class="sxs-lookup"><span data-stu-id="65abe-132">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="65abe-133">Microsoft 365 Defender etablerar automatiskt i samma datacenter i EU för kunder som har etablerat Defender för Slutpunkt på det här sättet.</span><span class="sxs-lookup"><span data-stu-id="65abe-133">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Defender for Endpoint in this manner.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="65abe-134">Bekräfta att tjänsten är på</span><span class="sxs-lookup"><span data-stu-id="65abe-134">Confirm that the service is on</span></span>

<span data-ttu-id="65abe-135">När tjänsten har etablerats läggs följande till:</span><span class="sxs-lookup"><span data-stu-id="65abe-135">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="65abe-136">Incidenthantering</span><span class="sxs-lookup"><span data-stu-id="65abe-136">Incidents management</span></span>](incidents-overview.md)
- [<span data-ttu-id="65abe-137">Varningskö</span><span class="sxs-lookup"><span data-stu-id="65abe-137">Alerts queue</span></span>](investigate-alerts.md)
- <span data-ttu-id="65abe-138">Ett åtgärdscenter för hantering [av automatiserad undersökning och svar](m365d-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="65abe-138">An action center for managing [automated investigation and response](m365d-autoir.md)</span></span>
- <span data-ttu-id="65abe-139">[Avancerade sökfunktioner](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="65abe-139">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>
- <span data-ttu-id="65abe-140">Analys av hot</span><span class="sxs-lookup"><span data-stu-id="65abe-140">Threat analytics</span></span>

<span data-ttu-id="65abe-141">![Bild av navigeringsfönstret i Microsoft 365 Säkerhetscenter med Microsoft 365 Defender-funktioner Microsoft 365 Säkerhetscenter med incidenthantering och andra ](../../media/overview-incident.png)
 *Microsoft 365 Defender-funktioner*</span><span class="sxs-lookup"><span data-stu-id="65abe-141">![Image of Microsoft 365 security center navigation pane with Microsoft 365 Defender features](../../media/overview-incident.png)
*Microsoft 365 security center with incidents management and other Microsoft 365 Defender capabilities*</span></span>

### <a name="getting-microsoft-defender-for-identity-data"></a><span data-ttu-id="65abe-142">Hämta Microsoft Defender för identitetsdata</span><span class="sxs-lookup"><span data-stu-id="65abe-142">Getting Microsoft Defender for Identity data</span></span> 
<span data-ttu-id="65abe-143">Om du vill aktivera integrering med Microsoft Cloud App Security måste du logga in på Microsoft Cloud App Security minst en gång.</span><span class="sxs-lookup"><span data-stu-id="65abe-143">To enable the integration with Microsoft Cloud App Security, you'll need to login to the Microsoft Cloud App Security at least once.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="65abe-144">Få hjälp</span><span class="sxs-lookup"><span data-stu-id="65abe-144">Get assistance</span></span>

<span data-ttu-id="65abe-145">Läs vanliga frågor om hur du använder Microsoft 365 Defender i Vanliga frågor och svar om hur du får svar på de vanligaste frågorna om hur du använder Microsoft 365 [Defender.](m365d-enable-faq.md)</span><span class="sxs-lookup"><span data-stu-id="65abe-145">To get answers to the most commonly asked questions about turning on Microsoft 365 Defender, [read the FAQ](m365d-enable-faq.md).</span></span>

<span data-ttu-id="65abe-146">Microsofts supportpersonal kan hjälpa dig med att tillhandahålla eller återkalla tjänsten och relaterade resurser i klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="65abe-146">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="65abe-147">Om du behöver hjälp väljer du Behöver du **hjälp?** i Säkerhetscenter för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="65abe-147">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="65abe-148">När du kontaktar supporten nämner du Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="65abe-148">When contacting support, mention Microsoft 365 Defender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="65abe-149">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="65abe-149">Related topics</span></span>

- [<span data-ttu-id="65abe-150">Vanliga frågor och svar</span><span class="sxs-lookup"><span data-stu-id="65abe-150">Frequently asked questions</span></span>](m365d-enable-faq.md)
- [<span data-ttu-id="65abe-151">Licenskrav och andra krav</span><span class="sxs-lookup"><span data-stu-id="65abe-151">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="65abe-152">Distribuera tjänster som stöds</span><span class="sxs-lookup"><span data-stu-id="65abe-152">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="65abe-153">Översikt över Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="65abe-153">Microsoft 365 Defender overview</span></span>](microsoft-365-defender.md)
- [<span data-ttu-id="65abe-154">Översikt över Microsoft Defender för slutpunkt</span><span class="sxs-lookup"><span data-stu-id="65abe-154">Microsoft Defender for Endpoint overview</span></span>](../defender-endpoint/microsoft-defender-endpoint.md)
- [<span data-ttu-id="65abe-155">Översikt över Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="65abe-155">Defender for Office 365 overview</span></span>](../office-365-security/defender-for-office-365.md)
- [<span data-ttu-id="65abe-156">Översikt över säkerhet i Microsoft Cloud App</span><span class="sxs-lookup"><span data-stu-id="65abe-156">Microsoft Cloud App Security overview</span></span>](/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="65abe-157">Översikt över Microsoft Defender för identitet</span><span class="sxs-lookup"><span data-stu-id="65abe-157">Microsoft Defender for Identity overview</span></span>](/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="65abe-158">Microsoft Defender för slutpunktsdatalagring</span><span class="sxs-lookup"><span data-stu-id="65abe-158">Microsoft Defender for Endpoint data storage</span></span>](../defender-endpoint/data-storage-privacy.md)
