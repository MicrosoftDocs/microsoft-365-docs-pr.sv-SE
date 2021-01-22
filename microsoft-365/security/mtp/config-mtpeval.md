---
title: Konfigurera Microsoft 365 Defender-pelare för testlabb eller pilotmiljö
description: Konfigurera Microsoft 365 Defender-pelare, till exempel Microsoft Defender för Office 365, Microsoft Defender för identitet, Microsoft Cloud App Security och Microsoft Defender för Endpoint, för din testlabb- eller pilotmiljö.
keywords: konfigurera utvärderingsversionen av Microsoft Threat Protection, utvärderingskonfiguration för Microsoft Threat Protection, konfigurera Microsoft Threat Protection-pilotprojektet, konfigurera Microsoft Threat Protection-pelarna, Microsoft Threat Protection-pelarna
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 78b37d9d435eabce47d360efd630c2e55cadacd1
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932244"
---
# <a name="configure-microsoft-365-defender-pillars-for-your-trial-lab-or-pilot-environment"></a><span data-ttu-id="6f4a2-104">Konfigurera Microsoft 365 Defender-pelare för ditt testlabb eller pilotmiljö</span><span class="sxs-lookup"><span data-stu-id="6f4a2-104">Configure Microsoft 365 Defender pillars for your trial lab or pilot environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6f4a2-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="6f4a2-105">**Applies to:**</span></span>
- <span data-ttu-id="6f4a2-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6f4a2-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="6f4a2-107">Att skapa ett testlabb eller pilotmiljö i Microsoft 365 Defender och distribuera den är en process i tre steg:</span><span class="sxs-lookup"><span data-stu-id="6f4a2-107">Creating a Microsoft 365 Defender trial lab or pilot environment and deploying it is a three-phase process:</span></span>

