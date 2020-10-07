---
title: Reglerar informationen som lyder under data integritets förordning
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
description: Använd Microsoft 365 bevarande etiketter och principer för att hantera person uppgifter i din Microsoft 365-miljö.
ms.openlocfilehash: c2a933e556213ae4b78db9dc5f903885df969b27
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377051"
---
# <a name="govern-information-subject-to-data-privacy-regulation"></a><span data-ttu-id="f66a1-103">Reglerar informationen som lyder under data integritets förordning</span><span class="sxs-lookup"><span data-stu-id="f66a1-103">Govern information subject to data privacy regulation</span></span>

<span data-ttu-id="f66a1-104">Du kan använda informations styrning i din miljö för att hjälpa dig att adressera data integritets behovet, inklusive ett nummer som är specifikt för allmänt om allmänna data skydds regler (GDPR), HIPAA-HITECH (Health värna om sjukvård), California konsument skydd Act (CCPA) och Brasilien Data Protection Act (LGPD).</span><span class="sxs-lookup"><span data-stu-id="f66a1-104">Information governance controls can be employed in your environment to help address data privacy compliance needs, including a number that are specific to General Data Protection Regulation (GDPR), HIPAA-HITECH (the United States health care privacy act), California Consumer Protection Act (CCPA), and the Brazil Data Protection Act (LGPD).</span></span> 

<span data-ttu-id="f66a1-105">Dessa kontroller är främst i följande lösnings områden:</span><span class="sxs-lookup"><span data-stu-id="f66a1-105">These controls primarily fall into the following solution areas:</span></span>

- <span data-ttu-id="f66a1-106">Kvarhållningsprinciper</span><span class="sxs-lookup"><span data-stu-id="f66a1-106">Retention policies</span></span>
- <span data-ttu-id="f66a1-107">Kvarhållningsetiketter</span><span class="sxs-lookup"><span data-stu-id="f66a1-107">Retention labels</span></span>
- <span data-ttu-id="f66a1-108">Hantering av arkivhandlingar</span><span class="sxs-lookup"><span data-stu-id="f66a1-108">Records management</span></span>

## <a name="data-privacy-regulations-impacting-information-governance-controls"></a><span data-ttu-id="f66a1-109">Data integritets regler som påverkar informations styrnings kontroller</span><span class="sxs-lookup"><span data-stu-id="f66a1-109">Data privacy regulations impacting information governance controls</span></span>

<span data-ttu-id="f66a1-110">Här är ett exempel på en lista över data integritets regler som kan gälla för informations styrnings kontroller:</span><span class="sxs-lookup"><span data-stu-id="f66a1-110">Here is a sample listing of data privacy regulations that may relate to information governance controls:</span></span>

- <span data-ttu-id="f66a1-111">GDPR-artikel (13) (2) (a)</span><span class="sxs-lookup"><span data-stu-id="f66a1-111">GDPR Article (13)(2)(a)</span></span>
- <span data-ttu-id="f66a1-112">GDPR-artikel (5) (1) (f)</span><span class="sxs-lookup"><span data-stu-id="f66a1-112">GDPR Article (5)(1)(f)</span></span>
- <span data-ttu-id="f66a1-113">HIPAA-HITECH (45 CFR 164.312 (c) (2))</span><span class="sxs-lookup"><span data-stu-id="f66a1-113">HIPAA-HITECH (45 CFR 164.312(c)(2))</span></span>
- <span data-ttu-id="f66a1-114">HIPAA-HITECH (45 CFR 164.316 (b) (1) (i))</span><span class="sxs-lookup"><span data-stu-id="f66a1-114">HIPAA-HITECH (45 CFR 164.316(b)(1)(i))</span></span>
- <span data-ttu-id="f66a1-115">HIPAA-HITECH (45 CFR 164.316 (b) (1) (II))</span><span class="sxs-lookup"><span data-stu-id="f66a1-115">HIPAA-HITECH (45 CFR 164.316(b)(1)(ii))</span></span>
- <span data-ttu-id="f66a1-116">LGPD artikel 46</span><span class="sxs-lookup"><span data-stu-id="f66a1-116">LGPD Article 46</span></span>

<span data-ttu-id="f66a1-117">Mer information om dessa regler finns i [bedöma riskerna för data integritet och identifiera känslig information](information-protection-deploy-assess.md).</span><span class="sxs-lookup"><span data-stu-id="f66a1-117">For more information on these regulations, see the [assess data privacy risks and identify sensitive information article](information-protection-deploy-assess.md).</span></span>

<span data-ttu-id="f66a1-118">För informations hantering kan data integritets reglerna normalt ringa till följande:</span><span class="sxs-lookup"><span data-stu-id="f66a1-118">For information governance, data privacy regulations typically call for the following:</span></span>

