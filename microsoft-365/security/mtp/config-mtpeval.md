---
title: Konfigurera Microsoft 365 Defender-pelaren för utvärderings labbet eller pilot miljön
description: Konfigurera Microsoft 365 Defender-pelaren, till exempel Microsoft Defender för Office 365, Microsoft Defender för identitet, Microsoft Cloud App-säkerhet och Microsoft Defender för slut punkten, för utvärderings labbet eller pilot miljön.
keywords: Konfigurera utvärderings versionen av Microsoft Threat Protection, test version av Microsoft Threat Protection, konfigurera Microsoft Threat Protection Pilot-projekt, konfigurera Microsoft Threat Protection-spel, Microsoft Threat Protection-pelare
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
- m365solution-evalutatemtp
ms.topic: article
ms.openlocfilehash: 240ffd7ec8d46da33c43ec2f9cb50cf59c89f11b
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/18/2020
ms.locfileid: "49131303"
---
# <a name="configure-microsoft-365-defender-pillars-for-your-trial-lab-or-pilot-environment"></a><span data-ttu-id="587a3-104">Konfigurera Microsoft 365 Defender-pelaren för utvärderings labbet eller pilot miljön</span><span class="sxs-lookup"><span data-stu-id="587a3-104">Configure Microsoft 365 Defender pillars for your trial lab or pilot environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="587a3-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="587a3-105">**Applies to:**</span></span>
- <span data-ttu-id="587a3-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="587a3-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="587a3-107">Att skapa en test labb-eller pilot miljö för Microsoft 365 Defender och distribuera det är en process i tre steg:</span><span class="sxs-lookup"><span data-stu-id="587a3-107">Creating a Microsoft 365 Defender trial lab or pilot environment and deploying it is a three-phase process:</span></span>

