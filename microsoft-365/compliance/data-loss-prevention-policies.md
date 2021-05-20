---
title: Referens för förebyggande av dataförlust
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: low
ms.collection:
- M365-security-compliance
- SPO_Content
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: referensmaterial för förebyggande av dataförlust
ms.openlocfilehash: a6dc0b2702899e05f78c54331fb33b87495672d8
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572567"
---
# <a name="data-loss-prevention-reference"></a><span data-ttu-id="c0ce4-103">Referens för förebyggande av dataförlust</span><span class="sxs-lookup"><span data-stu-id="c0ce4-103">Data loss prevention reference</span></span>
 
> [!IMPORTANT]
> <span data-ttu-id="c0ce4-104">Det här är referensavsnittet är inte längre den viktigaste resursen Microsoft 365 DLP-information (Data Loss Prevention).</span><span class="sxs-lookup"><span data-stu-id="c0ce4-104">This is reference topic is no longer the main resource for Microsoft 365 data loss prevention (DLP) information.</span></span> <span data-ttu-id="c0ce4-105">DLP-innehållsuppsättningen uppdateras och omstruktureras.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-105">The DLP content set is being updated and restructured.</span></span> <span data-ttu-id="c0ce4-106">De ämnen som behandlas i den här artikeln kommer att gå över till nya, uppdaterade artiklar.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-106">The topics covered in this article will be moving to new, updated articles.</span></span> <span data-ttu-id="c0ce4-107">Mer information om DLP finns i Lär [dig mer om förebyggande av dataförlust](dlp-learn-about-dlp.md).</span><span class="sxs-lookup"><span data-stu-id="c0ce4-107">For more information about DLP, see [Learn about data loss prevention](dlp-learn-about-dlp.md).</span></span>

<!-- this topic needs to be split into smaller, more coherent ones. It is confusing as it is. -->
<!-- move this note to a more appropriate place, no topic should start with a note -->
> [!NOTE]
> <span data-ttu-id="c0ce4-108">Funktioner för att förebygga dataförlust lades nyligen till i Microsoft Teams chatt- och kanalmeddelanden för användare som licensierats för Office 365 Advanced Compliance, vilket är tillgängligt som ett fristående alternativ och ingår i Office 365 E5 och Microsoft 365 E5 Compliance.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-108">Data loss prevention capabilities were recently added to Microsoft Teams chat and channel messages for users licensed for Office 365 Advanced Compliance, which is available as a standalone option and is included in Office 365 E5 and Microsoft 365 E5 Compliance.</span></span> <span data-ttu-id="c0ce4-109">Mer information om licenskrav finns i [Microsoft 365 Tenant-Level Services Licensing Guidance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).</span><span class="sxs-lookup"><span data-stu-id="c0ce4-109">To learn more about licensing requirements, see [Microsoft 365 Tenant-Level Services Licensing Guidance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).</span></span>



<!-- MOVED TO LEARN ABOUT To comply with business standards and industry regulations, organizations must protect sensitive information and prevent its inadvertent disclosure. Sensitive information can include financial data or personally identifiable information (PII) such as credit card numbers, social security numbers, or health records. With a data loss prevention (DLP) policy in the Office 365 Security &amp; Compliance Center, you can identify, monitor, and automatically protect sensitive information across Office 365.
  
With a DLP policy, you can:
  
- **Identify sensitive information across many locations, such as Exchange Online, SharePoint Online, OneDrive for Business, and Microsoft Teams.**
    
    For example, you can identify any document containing a credit card number that's stored in any OneDrive for Business site, or you can monitor just the OneDrive sites of specific people.
    
- **Prevent the accidental sharing of sensitive information**. 
    
    For example, you can identify any document or email containing a health record that's shared with people outside your organization, and then automatically block access to that document or block the email from being sent.
    
- **Monitor and protect sensitive information in the desktop versions of Excel, PowerPoint, and Word.**
    
    Just like in Exchange Online, SharePoint Online, and OneDrive for Business, these Office desktop programs include the same capabilities to identify sensitive information and apply DLP policies. DLP provides continuous monitoring when people share content in these Office programs.
    
- **Help users learn how to stay compliant without interrupting their workflow.**
    
    You can educate your users about DLP policies and help them remain compliant without blocking their work. For example, if a user tries to share a document containing sensitive information, a DLP policy can both send them an email notification and show them a policy tip in the context of the document library that allows them to override the policy if they have a business justification. The same policy tips also appear in Outlook on the web, Outlook, Excel, PowerPoint, and Word.
    
- **View DLP alerts and reports showing content that matches your organization’s DLP policies.**
    
    To view alerts and metadata related to your DLP policies you can use the [DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md). You can also view policy match reports to assess how your organization is complying with a DLP policy. If a DLP policy allows users to override a policy tip and report a false positive, you can also view what users have reported

-->    
## <a name="create-and-manage-dlp-policies"></a><span data-ttu-id="c0ce4-110">Skapa och hantera DLP-principer</span><span class="sxs-lookup"><span data-stu-id="c0ce4-110">Create and manage DLP policies</span></span>

<span data-ttu-id="c0ce4-111">Du skapar och hanterar DLP-principer på sidan Dataförlustförebyggande i Microsoft 365 Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-111">You create and manage DLP policies on the Data loss prevention page in the Microsoft 365 Compliance center.</span></span>
  
![Sidan dataförlustförebyggande i Office 365 Security &amp; Compliance Center](../media/943fd01c-d7aa-43a9-846d-0561321a405e.png)
  
<!-- MOVED TO LEARN ABOUT ## What a DLP policy contains

A DLP policy contains a few basic things:
  
- Where to protect the content: **locations** such as Exchange Online, SharePoint Online, and OneDrive for Business sites, as well as Microsoft Teams chat and channel messages. 
    
- When and how to protect the content by enforcing **rules** comprised of: 
    
  - **Conditions** the content must match before the rule is enforced. For example, a rule might be configured to look only for content containing Social Security numbers that's been shared with people outside your organization. 
    
  - **Actions** that you want the rule to take automatically when content matching the conditions is found. For example, a rule might be configured to block access to a document and send both the user and compliance officer an email notification. -->
    
<span data-ttu-id="c0ce4-113">Du kan använda en regel för att uppfylla ett specifikt skyddskrav och sedan använda en DLP-policy för att gruppera gemensamma skyddskrav, till exempel alla regler som behövs för att följa en viss förordning.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-113">You can use a rule to meet a specific protection requirement, and then use a DLP policy to group together common protection requirements, such as all of the rules needed to comply with a specific regulation.</span></span>
  
<span data-ttu-id="c0ce4-114">Du kan till exempel ha en DLP-policy som hjälper dig att upptäcka förekomsten av information som omfattas av Hipaa (Health Insurance Portability and Accountability Act).</span><span class="sxs-lookup"><span data-stu-id="c0ce4-114">For example, you might have a DLP policy that helps you detect the presence of information subject to the Health Insurance Portability and Accountability Act (HIPAA).</span></span> <span data-ttu-id="c0ce4-115">Den här DLP-principen kan hjälpa till att skydda HIPAA-data (vad) på alla SharePoint Online-webbplatser och alla OneDrive för företag-webbplatser (var) genom att hitta alla dokument som innehåller den här känsliga informationen som delas med personer utanför organisationen (villkoren) och sedan blockera åtkomst till dokumentet och skicka ett meddelande (åtgärderna).</span><span class="sxs-lookup"><span data-stu-id="c0ce4-115">This DLP policy could help protect HIPAA data (the what) across all SharePoint Online sites and all OneDrive for Business sites (the where) by finding any document containing this sensitive information that's shared with people outside your organization (the conditions) and then blocking access to the document and sending a notification (the actions).</span></span> <span data-ttu-id="c0ce4-116">Dessa krav lagras som individuella regler och grupperas tillsammans som en DLP-policy för att förenkla hantering och rapportering.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-116">These requirements are stored as individual rules and grouped together as a DLP policy to simplify management and reporting.</span></span>
  
![Diagrammet visar att DLP-principen innehåller platser och regler](../media/c006860c-2d00-42cb-aaa4-5b5638d139f7.png)
  
<!-- MOVED TO LEARN ABOUT ### Locations

DLP policies are applied to sensitive items across Microsoft 365 locations and can be further scoped as detailed in this table.


|Location | Include/exclude by|
|---------|---------|
|Exchange email| distribution groups|
|SharePoint sites |sites |
|OneDrive accounts |accounts |
|Teams chat and channel messages |accounts |
|Windows 10 devices |user or group |
|Microsoft Cloud App Security |instance |
 -->

<span data-ttu-id="c0ce4-118">Om du väljer att inkludera specifika distributionsgrupper Exchange kommer DLP-principen endast att omfatta medlemmarna i den gruppen.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-118">If you choose to include specific distribution groups in Exchange, the DLP policy will be scoped only to the members of that group.</span></span> <span data-ttu-id="c0ce4-119">Om du utesluter en distributionsgrupp utesluts inte heller alla medlemmar i distributionsgruppen från principutvärderingen.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-119">Similarly excluding a distribution group will exclude all the members of that distribution group from policy evaluation.</span></span> <span data-ttu-id="c0ce4-120">Du kan välja att omfånga en princip till medlemmarna i distributionslistor, dynamiska distributionsgrupper och säkerhetsgrupper.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-120">You can choose to scope a policy to the members of distribution lists, dynamic distribution groups, and security groups.</span></span> <span data-ttu-id="c0ce4-121">En DLP-policy får inte innehålla mer än 50 sådana införanden och undantag.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-121">A DLP policy can contain no more than 50 such inclusions and exclusions.</span></span>

<span data-ttu-id="c0ce4-122">Om du väljer att inkludera eller utesluta SharePoint vissa webbplatser kan en DLP-princip innehålla högst 100 sådana inkluderingar och undantag.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-122">If you choose to include or exclude specific SharePoint sites, a DLP policy can contain no more than 100 such inclusions and exclusions.</span></span> <span data-ttu-id="c0ce4-123">Även om den här gränsen finns kan du överskrida den här gränsen genom att tillämpa antingen en organisationsomfattande princip eller en princip som gäller för hela platser.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-123">Although this limit exists, you can exceed this limit by applying either an org-wide policy or a policy that applies to entire locations.</span></span>

<span data-ttu-id="c0ce4-124">Om du väljer att inkludera eller utesluta specifika OneDrive-konton eller grupper kan en DLP-princip innehålla högst 100 användarkonton eller 50 grupper som inkludering eller undantag.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-124">If you choose to include or exclude specific OneDrive accounts or groups, a DLP policy can contain no more than 100 user accounts or 50 groups as inclusion or exclusion.</span></span>

> [!NOTE]
> <span data-ttu-id="c0ce4-125">OneDrive för affärsprincip omfång med konton eller grupper är i offentlig förhandsgranskning.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-125">OneDrive for business policy scoping using accounts or groups is in public preview.</span></span> <span data-ttu-id="c0ce4-126">Under den här fasen kan du antingen inkludera eller utesluta användarkonton och grupper som en del av en DLP-princip.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-126">During this phase, you can either include or exclude user accounts and groups as part of a DLP policy.</span></span> <span data-ttu-id="c0ce4-127">Både inkludering och uteslutning som en del av samma politik stöds inte.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-127">Both inclusion and exclusion as part of the same policy is not supported.</span></span>
  
### <a name="rules"></a><span data-ttu-id="c0ce4-128">Regler</span><span class="sxs-lookup"><span data-stu-id="c0ce4-128">Rules</span></span>

> [!NOTE]
> <span data-ttu-id="c0ce4-129">Standardbeteendet för en DLP-princip, när ingen avisering är konfigurerad, är inte att varna eller utlösa.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-129">The default behavior of a DLP policy, when there is no alert configured, is not to alert or trigger.</span></span> <span data-ttu-id="c0ce4-130">Detta gäller endast standardinformationstyper.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-130">This applies only to default information types.</span></span> <span data-ttu-id="c0ce4-131">För anpassade informations typer kommer systemet att varna även om det inte finns någon åtgärd definierad i principen.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-131">For custom information types, the system will alert even if there is no action defined in the policy.</span></span>