- <span data-ttu-id="f66a1-119">Du bör använda en teknisk stödordning för bevarande och borttagning av person uppgifter som lagras i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f66a1-119">You should employ a technical scheme for retention and deletion for personal data stored in Microsoft 365.</span></span>
- <span data-ttu-id="f66a1-120">Om du ska lagra person uppgifter kan du informera om hur länge informationen lagras, vilket är en standard övning nu på front webb system.</span><span class="sxs-lookup"><span data-stu-id="f66a1-120">If you're going to store personal data, inform the subject of how long the data will be stored, which is a standard practice now on front-end web systems.</span></span>
- <span data-ttu-id="f66a1-121">Person uppgifter bör skyddas mot oavsiktlig behandling, förlust eller ändring med kontrollerbara metoder.</span><span class="sxs-lookup"><span data-stu-id="f66a1-121">Personal data should be protected against accidental processing, loss, or alteration using verifiable methods.</span></span>
- <span data-ttu-id="f66a1-122">Alla åtgärder som utförs mot person uppgifter bör dokumenteras och dokumentationen bör bevaras under en viss tid.</span><span class="sxs-lookup"><span data-stu-id="f66a1-122">Any action executed against personal data should be documented and that documentation should be retained for a specified period.</span></span>

<span data-ttu-id="f66a1-123">Eftersom reglerna för data integritet inte är särskilt specifika när det gäller data lagring och borttagning måste andra faktorer beaktas som kan diktera informations styrnings rikt linjer för person uppgifter som lagras i Microsoft 365-prenumerationen.</span><span class="sxs-lookup"><span data-stu-id="f66a1-123">Because the data privacy regulations are not very specific when it comes to data retention and deletion, other factors need to be taken into consideration that may dictate information governance guidelines for personal information stored in your Microsoft 365 subscription.</span></span> <span data-ttu-id="f66a1-124">Här följer några exempel:</span><span class="sxs-lookup"><span data-stu-id="f66a1-124">Here are a few examples:</span></span>

- <span data-ttu-id="f66a1-125">Åldrande av konsument konton efter fem års inaktivitet och borttagnings-eller anonymisering av konto data efter den punkten, som kräver dirigering mellan systemet som lagrar data och arbets flöden relaterade till meddelanden och annan automatisering.</span><span class="sxs-lookup"><span data-stu-id="f66a1-125">Aging out consumer accounts after 5 years of inactivity and requires deletion or anonymization of account data after that point, requiring orchestration between the system storing the data and workflows related to notifications and other automation.</span></span>
- <span data-ttu-id="f66a1-126">Konfigurera regler för att behålla principer och procedurer relaterade till GDPR i tre år efter det att de har ersatts, som justeras efter organisationens bevarande schema för principer och procedurer.</span><span class="sxs-lookup"><span data-stu-id="f66a1-126">Configuring rules for keeping policies and procedures related to GDPR around for three years after they've been superseded, which aligns with the organization's retention schedule for policies and procedures.</span></span>
- <span data-ttu-id="f66a1-127">Upprätthålla ett separat abonnemang för kommunikation med konsumenter via dess support organisation.</span><span class="sxs-lookup"><span data-stu-id="f66a1-127">Maintaining a separate subscription for communicating with consumers through its support organization.</span></span> <span data-ttu-id="f66a1-128">All e-postkommunikation behålls och togs bort efter två veckor för att minska eventuell sekretess skuld buildup i systemet.</span><span class="sxs-lookup"><span data-stu-id="f66a1-128">All email communications were retained and deleted after two weeks to reduce any privacy debt buildup in the system.</span></span>

<span data-ttu-id="f66a1-129">En viktig fråga är:</span><span class="sxs-lookup"><span data-stu-id="f66a1-129">A key question to answer is:</span></span> 

- <span data-ttu-id="f66a1-130">Hur länge ska information som innehåller person uppgifter behöva behållas i ett giltigt företags skäl för att undvika "Behåll det för alltid".</span><span class="sxs-lookup"><span data-stu-id="f66a1-130">How long does information containing personal data need to be kept around for valid business reasons to avoid "keep it forever" practices?</span></span> <span data-ttu-id="f66a1-131">Detta måste bal anse ras för att behålla behovet av affärs kontinuitet.</span><span class="sxs-lookup"><span data-stu-id="f66a1-131">This must be balanced with retention needs for business continuity.</span></span>

<span data-ttu-id="f66a1-132">Oberoende av juridiska och affärsmässiga skäl för att hålla person uppgifter eller ta bort den, erbjuder Microsoft ett antal funktioner för att implementera ditt data styrnings schema i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f66a1-132">Regardless of the legal and business reasons for keeping personal information around or deleting it, Microsoft provides a number of capabilities to implement your data governance scheme in Microsoft 365.</span></span>

## <a name="managing-information-governance-in-microsoft-365"></a><span data-ttu-id="f66a1-133">Hantera informations styrning i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f66a1-133">Managing information governance in Microsoft 365</span></span>

<span data-ttu-id="f66a1-134">För att börja läser du [Hantera informations styrning](../compliance/manage-information-governance.md) och [data lagring, borttagning och förstörelse i Microsoft 365](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).</span><span class="sxs-lookup"><span data-stu-id="f66a1-134">To begin, see [Manage information governance](../compliance/manage-information-governance.md) and [Data Retention, Deletion and Destruction in Microsoft 365](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).</span></span>

