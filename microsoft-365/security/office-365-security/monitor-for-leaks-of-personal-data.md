---
title: Övervaka läckage av personliga data
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 02/07/2018
audience: ITPro
ms.topic: overview
ms.collection:
- Strat_O365_Enterprise
- Ent_O365
- GDPR
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Läs om tre verktyg som du kan använda för att övervaka personliga data.
ms.openlocfilehash: 67cce80435aa0f01f496ec67d617f0a2dfff8ec8
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202705"
---
# <a name="monitor-for-leaks-of-personal-data"></a><span data-ttu-id="15d7b-103">Övervaka läckage av personliga data</span><span class="sxs-lookup"><span data-stu-id="15d7b-103">Monitor for leaks of personal data</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="15d7b-104">Det finns många verktyg som kan användas för att övervaka användning och transport av personliga data.</span><span class="sxs-lookup"><span data-stu-id="15d7b-104">There are many tools that can be used to monitor the use and transport of personal data.</span></span> <span data-ttu-id="15d7b-105">I det här avsnittet beskrivs tre verktyg som fungerar bra.</span><span class="sxs-lookup"><span data-stu-id="15d7b-105">This topic describes three tools that work well.</span></span>

![Verktyg för att övervaka användning och transport av personliga data](../../media/Monitor-for-leaks-of-personal-data-image1.png)

<span data-ttu-id="15d7b-107">På bilden:</span><span class="sxs-lookup"><span data-stu-id="15d7b-107">In the illustration:</span></span>

- <span data-ttu-id="15d7b-108">Börja med Microsoft 365-rapporter för dataförlustskydd för att övervaka personliga data i SharePoint Online, OneDrive för företag och e-post under överföring.</span><span class="sxs-lookup"><span data-stu-id="15d7b-108">Start with Microsoft 365 data loss prevention reports for monitoring personal data in SharePoint Online, OneDrive for Business, and email in transit.</span></span> <span data-ttu-id="15d7b-109">De ger den högsta detaljnivån för övervakning av personliga data.</span><span class="sxs-lookup"><span data-stu-id="15d7b-109">These provide the greatest level of detail for monitoring personal data.</span></span> <span data-ttu-id="15d7b-110">Rapporterna innefattar dock inte alla tjänster i Office 365.</span><span class="sxs-lookup"><span data-stu-id="15d7b-110">However, these reports don't include all services in Office 365.</span></span>

- <span data-ttu-id="15d7b-111">Använd sedan aviseringsprinciper och granskningsloggen för att övervaka aktiviteten i flera tjänster.</span><span class="sxs-lookup"><span data-stu-id="15d7b-111">Next, use alert policies and the audit log to monitor activity across services.</span></span> <span data-ttu-id="15d7b-112">Konfigurera löpande övervakning eller sök efter en händelse i granskningsloggen.</span><span class="sxs-lookup"><span data-stu-id="15d7b-112">Setup ongoing monitoring or search the audit log to investigate an incident.</span></span> <span data-ttu-id="15d7b-113">Granskningsloggen fungerar för alla tjänster – Sway, PowerBI, eDiscovery, Dynamics 365, Microsoft Flow, Microsoft Teams, administratörsaktivitet, OneDrive för företag, SharePoint Online, e-post under överföring och vilande inkorgar.</span><span class="sxs-lookup"><span data-stu-id="15d7b-113">The audit log works across services — Sway, PowerBI, eDiscovery, Dynamics 365, Microsoft Flow, Microsoft Teams, Admin activity, OneDrive for Business, SharePoint Online, mail in transit, and mailboxes at rest.</span></span> <span data-ttu-id="15d7b-114">Skype-konversationer ingår i vilande inkorgar.</span><span class="sxs-lookup"><span data-stu-id="15d7b-114">Skype conversations are included in mailboxes at rest.</span></span>

- <span data-ttu-id="15d7b-115">Till sist ska du använda Microsoft Cloud App Security för att övervaka filer med känsliga data hos andra SaaS-leverantörer.</span><span class="sxs-lookup"><span data-stu-id="15d7b-115">Finally, Use Microsoft Cloud App Security to monitor files with sensitive data in other SaaS providers.</span></span> <span data-ttu-id="15d7b-116">Inom kort blir det möjligt att använda känsliga informationstyper och enhetliga etiketter för Azure Information Protection och Office med Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="15d7b-116">Coming soon is the ability to use sensitive information types and unified labels across Azure Information Protection and Office with Cloud App Security.</span></span> <span data-ttu-id="15d7b-117">Du kan konfigurera principer som gäller för alla dina SaaS-appar eller vissa appar (som Box).</span><span class="sxs-lookup"><span data-stu-id="15d7b-117">You can setup policies that apply to all of your SaaS apps or specific apps (like Box).</span></span> <span data-ttu-id="15d7b-118">Cloud App Security identifierar inte filer i Exchange Online, till exempel bifogade filer i e-post.</span><span class="sxs-lookup"><span data-stu-id="15d7b-118">Cloud App Security doesn't discover files in Exchange Online, including files attached to email.</span></span>

