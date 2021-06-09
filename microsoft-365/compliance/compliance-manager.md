---
title: Microsoft Compliance Manager
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-compliancemanager
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft Compliance Manager hjälper organisationer att förenkla och automatisera riskutvärderingar och föreslår rekommenderade åtgärder för att hantera risker.
ms.openlocfilehash: 7eb8e0fdea26ca24453ca7071ab1282c686d5848
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244401"
---
# <a name="microsoft-compliance-manager"></a><span data-ttu-id="4f705-103">Microsoft Compliance Manager</span><span class="sxs-lookup"><span data-stu-id="4f705-103">Microsoft Compliance Manager</span></span>

<span data-ttu-id="4f705-104">**I den här artikeln:** Lär dig vad Efterlevnadshanteraren är, hur den förenklar efterlevnad och minskar risker samt nyckelkomponenter.</span><span class="sxs-lookup"><span data-stu-id="4f705-104">**In this article:** Learn what Compliance Manager is, how it helps simplify compliance and reduce risk, and its key components.</span></span>

## <a name="whats-new-the-ga-release-of-compliance-manager"></a><span data-ttu-id="4f705-105">Vad är nytt: GA-versionen av Efterlevnadshanteraren</span><span class="sxs-lookup"><span data-stu-id="4f705-105">What's new: the GA release of Compliance Manager</span></span>

