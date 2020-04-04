---
title: Visa e-säkerhetsrapporter &amp; i Security Compliance Center, komprometterade användare, Kryptering, hotskyddsstatus, upptäckt av skadlig programvara, Top malware, spam detection, skickade och mottagna e-postmeddelanden, användarrapporter, läsa rapporter, upptäckt, säkerhetsdata, säkerhetsinformation
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 01/16/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
ms.collection:
- M365-security-compliance
description: Läs om hur du hittar och använder säkerhetsrapporter för e-post för din organisation. Säkerhetsrapporter för e-post &amp; finns i Säkerhetsefterlevnadscenter.
ms.openlocfilehash: b6c4e737d0bcc9f7373a669e8dcd20661733b294
ms.sourcegitcommit: ff62dd99fa0d4e780da25dc622f93ddc8f7f95a0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/03/2020
ms.locfileid: "43142720"
---
# <a name="view-email-security-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="f195d-104">Visa säkerhetsrapporter för &amp; e-post i Säkerhetsefterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="f195d-104">View email security reports in the Security &amp; Compliance Center</span></span>

<span data-ttu-id="f195d-105">Det finns en mängd olika rapporter i [Security &amp; Compliance Center](https://protection.office.com) som hjälper dig att se hur säkerhetsfunktioner för e-post, till exempel anti-spam, anti-malware och krypteringsfunktioner i Office 365 skyddar din organisation.</span><span class="sxs-lookup"><span data-stu-id="f195d-105">A variety of reports are available in the [Security &amp; Compliance Center](https://protection.office.com) to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Office 365 are protecting your organization.</span></span> <span data-ttu-id="f195d-106">Om du har [de behörigheter som krävs](#what-permissions-are-needed-to-view-these-reports)kan &amp; du visa dessa rapporter i Säkerhetsefterlevnadscenter genom att gå till **Instrumentpanelen** **för rapporter** \> .</span><span class="sxs-lookup"><span data-stu-id="f195d-106">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Security &amp; Compliance Center by going to **Reports** \> **Dashboard**.</span></span>
  
![Instrumentpanel där du ser hur avancerat skydd mot hot fungerar](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
<span data-ttu-id="f195d-108">Dina säkerhetsrapporter för e-post innehåller följande:</span><span class="sxs-lookup"><span data-stu-id="f195d-108">Your email security reports include the following:</span></span>
- <span data-ttu-id="f195d-109">[URL Threat Protection rapport](#url-threat-protection-report-new) **(NYHET!**)</span><span class="sxs-lookup"><span data-stu-id="f195d-109">[URL Threat Protection report](#url-threat-protection-report-new) (**NEW!**)</span></span>
- [<span data-ttu-id="f195d-110">Rapport över komprometterade användare</span><span class="sxs-lookup"><span data-stu-id="f195d-110">Compromised Users report</span></span>](#compromised-users-report)
- [<span data-ttu-id="f195d-111">Krypteringsrapport</span><span class="sxs-lookup"><span data-stu-id="f195d-111">Encryption report</span></span>](#encryption-report)
- [<span data-ttu-id="f195d-112">Statusrapport för hotskydd</span><span class="sxs-lookup"><span data-stu-id="f195d-112">Threat Protection Status report</span></span>](#threat-protection-status-report) 
- [<span data-ttu-id="f195d-113">Rapport över identifieringar av skadlig kod</span><span class="sxs-lookup"><span data-stu-id="f195d-113">Malware Detections report</span></span>](#malware-detections-report) 
- [<span data-ttu-id="f195d-114">Topp malware rapport</span><span class="sxs-lookup"><span data-stu-id="f195d-114">Top Malware report</span></span>](#top-malware-report)
- [<span data-ttu-id="f195d-115">Topprapport för avsändare och mottagare</span><span class="sxs-lookup"><span data-stu-id="f195d-115">Top Senders and Recipients report</span></span>](#top-senders-and-recipients-report)
- [<span data-ttu-id="f195d-116">Rapport över falska identifieringar</span><span class="sxs-lookup"><span data-stu-id="f195d-116">Spoof Detections report</span></span>](#spoof-detections-report)
- [<span data-ttu-id="f195d-117">Rapport om skräppostidentifieringar</span><span class="sxs-lookup"><span data-stu-id="f195d-117">Spam Detections report</span></span>](#spam-detections-report)
- [<span data-ttu-id="f195d-118">Skickad och mottagen e-postrapport</span><span class="sxs-lookup"><span data-stu-id="f195d-118">Sent and received email report</span></span>](#sent-and-received-email-report)
- [<span data-ttu-id="f195d-119">Rapport över användarrapporterade meddelanden</span><span class="sxs-lookup"><span data-stu-id="f195d-119">User-reported messages report</span></span>](#user-reported-messages-report)


## <a name="url-threat-protection-report-new"></a><span data-ttu-id="f195d-120">URL Threat Protection rapport **(NYHET!**)</span><span class="sxs-lookup"><span data-stu-id="f195d-120">URL Threat Protection report (**NEW!**)</span></span>

<span data-ttu-id="f195d-121">Url-rapporten för hotskydd är tillgänglig för alla med:</span><span class="sxs-lookup"><span data-stu-id="f195d-121">The URL Threat Protection report is available to anyone with:</span></span>

- <span data-ttu-id="f195d-122">Ett exchange online-skydd *och* avancerat hotskyddstillägg (plan 1 *eller* plan 2)</span><span class="sxs-lookup"><span data-stu-id="f195d-122">An Exchange Online Protection, *and* Advanced Threat Protection add-on (Plan 1 *or* Plan 2)</span></span> 
- <span data-ttu-id="f195d-123">En Microsoft 365 E5-prenumeration</span><span class="sxs-lookup"><span data-stu-id="f195d-123">A Microsoft 365 E5 subscription</span></span>

<span data-ttu-id="f195d-124">Detta är en klickcentrerad rapport som har två aggregerade vyer.</span><span class="sxs-lookup"><span data-stu-id="f195d-124">This is a 'click-centric' report that has two aggregated views.</span></span>
 
1. <span data-ttu-id="f195d-125">Den första vyn är genom *URL-klickskyddsåtgärd*, som fokuserar på att visa antalet URL-klick för användare i klienten och resultatet av klicket.</span><span class="sxs-lookup"><span data-stu-id="f195d-125">The first view is by *URL click-protection action*, which is focused on showing the number of URL clicks by users within the tenant, and the result of the click.</span></span> <span data-ttu-id="f195d-126">Ett klick här anger att användaren har klickat genom blocksidan till den skadliga webbplatsen (detta kan inaktiveras av administratören inom en princip för säkra länkar).</span><span class="sxs-lookup"><span data-stu-id="f195d-126">A click here indicates that the user has clicked through the block page to the malicious website (this can be disabled by the administrator within a Safe Links policy).</span></span>
 
2. <span data-ttu-id="f195d-127">Den andra vyn är *URL-klick för program*, som visar antalet webbadresser klickar i olika program som stöder säkra länkar idag, till exempel i en e-postklient eller i Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="f195d-127">The second view is *URL click by applications*, which shows the number of URLs click in different applications that support Safe Links today, such as in an email client or in Microsoft Word.</span></span> <span data-ttu-id="f195d-128">Data i båda aggregerade vyer uppdateras en gång var fjärde timme.</span><span class="sxs-lookup"><span data-stu-id="f195d-128">Data in both aggregated views are refreshed once every 4 hours.</span></span>

<span data-ttu-id="f195d-129">Informationstabellen i rapporten URL Threat Protection ger en vy i nästan realtid över alla klick som sker i klienten, och den innehåller undersökande information som *användarnamn*, *URL*, *nätverksmeddelande-ID* (om webbadressen klickades från ett e-postmeddelande) och annan värdefull information som är användbar för undersökningar och analyser.</span><span class="sxs-lookup"><span data-stu-id="f195d-129">The details table of the URL Threat Protection report provides a near-real-time view of all clicks that happen within the tenant, and it includes investigative information such as *username*, *URL*, the *network message ID* (if the URL was clicked from an email), and other valuable pieces of information useful for investigations and analyses.</span></span>  

<span data-ttu-id="f195d-130">Som standard visar rapporten bara data om klick från webbadresser som blockerades av säkra länkar, men det är också möjligt att se information för alla URL-klick genom att markera kryssrutan *Tillåtna webbadresser* i filtren.</span><span class="sxs-lookup"><span data-stu-id="f195d-130">By default, the report only shows data on clicks from URLs that were blocked by Safe Links, but it is also possible to see information for all URL clicks through selecting *Allowed URLs* checkbox in the filters.</span></span>  

<span data-ttu-id="f195d-131">Den här rapporten kommer inte att ha data med klick från användare där principen Säkra länkar som tillämpas har alternativet *Spåra inte användarens klick* markerat.</span><span class="sxs-lookup"><span data-stu-id="f195d-131">This report will not have data of clicks from users where the Safe Links policy applied has the *Do not track user clicks* option selected.</span></span>

![Bild av URL-hotskyddsrapporten i aktion.](../../media/tp-URLThreatProRpt1.PNG)

## <a name="compromised-users-report"></a><span data-ttu-id="f195d-133">Rapport över komprometterade användare</span><span class="sxs-lookup"><span data-stu-id="f195d-133">Compromised Users report</span></span> 

<span data-ttu-id="f195d-134">Den här rapporten, som är tillgänglig för alla med Exchange Online Protection, visar antalet användarkonton som markerats som misstänkta eller begränsade användare, data som är särskilt användbara eftersom konton anger något av de tillstånd som anger att användarkontot kan vara problematiskt eller till och med komprometterat.</span><span class="sxs-lookup"><span data-stu-id="f195d-134">This report, available to anyone with Exchange Online Protection, shows the number of user accounts marked as Suspicious or Restricted users, data particularly useful as accounts enter either of the states that indicate the user account may be problematic, or even compromised.</span></span> <span data-ttu-id="f195d-135">Med frekvent användning kan rapporten Komprometterad användare upptäcka toppar, och till och med trender, i konton som är markerade i misstänkta eller begränsade tillstånd, vilket ger bevis för att det kan finnas ett problem med säkerheten och välbefinnandet för din klient.</span><span class="sxs-lookup"><span data-stu-id="f195d-135">With frequent use, the Compromised User report can spot spikes, and even trends, in accounts marked in suspicious or restricted states, giving evidence there could be an issue with security and the wellness of your tenant.</span></span>

![De komprometterade användarna rapporterar så som det visas i Office 365.](../../media/tp-threatProtectStatRpt-CompromisedUserRpt.png)

## <a name="encryption-report"></a><span data-ttu-id="f195d-137">Krypteringsrapport</span><span class="sxs-lookup"><span data-stu-id="f195d-137">Encryption report</span></span>

<span data-ttu-id="f195d-138">**Krypteringsrapporten** visar information om e-postmeddelanden som har krypterats, antingen via organisationens principer eller via slutanvändarkontroller.</span><span class="sxs-lookup"><span data-stu-id="f195d-138">The **Encryption report** shows information about email messages that were encrypted, either through your organization's policies, or through end-user controls.</span></span> <span data-ttu-id="f195d-139">Organisationens säkerhetsteam kan använda information i den här rapporten för att identifiera mönster och proaktivt tillämpa eller justera principer för känsliga e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="f195d-139">Your organization's security team can use information in this report to identify patterns and proactively apply or adjust policies for sensitive email messages.</span></span>

<span data-ttu-id="f195d-140">Om du vill visa den här rapporten går du till rapporten **Rapporter** \> **med instrumentpanelskryptering** \> **Encryption report**i säkerhets- & compliance center .</span><span class="sxs-lookup"><span data-stu-id="f195d-140">To view this report, in the Security & Compliance Center, go to **Reports** \> **Dashboard** \> **Encryption report**.</span></span>

![Krypteringsrapport](../../media/encryptionreport-defaultview.png) 

<span data-ttu-id="f195d-142">När rapporten öppnas första gången visas data om krypteringsmetoder som används i e-postmeddelanden under de senaste sju (7) dagarna.</span><span class="sxs-lookup"><span data-stu-id="f195d-142">When the report first opens, you'll see data about encryption methods used on email messages for the past seven (7) days.</span></span> <span data-ttu-id="f195d-143">Du kan ändra datumintervallet och informationen som visas i rapporten genom att klicka på **Filter** i det övre högra hörnet på skärmen.</span><span class="sxs-lookup"><span data-stu-id="f195d-143">You can change the date range and the details that are displayed in the report by clicking **Filters** in the upper right corner of the screen.</span></span>

![Filter för krypteringsrapport](../../media/encryptionreport-filters.png)   

<span data-ttu-id="f195d-145">Du kan också använda **menyn Dela upp efter** för att visa data efter krypteringsmall (eller metod).</span><span class="sxs-lookup"><span data-stu-id="f195d-145">You can also use the **Break down by** menu to view data by encryption template (or method).</span></span>

![Krypteringsmetod eller mall](../../media/encryptionreport-breakdownby.png)

<span data-ttu-id="f195d-147">Och du kan använda **Visa data efter** meny för att ändra vyn för att se antalet krypterade meddelanden till de fem främsta mottagardomänerna.</span><span class="sxs-lookup"><span data-stu-id="f195d-147">And, you can use the **View data by** menu to change the view to see counts of encrypted messages to the top five recipient domains.</span></span>

![Data för krypteringsrapportvy efter meny](../../media/encryptionreport-viewdataby.png)

<span data-ttu-id="f195d-149">Med flexibiliteten i den nya krypteringsrapporten kan du visa trender och vidta lämpliga åtgärder.</span><span class="sxs-lookup"><span data-stu-id="f195d-149">With the flexibility of the new Encryption report, you can view trends and take appropriate actions.</span></span> <span data-ttu-id="f195d-150">Om du till exempel ser ett stort antal e-postmeddelanden krypterade av användare kanske du vill lägga till en krypteringsprincip för att automatisera kryptering för vissa användningsfall.</span><span class="sxs-lookup"><span data-stu-id="f195d-150">For example, if you see a high number of email messages encrypted by users, you might want to add an encryption policy to automate encryption for certain use cases.</span></span> <span data-ttu-id="f195d-151">(Mer information om detta finns i [Definiera regler för e-postflöde för att kryptera e-postmeddelanden i Office 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).) Om du har ett antal krypteringsmallar tillgängliga men ingen använder dem kan du undersöka om användarna behöver utbildning för den funktionen.</span><span class="sxs-lookup"><span data-stu-id="f195d-151">(To get help with that, see [Define mail flow rules to encrypt email messages in Office 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).) As another example, if you have a number of encryption templates available but no one is using them, you might explore whether users need training for that feature.</span></span> 

<span data-ttu-id="f195d-152">Med hjälp av den här rapporten kan organisationens säkerhets- och efterlevnadsteam övervaka hur meddelandekryptering används och om ytterligare åtgärder behövs.</span><span class="sxs-lookup"><span data-stu-id="f195d-152">Use this report enables your organization's security and compliance team to monitor how message encryption is being used, and whether further actions are needed.</span></span> <span data-ttu-id="f195d-153">Mer information om kryptering finns [i E-postkryptering i Office 365](../../compliance/email-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="f195d-153">To learn more about encryption, see [Email encryption in Office 365](../../compliance/email-encryption.md).</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="f195d-154">Statusrapport för hotskydd</span><span class="sxs-lookup"><span data-stu-id="f195d-154">Threat Protection Status report</span></span>

<span data-ttu-id="f195d-155">Rapporten **Status för hotskydd** är en smart rapport som visar skadlig e-post som har upptäckts och blockerats av Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="f195d-155">The **Threat Protection Status** report is a smart report that shows malicious email that was detected and blocked by Exchange Online Protection.</span></span> <span data-ttu-id="f195d-156">Den här rapporten är användbar för att visa e-post som identifierats som skadlig kod eller ett nätfiskeförsök över tid (upp till 90 dagar), och den gör det möjligt för säkerhetsadministratörer att identifiera trender eller avgöra om principer behöver justeras.</span><span class="sxs-lookup"><span data-stu-id="f195d-156">This report is useful for viewing email identified as malware or a phishing attempt over time (up to 90 days), and it enables security administrators to identify trends or determine whether policies need adjustments.</span></span>

> [!NOTE]
> <span data-ttu-id="f195d-157">En rapport om status för hotskydd är tillgänglig för kunder som har antingen [Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) eller [Exchange Online Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/what-is-eop) (EOP). Informationen som visas i rapporten Status för hotskydd för ATP-kunder innehåller dock sannolikt andra data än vad EOP-kunder kan se.</span><span class="sxs-lookup"><span data-stu-id="f195d-157">A Threat Protection Status report is available to customers who have either [Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) or [Exchange Online Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/what-is-eop) (EOP); however, the information that is displayed in the Threat Protection Status report for ATP customers will likely contain different data than what EOP customers might see.</span></span> <span data-ttu-id="f195d-158">EOP-kunder kan till exempel visa information om skadlig kod som identifierats i e-post, men inte information om [skadliga filer som identifierats i SharePoint Online, OneDrive eller Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams), en ATP-specifik funktion.</span><span class="sxs-lookup"><span data-stu-id="f195d-158">For example, EOP customers can view information about malware detected in email, but not information about [malicious files detected in SharePoint Online, OneDrive, or Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams), an ATP-specific capability.</span></span> <span data-ttu-id="f195d-159">(Läs[mer om ATP-rapporter](https://docs.microsoft.com/microsoft-365/security/office-365-security/view-reports-for-atp).)</span><span class="sxs-lookup"><span data-stu-id="f195d-159">([Learn more about ATP reports](https://docs.microsoft.com/microsoft-365/security/office-365-security/view-reports-for-atp).)</span></span>
  
<span data-ttu-id="f195d-160">Om du vill visa [ &amp; den](https://protection.office.com)här rapporten går du till **Rapporter om** \> **skydd av instrumentpanelshotskydd** **Dashboard** \> .</span><span class="sxs-lookup"><span data-stu-id="f195d-160">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>
  
![Statusrapport för hotskydd](../../media/0ff86e12-c2b2-4d89-92a5-cefb054dc070.png)
  
<span data-ttu-id="f195d-162">När du först öppnar rapporten Status för hotskydd visar rapporten data för de senaste sju dagarna som standard. Du kan dock klicka på **Filter** och ändra datumintervallet i upp till 90 dagars detalj.</span><span class="sxs-lookup"><span data-stu-id="f195d-162">When you first open the Threat Protection Status report, the report shows data for the past seven days by default; however, you can click **Filters** and change the date range for up to 90 days of detail.</span></span> <span data-ttu-id="f195d-163">(Om du använder en utvärderingsprenumeration kan du vara begränsad till 30 dagars data.)</span><span class="sxs-lookup"><span data-stu-id="f195d-163">(If you are using a trial subscription, you might be limited to 30 days' of data.)</span></span>

<span data-ttu-id="f195d-164">Den här rapporten är användbar för att visa effektiviteten och effekten av organisationens [Exchange Online Protection-funktioner](https://docs.microsoft.com/microsoft-365/security/office-365-security/eop-features)och för långsiktiga trender.</span><span class="sxs-lookup"><span data-stu-id="f195d-164">This report is useful for viewing the effectiveness and impact of your organization's [Exchange Online Protection features](https://docs.microsoft.com/microsoft-365/security/office-365-security/eop-features), and for longer-term trending.</span></span> 
  
![Rapportfilter för status för hot](../../media/ab6b6b8d-e97a-4c3a-8fb1-c4940dcb7a07.png)
  
<span data-ttu-id="f195d-166">Du kan också välja om du vill visa data för e-post som identifierats som skadlig, e-post som identifierats som ett nätfiskeförsök eller e-post som identifierats som innehållande skadlig kod.</span><span class="sxs-lookup"><span data-stu-id="f195d-166">You can also choose whether to view data for email identified as malicious, email identified as a phishing attempts, or email identified as containing malware.</span></span>
  
![Alternativ för rapportvy för hotskyddsstatus](../../media/d429ecd7-cb7a-4c99-8d27-79a2832cf467.png)
  
## <a name="malware-detections-report"></a><span data-ttu-id="f195d-168">Rapport över identifieringar av skadlig kod</span><span class="sxs-lookup"><span data-stu-id="f195d-168">Malware Detections report</span></span>

<span data-ttu-id="f195d-169">Rapporten **Identifiering av skadlig kod** visar hur många inkommande och utgående meddelanden som har identifierats som innehållande skadlig kod för din organisation.</span><span class="sxs-lookup"><span data-stu-id="f195d-169">The **Malware Detections** report shows how many incoming and outgoing messages were detected as containing malware for your organization.</span></span> 
  
<span data-ttu-id="f195d-170">Om du vill visa [ &amp; den](https://protection.office.com)här rapporten går du till **Rapporter om** \> identifiering av **skadlig kod för instrumentpanelen** \> **Malware Detections**.</span><span class="sxs-lookup"><span data-stu-id="f195d-170">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Malware Detections**.</span></span>
  
![Exempel på identifiering av skadlig kod Rapport](../../media/a1ba61a3-565a-46d6-b0d5-6a6cff6b31d7.png)
  
<span data-ttu-id="f195d-172">I likhet med andra rapporter, till exempel [rapporten Status för hotskydd,](#threat-protection-status-report)visar rapporten data för de senaste sju dagarna som standard.</span><span class="sxs-lookup"><span data-stu-id="f195d-172">Similar to other reports, like the [Threat Protection Status report](#threat-protection-status-report), the report displays data for the past seven days by default.</span></span> <span data-ttu-id="f195d-173">Du kan dock välja **Filter för** att ändra datumintervallet.</span><span class="sxs-lookup"><span data-stu-id="f195d-173">However, you can choose **Filters** to change the date range.</span></span> 
  
## <a name="top-malware-report"></a><span data-ttu-id="f195d-174">Topp malware rapport</span><span class="sxs-lookup"><span data-stu-id="f195d-174">Top Malware report</span></span>

<span data-ttu-id="f195d-175">Top **Malware** rapporten visar de olika typer av skadlig kod som upptäcktes av [Exchange Online](https://docs.microsoft.com/microsoft-365/security/office-365-security/eop-features).</span><span class="sxs-lookup"><span data-stu-id="f195d-175">The **Top Malware** report shows the various kinds of malware that was detected by [Exchange Online](https://docs.microsoft.com/microsoft-365/security/office-365-security/eop-features).</span></span> 
  
<span data-ttu-id="f195d-176">Om du vill visa [ &amp; den](https://protection.office.com)här rapporten går du till **Rapporter om** \> **instrumentpanelens** \> **övre skadlig kod**.</span><span class="sxs-lookup"><span data-stu-id="f195d-176">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Top Malware**.</span></span>
  
![SCC - EOP Top Malware](../../media/763330b3-f56e-4ba4-b0bb-051500ae950a.png)
  
<span data-ttu-id="f195d-178">När du hovrar över en kil i cirkeldiagrammet kan du se namnet på en typ av skadlig kod och hur många meddelanden som har upptäckts ha den skadliga koden.</span><span class="sxs-lookup"><span data-stu-id="f195d-178">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>
  
<span data-ttu-id="f195d-179">Klicka (eller tryck) på rapporten för att öppna den i ett nytt webbläsarfönster, där du kan få en mer detaljerad vy av rapporten.</span><span class="sxs-lookup"><span data-stu-id="f195d-179">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
![Den här rapporten visar den vanligaste skadliga koden som har identifierats för din organisation](../../media/3fded224-fb31-4713-86f2-8afce5ce2991.png)
  
<span data-ttu-id="f195d-181">Under diagrammet visas en lista över upptäckt skadlig kod och hur många meddelanden som har upptäckts som att ha den skadliga koden.</span><span class="sxs-lookup"><span data-stu-id="f195d-181">Below the chart, you'll see a list of detected malware and how many messages were detected as having that malware.</span></span>
  
## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="f195d-182">Topprapport för avsändare och mottagare</span><span class="sxs-lookup"><span data-stu-id="f195d-182">Top Senders and Recipients report</span></span>

<span data-ttu-id="f195d-183">Rapporten **Toppavsändare och mottagare** är ett cirkeldiagram som visar dina främsta e-postavsändare.</span><span class="sxs-lookup"><span data-stu-id="f195d-183">The **Top Senders and Recipients** report is a pie chart showing your top email senders.</span></span> 
  
<span data-ttu-id="f195d-184">Om du vill visa [ &amp; den](https://protection.office.com)här rapporten går du till Rapporter över **avsändare och mottagare för** **instrumentpanelen** \> **Reports** \> .</span><span class="sxs-lookup"><span data-stu-id="f195d-184">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Top Senders and Recipients**.</span></span>
  
![Om du vill visa &amp; den här rapporten \> går \> du till Rapporter över avsändare och mottagare av instrumentpanelen](../../media/b5506b5c-2420-4a5a-9ea3-d654294ac838.png)
  
<span data-ttu-id="f195d-186">När du hovrar över en kil i cirkeldiagrammet kan du se ett antal meddelanden som skickas eller tas emot.</span><span class="sxs-lookup"><span data-stu-id="f195d-186">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>
  
<span data-ttu-id="f195d-187">Klicka (eller tryck) på rapporten för att öppna den i ett nytt webbläsarfönster, där du kan få en mer detaljerad vy av rapporten.</span><span class="sxs-lookup"><span data-stu-id="f195d-187">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
<span data-ttu-id="f195d-188">Använd listan **Visa data för** att välja om du vill visa data för de främsta avsändarna, mottagarna, skräppostmottagarna och mottagarna av skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="f195d-188">Use the **Show data for** list to choose whether to view data for top senders, receivers, spam recipients, and malware recipients.</span></span> <span data-ttu-id="f195d-189">Du kan också se vem som fick skadlig kod som upptäcktes av [Exchange Online Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/what-is-eop).</span><span class="sxs-lookup"><span data-stu-id="f195d-189">You can also see who received malware that was detected by [Exchange Online Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/what-is-eop).</span></span> 
  
![Använda listan Visa data för för att visa specifik information](../../media/bd91449f-7d42-4749-8666-7b44044049b8.png)
  
<span data-ttu-id="f195d-191">Under diagrammet ser du vilka de främsta e-postavsändarna eller mottagarna var, tillsammans med ett antal meddelanden som skickats eller tagits emot under den angivna tidsperioden.</span><span class="sxs-lookup"><span data-stu-id="f195d-191">Below the chart, you'll see who the top email senders or recipients were, along with a count of messages sent or received for the given time period.</span></span>
  
## <a name="spoof-detections-report"></a><span data-ttu-id="f195d-192">Rapport över falska identifieringar</span><span class="sxs-lookup"><span data-stu-id="f195d-192">Spoof Detections report</span></span>

<span data-ttu-id="f195d-193">**Rapporten Spoof Detections** visar hur många falska e-postmeddelanden som upptäcktes och vilka som ansågs vara "bra" (falska e-postmeddelanden gjorda av legitima affärsskäl).</span><span class="sxs-lookup"><span data-stu-id="f195d-193">The **Spoof Detections** report shows how many spoof mail messages were detected, and of those, which ones were considered "good" (spoof mail done for legitimate business reasons).</span></span> 
  
<span data-ttu-id="f195d-194">Om du vill visa [ &amp; den](https://protection.office.com)här rapporten går du till **Rapporter** \> \> **instrumentpanelsspoof Mail**. **Dashboard**</span><span class="sxs-lookup"><span data-stu-id="f195d-194">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Spoof Mail**.</span></span>
  
![Gå till &amp; Rapporter \> instrumentpanelsspoof \> e-post i Säkerhetsefterlevnadscenter](../../media/0427e85c-9e40-4225-a0f0-e21a4e8b0e44.png)
  
<span data-ttu-id="f195d-196">När du hovrar över en dag i diagrammet kan du se hur många falska e-postmeddelanden som kom fram.</span><span class="sxs-lookup"><span data-stu-id="f195d-196">When you hover over a day in the chart, you can see how many spoof mail messages came through.</span></span>
  
<span data-ttu-id="f195d-197">Klicka (eller tryck) på rapporten för att öppna den i ett nytt webbläsarfönster, där du kan få en mer detaljerad vy av rapporten.</span><span class="sxs-lookup"><span data-stu-id="f195d-197">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span> <span data-ttu-id="f195d-198">Mer information om skydd mot förfalskning finns i Skydd mot förfalskning [i Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spoofing-protection).</span><span class="sxs-lookup"><span data-stu-id="f195d-198">To learn more about anti-spoof protection, see [Anti-spoofing protection in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spoofing-protection).</span></span>
  
## <a name="spam-detections-report"></a><span data-ttu-id="f195d-199">Rapport om skräppostidentifieringar</span><span class="sxs-lookup"><span data-stu-id="f195d-199">Spam Detections report</span></span>

<span data-ttu-id="f195d-200">Rapporten **Skräppostidentifieringar** visar allt skräppostinnehåll som blockeras av Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f195d-200">The **Spam Detections** report shows all the spam content blocked by Exchange Online.</span></span> <span data-ttu-id="f195d-201">Meddelanden räknas per meddelande och inte per mottagare.</span><span class="sxs-lookup"><span data-stu-id="f195d-201">Messages are counted per message, and not per recipient.</span></span> <span data-ttu-id="f195d-202">Om ett e-postmeddelande till exempel skickades till 100 mottagare i organisationen räknas det som ett meddelande.</span><span class="sxs-lookup"><span data-stu-id="f195d-202">For example, if an email message was sent to 100 recipients in your organization, it is counted as one message.</span></span>
  
<span data-ttu-id="f195d-203">Om du vill visa [ &amp; den](https://protection.office.com)här rapporten går du till Rapporter om \> **skräppostidentifieringar**på \> **instrumentpanelen** . **Reports**</span><span class="sxs-lookup"><span data-stu-id="f195d-203">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Spam Detections**.</span></span>
  
![Om du vill visa &amp; den här rapporten \> går \> du till Rapporter om EOP-skräppostidentifieringar i Säkerhetsefterlevnad](../../media/028cff3c-79ce-4ec0-8f0f-ec32ac28243a.png)
  
<span data-ttu-id="f195d-205">När du hovrar över en dag i diagrammet kan du se hur många objekt som blockerades den dagen och hur dessa objekt kategoriseras.</span><span class="sxs-lookup"><span data-stu-id="f195d-205">When you hover over a day in the chart, you can see how many items were blocked that day, as well as how those items are categorized.</span></span> <span data-ttu-id="f195d-206">Du kan till exempel se hur många skräppostmeddelanden som filtrerats och hur många objekt som kom från en blockerad IP-adress (Internet Protocol).</span><span class="sxs-lookup"><span data-stu-id="f195d-206">For example, you can see how many spam messages were filtered, and how many items came from a blocked Internet Protocol (IP) address.</span></span>
  
<span data-ttu-id="f195d-207">Klicka (eller tryck) på rapporten för att öppna den i ett nytt webbläsarfönster, där du kan få en mer detaljerad vy av rapporten.</span><span class="sxs-lookup"><span data-stu-id="f195d-207">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
![Rapporten Skräppostidentifieringar visar hur många skräppostmeddelanden som har blockerats eller filtrerats bort](../../media/370ec67d-eb30-4863-bfcf-68a41be02295.png)
  
<span data-ttu-id="f195d-209">Under diagrammet visas en lista över skräppostobjekt som har upptäckts.</span><span class="sxs-lookup"><span data-stu-id="f195d-209">Below the chart, you'll see a list of spam items that were detected.</span></span> <span data-ttu-id="f195d-210">Välj ett objekt om du vill visa ytterligare information, till exempel om skräppostobjektet var inkommande eller utgående, dess meddelande-ID och dess mottagare.</span><span class="sxs-lookup"><span data-stu-id="f195d-210">Select an item to view additional information, such as whether the spam item was inbound or outbound, its message ID, and its recipient.</span></span> <span data-ttu-id="f195d-211">Mer information om skydd mot skräppost finns i [Office 365-skydd mot skräppost via e-post](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-and-anti-malware-protection).</span><span class="sxs-lookup"><span data-stu-id="f195d-211">To learn more about anti-spam protection, see [Office 365 email anti-spam protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-and-anti-malware-protection).</span></span>
  
## <a name="sent-and-received-email-report"></a><span data-ttu-id="f195d-212">Skickad och mottagen e-postrapport</span><span class="sxs-lookup"><span data-stu-id="f195d-212">Sent and received email report</span></span>

<span data-ttu-id="f195d-213">Rapporten **Skickat och mottaget e-post** är en smart rapport som visar information om inkommande och utgående e-post, inklusive skräppostidentifieringar, skadlig kod och e-post som identifierats som "bra".</span><span class="sxs-lookup"><span data-stu-id="f195d-213">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> 
  
<span data-ttu-id="f195d-214">Om du vill visa den här rapporten går du till **Instrumentpanelen för rapporter** \> **som skickats och tagits emot via e-post**i [Säkerhetsefterlevnadscenter. &amp; ](https://protection.office.com) **Dashboard** \></span><span class="sxs-lookup"><span data-stu-id="f195d-214">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Sent and received email**.</span></span>
  
![Om du vill visa &amp; den här rapporten \> går \> du till Instrumentpanelen för rapporter som skickats och har tagits emot via e-post i](../../media/0e710ed0-1b0e-4dac-8796-94a01a710f3a.png)
  
<span data-ttu-id="f195d-216">När du hovrar över en dag i diagrammet kan du se hur många meddelanden som kom in och hur dessa meddelanden kategoriseras.</span><span class="sxs-lookup"><span data-stu-id="f195d-216">When you hover over a day in the chart, you can see how many messages came in, and how those messages are categorized.</span></span> <span data-ttu-id="f195d-217">Du kan till exempel se hur många meddelanden som har identifierats som innehållande skadlig kod och hur många som identifierades som skräppost.</span><span class="sxs-lookup"><span data-stu-id="f195d-217">For example, you can see how many messages were detected as containing malware, and how many were identified as spam.</span></span>
  
<span data-ttu-id="f195d-218">Klicka (eller tryck) på rapporten för att öppna den i ett nytt webbläsarfönster, där du kan få en mer detaljerad vy av rapporten.</span><span class="sxs-lookup"><span data-stu-id="f195d-218">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
<span data-ttu-id="f195d-219">Du kan använda listan **Dela upp efter** för att visa information efter typ eller riktning (inkommande och utgående).</span><span class="sxs-lookup"><span data-stu-id="f195d-219">You can use the **Break down by** list to view information by type or by direction (incoming and outgoing).</span></span> 
  
![Använd listan Bryt ned efter för att visa information efter typ eller riktning](../../media/a5b30c94-d75f-4bfc-851a-cb155685b177.png)
  
<span data-ttu-id="f195d-221">Under diagrammet visas en lista över e-postkategorier, till exempel **GoodMail**, **SpamContentFiltered**och så vidare.</span><span class="sxs-lookup"><span data-stu-id="f195d-221">Below the chart, you'll see a list of email categories, such as **GoodMail**, **SpamContentFiltered**, and so on.</span></span> <span data-ttu-id="f195d-222">Välj en kategori om du vill visa ytterligare information, till exempel åtgärder som har vidtagits för skadlig kod, och om e-post var inkommande eller utgående.</span><span class="sxs-lookup"><span data-stu-id="f195d-222">Select a category to view additional information, such as actions that were taken for malware, and whether email was incoming or outgoing.</span></span>
  
![Den här rapporten berättar om anti-malware, anti-spam och andra meddelandeupptäckter](../../media/9ea4b606-f27a-46ee-97a7-be018e2b839c.png)

<span data-ttu-id="f195d-224">Mer information om e-postinformation finns [i Information om e-postflöde i Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/mail-flow-intelligence-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="f195d-224">To learn more about email intelligence, see [Mail flow intelligence in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/mail-flow-intelligence-in-office-365).</span></span>
  
## <a name="user-reported-messages-report"></a><span data-ttu-id="f195d-225">Rapport över användarrapporterade meddelanden</span><span class="sxs-lookup"><span data-stu-id="f195d-225">User-reported messages report</span></span>

<span data-ttu-id="f195d-226">Rapporten Meddelanden som rapporterats av användaren visar information om **e-postmeddelanden** som användare har rapporterat som skräppost, nätfiskeförsök eller bra [e-post](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in)med hjälp av tillägget Rapportera meddelande .</span><span class="sxs-lookup"><span data-stu-id="f195d-226">The **User-reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in).</span></span>
  
<span data-ttu-id="f195d-227">Information är tillgänglig för varje meddelande, inklusive leveransorsaken, ett sådant undantag för skräppostprinciper eller e-postflödesregel som konfigurerats för din organisation.</span><span class="sxs-lookup"><span data-stu-id="f195d-227">Details are available for each message, including the delivery reason, such a spam policy exception or mail flow rule configured for your organization.</span></span> <span data-ttu-id="f195d-228">Om du vill visa information markerar du ett objekt i listan med användarrapporter och visar sedan informationen på flikarna **Sammanfattning** och **Information.**</span><span class="sxs-lookup"><span data-stu-id="f195d-228">To view details, select an item in the user-reports list, and then view the information on the **Summary** and **Details** tabs.</span></span> 
  
![Rapporten Användares rapporterade meddelanden visar meddelanden som användare som är märkta som skräppost, inte skräppost eller nätfiskeförsök.](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)
  
<span data-ttu-id="f195d-230">Så här visar du den här rapporten i [Security &amp; Compliance Center:](https://protection.office.com)</span><span class="sxs-lookup"><span data-stu-id="f195d-230">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), do one of the following:</span></span>
  
- <span data-ttu-id="f195d-231">Gå till **Dashboard** \> **Användarrapporterade meddelanden**för **hothanteringshantering** \> .</span><span class="sxs-lookup"><span data-stu-id="f195d-231">Go to **Threat management** \> **Dashboard** \> **User-reported messages**.</span></span>
    
- <span data-ttu-id="f195d-232">Gå till **Hothantering** \> **Granska** \> **användarrapporterade meddelanden**.</span><span class="sxs-lookup"><span data-stu-id="f195d-232">Go to **Threat management** \> **Review** \> **User-reported messages**.</span></span>
    
![I Security &amp; Compliance Center väljer \> \> du Meddelanden om granskning av hothanteringsanvändare](../../media/e372c57c-1414-4616-957b-bc933b8c8711.png)
  
> [!IMPORTANT]
> <span data-ttu-id="f195d-234">För att rapporten Användarrapporterade meddelanden ska fungera korrekt **måste granskningsloggning vara aktiverat** för Office 365-miljön.</span><span class="sxs-lookup"><span data-stu-id="f195d-234">In order for the User-reported messages report to work correctly, **audit logging must be turned on** for your Office 365 environment.</span></span> <span data-ttu-id="f195d-235">Detta görs vanligtvis av någon som har rollen Granskningsloggar tilldelad i Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f195d-235">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="f195d-236">Du kan läsa mer i [Aktivera och inaktivera granskningsloggsökning för Office 365](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off).</span><span class="sxs-lookup"><span data-stu-id="f195d-236">For more information, see [Turn Office 365 audit log search on or off](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off).</span></span> 
  
## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="f195d-237">Vilka behörigheter behövs för att visa dessa rapporter?</span><span class="sxs-lookup"><span data-stu-id="f195d-237">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="f195d-238">Om du vill visa och använda de rapporter som beskrivs i den här artikeln **måste du ha tilldelat en lämplig roll för både Security &amp; Compliance Center och Administrationscenter för Exchange**.</span><span class="sxs-lookup"><span data-stu-id="f195d-238">In order to view and use the reports described in this article, **you must have an appropriate role assigned for both the Security &amp; Compliance Center and the Exchange admin center**.</span></span>

- <span data-ttu-id="f195d-239">För Säkerhetsefterlevnadscenter &amp; måste du ha tilldelat en av följande roller:</span><span class="sxs-lookup"><span data-stu-id="f195d-239">For the Security &amp; Compliance Center, you must have one of the following roles assigned:</span></span>
    - <span data-ttu-id="f195d-240">Organisationshantering</span><span class="sxs-lookup"><span data-stu-id="f195d-240">Organization Management</span></span>
    - <span data-ttu-id="f195d-241">Säkerhetsadministratör (detta kan tilldelas i Azure Active[https://aad.portal.azure.com](https://aad.portal.azure.com)Directory admin center ( )</span><span class="sxs-lookup"><span data-stu-id="f195d-241">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>
    - <span data-ttu-id="f195d-242">Säkerhetsläsare</span><span class="sxs-lookup"><span data-stu-id="f195d-242">Security Reader</span></span>

- <span data-ttu-id="f195d-243">För Exchange Online måste du ha någon av följande roller tilldelad i administrationscentret för Exchange ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) eller med PowerShell-cmdletar (Se Exchange Online [PowerShell):](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="f195d-243">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):</span></span>
    - <span data-ttu-id="f195d-244">Organisationshantering</span><span class="sxs-lookup"><span data-stu-id="f195d-244">Organization Management</span></span>
    - <span data-ttu-id="f195d-245">Organisationshantering endast för vy</span><span class="sxs-lookup"><span data-stu-id="f195d-245">View-only Organization Management</span></span>
    - <span data-ttu-id="f195d-246">Rollen Endast visa mottagare</span><span class="sxs-lookup"><span data-stu-id="f195d-246">View-Only Recipients role</span></span>
    - <span data-ttu-id="f195d-247">Hantering av efterlevnad</span><span class="sxs-lookup"><span data-stu-id="f195d-247">Compliance Management</span></span>

<span data-ttu-id="f195d-248">Mer information finns i följande resurser:</span><span class="sxs-lookup"><span data-stu-id="f195d-248">To learn more, see the following resources:</span></span>

- [<span data-ttu-id="f195d-249">Permissions in the Office 365 Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="f195d-249">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)

- [<span data-ttu-id="f195d-250">Funktionsbehörigheter i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="f195d-250">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
   
   
## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="f195d-251">Vad händer om rapporterna inte visar data?</span><span class="sxs-lookup"><span data-stu-id="f195d-251">What if the reports aren't showing data?</span></span>

<span data-ttu-id="f195d-252">Om du inte ser data i dina rapporter dubbelkollar du att dina principer är korrekt konfigurerade.</span><span class="sxs-lookup"><span data-stu-id="f195d-252">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="f195d-253">Mer information finns [i Skydda mot hot i Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats).</span><span class="sxs-lookup"><span data-stu-id="f195d-253">To learn more, see [Protect against threats in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="f195d-254">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="f195d-254">Related topics</span></span>

[<span data-ttu-id="f195d-255">Skydd mot skräppost för e-post i Office 365</span><span class="sxs-lookup"><span data-stu-id="f195d-255">Office 365 Email Anti-Spam Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-and-anti-malware-protection)
  
[<span data-ttu-id="f195d-256">Rapporter och insikter i Office 365 Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="f195d-256">Reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/reports-and-insights-in-security-and-compliance)
  
[<span data-ttu-id="f195d-257">Skapa ett schema för en &amp; rapport i Säkerhetsefterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="f195d-257">Create a schedule for a report in the Security &amp; Compliance Center</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-a-schedule-for-a-report)
  
[<span data-ttu-id="f195d-258">Konfigurera och hämta en anpassad &amp; rapport i Security Compliance Center</span><span class="sxs-lookup"><span data-stu-id="f195d-258">Set up and download a custom report in the Security &amp; Compliance Center</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-and-download-a-custom-report)
  

