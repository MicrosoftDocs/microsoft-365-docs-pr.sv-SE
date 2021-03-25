---
title: Konfigurera Microsoft 365 Defender-pelarna för testlabb eller pilotmiljö
description: Konfigurera Microsoft 365 Defender-pelare, till exempel Microsoft Defender för Office 365, Microsoft Defender för identitet, Microsoft Cloud App Security och Microsoft Defender för Slutpunkt, för din testlabb- eller pilotmiljö.
keywords: konfigurera utvärderingsversion av Microsoft Threat Protection, utvärderingsversion av Microsoft Threat Protection, konfigurera Microsoft Threat Protection-pilotprojekt, konfigurera Microsoft Threat Protection-pelarna, Microsoft Threat Protection-pelarna
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 8bb80e032fd2eb4c618b60f4ab46829d5cf11b6d
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199235"
---
# <a name="configure-microsoft-365-defender-pillars-for-your-trial-lab-or-pilot-environment"></a><span data-ttu-id="8b306-104">Konfigurera Microsoft 365 Defender-pelarna för din testlabb- eller pilotmiljö</span><span class="sxs-lookup"><span data-stu-id="8b306-104">Configure Microsoft 365 Defender pillars for your trial lab or pilot environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="8b306-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="8b306-105">**Applies to:**</span></span>
- <span data-ttu-id="8b306-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8b306-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="8b306-107">Det är en process i tre steg att skapa en provlabb eller pilotmiljö med Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="8b306-107">Creating a Microsoft 365 Defender trial lab or pilot environment and deploying it is a three-phase process:</span></span>

