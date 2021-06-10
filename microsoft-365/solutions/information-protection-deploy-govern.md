---
title: Reglera information som omfattas av datasekretess
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
- m365solution-scenario
ms.custom: ''
description: Använd Microsoft 365 och bevarandeprinciper för att hantera personliga data i din Microsoft 365 miljö.
ms.openlocfilehash: 62c2386ac8f9c5b31650df8be2c2a411d8b75959
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928442"
---
# <a name="govern-information-subject-to-data-privacy-regulation"></a><span data-ttu-id="d37f8-103">Reglera information som omfattas av datasekretess</span><span class="sxs-lookup"><span data-stu-id="d37f8-103">Govern information subject to data privacy regulation</span></span>

<span data-ttu-id="d37f8-104">Informationsstyrningskontroller kan användas i din miljö för att tillgodose behov av datasekretessefterlevnad, inklusive ett nummer som är specifikt för Allmän dataskyddsförordning (GDPR), HIPAA-HITECH (United States Health Care Privacy Act), California Consumer Protection Act (CCPA) och Brazil Data Protection Act (LGPD).</span><span class="sxs-lookup"><span data-stu-id="d37f8-104">Information governance controls can be employed in your environment to help address data privacy compliance needs, including a number that are specific to General Data Protection Regulation (GDPR), HIPAA-HITECH (the United States health care privacy act), California Consumer Protection Act (CCPA), and the Brazil Data Protection Act (LGPD).</span></span> 

<span data-ttu-id="d37f8-105">Dessa kontroller faller främst inom följande lösningsområden:</span><span class="sxs-lookup"><span data-stu-id="d37f8-105">These controls primarily fall into the following solution areas:</span></span>

- <span data-ttu-id="d37f8-106">Kvarhållningsprinciper</span><span class="sxs-lookup"><span data-stu-id="d37f8-106">Retention policies</span></span>
- <span data-ttu-id="d37f8-107">Kvarhållningsetiketter</span><span class="sxs-lookup"><span data-stu-id="d37f8-107">Retention labels</span></span>
- <span data-ttu-id="d37f8-108">Hantering av arkivhandlingar</span><span class="sxs-lookup"><span data-stu-id="d37f8-108">Records management</span></span>

## <a name="data-privacy-regulations-impacting-information-governance-controls"></a><span data-ttu-id="d37f8-109">Datasekretessförordningar som påverkar kontroll av informationsstyrning</span><span class="sxs-lookup"><span data-stu-id="d37f8-109">Data privacy regulations impacting information governance controls</span></span>

<span data-ttu-id="d37f8-110">Här är ett exempel på en lista med regler för datasekretess som kan relatera till kontroller för informationsstyrning:</span><span class="sxs-lookup"><span data-stu-id="d37f8-110">Here is a sample listing of data privacy regulations that may relate to information governance controls:</span></span>

- <span data-ttu-id="d37f8-111">GDPR-artikel (13)(2)(a)</span><span class="sxs-lookup"><span data-stu-id="d37f8-111">GDPR Article (13)(2)(a)</span></span>
- <span data-ttu-id="d37f8-112">GDPR-artikel (5)(1)(f)</span><span class="sxs-lookup"><span data-stu-id="d37f8-112">GDPR Article (5)(1)(f)</span></span>
- <span data-ttu-id="d37f8-113">HIPAA-HITECH (45 CFR 164.312(c)(2))</span><span class="sxs-lookup"><span data-stu-id="d37f8-113">HIPAA-HITECH (45 CFR 164.312(c)(2))</span></span>
- <span data-ttu-id="d37f8-114">HIPAA-HITECH (45 CFR 164.316(b)(1)(i))</span><span class="sxs-lookup"><span data-stu-id="d37f8-114">HIPAA-HITECH (45 CFR 164.316(b)(1)(i))</span></span>
- <span data-ttu-id="d37f8-115">HIPAA-HITECH (45 CFR 164.316(b)(1)(ii))</span><span class="sxs-lookup"><span data-stu-id="d37f8-115">HIPAA-HITECH (45 CFR 164.316(b)(1)(ii))</span></span>
- <span data-ttu-id="d37f8-116">LGPD, artikel 46</span><span class="sxs-lookup"><span data-stu-id="d37f8-116">LGPD Article 46</span></span>