|<span data-ttu-id="587a3-108">[![Fas 1: förbereda](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="587a3-108">[![Phase 1: Prepare](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)</span></span><br/>[<span data-ttu-id="587a3-109">Fas 1: förbereda</span><span class="sxs-lookup"><span data-stu-id="587a3-109">Phase 1: Prepare</span></span>](prepare-mtpeval.md) |<span data-ttu-id="587a3-110">[![Fas 2: Konfigurera](../../media/phase-diagrams/setup.png)](setup-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="587a3-110">[![Phase 2: Set up](../../media/phase-diagrams/setup.png)](setup-mtpeval.md)</span></span><br/>[<span data-ttu-id="587a3-111">Fas 2: Konfigurera</span><span class="sxs-lookup"><span data-stu-id="587a3-111">Phase 2: Set up</span></span>](setup-mtpeval.md) |![Fas 3: inbyggt](../../media/phase-diagrams/onboard.png)<br/><span data-ttu-id="587a3-113">Fas 3: inbyggt</span><span class="sxs-lookup"><span data-stu-id="587a3-113">Phase 3: Onboard</span></span> | <span data-ttu-id="587a3-114">[![Tillbaka till piloten](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="587a3-114">[![Back to pilot](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)</span></span><br/>[<span data-ttu-id="587a3-115">Tillbaka till pilot Playbook</span><span class="sxs-lookup"><span data-stu-id="587a3-115">Back to pilot playbook</span></span>](mtp-pilot.md) |
|--|--|--|--|
|| |<span data-ttu-id="587a3-116">*Nu är det här!*</span><span class="sxs-lookup"><span data-stu-id="587a3-116">*You are here!*</span></span> | |

<span data-ttu-id="587a3-117">Du är för närvarande i konfigurations fasen.</span><span class="sxs-lookup"><span data-stu-id="587a3-117">You're currently in the configuration phase.</span></span>

<span data-ttu-id="587a3-118">Förberedelsen är viktig för eventuell distribution.</span><span class="sxs-lookup"><span data-stu-id="587a3-118">Preparation is key to any successful deployment.</span></span> <span data-ttu-id="587a3-119">I den här artikeln vägleder vi dig på de Points du måste tänka på när du förbereder dig för att distribuera Microsoft Defender för slut punkten.</span><span class="sxs-lookup"><span data-stu-id="587a3-119">In this article, you'll be guided on the points you'll need to consider as you prepare to deploy Microsoft Defender for Endpoint.</span></span>


## <a name="microsoft-365-defender-pillars"></a><span data-ttu-id="587a3-120">Microsoft 365 Defender-pelare</span><span class="sxs-lookup"><span data-stu-id="587a3-120">Microsoft 365 Defender pillars</span></span>
<span data-ttu-id="587a3-121">Microsoft 365 Defender består av fyra pelare.</span><span class="sxs-lookup"><span data-stu-id="587a3-121">Microsoft 365 Defender consists of four pillars.</span></span> <span data-ttu-id="587a3-122">Även om en pelare redan kan ge ett värde till din organisations säkerhet i ditt nätverk, ger de fyra hög365 Defender-stenarna det mest aktuella värdet.</span><span class="sxs-lookup"><span data-stu-id="587a3-122">Although one pillar can already provide value to your network organization's security, enabling the four Microsoft 365 Defender pillars will give your organization the most value.</span></span>

![Bild of_Microsoft 365 Defender-lösning för användare, Microsoft Defender för identitet för slut punkter Microsoft Defender för slut punkter, moln program, Microsoft Cloud App-säkerhet och för data, Microsoft Defender för Office 365](../../media/mtp/m365pillars.png)

<span data-ttu-id="587a3-124">I det här avsnittet får du hjälp att konfigurera:</span><span class="sxs-lookup"><span data-stu-id="587a3-124">This section will guide you to configure:</span></span>
-   <span data-ttu-id="587a3-125">Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="587a3-125">Microsoft Defender for Office 365</span></span>
-   <span data-ttu-id="587a3-126">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="587a3-126">Microsoft Defender for Identity</span></span> 
-   <span data-ttu-id="587a3-127">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="587a3-127">Microsoft Cloud App Security</span></span>
-   <span data-ttu-id="587a3-128">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="587a3-128">Microsoft Defender for Endpoint</span></span>


## <a name="configure-microsoft-defender-for-office-365"></a><span data-ttu-id="587a3-129">Konfigurera Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="587a3-129">Configure Microsoft Defender for Office 365</span></span>

>[!NOTE]
><span data-ttu-id="587a3-130">Hoppa över det här steget om du redan har aktiverat Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="587a3-130">Skip this step if you've already enabled Defender for Office 365.</span></span> 

<span data-ttu-id="587a3-131">Det finns en PowerShell-modul som heter *Office 365 Advanced Threat Protection (Orca)* som hjälper dig att avgöra vissa av de här inställningarna.</span><span class="sxs-lookup"><span data-stu-id="587a3-131">There's a PowerShell Module called the *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* that helps determine some of these settings.</span></span> <span data-ttu-id="587a3-132">När du kör som administratör i klient organisationen kan du med ORCAReport få en utvärdering av skräp post, anti-Phish och andra inställningar för meddelande hygien.</span><span class="sxs-lookup"><span data-stu-id="587a3-132">When run as an administrator in your tenant, get-ORCAReport will help generate an assessment of the anti-spam, anti-phish, and other message hygiene settings.</span></span> <span data-ttu-id="587a3-133">Du kan hämta den här modulen från https://www.powershellgallery.com/packages/ORCA/ .</span><span class="sxs-lookup"><span data-stu-id="587a3-133">You can download this module from https://www.powershellgallery.com/packages/ORCA/.</span></span> 

1. <span data-ttu-id="587a3-134">Navigera till [Office 365-säkerhets &](https://protection.office.com/homepage)  >  policy för **hantering** av villkor för efterlevnad  >  **Policy**.</span><span class="sxs-lookup"><span data-stu-id="587a3-134">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Policy**.</span></span>

   ![Bild of_Office 365 säkerhets & policy för Threat Management-hantering](../../media/mtp-eval-32.png)
 
2. <span data-ttu-id="587a3-136">Klicka på **nätfiske**, Välj **skapa** och fyll i princip namnet och beskrivningen.</span><span class="sxs-lookup"><span data-stu-id="587a3-136">Click **Anti-phishing**, select **Create** and fill in the policy name and description.</span></span> <span data-ttu-id="587a3-137">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="587a3-137">Click **Next**.</span></span>

   ![Bild of_Office 365 säkerhet & policy för skydd mot Office-nätfiske där du kan namnge policyn](../../media/mtp-eval-33.png)

   > [!NOTE]
   > <span data-ttu-id="587a3-139">Redigera din avancerade policy för anti-nätfiske i Microsoft Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="587a3-139">Edit your Advanced anti-phishing policy in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="587a3-140">Ändra den **avancerade nät fiske tröskeln** till **2-aggressivt**.</span><span class="sxs-lookup"><span data-stu-id="587a3-140">Change **Advanced Phishing Threshold** to **2 - Aggressive**.</span></span>

3. <span data-ttu-id="587a3-141">Klicka på den nedrullningsbara menyn **Lägg till en villkors** lista och välj din domän (er) som mottagar domän.</span><span class="sxs-lookup"><span data-stu-id="587a3-141">Click the **Add a condition** drop-down menu and select your domain(s) as recipient domain.</span></span> <span data-ttu-id="587a3-142">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="587a3-142">Click **Next**.</span></span>

   ![Bild of_Office 365 säkerhet & policy för skydd mot server för uppringnings Center där du kan lägga till ett villkor för dess program](../../media/mtp-eval-34.png)
 
4. <span data-ttu-id="587a3-144">Granska dina inställningar.</span><span class="sxs-lookup"><span data-stu-id="587a3-144">Review your settings.</span></span> <span data-ttu-id="587a3-145">Klicka på **skapa den här principen** för att bekräfta.</span><span class="sxs-lookup"><span data-stu-id="587a3-145">Click **Create this policy** to confirm.</span></span> 

   ![Bild of_Office 365 säkerhets & policy för skydd mot efterlevnad för nätfiske där du kan granska dina inställningar och klicka på knappen Skapa den här principen](../../media/mtp-eval-35.png)
 
5. <span data-ttu-id="587a3-147">Välj **bifogade filer** och välj alternativet **Aktivera ATP för SharePoint, OneDrive och Microsoft Teams** .</span><span class="sxs-lookup"><span data-stu-id="587a3-147">Select **Safe Attachments** and select the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** option.</span></span>

   ![Bild of_Office 365 säkerhets & sidan Compliance Center där du kan aktivera ATP för SharePoint, OneDrive och Microsoft Teams](../../media/mtp-eval-36.png)

6. <span data-ttu-id="587a3-149">Klicka på ikonen + för att skapa en ny princip för säker bifogad fil, tillämpa den som mottagar domän i domänerna.</span><span class="sxs-lookup"><span data-stu-id="587a3-149">Click the + icon to create a new safe attachment policy, apply it as recipient domain to your domains.</span></span> <span data-ttu-id="587a3-150">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="587a3-150">Click **Save**.</span></span>

   ![Bild of_Office 365 säkerhets & sidan Compliance Center, där du kan skapa en ny princip för säker bifogad fil](../../media/mtp-eval-37.png)
 
7. <span data-ttu-id="587a3-152">Välj sedan principen för **säkra länkar** och klicka sedan på Penn ikonen för att redigera standard principen.</span><span class="sxs-lookup"><span data-stu-id="587a3-152">Next, select the **Safe Links** policy, then click the pencil icon to edit the default policy.</span></span>

8. <span data-ttu-id="587a3-153">Kontrol lera att alternativet **Spåra inte när användare klickar på säkra länkar** inte är markerat, medan resten av alternativen är markerade.</span><span class="sxs-lookup"><span data-stu-id="587a3-153">Make sure that the **Do not track when users click safe links** option is not selected, while the rest of the options are selected.</span></span> <span data-ttu-id="587a3-154">Se [Inställningar för Safe Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) .</span><span class="sxs-lookup"><span data-stu-id="587a3-154">See [Safe Links settings](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) for details.</span></span> <span data-ttu-id="587a3-155">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="587a3-155">Click **Save**.</span></span> 

   ![Bild of_Office 365 säkerhets & sidan Compliance Center som visar att alternativet spåra inte när användare klickar på säker är inte markerat](../../media/mtp-eval-38.png)

9. <span data-ttu-id="587a3-157">Välj sedan standard principen för att förhindra **mot skadlig program vara** och välj sedan Penn ikonen.</span><span class="sxs-lookup"><span data-stu-id="587a3-157">Next select the **Anti-malware** policy, select the default, and choose the pencil icon.</span></span>

10. <span data-ttu-id="587a3-158">Klicka på **Inställningar** och välj **Ja och Använd standard meddelande texten** för att aktivera **identifiering av skadlig program vara**.</span><span class="sxs-lookup"><span data-stu-id="587a3-158">Click **Settings** and select **Yes and use the default notification text** to enable **Malware Detection Response**.</span></span> <span data-ttu-id="587a3-159">Aktivera **filtret vanliga typer av bifogade filer** .</span><span class="sxs-lookup"><span data-stu-id="587a3-159">Turn the **Common Attachment Types Filter** on.</span></span> <span data-ttu-id="587a3-160">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="587a3-160">Click **Save**.</span></span>

    ![Bild of_Office 365 säkerhets & sidan Compliance Center som visar att svaret om skadlig program vara är aktiverat med standard meddelande och att filtret vanliga bilage typer är aktiverat](../../media/mtp-eval-39.png)
  
11. <span data-ttu-id="587a3-162">Navigera till [Office 365-säkerhets & Compliance Center](https://protection.office.com/homepage)  >  **Sök** efter  >  **gransknings loggs ökning** och aktivera granskning.</span><span class="sxs-lookup"><span data-stu-id="587a3-162">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Search** > **Audit log search** and turn Auditing on.</span></span>

    ![Bild of_Office 365 säkerhets & sidan Compliance Center där du kan aktivera gransknings loggs ökningen](../../media/mtp-eval-40.png)

12. <span data-ttu-id="587a3-164">Integrera Microsoft Defender för Office 365 med Microsoft Defender för slut punkten.</span><span class="sxs-lookup"><span data-stu-id="587a3-164">Integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="587a3-165">Navigera till [Office 365-säkerhets & efterlevnad för Compliance Center](https://protection.office.com/homepage)  >  **Threat management**  >  **Explorer** och välj **Microsoft Defender för slut punkts inställningar** i det övre högra hörnet av skärmen.</span><span class="sxs-lookup"><span data-stu-id="587a3-165">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Explorer** and select **Microsoft Defender for Endpoint Settings** on the upper right corner of the screen.</span></span> <span data-ttu-id="587a3-166">I dialog rutan Defender för slut punkts anslutning aktiverar **du Anslut till Microsoft Defender för slut punkt**.</span><span class="sxs-lookup"><span data-stu-id="587a3-166">In the Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span>

    ![Bild of_Office 365 säkerhets & sidan Compliance Center där du kan aktivera Microsoft Defender för slut punkts anslutning på](../../media/mtp-eval-41.png)

## <a name="configure-microsoft-defender-for-identity"></a><span data-ttu-id="587a3-168">Konfigurera Microsoft Defender för identitet</span><span class="sxs-lookup"><span data-stu-id="587a3-168">Configure Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="587a3-169">Hoppa över det här steget om du redan har aktiverat Microsoft Defender för identitet</span><span class="sxs-lookup"><span data-stu-id="587a3-169">Skip this step if you've already enabled Microsoft Defender for Identity</span></span>

1. <span data-ttu-id="587a3-170">Navigera till [Microsoft 365 säkerhets Center](https://security.microsoft.com/info) > Välj **fler resurser**  >  **Microsoft Defender för identitet**.</span><span class="sxs-lookup"><span data-stu-id="587a3-170">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > select **More Resources** > **Microsoft Defender for Identity**.</span></span>

   ![Bild of_Microsoft 365 säkerhets Center sida där det finns ett alternativ för att öppna Microsoft Defender för identitet](../../media/mtp-eval-42.png)

2. <span data-ttu-id="587a3-172">Klicka på **skapa** för att starta Microsoft Defender för identitets guiden.</span><span class="sxs-lookup"><span data-stu-id="587a3-172">Click **Create** to start the Microsoft Defender for Identity wizard.</span></span> 

   ![Bild of_Microsoft Defender för guiden för identitet där du bör Klicka på knappen Skapa](../../media/mtp-eval-43.png)

3. <span data-ttu-id="587a3-174">Välj **ge ett användar namn och lösen ord för att ansluta till Active Directory-skogen**.</span><span class="sxs-lookup"><span data-stu-id="587a3-174">Choose **Provide a username and password to connect to your Active Directory forest**.</span></span>  

   ![Bild of_Microsoft Defender för välkomst sida](../../media/mtp-eval-44.png)

4. <span data-ttu-id="587a3-176">Ange lokala inloggnings uppgifter för Active Directory.</span><span class="sxs-lookup"><span data-stu-id="587a3-176">Enter your Active Directory on-premises credentials.</span></span> <span data-ttu-id="587a3-177">Det kan vara vilket användar konto som helst som har Läs åtkomst till Active Directory.</span><span class="sxs-lookup"><span data-stu-id="587a3-177">This can be any user account that has read access to Active Directory.</span></span>

   ![Bild of_Microsoft Defender för identitets katalog tjänster där du ska ange dina uppgifter](../../media/mtp-eval-45.png)

5. <span data-ttu-id="587a3-179">Välj sedan **Ladda ned sensor konfiguration** och överföra fil till domänkontrollanten.</span><span class="sxs-lookup"><span data-stu-id="587a3-179">Next, choose **Download Sensor Setup** and transfer file to your domain controller.</span></span>

   ![Bild of_Microsoft Defender för identitets sida där du kan välja nedladdnings sensor inställning](../../media/mtp-eval-46.png)

6. <span data-ttu-id="587a3-181">Kör installations programmet för Microsoft Defender för identitets sensor och börja följa guiden.</span><span class="sxs-lookup"><span data-stu-id="587a3-181">Execute the Microsoft Defender for Identity Sensor Setup and begin following the wizard.</span></span>

   ![Bild of_Microsoft Defender för identitets sida där du bör Klicka på Nästa för att följa Microsoft Defender-guiden för identitets sensor](../../media/mtp-eval-47.png)
 
7. <span data-ttu-id="587a3-183">Klicka på **Nästa** på sensor distributions typen.</span><span class="sxs-lookup"><span data-stu-id="587a3-183">Click **Next** at the sensor deployment type.</span></span>

   ![Bild of_Microsoft Defender för identitets sida där du bör klicka bredvid gå till nästa sida](../../media/mtp-eval-48.png)
 
8. <span data-ttu-id="587a3-185">Kopiera snabb tangenten eftersom du måste ange den intill i guiden.</span><span class="sxs-lookup"><span data-stu-id="587a3-185">Copy the access key because you need to enter it next in the Wizard.</span></span>

   ![Bild of_the sensorer-sida där du vill kopiera den snabb åtkomst-knapp som du måste ange på nästa sida i guiden Konfigurera Microsoft Defender för identitets sensor](../../media/mtp-eval-49.png)
 
9. <span data-ttu-id="587a3-187">Kopiera till guiden och klicka på **Installera**.</span><span class="sxs-lookup"><span data-stu-id="587a3-187">Copy the access key into the Wizard and click **Install**.</span></span> 

   ![Bild of_Microsoft Defender för guiden för identitets sensor där du bör tillhandahålla åtkomst-tangenten och sedan klicka på knappen Installera](../../media/mtp-eval-50.png)

10. <span data-ttu-id="587a3-189">Grattis! du har konfigurerat Microsoft Defender för din domänkontrollant.</span><span class="sxs-lookup"><span data-stu-id="587a3-189">Congratulations, you've successfully configured Microsoft Defender for Identity on your domain controller.</span></span>

    ![Bild of_Microsoft Defender för guiden för identitets sensor installation, där du bör Klicka på knappen Slutför](../../media/mtp-eval-51.png)
 
11. <span data-ttu-id="587a3-191">Under [Microsoft Defender för identitets](https://go.microsoft.com/fwlink/?linkid=2040449) inställningar väljer du \* \* Microsoft Defender för slut punkt \* \* och aktiverar sedan växlingen.</span><span class="sxs-lookup"><span data-stu-id="587a3-191">Under the [Microsoft Defender for Identity](https://go.microsoft.com/fwlink/?linkid=2040449) settings section, select \*\*Microsoft Defender for Endpoint \*\*, then turn on the toggle.</span></span> <span data-ttu-id="587a3-192">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="587a3-192">Click **Save**.</span></span> 

    ![Bild of_the inställningar för inloggnings sidan för Microsoft Defender för att du ska aktivera växla mellan Microsoft Defender för slut punkt](../../media/mtp-eval-52.png)

>[!NOTE]
><span data-ttu-id="587a3-194">Windows Defender ATP har ändrats som Microsoft Defender för slut punkt.</span><span class="sxs-lookup"><span data-stu-id="587a3-194">Windows Defender ATP has been rebranded as Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="587a3-195">Att ändra dina ändringar i alla portaler blir då mer konsekvens.</span><span class="sxs-lookup"><span data-stu-id="587a3-195">Rebranding changes across all of our portals are being rolled out the for consistency.</span></span>


## <a name="configure-microsoft-cloud-app-security"></a><span data-ttu-id="587a3-196">Konfigurera säkerhet för Microsoft Cloud App</span><span class="sxs-lookup"><span data-stu-id="587a3-196">Configure Microsoft Cloud App Security</span></span>

>[!NOTE]
><span data-ttu-id="587a3-197">Hoppa över det här steget om du redan har aktiverat säkerhet för Microsoft Cloud App.</span><span class="sxs-lookup"><span data-stu-id="587a3-197">Skip this step if you've already enabled Microsoft Cloud App Security.</span></span> 

1. <span data-ttu-id="587a3-198">Navigera till [Microsoft 365 säkerhets Center](https://security.microsoft.com/info)  >  **fler resurser**  >  **Microsoft Cloud App-säkerhet**.</span><span class="sxs-lookup"><span data-stu-id="587a3-198">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Cloud App Security**.</span></span>

   ![Bild of_Microsoft 365 säkerhets Center sida där du kan se Microsoft Cloud App Card och ska klicka på knappen Öppna](../../media/mtp-eval-53.png)

2. <span data-ttu-id="587a3-200">I rutan information om hur du integrerar Microsoft Defender för identiteter väljer du **aktivera Microsoft Defender för identitets data integrering**.</span><span class="sxs-lookup"><span data-stu-id="587a3-200">At the information prompt to integrate Microsoft Defender for Identity, select **Enable Microsoft Defender for Identity data integration**.</span></span>
  
   ![Of_the om du vill integrera Microsoft Defender för en identitet där du bör välja länken Aktivera Microsoft Defender för identitets data integrering](../../media/mtp-eval-54.png)

   > [!NOTE]
   > <span data-ttu-id="587a3-202">Om du inte ser den här uppmaningen kan det betyda att din Microsoft Defender för identitets data integrering redan har Aktiver ATS.</span><span class="sxs-lookup"><span data-stu-id="587a3-202">If you don’t see this prompt, it might mean that your Microsoft Defender for Identity data integration has already been enabled.</span></span> <span data-ttu-id="587a3-203">Om du är osäker kontaktar du IT-administratören för att bekräfta.</span><span class="sxs-lookup"><span data-stu-id="587a3-203">However, if you are not sure, contact your IT Administrator to confirm.</span></span> 

3. <span data-ttu-id="587a3-204">Gå till **Inställningar**, aktivera växla mellan **Microsoft Defender för identitets integrering** och klicka sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="587a3-204">Go to **Settings**, turn on the **Microsoft Defender for Identity integration** toggle, then click **Save**.</span></span> 

   ![Sidan image of_the inställningar där du bör aktivera växla mellan Microsoft Defender för identitets integrering och klicka på Spara.](../../media/mtp-eval-55.png)
   
   > [!NOTE]
   > <span data-ttu-id="587a3-206">För nya Microsoft Defender för identitets instanser är denna växel växling automatiskt aktive rad.</span><span class="sxs-lookup"><span data-stu-id="587a3-206">For new Microsoft Defender for Identity instances, this integration toggle is automatically turned on.</span></span> <span data-ttu-id="587a3-207">Kontrol lera att din Microsoft Defender för identitets integrering har Aktiver ATS innan du fortsätter till nästa steg.</span><span class="sxs-lookup"><span data-stu-id="587a3-207">Confirm that your Microsoft Defender for Identity integration has been enabled before you proceed to the next step.</span></span>
 
4. <span data-ttu-id="587a3-208">Under Inställningar för moln identifiering väljer du **Microsoft Defender för slut punkts integrering** och aktiverar integrationen.</span><span class="sxs-lookup"><span data-stu-id="587a3-208">Under the Cloud discovery settings, select **Microsoft Defender for Endpoint integration**, then enable the integration.</span></span> <span data-ttu-id="587a3-209">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="587a3-209">Click **Save**.</span></span>

   ![Bild of_the Microsoft Defender för slut punkts sida där kryss rutan blockera program utan sanktioner under Microsoft Defender för slut punkts integrering är markerad.](../../media/mtp-eval-56.png)

5. <span data-ttu-id="587a3-212">Under Inställningar för moln identifiering väljer du **användar upplevelse** och aktiverar integrationen med Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="587a3-212">Under Cloud discovery settings, select **User enrichment**, then enable the integration with Azure Active Directory.</span></span>

   ![Bild av avsnittet användar berikning där kryss rutan utökad identifiering av användar identifierare med Azure Active Directory-username är markerad](../../media/mtp-eval-57.png)


## <a name="configure-microsoft-defender-for-endpoint"></a><span data-ttu-id="587a3-214">Konfigurera Microsoft Defender för slut punkten</span><span class="sxs-lookup"><span data-stu-id="587a3-214">Configure Microsoft Defender for Endpoint</span></span>

>[!NOTE]
><span data-ttu-id="587a3-215">Hoppa över det här steget om du redan har aktiverat Microsoft Defender för slut punkter.</span><span class="sxs-lookup"><span data-stu-id="587a3-215">Skip this step if you've already enabled Microsoft Defender for Endpoint.</span></span>

1. <span data-ttu-id="587a3-216">Gå till [Microsoft 365 säkerhets Center](https://security.microsoft.com/info)  >  **fler resurser**  >  **Microsoft Defender säkerhets Center**.</span><span class="sxs-lookup"><span data-stu-id="587a3-216">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Defender Security Center**.</span></span> <span data-ttu-id="587a3-217">Klicka på **Öppna**.</span><span class="sxs-lookup"><span data-stu-id="587a3-217">Click **Open**.</span></span>

   ![Bild of_Microsoft Defender säkerhets Center på sidan Microsoft 365 Security Center](../../media/mtp-eval-58.png)
 
2. <span data-ttu-id="587a3-219">Följ instruktionerna i Microsoft Defender för slut punkter.</span><span class="sxs-lookup"><span data-stu-id="587a3-219">Follow the Microsoft Defender for Endpoint wizard.</span></span> <span data-ttu-id="587a3-220">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="587a3-220">Click **Next**.</span></span> 

   ![Bild of_the sidan Välkommen till Microsoft Defender säkerhets Center](../../media/mtp-eval-59.png)

3. <span data-ttu-id="587a3-222">Välj baserat på din önskade lagrings plats för data, bevarande princip för data, organisations storlek och val för förhands gransknings funktioner.</span><span class="sxs-lookup"><span data-stu-id="587a3-222">Choose based on your preferred data storage location, data retention policy, organization size, and opt-in for preview features.</span></span>

   ![Bild of_the sida för att välja data lagrings land, bevarande princip och organisations storlek.](../../media/mtp-eval-60.png)
   
   > [!NOTE]
   > <span data-ttu-id="587a3-225">Du kan inte ändra vissa inställningar, till exempel data lagrings plats, efteråt.</span><span class="sxs-lookup"><span data-stu-id="587a3-225">You cannot change some of the settings, like data storage location, afterwards.</span></span> 

   <span data-ttu-id="587a3-226">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="587a3-226">Click **Next**.</span></span> 

4. <span data-ttu-id="587a3-227">Klicka på **Fortsätt** så tillhandahåller Microsoft Defender för slut punkts klient organisation.</span><span class="sxs-lookup"><span data-stu-id="587a3-227">Click **Continue** and it will provision your Microsoft Defender for Endpoint tenant.</span></span>

   ![Bild of_the sida där du uppmanas att klicka på knappen Fortsätt för att skapa din moln instans](../../media/mtp-eval-61.png)

5. <span data-ttu-id="587a3-229">Ta fram dina slut punkter via grup principer, Microsoft slut punkts hanteraren eller genom att köra ett lokalt skript till Microsoft Defender för slut punkt.</span><span class="sxs-lookup"><span data-stu-id="587a3-229">Onboard your endpoints through Group Policies, Microsoft Endpoint Manager or by running a local script to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="587a3-230">För enkelhetens skull använder den här guiden det lokala skriptet.</span><span class="sxs-lookup"><span data-stu-id="587a3-230">For simplicity, this guide uses the local script.</span></span>

6. <span data-ttu-id="587a3-231">Klicka på **Ladda ned paket** och kopiera registrerings skriptet till din slut punkt (er).</span><span class="sxs-lookup"><span data-stu-id="587a3-231">Click **Download package** and copy the onboarding script to your endpoint(s).</span></span>

   ![Bild of_page du uppmanas att klicka på knappen Ladda ned paket för att kopiera det inbyggda skriptet till slut punkten eller slut punkterna](../../media/mtp-eval-62.png)

7. <span data-ttu-id="587a3-233">Kör skriptet som administratör på slut punkten och välj Y.</span><span class="sxs-lookup"><span data-stu-id="587a3-233">On your endpoint, run the onboarding script as Administrator and choose Y.</span></span> 

   ![Bild of_the kommando rad där du kör det inbyggda skriptet och väljer sedan Y för att fortsätta](../../media/mtp-eval-63.png)

8. <span data-ttu-id="587a3-235">Grattis! du har öppnat din första slut punkt.</span><span class="sxs-lookup"><span data-stu-id="587a3-235">Congratulations, you've onboarded your first endpoint.</span></span>

   ![Bild of_the kommando rad där du får bekräftelse på att du har öppnat din första slut punkt.](../../media/mtp-eval-64.png)

9. <span data-ttu-id="587a3-238">Kopiera – klistra in identifierings testet från Microsoft Defender för slut punkts guiden.</span><span class="sxs-lookup"><span data-stu-id="587a3-238">Copy-paste the detection test from the Microsoft Defender for Endpoint wizard.</span></span>

   ![Bild of_the kör ett identifierings test steg där du bör Klicka på Kopiera för att kopiera det identifierings test som du vill klistra in i kommando tolken](../../media/mtp-eval-65.png)

10. <span data-ttu-id="587a3-240">Kopiera PowerShell-skriptet till en upphöjd kommando tolk och kör det.</span><span class="sxs-lookup"><span data-stu-id="587a3-240">Copy the PowerShell script to an elevated command prompt and run it.</span></span> 

    ![Bild of_command fråga var du bör kopiera PowerShell-skriptet till en upphöjd kommando tolk och köra det](../../media/mtp-eval-66.png)

11. <span data-ttu-id="587a3-242">Välj **börja använda Microsoft Defender för slut punkt** från guiden.</span><span class="sxs-lookup"><span data-stu-id="587a3-242">Select **Start using Microsoft Defender for Endpoint** from the Wizard.</span></span>

    ![Bild of_the bekräfta uppmaning i guiden där du bör Klicka på börja använda Microsoft Defender för slut punkt](../../media/mtp-eval-67.png)
 
12. <span data-ttu-id="587a3-244">Gå till [Microsoft Defender säkerhets Center](https://securitycenter.windows.com/).</span><span class="sxs-lookup"><span data-stu-id="587a3-244">Visit the [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span></span> <span data-ttu-id="587a3-245">Gå till **Inställningar** och välj sedan **avancerade funktioner**.</span><span class="sxs-lookup"><span data-stu-id="587a3-245">Go to **Settings** and then select **Advanced features**.</span></span> 

    ![Bild of_Microsoft Defender säkerhets Center-menyn inställningar där du bör välja avancerade funktioner](../../media/mtp-eval-68.png)

13. <span data-ttu-id="587a3-247">Aktivera integrationen med **Microsoft Defender för identiteten**.</span><span class="sxs-lookup"><span data-stu-id="587a3-247">Turn on the integration with **Microsoft Defender for Identity**.</span></span>  

    ![Bild of_Microsoft Defender säkerhets Center avancerade funktioner, alternativ för Microsoft Defender för identitet som du måste aktivera](../../media/mtp-eval-69.png)

14. <span data-ttu-id="587a3-249">Aktivera integrationen med **Office 365 Threat Intelligence**.</span><span class="sxs-lookup"><span data-stu-id="587a3-249">Turn on the integration with **Office 365 Threat Intelligence**.</span></span>

    ![Bild of_Microsoft Defender säkerhets Center avancerade funktioner, alternativ för Office 365 Threat Intelligence växla till att aktivera](../../media/mtp-eval-70.png)

15. <span data-ttu-id="587a3-251">Aktivera integrering med **säkerhet för Microsoft Cloud App**.</span><span class="sxs-lookup"><span data-stu-id="587a3-251">Turn on integration with **Microsoft Cloud App Security**.</span></span>

    ![Bild of_Microsoft Defender säkerhets Center avancerade funktioner, säkerhets alternativ för Microsoft Cloud App](../../media/mtp-eval-71.png)

16. <span data-ttu-id="587a3-253">Rulla nedåt och klicka på **Spara inställningar** för att bekräfta de nya integreringarna.</span><span class="sxs-lookup"><span data-stu-id="587a3-253">Scroll down and click **Save preferences** to confirm the new integrations.</span></span>

    ![Knappen bild of_Save inställningar som du måste klicka på](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-365-defender-service"></a><span data-ttu-id="587a3-255">Starta tjänsten Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="587a3-255">Start the Microsoft 365 Defender service</span></span>

>[!NOTE]
><span data-ttu-id="587a3-256">Från och med den 1 juni 2020, aktiverar Microsoft automatiskt Microsoft 365 Defender-funktioner för alla kvalificerade klient organisationer.</span><span class="sxs-lookup"><span data-stu-id="587a3-256">Starting June 1, 2020, Microsoft automatically enables Microsoft 365 Defender features for all eligible tenants.</span></span> <span data-ttu-id="587a3-257">Mer information finns i den här [artikeln i Microsoft Tech community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) .</span><span class="sxs-lookup"><span data-stu-id="587a3-257">See this [Microsoft Tech Community article on license eligibility](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) for details.</span></span> 


<span data-ttu-id="587a3-258">Gå till [Microsoft 365 säkerhets Center](https://security.microsoft.com/homepage).</span><span class="sxs-lookup"><span data-stu-id="587a3-258">Go to [Microsoft 365 Security Center](https://security.microsoft.com/homepage).</span></span> <span data-ttu-id="587a3-259">Navigera till **Inställningar** och välj sedan **Microsoft 365 Defender**.</span><span class="sxs-lookup"><span data-stu-id="587a3-259">Navigate to **Settings** and then select **Microsoft 365 Defender**.</span></span>

![<span data-ttu-id="587a3-260">Bild of_Microsoft 365 Defender alternativ skärm bild från sidan Inställningar för säkerhets Center för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="587a3-260">Image of_Microsoft 365 Defender option screenshot from the Microsoft 365 Security Center Settings page</span></span> ](../../media/mtp-eval-72b.png) <br>

<span data-ttu-id="587a3-261">En mer omfattande vägledning finns i [aktivera Microsoft 365 Defender](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="587a3-261">For a more comprehensive guidance, see [Turn on Microsoft 365 Defender](mtp-enable.md).</span></span> 

<span data-ttu-id="587a3-262">Grattis!</span><span class="sxs-lookup"><span data-stu-id="587a3-262">Congratulations!</span></span> <span data-ttu-id="587a3-263">Du har just skapat en utvärderings version av Microsoft 365 Defender eller pilot miljö!</span><span class="sxs-lookup"><span data-stu-id="587a3-263">You've just created your Microsoft 365 Defender trial lab or pilot environment!</span></span> <span data-ttu-id="587a3-264">Nu kan du bekanta dig med Microsoft 365 Defender-användargränssnittet!</span><span class="sxs-lookup"><span data-stu-id="587a3-264">Now you can familiarize yourself with the Microsoft 365 Defender user interface!</span></span> <span data-ttu-id="587a3-265">Se vad du kan lära dig från följande Microsoft 365 Defender interaktiva guide och hur du använder varje instrument panel för dina dagliga säkerhets åtgärder.</span><span class="sxs-lookup"><span data-stu-id="587a3-265">See what you can learn from the following Microsoft 365 Defender interactive guide and know how to use each dashboard for your day-to-day security operation tasks.</span></span>


>[!VIDEO https://aka.ms/MTP-Interactive-Guide]

<span data-ttu-id="587a3-266">Sedan kan du simulera en attack och se hur funktionerna för kors produkten identifieras, skapa aviseringar och automatiskt svara på en fillös attack på en slut punkt.</span><span class="sxs-lookup"><span data-stu-id="587a3-266">Next, you can simulate an attack and see how the cross product capabilities detect, create alerts, and automatically respond to a fileless attack on an endpoint.</span></span>

## <a name="next-step"></a><span data-ttu-id="587a3-267">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="587a3-267">Next step</span></span>
|[<span data-ttu-id="587a3-268">Fasen för attack simulering</span><span class="sxs-lookup"><span data-stu-id="587a3-268">Attack simulation phase</span></span>](mtp-pilot-simulate.md) | <span data-ttu-id="587a3-269">Kör angrepps simuleringen för din Microsoft 365 Defender pilot miljö.</span><span class="sxs-lookup"><span data-stu-id="587a3-269">Run the attack simulation for your Microsoft 365 Defender pilot environment.</span></span>
|:-------|:-----|
