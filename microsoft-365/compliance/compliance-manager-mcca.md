---
title: Microsoft Compliance Configuration Analyzer för Efterlevnadshanteraren
f1.keywords:
- NOCSH
ms.author: v-jgriffee
author: jmgriffee
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Förstå hur du använder Microsoft Compliance Configuration Analyzer för att snabbt komma igång med Microsoft Compliance Manager.
ms.openlocfilehash: 36f11597eac1837e3e18885f3c0a5d8dbc89a774
ms.sourcegitcommit: 46b77a41dfcc0ee80e2b89a7aa49e9bbe5deae5a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/26/2021
ms.locfileid: "53148968"
---
# <a name="microsoft-compliance-configuration-analyzer-for-compliance-manager-preview"></a><span data-ttu-id="01a67-103">Microsoft Compliance Configuration Analyzer för Efterlevnadshanteraren (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="01a67-103">Microsoft Compliance Configuration Analyzer for Compliance Manager (preview)</span></span>

<span data-ttu-id="01a67-104">**I den här artikeln:** Lär dig hur du installerar och kör verktyget Microsoft Compliance Configure Analyzer för att snabbt komma igång med Microsoft Compliance Manger.</span><span class="sxs-lookup"><span data-stu-id="01a67-104">**In this article:** Learn how to install and run the Microsoft Compliance Configure Analyzer tool to get quickly started with Microsoft Compliance Manger.</span></span>

## <a name="microsoft-compliance-configuration-analyzer-mcca-preview-overview"></a><span data-ttu-id="01a67-105">Översikt över Microsoft Compliance Configuration Analyzer (MCCA) (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="01a67-105">Microsoft Compliance Configuration Analyzer (MCCA) (preview) overview</span></span>

<span data-ttu-id="01a67-106">Microsoft Compliance Configuration Analyzer (MCCA) är ett förhandsversionsverktyg som kan hjälpa dig att komma igång med [Microsoft Compliance Manager.](compliance-manager.md)</span><span class="sxs-lookup"><span data-stu-id="01a67-106">The Microsoft Compliance Configuration Analyzer (MCCA) is a preview tool that can help you get started with [Microsoft Compliance Manager](compliance-manager.md).</span></span> <span data-ttu-id="01a67-107">MCCA är ett PowerShell-baserat verktyg som hämtar organisationens aktuella konfigurationer och verifierar dem Microsoft 365 rekommenderade metodtips.</span><span class="sxs-lookup"><span data-stu-id="01a67-107">MCCA is a PowerShell-based utility that will fetch your organization’s current configurations and validate them against Microsoft 365 recommended best practices.</span></span> <span data-ttu-id="01a67-108">Dessa metodtips baseras på en uppsättning kontroller som omfattar viktiga bestämmelser och standarder för dataskydd och datastyrning.</span><span class="sxs-lookup"><span data-stu-id="01a67-108">These best practices are based on a set of controls that include key regulations and standards for data protection and data governance.</span></span>

<span data-ttu-id="01a67-109">Med MCCA kan du snabbt se vilka förbättringsåtgärder i Efterlevnadshanteraren som gäller för din Microsoft 365 miljö.</span><span class="sxs-lookup"><span data-stu-id="01a67-109">MCCA can help you quickly see which improvement actions in Compliance Manager apply to your current Microsoft 365 environment.</span></span> <span data-ttu-id="01a67-110">Varje åtgärd som identifieras av MCCA ger dig rekommendationer om implementering, med direktlänkar till Efterlevnadshanteraren och den tillämpliga lösningen för att börja vidta korrigerande åtgärder.</span><span class="sxs-lookup"><span data-stu-id="01a67-110">Each action identified by MCCA will give you recommendations for implementation, with direct links to Compliance Manager and the applicable solution to start taking corrective action.</span></span>

