---
title: Reglera information som omfattas av dataskyddsförordningen
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
ms.custom: ''
description: Använd Microsoft 365-lagringsetiketter och policyer för att hantera personuppgifter i microsoft 365-miljön.
ms.openlocfilehash: a7a0d6e00d29d80dfd0cb72ba217177aa6029a2c
ms.sourcegitcommit: 0f71042edc7c3a7f10a7b92e1943abf51532cbf5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/29/2020
ms.locfileid: "46522307"
---
# <a name="govern-information-subject-to-data-privacy-regulation"></a><span data-ttu-id="99aef-103">Reglera information som omfattas av dataskyddsförordningen</span><span class="sxs-lookup"><span data-stu-id="99aef-103">Govern information subject to data privacy regulation</span></span>

<span data-ttu-id="99aef-104">Kontroller för informationsstyrning kan användas i din miljö för att hjälpa till att tillgodose behoven av efterlevnad av datasekretess, inklusive ett nummer som är specifikt för General Data Protection Regulation (GDPR), HIPAA-HITECH (United States health care privacy act), California Consumer Protection Act (CCPA) och Brazil Data Protection Act (LGPD).</span><span class="sxs-lookup"><span data-stu-id="99aef-104">Information governance controls can be employed in your environment to help address data privacy compliance needs, including a number that are specific to General Data Protection Regulation (GDPR), HIPAA-HITECH (the United States health care privacy act), California Consumer Protection Act (CCPA), and the Brazil Data Protection Act (LGPD).</span></span> 

<span data-ttu-id="99aef-105">Dessa kontroller faller främst in i följande lösningsområden:</span><span class="sxs-lookup"><span data-stu-id="99aef-105">These controls primarily fall into the following solution areas:</span></span>

- <span data-ttu-id="99aef-106">Kvarhållningsprinciper</span><span class="sxs-lookup"><span data-stu-id="99aef-106">Retention policies</span></span>
- <span data-ttu-id="99aef-107">Kvarhållningsetiketter</span><span class="sxs-lookup"><span data-stu-id="99aef-107">Retention labels</span></span>
- <span data-ttu-id="99aef-108">Hantering av arkivhandlingar</span><span class="sxs-lookup"><span data-stu-id="99aef-108">Records management</span></span>

## <a name="data-privacy-regulations-impacting-information-governance-controls"></a><span data-ttu-id="99aef-109">Regler för datasekretess som påverkar kontroller för informationsstyrning</span><span class="sxs-lookup"><span data-stu-id="99aef-109">Data privacy regulations impacting information governance controls</span></span>

<span data-ttu-id="99aef-110">Här är ett exempel på datasekretessregler som kan relatera till informationsstyrningskontroller:</span><span class="sxs-lookup"><span data-stu-id="99aef-110">Here is a sample listing of data privacy regulations that may relate to information governance controls:</span></span>

- <span data-ttu-id="99aef-111">GDPR Artikel 13.2 a</span><span class="sxs-lookup"><span data-stu-id="99aef-111">GDPR Article (13)(2)(a)</span></span>
- <span data-ttu-id="99aef-112">GDPR Artikel 5.1 f</span><span class="sxs-lookup"><span data-stu-id="99aef-112">GDPR Article (5)(1)(f)</span></span>
- <span data-ttu-id="99aef-113">HIPAA-HITECH (45 CFR 164.312(c)(2))</span><span class="sxs-lookup"><span data-stu-id="99aef-113">HIPAA-HITECH (45 CFR 164.312(c)(2))</span></span>
- <span data-ttu-id="99aef-114">HIPAA-HITECH (45 CFR 164.316 b(1)(i))</span><span class="sxs-lookup"><span data-stu-id="99aef-114">HIPAA-HITECH (45 CFR 164.316(b)(1)(i))</span></span>
- <span data-ttu-id="99aef-115">HIPAA-HITECH (45 CFR 164.316 b.1)(ii))</span><span class="sxs-lookup"><span data-stu-id="99aef-115">HIPAA-HITECH (45 CFR 164.316(b)(1)(ii))</span></span>
- <span data-ttu-id="99aef-116">LGPD Artikel 46</span><span class="sxs-lookup"><span data-stu-id="99aef-116">LGPD Article 46</span></span>