<span data-ttu-id="d37f8-117">Mer information om dessa bestämmelser finns i artikeln om att [bedöma datasekretess och identifiera känslig information.](information-protection-deploy-assess.md)</span><span class="sxs-lookup"><span data-stu-id="d37f8-117">For more information on these regulations, see the [assess data privacy risks and identify sensitive information article](information-protection-deploy-assess.md).</span></span>

<span data-ttu-id="d37f8-118">För informationsstyrning anropar datasekretessföreskrifter vanligtvis följande:</span><span class="sxs-lookup"><span data-stu-id="d37f8-118">For information governance, data privacy regulations typically call for the following:</span></span>

- <span data-ttu-id="d37f8-119">Du bör använda ett tekniskt system för lagring och borttagning av personuppgifter som lagras i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d37f8-119">You should employ a technical scheme for retention and deletion for personal data stored in Microsoft 365.</span></span>
- <span data-ttu-id="d37f8-120">Om du kommer att lagra personlig information informerar du ämnet om hur länge data kommer att lagras, vilket är en standardmetod nu på frontend-webbsystem.</span><span class="sxs-lookup"><span data-stu-id="d37f8-120">If you're going to store personal data, inform the subject of how long the data will be stored, which is a standard practice now on front-end web systems.</span></span>
- <span data-ttu-id="d37f8-121">Personuppgifter bör skyddas mot oavsiktlig bearbetning, förlust eller ändring med hjälp av verifierbara metoder.</span><span class="sxs-lookup"><span data-stu-id="d37f8-121">Personal data should be protected against accidental processing, loss, or alteration using verifiable methods.</span></span>
- <span data-ttu-id="d37f8-122">Alla åtgärder som utförs mot personuppgifter ska dokumenteras och att dokumentationen ska behållas under en viss tidsperiod.</span><span class="sxs-lookup"><span data-stu-id="d37f8-122">Any action executed against personal data should be documented and that documentation should be retained for a specified period.</span></span>

<span data-ttu-id="d37f8-123">Eftersom bestämmelser om datasekretess inte är särskilt specifika när det gäller lagring och borttagning av data måste andra faktorer beaktas som kan diktera riktlinjer för informationsstyrning för personlig information som lagras i Microsoft 365-prenumerationen.</span><span class="sxs-lookup"><span data-stu-id="d37f8-123">Because the data privacy regulations are not very specific when it comes to data retention and deletion, other factors need to be taken into consideration that may dictate information governance guidelines for personal information stored in your Microsoft 365 subscription.</span></span> <span data-ttu-id="d37f8-124">Här är några exempel:</span><span class="sxs-lookup"><span data-stu-id="d37f8-124">Here are a few examples:</span></span>

- <span data-ttu-id="d37f8-125">Föråldring av konsumentkonton efter 5 års inaktivitet och kräver borttagning eller anonymisering av kontodata efter den tidpunkten, vilket kräver att data och arbetsflöden som är relaterade till meddelanden och annan automation behöver fördelas mellan systemet.</span><span class="sxs-lookup"><span data-stu-id="d37f8-125">Aging out consumer accounts after 5 years of inactivity and requires deletion or anonymization of account data after that point, requiring orchestration between the system storing the data and workflows related to notifications and other automation.</span></span>
- <span data-ttu-id="d37f8-126">Konfigurera regler för att behålla principer och procedurer relaterade till GDPR i tre år efter att de har ersatts, vilket överensstämmer med organisationens kvarhållningsschema för principer och procedurer.</span><span class="sxs-lookup"><span data-stu-id="d37f8-126">Configuring rules for keeping policies and procedures related to GDPR around for three years after they've been superseded, which aligns with the organization's retention schedule for policies and procedures.</span></span>
- <span data-ttu-id="d37f8-127">Ett separat abonnemang för kommunikation med konsumenter via supportorganisationen.</span><span class="sxs-lookup"><span data-stu-id="d37f8-127">Maintaining a separate subscription for communicating with consumers through its support organization.</span></span> <span data-ttu-id="d37f8-128">All e-postkommunikation behålls och raderas efter två veckor för att minska eventuella problem med att skapa sekretess i systemet.</span><span class="sxs-lookup"><span data-stu-id="d37f8-128">All email communications were retained and deleted after two weeks to reduce any privacy debt buildup in the system.</span></span>

