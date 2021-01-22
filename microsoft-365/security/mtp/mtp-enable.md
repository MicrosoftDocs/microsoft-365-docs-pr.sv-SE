---
title: Aktivera Microsoft 365 Defender i Säkerhetscenter för Microsoft 365
description: Lär dig hur du aktiverar Microsoft 365 Defender och börjar integrera säkerhetshändelsen och svaret.
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 19f035a271626077911b05082a4aba6d67355cdb
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930228"
---
# <a name="turn-on-microsoft-365-defender"></a><span data-ttu-id="9bcdf-104">Aktivera Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9bcdf-104">Turn on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9bcdf-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="9bcdf-105">**Applies to:**</span></span>
- <span data-ttu-id="9bcdf-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9bcdf-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="9bcdf-107">[Microsoft 365 Defender](microsoft-threat-protection.md) ger en enhetlig svarsprocess för incidenter genom att integrera nyckelfunktioner i Microsoft Defender för Endpoint, Microsoft Defender för Office 365, Microsoft Cloud App Security och Microsoft Defender för identitet.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-107">[Microsoft 365 Defender](microsoft-threat-protection.md) unifies your incident response process by integrating key capabilities across Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="9bcdf-108">Den här enhetliga upplevelsen ger kraftfulla funktioner som du kan komma åt i Säkerhetscenter för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="9bcdf-109">Microsoft 365 Defender aktiveras automatiskt när berättigade kunder med rätt behörighet besöker Microsoft 365 säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-109">Microsoft 365 Defender automatically turns on when eligible customers with the required permissions visit Microsoft 365 security center.</span></span> <span data-ttu-id="9bcdf-110">Läs den här artikeln för att förstå olika krav och hur Microsoft 365 Defender etableras.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-110">Read this article to understand various prerequisites and how Microsoft 365 Defender is provisioned.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="9bcdf-111">Kontrollera behörigheten för licensen och de behörigheter som krävs</span><span class="sxs-lookup"><span data-stu-id="9bcdf-111">Check license eligibility and required permissions</span></span>

<span data-ttu-id="9bcdf-112">En licens till en Microsoft 365-säkerhetsprodukt ger vanligtvis dig rätt att använda Microsoft 365 Defender i Microsoft 365 säkerhetscenter utan ytterligare licenskostnad.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-112">A license to a Microsoft 365 security product generally entitles you to use Microsoft 365 Defender in Microsoft 365 security center without additional licensing cost.</span></span> <span data-ttu-id="9bcdf-113">Vi rekommenderar att du skaffar en Microsoft 365 E5-, E5-säkerhets-, A5- eller A5-säkerhetslicens eller en giltig kombination av licenser som ger tillgång till alla tjänster som stöds.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-113">We do recommend getting a Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses that provides access to all supported services.</span></span>