<span data-ttu-id="99aef-117">Mer information om dessa föreskrifter finns i [artikeln för att bedöma datasekretessen och identifiera en artikel om känslig information](information-protection-deploy-assess.md).</span><span class="sxs-lookup"><span data-stu-id="99aef-117">For more information on these regulations, see the [assess data privacy risks and identify sensitive information article](information-protection-deploy-assess.md).</span></span>

<span data-ttu-id="99aef-118">För informationsstyrning kräver datasekretessregler vanligtvis följande:</span><span class="sxs-lookup"><span data-stu-id="99aef-118">For information governance, data privacy regulations typically call for the following:</span></span>

- <span data-ttu-id="99aef-119">Du bör använda ett tekniskt schema för lagring och radering av personuppgifter som lagras i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="99aef-119">You should employ a technical scheme for retention and deletion for personal data stored in Microsoft 365.</span></span>
- <span data-ttu-id="99aef-120">Om du ska lagra personuppgifter, informera ämnet om hur länge uppgifterna kommer att lagras, vilket är en vanlig praxis nu på frontend webbsystem.</span><span class="sxs-lookup"><span data-stu-id="99aef-120">If you're going to store personal data, inform the subject of how long the data will be stored, which is a standard practice now on front-end web systems.</span></span>
- <span data-ttu-id="99aef-121">Personuppgifter bör skyddas mot oavsiktlig behandling, förlust eller ändring med hjälp av kontrollerbara metoder.</span><span class="sxs-lookup"><span data-stu-id="99aef-121">Personal data should be protected against accidental processing, loss, or alteration using verifiable methods.</span></span>
- <span data-ttu-id="99aef-122">Alla åtgärder som utförs mot personuppgifter bör dokumenteras och denna dokumentation bör behållas under en viss period.</span><span class="sxs-lookup"><span data-stu-id="99aef-122">Any action executed against personal data should be documented and that documentation should be retained for a specified period.</span></span>

<span data-ttu-id="99aef-123">Eftersom reglerna för datasekretess inte är särskilt specifika när det gäller lagring och radering av data måste andra faktorer beaktas som kan diktera riktlinjer för informationsstyrning för personlig information som lagras i din Microsoft 365-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="99aef-123">Because the data privacy regulations are not very specific when it comes to data retention and deletion, other factors need to be taken into consideration that may dictate information governance guidelines for personal information stored in your Microsoft 365 subscription.</span></span> <span data-ttu-id="99aef-124">Här är några exempel:</span><span class="sxs-lookup"><span data-stu-id="99aef-124">Here are a few examples:</span></span>

- <span data-ttu-id="99aef-125">Åldrande ut konsumentkonton efter 5 års inaktivitet och kräver radering eller anonymisering av kontodata efter den punkten, vilket kräver orkestrering mellan systemet som lagrar data och arbetsflöden relaterade till meddelanden och annan automatisering.</span><span class="sxs-lookup"><span data-stu-id="99aef-125">Aging out consumer accounts after 5 years of inactivity and requires deletion or anonymization of account data after that point, requiring orchestration between the system storing the data and workflows related to notifications and other automation.</span></span>
- <span data-ttu-id="99aef-126">Konfigurera regler för att hålla principer och procedurer relaterade till GDPR runt i tre år efter att de har ersatts, vilket överensstämmer med organisationens bevarandeschema för principer och procedurer.</span><span class="sxs-lookup"><span data-stu-id="99aef-126">Configuring rules for keeping policies and procedures related to GDPR around for three years after they've been superseded, which aligns with the organization's retention schedule for policies and procedures.</span></span>
- <span data-ttu-id="99aef-127">Upprätthålla en separat prenumeration för att kommunicera med konsumenter genom sin supportorganisation.</span><span class="sxs-lookup"><span data-stu-id="99aef-127">Maintaining a separate subscription for communicating with consumers through its support organization.</span></span> <span data-ttu-id="99aef-128">All e-postkommunikation behölls och raderades efter två veckor för att minska eventuella integritetsskulder i systemet.</span><span class="sxs-lookup"><span data-stu-id="99aef-128">All email communications were retained and deleted after two weeks to reduce any privacy debt buildup in the system.</span></span>

<span data-ttu-id="99aef-129">En viktig fråga att besvara är:</span><span class="sxs-lookup"><span data-stu-id="99aef-129">A key question to answer is:</span></span> 

