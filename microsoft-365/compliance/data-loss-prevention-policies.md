---
title: Referens för dataförlustskydd
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
description: referensmaterial för dataförlustskydd
ms.openlocfilehash: a94dde0bba3fdfc869746f51687ed7709a96639a
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52163023"
---
# <a name="data-loss-prevention-reference"></a><span data-ttu-id="38e52-103">Referens för dataförlustskydd</span><span class="sxs-lookup"><span data-stu-id="38e52-103">Data loss prevention reference</span></span>
 
> [!IMPORTANT]
> <span data-ttu-id="38e52-104">Det här referensavsnittet är inte längre huvudresursen Microsoft 365 skydd mot dataförlust (DLP).</span><span class="sxs-lookup"><span data-stu-id="38e52-104">This is reference topic is no longer the main resource for Microsoft 365 data loss prevention (DLP) information.</span></span> <span data-ttu-id="38e52-105">DLP-innehållsuppsättningen uppdateras och struktureras om.</span><span class="sxs-lookup"><span data-stu-id="38e52-105">The DLP content set is being updated and restructured.</span></span> <span data-ttu-id="38e52-106">Artiklarna i den här artikeln flyttas till nya, uppdaterade artiklar.</span><span class="sxs-lookup"><span data-stu-id="38e52-106">The topics covered in this article will be moving to new, updated articles.</span></span> <span data-ttu-id="38e52-107">Mer information om DLP finns i [Läs mer om skydd mot dataförlust.](dlp-learn-about-dlp.md)</span><span class="sxs-lookup"><span data-stu-id="38e52-107">For more information about DLP, see [Learn about data loss prevention](dlp-learn-about-dlp.md).</span></span>

<!-- this topic needs to be split into smaller, more coherent ones. It is confusing as it is. -->
<!-- move this note to a more appropriate place, no topic should start with a note -->
> [!NOTE]
> <span data-ttu-id="38e52-108">Funktioner för dataförlustskydd har nyligen lagts till i Microsoft Teams chatt- och kanalmeddelanden för användare som är licensierade för Office 365 Advanced Compliance, som är tillgängligt som ett fristående alternativ och ingår i Office 365 E5 och Microsoft 365 E5 Compliance.</span><span class="sxs-lookup"><span data-stu-id="38e52-108">Data loss prevention capabilities were recently added to Microsoft Teams chat and channel messages for users licensed for Office 365 Advanced Compliance, which is available as a standalone option and is included in Office 365 E5 and Microsoft 365 E5 Compliance.</span></span> <span data-ttu-id="38e52-109">Mer information om licenskrav finns i [licensvägledning Microsoft 365 Tenant-Level Services Licensing Guidance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).</span><span class="sxs-lookup"><span data-stu-id="38e52-109">To learn more about licensing requirements, see [Microsoft 365 Tenant-Level Services Licensing Guidance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).</span></span>



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
## <a name="create-and-manage-dlp-policies"></a><span data-ttu-id="38e52-110">Skapa och hantera DLP-principer</span><span class="sxs-lookup"><span data-stu-id="38e52-110">Create and manage DLP policies</span></span>

<span data-ttu-id="38e52-111">Du skapar och hanterar DLP-principer på sidan Skydd mot dataförlust i Microsoft 365 Efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="38e52-111">You create and manage DLP policies on the Data loss prevention page in the Microsoft 365 Compliance center.</span></span>
  
![Sidan Skydd mot dataförlust i Office 365 &amp; Säkerhetsefterlevnad](../media/943fd01c-d7aa-43a9-846d-0561321a405e.png)
  
<!-- MOVED TO LEARN ABOUT ## What a DLP policy contains

A DLP policy contains a few basic things:
  
- Where to protect the content: **locations** such as Exchange Online, SharePoint Online, and OneDrive for Business sites, as well as Microsoft Teams chat and channel messages. 
    
- When and how to protect the content by enforcing **rules** comprised of: 
    
  - **Conditions** the content must match before the rule is enforced. For example, a rule might be configured to look only for content containing Social Security numbers that's been shared with people outside your organization. 
    
  - **Actions** that you want the rule to take automatically when content matching the conditions is found. For example, a rule might be configured to block access to a document and send both the user and compliance officer an email notification. -->
    
<span data-ttu-id="38e52-113">Du kan använda en regel för att uppfylla ett särskilt skyddskrav och sedan använda en DLP-princip för att gruppera samman vanliga skyddskrav, till exempel alla regler som krävs för att uppfylla en viss regel.</span><span class="sxs-lookup"><span data-stu-id="38e52-113">You can use a rule to meet a specific protection requirement, and then use a DLP policy to group together common protection requirements, such as all of the rules needed to comply with a specific regulation.</span></span>
  
<span data-ttu-id="38e52-114">Du kan till exempel ha en DLP-princip som hjälper dig att identifiera förekomsten av information som omfattas av HIPAA (Health Insurance Portability and Accountability Act).</span><span class="sxs-lookup"><span data-stu-id="38e52-114">For example, you might have a DLP policy that helps you detect the presence of information subject to the Health Insurance Portability and Accountability Act (HIPAA).</span></span> <span data-ttu-id="38e52-115">Den här DLP-principen kan skydda HIPAA-data (vad) på alla SharePoint Online-webbplatser och alla OneDrive för företag-webbplatser (där) genom att hitta alla dokument som innehåller den här känsliga informationen som delas med personer utanför organisationen (villkoren) och sedan blockera åtkomsten till dokumentet och skicka ett meddelande (åtgärderna).</span><span class="sxs-lookup"><span data-stu-id="38e52-115">This DLP policy could help protect HIPAA data (the what) across all SharePoint Online sites and all OneDrive for Business sites (the where) by finding any document containing this sensitive information that's shared with people outside your organization (the conditions) and then blocking access to the document and sending a notification (the actions).</span></span> <span data-ttu-id="38e52-116">Dessa krav lagras som enskilda regler och grupperas tillsammans som en DLP-princip för att förenkla hantering och rapportering.</span><span class="sxs-lookup"><span data-stu-id="38e52-116">These requirements are stored as individual rules and grouped together as a DLP policy to simplify management and reporting.</span></span>
  
![Diagram som visar att DLP-principen innehåller platser och regler](../media/c006860c-2d00-42cb-aaa4-5b5638d139f7.png)
  
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

<span data-ttu-id="38e52-118">Om du väljer att inkludera specifika distributionsgrupper i Exchange omfattningen av DLP-principen endast till medlemmar i den gruppen.</span><span class="sxs-lookup"><span data-stu-id="38e52-118">If you choose to include specific distribution groups in Exchange, the DLP policy will be scoped only to the members of that group.</span></span> <span data-ttu-id="38e52-119">På samma sätt utesluter du en distributionsgrupp alla medlemmar i distributionsgruppen från principutvärderingen.</span><span class="sxs-lookup"><span data-stu-id="38e52-119">Similarly excluding a distribution group will exclude all the members of that distribution group from policy evaluation.</span></span> <span data-ttu-id="38e52-120">Du kan välja att begränsa en princip till medlemmar i distributionslistor, dynamiska distributionsgrupper och säkerhetsgrupper.</span><span class="sxs-lookup"><span data-stu-id="38e52-120">You can choose to scope a policy to the members of distribution lists, dynamic distribution groups, and security groups.</span></span> <span data-ttu-id="38e52-121">En DLP-princip får inte innehålla fler än 50 sådana inkludering och undantag.</span><span class="sxs-lookup"><span data-stu-id="38e52-121">A DLP policy can contain no more than 50 such inclusions and exclusions.</span></span>

<span data-ttu-id="38e52-122">Om du väljer att inkludera eller exkludera specifika SharePoint webbplatser kan en DLP-princip inte innehålla fler än 100 sådana inkludering och undantag.</span><span class="sxs-lookup"><span data-stu-id="38e52-122">If you choose to include or exclude specific SharePoint sites, a DLP policy can contain no more than 100 such inclusions and exclusions.</span></span> <span data-ttu-id="38e52-123">Även om den här gränsen finns kan du överskrida den här gränsen genom att använda en organisationsomfattande princip eller en princip som gäller för hela platser.</span><span class="sxs-lookup"><span data-stu-id="38e52-123">Although this limit exists, you can exceed this limit by applying either an org-wide policy or a policy that applies to entire locations.</span></span>

<span data-ttu-id="38e52-124">Om du väljer att inkludera eller exkludera specifika OneDrive-konton eller grupper kan en DLP-princip innehålla högst 100 användarkonton eller 50 grupper som inkludering eller undantag.</span><span class="sxs-lookup"><span data-stu-id="38e52-124">If you choose to include or exclude specific OneDrive accounts or groups, a DLP policy can contain no more than 100 user accounts or 50 groups as inclusion or exclusion.</span></span>

> [!NOTE]
> <span data-ttu-id="38e52-125">OneDrive för företag-principens användning av konton eller grupper är en offentlig förhandsversion.</span><span class="sxs-lookup"><span data-stu-id="38e52-125">OneDrive for business policy scoping using accounts or groups is in public preview.</span></span> <span data-ttu-id="38e52-126">Under den här fasen kan du antingen inkludera eller exkludera användarkonton och grupper som en del av en DLP-princip.</span><span class="sxs-lookup"><span data-stu-id="38e52-126">During this phase, you can either include or exclude user accounts and groups as part of a DLP policy.</span></span> <span data-ttu-id="38e52-127">Både inkludering och undantag som en del av samma princip stöds inte.</span><span class="sxs-lookup"><span data-stu-id="38e52-127">Both inclusion and exclusion as part of the same policy is not supported.</span></span>
  
### <a name="rules"></a><span data-ttu-id="38e52-128">Regler</span><span class="sxs-lookup"><span data-stu-id="38e52-128">Rules</span></span>

> [!NOTE]
> <span data-ttu-id="38e52-129">När det inte finns någon konfigurerad avisering ska standardbeteendet för en DLP-princip vara att inte avisering eller utlösare.</span><span class="sxs-lookup"><span data-stu-id="38e52-129">The default behavior of a DLP policy, when there is no alert configured, is not to alert or trigger.</span></span> <span data-ttu-id="38e52-130">Det här gäller endast för standardinformationstyper.</span><span class="sxs-lookup"><span data-stu-id="38e52-130">This applies only to default information types.</span></span> <span data-ttu-id="38e52-131">För anpassade informationstyper varnas systemet även om det inte finns någon definierad åtgärd i principen.</span><span class="sxs-lookup"><span data-stu-id="38e52-131">For custom information types, the system will alert even if there is no action defined in the policy.</span></span>

<span data-ttu-id="38e52-132">Regler är det som tillämpar affärskraven på organisationens innehåll.</span><span class="sxs-lookup"><span data-stu-id="38e52-132">Rules are what enforce your business requirements on your organization's content.</span></span> <span data-ttu-id="38e52-133">En princip innehåller en eller flera regler och varje regel består av villkor och åtgärder.</span><span class="sxs-lookup"><span data-stu-id="38e52-133">A policy contains one or more rules, and each rule consists of conditions and actions.</span></span> <span data-ttu-id="38e52-134">När villkoren uppfylls för varje regel vidtas åtgärderna automatiskt.</span><span class="sxs-lookup"><span data-stu-id="38e52-134">For each rule, when the conditions are met, the actions are taken automatically.</span></span> <span data-ttu-id="38e52-135">Regler körs sekventiellt och börjar med regeln med högst prioritet i varje princip.</span><span class="sxs-lookup"><span data-stu-id="38e52-135">Rules are executed sequentially, starting with the highest-priority rule in each policy.</span></span>
  
<span data-ttu-id="38e52-136">En regel innehåller också alternativ för att meddela användare (med principtips och e-postaviseringar) och administratörer (med rapporter om e-posttillbud) som har matchat regeln.</span><span class="sxs-lookup"><span data-stu-id="38e52-136">A rule also provides options to notify users (with policy tips and email notifications) and admins (with email incident reports) that content has matched the rule.</span></span>
  
<span data-ttu-id="38e52-137">Här är komponenterna i en regel, som förklaras nedan.</span><span class="sxs-lookup"><span data-stu-id="38e52-137">Here are the components of a rule, each explained below.</span></span>
  
![Avsnitt i DLP-regelredigeraren](../media/1859d504-b9c2-45ed-961b-a0092251acc2.png)
  
#### <a name="conditions"></a><span data-ttu-id="38e52-139">Villkor</span><span class="sxs-lookup"><span data-stu-id="38e52-139">Conditions</span></span>

<span data-ttu-id="38e52-140">Villkoren är viktiga eftersom de avgör vilka typer av information du letar efter och när de ska vidta en åtgärd.</span><span class="sxs-lookup"><span data-stu-id="38e52-140">Conditions are important because they determine what types of information you're looking for, and when to take an action.</span></span> <span data-ttu-id="38e52-141">Du kan till exempel välja att ignorera innehåll som innehåller passnummer om inte innehållet innehåller fler än 10 sådana nummer och delas med personer utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="38e52-141">For example, you might choose to ignore content containing passport numbers unless the content contains more than 10 such numbers and is shared with people outside your organization.</span></span>
  
<span data-ttu-id="38e52-142">Villkor fokuserar **på innehållet,** t.ex. vilka typer av känslig information du letar efter, och även på **sammanhanget,** t.ex. vem dokumentet delas med.</span><span class="sxs-lookup"><span data-stu-id="38e52-142">Conditions focus on the **content**, such as what types of sensitive information you're looking for, and also on the **context**, such as who the document is shared with.</span></span> <span data-ttu-id="38e52-143">Du kan använda villkor för att tilldela olika åtgärder till olika risknivåer.</span><span class="sxs-lookup"><span data-stu-id="38e52-143">You can use conditions to assign different actions to different risk levels.</span></span> <span data-ttu-id="38e52-144">Till exempel kan känsligt innehåll som delas internt vara en lägre risk och kräver färre åtgärder än känsligt innehåll som delas med personer utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="38e52-144">For example, sensitive content shared internally might be lower risk and require fewer actions than sensitive content shared with people outside the organization.</span></span> 
  
