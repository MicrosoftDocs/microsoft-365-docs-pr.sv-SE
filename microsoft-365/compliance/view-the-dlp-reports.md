---
title: Visa rapporter för dataförlustskydd
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/7/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-apr2020
description: Använd DLP-rapporterna i Office 365 för att visa antalet matchningar, åsidosättningar eller falska matchningar av DLP-principen och se om de trender uppåt eller nedåt över tid.
ms.openlocfilehash: 742f0ef0334e714c7f31cbc2f97559993454f6b7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162328"
---
# <a name="view-the-reports-for-data-loss-prevention"></a><span data-ttu-id="a3098-103">Visa rapporter för dataförlustskydd</span><span class="sxs-lookup"><span data-stu-id="a3098-103">View the reports for data loss prevention</span></span>

<span data-ttu-id="a3098-104">När du har skapat dina principer för dataförlustskydd (DLP) ska du kontrollera att de fungerar som de ska och hjälper dig att hålla dig uppdaterad.</span><span class="sxs-lookup"><span data-stu-id="a3098-104">After you create your data loss prevention (DLP) policies, you'll want to verify that they're working as you intended and helping you to stay compliant.</span></span> <span data-ttu-id="a3098-105">Med DLP-rapporterna i &amp; Säkerhetsefterlevnadscenter kan du snabbt visa:</span><span class="sxs-lookup"><span data-stu-id="a3098-105">With the DLP reports in the Security &amp; Compliance Center, you can quickly view:</span></span>
  
- <span data-ttu-id="a3098-106">**DLP-principmatchning** Den här rapporten visar antalet DLP-principmatchningar över tid.</span><span class="sxs-lookup"><span data-stu-id="a3098-106">**DLP policy matches** This report shows the count of DLP policy matches over time.</span></span> <span data-ttu-id="a3098-107">Du kan filtrera rapporten efter datum, plats, princip eller åtgärd.</span><span class="sxs-lookup"><span data-stu-id="a3098-107">You can filter the report by date, location, policy, or action.</span></span> <span data-ttu-id="a3098-108">Du kan använda den här rapporten för att:</span><span class="sxs-lookup"><span data-stu-id="a3098-108">You can use this report to:</span></span> 
    
  - <span data-ttu-id="a3098-109">Finjustera eller förfina DLP-principerna när du kör dem i testläge.</span><span class="sxs-lookup"><span data-stu-id="a3098-109">Tune or refine your DLP policies as you run them in test mode.</span></span> <span data-ttu-id="a3098-110">Du kan visa den specifika regel som matchade innehållet.</span><span class="sxs-lookup"><span data-stu-id="a3098-110">You can view the specific rule that matched the content.</span></span>
    
  - <span data-ttu-id="a3098-111">Fokusera på vissa tidsperioder och förstå orsakerna till toppar och trender.</span><span class="sxs-lookup"><span data-stu-id="a3098-111">Focus on specific time periods and understand the reasons for spikes and trends.</span></span>
    
  - <span data-ttu-id="a3098-112">Upptäck affärsprocesser som strider mot organisationens DLP-principer.</span><span class="sxs-lookup"><span data-stu-id="a3098-112">Discover business processes that violate your organization's DLP policies.</span></span>
    
  - <span data-ttu-id="a3098-113">Förstå DLP-principernas eventuella affärseffekter genom att se vilka åtgärder som tillämpas på innehållet.</span><span class="sxs-lookup"><span data-stu-id="a3098-113">Understand any business impact of the DLP policies by seeing what actions are being applied to content.</span></span>
    
  - <span data-ttu-id="a3098-114">Kontrollera efterlevnaden med en särskild DLP-princip genom att visa de olika matchningarna för den principen.</span><span class="sxs-lookup"><span data-stu-id="a3098-114">Verify compliance with a specific DLP policy by showing any matches for that policy.</span></span>
    
  - <span data-ttu-id="a3098-115">Visa en lista över de största användarna och upprepa användare som bidrar till incidenter i organisationen.</span><span class="sxs-lookup"><span data-stu-id="a3098-115">View a list of top users and repeat users who are contributing to incidents in your organization.</span></span>
    
  - <span data-ttu-id="a3098-116">Visa en lista över de vanligaste typerna av känslig information i organisationen.</span><span class="sxs-lookup"><span data-stu-id="a3098-116">View a list of the top types of sensitive information in your organization.</span></span>
    