- <span data-ttu-id="99aef-130">Hur länge behöver information som innehåller personuppgifter bevaras av giltiga affärsskäl för att undvika "keep it forever"-metoder?</span><span class="sxs-lookup"><span data-stu-id="99aef-130">How long does information containing personal data need to be kept around for valid business reasons to avoid "keep it forever" practices?</span></span> <span data-ttu-id="99aef-131">Detta måste balanseras med bevarandebehov för kontinuitet i verksamheten.</span><span class="sxs-lookup"><span data-stu-id="99aef-131">This must be balanced with retention needs for business continuity.</span></span>

<span data-ttu-id="99aef-132">Oavsett de juridiska och affärsmässiga skälen för att hålla personlig information runt eller ta bort den, tillhandahåller Microsoft ett antal funktioner för att implementera ditt datastyrningssystem i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="99aef-132">Regardless of the legal and business reasons for keeping personal information around or deleting it, Microsoft provides a number of capabilities to implement your data governance scheme in Microsoft 365.</span></span>

## <a name="managing-information-governance-in-microsoft-365"></a><span data-ttu-id="99aef-133">Hantera informationsstyrning i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="99aef-133">Managing information governance in Microsoft 365</span></span>

<span data-ttu-id="99aef-134">Börja med att se [Hantera informationsstyrning](../compliance/manage-information-governance.md) och [datalagring, borttagning och destruktion i Microsoft 365](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).</span><span class="sxs-lookup"><span data-stu-id="99aef-134">To begin, see [Manage information governance](../compliance/manage-information-governance.md) and [Data Retention, Deletion and Destruction in Microsoft 365](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).</span></span>

### <a name="develop-data-retention-schedules-for-containers-email-and-content"></a><span data-ttu-id="99aef-135">Utveckla datalagringsscheman för behållare, e-post och innehåll</span><span class="sxs-lookup"><span data-stu-id="99aef-135">Develop data retention schedules for containers, email, and content</span></span>

<span data-ttu-id="99aef-136">Tänk på följande:</span><span class="sxs-lookup"><span data-stu-id="99aef-136">Keep the following in mind:</span></span>

- <span data-ttu-id="99aef-137">Upprättande av en datalagringsplan för definierade informationstyper bör betraktas som en förutsättning för att genomföra ett lagrings- eller raderingsschema.</span><span class="sxs-lookup"><span data-stu-id="99aef-137">Establishing a data retention schedule for defined information types should be considered a prerequisite to implementing any retention or deletion scheme.</span></span>

- <span data-ttu-id="99aef-138">Med tanke på antalet informationstyper som de flesta organisationer anser vara viktiga och motsvarande stora lagringsscheman för stora poster som följer med dem, kräver implementering av en strategi för datalagring och datahantering planering.</span><span class="sxs-lookup"><span data-stu-id="99aef-138">Given the number of information types that most organizations consider important and the corresponding large records retention schedules that go along with them, implementing a data retention and records management strategy requires planning.</span></span> 

- <span data-ttu-id="99aef-139">Nyckeln till att upprätta en effektiv strategi för datastyrning av den här typen är att fokusera på de högsta prioriterade affärsfunktioner och informationstyper som kräver mer formell hantering.</span><span class="sxs-lookup"><span data-stu-id="99aef-139">The key to establishing an effective data governance strategy of this type is to focus on the highest priority business functions and information types that require more formal management.</span></span> <span data-ttu-id="99aef-140">Exempel är juridiska kontrakt, bokslut och dokumentation om regelefterlevnad.</span><span class="sxs-lookup"><span data-stu-id="99aef-140">Examples are legal contracts, financial statements, and regulatory compliance documentation.</span></span> <span data-ttu-id="99aef-141">Försök att undvika att ha ett separat kvarhållningsschema för varje enskild informationstyp.</span><span class="sxs-lookup"><span data-stu-id="99aef-141">Try to avoid having a separate retention schedule for every single information type.</span></span> <span data-ttu-id="99aef-142">Försök att använda allmänna kategorier så mycket som möjligt, till exempel med kvarhållningsscheman på 7 år för allmänt affärsinnehåll.</span><span class="sxs-lookup"><span data-stu-id="99aef-142">Try to utilize general categories as much as possible, for example, with retention schedules of 7 years for general business content.</span></span>