![Lista med tillgängliga DLP-villkor](../media/0fa43f90-d007-4506-ae93-43e8424fe103.png)
  
<span data-ttu-id="38e52-146">De tillgängliga villkoren kan avgöra om:</span><span class="sxs-lookup"><span data-stu-id="38e52-146">The conditions now available can determine if:</span></span>
  
- <span data-ttu-id="38e52-147">Innehållet innehåller en typ av känslig information.</span><span class="sxs-lookup"><span data-stu-id="38e52-147">Content contains a type of sensitive information.</span></span>
    
- <span data-ttu-id="38e52-148">Innehållet innehåller en etikett.</span><span class="sxs-lookup"><span data-stu-id="38e52-148">Content contains a label.</span></span> <span data-ttu-id="38e52-149">Mer information finns i avsnittet Använda en bevarandeetikett som ett [villkor i en DLP-princip nedan.](#using-a-retention-label-as-a-condition-in-a-dlp-policy)</span><span class="sxs-lookup"><span data-stu-id="38e52-149">For more information, see the below section [Using a retention label as a condition in a DLP policy](#using-a-retention-label-as-a-condition-in-a-dlp-policy).</span></span>
    
- <span data-ttu-id="38e52-150">Innehåll delas med personer utanför eller inom organisationen.</span><span class="sxs-lookup"><span data-stu-id="38e52-150">Content is shared with people outside or inside your organization.</span></span>

  > [!NOTE]
  > <span data-ttu-id="38e52-151">Användare som har icke-gästkonton i värdorganisationens Active Directory eller Azure Active Directory betraktas som personer i organisationen.</span><span class="sxs-lookup"><span data-stu-id="38e52-151">Users who have non-guest accounts in a host organization's Active Directory or Azure Active Directory tenant are considered as people inside the organization.</span></span>
    
#### <a name="types-of-sensitive-information"></a><span data-ttu-id="38e52-152">Typer av känslig information</span><span class="sxs-lookup"><span data-stu-id="38e52-152">Types of sensitive information</span></span>

<span data-ttu-id="38e52-153">En DLP-princip kan skydda känslig information som definieras som en **typ av känslig information.**</span><span class="sxs-lookup"><span data-stu-id="38e52-153">A DLP policy can help protect sensitive information, which is defined as a **sensitive information type**.</span></span> <span data-ttu-id="38e52-154">Microsoft 365 innehåller definitioner av vanliga typer av känslig information i många olika regioner som är färdiga att använda, till exempel kreditkortsnummer, bankkontonummer, nationella ID-nummer och passnummer.</span><span class="sxs-lookup"><span data-stu-id="38e52-154">Microsoft 365 includes definitions for many common sensitive information types across many different regions that are ready for you to use, such as a credit card number, bank account numbers, national ID numbers, and passport numbers.</span></span> 
  
![Lista över tillgängliga typer av känslig information](../media/3eaa9911-bc94-44be-902f-363dbf3b07fe.png)
  
<span data-ttu-id="38e52-156">När en DLP-princip söker efter en typ av känslig information, till exempel kreditkortsnummer, söker den inte bara efter ett nummer med 16 siffror.</span><span class="sxs-lookup"><span data-stu-id="38e52-156">When a DLP policy looks for a sensitive information type such as a credit card number, it doesn't simply look for a 16-digit number.</span></span> <span data-ttu-id="38e52-157">Varje typ av känslig information definieras och identifieras genom en kombination av följande:</span><span class="sxs-lookup"><span data-stu-id="38e52-157">Each sensitive information type is defined and detected by using a combination of:</span></span>
  
- <span data-ttu-id="38e52-158">Nyckelord.</span><span class="sxs-lookup"><span data-stu-id="38e52-158">Keywords.</span></span>
    
- <span data-ttu-id="38e52-159">Interna funktioner för att validera kontrollsummar eller sammansättning.</span><span class="sxs-lookup"><span data-stu-id="38e52-159">Internal functions to validate checksums or composition.</span></span>
    
- <span data-ttu-id="38e52-160">Utvärdering av reguljära uttryck för att hitta mönstermatchningar.</span><span class="sxs-lookup"><span data-stu-id="38e52-160">Evaluation of regular expressions to find pattern matches.</span></span>
    
- <span data-ttu-id="38e52-161">Andra innehållsundersökningar.</span><span class="sxs-lookup"><span data-stu-id="38e52-161">Other content examination.</span></span>
    
<span data-ttu-id="38e52-162">Det här hjälper DLP-identifiering att uppnå en hög grad av exakthet samtidigt som antalet falska positiva identifieringar som kan avbryta personers arbete minskar.</span><span class="sxs-lookup"><span data-stu-id="38e52-162">This helps DLP detection achieve a high degree of accuracy while reducing the number of false positives that can interrupt peoples' work.</span></span>
  
#### <a name="actions"></a><span data-ttu-id="38e52-163">Åtgärder</span><span class="sxs-lookup"><span data-stu-id="38e52-163">Actions</span></span>

<span data-ttu-id="38e52-164">När innehållet matchar ett villkor i en regel kan du använda åtgärder för att automatiskt skydda innehållet.</span><span class="sxs-lookup"><span data-stu-id="38e52-164">When content matches a condition in a rule, you can apply actions to automatically protect the content.</span></span>
  
![Lista över tillgängliga DLP-åtgärder](../media/8aef17fc-1e99-4ac7-adfc-0f2c9c1a0697.png)
  
<span data-ttu-id="38e52-166">När åtgärderna är tillgängliga kan du göra följande:</span><span class="sxs-lookup"><span data-stu-id="38e52-166">With the actions now available, you can:</span></span>
  
- <span data-ttu-id="38e52-167">**Begränsa åtkomst till innehållet** Beroende på dina behov kan du begränsa åtkomsten till innehåll på tre sätt:</span><span class="sxs-lookup"><span data-stu-id="38e52-167">**Restrict access to the content** Depending on your need, you can restrict access to content in three ways:</span></span>

  1. <span data-ttu-id="38e52-168">Begränsa åtkomsten till innehåll för alla.</span><span class="sxs-lookup"><span data-stu-id="38e52-168">Restrict access to content for everyone.</span></span>
  2. <span data-ttu-id="38e52-169">Begränsa åtkomst till innehåll för personer utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="38e52-169">Restrict access to content for people outside the organization.</span></span>
  3. <span data-ttu-id="38e52-170">Begränsa åtkomsten till Alla som har länken.</span><span class="sxs-lookup"><span data-stu-id="38e52-170">Restrict access to "Anyone with the link."</span></span>

  <span data-ttu-id="38e52-171">För webbplatsinnehåll innebär det att behörigheterna för dokumentet är begränsade för alla utom den primära administratören för webbplatssamlingen, dokumentägaren och personen som senast ändrade dokumentet.</span><span class="sxs-lookup"><span data-stu-id="38e52-171">For site content, this means that permissions for the document are restricted for everyone except the primary site collection administrator, document owner, and person who last modified the document.</span></span> <span data-ttu-id="38e52-172">De här personerna kan ta bort den känsliga informationen från dokumentet eller vidta andra åtgärder.</span><span class="sxs-lookup"><span data-stu-id="38e52-172">These people can remove the sensitive information from the document or take other remedial action.</span></span> <span data-ttu-id="38e52-173">När dokumentet uppfyller alla regler och regler återställs de ursprungliga behörigheterna automatiskt.</span><span class="sxs-lookup"><span data-stu-id="38e52-173">When the document is in compliance, the original permissions are automatically restored.</span></span> <span data-ttu-id="38e52-174">När åtkomsten till ett dokument blockeras visas dokumentet med en särskild principtipsikon i biblioteket på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="38e52-174">When access to a document is blocked, the document appears with a special policy tip icon in the library on the site.</span></span> 
    
  ![Principtips som visar att åtkomst till dokument blockeras](../media/b6cefed3-d212-43d7-8534-4b92b26ebd50.png)
  
  <span data-ttu-id="38e52-176">För e-postinnehåll blockerar den här åtgärden meddelandet från att skickas.</span><span class="sxs-lookup"><span data-stu-id="38e52-176">For email content, this action blocks the message from being sent.</span></span> <span data-ttu-id="38e52-177">Beroende på hur DLP-regeln har konfigurerats ser avsändaren en NDR-meddelande eller (om regeln använder ett meddelande) ett principtips och/eller ett e-postmeddelande.</span><span class="sxs-lookup"><span data-stu-id="38e52-177">Depending on how the DLP rule is configured, the sender sees an NDR or (if the rule uses a notification) a policy tip and/or email notification.</span></span>
    
  ![Varning om att obehöriga mottagare måste tas bort från meddelandet](../media/302f9994-912d-41e7-861f-8a4539b3c285.png)
  
#### <a name="user-notifications-and-user-overrides"></a><span data-ttu-id="38e52-179">Användarmeddelanden och åsidosättningar av användare</span><span class="sxs-lookup"><span data-stu-id="38e52-179">User notifications and user overrides</span></span>

<span data-ttu-id="38e52-180">Du kan använda meddelanden och åsidosättningar för att informera användarna om DLP-principer och hjälpa dem att uppfylla alla regler utan att blockera deras arbete.</span><span class="sxs-lookup"><span data-stu-id="38e52-180">You can use notifications and overrides to educate your users about DLP policies and help them remain compliant without blocking their work.</span></span> <span data-ttu-id="38e52-181">Om en användare till exempel försöker dela ett dokument som innehåller känslig information kan en DLP-princip både skicka ett e-postmeddelande till dem och visa dem ett principtips inom ramen för dokumentbiblioteket som gör att de kan åsidosätta principen om de har en affärs-justering.</span><span class="sxs-lookup"><span data-stu-id="38e52-181">For example, if a user tries to share a document containing sensitive information, a DLP policy can both send them an email notification and show them a policy tip in the context of the document library that allows them to override the policy if they have a business justification.</span></span>
  
![Användarmeddelanden och användaren åsidosätter avsnitt i DLP-regelredigeraren](../media/37b560d4-6e4e-489e-9134-d4b9daf60296.png)
  
<span data-ttu-id="38e52-183">I e-postmeddelandet kan personen som skickade, delade eller senast ändrade innehållet meddelas och, för webbplatsinnehåll, den primära administratören för webbplatssamlingen och dokumentets ägare.</span><span class="sxs-lookup"><span data-stu-id="38e52-183">The email can notify the person who sent, shared, or last modified the content and, for site content, the primary site collection administrator and document owner.</span></span> <span data-ttu-id="38e52-184">Du kan dessutom lägga till eller ta bort vilka du vill i e-postmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="38e52-184">In addition, you can add or remove whomever you choose from the email notification.</span></span>
  
<span data-ttu-id="38e52-185">Förutom att skicka ett e-postmeddelande visar en användare ett principtips:</span><span class="sxs-lookup"><span data-stu-id="38e52-185">In addition to sending an email notification, a user notification displays a policy tip:</span></span>
  
- <span data-ttu-id="38e52-186">I Outlook och Outlook på webben.</span><span class="sxs-lookup"><span data-stu-id="38e52-186">In Outlook and Outlook on the web.</span></span>
    
- <span data-ttu-id="38e52-187">För dokumentet på en SharePoint Online eller OneDrive för företag webbplats.</span><span class="sxs-lookup"><span data-stu-id="38e52-187">For the document on a SharePoint Online or OneDrive for Business site.</span></span>
    
- <span data-ttu-id="38e52-188">I Excel, PowerPoint och Word, när dokumentet lagras på en webbplats som ingår i en DLP-princip.</span><span class="sxs-lookup"><span data-stu-id="38e52-188">In Excel, PowerPoint, and Word, when the document is stored on a site included in a DLP policy.</span></span>
    
<span data-ttu-id="38e52-189">E-postmeddelandet och principtipset förklarar varför innehållet står i konflikt med en DLP-princip.</span><span class="sxs-lookup"><span data-stu-id="38e52-189">The email notification and policy tip explain why content conflicts with a DLP policy.</span></span> <span data-ttu-id="38e52-190">Om du väljer kan e-postaviseringar och principtips tillåta användare att åsidosätta en regel genom att rapportera en felaktig positiv eller ange en affärs motivering.</span><span class="sxs-lookup"><span data-stu-id="38e52-190">If you choose, the email notification and policy tip can allow users to override a rule by reporting a false positive or providing a business justification.</span></span> <span data-ttu-id="38e52-191">På så sätt kan du utbilda användarna om DLP-principerna och tillämpa dem utan att hindra personer från att göra sina arbeten.</span><span class="sxs-lookup"><span data-stu-id="38e52-191">This can help you educate users about your DLP policies and enforce them without preventing people from doing their work.</span></span> <span data-ttu-id="38e52-192">Information om åsidosättningar och falska positiva resultat loggas också för rapportering (se nedan om DLP-rapporter) och inkluderas i incidentrapporterna (nästa avsnitt), så att efterlevnadsombudet regelbundet kan granska den här informationen.</span><span class="sxs-lookup"><span data-stu-id="38e52-192">Information about overrides and false positives is also logged for reporting (see below about the DLP reports) and included in the incident reports (next section), so that the compliance officer can regularly review this information.</span></span>
  
<span data-ttu-id="38e52-193">Så här ser ett principtips ut i ett OneDrive för företag konto.</span><span class="sxs-lookup"><span data-stu-id="38e52-193">Here's what a policy tip looks like in a OneDrive for Business account.</span></span>
  
![Principtips för ett dokument i ett OneDrive konto](../media/f9834d35-94f0-4511-8555-0fe69855ce6d.png)

 <span data-ttu-id="38e52-195">Mer information om användarmeddelanden och principtips i DLP-principer finns i [Använda meddelanden och principtips.](use-notifications-and-policy-tips.md)</span><span class="sxs-lookup"><span data-stu-id="38e52-195">To learn more about user notifications and policy tips in DLP policies, see [Use notifications and policy tips](use-notifications-and-policy-tips.md).</span></span>

#### <a name="alerts-and-incident-reports"></a><span data-ttu-id="38e52-196">Aviseringar och incidentrapporter</span><span class="sxs-lookup"><span data-stu-id="38e52-196">Alerts and Incident reports</span></span>

<span data-ttu-id="38e52-197">När en regel matchas kan du skicka ett e-postmeddelande med en avisering till efterlevnadsombudet (eller till valfri person) med information om aviseringen.</span><span class="sxs-lookup"><span data-stu-id="38e52-197">When a rule is matched, you can send an alert email to your compliance officer ( or any person(s) you choose) with details of the alert.</span></span> <span data-ttu-id="38e52-198">Det här e-postmeddelandet med en länk till Instrumentpanelen för hantering av [DLP-aviseringar](dlp-configure-view-alerts-policies.md) som efterlevnadsombud kan gå till för att visa information om händelser och händelser.</span><span class="sxs-lookup"><span data-stu-id="38e52-198">This alert email will carry a link of the [DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md) which the compliance officer can go to view the details of alert and events.</span></span> <span data-ttu-id="38e52-199">Instrumentpanelen innehåller information om händelsen som utlöste aviseringen tillsammans med information om matchad DLP-princip och vilket känsligt innehåll som upptäckts.</span><span class="sxs-lookup"><span data-stu-id="38e52-199">The dashboard contains details of the event that triggered the alert along with details of the DLP policy matched and the sensitive content detected.</span></span>

<span data-ttu-id="38e52-200">Dessutom kan du skicka en incidentrapport med information om händelsen.</span><span class="sxs-lookup"><span data-stu-id="38e52-200">In addition, you can also send an incident report with details of the event.</span></span> <span data-ttu-id="38e52-201">Den här rapporten innehåller information om det objekt som matchades, det faktiska innehållet som matchade regeln och namnet på den person som senast ändrade innehållet.</span><span class="sxs-lookup"><span data-stu-id="38e52-201">This report includes information about the item that was matched, the actual content that matched the rule, and the name of the person who last modified the content.</span></span> <span data-ttu-id="38e52-202">För e-postmeddelanden innehåller rapporten också det ursprungliga meddelandet som matchar en DLP-princip som en bifogad fil.</span><span class="sxs-lookup"><span data-stu-id="38e52-202">For email messages, the report also includes as an attachment the original message that matches a DLP policy.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="38e52-203">![Sida för att konfigurera incidentrapporter](../media/Alerts-and-incident-report.png)</span><span class="sxs-lookup"><span data-stu-id="38e52-203">![Page for configuring incident reports](../media/Alerts-and-incident-report.png)</span></span>

<span data-ttu-id="38e52-204">DLP söker igenom e-post på ett annat sätt än objekten SharePoint online eller OneDrive för företag.</span><span class="sxs-lookup"><span data-stu-id="38e52-204">DLP scans email differently from items in SharePoint Online or OneDrive for Business.</span></span> <span data-ttu-id="38e52-205">I SharePoint Online OneDrive för företag genomsöker DLP både befintliga och nya objekt och genererar en avisering och incidentrapport när en matchning hittas.</span><span class="sxs-lookup"><span data-stu-id="38e52-205">In SharePoint Online and OneDrive for Business, DLP scans existing items as well as new ones and generates an alert and incident report whenever a match is found.</span></span> <span data-ttu-id="38e52-206">I Exchange Online söker DLP bara igenom nya e-postmeddelanden och genererar en rapport om det finns en principmatchning.</span><span class="sxs-lookup"><span data-stu-id="38e52-206">In Exchange Online, DLP only scans new email messages and generates a report if there is a policy match.</span></span> <span data-ttu-id="38e52-207">DLP ***söker inte igenom*** eller matchar tidigare befintliga e-postobjekt som lagrats i en postlåda eller ett arkiv.</span><span class="sxs-lookup"><span data-stu-id="38e52-207">DLP ***does not*** scan or match previously existing email items that are stored in a mailbox or archive.</span></span>
  
## <a name="grouping-and-logical-operators"></a><span data-ttu-id="38e52-208">Grupperingsoperatorer och logiska operatorer</span><span class="sxs-lookup"><span data-stu-id="38e52-208">Grouping and logical operators</span></span>

<span data-ttu-id="38e52-209">Ofta har DLP-principen ett enkelt krav, till exempel att identifiera allt innehåll som innehåller ett amerikanskt personnummer.</span><span class="sxs-lookup"><span data-stu-id="38e52-209">Often your DLP policy has a straightforward requirement, such as to identify all content that contains a U.S. Social Security Number.</span></span> <span data-ttu-id="38e52-210">I andra fall kan dock DLP-principen behöva identifiera mer löst definierade data.</span><span class="sxs-lookup"><span data-stu-id="38e52-210">However, in other scenarios, your DLP policy might need to identify more loosely defined data.</span></span>
  
<span data-ttu-id="38e52-211">Om du till exempel vill identifiera innehåll som omfattas av U.S. Health Insurance Act (HIPAA) måste du leta efter:</span><span class="sxs-lookup"><span data-stu-id="38e52-211">For example, to identify content subject to the U.S. Health Insurance Act (HIPAA), you need to look for:</span></span>
  
- <span data-ttu-id="38e52-212">Innehåll som innehåller särskilda typer av känslig information, till exempel ett U.S. Social Security Number eller DeA (DeA).</span><span class="sxs-lookup"><span data-stu-id="38e52-212">Content that contains specific types of sensitive information, such as a U.S. Social Security Number or Drug Enforcement Agency (DEA) Number.</span></span>
    
    <span data-ttu-id="38e52-213">OCH</span><span class="sxs-lookup"><span data-stu-id="38e52-213">AND</span></span>
    
- <span data-ttu-id="38e52-214">Innehåll som är svårare att identifiera, till exempel kommunikation om en patientvård eller beskrivningar av medicinsk information.</span><span class="sxs-lookup"><span data-stu-id="38e52-214">Content that's more difficult to identify, such as communications about a patient's care or descriptions of medical services provided.</span></span> <span data-ttu-id="38e52-215">För att kunna identifiera det här innehållet krävs matchande nyckelord från mycket stora nyckelordslistor, till exempel den internationella klassificeringen av tidsklassificering (ICD-9 CM eller ICD-10-CM).</span><span class="sxs-lookup"><span data-stu-id="38e52-215">Identifying this content requires matching keywords from very large keyword lists, such as the International Classification of Diseases (ICD-9-CM or ICD-10-CM).</span></span>
    
<span data-ttu-id="38e52-216">Du kan enkelt identifiera lösa data med hjälp av grupperingsoperatorer och logiska operatorer (OCH, ELLER).</span><span class="sxs-lookup"><span data-stu-id="38e52-216">You can easily identify such loosely defined data by using grouping and logical operators (AND, OR).</span></span> <span data-ttu-id="38e52-217">När du skapar en DLP-princip kan du:</span><span class="sxs-lookup"><span data-stu-id="38e52-217">When you create a DLP policy, you can:</span></span>
  
- <span data-ttu-id="38e52-218">Gruppera typer av känslig information.</span><span class="sxs-lookup"><span data-stu-id="38e52-218">Group sensitive information types.</span></span>
    
- <span data-ttu-id="38e52-219">Välj den logiska operatorn mellan typerna av känslig information i en grupp och mellan grupperna.</span><span class="sxs-lookup"><span data-stu-id="38e52-219">Choose the logical operator between the sensitive information types within a group and between the groups themselves.</span></span>
    
### <a name="choosing-the-operator-within-a-group"></a><span data-ttu-id="38e52-220">Välja operator inom en grupp</span><span class="sxs-lookup"><span data-stu-id="38e52-220">Choosing the operator within a group</span></span>

<span data-ttu-id="38e52-221">Inom en grupp kan du välja om något eller samtliga av villkoren i gruppen ska vara uppfyllda för att innehållet ska matcha regeln.</span><span class="sxs-lookup"><span data-stu-id="38e52-221">Within a group, you can choose whether any or all of the conditions in that group must be satisfied for the content to match the rule.</span></span>
  
![Grupp som visar operatorerna i gruppen](../media/6a12f1e8-112d-48ee-9a73-82b3dd0542e7.png)
  
### <a name="adding-a-group"></a><span data-ttu-id="38e52-223">Lägga till en grupp</span><span class="sxs-lookup"><span data-stu-id="38e52-223">Adding a group</span></span>

<span data-ttu-id="38e52-224">Du kan snabbt lägga till en grupp, som kan ha egna villkor och operatorer inom den gruppen.</span><span class="sxs-lookup"><span data-stu-id="38e52-224">You can quickly add a group, which can have its own conditions and operator within that group.</span></span>
  
![Knappen Lägg till grupp](../media/5f72f292-d1f3-4f11-a911-a9f71e10abf6.png)
  
### <a name="choosing-the-operator-between-groups"></a><span data-ttu-id="38e52-226">Välja operator mellan grupper</span><span class="sxs-lookup"><span data-stu-id="38e52-226">Choosing the operator between groups</span></span>

<span data-ttu-id="38e52-227">Mellan grupper kan du välja om villkoren i bara en grupp eller alla grupper ska vara uppfyllda för att innehållet ska matcha regeln.</span><span class="sxs-lookup"><span data-stu-id="38e52-227">Between groups, you can choose whether the conditions in just one group or all of the groups must be satisfied for the content to match the rule.</span></span>
  
<span data-ttu-id="38e52-228">Den inbyggda amerikanska **HIPAA-policyn** har till exempel en regel som använder en **OCH-operator** mellan grupperna så att den identifierar innehåll som innehåller:</span><span class="sxs-lookup"><span data-stu-id="38e52-228">For example, the built-in **U.S. HIPAA** policy has a rule that uses an **AND** operator between the groups so that it identifies content that contains:</span></span> 
  
- <span data-ttu-id="38e52-229">från gruppens **PII-identifierare** (minst ett SSN-nummer **ELLER** DEA-nummer)</span><span class="sxs-lookup"><span data-stu-id="38e52-229">from the group **PII Identifiers** (at least one SSN number **OR** DEA number)</span></span> 
    
    <span data-ttu-id="38e52-230">**OCH**</span><span class="sxs-lookup"><span data-stu-id="38e52-230">**AND**</span></span>
    
- <span data-ttu-id="38e52-231">från gruppens **medicinska villkor** (minst ett ICD-9-CM-nyckelord **ELLER** ICD-10-CM-nyckelord)</span><span class="sxs-lookup"><span data-stu-id="38e52-231">from the group **Medical Terms** (at least one ICD-9-CM keyword **OR** ICD-10-CM keyword)</span></span> 
    
![Grupper som visar operatorn mellan grupper](../media/354aa77f-569c-4847-9dfe-605ee2bb28d1.png)
  
## <a name="the-priority-by-which-rules-are-processed"></a><span data-ttu-id="38e52-233">Prioritet som regler bearbetas med</span><span class="sxs-lookup"><span data-stu-id="38e52-233">The priority by which rules are processed</span></span>

<span data-ttu-id="38e52-234">När du skapar regler i en princip tilldelas varje regel prioritet i den ordning som den skapas, det vill säga att den regel som skapas först har första prioritet, den regel som skapas först har den andra prioriteten och så vidare.</span><span class="sxs-lookup"><span data-stu-id="38e52-234">When you create rules in a policy, each rule is assigned a priority in the order in which it's created — meaning, the rule created first has first priority, the rule created second has second priority, and so on.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="38e52-235">![Regler i prioritetsordning](../media/dlp-rules-in-priority-order.png)</span><span class="sxs-lookup"><span data-stu-id="38e52-235">![Rules in priority order](../media/dlp-rules-in-priority-order.png)</span></span>
  
<span data-ttu-id="38e52-236">När du har konfigurerat fler än en DLP-princip kan du ändra prioriteten för en eller flera principer.</span><span class="sxs-lookup"><span data-stu-id="38e52-236">After you have set up more than one DLP policy, you can change the priority of one or more policies.</span></span> <span data-ttu-id="38e52-237">Det gör du genom att välja en princip, **välja Redigera** princip och ange **prioritet i** listan Prioritet.</span><span class="sxs-lookup"><span data-stu-id="38e52-237">To do that, select a policy, choose **Edit policy**, and use the **Priority** list to specify its priority.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="38e52-238">![Ange prioritet för en princip](../media/dlp-set-policy-priority.png)</span><span class="sxs-lookup"><span data-stu-id="38e52-238">![Set priority for a policy](../media/dlp-set-policy-priority.png)</span></span>

<span data-ttu-id="38e52-239">När innehåll utvärderas mot regler bearbetas reglerna i prioritetsordning.</span><span class="sxs-lookup"><span data-stu-id="38e52-239">When content is evaluated against rules, the rules are processed in priority order.</span></span> <span data-ttu-id="38e52-240">Om innehållet matchar flera regler bearbetas reglerna i prioritetsordning och den mest restriktiva åtgärden tillämpas.</span><span class="sxs-lookup"><span data-stu-id="38e52-240">If content matches multiple rules, the rules are processed in priority order and the most restrictive action is enforced.</span></span> <span data-ttu-id="38e52-241">Om innehållet till exempel matchar alla följande regler tillämpas regel 3 eftersom den har högsta prioritet och mest restriktiv regel:</span><span class="sxs-lookup"><span data-stu-id="38e52-241">For example, if content matches all of the following rules, Rule 3 is enforced because it's the highest priority, most restrictive rule:</span></span>
  
- <span data-ttu-id="38e52-242">Regel 1: Endast meddelar användarna</span><span class="sxs-lookup"><span data-stu-id="38e52-242">Rule 1: only notifies users</span></span>
    
- <span data-ttu-id="38e52-243">Regel 2: Meddelar användarna, begränsar åtkomsten och tillåter att användaren åsidosätter</span><span class="sxs-lookup"><span data-stu-id="38e52-243">Rule 2: notifies users, restricts access, and allows user overrides</span></span>
    
- <span data-ttu-id="38e52-244">Regel 3: Meddelar användarna, begränsar åtkomsten och tillåter inte åsidosättningar av användare</span><span class="sxs-lookup"><span data-stu-id="38e52-244">Rule 3: notifies users, restricts access, and does not allow user overrides</span></span>
    
- <span data-ttu-id="38e52-245">Regel 4: Meddelar endast användarna</span><span class="sxs-lookup"><span data-stu-id="38e52-245">Rule 4: only notifies users</span></span>
    
- <span data-ttu-id="38e52-246">Regel 5: Begränsar åtkomsten</span><span class="sxs-lookup"><span data-stu-id="38e52-246">Rule 5: restricts access</span></span>
    
- <span data-ttu-id="38e52-247">Regel 6: Meddelar användare, begränsar åtkomsten och tillåter inte åsidosättningar av användare</span><span class="sxs-lookup"><span data-stu-id="38e52-247">Rule 6: notifies users, restricts access, and does not allow user overrides</span></span>
    
<span data-ttu-id="38e52-248">I det här exemplet registreras matchningar för alla regler i granskningsloggarna och visas i DLP-rapporterna, även om endast den mest restriktiva regeln tillämpas.</span><span class="sxs-lookup"><span data-stu-id="38e52-248">In this example, note that matches for all of the rules are recorded in the audit logs and shown in the DLP reports, even though only the most restrictive rule is enforced.</span></span>
  
<span data-ttu-id="38e52-249">Observera följande när det gäller policytips:</span><span class="sxs-lookup"><span data-stu-id="38e52-249">Regarding policy tips, note that:</span></span>
  
- <span data-ttu-id="38e52-250">Endast principtipset med högst prioritet, den mest restriktiva regeln visas.</span><span class="sxs-lookup"><span data-stu-id="38e52-250">Only the policy tip from the highest priority, most restrictive rule will be shown.</span></span> <span data-ttu-id="38e52-251">Till exempel kommer ett principtips från en regel som blockerar åtkomst till innehåll att visas över ett principtips från en regel som helt enkelt skickar ett meddelande.</span><span class="sxs-lookup"><span data-stu-id="38e52-251">For example, a policy tip from a rule that blocks access to content will be shown over a policy tip from a rule that simply sends a notification.</span></span> <span data-ttu-id="38e52-252">Det gör att det inte går att se en störtlapp av principtips.</span><span class="sxs-lookup"><span data-stu-id="38e52-252">This prevents people from seeing a cascade of policy tips.</span></span>
    
- <span data-ttu-id="38e52-253">Om principtipset i den mest restriktiva regeln tillåter att användare åsidosätter regeln åsidosätter den här regeln även eventuella andra regler som det matchade innehållet.</span><span class="sxs-lookup"><span data-stu-id="38e52-253">If the policy tips in the most restrictive rule allow people to override the rule, then overriding this rule also overrides any other rules that the content matched.</span></span>
    
## <a name="tuning-rules-to-make-them-easier-or-harder-to-match"></a><span data-ttu-id="38e52-254">Justera regler så att de blir lättare eller svårare att matcha</span><span class="sxs-lookup"><span data-stu-id="38e52-254">Tuning rules to make them easier or harder to match</span></span>

<span data-ttu-id="38e52-255">När användare skapar och aktiverar sina DLP-principer kan de ibland få följande problem:</span><span class="sxs-lookup"><span data-stu-id="38e52-255">After people create and turn on their DLP policies, they sometimes run into these issues:</span></span>
  
- <span data-ttu-id="38e52-256">För mycket innehåll som **inte är** känslig information matchar reglerna, med andra ord för många falska positiva resultat.</span><span class="sxs-lookup"><span data-stu-id="38e52-256">Too much content that **is not** sensitive information matches the rules — in other words, too many false positives.</span></span> 
    
- <span data-ttu-id="38e52-257">För lite innehåll som **är känslig** information matchar reglerna.</span><span class="sxs-lookup"><span data-stu-id="38e52-257">Too little content that **is** sensitive information matches the rules.</span></span> <span data-ttu-id="38e52-258">Skyddsåtgärder upprätthålls alltså inte för den känsliga informationen.</span><span class="sxs-lookup"><span data-stu-id="38e52-258">In other words, the protective actions aren't being enforced on the sensitive information.</span></span> 
    
<span data-ttu-id="38e52-259">För att åtgärda dessa problem kan du justera reglerna genom att justera antalet förekomster och matchningsprecisionen för att göra det svårare eller enklare för innehållet att matcha reglerna.</span><span class="sxs-lookup"><span data-stu-id="38e52-259">To address these issues, you can tune your rules by adjusting the instance count and match accuracy to make it harder or easier for content to match the rules.</span></span> <span data-ttu-id="38e52-260">Varje typ av känslig information som används i en regel har både antal förekomster och matchningsprecision.</span><span class="sxs-lookup"><span data-stu-id="38e52-260">Each sensitive information type used in a rule has both an instance count and match accuracy.</span></span>
  
### <a name="instance-count"></a><span data-ttu-id="38e52-261">Antal instanser</span><span class="sxs-lookup"><span data-stu-id="38e52-261">Instance count</span></span>

<span data-ttu-id="38e52-262">Antal förekomster innebär bara hur många förekomster av en viss typ av känslig information som måste finnas för att innehållet ska matcha regeln.</span><span class="sxs-lookup"><span data-stu-id="38e52-262">Instance count means simply how many occurrences of a specific type of sensitive information must be present for content to match the rule.</span></span> <span data-ttu-id="38e52-263">Innehåll matchar till exempel regeln nedan om mellan 1 och 9 unika usa eller Storbritannien.</span><span class="sxs-lookup"><span data-stu-id="38e52-263">For example, content matches the rule shown below if between 1 and 9 unique U.S. or U.K.</span></span> <span data-ttu-id="38e52-264">passnummer identifieras.</span><span class="sxs-lookup"><span data-stu-id="38e52-264">passport numbers are identified.</span></span>

> [!NOTE]
> <span data-ttu-id="38e52-265">Antalet förekomster omfattar endast **unika matchningar** för typer av känslig information och nyckelord.</span><span class="sxs-lookup"><span data-stu-id="38e52-265">The instance count includes only **unique** matches for sensitive information types and keywords.</span></span> <span data-ttu-id="38e52-266">Om ett e-postmeddelande till exempel innehåller 10 förekomster av samma kreditkortsnummer räknas dessa tio förekomster som en enskild förekomst av ett kreditkortsnummer.</span><span class="sxs-lookup"><span data-stu-id="38e52-266">For example, if an email contains 10 occurrences of the same credit card number, those 10 occurrences count as a single instance of a credit card number.</span></span>
  
<span data-ttu-id="38e52-267">Om du vill använda antal instanser för att finjustera regler är vägledningen enkel:</span><span class="sxs-lookup"><span data-stu-id="38e52-267">To use instance count to tune rules, the guidance is straightforward:</span></span>
  
- <span data-ttu-id="38e52-268">För att regeln ska bli lättare att matcha minskar du **minantalet** och/eller ökar **maxantalet.**</span><span class="sxs-lookup"><span data-stu-id="38e52-268">To make the rule easier to match, decrease the **min** count and/or increase the **max** count.</span></span> <span data-ttu-id="38e52-269">Du kan också ange **maxvärdet** för **ett värde genom** att ta bort det numeriska värdet.</span><span class="sxs-lookup"><span data-stu-id="38e52-269">You can also set **max** to **any** by deleting the numerical value.</span></span> 
    
- <span data-ttu-id="38e52-270">Öka minantalet för att regeln ska bli svårare **att matcha.**</span><span class="sxs-lookup"><span data-stu-id="38e52-270">To make the rule harder to match, increase the **min** count.</span></span> 
    
<span data-ttu-id="38e52-271">Vanligtvis använder du mindre restriktiva åtgärder, till exempel att skicka användarmeddelanden, i en regel med ett lägre antal instanser (till exempel 1–9).</span><span class="sxs-lookup"><span data-stu-id="38e52-271">Typically, you use less restrictive actions, such as sending user notifications, in a rule with a lower instance count (for example, 1-9).</span></span> <span data-ttu-id="38e52-272">Och du använder mer restriktiva åtgärder, till exempel att begränsa åtkomsten till innehåll utan att tillåta åsidosättningar av användare, i en regel med ett högre antal förekomster (till exempel 10-alla).</span><span class="sxs-lookup"><span data-stu-id="38e52-272">And you use more restrictive actions, such as restricting access to content without allowing user overrides, in a rule with a higher instance count (for example, 10-any).</span></span>
  
![Antal förekomster i regelredigeraren](../media/e7ea3c12-72c5-4bb3-9590-c924c665e84d.png)
  
### <a name="match-accuracy"></a><span data-ttu-id="38e52-274">Matchningsprecision</span><span class="sxs-lookup"><span data-stu-id="38e52-274">Match accuracy</span></span>

<span data-ttu-id="38e52-275">Enligt beskrivningen ovan definieras och identifieras en typ av känslig information genom en kombination av olika typer av bevis.</span><span class="sxs-lookup"><span data-stu-id="38e52-275">As described above, a sensitive information type is defined and detected by using a combination of different types of evidence.</span></span> <span data-ttu-id="38e52-276">En typ av känslig information definieras ofta av flera sådana kombinationer, så kallade mönster.</span><span class="sxs-lookup"><span data-stu-id="38e52-276">Commonly, a sensitive information type is defined by multiple such combinations, called patterns.</span></span> <span data-ttu-id="38e52-277">Ett mönster som kräver mindre bevis har en lägre matchningsprecision (eller konfidensnivå), medan ett mönster som kräver fler bevis har högre matchningsprecision (eller konfidensnivå).</span><span class="sxs-lookup"><span data-stu-id="38e52-277">A pattern that requires less evidence has a lower match accuracy (or confidence level), while a pattern that requires more evidence has a higher match accuracy (or confidence level).</span></span> <span data-ttu-id="38e52-278">Mer information om de faktiska mönster och konfidensnivåer som används av alla typer av känslig information finns i Definitioner av [typ av känslig information.](sensitive-information-type-entity-definitions.md)</span><span class="sxs-lookup"><span data-stu-id="38e52-278">To learn more about the actual patterns and confidence levels used by every sensitive information type, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md).</span></span>
  