- <span data-ttu-id="a3098-117">**DLP-incidenter** Den här rapporten visar även principmatchningar över tid, t.ex. rapporten principmatchningar.</span><span class="sxs-lookup"><span data-stu-id="a3098-117">**DLP incidents** This report also shows policy matches over time, like the policy matches report.</span></span> <span data-ttu-id="a3098-118">Men rapporten principmatchningar visar matchningar på en regelnivå. Om till exempel ett e-postmeddelande matchade tre olika regler, visas tre olika radobjekt i rapporten principmatchningar.</span><span class="sxs-lookup"><span data-stu-id="a3098-118">However, the policy matches report shows matches at a rule level; for example, if an email matched three different rules, the policy matches report shows three different line items.</span></span> <span data-ttu-id="a3098-119">Incidentrapporten visar däremot matchningar på objektnivå. Om till exempel ett e-postmeddelande matchade tre olika regler, visar incidentrapporten ett enda radobjekt för innehållsbiten.</span><span class="sxs-lookup"><span data-stu-id="a3098-119">By contrast, the incidents report shows matches at an item level; for example, if an email matched three different rules, the incidents report shows a single line item for that piece of content.</span></span> 
    
  <span data-ttu-id="a3098-120">Eftersom rapportantalen aggregeras olika är rapportmatchningen bättre för att identifiera matchningar med specifika regler och finjustera DLP-principer.</span><span class="sxs-lookup"><span data-stu-id="a3098-120">Because the report counts are aggregated differently, the policy matches report is better for identifying matches with specific rules and fine tuning DLP policies.</span></span> <span data-ttu-id="a3098-121">Med incidentrapporten kan du bättre identifiera specifika innehållsdelar som är problematiska för DLP-principerna.</span><span class="sxs-lookup"><span data-stu-id="a3098-121">The incidents report is better for identifying specific pieces of content that are problematic for your DLP policies.</span></span>
    
- <span data-ttu-id="a3098-122">**DLP falska positiva resultat och åsidosättningar** Om DLP-principen tillåter att användare åsidosätter den eller rapporterar en felaktig positiv inställning visas antalet sådana instanser över tid i den här rapporten.</span><span class="sxs-lookup"><span data-stu-id="a3098-122">**DLP false positives and overrides** If your DLP policy allows users to override it or report a false positive, this report shows a count of such instances over time.</span></span> <span data-ttu-id="a3098-123">Du kan filtrera rapporten efter datum, plats eller princip.</span><span class="sxs-lookup"><span data-stu-id="a3098-123">You can filter the report by date, location, or policy.</span></span> <span data-ttu-id="a3098-124">Du kan använda den här rapporten för att:</span><span class="sxs-lookup"><span data-stu-id="a3098-124">You can use this report to:</span></span> 
    
  - <span data-ttu-id="a3098-125">Finjustera eller förfina DLP-principerna genom att se vilka principer som medför ett stort antal falska positiva resultat.</span><span class="sxs-lookup"><span data-stu-id="a3098-125">Tune or refine your DLP policies by seeing which policies incur a high number of false positives.</span></span>
    
  - <span data-ttu-id="a3098-126">Visa argument som skickats av användare när de löser ett principtips genom att åsidosätta principen.</span><span class="sxs-lookup"><span data-stu-id="a3098-126">View the justifications submitted by users when they resolve a policy tip by overriding the policy.</span></span>
    
  - <span data-ttu-id="a3098-127">Upptäck var DLP-principerna står i konflikt med giltiga affärsprocesser genom att ett stort antal användare åsidosätts.</span><span class="sxs-lookup"><span data-stu-id="a3098-127">Discover where DLP policies conflict with valid business processes by incurring a high number of user overrides.</span></span>
    