<span data-ttu-id="01a67-111">Ytterligare en resurs för att förstå MCCA är genom att gå till [README-anvisningarna på GitHub](https://github.com/OfficeDev/MCCA#overview).</span><span class="sxs-lookup"><span data-stu-id="01a67-111">An additional resource for understanding MCCA is by visiting the [README instructions on GitHub](https://github.com/OfficeDev/MCCA#overview).</span></span> <span data-ttu-id="01a67-112">På den här sidan finns detaljerad information om krav och fullständiga installationsanvisningar.</span><span class="sxs-lookup"><span data-stu-id="01a67-112">This page provides detailed information about prerequisites and gives full installation instructions.</span></span> <span data-ttu-id="01a67-113">Du behöver inte ett konto GitHub komma åt den här sidan.</span><span class="sxs-lookup"><span data-stu-id="01a67-113">You don’t need a GitHub account to access this page.</span></span>

<span data-ttu-id="01a67-114">**Tillgänglighet:** MCCA är tillgängligt för alla organisationer med Office 365- och Microsoft 365-licenser och kunder med amerikanska Government Community (GCC) Måttliga, GCC High och Department of Defense (DoD).</span><span class="sxs-lookup"><span data-stu-id="01a67-114">**Availability**: MCCA is available to all organizations with Office 365 and Microsoft 365 licenses and US Government Community (GCC) Moderate, GCC High, and Department of Defense (DoD) customers.</span></span>

## <a name="install-mcca-and-run-a-report"></a><span data-ttu-id="01a67-115">Installera MCCA och kör en rapport</span><span class="sxs-lookup"><span data-stu-id="01a67-115">Install MCCA and run a report</span></span>

<span data-ttu-id="01a67-116">Du kan installera MCCA-verktyget med Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="01a67-116">You can install the MCCA tool using Windows PowerShell.</span></span> <span data-ttu-id="01a67-117">När du har laddat ned och installerat verktyget behöver du inte upprepa dessa steg för att kunna köra rapporter.</span><span class="sxs-lookup"><span data-stu-id="01a67-117">Once you download and install the tool, you don’t need to repeat those steps in order to run reports.</span></span> <span data-ttu-id="01a67-118">Varje gång du öppnar MCCA uppmanas du att logga in och en ny, uppdaterad rapport skapas.</span><span class="sxs-lookup"><span data-stu-id="01a67-118">Each time you open MCCA, it will ask you for your login credentials, and it will generate a new, updated report.</span></span>

#### <a name="step-1-install-windows-powershell"></a><span data-ttu-id="01a67-119">Steg 1: Installera Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="01a67-119">Step 1: Install Windows PowerShell</span></span>
<span data-ttu-id="01a67-120">För att börja behöver du den Exchange Online PowerShell-modul (v2.0.3 eller senare) som finns tillgänglig i PowerShell-galleriet.</span><span class="sxs-lookup"><span data-stu-id="01a67-120">To begin, you'll need the Exchange Online PowerShell module (v2.0.3 or higher) that's available in the PowerShell gallery.</span></span> <span data-ttu-id="01a67-121">[Få installationsanvisningar.](https://www.powershellgallery.com/packages/ExchangeOnlineManagement/2.0.3)</span><span class="sxs-lookup"><span data-stu-id="01a67-121">[Get installation instructions](https://www.powershellgallery.com/packages/ExchangeOnlineManagement/2.0.3).</span></span>

#### <a name="step-2-install-mcca"></a><span data-ttu-id="01a67-122">Steg 2: Installera MCCA</span><span class="sxs-lookup"><span data-stu-id="01a67-122">Step 2: Install MCCA</span></span>

<span data-ttu-id="01a67-123">Installera MCCA genom att börja med att använda PowerShell i administratörsläge.</span><span class="sxs-lookup"><span data-stu-id="01a67-123">To install MCCA, start by using PowerShell in administrator mode.</span></span> <span data-ttu-id="01a67-124">Följ stegen nedan:</span><span class="sxs-lookup"><span data-stu-id="01a67-124">Follow the steps below:</span></span>

1. <span data-ttu-id="01a67-125">Välj Windows **Start.**</span><span class="sxs-lookup"><span data-stu-id="01a67-125">Select the Windows **Start** button.</span></span>
2. <span data-ttu-id="01a67-126">Skriv **PowerShell**, högerklicka på **Windows PowerShell** välj sedan Kör som **administratör.**</span><span class="sxs-lookup"><span data-stu-id="01a67-126">Type **PowerShell**, right-click on **Windows PowerShell**, then select **Run as administrator**.</span></span>
1. <span data-ttu-id="01a67-127">I kommandotolken skriver du:</span><span class="sxs-lookup"><span data-stu-id="01a67-127">At the command prompt, type:</span></span>

    ```powershell
    Install-Module -Name MCCAPreview
    ```

#### <a name="step-3-run-a-report"></a><span data-ttu-id="01a67-128">Steg 3: Kör en rapport</span><span class="sxs-lookup"><span data-stu-id="01a67-128">Step 3: Run a report</span></span>

<span data-ttu-id="01a67-129">När du har installerat MCCA kan du köra MCCA och generera en rapport.</span><span class="sxs-lookup"><span data-stu-id="01a67-129">After you install MCCA, you can run MCCA and generate a report.</span></span> <span data-ttu-id="01a67-130">Så här kör du en rapport:</span><span class="sxs-lookup"><span data-stu-id="01a67-130">To run a report:</span></span>

1. <span data-ttu-id="01a67-131">Öppna PowerShell</span><span class="sxs-lookup"><span data-stu-id="01a67-131">Open PowerShell</span></span>
2. <span data-ttu-id="01a67-132">Kör cmdleten:</span><span class="sxs-lookup"><span data-stu-id="01a67-132">Run the cmdlet:</span></span>

    ```powershell
    Get-MCCAReport
    ```

   <span data-ttu-id="01a67-133">Om du är en GCC High-kund måste du ange en ytterligare indataparameter för att köra rapporten:</span><span class="sxs-lookup"><span data-stu-id="01a67-133">If you're a GCC High customer, you'll need to provide an additional input parameter to run the report:</span></span>

    ```powershell
    Get-MCCAReport -ExchangeEnvironmentName O365USGovGCCHigh
    ```

3. <span data-ttu-id="01a67-134">När MCCA körs gör den en första versionskontroll och begär autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="01a67-134">Once MCCA runs, it does an initial version check and ask for credentials.</span></span> <span data-ttu-id="01a67-135">I meddelandet Ange användarnamn loggar du in med e-postadressen för Microsoft 365 konto (visa rollerna[som är kvalificerade för att skapa rapporter).](#role-based-reporting)</span><span class="sxs-lookup"><span data-stu-id="01a67-135">At the Input the user name prompt, sign in with your Microsoft 365 account email address ([view the roles eligible to create reports](#role-based-reporting)).</span></span> <span data-ttu-id="01a67-136">Ange sedan lösenordet när du uppmanas att ange lösenordet.</span><span class="sxs-lookup"><span data-stu-id="01a67-136">Then enter your password at the password prompt.</span></span>

<span data-ttu-id="01a67-137">Det tar sedan ungefär 2–5 minuter att generera rapporten.</span><span class="sxs-lookup"><span data-stu-id="01a67-137">Your report will then take approximately 2-5 minutes to generate.</span></span> <span data-ttu-id="01a67-138">När det är klart öppnas ett webbläsarfönster med HTML-rapporten.</span><span class="sxs-lookup"><span data-stu-id="01a67-138">When it’s done, a browser window opens and displays your HTML report.</span></span> <span data-ttu-id="01a67-139">Varje gång du kör verktyget begär den dina autentiseringsuppgifter och skapar en ny rapport.</span><span class="sxs-lookup"><span data-stu-id="01a67-139">Every time you run the tool, it will ask for your credentials and generate a new report.</span></span> <span data-ttu-id="01a67-140">Den här rapporten lagras lokalt i följande katalog:</span><span class="sxs-lookup"><span data-stu-id="01a67-140">This report is stored locally in the following directory:</span></span>

<span data-ttu-id="01a67-141">C:\Users \<username> \AppData\Local\Microsoft\MCCA.</span><span class="sxs-lookup"><span data-stu-id="01a67-141">C:\Users\<username>\AppData\Local\Microsoft\MCCA.</span></span> 

<span data-ttu-id="01a67-142">Du kan komma åt tidigare skapade rapporter från den här katalogen.</span><span class="sxs-lookup"><span data-stu-id="01a67-142">You can access previously generated reports from this directory.</span></span>

## <a name="understanding-your-report"></a><span data-ttu-id="01a67-143">Förstå rapporten</span><span class="sxs-lookup"><span data-stu-id="01a67-143">Understanding your report</span></span>

<span data-ttu-id="01a67-144">I rapporten återges data baserat på datum och tid då de skapades.</span><span class="sxs-lookup"><span data-stu-id="01a67-144">Your report reflects data based on the date and time at which it was generated.</span></span> <span data-ttu-id="01a67-145">I det övre avsnittet finns information om när den skapades, organisationens namn och klientorganisations-ID.</span><span class="sxs-lookup"><span data-stu-id="01a67-145">The top section provides details on when it was generated, your organization name, and tenant ID.</span></span>

#### <a name="geolocation-based-reporting"></a><span data-ttu-id="01a67-146">Geolokaliseringsbaserad rapportering</span><span class="sxs-lookup"><span data-stu-id="01a67-146">Geolocation-based reporting</span></span>

<span data-ttu-id="01a67-147">Avsnittet **Anteckning** visar att rapporten är anpassad baserat på klientorganisationens geografiska position.</span><span class="sxs-lookup"><span data-stu-id="01a67-147">The **Note** section shows that your report is customized based on the geographic location of your tenant.</span></span> <span data-ttu-id="01a67-148">Rekommendationer som visas i verktyget är specifika för ditt land eller din region.</span><span class="sxs-lookup"><span data-stu-id="01a67-148">Recommendations listed in the tool will be specific to your country or region.</span></span>

<span data-ttu-id="01a67-149">Ditt geolokaliseringsval används för att bedöma typer av känslig information (SITs) som är relevanta för den geolokaliseringen och generera en rapport som passar ditt land eller din region.</span><span class="sxs-lookup"><span data-stu-id="01a67-149">Your geolocation selection is used to assess sensitive information types (SITs) which are relevant to that geolocation and generate a report that aligns to your country or region.</span></span> <span data-ttu-id="01a67-150">Välj geolokaliseringar baserat på data som finns i klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="01a67-150">Choose geolocations based on data you have in your tenant.</span></span>

<span data-ttu-id="01a67-151">Om du vill ändra rapportens platsinformation måste du ange en geolokaliseringsparameter (-Geo).</span><span class="sxs-lookup"><span data-stu-id="01a67-151">To change your report's location information, you need provide a geolocation (-Geo) input parameter.</span></span> <span data-ttu-id="01a67-152">Du kan välja en eller flera geolokaliseringar som gäller för din klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="01a67-152">You can choose either one or multiple geolocations applicable for your tenant.</span></span>

<span data-ttu-id="01a67-153">Följ de här anvisningarna om du vill köra en rapport baserat på en viss plats:</span><span class="sxs-lookup"><span data-stu-id="01a67-153">Follow these instructions to run a report based on a specific location:</span></span>

1. <span data-ttu-id="01a67-154">Öppna PowerShell</span><span class="sxs-lookup"><span data-stu-id="01a67-154">Open PowerShell</span></span>
2. <span data-ttu-id="01a67-155">Om du vill ange en viss region kör du en cmdlet med siffrorna i tabellen nedan som motsvarar landet eller regionen.</span><span class="sxs-lookup"><span data-stu-id="01a67-155">To specify a certain region, you’ll run a cmdlet using the numbers from the table below that correspond to the country or region.</span></span> <span data-ttu-id="01a67-156">Ange flera tal genom att avgränsa dem med kommatecken.</span><span class="sxs-lookup"><span data-stu-id="01a67-156">Enter multiple numbers by separating them with a comma.</span></span> <span data-ttu-id="01a67-157">Cmdleten nedan kör till exempel en anpassad rapport för Asia-Pacific och Japan:</span><span class="sxs-lookup"><span data-stu-id="01a67-157">For example, the cmdlet below will run a customized report for Asia-Pacific and Japan:</span></span>

    ```powershell
    Get-MCCAReport -Geo @(1,7)
    ```
  | <span data-ttu-id="01a67-158">Inmatning</span><span class="sxs-lookup"><span data-stu-id="01a67-158">Input</span></span> |  <span data-ttu-id="01a67-159">Land eller region</span><span class="sxs-lookup"><span data-stu-id="01a67-159">Country or Region</span></span> | 
  | :------------- | :------------: |
  | <span data-ttu-id="01a67-160">1</span><span class="sxs-lookup"><span data-stu-id="01a67-160">1</span></span> | <span data-ttu-id="01a67-161">Asia-Pacific</span><span class="sxs-lookup"><span data-stu-id="01a67-161">Asia-Pacific</span></span> |
  | <span data-ttu-id="01a67-162">2</span><span class="sxs-lookup"><span data-stu-id="01a67-162">2</span></span> | <span data-ttu-id="01a67-163">Australien</span><span class="sxs-lookup"><span data-stu-id="01a67-163">Australia</span></span> |
  | <span data-ttu-id="01a67-164">3</span><span class="sxs-lookup"><span data-stu-id="01a67-164">3</span></span> | <span data-ttu-id="01a67-165">Kanada</span><span class="sxs-lookup"><span data-stu-id="01a67-165">Canada</span></span> |
  | <span data-ttu-id="01a67-166">4</span><span class="sxs-lookup"><span data-stu-id="01a67-166">4</span></span> | <span data-ttu-id="01a67-167">Europa (undantaget Frankrike) / Mellanöstern/Afrika</span><span class="sxs-lookup"><span data-stu-id="01a67-167">Europe (excluding France) / Middle East / Africa</span></span> |
  | <span data-ttu-id="01a67-168">5</span><span class="sxs-lookup"><span data-stu-id="01a67-168">5</span></span> | <span data-ttu-id="01a67-169">Frankrike</span><span class="sxs-lookup"><span data-stu-id="01a67-169">France</span></span> |
  | <span data-ttu-id="01a67-170">6</span><span class="sxs-lookup"><span data-stu-id="01a67-170">6</span></span> | <span data-ttu-id="01a67-171">Indien</span><span class="sxs-lookup"><span data-stu-id="01a67-171">India</span></span> |
  | <span data-ttu-id="01a67-172">7</span><span class="sxs-lookup"><span data-stu-id="01a67-172">7</span></span> | <span data-ttu-id="01a67-173">Japan </span><span class="sxs-lookup"><span data-stu-id="01a67-173">Japan</span></span> |
  | <span data-ttu-id="01a67-174">8</span><span class="sxs-lookup"><span data-stu-id="01a67-174">8</span></span> | <span data-ttu-id="01a67-175">Korea </span><span class="sxs-lookup"><span data-stu-id="01a67-175">Korea</span></span> |
  | <span data-ttu-id="01a67-176">9</span><span class="sxs-lookup"><span data-stu-id="01a67-176">9</span></span> | <span data-ttu-id="01a67-177">Nordamerika (exklusive Kanada)</span><span class="sxs-lookup"><span data-stu-id="01a67-177">North America (excluding Canada)</span></span> |
  | <span data-ttu-id="01a67-178">10</span><span class="sxs-lookup"><span data-stu-id="01a67-178">10</span></span> | <span data-ttu-id="01a67-179">Sydamerika</span><span class="sxs-lookup"><span data-stu-id="01a67-179">South America</span></span> |
  | <span data-ttu-id="01a67-180">11</span><span class="sxs-lookup"><span data-stu-id="01a67-180">11</span></span> | <span data-ttu-id="01a67-181">Sydafrika</span><span class="sxs-lookup"><span data-stu-id="01a67-181">South Africa</span></span> |
  | <span data-ttu-id="01a67-182">12</span><span class="sxs-lookup"><span data-stu-id="01a67-182">12</span></span> | <span data-ttu-id="01a67-183">Schweiz</span><span class="sxs-lookup"><span data-stu-id="01a67-183">Switzerland</span></span> |
  | <span data-ttu-id="01a67-184">13</span><span class="sxs-lookup"><span data-stu-id="01a67-184">13</span></span> | <span data-ttu-id="01a67-185">Förenade Arabemiraten</span><span class="sxs-lookup"><span data-stu-id="01a67-185">United Arab Emirates</span></span> |
  | <span data-ttu-id="01a67-186">14</span><span class="sxs-lookup"><span data-stu-id="01a67-186">14</span></span> | <span data-ttu-id="01a67-187">Storbritannien</span><span class="sxs-lookup"><span data-stu-id="01a67-187">United Kingdom</span></span> |


 > [!NOTE]
> <span data-ttu-id="01a67-188">Rapporten kommer alltid att innehålla internationella typer av känslig information som stöds av MCCA, till exempel SWIFT-kod, kreditkortsnummer osv.</span><span class="sxs-lookup"><span data-stu-id="01a67-188">The report will always include MCCA supported international sensitive information types such as SWIFT code, credit card number, etc.</span></span>

#### <a name="role-based-reporting"></a><span data-ttu-id="01a67-189">Rollbaserad rapportering</span><span class="sxs-lookup"><span data-stu-id="01a67-189">Role-based reporting</span></span>

<span data-ttu-id="01a67-190">Rapporten anpassas också efter din roll.</span><span class="sxs-lookup"><span data-stu-id="01a67-190">Your report will also be customized based on your role.</span></span>

<span data-ttu-id="01a67-191">I tabellen nedan visas vilka roller som har åtkomst till vilka avsnitt i rapporten.</span><span class="sxs-lookup"><span data-stu-id="01a67-191">The table below shows which roles have access to which sections of the report.</span></span> <span data-ttu-id="01a67-192">Andra roller i organisationen (som inte visas i tabellen nedan) kanske inte kan köra verktyget, eller så kan de köra verktyget och har begränsad åtkomst till information i den slutliga rapporten.</span><span class="sxs-lookup"><span data-stu-id="01a67-192">Other roles within your organization (not listed in the table below) may not be able to run the tool, or they may run the tool and have limited access to information in the final report.</span></span>

<span data-ttu-id="01a67-193">![MCCA – roller](../media/compliance-manager-mcca-roles.png "MCCA-roller")</span><span class="sxs-lookup"><span data-stu-id="01a67-193">![MCCA - roles](../media/compliance-manager-mcca-roles.png "MCCA roles")</span></span>

<span data-ttu-id="01a67-194">Undantag:</span><span class="sxs-lookup"><span data-stu-id="01a67-194">Exceptions:</span></span>
1. <span data-ttu-id="01a67-195">Användarna kan inte generera rapporten om IP förutom avsnittet "Använd IRM för Exchange Online".</span><span class="sxs-lookup"><span data-stu-id="01a67-195">Users won't be able to generate report for IP apart from “Use IRM for Exchange Online” section.</span></span>
2. <span data-ttu-id="01a67-196">Användarna kan generera rapporten om IP förutom avsnittet "Använd IRM för Exchange Online".</span><span class="sxs-lookup"><span data-stu-id="01a67-196">Users will be able to generate report for IP apart from “Use IRM for Exchange Online” section.</span></span>
3. <span data-ttu-id="01a67-197">Användarna kommer att kunna generera en rapport om IP förutom avsnittet "Aktivera kommunikationsefterlevnad i O365".</span><span class="sxs-lookup"><span data-stu-id="01a67-197">Users will be able to generate report for IP apart from “Enable Communication Compliance in O365” section.</span></span>
4. <span data-ttu-id="01a67-198">Användarna kan inte generera rapporter för IP förutom avsnittet "Aktivera granskning i Office 365".</span><span class="sxs-lookup"><span data-stu-id="01a67-198">Users won't be able to generate report for IP apart from “Enable Auditing in Office 365” section.</span></span>
5. <span data-ttu-id="01a67-199">Användarna kan generera rapporten för IP förutom avsnittet "Aktivera granskning i Office 365".</span><span class="sxs-lookup"><span data-stu-id="01a67-199">Users will be able generate report for IP apart from “Enable Auditing in Office 365” section.</span></span>

#### <a name="solutions-summary-section"></a><span data-ttu-id="01a67-200">Avsnittet Sammanfattning av lösningar</span><span class="sxs-lookup"><span data-stu-id="01a67-200">Solutions Summary section</span></span>

<span data-ttu-id="01a67-201">I **avsnittet Sammanfattning av** lösningar i rapporten finns en översikt över de förbättringsåtgärder som din organisation kan vidta i Efterlevnadshanteraren för att förbättra kompatibiliteten.</span><span class="sxs-lookup"><span data-stu-id="01a67-201">The **Solutions Summary** section of the report gives an overview of improvement actions that your organization can take in Compliance Manager to help improve your compliance posture.</span></span>

<span data-ttu-id="01a67-202">![MCCA – sammanfattning av lösningar](../media/compliance-manager-mcca-solutions.png "Sammanfattningsskärm för MCCA-lösningar")</span><span class="sxs-lookup"><span data-stu-id="01a67-202">![MCCA - solutions summary](../media/compliance-manager-mcca-solutions.png "MCCA Solutions Summary screen")</span></span>

<span data-ttu-id="01a67-203">MCCA utvärderar dina aktuella konfigurationer mot rekommenderade förbättringsåtgärder i Efterlevnadshanteraren.</span><span class="sxs-lookup"><span data-stu-id="01a67-203">MCCA evaluates your current configurations against the recommended improvement actions in Compliance Manager.</span></span> <span data-ttu-id="01a67-204">Eventuella förbättringsåtgärder som identifieras av MCCA-verktyget som behöver uppmärksammas visas i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="01a67-204">Any improvement action identified by the MCCA tool as needing attention will be listed in this section.</span></span>

<span data-ttu-id="01a67-205">Bredvid varje Microsoft-lösning finns färgkodade rutor som anger antalet objekt som motsvarar förbättringsåtgärder i Efterlevnadshanteraren.</span><span class="sxs-lookup"><span data-stu-id="01a67-205">Next to each Microsoft solution are color-coded boxes indicating the number of items that correspond to improvement actions in Compliance Manager.</span></span> <span data-ttu-id="01a67-206">Åtgärderna delas in i tre statustillstånd:</span><span class="sxs-lookup"><span data-stu-id="01a67-206">The actions are broken down into three status states:</span></span>

- <span data-ttu-id="01a67-207">**OK:** de åtgärder som uppfyller rekommenderade villkor och som inte behöver uppmärksammas just nu</span><span class="sxs-lookup"><span data-stu-id="01a67-207">**OK**: the actions that meet recommended conditions and need no attention at this time</span></span>
- <span data-ttu-id="01a67-208">**Förbättring:** åtgärder som behöver uppmärksammas</span><span class="sxs-lookup"><span data-stu-id="01a67-208">**Improvement**: actions that need attention</span></span>
- <span data-ttu-id="01a67-209">**Rekommendation:** åtgärder som inte behöver uppmärksammas, men som vi rekommenderar metodtips för</span><span class="sxs-lookup"><span data-stu-id="01a67-209">**Recommendation**: actions that don’t need attention, but for which we recommend best practices</span></span>
 
<span data-ttu-id="01a67-210">Markera en ruta för att visa förbättringar och rekommendationer.</span><span class="sxs-lookup"><span data-stu-id="01a67-210">Select a box to view improvements and recommendations.</span></span>

<span data-ttu-id="01a67-211">**Objekt med förbättringsstatus**</span><span class="sxs-lookup"><span data-stu-id="01a67-211">**Items with the Improvement status**</span></span>

<span data-ttu-id="01a67-212">Välj listrutan bredvid etiketten **Förbättring** till höger om förbättringsåtgärden.</span><span class="sxs-lookup"><span data-stu-id="01a67-212">Select the dropdown next to the **Improvement** label to the right of the improvement action.</span></span> <span data-ttu-id="01a67-213">Du ser en snabbsammanfattning och information om dina aktuella inställningar och rekommenderade förbättringsåtgärder.</span><span class="sxs-lookup"><span data-stu-id="01a67-213">You’ll see a quick summary and details about your current settings and the recommended improvement actions.</span></span> <span data-ttu-id="01a67-214">Sammanfattningen innehåller direktlänkar till Efterlevnadshanteraren, den tillämpliga lösningen i Microsoft 365 Efterlevnadscenter och relevant dokumentation.</span><span class="sxs-lookup"><span data-stu-id="01a67-214">The summary includes direct links into Compliance Manager, the applicable solution in the Microsoft 365 compliance center, and relevant documentation.</span></span>

<span data-ttu-id="01a67-215">Om du klickar på länken Efterlevnadshanteraren visas en filtrerad vy över alla förbättringsåtgärder i lösningen som du ännu inte har implementerat.</span><span class="sxs-lookup"><span data-stu-id="01a67-215">Clicking on the Compliance Manager link takes you to a filtered view of all the improvement actions within that solution that you have not yet implemented.</span></span> <span data-ttu-id="01a67-216">Därifrån kan du se antalet punkter du kan uppnå för att öka ditt efterlevnadsresultat [,](compliance-score-calculation.md)och de utvärderingar som de gäller för, samt tillämpliga bestämmelser och certifieringar.</span><span class="sxs-lookup"><span data-stu-id="01a67-216">From there, you can see the number of points you can achieve to increase your [compliance score](compliance-score-calculation.md), and the assessments they apply to, and the applicable regulations and certifications.</span></span>

<span data-ttu-id="01a67-217">För DLP finns knappen **Åtgärdsskript** som ger dig ett förgenererat PowerShell-skript baserat på vad som rekommenderas.</span><span class="sxs-lookup"><span data-stu-id="01a67-217">For DLP, there’s a **Remediation Script** button that gives you a pre-generated PowerShell script based on what’s recommended.</span></span> <span data-ttu-id="01a67-218">Du kan kopiera och klistra in den direkt i PowerShell-konsolen.</span><span class="sxs-lookup"><span data-stu-id="01a67-218">You can copy and paste it directly in your PowerShell console.</span></span> <span data-ttu-id="01a67-219">En DLP-princip skapas i testläge</span><span class="sxs-lookup"><span data-stu-id="01a67-219">It will create a DLP policy in test mode</span></span>

<span data-ttu-id="01a67-220">**Objekt med rekommendationsstatus**</span><span class="sxs-lookup"><span data-stu-id="01a67-220">**Items with Recommendation status**</span></span>

<span data-ttu-id="01a67-221">Välj listrutan bredvid etiketten **Rekommendation** till höger om förbättringsåtgärden.</span><span class="sxs-lookup"><span data-stu-id="01a67-221">Select the dropdown next to the **Recommendation** label to the right of the improvement action.</span></span> <span data-ttu-id="01a67-222">En sammanfattning av organisationens aktuella användningsmiljö Microsoft 365 förbättringsåtgärden visas tillsammans med rekommenderade metodtips.</span><span class="sxs-lookup"><span data-stu-id="01a67-222">You’ll see a summary of your organization’s current Microsoft 365 environment related to the improvement action, along with recommended best practices.</span></span>

## <a name="resources"></a><span data-ttu-id="01a67-223">Resurser</span><span class="sxs-lookup"><span data-stu-id="01a67-223">Resources</span></span>

<span data-ttu-id="01a67-224">Mer detaljerad information om att installera, konfigurera och använda MCCA finns i [README-anvisningarna](https://github.com/OfficeDev/MCCA#overview) för GitHub (inget GitHub konto krävs).</span><span class="sxs-lookup"><span data-stu-id="01a67-224">For more detailed information on installing, setting up, and using MCCA, see the [README instructions on GitHub](https://github.com/OfficeDev/MCCA#overview) (no GitHub account required).</span></span>

<span data-ttu-id="01a67-225">Mer information om Windows PowerShell finns i Så [här använder du PowerShell-dokumentationen.](/powershell/scripting/how-to-use-docs?view=powershell-7)</span><span class="sxs-lookup"><span data-stu-id="01a67-225">For more information on Windows PowerShell, start at [How to use the PowerShell documentation](/powershell/scripting/how-to-use-docs?view=powershell-7).</span></span> <span data-ttu-id="01a67-226">Se även [Windows PowerShell.](/powershell/scripting/windows-powershell/starting-windows-powershell?view=powershell-7)</span><span class="sxs-lookup"><span data-stu-id="01a67-226">See also [Starting Windows PowerShell](/powershell/scripting/windows-powershell/starting-windows-powershell?view=powershell-7).</span></span>