<span data-ttu-id="d37f8-129">En viktig fråga att besvara är:</span><span class="sxs-lookup"><span data-stu-id="d37f8-129">A key question to answer is:</span></span> 

- <span data-ttu-id="d37f8-130">Hur länge måste information som innehåller personuppgifter sparas av giltiga affärsorsaker för att undvika att använda det för alltid?</span><span class="sxs-lookup"><span data-stu-id="d37f8-130">How long does information containing personal data need to be kept around for valid business reasons to avoid "keep it forever" practices?</span></span> <span data-ttu-id="d37f8-131">Det måste balanseras med bevarandebehov för affärskontinualitet.</span><span class="sxs-lookup"><span data-stu-id="d37f8-131">This must be balanced with retention needs for business continuity.</span></span>

<span data-ttu-id="d37f8-132">Oavsett juridiska skäl och affärsorsaker till att ha personlig information runt om eller ta bort den tillhandahåller Microsoft ett antal funktioner för att implementera ditt datastyrningsschema i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d37f8-132">Regardless of the legal and business reasons for keeping personal information around or deleting it, Microsoft provides a number of capabilities to implement your data governance scheme in Microsoft 365.</span></span>

## <a name="managing-information-governance-in-microsoft-365"></a><span data-ttu-id="d37f8-133">Hantera informationsstyrning i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d37f8-133">Managing information governance in Microsoft 365</span></span>

<span data-ttu-id="d37f8-134">Börja med att gå [till Hantera informationsstyrning](../compliance/manage-information-governance.md) [och datalagring, borttagning och bevarande i Microsoft 365.](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)</span><span class="sxs-lookup"><span data-stu-id="d37f8-134">To begin, see [Manage information governance](../compliance/manage-information-governance.md) and [Data Retention, Deletion and Destruction in Microsoft 365](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).</span></span>

### <a name="develop-data-retention-schedules-for-containers-email-and-content"></a><span data-ttu-id="d37f8-135">Utveckla datalagringsscheman för behållare, e-post och innehåll</span><span class="sxs-lookup"><span data-stu-id="d37f8-135">Develop data retention schedules for containers, email, and content</span></span>

<span data-ttu-id="d37f8-136">Tänk på följande:</span><span class="sxs-lookup"><span data-stu-id="d37f8-136">Keep the following in mind:</span></span>

- <span data-ttu-id="d37f8-137">Att upprätta ett datalagringsschema för definierade informationstyper bör vara en förutsättning för att implementera ett bevarande- eller borttagningsschema.</span><span class="sxs-lookup"><span data-stu-id="d37f8-137">Establishing a data retention schedule for defined information types should be considered a prerequisite to implementing any retention or deletion scheme.</span></span>

- <span data-ttu-id="d37f8-138">Med hänsyn till antalet informationstyper som de flesta organisationer anser vara viktiga och de motsvarande stora arkiveringsscheman som följer med dem, måste du planera för att implementera en strategi för datalagring och hantering av arkivhandlingar.</span><span class="sxs-lookup"><span data-stu-id="d37f8-138">Given the number of information types that most organizations consider important and the corresponding large records retention schedules that go along with them, implementing a data retention and records management strategy requires planning.</span></span> 