<span data-ttu-id="a3098-128">Alla DLP-rapporter kan visa data från den senaste tidsperioden på fyra månader.</span><span class="sxs-lookup"><span data-stu-id="a3098-128">All DLP reports can show data from the most recent four-month time period.</span></span> <span data-ttu-id="a3098-129">Det kan ta upp till 24 timmar innan de senaste data visas i rapporterna.</span><span class="sxs-lookup"><span data-stu-id="a3098-129">The most recent data can take up to 24 hours to appear in the reports.</span></span>
  
<span data-ttu-id="a3098-130">Du hittar dessa rapporter i instrumentpanelen för rapporter &amp; i \> **Säkerhetsefterlevnadscenter.** \> </span><span class="sxs-lookup"><span data-stu-id="a3098-130">You can find these reports in the Security &amp; Compliance Center \> **Reports** \> **Dashboard**.</span></span>
  
![Rapport om DLP-principmatchning](../media/117d20c9-d379-403f-ad68-1f5cd6c4e5cf.png)
  
## <a name="view-the-justification-submitted-by-a-user-for-an-override"></a><span data-ttu-id="a3098-132">Visa en användares justering för en åsidosättning</span><span class="sxs-lookup"><span data-stu-id="a3098-132">View the justification submitted by a user for an override</span></span>

<span data-ttu-id="a3098-133">Om DLP-principen tillåter att användare åsidosätter den kan du använda den falska positiva inställningen och åsidosättningen av rapporten om du vill visa texten som skickats in av användare i principtipset.</span><span class="sxs-lookup"><span data-stu-id="a3098-133">If your DLP policy allows users to override it, you can use the false positive and override report to view the text submitted by users in the policy tip.</span></span>
  
![Fältet Justering i information om falsk positiv DLP-kod och en åsidosättningsrapport](../media/e11e3126-026d-4e77-a16d-74a0686d1fa3.png)
  
## <a name="take-action-on-insights-and-recommendations"></a><span data-ttu-id="a3098-135">Vidta åtgärder för insikter och rekommendationer</span><span class="sxs-lookup"><span data-stu-id="a3098-135">Take action on insights and recommendations</span></span>

<span data-ttu-id="a3098-136">Rapporter kan visa insikter och rekommendationer där du kan klicka på den röda varningsikonen för att se information om potentiella problem och vidta möjliga åtgärder.</span><span class="sxs-lookup"><span data-stu-id="a3098-136">Reports can show insights and recommendations where you can click the red warning icon to see details about potential issues and take possible remedial action.</span></span>
  
![Klicka på en insikter-ikon för att visa information och åtgärder som ska vidtas](../media/51782036-7299-4960-8175-75c2b1637159.png)
  
## <a name="permissions-for-dlp-reports"></a><span data-ttu-id="a3098-138">Behörigheter för DLP-rapporter</span><span class="sxs-lookup"><span data-stu-id="a3098-138">Permissions for DLP reports</span></span>

<span data-ttu-id="a3098-139">För att kunna visa DLP-rapporter i & säkerhets- och efterlevnadscenter måste du tilldelas:</span><span class="sxs-lookup"><span data-stu-id="a3098-139">To view DLP reports in the Security & Compliance Center, you have to be assigned the:</span></span>

- <span data-ttu-id="a3098-140">**Rollen Säkerhetsläsare** i Exchange administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="a3098-140">**Security Reader** role in the Exchange admin center.</span></span> <span data-ttu-id="a3098-141">Som standard är den här rollen tilldelad rollgrupperna Organisationshantering och Säkerhetsläsare i Exchange administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="a3098-141">By default, this role is assigned to the Organization Management and Security Reader role groups in the Exchange admin center.</span></span>

- <span data-ttu-id="a3098-142">**Rollen Endast visad DLP-efterlevnadshantering** i Säkerhets- & Efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="a3098-142">**View-Only DLP Compliance Management** role in the Security & Compliance Center.</span></span> <span data-ttu-id="a3098-143">Som standard tilldelas den här rollen rollgrupperna Efterlevnadsadministratör, Organisationshantering, Säkerhetsadministratör och Säkerhetsläsare i säkerhets- & Säkerhets- och efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="a3098-143">By default, this role is assigned to the Compliance Administrator, Organization Management, Security Administrator, and Security Reader role groups in the Security & Compliance Center.</span></span>