<span data-ttu-id="c0ce4-132">Regler är vad som upprätthåller dina affärskrav på organisationens innehåll.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-132">Rules are what enforce your business requirements on your organization's content.</span></span> <span data-ttu-id="c0ce4-133">En princip innehåller en eller flera regler, och varje regel består av villkor och åtgärder.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-133">A policy contains one or more rules, and each rule consists of conditions and actions.</span></span> <span data-ttu-id="c0ce4-134">För varje regel, när villkoren är uppfyllda, vidtas åtgärderna automatiskt.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-134">For each rule, when the conditions are met, the actions are taken automatically.</span></span> <span data-ttu-id="c0ce4-135">Regler körs sekventiellt, med början med regeln med högst prioritet i varje princip.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-135">Rules are executed sequentially, starting with the highest-priority rule in each policy.</span></span>
  
<span data-ttu-id="c0ce4-136">En regel innehåller också alternativ för att meddela användare (med principtips och e-postaviseringar) och administratörer (med e-postincidentrapporter) att innehållet har matchat regeln.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-136">A rule also provides options to notify users (with policy tips and email notifications) and admins (with email incident reports) that content has matched the rule.</span></span>
  
<span data-ttu-id="c0ce4-137">Här är komponenterna i en regel, var och en förklaras nedan.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-137">Here are the components of a rule, each explained below.</span></span>
  
![Avsnitt i DLP-regelredigeraren](../media/1859d504-b9c2-45ed-961b-a0092251acc2.png)
  
#### <a name="conditions"></a><span data-ttu-id="c0ce4-139">Villkor</span><span class="sxs-lookup"><span data-stu-id="c0ce4-139">Conditions</span></span>

<span data-ttu-id="c0ce4-140">Villkor är viktiga eftersom de bestämmer vilka typer av information du letar efter och när du ska vidta en åtgärd.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-140">Conditions are important because they determine what types of information you're looking for, and when to take an action.</span></span> <span data-ttu-id="c0ce4-141">Du kan till exempel välja att ignorera innehåll som innehåller passnummer om inte innehållet innehåller fler än 10 sådana nummer och delas med personer utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-141">For example, you might choose to ignore content containing passport numbers unless the content contains more than 10 such numbers and is shared with people outside your organization.</span></span>
  
<span data-ttu-id="c0ce4-142">Villkoren fokuserar på **innehållet**, till exempel vilka typer av känslig information du letar efter och även på **sammanhanget**, till exempel vem dokumentet delas med.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-142">Conditions focus on the **content**, such as what types of sensitive information you're looking for, and also on the **context**, such as who the document is shared with.</span></span> <span data-ttu-id="c0ce4-143">Du kan använda villkor för att tilldela olika åtgärder till olika risknivåer.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-143">You can use conditions to assign different actions to different risk levels.</span></span> <span data-ttu-id="c0ce4-144">Känsligt innehåll som delas internt kan till exempel vara lägre risk och kräver färre åtgärder än känsligt innehåll som delas med personer utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-144">For example, sensitive content shared internally might be lower risk and require fewer actions than sensitive content shared with people outside the organization.</span></span> 
  
![Lista som visar tillgängliga DLP-villkor](../media/0fa43f90-d007-4506-ae93-43e8424fe103.png)
  
<span data-ttu-id="c0ce4-146">De villkor som nu är tillgängliga kan avgöra om:</span><span class="sxs-lookup"><span data-stu-id="c0ce4-146">The conditions now available can determine if:</span></span>
  
- <span data-ttu-id="c0ce4-147">Innehållet innehåller en typ av känslig information.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-147">Content contains a type of sensitive information.</span></span>
    
- <span data-ttu-id="c0ce4-148">Innehållet innehåller en etikett.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-148">Content contains a label.</span></span> <span data-ttu-id="c0ce4-149">Mer information finns i avsnittet nedan använda en [lagringsetikett som ett villkor i en DLP-princip](#using-a-retention-label-as-a-condition-in-a-dlp-policy).</span><span class="sxs-lookup"><span data-stu-id="c0ce4-149">For more information, see the below section [Using a retention label as a condition in a DLP policy](#using-a-retention-label-as-a-condition-in-a-dlp-policy).</span></span>
    
- <span data-ttu-id="c0ce4-150">Innehållet delas med personer utanför eller inom organisationen.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-150">Content is shared with people outside or inside your organization.</span></span>

  > [!NOTE]
  > <span data-ttu-id="c0ce4-151">Användare som har konton som inte är gästar i en värdorganisations Active Directory eller Azure Active Directory-klient betraktas som personer inom organisationen.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-151">Users who have non-guest accounts in a host organization's Active Directory or Azure Active Directory tenant are considered as people inside the organization.</span></span>
    
#### <a name="types-of-sensitive-information"></a><span data-ttu-id="c0ce4-152">Typer av känslig information</span><span class="sxs-lookup"><span data-stu-id="c0ce4-152">Types of sensitive information</span></span>

<span data-ttu-id="c0ce4-153">Med en DLP-princip skyddar du känslig information som har definierats med en **typ av känslig information**.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-153">A DLP policy can help protect sensitive information, which is defined as a **sensitive information type**.</span></span> <span data-ttu-id="c0ce4-154">Microsoft 365 innehåller definitioner för många vanliga känsliga informationstyper i många olika regioner som är redo för dig att använda, till exempel ett kreditkortsnummer, bankkontonummer, nationella ID-nummer och passnummer.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-154">Microsoft 365 includes definitions for many common sensitive information types across many different regions that are ready for you to use, such as a credit card number, bank account numbers, national ID numbers, and passport numbers.</span></span> 
  
![Lista över tillgängliga känsliga informationstyper](../media/3eaa9911-bc94-44be-902f-363dbf3b07fe.png)
  
<span data-ttu-id="c0ce4-156">När en DLP-princip söker efter en känslig informationstyp, till exempel ett kreditkortsnummer, letar den inte bara efter ett 16-siffrigt nummer.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-156">When a DLP policy looks for a sensitive information type such as a credit card number, it doesn't simply look for a 16-digit number.</span></span> <span data-ttu-id="c0ce4-157">Varje känslig informationstyp definieras och identifieras med hjälp av en kombination av:</span><span class="sxs-lookup"><span data-stu-id="c0ce4-157">Each sensitive information type is defined and detected by using a combination of:</span></span>
  
- <span data-ttu-id="c0ce4-158">nyckelord.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-158">Keywords.</span></span>
    
- <span data-ttu-id="c0ce4-159">Interna funktioner för att validera kontrollsummar eller sammansättning.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-159">Internal functions to validate checksums or composition.</span></span>
    
- <span data-ttu-id="c0ce4-160">Utvärdering av reguljära uttryck för att hitta mönstermatchningar.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-160">Evaluation of regular expressions to find pattern matches.</span></span>
    
- <span data-ttu-id="c0ce4-161">Annan innehållsundersökning.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-161">Other content examination.</span></span>
    
<span data-ttu-id="c0ce4-162">Detta hjälper DLP-identifiering att uppnå en hög grad av noggrannhet samtidigt som antalet falska positiva identifieringar som kan avbryta människors arbete minskar.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-162">This helps DLP detection achieve a high degree of accuracy while reducing the number of false positives that can interrupt peoples' work.</span></span>
  
#### <a name="actions"></a><span data-ttu-id="c0ce4-163">Åtgärder</span><span class="sxs-lookup"><span data-stu-id="c0ce4-163">Actions</span></span>

<span data-ttu-id="c0ce4-164">När innehåll matchar ett villkor i en regel kan du tillämpa åtgärder för att automatiskt skydda innehållet.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-164">When content matches a condition in a rule, you can apply actions to automatically protect the content.</span></span>
  
![Lista över tillgängliga DLP-åtgärder](../media/8aef17fc-1e99-4ac7-adfc-0f2c9c1a0697.png)
  
<span data-ttu-id="c0ce4-166">Med de åtgärder som nu är tillgängliga kan du:</span><span class="sxs-lookup"><span data-stu-id="c0ce4-166">With the actions now available, you can:</span></span>
  
- <span data-ttu-id="c0ce4-167">**Begränsa åtkomsten till innehållet** Beroende på ditt behov kan du begränsa åtkomsten till innehåll på tre sätt:</span><span class="sxs-lookup"><span data-stu-id="c0ce4-167">**Restrict access to the content** Depending on your need, you can restrict access to content in three ways:</span></span>

  1. <span data-ttu-id="c0ce4-168">Begränsa åtkomsten till innehåll för alla.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-168">Restrict access to content for everyone.</span></span>
  2. <span data-ttu-id="c0ce4-169">Begränsa åtkomsten till innehåll för personer utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-169">Restrict access to content for people outside the organization.</span></span>
  3. <span data-ttu-id="c0ce4-170">Begränsa åtkomsten till "Alla med länken".</span><span class="sxs-lookup"><span data-stu-id="c0ce4-170">Restrict access to "Anyone with the link."</span></span>

  <span data-ttu-id="c0ce4-171">För webbplatsinnehåll innebär detta att behörigheterna för dokumentet är begränsade för alla utom den primära webbplatssamlingsadministratören, dokumentägaren och personen som senast ändrade dokumentet.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-171">For site content, this means that permissions for the document are restricted for everyone except the primary site collection administrator, document owner, and person who last modified the document.</span></span> <span data-ttu-id="c0ce4-172">Dessa personer kan ta bort känslig information från dokumentet eller vidta andra åtgärdsåtgärder.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-172">These people can remove the sensitive information from the document or take other remedial action.</span></span> <span data-ttu-id="c0ce4-173">När dokumentet är i överensstämmelse återställs de ursprungliga behörigheterna automatiskt.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-173">When the document is in compliance, the original permissions are automatically restored.</span></span> <span data-ttu-id="c0ce4-174">När åtkomsten till ett dokument är blockerad visas dokumentet med en särskild principtipsikon i biblioteket på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-174">When access to a document is blocked, the document appears with a special policy tip icon in the library on the site.</span></span> 
    
  ![Principtips som visar åtkomst till dokument är blockerat](../media/b6cefed3-d212-43d7-8534-4b92b26ebd50.png)
  
  <span data-ttu-id="c0ce4-176">För e-postinnehåll blockerar den här åtgärden meddelandet från att skickas.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-176">For email content, this action blocks the message from being sent.</span></span> <span data-ttu-id="c0ce4-177">Beroende på hur DLP-regeln är konfigurerad ser avsändaren en NDR eller (om regeln använder ett meddelande) ett principtips och/eller e-postmeddelande.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-177">Depending on how the DLP rule is configured, the sender sees an NDR or (if the rule uses a notification) a policy tip and/or email notification.</span></span>
    
  ![Varning om att obehöriga mottagare måste tas bort från meddelandet](../media/302f9994-912d-41e7-861f-8a4539b3c285.png)
  
#### <a name="user-notifications-and-user-overrides"></a><span data-ttu-id="c0ce4-179">Användarmeddelanden och användaråsidosättning</span><span class="sxs-lookup"><span data-stu-id="c0ce4-179">User notifications and user overrides</span></span>

<span data-ttu-id="c0ce4-180">Du kan använda aviseringar och åsidosättningar för att utbilda användarna om DLP-principer och hjälpa dem att förbli kompatibla utan att blockera deras arbete.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-180">You can use notifications and overrides to educate your users about DLP policies and help them remain compliant without blocking their work.</span></span> <span data-ttu-id="c0ce4-181">Om en användare till exempel försöker dela ett dokument som innehåller känslig information kan en DLP-princip både skicka dem ett e-postmeddelande och visa dem ett principtips i samband med dokumentbiblioteket som gör att de kan åsidosätta principen om de har en affärs motivering.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-181">For example, if a user tries to share a document containing sensitive information, a DLP policy can both send them an email notification and show them a policy tip in the context of the document library that allows them to override the policy if they have a business justification.</span></span>
  
![Användarmeddelanden och användare åsidosätter avsnitt i DLP-regelredigeraren](../media/37b560d4-6e4e-489e-9134-d4b9daf60296.png)
  