## <a name="data-loss-prevention-reports"></a><span data-ttu-id="15d7b-119">Rapporter för dataförlustskydd</span><span class="sxs-lookup"><span data-stu-id="15d7b-119">Data loss prevention reports</span></span>

<span data-ttu-id="15d7b-120">När du har skapat dina principer för dataförlustskydd (DLP) ska du kontrollera att de fungerar som de ska och hjälper dig att hålla dig uppdaterad.</span><span class="sxs-lookup"><span data-stu-id="15d7b-120">After you create your data loss prevention (DLP) policies, you'll want to verify that they're working as you intended and helping you to stay compliant.</span></span> <span data-ttu-id="15d7b-121">Med DLP-rapporterna i Office 365 kan du snabbt visa antalet DLP-principmatchningar, åsidosättningar eller falska positiva identifieringar, kontrollera om de ökar eller minskar med tiden, filtrera rapporten på olika sätt och visa ytterligare information genom att markera en punkt på en linje i diagrammet.</span><span class="sxs-lookup"><span data-stu-id="15d7b-121">With the DLP reports in Office 365, you can quickly view the number of DLP policy matches, overrides, or false positives; see whether they're trending up or down over time; filter the report in different ways; and view additional details by selecting a point on a line on the graph.</span></span>

<span data-ttu-id="15d7b-122">Du kan använda DLP-rapporterna för att:</span><span class="sxs-lookup"><span data-stu-id="15d7b-122">You can use the DLP reports to:</span></span>

- <span data-ttu-id="15d7b-123">Fokusera på vissa tidsperioder och förstå orsakerna till toppar och trender.</span><span class="sxs-lookup"><span data-stu-id="15d7b-123">Focus on specific time periods and understand the reasons for spikes and trends.</span></span>

- <span data-ttu-id="15d7b-124">Upptäck affärsprocesser som strider mot organisationens DLP-principer.</span><span class="sxs-lookup"><span data-stu-id="15d7b-124">Discover business processes that violate your organization's DLP policies.</span></span>

- <span data-ttu-id="15d7b-125">Förstå alla affärseffekter i DLP-principerna.</span><span class="sxs-lookup"><span data-stu-id="15d7b-125">Understand any business impact of the DLP policies.</span></span>

- <span data-ttu-id="15d7b-126">Visa de resultat som skickats av användare när de löser ett principtips genom att åsidosätta principen eller rapportera en falsk positiv identifiering.</span><span class="sxs-lookup"><span data-stu-id="15d7b-126">View the justifications submitted by users when they resolve a policy tip by overriding the policy or reporting a false positive.</span></span>

- <span data-ttu-id="15d7b-127">Kontrollera efterlevnaden med en särskild DLP-princip genom att visa de olika matchningarna för den principen.</span><span class="sxs-lookup"><span data-stu-id="15d7b-127">Verify compliance with a specific DLP policy by showing any matches for that policy.</span></span>

- <span data-ttu-id="15d7b-128">Visa en lista med filer med känsliga data som överensstämmer med dina DLP-principer i informationsfönstret.</span><span class="sxs-lookup"><span data-stu-id="15d7b-128">View a list of files with sensitive data that matches your DLP policies in the details pane.</span></span>

<span data-ttu-id="15d7b-129">Du kan också använda DLP-rapporterna för att finjustera dina DLP-principer när du kör dem i testläge.</span><span class="sxs-lookup"><span data-stu-id="15d7b-129">In addition, you can use the DLP reports to fine tune your DLP policies as you run them in test mode.</span></span>

<span data-ttu-id="15d7b-130">DLP-rapporter finns i säkerhetscenter och efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="15d7b-130">DLP reports are in the security center and the compliance center.</span></span> <span data-ttu-id="15d7b-131">Gå till Rapporter \> Visa rapporter.</span><span class="sxs-lookup"><span data-stu-id="15d7b-131">Navigate to Reports \> View reports.</span></span> <span data-ttu-id="15d7b-132">Under Dataförlustskydd (DLP) går du till antingen Matchning mot DLP-principer och regler eller Falskt positiva identifieringar och åsidosättningar för DLP.</span><span class="sxs-lookup"><span data-stu-id="15d7b-132">Under Data loss prevention (DLP), go to either DLP policy and rule matches or DLP false positives and overrides.</span></span>