<span data-ttu-id="9bcdf-114">Om du vill ha detaljerad [licensinformation läser du licenskraven.](prerequisites.md#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="9bcdf-114">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="9bcdf-115">Kontrollera din roll</span><span class="sxs-lookup"><span data-stu-id="9bcdf-115">Check your role</span></span>

<span data-ttu-id="9bcdf-116">Du måste vara **global administratör eller** **säkerhetsadministratör i** Azure Active Directory för att kunna aktivera Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-116">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> [<span data-ttu-id="9bcdf-117">Visa dina roller i Azure AD</span><span class="sxs-lookup"><span data-stu-id="9bcdf-117">View your roles in Azure AD</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a><span data-ttu-id="9bcdf-118">Tjänster som stöds</span><span class="sxs-lookup"><span data-stu-id="9bcdf-118">Supported services</span></span>

<span data-ttu-id="9bcdf-119">Microsoft 365 Defender sammanställer data från de olika tjänster som stöds och som du redan har distribuerat.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-119">Microsoft 365 Defender aggregates data from the various supported services that you've already deployed.</span></span> <span data-ttu-id="9bcdf-120">Den kommer att bearbeta och lagra data centralt för att identifiera nya insikter och göra centraliserade svarsarbetsflöden möjliga.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-120">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span> <span data-ttu-id="9bcdf-121">Det gör detta utan att påverka befintliga distributioner, inställningar eller data som är kopplade till de integrerade tjänsterna.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-121">It does this without affecting existing deployments, settings, or data associated with the integrated services.</span></span>

<span data-ttu-id="9bcdf-122">För att få bästa skydd och optimera Microsoft 365 Defender rekommenderar vi att du distribuerar alla tillämpliga tjänster som stöds i nätverket.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-122">To get the best protection and optimize Microsoft 365 Defender, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="9bcdf-123">Mer information finns i [om hur du distribuerar tjänster som stöds.](deploy-supported-services.md)</span><span class="sxs-lookup"><span data-stu-id="9bcdf-123">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="before-starting-the-service"></a><span data-ttu-id="9bcdf-124">Innan tjänsten startas</span><span class="sxs-lookup"><span data-stu-id="9bcdf-124">Before starting the service</span></span>

<span data-ttu-id="9bcdf-125">Innan du aktiverar tjänsten visas inställningssidan i Microsoft 365 Säkerhetscenter[(security.microsoft.com)](https://security.microsoft.com)i Microsoft 365 Defender  när du väljer Incidenter, Åtgärdscenter eller Jagning i navigeringsfönstret. </span><span class="sxs-lookup"><span data-stu-id="9bcdf-125">Before you turn on the service, the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) shows the Microsoft 365 Defender settings page when you select **Incidents**, **Action center**, or **Hunting** from the navigation pane.</span></span> <span data-ttu-id="9bcdf-126">De här navigeringsobjekten visas inte om du inte är berättigad att använda Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-126">These navigation items are not shown if you are not eligible to use Microsoft 365 Defender.</span></span>

<span data-ttu-id="9bcdf-127">![Bild på inställningssidan för Microsoft 365 Defender som visas om Microsoft 365 Defender inte har aktiverats i inställningarna för ](../../media/mtp-enable/mtp-settings.png)
 *Microsoft 365 Defender i Säkerhetscenter för Microsoft 365*</span><span class="sxs-lookup"><span data-stu-id="9bcdf-127">![Image of the Microsoft 365 Defender settings page shown if Microsoft 365 Defender has not been turned on](../../media/mtp-enable/mtp-settings.png)
*Microsoft 365 Defender settings in Microsoft 365 security center*</span></span>

## <a name="starting-the-service"></a><span data-ttu-id="9bcdf-128">Starta tjänsten</span><span class="sxs-lookup"><span data-stu-id="9bcdf-128">Starting the service</span></span>

<span data-ttu-id="9bcdf-129">Om du vill aktivera Microsoft 365 Defender väljer du **Aktivera Microsoft 365 Defender** och tillämpa ändringen.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-129">To turn on Microsoft 365 Defender, simply select **Turn on Microsoft 365 Defender** and apply the change.</span></span> <span data-ttu-id="9bcdf-130">Du kan också öppna  det här alternativet genom att välja Inställningar [(security.microsoft.com/settings)](https://security.microsoft.com/settings)i navigeringsfönstret och sedan **välja Microsoft 365 Defender.**</span><span class="sxs-lookup"><span data-stu-id="9bcdf-130">You can also access this option by selecting **Settings** ([security.microsoft.com/settings](https://security.microsoft.com/settings)) in the navigation pane and then selecting **Microsoft 365 Defender**.</span></span>

> [!NOTE]
> <span data-ttu-id="9bcdf-131">Om du inte ser Inställningar **i** navigeringsfönstret eller inte kunde komma åt sidan kontrollerar du dina behörigheter och licenser.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-131">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>

### <a name="data-center-location"></a><span data-ttu-id="9bcdf-132">Datacenterplats</span><span class="sxs-lookup"><span data-stu-id="9bcdf-132">Data center location</span></span>

<span data-ttu-id="9bcdf-133">Microsoft 365 Defender lagrar och bearbetar data på samma plats som [används av Microsoft Defender för Endpoint.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)</span><span class="sxs-lookup"><span data-stu-id="9bcdf-133">Microsoft 365 Defender will store and process data in the [same location used by Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="9bcdf-134">Om du inte har Microsoft Defender för Slutpunkt väljs en ny datacenterplats automatiskt utifrån var aktiva Microsoft 365-säkerhetstjänster finns.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-134">If you don't have Microsoft Defender for Endpoint, a new data center location is automatically selected based on the location of active Microsoft 365 security services.</span></span> <span data-ttu-id="9bcdf-135">Den valda platsen för datacentret visas på skärmen.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-135">The selected data center location is shown in the screen.</span></span>

<span data-ttu-id="9bcdf-136">Välj **Behöver du hjälp?** i Säkerhetscenter för Microsoft 365 om du vill kontakta Microsofts support om etablering av Microsoft 365 Defender på en annan datacenterplats.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-136">Select **Need help?** in the Microsoft 365 security center to contact Microsoft support about provisioning Microsoft 365 Defender in a different data center location.</span></span>

> [!NOTE]
> <span data-ttu-id="9bcdf-137">Microsoft Defender för Slutpunkt tillhandahåller automatiskt datacenter i Europeiska unionen (EU) när det aktiveras via Azure Defender.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-137">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="9bcdf-138">Microsoft 365 Defender etablerar automatiskt i samma DATACENTER i EU för kunder som har etablerat Defender för Endpoint på det här sättet.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-138">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Defender for Endpoint in this manner.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="9bcdf-139">Bekräfta att tjänsten är på</span><span class="sxs-lookup"><span data-stu-id="9bcdf-139">Confirm that the service is on</span></span>

<span data-ttu-id="9bcdf-140">När tjänsten har etablerats lägger den till:</span><span class="sxs-lookup"><span data-stu-id="9bcdf-140">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="9bcdf-141">Incidenthantering</span><span class="sxs-lookup"><span data-stu-id="9bcdf-141">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="9bcdf-142">Ett åtgärdscenter för hantering [av automatiserad undersökning och svar](mtp-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="9bcdf-142">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="9bcdf-143">[Avancerade sökfunktioner](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="9bcdf-143">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>

<span data-ttu-id="9bcdf-144">![Bild av navigeringsfönstret i Microsoft 365 Säkerhetscenter med Microsoft 365 Defender-funktionerna i Microsoft 365 Säkerhetscenter med incidenthantering och andra ](../../media/mtp-enable/mtp-on.png)
 *Microsoft 365 Defender-funktioner*</span><span class="sxs-lookup"><span data-stu-id="9bcdf-144">![Image of Microsoft 365 security center navigation pane with Microsoft 365 Defender features](../../media/mtp-enable/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft 365 Defender capabilities*</span></span>

### <a name="getting-microsoft-defender-for-identity-data"></a><span data-ttu-id="9bcdf-145">Hämta Microsoft Defender för identitetsdata</span><span class="sxs-lookup"><span data-stu-id="9bcdf-145">Getting Microsoft Defender for Identity data</span></span>

<span data-ttu-id="9bcdf-146">Om du vill dela Microsoft Defender för identitetsdata med Microsoft 365 Defender ska du se till att Microsoft Cloud App Security och Microsoft Defender för identitetsintegrering är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-146">To share Microsoft Defender for Identity data with Microsoft 365 Defender, ensure that Microsoft Cloud App Security and Microsoft Defender for Identity integration is turned on.</span></span> <span data-ttu-id="9bcdf-147">[Läs mer om den här integreringen.](https://docs.microsoft.com/cloud-app-security/mdi-integration)</span><span class="sxs-lookup"><span data-stu-id="9bcdf-147">[Learn more about this integration](https://docs.microsoft.com/cloud-app-security/mdi-integration).</span></span>

## <a name="get-assistance"></a><span data-ttu-id="9bcdf-148">Få hjälp</span><span class="sxs-lookup"><span data-stu-id="9bcdf-148">Get assistance</span></span>

<span data-ttu-id="9bcdf-149">Läs vanliga frågor och svar om hur du använder Microsoft 365 [Defender.](mtp-enable-faq.md)</span><span class="sxs-lookup"><span data-stu-id="9bcdf-149">To get answers to the most commonly asked questions about turning on Microsoft 365 Defender, [read the FAQ](mtp-enable-faq.md).</span></span>

<span data-ttu-id="9bcdf-150">Microsofts supportpersonal kan hjälpa till att tillhandahålla eller återkalla tjänsten och relaterade resurser i klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-150">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="9bcdf-151">Behöver du hjälp väljer **du Behöver du hjälp?** i Säkerhetscenter för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-151">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="9bcdf-152">När du kontaktar supporten kan du nämna Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-152">When contacting support, mention Microsoft 365 Defender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="9bcdf-153">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="9bcdf-153">Related topics</span></span>

- [<span data-ttu-id="9bcdf-154">Vanliga frågor och svar</span><span class="sxs-lookup"><span data-stu-id="9bcdf-154">Frequently asked questions</span></span>](mtp-enable-faq.md)
- [<span data-ttu-id="9bcdf-155">Licenskrav och andra förutsättningar</span><span class="sxs-lookup"><span data-stu-id="9bcdf-155">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="9bcdf-156">Distribuera tjänster som stöds</span><span class="sxs-lookup"><span data-stu-id="9bcdf-156">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="9bcdf-157">Översikt över Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9bcdf-157">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="9bcdf-158">Översikt över Microsoft Defender för slutpunkt</span><span class="sxs-lookup"><span data-stu-id="9bcdf-158">Microsoft Defender for Endpoint overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="9bcdf-159">Översikt över Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="9bcdf-159">Defender for Office 365 overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="9bcdf-160">Översikt över säkerhet i Microsoft Cloud App</span><span class="sxs-lookup"><span data-stu-id="9bcdf-160">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="9bcdf-161">Översikt över Microsoft Defender för identitet</span><span class="sxs-lookup"><span data-stu-id="9bcdf-161">Microsoft Defender for Identity overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="9bcdf-162">Microsoft Defender för lagring av slutpunktsdata</span><span class="sxs-lookup"><span data-stu-id="9bcdf-162">Microsoft Defender for Endpoint data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