<span data-ttu-id="c0ce4-183">E-postmeddelandet kan meddela den person som skickade, delade eller senast ändrade innehållet och, för webbplatsinnehåll, den primära administratören för webbplatssamlingen och dokumentägaren.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-183">The email can notify the person who sent, shared, or last modified the content and, for site content, the primary site collection administrator and document owner.</span></span> <span data-ttu-id="c0ce4-184">Dessutom kan du lägga till eller ta bort vem du vill från e-postmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-184">In addition, you can add or remove whomever you choose from the email notification.</span></span>
  
<span data-ttu-id="c0ce4-185">Förutom att skicka ett e-postmeddelande visas ett principtips i ett användarmeddelande:</span><span class="sxs-lookup"><span data-stu-id="c0ce4-185">In addition to sending an email notification, a user notification displays a policy tip:</span></span>
  
- <span data-ttu-id="c0ce4-186">I Outlook och Outlook på webben.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-186">In Outlook and Outlook on the web.</span></span>
    
- <span data-ttu-id="c0ce4-187">För dokumentet på en SharePoint Online eller OneDrive för företag webbplats.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-187">For the document on a SharePoint Online or OneDrive for Business site.</span></span>
    
- <span data-ttu-id="c0ce4-188">I Excel PowerPoint word när dokumentet lagras på en webbplats som ingår i en DLP-princip.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-188">In Excel, PowerPoint, and Word, when the document is stored on a site included in a DLP policy.</span></span>
    
<span data-ttu-id="c0ce4-189">E-postmeddelandet och principtipset förklarar varför innehåll strider mot en DLP-policy.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-189">The email notification and policy tip explain why content conflicts with a DLP policy.</span></span> <span data-ttu-id="c0ce4-190">Om du väljer kan e-postmeddelandet och principtipset tillåta användare att åsidosätta en regel genom att rapportera ett falskt positivt eller tillhandahålla en affärs motivering.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-190">If you choose, the email notification and policy tip can allow users to override a rule by reporting a false positive or providing a business justification.</span></span> <span data-ttu-id="c0ce4-191">Detta kan hjälpa dig att utbilda användare om dina DLP-principer och genomdriva dem utan att hindra människor från att göra sitt arbete.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-191">This can help you educate users about your DLP policies and enforce them without preventing people from doing their work.</span></span> <span data-ttu-id="c0ce4-192">Information om åsidosättningar och falska positiva identifieringar loggas också för rapportering (se nedan om DLP-rapporterna) och ingår i incidentrapporterna (nästa avsnitt), så att efterlevnadsansvarige regelbundet kan granska denna information.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-192">Information about overrides and false positives is also logged for reporting (see below about the DLP reports) and included in the incident reports (next section), so that the compliance officer can regularly review this information.</span></span>
  
<span data-ttu-id="c0ce4-193">Så här ser ett principtips ut på ett OneDrive för företag konto.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-193">Here's what a policy tip looks like in a OneDrive for Business account.</span></span>
  
![Principtips för ett dokument i ett OneDrive konto](../media/f9834d35-94f0-4511-8555-0fe69855ce6d.png)

 <span data-ttu-id="c0ce4-195">Mer information om användaraviseringar och principtips i DLP-principer finns i [Använda aviseringar och principtips](use-notifications-and-policy-tips.md).</span><span class="sxs-lookup"><span data-stu-id="c0ce4-195">To learn more about user notifications and policy tips in DLP policies, see [Use notifications and policy tips](use-notifications-and-policy-tips.md).</span></span>

#### <a name="alerts-and-incident-reports"></a><span data-ttu-id="c0ce4-196">Aviseringar och incidentrapporter</span><span class="sxs-lookup"><span data-stu-id="c0ce4-196">Alerts and Incident reports</span></span>

<span data-ttu-id="c0ce4-197">När en regel matchas kan du skicka ett e-postmeddelande till din compliance officer (eller någon person du väljer) med information om aviseringen.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-197">When a rule is matched, you can send an alert email to your compliance officer ( or any person(s) you choose) with details of the alert.</span></span> <span data-ttu-id="c0ce4-198">Det här e-postmeddelandet kommer att ha en länk [till DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md) som efterlevnadsansvarigen kan gå för att visa information om aviseringar och händelser.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-198">This alert email will carry a link of the [DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md) which the compliance officer can go to view the details of alert and events.</span></span> <span data-ttu-id="c0ce4-199">Instrumentpanelen innehåller information om händelsen som utlöste aviseringen tillsammans med information om DLP-principen som matchades och det känsliga innehållet som identifierades.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-199">The dashboard contains details of the event that triggered the alert along with details of the DLP policy matched and the sensitive content detected.</span></span>

<span data-ttu-id="c0ce4-200">Dessutom kan du också skicka en incidentrapport med information om händelsen.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-200">In addition, you can also send an incident report with details of the event.</span></span> <span data-ttu-id="c0ce4-201">Den här rapporten innehåller information om det objekt som matchades, det faktiska innehållet som matchade regeln och namnet på den person som senast ändrade innehållet.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-201">This report includes information about the item that was matched, the actual content that matched the rule, and the name of the person who last modified the content.</span></span> <span data-ttu-id="c0ce4-202">För e-postmeddelanden innehåller rapporten också som en bifogad fil det ursprungliga meddelandet som matchar en DLP-princip.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-202">For email messages, the report also includes as an attachment the original message that matches a DLP policy.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c0ce4-203">![Sida för konfigurering av incidentrapporter](../media/Alerts-and-incident-report.png)</span><span class="sxs-lookup"><span data-stu-id="c0ce4-203">![Page for configuring incident reports](../media/Alerts-and-incident-report.png)</span></span>

<span data-ttu-id="c0ce4-204">DLP skannar e-post på ett annat sätt än objekt i SharePoint Online eller OneDrive för företag.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-204">DLP scans email differently from items in SharePoint Online or OneDrive for Business.</span></span> <span data-ttu-id="c0ce4-205">I SharePoint Online och OneDrive för företag DLP befintliga objekt samt nya och genererar en aviserings- och incidentrapport när en matchning hittas.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-205">In SharePoint Online and OneDrive for Business, DLP scans existing items as well as new ones and generates an alert and incident report whenever a match is found.</span></span> <span data-ttu-id="c0ce4-206">I Exchange Online DLP bara nya e-postmeddelanden och genererar en rapport om det finns en principmatchning.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-206">In Exchange Online, DLP only scans new email messages and generates a report if there is a policy match.</span></span> <span data-ttu-id="c0ce4-207">DLP ***söker inte igenom*** eller matchar tidigare befintliga e-postobjekt som lagras i en postlåda eller ett arkiv.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-207">DLP ***does not*** scan or match previously existing email items that are stored in a mailbox or archive.</span></span>
  
## <a name="grouping-and-logical-operators"></a><span data-ttu-id="c0ce4-208">Gruppering och logiska operatorer</span><span class="sxs-lookup"><span data-stu-id="c0ce4-208">Grouping and logical operators</span></span>

<span data-ttu-id="c0ce4-209">Ofta har din DLP-policy ett enkelt krav, till exempel att identifiera allt innehåll som innehåller ett amerikanskt personnummer.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-209">Often your DLP policy has a straightforward requirement, such as to identify all content that contains a U.S. Social Security Number.</span></span> <span data-ttu-id="c0ce4-210">I andra scenarier kan dock DLP-principen behöva identifiera mer löst definierade data.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-210">However, in other scenarios, your DLP policy might need to identify more loosely defined data.</span></span>
  
<span data-ttu-id="c0ce4-211">Om du till exempel vill identifiera innehåll som omfattas av U.S. Health Insurance Act (HIPAA) måste du leta efter:</span><span class="sxs-lookup"><span data-stu-id="c0ce4-211">For example, to identify content subject to the U.S. Health Insurance Act (HIPAA), you need to look for:</span></span>
  
- <span data-ttu-id="c0ce4-212">Innehåll som innehåller specifika typer av känslig information, till exempel ett amerikanskt personnummer eller DEA-nummer (Drug Enforcement Agency).</span><span class="sxs-lookup"><span data-stu-id="c0ce4-212">Content that contains specific types of sensitive information, such as a U.S. Social Security Number or Drug Enforcement Agency (DEA) Number.</span></span>
    
    <span data-ttu-id="c0ce4-213">och</span><span class="sxs-lookup"><span data-stu-id="c0ce4-213">AND</span></span>
    
- <span data-ttu-id="c0ce4-214">Innehåll som är svårare att identifiera, till exempel kommunikation om en patients vård eller beskrivningar av medicinska tjänster som tillhandahålls.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-214">Content that's more difficult to identify, such as communications about a patient's care or descriptions of medical services provided.</span></span> <span data-ttu-id="c0ce4-215">För att identifiera det här innehållet krävs matchande nyckelord från mycket stora sökordslistor, till exempel international classification of diseases (ICD-9-CM eller ICD-10-CM).</span><span class="sxs-lookup"><span data-stu-id="c0ce4-215">Identifying this content requires matching keywords from very large keyword lists, such as the International Classification of Diseases (ICD-9-CM or ICD-10-CM).</span></span>
    
<span data-ttu-id="c0ce4-216">Du kan enkelt identifiera sådana löst definierade data med hjälp av gruppering och logiska operatorer (AND, OR).</span><span class="sxs-lookup"><span data-stu-id="c0ce4-216">You can easily identify such loosely defined data by using grouping and logical operators (AND, OR).</span></span> <span data-ttu-id="c0ce4-217">När du skapar en DLP-princip kan du:</span><span class="sxs-lookup"><span data-stu-id="c0ce4-217">When you create a DLP policy, you can:</span></span>
  
- <span data-ttu-id="c0ce4-218">Gruppera känsliga informationstyper.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-218">Group sensitive information types.</span></span>
    
- <span data-ttu-id="c0ce4-219">Välj den logiska operatorn mellan de känsliga informationstyperna i en grupp och mellan grupperna själva.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-219">Choose the logical operator between the sensitive information types within a group and between the groups themselves.</span></span>
    
### <a name="choosing-the-operator-within-a-group"></a><span data-ttu-id="c0ce4-220">Välja operator inom en grupp</span><span class="sxs-lookup"><span data-stu-id="c0ce4-220">Choosing the operator within a group</span></span>

<span data-ttu-id="c0ce4-221">I en grupp kan du välja om något eller alla villkor i den gruppen måste vara uppfyllda för att innehållet ska matcha regeln.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-221">Within a group, you can choose whether any or all of the conditions in that group must be satisfied for the content to match the rule.</span></span>
  
![Grupp som visar operatorerna inom koncernen](../media/6a12f1e8-112d-48ee-9a73-82b3dd0542e7.png)
  
### <a name="adding-a-group"></a><span data-ttu-id="c0ce4-223">Lägga till en grupp</span><span class="sxs-lookup"><span data-stu-id="c0ce4-223">Adding a group</span></span>

<span data-ttu-id="c0ce4-224">Du kan snabbt lägga till en grupp som kan ha sina egna villkor och en operator inom den gruppen.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-224">You can quickly add a group, which can have its own conditions and operator within that group.</span></span>
  
![Knappen Lägg till grupp](../media/5f72f292-d1f3-4f11-a911-a9f71e10abf6.png)
  
### <a name="choosing-the-operator-between-groups"></a><span data-ttu-id="c0ce4-226">Välja operator mellan grupper</span><span class="sxs-lookup"><span data-stu-id="c0ce4-226">Choosing the operator between groups</span></span>

<span data-ttu-id="c0ce4-227">Mellan grupper kan du välja om villkoren i bara en grupp eller alla grupper måste uppfyllas för att innehållet ska matcha regeln.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-227">Between groups, you can choose whether the conditions in just one group or all of the groups must be satisfied for the content to match the rule.</span></span>
  
<span data-ttu-id="c0ce4-228">Den inbyggda **HIPAA-principen** i USA har till exempel en regel som använder en **AND-operator** mellan grupperna så att den identifierar innehåll som innehåller:</span><span class="sxs-lookup"><span data-stu-id="c0ce4-228">For example, the built-in **U.S. HIPAA** policy has a rule that uses an **AND** operator between the groups so that it identifies content that contains:</span></span> 
  
- <span data-ttu-id="c0ce4-229">från gruppen **PII-identifierare (minst** ett SSN-nummer ELLER DEA-nummer) </span><span class="sxs-lookup"><span data-stu-id="c0ce4-229">from the group **PII Identifiers** (at least one SSN number **OR** DEA number)</span></span> 
    
    <span data-ttu-id="c0ce4-230">**och**</span><span class="sxs-lookup"><span data-stu-id="c0ce4-230">**AND**</span></span>
    
