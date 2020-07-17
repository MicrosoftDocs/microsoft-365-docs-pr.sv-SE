---
title: Konfigurera Microsoft Threat Protection-pelare för testlabbets miljö
description: Konfigurera Microsoft Threat Protection-pelare, Office 365 ATP, Azure ATP, Microsoft Cloud App Security och Microsoft Defender ATP för teststudiemiljön
keywords: konfigurera Testversionen av Microsoft Threat Protection, testkonfigurationen för Microsoft Threat Protection, konfigurera Microsoft Threat Protection-pelare, Microsoft Threat Protection-pelare
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 8a435b220343bd0353f2e0ef85ddf856ebf3e8aa
ms.sourcegitcommit: 7c1b34205746ff0690ffc774a74bdfd434256cf5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/07/2020
ms.locfileid: "45049946"
---
# <a name="configure-microsoft-threat-protection-pillars-for-your-trial-lab-environment"></a><span data-ttu-id="c7186-104">Konfigurera Microsoft Threat Protection-pelare för testlabbeta</span><span class="sxs-lookup"><span data-stu-id="c7186-104">Configure Microsoft Threat Protection pillars for your trial lab environment</span></span>

<span data-ttu-id="c7186-105">**Gäller:**</span><span class="sxs-lookup"><span data-stu-id="c7186-105">**Applies to:**</span></span>
- <span data-ttu-id="c7186-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="c7186-106">Microsoft Threat Protection</span></span>


<span data-ttu-id="c7186-107">Att skapa en testlabbmiljö för Microsoft Threat Protection och distribuera den är en trefasprocess:</span><span class="sxs-lookup"><span data-stu-id="c7186-107">Creating a Microsoft Threat Protection trial lab environment and deploying it is a three-phase process:</span></span>

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab environment" title="Förbered testlabbeta för Microsoft Threat Protection" />
      <br/><span data-ttu-id="c7186-109">Fas 1: Förbered</a></span><span class="sxs-lookup"><span data-stu-id="c7186-109">Phase 1: Prepare </a></span></span><br>
    </td>
     <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab environment" title="Konfigurera testlabbmiljön för Microsoft Threat Protection" />
      <br/><span data-ttu-id="c7186-111">Fas 2: Installation</a></span><span class="sxs-lookup"><span data-stu-id="c7186-111">Phase 2: Setup </a></span></span><br>
    </td>
    <td align="center" bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="Configure & Onboard" title="Konfigurera varje Microsoft Threat Protection-pelare för testlabbmiljön för Microsoft Threat Protection och slutpunkter ombord" />
      <br/><span data-ttu-id="c7186-113">Fas 3: Konfigurera & ombord</a></span><span class="sxs-lookup"><span data-stu-id="c7186-113">Phase 3: Configure & Onboard </a></span></span><br>
</td>


  </tr>
</table>

<span data-ttu-id="c7186-114">Du befinner dig för närvarande i konfigurationsfasen.</span><span class="sxs-lookup"><span data-stu-id="c7186-114">You are currently in the configuration phase.</span></span>


<span data-ttu-id="c7186-115">Förberedelse är nyckeln till en lyckad distribution.</span><span class="sxs-lookup"><span data-stu-id="c7186-115">Preparation is key to any successful deployment.</span></span> <span data-ttu-id="c7186-116">I den här artikeln får du vägledning om de punkter du behöver tänka på när du förbereder distributionen av Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="c7186-116">In this article, you'll be guided on the points you'll need to consider as you prepare to deploy Microsoft Defender ATP.</span></span>


## <a name="microsoft-threat-protection-pillars"></a><span data-ttu-id="c7186-117">Pelare för skydd av Microsofts hotskydd</span><span class="sxs-lookup"><span data-stu-id="c7186-117">Microsoft Threat Protection pillars</span></span>
<span data-ttu-id="c7186-118">Microsoft Threat Protection består av fyra pelare.</span><span class="sxs-lookup"><span data-stu-id="c7186-118">Microsoft Threat Protection consists of four pillars.</span></span> <span data-ttu-id="c7186-119">Även om en pelare redan kan ge värde till nätverksorganisationens säkerhet, ger aktivering av de fyra Microsoft Threat Protection-pelarna din organisation mest värde.</span><span class="sxs-lookup"><span data-stu-id="c7186-119">Although one pillar can already provide value to your network organization's security, enabling the four Microsoft Threat Protection pillars will give your organization the most value.</span></span>

