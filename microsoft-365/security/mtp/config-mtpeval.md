---
title: Konfigurera Microsoft Threat Protection-pelare för utvärderings labbet eller pilot miljön
description: Konfigurera skydd mot Microsoft Threat Protection, till exempel Office 365 ATP, Azure ATP, Microsoft Cloud App Security och Microsoft Defender ATP, för utvärderings labbet eller pilot miljön.
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 1778e8485e859d01e4eec40c7a0d404636e27e8d
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199655"
---
# <a name="configure-microsoft-threat-protection-pillars-for-your-trial-lab-or-pilot-environment"></a><span data-ttu-id="2b6d5-104">Konfigurera skydd mot Microsoft Threat för utvärderings labbet eller pilot miljön</span><span class="sxs-lookup"><span data-stu-id="2b6d5-104">Configure Microsoft Threat Protection pillars for your trial lab or pilot environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="2b6d5-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="2b6d5-105">**Applies to:**</span></span>
- <span data-ttu-id="2b6d5-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="2b6d5-106">Microsoft Threat Protection</span></span>


<span data-ttu-id="2b6d5-107">Att skapa ett utvärderings labb för Microsoft Threat-eller pilot miljö och distribuera det är en process i tre steg:</span><span class="sxs-lookup"><span data-stu-id="2b6d5-107">Creating a Microsoft Threat Protection trial lab or pilot environment and deploying it is a three-phase process:</span></span>

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab or pilot environment" title="Förbereda ett utvärderings labb för Microsoft Threat Protection eller pilot miljö" />
      <br/><span data-ttu-id="2b6d5-109">Fas 1: förbereda </a></span><span class="sxs-lookup"><span data-stu-id="2b6d5-109">Phase 1: Prepare </a></span></span><br>
    </td>
     <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab or pilot environment" title="Ställ in ett utvärderings labb eller pilot miljö för Microsoft Threat Protection" />
      <br/><span data-ttu-id="2b6d5-111">Fas 2: konfiguration </a></span><span class="sxs-lookup"><span data-stu-id="2b6d5-111">Phase 2: Setup </a></span></span><br>
    </td>
    <td align="center" bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="Configure & Onboard" title="Konfigurera var and rings skydd för ditt Microsoft Threat Protection test labb eller pilot miljö och inbyggda slut punkter" />
      <br/><span data-ttu-id="2b6d5-113">Steg 3: Konfigurera & inbyggt </a></span><span class="sxs-lookup"><span data-stu-id="2b6d5-113">Phase 3: Configure & Onboard </a></span></span><br>
</td>


  </tr>
</table>

<span data-ttu-id="2b6d5-114">Du är för närvarande i konfigurations fasen.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-114">You're currently in the configuration phase.</span></span>


<span data-ttu-id="2b6d5-115">Förberedelsen är viktig för eventuell distribution.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-115">Preparation is key to any successful deployment.</span></span> <span data-ttu-id="2b6d5-116">I den här artikeln ska du vägleda dig på de Points du måste tänka på när du förbereder dig för att distribuera Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-116">In this article, you'll be guided on the points you'll need to consider as you prepare to deploy Microsoft Defender ATP.</span></span>


## <a name="microsoft-threat-protection-pillars"></a><span data-ttu-id="2b6d5-117">Microsoft Threat Protection-pelare</span><span class="sxs-lookup"><span data-stu-id="2b6d5-117">Microsoft Threat Protection pillars</span></span>
<span data-ttu-id="2b6d5-118">Microsoft Threat Protection består av fyra pelare.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-118">Microsoft Threat Protection consists of four pillars.</span></span> <span data-ttu-id="2b6d5-119">Även om en pelare redan kan ge ett värde till din nätverks organisations säkerhet, ger det fyra till gång till din organisation flest värde.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-119">Although one pillar can already provide value to your network organization's security, enabling the four Microsoft Threat Protection pillars will give your organization the most value.</span></span>
<br>
<span data-ttu-id="2b6d5-120">![Of_Microsoft hot skydds lösning för användare, Azure Avancerat skydd för slut punkter Microsoft Defender Avancerat skydd, för Cloud-appar, Microsoft Cloud App-säkerhet och för data, Office 365 Avancerat skydd  ](../../media/mtp-eval-31.png)</span><span class="sxs-lookup"><span data-stu-id="2b6d5-120">![Image of_Microsoft Threat Protection solution for users, Azure Advanced Threat Protection, for endpoints Microsoft Defender Advanced Threat Protection, for cloud apps, Microsoft Cloud App Security, and for data, Office 365 Advanced Threat Protection  ](../../media/mtp-eval-31.png)</span></span> <br>

<span data-ttu-id="2b6d5-121">I det här avsnittet får du hjälp att konfigurera:</span><span class="sxs-lookup"><span data-stu-id="2b6d5-121">This section will guide you to configure:</span></span>
-   <span data-ttu-id="2b6d5-122">Office 365 Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="2b6d5-122">Office 365 Advanced Threat Protection</span></span>
-   <span data-ttu-id="2b6d5-123">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="2b6d5-123">Azure Advanced Threat Protection</span></span> 
-   <span data-ttu-id="2b6d5-124">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="2b6d5-124">Microsoft Cloud App Security</span></span>
-   <span data-ttu-id="2b6d5-125">Microsoft Defender Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="2b6d5-125">Microsoft Defender Advanced Threat Protection</span></span>


## <a name="configure-office-365-advanced-threat-protection"></a><span data-ttu-id="2b6d5-126">Konfigurera Office 365 Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="2b6d5-126">Configure Office 365 Advanced Threat Protection</span></span>
>[!NOTE]
><span data-ttu-id="2b6d5-127">Hoppa över det här steget om du redan har aktiverat Office 365 Avancerat skydd.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-127">Skip this step if you've already enabled Office 365 Advanced Threat Protection.</span></span> 