- <span data-ttu-id="c0ce4-231">från gruppen Medicinska **termer** (minst ett ICD-9-CM nyckelord **ELLER** ICD-10-CM nyckelord)</span><span class="sxs-lookup"><span data-stu-id="c0ce4-231">from the group **Medical Terms** (at least one ICD-9-CM keyword **OR** ICD-10-CM keyword)</span></span> 
    
![Grupper som visar operatorn mellan grupper](../media/354aa77f-569c-4847-9dfe-605ee2bb28d1.png)
  
## <a name="the-priority-by-which-rules-are-processed"></a><span data-ttu-id="c0ce4-233">Den prioritet genom vilken regler behandlas</span><span class="sxs-lookup"><span data-stu-id="c0ce4-233">The priority by which rules are processed</span></span>

<span data-ttu-id="c0ce4-234">När du skapar regler i en princip tilldelas varje regel en prioritet i den ordning den skapas, vilket innebär att regeln som skapas först har första prioritet, regeln som skapas andra prioritet och så vidare.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-234">When you create rules in a policy, each rule is assigned a priority in the order in which it's created — meaning, the rule created first has first priority, the rule created second has second priority, and so on.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c0ce4-235">![Regler i prioritetsordning](../media/dlp-rules-in-priority-order.png)</span><span class="sxs-lookup"><span data-stu-id="c0ce4-235">![Rules in priority order](../media/dlp-rules-in-priority-order.png)</span></span>
  
<span data-ttu-id="c0ce4-236">När du har konfigurerat mer än en DLP-princip kan du ändra prioriteten för en eller flera principer.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-236">After you have set up more than one DLP policy, you can change the priority of one or more policies.</span></span> <span data-ttu-id="c0ce4-237">Om du vill göra det väljer du en princip, **väljer Redigera princip** och använder **prioritetslistan** för att ange dess prioritet.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-237">To do that, select a policy, choose **Edit policy**, and use the **Priority** list to specify its priority.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c0ce4-238">![Ange prioritet för en princip](../media/dlp-set-policy-priority.png)</span><span class="sxs-lookup"><span data-stu-id="c0ce4-238">![Set priority for a policy](../media/dlp-set-policy-priority.png)</span></span>

<span data-ttu-id="c0ce4-239">När innehåll utvärderas mot regler bearbetas reglerna i prioritetsordning.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-239">When content is evaluated against rules, the rules are processed in priority order.</span></span> <span data-ttu-id="c0ce4-240">Om innehållet matchar flera regler bearbetas reglerna i prioritetsordning och den mest restriktiva åtgärden tillämpas.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-240">If content matches multiple rules, the rules are processed in priority order and the most restrictive action is enforced.</span></span> <span data-ttu-id="c0ce4-241">Om innehållet till exempel matchar alla följande regler tillämpas regel 3 eftersom det är den högst prioriterade och mest restriktiva regeln:</span><span class="sxs-lookup"><span data-stu-id="c0ce4-241">For example, if content matches all of the following rules, Rule 3 is enforced because it's the highest priority, most restrictive rule:</span></span>
  
- <span data-ttu-id="c0ce4-242">Regel 1: meddelar endast användare</span><span class="sxs-lookup"><span data-stu-id="c0ce4-242">Rule 1: only notifies users</span></span>
    
- <span data-ttu-id="c0ce4-243">Regel 2: meddelar användare, begränsar åtkomsten och tillåter användaråsidosättning</span><span class="sxs-lookup"><span data-stu-id="c0ce4-243">Rule 2: notifies users, restricts access, and allows user overrides</span></span>
    
- <span data-ttu-id="c0ce4-244">Regel 3: meddelar användare, begränsar åtkomsten och tillåter inte åsidosättningar av användare</span><span class="sxs-lookup"><span data-stu-id="c0ce4-244">Rule 3: notifies users, restricts access, and does not allow user overrides</span></span>
    
- <span data-ttu-id="c0ce4-245">Regel 4: meddelar endast användare</span><span class="sxs-lookup"><span data-stu-id="c0ce4-245">Rule 4: only notifies users</span></span>
    
- <span data-ttu-id="c0ce4-246">Regel 5: begränsar tillgången</span><span class="sxs-lookup"><span data-stu-id="c0ce4-246">Rule 5: restricts access</span></span>
    
- <span data-ttu-id="c0ce4-247">Regel 6: meddelar användare, begränsar åtkomsten och tillåter inte åsidosättningar av användare</span><span class="sxs-lookup"><span data-stu-id="c0ce4-247">Rule 6: notifies users, restricts access, and does not allow user overrides</span></span>
    
<span data-ttu-id="c0ce4-248">Observera i det här exemplet att matchningar för alla regler registreras i granskningsloggarna och visas i DLP-rapporterna, även om endast den mest restriktiva regeln tillämpas.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-248">In this example, note that matches for all of the rules are recorded in the audit logs and shown in the DLP reports, even though only the most restrictive rule is enforced.</span></span>
  
<span data-ttu-id="c0ce4-249">När det gäller policytips bör du notera att:</span><span class="sxs-lookup"><span data-stu-id="c0ce4-249">Regarding policy tips, note that:</span></span>
  
- <span data-ttu-id="c0ce4-250">Endast principtipset från den högst prioriterade, mest restriktiva regeln visas.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-250">Only the policy tip from the highest priority, most restrictive rule will be shown.</span></span> <span data-ttu-id="c0ce4-251">Ett principtips från en regel som blockerar åtkomst till innehåll visas till exempel över ett principtips från en regel som helt enkelt skickar ett meddelande.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-251">For example, a policy tip from a rule that blocks access to content will be shown over a policy tip from a rule that simply sends a notification.</span></span> <span data-ttu-id="c0ce4-252">Detta förhindrar att människor ser en kaskad av principtips.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-252">This prevents people from seeing a cascade of policy tips.</span></span>
    
- <span data-ttu-id="c0ce4-253">Om principtipsen i den mest restriktiva regeln tillåter personer att åsidosätta regeln åsidosätter åsidosätter du också alla andra regler som innehållet matchade.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-253">If the policy tips in the most restrictive rule allow people to override the rule, then overriding this rule also overrides any other rules that the content matched.</span></span>
    
## <a name="tuning-rules-to-make-them-easier-or-harder-to-match"></a><span data-ttu-id="c0ce4-254">Justeringsregler för att göra dem enklare eller svårare att matcha</span><span class="sxs-lookup"><span data-stu-id="c0ce4-254">Tuning rules to make them easier or harder to match</span></span>

<span data-ttu-id="c0ce4-255">När personer har skapat och aktiverar sina DLP-principer stöter de ibland på följande problem:</span><span class="sxs-lookup"><span data-stu-id="c0ce4-255">After people create and turn on their DLP policies, they sometimes run into these issues:</span></span>
  
- <span data-ttu-id="c0ce4-256">För mycket innehåll **som inte är** känslig information matchar reglerna – med andra ord för många falska positiva identifieringar.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-256">Too much content that **is not** sensitive information matches the rules — in other words, too many false positives.</span></span> 
    
- <span data-ttu-id="c0ce4-257">För lite innehåll **som är** känslig information matchar reglerna.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-257">Too little content that **is** sensitive information matches the rules.</span></span> <span data-ttu-id="c0ce4-258">Med andra ord tillämpas inte skyddsåtgärderna på känslig information.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-258">In other words, the protective actions aren't being enforced on the sensitive information.</span></span> 
    
<span data-ttu-id="c0ce4-259">För att åtgärda dessa problem kan du justera dina regler genom att justera antalet instanser och matcha noggrannheten så att det blir svårare eller enklare för innehåll att matcha reglerna.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-259">To address these issues, you can tune your rules by adjusting the instance count and match accuracy to make it harder or easier for content to match the rules.</span></span> <span data-ttu-id="c0ce4-260">Varje känslig informationstyp som används i en regel har både antal instanser och matchningsnoggrannhet.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-260">Each sensitive information type used in a rule has both an instance count and match accuracy.</span></span>
  
### <a name="instance-count"></a><span data-ttu-id="c0ce4-261">Antal instanser</span><span class="sxs-lookup"><span data-stu-id="c0ce4-261">Instance count</span></span>

<span data-ttu-id="c0ce4-262">Antalet instanser innebär helt enkelt hur många förekomster av en viss typ av känslig information som måste finnas för att innehållet ska matcha regeln.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-262">Instance count means simply how many occurrences of a specific type of sensitive information must be present for content to match the rule.</span></span> <span data-ttu-id="c0ce4-263">Innehållet matchar till exempel regeln nedan om mellan 1 och 9 unika amerikanska eller brittiska</span><span class="sxs-lookup"><span data-stu-id="c0ce4-263">For example, content matches the rule shown below if between 1 and 9 unique U.S. or U.K.</span></span> <span data-ttu-id="c0ce4-264">passnummer identifieras.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-264">passport numbers are identified.</span></span>

> [!NOTE]
> <span data-ttu-id="c0ce4-265">Antalet instanser innehåller endast **unika** matchningar för känsliga informationstyper och nyckelord.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-265">The instance count includes only **unique** matches for sensitive information types and keywords.</span></span> <span data-ttu-id="c0ce4-266">Om ett e-postmeddelande till exempel innehåller 10 förekomster av samma kreditkortsnummer räknas dessa 10 händelser som en enda instans av ett kreditkortsnummer.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-266">For example, if an email contains 10 occurrences of the same credit card number, those 10 occurrences count as a single instance of a credit card number.</span></span>
  
<span data-ttu-id="c0ce4-267">Om du vill använda antalet instanser för att finjustera regler är vägledningen enkel:</span><span class="sxs-lookup"><span data-stu-id="c0ce4-267">To use instance count to tune rules, the guidance is straightforward:</span></span>
  
- <span data-ttu-id="c0ce4-268">Om du vill göra regeln enklare att matcha minskar du **antalet minuter** och/eller ökar **det maximala** antalet.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-268">To make the rule easier to match, decrease the **min** count and/or increase the **max** count.</span></span> <span data-ttu-id="c0ce4-269">Du kan också ange **max till** **valfri genom** att ta bort det numeriska värdet.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-269">You can also set **max** to **any** by deleting the numerical value.</span></span> 
    
- <span data-ttu-id="c0ce4-270">Om du vill göra regeln svårare att matcha ökar du **antalet minuter.**</span><span class="sxs-lookup"><span data-stu-id="c0ce4-270">To make the rule harder to match, increase the **min** count.</span></span> 
    
<span data-ttu-id="c0ce4-271">Vanligtvis använder du mindre restriktiva åtgärder, till exempel att skicka användarmeddelanden, i en regel med lägre antal instanser (till exempel 1-9).</span><span class="sxs-lookup"><span data-stu-id="c0ce4-271">Typically, you use less restrictive actions, such as sending user notifications, in a rule with a lower instance count (for example, 1-9).</span></span> <span data-ttu-id="c0ce4-272">Och du använder mer restriktiva åtgärder, till exempel att begränsa åtkomsten till innehåll utan att tillåta användar åsidosättningar, i en regel med ett högre instans antal (till exempel 10-any).</span><span class="sxs-lookup"><span data-stu-id="c0ce4-272">And you use more restrictive actions, such as restricting access to content without allowing user overrides, in a rule with a higher instance count (for example, 10-any).</span></span>
  
![Antalet instanser i regelredigeraren](../media/e7ea3c12-72c5-4bb3-9590-c924c665e84d.png)
  
### <a name="match-accuracy"></a><span data-ttu-id="c0ce4-274">Matcha noggrannhet</span><span class="sxs-lookup"><span data-stu-id="c0ce4-274">Match accuracy</span></span>

