---
title: Vanliga frågor och svar om testbas
description: Gå igenom vanliga frågor och svar
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: troubleshooting
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: 9d24ecb807e60733471be60353d12789f19be1b4
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323385"
---
# <a name="test-base-faq"></a><span data-ttu-id="06674-103">Vanliga frågor och svar om testbas</span><span class="sxs-lookup"><span data-stu-id="06674-103">Test Base FAQ</span></span>

<span data-ttu-id="06674-104">**F: Hur skickar vi in våra paket till Test Base-teamet?**</span><span class="sxs-lookup"><span data-stu-id="06674-104">**Q: How do we submit our packages to Test Base team?**</span></span>

<span data-ttu-id="06674-105">**S:** Skicka paketen direkt till Test Base-miljön med vår självbetjäningsportal.</span><span class="sxs-lookup"><span data-stu-id="06674-105">**A:** Submit your packages directly to the Test Base environment using our self-serve portal.</span></span>

<span data-ttu-id="06674-106">Skicka programpaketet genom att gå till [Azure-portalen](https://www.aka.ms/testbaseportal "Startsida för testbas") och ladda upp en zippad mapp som innehåller programmets binärfiler, beroenden och testskript via instrumentpanelen Test Base-självbetjäning för portalen.</span><span class="sxs-lookup"><span data-stu-id="06674-106">To submit your application package, navigate to the [Azure Portal](https://www.aka.ms/testbaseportal "Test Base Homepage") and upload a zipped folder containing your application's binaries, dependencies, and test scripts via the self-serve Test Base portal dashboard.</span></span> 

<span data-ttu-id="06674-107">Mer information finns i introduktionsguiden eller kontakta vårt team för <testbasepreview@microsoft.com> att få hjälp och mer information.</span><span class="sxs-lookup"><span data-stu-id="06674-107">Please see the onboarding user guide for more information or contact our team at <testbasepreview@microsoft.com> for assistance and more information.</span></span>

<span data-ttu-id="06674-108">**F: Vad är OOB-tester (in-box)**</span><span class="sxs-lookup"><span data-stu-id="06674-108">**Q: What are Out-of-box (OOB) tests?**</span></span>

<span data-ttu-id="06674-109">**S:** OOB-tester (out-of-box) är standardiserade, standardtestet körs där programpaket installeras, startas och stängs trettio (30) gånger och avinstalleras sedan.</span><span class="sxs-lookup"><span data-stu-id="06674-109">**A:** Out-of-box (OOB) tests are standardized, default test runs where application packages are installed, launched and closed thirty (30) times, and then uninstalled.</span></span> 

<span data-ttu-id="06674-110">Paketen som skapas för Test Base har följande testskript: installera, starta, stäng och eventuellt avinstallationsskriptet.</span><span class="sxs-lookup"><span data-stu-id="06674-110">The packages created for Test Base will have the following test scripts: install, launch, close, and optionally the uninstall script.</span></span> 

<span data-ttu-id="06674-111">OOB-testerna (Out-box) ger dig standardiserade telemetri för programmet att jämföra mellan olika Windows byggen.</span><span class="sxs-lookup"><span data-stu-id="06674-111">The Out-of-box (OOB) tests provide you with standardized telemetry on your application to compare across Windows builds.</span></span>

<span data-ttu-id="06674-112">**F: Kan vi skicka in tester utanför de inramade testerna (installation, start, stängning, avinstallation av testskript)?**</span><span class="sxs-lookup"><span data-stu-id="06674-112">**Q: Can we submit tests outside of the Out-of-box tests (install, launch, close, uninstall test scripts)?**</span></span>

<span data-ttu-id="06674-113">**S:** Ja, kunder kan även ladda upp programpaket för **funktionstester** via instrumentpanelen på portalen.</span><span class="sxs-lookup"><span data-stu-id="06674-113">**A:** Yes, customers can also upload application packages for **functional tests** via the self-serve portal dashboard.</span></span>
<span data-ttu-id="06674-114">**Funktionstester** är tester som gör att kunderna kan köra sina skript för att köra anpassade funktioner på programmet.</span><span class="sxs-lookup"><span data-stu-id="06674-114">**Functional tests** are tests that enable customers execute their scripts to run custom functionality on their application.</span></span>


## <a name="testing"></a><span data-ttu-id="06674-115">Testning</span><span class="sxs-lookup"><span data-stu-id="06674-115">Testing</span></span>

<span data-ttu-id="06674-116">**F: Stöder ni funktionstester?**</span><span class="sxs-lookup"><span data-stu-id="06674-116">**Q: Do you support functional tests?**</span></span>

<span data-ttu-id="06674-117">**S:** Ja, testbas har stöd för funktionstester.</span><span class="sxs-lookup"><span data-stu-id="06674-117">**A:** Yes, Test Base supports functional tests.</span></span> <span data-ttu-id="06674-118">Funktionstester är tester som gör att våra kunder kan köra sina skript för att köra anpassade funktioner i programmet.</span><span class="sxs-lookup"><span data-stu-id="06674-118">Functional tests are tests that enable our customers execute their scripts to run custom functionality on their application.</span></span> 

<span data-ttu-id="06674-119">Om du vill skicka in ditt programpaket för funktionstestning behöver du bara ladda upp den zippade mappen som innehåller programmets binärfiler, beroenden och testskript via vår självbetjäningsportalinstrumentpanel.</span><span class="sxs-lookup"><span data-stu-id="06674-119">To submit your application package for functional testing, simply upload the zipped folder containing your application's binaries, dependencies, and test scripts via our self-serve portal dashboard.</span></span> 

<span data-ttu-id="06674-120">Mer information finns i introduktionsguiden eller kontakta vårt team för <testbasepreview@microsoft.com> att få hjälp och mer information.</span><span class="sxs-lookup"><span data-stu-id="06674-120">Please see the onboarding user guide for more information or contact our team at <testbasepreview@microsoft.com> for assistance and more information.</span></span>

<span data-ttu-id="06674-121">**F: Hur hanterar Test Base våra testdata?**</span><span class="sxs-lookup"><span data-stu-id="06674-121">**Q: How does Test Base handle our test data?**</span></span>

<span data-ttu-id="06674-122">**S:** Test Base samlar in och hanterar testdata på ett säkert sätt i Azure-miljön.</span><span class="sxs-lookup"><span data-stu-id="06674-122">**A:** Test Base securely collects and manages your test data on the Azure environment.</span></span> 

<span data-ttu-id="06674-123">**F: Kan testbasen stödja våra automatiska tester?**</span><span class="sxs-lookup"><span data-stu-id="06674-123">**Q: Can Test Base support our automated tests?**</span></span>

<span data-ttu-id="06674-124">Ja, Test Base stöder automatiska tester men vi stöder inte manuella tester just nu på grund av tjänstefunktioner.</span><span class="sxs-lookup"><span data-stu-id="06674-124">Yes, Test Base supports automated tests however, we do not support manual tests at this time due to service capabilities.</span></span>

<span data-ttu-id="06674-125">**F: Vilka språk och ramverk för automatiska tester stöder du?**</span><span class="sxs-lookup"><span data-stu-id="06674-125">**Q: What languages and frameworks of automated tests do you support?**</span></span>

<span data-ttu-id="06674-126">**S:** Vi stöder alla språk och ramverk.</span><span class="sxs-lookup"><span data-stu-id="06674-126">**A:** We support all languages and frameworks.</span></span> <span data-ttu-id="06674-127">Vi anropar alla skript via PowerShell.</span><span class="sxs-lookup"><span data-stu-id="06674-127">We invoke all scripts through PowerShell.</span></span> 

<span data-ttu-id="06674-128">Du måste också tillhandahålla (ladda upp) de beroende binärfilerna för det nödvändiga ramverket.</span><span class="sxs-lookup"><span data-stu-id="06674-128">You will also need to provide (upload) the dependent binaries of the required framework.</span></span>

<span data-ttu-id="06674-129">**F: Hur snart tillhandahåller Test Base testresultat?**</span><span class="sxs-lookup"><span data-stu-id="06674-129">**Q: How soon does Test Base provide test results?**</span></span>

<span data-ttu-id="06674-130">**S:** För varje test vi kör mot förhands versionerna kommer vi att tillhandahålla resultat inom 48 timmar på din [Azure Portal-instrumentpanel.](https://www.aka.ms/testbaseportal "Startsida för testbas")</span><span class="sxs-lookup"><span data-stu-id="06674-130">**A:** For each test that we run against the pre-release builds, we will provide results within 48 hours on your [Azure Portal](https://www.aka.ms/testbaseportal "Test Base Homepage") dashboard.</span></span>

<span data-ttu-id="06674-131">**F: Kan du starta om efter installationen?**</span><span class="sxs-lookup"><span data-stu-id="06674-131">**Q: Can you reboot after install?**</span></span>

<span data-ttu-id="06674-132">**S:** Ja, vår process har stöd för att starta om efter installationen.</span><span class="sxs-lookup"><span data-stu-id="06674-132">**A:** Yes, our process supports rebooting after installation.</span></span> <span data-ttu-id="06674-133">Se till att välja det här alternativet i listrutan "Valfria inställningar" när du anger **Dina** uppgifter på introduktionsportalen.</span><span class="sxs-lookup"><span data-stu-id="06674-133">Be sure to select this option from the “Optional settings” drop list when setting your **Tasks** on the onboarding portal.</span></span>

<span data-ttu-id="06674-134">För OOB-tester (Out-of-box) kan du ange om en omstart krävs för _installationsskriptet._</span><span class="sxs-lookup"><span data-stu-id="06674-134">For Out-of-box (OOB) tests, you can specify whether a reboot is needed for the _Install script._</span></span>

![Starta om bild](Media/reboot.png)

<span data-ttu-id="06674-136">När du ska köra funktionstester kan du ange om en omstart krävs för varje skript som läggs till.</span><span class="sxs-lookup"><span data-stu-id="06674-136">While for functional tests, you can specify whether a reboot is required for each script that is added.</span></span>

![Välja funktionstest](Media/functionalreboot.png)

<span data-ttu-id="06674-138">**F: Vilka Windows versioner stöder du?**</span><span class="sxs-lookup"><span data-stu-id="06674-138">**Q: What Windows versions do you support?**</span></span>

<span data-ttu-id="06674-139">**S:** Vi har för närvarande Windows 10 för klienter, Windows Server 2016, Windows Server 2016 Core-version, Windows Server 2019 och Windows Server 2019 Core-versionen.</span><span class="sxs-lookup"><span data-stu-id="06674-139">**A:** We currently support Windows 10 clients, Windows Server 2016, Windows Server 2016 Core version, Windows Server 2019, and Windows Server 2019 Core version.</span></span>

<span data-ttu-id="06674-140">**F: Vad är skillnaden mellan säkerhetsuppdateringstester och funktionsuppdateringstester?**</span><span class="sxs-lookup"><span data-stu-id="06674-140">**Q: What is the difference between Security Update tests and Feature Update tests?**</span></span>

<span data-ttu-id="06674-141">**S:** För tester av säkerhetsuppdateringar **<ins></ins>** testar vi mot de månatliga säkerhetsuppdateringarna den Windows som fokuserar på att se till att våra användare alltid är skyddade och skyddade.</span><span class="sxs-lookup"><span data-stu-id="06674-141">**A:** For Security update tests, we test against the **<ins>monthly pre-release security updates</ins>** on Windows which are focused on keeping our users always secure and protected.</span></span> <span data-ttu-id="06674-142">För funktionsuppdateringstesterna testar vi mot de **<ins>bi-årliga</ins>** förhandsuppdateringarna som introducerar nya funktioner på Windows.</span><span class="sxs-lookup"><span data-stu-id="06674-142">For the Feature update tests, we test against the **<ins>bi-annual pre-release feature updates</ins>** which introduces new features and capabilities on Windows.</span></span>

## <a name="debugging-options"></a><span data-ttu-id="06674-143">Felsökningsalternativ</span><span class="sxs-lookup"><span data-stu-id="06674-143">Debugging options</span></span>

<span data-ttu-id="06674-144">**F: Får vi tillgång till virtuella maskiner vid fel? Vad delar Testbas?**</span><span class="sxs-lookup"><span data-stu-id="06674-144">**Q: Do we get access to the Virtual Machines (VMs) in case of failures? What does Test Base share?**</span></span>

<span data-ttu-id="06674-145">**S:** För att tjänsten ska vara kompatibel och förhandsuppdateringarna är säkra är det bara Microsoft som har åtkomst till de virtuella maskinerna.</span><span class="sxs-lookup"><span data-stu-id="06674-145">**A:** For the service to be compliant and the pre-release updates be secure, only Microsoft has access to the VMs.</span></span> <span data-ttu-id="06674-146">Kunderna kan dock visa testresultat och andra testmått på portalens instrumentpanel, inklusive krasch- och hang-signaler, tillförlitlighetsmått, minnes- och cpu-användning osv. Vi skapar och tillhandahåller även loggar av test som körs på instrumentpanelen för nedladdning och vidare analys.</span><span class="sxs-lookup"><span data-stu-id="06674-146">However, customers can view test results and other test metrics on their portal dashboard, including crash and hang signals, reliability metrics, memory and CPU utilization etc. We also generate and provide logs of test runs on the dashboard for download and further analysis.</span></span> 

<span data-ttu-id="06674-147">Vi kan också lägga till minnesdumpor för felsökning av kraschar vid behov.</span><span class="sxs-lookup"><span data-stu-id="06674-147">We can also provide memory dumps for crash debugging as needed.</span></span>

<span data-ttu-id="06674-148">**F: Om det finns problem under testningen, vilka är nästa steg för att lösa problemen?**</span><span class="sxs-lookup"><span data-stu-id="06674-148">**Q: If there are issues found during the testing, what are the next steps to resolve these issues?**</span></span>

<span data-ttu-id="06674-149">**S:** Test Base-teamet utför en inledande triageprocess för att fastställa orsaken till felet, och sedan, beroende på våra resultat, kommer vi att dirigeras till kunden eller interna team i Microsoft för felsökning.</span><span class="sxs-lookup"><span data-stu-id="06674-149">**A:** The Test Base team will perform an initial triage process to determine the root cause of the error, and then depending on our findings, we will route to the customer or internal teams within Microsoft for debugging.</span></span> 

<span data-ttu-id="06674-150">Vi samarbetar alltid tillsammans med våra kunder för att lösa eventuella problem.</span><span class="sxs-lookup"><span data-stu-id="06674-150">We always work closely with our customers in joint remediation to resolve any issues.</span></span> 

<span data-ttu-id="06674-151">**F: Håller Microsoft kvar utgivningen av säkerhetskorrigeringen tills problemet är löst? Vilka alternativa upplösningar finns tillgängliga?**</span><span class="sxs-lookup"><span data-stu-id="06674-151">**Q: Does Microsoft hold the release of the security patch until the issue is resolved? What alternate resolutions are available?**</span></span>

<span data-ttu-id="06674-152">**S:** Syftet med Test Base är att säkerställa att våra kunder inte har några problem.</span><span class="sxs-lookup"><span data-stu-id="06674-152">**A:** The goal of Test Base is to ensure our joint end customers do not face any issues.</span></span> <span data-ttu-id="06674-153">Vi arbetar hårt med programvaruleverantörer för att lösa eventuella problem före versionen, men om korrigeringen inte är möjlig har vi andra lösningar, till exempel shims och block.</span><span class="sxs-lookup"><span data-stu-id="06674-153">We will work hard with Software Vendors to address any issues before the release, but in case the fix is not feasible we have other resolutions such as shims and blocks.</span></span>

## <a name="miscellaneous"></a><span data-ttu-id="06674-154">Diverse</span><span class="sxs-lookup"><span data-stu-id="06674-154">Miscellaneous</span></span>

<span data-ttu-id="06674-155">**F: Hur fungerar tjänsten med en on-prem-server?**</span><span class="sxs-lookup"><span data-stu-id="06674-155">**Q: How will the service work with an on-prem server?**</span></span>

<span data-ttu-id="06674-156">**S:** Vi tillhandahåller för närvarande inte stöd för on-prem-servrar.</span><span class="sxs-lookup"><span data-stu-id="06674-156">**A:** We currently do not provide support for on-prem servers.</span></span> <span data-ttu-id="06674-157">Men om servern visar HTTP-slutpunkten kan vi ansluta till den via Internet.</span><span class="sxs-lookup"><span data-stu-id="06674-157">However, if the server is exposing HTTP endpoint, we can connect to it over the internet.</span></span>

<span data-ttu-id="06674-158">**F: Vem värd för virtuella maskinerna?**</span><span class="sxs-lookup"><span data-stu-id="06674-158">**Q: Who hosts the VMs?**</span></span>

<span data-ttu-id="06674-159">**S:** Microsoft tillhandahåller den virtuella maskinerna för den här tjänsten och tar i så fall hand om detta från kunden.</span><span class="sxs-lookup"><span data-stu-id="06674-159">**A:** Microsoft provisions the VM for this service, taking the load of doing so from the customer.</span></span>

<span data-ttu-id="06674-160">**F: Stöder den här tjänsten webb-, mobil- eller skrivbordsappar?**</span><span class="sxs-lookup"><span data-stu-id="06674-160">**Q: Does this service support web, mobile, or desktop applications?**</span></span>

<span data-ttu-id="06674-161">**S:** För närvarande fokuserar vi på skrivbordsprogram, men vi planerar att introducera webbappar i framtiden, men vi stöder inte mobila program för närvarande.</span><span class="sxs-lookup"><span data-stu-id="06674-161">**A:** Currently, our focus is on desktop applications, however, we have plans to onboard web applications in the future, but we do not support mobile applications at this time.</span></span>

<span data-ttu-id="06674-162">**F: Vad är skillnaden mellan Testbas och TIDP?**</span><span class="sxs-lookup"><span data-stu-id="06674-162">**Q: What is the difference between Test Base and SUVP?**</span></span>

<span data-ttu-id="06674-163">**S:** Den största skillnaden mellan TestBas och SÅP är att våra partner för in deras program på Test base Azure-miljön för validering körs mot förhandsuppdateringar i stället för att själva utföra testerna.</span><span class="sxs-lookup"><span data-stu-id="06674-163">**A:** The biggest difference between Test Base and SUVP is that our partners onboard their applications onto the Test Base Azure environment for validation runs against pre-release updates instead of carrying out the tests themselves.</span></span> 

<span data-ttu-id="06674-164">Förutom förhandstestning av säkerhetsuppdateringar har vi stöd för förhandsuppdateringar av funktionsuppdateringar på vår plattform.</span><span class="sxs-lookup"><span data-stu-id="06674-164">In addition to pre-release security updates testing, we support pre-release feature updates testing on our platform.</span></span> <span data-ttu-id="06674-165">Vi har många andra typer av uppdateringar och OS-tester på vår översikt.</span><span class="sxs-lookup"><span data-stu-id="06674-165">We have many other types of updates and OS testing on our roadmap.</span></span>

<span data-ttu-id="06674-166">**F: Är det någon kostnad kopplad till tjänsten?**</span><span class="sxs-lookup"><span data-stu-id="06674-166">**Q: Is there a cost associated with the service?**</span></span>

<span data-ttu-id="06674-167">**S:** Testbastjänsten kommer att vara tillgänglig för användarna fram till den allmänna tillgängligheten (GA).</span><span class="sxs-lookup"><span data-stu-id="06674-167">**A:** The Test Base service will be free to users until General Availability (GA).</span></span> <span data-ttu-id="06674-168">Då kommer vi att presentera en kostnadsstruktur som ska gälla för alla kunder.</span><span class="sxs-lookup"><span data-stu-id="06674-168">At that time, we will announce a cost structure that will be in effect for all customers.</span></span> 

<span data-ttu-id="06674-169">**F: Hur kan jag ge feedback om Test Base?**</span><span class="sxs-lookup"><span data-stu-id="06674-169">**Q: How can I provide feedback about Test Base?**</span></span>

<span data-ttu-id="06674-170">**S:** Om du vill dela med dig av din feedback om Test Base väljer **du feedbackikonen** längst ned till vänster i portalen.</span><span class="sxs-lookup"><span data-stu-id="06674-170">**A:** To share your feedback about Test Base, select the **Feedback** icon at the bottom left of the portal.</span></span> <span data-ttu-id="06674-171">Ta med en skärmbild i ditt inskickade material så att Microsoft förstår din feedback bättre.</span><span class="sxs-lookup"><span data-stu-id="06674-171">Include a screenshot with your submission to help Microsoft better understand your feedback.</span></span> 

<span data-ttu-id="06674-172">Du kan också skicka produktförslag och hålla med andra idéer på <testbasepreview@microsoft.com> .</span><span class="sxs-lookup"><span data-stu-id="06674-172">You can also submit product suggestions and upvote other ideas at <testbasepreview@microsoft.com>.</span></span>