- <span data-ttu-id="a3098-144">**Rollen Endast visa mottagare** i Exchange administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="a3098-144">**View-Only Recipients** role in the Exchange admin center.</span></span> <span data-ttu-id="a3098-145">Som standard är den här rollen tilldelad rollgrupperna Efterlevnadshantering, Organisationshantering och View-Only Organisationshantering i Exchange administrationscenter.</span><span class="sxs-lookup"><span data-stu-id="a3098-145">By default, this role is assigned to the Compliance Management, Organization Management, and View-Only Organization Management role groups in the Exchange admin center.</span></span>

## <a name="find-the-cmdlets-for-the-dlp-reports"></a><span data-ttu-id="a3098-146">Hitta cmdletarna för DLP-rapporterna</span><span class="sxs-lookup"><span data-stu-id="a3098-146">Find the cmdlets for the DLP reports</span></span>

<span data-ttu-id="a3098-147">Om du vill använda de flesta cmdlets för &amp; Säkerhetsefterlevnadscenter måste du:</span><span class="sxs-lookup"><span data-stu-id="a3098-147">To use most of the cmdlets for the Security &amp; Compliance Center, you need to:</span></span>
  
1. [<span data-ttu-id="a3098-148">Anslut till &amp; Säkerhetsefterlevnadscenter med fjärr-PowerShell</span><span class="sxs-lookup"><span data-stu-id="a3098-148">Connect to the Security &amp; Compliance Center using remote PowerShell</span></span>](/powershell/exchange/connect-to-scc-powershell&amp;clcid=0x409)
    
2. <span data-ttu-id="a3098-149">Använda någon av följande [ &amp; cmdlets för Säkerhetsefterlevnadscenter](/powershell/exchange/exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="a3098-149">Use any of these [Security &amp; Compliance Center cmdlets](/powershell/exchange/exchange-online-powershell)</span></span>
    
<span data-ttu-id="a3098-150">Men DLP-rapporter behöver hämta data från hela Office 365, inklusive Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="a3098-150">However, DLP reports need pull data from across Office 365, including Exchange Online.</span></span> <span data-ttu-id="a3098-151">Därför är cmdlet:arna för DLP-rapporterna tillgängliga i Exchange Online Powershell – inte i Powershell för &amp; säkerhetsefterlevnad.</span><span class="sxs-lookup"><span data-stu-id="a3098-151">For this reason, the cmdlets for the DLP reports are available in Exchange Online Powershell—not in Security &amp; Compliance Center Powershell.</span></span> <span data-ttu-id="a3098-152">Om du vill använda cmdlet:ar för DLP-rapporterna måste du därför:</span><span class="sxs-lookup"><span data-stu-id="a3098-152">Therefore, to use the cmdlets for the DLP reports, you need to:</span></span>
  
1. [<span data-ttu-id="a3098-153">Ansluta till Exchange Online med fjärr-PowerShell</span><span class="sxs-lookup"><span data-stu-id="a3098-153">Connect to Exchange Online using remote PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)
    
2. <span data-ttu-id="a3098-154">Använd någon av följande cmdlets för DLP-rapporter:</span><span class="sxs-lookup"><span data-stu-id="a3098-154">Use any of these cmdlets for the DLP reports:</span></span>
    
      - [<span data-ttu-id="a3098-155">Get-DlpDetectionsReport</span><span class="sxs-lookup"><span data-stu-id="a3098-155">Get-DlpDetectionsReport</span></span>](/powershell/module/exchange/get-dlpdetectionsreport)
    
      - [<span data-ttu-id="a3098-156">Get-DlpDetailReport</span><span class="sxs-lookup"><span data-stu-id="a3098-156">Get-DlpDetailReport</span></span>](/powershell/module/exchange/get-dlpdetailreport)