|<span data-ttu-id="8b306-108">[![Fas 1: Förbereda](../../media/phase-diagrams/prepare.png)](prepare-m365d-eval.md)</span><span class="sxs-lookup"><span data-stu-id="8b306-108">[![Phase 1: Prepare](../../media/phase-diagrams/prepare.png)](prepare-m365d-eval.md)</span></span><br/>[<span data-ttu-id="8b306-109">Fas 1: Förbereda</span><span class="sxs-lookup"><span data-stu-id="8b306-109">Phase 1: Prepare</span></span>](prepare-m365d-eval.md) |<span data-ttu-id="8b306-110">[![Fas 2: Konfigurera](../../media/phase-diagrams/setup.png)](setup-m365deval.md)</span><span class="sxs-lookup"><span data-stu-id="8b306-110">[![Phase 2: Set up](../../media/phase-diagrams/setup.png)](setup-m365deval.md)</span></span><br/>[<span data-ttu-id="8b306-111">Fas 2: Konfigurera</span><span class="sxs-lookup"><span data-stu-id="8b306-111">Phase 2: Set up</span></span>](setup-m365deval.md) |![Fas 3: Introduktion](../../media/phase-diagrams/onboard.png)<br/><span data-ttu-id="8b306-113">Fas 3: Introduktion</span><span class="sxs-lookup"><span data-stu-id="8b306-113">Phase 3: Onboard</span></span> | <span data-ttu-id="8b306-114">[![Tillbaka till pilottestning](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="8b306-114">[![Back to pilot](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)</span></span><br/>[<span data-ttu-id="8b306-115">Tillbaka till pilotspelboken</span><span class="sxs-lookup"><span data-stu-id="8b306-115">Back to pilot playbook</span></span>](m365d-pilot.md) |
|--|--|--|--|
|| |<span data-ttu-id="8b306-116">*Du är här!*</span><span class="sxs-lookup"><span data-stu-id="8b306-116">*You are here!*</span></span> | |

<span data-ttu-id="8b306-117">Du befinner dig för närvarande i konfigurationsfasen.</span><span class="sxs-lookup"><span data-stu-id="8b306-117">You're currently in the configuration phase.</span></span>

<span data-ttu-id="8b306-118">Förberedelse är avgörande för en lyckad distribution.</span><span class="sxs-lookup"><span data-stu-id="8b306-118">Preparation is key to any successful deployment.</span></span> <span data-ttu-id="8b306-119">I den här artikeln får du vägledning i de punkter du behöver tänka på när du förbereder distributionen av Microsoft Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="8b306-119">In this article, you'll be guided on the points you'll need to consider as you prepare to deploy Microsoft Defender for Endpoint.</span></span>


## <a name="microsoft-365-defender-pillars"></a><span data-ttu-id="8b306-120">Microsoft 365 Defender-pelarpelare</span><span class="sxs-lookup"><span data-stu-id="8b306-120">Microsoft 365 Defender pillars</span></span>
<span data-ttu-id="8b306-121">Microsoft 365 Defender består av fyra pelar.</span><span class="sxs-lookup"><span data-stu-id="8b306-121">Microsoft 365 Defender consists of four pillars.</span></span> <span data-ttu-id="8b306-122">Även om en av de här pelarna redan kan ge värde åt nätverksorganisationens säkerhet ger det din organisation störst värde genom att aktivera de fyra Microsoft 365 Defender-pelarna.</span><span class="sxs-lookup"><span data-stu-id="8b306-122">Although one pillar can already provide value to your network organization's security, enabling the four Microsoft 365 Defender pillars will give your organization the most value.</span></span>

![Bild of_Microsoft 365 Defender-lösning för användare, Microsoft Defender för identitet, för slutpunkter Microsoft Defender för Slutpunkt, för molnappar, Microsoft Cloud App Security och för data, Microsoft Defender för Office 365](../../media/mtp/m365pillars.png)

<span data-ttu-id="8b306-124">I det här avsnittet får du veta hur du konfigurerar:</span><span class="sxs-lookup"><span data-stu-id="8b306-124">This section will guide you to configure:</span></span>
-   <span data-ttu-id="8b306-125">Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="8b306-125">Microsoft Defender for Office 365</span></span>
-   <span data-ttu-id="8b306-126">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="8b306-126">Microsoft Defender for Identity</span></span> 
-   <span data-ttu-id="8b306-127">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="8b306-127">Microsoft Cloud App Security</span></span>
-   <span data-ttu-id="8b306-128">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="8b306-128">Microsoft Defender for Endpoint</span></span>


## <a name="configure-microsoft-defender-for-office-365"></a><span data-ttu-id="8b306-129">Konfigurera Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="8b306-129">Configure Microsoft Defender for Office 365</span></span>

>[!NOTE]
><span data-ttu-id="8b306-130">Hoppa över det här steget om du redan har aktiverat Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="8b306-130">Skip this step if you've already enabled Defender for Office 365.</span></span> 

<span data-ttu-id="8b306-131">Det finns en PowerShell-modul som kallas *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* som hjälper dig att avgöra vissa av de här inställningarna.</span><span class="sxs-lookup"><span data-stu-id="8b306-131">There's a PowerShell Module called the *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* that helps determine some of these settings.</span></span> <span data-ttu-id="8b306-132">När du kör som administratör i klientorganisationen får du en utvärdering av anti-spam, anti-phish och andra inställningar för att bli kontaktad av ett meddelande.</span><span class="sxs-lookup"><span data-stu-id="8b306-132">When run as an administrator in your tenant, get-ORCAReport will help generate an assessment of the anti-spam, anti-phish, and other message hygiene settings.</span></span> <span data-ttu-id="8b306-133">Du kan hämta den här modulen från https://www.powershellgallery.com/packages/ORCA/ .</span><span class="sxs-lookup"><span data-stu-id="8b306-133">You can download this module from https://www.powershellgallery.com/packages/ORCA/.</span></span> 

1. <span data-ttu-id="8b306-134">Gå till [Office 365 Security & Compliance Center](https://protection.office.com/homepage)Threat  >  **Management**  >  **Policy**.</span><span class="sxs-lookup"><span data-stu-id="8b306-134">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Policy**.</span></span>

   ![Image of_Office 365 Security & Compliance Center Threat Management Policy page](../../media/mtp-eval-32.png)
 
2. <span data-ttu-id="8b306-136">Klicka **på Skydd mot nätfiske** och **välj** Skapa och fyll i principens namn och beskrivning.</span><span class="sxs-lookup"><span data-stu-id="8b306-136">Click **Anti-phishing**, select **Create** and fill in the policy name and description.</span></span> <span data-ttu-id="8b306-137">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="8b306-137">Click **Next**.</span></span>

   ![Bild of_Office 365 Security & Compliance Center – skydd mot nätfiske-policy där du kan namnge principen](../../media/mtp-eval-33.png)

   > [!NOTE]
   > <span data-ttu-id="8b306-139">Redigera principen för avancerad skydd mot nätfiske i Microsoft Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="8b306-139">Edit your Advanced anti-phishing policy in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="8b306-140">Ändra **avancerat tröskelvärde för nätfiske** **till 2 – Aggressivt.**</span><span class="sxs-lookup"><span data-stu-id="8b306-140">Change **Advanced Phishing Threshold** to **2 - Aggressive**.</span></span>

3. <span data-ttu-id="8b306-141">Klicka på **listrutan Lägg** till ett villkor och välj dina domäner som mottagardomän.</span><span class="sxs-lookup"><span data-stu-id="8b306-141">Click the **Add a condition** drop-down menu and select your domain(s) as recipient domain.</span></span> <span data-ttu-id="8b306-142">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="8b306-142">Click **Next**.</span></span>

   ![Bild of_Office 365 Säkerhetscenter & policysida mot nätfiske där du kan lägga till ett villkor för programmet](../../media/mtp-eval-34.png)
 
4. <span data-ttu-id="8b306-144">Granska inställningarna.</span><span class="sxs-lookup"><span data-stu-id="8b306-144">Review your settings.</span></span> <span data-ttu-id="8b306-145">Klicka **på Skapa den här principen för** att bekräfta.</span><span class="sxs-lookup"><span data-stu-id="8b306-145">Click **Create this policy** to confirm.</span></span> 

   ![Bild of_Office 365 Säkerhet & sidan Skydd mot nätfiskeprincip i Säkerhetscenter där du kan granska dina inställningar och klicka på knappen Skapa den här principen](../../media/mtp-eval-35.png)
 
5. <span data-ttu-id="8b306-147">Välj **Säkra bifogade** filer och välj alternativet Aktivera **ATP för SharePoint, OneDrive och Microsoft Teams.**</span><span class="sxs-lookup"><span data-stu-id="8b306-147">Select **Safe Attachments** and select the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** option.</span></span>

   ![Bild of_Office 365 Säkerhets- & Efterlevnadscenter där du kan aktivera ATP för SharePoint, OneDrive och Microsoft Teams](../../media/mtp-eval-36.png)

6. <span data-ttu-id="8b306-149">Klicka på +-ikonen för att skapa en ny princip för säkra bifogade filer, använd den som mottagardomän för domänerna.</span><span class="sxs-lookup"><span data-stu-id="8b306-149">Click the + icon to create a new safe attachment policy, apply it as recipient domain to your domains.</span></span> <span data-ttu-id="8b306-150">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="8b306-150">Click **Save**.</span></span>

   ![Bild of_Office 365 Säkerhets- & Efterlevnadscenter där du kan skapa en ny princip för säkra bifogade filer](../../media/mtp-eval-37.png)
 
7. <span data-ttu-id="8b306-152">Välj sedan principen För **säkra länkar** och klicka sedan på pennikonen för att redigera standardprincipen.</span><span class="sxs-lookup"><span data-stu-id="8b306-152">Next, select the **Safe Links** policy, then click the pencil icon to edit the default policy.</span></span>

8. <span data-ttu-id="8b306-153">Kontrollera att alternativet **Spåra inte när användare klickar** på säkra länkar inte är markerat, medan resten av alternativen är markerade.</span><span class="sxs-lookup"><span data-stu-id="8b306-153">Make sure that the **Do not track when users click safe links** option is not selected, while the rest of the options are selected.</span></span> <span data-ttu-id="8b306-154">Mer [information finns i Inställningarna](/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365) för säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="8b306-154">See [Safe Links settings](/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365) for details.</span></span> <span data-ttu-id="8b306-155">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="8b306-155">Click **Save**.</span></span> 

   ![Bild of_Office 365 Säkerhets- & Säkerhetscenter som visar att alternativet Spåra inte när användare klickar på Kassaskåp inte är markerat](../../media/mtp-eval-38.png)

9. <span data-ttu-id="8b306-157">Välj sedan **standardprincipen** för skadlig programvara och pennikonen.</span><span class="sxs-lookup"><span data-stu-id="8b306-157">Next select the **Anti-malware** policy, select the default, and choose the pencil icon.</span></span>

10. <span data-ttu-id="8b306-158">Klicka **på Inställningar** och välj Ja och använd **standardmeddelandetexten för** att aktivera svar för identifiering av skadlig **programvara.**</span><span class="sxs-lookup"><span data-stu-id="8b306-158">Click **Settings** and select **Yes and use the default notification text** to enable **Malware Detection Response**.</span></span> <span data-ttu-id="8b306-159">Aktivera filtret **Vanliga typer av bifogade filer.**</span><span class="sxs-lookup"><span data-stu-id="8b306-159">Turn the **Common Attachment Types Filter** on.</span></span> <span data-ttu-id="8b306-160">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="8b306-160">Click **Save**.</span></span>

    ![Bild of_Office 365 Säkerhet och efterlevnadscenter & som visar att svaret för identifiering av skadlig programvara är aktiverat med standardmeddelande och att filtret för vanliga bifogade filer är aktiverat](../../media/mtp-eval-39.png)
  
11. <span data-ttu-id="8b306-162">Gå till [Office 365-& granskningsloggsökning](https://protection.office.com/homepage)för efterlevnadscenter  >    >   och aktivera granskning.</span><span class="sxs-lookup"><span data-stu-id="8b306-162">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Search** > **Audit log search** and turn Auditing on.</span></span>

    ![Bild of_Office 365 säkerhets- & efterlevnadscenter där du kan aktivera granskningsloggsökning](../../media/mtp-eval-40.png)

12. <span data-ttu-id="8b306-164">Integrera Microsoft Defender för Office 365 med Microsoft Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="8b306-164">Integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="8b306-165">Gå till [Office 365 Security & Compliance Center Threat](https://protection.office.com/homepage)Management Explorer och välj Microsoft Defender för Slutpunktsinställningar i det övre  >    >   högra hörnet av skärmen. </span><span class="sxs-lookup"><span data-stu-id="8b306-165">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Explorer** and select **Microsoft Defender for Endpoint Settings** on the upper right corner of the screen.</span></span> <span data-ttu-id="8b306-166">I dialogrutan Defender för slutpunktsanslutning aktiverar du **Anslut till Microsoft Defender för Slutpunkt.**</span><span class="sxs-lookup"><span data-stu-id="8b306-166">In the Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span>

    ![Bild of_Office 365 Säkerhets- & Efterlevnadscenter där du kan aktivera Microsoft Defender för slutpunktsanslutning](../../media/mtp-eval-41.png)

## <a name="configure-microsoft-defender-for-identity"></a><span data-ttu-id="8b306-168">Konfigurera Microsoft Defender för identitet</span><span class="sxs-lookup"><span data-stu-id="8b306-168">Configure Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="8b306-169">Hoppa över det här steget om du redan har aktiverat Microsoft Defender för identitet</span><span class="sxs-lookup"><span data-stu-id="8b306-169">Skip this step if you've already enabled Microsoft Defender for Identity</span></span>

1. <span data-ttu-id="8b306-170">Gå till [Säkerhetscenter för Microsoft 365 >](https://security.microsoft.com/info) **välja Fler resurser** Microsoft Defender för  >  **identitet.**</span><span class="sxs-lookup"><span data-stu-id="8b306-170">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > select **More Resources** > **Microsoft Defender for Identity**.</span></span>

   ![Bild of_Microsoft 365 Säkerhetscenter där det finns ett alternativ för att öppna Microsoft Defender för identitet](../../media/mtp-eval-42.png)

2. <span data-ttu-id="8b306-172">Klicka **på Skapa** för att starta guiden Microsoft Defender för identitet.</span><span class="sxs-lookup"><span data-stu-id="8b306-172">Click **Create** to start the Microsoft Defender for Identity wizard.</span></span> 

   ![Bild of_Microsoft sida i guiden Defender för identitet där du ska klicka på knappen Skapa](../../media/mtp-eval-43.png)

3. <span data-ttu-id="8b306-174">Välj **Ange ett användarnamn och lösenord för att ansluta till Active Directory-skogen**.</span><span class="sxs-lookup"><span data-stu-id="8b306-174">Choose **Provide a username and password to connect to your Active Directory forest**.</span></span>  

   ![Bild of_Microsoft välkomstsidan för Defender för identitet](../../media/mtp-eval-44.png)

4. <span data-ttu-id="8b306-176">Ange lokala autentiseringsuppgifter för Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8b306-176">Enter your Active Directory on-premises credentials.</span></span> <span data-ttu-id="8b306-177">Det kan vara alla användarkonton som har läsbehörighet till Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8b306-177">This can be any user account that has read access to Active Directory.</span></span>

   ![Bild of_Microsoft för sidan Tjänster i Identitetskatalogen där du bör lägga till dina autentiseringsuppgifter](../../media/mtp-eval-45.png)

5. <span data-ttu-id="8b306-179">Välj sedan Ladda **ned sensorinstallation och** överför filen till domänkontrollanten.</span><span class="sxs-lookup"><span data-stu-id="8b306-179">Next, choose **Download Sensor Setup** and transfer file to your domain controller.</span></span>

   ![Bild of_Microsoft Defender för identitetssida där du kan välja Hämtnings sensorinställning](../../media/mtp-eval-46.png)

6. <span data-ttu-id="8b306-181">Kör Microsoft Defender för konfiguration av identitets sensor och börja följa guiden.</span><span class="sxs-lookup"><span data-stu-id="8b306-181">Execute the Microsoft Defender for Identity Sensor Setup and begin following the wizard.</span></span>

   ![Bild of_Microsoft Defender för identitetssida där du ska klicka på nästa för att följa guiden Microsoft Defender för identitets sensor](../../media/mtp-eval-47.png)
 
7. <span data-ttu-id="8b306-183">Klicka **på** Nästa vid sensordistributionstypen.</span><span class="sxs-lookup"><span data-stu-id="8b306-183">Click **Next** at the sensor deployment type.</span></span>

   ![Bild of_Microsoft Defender för identitetssida där du ska klicka på Nästa för att gå till nästa sida](../../media/mtp-eval-48.png)
 
8. <span data-ttu-id="8b306-185">Kopiera snabbtangenten eftersom du måste ange den nästa i guiden.</span><span class="sxs-lookup"><span data-stu-id="8b306-185">Copy the access key because you need to enter it next in the Wizard.</span></span>

   ![Bild of_the sensorsidan där du bör kopiera snabbtangenten som du behöver ange på nästa sida i Microsoft Defender för installationsguiden för identitetssensorer](../../media/mtp-eval-49.png)
 
9. <span data-ttu-id="8b306-187">Kopiera in snabbtangenten i guiden och klicka på **Installera**.</span><span class="sxs-lookup"><span data-stu-id="8b306-187">Copy the access key into the Wizard and click **Install**.</span></span> 

   ![Bild of_Microsoft sidan för guiden Defender för identitets sensor, där du bör ange snabbtangenten och klicka sedan på installationsknappen](../../media/mtp-eval-50.png)

10. <span data-ttu-id="8b306-189">Grattis! Du har konfigurerat Microsoft Defender för identitet på domänkontrollanten.</span><span class="sxs-lookup"><span data-stu-id="8b306-189">Congratulations, you've successfully configured Microsoft Defender for Identity on your domain controller.</span></span>

    ![Bild of_Microsoft defender för komplettering av identitets sensorguiden, där du ska klicka på knappen Slutför](../../media/mtp-eval-51.png)
 
11. <span data-ttu-id="8b306-191">Under avsnittet [Microsoft Defender för identitetsinställningar](https://go.microsoft.com/fwlink/?linkid=2040449) väljer du \*\*Microsoft Defender för slutpunkt \*\*. Aktivera sedan växlingsknappen.</span><span class="sxs-lookup"><span data-stu-id="8b306-191">Under the [Microsoft Defender for Identity](https://go.microsoft.com/fwlink/?linkid=2040449) settings section, select \*\*Microsoft Defender for Endpoint \*\*, then turn on the toggle.</span></span> <span data-ttu-id="8b306-192">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="8b306-192">Click **Save**.</span></span> 

    ![Bild of_the microsoft Defender för identitetsinställningar, där du ska aktivera växlingsknappen Microsoft Defender för slutpunkt](../../media/mtp-eval-52.png)

> [!NOTE]
> <span data-ttu-id="8b306-194">Windows Defender ATP har rebranderats som Microsoft Defender för Endpoint.</span><span class="sxs-lookup"><span data-stu-id="8b306-194">Windows Defender ATP has been rebranded as Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="8b306-195">Ändringar som rebranderas i alla våra portaler distribueras för att skapa konsekvens.</span><span class="sxs-lookup"><span data-stu-id="8b306-195">Rebranding changes across all of our portals are being rolled out the for consistency.</span></span>


## <a name="configure-microsoft-cloud-app-security"></a><span data-ttu-id="8b306-196">Konfigurera Microsoft Cloud App-säkerhet</span><span class="sxs-lookup"><span data-stu-id="8b306-196">Configure Microsoft Cloud App Security</span></span>

> [!NOTE]
> <span data-ttu-id="8b306-197">Hoppa över det här steget om du redan har aktiverat Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="8b306-197">Skip this step if you've already enabled Microsoft Cloud App Security.</span></span> 

1. <span data-ttu-id="8b306-198">Gå till [Microsoft 365 Säkerhetscenter](https://security.microsoft.com/info)  >  **Fler resurser Microsoft** Cloud App  >  **Security**.</span><span class="sxs-lookup"><span data-stu-id="8b306-198">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Cloud App Security**.</span></span>

   ![Bild of_Microsoft 365 Säkerhetscenter där du kan se kortet Microsoft Cloud App och ska klicka på öppna-knappen](../../media/mtp-eval-53.png)

2. <span data-ttu-id="8b306-200">När du uppmanas att integrera Microsoft Defender för identitet markerar du **Aktivera Microsoft Defender för identitetsdataintegrering.**</span><span class="sxs-lookup"><span data-stu-id="8b306-200">At the information prompt to integrate Microsoft Defender for Identity, select **Enable Microsoft Defender for Identity data integration**.</span></span>
  
   ![Bild of_the informationsfråga om att integrera Microsoft Defender för identitet, där du bör välja länken Aktivera Microsoft Defender för identitetsdataintegrering](../../media/mtp-eval-54.png)

   > [!NOTE]
   > <span data-ttu-id="8b306-202">Om du inte ser det här alternativet kan det innebära att microsoft Defender för identitetsdataintegrering redan har aktiverats.</span><span class="sxs-lookup"><span data-stu-id="8b306-202">If you don’t see this prompt, it might mean that your Microsoft Defender for Identity data integration has already been enabled.</span></span> <span data-ttu-id="8b306-203">Om du är osäker kan du kontakta IT-administratören för att bekräfta.</span><span class="sxs-lookup"><span data-stu-id="8b306-203">However, if you are not sure, contact your IT Administrator to confirm.</span></span> 

3. <span data-ttu-id="8b306-204">Gå till **Inställningar**, aktivera växlingsknappen **Microsoft Defender för** identitetsintegrering och klicka sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="8b306-204">Go to **Settings**, turn on the **Microsoft Defender for Identity integration** toggle, then click **Save**.</span></span> 

   ![Bild of_the inställningar där du ska aktivera växlingsknappen För identitetsintegrering i Microsoft Defender och sedan klicka på Spara](../../media/mtp-eval-55.png)
   
   > [!NOTE]
   > <span data-ttu-id="8b306-206">För nya microsoft Defender för identitetsinstanser är växlingsknappen för den här integreringen aktiverad automatiskt.</span><span class="sxs-lookup"><span data-stu-id="8b306-206">For new Microsoft Defender for Identity instances, this integration toggle is automatically turned on.</span></span> <span data-ttu-id="8b306-207">Bekräfta att Microsoft Defender för identitetsintegrering har aktiverats innan du går vidare till nästa steg.</span><span class="sxs-lookup"><span data-stu-id="8b306-207">Confirm that your Microsoft Defender for Identity integration has been enabled before you proceed to the next step.</span></span>
 
4. <span data-ttu-id="8b306-208">Under inställningarna för molnidentifiering väljer du **Microsoft Defender för Slutpunktsintegrering** och aktiverar sedan integreringen.</span><span class="sxs-lookup"><span data-stu-id="8b306-208">Under the Cloud discovery settings, select **Microsoft Defender for Endpoint integration**, then enable the integration.</span></span> <span data-ttu-id="8b306-209">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="8b306-209">Click **Save**.</span></span>

   ![Bild of_the på sidan Microsoft Defender för slutpunkt där kryssrutan blockera osanerade appar under Microsoft Defender för slutpunktsintegrering är markerad.](../../media/mtp-eval-56.png)

5. <span data-ttu-id="8b306-212">Under Inställningar för molnidentifiering **väljer du Användarberikning** och aktiverar sedan integreringen med Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8b306-212">Under Cloud discovery settings, select **User enrichment**, then enable the integration with Azure Active Directory.</span></span>

   ![Bild av avsnittet användarberikning där kryssrutan identifierad användaridentifierare med Azure Active Directory-användarnamn är markerad](../../media/mtp-eval-57.png)


## <a name="configure-microsoft-defender-for-endpoint"></a><span data-ttu-id="8b306-214">Konfigurera Microsoft Defender för slutpunkt</span><span class="sxs-lookup"><span data-stu-id="8b306-214">Configure Microsoft Defender for Endpoint</span></span>

>[!NOTE]
><span data-ttu-id="8b306-215">Hoppa över det här steget om du redan har aktiverat Microsoft Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="8b306-215">Skip this step if you've already enabled Microsoft Defender for Endpoint.</span></span>

1. <span data-ttu-id="8b306-216">Gå till [Microsoft 365 Säkerhetscenter](https://security.microsoft.com/info)  >  **Fler resurser** Microsoft Defender  >  **Säkerhetscenter**.</span><span class="sxs-lookup"><span data-stu-id="8b306-216">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Defender Security Center**.</span></span> <span data-ttu-id="8b306-217">Klicka **på Öppna**.</span><span class="sxs-lookup"><span data-stu-id="8b306-217">Click **Open**.</span></span>

   ![Bild of_Microsoft alternativ i Defender Säkerhetscenter på sidan Säkerhetscenter för Microsoft 365](../../media/mtp-eval-58.png)
 
2. <span data-ttu-id="8b306-219">Följ guiden Microsoft Defender för slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="8b306-219">Follow the Microsoft Defender for Endpoint wizard.</span></span> <span data-ttu-id="8b306-220">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="8b306-220">Click **Next**.</span></span> 

   ![Bild of_the sida i välkomstguiden för Microsoft Defender Säkerhetscenter](../../media/mtp-eval-59.png)

3. <span data-ttu-id="8b306-222">Välj baserat på önskad datalagringsplats, databevarandeprincip, organisationsstorlek och möjlighet att registrera dig för förhandsgranskningsfunktioner.</span><span class="sxs-lookup"><span data-stu-id="8b306-222">Choose based on your preferred data storage location, data retention policy, organization size, and opt-in for preview features.</span></span>

   ![Bild of_the väljer du land för datalagring, bevarandeprincip och organisationsstorlek.](../../media/mtp-eval-60.png)
   
   > [!NOTE]
   > <span data-ttu-id="8b306-225">Du kan inte ändra vissa inställningar, till exempel datalagringsplats efteråt.</span><span class="sxs-lookup"><span data-stu-id="8b306-225">You cannot change some of the settings, like data storage location, afterwards.</span></span> 

   <span data-ttu-id="8b306-226">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="8b306-226">Click **Next**.</span></span> 

4. <span data-ttu-id="8b306-227">Klicka **på Fortsätt** så etableras microsoft Defender för slutpunktsklientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="8b306-227">Click **Continue** and it will provision your Microsoft Defender for Endpoint tenant.</span></span>

   ![Bild of_the sida som uppmanar dig att klicka på knappen Fortsätt för att skapa din molninstans](../../media/mtp-eval-61.png)

5. <span data-ttu-id="8b306-229">Få igång slutpunkterna genom grupprinciper, Microsoft Endpoint Manager eller genom att köra ett lokalt skript i Microsoft Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="8b306-229">Onboard your endpoints through Group Policies, Microsoft Endpoint Manager or by running a local script to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="8b306-230">För enkelhetens skull använder den här guiden det lokala skriptet.</span><span class="sxs-lookup"><span data-stu-id="8b306-230">For simplicity, this guide uses the local script.</span></span>

6. <span data-ttu-id="8b306-231">Klicka **på Ladda ned** paket och kopiera introduktionsskriptet till slutpunkterna.</span><span class="sxs-lookup"><span data-stu-id="8b306-231">Click **Download package** and copy the onboarding script to your endpoint(s).</span></span>

   ![Bild of_page du uppmanas att klicka på knappen Ladda ned paket för att kopiera onboarding-skriptet till slutpunkten eller slutpunkterna](../../media/mtp-eval-62.png)

7. <span data-ttu-id="8b306-233">Kör onboarding-skriptet som administratör på slutpunkten och välj Y.</span><span class="sxs-lookup"><span data-stu-id="8b306-233">On your endpoint, run the onboarding script as Administrator and choose Y.</span></span> 

   ![Bild of_the här du kör onboarding-skriptet och väljer Y för att fortsätta](../../media/mtp-eval-63.png)

8. <span data-ttu-id="8b306-235">Grattis! Du har introducerat din första slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="8b306-235">Congratulations, you've onboarded your first endpoint.</span></span>

   ![Bild of_the här kommandotolken där du får bekräftelse på att du har introducerat din första slutpunkt.](../../media/mtp-eval-64.png)

9. <span data-ttu-id="8b306-238">Kopiera och klistra in identifieringstestet från guiden Microsoft Defender för slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="8b306-238">Copy-paste the detection test from the Microsoft Defender for Endpoint wizard.</span></span>

   ![Bild of_the köra ett teststeg för identifiering där du ska klicka på Kopiera för att kopiera det identifieringstestskript som du ska klistra in i kommandotolken](../../media/mtp-eval-65.png)

10. <span data-ttu-id="8b306-240">Kopiera PowerShell-skriptet till en upphöjd kommandotolk och kör den.</span><span class="sxs-lookup"><span data-stu-id="8b306-240">Copy the PowerShell script to an elevated command prompt and run it.</span></span> 

    ![Bild of_command fråga var du ska kopiera PowerShell-skriptet till en upphöjd kommandotolk och köra den](../../media/mtp-eval-66.png)

11. <span data-ttu-id="8b306-242">Välj **Börja använda Microsoft Defender för slutpunkt** i guiden.</span><span class="sxs-lookup"><span data-stu-id="8b306-242">Select **Start using Microsoft Defender for Endpoint** from the Wizard.</span></span>

    ![Bild of_the i guiden där du ska klicka på Börja använda Microsoft Defender för slutpunkt](../../media/mtp-eval-67.png)
 
12. <span data-ttu-id="8b306-244">Besök [Microsoft Defender Säkerhetscenter.](https://securitycenter.windows.com/)</span><span class="sxs-lookup"><span data-stu-id="8b306-244">Visit the [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span></span> <span data-ttu-id="8b306-245">Gå till **Inställningar** och välj sedan **Avancerade funktioner**.</span><span class="sxs-lookup"><span data-stu-id="8b306-245">Go to **Settings** and then select **Advanced features**.</span></span> 

    ![Bild of_Microsoft inställningsmenyn i Defender Säkerhetscenter där du bör välja Avancerade funktioner](../../media/mtp-eval-68.png)

13. <span data-ttu-id="8b306-247">Aktivera integrering med **Microsoft Defender för identitet.**</span><span class="sxs-lookup"><span data-stu-id="8b306-247">Turn on the integration with **Microsoft Defender for Identity**.</span></span>  

    ![Bild of_Microsoft av avancerade funktioner i Defender Säkerhetscenter, alternativet Microsoft Defender för identitet, omkopplare som du behöver aktivera](../../media/mtp-eval-69.png)

14. <span data-ttu-id="8b306-249">Aktivera integrering med **Office 365 Threat Intelligence.**</span><span class="sxs-lookup"><span data-stu-id="8b306-249">Turn on the integration with **Office 365 Threat Intelligence**.</span></span>

    ![Bild of_Microsoft av avancerade funktioner i Defender Säkerhetscenter, alternativ för Office 365 Threat Intelligence som du behöver aktivera](../../media/mtp-eval-70.png)

15. <span data-ttu-id="8b306-251">Aktivera integrering med **Microsoft Cloud App Security.**</span><span class="sxs-lookup"><span data-stu-id="8b306-251">Turn on integration with **Microsoft Cloud App Security**.</span></span>

    ![Bild of_Microsoft Av/på avancerade funktioner i Defender Säkerhetscenter, med alternativet Säkerhet i Microsoft Cloud App](../../media/mtp-eval-71.png)

16. <span data-ttu-id="8b306-253">Rulla nedåt och klicka **på Spara inställningar** för att bekräfta de nya integrationerna.</span><span class="sxs-lookup"><span data-stu-id="8b306-253">Scroll down and click **Save preferences** to confirm the new integrations.</span></span>

    ![Bild of_Save inställningar som du behöver klicka på](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-365-defender-service"></a><span data-ttu-id="8b306-255">Starta tjänsten Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8b306-255">Start the Microsoft 365 Defender service</span></span>

>[!NOTE]
><span data-ttu-id="8b306-256">Från och med den 1 juni 2020 aktiverar Microsoft automatiskt Microsoft 365 Defender-funktioner för alla berättigade klienter.</span><span class="sxs-lookup"><span data-stu-id="8b306-256">Starting June 1, 2020, Microsoft automatically enables Microsoft 365 Defender features for all eligible tenants.</span></span> <span data-ttu-id="8b306-257">Mer information finns [i den här Microsoft Tech Community-artikeln om licensberättigande.](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426)</span><span class="sxs-lookup"><span data-stu-id="8b306-257">See this [Microsoft Tech Community article on license eligibility](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) for details.</span></span> 


<span data-ttu-id="8b306-258">Gå till [Microsoft 365 Säkerhetscenter.](https://security.microsoft.com/homepage)</span><span class="sxs-lookup"><span data-stu-id="8b306-258">Go to [Microsoft 365 Security Center](https://security.microsoft.com/homepage).</span></span> <span data-ttu-id="8b306-259">Gå till **Inställningar** och välj sedan **Microsoft 365 Defender.**</span><span class="sxs-lookup"><span data-stu-id="8b306-259">Navigate to **Settings** and then select **Microsoft 365 Defender**.</span></span>

![<span data-ttu-id="8b306-260">Bild of_Microsoft skärmbild med alternativ för 365 Defender från sidan Inställningar för Säkerhetscenter i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8b306-260">Image of_Microsoft 365 Defender option screenshot from the Microsoft 365 Security Center Settings page</span></span> ](../../media/mtp-eval-72b.png) <br>

<span data-ttu-id="8b306-261">Mer omfattande vägledning finns i Aktivera [Microsoft 365 Defender.](m365d-enable.md)</span><span class="sxs-lookup"><span data-stu-id="8b306-261">For a more comprehensive guidance, see [Turn on Microsoft 365 Defender](m365d-enable.md).</span></span> 

<span data-ttu-id="8b306-262">Grattis!</span><span class="sxs-lookup"><span data-stu-id="8b306-262">Congratulations!</span></span> <span data-ttu-id="8b306-263">Du har just skapat din utvärderingsversionsmiljö i Microsoft 365 Defender!</span><span class="sxs-lookup"><span data-stu-id="8b306-263">You've just created your Microsoft 365 Defender trial lab or pilot environment!</span></span> <span data-ttu-id="8b306-264">Nu kan du bekanta dig med Användargränssnittet i Microsoft 365 Defender!</span><span class="sxs-lookup"><span data-stu-id="8b306-264">Now you can familiarize yourself with the Microsoft 365 Defender user interface!</span></span> <span data-ttu-id="8b306-265">Se vad du kan lära dig av följande interaktiva guide i Microsoft 365 Defender och hur du använder varje instrumentpanel för dina dagliga säkerhetsåtgärdsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="8b306-265">See what you can learn from the following Microsoft 365 Defender interactive guide and know how to use each dashboard for your day-to-day security operation tasks.</span></span>


>[!VIDEO https://aka.ms/MTP-Interactive-Guide]

<span data-ttu-id="8b306-266">Sedan kan du simulera en attack och se hur funktionerna i olika produkter identifierar, skapar aviseringar och automatiskt svarar på fillösa angrepp mot en slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="8b306-266">Next, you can simulate an attack and see how the cross product capabilities detect, create alerts, and automatically respond to a fileless attack on an endpoint.</span></span>

## <a name="next-step"></a><span data-ttu-id="8b306-267">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="8b306-267">Next step</span></span>

- <span data-ttu-id="8b306-268">[Generera en testavisering](generate-test-alert.md) – Kör en attack simulering i ditt provlabb i Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="8b306-268">[Generate a test alert](generate-test-alert.md) - Run an attack simulation in your Microsoft 365 Defender trial lab.</span></span>