|<span data-ttu-id="6f4a2-108">[![Fas 1: Förbereda](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="6f4a2-108">[![Phase 1: Prepare](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)</span></span><br/>[<span data-ttu-id="6f4a2-109">Fas 1: Förbereda</span><span class="sxs-lookup"><span data-stu-id="6f4a2-109">Phase 1: Prepare</span></span>](prepare-mtpeval.md) |<span data-ttu-id="6f4a2-110">[![Fas 2: Konfigurera](../../media/phase-diagrams/setup.png)](setup-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="6f4a2-110">[![Phase 2: Set up](../../media/phase-diagrams/setup.png)](setup-mtpeval.md)</span></span><br/>[<span data-ttu-id="6f4a2-111">Fas 2: Konfigurera</span><span class="sxs-lookup"><span data-stu-id="6f4a2-111">Phase 2: Set up</span></span>](setup-mtpeval.md) |![Fas 3: Onboard](../../media/phase-diagrams/onboard.png)<br/><span data-ttu-id="6f4a2-113">Fas 3: Onboard</span><span class="sxs-lookup"><span data-stu-id="6f4a2-113">Phase 3: Onboard</span></span> | <span data-ttu-id="6f4a2-114">[![Tillbaka till pilottestning](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="6f4a2-114">[![Back to pilot](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)</span></span><br/>[<span data-ttu-id="6f4a2-115">Tillbaka till pilotspelboken</span><span class="sxs-lookup"><span data-stu-id="6f4a2-115">Back to pilot playbook</span></span>](mtp-pilot.md) |
|--|--|--|--|
|| |<span data-ttu-id="6f4a2-116">*Du är här!*</span><span class="sxs-lookup"><span data-stu-id="6f4a2-116">*You are here!*</span></span> | |

<span data-ttu-id="6f4a2-117">Du befinner dig för närvarande i konfigurationsfasen.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-117">You're currently in the configuration phase.</span></span>

<span data-ttu-id="6f4a2-118">Förberedelse är avgörande för en lyckad distribution.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-118">Preparation is key to any successful deployment.</span></span> <span data-ttu-id="6f4a2-119">I den här artikeln får du vägledning om de punkter du behöver tänka på när du förbereder för distribution av Microsoft Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-119">In this article, you'll be guided on the points you'll need to consider as you prepare to deploy Microsoft Defender for Endpoint.</span></span>


## <a name="microsoft-365-defender-pillars"></a><span data-ttu-id="6f4a2-120">Microsoft 365 Defender-pelare</span><span class="sxs-lookup"><span data-stu-id="6f4a2-120">Microsoft 365 Defender pillars</span></span>
<span data-ttu-id="6f4a2-121">Microsoft 365 Defender består av fyrapelare.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-121">Microsoft 365 Defender consists of four pillars.</span></span> <span data-ttu-id="6f4a2-122">Även om en av de två pelarna redan kan ge värde åt nätverksorganisationens säkerhet, ger de fyra Microsoft 365 Defender-pelarna din organisation mest värde.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-122">Although one pillar can already provide value to your network organization's security, enabling the four Microsoft 365 Defender pillars will give your organization the most value.</span></span>

![Bild of_Microsoft 365 Defender-lösning för användare, Microsoft Defender för identitet, för slutpunkter Microsoft Defender för Slutpunkt, för molnappar, Microsoft Cloud App Security och för data, Microsoft Defender för Office 365](../../media/mtp/m365pillars.png)

<span data-ttu-id="6f4a2-124">I det här avsnittet får du hjälp med att konfigurera:</span><span class="sxs-lookup"><span data-stu-id="6f4a2-124">This section will guide you to configure:</span></span>
-   <span data-ttu-id="6f4a2-125">Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="6f4a2-125">Microsoft Defender for Office 365</span></span>
-   <span data-ttu-id="6f4a2-126">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="6f4a2-126">Microsoft Defender for Identity</span></span> 
-   <span data-ttu-id="6f4a2-127">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="6f4a2-127">Microsoft Cloud App Security</span></span>
-   <span data-ttu-id="6f4a2-128">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="6f4a2-128">Microsoft Defender for Endpoint</span></span>


## <a name="configure-microsoft-defender-for-office-365"></a><span data-ttu-id="6f4a2-129">Konfigurera Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="6f4a2-129">Configure Microsoft Defender for Office 365</span></span>

>[!NOTE]
><span data-ttu-id="6f4a2-130">Hoppa över det här steget om du redan har aktiverat Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-130">Skip this step if you've already enabled Defender for Office 365.</span></span> 

<span data-ttu-id="6f4a2-131">Det finns en PowerShell-modul som kallas *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* som hjälper dig att avgöra några av de här inställningarna.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-131">There's a PowerShell Module called the *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* that helps determine some of these settings.</span></span> <span data-ttu-id="6f4a2-132">När du kör som administratör i klientorganisationen kan du använda GET-ORCAReport för att generera en utvärdering av skydd mot skräppost, nätfjädrade meddelanden och andra inställningar för att skapa meddelanden.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-132">When run as an administrator in your tenant, get-ORCAReport will help generate an assessment of the anti-spam, anti-phish, and other message hygiene settings.</span></span> <span data-ttu-id="6f4a2-133">Du kan hämta den här modulen https://www.powershellgallery.com/packages/ORCA/ från.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-133">You can download this module from https://www.powershellgallery.com/packages/ORCA/.</span></span> 

1. <span data-ttu-id="6f4a2-134">Gå till [Office 365 Security & Compliance Center](https://protection.office.com/homepage)Threat  >  **Management**  >  **Policy.**</span><span class="sxs-lookup"><span data-stu-id="6f4a2-134">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Policy**.</span></span>

   ![Image of_Office 365 Security & Compliance Center Threat Management Policy Page](../../media/mtp-eval-32.png)
 
2. <span data-ttu-id="6f4a2-136">Klicka **på Skydd mot nätfiske,** **välj** Skapa och fyll i principens namn och beskrivning.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-136">Click **Anti-phishing**, select **Create** and fill in the policy name and description.</span></span> <span data-ttu-id="6f4a2-137">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-137">Click **Next**.</span></span>

   ![Bild of_Office 365 Security & Compliance Center – sidan mot nätfiske där du kan namnge principen](../../media/mtp-eval-33.png)

   > [!NOTE]
   > <span data-ttu-id="6f4a2-139">Redigera avancerad nätfiskeprincip i Microsoft Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-139">Edit your Advanced anti-phishing policy in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="6f4a2-140">Ändra **avancerad nätfisketröskel till** **2 – Aggressiv.**</span><span class="sxs-lookup"><span data-stu-id="6f4a2-140">Change **Advanced Phishing Threshold** to **2 - Aggressive**.</span></span>

3. <span data-ttu-id="6f4a2-141">Klicka på **listrutan Lägg** till ett villkor och välj dina domäner som mottagardomän.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-141">Click the **Add a condition** drop-down menu and select your domain(s) as recipient domain.</span></span> <span data-ttu-id="6f4a2-142">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-142">Click **Next**.</span></span>

   ![Bild of_Office 365 Security & Compliance Center – skydd mot nätfiske-policy där du kan lägga till ett villkor för programmet](../../media/mtp-eval-34.png)
 
4. <span data-ttu-id="6f4a2-144">Granska inställningarna.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-144">Review your settings.</span></span> <span data-ttu-id="6f4a2-145">Klicka **på Skapa den här principen för** att bekräfta.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-145">Click **Create this policy** to confirm.</span></span> 

   ![Bild of_Office 365 Security & Compliance Center – skydd mot nätfiske-policy där du kan granska dina inställningar och klicka på knappen Skapa den här principen](../../media/mtp-eval-35.png)
 
5. <span data-ttu-id="6f4a2-147">Välj **Säkra bifogade** filer och välj Aktivera **ATP för SharePoint, OneDrive och Microsoft Teams.**</span><span class="sxs-lookup"><span data-stu-id="6f4a2-147">Select **Safe Attachments** and select the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** option.</span></span>

   ![Bild of_Office 365 Security & Compliance Center där du kan aktivera ATP för SharePoint, OneDrive och Microsoft Teams](../../media/mtp-eval-36.png)

6. <span data-ttu-id="6f4a2-149">Klicka på +-ikonen för att skapa en ny princip för säkra bifogade filer och använd den som mottagardomän för domänerna.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-149">Click the + icon to create a new safe attachment policy, apply it as recipient domain to your domains.</span></span> <span data-ttu-id="6f4a2-150">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-150">Click **Save**.</span></span>

   ![Bild of_Office 365 Säkerhets- & Efterlevnadscenter där du kan skapa en ny princip för säkra bifogade filer](../../media/mtp-eval-37.png)
 
7. <span data-ttu-id="6f4a2-152">Välj sedan principen Säkra **länkar** och klicka sedan på pennikonen för att redigera standardprincipen.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-152">Next, select the **Safe Links** policy, then click the pencil icon to edit the default policy.</span></span>

8. <span data-ttu-id="6f4a2-153">Se till att **alternativet Spåra inte när användare klickar** på säkra länkar inte är markerat, medan resten av alternativen är markerade.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-153">Make sure that the **Do not track when users click safe links** option is not selected, while the rest of the options are selected.</span></span> <span data-ttu-id="6f4a2-154">Se [inställningarna för säkra länkar](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) för mer information.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-154">See [Safe Links settings](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) for details.</span></span> <span data-ttu-id="6f4a2-155">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-155">Click **Save**.</span></span> 

   ![Bild of_Office 365 säkerhets- & Efterlevnadscenter som visar att alternativet Spåra inte när användare klickar på Säkra inte är markerat](../../media/mtp-eval-38.png)

9. <span data-ttu-id="6f4a2-157">Välj sedan **standardprincipen** för skadlig programvara och sedan pennikonen.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-157">Next select the **Anti-malware** policy, select the default, and choose the pencil icon.</span></span>

10. <span data-ttu-id="6f4a2-158">Klicka **på Inställningar** och välj Ja och använd **standardmeddelandetexten för** att aktivera svar för identifiering av skadlig **kod.**</span><span class="sxs-lookup"><span data-stu-id="6f4a2-158">Click **Settings** and select **Yes and use the default notification text** to enable **Malware Detection Response**.</span></span> <span data-ttu-id="6f4a2-159">Aktivera filtret **För vanliga bifogade filer.**</span><span class="sxs-lookup"><span data-stu-id="6f4a2-159">Turn the **Common Attachment Types Filter** on.</span></span> <span data-ttu-id="6f4a2-160">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-160">Click **Save**.</span></span>

    ![Bild of_Office 365 Säkerhets- & Efterlevnadscenter som visar att svaret för identifiering av skadlig programvara är aktiverat med standardmeddelande och att filtret för vanliga bifogade filer är aktiverat](../../media/mtp-eval-39.png)
  
11. <span data-ttu-id="6f4a2-162">Gå till [Office 365-& granskningsloggsökning](https://protection.office.com/homepage)i  >    >  **Efterlevnadscenter** och aktivera granskning.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-162">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Search** > **Audit log search** and turn Auditing on.</span></span>

    ![Bild of_Office 365 & Efterlevnadscenter där du kan aktivera granskningsloggsökning](../../media/mtp-eval-40.png)

12. <span data-ttu-id="6f4a2-164">Integrera Microsoft Defender för Office 365 med Microsoft Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-164">Integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="6f4a2-165">Gå till [Office 365 Security & Compliance Center](https://protection.office.com/homepage)Threat Management Explorer och välj Microsoft Defender för Slutpunktsinställningar i det övre högra hörnet av  >    >   skärmen. </span><span class="sxs-lookup"><span data-stu-id="6f4a2-165">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Explorer** and select **Microsoft Defender for Endpoint Settings** on the upper right corner of the screen.</span></span> <span data-ttu-id="6f4a2-166">I dialogrutan Defender för slutpunktsanslutning aktiverar du **Anslut till Microsoft Defender för Slutpunkt.**</span><span class="sxs-lookup"><span data-stu-id="6f4a2-166">In the Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span>

    ![Bild of_Office 365 & Compliance Center där du kan aktivera Microsoft Defender för slutpunktsanslutning](../../media/mtp-eval-41.png)

## <a name="configure-microsoft-defender-for-identity"></a><span data-ttu-id="6f4a2-168">Konfigurera Microsoft Defender för identitet</span><span class="sxs-lookup"><span data-stu-id="6f4a2-168">Configure Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="6f4a2-169">Hoppa över det här steget om du redan har aktiverat Microsoft Defender för identitet</span><span class="sxs-lookup"><span data-stu-id="6f4a2-169">Skip this step if you've already enabled Microsoft Defender for Identity</span></span>

1. <span data-ttu-id="6f4a2-170">Gå till [Microsoft 365 Säkerhetscenter och >](https://security.microsoft.com/info) välja Fler **resurser** Microsoft Defender  >  **för identitet.**</span><span class="sxs-lookup"><span data-stu-id="6f4a2-170">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > select **More Resources** > **Microsoft Defender for Identity**.</span></span>

   ![Bild of_Microsoft 365 Säkerhetscenter där det finns ett alternativ för att öppna Microsoft Defender för identitet](../../media/mtp-eval-42.png)

2. <span data-ttu-id="6f4a2-172">Klicka **på Skapa** för att starta guiden Microsoft Defender för identitet.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-172">Click **Create** to start the Microsoft Defender for Identity wizard.</span></span> 

   ![Bild of_Microsoft sida i guiden Defender för identitet där du ska klicka på knappen Skapa](../../media/mtp-eval-43.png)

3. <span data-ttu-id="6f4a2-174">Välj **Ange ett användarnamn och lösenord för att ansluta till Active Directory-skogen.**</span><span class="sxs-lookup"><span data-stu-id="6f4a2-174">Choose **Provide a username and password to connect to your Active Directory forest**.</span></span>  

   ![Bild of_Microsoft välkomstsida för Defender för identitet](../../media/mtp-eval-44.png)

4. <span data-ttu-id="6f4a2-176">Ange lokala autentiseringsuppgifter för Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-176">Enter your Active Directory on-premises credentials.</span></span> <span data-ttu-id="6f4a2-177">Det kan vara alla användarkonton som har läsbehörighet till Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-177">This can be any user account that has read access to Active Directory.</span></span>

   ![Bild of_Microsoft sida för tjänster i Defender för identitetskatalog där du bör lägga till dina autentiseringsuppgifter](../../media/mtp-eval-45.png)

5. <span data-ttu-id="6f4a2-179">Välj sedan Ladda **ned sensorinstallationen** och överför filen till domänkontrollanten.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-179">Next, choose **Download Sensor Setup** and transfer file to your domain controller.</span></span>

   ![Bild of_Microsoft Defender för identitet där du kan välja Konfigurera nedladdnings sensor](../../media/mtp-eval-46.png)

6. <span data-ttu-id="6f4a2-181">Kör Microsoft Defender för konfiguration av identitets sensor och börja följa guiden.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-181">Execute the Microsoft Defender for Identity Sensor Setup and begin following the wizard.</span></span>

   ![Bild of_Microsoft Defender för identitet där du ska klicka på nästa för att följa guiden Microsoft Defender för identitets sensor](../../media/mtp-eval-47.png)
 
7. <span data-ttu-id="6f4a2-183">Klicka **på Nästa** på sensordistributionstypen.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-183">Click **Next** at the sensor deployment type.</span></span>

   ![Bild of_Microsoft Defender för identitet där du ska klicka på Nästa för att gå till nästa sida](../../media/mtp-eval-48.png)
 
8. <span data-ttu-id="6f4a2-185">Kopiera snabbtangenten eftersom du måste ange den nästa i guiden.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-185">Copy the access key because you need to enter it next in the Wizard.</span></span>

   ![Bild of_the för sensorsidan där du bör kopiera den snabbtangent som du behöver ange på nästa sida i installationsguiden för Microsoft Defender för identitetssensorer](../../media/mtp-eval-49.png)
 
9. <span data-ttu-id="6f4a2-187">Kopiera snabbtangenten till guiden och klicka på **Installera.**</span><span class="sxs-lookup"><span data-stu-id="6f4a2-187">Copy the access key into the Wizard and click **Install**.</span></span> 

   ![Bild of_Microsoft sida i guiden Defender för identitets sensor där du ska ange snabbtangenten och klicka sedan på installationsknappen](../../media/mtp-eval-50.png)

10. <span data-ttu-id="6f4a2-189">Grattis! Du har konfigurerat Microsoft Defender för identitet på domänkontrollanten.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-189">Congratulations, you've successfully configured Microsoft Defender for Identity on your domain controller.</span></span>

    ![Bild of_Microsoft installation av guiden Defender för identitets sensorinstallation där du ska klicka på avslutsknappen](../../media/mtp-eval-51.png)
 
11. <span data-ttu-id="6f4a2-191">Under avsnittet [Inställningar för Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2040449) för identitet väljer du \*\*Microsoft Defender för Slutpunkt \*\*. Aktivera sedan växlingsknappen.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-191">Under the [Microsoft Defender for Identity](https://go.microsoft.com/fwlink/?linkid=2040449) settings section, select \*\*Microsoft Defender for Endpoint \*\*, then turn on the toggle.</span></span> <span data-ttu-id="6f4a2-192">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-192">Click **Save**.</span></span> 

    ![Bild of_the inställningssidan för Microsoft Defender för identitet där du ska aktivera växlingsknappen Microsoft Defender för slutpunkt](../../media/mtp-eval-52.png)

>[!NOTE]
><span data-ttu-id="6f4a2-194">Windows Defender ATP har rebranded as Microsoft Defender för Endpoint.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-194">Windows Defender ATP has been rebranded as Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="6f4a2-195">Rebranding changes across all of our portals are under rolled out the consistency.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-195">Rebranding changes across all of our portals are being rolled out the for consistency.</span></span>


## <a name="configure-microsoft-cloud-app-security"></a><span data-ttu-id="6f4a2-196">Konfigurera Microsoft Cloud App-säkerhet</span><span class="sxs-lookup"><span data-stu-id="6f4a2-196">Configure Microsoft Cloud App Security</span></span>

>[!NOTE]
><span data-ttu-id="6f4a2-197">Hoppa över det här steget om du redan har aktiverat Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-197">Skip this step if you've already enabled Microsoft Cloud App Security.</span></span> 

1. <span data-ttu-id="6f4a2-198">Gå till [Microsoft 365 Säkerhetscenter](https://security.microsoft.com/info)  >  **Fler resurser** Microsoft Cloud App  >  **Security.**</span><span class="sxs-lookup"><span data-stu-id="6f4a2-198">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Cloud App Security**.</span></span>

   ![Bild of_Microsoft 365 Säkerhetscenter där du kan se Microsoft Cloud App-kort och ska klicka på öppna-knappen](../../media/mtp-eval-53.png)

2. <span data-ttu-id="6f4a2-200">När du uppmanas att integrera Microsoft Defender för identitet väljer du **Aktivera Microsoft Defender för identitetsdataintegrering.**</span><span class="sxs-lookup"><span data-stu-id="6f4a2-200">At the information prompt to integrate Microsoft Defender for Identity, select **Enable Microsoft Defender for Identity data integration**.</span></span>
  
   ![Bild of_the fråga om du vill integrera Microsoft Defender för identitet, där du bör välja länken Aktivera Microsoft Defender för identitetsdataintegrering](../../media/mtp-eval-54.png)

   > [!NOTE]
   > <span data-ttu-id="6f4a2-202">Om du inte ser det här alternativet kan det innebära att dataintegreringen i Microsoft Defender för identitet redan har aktiverats.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-202">If you don’t see this prompt, it might mean that your Microsoft Defender for Identity data integration has already been enabled.</span></span> <span data-ttu-id="6f4a2-203">Om du är osäker kontaktar du IT-administratören för att bekräfta.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-203">However, if you are not sure, contact your IT Administrator to confirm.</span></span> 

3. <span data-ttu-id="6f4a2-204">Gå till **Inställningar,** aktivera växlingsknappen **för Microsoft Defender för** identitetsintegrering och klicka sedan på **Spara.**</span><span class="sxs-lookup"><span data-stu-id="6f4a2-204">Go to **Settings**, turn on the **Microsoft Defender for Identity integration** toggle, then click **Save**.</span></span> 

   ![Bild of_the inställningar där du bör aktivera växlingsknappen för Microsoft Defender för identitetsintegrering och sedan klicka på Spara](../../media/mtp-eval-55.png)
   
   > [!NOTE]
   > <span data-ttu-id="6f4a2-206">För nya Microsoft Defender för identitetsinstanser aktiveras den här integreringsreglaget automatiskt.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-206">For new Microsoft Defender for Identity instances, this integration toggle is automatically turned on.</span></span> <span data-ttu-id="6f4a2-207">Kontrollera att Microsoft Defender för identitetsintegrering har aktiverats innan du går vidare till nästa steg.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-207">Confirm that your Microsoft Defender for Identity integration has been enabled before you proceed to the next step.</span></span>
 
4. <span data-ttu-id="6f4a2-208">Under inställningarna för molnidentifiering väljer du **Microsoft Defender för slutpunktsintegrering** och aktiverar sedan integreringen.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-208">Under the Cloud discovery settings, select **Microsoft Defender for Endpoint integration**, then enable the integration.</span></span> <span data-ttu-id="6f4a2-209">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-209">Click **Save**.</span></span>

   ![Bild of_the microsoft Defender för slutpunktssida där kryssrutan osanerade blockerade appar är markerad under Microsoft Defender för slutpunktsintegrering.](../../media/mtp-eval-56.png)

5. <span data-ttu-id="6f4a2-212">Under inställningar för molnidentifiering **väljer du Användarberikning** och aktiverar sedan integreringen med Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-212">Under Cloud discovery settings, select **User enrichment**, then enable the integration with Azure Active Directory.</span></span>

   ![Bild av avsnittet Användarberikning där kryssrutan för att utöka identifierad användaridentifierare med Azure Active Directory-användarnamn är markerad](../../media/mtp-eval-57.png)


## <a name="configure-microsoft-defender-for-endpoint"></a><span data-ttu-id="6f4a2-214">Konfigurera Microsoft Defender för slutpunkt</span><span class="sxs-lookup"><span data-stu-id="6f4a2-214">Configure Microsoft Defender for Endpoint</span></span>

>[!NOTE]
><span data-ttu-id="6f4a2-215">Hoppa över det här steget om du redan har aktiverat Microsoft Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-215">Skip this step if you've already enabled Microsoft Defender for Endpoint.</span></span>

1. <span data-ttu-id="6f4a2-216">Gå till [Microsoft 365 Säkerhetscenter](https://security.microsoft.com/info)  >  **Fler resurser** Microsoft Defender  >  **Säkerhetscenter.**</span><span class="sxs-lookup"><span data-stu-id="6f4a2-216">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Defender Security Center**.</span></span> <span data-ttu-id="6f4a2-217">Klicka **på Öppna.**</span><span class="sxs-lookup"><span data-stu-id="6f4a2-217">Click **Open**.</span></span>

   ![Bild of_Microsoft Defender Säkerhetscenter på sidan Microsoft 365 Säkerhetscenter](../../media/mtp-eval-58.png)
 
2. <span data-ttu-id="6f4a2-219">Följ guiden Microsoft Defender för slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-219">Follow the Microsoft Defender for Endpoint wizard.</span></span> <span data-ttu-id="6f4a2-220">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-220">Click **Next**.</span></span> 

   ![Bild of_the välkomstguiden för Microsoft Defender Säkerhetscenter](../../media/mtp-eval-59.png)

3. <span data-ttu-id="6f4a2-222">Välj baserat på önskad datalagringsplats, databevarandeprincip, organisationsstorlek och möjlighet att registrera dig för förhandsgranskningsfunktioner.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-222">Choose based on your preferred data storage location, data retention policy, organization size, and opt-in for preview features.</span></span>

   ![Bild of_the väljer land, bevarandeprincip och organisationsstorlek för datalagringslandet.](../../media/mtp-eval-60.png)
   
   > [!NOTE]
   > <span data-ttu-id="6f4a2-225">Du kan inte ändra vissa inställningar, till exempel datalagringsplats, efteråt.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-225">You cannot change some of the settings, like data storage location, afterwards.</span></span> 

   <span data-ttu-id="6f4a2-226">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-226">Click **Next**.</span></span> 

4. <span data-ttu-id="6f4a2-227">Klicka **på Fortsätt** så etableras din Microsoft Defender för slutpunktsklientorganisation.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-227">Click **Continue** and it will provision your Microsoft Defender for Endpoint tenant.</span></span>

   ![Bild of_the fråga om du klickar på knappen Fortsätt för att skapa din molninstans](../../media/mtp-eval-61.png)

5. <span data-ttu-id="6f4a2-229">Introducera dina slutpunkter genom grupprinciper, Microsoft Endpoint Manager eller genom att köra ett lokalt skript till Microsoft Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-229">Onboard your endpoints through Group Policies, Microsoft Endpoint Manager or by running a local script to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="6f4a2-230">För enkelhetens skull använder den här guiden det lokala skriptet.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-230">For simplicity, this guide uses the local script.</span></span>

6. <span data-ttu-id="6f4a2-231">Klicka **på Ladda ned** paket och kopiera onboarding-skriptet till dina slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-231">Click **Download package** and copy the onboarding script to your endpoint(s).</span></span>

   ![Bild of_page du tillfrågas om att klicka på knappen Ladda ned paket för att kopiera onboarding-skriptet till slutpunkten eller slutpunkterna](../../media/mtp-eval-62.png)

7. <span data-ttu-id="6f4a2-233">Kör onboarding-skriptet som administratör på slutpunkten och välj Y.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-233">On your endpoint, run the onboarding script as Administrator and choose Y.</span></span> 

   ![Bild of_the kommandoraden där du kör onboarding-skriptet och väljer Y för att fortsätta](../../media/mtp-eval-63.png)

8. <span data-ttu-id="6f4a2-235">Grattis! Du har tagit med din första slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-235">Congratulations, you've onboarded your first endpoint.</span></span>

   ![Bild of_the kommandorad där du får en bekräftelse på att du har tagit med din första slutpunkt.](../../media/mtp-eval-64.png)

9. <span data-ttu-id="6f4a2-238">Kopiera och klistra in identifieringstestet från guiden Microsoft Defender för slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-238">Copy-paste the detection test from the Microsoft Defender for Endpoint wizard.</span></span>

   ![Bild of_the köra ett identifieringsteststeg där du ska klicka på Kopiera för att kopiera det identifieringstestskript som du ska klistra in i kommandotolken](../../media/mtp-eval-65.png)

10. <span data-ttu-id="6f4a2-240">Kopiera PowerShell-skriptet till en upphöjd kommandotolk och kör det.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-240">Copy the PowerShell script to an elevated command prompt and run it.</span></span> 

    ![Bild of_command fråga var du ska kopiera PowerShell-skriptet till en upphöjd kommandotolk och köra den](../../media/mtp-eval-66.png)

11. <span data-ttu-id="6f4a2-242">Välj **Börja använda Microsoft Defender för slutpunkt** i guiden.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-242">Select **Start using Microsoft Defender for Endpoint** from the Wizard.</span></span>

    ![Bild of_the bekräftelsemeddelande från guiden där du ska klicka på Börja använda Microsoft Defender för Slutpunkt](../../media/mtp-eval-67.png)
 
12. <span data-ttu-id="6f4a2-244">Besök [Microsoft Defender Säkerhetscenter.](https://securitycenter.windows.com/)</span><span class="sxs-lookup"><span data-stu-id="6f4a2-244">Visit the [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span></span> <span data-ttu-id="6f4a2-245">Gå till **Inställningar** och välj sedan **Avancerade funktioner.**</span><span class="sxs-lookup"><span data-stu-id="6f4a2-245">Go to **Settings** and then select **Advanced features**.</span></span> 

    ![Bild of_Microsoft Inställningsmenyn i Defender Säkerhetscenter där du ska välja Avancerade funktioner](../../media/mtp-eval-68.png)

13. <span data-ttu-id="6f4a2-247">Aktivera integreringen med **Microsoft Defender för identitet.**</span><span class="sxs-lookup"><span data-stu-id="6f4a2-247">Turn on the integration with **Microsoft Defender for Identity**.</span></span>  

    ![Bild of_Microsoft avancerade funktioner i Defender Säkerhetscenter, växlingsknappen Microsoft Defender för identitet som du behöver aktivera](../../media/mtp-eval-69.png)

14. <span data-ttu-id="6f4a2-249">Aktivera integrering med **Office 365 Threat Intelligence.**</span><span class="sxs-lookup"><span data-stu-id="6f4a2-249">Turn on the integration with **Office 365 Threat Intelligence**.</span></span>

    ![Bild of_Microsoft Avancerade funktioner i Defender Säkerhetscenter, växlingsknappen för Office 365 Threat Intelligence som du behöver aktivera](../../media/mtp-eval-70.png)

15. <span data-ttu-id="6f4a2-251">Aktivera integrering med **Microsoft Cloud App Security.**</span><span class="sxs-lookup"><span data-stu-id="6f4a2-251">Turn on integration with **Microsoft Cloud App Security**.</span></span>

    ![Bild of_Microsoft avancerade funktioner i Defender Säkerhetscenter, växlingsknappen Microsoft Cloud App Security som du behöver aktivera](../../media/mtp-eval-71.png)

16. <span data-ttu-id="6f4a2-253">Rulla nedåt och klicka **på Spara inställningar för** att bekräfta de nya integrationerna.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-253">Scroll down and click **Save preferences** to confirm the new integrations.</span></span>

    ![Bild of_Save inställningar som du behöver klicka på](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-365-defender-service"></a><span data-ttu-id="6f4a2-255">Starta tjänsten Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6f4a2-255">Start the Microsoft 365 Defender service</span></span>

>[!NOTE]
><span data-ttu-id="6f4a2-256">Från och med den 1 juni 2020 aktiverar Microsoft automatiskt Microsoft 365 Defender-funktioner för alla berättigade klientorganisationar.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-256">Starting June 1, 2020, Microsoft automatically enables Microsoft 365 Defender features for all eligible tenants.</span></span> <span data-ttu-id="6f4a2-257">Mer information finns [i den här Microsoft Tech Community-artikeln om licensberättigande.](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426)</span><span class="sxs-lookup"><span data-stu-id="6f4a2-257">See this [Microsoft Tech Community article on license eligibility](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) for details.</span></span> 


<span data-ttu-id="6f4a2-258">Gå till [Microsoft 365 Säkerhetscenter.](https://security.microsoft.com/homepage)</span><span class="sxs-lookup"><span data-stu-id="6f4a2-258">Go to [Microsoft 365 Security Center](https://security.microsoft.com/homepage).</span></span> <span data-ttu-id="6f4a2-259">Gå till **Inställningar** och välj sedan **Microsoft 365 Defender.**</span><span class="sxs-lookup"><span data-stu-id="6f4a2-259">Navigate to **Settings** and then select **Microsoft 365 Defender**.</span></span>

![<span data-ttu-id="6f4a2-260">Skärmbild of_Microsoft alternativ för 365 Defender från sidan Inställningar för Säkerhetscenter i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6f4a2-260">Image of_Microsoft 365 Defender option screenshot from the Microsoft 365 Security Center Settings page</span></span> ](../../media/mtp-eval-72b.png) <br>

<span data-ttu-id="6f4a2-261">Mer omfattande vägledning finns i Aktivera [Microsoft 365 Defender.](mtp-enable.md)</span><span class="sxs-lookup"><span data-stu-id="6f4a2-261">For a more comprehensive guidance, see [Turn on Microsoft 365 Defender](mtp-enable.md).</span></span> 

<span data-ttu-id="6f4a2-262">Grattis!</span><span class="sxs-lookup"><span data-stu-id="6f4a2-262">Congratulations!</span></span> <span data-ttu-id="6f4a2-263">Du har just skapat din utvärderingslabb- eller pilotmiljö i Microsoft 365 Defender!</span><span class="sxs-lookup"><span data-stu-id="6f4a2-263">You've just created your Microsoft 365 Defender trial lab or pilot environment!</span></span> <span data-ttu-id="6f4a2-264">Nu kan du bekanta dig med användargränssnittet i Microsoft 365 Defender!</span><span class="sxs-lookup"><span data-stu-id="6f4a2-264">Now you can familiarize yourself with the Microsoft 365 Defender user interface!</span></span> <span data-ttu-id="6f4a2-265">Se vad du kan lära dig av följande interaktiva Microsoft 365 Defender-guide och vet hur du använder varje instrumentpanel för dina dagliga säkerhetsåtgärdsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-265">See what you can learn from the following Microsoft 365 Defender interactive guide and know how to use each dashboard for your day-to-day security operation tasks.</span></span>


>[!VIDEO https://aka.ms/MTP-Interactive-Guide]

<span data-ttu-id="6f4a2-266">Därefter kan du simulera en attack och se hur funktionerna i korsprodukten identifierar, skapar aviseringar och automatiskt svarar på fillösa angrepp på en slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-266">Next, you can simulate an attack and see how the cross product capabilities detect, create alerts, and automatically respond to a fileless attack on an endpoint.</span></span>

## <a name="next-step"></a><span data-ttu-id="6f4a2-267">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="6f4a2-267">Next step</span></span>
|[<span data-ttu-id="6f4a2-268">Attackfas för simulering</span><span class="sxs-lookup"><span data-stu-id="6f4a2-268">Attack simulation phase</span></span>](mtp-pilot-simulate.md) | <span data-ttu-id="6f4a2-269">Kör attacksimuleringen för din Microsoft 365 Defender-pilotmiljö.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-269">Run the attack simulation for your Microsoft 365 Defender pilot environment.</span></span>
|:-------|:-----|