<span data-ttu-id="38e52-279">Den typ av känslig information som heter Kreditkortsnummer definieras till exempel med två mönster:</span><span class="sxs-lookup"><span data-stu-id="38e52-279">For example, the sensitive information type named Credit Card Number is defined by two patterns:</span></span>
  
- <span data-ttu-id="38e52-280">Ett mönster med 65 % konfidens som kräver:</span><span class="sxs-lookup"><span data-stu-id="38e52-280">A pattern with 65% confidence that requires:</span></span>
    
  - <span data-ttu-id="38e52-281">Ett tal i ett kreditkortsnummer.</span><span class="sxs-lookup"><span data-stu-id="38e52-281">A number in the format of a credit card number.</span></span>
    
  - <span data-ttu-id="38e52-282">Ett tal som klarar kontrollsumman.</span><span class="sxs-lookup"><span data-stu-id="38e52-282">A number that passes the checksum.</span></span>
    
- <span data-ttu-id="38e52-283">Ett mönster med 85 % säkerhet som kräver:</span><span class="sxs-lookup"><span data-stu-id="38e52-283">A pattern with 85% confidence that requires:</span></span>
    
  - <span data-ttu-id="38e52-284">Ett tal i ett kreditkortsnummer.</span><span class="sxs-lookup"><span data-stu-id="38e52-284">A number in the format of a credit card number.</span></span>
    
  - <span data-ttu-id="38e52-285">Ett tal som klarar kontrollsumman.</span><span class="sxs-lookup"><span data-stu-id="38e52-285">A number that passes the checksum.</span></span>
    
  - <span data-ttu-id="38e52-286">Ett nyckelord eller ett utgångsdatum i rätt format.</span><span class="sxs-lookup"><span data-stu-id="38e52-286">A keyword or an expiration date in the right format.</span></span>
    
