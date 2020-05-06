---
title: Konfigurera Microsoft Threat Protection-pelare för testlabbetamiljön
description: Konfigurera Microsoft Threat Protection-pelare, Office 365 ATP, Azure ATP, Microsoft Cloud App Security och Microsoft Defender ATP för testlabbetamiljön
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
ms.openlocfilehash: 68d8f06803d75c3f89cae6fa7998734fd54084ca
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049515"
---
# <a name="configure-microsoft-threat-protection-pillars-for-your-trial-lab-environment"></a><span data-ttu-id="fd1b0-104">Konfigurera Microsoft Threat Protection-pelare för testlabbeta</span><span class="sxs-lookup"><span data-stu-id="fd1b0-104">Configure Microsoft Threat Protection pillars for your trial lab environment</span></span>

<span data-ttu-id="fd1b0-105">**Gäller:**</span><span class="sxs-lookup"><span data-stu-id="fd1b0-105">**Applies to:**</span></span>
- <span data-ttu-id="fd1b0-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="fd1b0-106">Microsoft Threat Protection</span></span>


<span data-ttu-id="fd1b0-107">Att skapa en testlabbmiljö för Microsoft Threat Protection och distribuera den är en trefasprocess:</span><span class="sxs-lookup"><span data-stu-id="fd1b0-107">Creating a Microsoft Threat Protection trial lab environment and deploying it is a three-phase process:</span></span>

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab environment" title="Förbereda testlabbeta för Microsoft Threat Protection" />
      <br/><span data-ttu-id="fd1b0-109">Fas 1: Förbered</a></span><span class="sxs-lookup"><span data-stu-id="fd1b0-109">Phase 1: Prepare </a></span></span><br>
    </td>
     <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab environment" title="Konfigurera testlabbeta för Microsoft Threat Protection" />
      <br/><span data-ttu-id="fd1b0-111">Fas 2: Installation</a></span><span class="sxs-lookup"><span data-stu-id="fd1b0-111">Phase 2: Setup </a></span></span><br>
    </td>
    <td align="center" bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="Configure & Onboard" title="Konfigurera varje Microsoft Threat Protection-pelare för testlabbmiljön för Microsoft Threat Protection och slutpunkter ombord" />
      <br/><span data-ttu-id="fd1b0-113">Fas 3: Konfigurera & ombord</a></span><span class="sxs-lookup"><span data-stu-id="fd1b0-113">Phase 3: Configure & Onboard </a></span></span><br>
</td>


  </tr>
</table>

<span data-ttu-id="fd1b0-114">Du befinner dig för närvarande i konfigurationsfasen.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-114">You are currently in the configuration phase.</span></span>


<span data-ttu-id="fd1b0-115">Förberedelse är nyckeln till en lyckad distribution.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-115">Preparation is key to any successful deployment.</span></span> <span data-ttu-id="fd1b0-116">I den här artikeln får du vägledning på de punkter du behöver tänka på när du förbereder distributionen av Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-116">In this article, you'll be guided on the points you'll need to consider as you prepare to deploy Microsoft Defender ATP.</span></span>


## <a name="microsoft-threat-protection-pillars"></a><span data-ttu-id="fd1b0-117">Pelare för skydd av Microsofts hotskydd</span><span class="sxs-lookup"><span data-stu-id="fd1b0-117">Microsoft Threat Protection pillars</span></span>
<span data-ttu-id="fd1b0-118">Microsoft Threat Protection består av fyra pelare.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-118">Microsoft Threat Protection consists of four pillars.</span></span> <span data-ttu-id="fd1b0-119">Även om en pelare redan kan ge värde till nätverksorganisationens säkerhet, ger aktivering av de fyra Microsoft Threat Protection-pelarna din organisation mest värde.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-119">Although one pillar can already provide value to your network organization's security, enabling the four Microsoft Threat Protection pillars will give your organization the most value.</span></span>

![Bild of_page](../../media/mtp-eval-31.png) <br>