- <span data-ttu-id="99aef-143">När de personliga informationstyperna i din miljö är mer kända, upprätta kvarhållnings- och borttagningsscheman för den här typen av innehåll och justera din informationsarkitektur för att göra styrningen av den här typen av information enklare.</span><span class="sxs-lookup"><span data-stu-id="99aef-143">Once the personal information types in your environment are better known, establish retention and deletion schedules for this type of content and adjust your information architecture to make governance of this sort of information easier.</span></span> <span data-ttu-id="99aef-144">Isolera till exempel personlig information på separata platser, bibliotek eller mappar med kontrollerad åtkomst.</span><span class="sxs-lookup"><span data-stu-id="99aef-144">For example, isolate personal information in separate sites, libraries, or folders with controlled access.</span></span>

### <a name="retention-policies"></a><span data-ttu-id="99aef-145">Kvarhållningsprinciper</span><span class="sxs-lookup"><span data-stu-id="99aef-145">Retention policies</span></span>

<span data-ttu-id="99aef-146">Skapa och distribuera [bevarandeprinciper](../compliance/retention-policies.md) för innehåll på webbplatser som tillämpas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="99aef-146">Create and deploy [retention policies](../compliance/retention-policies.md) for content in sites that are automatically applied.</span></span>

<span data-ttu-id="99aef-147">För datasekretess för webbplatser som innehåller eller förväntas innehålla personuppgifter anger du lagrings- eller raderingsregler för att hantera organisationsstandarder.</span><span class="sxs-lookup"><span data-stu-id="99aef-147">For data privacy for sites that contain or are expected to contain personal data, specify retention or deletion rules to address organizational standards.</span></span>

### <a name="retention-labels"></a><span data-ttu-id="99aef-148">Kvarhållningsetiketter</span><span class="sxs-lookup"><span data-stu-id="99aef-148">Retention labels</span></span>

<span data-ttu-id="99aef-149">Skapa och distribuera [kvarhållningsetiketter](../compliance/labels.md) för innehåll och e-post.</span><span class="sxs-lookup"><span data-stu-id="99aef-149">Create and deploy [retention labels](../compliance/labels.md) for content and email.</span></span>

<span data-ttu-id="99aef-150">För datasekretess för webbplatser, bibliotek, mappar och e-post som innehåller eller förväntas innehålla personuppgifter anger du regler för automatisk lagring eller radering för att hantera organisationsstandarder.</span><span class="sxs-lookup"><span data-stu-id="99aef-150">For data privacy for sites, libraries, folders, and email that contain or are expected to contain personal data, specify auto retention or deletion rules to address organizational standards.</span></span>

### <a name="records-management"></a><span data-ttu-id="99aef-151">Hantering av arkivhandlingar</span><span class="sxs-lookup"><span data-stu-id="99aef-151">Records management</span></span>

<span data-ttu-id="99aef-152">Skapa och distribuera kvarhållningsetiketter för arkivhantering baserat på ett schema för bevarande av poster och filplan.</span><span class="sxs-lookup"><span data-stu-id="99aef-152">Create and deploy retention labels for records management based on a records retention schedule and file plan.</span></span>

<span data-ttu-id="99aef-153">För datasekretess, registrerade förfrågningar (DSRs) emot av den juridiska avdelningen förklaras en post och lagras på obestämd tid för att följa regulatoriska specifikationer aktivitet lagring.</span><span class="sxs-lookup"><span data-stu-id="99aef-153">For data privacy, data subject requests (DSRs) received by the legal department are declared a record and stored indefinitely to adhere to regulatory activity retention specifications.</span></span>

<span data-ttu-id="99aef-154">Mer information finns i de här resurserna:</span><span class="sxs-lookup"><span data-stu-id="99aef-154">See these resources for more information:</span></span> 

- [<span data-ttu-id="99aef-155">Hantering av arkivhandlingar</span><span class="sxs-lookup"><span data-stu-id="99aef-155">Records Management</span></span>](../compliance/records-management.md)
- [<span data-ttu-id="99aef-156">Filplanshanterare</span><span class="sxs-lookup"><span data-stu-id="99aef-156">File plan manager</span></span>](../compliance/file-plan-manager.md)
- [<span data-ttu-id="99aef-157">Händelsebaserad kvarhållning för registerhantering</span><span class="sxs-lookup"><span data-stu-id="99aef-157">Event-based retention for records management</span></span>](../compliance/automate-event-driven-retention.md)
- [<span data-ttu-id="99aef-158">Disposition av innehåll</span><span class="sxs-lookup"><span data-stu-id="99aef-158">Disposition of content</span></span>](../compliance/disposition-reviews.md)