![<span data-ttu-id="c7186-120">Image of_Microsoft Threat Protection-lösning för användare, Azure Advanced Threat Protection, för slutpunkter Microsoft Defender Advanced Threat Protection, för molnappar, Microsoft Cloud App Security och för data, Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c7186-120">Image of_Microsoft Threat Protection solution for users, Azure Advanced Threat Protection, for endpoints Microsoft Defender Advanced Threat Protection, for cloud apps, Microsoft Cloud App Security, and for data, Office 365 Advanced Threat Protection</span></span>  ](../../media/mtp-eval-31.png) <br>

<span data-ttu-id="c7186-121">Det här avsnittet hjälper dig att konfigurera:</span><span class="sxs-lookup"><span data-stu-id="c7186-121">This section will guide you to configure:</span></span>
-   <span data-ttu-id="c7186-122">Office 365 Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="c7186-122">Office 365 Advanced Threat Protection</span></span>
-   <span data-ttu-id="c7186-123">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c7186-123">Azure Advanced Threat Protection</span></span> 
-   <span data-ttu-id="c7186-124">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="c7186-124">Microsoft Cloud App Security</span></span>
-   <span data-ttu-id="c7186-125">Microsoft Defender Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="c7186-125">Microsoft Defender Advanced Threat Protection</span></span>


## <a name="configure-office-365-advanced-threat-protection"></a><span data-ttu-id="c7186-126">Konfigurera avancerat hotskydd för Office 365</span><span class="sxs-lookup"><span data-stu-id="c7186-126">Configure Office 365 Advanced Threat Protection</span></span>
>[!NOTE]
><span data-ttu-id="c7186-127">Hoppa över det här steget om du redan har aktiverat förhandsskydd för Office 365.Skip this step if you have already enabled Office 365 Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="c7186-127">Skip this step if you have already enabled Office 365 Advanced Threat Protection.</span></span> 

<span data-ttu-id="c7186-128">Det finns en PowerShell-modul som kallas *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* som hjälper till att avgöra några av dessa inställningar.</span><span class="sxs-lookup"><span data-stu-id="c7186-128">There is a PowerShell Module called the *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* that helps determine some of these settings.</span></span> <span data-ttu-id="c7186-129">När du kör som administratör i din klientorganisation, get-ORCAReport kommer att bidra till att generera en bedömning av anti-spam, anti-phish och andra inställningar meddelandehygien.</span><span class="sxs-lookup"><span data-stu-id="c7186-129">When run as an administrator in your tenant, get-ORCAReport will help generate an assessment of the anti-spam, anti-phish, and other message hygiene settings.</span></span> <span data-ttu-id="c7186-130">Du kan ladda ner denna modul från https://www.powershellgallery.com/packages/ORCA/ .</span><span class="sxs-lookup"><span data-stu-id="c7186-130">You can download this module from https://www.powershellgallery.com/packages/ORCA/.</span></span> 

1. <span data-ttu-id="c7186-131">Navigera till [Office 365 Security & Compliance Center](https://protection.office.com/homepage)Threat  >  **management**  >  **Policy**.</span><span class="sxs-lookup"><span data-stu-id="c7186-131">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Policy**.</span></span>
<span data-ttu-id="c7186-132">![Sidan Of_Office 365 Security & Compliance Center Threat management policy](../../media/mtp-eval-32.png)</span><span class="sxs-lookup"><span data-stu-id="c7186-132">![Image of_Office 365 Security & Compliance Center Threat management policy page](../../media/mtp-eval-32.png)</span></span> <br>
 
2. <span data-ttu-id="c7186-133">Klicka på **ATP-anti-nätfiske,** välj **Skapa** och fyll i principnamnet och beskrivningen.</span><span class="sxs-lookup"><span data-stu-id="c7186-133">Click **ATP anti-phishing**, select **Create** and fill in the policy name and description.</span></span> <span data-ttu-id="c7186-134">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="c7186-134">Click **Next**.</span></span>
<span data-ttu-id="c7186-135">![Bild of_Office 365 Security & Compliance Center anti-phishing-policysida där du kan namnge din policy](../../media/mtp-eval-33.png)</span><span class="sxs-lookup"><span data-stu-id="c7186-135">![Image of_Office 365 Security & Compliance Center anti-phishing policy page where you can name your policy](../../media/mtp-eval-33.png)</span></span> <br>

>[!NOTE]
><span data-ttu-id="c7186-136">Redigera din avancerade ATP-policy mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="c7186-136">Edit your Advanced ATP anti-phishing policy.</span></span> <span data-ttu-id="c7186-137">Ändra **avancerad nätfisketröskel** till **2 - Aggressiv**.</span><span class="sxs-lookup"><span data-stu-id="c7186-137">Change **Advanced Phishing Threshold** to **2 - Aggressive**.</span></span>
<br>

3. <span data-ttu-id="c7186-138">Klicka på den nedrullningsbara menyn **Lägg till ett villkor** och välj domänen/domänerna som mottagardomän.</span><span class="sxs-lookup"><span data-stu-id="c7186-138">Click the **Add a condition** drop-down menu and select your domain(s) as recipient domain.</span></span> <span data-ttu-id="c7186-139">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="c7186-139">Click **Next**.</span></span>
<span data-ttu-id="c7186-140">![Bild of_Office 365 Security & Compliance Center anti-phishing policy sida där du kan lägga till ett villkor för dess program](../../media/mtp-eval-34.png)</span><span class="sxs-lookup"><span data-stu-id="c7186-140">![Image of_Office 365 Security & Compliance Center anti-phishing policy page where you can add a condition for its application](../../media/mtp-eval-34.png)</span></span> <br>
 
4. <span data-ttu-id="c7186-141">Granska dina inställningar.</span><span class="sxs-lookup"><span data-stu-id="c7186-141">Review your settings.</span></span> <span data-ttu-id="c7186-142">Klicka på **Skapa den här principen** för att bekräfta.</span><span class="sxs-lookup"><span data-stu-id="c7186-142">Click **Create this policy** to confirm.</span></span> 
<span data-ttu-id="c7186-143">![Bild of_Office 365 Security & Compliance Center anti-phishing policy sida där du kan granska dina inställningar och klicka på knappen Skapa den här principen](../../media/mtp-eval-35.png)</span><span class="sxs-lookup"><span data-stu-id="c7186-143">![Image of_Office 365 Security & Compliance Center anti-phishing policy page where you can review your settings and click the create this policy button](../../media/mtp-eval-35.png)</span></span> <br>
 
5. <span data-ttu-id="c7186-144">Välj **ATP Säkra bilagor** och välj alternativet Aktivera **ATP för SharePoint, OneDrive och Microsoft Teams.**</span><span class="sxs-lookup"><span data-stu-id="c7186-144">Select **ATP Safe attachments** and select the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** option.</span></span>  
<span data-ttu-id="c7186-145">![Bild of_Office sidan 365 Security & Compliance Center där du kan aktivera ATP för SharePoint, OneDrive och Microsoft Teams](../../media/mtp-eval-36.png)</span><span class="sxs-lookup"><span data-stu-id="c7186-145">![Image of_Office 365 Security & Compliance Center page where you can turn on ATP for SharePoint, OneDrive, and Microsoft Teams](../../media/mtp-eval-36.png)</span></span> <br>

6. <span data-ttu-id="c7186-146">Klicka på ikonen + om du vill skapa en ny princip för säker bifogade filer och tillämpa den som mottagaredomän på dina domäner.</span><span class="sxs-lookup"><span data-stu-id="c7186-146">Click the + icon to create a new safe attachment policy, apply it as recipient domain to your domains.</span></span> <span data-ttu-id="c7186-147">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="c7186-147">Click **Save**.</span></span>
<span data-ttu-id="c7186-148">![Bild of_Office 365 Security & Compliance Center sida där du kan skapa en ny skapa en ny säker bilaga princip](../../media/mtp-eval-37.png)</span><span class="sxs-lookup"><span data-stu-id="c7186-148">![Image of_Office 365 Security & Compliance Center page where you can create a new create a new safe attachment policy](../../media/mtp-eval-37.png)</span></span> <br>
 
7. <span data-ttu-id="c7186-149">Välj sedan **atp-principen för säkra länkar** och klicka sedan på pennikonen för att redigera standardprincipen.</span><span class="sxs-lookup"><span data-stu-id="c7186-149">Next, select the **ATP Safe Links** policy, then click the pencil icon to edit the default policy.</span></span>

8. <span data-ttu-id="c7186-150">Kontrollera att alternativet **Spåra inte när användare klickar på säkra länkar** inte är markerat, medan resten av alternativen är markerade.</span><span class="sxs-lookup"><span data-stu-id="c7186-150">Make sure that the **Do not track when users click safe links** option is not selected, while the rest of the options are selected.</span></span> <span data-ttu-id="c7186-151">Mer information finns i inställningar för [säkra länkar.](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="c7186-151">See [Safe Links settings](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp?view=o365-worldwide) for details.</span></span> <span data-ttu-id="c7186-152">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="c7186-152">Click **Save**.</span></span> 
<span data-ttu-id="c7186-153">![Bild of_Office 365 Sidan Security & Compliance Center som visar att alternativet Spåra inte när användarna klickar säkert inte är markerat](../../media/mtp-eval-38.png)</span><span class="sxs-lookup"><span data-stu-id="c7186-153">![Image of_Office 365 Security & Compliance Center page which shows that the option Do not track when users click safe is not selected](../../media/mtp-eval-38.png)</span></span> <br>

9. <span data-ttu-id="c7186-154">Välj sedan policyn **mot skadlig kod,** välj standardikonen och välj pennikonen.</span><span class="sxs-lookup"><span data-stu-id="c7186-154">Next select the **Anti-malware** policy, select the default, and choose the pencil icon.</span></span>

10. <span data-ttu-id="c7186-155">Klicka på **Inställningar** och välj **Ja och använd standardmeddelandetexten** för att aktivera **svar på identifiering av skadlig kod**.</span><span class="sxs-lookup"><span data-stu-id="c7186-155">Click **Settings** and select **Yes and use the default notification text** to enable **Malware Detection Response**.</span></span> <span data-ttu-id="c7186-156">Aktivera **filtret Vanliga typer av bifogade filer.**</span><span class="sxs-lookup"><span data-stu-id="c7186-156">Turn the **Common Attachment Types Filter** on.</span></span> <span data-ttu-id="c7186-157">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="c7186-157">Click **Save**.</span></span>
<br><span data-ttu-id="c7186-158">![Bild of_Office sidan 365 Security & Compliance Center som visar att svar på identifiering av skadlig kod är aktiverat med standardmeddelande och filtret för vanliga typer av bifogade filer är aktiverat](../../media/mtp-eval-39.png)</span><span class="sxs-lookup"><span data-stu-id="c7186-158">![Image of_Office 365 Security & Compliance Center page which shows that the malware detection response is turned on with default notification and the common attachment types filter is turned on](../../media/mtp-eval-39.png)</span></span> <br>
  
11. <span data-ttu-id="c7186-159">Navigera till [Office 365 Security &](https://protection.office.com/homepage)  >  **Search**  >  **Audit-loggsökning för** efterlevnadscenter och aktivera granskning.</span><span class="sxs-lookup"><span data-stu-id="c7186-159">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Search** > **Audit log search** and turn Auditing on.</span></span>  
<span data-ttu-id="c7186-160">![Bild of_Office 365 Säkerhets- & compliance center-sidan där du kan aktivera granskningsloggsökningen](../../media/mtp-eval-40.png)</span><span class="sxs-lookup"><span data-stu-id="c7186-160">![Image of_Office 365 Security & Compliance Center page where you can turn on the Audit log search](../../media/mtp-eval-40.png)</span></span> <br>

12. <span data-ttu-id="c7186-161">Integrera Office 365 ATP med Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="c7186-161">Integrate Office 365 ATP with Microsoft Defender ATP.</span></span> <span data-ttu-id="c7186-162">Navigera till [Office 365 Security & Compliance Center](https://protection.office.com/homepage)Threat  >  **management**  >  **Explorer** och välj **WDATP-inställningar** längst upp till höger på skärmen.</span><span class="sxs-lookup"><span data-stu-id="c7186-162">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Explorer** and select **WDATP Settings** on the upper right corner of the screen.</span></span> <span data-ttu-id="c7186-163">Aktivera **Anslut till Windows ATP**i dialogrutan Microsoft Defender ATP-anslutning .</span><span class="sxs-lookup"><span data-stu-id="c7186-163">In the Microsoft Defender ATP connection dialog box, turn on **Connect to Windows ATP**.</span></span>
<span data-ttu-id="c7186-164">![Bild of_Office 365 Security & Compliance Center sida där du kan aktivera Windows Defender ATP-anslutning](../../media/mtp-eval-41.png)</span><span class="sxs-lookup"><span data-stu-id="c7186-164">![Image of_Office 365 Security & Compliance Center page where you can turn Windows Defender ATP connection on](../../media/mtp-eval-41.png)</span></span> <br>

## <a name="configure-azure-advanced-threat-protection"></a><span data-ttu-id="c7186-165">Konfigurera Avancerat hotskydd för Azure</span><span class="sxs-lookup"><span data-stu-id="c7186-165">Configure Azure Advanced Threat Protection</span></span>
>[!NOTE]
><span data-ttu-id="c7186-166">Hoppa över det här steget om du redan har aktiverat Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c7186-166">Skip this step if you have already enabled Azure Advanced Threat Protection</span></span>


1. <span data-ttu-id="c7186-167">Navigera till [Microsoft 365 Security Center](https://security.microsoft.com/info) > välja Fler **resurser**Azure Advanced  >  **Threat Protection**.</span><span class="sxs-lookup"><span data-stu-id="c7186-167">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > select **More Resources** > **Azure Advanced Threat Protection**.</span></span>
<span data-ttu-id="c7186-168">![Bild of_Microsoft 365 Security Center-sida där det finns ett alternativ för att öppna Azure Advanced Threat Protection](../../media/mtp-eval-42.png)</span><span class="sxs-lookup"><span data-stu-id="c7186-168">![Image of_Microsoft 365 Security Center page where there's an option to open Azure Advanced Threat Protection](../../media/mtp-eval-42.png)</span></span> <br>

2. <span data-ttu-id="c7186-169">Klicka på Skapa om du vill starta guiden Avancerat skydd mot Azure.Click **Create** to start the Azure Advanced Threat Protection wizard.</span><span class="sxs-lookup"><span data-stu-id="c7186-169">Click **Create** to start the Azure Advanced Threat Protection wizard.</span></span> 
<br><span data-ttu-id="c7186-170">![Bild of_Azure guidesida för avancerat skydd mot hot där du ska klicka på Knappen Skapa](../../media/mtp-eval-43.png)</span><span class="sxs-lookup"><span data-stu-id="c7186-170">![Image of_Azure Advanced Threat Protection wizard page where you should click Create button](../../media/mtp-eval-43.png)</span></span> <br>

3. <span data-ttu-id="c7186-171">Välj **Ange ett användarnamn och lösenord för att ansluta till Active Directory-skogen**.</span><span class="sxs-lookup"><span data-stu-id="c7186-171">Choose **Provide a username and password to connect to your Active Directory forest**.</span></span>  
<span data-ttu-id="c7186-172">![Välkommen sida för of_Azure avancerat skydd mot skydd](../../media/mtp-eval-44.png)</span><span class="sxs-lookup"><span data-stu-id="c7186-172">![Image of_Azure Advanced Threat Protection welcome page](../../media/mtp-eval-44.png)</span></span> <br>

4. <span data-ttu-id="c7186-173">Ange lokala autentiseringsuppgifter för Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c7186-173">Enter your Active Directory on-premises credentials.</span></span> <span data-ttu-id="c7186-174">Detta kan vara alla användarkonton som har läsbehörighet till Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c7186-174">This can be any user account that has read access to Active Directory.</span></span>
<span data-ttu-id="c7186-175">![Bild of_Azure sidan Advanced Threat Protection Directory services där du bör placera dina autentiseringsuppgifter](../../media/mtp-eval-45.png)</span><span class="sxs-lookup"><span data-stu-id="c7186-175">![Image of_Azure Advanced Threat Protection Directory services page where you should put your credentials](../../media/mtp-eval-45.png)</span></span> <br>

5. <span data-ttu-id="c7186-176">Välj sedan **Hämta sensorinstallation och** överför filen till domänkontrollanten.</span><span class="sxs-lookup"><span data-stu-id="c7186-176">Next, choose **Download Sensor Setup** and transfer file to your domain controller.</span></span> 
<span data-ttu-id="c7186-177">![Bild of_Azure sidan Avancerat skydd mot hot där du kan välja Inställningar för hämtningssensor](../../media/mtp-eval-46.png)</span><span class="sxs-lookup"><span data-stu-id="c7186-177">![Image of_Azure Advanced Threat Protection page where you can select Download Sensor Setup](../../media/mtp-eval-46.png)</span></span> <br>

6. <span data-ttu-id="c7186-178">Kör installationen av Azure ATP-sensor och börja följa guiden.</span><span class="sxs-lookup"><span data-stu-id="c7186-178">Execute the Azure ATP Sensor Setup and begin following the wizard.</span></span>
<br><span data-ttu-id="c7186-179">![Bild of_Azure sidan Avancerat skydd mot hot där du ska klicka bredvid för att följa guiden Azure ATP-sensor](../../media/mtp-eval-47.png)</span><span class="sxs-lookup"><span data-stu-id="c7186-179">![Image of_Azure Advanced Threat Protection page where you should click next to follow the Azure ATP sensor wizard](../../media/mtp-eval-47.png)</span></span> <br>
 
7. <span data-ttu-id="c7186-180">Klicka på **Nästa** vid sensordistributionstypen.</span><span class="sxs-lookup"><span data-stu-id="c7186-180">Click **Next** at the sensor deployment type.</span></span>
<br><span data-ttu-id="c7186-181">![Bild of_Azure sidan Avancerat skydd mot hot där du ska klicka bredvid för att följa guiden Azure ATP-sensor](../../media/mtp-eval-48.png)</span><span class="sxs-lookup"><span data-stu-id="c7186-181">![Image of_Azure Advanced Threat Protection page where you should click next to follow the Azure ATP sensor wizard](../../media/mtp-eval-48.png)</span></span> <br>
 
8. <span data-ttu-id="c7186-182">Kopiera åtkomstnyckeln som du behöver för att ange den nästa i guiden.</span><span class="sxs-lookup"><span data-stu-id="c7186-182">Copy the access key as you will need to enter it next in the Wizard.</span></span>
<span data-ttu-id="c7186-183">![Bild of_the sensorsida där du ska kopiera åtkomstnyckeln som du behöver ange på nästa guidesida för Azure ATP-sensorinstallation](../../media/mtp-eval-49.png)</span><span class="sxs-lookup"><span data-stu-id="c7186-183">![Image of_the sensors page where you should copy the access key that you need to enter in the next Azure ATP sensor setup wizard page](../../media/mtp-eval-49.png)</span></span> <br>
 
9. <span data-ttu-id="c7186-184">Kopiera åtkomstnyckeln till guiden och klicka på **Installera**.</span><span class="sxs-lookup"><span data-stu-id="c7186-184">Copy the access key into the Wizard and click **Install**.</span></span> 
<br><span data-ttu-id="c7186-185">![Bild of_Azure Avancerad hotskydd Azure ATP sensor guide sida där du bör ange åtkomstnyckeln och klicka sedan på installationsknappen](../../media/mtp-eval-50.png)</span><span class="sxs-lookup"><span data-stu-id="c7186-185">![Image of_Azure Advanced Threat Protection Azure ATP sensor wizard page where you should provide the access key and then click the install button](../../media/mtp-eval-50.png)</span></span> <br>

10. <span data-ttu-id="c7186-186">Grattis, du har konfigurerat Azure Advanced Threat Protection på domänkontrollanten.</span><span class="sxs-lookup"><span data-stu-id="c7186-186">Congratulations, you have successfully configured Azure Advanced Threat Protection on your domain controller.</span></span>
<span data-ttu-id="c7186-187">![Avbildning of_Azure Avancerat skydd Mot Azure ATP-sensorguiden installationsavslutning där du ska klicka på knappen Slutför](../../media/mtp-eval-51.png)</span><span class="sxs-lookup"><span data-stu-id="c7186-187">![Image of_Azure Advanced Threat Protection Azure ATP sensor wizard installation completion where you should click the finish button](../../media/mtp-eval-51.png)</span></span> <br>
 
11. <span data-ttu-id="c7186-188">Under avsnittet [Azure Azure ATP-inställningar](https://go.microsoft.com/fwlink/?linkid=2040449) väljer du **Windows Defender ATP**och aktiverar sedan växlingsknappen.</span><span class="sxs-lookup"><span data-stu-id="c7186-188">Under the [Azure Azure ATP](https://go.microsoft.com/fwlink/?linkid=2040449) settings section, select **Windows Defender ATP**, then turn the toggle on.</span></span> <span data-ttu-id="c7186-189">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="c7186-189">Click **Save**.</span></span> 
<span data-ttu-id="c7186-190">![Avbildning of_the azure azure-atp-inställningssida där du ska aktivera Windows Defender ATP-växlingsknappen](../../media/mtp-eval-52.png)</span><span class="sxs-lookup"><span data-stu-id="c7186-190">![Image of_the Azure Azure ATP settings page where you should turn the Windows Defender ATP toggle on](../../media/mtp-eval-52.png)</span></span> <br>

>[!NOTE]
><span data-ttu-id="c7186-191">Windows Defender ATP har bytt namn till Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="c7186-191">Windows Defender ATP has been rebranded as Microsoft Defender ATP.</span></span> <span data-ttu-id="c7186-192">Omprofilering förändringar över alla våra portaler håller på att rullas ut för konsekvens.</span><span class="sxs-lookup"><span data-stu-id="c7186-192">Rebranding changes across all of our portals are being rolled out the for consistency.</span></span>


## <a name="configure-microsoft-cloud-app-security"></a><span data-ttu-id="c7186-193">Konfigurera Säkerhet för Microsoft Cloud-appar</span><span class="sxs-lookup"><span data-stu-id="c7186-193">Configure Microsoft Cloud App Security</span></span>
>[!NOTE]
><span data-ttu-id="c7186-194">Hoppa över det här steget om du redan har aktiverat Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="c7186-194">Skip this step if you have already enabled Microsoft Cloud App Security.</span></span> 

1. <span data-ttu-id="c7186-195">Navigera till [Microsoft 365 Security Center](https://security.microsoft.com/info)Fler  >  **resurser**Microsoft Cloud  >  **App Security**.</span><span class="sxs-lookup"><span data-stu-id="c7186-195">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Cloud App Security**.</span></span>
<span data-ttu-id="c7186-196">![Bild of_Microsoft 365 Security Center-sida där du kan se Microsoft Cloud App-kort och klicka på knappen Öppna](../../media/mtp-eval-53.png)</span><span class="sxs-lookup"><span data-stu-id="c7186-196">![Image of_Microsoft 365 Security Center page where you can see Microsoft Cloud App card and should click the open button](../../media/mtp-eval-53.png)</span></span> <br>

2. <span data-ttu-id="c7186-197">Vid informationsfrågan om att integrera Azure ATP väljer du **Aktivera Azure ATP-dataintegration**.</span><span class="sxs-lookup"><span data-stu-id="c7186-197">At the information prompt to integrate Azure ATP, select **Enable Azure ATP data integration**.</span></span> 
<br><span data-ttu-id="c7186-198">![Avbildning of_the informationsfråga för att integrera Azure ATP där du bör välja länken Aktivera Azure ATP-dataintegration](../../media/mtp-eval-54.png)</span><span class="sxs-lookup"><span data-stu-id="c7186-198">![Image of_the information prompt to integrate Azure ATP where you should select the Enable Azure ATP data integration link](../../media/mtp-eval-54.png)</span></span> <br>

>[!NOTE]
><span data-ttu-id="c7186-199">Om du inte ser den här prompten kan det innebära att din Azure ATP-dataintegrering redan har aktiverats.</span><span class="sxs-lookup"><span data-stu-id="c7186-199">If you don’t see this prompt, it might mean that your Azure ATP data integration has already been enabled.</span></span> <span data-ttu-id="c7186-200">Om du är osäker kontaktar du dock IT-administratören för att bekräfta.</span><span class="sxs-lookup"><span data-stu-id="c7186-200">However, if you are not sure, contact your IT Administrator to confirm.</span></span> 

3. <span data-ttu-id="c7186-201">Gå till **Inställningar**, aktivera växlingsknappen för **Azure ATP-integrering** och klicka sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="c7186-201">Go to **Settings**, turn the **Azure ATP integration** toggle on, then click **Save**.</span></span> 
<span data-ttu-id="c7186-202">![Bild of_the inställningssida där du ska aktivera växlingsknappen för Azure ATP-integrering och klicka sedan på spara](../../media/mtp-eval-55.png)</span><span class="sxs-lookup"><span data-stu-id="c7186-202">![Image of_the settings page where you should turn the Azure ATP integration toggle on then click save](../../media/mtp-eval-55.png)</span></span> <br>
>[!NOTE]
><span data-ttu-id="c7186-203">För nya Azure ATP-instanser aktiveras den här integrationsväxlingen automatiskt.</span><span class="sxs-lookup"><span data-stu-id="c7186-203">For new Azure ATP instances, this integration toggle is automatically turned on.</span></span> <span data-ttu-id="c7186-204">Bekräfta att din Azure ATP-integrering har aktiverats innan du går vidare till nästa steg.</span><span class="sxs-lookup"><span data-stu-id="c7186-204">Confirm that your Azure ATP integration has been enabled before you proceed to the next step.</span></span>
 
4. <span data-ttu-id="c7186-205">Under inställningarna för molnidentifiering väljer du **Microsoft Defender ATP-integrering**och aktiverar integreringen.</span><span class="sxs-lookup"><span data-stu-id="c7186-205">Under the Cloud discovery settings, select **Microsoft Defender ATP integration**, then enable the integration.</span></span> <span data-ttu-id="c7186-206">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="c7186-206">Click **Save**.</span></span>
<span data-ttu-id="c7186-207">![Bild of_the Microsoft Defender ATP-sida där kryssrutan blockera oregistrerade appar under Microsoft Defender ATP-integrering är markerad.</span><span class="sxs-lookup"><span data-stu-id="c7186-207">![Image of_the Microsoft Defender ATP page where the block unsanctioned apps checkbox under Microsoft Defender ATP integration is selected.</span></span> <span data-ttu-id="c7186-208">Klicka på Spara.](../../media/mtp-eval-56.png)</span><span class="sxs-lookup"><span data-stu-id="c7186-208">Click save.](../../media/mtp-eval-56.png)</span></span> <br>

5. <span data-ttu-id="c7186-209">Under Molnidentifieringsinställningar väljer du **Användarberikande**och aktiverar sedan integreringen med Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c7186-209">Under Cloud discovery settings, select **User enrichment**, then enable the integration with Azure Active Directory.</span></span>
<span data-ttu-id="c7186-210">![Avbildning av avsnittet Användares anrikning där kryssrutan berikade identifierade användaridentifierare med Azure Active Directory-användarnamn är markerat](../../media/mtp-eval-57.png)</span><span class="sxs-lookup"><span data-stu-id="c7186-210">![Image of User enrichment section where the enrich discovered user identifiers with Azure Active Directory usernames checkbox is selected](../../media/mtp-eval-57.png)</span></span> <br>

## <a name="configure-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="c7186-211">Konfigurera avancerat hotskydd för Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="c7186-211">Configure Microsoft Defender Advanced Threat Protection</span></span>
>[!NOTE]
><span data-ttu-id="c7186-212">Hoppa över det här steget om du redan har aktiverat Microsoft Defender Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="c7186-212">Skip this step if you have already enabled Microsoft Defender Advanced Threat Protection.</span></span>

1. <span data-ttu-id="c7186-213">Navigera till [Microsoft 365 Security Center](https://security.microsoft.com/info)Mer  >  **resurser**Microsoft Defender  >  **Security Center**.</span><span class="sxs-lookup"><span data-stu-id="c7186-213">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Defender Security Center**.</span></span> <span data-ttu-id="c7186-214">Klicka på **Öppna**.</span><span class="sxs-lookup"><span data-stu-id="c7186-214">Click **Open**.</span></span>
<br><span data-ttu-id="c7186-215">![Bild of_Microsoft alternativet Defender Security Center på sidan Microsoft 365 Security Center](../../media/mtp-eval-58.png)</span><span class="sxs-lookup"><span data-stu-id="c7186-215">![Image of_Microsoft Defender Security Center option in the Microsoft 365 Security Center page](../../media/mtp-eval-58.png)</span></span> <br>
 
2. <span data-ttu-id="c7186-216">Följ guiden Avancerat skydd mot microsoft defender.Follow the Microsoft Defender Advanced Threat Protection wizard.</span><span class="sxs-lookup"><span data-stu-id="c7186-216">Follow the Microsoft Defender Advanced Threat Protection wizard.</span></span> <span data-ttu-id="c7186-217">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="c7186-217">Click **Next**.</span></span> 
<br><span data-ttu-id="c7186-218">![Sidan Välkommen of_the Microsoft Defender Security Center](../../media/mtp-eval-59.png)</span><span class="sxs-lookup"><span data-stu-id="c7186-218">![Image of_the Microsoft Defender Security Center welcome wizard page](../../media/mtp-eval-59.png)</span></span> <br>

3. <span data-ttu-id="c7186-219">Välj baserat på önskad plats för datalagring, datalagringsprincip, organisationsstorlek och opt-in för förhandsversionsfunktioner.</span><span class="sxs-lookup"><span data-stu-id="c7186-219">Choose based on your preferred data storage location, data retention policy, organization size, and opt-in for preview features.</span></span> 
<br><span data-ttu-id="c7186-220">![Bild of_the sida för att välja datalagringsland, lagringsprincip och organisationsstorlek.</span><span class="sxs-lookup"><span data-stu-id="c7186-220">![Image of_the page to select your data storage country, retention policy, and organization size.</span></span> <span data-ttu-id="c7186-221">Klicka på nästa när du är klar med markeringen.](../../media/mtp-eval-60.png)</span><span class="sxs-lookup"><span data-stu-id="c7186-221">Click next when you're done selecting.](../../media/mtp-eval-60.png)</span></span> <br>
>[!NOTE]
><span data-ttu-id="c7186-222">Du kan inte ändra vissa inställningar, till exempel datalagringsplats, efteråt.</span><span class="sxs-lookup"><span data-stu-id="c7186-222">You cannot change some of the settings, like data storage location, afterwards.</span></span> 
<br>

<span data-ttu-id="c7186-223">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="c7186-223">Click **Next**.</span></span> 

4. <span data-ttu-id="c7186-224">Klicka på **Fortsätt** så etablerar microsoft defender ATP-klienten.</span><span class="sxs-lookup"><span data-stu-id="c7186-224">Click **Continue** and it will provision your Microsoft Defender ATP tenant.</span></span>
<br><span data-ttu-id="c7186-225">![Bild of_the sida som uppmanar dig att klicka på knappen Fortsätt för att skapa din molninstans](../../media/mtp-eval-61.png)</span><span class="sxs-lookup"><span data-stu-id="c7186-225">![Image of_the page prompting you click the continue button to create your cloud instance](../../media/mtp-eval-61.png)</span></span> <br>

5. <span data-ttu-id="c7186-226">Ombord på dina slutpunkter via grupprinciper, Microsoft Slutpunktshanteraren eller genom att köra ett lokalt skript till Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="c7186-226">Onboard your endpoints through Group Policies, Microsoft Endpoint Manager or by running a local script to Microsoft Defender ATP.</span></span> <span data-ttu-id="c7186-227">För enkelhetens skull använder den här guiden det lokala skriptet.</span><span class="sxs-lookup"><span data-stu-id="c7186-227">For simplicity, this guide uses the local script.</span></span>

6. <span data-ttu-id="c7186-228">Klicka på **Hämta paket** och kopiera introduktionsskriptet till slutpunkterna.</span><span class="sxs-lookup"><span data-stu-id="c7186-228">Click **Download package** and copy the onboarding script to your endpoint(s).</span></span>  
<br><span data-ttu-id="c7186-229">![Bild of_page du uppmanas att klicka på knappen Hämta paket för att kopiera introduktionsskriptet till slutpunkten eller slutpunkterna](../../media/mtp-eval-62.png)</span><span class="sxs-lookup"><span data-stu-id="c7186-229">![Image of_page prompting you click the Download package button to copy the onboarding script to your endpoint or endpoints](../../media/mtp-eval-62.png)</span></span> <br>

7. <span data-ttu-id="c7186-230">På slutpunkten kör du introduktionsskriptet som administratör och väljer Y.</span><span class="sxs-lookup"><span data-stu-id="c7186-230">On your endpoint, run the onboarding script as Administrator and choose Y.</span></span>
<br><span data-ttu-id="c7186-231">![Bild of_the kommandorad där du kör introduktionsskriptet och väljer Y att fortsätta](../../media/mtp-eval-63.png)</span><span class="sxs-lookup"><span data-stu-id="c7186-231">![Image of_the commandline where you run the onboarding script and choose Y to proceed](../../media/mtp-eval-63.png)</span></span> <br>

8. <span data-ttu-id="c7186-232">Grattis, du har onboarded din första slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="c7186-232">Congratulations, you have onboarded your first endpoint.</span></span>  
<br>![Bild of_the kommandorad där du får en bekräftelse på att du har lagt till din första slutpunkt.](../../media/mtp-eval-64.png) <br>

9. <span data-ttu-id="c7186-235">Kopiera in identifieringstestet från Atp-guiden Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="c7186-235">Copy-paste the detection test from the Microsoft Defender ATP wizard.</span></span>
<br><span data-ttu-id="c7186-236">![Bild of_the köra ett teststeg där du bör klicka på Kopiera för att kopiera det identifieringstestskript som du bör klistra in i kommandotolken](../../media/mtp-eval-65.png)</span><span class="sxs-lookup"><span data-stu-id="c7186-236">![Image of_the run a detection test step where you should click Copy to copy the detection test script that you should paste in the command prompt](../../media/mtp-eval-65.png)</span></span> <br>

10. <span data-ttu-id="c7186-237">Kopiera PowerShell-skriptet till en upphöjd kommandotolk och kör det.</span><span class="sxs-lookup"><span data-stu-id="c7186-237">Copy the PowerShell script to an elevated command prompt and run it.</span></span> 
<br><span data-ttu-id="c7186-238">![Bild of_command fråga om var du ska kopiera PowerShell-skriptet till en upphöjd kommandotolk och köra den](../../media/mtp-eval-66.png)</span><span class="sxs-lookup"><span data-stu-id="c7186-238">![Image of_command prompt where you should copy the PowerShell script to an elevated command prompt and run it](../../media/mtp-eval-66.png)</span></span> <br>

11. <span data-ttu-id="c7186-239">Välj **Börja använda Microsoft Defender ATP** i guiden.</span><span class="sxs-lookup"><span data-stu-id="c7186-239">Select **Start using Microsoft Defender ATP** from the Wizard.</span></span>
<br><span data-ttu-id="c7186-240">![Bild of_the bekräftelsefråga från guiden där du bör klicka på Börja använda Microsoft Defender ATP](../../media/mtp-eval-67.png)</span><span class="sxs-lookup"><span data-stu-id="c7186-240">![Image of_the confirmation prompt from the wizard where you should click Start using Microsoft Defender ATP](../../media/mtp-eval-67.png)</span></span> <br>
 
12. <span data-ttu-id="c7186-241">Besök [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span><span class="sxs-lookup"><span data-stu-id="c7186-241">Visit the [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span></span> <span data-ttu-id="c7186-242">Gå till **Inställningar** och välj sedan **Avancerade funktioner**.</span><span class="sxs-lookup"><span data-stu-id="c7186-242">Go to **Settings** and then select **Advanced features**.</span></span> 
<br><span data-ttu-id="c7186-243">![Bild of_Microsoft menyn Inställningar för Defender Security Center där du bör välja Avancerade funktioner](../../media/mtp-eval-68.png)</span><span class="sxs-lookup"><span data-stu-id="c7186-243">![Image of_Microsoft Defender Security Center Settings menu where you should select Advanced features](../../media/mtp-eval-68.png)</span></span> <br>

13. <span data-ttu-id="c7186-244">Aktivera integreringen med **Azure Advanced Threat Protection**.</span><span class="sxs-lookup"><span data-stu-id="c7186-244">Turn on the integration with **Azure Advanced Threat Protection**.</span></span>  
<br><span data-ttu-id="c7186-245">![Avbildning of_Microsoft Defender Security Center Avancerade funktioner, Azure Advanced Threat Protection alternativ växla som du behöver för att aktivera](../../media/mtp-eval-69.png)</span><span class="sxs-lookup"><span data-stu-id="c7186-245">![Image of_Microsoft Defender Security Center Advanced features, Azure Advanced Threat Protection option toggle that you need to turn on](../../media/mtp-eval-69.png)</span></span> <br>

14. <span data-ttu-id="c7186-246">Aktivera integreringen med **Office 365 Threat Intelligence**.</span><span class="sxs-lookup"><span data-stu-id="c7186-246">Turn on the integration with **Office 365 Threat Intelligence**.</span></span>
<br><span data-ttu-id="c7186-247">![Bild of_Microsoft Defender Security Center Avancerade funktioner, Office 365 Threat Intelligence-alternativet växla som du behöver aktivera](../../media/mtp-eval-70.png)</span><span class="sxs-lookup"><span data-stu-id="c7186-247">![Image of_Microsoft Defender Security Center Advanced features, Office 365 Threat Intelligence option toggle that you need to turn on](../../media/mtp-eval-70.png)</span></span> <br>

15. <span data-ttu-id="c7186-248">Aktivera integrering med **Microsoft Cloud App Security**.</span><span class="sxs-lookup"><span data-stu-id="c7186-248">Turn on integration with **Microsoft Cloud App Security**.</span></span>
<br><span data-ttu-id="c7186-249">![Bild of_Microsoft Defender Security Center Avancerade funktioner, Microsoft Cloud App Security-alternativet växla som du behöver aktivera](../../media/mtp-eval-71.png)</span><span class="sxs-lookup"><span data-stu-id="c7186-249">![Image of_Microsoft Defender Security Center Advanced features, Microsoft Cloud App Security option toggle that you need to turn on](../../media/mtp-eval-71.png)</span></span> <br>

16. <span data-ttu-id="c7186-250">Bläddra nedåt och klicka på **Spara inställningar** för att bekräfta de nya integreringarna.</span><span class="sxs-lookup"><span data-stu-id="c7186-250">Scroll down and click **Save preferences** to confirm the new integrations.</span></span>
<br><span data-ttu-id="c7186-251">![Knappen Bild of_Save inställningar som du måste klicka på](../../media/mtp-eval-72.png)</span><span class="sxs-lookup"><span data-stu-id="c7186-251">![Image of_Save preferences button that you need to click](../../media/mtp-eval-72.png)</span></span> <br>

## <a name="start-the-microsoft-threat-protection-service"></a><span data-ttu-id="c7186-252">Starta tjänsten Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c7186-252">Start the Microsoft Threat Protection service</span></span>
>[!NOTE]
><span data-ttu-id="c7186-253">Från och med den 1 juni 2020 aktiverar Microsoft automatiskt Microsoft Threat Protection-funktioner för alla berättigade klienter.</span><span class="sxs-lookup"><span data-stu-id="c7186-253">Starting June 1, 2020, Microsoft automatically enables Microsoft Threat Protection features for all eligible tenants.</span></span> <span data-ttu-id="c7186-254">Mer information finns i den här [artikeln i Microsoft Tech Community om licensberättigande.](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426)</span><span class="sxs-lookup"><span data-stu-id="c7186-254">See this [Microsoft Tech Community article on license eligibility](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) for details.</span></span> 
<br>

<span data-ttu-id="c7186-255">Gå till [Microsoft 365 Security Center](https://security.microsoft.com/homepage).</span><span class="sxs-lookup"><span data-stu-id="c7186-255">Go to [Microsoft 365 Security Center](https://security.microsoft.com/homepage).</span></span> <span data-ttu-id="c7186-256">Navigera till **Inställningar** och välj sedan **Microsoft Threat Protection**.</span><span class="sxs-lookup"><span data-stu-id="c7186-256">Navigate to **Settings** and then select **Microsoft Threat Protection**.</span></span>
<br><span data-ttu-id="c7186-257">![Bild of_Microsoft alternativ för skydd av hot från sidan Inställningar för Microsoft 365 Security Center](../../media/mtp-eval-72b.png)</span><span class="sxs-lookup"><span data-stu-id="c7186-257">![Image of_Microsoft Threat Protection option screenshot from the Microsoft 365 Security Center Settings page ](../../media/mtp-eval-72b.png)</span></span> <br>

<span data-ttu-id="c7186-258">Mer omfattande vägledning finns i [Aktivera Microsoft Threat Protection](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="c7186-258">For a more comprehensive guidance, see [Turn on Microsoft Threat Protection](mtp-enable.md).</span></span> 

<span data-ttu-id="c7186-259">Grattis!</span><span class="sxs-lookup"><span data-stu-id="c7186-259">Congratulations!</span></span> <span data-ttu-id="c7186-260">Du har precis skapat testlabbmiljön för Microsoft Threat Protection!</span><span class="sxs-lookup"><span data-stu-id="c7186-260">You've just created your Microsoft Threat Protection trial lab environment!</span></span> <span data-ttu-id="c7186-261">Nu kan du bekanta dig med användargränssnittet i Microsoft Threat Protection!</span><span class="sxs-lookup"><span data-stu-id="c7186-261">Now you can familiarize yourself with the Microsoft Threat Protection user interface!</span></span> <span data-ttu-id="c7186-262">Se vad du kan lära dig av och veta hur du använder varje instrumentpanel för dina dagliga säkerhetsoperationsuppgifter: [Interaktiv guide för Microsoft Threat Protection](https://aka.ms/MTP-Interactive-Guide).</span><span class="sxs-lookup"><span data-stu-id="c7186-262">See what you can learn from and know how to use each dashboards for your day-to-day security operation tasks: [Microsoft Threat Protection interactive guide](https://aka.ms/MTP-Interactive-Guide).</span></span>

<span data-ttu-id="c7186-263">Därefter kan du simulera en attack och se hur cross-produktfunktionerna identifierar, skapar aviseringar och automatiskt svarar på en fillös attack på en slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="c7186-263">Next, you can simulate an attack and see how the cross product capabilities detect, create alerts, and automatically respond to a fileless attack on an endpoint.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c7186-264">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="c7186-264">Next steps</span></span>
<span data-ttu-id="c7186-265">[Generera en testavisering](generate-test-alert.md).</span><span class="sxs-lookup"><span data-stu-id="c7186-265">[Generate a test alert](generate-test-alert.md).</span></span>