<span data-ttu-id="fd1b0-121">Det här avsnittet hjälper dig att konfigurera:</span><span class="sxs-lookup"><span data-stu-id="fd1b0-121">This section will guide you to configure:</span></span>
-   <span data-ttu-id="fd1b0-122">Office 365 Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="fd1b0-122">Office 365 Advanced Threat Protection</span></span>
-   <span data-ttu-id="fd1b0-123">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="fd1b0-123">Azure Advanced Threat Protection</span></span> 
-   <span data-ttu-id="fd1b0-124">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="fd1b0-124">Microsoft Cloud App Security</span></span>
-   <span data-ttu-id="fd1b0-125">Microsoft Defender Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="fd1b0-125">Microsoft Defender Advanced Threat Protection</span></span>


## <a name="configure-office-365-advanced-threat-protection"></a><span data-ttu-id="fd1b0-126">Konfigurera avancerat hotskydd för Office 365</span><span class="sxs-lookup"><span data-stu-id="fd1b0-126">Configure Office 365 Advanced Threat Protection</span></span>
>[!NOTE]
><span data-ttu-id="fd1b0-127">Hoppa över det här steget om du redan har aktiverat avancerat skydd mot Office 365-hot.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-127">Skip this step if you have already enabled Office 365 Advanced Threat Protection.</span></span> 

<span data-ttu-id="fd1b0-128">Det finns en PowerShell-modul som kallas *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* som hjälper till att avgöra några av dessa inställningar.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-128">There is a PowerShell Module called the *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* that helps determine some of these settings.</span></span> <span data-ttu-id="fd1b0-129">När du kör som administratör i din klientorganisation, get-ORCAReport kommer att bidra till att generera en bedömning av anti-spam, anti-phish och andra inställningar meddelandehygien.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-129">When run as an administrator in your tenant, get-ORCAReport will help generate an assessment of the anti-spam, anti-phish, and other message hygiene settings.</span></span> <span data-ttu-id="fd1b0-130">Du kan ladda https://www.powershellgallery.com/packages/ORCA/ner denna modul från .</span><span class="sxs-lookup"><span data-stu-id="fd1b0-130">You can download this module from https://www.powershellgallery.com/packages/ORCA/.</span></span> 