<span data-ttu-id="38e52-287">Du kan använda dessa konfidensnivåer (eller matchningsprecision) i reglerna.</span><span class="sxs-lookup"><span data-stu-id="38e52-287">You can use these confidence levels (or match accuracy) in your rules.</span></span> <span data-ttu-id="38e52-288">Vanligtvis använder du mindre restriktiva åtgärder, till exempel att skicka användarmeddelanden, i en regel med lägre matchningsprecision.</span><span class="sxs-lookup"><span data-stu-id="38e52-288">Typically, you use less restrictive actions, such as sending user notifications, in a rule with lower match accuracy.</span></span> <span data-ttu-id="38e52-289">Och du använder mer restriktiva åtgärder, till exempel att begränsa åtkomsten till innehåll utan att tillåta åsidosättningar av användare, i en regel med högre matchningsprecision.</span><span class="sxs-lookup"><span data-stu-id="38e52-289">And you use more restrictive actions, such as restricting access to content without allowing user overrides, in a rule with higher match accuracy.</span></span>
  
<span data-ttu-id="38e52-290">Det är viktigt att förstå att när en viss typ av känslig information, t.ex. kreditkortsnummer, identifieras i innehåll returneras bara ett enda konfidensnivå:</span><span class="sxs-lookup"><span data-stu-id="38e52-290">It's important to understand that when a specific type of sensitive information, such as a credit card number, is identified in content, only a single confidence level is returned:</span></span>
  