<span data-ttu-id="15d7b-133">Mer information finns i [Visa rapporterna för dataförlustskydd](https://docs.microsoft.com/microsoft-365/compliance/view-the-dlp-reports).</span><span class="sxs-lookup"><span data-stu-id="15d7b-133">For more information, see [View the reports for data loss prevention](https://docs.microsoft.com/microsoft-365/compliance/view-the-dlp-reports).</span></span>

![Rapport som visar matchningar av DLP-principer](../../media/Monitor-for-leaks-of-personal-data-image2.png)

## <a name="audit-log-and-alert-policies"></a><span data-ttu-id="15d7b-135">Principer för granskningslogg och aviseringar</span><span class="sxs-lookup"><span data-stu-id="15d7b-135">audit log and alert policies</span></span>

<span data-ttu-id="15d7b-136">I granskningsloggen finns händelser från Exchange Online, SharePoint Online, OneDrive för företag, Azure Active Directory, Microsoft Teams, Power BI, Sway och andra tjänster.</span><span class="sxs-lookup"><span data-stu-id="15d7b-136">The audit log contains events from Exchange Online, SharePoint Online, OneDrive for Business, Azure Active Directory, Microsoft Teams, Power BI, Sway, and other services.</span></span>

<span data-ttu-id="15d7b-137">Säkerhetscenter och efterlevnadscenter tillhandahåller två olika sätt att övervaka och rapportera mot granskningsloggen:</span><span class="sxs-lookup"><span data-stu-id="15d7b-137">The security center and compliance center provide two ways to monitor and report against the audit log:</span></span>

- <span data-ttu-id="15d7b-138">Konfigurera aviseringsprinciper, visa aviseringar och följa trender – använd verktygen för aviseringsprinciper och avisering på instrumentpanelen i säkerhetscenter eller efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="15d7b-138">Setup alert policies, view alerts, and monitor trends — Use the alert policy and alert dashboard tools in either the security center or compliance center.</span></span>

- <span data-ttu-id="15d7b-139">Sök direkt i granskningsloggen – sök efter alla händelser i ett specifikt datumintervall.</span><span class="sxs-lookup"><span data-stu-id="15d7b-139">Search the audit log directly — Search for all events in a specified date rage.</span></span> <span data-ttu-id="15d7b-140">Du kan också filtrera resultatet utifrån vissa villkor, t. ex. användaren som utförde åtgärden, åtgärden eller målobjektet.</span><span class="sxs-lookup"><span data-stu-id="15d7b-140">Or you can filter the results based on specific criteria, such as the user who performed the action, the action, or the target object.</span></span>

<span data-ttu-id="15d7b-141">Informationssäkerhets- och regelefterlevnadsteam kan använda de här verktygen för att proaktivt granska aktiviteter som utförs av både slutanvändare och administratörer i olika tjänster.</span><span class="sxs-lookup"><span data-stu-id="15d7b-141">Information security and compliance teams can use these tools to proactively review activities performed by both end users and administrators across services.</span></span> <span data-ttu-id="15d7b-142">Automatiska aviseringar kan konfigureras för att skicka e-postmeddelanden när vissa aktiviteter förekommer på särskilda webbplatssamlingar, till exempel när innehåll delas från webbplatser som är kända för att innehålla GDPR-relaterad information.</span><span class="sxs-lookup"><span data-stu-id="15d7b-142">Automatic alerts can be configured to send email notifications when certain activities occur on specific site collections - for example when content is shared from sites known to contain GDPR related information.</span></span> <span data-ttu-id="15d7b-143">På så sätt kan teamen följa upp användare för att säkerställa att företagets säkerhetsprinciper följs eller för att erbjuda ytterligare utbildning.</span><span class="sxs-lookup"><span data-stu-id="15d7b-143">This allows those teams to follow up with users to ensure that corporate security policies are followed, or to provide additional training.</span></span>

<span data-ttu-id="15d7b-144">Team med ansvar för informationssäkerhet kan även söka i granskningsloggen för att undersöka misstänkta dataöverträdelser och fastställa både överträdelsens grundorsak och omfattning.</span><span class="sxs-lookup"><span data-stu-id="15d7b-144">Information security teams can also search the audit log to investigate suspected data breaches and determine both root cause and the extent of the breach.</span></span> <span data-ttu-id="15d7b-145">Denna inbyggda funktion underlättar efterlevnaden av artikel 33 och 34 i GDPR, som kräver att anmälningar lämnas in till GDPR-tillsynsmyndigheterna och till de registrerade själva vid en dataöverträdelse under en viss tidsperiod.</span><span class="sxs-lookup"><span data-stu-id="15d7b-145">This built in capability facilitates compliance with article 33 and 34 of the GDPR, which require notifications be provided to the GDPR supervisory authority and to the data subjects themselves of a data breach within a specific time period.</span></span> <span data-ttu-id="15d7b-146">Poster i granskningsloggen sparas bara i 90 dagar i tjänsten, men det rekommenderas ofta (och många organisationer har krävt) att loggarna sparas under längre tidsperioder.</span><span class="sxs-lookup"><span data-stu-id="15d7b-146">Audit log entries are only retained for 90 days within the service - it is often recommended and many organizations required that these logs be retained for longer periods of time.</span></span>

<span data-ttu-id="15d7b-147">Det finns lösningar som du kan använda för att prenumerera på enhetliga granskningsloggar via API för Microsoft Management Activity och som kan lagra loggposter efter behov och tillhandahålla avancerade instrumentpaneler och aviseringar.</span><span class="sxs-lookup"><span data-stu-id="15d7b-147">Solutions are available which subscribe to the Unified Audit Logs through the Microsoft Management Activity API and can both store log entries as needed, and provide advanced dashboards and alerts.</span></span> <span data-ttu-id="15d7b-148">Ett exempel är [Microsoft Operations Management Suite (OMS)](https://docs.microsoft.com/azure/operations-management-suite/oms-solution-office-365).</span><span class="sxs-lookup"><span data-stu-id="15d7b-148">One example is [Microsoft Operations Management Suite (OMS)](https://docs.microsoft.com/azure/operations-management-suite/oms-solution-office-365).</span></span>

<span data-ttu-id="15d7b-149">Mer information om aviseringsprinciper och sökning i granskningsloggen:</span><span class="sxs-lookup"><span data-stu-id="15d7b-149">More information about alert policies and searching the audit log:</span></span>

- [<span data-ttu-id="15d7b-150">Aviseringsprinciper i säkerhets- och efterlevnadscenter för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="15d7b-150">Alert policies in the Microsoft 365 security and compliance centers</span></span>](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)

- <span data-ttu-id="15d7b-151">[Söka i granskningsloggen efter användar- och administratörsaktivitet i Office 365](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log) (introduktion)</span><span class="sxs-lookup"><span data-stu-id="15d7b-151">[Search the audit log for user and admin activity in Office 365](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log) (introduction)</span></span>

- [<span data-ttu-id="15d7b-152">Aktivera och inaktivera granskningsloggsökning</span><span class="sxs-lookup"><span data-stu-id="15d7b-152">Turn audit log search on or off</span></span>](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off)

- [<span data-ttu-id="15d7b-153">Söka i granskningsloggen</span><span class="sxs-lookup"><span data-stu-id="15d7b-153">Search the audit log</span></span>](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)

- <span data-ttu-id="15d7b-154">[Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) (cmdlet)</span><span class="sxs-lookup"><span data-stu-id="15d7b-154">[Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) (cmdlet)</span></span>

- [<span data-ttu-id="15d7b-155">Detaljerade egenskaper i granskningsloggen</span><span class="sxs-lookup"><span data-stu-id="15d7b-155">Detailed properties in the audit log</span></span>](https://docs.microsoft.com/microsoft-365/compliance/detailed-properties-in-the-office-365-audit-log)

## <a name="microsoft-cloud-app-security"></a><span data-ttu-id="15d7b-156">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="15d7b-156">Microsoft Cloud App Security</span></span>

<span data-ttu-id="15d7b-157">Med Microsoft Cloud App Security får du hjälp att upptäcka andra SaaS-appar som används i dina nätverk och känsliga data som skickas till och från dessa appar.</span><span class="sxs-lookup"><span data-stu-id="15d7b-157">Microsoft Cloud App Security helps you discover other SaaS apps in use across your networks and sensitive data that is sent to and from these apps.</span></span>

<span data-ttu-id="15d7b-158">Microsoft Cloud App Security är en omfattande tjänst som ger dig djup insyn, detaljerad kontroll och förbättrat skydd mot hot för dina molnbaserade appar.</span><span class="sxs-lookup"><span data-stu-id="15d7b-158">Microsoft Cloud App Security is a comprehensive service providing deep visibility, granular controls and enhanced threat protection for your cloud apps.</span></span> <span data-ttu-id="15d7b-159">Den identifierar fler än 15 000 molnprogram i nätverket – från alla enheter – och presenterar riskpoäng samt fortlöpande riskbedömning och -analys.</span><span class="sxs-lookup"><span data-stu-id="15d7b-159">It identifies more than 15,000 cloud applications in your network-from all devices-and provides risk scoring and ongoing risk assessment and analytics.</span></span> <span data-ttu-id="15d7b-160">Inga agenter krävs: informationen samlas in från dina brandväggar och proxyservrar för att ge dig fullständig insyn och sammanhang för molnanvändning och skugg-IT.</span><span class="sxs-lookup"><span data-stu-id="15d7b-160">No agents required: information is collected from your firewalls and proxies to give you complete visibility and context for cloud usage and shadow IT.</span></span>

<span data-ttu-id="15d7b-161">För att få en bättre förståelse för molnmiljön ger undersökningsfunktionen i Cloud App Security djup insyn i alla aktiviteter, filer och konton för sanktionerade och hanterade appar.</span><span class="sxs-lookup"><span data-stu-id="15d7b-161">To better understand your cloud environment, Cloud App Security investigate feature provides deep visibility into all activities, files and accounts for sanctioned and managed apps.</span></span> <span data-ttu-id="15d7b-162">Du kan få detaljerad information om en filnivå och identifiera varifrån data överförs i molnprogrammen.</span><span class="sxs-lookup"><span data-stu-id="15d7b-162">You can gain detailed information on a file level and discover where data travels in the cloud apps.</span></span>

<span data-ttu-id="15d7b-163">Som exempel visar följande bild två Cloud App Security-principer som kan hjälpa dig med GDPR.</span><span class="sxs-lookup"><span data-stu-id="15d7b-163">For examples, the following illustration demonstrates two Cloud App Security policies that can help with GDPR.</span></span>

![Exempel på Cloud App Security-principer](../../media/Monitor-for-leaks-of-personal-data-image3.png)

<span data-ttu-id="15d7b-165">Den första principen varnar när filer med ett fördefinierat PII-attribut eller ett anpassat uttryck som du väljer delas utanför organisationen från de SaaS-appar som du väljer.</span><span class="sxs-lookup"><span data-stu-id="15d7b-165">The first policy alerts when files with a predefined PII attribute or custom expression that you choose is shared outside the organization from the SaaS apps that you choose.</span></span>

<span data-ttu-id="15d7b-166">Den andra principen blockerar nedladdning av filer till en ohanterad enhet.</span><span class="sxs-lookup"><span data-stu-id="15d7b-166">The second policy blocks downloads of files to any unmanaged device.</span></span> <span data-ttu-id="15d7b-167">Du väljer vilka attribut i filerna du vill söka efter och vilka SaaS-appar du vill att principen ska gälla för.</span><span class="sxs-lookup"><span data-stu-id="15d7b-167">You choose the attributes within the files to look for and the SaaS apps you want the policy to apply to.</span></span>

<span data-ttu-id="15d7b-168">Dessa attributtyper kommer snart att ingå i Cloud App Security:</span><span class="sxs-lookup"><span data-stu-id="15d7b-168">These attribute types are coming soon to Cloud App Security:</span></span>

- <span data-ttu-id="15d7b-169">Typer av känslig information</span><span class="sxs-lookup"><span data-stu-id="15d7b-169">Sensitive information types</span></span>

- <span data-ttu-id="15d7b-170">Enhetliga etiketter i Microsoft 365 och Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="15d7b-170">Unified labels across Microsoft 365 and Azure Information Protection</span></span>

### <a name="cloud-app-security-dashboard"></a><span data-ttu-id="15d7b-171">Instrumentpanelen i Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="15d7b-171">Cloud App Security dashboard</span></span>

<span data-ttu-id="15d7b-172">Börja med att starta Cloud App Security om du inte redan har börjat använda det.</span><span class="sxs-lookup"><span data-stu-id="15d7b-172">If you haven't yet started to use Cloud App Security, begin by starting it up.</span></span> <span data-ttu-id="15d7b-173">Så här får du tillgång till Cloud App Security: <https://portal.cloudappsecurity.com>.</span><span class="sxs-lookup"><span data-stu-id="15d7b-173">To access Cloud App Security: <https://portal.cloudappsecurity.com>.</span></span>

<span data-ttu-id="15d7b-174">OBS! Kom ihåg att aktivera automatiskt genomsökning av filnamn för Azure Information Protection-klassificeringsetiketter (i Allmänna inställningar) när du ska komma igång med Cloud App Security eller innan du tilldelar etiketter.</span><span class="sxs-lookup"><span data-stu-id="15d7b-174">Note: Be sure to enable 'Automatically scan files for Azure Information Protection classification labels' (in General settings) when getting started with Cloud App Security or before you assign labels.</span></span> <span data-ttu-id="15d7b-175">När du har gjort det genomsöker inte Cloud App Security befintliga filer igen förrän de ändras.</span><span class="sxs-lookup"><span data-stu-id="15d7b-175">After setup, Cloud App Security does not scan existing files again until they are modified.</span></span>

![Instrumentpanel som visar information om aviseringar](../../media/Monitor-for-leaks-of-personal-data-image4.png)

<span data-ttu-id="15d7b-177">Mer information:</span><span class="sxs-lookup"><span data-stu-id="15d7b-177">More information:</span></span>

- [<span data-ttu-id="15d7b-178">Distribuera Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="15d7b-178">Deploy Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security)

- [<span data-ttu-id="15d7b-179">Mer information om Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="15d7b-179">More information about Microsoft Cloud App Security</span></span>](https://www.microsoft.com/cloud-platform/cloud-app-security)

- [<span data-ttu-id="15d7b-180">Blockera nedladdning av känslig information med Microsoft Cloud App Security-proxyn</span><span class="sxs-lookup"><span data-stu-id="15d7b-180">Block downloads of sensitive information using the Microsoft Cloud App Security proxy</span></span>](https://docs.microsoft.com/cloud-app-security/use-case-proxy-block-session-aad)

## <a name="example-file-and-activity-policies-to-detect-sharing-of-personal-data"></a><span data-ttu-id="15d7b-181">Exempel på fil- och aktivitetsprinciper som identifierar delning av personliga data</span><span class="sxs-lookup"><span data-stu-id="15d7b-181">Example file and activity policies to detect sharing of personal data</span></span>

### <a name="detect-sharing-of-files-containing-pii--credit-card-number"></a><span data-ttu-id="15d7b-182">Identifiera delning av filer som innehåller PII – kreditkortsnummer</span><span class="sxs-lookup"><span data-stu-id="15d7b-182">Detect sharing of files containing PII — Credit card number</span></span>

<span data-ttu-id="15d7b-183">Avisera när en fil som innehåller ett kreditkortsnummer delas från en godkänd molnapp.</span><span class="sxs-lookup"><span data-stu-id="15d7b-183">Alert when a file containing a credit card number is shared from an approved cloud app.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="15d7b-184"><strong>Kontroll</strong></span><span class="sxs-lookup"><span data-stu-id="15d7b-184"><strong>Control</strong></span></span></th>
<th align="left"><span data-ttu-id="15d7b-185"><strong>Inställningar</strong></span><span class="sxs-lookup"><span data-stu-id="15d7b-185"><strong>Settings</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="15d7b-186">Typ av princip</span><span class="sxs-lookup"><span data-stu-id="15d7b-186">Policy type</span></span></td>
<td align="left"><span data-ttu-id="15d7b-187">Filprincip</span><span class="sxs-lookup"><span data-stu-id="15d7b-187">File policy</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="15d7b-188">Principmall</span><span class="sxs-lookup"><span data-stu-id="15d7b-188">Policy template</span></span></td>
<td align="left"><span data-ttu-id="15d7b-189">Ingen mall</span><span class="sxs-lookup"><span data-stu-id="15d7b-189">No template</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="15d7b-190">Allvarlighetsgrad för princip</span><span class="sxs-lookup"><span data-stu-id="15d7b-190">Policy severity</span></span></td>
<td align="left"><span data-ttu-id="15d7b-191">Högsta</span><span class="sxs-lookup"><span data-stu-id="15d7b-191">High</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="15d7b-192">Kategori</span><span class="sxs-lookup"><span data-stu-id="15d7b-192">Category</span></span></td>
<td align="left"><span data-ttu-id="15d7b-193">DLP</span><span class="sxs-lookup"><span data-stu-id="15d7b-193">DLP</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="15d7b-194">Filterinställningar</span><span class="sxs-lookup"><span data-stu-id="15d7b-194">Filter settings</span></span></td>
<td align="left"><p><span data-ttu-id="15d7b-195">Åtkomstnivå = offentlig (Internet), offentlig, extern</span><span class="sxs-lookup"><span data-stu-id="15d7b-195">Access level = Public (Internet), Public, External</span></span></p>
<p><span data-ttu-id="15d7b-196">App = &lt;välj appar&gt; (använd den här inställningen om du vill begränsa övervakning till vissa SaaS-appar)</span><span class="sxs-lookup"><span data-stu-id="15d7b-196">App = &lt;select apps&gt; (use this setting if you want to limit monitoring to specific SaaS apps)</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="15d7b-197">Använd för</span><span class="sxs-lookup"><span data-stu-id="15d7b-197">Apply to</span></span></td>
<td align="left"><span data-ttu-id="15d7b-198">Alla filer, alla ägare</span><span class="sxs-lookup"><span data-stu-id="15d7b-198">All files, all owners</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="15d7b-199">Innehållsgranskning</span><span class="sxs-lookup"><span data-stu-id="15d7b-199">Content inspection</span></span></td>
<td align="left"><p><span data-ttu-id="15d7b-200">Innefattar filer som matchar ett befintligt uttryck: Alla länder: Ekonomi: Kreditkortsnummer</span><span class="sxs-lookup"><span data-stu-id="15d7b-200">Includes files that match a present expression: All countries: Finance: Credit card number</span></span></p>
<p><span data-ttu-id="15d7b-201">Kräv inte relevant kontext: avmarkerat (matchar nyckelord och regex)</span><span class="sxs-lookup"><span data-stu-id="15d7b-201">Don't require relevant context: unchecked (this will match keywords as well as regex)</span></span></p>
<p><span data-ttu-id="15d7b-202">Innefattar filer med minst 1 matchning</span><span class="sxs-lookup"><span data-stu-id="15d7b-202">Includes files with at least 1 match</span></span></p>
<p><span data-ttu-id="15d7b-203">Ta bort mask för de fyra sista tecknen i överträdelsen: markerat</span><span class="sxs-lookup"><span data-stu-id="15d7b-203">Unmask the last 4 characters of the violation: checked</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="15d7b-204">Varningar</span><span class="sxs-lookup"><span data-stu-id="15d7b-204">Alerts</span></span></td>
<td align="left"><p><span data-ttu-id="15d7b-205">Skapa en avisering för varje matchande fil: markerat</span><span class="sxs-lookup"><span data-stu-id="15d7b-205">Create an alert for each matching file: checked</span></span></p>
<p><span data-ttu-id="15d7b-206">Daglig aviseringsgräns: 1 000</span><span class="sxs-lookup"><span data-stu-id="15d7b-206">Daily alert limit: 1000</span></span></p>
<p><span data-ttu-id="15d7b-207">Välj en avisering som e-post: markerat</span><span class="sxs-lookup"><span data-stu-id="15d7b-207">Select an alert as email: checked</span></span></p>
<p><span data-ttu-id="15d7b-208">Till: infosec@contoso.com</span><span class="sxs-lookup"><span data-stu-id="15d7b-208">To: infosec@contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="15d7b-209">Styrning</span><span class="sxs-lookup"><span data-stu-id="15d7b-209">Governance</span></span></td>
<td align="left"><p><span data-ttu-id="15d7b-210">Microsoft OneDrive för företag</span><span class="sxs-lookup"><span data-stu-id="15d7b-210">Microsoft OneDrive for Business</span></span></p>
<p><span data-ttu-id="15d7b-211">Gör privat: markera Ta bort externa användare</span><span class="sxs-lookup"><span data-stu-id="15d7b-211">Make private: check Remove External Users</span></span></p>
<p><span data-ttu-id="15d7b-212">Alla andra inställningar: avmarkerade</span><span class="sxs-lookup"><span data-stu-id="15d7b-212">All other settings: unchecked</span></span></p>
<p><span data-ttu-id="15d7b-213">Microsoft SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="15d7b-213">Microsoft SharePoint Online</span></span></p>
<p><span data-ttu-id="15d7b-214">Gör privat: markera Ta bort externa användare</span><span class="sxs-lookup"><span data-stu-id="15d7b-214">Make private: check Remove External Users</span></span></p>
<p><span data-ttu-id="15d7b-215">Alla andra inställningar: avmarkerade</span><span class="sxs-lookup"><span data-stu-id="15d7b-215">All other settings: unchecked</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="15d7b-216">Liknande principer:</span><span class="sxs-lookup"><span data-stu-id="15d7b-216">Similar policies:</span></span>

- <span data-ttu-id="15d7b-217">Identifiera delning av filer som innehåller PII – e-postadress</span><span class="sxs-lookup"><span data-stu-id="15d7b-217">Detect sharing of Files containing PII - Email Address</span></span>

- <span data-ttu-id="15d7b-218">Identifiera delning av filer som innehåller PII – passnummer</span><span class="sxs-lookup"><span data-stu-id="15d7b-218">Detect sharing of Files containing PII - Passport Number</span></span>

### <a name="detect-customer-or-hr-data-in-box-or-onedrive-for-business"></a><span data-ttu-id="15d7b-219">Identifiera kund- eller HR-data i Box eller OneDrive för företag</span><span class="sxs-lookup"><span data-stu-id="15d7b-219">Detect Customer or HR Data in Box or OneDrive for Business</span></span>

<span data-ttu-id="15d7b-220">Avisera när en fil som är markerad som kunddata eller HR-information överförs till OneDrive för företag eller Box.</span><span class="sxs-lookup"><span data-stu-id="15d7b-220">Alert when a file labeled as Customer Data or HR Data is uploaded to OneDrive for Business or Box.</span></span>

<span data-ttu-id="15d7b-221">Kommentarer:</span><span class="sxs-lookup"><span data-stu-id="15d7b-221">Notes:</span></span>

- <span data-ttu-id="15d7b-222">Box-övervakning kräver att en anslutning konfigureras med hjälp av API-anslutaren SDK.</span><span class="sxs-lookup"><span data-stu-id="15d7b-222">Box monitoring requires a connector be configured using the API Connector SDK.</span></span>

- <span data-ttu-id="15d7b-223">Principen kräver funktioner som för närvarande är i privat förhandsversion.</span><span class="sxs-lookup"><span data-stu-id="15d7b-223">This policy requires capabilities that are currently in private preview.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="15d7b-224"><strong>Kontroll</strong></span><span class="sxs-lookup"><span data-stu-id="15d7b-224"><strong>Control</strong></span></span></th>
<th align="left"><span data-ttu-id="15d7b-225"><strong>Inställningar</strong></span><span class="sxs-lookup"><span data-stu-id="15d7b-225"><strong>Settings</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="15d7b-226">Typ av princip</span><span class="sxs-lookup"><span data-stu-id="15d7b-226">Policy type</span></span></td>
<td align="left"><span data-ttu-id="15d7b-227">Aktivitetspolicy</span><span class="sxs-lookup"><span data-stu-id="15d7b-227">Activity policy</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="15d7b-228">Principmall</span><span class="sxs-lookup"><span data-stu-id="15d7b-228">Policy template</span></span></td>
<td align="left"><span data-ttu-id="15d7b-229">Ingen mall</span><span class="sxs-lookup"><span data-stu-id="15d7b-229">No template</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="15d7b-230">Allvarlighetsgrad för princip</span><span class="sxs-lookup"><span data-stu-id="15d7b-230">Policy severity</span></span></td>
<td align="left"><span data-ttu-id="15d7b-231">Högsta</span><span class="sxs-lookup"><span data-stu-id="15d7b-231">High</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="15d7b-232">Kategori</span><span class="sxs-lookup"><span data-stu-id="15d7b-232">Category</span></span></td>
<td align="left"><span data-ttu-id="15d7b-233">Delningskontroll</span><span class="sxs-lookup"><span data-stu-id="15d7b-233">Sharing Control</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="15d7b-234">Agera på</span><span class="sxs-lookup"><span data-stu-id="15d7b-234">Act on</span></span></td>
<td align="left"><span data-ttu-id="15d7b-235">Enskild aktivitet</span><span class="sxs-lookup"><span data-stu-id="15d7b-235">Single activity</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="15d7b-236">Filterinställningar</span><span class="sxs-lookup"><span data-stu-id="15d7b-236">Filter settings</span></span></td>
<td align="left"><p><span data-ttu-id="15d7b-237">Aktivitetstyp = överföra fil</span><span class="sxs-lookup"><span data-stu-id="15d7b-237">Activity type = Upload File</span></span></p>
<p><span data-ttu-id="15d7b-238">App = Microsoft OneDrive för företag och Box</span><span class="sxs-lookup"><span data-stu-id="15d7b-238">App = Microsoft OneDrive for Business and Box</span></span></p>
<p><span data-ttu-id="15d7b-239">Klassificeringsetikett (för närvarande i privat förhandsversion): Azure Information Protection = kunddata, personal – löneuppgifter, personal – information om anställda</span><span class="sxs-lookup"><span data-stu-id="15d7b-239">Classification Label (currently in private preview): Azure Information Protection = Customer Data, Human Resources—Salary Data, Human Resources—Employee Data</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="15d7b-240">Varningar</span><span class="sxs-lookup"><span data-stu-id="15d7b-240">Alerts</span></span></td>
<td align="left"><p><span data-ttu-id="15d7b-241">Skapa en avisering: markerad</span><span class="sxs-lookup"><span data-stu-id="15d7b-241">Create an alert: checked</span></span></p>
<p><span data-ttu-id="15d7b-242">Daglig aviseringsgräns: 1 000</span><span class="sxs-lookup"><span data-stu-id="15d7b-242">Daily alert limit: 1000</span></span></p>
<p><span data-ttu-id="15d7b-243">Välj en avisering som e-post: markerat</span><span class="sxs-lookup"><span data-stu-id="15d7b-243">Select an alert as email: checked</span></span></p>
<p><span data-ttu-id="15d7b-244">Till: infosec@contoso.com</span><span class="sxs-lookup"><span data-stu-id="15d7b-244">To: infosec@contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="15d7b-245">Styrning</span><span class="sxs-lookup"><span data-stu-id="15d7b-245">Governance</span></span></td>
<td align="left"><p><span data-ttu-id="15d7b-246">Alla appar</span><span class="sxs-lookup"><span data-stu-id="15d7b-246">All apps</span></span></p>
<p><span data-ttu-id="15d7b-247">Placera användare i karantän: markerad</span><span class="sxs-lookup"><span data-stu-id="15d7b-247">Put user in quarantine: check</span></span></p>
<p><span data-ttu-id="15d7b-248">Alla andra inställningar: avmarkerade</span><span class="sxs-lookup"><span data-stu-id="15d7b-248">All other settings: unchecked</span></span></p>
<p><span data-ttu-id="15d7b-249">Office 365</span><span class="sxs-lookup"><span data-stu-id="15d7b-249">Office 365</span></span></p>
<p><span data-ttu-id="15d7b-250">Placera användare i karantän: markerad</span><span class="sxs-lookup"><span data-stu-id="15d7b-250">Put user in quarantine: check</span></span></p>
<p><span data-ttu-id="15d7b-251">Alla andra inställningar: avmarkerade</span><span class="sxs-lookup"><span data-stu-id="15d7b-251">All other settings: unchecked</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="15d7b-252">Liknande principer:</span><span class="sxs-lookup"><span data-stu-id="15d7b-252">Similar policies:</span></span>

- <span data-ttu-id="15d7b-253">Identifiera stora nedladdningar med kunddata eller HR-data – avisera när ett stort antal filer som innehåller kunddata eller HR-data har laddats ned av en enskild användare under en begränsad tidsperiod.</span><span class="sxs-lookup"><span data-stu-id="15d7b-253">Detect large downloads of Customer data or HR Data — Alert when a large number of files containing customer data or HR data have been detected being downloaded by a single user within a short period of time.</span></span>

- <span data-ttu-id="15d7b-254">Identifiera delning av kunddata och HR-data – avisera när filer som innehåller kund- eller HR-data delas.</span><span class="sxs-lookup"><span data-stu-id="15d7b-254">Detect Sharing of Customer and HR Data — Alert when files containing Customer or HR Data are shared.</span></span>