1. <span data-ttu-id="fd1b0-131">Navigera till [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Policy**.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-131">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Policy**.</span></span>
<span data-ttu-id="fd1b0-132">![Bild of_page](../../media/mtp-eval-32.png)</span><span class="sxs-lookup"><span data-stu-id="fd1b0-132">![Image of_page](../../media/mtp-eval-32.png)</span></span> <br>
 
2. <span data-ttu-id="fd1b0-133">Klicka på **ATP-anti-nätfiske,** välj **Skapa** och fyll i principnamnet och beskrivningen.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-133">Click **ATP anti-phishing**, select **Create** and fill in the policy name and description.</span></span> <span data-ttu-id="fd1b0-134">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-134">Click **Next**.</span></span>
<span data-ttu-id="fd1b0-135">![Bild of_page](../../media/mtp-eval-33.png)</span><span class="sxs-lookup"><span data-stu-id="fd1b0-135">![Image of_page](../../media/mtp-eval-33.png)</span></span> <br>

>[!NOTE]
><span data-ttu-id="fd1b0-136">Redigera din avancerade ATP-policy mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-136">Edit your Advanced ATP anti-phishing policy.</span></span> <span data-ttu-id="fd1b0-137">Ändra **avancerad tröskel för nätfiske** till **2 - Aggressiv**.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-137">Change **Advanced Phishing Threshold** to **2 - Aggressive**.</span></span>
<br>

3. <span data-ttu-id="fd1b0-138">Klicka på den nedrullningsbara menyn **Lägg till ett villkor** och välj domänen/domänerna som mottagardomän.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-138">Click the **Add a condition** drop-down menu and select your domain(s) as recipient domain.</span></span> <span data-ttu-id="fd1b0-139">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-139">Click **Next**.</span></span>
<span data-ttu-id="fd1b0-140">![Bild of_page](../../media/mtp-eval-34.png)</span><span class="sxs-lookup"><span data-stu-id="fd1b0-140">![Image of_page](../../media/mtp-eval-34.png)</span></span> <br>
 
4. <span data-ttu-id="fd1b0-141">Granska dina inställningar.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-141">Review your settings.</span></span> <span data-ttu-id="fd1b0-142">Klicka på **Skapa den här principen** för att bekräfta.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-142">Click **Create this policy** to confirm.</span></span> 
<span data-ttu-id="fd1b0-143">![Bild of_page](../../media/mtp-eval-35.png)</span><span class="sxs-lookup"><span data-stu-id="fd1b0-143">![Image of_page](../../media/mtp-eval-35.png)</span></span> <br>
 
5. <span data-ttu-id="fd1b0-144">Välj **ATP Säkra bilagor** och välj alternativet Aktivera **ATP för SharePoint, OneDrive och Microsoft Teams.**</span><span class="sxs-lookup"><span data-stu-id="fd1b0-144">Select **ATP Safe attachments** and select the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** option.</span></span>  
<span data-ttu-id="fd1b0-145">![Bild of_page](../../media/mtp-eval-36.png)</span><span class="sxs-lookup"><span data-stu-id="fd1b0-145">![Image of_page](../../media/mtp-eval-36.png)</span></span> <br>

6. <span data-ttu-id="fd1b0-146">Klicka på ikonen + om du vill skapa en ny princip för säker bifogad fil och tillämpa den som mottagaredomän på dina domäner.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-146">Click the + icon to create a new safe attachment policy, apply it as recipient domain to your domains.</span></span> <span data-ttu-id="fd1b0-147">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-147">Click **Save**.</span></span>
<span data-ttu-id="fd1b0-148">![Bild of_page](../../media/mtp-eval-37.png)</span><span class="sxs-lookup"><span data-stu-id="fd1b0-148">![Image of_page](../../media/mtp-eval-37.png)</span></span> <br>
 
7. <span data-ttu-id="fd1b0-149">Välj sedan **atp-principen för säkra länkar** och klicka sedan på pennikonen för att redigera standardprincipen.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-149">Next, select the **ATP Safe Links** policy, then click the pencil icon to edit the default policy.</span></span>

8. <span data-ttu-id="fd1b0-150">Kontrollera att alternativet **Spåra inte när användare klickar på säkra länkar** inte är markerat, medan resten av alternativen är markerade.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-150">Make sure that the **Do not track when users click safe links** option is not selected, while the rest of the options are selected.</span></span> <span data-ttu-id="fd1b0-151">Mer information finns i inställningar för [säkra länkar.](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="fd1b0-151">See [Safe Links settings](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp?view=o365-worldwide) for details.</span></span> <span data-ttu-id="fd1b0-152">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-152">Click **Save**.</span></span> 
<span data-ttu-id="fd1b0-153">![Bild of_page](../../media/mtp-eval-38.png)</span><span class="sxs-lookup"><span data-stu-id="fd1b0-153">![Image of_page](../../media/mtp-eval-38.png)</span></span> <br>

9. <span data-ttu-id="fd1b0-154">Välj sedan policyn **mot skadlig kod,** välj standard och välj pennikonen.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-154">Next select the **Anti-malware** policy, select the default, and choose the pencil icon.</span></span>

10. <span data-ttu-id="fd1b0-155">Klicka på **Inställningar** och välj **Ja och använd standardmeddelandetexten** för att aktivera **svar på identifiering av skadlig kod**.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-155">Click **Settings** and select **Yes and use the default notification text** to enable **Malware Detection Response**.</span></span> <span data-ttu-id="fd1b0-156">Aktivera **filtret Vanliga typer av bifogade filer.**</span><span class="sxs-lookup"><span data-stu-id="fd1b0-156">Turn the **Common Attachment Types Filter** on.</span></span> <span data-ttu-id="fd1b0-157">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-157">Click **Save**.</span></span>
<br><span data-ttu-id="fd1b0-158">![Bild of_page](../../media/mtp-eval-39.png)</span><span class="sxs-lookup"><span data-stu-id="fd1b0-158">![Image of_page](../../media/mtp-eval-39.png)</span></span> <br>
  
11. <span data-ttu-id="fd1b0-159">Navigera till [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Search** > **Audit log search** och aktivera Granskning.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-159">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Search** > **Audit log search** and turn Auditing on.</span></span>  
<span data-ttu-id="fd1b0-160">![Bild of_page](../../media/mtp-eval-40.png)</span><span class="sxs-lookup"><span data-stu-id="fd1b0-160">![Image of_page](../../media/mtp-eval-40.png)</span></span> <br>

12. <span data-ttu-id="fd1b0-161">Integrera Office 365 ATP med Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-161">Integrate Office 365 ATP with Microsoft Defender ATP.</span></span> <span data-ttu-id="fd1b0-162">Navigera till [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Explorer** och välj **WDATP-inställningar** längst upp till höger på skärmen.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-162">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Explorer** and select **WDATP Settings** on the upper right corner of the screen.</span></span> <span data-ttu-id="fd1b0-163">Aktivera **Anslut till Windows ATP**i dialogrutan Microsoft Defender ATP-anslutning.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-163">In the Microsoft Defender ATP connection dialog box, turn on **Connect to Windows ATP**.</span></span>
<span data-ttu-id="fd1b0-164">![Bild of_page](../../media/mtp-eval-41.png)</span><span class="sxs-lookup"><span data-stu-id="fd1b0-164">![Image of_page](../../media/mtp-eval-41.png)</span></span> <br>

## <a name="configure-azure-advanced-threat-protection"></a><span data-ttu-id="fd1b0-165">Konfigurera Avancerat hotskydd för Azure</span><span class="sxs-lookup"><span data-stu-id="fd1b0-165">Configure Azure Advanced Threat Protection</span></span>
>[!NOTE]
><span data-ttu-id="fd1b0-166">Hoppa över det här steget om du redan har aktiverat Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="fd1b0-166">Skip this step if you have already enabled Azure Advanced Threat Protection</span></span>


1. <span data-ttu-id="fd1b0-167">Navigera till [Microsoft 365 Security Center](https://security.microsoft.com/info) > välja Fler **resurser** > **Azure Advanced Threat Protection**.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-167">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > select **More Resources** > **Azure Advanced Threat Protection**.</span></span>
<span data-ttu-id="fd1b0-168">![Bild of_page](../../media/mtp-eval-42.png)</span><span class="sxs-lookup"><span data-stu-id="fd1b0-168">![Image of_page](../../media/mtp-eval-42.png)</span></span> <br>

2. <span data-ttu-id="fd1b0-169">Klicka på Skapa om du vill starta guiden Avancerat skydd mot Azure.Click **Create** to start the Azure Advanced Threat Protection wizard.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-169">Click **Create** to start the Azure Advanced Threat Protection wizard.</span></span> 
<br><span data-ttu-id="fd1b0-170">![Bild of_page](../../media/mtp-eval-43.png)</span><span class="sxs-lookup"><span data-stu-id="fd1b0-170">![Image of_page](../../media/mtp-eval-43.png)</span></span> <br>

3. <span data-ttu-id="fd1b0-171">Välj **Ange ett användarnamn och lösenord för att ansluta till Active Directory-skogen**.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-171">Choose **Provide a username and password to connect to your Active Directory forest**.</span></span>  
<span data-ttu-id="fd1b0-172">![Bild of_page](../../media/mtp-eval-44.png)</span><span class="sxs-lookup"><span data-stu-id="fd1b0-172">![Image of_page](../../media/mtp-eval-44.png)</span></span> <br>

4. <span data-ttu-id="fd1b0-173">Ange lokala autentiseringsuppgifter för Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-173">Enter your Active Directory on-premises credentials.</span></span> <span data-ttu-id="fd1b0-174">Detta kan vara alla användarkonton som har läsbehörighet till Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-174">This can be any user account that has read access to Active Directory.</span></span>
<span data-ttu-id="fd1b0-175">![Bild of_page](../../media/mtp-eval-45.png)</span><span class="sxs-lookup"><span data-stu-id="fd1b0-175">![Image of_page](../../media/mtp-eval-45.png)</span></span> <br>

5. <span data-ttu-id="fd1b0-176">Välj sedan **Hämta sensorinstallation och** överför filen till domänkontrollanten.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-176">Next, choose **Download Sensor Setup** and transfer file to your domain controller.</span></span> 
<span data-ttu-id="fd1b0-177">![Bild of_page](../../media/mtp-eval-46.png)</span><span class="sxs-lookup"><span data-stu-id="fd1b0-177">![Image of_page](../../media/mtp-eval-46.png)</span></span> <br>

6. <span data-ttu-id="fd1b0-178">Kör installationen av Azure ATP-sensor och börja följa guiden.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-178">Execute the Azure ATP Sensor Setup and begin following the wizard.</span></span>
<br><span data-ttu-id="fd1b0-179">![Bild of_page](../../media/mtp-eval-47.png)</span><span class="sxs-lookup"><span data-stu-id="fd1b0-179">![Image of_page](../../media/mtp-eval-47.png)</span></span> <br>
 
7. <span data-ttu-id="fd1b0-180">Klicka på **Nästa** vid sensordistributionstypen.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-180">Click **Next** at the sensor deployment type.</span></span>
<br><span data-ttu-id="fd1b0-181">![Bild of_page](../../media/mtp-eval-48.png)</span><span class="sxs-lookup"><span data-stu-id="fd1b0-181">![Image of_page](../../media/mtp-eval-48.png)</span></span> <br>
 
8. <span data-ttu-id="fd1b0-182">Kopiera åtkomstnyckeln som du behöver för att ange den nästa i guiden.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-182">Copy the access key as you will need to enter it next in the Wizard.</span></span>
<span data-ttu-id="fd1b0-183">![Bild of_page](../../media/mtp-eval-49.png)</span><span class="sxs-lookup"><span data-stu-id="fd1b0-183">![Image of_page](../../media/mtp-eval-49.png)</span></span> <br>
 
9. <span data-ttu-id="fd1b0-184">Kopiera åtkomstnyckeln till guiden och klicka på **Installera**.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-184">Copy the access key into the Wizard and click **Install**.</span></span> 
<br><span data-ttu-id="fd1b0-185">![Bild of_page](../../media/mtp-eval-50.png)</span><span class="sxs-lookup"><span data-stu-id="fd1b0-185">![Image of_page](../../media/mtp-eval-50.png)</span></span> <br>

10. <span data-ttu-id="fd1b0-186">Grattis, du har konfigurerat Azure Advanced Threat Protection på domänkontrollanten.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-186">Congratulations, you have successfully configured Azure Advanced Threat Protection on your domain controller.</span></span>
<span data-ttu-id="fd1b0-187">![Bild of_page](../../media/mtp-eval-51.png)</span><span class="sxs-lookup"><span data-stu-id="fd1b0-187">![Image of_page](../../media/mtp-eval-51.png)</span></span> <br>
 
11. <span data-ttu-id="fd1b0-188">Under avsnittet [Azure Azure ATP-inställningar](https://go.microsoft.com/fwlink/?linkid=2040449) väljer du **Windows Defender ATP**och aktiverar sedan växlingsknappen.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-188">Under the [Azure Azure ATP](https://go.microsoft.com/fwlink/?linkid=2040449) settings section, select **Windows Defender ATP**, then turn the toggle on.</span></span> <span data-ttu-id="fd1b0-189">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-189">Click **Save**.</span></span> 
<span data-ttu-id="fd1b0-190">![Bild of_page](../../media/mtp-eval-52.png)</span><span class="sxs-lookup"><span data-stu-id="fd1b0-190">![Image of_page](../../media/mtp-eval-52.png)</span></span> <br>

>[!NOTE]
><span data-ttu-id="fd1b0-191">Windows Defender ATP har bytt namn till Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-191">Windows Defender ATP has been rebranded as Microsoft Defender ATP.</span></span> <span data-ttu-id="fd1b0-192">Omprofilering förändringar över alla våra portaler håller på att rullas ut för konsekvens.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-192">Rebranding changes across all of our portals are being rolled out the for consistency.</span></span>


## <a name="configure-microsoft-cloud-app-security"></a><span data-ttu-id="fd1b0-193">Konfigurera Säkerhet för Microsoft Cloud-appar</span><span class="sxs-lookup"><span data-stu-id="fd1b0-193">Configure Microsoft Cloud App Security</span></span>
>[!NOTE]
><span data-ttu-id="fd1b0-194">Hoppa över det här steget om du redan har aktiverat Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-194">Skip this step if you have already enabled Microsoft Cloud App Security.</span></span> 

1. <span data-ttu-id="fd1b0-195">Navigera till [Microsoft 365 Security Center](https://security.microsoft.com/info) > **Mer resurser** > **Microsoft Cloud App Security**.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-195">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Cloud App Security**.</span></span>
<span data-ttu-id="fd1b0-196">![Bild of_page](../../media/mtp-eval-53.png)</span><span class="sxs-lookup"><span data-stu-id="fd1b0-196">![Image of_page](../../media/mtp-eval-53.png)</span></span> <br>

2. <span data-ttu-id="fd1b0-197">Vid informationsfrågan om att integrera Azure ATP väljer du **Aktivera Azure ATP-dataintegration**.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-197">At the information prompt to integrate Azure ATP, select **Enable Azure ATP data integration**.</span></span> 
<br><span data-ttu-id="fd1b0-198">![Bild of_page](../../media/mtp-eval-54.png)</span><span class="sxs-lookup"><span data-stu-id="fd1b0-198">![Image of_page](../../media/mtp-eval-54.png)</span></span> <br>

>[!NOTE]
><span data-ttu-id="fd1b0-199">Om du inte ser den här prompten kan det innebära att din Azure ATP-dataintegrering redan har aktiverats.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-199">If you don’t see this prompt, it might mean that your Azure ATP data integration has already been enabled.</span></span> <span data-ttu-id="fd1b0-200">Om du är osäker kontaktar du dock IT-administratören för att bekräfta.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-200">However, if you are not sure, contact your IT Administrator to confirm.</span></span> 

3. <span data-ttu-id="fd1b0-201">Gå till **Inställningar**, aktivera växlingsknappen för **Azure ATP-integrering** och klicka sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-201">Go to **Settings**, turn the **Azure ATP integration** toggle on, then click **Save**.</span></span> 
<span data-ttu-id="fd1b0-202">![Bild of_page](../../media/mtp-eval-55.png)</span><span class="sxs-lookup"><span data-stu-id="fd1b0-202">![Image of_page](../../media/mtp-eval-55.png)</span></span> <br>
>[!NOTE]
><span data-ttu-id="fd1b0-203">För nya Azure ATP-instanser aktiveras den här integrationsväxlingen automatiskt.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-203">For new Azure ATP instances, this integration toggle is automatically turned on.</span></span> <span data-ttu-id="fd1b0-204">Bekräfta att din Azure ATP-integrering har aktiverats innan du går vidare till nästa steg.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-204">Confirm that your Azure ATP integration has been enabled before you proceed to the next step.</span></span>
 
4. <span data-ttu-id="fd1b0-205">Under inställningarna för molnidentifiering väljer du **Microsoft Defender ATP-integrering**och aktiverar integreringen.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-205">Under the Cloud discovery settings, select **Microsoft Defender ATP integration**, then enable the integration.</span></span> <span data-ttu-id="fd1b0-206">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-206">Click **Save**.</span></span>
<span data-ttu-id="fd1b0-207">![Bild of_page](../../media/mtp-eval-56.png)</span><span class="sxs-lookup"><span data-stu-id="fd1b0-207">![Image of_page](../../media/mtp-eval-56.png)</span></span> <br>

5. <span data-ttu-id="fd1b0-208">Under Molnidentifieringsinställningar väljer du **Användarberikande**och aktiverar sedan integreringen med Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-208">Under Cloud discovery settings, select **User enrichment**, then enable the integration with Azure Active Directory.</span></span>
<span data-ttu-id="fd1b0-209">![Bild of_page](../../media/mtp-eval-57.png)</span><span class="sxs-lookup"><span data-stu-id="fd1b0-209">![Image of_page](../../media/mtp-eval-57.png)</span></span> <br>

## <a name="configure-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="fd1b0-210">Konfigurera avancerat hotskydd för Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="fd1b0-210">Configure Microsoft Defender Advanced Threat Protection</span></span>
>[!NOTE]
><span data-ttu-id="fd1b0-211">Hoppa över det här steget om du redan har aktiverat Microsoft Defender Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-211">Skip this step if you have already enabled Microsoft Defender Advanced Threat Protection.</span></span>

1. <span data-ttu-id="fd1b0-212">Navigera till [Microsoft 365 Security Center](https://security.microsoft.com/info) > **Mer resurser** > **Microsoft Defender Security Center**.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-212">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Defender Security Center**.</span></span> <span data-ttu-id="fd1b0-213">Klicka på **Öppna**.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-213">Click **Open**.</span></span>
<br><span data-ttu-id="fd1b0-214">![Bild of_page](../../media/mtp-eval-58.png)</span><span class="sxs-lookup"><span data-stu-id="fd1b0-214">![Image of_page](../../media/mtp-eval-58.png)</span></span> <br>
 
2. <span data-ttu-id="fd1b0-215">Följ guiden Avancerat skydd mot microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-215">Follow the Microsoft Defender Advanced Threat Protection wizard.</span></span> <span data-ttu-id="fd1b0-216">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-216">Click **Next**.</span></span> 
<br><span data-ttu-id="fd1b0-217">![Bild of_page](../../media/mtp-eval-59.png)</span><span class="sxs-lookup"><span data-stu-id="fd1b0-217">![Image of_page](../../media/mtp-eval-59.png)</span></span> <br>

3. <span data-ttu-id="fd1b0-218">Välj baserat på önskad plats för datalagring, datalagringsprincip, organisationsstorlek och opt-in för förhandsversionsfunktioner.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-218">Choose based on your preferred data storage location, data retention policy, organization size, and opt-in for preview features.</span></span> 
<br><span data-ttu-id="fd1b0-219">![Bild of_page](../../media/mtp-eval-60.png)</span><span class="sxs-lookup"><span data-stu-id="fd1b0-219">![Image of_page](../../media/mtp-eval-60.png)</span></span> <br>
>[!NOTE]
><span data-ttu-id="fd1b0-220">Du kan inte ändra vissa inställningar, till exempel lagringsplats för data, efteråt.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-220">You cannot change some of the settings, like data storage location, afterwards.</span></span> 
<br>

<span data-ttu-id="fd1b0-221">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-221">Click **Next**.</span></span> 

4. <span data-ttu-id="fd1b0-222">Klicka på **Fortsätt** så etablerar microsoft defender ATP-klienten.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-222">Click **Continue** and it will provision your Microsoft Defender ATP tenant.</span></span>
<br><span data-ttu-id="fd1b0-223">![Bild of_page](../../media/mtp-eval-61.png)</span><span class="sxs-lookup"><span data-stu-id="fd1b0-223">![Image of_page](../../media/mtp-eval-61.png)</span></span> <br>

5. <span data-ttu-id="fd1b0-224">Ombord på dina slutpunkter via grupprinciper, Microsoft Slutpunktshanteraren eller genom att köra ett lokalt skript till Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-224">Onboard your endpoints through Group Policies, Microsoft Endpoint Manager or by running a local script to Microsoft Defender ATP.</span></span> <span data-ttu-id="fd1b0-225">För enkelhetens skull använder den här guiden det lokala skriptet.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-225">For simplicity, this guide uses the local script.</span></span>

6. <span data-ttu-id="fd1b0-226">Klicka på **Hämta paket** och kopiera introduktionsskriptet till slutpunkterna.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-226">Click **Download package** and copy the onboarding script to your endpoint(s).</span></span>  
<br><span data-ttu-id="fd1b0-227">![Bild of_page](../../media/mtp-eval-62.png)</span><span class="sxs-lookup"><span data-stu-id="fd1b0-227">![Image of_page](../../media/mtp-eval-62.png)</span></span> <br>

7. <span data-ttu-id="fd1b0-228">Kör introduktionsskriptet som administratör på slutpunkten och välj Y.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-228">On your endpoint, run the onboarding script as Administrator and choose Y.</span></span>
<br><span data-ttu-id="fd1b0-229">![Bild of_page](../../media/mtp-eval-63.png)</span><span class="sxs-lookup"><span data-stu-id="fd1b0-229">![Image of_page](../../media/mtp-eval-63.png)</span></span> <br>

8. <span data-ttu-id="fd1b0-230">Grattis, du har onboarded din första slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-230">Congratulations, you have onboarded your first endpoint.</span></span>  
<br>![Bild of_page](../../media/mtp-eval-64.png) <br>

9. <span data-ttu-id="fd1b0-232">Kopiera in identifieringstestet från ATP-guiden Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-232">Copy-paste the detection test from the Microsoft Defender ATP wizard.</span></span>
<br><span data-ttu-id="fd1b0-233">![Bild of_page](../../media/mtp-eval-65.png)</span><span class="sxs-lookup"><span data-stu-id="fd1b0-233">![Image of_page](../../media/mtp-eval-65.png)</span></span> <br>

10. <span data-ttu-id="fd1b0-234">Kopiera PowerShell-skriptet till en upphöjd kommandotolk och kör det.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-234">Copy the PowerShell script to an elevated command prompt and run it.</span></span> 
<br><span data-ttu-id="fd1b0-235">![Bild of_page](../../media/mtp-eval-66.png)</span><span class="sxs-lookup"><span data-stu-id="fd1b0-235">![Image of_page](../../media/mtp-eval-66.png)</span></span> <br>

11. <span data-ttu-id="fd1b0-236">Välj **Börja använda Microsoft Defender ATP** i guiden.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-236">Select **Start using Microsoft Defender ATP** from the Wizard.</span></span>
<br><span data-ttu-id="fd1b0-237">![Bild of_page](../../media/mtp-eval-67.png)</span><span class="sxs-lookup"><span data-stu-id="fd1b0-237">![Image of_page](../../media/mtp-eval-67.png)</span></span> <br>
 
12. <span data-ttu-id="fd1b0-238">Besök [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span><span class="sxs-lookup"><span data-stu-id="fd1b0-238">Visit the [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span></span> <span data-ttu-id="fd1b0-239">Gå till **Inställningar** och välj sedan **Avancerade funktioner**.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-239">Go to **Settings** and then select **Advanced features**.</span></span> 
<br><span data-ttu-id="fd1b0-240">![Bild of_page](../../media/mtp-eval-68.png)</span><span class="sxs-lookup"><span data-stu-id="fd1b0-240">![Image of_page](../../media/mtp-eval-68.png)</span></span> <br>

13. <span data-ttu-id="fd1b0-241">Aktivera integreringen med **Azure Advanced Threat Protection**.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-241">Turn on the integration with **Azure Advanced Threat Protection**.</span></span>  
<br><span data-ttu-id="fd1b0-242">![Bild of_page](../../media/mtp-eval-69.png)</span><span class="sxs-lookup"><span data-stu-id="fd1b0-242">![Image of_page](../../media/mtp-eval-69.png)</span></span> <br>

14. <span data-ttu-id="fd1b0-243">Aktivera integreringen med **Office 365 Threat Intelligence**.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-243">Turn on the integration with **Office 365 Threat Intelligence**.</span></span>
<br><span data-ttu-id="fd1b0-244">![Bild of_page](../../media/mtp-eval-70.png)</span><span class="sxs-lookup"><span data-stu-id="fd1b0-244">![Image of_page](../../media/mtp-eval-70.png)</span></span> <br>

15. <span data-ttu-id="fd1b0-245">Aktivera integrering med **Microsoft Cloud App Security**.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-245">Turn on integration with **Microsoft Cloud App Security**.</span></span>
<br><span data-ttu-id="fd1b0-246">![Bild of_page](../../media/mtp-eval-71.png)</span><span class="sxs-lookup"><span data-stu-id="fd1b0-246">![Image of_page](../../media/mtp-eval-71.png)</span></span> <br>

16. <span data-ttu-id="fd1b0-247">Bläddra nedåt och klicka på **Spara inställningar** för att bekräfta de nya integreringarna.</span><span class="sxs-lookup"><span data-stu-id="fd1b0-247">Scroll down and click **Save preferences** to confirm the new integrations.</span></span>
<br><span data-ttu-id="fd1b0-248">![Bild of_page](../../media/mtp-eval-72.png)</span><span class="sxs-lookup"><span data-stu-id="fd1b0-248">![Image of_page](../../media/mtp-eval-72.png)</span></span> <br>

## <a name="next-steps"></a><span data-ttu-id="fd1b0-249">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="fd1b0-249">Next steps</span></span>
<span data-ttu-id="fd1b0-250">[Aktivera Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable?view=o365-worldwide#start-using-the-service) och generera sedan [en testvarning](generate-test-alert.md).</span><span class="sxs-lookup"><span data-stu-id="fd1b0-250">[Turn on Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable?view=o365-worldwide#start-using-the-service) and then [generate a test alert](generate-test-alert.md).</span></span>