<span data-ttu-id="c0ce4-275">Som beskrivits ovan definieras och upptäcks en känslig informationstyp med hjälp av en kombination av olika typer av bevis.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-275">As described above, a sensitive information type is defined and detected by using a combination of different types of evidence.</span></span> <span data-ttu-id="c0ce4-276">Vanligtvis definieras en känslig informationstyp av flera sådana kombinationer, så kallade mönster.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-276">Commonly, a sensitive information type is defined by multiple such combinations, called patterns.</span></span> <span data-ttu-id="c0ce4-277">Ett mönster som kräver mindre bevis har en lägre matchningsnoggrannhet (eller konfidensnivå), medan ett mönster som kräver mer bevis har en högre matchningsnoggrannhet (eller konfidensnivå).</span><span class="sxs-lookup"><span data-stu-id="c0ce4-277">A pattern that requires less evidence has a lower match accuracy (or confidence level), while a pattern that requires more evidence has a higher match accuracy (or confidence level).</span></span> <span data-ttu-id="c0ce4-278">Mer information om de faktiska mönster och konfidensnivåer som används av alla känsliga informationstyper finns i [Definitioner av känsliga informationstyper](sensitive-information-type-entity-definitions.md).</span><span class="sxs-lookup"><span data-stu-id="c0ce4-278">To learn more about the actual patterns and confidence levels used by every sensitive information type, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md).</span></span>
  
<span data-ttu-id="c0ce4-279">Den känsliga informationstypen kreditkortsnummer definieras till exempel av två mönster:</span><span class="sxs-lookup"><span data-stu-id="c0ce4-279">For example, the sensitive information type named Credit Card Number is defined by two patterns:</span></span>
  
- <span data-ttu-id="c0ce4-280">Ett mönster med 65% förtroende som kräver:</span><span class="sxs-lookup"><span data-stu-id="c0ce4-280">A pattern with 65% confidence that requires:</span></span>
    
  - <span data-ttu-id="c0ce4-281">Ett nummer i formatet på ett kreditkortsnummer.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-281">A number in the format of a credit card number.</span></span>
    
  - <span data-ttu-id="c0ce4-282">Ett nummer som passerar kontrollsumman.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-282">A number that passes the checksum.</span></span>
    
- <span data-ttu-id="c0ce4-283">Ett mönster med 85% förtroende som kräver:</span><span class="sxs-lookup"><span data-stu-id="c0ce4-283">A pattern with 85% confidence that requires:</span></span>
    
  - <span data-ttu-id="c0ce4-284">Ett nummer i formatet på ett kreditkortsnummer.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-284">A number in the format of a credit card number.</span></span>
    
  - <span data-ttu-id="c0ce4-285">Ett nummer som passerar kontrollsumman.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-285">A number that passes the checksum.</span></span>
    
  - <span data-ttu-id="c0ce4-286">Ett nyckelord eller ett utgångsdatum i rätt format.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-286">A keyword or an expiration date in the right format.</span></span>
    
<span data-ttu-id="c0ce4-287">Du kan använda dessa förtroendenivåer (eller matcha noggrannhet) i dina regler.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-287">You can use these confidence levels (or match accuracy) in your rules.</span></span> <span data-ttu-id="c0ce4-288">Vanligtvis använder du mindre restriktiva åtgärder, till exempel att skicka användaraviseringar, i en regel med lägre matchningsnoggrannhet.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-288">Typically, you use less restrictive actions, such as sending user notifications, in a rule with lower match accuracy.</span></span> <span data-ttu-id="c0ce4-289">Och du använder mer restriktiva åtgärder, till exempel att begränsa åtkomsten till innehåll utan att tillåta användaråsidosättning, i en regel med högre matchningsnoggrannhet.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-289">And you use more restrictive actions, such as restricting access to content without allowing user overrides, in a rule with higher match accuracy.</span></span>
  
<span data-ttu-id="c0ce4-290">Det är viktigt att förstå att när en viss typ av känslig information, till exempel ett kreditkortsnummer, identifieras i innehåll returneras endast en enda konfidensnivå:</span><span class="sxs-lookup"><span data-stu-id="c0ce4-290">It's important to understand that when a specific type of sensitive information, such as a credit card number, is identified in content, only a single confidence level is returned:</span></span>
  
- <span data-ttu-id="c0ce4-291">Om alla matchningar är för ett enda mönster returneras konfidensnivån för det mönstret.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-291">If all of the matches are for a single pattern, the confidence level for that pattern is returned.</span></span>
    
- <span data-ttu-id="c0ce4-292">Om det finns matchningar för mer än ett mönster (det vill säga det finns matchningar med två olika konfidensnivåer) returneras en konfidensnivå som är högre än något av de enskilda mönstren ensam.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-292">If there are matches for more than one pattern (that is, there are matches with two different confidence levels), a confidence level higher than any of the single patterns alone is returned.</span></span> <span data-ttu-id="c0ce4-293">Det här är den svåra delen.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-293">This is the tricky part.</span></span> <span data-ttu-id="c0ce4-294">För ett kreditkort, om till exempel både 65% och 85% mönster matchas, är konfidensnivån som returneras för den känsliga informationstypen större än 90% eftersom mer bevis betyder mer förtroende.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-294">For example, for a credit card, if both the 65% and 85% patterns are matched, the confidence level returned for that sensitive information type is greater than 90% because more evidence means more confidence.</span></span>
    
<span data-ttu-id="c0ce4-295">Så om du vill skapa två ömsesidigt uteslutande regler för kreditkort, en för 65% matchnoggrannhet och en för 85% matchnoggrannhet, skulle intervallen för matchnoggrannhet se ut så här.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-295">So if you want to create two mutually exclusive rules for credit cards, one for the 65% match accuracy and one for the 85% match accuracy, the ranges for match accuracy would look like this.</span></span> <span data-ttu-id="c0ce4-296">Den första regeln plockar bara upp matchningar av 65% -mönstret.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-296">The first rule picks up only matches of the 65% pattern.</span></span> <span data-ttu-id="c0ce4-297">Den andra regeln plockar upp matcher med **minst en matchning på** 85% och kan potentiellt ha **andra** matcher med lägre självförtroende.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-297">The second rule picks up matches with **at least one** 85% match and **can potentially have** other lower-confidence matches.</span></span> 
  
![Två regler med olika intervall för matchnoggrannhet](../media/21bdfe36-7a91-4347-8098-11809a92f9a4.png)
  
<span data-ttu-id="c0ce4-299">Av dessa skäl är vägledningen för att skapa regler med olika matchningsnoggrannhet:</span><span class="sxs-lookup"><span data-stu-id="c0ce4-299">For these reasons, the guidance for creating rules with different match accuracies is:</span></span>
  
- <span data-ttu-id="c0ce4-300">Den lägsta konfidensnivån använder vanligtvis samma värde för **min** och **max** (inte ett intervall).</span><span class="sxs-lookup"><span data-stu-id="c0ce4-300">The lowest confidence level typically uses the same value for **min** and **max** (not a range).</span></span> 
    
- <span data-ttu-id="c0ce4-301">Den högsta konfidensnivån är vanligtvis ett intervall från strax över den lägre konfidensnivån till 100.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-301">The highest confidence level is typically a range from just above the lower confidence level to 100.</span></span>
    
- <span data-ttu-id="c0ce4-302">Eventuella mellannivåer varierar vanligtvis från strax över den lägre konfidensnivån till strax under den högre konfidensnivån.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-302">Any in-between confidence levels typically range from just above the lower confidence level to just below the higher confidence level.</span></span>
    
## <a name="using-a-retention-label-as-a-condition-in-a-dlp-policy"></a><span data-ttu-id="c0ce4-303">Använda en kvarhållningsetikett som ett villkor i en DLP-princip</span><span class="sxs-lookup"><span data-stu-id="c0ce4-303">Using a retention label as a condition in a DLP policy</span></span>