- <span data-ttu-id="38e52-291">Om alla matchningar gäller för ett enda mönster returneras konfidensnivån för det mönstret.</span><span class="sxs-lookup"><span data-stu-id="38e52-291">If all of the matches are for a single pattern, the confidence level for that pattern is returned.</span></span>
    
- <span data-ttu-id="38e52-292">Om det finns matchningar för fler än ett mönster (det vill säga det finns matchningar med två olika konfidensnivåer), returneras en konfidensnivå som är högre än något av de enskilda mönsteren.</span><span class="sxs-lookup"><span data-stu-id="38e52-292">If there are matches for more than one pattern (that is, there are matches with two different confidence levels), a confidence level higher than any of the single patterns alone is returned.</span></span> <span data-ttu-id="38e52-293">Det här är den knepiga delen.</span><span class="sxs-lookup"><span data-stu-id="38e52-293">This is the tricky part.</span></span> <span data-ttu-id="38e52-294">Om både 65 % och 85 % mönster matchas för ett kreditkort, är den konfidensnivå som returneras för den känsliga informationstypen större än 90 % eftersom fler bevis innebär mer förtroende.</span><span class="sxs-lookup"><span data-stu-id="38e52-294">For example, for a credit card, if both the 65% and 85% patterns are matched, the confidence level returned for that sensitive information type is greater than 90% because more evidence means more confidence.</span></span>
    
<span data-ttu-id="38e52-295">Så om du vill skapa två ömsesidigt uteslutande regler för kreditkort, en för 65 % matchningsprecision och en för 85 % matchningsprecision, skulle intervallen för matchningsprecision se ut så här.</span><span class="sxs-lookup"><span data-stu-id="38e52-295">So if you want to create two mutually exclusive rules for credit cards, one for the 65% match accuracy and one for the 85% match accuracy, the ranges for match accuracy would look like this.</span></span> <span data-ttu-id="38e52-296">Den första regeln tar endast upp matchningar för mönstret på 65 %.</span><span class="sxs-lookup"><span data-stu-id="38e52-296">The first rule picks up only matches of the 65% pattern.</span></span> <span data-ttu-id="38e52-297">Den andra regeln tar upp matchningar **med minst en** matchning på 85 % och kan potentiellt ha andra matchningar med lägre förtroende. </span><span class="sxs-lookup"><span data-stu-id="38e52-297">The second rule picks up matches with **at least one** 85% match and **can potentially have** other lower-confidence matches.</span></span> 
  
![Två regler med olika intervall för att matcha precisionen](../media/21bdfe36-7a91-4347-8098-11809a92f9a4.png)
  
<span data-ttu-id="38e52-299">Därför är vägledningen för att skapa regler med olika matchningsprecision:</span><span class="sxs-lookup"><span data-stu-id="38e52-299">For these reasons, the guidance for creating rules with different match accuracies is:</span></span>
  
- <span data-ttu-id="38e52-300">Den lägsta konfidensnivån använder vanligtvis samma värde för **min och** **max** (inte ett intervall).</span><span class="sxs-lookup"><span data-stu-id="38e52-300">The lowest confidence level typically uses the same value for **min** and **max** (not a range).</span></span> 
    
- <span data-ttu-id="38e52-301">Den högsta konfidensnivån är vanligtvis ett intervall från strax över den lägre konfidensnivån till 100.</span><span class="sxs-lookup"><span data-stu-id="38e52-301">The highest confidence level is typically a range from just above the lower confidence level to 100.</span></span>
    
- <span data-ttu-id="38e52-302">Konfidensnivåer mellan konfidensnivåer ligger normalt strax över den lägre konfidensnivån till strax under den högre konfidensnivån.</span><span class="sxs-lookup"><span data-stu-id="38e52-302">Any in-between confidence levels typically range from just above the lower confidence level to just below the higher confidence level.</span></span>
    
## <a name="using-a-retention-label-as-a-condition-in-a-dlp-policy"></a><span data-ttu-id="38e52-303">Använda en bevarandeetikett som ett villkor i en DLP-princip</span><span class="sxs-lookup"><span data-stu-id="38e52-303">Using a retention label as a condition in a DLP policy</span></span>