<span data-ttu-id="4f705-106">Efterlevnadshanteraren är nu allmänt tillgänglig (GA) som en punkt till punkt-lösning för efterlevnadshantering i [Microsoft 365 för efterlevnadscenter.](microsoft-365-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="4f705-106">Compliance Manager is now generally available (GA) as an end-to-end compliance management solution inside the [Microsoft 365 compliance center](microsoft-365-compliance-center.md).</span></span> <span data-ttu-id="4f705-107">Med den här versionen slutförs övergången från den tidigare platsen i Microsoft Service Trust Portal.</span><span class="sxs-lookup"><span data-stu-id="4f705-107">With this release, Compliance Manager completes the transition from its previous location in the Microsoft Service Trust Portal.</span></span> <span data-ttu-id="4f705-108">Efterlevnadshanteraren är även tillgänglig för kunder i amerikanska government community (GCC) måttliga, GCC hög och doD-kunder (Department of Defense).</span><span class="sxs-lookup"><span data-stu-id="4f705-108">Compliance Manager is also  available to US Government Community (GCC) Moderate, GCC High, and Department of Defense (DoD) customers.</span></span>

<span data-ttu-id="4f705-109">Det som började som den offentliga förhandsversionen av Efterlevnadsresultat har utvecklats till ett centralt verktyg med förbättrade funktioner för efterlevnadshantering och enklare användning.</span><span class="sxs-lookup"><span data-stu-id="4f705-109">What began as the public preview of Compliance Score has evolved into a centralized tool with enhanced compliance management capabilities and greater ease of use.</span></span>  <span data-ttu-id="4f705-110">Med GA-versionen får du en större samling färdiga bedömningar som hjälper dig att anpassa dina efterlevnadsaktiviteter.</span><span class="sxs-lookup"><span data-stu-id="4f705-110">The GA release brings a larger collection of pre-built assessments to help you scale your compliance activities.</span></span>

<span data-ttu-id="4f705-111">**Läs mer om GA-versionen:**</span><span class="sxs-lookup"><span data-stu-id="4f705-111">**Learn more about the GA release:**</span></span>
- <span data-ttu-id="4f705-112">Våra [vanliga frågor går](compliance-manager-faq.md) igenom utvecklingen i detalj.</span><span class="sxs-lookup"><span data-stu-id="4f705-112">Our [frequently asked questions](compliance-manager-faq.md) walk you through the evolution in greater detail.</span></span>
- <span data-ttu-id="4f705-113">Läs mer om förbättringar av GA-funktioner [i det här blogginlägget.](https://aka.ms/compliancemanager/GAblog)</span><span class="sxs-lookup"><span data-stu-id="4f705-113">Read about GA feature enhancements in [this blog post](https://aka.ms/compliancemanager/GAblog).</span></span>

<span data-ttu-id="4f705-114">Titta på videon nedan för att lära dig hur Efterlevnadshanteraren kan förenkla hur organisationen hanterar efterlevnad:</span><span class="sxs-lookup"><span data-stu-id="4f705-114">Watch the video below to learn how Compliance Manager can help simplify how your organization manages compliance:</span></span>
<br>
<br>
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4FGYZ]

## <a name="what-is-compliance-manager"></a><span data-ttu-id="4f705-115">Vad är Efterlevnadshanteraren</span><span class="sxs-lookup"><span data-stu-id="4f705-115">What is Compliance Manager</span></span>

<span data-ttu-id="4f705-116">[Microsoft Compliance Manager](https://compliance.microsoft.com/compliancemanager) är en funktion i [Microsoft 365 efterlevnadscenter](microsoft-365-compliance-center.md) som hjälper dig att hantera organisationens efterlevnadskrav enklare och enklare.</span><span class="sxs-lookup"><span data-stu-id="4f705-116">[Microsoft Compliance Manager](https://compliance.microsoft.com/compliancemanager) is a feature in the [Microsoft 365 compliance center](microsoft-365-compliance-center.md) that helps you manage your organization’s compliance requirements with greater ease and convenience.</span></span> <span data-ttu-id="4f705-117">Efterlevnadshanteraren kan hjälpa dig under hela resan, från att inventera dina dataskyddsrisker till att hantera komplexiteten i implementeringen av kontroller, hålla dig aktuell med bestämmelser och certifieringar och rapportera till granskare.</span><span class="sxs-lookup"><span data-stu-id="4f705-117">Compliance Manager can help you throughout your compliance journey, from taking inventory of your data protection risks to managing the complexities of implementing controls, staying current with regulations and certifications, and reporting to auditors.</span></span>

<span data-ttu-id="4f705-118">Efterlevnadshanteraren hjälper till att förenkla efterlevnad och minska risken genom att tillhandahålla:</span><span class="sxs-lookup"><span data-stu-id="4f705-118">Compliance Manager helps simplify compliance and reduce risk by providing:</span></span>

- <span data-ttu-id="4f705-119">Förbyggda bedömningar av vanliga bransch- och regionala standarder och bestämmelser, eller anpassade utvärderingar för att uppfylla dina unika efterlevnadsbehov (tillgängliga bedömningar beror på ditt licensavtal; [läs mer](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)).</span><span class="sxs-lookup"><span data-stu-id="4f705-119">Pre-built assessments for common industry and regional standards and regulations, or custom assessments to meet your unique compliance needs (available assessments depend on your licensing agreement; [learn more](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)).</span></span>

- <span data-ttu-id="4f705-120">Arbetsflödesfunktioner som hjälper dig att effektivt slutföra dina riskutvärderingar genom ett enda verktyg.</span><span class="sxs-lookup"><span data-stu-id="4f705-120">Workflow capabilities to help you efficiently complete your risk assessments through a single tool.</span></span>

- <span data-ttu-id="4f705-121">Detaljerad steg för steg-vägledning om föreslagna förbättringsåtgärder som hjälper dig att följa de standarder och bestämmelser som är mest relevanta för din organisation.</span><span class="sxs-lookup"><span data-stu-id="4f705-121">Detailed step-by-step guidance on suggested improvement actions to help you comply with the standards and regulations that are most relevant for your organization.</span></span> <span data-ttu-id="4f705-122">För åtgärder som hanteras av Microsoft ser du implementeringsinformation och granskningsresultat.</span><span class="sxs-lookup"><span data-stu-id="4f705-122">For actions that are managed by Microsoft, you’ll see implementation details and audit results.</span></span>

- <span data-ttu-id="4f705-123">Ett riskbaserat efterlevnadsresultat som hjälper dig att förstå hur efterlevnad ser ut genom att mäta förloppet för att slutföra förbättringsåtgärder.</span><span class="sxs-lookup"><span data-stu-id="4f705-123">A risk-based compliance score to help you understand your compliance posture by measuring your progress in completing improvement actions.</span></span>

<span data-ttu-id="4f705-124">Instrumentpanelen för Efterlevnadshanteraren visar ditt aktuella efterlevnadsresultat, hjälper dig att se vad som behöver uppmärksammas och vägleder dig till viktiga förbättringsåtgärder.</span><span class="sxs-lookup"><span data-stu-id="4f705-124">Your Compliance Manager dashboard shows your current compliance score, helps you see what needs attention, and guides you to key improvement actions.</span></span> <span data-ttu-id="4f705-125">Nedan är ett exempel på hur instrumentpanelen för Efterlevnadshanteraren kommer att se ut:</span><span class="sxs-lookup"><span data-stu-id="4f705-125">Below is an example of what your Compliance Manager dashboard will look like:</span></span>

<span data-ttu-id="4f705-126">![Efterlevnadshanteraren – instrumentpanel](../media/compliance-manager-dashboard.png "Instrumentpanel för Efterlevnadshanteraren")</span><span class="sxs-lookup"><span data-stu-id="4f705-126">![Compliance Manager - dashboard](../media/compliance-manager-dashboard.png "Compliance Manager dashboard")</span></span>

## <a name="understanding-your-compliance-score"></a><span data-ttu-id="4f705-127">Förstå din efterlevnadspoäng</span><span class="sxs-lookup"><span data-stu-id="4f705-127">Understanding your compliance score</span></span>

<span data-ttu-id="4f705-128">Efterlevnadshanteraren belönar dig för att du har slutfört förbättringsåtgärder som vidtas för att följa en regel, standard eller princip och kombinerar dessa punkter till en övergripande efterlevnadspoäng.</span><span class="sxs-lookup"><span data-stu-id="4f705-128">Compliance Manager awards you points for completing improvement actions taken to comply with a regulation, standard, or policy, and combines those points into an overall compliance score.</span></span> <span data-ttu-id="4f705-129">Varje åtgärd har olika påverkan på ditt resultat beroende på de potentiella risker som ingår.</span><span class="sxs-lookup"><span data-stu-id="4f705-129">Each action has a different impact on your score depending on the potential risks involved.</span></span> <span data-ttu-id="4f705-130">Din efterlevnadspoäng kan hjälpa dig att prioritera vilken åtgärd du ska fokusera på för att förbättra din övergripande efterlevnad.</span><span class="sxs-lookup"><span data-stu-id="4f705-130">Your compliance score can help prioritize which action to focus on to improve your overall compliance posture.</span></span>

<span data-ttu-id="4f705-131">Efterlevnadshanteraren ger dig en inledande poäng baserat Microsoft 365 dataskyddsbaslinje.</span><span class="sxs-lookup"><span data-stu-id="4f705-131">Compliance Manager gives you an initial score based on the Microsoft 365 data protection baseline.</span></span> <span data-ttu-id="4f705-132">Den här baslinjen är en uppsättning kontroller som innehåller viktiga bestämmelser och standarder för dataskydd och allmän datastyrning.</span><span class="sxs-lookup"><span data-stu-id="4f705-132">This baseline is a set of controls that includes key regulations and standards for data protection and general data governance.</span></span>

##### <a name="learn-more"></a><span data-ttu-id="4f705-133">Mer information</span><span class="sxs-lookup"><span data-stu-id="4f705-133">Learn more</span></span>

<span data-ttu-id="4f705-134">[Förstå hur ditt efterlevnadsresultat beräknas](compliance-score-calculation.md).</span><span class="sxs-lookup"><span data-stu-id="4f705-134">[Understand how your compliance score is calculated](compliance-score-calculation.md).</span></span>

<span data-ttu-id="4f705-135">[Lär dig hur du arbetar med förbättringsåtgärder](compliance-manager-improvement-actions.md).</span><span class="sxs-lookup"><span data-stu-id="4f705-135">[Learn how to work with improvement actions](compliance-manager-improvement-actions.md).</span></span>

## <a name="key-elements-controls-assessments-templates-improvement-actions"></a><span data-ttu-id="4f705-136">Huvudelement: kontroller, utvärderingar, mallar, förbättringsåtgärder</span><span class="sxs-lookup"><span data-stu-id="4f705-136">Key elements: controls, assessments, templates, improvement actions</span></span>

<span data-ttu-id="4f705-137">Efterlevnadshanteraren använder flera dataelement som hjälper dig att hantera dina efterlevnadsaktiviteter.</span><span class="sxs-lookup"><span data-stu-id="4f705-137">Compliance Manager uses several data elements to help you manage your compliance activities.</span></span> <span data-ttu-id="4f705-138">När du använder Efterlevnadshanteraren för att tilldela, testa och övervaka efterlevnadsaktiviteter är det bra att ha en grundläggande förståelse för de viktigaste elementen: kontroller, utvärderingar, mallar och förbättringsåtgärder.</span><span class="sxs-lookup"><span data-stu-id="4f705-138">As you use Compliance Manager to assign, test, and monitor compliance activities, it’s helpful to have a basic understanding of the key elements: controls, assessments, templates, and improvement actions.</span></span>

### <a name="controls"></a><span data-ttu-id="4f705-139">Kontroller</span><span class="sxs-lookup"><span data-stu-id="4f705-139">Controls</span></span>

<span data-ttu-id="4f705-140">En kontroll är ett krav för en regel, standard eller princip.</span><span class="sxs-lookup"><span data-stu-id="4f705-140">A control is a requirement of a regulation, standard, or policy.</span></span> <span data-ttu-id="4f705-141">Den definierar hur du utvärderar och hanterar systemkonfiguration, organisationsprocess och personer som ansvarar för att uppfylla ett visst krav för en regel, standard eller princip.</span><span class="sxs-lookup"><span data-stu-id="4f705-141">It defines how you assess and manage system configuration, organizational process, and people responsible for meeting a specific requirement of a regulation, standard, or policy.</span></span>

<span data-ttu-id="4f705-142">Efterlevnadshanteraren håller i följande typer av kontroller:</span><span class="sxs-lookup"><span data-stu-id="4f705-142">Compliance Manager tracks the following types of controls:</span></span>

1. <span data-ttu-id="4f705-143">**Microsoft-hanterade** kontroller: kontroller för Microsoft-molntjänster, som Microsoft ansvarar för att implementera</span><span class="sxs-lookup"><span data-stu-id="4f705-143">**Microsoft managed controls**: controls for Microsoft cloud services, which Microsoft is responsible for implementing</span></span>
2. <span data-ttu-id="4f705-144">**Dina kontroller:** kallas ibland för kund hanterade kontroller, dessa är kontroller implementerade och hanterade av din organisation</span><span class="sxs-lookup"><span data-stu-id="4f705-144">**Your controls**: sometimes referred to as customer managed controls, these are controls implemented and managed by your organization</span></span>
3. <span data-ttu-id="4f705-145">**Delade kontroller:** det här är kontroller som både din organisation och Microsoft har ansvar för att implementera</span><span class="sxs-lookup"><span data-stu-id="4f705-145">**Shared controls**: these are controls that both your organization and Microsoft share responsibility for implementing</span></span>

##### <a name="learn-more"></a><span data-ttu-id="4f705-146">Mer information</span><span class="sxs-lookup"><span data-stu-id="4f705-146">Learn more</span></span>

<span data-ttu-id="4f705-147">[Övervaka förloppet för dina kontroller.](compliance-manager-assessments.md#monitor-assessment-progress-and-controls)</span><span class="sxs-lookup"><span data-stu-id="4f705-147">[Monitor progress of your controls](compliance-manager-assessments.md#monitor-assessment-progress-and-controls).</span></span>

<span data-ttu-id="4f705-148">[Lär dig hur Efterlevnadshanteraren kontinuerligt utvärderar kontroller.](compliance-score-calculation.md#how-compliance-manager-continuously-assesses-controls)</span><span class="sxs-lookup"><span data-stu-id="4f705-148">[Learn how Compliance Manager continuously assesses controls](compliance-score-calculation.md#how-compliance-manager-continuously-assesses-controls).</span></span>

### <a name="assessments"></a><span data-ttu-id="4f705-149">Utvärderingar</span><span class="sxs-lookup"><span data-stu-id="4f705-149">Assessments</span></span>

<span data-ttu-id="4f705-150">En bedömning består av gruppering av kontroller från en viss regel, standard eller princip.</span><span class="sxs-lookup"><span data-stu-id="4f705-150">An assessment is grouping of controls from a specific regulation, standard, or policy.</span></span> <span data-ttu-id="4f705-151">Att utföra åtgärder inom en bedömning hjälper dig att uppfylla kraven i en standard, regel eller lag.</span><span class="sxs-lookup"><span data-stu-id="4f705-151">Completing the actions within an assessment help you meet the requirements of a standard, regulation, or law.</span></span> <span data-ttu-id="4f705-152">Du kan till exempel göra en bedömning som gör att dina Microsoft 365-inställningar uppfyller ISO 27001-kraven när du har slutfört alla åtgärder i den.</span><span class="sxs-lookup"><span data-stu-id="4f705-152">For example, you may have an assessment that, when you complete all actions within it, helps to bring your Microsoft 365 settings in line with ISO 27001 requirements.</span></span>

<span data-ttu-id="4f705-153">Utvärderingar innehåller flera komponenter:</span><span class="sxs-lookup"><span data-stu-id="4f705-153">Assessments have several components:</span></span>

- <span data-ttu-id="4f705-154">**Tjänster inom omfattningen**: den specifika uppsättningen Microsoft-tjänster som gäller för utvärderingen</span><span class="sxs-lookup"><span data-stu-id="4f705-154">**In-scope services**: the specific set of Microsoft services applicable to the assessment</span></span>
- <span data-ttu-id="4f705-155">**Hanterade kontroller från Microsoft:** kontroller för Microsoft-molntjänster som Microsoft implementerar åt dig</span><span class="sxs-lookup"><span data-stu-id="4f705-155">**Microsoft managed controls**: controls for Microsoft cloud services, which Microsoft implements on your behalf</span></span>
- <span data-ttu-id="4f705-156">**Dina kontroller:** kallas ibland för kund hanterade kontroller, dessa är kontroller implementerade och hanterade av din organisation</span><span class="sxs-lookup"><span data-stu-id="4f705-156">**Your controls**: sometimes referred to as customer managed controls, these are controls implemented and managed by your organization</span></span>
- <span data-ttu-id="4f705-157">**Delade kontroller:** det här är kontroller som både din organisation och Microsoft har ansvar för att implementera</span><span class="sxs-lookup"><span data-stu-id="4f705-157">**Shared controls**: these are controls that both your organization and Microsoft share responsibility for implementing</span></span>
- <span data-ttu-id="4f705-158">**Utvärderingsresultat:** Visar förloppet för att uppnå totalt antal möjliga poäng från åtgärder inom utvärderingen som hanteras av din organisation och av Microsoft</span><span class="sxs-lookup"><span data-stu-id="4f705-158">**Assessment score**: shows your progress in achieving total possible points from actions within the assessment that are managed by your organization and by Microsoft</span></span>

<span data-ttu-id="4f705-159">När du skapar utvärderingar tilldelar du dem till en grupp.</span><span class="sxs-lookup"><span data-stu-id="4f705-159">When creating assessments, you’ll assign them to a group.</span></span> <span data-ttu-id="4f705-160">Du kan konfigurera grupper på det sätt som är mest logiskt för din organisation.</span><span class="sxs-lookup"><span data-stu-id="4f705-160">You can configure groups in whatever way is most logical for your organization.</span></span> <span data-ttu-id="4f705-161">Du kan till exempel gruppera utvärderingar efter granskningsår, region, lösning, grupper inom organisationen eller på något annat sätt.</span><span class="sxs-lookup"><span data-stu-id="4f705-161">For example, you may group assessments by audit year, region, solution, teams within your organization, or some other way.</span></span> <span data-ttu-id="4f705-162">När du har skapat grupper kan du [filtrera instrumentpanelen för Efterlevnadshanteraren](compliance-manager-setup.md#filtering-your-dashboard-view) och visa resultatet efter en eller flera grupper.</span><span class="sxs-lookup"><span data-stu-id="4f705-162">Once you create groups, you can [filter your Compliance Manager dashboard](compliance-manager-setup.md#filtering-your-dashboard-view) to view your score by one or more groups.</span></span>

##### <a name="learn-more"></a><span data-ttu-id="4f705-163">Mer information</span><span class="sxs-lookup"><span data-stu-id="4f705-163">Learn more</span></span>

<span data-ttu-id="4f705-164">[Skapa och hantera utvärderingar i Efterlevnadshanteraren.](compliance-manager-assessments.md)</span><span class="sxs-lookup"><span data-stu-id="4f705-164">[Build and manage assessments in Compliance Manager](compliance-manager-assessments.md).</span></span>

### <a name="templates"></a><span data-ttu-id="4f705-165">Mallar</span><span class="sxs-lookup"><span data-stu-id="4f705-165">Templates</span></span>

<span data-ttu-id="4f705-166">Efterlevnadshanteraren innehåller mallar som hjälper dig att snabbt skapa utvärderingar.</span><span class="sxs-lookup"><span data-stu-id="4f705-166">Compliance Manager provides templates to help you quickly create assessments.</span></span> <span data-ttu-id="4f705-167">Du kan ändra de här mallarna för att skapa en utvärdering som är optimerad för dina behov.</span><span class="sxs-lookup"><span data-stu-id="4f705-167">You can modify these templates to create an assessment optimized for your needs.</span></span> <span data-ttu-id="4f705-168">Du kan också skapa en anpassad bedömning genom att skapa en mall med egna kontroller och åtgärder.</span><span class="sxs-lookup"><span data-stu-id="4f705-168">You can also build a custom assessment by creating a template with your own controls and actions.</span></span> <span data-ttu-id="4f705-169">Du kanske till exempel vill ha en mall som omfattar en intern affärsprocesskontroll eller en regional dataskyddsstandard som inte omfattas av någon av våra färdiga 325 utvärderingsmallar.</span><span class="sxs-lookup"><span data-stu-id="4f705-169">For example, you may want a template to cover an internal business process control, or a regional data protection standard that isn’t covered by one of our 325+ pre-built assessment templates.</span></span>

##### <a name="learn-more"></a><span data-ttu-id="4f705-170">Mer information</span><span class="sxs-lookup"><span data-stu-id="4f705-170">Learn more</span></span>

<span data-ttu-id="4f705-171">[Visa listan över utvärderingsmallar som tillhandahålls av Efterlevnadshanteraren.](compliance-manager-templates-list.md)</span><span class="sxs-lookup"><span data-stu-id="4f705-171">[View the list of assessment templates provided by Compliance Manager](compliance-manager-templates-list.md).</span></span>

<span data-ttu-id="4f705-172">[Få detaljerade instruktioner för att skapa och ändra mallar för utvärderingar.](compliance-manager-templates.md)</span><span class="sxs-lookup"><span data-stu-id="4f705-172">[Get detailed instructions for creating and modifying templates for assessments](compliance-manager-templates.md).</span></span>

### <a name="improvement-actions"></a><span data-ttu-id="4f705-173">Förbättringsåtgärder</span><span class="sxs-lookup"><span data-stu-id="4f705-173">Improvement actions</span></span>

<span data-ttu-id="4f705-174">Förbättringsåtgärder hjälper till att centralisera efterlevnadsaktiviteter.</span><span class="sxs-lookup"><span data-stu-id="4f705-174">Improvement actions help centralize your compliance activities.</span></span> <span data-ttu-id="4f705-175">Varje förbättringsåtgärd ger rekommenderade riktlinjer som är avsedda att hjälpa dig att anpassa till dataskyddsföreskrifter och standarder.</span><span class="sxs-lookup"><span data-stu-id="4f705-175">Each improvement action provides recommended guidance that’s intended to help you align with data protection regulations and standards.</span></span> <span data-ttu-id="4f705-176">Förbättringsåtgärder kan tilldelas till användare i organisationen för att utföra implementerings- och testarbete.</span><span class="sxs-lookup"><span data-stu-id="4f705-176">Improvement actions can be assigned to users in your organization to perform implementation and testing work.</span></span> <span data-ttu-id="4f705-177">Du kan också lagra dokumentation, anteckningar och spela in statusuppdateringar i förbättringsåtgärden.</span><span class="sxs-lookup"><span data-stu-id="4f705-177">You can also store documentation, notes, and record status updates within the improvement action.</span></span>

##### <a name="learn-more"></a><span data-ttu-id="4f705-178">Mer information</span><span class="sxs-lookup"><span data-stu-id="4f705-178">Learn more</span></span>

<span data-ttu-id="4f705-179">[Använd förbättringsåtgärder för att hantera arbetsflödet för efterlevnad.](compliance-manager-improvement-actions.md)</span><span class="sxs-lookup"><span data-stu-id="4f705-179">[Use improvement actions to manage your compliance workflow](compliance-manager-improvement-actions.md).</span></span>

<span data-ttu-id="4f705-180">[Läs om hur åtgärder påverkar ditt efterlevnadsresultat](compliance-score-calculation.md#action-types-and-points).</span><span class="sxs-lookup"><span data-stu-id="4f705-180">[Learn how actions impact your compliance score](compliance-score-calculation.md#action-types-and-points).</span></span>

## <a name="supported-languages"></a><span data-ttu-id="4f705-181">Språk som stöds</span><span class="sxs-lookup"><span data-stu-id="4f705-181">Supported languages</span></span>

<span data-ttu-id="4f705-182">Efterlevnadshanteraren är tillgänglig på följande språk:</span><span class="sxs-lookup"><span data-stu-id="4f705-182">Compliance Manager is available in the following languages:</span></span>

- <span data-ttu-id="4f705-183">Engelska</span><span class="sxs-lookup"><span data-stu-id="4f705-183">English</span></span>
- <span data-ttu-id="4f705-184">Bahasa Indonesian</span><span class="sxs-lookup"><span data-stu-id="4f705-184">Bahasa Indonesian</span></span>
- <span data-ttu-id="4f705-185">Bahasa Malajiska</span><span class="sxs-lookup"><span data-stu-id="4f705-185">Bahasa Malay</span></span>
- <span data-ttu-id="4f705-186">Kinesiska (förenklad)</span><span class="sxs-lookup"><span data-stu-id="4f705-186">Chinese (Simplified)</span></span>
- <span data-ttu-id="4f705-187">Kinesiska (traditionell)</span><span class="sxs-lookup"><span data-stu-id="4f705-187">Chinese (Traditional)</span></span>
- <span data-ttu-id="4f705-188">Czech</span><span class="sxs-lookup"><span data-stu-id="4f705-188">Czech</span></span>
- <span data-ttu-id="4f705-189">Danish</span><span class="sxs-lookup"><span data-stu-id="4f705-189">Danish</span></span>
- <span data-ttu-id="4f705-190">Dutch</span><span class="sxs-lookup"><span data-stu-id="4f705-190">Dutch</span></span>
- <span data-ttu-id="4f705-191">Finnish</span><span class="sxs-lookup"><span data-stu-id="4f705-191">Finnish</span></span>
- <span data-ttu-id="4f705-192">French</span><span class="sxs-lookup"><span data-stu-id="4f705-192">French</span></span>
- <span data-ttu-id="4f705-193">German</span><span class="sxs-lookup"><span data-stu-id="4f705-193">German</span></span>
- <span data-ttu-id="4f705-194">Hebrew</span><span class="sxs-lookup"><span data-stu-id="4f705-194">Hebrew</span></span>
- <span data-ttu-id="4f705-195">Hungarian</span><span class="sxs-lookup"><span data-stu-id="4f705-195">Hungarian</span></span>
- <span data-ttu-id="4f705-196">Italian</span><span class="sxs-lookup"><span data-stu-id="4f705-196">Italian</span></span>
- <span data-ttu-id="4f705-197">Japanska</span><span class="sxs-lookup"><span data-stu-id="4f705-197">Japanese</span></span>
- <span data-ttu-id="4f705-198">Koreanska</span><span class="sxs-lookup"><span data-stu-id="4f705-198">Korean</span></span>
- <span data-ttu-id="4f705-199">Norska</span><span class="sxs-lookup"><span data-stu-id="4f705-199">Norwegian</span></span>
- <span data-ttu-id="4f705-200">Polish</span><span class="sxs-lookup"><span data-stu-id="4f705-200">Polish</span></span>
- <span data-ttu-id="4f705-201">Portugisiska (Brasilien)</span><span class="sxs-lookup"><span data-stu-id="4f705-201">Portuguese (Brazilian)</span></span>
- <span data-ttu-id="4f705-202">Russian</span><span class="sxs-lookup"><span data-stu-id="4f705-202">Russian</span></span>
- <span data-ttu-id="4f705-203">Spanish</span><span class="sxs-lookup"><span data-stu-id="4f705-203">Spanish</span></span>
- <span data-ttu-id="4f705-204">Swedish</span><span class="sxs-lookup"><span data-stu-id="4f705-204">Swedish</span></span>
- <span data-ttu-id="4f705-205">Thai</span><span class="sxs-lookup"><span data-stu-id="4f705-205">Thai</span></span>
- <span data-ttu-id="4f705-206">Turkish</span><span class="sxs-lookup"><span data-stu-id="4f705-206">Turkish</span></span>

## <a name="next-steps-set-up-and-customize"></a><span data-ttu-id="4f705-207">Nästa steg: konfigurera och anpassa</span><span class="sxs-lookup"><span data-stu-id="4f705-207">Next steps: set up and customize</span></span>

<span data-ttu-id="4f705-208">Läs om hur du loggar in, tilldelar behörigheter och roller, konfigurerar inställningar och anpassar instrumentpanelsvyn i [Kom igång med Efterlevnadshanteraren.](compliance-manager-setup.md)</span><span class="sxs-lookup"><span data-stu-id="4f705-208">Learn how to sign in, assign permissions and roles, configure settings, and personalize your dashboard view at [Get started with Compliance Manager](compliance-manager-setup.md).</span></span>

<span data-ttu-id="4f705-209">Börja sedan anpassa Efterlevnadshanteraren så att du kan följa de branschstandarder som är viktigast för din organisation genom [att konfigurera utvärderingar.](compliance-manager-assessments.md)</span><span class="sxs-lookup"><span data-stu-id="4f705-209">Then start customizing Compliance Manager to help you comply with industry standards that matter most to your organization by [setting up assessments](compliance-manager-assessments.md).</span></span>

<span data-ttu-id="4f705-210">För att hjälpa dig att följa regler om datasekretess har vi utformat ett arbetsflöde som vägleder dig genom en end-to-end-process för att planera och implementera funktioner i Microsoft 365, inklusive användning av Efterlevnadshanteraren.</span><span class="sxs-lookup"><span data-stu-id="4f705-210">To help you comply with data privacy regulations, we’ve designed a workflow to guide you through an end-to-end process to plan and implement capabilities across Microsoft 365, including using Compliance Manager.</span></span> <span data-ttu-id="4f705-211">Mer information finns i [Distribuera informationsskydd för föreskrifter för datasekretess med Microsoft 365](../solutions/information-protection-deploy.md) (aka.ms/m365dataprivacy).</span><span class="sxs-lookup"><span data-stu-id="4f705-211">For more information, see [Deploy information protection for data privacy regulations with Microsoft 365](../solutions/information-protection-deploy.md) (aka.ms/m365dataprivacy).</span></span> 