<span data-ttu-id="c0ce4-304">När du använder en tidigare skapad och publicerad [kvarhållningsetikett](retention.md#retention-labels) som ett villkor i en DLP-princip finns det några saker att vara medveten om:</span><span class="sxs-lookup"><span data-stu-id="c0ce4-304">When you use a previously created and published [retention label](retention.md#retention-labels) as a condition in a DLP policy, there are some things to be aware of:</span></span>

- <span data-ttu-id="c0ce4-305">Kvarhållningsetiketten måste skapas och publiceras innan du försöker använda den som ett villkor i en DLP-princip.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-305">The retention label must be created and published before you attempt to use it as a condition in a DLP policy.</span></span>
- <span data-ttu-id="c0ce4-306">Publicerade lagringsetiketter kan ta från en till sju dagar att synkronisera. Mer information finns i När [lagringsetiketter blir tillgängliga för](create-apply-retention-labels.md#when-retention-labels-become-available-to-apply) lagringsetiketter som publiceras i en bevarandeprincip och [Hur lång tid det tar för lagringsetiketter att träda i kraft](apply-retention-labels-automatically.md#how-long-it-takes-for-retention-labels-to-take-effect) för lagringsetiketter som publiceras automatiskt.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-306">Published retention labels can take from one to seven days to sync. For more information, see [When retention labels become available to apply](create-apply-retention-labels.md#when-retention-labels-become-available-to-apply) for retention labels published in a retention policy, and [How long it takes for retention labels to take effect](apply-retention-labels-automatically.md#how-long-it-takes-for-retention-labels-to-take-effect) for retention labels that are auto-published.</span></span>
- <span data-ttu-id="c0ce4-307">Att använda en kvarhållningsetikett i en princip \*\*stöds bara för objekt i SharePoint och OneDrive\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-307">Using a retention label in a policy \*\*is only supported for items in SharePoint and OneDrive\*\*\*.</span></span>

  ![Etiketter som ett villkor](../media/5b1752b4-a129-4a88-b010-8dcf8a38bb09.png)

  <span data-ttu-id="c0ce4-309">Du kanske vill använda en kvarhållningsetikett i en DLP-princip om du har objekt som är under kvarhållning och disposition, och du också vill tillämpa andra kontroller på dem, till exempel:</span><span class="sxs-lookup"><span data-stu-id="c0ce4-309">You might want to use a retention label in a DLP policy if you have items that are under retention and disposition, and you also want to apply other controls to them, for example:</span></span>

  - <span data-ttu-id="c0ce4-310">Du publicerade en lagringsetikett **med namnet skatteår 2018**, som när den tillämpas på skattedokument från 2018 som lagras i SharePoint behåller dem i 10 år och sedan kasserar dem.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-310">You published a retention label named **tax year 2018**, which when applied to tax documents from 2018 that are stored in SharePoint retains them for 10 years then disposes of them.</span></span> <span data-ttu-id="c0ce4-311">Du vill inte heller att dessa objekt ska delas utanför organisationen, vilket du kan göra med en DLP-princip.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-311">You also don't want those items being shared outside your organization, which you can do with a DLP policy.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="c0ce4-312">Det här felet visas om du anger en lagringsetikett som ett villkor i en DLP-princip och du även inkluderar Exchange och/eller Teams som plats: **"Skydda märkt innehåll i e-postmeddelanden och teammeddelanden stöds inte. Ta antingen bort etiketten nedan eller stäng Exchange och Teams som en plats.".**</span><span class="sxs-lookup"><span data-stu-id="c0ce4-312">You'll get this error if you specify a retention label as a condition in a DLP policy and you also include Exchange and/or Teams as a location: **"Protecting labeled content in email and teams messages isn't supported. Either remove the label below or turn off Exchange and Teams as a location."**</span></span> <span data-ttu-id="c0ce4-313">Detta beror på Exchange transporten inte utvärderar etikettmetadata under meddelandeöverföring och leverans.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-313">This is because Exchange transport does not evaluate the label metadata during message submission and delivery.</span></span> 

### <a name="using-a-sensitivity-label-as-a-condition-in-a-dlp-policy"></a><span data-ttu-id="c0ce4-314">Använda en känslighetsetikett som ett villkor i en DLP-princip</span><span class="sxs-lookup"><span data-stu-id="c0ce4-314">Using a sensitivity label as a condition in a DLP policy</span></span>

<span data-ttu-id="c0ce4-315">[Läs mer om](./dlp-sensitivity-label-as-condition.md) hur du använder känslighetsetiketten som ett villkor i DLP-principer.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-315">[Learn more](./dlp-sensitivity-label-as-condition.md) about using Sensitivity label as a condition in DLP policies.</span></span>
  
### <a name="how-this-feature-relates-to-other-features"></a><span data-ttu-id="c0ce4-316">Hur den här funktionen relaterar till andra funktioner</span><span class="sxs-lookup"><span data-stu-id="c0ce4-316">How this feature relates to other features</span></span>

<span data-ttu-id="c0ce4-317">Flera funktioner kan tillämpas på innehåll som innehåller känslig information:</span><span class="sxs-lookup"><span data-stu-id="c0ce4-317">Several features can be applied to content containing sensitive information:</span></span>
  
- <span data-ttu-id="c0ce4-318">En [lagringsetikett och en bevarande princip kan](retention.md) båda genomdriva **kvarhållningsåtgärder** för det här innehållet.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-318">A [retention label and a retention policy](retention.md) can both enforce **retention** actions on this content.</span></span> 
    
- <span data-ttu-id="c0ce4-319">En DLP-princip kan genomdriva **skyddsåtgärder** för det här innehållet.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-319">A DLP policy can enforce **protection** actions on this content.</span></span> <span data-ttu-id="c0ce4-320">Och innan dessa åtgärder verkställs kan en DLP-policy kräva att andra villkor uppfylls utöver innehållet som innehåller en etikett.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-320">And before enforcing these actions, a DLP policy can require other conditions to be met in addition to the content containing a label.</span></span> 
    
![Diagram över funktioner som kan tillämpas på känslig information](../media/dd410f97-a3a3-455c-a1e9-7ed8ae6893d6.png)
  
<span data-ttu-id="c0ce4-322">Observera att en DLP-princip har en rikare identifierings funktion än en etikett eller bevarande princip som tillämpas på känslig information.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-322">Note that a DLP policy has a richer detection capability than a label or retention policy applied to sensitive information.</span></span> <span data-ttu-id="c0ce4-323">En DLP-princip kan genomdriva skyddsåtgärder på innehåll som innehåller känslig information, och om känslig information tas bort från innehållet ångras dessa skyddsåtgärder nästa gång innehållet skannas.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-323">A DLP policy can enforce protective actions on content containing sensitive information, and if the sensitive information is removed from the content, those protective actions are undone the next time the content's scanned.</span></span> <span data-ttu-id="c0ce4-324">Men om en bevarande princip eller etikett tillämpas på innehåll som innehåller känslig information är det en engångs åtgärd som inte ångras även om känslig information tas bort.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-324">But if a retention policy or label is applied to content containing sensitive information, that's a one-time action that won't be undone even if the sensitive information is removed.</span></span>
  
<span data-ttu-id="c0ce4-325">Genom att använda en etikett som ett villkor i en DLP-princip kan du genomdriva både kvarhållnings- och skyddsåtgärder på innehåll med den etiketten.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-325">By using a label as a condition in a DLP policy, you can enforce both retention and protection actions on content with that label.</span></span> <span data-ttu-id="c0ce4-326">Du kan tänka på innehåll som innehåller en etikett exakt som innehåll som innehåller känslig information - både en etikett och en känslig informationstyp är egenskaper som används för att klassificera innehåll, så att du kan genomdriva åtgärder för det innehållet.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-326">You can think of content containing a label exactly like content containing sensitive information - both a label and a sensitive information type are properties used to classify content, so that you can enforce actions on that content.</span></span>
  
![Diagram över DLP-principen med etiketten som villkor](../media/4538fd8f-fb74-4743-bc22-a5de33adfebb.png)
  
## <a name="simple-settings-vs-advanced-settings"></a><span data-ttu-id="c0ce4-328">Enkla inställningar kontra avancerade inställningar</span><span class="sxs-lookup"><span data-stu-id="c0ce4-328">Simple settings vs. advanced settings</span></span>

<span data-ttu-id="c0ce4-329">När du skapar en DLP-princip väljer du mellan enkla eller avancerade inställningar:</span><span class="sxs-lookup"><span data-stu-id="c0ce4-329">When you create a DLP policy, you'll choose between simple or advanced settings:</span></span>
  
- <span data-ttu-id="c0ce4-330">**Enkla inställningar** gör det enkelt att skapa den vanligaste typen av DLP-princip utan att använda regelredigeraren för att skapa eller ändra regler.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-330">**Simple settings** make it easy to create the most common type of DLP policy without using the rule editor to create or modify rules.</span></span> 
    
- <span data-ttu-id="c0ce4-331">**Avancerade inställningar använder** regelredigeraren för att ge dig fullständig kontroll över varje inställning för din DLP-princip.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-331">**Advanced settings** use the rule editor to give you complete control over every setting for your DLP policy.</span></span> 
    
<span data-ttu-id="c0ce4-332">Oroa dig inte, under täcket fungerar enkla inställningar och avancerade inställningar exakt likadant, genom att genomdriva regler som består av villkor och åtgärder – bara med enkla inställningar ser du inte regelredigeraren.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-332">Don't worry, under the covers, simple settings and advanced settings work exactly the same, by enforcing rules comprised of conditions and actions—only with simple settings, you don't see the rule editor.</span></span> <span data-ttu-id="c0ce4-333">Det är ett snabbt sätt att skapa en DLP-princip.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-333">It's a quick way to create a DLP policy.</span></span>
  
### <a name="simple-settings"></a><span data-ttu-id="c0ce4-334">Enkla inställningar</span><span class="sxs-lookup"><span data-stu-id="c0ce4-334">Simple settings</span></span>

<span data-ttu-id="c0ce4-335">Det överlägset vanligaste DLP-scenariot är att skapa en princip för att skydda innehåll som innehåller känslig information från att delas med personer utanför organisationen och vidta en automatisk åtgärd för att åtgärda åtgärder som att begränsa vem som kan komma åt innehållet, skicka slutanvändar- eller administratörsmeddelanden och granska händelsen för senare granskning.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-335">By far, the most common DLP scenario is creating a policy to help protect content containing sensitive information from being shared with people outside your organization, and taking an automatic remediating action such as restricting who can access the content, sending end-user or admin notifications, and auditing the event for later investigation.</span></span> <span data-ttu-id="c0ce4-336">Personer använder DLP för att förhindra oavsiktligt utlämnande av känslig information.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-336">People use DLP to help prevent the inadvertent disclosure of sensitive information.</span></span>
  
<span data-ttu-id="c0ce4-337">Om du vill förenkla uppnåendet av det här målet kan du välja Använd enkla inställningar när du **skapar en DLP-princip**.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-337">To simplify achieving this goal, when you create a DLP policy, you can choose **Use simple settings**.</span></span> <span data-ttu-id="c0ce4-338">Dessa inställningar ger allt du behöver för att implementera den vanligaste DLP-principen, utan att behöva gå in i regelredigeraren.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-338">These settings provide everything you need to implement the most common DLP policy, without having to go into the rule editor.</span></span>
  
![DLP-alternativ för enkla och avancerade inställningar](../media/33c93824-ead5-43b6-9c3e-fd1630c92a7d.png)
  
### <a name="advanced-settings"></a><span data-ttu-id="c0ce4-340">Avancerade inställningar</span><span class="sxs-lookup"><span data-stu-id="c0ce4-340">Advanced settings</span></span>

<span data-ttu-id="c0ce4-341">Om du behöver skapa mer anpassade DLP-principer kan du välja **Använd avancerade inställningar**.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-341">If you need to create more customized DLP policies, you can choose **Use advanced settings**.</span></span>
  
<span data-ttu-id="c0ce4-342">De avancerade inställningarna ger dig regelredigeraren, där du har full kontroll över alla möjliga alternativ, inklusive antalet instanser och matchningsnoggrannheten (konfidensnivå) för varje regel.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-342">The advanced settings present you with the rule editor, where you have full control over every possible option, including the instance count and match accuracy (confidence level) for each rule.</span></span>
  
<span data-ttu-id="c0ce4-343">Om du snabbt vill gå till ett avsnitt klickar du på ett objekt i regelredigerarens övre navigering för att gå till det avsnittet nedan.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-343">To jump to a section quickly, click an item in the top navigation of the rule editor to go to that section below.</span></span>
  
![Den översta navigeringsmenyn för DLP-regelredigeraren](../media/c527b97f-ca53-4c79-ad19-1a63be8a8ecc.png)
  
## <a name="dlp-policy-templates"></a><span data-ttu-id="c0ce4-345">DLP-principmallar</span><span class="sxs-lookup"><span data-stu-id="c0ce4-345">DLP policy templates</span></span>

<span data-ttu-id="c0ce4-346">Det första steget i att skapa en DLP-princip är att välja vilken information som ska skyddas.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-346">The first step in creating a DLP policy is choosing what information to protect.</span></span> <span data-ttu-id="c0ce4-347">Genom att börja med en DLP-mall sparar du arbetet med att skapa en ny uppsättning regler från grunden och ta reda på vilka typer av information som ska inkluderas som standard.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-347">By starting with a DLP template, you save the work of building a new set of rules from scratch, and figuring out which types of information should be included by default.</span></span> <span data-ttu-id="c0ce4-348">Du kan sedan lägga till eller ändra dessa krav för att finjustera regeln så att den uppfyller organisationens specifika krav.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-348">You can then add to or modify these requirements to fine tune the rule to meet your organization's specific requirements.</span></span>
  
<span data-ttu-id="c0ce4-349">En förkonfigurerad DLP-principmall kan hjälpa dig att identifiera specifika typer av känslig information, till exempel HIPAA-data, PCI-DSS-data, Gramm-Leach-Bliley Act-data eller till och med språkspecifik personligt identifierbar information (P.I.).</span><span class="sxs-lookup"><span data-stu-id="c0ce4-349">A preconfigured DLP policy template can help you detect specific types of sensitive information, such as HIPAA data, PCI-DSS data, Gramm-Leach-Bliley Act data, or even locale-specific personally identifiable information (P.I.).</span></span> <span data-ttu-id="c0ce4-350">För att göra det enkelt för dig att hitta och skydda vanliga typer av känslig information innehåller de principmallar som ingår i Microsoft 365 redan de vanligaste känsliga informationstyperna som krävs för att du ska komma igång.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-350">To make it easy for you to find and protect common types of sensitive information, the policy templates included in Microsoft 365 already contain the most common sensitive information types necessary for you to get started.</span></span>
  
![Lista över mallar för policyer för förebyggande av dataförluster med fokus på mall för U.S. Patriot Act](../media/791b2403-430b-4987-8643-cc20abbd8148.png)
  
<span data-ttu-id="c0ce4-352">Din organisation kan också ha sina egna specifika krav, i vilket fall du kan skapa en DLP-princip från grunden genom att välja **alternativet Anpassad princip.**</span><span class="sxs-lookup"><span data-stu-id="c0ce4-352">Your organization may also have its own specific requirements, in which case you can create a DLP policy from scratch by choosing the **Custom policy** option.</span></span> <span data-ttu-id="c0ce4-353">En anpassad princip är tom och innehåller inga färdiga regler.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-353">A custom policy is empty and contains no premade rules.</span></span> 
  
<!-- ## Roll out DLP policies gradually with test mode

rehomed to Plan for DLP

When you create your DLP policies, you should consider rolling them out gradually to assess their impact and test their effectiveness before fully enforcing them. For example, you don't want a new DLP policy to unintentionally block access to thousands of documents that people require access to in order to get their work done.
  
If you're creating DLP policies with a large potential impact, we recommend following this sequence:
  
1. **Start in test mode without Policy Tips** and then use the DLP reports and any incident reports to assess the impact. You can use DLP reports to view the number, location, type, and severity of policy matches. Based on the results, you can fine tune the rules as needed. In test mode, DLP policies will not impact the productivity of people working in your organization. 
    
2. **Move to Test mode with notifications and Policy Tips** so that you can begin to teach users about your compliance policies and prepare them for the rules that are going to be applied. At this stage, you can also ask users to report false positives so that you can further refine the rules. 
    
3. **Start full enforcement on the policies** so that the actions in the rules are applied and the content's protected. Continue to monitor the DLP reports and any incident reports or notifications to make sure that the results are what you intend. 

    ![Options for using test mode and turning on policy](../media/49fafaac-c6cb-41de-99c4-c43c3e380c3a.png)

    You can turn off a DLP policy at any time, which affects all rules in the policy. However, each rule can also be turned off individually by toggling its status in the rule editor.

    ![Options for turning off a rule in a policy](../media/f7b258ff-1b8b-4127-b580-83c6492f2bef.png)

    You can also change the priority of multiple rules in a policy. To do that, open a policy for editing. In a row for a rule, choose the ellipses (**...**), and then choose an option, such as **Move down** or **Bring to last**.

    > [!div class="mx-imgBorder"]
    > ![Set rule priority](../media/dlp-set-rule-priority.png)-->
  
## <a name="dlp-reports"></a><span data-ttu-id="c0ce4-354">DLP-rapporter</span><span class="sxs-lookup"><span data-stu-id="c0ce4-354">DLP reports</span></span>

<span data-ttu-id="c0ce4-355">När du har skapat och aktiverar dina DLP-principer vill du verifiera att de fungerar som du tänkt och hjälper dig att hålla dig kompatibel.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-355">After you create and turn on your DLP policies, you'll want to verify that they're working as you intended and helping you stay compliant.</span></span> <span data-ttu-id="c0ce4-356">Med DLP-rapporter kan du snabbt visa antalet DLP-principer och regelmatchningar över tid och antalet falska positiva identifieringar och åsidosättningar.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-356">With DLP reports, you can quickly view the number of DLP policy and rule matches over time, and the number of false positives and overrides.</span></span> <span data-ttu-id="c0ce4-357">För varje rapport kan du filtrera dessa matchningar efter plats, tidsram och till och med begränsa den till en viss princip, regel eller åtgärd.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-357">For each report, you can filter those matches by location, time frame, and even narrow it down to a specific policy, rule, or action.</span></span>
  
<span data-ttu-id="c0ce4-358">Med DLP-rapporterna kan du få affärsinsikter och:</span><span class="sxs-lookup"><span data-stu-id="c0ce4-358">With the DLP reports, you can get business insights and:</span></span>
  
- <span data-ttu-id="c0ce4-359">Fokusera på vissa tidsperioder och förstå orsakerna till toppar och trender.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-359">Focus on specific time periods and understand the reasons for spikes and trends.</span></span>
    
- <span data-ttu-id="c0ce4-360">Upptäck affärsprocesser som bryter mot organisationens efterlevnadspolicyer.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-360">Discover business processes that violate your organization's compliance policies.</span></span>
    
- <span data-ttu-id="c0ce4-361">Förstå alla affärseffekter i DLP-principerna.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-361">Understand any business impact of the DLP policies.</span></span>
    
<span data-ttu-id="c0ce4-362">Dessutom kan du använda DLP-rapporterna för att finjustera dina DLP-principer när du kör dem.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-362">In addition, you can use the DLP reports to fine tune your DLP policies as you run them.</span></span>
  
![Instrumentpanel för rapporter i Säkerhets- och efterlevnadscenter](../media/6d741252-a0ce-4429-95ba-6c857ecc9a7e.png)
  
## <a name="how-dlp-policies-work"></a><span data-ttu-id="c0ce4-364">Så här fungerar DLP-principer</span><span class="sxs-lookup"><span data-stu-id="c0ce4-364">How DLP policies work</span></span>

<span data-ttu-id="c0ce4-365">DLP upptäcker känslig information med hjälp av djup innehållsanalys (inte bara en enkel textsökning).</span><span class="sxs-lookup"><span data-stu-id="c0ce4-365">DLP detects sensitive information by using deep content analysis (not just a simple text scan).</span></span> <span data-ttu-id="c0ce4-366">Den här djupinnehållsanalysen använder nyckelordsmatchningar, ordlistematchningar, utvärdering av reguljära uttryck, interna funktioner och andra metoder för att identifiera innehåll som matchar dina DLP-principer.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-366">This deep content analysis uses keyword matches, dictionary matches, the evaluation of regular expressions, internal functions, and other methods to detect content that matches your DLP policies.</span></span> <span data-ttu-id="c0ce4-367">Potentiellt anses endast en liten andel av dina data vara känsliga.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-367">Potentially only a small percentage of your data is considered sensitive.</span></span> <span data-ttu-id="c0ce4-368">En DLP-princip kan identifiera, övervaka och automatiskt skydda just dessa data, utan att inverka på eller påverka personer som arbetar med resten av ditt innehåll.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-368">A DLP policy can identify, monitor, and automatically protect just that data, without impeding or affecting people who work with the rest of your content.</span></span>
  
### <a name="policies-are-synced"></a><span data-ttu-id="c0ce4-369">Principer synkroniseras</span><span class="sxs-lookup"><span data-stu-id="c0ce4-369">Policies are synced</span></span>

<span data-ttu-id="c0ce4-370">När du har skapat en DLP-princip i Security &amp; Compliance Center lagras den i ett centralt principarkiv och synkroniseras sedan med de olika innehållskällorna, inklusive:</span><span class="sxs-lookup"><span data-stu-id="c0ce4-370">After you create a DLP policy in the Security &amp; Compliance Center, it's stored in a central policy store, and then synced to the various content sources, including:</span></span>
  
- <span data-ttu-id="c0ce4-371">Exchange Online, och därifrån till Outlook på webben och Outlook.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-371">Exchange Online, and from there to Outlook on the web and Outlook.</span></span>
    
- <span data-ttu-id="c0ce4-372">OneDrive för företag platser.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-372">OneDrive for Business sites.</span></span>
    
- <span data-ttu-id="c0ce4-373">SharePoint Online-webbplatser.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-373">SharePoint Online sites.</span></span>
    
- <span data-ttu-id="c0ce4-374">Office skrivbordsprogram (Excel, PowerPoint och Word).</span><span class="sxs-lookup"><span data-stu-id="c0ce4-374">Office desktop programs (Excel, PowerPoint, and Word).</span></span>

- <span data-ttu-id="c0ce4-375">Microsoft Teams kanaler och chattmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-375">Microsoft Teams channels and chat messages.</span></span>
    
<span data-ttu-id="c0ce4-376">När principen har synkroniserats till rätt platser börjar den utvärdera innehåll och genomdriva åtgärder.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-376">After the policy's synced to the right locations, it starts to evaluate content and enforce actions.</span></span>
<!-- what is the time delay for first deployment of a policy and what is the sync schedule? -->
  
### <a name="policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites"></a><span data-ttu-id="c0ce4-377">Policyutvärdering på OneDrive för företag och SharePoint onlinewebbplatser</span><span class="sxs-lookup"><span data-stu-id="c0ce4-377">Policy evaluation in OneDrive for Business and SharePoint Online sites</span></span>

<span data-ttu-id="c0ce4-378">På alla dina SharePoint Online-webbplatser och OneDrive för företag-webbplatser ändras dokument ständigt – de skapas, redigeras, delas och så vidare.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-378">Across all of your SharePoint Online sites and OneDrive for Business sites, documents are constantly changing — they're continually being created, edited, shared, and so on.</span></span> <span data-ttu-id="c0ce4-379">Detta innebär att dokument kan komma i konflikt med eller bli kompatibla med en DLP-princip när som helst.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-379">This means documents can conflict or become compliant with a DLP policy at any time.</span></span> <span data-ttu-id="c0ce4-380">En person kan till exempel ladda upp ett dokument som inte innehåller känslig information till gruppwebbplatsen, men senare kan en annan person redigera samma dokument och lägga till känslig information i det.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-380">For example, a person can upload a document that contains no sensitive information to their team site, but later, a different person can edit the same document and add sensitive information to it.</span></span>
  
<span data-ttu-id="c0ce4-381">Därför kontrollerar DLP-principer dokument för principmatchningar ofta i bakgrunden.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-381">For this reason, DLP policies check documents for policy matches frequently in the background.</span></span> <span data-ttu-id="c0ce4-382">Du kan se detta som asynkron politisk utvärdering.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-382">You can think of this as asynchronous policy evaluation.</span></span>
<!-- what is the frequency? looks like it is tied to the search crawl schedule -->
  
#### <a name="how-it-works"></a><span data-ttu-id="c0ce4-383">Så här fungerar det</span><span class="sxs-lookup"><span data-stu-id="c0ce4-383">How it works</span></span>
 
<span data-ttu-id="c0ce4-384">När personer lägger till eller ändrar dokument på sina webbplatser skannar sökmotorn innehållet så att du kan söka efter det senare.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-384">As people add or change documents in their sites, the search engine scans the content, so that you can search for it later.</span></span> <span data-ttu-id="c0ce4-385">Medan detta händer genomsöks innehållet också efter känslig information och för att kontrollera om det delas.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-385">While this is happening, the content's also scanned for sensitive information and to check if it's shared.</span></span> <span data-ttu-id="c0ce4-386">All känslig information som hittas lagras säkert i sökindexet, så att endast efterlevnadsteamet kan komma åt den, men inte typiska användare.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-386">Any sensitive information that's found is stored securely in the search index, so that only the compliance team can access it, but not typical users.</span></span> <span data-ttu-id="c0ce4-387">Varje DLP-princip som du har aktiverat körs i bakgrunden (asynkront), söker ofta efter innehåll som matchar en princip och tillämpar åtgärder för att skydda den från oavsiktliga läckor.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-387">Each DLP policy that you've turned on runs in the background (asynchronously), checking search frequently for any content that matches a policy, and applying actions to protect it from inadvertent leaks.</span></span>
  
![Diagram som visar hur DLP-principen utvärderar innehållet asynkront](../media/bdf73099-039a-4909-ae89-ac12c41992ba.png)
  
<!-- conflict with a DLP policy is bad wording -->
<span data-ttu-id="c0ce4-389">Slutligen kan dokument stå i konflikt med en DLP-princip, men de kan också bli kompatibla med en DLP-princip.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-389">Finally, documents can conflict with a DLP policy, but they can also become compliant with a DLP policy.</span></span> <span data-ttu-id="c0ce4-390">Om en person till exempel lägger till kreditkortsnummer i ett dokument kan det leda till att en DLP-princip blockerar åtkomsten till dokumentet automatiskt.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-390">For example, if a person adds credit card numbers to a document, it might cause a DLP policy to block access to the document automatically.</span></span> <span data-ttu-id="c0ce4-391">Men om personen senare tar bort känslig information ångras åtgärden (i det här fallet blockering) automatiskt nästa gång dokumentet utvärderas mot principen.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-391">But if the person later removes the sensitive information, the action (in this case, blocking) is automatically undone the next time the document is evaluated against the policy.</span></span>
  
<span data-ttu-id="c0ce4-392">DLP utvärderar allt innehåll som kan indexeras.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-392">DLP evaluates any content that can be indexed.</span></span> <span data-ttu-id="c0ce4-393">Mer information om vilka filtyper som genomsöks som standard finns i [Standardtillägg för crawlade filnamn och tosparade filtyper i SharePoint Server](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types).</span><span class="sxs-lookup"><span data-stu-id="c0ce4-393">For more information on what file types are crawled by default, see [Default crawled file name extensions and parsed file types in SharePoint Server](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types).</span></span>

> [!NOTE]
> <span data-ttu-id="c0ce4-394">För att förhindra att dokument delas innan DLP-principer hade möjlighet att analysera dem kan delning av nya filer i SharePoint blockeras tills innehållet har indexerats.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-394">In order to prevent documents from being shared before DLP policies had the opportunity to analyze them, sharing of new files in SharePoint can be blocked until its content has been indexed.</span></span> <span data-ttu-id="c0ce4-395">Se Markera [nya filer som känsliga som standard](/sharepoint/sensitive-by-default) för detaljerad information.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-395">See, [Mark new files as sensitive by default](/sharepoint/sensitive-by-default) for detailed information.</span></span> 
  
### <a name="policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web"></a><span data-ttu-id="c0ce4-396">Policyutvärdering i Exchange Online, Outlook och Outlook på webben</span><span class="sxs-lookup"><span data-stu-id="c0ce4-396">Policy evaluation in Exchange Online, Outlook, and Outlook on the web</span></span>

<span data-ttu-id="c0ce4-397">När du skapar en DLP-princip som innehåller Exchange Online som plats synkroniseras principen från Office 365 Security &amp; Compliance Center till Exchange Online och sedan från Exchange Online till Outlook på webben och Outlook.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-397">When you create a DLP policy that includes Exchange Online as a location, the policy's synced from the Office 365 Security &amp; Compliance Center to Exchange Online, and then from Exchange Online to Outlook on the web and Outlook.</span></span>
  
<span data-ttu-id="c0ce4-398">När ett meddelande skrivs i Outlook kan användaren se principtips när innehållet som skapas utvärderas mot DLP-principer.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-398">When a message is being composed in Outlook, the user can see policy tips as the content being created is evaluated against DLP policies.</span></span> <span data-ttu-id="c0ce4-399">Och när ett meddelande har skickats utvärderas det mot DLP-principer som en normal del av e-postflödet, tillsammans med Exchange-e-postflödesregler (även kallade transportregler) och DLP-principer som skapats i administrationscentret för Exchange.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-399">And after a message is sent, it's evaluated against DLP policies as a normal part of mail flow, along with Exchange mail flow rules (also known as transport rules) and DLP policies created in the Exchange admin center.</span></span> <span data-ttu-id="c0ce4-400">DLP-principer söker igenom både meddelandet och eventuella bifogade filer.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-400">DLP policies scan both the message and any attachments.</span></span>
  
### <a name="policy-evaluation-in-the-office-desktop-programs"></a><span data-ttu-id="c0ce4-401">Principutvärdering i Office skrivbordsprogram</span><span class="sxs-lookup"><span data-stu-id="c0ce4-401">Policy evaluation in the Office desktop programs</span></span>

<!-- same capability to identify sensitive information line conflates sensitive information types and such -->
<span data-ttu-id="c0ce4-402">Excel, PowerPoint och Word samma funktion för att identifiera känslig information och tillämpa DLP-principer som SharePoint Online och OneDrive för företag.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-402">Excel, PowerPoint, and Word include the same capability to identify sensitive information and apply DLP policies as SharePoint Online and OneDrive for Business.</span></span> <span data-ttu-id="c0ce4-403">Dessa Office-program synkroniserar sina DLP-principer direkt från det centrala principarkivet och utvärderar sedan kontinuerligt innehållet mot DLP-principerna när personer arbetar med dokument som öppnas från en webbplats som ingår i en DLP-princip.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-403">These Office programs sync their DLP policies directly from the central policy store, and then continuously evaluate the content against the DLP policies when people work with documents opened from a site that's included in a DLP policy.</span></span>
  
<span data-ttu-id="c0ce4-404">DLP-policyutvärdering Office är utformad för att inte påverka programmens prestanda eller produktiviteten hos personer som arbetar med innehåll.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-404">DLP policy evaluation in Office is designed not to affect the performance of the programs or the productivity of people working on content.</span></span> <span data-ttu-id="c0ce4-405">Om de arbetar med ett stort dokument, eller om användarens dator är upptagen, kan det ta några sekunder innan ett principtips visas.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-405">If they're working on a large document, or the user's computer is busy, it might take a few seconds for a policy tip to appear.</span></span>

### <a name="policy-evaluation-in-microsoft-teams"></a><span data-ttu-id="c0ce4-406">Politisk utvärdering i Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c0ce4-406">Policy evaluation in Microsoft Teams</span></span>
 <!--what do you mean that it's synched to user accounts?  I thought DLP policies were applied to locations not users like sensitivity labels are  -->

<span data-ttu-id="c0ce4-407">När du skapar en DLP-princip som innehåller Microsoft Teams som plats synkroniseras principen från Office 365 Security &amp; Compliance Center till användarkonton och Microsoft Teams-kanaler och chattmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-407">When you create a DLP policy that includes Microsoft Teams as a location, the policy's synced from the Office 365 Security &amp; Compliance Center to user accounts and Microsoft Teams channels and chat messages.</span></span> <span data-ttu-id="c0ce4-408">Beroende på hur DLP-principer konfigureras kan meddelandet blockeras eller återkallas när någon försöker dela känslig information i en Microsoft Teams-chatt eller kanalmeddelande.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-408">Depending on how DLP policies are configured, when someone attempts to share sensitive information in a Microsoft Teams chat or channel message, the message can be blocked or revoked.</span></span> <span data-ttu-id="c0ce4-409">Och dokument som innehåller känslig information och som delas med gäster (externa användare) öppnas inte för dessa användare.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-409">And, documents that contain sensitive information and that are shared with guests (external users) won't open for those users.</span></span> <span data-ttu-id="c0ce4-410">Mer information finns i [Dataförlustförebyggande och Microsoft Teams](dlp-microsoft-teams.md).</span><span class="sxs-lookup"><span data-stu-id="c0ce4-410">To learn more, see [Data loss prevention and Microsoft Teams](dlp-microsoft-teams.md).</span></span>
 
## <a name="permissions"></a><span data-ttu-id="c0ce4-411">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="c0ce4-411">Permissions</span></span>

<span data-ttu-id="c0ce4-412">Medlemmar i ditt efterlevnadsteam som skapar DLP-principer behöver behörighet till Security &amp; Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-412">Members of your compliance team who will create DLP policies need permissions to the Security &amp; Compliance Center.</span></span> <span data-ttu-id="c0ce4-413">Som standard har din klient administratör åtkomst till den här platsen och kan ge efterlevnadsansvariga och andra personer åtkomst till Security Compliance Center, utan att ge dem &amp; alla behörigheter för en klient administratör. För att göra detta rekommenderar vi att du:</span><span class="sxs-lookup"><span data-stu-id="c0ce4-413">By default, your tenant admin will have access to this location and can give compliance officers and other people access to the Security &amp; Compliance Center, without giving them all of the permissions of a tenant admin. To do this, we recommend that you:</span></span>
  
1. <span data-ttu-id="c0ce4-414">Skapa en grupp i Microsoft 365 lägga till efterlevnadsansvariga i den.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-414">Create a group in Microsoft 365 and add compliance officers to it.</span></span>
    
2. <span data-ttu-id="c0ce4-415">Skapa en rollgrupp på sidan **Behörigheter** i Security &amp; Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-415">Create a role group on the **Permissions** page of the Security &amp; Compliance Center.</span></span> 

3. <span data-ttu-id="c0ce4-416">När du skapar rollgruppen använder du avsnittet **Välj roller för** att lägga till följande roll i rollgruppen: **DLP Compliance Management**.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-416">While creating the role group, use the **Choose Roles** section to add the following role to the Role Group: **DLP Compliance Management**.</span></span>
    
4. <span data-ttu-id="c0ce4-417">Använd avsnittet **Välj medlemmar om** du vill lägga Microsoft 365 den grupp som du har skapat tidigare i rollgruppen.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-417">Use the **Choose Members** section to add the Microsoft 365 group you created before to the role group.</span></span>

<span data-ttu-id="c0ce4-418">Du kan också skapa en rollgrupp med skrivbehörighet till DLP-principerna och DLP-rapporterna genom att bevilja **rollen Endast visning av DLP-efterlevnad.**</span><span class="sxs-lookup"><span data-stu-id="c0ce4-418">You can also create a role group with view-only privileges to the DLP policies and DLP reports by granting the **View-Only DLP Compliance Management** role.</span></span>

<span data-ttu-id="c0ce4-419">Mer information finns i [Ge användarna åtkomst till Office 365 Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="c0ce4-419">For more information, see [Give users access to the Office 365 Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>
  
<span data-ttu-id="c0ce4-420">Dessa behörigheter krävs bara för att skapa och tillämpa en DLP-princip.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-420">These permissions are required only to create and apply a DLP policy.</span></span> <span data-ttu-id="c0ce4-421">Tvingande princip kräver inte åtkomst till innehållet.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-421">Policy enforcement does not require access to the content.</span></span>
  
## <a name="find-the-dlp-cmdlets"></a><span data-ttu-id="c0ce4-422">Hitta DLP-cmdlets</span><span class="sxs-lookup"><span data-stu-id="c0ce4-422">Find the DLP cmdlets</span></span>

<span data-ttu-id="c0ce4-423">Om du vill använda de flesta cmdletar för Security &amp; Compliance Center måste du:</span><span class="sxs-lookup"><span data-stu-id="c0ce4-423">To use most of the cmdlets for the Security &amp; Compliance Center, you need to:</span></span>
  
1. <span data-ttu-id="c0ce4-424">[Anslut till Office 365 Security &amp; Compliance Center med fjärr-PowerShell](/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="c0ce4-424">[Connect to the Office 365 Security &amp; Compliance Center using remote PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>
    
2. <span data-ttu-id="c0ce4-425">Använd någon av dessa [policy-and-compliance-dlp cmdlets](/powershell/module/exchange/export-dlppolicycollection).</span><span class="sxs-lookup"><span data-stu-id="c0ce4-425">Use any of these [policy-and-compliance-dlp cmdlets](/powershell/module/exchange/export-dlppolicycollection).</span></span>
    
<span data-ttu-id="c0ce4-426">DLP-rapporter behöver dock hämta data från Microsoft 365, inklusive Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-426">However, DLP reports need pull data from across Microsoft 365, including Exchange Online.</span></span> <span data-ttu-id="c0ce4-427">Därför är **cmdlets för DLP-rapporterna tillgängliga i Exchange Online Powershell – inte i Security &amp; Compliance Center Powershell**.</span><span class="sxs-lookup"><span data-stu-id="c0ce4-427">For this reason, **the cmdlets for the DLP reports are available in Exchange Online Powershell -- not in Security &amp; Compliance Center Powershell**.</span></span> <span data-ttu-id="c0ce4-428">För att använda cmdlets för DLP-rapporterna måste du därför:</span><span class="sxs-lookup"><span data-stu-id="c0ce4-428">Therefore, to use the cmdlets for the DLP reports, you need to:</span></span>
  
1. <span data-ttu-id="c0ce4-429">[Ansluta till Exchange Online med fjärr-PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="c0ce4-429">[Connect to Exchange Online using remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>
    
2. <span data-ttu-id="c0ce4-430">Använd någon av dessa cmdletar för DLP-rapporterna:</span><span class="sxs-lookup"><span data-stu-id="c0ce4-430">Use any of these cmdlets for the DLP reports:</span></span>
    
    - [<span data-ttu-id="c0ce4-431">Hämta-DlpDetectionsRapport</span><span class="sxs-lookup"><span data-stu-id="c0ce4-431">Get-DlpDetectionsReport</span></span>](/powershell/module/exchange/Get-DlpDetectionsReport)

    - [<span data-ttu-id="c0ce4-432">Get-DlpDetailRapport</span><span class="sxs-lookup"><span data-stu-id="c0ce4-432">Get-DlpDetailReport</span></span>](/powershell/module/exchange/Get-DlpDetailReport)
    
## <a name="more-information"></a><span data-ttu-id="c0ce4-433">Mer information</span><span class="sxs-lookup"><span data-stu-id="c0ce4-433">More information</span></span>

- [<span data-ttu-id="c0ce4-434">Skapa en DLP-princip från en mall</span><span class="sxs-lookup"><span data-stu-id="c0ce4-434">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
    
- [<span data-ttu-id="c0ce4-435">Skicka meddelanden och visa principtips för DLP-principer</span><span class="sxs-lookup"><span data-stu-id="c0ce4-435">Send notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)
    
- [<span data-ttu-id="c0ce4-436">Skapa en DLP-princip för att skydda dokument med FCI eller andra egenskaper</span><span class="sxs-lookup"><span data-stu-id="c0ce4-436">Create a DLP policy to protect documents with FCI or other properties</span></span>](protect-documents-that-have-fci-or-other-properties.md)
    
- [<span data-ttu-id="c0ce4-437">Det här innehåller DLP-principmallarna</span><span class="sxs-lookup"><span data-stu-id="c0ce4-437">What the DLP policy templates include</span></span>](what-the-dlp-policy-templates-include.md)
    
- [<span data-ttu-id="c0ce4-438">Entitetsdefinitioner för typer av känslig information</span><span class="sxs-lookup"><span data-stu-id="c0ce4-438">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
    
- [<span data-ttu-id="c0ce4-439">Vad DLP-funktionerna letar efter</span><span class="sxs-lookup"><span data-stu-id="c0ce4-439">What the DLP functions look for</span></span>](what-the-dlp-functions-look-for.md)
    
- [<span data-ttu-id="c0ce4-440">Skapa en anpassad känslig informationstyp</span><span class="sxs-lookup"><span data-stu-id="c0ce4-440">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