<span data-ttu-id="38e52-304">När du använder en tidigare skapad och publicerad [bevarandeetikett](retention.md#retention-labels) som ett villkor i en DLP-princip finns det några saker du bör känna till:</span><span class="sxs-lookup"><span data-stu-id="38e52-304">When you use a previously created and published [retention label](retention.md#retention-labels) as a condition in a DLP policy, there are some things to be aware of:</span></span>

- <span data-ttu-id="38e52-305">Bevarandeetiketten måste skapas och publiceras innan du kan använda den som ett villkor i en DLP-princip.</span><span class="sxs-lookup"><span data-stu-id="38e52-305">The retention label must be created and published before you attempt to use it as a condition in a DLP policy.</span></span>
- <span data-ttu-id="38e52-306">Publicerade bevarandeetiketter kan ta från en till sju dagar att synkronisera. Mer information finns [](create-apply-retention-labels.md#when-retention-labels-become-available-to-apply) i När bevarandeetiketter blir tillgängliga för bevarandeetiketter som publiceras i en bevarandeprincip och Hur lång tid det tar för de bevarandeetiketter som publiceras automatiskt att gälla. [](apply-retention-labels-automatically.md#how-long-it-takes-for-retention-labels-to-take-effect)</span><span class="sxs-lookup"><span data-stu-id="38e52-306">Published retention labels can take from one to seven days to sync. For more information, see [When retention labels become available to apply](create-apply-retention-labels.md#when-retention-labels-become-available-to-apply) for retention labels published in a retention policy, and [How long it takes for retention labels to take effect](apply-retention-labels-automatically.md#how-long-it-takes-for-retention-labels-to-take-effect) for retention labels that are auto-published.</span></span>
- <span data-ttu-id="38e52-307">Bevarandeetiketter stöds bara för objekt i SharePoint och OneDrive\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="38e52-307">Using a retention label in a policy \*\*is only supported for items in SharePoint and OneDrive\*\*\*.</span></span>

  ![Etiketter som ett villkor](../media/5b1752b4-a129-4a88-b010-8dcf8a38bb09.png)

  <span data-ttu-id="38e52-309">Du kanske vill använda en bevarandeetikett i en DLP-princip om det finns objekt som ligger under bevarande och disposition, och du även vill tillämpa andra kontroller på dem, till exempel:</span><span class="sxs-lookup"><span data-stu-id="38e52-309">You might want to use a retention label in a DLP policy if you have items that are under retention and disposition, and you also want to apply other controls to them, for example:</span></span>

  - <span data-ttu-id="38e52-310">Du publicerade en bevarandeetikett med namnet Moms **år 2018,** som när den används för skattedokument från 2018 som lagras i SharePoint behåller dem i 10 år.</span><span class="sxs-lookup"><span data-stu-id="38e52-310">You published a retention label named **tax year 2018**, which when applied to tax documents from 2018 that are stored in SharePoint retains them for 10 years then disposes of them.</span></span> <span data-ttu-id="38e52-311">Du vill inte heller att de objekten ska delas utanför organisationen, vilket du kan göra med en DLP-princip.</span><span class="sxs-lookup"><span data-stu-id="38e52-311">You also don't want those items being shared outside your organization, which you can do with a DLP policy.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="38e52-312">Det här felmeddelandet visas om du anger en bevarandeetikett som ett villkor i en DLP-princip och du även tar med Exchange och/eller Teams som en plats: "Skydda märkt innehåll i e-postmeddelanden och gruppmeddelanden stöds **inte. Ta antingen bort etiketten nedan eller inaktivera Exchange och Teams som en plats".**</span><span class="sxs-lookup"><span data-stu-id="38e52-312">You'll get this error if you specify a retention label as a condition in a DLP policy and you also include Exchange and/or Teams as a location: **"Protecting labeled content in email and teams messages isn't supported. Either remove the label below or turn off Exchange and Teams as a location."**</span></span> <span data-ttu-id="38e52-313">Det beror på Exchange transport inte utvärderar etikettmetadata vid sändning och leverans av meddelanden.</span><span class="sxs-lookup"><span data-stu-id="38e52-313">This is because Exchange transport does not evaluate the label metadata during message submission and delivery.</span></span> 

### <a name="using-a-sensitivity-label-as-a-condition-in-a-dlp-policy"></a><span data-ttu-id="38e52-314">Använda en känslighetsetikett som ett villkor i en DLP-princip</span><span class="sxs-lookup"><span data-stu-id="38e52-314">Using a sensitivity label as a condition in a DLP policy</span></span>

<span data-ttu-id="38e52-315">Känslighetsetikett som ett villkor i DLP-principer är för närvarande i förhandsgranskning.</span><span class="sxs-lookup"><span data-stu-id="38e52-315">Sensitivity label as a condition in DLP policies is currently in preview.</span></span> <span data-ttu-id="38e52-316">[Mer information](./dlp-sensitivity-label-as-condition.md).</span><span class="sxs-lookup"><span data-stu-id="38e52-316">[Learn more](./dlp-sensitivity-label-as-condition.md).</span></span>
  
### <a name="how-this-feature-relates-to-other-features"></a><span data-ttu-id="38e52-317">Hur den här funktionen relaterar till andra funktioner</span><span class="sxs-lookup"><span data-stu-id="38e52-317">How this feature relates to other features</span></span>

<span data-ttu-id="38e52-318">Flera funktioner kan användas på innehåll som innehåller känslig information:</span><span class="sxs-lookup"><span data-stu-id="38e52-318">Several features can be applied to content containing sensitive information:</span></span>
  
- <span data-ttu-id="38e52-319">[Bevarandeetiketter och bevarandeprinciper kan](retention.md) både tillämpa **bevarandeåtgärder** på innehållet.</span><span class="sxs-lookup"><span data-stu-id="38e52-319">A [retention label and a retention policy](retention.md) can both enforce **retention** actions on this content.</span></span> 
    
- <span data-ttu-id="38e52-320">En DLP-princip kan tillämpa **skyddsåtgärder** på det här innehållet.</span><span class="sxs-lookup"><span data-stu-id="38e52-320">A DLP policy can enforce **protection** actions on this content.</span></span> <span data-ttu-id="38e52-321">Innan dessa åtgärder framtvingas kan en DLP-princip kräva att andra villkor uppfylls utöver det innehåll som innehåller en etikett.</span><span class="sxs-lookup"><span data-stu-id="38e52-321">And before enforcing these actions, a DLP policy can require other conditions to be met in addition to the content containing a label.</span></span> 
    
![Diagram över funktioner som kan användas för känslig information](../media/dd410f97-a3a3-455c-a1e9-7ed8ae6893d6.png)
  
<span data-ttu-id="38e52-323">Observera att en DLP-princip har bättre identifieringsfunktioner än en etikett- eller kvarhållningsprincip som används för känslig information.</span><span class="sxs-lookup"><span data-stu-id="38e52-323">Note that a DLP policy has a richer detection capability than a label or retention policy applied to sensitive information.</span></span> <span data-ttu-id="38e52-324">En DLP-princip kan tillämpa skyddsåtgärder för innehåll som innehåller känslig information och om den känsliga informationen tas bort från innehållet ångras skyddsåtgärderna nästa gång innehållet genomsöks.</span><span class="sxs-lookup"><span data-stu-id="38e52-324">A DLP policy can enforce protective actions on content containing sensitive information, and if the sensitive information is removed from the content, those protective actions are undone the next time the content's scanned.</span></span> <span data-ttu-id="38e52-325">Men om en bevarandeprincip eller etikett används på innehåll som innehåller känslig information är det en enda åtgärd som inte kan ångras även om den känsliga informationen tas bort.</span><span class="sxs-lookup"><span data-stu-id="38e52-325">But if a retention policy or label is applied to content containing sensitive information, that's a one-time action that won't be undone even if the sensitive information is removed.</span></span>
  
<span data-ttu-id="38e52-326">Genom att använda en etikett som ett villkor i en DLP-princip kan du tillämpa både bevarande- och skyddsåtgärder på innehåll med den etiketten.</span><span class="sxs-lookup"><span data-stu-id="38e52-326">By using a label as a condition in a DLP policy, you can enforce both retention and protection actions on content with that label.</span></span> <span data-ttu-id="38e52-327">Du kan tänka på innehåll som innehåller en etikett exakt som innehåll som innehåller känslig information – både en etikett och en typ av känslig information används för att klassificera innehåll, så att du kan tillämpa åtgärder på innehållet.</span><span class="sxs-lookup"><span data-stu-id="38e52-327">You can think of content containing a label exactly like content containing sensitive information - both a label and a sensitive information type are properties used to classify content, so that you can enforce actions on that content.</span></span>
  
![Diagram över DLP-princip med etikett som villkor](../media/4538fd8f-fb74-4743-bc22-a5de33adfebb.png)
  
## <a name="simple-settings-vs-advanced-settings"></a><span data-ttu-id="38e52-329">Enkla inställningar jämfört med avancerade inställningar</span><span class="sxs-lookup"><span data-stu-id="38e52-329">Simple settings vs. advanced settings</span></span>

<span data-ttu-id="38e52-330">När du skapar en DLP-princip väljer du mellan enkla eller avancerade inställningar:</span><span class="sxs-lookup"><span data-stu-id="38e52-330">When you create a DLP policy, you'll choose between simple or advanced settings:</span></span>
  
- <span data-ttu-id="38e52-331">**Med enkla** inställningar är det enkelt att skapa den vanligaste typen av DLP-princip utan att använda regelredigeraren för att skapa eller ändra regler.</span><span class="sxs-lookup"><span data-stu-id="38e52-331">**Simple settings** make it easy to create the most common type of DLP policy without using the rule editor to create or modify rules.</span></span> 
    
- <span data-ttu-id="38e52-332">**Avancerade inställningar** använder regelredigeraren för att ge dig fullständig kontroll över alla inställningar för DLP-principen.</span><span class="sxs-lookup"><span data-stu-id="38e52-332">**Advanced settings** use the rule editor to give you complete control over every setting for your DLP policy.</span></span> 
    
<span data-ttu-id="38e52-333">Men oroa dig inte. Enkla inställningar och avancerade inställningar fungerar på exakt samma sätt under tvingande regler som utgörs av villkor och åtgärder, men med enkla inställningar visas inte regelredigeraren.</span><span class="sxs-lookup"><span data-stu-id="38e52-333">Don't worry, under the covers, simple settings and advanced settings work exactly the same, by enforcing rules comprised of conditions and actions—only with simple settings, you don't see the rule editor.</span></span> <span data-ttu-id="38e52-334">Det är ett snabbt sätt att skapa en DLP-princip.</span><span class="sxs-lookup"><span data-stu-id="38e52-334">It's a quick way to create a DLP policy.</span></span>
  
### <a name="simple-settings"></a><span data-ttu-id="38e52-335">Enkla inställningar</span><span class="sxs-lookup"><span data-stu-id="38e52-335">Simple settings</span></span>

<span data-ttu-id="38e52-336">Det vanligaste DLP-scenariot är att skapa en princip som hjälper till att skydda innehåll som innehåller känslig information från att delas med personer utanför organisationen, och vidta en automatisk åtgärd, till exempel att begränsa vem som kan komma åt innehållet, skicka meddelanden till slutanvändaren eller administratörer och granska händelsen för senare undersökning.</span><span class="sxs-lookup"><span data-stu-id="38e52-336">By far, the most common DLP scenario is creating a policy to help protect content containing sensitive information from being shared with people outside your organization, and taking an automatic remediating action such as restricting who can access the content, sending end-user or admin notifications, and auditing the event for later investigation.</span></span> <span data-ttu-id="38e52-337">Användare använder DLP för att förhindra att känslig information oavsiktligt delar på informationen.</span><span class="sxs-lookup"><span data-stu-id="38e52-337">People use DLP to help prevent the inadvertent disclosure of sensitive information.</span></span>
  
<span data-ttu-id="38e52-338">Om du vill göra det enklare att uppnå detta mål kan du när du skapar en DLP-princip **välja Använd enkla inställningar.**</span><span class="sxs-lookup"><span data-stu-id="38e52-338">To simplify achieving this goal, when you create a DLP policy, you can choose **Use simple settings**.</span></span> <span data-ttu-id="38e52-339">Med de här inställningarna får du allt du behöver för att implementera den vanligaste DLP-principen utan att behöva gå in i regelredigeraren.</span><span class="sxs-lookup"><span data-stu-id="38e52-339">These settings provide everything you need to implement the most common DLP policy, without having to go into the rule editor.</span></span>
  
![DLP-alternativ för enkla och avancerade inställningar](../media/33c93824-ead5-43b6-9c3e-fd1630c92a7d.png)
  
### <a name="advanced-settings"></a><span data-ttu-id="38e52-341">Avancerade inställningar</span><span class="sxs-lookup"><span data-stu-id="38e52-341">Advanced settings</span></span>

<span data-ttu-id="38e52-342">Om du behöver skapa mer anpassade DLP-principer kan du välja **Använd avancerade inställningar.**</span><span class="sxs-lookup"><span data-stu-id="38e52-342">If you need to create more customized DLP policies, you can choose **Use advanced settings**.</span></span>
  
<span data-ttu-id="38e52-343">I de avancerade inställningarna visas regelredigeraren, där du har full kontroll över alla möjliga alternativ, inklusive antal förekomster och matchning av noggrannhet (konfidensnivå) för varje regel.</span><span class="sxs-lookup"><span data-stu-id="38e52-343">The advanced settings present you with the rule editor, where you have full control over every possible option, including the instance count and match accuracy (confidence level) for each rule.</span></span>
  
<span data-ttu-id="38e52-344">Om du snabbt vill hoppa till ett avsnitt klickar du på ett objekt i det övre navigeringsfältet i regelredigeraren för att gå till avsnittet nedan.</span><span class="sxs-lookup"><span data-stu-id="38e52-344">To jump to a section quickly, click an item in the top navigation of the rule editor to go to that section below.</span></span>
  
![Övre navigeringsmenyn i DLP-regelredigeraren](../media/c527b97f-ca53-4c79-ad19-1a63be8a8ecc.png)
  
## <a name="dlp-policy-templates"></a><span data-ttu-id="38e52-346">DLP-principmallar</span><span class="sxs-lookup"><span data-stu-id="38e52-346">DLP policy templates</span></span>

<span data-ttu-id="38e52-347">Det första steget när du skapar en DLP-princip är att välja vilken information som ska skyddas.</span><span class="sxs-lookup"><span data-stu-id="38e52-347">The first step in creating a DLP policy is choosing what information to protect.</span></span> <span data-ttu-id="38e52-348">Genom att börja med en DLP-mall sparar du arbetet med att skapa en ny uppsättning regler från grunden och ta reda på vilka typer av information som ska ingå som standard.</span><span class="sxs-lookup"><span data-stu-id="38e52-348">By starting with a DLP template, you save the work of building a new set of rules from scratch, and figuring out which types of information should be included by default.</span></span> <span data-ttu-id="38e52-349">Du kan sedan lägga till eller ändra dessa krav för att finjustera regeln så att den uppfyller organisationens specifika krav.</span><span class="sxs-lookup"><span data-stu-id="38e52-349">You can then add to or modify these requirements to fine tune the rule to meet your organization's specific requirements.</span></span>
  
<span data-ttu-id="38e52-350">En förkonfigurerad DLP-principmall kan hjälpa dig att identifiera särskilda typer av känslig information, t.ex. HIPAA-data, PENO-DSS-data, Gramm-Leach-Bliley Act-data eller till och med språkspecifik personligt identifierbar information (P.I.).</span><span class="sxs-lookup"><span data-stu-id="38e52-350">A preconfigured DLP policy template can help you detect specific types of sensitive information, such as HIPAA data, PCI-DSS data, Gramm-Leach-Bliley Act data, or even locale-specific personally identifiable information (P.I.).</span></span> <span data-ttu-id="38e52-351">För att göra det enkelt för dig att hitta och skydda vanliga typer av känslig information innehåller principmallarna i Microsoft 365 redan de vanligaste typerna av känslig information så att du kan komma igång.</span><span class="sxs-lookup"><span data-stu-id="38e52-351">To make it easy for you to find and protect common types of sensitive information, the policy templates included in Microsoft 365 already contain the most common sensitive information types necessary for you to get started.</span></span>
  
![Lista över mallar för policyer för dataförlustskydd med fokus på mall för U.S. Act](../media/791b2403-430b-4987-8643-cc20abbd8148.png)
  
<span data-ttu-id="38e52-353">Organisationen kan också ha egna specifika krav. I sådana fall kan du skapa en DLP-princip från grunden genom att välja **alternativet Anpassad** princip.</span><span class="sxs-lookup"><span data-stu-id="38e52-353">Your organization may also have its own specific requirements, in which case you can create a DLP policy from scratch by choosing the **Custom policy** option.</span></span> <span data-ttu-id="38e52-354">En anpassad princip är tom och innehåller inga förinmade regler.</span><span class="sxs-lookup"><span data-stu-id="38e52-354">A custom policy is empty and contains no premade rules.</span></span> 
  
## <a name="roll-out-dlp-policies-gradually-with-test-mode"></a><span data-ttu-id="38e52-355">Distribuera DLP-principer gradvis med testläge</span><span class="sxs-lookup"><span data-stu-id="38e52-355">Roll out DLP policies gradually with test mode</span></span>

<span data-ttu-id="38e52-356">När du skapar DLP-principerna bör du överväga att lansera dem gradvis för att bedöma deras påverkan och testa deras effektivitet innan du helt tillämpar dem.</span><span class="sxs-lookup"><span data-stu-id="38e52-356">When you create your DLP policies, you should consider rolling them out gradually to assess their impact and test their effectiveness before fully enforcing them.</span></span> <span data-ttu-id="38e52-357">Du vill t.ex. inte att en ny DLP-princip oavsiktligt ska blockera åtkomst till tusentals dokument som personer behöver åtkomst till för att få jobbet gjort.</span><span class="sxs-lookup"><span data-stu-id="38e52-357">For example, you don't want a new DLP policy to unintentionally block access to thousands of documents that people require access to in order to get their work done.</span></span>
  
<span data-ttu-id="38e52-358">Om du skapar DLP-principer med stor potential rekommenderar vi att du följer den här ordningen:</span><span class="sxs-lookup"><span data-stu-id="38e52-358">If you're creating DLP policies with a large potential impact, we recommend following this sequence:</span></span>
  
1. <span data-ttu-id="38e52-359">**Börja i testläge utan Tips** och använd sedan DLP-rapporter och eventuella incidentrapporter för att bedöma påverkan.</span><span class="sxs-lookup"><span data-stu-id="38e52-359">**Start in test mode without Policy Tips** and then use the DLP reports and any incident reports to assess the impact.</span></span> <span data-ttu-id="38e52-360">Du kan använda DLP-rapporter för att visa antal, plats, typ och allvarlighetsgrad för principmatchningar.</span><span class="sxs-lookup"><span data-stu-id="38e52-360">You can use DLP reports to view the number, location, type, and severity of policy matches.</span></span> <span data-ttu-id="38e52-361">Baserat på resultatet kan du finjustera reglerna efter behov.</span><span class="sxs-lookup"><span data-stu-id="38e52-361">Based on the results, you can fine tune the rules as needed.</span></span> <span data-ttu-id="38e52-362">I testläge påverkar inte DLP-principerna produktiviteten för personer som arbetar i organisationen.</span><span class="sxs-lookup"><span data-stu-id="38e52-362">In test mode, DLP policies will not impact the productivity of people working in your organization.</span></span> 
    
2. <span data-ttu-id="38e52-363">**Flytta till testläge med** meddelanden och princip Tips så att du kan börja lära användarna om dina efterlevnadsprinciper och förbereda dem för de regler som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="38e52-363">**Move to Test mode with notifications and Policy Tips** so that you can begin to teach users about your compliance policies and prepare them for the rules that are going to be applied.</span></span> <span data-ttu-id="38e52-364">I det här läget kan du också be användarna att rapportera falska positiva resultat så att du kan ytterligare förfina reglerna.</span><span class="sxs-lookup"><span data-stu-id="38e52-364">At this stage, you can also ask users to report false positives so that you can further refine the rules.</span></span> 
    
3. <span data-ttu-id="38e52-365">**Börja tillämpa principerna fullt ut** så att åtgärderna i reglerna tillämpas och att innehållet skyddas.</span><span class="sxs-lookup"><span data-stu-id="38e52-365">**Start full enforcement on the policies** so that the actions in the rules are applied and the content's protected.</span></span> <span data-ttu-id="38e52-366">Fortsätt att övervaka DLP-rapporterna och eventuella incidentrapporter och -aviseringar för att se till att du får de resultat du vill ha.</span><span class="sxs-lookup"><span data-stu-id="38e52-366">Continue to monitor the DLP reports and any incident reports or notifications to make sure that the results are what you intend.</span></span> 

    ![Alternativ för att använda testläge och aktivera princip](../media/49fafaac-c6cb-41de-99c4-c43c3e380c3a.png)

    <span data-ttu-id="38e52-368">Du kan inaktivera en DLP-princip när som helst, vilket påverkar alla regler i principen.</span><span class="sxs-lookup"><span data-stu-id="38e52-368">You can turn off a DLP policy at any time, which affects all rules in the policy.</span></span> <span data-ttu-id="38e52-369">Men varje regel kan också inaktiveras individuellt genom att växla status i regelredigeraren.</span><span class="sxs-lookup"><span data-stu-id="38e52-369">However, each rule can also be turned off individually by toggling its status in the rule editor.</span></span>

    ![Alternativ för att inaktivera en regel i en princip](../media/f7b258ff-1b8b-4127-b580-83c6492f2bef.png)

    <span data-ttu-id="38e52-371">Du kan också ändra prioriteten för flera regler i en princip.</span><span class="sxs-lookup"><span data-stu-id="38e52-371">You can also change the priority of multiple rules in a policy.</span></span> <span data-ttu-id="38e52-372">Det gör du genom att öppna en princip för redigering.</span><span class="sxs-lookup"><span data-stu-id="38e52-372">To do that, open a policy for editing.</span></span> <span data-ttu-id="38e52-373">På en rad för en regel väljer du ellipsen (**...**) och väljer sedan ett alternativ, till exempel Flytta **ned** eller **Bring to last**.</span><span class="sxs-lookup"><span data-stu-id="38e52-373">In a row for a rule, choose the ellipses (**...**), and then choose an option, such as **Move down** or **Bring to last**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="38e52-374">![Ange regelprioritet](../media/dlp-set-rule-priority.png)</span><span class="sxs-lookup"><span data-stu-id="38e52-374">![Set rule priority](../media/dlp-set-rule-priority.png)</span></span>
  
## <a name="dlp-reports"></a><span data-ttu-id="38e52-375">DLP-rapporter</span><span class="sxs-lookup"><span data-stu-id="38e52-375">DLP reports</span></span>

<span data-ttu-id="38e52-376">När du har skapat och aktiverar DLP-principerna ska du kontrollera att de fungerar som du tänkt dig och hjälpa dig att uppfylla kraven.</span><span class="sxs-lookup"><span data-stu-id="38e52-376">After you create and turn on your DLP policies, you'll want to verify that they're working as you intended and helping you stay compliant.</span></span> <span data-ttu-id="38e52-377">Med DLP-rapporter kan du snabbt se antalet matchningar och matchningar av DLP-regler över tid och antalet felaktiga matchningar och åsidosättanden.</span><span class="sxs-lookup"><span data-stu-id="38e52-377">With DLP reports, you can quickly view the number of DLP policy and rule matches over time, and the number of false positives and overrides.</span></span> <span data-ttu-id="38e52-378">För varje rapport kan du filtrera matchningarna efter plats, tidsram och till och med begränsa det till en viss princip, regel eller åtgärd.</span><span class="sxs-lookup"><span data-stu-id="38e52-378">For each report, you can filter those matches by location, time frame, and even narrow it down to a specific policy, rule, or action.</span></span>
  
<span data-ttu-id="38e52-379">Med DLP-rapporterna kan du få affärsinsikter och:</span><span class="sxs-lookup"><span data-stu-id="38e52-379">With the DLP reports, you can get business insights and:</span></span>
  
- <span data-ttu-id="38e52-380">Fokusera på vissa tidsperioder och förstå orsakerna till toppar och trender.</span><span class="sxs-lookup"><span data-stu-id="38e52-380">Focus on specific time periods and understand the reasons for spikes and trends.</span></span>
    
- <span data-ttu-id="38e52-381">Upptäck affärsprocesser som strider mot organisationens efterlevnadsprinciper.</span><span class="sxs-lookup"><span data-stu-id="38e52-381">Discover business processes that violate your organization's compliance policies.</span></span>
    
- <span data-ttu-id="38e52-382">Förstå alla affärseffekter i DLP-principerna.</span><span class="sxs-lookup"><span data-stu-id="38e52-382">Understand any business impact of the DLP policies.</span></span>
    
<span data-ttu-id="38e52-383">Du kan dessutom använda DLP-rapporterna för att finjustera DLP-principerna när du kör dem.</span><span class="sxs-lookup"><span data-stu-id="38e52-383">In addition, you can use the DLP reports to fine tune your DLP policies as you run them.</span></span>
  
![Instrumentpanel för rapporter i Säkerhets- och efterlevnadscenter](../media/6d741252-a0ce-4429-95ba-6c857ecc9a7e.png)
  
## <a name="how-dlp-policies-work"></a><span data-ttu-id="38e52-385">Så här fungerar DLP-principer</span><span class="sxs-lookup"><span data-stu-id="38e52-385">How DLP policies work</span></span>

<span data-ttu-id="38e52-386">DLP identifierar känslig information med hjälp av djup innehållsanalys (inte bara en enkel genomsökning av text).</span><span class="sxs-lookup"><span data-stu-id="38e52-386">DLP detects sensitive information by using deep content analysis (not just a simple text scan).</span></span> <span data-ttu-id="38e52-387">Den djupa innehållsanalysen använder matchningar för nyckelord, matchningar i ordlistor, utvärdering av reguljära uttryck, interna funktioner och andra metoder för att identifiera innehåll som matchar dina DLP-principer.</span><span class="sxs-lookup"><span data-stu-id="38e52-387">This deep content analysis uses keyword matches, dictionary matches, the evaluation of regular expressions, internal functions, and other methods to detect content that matches your DLP policies.</span></span> <span data-ttu-id="38e52-388">Potentiellt sett är endast en liten procentandel av alla data att betrakta som känsliga.</span><span class="sxs-lookup"><span data-stu-id="38e52-388">Potentially only a small percentage of your data is considered sensitive.</span></span> <span data-ttu-id="38e52-389">En DLP-princip kan automatiskt identifiera, övervaka och skydda endast dessa data, utan att påverka eller påverka personer som arbetar med resten av innehållet.</span><span class="sxs-lookup"><span data-stu-id="38e52-389">A DLP policy can identify, monitor, and automatically protect just that data, without impeding or affecting people who work with the rest of your content.</span></span>
  
### <a name="policies-are-synced"></a><span data-ttu-id="38e52-390">Principer synkroniseras</span><span class="sxs-lookup"><span data-stu-id="38e52-390">Policies are synced</span></span>

<span data-ttu-id="38e52-391">När du har skapat en DLP-princip i Säkerhetsefterlevnadscenter lagras den i en central principkälla och synkroniseras sedan med de olika &amp; innehållskällorna, till exempel:</span><span class="sxs-lookup"><span data-stu-id="38e52-391">After you create a DLP policy in the Security &amp; Compliance Center, it's stored in a central policy store, and then synced to the various content sources, including:</span></span>
  
- <span data-ttu-id="38e52-392">Exchange Online och vidare till Outlook på webben och Outlook.</span><span class="sxs-lookup"><span data-stu-id="38e52-392">Exchange Online, and from there to Outlook on the web and Outlook.</span></span>
    
- <span data-ttu-id="38e52-393">OneDrive för företag webbplatser.</span><span class="sxs-lookup"><span data-stu-id="38e52-393">OneDrive for Business sites.</span></span>
    
- <span data-ttu-id="38e52-394">SharePoint Onlinewebbplatser.</span><span class="sxs-lookup"><span data-stu-id="38e52-394">SharePoint Online sites.</span></span>
    
- <span data-ttu-id="38e52-395">Office -skrivbordsprogram (Excel, PowerPoint och Word).</span><span class="sxs-lookup"><span data-stu-id="38e52-395">Office desktop programs (Excel, PowerPoint, and Word).</span></span>

- <span data-ttu-id="38e52-396">Microsoft Teams kanaler och chattmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="38e52-396">Microsoft Teams channels and chat messages.</span></span>
    
<span data-ttu-id="38e52-397">När principen har synkroniserats till rätt platser börjar den utvärdera innehåll och tillämpa åtgärder.</span><span class="sxs-lookup"><span data-stu-id="38e52-397">After the policy's synced to the right locations, it starts to evaluate content and enforce actions.</span></span>
<!-- what is the time delay for first deployment of a policy and what is the sync schedule? -->
  
### <a name="policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites"></a><span data-ttu-id="38e52-398">Principutvärderingar i OneDrive för företag och SharePoint onlinewebbplatser</span><span class="sxs-lookup"><span data-stu-id="38e52-398">Policy evaluation in OneDrive for Business and SharePoint Online sites</span></span>

<span data-ttu-id="38e52-399">I alla SharePoint Online-webbplatser och OneDrive för företag ändras ändras dokumenten kontinuerligt – de skapas, redigeras, delas och så vidare.</span><span class="sxs-lookup"><span data-stu-id="38e52-399">Across all of your SharePoint Online sites and OneDrive for Business sites, documents are constantly changing — they're continually being created, edited, shared, and so on.</span></span> <span data-ttu-id="38e52-400">Det innebär att dokumenten när som helst kan gå i konflikt med eller bli kompatibla med en DLP-princip.</span><span class="sxs-lookup"><span data-stu-id="38e52-400">This means documents can conflict or become compliant with a DLP policy at any time.</span></span> <span data-ttu-id="38e52-401">En person kan till exempel ladda upp ett dokument som inte innehåller någon känslig information på gruppwebbplatsen, men någon annan person kan senare redigera samma dokument och lägga till känslig information i det.</span><span class="sxs-lookup"><span data-stu-id="38e52-401">For example, a person can upload a document that contains no sensitive information to their team site, but later, a different person can edit the same document and add sensitive information to it.</span></span>
  
<span data-ttu-id="38e52-402">Därför söker DLP-principerna igenom dokument ofta i bakgrunden efter principmatchning.</span><span class="sxs-lookup"><span data-stu-id="38e52-402">For this reason, DLP policies check documents for policy matches frequently in the background.</span></span> <span data-ttu-id="38e52-403">Tänk på det som en asynkron principutvärdering.</span><span class="sxs-lookup"><span data-stu-id="38e52-403">You can think of this as asynchronous policy evaluation.</span></span>
<!-- what is the frequency? looks like it is tied to the search crawl schedule -->
  
#### <a name="how-it-works"></a><span data-ttu-id="38e52-404">Så här fungerar det</span><span class="sxs-lookup"><span data-stu-id="38e52-404">How it works</span></span>
 
<span data-ttu-id="38e52-405">När andra lägger till eller ändrar dokument på sina webbplatser söker sökmotor igenom innehållet så att du kan söka efter det senare.</span><span class="sxs-lookup"><span data-stu-id="38e52-405">As people add or change documents in their sites, the search engine scans the content, so that you can search for it later.</span></span> <span data-ttu-id="38e52-406">När detta händer genomsöks även innehållet efter känslig information och för att kontrollera om det delas.</span><span class="sxs-lookup"><span data-stu-id="38e52-406">While this is happening, the content's also scanned for sensitive information and to check if it's shared.</span></span> <span data-ttu-id="38e52-407">Känslig information som hittas lagras på ett säkert sätt i sökindexet, så att bara efterlevnadsteamet kan komma åt den, men inte vanliga användare.</span><span class="sxs-lookup"><span data-stu-id="38e52-407">Any sensitive information that's found is stored securely in the search index, so that only the compliance team can access it, but not typical users.</span></span> <span data-ttu-id="38e52-408">Varje DLP-princip som du har aktiverat körs i bakgrunden (asynkront), söker ofta efter innehåll som matchar en princip och tillämpar åtgärder för att skydda den från oavsiktliga läckor.</span><span class="sxs-lookup"><span data-stu-id="38e52-408">Each DLP policy that you've turned on runs in the background (asynchronously), checking search frequently for any content that matches a policy, and applying actions to protect it from inadvertent leaks.</span></span>
  
![Diagram som visar hur DLP-principen utvärderar innehållet asynkront](../media/bdf73099-039a-4909-ae89-ac12c41992ba.png)
  
<!-- conflict with a DLP policy is bad wording -->
<span data-ttu-id="38e52-410">Slutligen kan dokument vara i konflikt med en DLP-princip, men de kan också bli kompatibla med en DLP-princip.</span><span class="sxs-lookup"><span data-stu-id="38e52-410">Finally, documents can conflict with a DLP policy, but they can also become compliant with a DLP policy.</span></span> <span data-ttu-id="38e52-411">Om en person lägger till kreditkortsnummer i ett dokument kan det leda till att åtkomsten till dokumentet blockeras automatiskt av DLP-principen.</span><span class="sxs-lookup"><span data-stu-id="38e52-411">For example, if a person adds credit card numbers to a document, it might cause a DLP policy to block access to the document automatically.</span></span> <span data-ttu-id="38e52-412">Men om personen senare tar bort den känsliga informationen ångras åtgärden (i det här fallet blockeringen) automatiskt nästa gång dokumentet utvärderas mot principen.</span><span class="sxs-lookup"><span data-stu-id="38e52-412">But if the person later removes the sensitive information, the action (in this case, blocking) is automatically undone the next time the document is evaluated against the policy.</span></span>
  
<span data-ttu-id="38e52-413">DLP utvärderar allt innehåll som kan indexeras.</span><span class="sxs-lookup"><span data-stu-id="38e52-413">DLP evaluates any content that can be indexed.</span></span> <span data-ttu-id="38e52-414">Mer information om vilka filtyper som crawlas som standard finns i Filnamnstillägg som crawlas som standard och filtyper som [analyseras i SharePoint Server.](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)</span><span class="sxs-lookup"><span data-stu-id="38e52-414">For more information on what file types are crawled by default, see [Default crawled file name extensions and parsed file types in SharePoint Server](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types).</span></span>

> [!NOTE]
> <span data-ttu-id="38e52-415">För att förhindra att dokument delas innan DLP-principerna kunde analyseras kan delning av nya filer i SharePoint blockeras tills dess innehåll har indexerats.</span><span class="sxs-lookup"><span data-stu-id="38e52-415">In order to prevent documents from being shared before DLP policies had the opportunity to analyze them, sharing of new files in SharePoint can be blocked until its content has been indexed.</span></span> <span data-ttu-id="38e52-416">Mer information [finns i Markera nya filer som känsliga som](/sharepoint/sensitive-by-default) standard.</span><span class="sxs-lookup"><span data-stu-id="38e52-416">See, [Mark new files as sensitive by default](/sharepoint/sensitive-by-default) for detailed information.</span></span> 
  
### <a name="policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web"></a><span data-ttu-id="38e52-417">Principutvärderingar i Exchange Online, Outlook och Outlook på webben</span><span class="sxs-lookup"><span data-stu-id="38e52-417">Policy evaluation in Exchange Online, Outlook, and Outlook on the web</span></span>

<span data-ttu-id="38e52-418">När du skapar en DLP-princip som innehåller Exchange Online som en plats synkroniseras principen från säkerhetsefterlevnadscentret för Office 365 till Exchange Online och sedan från Exchange Online till Outlook på webben &amp; och Outlook.</span><span class="sxs-lookup"><span data-stu-id="38e52-418">When you create a DLP policy that includes Exchange Online as a location, the policy's synced from the Office 365 Security &amp; Compliance Center to Exchange Online, and then from Exchange Online to Outlook on the web and Outlook.</span></span>
  
<span data-ttu-id="38e52-419">När ett meddelande skapas i Outlook kan användaren se principtips när innehållet som skapas utvärderas mot DLP-principer.</span><span class="sxs-lookup"><span data-stu-id="38e52-419">When a message is being composed in Outlook, the user can see policy tips as the content being created is evaluated against DLP policies.</span></span> <span data-ttu-id="38e52-420">När ett meddelande har skickats utvärderas det mot DLP-principer som en normal del av e-postflödet, tillsammans med Exchange-e-postflödesregler (kallas även transportregler) och DLP-principer som skapats i Exchange-administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="38e52-420">And after a message is sent, it's evaluated against DLP policies as a normal part of mail flow, along with Exchange mail flow rules (also known as transport rules) and DLP policies created in the Exchange admin center.</span></span> <span data-ttu-id="38e52-421">DLP-principer söker igenom både meddelandet och eventuella bifogade filer.</span><span class="sxs-lookup"><span data-stu-id="38e52-421">DLP policies scan both the message and any attachments.</span></span>
  
### <a name="policy-evaluation-in-the-office-desktop-programs"></a><span data-ttu-id="38e52-422">Principutvärdering i Office skrivbordsprogram</span><span class="sxs-lookup"><span data-stu-id="38e52-422">Policy evaluation in the Office desktop programs</span></span>

<!-- same capability to identify sensitive information line conflates sensitive information types and such -->
<span data-ttu-id="38e52-423">Excel, PowerPoint och Word har samma funktion för att identifiera känslig information och använda DLP-principer som SharePoint Online och OneDrive för företag.</span><span class="sxs-lookup"><span data-stu-id="38e52-423">Excel, PowerPoint, and Word include the same capability to identify sensitive information and apply DLP policies as SharePoint Online and OneDrive for Business.</span></span> <span data-ttu-id="38e52-424">Dessa Office-program synkroniserar sina DLP-principer direkt från det centrala principarkivet och utvärderar sedan kontinuerligt innehållet mot DLP-principerna när personer arbetar med dokument som öppnas från en webbplats som ingår i en DLP-princip.</span><span class="sxs-lookup"><span data-stu-id="38e52-424">These Office programs sync their DLP policies directly from the central policy store, and then continuously evaluate the content against the DLP policies when people work with documents opened from a site that's included in a DLP policy.</span></span>
  
<span data-ttu-id="38e52-425">Utvärdering av DLP-Office i Office har utformats för att inte påverka programs prestanda eller produktiviteten för personer som arbetar med innehåll.</span><span class="sxs-lookup"><span data-stu-id="38e52-425">DLP policy evaluation in Office is designed not to affect the performance of the programs or the productivity of people working on content.</span></span> <span data-ttu-id="38e52-426">Om användaren arbetar med ett stort dokument eller om användarens dator är upptagen kan det ta några sekunder innan ett principtips visas.</span><span class="sxs-lookup"><span data-stu-id="38e52-426">If they're working on a large document, or the user's computer is busy, it might take a few seconds for a policy tip to appear.</span></span>

### <a name="policy-evaluation-in-microsoft-teams"></a><span data-ttu-id="38e52-427">Principutvärdering i Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="38e52-427">Policy evaluation in Microsoft Teams</span></span>
 <!--what do you mean that it's synched to user accounts?  I thought DLP policies were applied to locations not users like sensitivity labels are  -->

<span data-ttu-id="38e52-428">När du skapar en DLP-princip som innehåller Microsoft Teams som en plats synkroniseras principen från säkerhetsefterlevnadscentret för Office 365 till användarkonton och Microsoft Teams kanaler och &amp; chattmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="38e52-428">When you create a DLP policy that includes Microsoft Teams as a location, the policy's synced from the Office 365 Security &amp; Compliance Center to user accounts and Microsoft Teams channels and chat messages.</span></span> <span data-ttu-id="38e52-429">När någon försöker dela känslig information i ett Microsoft Teams-chatt- eller kanalmeddelande kan meddelandet blockeras eller återkallas, beroende på hur DLP-principerna är konfigurerade.</span><span class="sxs-lookup"><span data-stu-id="38e52-429">Depending on how DLP policies are configured, when someone attempts to share sensitive information in a Microsoft Teams chat or channel message, the message can be blocked or revoked.</span></span> <span data-ttu-id="38e52-430">Och dokument som innehåller känslig information och som delas med gäster (externa användare) öppnas inte för dessa användare.</span><span class="sxs-lookup"><span data-stu-id="38e52-430">And, documents that contain sensitive information and that are shared with guests (external users) won't open for those users.</span></span> <span data-ttu-id="38e52-431">Mer information finns i [Skydd mot dataförlust och Microsoft Teams.](dlp-microsoft-teams.md)</span><span class="sxs-lookup"><span data-stu-id="38e52-431">To learn more, see [Data loss prevention and Microsoft Teams](dlp-microsoft-teams.md).</span></span>
 
## <a name="permissions"></a><span data-ttu-id="38e52-432">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="38e52-432">Permissions</span></span>

<span data-ttu-id="38e52-433">Medlemmar i efterlevnadsteamet som ska skapa DLP-principer behöver behörighet till &amp; Säkerhetsefterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="38e52-433">Members of your compliance team who will create DLP policies need permissions to the Security &amp; Compliance Center.</span></span> <span data-ttu-id="38e52-434">Som standard har din innehavaradministratör åtkomst till den här platsen och kan ge efterlevnadsansvariga och andra personer tillgång till Säkerhetsefterlevnadscenter, utan att ge dem alla behörigheter som en administratör för &amp; klientorganisationen har. För att göra det rekommenderar vi att du:</span><span class="sxs-lookup"><span data-stu-id="38e52-434">By default, your tenant admin will have access to this location and can give compliance officers and other people access to the Security &amp; Compliance Center, without giving them all of the permissions of a tenant admin. To do this, we recommend that you:</span></span>
  
1. <span data-ttu-id="38e52-435">Skapa en grupp i Microsoft 365 och lägg till efterlevnadsansvariga i den.</span><span class="sxs-lookup"><span data-stu-id="38e52-435">Create a group in Microsoft 365 and add compliance officers to it.</span></span>
    
2. <span data-ttu-id="38e52-436">Skapa en rollgrupp på **sidan Behörigheter** i &amp; Säkerhetsefterlevnad.</span><span class="sxs-lookup"><span data-stu-id="38e52-436">Create a role group on the **Permissions** page of the Security &amp; Compliance Center.</span></span> 

3. <span data-ttu-id="38e52-437">När du skapar rollgruppen använder du **avsnittet Välj roller** för att lägga till följande roll i rollgruppen: **DLP-efterlevnadshantering.**</span><span class="sxs-lookup"><span data-stu-id="38e52-437">While creating the role group, use the **Choose Roles** section to add the following role to the Role Group: **DLP Compliance Management**.</span></span>
    
4. <span data-ttu-id="38e52-438">Använd avsnittet **Välj medlemmar** för att lägga till Microsoft 365 grupp som du skapade före i rollgruppen.</span><span class="sxs-lookup"><span data-stu-id="38e52-438">Use the **Choose Members** section to add the Microsoft 365 group you created before to the role group.</span></span>

<span data-ttu-id="38e52-439">Du kan också skapa en rollgrupp med endast visningsbehörighet för DLP-principerna och DLP-rapporter genom att ge rollen **Endast visa-efterlevnadshantering för DLP.**</span><span class="sxs-lookup"><span data-stu-id="38e52-439">You can also create a role group with view-only privileges to the DLP policies and DLP reports by granting the **View-Only DLP Compliance Management** role.</span></span>

<span data-ttu-id="38e52-440">Mer information finns i [Ge användarna tillgång till Office 365 kompatibilitetscenter.](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="38e52-440">For more information, see [Give users access to the Office 365 Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>
  
<span data-ttu-id="38e52-441">De här behörigheterna krävs endast för att skapa och tillämpa en DLP-princip.</span><span class="sxs-lookup"><span data-stu-id="38e52-441">These permissions are required only to create and apply a DLP policy.</span></span> <span data-ttu-id="38e52-442">Tillämpning av policyer kräver inte åtkomst till innehållet.</span><span class="sxs-lookup"><span data-stu-id="38e52-442">Policy enforcement does not require access to the content.</span></span>
  
## <a name="find-the-dlp-cmdlets"></a><span data-ttu-id="38e52-443">Hitta DLP-cmdlet:arna</span><span class="sxs-lookup"><span data-stu-id="38e52-443">Find the DLP cmdlets</span></span>

<span data-ttu-id="38e52-444">Om du vill använda de flesta cmdlets för &amp; Säkerhetsefterlevnadscenter måste du:</span><span class="sxs-lookup"><span data-stu-id="38e52-444">To use most of the cmdlets for the Security &amp; Compliance Center, you need to:</span></span>
  
1. <span data-ttu-id="38e52-445">[Anslut till Office 365 säkerhet &amp; Efterlevnadscenter med fjärr-PowerShell.](/powershell/exchange/connect-to-scc-powershell)</span><span class="sxs-lookup"><span data-stu-id="38e52-445">[Connect to the Office 365 Security &amp; Compliance Center using remote PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>
    
2. <span data-ttu-id="38e52-446">Använd någon av dessa [cmdlets med policy-and-compliance-dlp.](/powershell/module/exchange/export-dlppolicycollection)</span><span class="sxs-lookup"><span data-stu-id="38e52-446">Use any of these [policy-and-compliance-dlp cmdlets](/powershell/module/exchange/export-dlppolicycollection).</span></span>
    
<span data-ttu-id="38e52-447">Men DLP-rapporter behöver hämta data från hela Microsoft 365, inklusive Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="38e52-447">However, DLP reports need pull data from across Microsoft 365, including Exchange Online.</span></span> <span data-ttu-id="38e52-448">Därför är **cmdlet:arna för DLP-rapporterna tillgängliga i Exchange Online Powershell – inte i Powershell för &amp; säkerhetsefterlevnad.**</span><span class="sxs-lookup"><span data-stu-id="38e52-448">For this reason, **the cmdlets for the DLP reports are available in Exchange Online Powershell -- not in Security &amp; Compliance Center Powershell**.</span></span> <span data-ttu-id="38e52-449">Om du vill använda cmdlet:ar för DLP-rapporterna måste du därför:</span><span class="sxs-lookup"><span data-stu-id="38e52-449">Therefore, to use the cmdlets for the DLP reports, you need to:</span></span>
  
1. <span data-ttu-id="38e52-450">[Ansluta till Exchange Online med fjärr-PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="38e52-450">[Connect to Exchange Online using remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>
    
2. <span data-ttu-id="38e52-451">Använd någon av följande cmdlets för DLP-rapporter:</span><span class="sxs-lookup"><span data-stu-id="38e52-451">Use any of these cmdlets for the DLP reports:</span></span>
    
    - [<span data-ttu-id="38e52-452">Get-DlpDetectionsReport</span><span class="sxs-lookup"><span data-stu-id="38e52-452">Get-DlpDetectionsReport</span></span>](/powershell/module/exchange/Get-DlpDetectionsReport)

    - [<span data-ttu-id="38e52-453">Get-DlpDetailReport</span><span class="sxs-lookup"><span data-stu-id="38e52-453">Get-DlpDetailReport</span></span>](/powershell/module/exchange/Get-DlpDetailReport)
    
## <a name="more-information"></a><span data-ttu-id="38e52-454">Mer information</span><span class="sxs-lookup"><span data-stu-id="38e52-454">More information</span></span>

- [<span data-ttu-id="38e52-455">Skapa en DLP-princip från en mall</span><span class="sxs-lookup"><span data-stu-id="38e52-455">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
    
- [<span data-ttu-id="38e52-456">Skicka meddelanden och visa principtips för DLP-principer</span><span class="sxs-lookup"><span data-stu-id="38e52-456">Send notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)
    
- [<span data-ttu-id="38e52-457">Skapa en DLP-princip för att skydda dokument med FCI eller andra egenskaper</span><span class="sxs-lookup"><span data-stu-id="38e52-457">Create a DLP policy to protect documents with FCI or other properties</span></span>](protect-documents-that-have-fci-or-other-properties.md)
    
- [<span data-ttu-id="38e52-458">Det här innehåller DLP-principmallarna</span><span class="sxs-lookup"><span data-stu-id="38e52-458">What the DLP policy templates include</span></span>](what-the-dlp-policy-templates-include.md)
    
- [<span data-ttu-id="38e52-459">Entitetsdefinitioner för typer av känslig information</span><span class="sxs-lookup"><span data-stu-id="38e52-459">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
    
- [<span data-ttu-id="38e52-460">Vad DLP-funktionerna letar efter</span><span class="sxs-lookup"><span data-stu-id="38e52-460">What the DLP functions look for</span></span>](what-the-dlp-functions-look-for.md)
    
- [<span data-ttu-id="38e52-461">Skapa en anpassad typ av känslig information</span><span class="sxs-lookup"><span data-stu-id="38e52-461">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