- <span data-ttu-id="d37f8-139">Nyckeln till att upprätta en effektiv datastyrningsstrategi av den här typen är att fokusera på de affärsfunktioner och informationstyper med högsta prioritet som kräver mer formell hantering.</span><span class="sxs-lookup"><span data-stu-id="d37f8-139">The key to establishing an effective data governance strategy of this type is to focus on the highest priority business functions and information types that require more formal management.</span></span> <span data-ttu-id="d37f8-140">Några exempel är juridiska kontrakt, ekonomiska rapporter och dokumentation om regelefterlevnad.</span><span class="sxs-lookup"><span data-stu-id="d37f8-140">Examples are legal contracts, financial statements, and regulatory compliance documentation.</span></span> <span data-ttu-id="d37f8-141">Försök att undvika ett separat kvarhållningsschema för varje enskild informationstyp.</span><span class="sxs-lookup"><span data-stu-id="d37f8-141">Try to avoid having a separate retention schedule for every single information type.</span></span> <span data-ttu-id="d37f8-142">Försök att använda allmänna kategorier så mycket som möjligt, till exempel med kvarhållningsscheman på 7 år för allmänt affärsinnehåll.</span><span class="sxs-lookup"><span data-stu-id="d37f8-142">Try to utilize general categories as much as possible, for example, with retention schedules of 7 years for general business content.</span></span>

- <span data-ttu-id="d37f8-143">När typerna av personlig information i din miljö är mer kända bör du upprätta scheman för bevarande och borttagning för den här typen av innehåll och justera informationsarkitekturen för att göra styrning av den här typen av information enklare.</span><span class="sxs-lookup"><span data-stu-id="d37f8-143">Once the personal information types in your environment are better known, establish retention and deletion schedules for this type of content and adjust your information architecture to make governance of this sort of information easier.</span></span> <span data-ttu-id="d37f8-144">Isolera till exempel personlig information på separata webbplatser, i bibliotek eller i mappar med kontrollerad åtkomst.</span><span class="sxs-lookup"><span data-stu-id="d37f8-144">For example, isolate personal information in separate sites, libraries, or folders with controlled access.</span></span>

### <a name="retention-policies-and-retention-labels"></a><span data-ttu-id="d37f8-145">Kvarhållningsprinciper och -etiketter</span><span class="sxs-lookup"><span data-stu-id="d37f8-145">Retention policies and retention labels</span></span>

<span data-ttu-id="d37f8-146">Använd [bevarandeprinciper och bevarandeetiketter](../compliance/retention.md) för att behålla eller ta bort Microsoft 365 innehåll som innehåller eller förväntas innehålla personuppgifter.</span><span class="sxs-lookup"><span data-stu-id="d37f8-146">Use [retention policies and retention labels](../compliance/retention.md) to retain or delete content in Microsoft 365 that contains or is expected to contain personal data.</span></span>

### <a name="records-management"></a><span data-ttu-id="d37f8-147">Hantering av arkivhandlingar</span><span class="sxs-lookup"><span data-stu-id="d37f8-147">Records management</span></span>

<span data-ttu-id="d37f8-148">Använd bevarandeetiketter som deklarerar innehåll för en arkivering för att implementera en lösning [för hantering](../compliance/records-management.md) av arkivhandlingar för data i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d37f8-148">Use retention labels that declare content a record to implement a [records management solution](../compliance/records-management.md) for data in Microsoft 365.</span></span>

<span data-ttu-id="d37f8-149">För datasekretess deklareras de DSR-förfrågningar som tas emot av den juridiska avdelningen och kan lagras på obestämd tid eller kasseras med bevis, för att följa bevarandespecifikationer för regelaktivitet.</span><span class="sxs-lookup"><span data-stu-id="d37f8-149">For data privacy, data subject requests (DSRs) received by the legal department are declared a record and can be stored indefinitely or disposed of with proof, to adhere to regulatory activity retention specifications.</span></span>