<span data-ttu-id="2b6d5-128">Det finns en PowerShell-modul som heter *Office 365 Advanced Threat Protection (Orca)* som hjälper dig att avgöra vissa av de här inställningarna.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-128">There's a PowerShell Module called the *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* that helps determine some of these settings.</span></span> <span data-ttu-id="2b6d5-129">När du kör som administratör i klient organisationen kan du med ORCAReport få en utvärdering av skräp post, anti-Phish och andra inställningar för meddelande hygien.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-129">When run as an administrator in your tenant, get-ORCAReport will help generate an assessment of the anti-spam, anti-phish, and other message hygiene settings.</span></span> <span data-ttu-id="2b6d5-130">Du kan hämta den här modulen från https://www.powershellgallery.com/packages/ORCA/ .</span><span class="sxs-lookup"><span data-stu-id="2b6d5-130">You can download this module from https://www.powershellgallery.com/packages/ORCA/.</span></span> 

1. <span data-ttu-id="2b6d5-131">Navigera till [Office 365-säkerhets &](https://protection.office.com/homepage)  >  policy för**hantering**av villkor för efterlevnad  >  **Policy**.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-131">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Policy**.</span></span>
<span data-ttu-id="2b6d5-132">![Bild of_Office 365 säkerhets & policy för Threat Management-hantering](../../media/mtp-eval-32.png)</span><span class="sxs-lookup"><span data-stu-id="2b6d5-132">![Image of_Office 365 Security & Compliance Center Threat management policy page](../../media/mtp-eval-32.png)</span></span> <br>
 
2. <span data-ttu-id="2b6d5-133">Klicka på **ATP-nätfiske**och välj **skapa** och fyll i Principens namn och beskrivning.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-133">Click **ATP anti-phishing**, select **Create** and fill in the policy name and description.</span></span> <span data-ttu-id="2b6d5-134">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-134">Click **Next**.</span></span>
<span data-ttu-id="2b6d5-135">![Bild of_Office 365 säkerhet & policy för skydd mot Office-nätfiske där du kan namnge policyn](../../media/mtp-eval-33.png)</span><span class="sxs-lookup"><span data-stu-id="2b6d5-135">![Image of_Office 365 Security & Compliance Center anti-phishing policy page where you can name your policy](../../media/mtp-eval-33.png)</span></span> <br>

>[!NOTE]
><span data-ttu-id="2b6d5-136">Redigera din avancerade policy för ATP-anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-136">Edit your Advanced ATP anti-phishing policy.</span></span> <span data-ttu-id="2b6d5-137">Ändra den **avancerade nät fiske tröskeln** till **2-aggressivt**.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-137">Change **Advanced Phishing Threshold** to **2 - Aggressive**.</span></span>
<br>

3. <span data-ttu-id="2b6d5-138">Klicka på den nedrullningsbara menyn **Lägg till en villkors** lista och välj din domän (er) som mottagar domän.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-138">Click the **Add a condition** drop-down menu and select your domain(s) as recipient domain.</span></span> <span data-ttu-id="2b6d5-139">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-139">Click **Next**.</span></span>
<span data-ttu-id="2b6d5-140">![Bild of_Office 365 säkerhet & policy för skydd mot server för uppringnings Center där du kan lägga till ett villkor för dess program](../../media/mtp-eval-34.png)</span><span class="sxs-lookup"><span data-stu-id="2b6d5-140">![Image of_Office 365 Security & Compliance Center anti-phishing policy page where you can add a condition for its application](../../media/mtp-eval-34.png)</span></span> <br>
 
4. <span data-ttu-id="2b6d5-141">Granska dina inställningar.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-141">Review your settings.</span></span> <span data-ttu-id="2b6d5-142">Klicka på **skapa den här principen** för att bekräfta.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-142">Click **Create this policy** to confirm.</span></span> 
<span data-ttu-id="2b6d5-143">![Bild of_Office 365 säkerhets & policy för skydd mot efterlevnad för nätfiske där du kan granska dina inställningar och klicka på knappen Skapa den här principen](../../media/mtp-eval-35.png)</span><span class="sxs-lookup"><span data-stu-id="2b6d5-143">![Image of_Office 365 Security & Compliance Center anti-phishing policy page where you can review your settings and click the create this policy button](../../media/mtp-eval-35.png)</span></span> <br>
 
5. <span data-ttu-id="2b6d5-144">Markera alternativet för **säker säkerhet för ATP** och välj alternativ **för att aktivera ATP för SharePoint, OneDrive och Microsoft Teams** .</span><span class="sxs-lookup"><span data-stu-id="2b6d5-144">Select **ATP Safe attachments** and select the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** option.</span></span>  
<span data-ttu-id="2b6d5-145">![Bild of_Office 365 säkerhets & sidan Compliance Center där du kan aktivera ATP för SharePoint, OneDrive och Microsoft Teams](../../media/mtp-eval-36.png)</span><span class="sxs-lookup"><span data-stu-id="2b6d5-145">![Image of_Office 365 Security & Compliance Center page where you can turn on ATP for SharePoint, OneDrive, and Microsoft Teams](../../media/mtp-eval-36.png)</span></span> <br>

6. <span data-ttu-id="2b6d5-146">Klicka på ikonen + för att skapa en ny princip för säker bifogad fil, tillämpa den som mottagar domän i domänerna.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-146">Click the + icon to create a new safe attachment policy, apply it as recipient domain to your domains.</span></span> <span data-ttu-id="2b6d5-147">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-147">Click **Save**.</span></span>
<span data-ttu-id="2b6d5-148">![Bild of_Office 365 säkerhets & sidan Compliance Center, där du kan skapa en ny princip för säker bifogad fil](../../media/mtp-eval-37.png)</span><span class="sxs-lookup"><span data-stu-id="2b6d5-148">![Image of_Office 365 Security & Compliance Center page where you can create a new create a new safe attachment policy](../../media/mtp-eval-37.png)</span></span> <br>
 
7. <span data-ttu-id="2b6d5-149">Välj sedan policyn för **Safet ATP-länkar** och klicka sedan på Penn ikonen för att redigera standard principen.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-149">Next, select the **ATP Safe Links** policy, then click the pencil icon to edit the default policy.</span></span>

8. <span data-ttu-id="2b6d5-150">Kontrol lera att alternativet **Spåra inte när användare klickar på säkra länkar** inte är markerat, medan resten av alternativen är markerade.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-150">Make sure that the **Do not track when users click safe links** option is not selected, while the rest of the options are selected.</span></span> <span data-ttu-id="2b6d5-151">Se [Inställningar för Safe Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) .</span><span class="sxs-lookup"><span data-stu-id="2b6d5-151">See [Safe Links settings](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) for details.</span></span> <span data-ttu-id="2b6d5-152">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-152">Click **Save**.</span></span> 
<span data-ttu-id="2b6d5-153">![Bild of_Office 365 säkerhets & sidan Compliance Center som visar att alternativet spåra inte när användare klickar på säker är inte markerat](../../media/mtp-eval-38.png)</span><span class="sxs-lookup"><span data-stu-id="2b6d5-153">![Image of_Office 365 Security & Compliance Center page which shows that the option Do not track when users click safe is not selected](../../media/mtp-eval-38.png)</span></span> <br>

9. <span data-ttu-id="2b6d5-154">Välj sedan standard principen för att förhindra **mot skadlig program vara** och välj sedan Penn ikonen.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-154">Next select the **Anti-malware** policy, select the default, and choose the pencil icon.</span></span>

10. <span data-ttu-id="2b6d5-155">Klicka på **Inställningar** och välj **Ja och Använd standard meddelande texten** för att aktivera **identifiering av skadlig program vara**.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-155">Click **Settings** and select **Yes and use the default notification text** to enable **Malware Detection Response**.</span></span> <span data-ttu-id="2b6d5-156">Aktivera **filtret vanliga typer av bifogade filer** .</span><span class="sxs-lookup"><span data-stu-id="2b6d5-156">Turn the **Common Attachment Types Filter** on.</span></span> <span data-ttu-id="2b6d5-157">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-157">Click **Save**.</span></span>
<br><span data-ttu-id="2b6d5-158">![Bild of_Office 365 säkerhets & sidan Compliance Center som visar att svaret om skadlig program vara är aktiverat med standard meddelande och att filtret vanliga bilage typer är aktiverat](../../media/mtp-eval-39.png)</span><span class="sxs-lookup"><span data-stu-id="2b6d5-158">![Image of_Office 365 Security & Compliance Center page which shows that the malware detection response is turned on with default notification and the common attachment types filter is turned on](../../media/mtp-eval-39.png)</span></span> <br>
  
11. <span data-ttu-id="2b6d5-159">Navigera till [Office 365-säkerhets & Compliance Center](https://protection.office.com/homepage)  >  **Sök**efter  >  **gransknings loggs ökning** och aktivera granskning.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-159">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Search** > **Audit log search** and turn Auditing on.</span></span>  
<span data-ttu-id="2b6d5-160">![Bild of_Office 365 säkerhets & sidan Compliance Center där du kan aktivera gransknings loggs ökningen](../../media/mtp-eval-40.png)</span><span class="sxs-lookup"><span data-stu-id="2b6d5-160">![Image of_Office 365 Security & Compliance Center page where you can turn on the Audit log search](../../media/mtp-eval-40.png)</span></span> <br>

12. <span data-ttu-id="2b6d5-161">Integrera Office 365 ATP med Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-161">Integrate Office 365 ATP with Microsoft Defender ATP.</span></span> <span data-ttu-id="2b6d5-162">Navigera till [Office 365-säkerhets &](https://protection.office.com/homepage)  >  **hanterings**Center för regelefterlevnad  >  **Explorer** och välj **WDATP inställningar** i det övre högra hörnet av skärmen.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-162">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Explorer** and select **WDATP Settings** on the upper right corner of the screen.</span></span> <span data-ttu-id="2b6d5-163">I dialog rutan Microsoft Defender ATP-anslutning aktiverar **du Anslut till Windows ATP**.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-163">In the Microsoft Defender ATP connection dialog box, turn on **Connect to Windows ATP**.</span></span>
<span data-ttu-id="2b6d5-164">![Bild of_Office 365 säkerhets & sidan Compliance Center där du kan aktivera Windows Defender ATP-anslutning på](../../media/mtp-eval-41.png)</span><span class="sxs-lookup"><span data-stu-id="2b6d5-164">![Image of_Office 365 Security & Compliance Center page where you can turn Windows Defender ATP connection on](../../media/mtp-eval-41.png)</span></span> <br>

## <a name="configure-azure-advanced-threat-protection"></a><span data-ttu-id="2b6d5-165">Konfigurera Avancerat skydd för Azure</span><span class="sxs-lookup"><span data-stu-id="2b6d5-165">Configure Azure Advanced Threat Protection</span></span>
>[!NOTE]
><span data-ttu-id="2b6d5-166">Hoppa över det här steget om du redan har aktiverat Azure Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="2b6d5-166">Skip this step if you've already enabled Azure Advanced Threat Protection</span></span>


1. <span data-ttu-id="2b6d5-167">Gå till [Microsoft 365-säkerhets Center](https://security.microsoft.com/info) > Välj **fler resurser**  >  **Azure Avancerat skydd**.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-167">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > select **More Resources** > **Azure Advanced Threat Protection**.</span></span>
<span data-ttu-id="2b6d5-168">![Bild of_Microsoft 365 säkerhets Center sida där det finns ett alternativ för att öppna Azure Avancerat skydd](../../media/mtp-eval-42.png)</span><span class="sxs-lookup"><span data-stu-id="2b6d5-168">![Image of_Microsoft 365 Security Center page where there's an option to open Azure Advanced Threat Protection](../../media/mtp-eval-42.png)</span></span> <br>

2. <span data-ttu-id="2b6d5-169">Klicka på **skapa** för att starta guiden Avancerat skydd för Azure.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-169">Click **Create** to start the Azure Advanced Threat Protection wizard.</span></span> 
<br><span data-ttu-id="2b6d5-170">![Bild of_Azure sidan för avancerat skydd på guiden där du bör Klicka på knappen Skapa](../../media/mtp-eval-43.png)</span><span class="sxs-lookup"><span data-stu-id="2b6d5-170">![Image of_Azure Advanced Threat Protection wizard page where you should click Create button](../../media/mtp-eval-43.png)</span></span> <br>

3. <span data-ttu-id="2b6d5-171">Välj **ge ett användar namn och lösen ord för att ansluta till Active Directory-skogen**.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-171">Choose **Provide a username and password to connect to your Active Directory forest**.</span></span>  
<span data-ttu-id="2b6d5-172">![Bild på Välkomst sidan för of_Azure avancerad skydd](../../media/mtp-eval-44.png)</span><span class="sxs-lookup"><span data-stu-id="2b6d5-172">![Image of_Azure Advanced Threat Protection welcome page](../../media/mtp-eval-44.png)</span></span> <br>

4. <span data-ttu-id="2b6d5-173">Ange lokala inloggnings uppgifter för Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-173">Enter your Active Directory on-premises credentials.</span></span> <span data-ttu-id="2b6d5-174">Det kan vara vilket användar konto som helst som har Läs åtkomst till Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-174">This can be any user account that has read access to Active Directory.</span></span>
<span data-ttu-id="2b6d5-175">![Bild of_Azure sidan för tjänsten för avancerat skydds katalog där du ska ange dina uppgifter](../../media/mtp-eval-45.png)</span><span class="sxs-lookup"><span data-stu-id="2b6d5-175">![Image of_Azure Advanced Threat Protection Directory services page where you should put your credentials](../../media/mtp-eval-45.png)</span></span> <br>

5. <span data-ttu-id="2b6d5-176">Välj sedan **Ladda ned sensor konfiguration** och överföra fil till domänkontrollanten.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-176">Next, choose **Download Sensor Setup** and transfer file to your domain controller.</span></span> 
<span data-ttu-id="2b6d5-177">![Bild of_Azure sidan för avancerat skydd där du kan välja nedladdnings sensor inställning](../../media/mtp-eval-46.png)</span><span class="sxs-lookup"><span data-stu-id="2b6d5-177">![Image of_Azure Advanced Threat Protection page where you can select Download Sensor Setup](../../media/mtp-eval-46.png)</span></span> <br>

6. <span data-ttu-id="2b6d5-178">Kör installations programmet för Azure ATP och börja följa guiden.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-178">Execute the Azure ATP Sensor Setup and begin following the wizard.</span></span>
<br><span data-ttu-id="2b6d5-179">![Bild of_Azure sidan för avancerat skydd där du bör Klicka på Nästa för att följa Azure ATP-sensor guiden](../../media/mtp-eval-47.png)</span><span class="sxs-lookup"><span data-stu-id="2b6d5-179">![Image of_Azure Advanced Threat Protection page where you should click next to follow the Azure ATP sensor wizard](../../media/mtp-eval-47.png)</span></span> <br>
 
7. <span data-ttu-id="2b6d5-180">Klicka på **Nästa** på sensor distributions typen.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-180">Click **Next** at the sensor deployment type.</span></span>
<br><span data-ttu-id="2b6d5-181">![Bild of_Azure sidan för avancerat skydd för hotet där du bör Klicka på Nästa för att gå till nästa sida](../../media/mtp-eval-48.png)</span><span class="sxs-lookup"><span data-stu-id="2b6d5-181">![Image of_Azure Advanced Threat Protection page where you should click next to go to next page](../../media/mtp-eval-48.png)</span></span> <br>
 
8. <span data-ttu-id="2b6d5-182">Kopiera snabb tangenten eftersom du måste ange den intill i guiden.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-182">Copy the access key because you need to enter it next in the Wizard.</span></span>
<span data-ttu-id="2b6d5-183">![Bild of_the sensorer-sida där du vill kopiera den snabb åtkomst du behöver ange på nästa sida med guiden för Azure ATP-sensor](../../media/mtp-eval-49.png)</span><span class="sxs-lookup"><span data-stu-id="2b6d5-183">![Image of_the sensors page where you should copy the access key that you need to enter in the next Azure ATP sensor setup wizard page](../../media/mtp-eval-49.png)</span></span> <br>
 
9. <span data-ttu-id="2b6d5-184">Kopiera till guiden och klicka på **Installera**.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-184">Copy the access key into the Wizard and click **Install**.</span></span> 
<br><span data-ttu-id="2b6d5-185">![Bild of_Azure sidan för avancerat skydd för Azure ATP-guiden där du bör tillhandahålla snabb tangenten och klicka sedan på knappen Installera.](../../media/mtp-eval-50.png)</span><span class="sxs-lookup"><span data-stu-id="2b6d5-185">![Image of_Azure Advanced Threat Protection Azure ATP sensor wizard page where you should provide the access key and then click the install button](../../media/mtp-eval-50.png)</span></span> <br>

10. <span data-ttu-id="2b6d5-186">Grattis! du har konfigurerat Azure Avancerat skydd för din domänkontrollant.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-186">Congratulations, you've successfully configured Azure Advanced Threat Protection on your domain controller.</span></span>
<span data-ttu-id="2b6d5-187">![Bild of_Azure Avancerat skydd för Azure ATP-sensor för installation av Office.](../../media/mtp-eval-51.png)</span><span class="sxs-lookup"><span data-stu-id="2b6d5-187">![Image of_Azure Advanced Threat Protection Azure ATP sensor wizard installation completion where you should click the finish button](../../media/mtp-eval-51.png)</span></span> <br>
 
11. <span data-ttu-id="2b6d5-188">Under Inställningar för [Azure Azure ATP](https://go.microsoft.com/fwlink/?linkid=2040449) väljer du **Windows Defender ATP**och aktiverar sedan växlings knappen.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-188">Under the [Azure Azure ATP](https://go.microsoft.com/fwlink/?linkid=2040449) settings section, select **Windows Defender ATP**, then turn on the toggle.</span></span> <span data-ttu-id="2b6d5-189">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-189">Click **Save**.</span></span> 
<span data-ttu-id="2b6d5-190">![Bild of_the sidan för Azure Azure ATP-inställningar där du bör aktivera Windows Defender ATP.](../../media/mtp-eval-52.png)</span><span class="sxs-lookup"><span data-stu-id="2b6d5-190">![Image of_the Azure Azure ATP settings page where you should turn the Windows Defender ATP toggle on](../../media/mtp-eval-52.png)</span></span> <br>

>[!NOTE]
><span data-ttu-id="2b6d5-191">Windows Defender ATP har ändrats som Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-191">Windows Defender ATP has been rebranded as Microsoft Defender ATP.</span></span> <span data-ttu-id="2b6d5-192">Att ändra dina ändringar i alla portaler blir då mer konsekvens.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-192">Rebranding changes across all of our portals are being rolled out the for consistency.</span></span>


## <a name="configure-microsoft-cloud-app-security"></a><span data-ttu-id="2b6d5-193">Konfigurera säkerhet för Microsoft Cloud App</span><span class="sxs-lookup"><span data-stu-id="2b6d5-193">Configure Microsoft Cloud App Security</span></span>
>[!NOTE]
><span data-ttu-id="2b6d5-194">Hoppa över det här steget om du redan har aktiverat säkerhet för Microsoft Cloud App.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-194">Skip this step if you've already enabled Microsoft Cloud App Security.</span></span> 

1. <span data-ttu-id="2b6d5-195">Navigera till [Microsoft 365 säkerhets Center](https://security.microsoft.com/info)  >  **fler resurser**  >  **Microsoft Cloud App-säkerhet**.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-195">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Cloud App Security**.</span></span>
<span data-ttu-id="2b6d5-196">![Bild of_Microsoft 365 säkerhets Center sida där du kan se Microsoft Cloud App Card och ska klicka på knappen Öppna](../../media/mtp-eval-53.png)</span><span class="sxs-lookup"><span data-stu-id="2b6d5-196">![Image of_Microsoft 365 Security Center page where you can see Microsoft Cloud App card and should click the open button](../../media/mtp-eval-53.png)</span></span> <br>

2. <span data-ttu-id="2b6d5-197">Välj **Aktivera Azure ATP-data integrering**i informations meddelandet om du vill integrera Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-197">At the information prompt to integrate Azure ATP, select **Enable Azure ATP data integration**.</span></span> 
<br><span data-ttu-id="2b6d5-198">![Bild of_the meddelande om att integrera Azure ATP där du bör välja länken Aktivera Azure ATP-data integrering](../../media/mtp-eval-54.png)</span><span class="sxs-lookup"><span data-stu-id="2b6d5-198">![Image of_the information prompt to integrate Azure ATP where you should select the Enable Azure ATP data integration link](../../media/mtp-eval-54.png)</span></span> <br>

>[!NOTE]
><span data-ttu-id="2b6d5-199">Om du inte ser den här uppmaningen kan det betyda att din Azure ATP-data integrering redan har Aktiver ATS.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-199">If you don’t see this prompt, it might mean that your Azure ATP data integration has already been enabled.</span></span> <span data-ttu-id="2b6d5-200">Om du är osäker kontaktar du IT-administratören för att bekräfta.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-200">However, if you are not sure, contact your IT Administrator to confirm.</span></span> 

3. <span data-ttu-id="2b6d5-201">Gå till **Inställningar**, aktivera **integreringen av Azure ATP** och klicka sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-201">Go to **Settings**, turn on the **Azure ATP integration** toggle, then click **Save**.</span></span> 
<span data-ttu-id="2b6d5-202">![Sidan image of_the inställningar där du bör aktivera och inaktivera integreringen med Azure ATP klickar du på Spara](../../media/mtp-eval-55.png)</span><span class="sxs-lookup"><span data-stu-id="2b6d5-202">![Image of_the settings page where you should turn on the Azure ATP integration toggle then click save](../../media/mtp-eval-55.png)</span></span> <br>
>[!NOTE]
><span data-ttu-id="2b6d5-203">För nya Azure ATP-instanser är denna växel växling automatiskt aktive rad.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-203">For new Azure ATP instances, this integration toggle is automatically turned on.</span></span> <span data-ttu-id="2b6d5-204">Kontrol lera att din Azure ATP-integrering har Aktiver ATS innan du går vidare till nästa steg.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-204">Confirm that your Azure ATP integration has been enabled before you proceed to the next step.</span></span>
 
4. <span data-ttu-id="2b6d5-205">Under Inställningar för moln identifiering väljer du **Microsoft Defender ATP-integrering**och aktiverar integrationen.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-205">Under the Cloud discovery settings, select **Microsoft Defender ATP integration**, then enable the integration.</span></span> <span data-ttu-id="2b6d5-206">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-206">Click **Save**.</span></span>
<span data-ttu-id="2b6d5-207">![Bild of_the Microsoft Defender ATP-sida där kryss rutan blockera program som inte används under Microsoft Defender ATP-integrering är markerad.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-207">![Image of_the Microsoft Defender ATP page where the block unsanctioned apps checkbox under Microsoft Defender ATP integration is selected.</span></span> <span data-ttu-id="2b6d5-208">Klicka på Spara.](../../media/mtp-eval-56.png)</span><span class="sxs-lookup"><span data-stu-id="2b6d5-208">Click save.](../../media/mtp-eval-56.png)</span></span> <br>

5. <span data-ttu-id="2b6d5-209">Under Inställningar för moln identifiering väljer du **användar upplevelse**och aktiverar integrationen med Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-209">Under Cloud discovery settings, select **User enrichment**, then enable the integration with Azure Active Directory.</span></span>
<span data-ttu-id="2b6d5-210">![Bild av avsnittet användar berikning där kryss rutan utökad identifiering av användar identifierare med Azure Active Directory-username är markerad](../../media/mtp-eval-57.png)</span><span class="sxs-lookup"><span data-stu-id="2b6d5-210">![Image of User enrichment section where the enrich discovered user identifiers with Azure Active Directory usernames checkbox is selected](../../media/mtp-eval-57.png)</span></span> <br>

## <a name="configure-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="2b6d5-211">Konfigurera Microsoft Defender Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="2b6d5-211">Configure Microsoft Defender Advanced Threat Protection</span></span>
>[!NOTE]
><span data-ttu-id="2b6d5-212">Hoppa över det här steget om du redan har aktiverat Microsoft Defender Avancerat skydd.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-212">Skip this step if you've already enabled Microsoft Defender Advanced Threat Protection.</span></span>

1. <span data-ttu-id="2b6d5-213">Gå till [Microsoft 365 säkerhets Center](https://security.microsoft.com/info)  >  **fler resurser**  >  **Microsoft Defender säkerhets Center**.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-213">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Defender Security Center**.</span></span> <span data-ttu-id="2b6d5-214">Klicka på **Öppna**.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-214">Click **Open**.</span></span>
<br><span data-ttu-id="2b6d5-215">![Bild of_Microsoft Defender säkerhets Center på sidan Microsoft 365 Security Center](../../media/mtp-eval-58.png)</span><span class="sxs-lookup"><span data-stu-id="2b6d5-215">![Image of_Microsoft Defender Security Center option in the Microsoft 365 Security Center page](../../media/mtp-eval-58.png)</span></span> <br>
 
2. <span data-ttu-id="2b6d5-216">Följ guiden för avancerat skydd mot Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-216">Follow the Microsoft Defender Advanced Threat Protection wizard.</span></span> <span data-ttu-id="2b6d5-217">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-217">Click **Next**.</span></span> 
<br><span data-ttu-id="2b6d5-218">![Bild of_the sidan Välkommen till Microsoft Defender säkerhets Center](../../media/mtp-eval-59.png)</span><span class="sxs-lookup"><span data-stu-id="2b6d5-218">![Image of_the Microsoft Defender Security Center welcome wizard page](../../media/mtp-eval-59.png)</span></span> <br>

3. <span data-ttu-id="2b6d5-219">Välj baserat på din önskade lagrings plats för data, bevarande princip för data, organisations storlek och val för förhands gransknings funktioner.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-219">Choose based on your preferred data storage location, data retention policy, organization size, and opt-in for preview features.</span></span> 
<br><span data-ttu-id="2b6d5-220">![Bild of_the sida för att välja data lagrings land, bevarande princip och organisations storlek.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-220">![Image of_the page to select your data storage country, retention policy, and organization size.</span></span> <span data-ttu-id="2b6d5-221">Klicka på Nästa när du är klar med valet.](../../media/mtp-eval-60.png)</span><span class="sxs-lookup"><span data-stu-id="2b6d5-221">Click next when you're done selecting.](../../media/mtp-eval-60.png)</span></span> <br>
>[!NOTE]
><span data-ttu-id="2b6d5-222">Du kan inte ändra vissa inställningar, till exempel data lagrings plats, efteråt.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-222">You cannot change some of the settings, like data storage location, afterwards.</span></span> 
<br>

<span data-ttu-id="2b6d5-223">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-223">Click **Next**.</span></span> 

4. <span data-ttu-id="2b6d5-224">Klicka på **Fortsätt** så etableras din Microsoft Defender ATP-klient.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-224">Click **Continue** and it will provision your Microsoft Defender ATP tenant.</span></span>
<br><span data-ttu-id="2b6d5-225">![Bild of_the sida där du uppmanas att klicka på knappen Fortsätt för att skapa din moln instans](../../media/mtp-eval-61.png)</span><span class="sxs-lookup"><span data-stu-id="2b6d5-225">![Image of_the page prompting you click the continue button to create your cloud instance](../../media/mtp-eval-61.png)</span></span> <br>

5. <span data-ttu-id="2b6d5-226">Ta fram dina slut punkter via grup principer, Microsoft slut punkts hanteraren eller genom att köra ett lokalt skript till Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-226">Onboard your endpoints through Group Policies, Microsoft Endpoint Manager or by running a local script to Microsoft Defender ATP.</span></span> <span data-ttu-id="2b6d5-227">För enkelhetens skull använder den här guiden det lokala skriptet.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-227">For simplicity, this guide uses the local script.</span></span>

6. <span data-ttu-id="2b6d5-228">Klicka på **Ladda ned paket** och kopiera registrerings skriptet till din slut punkt (er).</span><span class="sxs-lookup"><span data-stu-id="2b6d5-228">Click **Download package** and copy the onboarding script to your endpoint(s).</span></span>  
<br><span data-ttu-id="2b6d5-229">![Bild of_page du uppmanas att klicka på knappen Ladda ned paket för att kopiera det inbyggda skriptet till slut punkten eller slut punkterna](../../media/mtp-eval-62.png)</span><span class="sxs-lookup"><span data-stu-id="2b6d5-229">![Image of_page prompting you click the Download package button to copy the onboarding script to your endpoint or endpoints](../../media/mtp-eval-62.png)</span></span> <br>

7. <span data-ttu-id="2b6d5-230">Kör skriptet som administratör på slut punkten och välj Y.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-230">On your endpoint, run the onboarding script as Administrator and choose Y.</span></span>
<br><span data-ttu-id="2b6d5-231">![Bild of_the kommando rad där du kör det inbyggda skriptet och väljer sedan Y för att fortsätta](../../media/mtp-eval-63.png)</span><span class="sxs-lookup"><span data-stu-id="2b6d5-231">![Image of_the commandline where you run the onboarding script and choose Y to proceed](../../media/mtp-eval-63.png)</span></span> <br>

8. <span data-ttu-id="2b6d5-232">Grattis! du har öppnat din första slut punkt.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-232">Congratulations, you've onboarded your first endpoint.</span></span>  
<br>![Bild of_the kommando rad där du får bekräftelse på att du har öppnat din första slut punkt.](../../media/mtp-eval-64.png) <br>

9. <span data-ttu-id="2b6d5-235">Kopiera – klistra in identifierings testet från guiden Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-235">Copy-paste the detection test from the Microsoft Defender ATP wizard.</span></span>
<br><span data-ttu-id="2b6d5-236">![Bild of_the kör ett identifierings test steg där du bör Klicka på Kopiera för att kopiera det identifierings test som du vill klistra in i kommando tolken](../../media/mtp-eval-65.png)</span><span class="sxs-lookup"><span data-stu-id="2b6d5-236">![Image of_the run a detection test step where you should click Copy to copy the detection test script that you should paste in the command prompt](../../media/mtp-eval-65.png)</span></span> <br>

10. <span data-ttu-id="2b6d5-237">Kopiera PowerShell-skriptet till en upphöjd kommando tolk och kör det.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-237">Copy the PowerShell script to an elevated command prompt and run it.</span></span> 
<br><span data-ttu-id="2b6d5-238">![Bild of_command fråga var du bör kopiera PowerShell-skriptet till en upphöjd kommando tolk och köra det](../../media/mtp-eval-66.png)</span><span class="sxs-lookup"><span data-stu-id="2b6d5-238">![Image of_command prompt where you should copy the PowerShell script to an elevated command prompt and run it](../../media/mtp-eval-66.png)</span></span> <br>

11. <span data-ttu-id="2b6d5-239">Välj **börja använda Microsoft Defender ATP** från guiden.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-239">Select **Start using Microsoft Defender ATP** from the Wizard.</span></span>
<br><span data-ttu-id="2b6d5-240">![Bild of_the bekräfta meddelande i guiden där du bör Klicka på börja använda Microsoft Defender ATP](../../media/mtp-eval-67.png)</span><span class="sxs-lookup"><span data-stu-id="2b6d5-240">![Image of_the confirmation prompt from the wizard where you should click Start using Microsoft Defender ATP](../../media/mtp-eval-67.png)</span></span> <br>
 
12. <span data-ttu-id="2b6d5-241">Gå till [Microsoft Defender säkerhets Center](https://securitycenter.windows.com/).</span><span class="sxs-lookup"><span data-stu-id="2b6d5-241">Visit the [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span></span> <span data-ttu-id="2b6d5-242">Gå till **Inställningar** och välj sedan **avancerade funktioner**.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-242">Go to **Settings** and then select **Advanced features**.</span></span> 
<br><span data-ttu-id="2b6d5-243">![Bild of_Microsoft Defender säkerhets Center-menyn inställningar där du bör välja avancerade funktioner](../../media/mtp-eval-68.png)</span><span class="sxs-lookup"><span data-stu-id="2b6d5-243">![Image of_Microsoft Defender Security Center Settings menu where you should select Advanced features](../../media/mtp-eval-68.png)</span></span> <br>

13. <span data-ttu-id="2b6d5-244">Aktivera integrationen med **Avancerat Azure-skyddat skydd**.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-244">Turn on the integration with **Azure Advanced Threat Protection**.</span></span>  
<br><span data-ttu-id="2b6d5-245">![Bild of_Microsoft Defender säkerhets Center avancerade funktioner, alternativet för Azure Avancerat skydds alternativ växling som du måste aktivera](../../media/mtp-eval-69.png)</span><span class="sxs-lookup"><span data-stu-id="2b6d5-245">![Image of_Microsoft Defender Security Center Advanced features, Azure Advanced Threat Protection option toggle that you need to turn on](../../media/mtp-eval-69.png)</span></span> <br>

14. <span data-ttu-id="2b6d5-246">Aktivera integrationen med **Office 365 Threat Intelligence**.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-246">Turn on the integration with **Office 365 Threat Intelligence**.</span></span>
<br><span data-ttu-id="2b6d5-247">![Bild of_Microsoft Defender säkerhets Center avancerade funktioner, alternativ för Office 365 Threat Intelligence växla till att aktivera](../../media/mtp-eval-70.png)</span><span class="sxs-lookup"><span data-stu-id="2b6d5-247">![Image of_Microsoft Defender Security Center Advanced features, Office 365 Threat Intelligence option toggle that you need to turn on](../../media/mtp-eval-70.png)</span></span> <br>

15. <span data-ttu-id="2b6d5-248">Aktivera integrering med **säkerhet för Microsoft Cloud App**.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-248">Turn on integration with **Microsoft Cloud App Security**.</span></span>
<br><span data-ttu-id="2b6d5-249">![Bild of_Microsoft Defender säkerhets Center avancerade funktioner, säkerhets alternativ för Microsoft Cloud App](../../media/mtp-eval-71.png)</span><span class="sxs-lookup"><span data-stu-id="2b6d5-249">![Image of_Microsoft Defender Security Center Advanced features, Microsoft Cloud App Security option toggle that you need to turn on](../../media/mtp-eval-71.png)</span></span> <br>

16. <span data-ttu-id="2b6d5-250">Rulla nedåt och klicka på **Spara inställningar** för att bekräfta de nya integreringarna.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-250">Scroll down and click **Save preferences** to confirm the new integrations.</span></span>
<br><span data-ttu-id="2b6d5-251">![Knappen bild of_Save inställningar som du måste klicka på](../../media/mtp-eval-72.png)</span><span class="sxs-lookup"><span data-stu-id="2b6d5-251">![Image of_Save preferences button that you need to click](../../media/mtp-eval-72.png)</span></span> <br>

## <a name="start-the-microsoft-threat-protection-service"></a><span data-ttu-id="2b6d5-252">Starta tjänsten Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="2b6d5-252">Start the Microsoft Threat Protection service</span></span>
>[!NOTE]
><span data-ttu-id="2b6d5-253">Från och med den 1 juni 2020 aktive ras Microsoft automatiskt skydds funktioner för alla kvalificerade klient organisationer.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-253">Starting June 1, 2020, Microsoft automatically enables Microsoft Threat Protection features for all eligible tenants.</span></span> <span data-ttu-id="2b6d5-254">Mer information finns i den här [artikeln i Microsoft Tech community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) .</span><span class="sxs-lookup"><span data-stu-id="2b6d5-254">See this [Microsoft Tech Community article on license eligibility](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) for details.</span></span> 
<br>

<span data-ttu-id="2b6d5-255">Gå till [Microsoft 365 säkerhets Center](https://security.microsoft.com/homepage).</span><span class="sxs-lookup"><span data-stu-id="2b6d5-255">Go to [Microsoft 365 Security Center](https://security.microsoft.com/homepage).</span></span> <span data-ttu-id="2b6d5-256">Navigera till **Inställningar** och välj sedan **Microsoft Threat Protection**.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-256">Navigate to **Settings** and then select **Microsoft Threat Protection**.</span></span>
<br><span data-ttu-id="2b6d5-257">![Skärm bild av alternativ för of_Microsoft skydd från säkerhets Center för Microsoft 365 ](../../media/mtp-eval-72b.png)</span><span class="sxs-lookup"><span data-stu-id="2b6d5-257">![Image of_Microsoft Threat Protection option screenshot from the Microsoft 365 Security Center Settings page ](../../media/mtp-eval-72b.png)</span></span> <br>

<span data-ttu-id="2b6d5-258">Mer omfattande vägledning finns i [Aktivera skydd mot Microsoft Threat](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="2b6d5-258">For a more comprehensive guidance, see [Turn on Microsoft Threat Protection](mtp-enable.md).</span></span> 

<span data-ttu-id="2b6d5-259">Grattis!</span><span class="sxs-lookup"><span data-stu-id="2b6d5-259">Congratulations!</span></span> <span data-ttu-id="2b6d5-260">Du har just skapat ett utvärderings labb för Microsoft Threat Protection eller pilot miljö!</span><span class="sxs-lookup"><span data-stu-id="2b6d5-260">You've just created your Microsoft Threat Protection trial lab or pilot environment!</span></span> <span data-ttu-id="2b6d5-261">Nu kan du bekanta dig med användar gränssnittet för Microsoft Threat Protection!</span><span class="sxs-lookup"><span data-stu-id="2b6d5-261">Now you can familiarize yourself with the Microsoft Threat Protection user interface!</span></span> <span data-ttu-id="2b6d5-262">Se vad du kan lära dig från och hur du använder varje instrument panel för din dagliga säkerhets åtgärd: [Microsoft Threat Protection interaktiv guide](https://aka.ms/MTP-Interactive-Guide).</span><span class="sxs-lookup"><span data-stu-id="2b6d5-262">See what you can learn from and know how to use each dashboard for your day-to-day security operation tasks: [Microsoft Threat Protection interactive guide](https://aka.ms/MTP-Interactive-Guide).</span></span>

<span data-ttu-id="2b6d5-263">Sedan kan du simulera en attack och se hur funktionerna för kors produkten identifieras, skapa aviseringar och automatiskt svara på en fillös attack på en slut punkt.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-263">Next, you can simulate an attack and see how the cross product capabilities detect, create alerts, and automatically respond to a fileless attack on an endpoint.</span></span>

## <a name="next-step"></a><span data-ttu-id="2b6d5-264">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="2b6d5-264">Next step</span></span>
|<span data-ttu-id="2b6d5-265">![Fasen för attack simulering](../../media/mtp/run-sim.png)</span><span class="sxs-lookup"><span data-stu-id="2b6d5-265">![Attack simulation phase](../../media/mtp/run-sim.png)</span></span> <br>[<span data-ttu-id="2b6d5-266">Fasen för attack simulering</span><span class="sxs-lookup"><span data-stu-id="2b6d5-266">Attack simulation phase</span></span>](mtp-pilot-simulate.md) | <span data-ttu-id="2b6d5-267">Kör angrepps simuleringen för din pilot miljö för Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="2b6d5-267">Run the attack simulation for your Microsoft Threat Protection pilot environment.</span></span>
|:-------|:-----|