### <a name="develop-data-retention-schedules-for-containers-email-and-content"></a><span data-ttu-id="f66a1-135">Utveckla data lagrings scheman för behållare, e-post och innehåll</span><span class="sxs-lookup"><span data-stu-id="f66a1-135">Develop data retention schedules for containers, email, and content</span></span>

<span data-ttu-id="f66a1-136">Tänk på följande:</span><span class="sxs-lookup"><span data-stu-id="f66a1-136">Keep the following in mind:</span></span>

- <span data-ttu-id="f66a1-137">Att skapa ett schema för data lagring för definierade informations typer bör anses vara en förutsättning för att du ska kunna genomföra ett bevarande-eller borttagnings schema.</span><span class="sxs-lookup"><span data-stu-id="f66a1-137">Establishing a data retention schedule for defined information types should be considered a prerequisite to implementing any retention or deletion scheme.</span></span>

- <span data-ttu-id="f66a1-138">Baserat på det antal informations typer som de flesta organisationer anser vara viktiga och de motsvarande stora poster för bevarande av Arkiv handlingar som visas, måste du planera.</span><span class="sxs-lookup"><span data-stu-id="f66a1-138">Given the number of information types that most organizations consider important and the corresponding large records retention schedules that go along with them, implementing a data retention and records management strategy requires planning.</span></span> 

- <span data-ttu-id="f66a1-139">När det gäller att upprätta en effektiv data hanterings strategi av den här typen är att fokusera på de företags funktioner och informations typer som kräver mer formell hantering.</span><span class="sxs-lookup"><span data-stu-id="f66a1-139">The key to establishing an effective data governance strategy of this type is to focus on the highest priority business functions and information types that require more formal management.</span></span> <span data-ttu-id="f66a1-140">Exempel är juridiska avtal, finansiella rapporter och dokumentation om överensstämmelse.</span><span class="sxs-lookup"><span data-stu-id="f66a1-140">Examples are legal contracts, financial statements, and regulatory compliance documentation.</span></span> <span data-ttu-id="f66a1-141">Försök att undvika ett separat bevarande schema för varje enskild informations typ.</span><span class="sxs-lookup"><span data-stu-id="f66a1-141">Try to avoid having a separate retention schedule for every single information type.</span></span> <span data-ttu-id="f66a1-142">Försök att använda allmänna kategorier så mycket som möjligt, till exempel med bevarande scheman på 7 år för allmänt företags innehåll.</span><span class="sxs-lookup"><span data-stu-id="f66a1-142">Try to utilize general categories as much as possible, for example, with retention schedules of 7 years for general business content.</span></span>

- <span data-ttu-id="f66a1-143">När de personliga informations typerna i miljön är bättre kända kan du skapa scheman för bevarande och borttagning av den här typen av innehåll och justera din informations arkitektur så att den blir lättare att använda.</span><span class="sxs-lookup"><span data-stu-id="f66a1-143">Once the personal information types in your environment are better known, establish retention and deletion schedules for this type of content and adjust your information architecture to make governance of this sort of information easier.</span></span> <span data-ttu-id="f66a1-144">Du kan till exempel isolera personlig information i separata webbplatser, bibliotek eller mappar med styrd åtkomst.</span><span class="sxs-lookup"><span data-stu-id="f66a1-144">For example, isolate personal information in separate sites, libraries, or folders with controlled access.</span></span>

### <a name="retention-policies-and-retention-labels"></a><span data-ttu-id="f66a1-145">Bevarande principer och bevarande etiketter</span><span class="sxs-lookup"><span data-stu-id="f66a1-145">Retention policies and retention labels</span></span>

<span data-ttu-id="f66a1-146">Använd [bevarande principer och bevarande etiketter](../compliance/retention.md) för att behålla eller ta bort innehåll i Microsoft 365 som innehåller eller förväntas innehålla person uppgifter.</span><span class="sxs-lookup"><span data-stu-id="f66a1-146">Use [retention policies and retention labels](../compliance/retention.md) to retain or delete content in Microsoft 365 that contains or is expected to contain personal data.</span></span>

### <a name="records-management"></a><span data-ttu-id="f66a1-147">Hantering av arkivhandlingar</span><span class="sxs-lookup"><span data-stu-id="f66a1-147">Records management</span></span>

<span data-ttu-id="f66a1-148">Använd lagrings etiketter som deklarerar innehåll en post för att implementera en [lösning för hantering av Arkiv handlingar](../compliance/records-management.md) för data i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f66a1-148">Use retention labels that declare content a record to implement a [records management solution](../compliance/records-management.md) for data in Microsoft 365.</span></span>

<span data-ttu-id="f66a1-149">För data integritet förklaras en post med DSRs som tagits emot av den juridiska avdelningen och kan lagras obegränsat eller avyttrade med bevis, för att följa gällande bestämmelser om bevarande av tvister.</span><span class="sxs-lookup"><span data-stu-id="f66a1-149">For data privacy, data subject requests (DSRs) received by the legal department are declared a record and can be stored indefinitely or disposed of with proof, to adhere to regulatory activity retention specifications.</span></span>

