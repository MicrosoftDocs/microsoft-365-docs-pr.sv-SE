---
title: Komma igång med instrumentpanelen för dataförlustskyddsvarningar
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: Kom igång med att definiera och hantera aviseringar för principer för dataförlustskydd.
ms.openlocfilehash: 7f070dd960cc00ad7899c75117cd2a3fcf679973
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51760770"
---
# <a name="get-started-with-the-data-loss-prevention-alert-dashboard"></a><span data-ttu-id="da870-103">Komma igång med instrumentpanelen för dataförlustskyddsvarningar</span><span class="sxs-lookup"><span data-stu-id="da870-103">Get started with the data loss prevention alert dashboard</span></span>

<span data-ttu-id="da870-104">DLP-principer (Data Loss Prevention) kan vidta skyddsåtgärder för att förhindra oavsiktlig delning av känsliga objekt.</span><span class="sxs-lookup"><span data-stu-id="da870-104">Data loss prevention (DLP) policies can take protective actions to prevent unintentional sharing of sensitive items.</span></span> <span data-ttu-id="da870-105">När en åtgärd vidtas på ett känsligt objekt kan du få ett meddelande genom att konfigurera aviseringar för DLP.</span><span class="sxs-lookup"><span data-stu-id="da870-105">When an action is taken on a sensitive item, you can be notified by configuring alerts for DLP.</span></span> <span data-ttu-id="da870-106">I den här artikeln beskrivs hur du definierar principer för avancerade aviseringar som är kopplade till DLP-principer (dataförlustskydd).</span><span class="sxs-lookup"><span data-stu-id="da870-106">This article shows you how to define rich alert policies that are linked to your data loss prevention (DLP) policies.</span></span> <span data-ttu-id="da870-107">Du får se hur du använder instrumentpanelen för hantering av [DLP-aviseringar](https://compliance.microsoft.com/datalossprevention?viewid=dlpalerts) i Efterlevnadscenter för [Microsoft 365](https://compliance.microsoft.com/) för att visa aviseringar, händelser och tillhörande metadata för DLP-principfel.</span><span class="sxs-lookup"><span data-stu-id="da870-107">You'll see how to use the [DLP alert management dashboard](https://compliance.microsoft.com/datalossprevention?viewid=dlpalerts) in the [Microsoft 365 compliance center](https://compliance.microsoft.com/) to view alerts, events, and associated metadata for DLP policy violations.</span></span>

<span data-ttu-id="da870-108">Om DLP-aviseringar är nytt för dig bör du läsa Mer om instrumentpanelen för skydd mot [dataförlust](dlp-alerts-dashboard-learn.md)</span><span class="sxs-lookup"><span data-stu-id="da870-108">If you are new to DLP alerts, you should review [Learn about the data loss prevention alerts dashboard](dlp-alerts-dashboard-learn.md)</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="da870-109">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="da870-109">Before you begin</span></span>

<span data-ttu-id="da870-110">Innan du börjar kontrollerar du att du har de krav som krävs:</span><span class="sxs-lookup"><span data-stu-id="da870-110">Before you begin, make sure you have the necessary prerequisites:</span></span>

-   <span data-ttu-id="da870-111">Licensiering för Instrumentpanelen för hantering av DLP-aviseringar</span><span class="sxs-lookup"><span data-stu-id="da870-111">Licensing for the DLP alerts management dashboard</span></span>
-   <span data-ttu-id="da870-112">Licensiering för alternativ för aviseringskonfiguration</span><span class="sxs-lookup"><span data-stu-id="da870-112">Licensing for alert configuration options</span></span>
-   <span data-ttu-id="da870-113">Roller</span><span class="sxs-lookup"><span data-stu-id="da870-113">Roles</span></span>

### <a name="licensing-for-the-dlp-alert-management-dashboard"></a><span data-ttu-id="da870-114">Licensiering för Instrumentpanelen för DLP-aviseringshantering</span><span class="sxs-lookup"><span data-stu-id="da870-114">Licensing for the DLP alert management dashboard</span></span>

<span data-ttu-id="da870-115">Alla kvalificerade klientorganisationar för Office 365 DLP har åtkomst till Instrumentpanelen för DLP-aviseringshantering.</span><span class="sxs-lookup"><span data-stu-id="da870-115">All eligible tenants for Office 365 DLP can access the DLP alert management dashboard.</span></span> <span data-ttu-id="da870-116">För att komma igång bör du vara berättigad till Office 365 DLP för Exchange Online, SharePoint Online och OneDrive för företag.</span><span class="sxs-lookup"><span data-stu-id="da870-116">To get started, you should be eligible for Office 365 DLP for Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="da870-117">Mer information om licenskraven för Office 365 DLP finns i Vilka licenser tillhandahåller rättigheter som en användare kan dra [nytta av tjänsten?](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16)</span><span class="sxs-lookup"><span data-stu-id="da870-117">For more information about the licensing requirements for Office 365 DLP, see [Which licenses provide the rights for a user to benefit from the service?](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16).</span></span>

<span data-ttu-id="da870-118">Kunder som använder [Slutpunkt DLP som](endpoint-dlp-learn-about.md) är kvalificerade för Teams DLP ser deras DLP-principaviseringar för slutpunkten och aviseringar för Teams DLP-princip på instrumentpanelen för hantering av DLP-aviseringar. [](dlp-microsoft-teams.md)</span><span class="sxs-lookup"><span data-stu-id="da870-118">Customers who use [Endpoint DLP](endpoint-dlp-learn-about.md) who are eligible for [Teams DLP](dlp-microsoft-teams.md) will see their endpoint DLP policy alerts and Teams DLP policy alerts in the DLP alert management dashboard.</span></span>

<span data-ttu-id="da870-119">Funktionen **för förhandsgranskning** av innehåll är endast tillgänglig för följande licenser:</span><span class="sxs-lookup"><span data-stu-id="da870-119">The **content preview** feature is available only for these licenses:</span></span>

- <span data-ttu-id="da870-120">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="da870-120">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="da870-121">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="da870-121">Office 365 (E5)</span></span>
- <span data-ttu-id="da870-122">Advanced Compliance (E5) add on</span><span class="sxs-lookup"><span data-stu-id="da870-122">Advanced Compliance (E5) add on</span></span>
- <span data-ttu-id="da870-123">Informationsskydd och styrning i Microsoft 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="da870-123">Microsoft 365 E5/A5 Information Protection and Governance</span></span>
- <span data-ttu-id="da870-124">Efterlevnad i Microsft 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="da870-124">Microsft 365 E5/A5 Compliance</span></span>

### <a name="licensing-for-alert-configuration-options"></a><span data-ttu-id="da870-125">Licensiering för alternativ för aviseringskonfiguration</span><span class="sxs-lookup"><span data-stu-id="da870-125">Licensing for alert configuration options</span></span>

<span data-ttu-id="da870-126">**Aviseringskonfiguration** för enstaka händelser : Organisationer som har en E1-, F1- eller G1-prenumeration eller en E3- eller G3-prenumeration kan bara skapa aviseringsprinciper där en avisering utlöses varje gång en aktivitet inträffar.</span><span class="sxs-lookup"><span data-stu-id="da870-126">**Single-event alert configuration**: Organizations that have an E1, F1, or G1 subscription or an E3 or G3 subscription can create alert policies only where an alert is triggered every time an activity occurs.</span></span>

<span data-ttu-id="da870-127">**Aggregerad aviseringskonfiguration:** Om du vill konfigurera principer för aggregerad avisering baserat på ett tröskelvärde måste du en av följande licenskonfigurationer:</span><span class="sxs-lookup"><span data-stu-id="da870-127">**Aggregated alert configuration**: To configure aggregate alert policies based on a threshold, you must one of these licensing configurations:</span></span>

- <span data-ttu-id="da870-128">En E5- eller G5-prenumeration</span><span class="sxs-lookup"><span data-stu-id="da870-128">An E5 or G5 subscription</span></span>
- <span data-ttu-id="da870-129">En E1-, F1- eller G1-prenumeration eller en E3- eller G3-prenumeration som innehåller någon av följande funktioner:</span><span class="sxs-lookup"><span data-stu-id="da870-129">An E1, F1, or G1 subscription or an E3 or G3 subscription that includes one of the following features:</span></span>
    - <span data-ttu-id="da870-130">Office 365 Advanced Threat Protection Plan 2</span><span class="sxs-lookup"><span data-stu-id="da870-130">Office 365 Advanced Threat Protection Plan 2</span></span>
    - <span data-ttu-id="da870-131">Microsoft 365 E5 Compliance</span><span class="sxs-lookup"><span data-stu-id="da870-131">Microsoft 365 E5 Compliance</span></span>
    - <span data-ttu-id="da870-132">Tilläggslicens för Microsoft 365 eDiscovery och Granskning</span><span class="sxs-lookup"><span data-stu-id="da870-132">Microsoft 365 eDiscovery and Audit add-on license</span></span>

### <a name="roles"></a><span data-ttu-id="da870-133">Roller</span><span class="sxs-lookup"><span data-stu-id="da870-133">Roles</span></span>


<span data-ttu-id="da870-134">Om du vill visa instrumentpanelen för hantering av DLP-aviseringar eller redigera alternativ för aviseringskonfiguration i en DLP-princip måste du vara medlem i någon av dessa rollgrupper:</span><span class="sxs-lookup"><span data-stu-id="da870-134">If you want to view the DLP alert management dashboard or to edit the alert configuration options in a DLP policy, you must be a member of one of these role groups:</span></span>

- <span data-ttu-id="da870-135">Efterlevnadsadministratör</span><span class="sxs-lookup"><span data-stu-id="da870-135">Compliance Administrator</span></span>
- <span data-ttu-id="da870-136">Dataadministratör för efterlevnad</span><span class="sxs-lookup"><span data-stu-id="da870-136">Compliance Data Administrator</span></span>
- <span data-ttu-id="da870-137">Säkerhetsadministratör</span><span class="sxs-lookup"><span data-stu-id="da870-137">Security Administrator</span></span>
- <span data-ttu-id="da870-138">Säkerhetsoperatör</span><span class="sxs-lookup"><span data-stu-id="da870-138">Security Operator</span></span>
- <span data-ttu-id="da870-139">Säkerhetsläsare</span><span class="sxs-lookup"><span data-stu-id="da870-139">Security Reader</span></span>

<span data-ttu-id="da870-140">För att komma åt Instrumentpanelen för hantering av DLP-aviseringar behöver du:</span><span class="sxs-lookup"><span data-stu-id="da870-140">To access the DLP alert management dashboard, you need the:</span></span>

- <span data-ttu-id="da870-141">Hantera varningar</span><span class="sxs-lookup"><span data-stu-id="da870-141">Manage alerts</span></span>

<span data-ttu-id="da870-142">och någon av följande två roller:</span><span class="sxs-lookup"><span data-stu-id="da870-142">and either of these two roles:</span></span>

- <span data-ttu-id="da870-143">DLP-efterlevnadshantering</span><span class="sxs-lookup"><span data-stu-id="da870-143">DLP Compliance Management</span></span>
- <span data-ttu-id="da870-144">View-Only DLP-efterlevnadshantering</span><span class="sxs-lookup"><span data-stu-id="da870-144">View-Only DLP Compliance Management</span></span>

<span data-ttu-id="da870-145">För att komma åt funktionen Förhandsgranskning av innehåll och funktioner för matchat känsligt innehåll och kontext måste du vara medlem i:</span><span class="sxs-lookup"><span data-stu-id="da870-145">To access the Content preview feature and the Matched sensitive content and context features you must be a member of:</span></span>

- <span data-ttu-id="da870-146">Rollgruppen Innehållsvisare i Innehållsutforskaren</span><span class="sxs-lookup"><span data-stu-id="da870-146">Content Explorer Content Viewer role group</span></span>

<span data-ttu-id="da870-147">som har rollen dataklassificeringsinnehållsläsare för tilldelad.</span><span class="sxs-lookup"><span data-stu-id="da870-147">which has the data classification content viewer role pre-assigned.</span></span>

## <a name="dlp-alert-configuration"></a><span data-ttu-id="da870-148">Konfiguration av DLP-avisering</span><span class="sxs-lookup"><span data-stu-id="da870-148">DLP alert configuration</span></span>

<span data-ttu-id="da870-149">Information om hur du konfigurerar en avisering i DLP-principen finns i Här kan [du börja med skydd mot dataförlust.](create-test-tune-dlp-policy.md#where-to-start-with-data-loss-prevention)</span><span class="sxs-lookup"><span data-stu-id="da870-149">To learn how to configure an alert in your DLP policy, see [Where to start with data loss prevention](create-test-tune-dlp-policy.md#where-to-start-with-data-loss-prevention).</span></span>

### <a name="aggregate-event-alert-configuration"></a><span data-ttu-id="da870-150">Konfiguration av mängdhändelseavisering</span><span class="sxs-lookup"><span data-stu-id="da870-150">Aggregate event alert configuration</span></span>

<span data-ttu-id="da870-151">Om din organisation har licens för [konfigurationsalternativ](#licensing-for-alert-configuration-options)för aggregerade aviseringar visas de här alternativen när du skapar eller redigerar en DLP-princip.</span><span class="sxs-lookup"><span data-stu-id="da870-151">If your org is licensed for [aggregated alert configuration options](#licensing-for-alert-configuration-options), then you'll see these options when you create or edit a DLP policy.</span></span>

:::image type="content" source="../media/incident-reports-options-aggregated-alerts.png" alt-text="Skärmbild som visar alternativ för incidentrapporter för användare som är kvalificerade för konfigurationsalternativ för aggregerade aviseringar." border="false":::

<span data-ttu-id="da870-153">Med den här konfigurationen kan du konfigurera en princip för att generera en avisering varje gång en aktivitet matchar principvillkoren eller när ett visst tröskelvärde överskrids, baserat på antalet aktiviteter eller baserat på mängden data som förts över.</span><span class="sxs-lookup"><span data-stu-id="da870-153">This configuration allows you to set up a policy to generate an alert every time an activity matches the policy conditions or when a certain threshold is exceeded, based on the number of activities or based on the volume of exfiltrated data.</span></span>

### <a name="single-event-alert-configuration"></a><span data-ttu-id="da870-154">Konfiguration av en händelseavisering</span><span class="sxs-lookup"><span data-stu-id="da870-154">Single event alert configuration</span></span>

<span data-ttu-id="da870-155">Om din organisation har licens för konfigurationsalternativ för aviseringar för enstaka händelser visas de här alternativen när du skapar eller redigerar en [DLP-princip.](#licensing-for-alert-configuration-options)</span><span class="sxs-lookup"><span data-stu-id="da870-155">If your org is licensed for [single-event alert configuration options](#licensing-for-alert-configuration-options), then you'll see these options when you create or edit a DLP policy.</span></span> <span data-ttu-id="da870-156">Använd det här alternativet om du vill skapa en avisering som höjs varje gång en DLP-regel matchar.</span><span class="sxs-lookup"><span data-stu-id="da870-156">Use this option to create an alert that's raised every time a DLP rule match happens.</span></span>

:::image type="content" source="../media/incident-reports-options-single-event-alerts.png" alt-text="Skärmbild som visar alternativ för incidentrapporter för användare som är kvalificerade för konfigurationsalternativ för aviseringar för enstaka händelser." border="false":::

## <a name="investigate-a-dlp-alert"></a><span data-ttu-id="da870-158">Undersöka en DLP-avisering</span><span class="sxs-lookup"><span data-stu-id="da870-158">Investigate a DLP alert</span></span>

<span data-ttu-id="da870-159">Så här arbetar du med Instrumentpanelen för DLP-aviseringshantering:</span><span class="sxs-lookup"><span data-stu-id="da870-159">To work with the DLP alert management dashboard:</span></span>

1. <span data-ttu-id="da870-160">Gå till Skydd mot dataförlust i Efterlevnadscenter **för** [Microsoft 365.](https://www.compliance.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="da870-160">In the [Microsoft 365 compliance center](https://www.compliance.microsoft.com), go to **Data Loss Prevention**.</span></span>
2. <span data-ttu-id="da870-161">Välj fliken **Aviseringar för** att visa instrumentpanelen för DLP-aviseringar.</span><span class="sxs-lookup"><span data-stu-id="da870-161">Select the **Alerts** tab to view the DLP alerts dashboard.</span></span>
3. <span data-ttu-id="da870-162">Välj en avisering om du vill se mer information:</span><span class="sxs-lookup"><span data-stu-id="da870-162">Select an alert to see details:</span></span>

:::image type="content" source="../media/alert-details.png" alt-text="Skärmbild som visar aviseringsinformation på instrumentpanelen för hantering av DLP-aviseringar." border="false":::

4. <span data-ttu-id="da870-164">Välj fliken **Händelser** om du vill visa alla händelser som är associerade med aviseringen.</span><span class="sxs-lookup"><span data-stu-id="da870-164">Select the **Events** tab to view all of the events associated with the alert.</span></span> <span data-ttu-id="da870-165">Du kan välja en viss händelse om du vill visa dess information.</span><span class="sxs-lookup"><span data-stu-id="da870-165">You can choose a particular event to view its details.</span></span> <span data-ttu-id="da870-166">En lista över en del av den tillgängliga händelseinformationen finns i Läs mer om instrumentpanelen [för skydd mot dataförlust](dlp-alerts-dashboard-learn.md).</span><span class="sxs-lookup"><span data-stu-id="da870-166">For a list of some of the available event details, see, [Learn about the data loss prevention Alerts dashboard](dlp-alerts-dashboard-learn.md).</span></span>
5. <span data-ttu-id="da870-167">Välj **Information** för att öppna **sidan** Översikt för aviseringen.</span><span class="sxs-lookup"><span data-stu-id="da870-167">Select **Details** to open the **Overview** page for the alert.</span></span> <span data-ttu-id="da870-168">Översiktssidan ger en sammanfattning:</span><span class="sxs-lookup"><span data-stu-id="da870-168">The overview page provides a summary:</span></span>
    1. <span data-ttu-id="da870-169">av vad som hände</span><span class="sxs-lookup"><span data-stu-id="da870-169">of what happened</span></span>
    1. <span data-ttu-id="da870-170">vem som utförde de åtgärder som orsakade principmatchning</span><span class="sxs-lookup"><span data-stu-id="da870-170">who performed the actions that caused the policy match</span></span>
    1. <span data-ttu-id="da870-171">information om den matchade principen och mycket mer</span><span class="sxs-lookup"><span data-stu-id="da870-171">information about the matched policy, and more</span></span> 

6. <span data-ttu-id="da870-172">Välj fliken **Händelser** för att komma åt:</span><span class="sxs-lookup"><span data-stu-id="da870-172">Choose the **Events** tab to access the:</span></span>
    1. <span data-ttu-id="da870-173">innehåll som ingår</span><span class="sxs-lookup"><span data-stu-id="da870-173">content involved</span></span>
    1. <span data-ttu-id="da870-174">Matchning av känslig information</span><span class="sxs-lookup"><span data-stu-id="da870-174">sensitive information types matched</span></span>
    1. <span data-ttu-id="da870-175">metadata</span><span class="sxs-lookup"><span data-stu-id="da870-175">metadata</span></span>

7. <span data-ttu-id="da870-176">Välj fliken **Typer av känslig information** om du vill visa information om de typer av känslig information som upptäckts i innehållet.</span><span class="sxs-lookup"><span data-stu-id="da870-176">Select the **Sensitive Info Types** tab to view details about the sensitive information types detected in the content.</span></span> <span data-ttu-id="da870-177">I informationen ingår konfidens, antal och innehåll som matchar den typ av känslig information.</span><span class="sxs-lookup"><span data-stu-id="da870-177">Details include confidence, count, and the content that matches the sensitive information type.</span></span>

8. <span data-ttu-id="da870-178">När du har undersökt aviseringen går du tillbaka till fliken Översikt där du kan hantera triangeln och hantera dispositionen av aviseringen och lägga till kommentarer. </span><span class="sxs-lookup"><span data-stu-id="da870-178">After you investigate the alert, return to the **Overview** tab where you can manage triage and manage the disposition of the alert and add comments.</span></span>

- <span data-ttu-id="da870-179">Om du vill se historiken för arbetsflödeshantering väljer du **Hanteringslogg**.</span><span class="sxs-lookup"><span data-stu-id="da870-179">To see the history of workflow management, choose **Management log**.</span></span>
- <span data-ttu-id="da870-180">När du har vidta den åtgärd som krävs för aviseringen ställer du in statusen för aviseringen på **Matchad**.</span><span class="sxs-lookup"><span data-stu-id="da870-180">After you take the required action for the alert, set the status of the alert to **Resolved**.</span></span>

## <a name="see-also"></a><span data-ttu-id="da870-181">Se även</span><span class="sxs-lookup"><span data-stu-id="da870-181">See also</span></span>

- [<span data-ttu-id="da870-182">Läs mer om varningar om skydd mot dataförlust och instrumentpanelen för aviseringar</span><span class="sxs-lookup"><span data-stu-id="da870-182">Learn about data loss prevention alerts and the alerts dashboard</span></span>](dlp-alerts-dashboard-learn.md)
- [<span data-ttu-id="da870-183">Skapa, testa och justera en DLP-princip</span><span class="sxs-lookup"><span data-stu-id="da870-183">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)