---
title: Återställa efter utpressningstrojanattack
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Microsoft 365-administratörer kan ta reda på hur de kan återställa efter utpressningstrojaner.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 242a4a2f43bd91d75caeaeaa0488f23a5ba4319d
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207155"
---
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a><span data-ttu-id="2705a-103">Återställ från en utpressningstrojanattack i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2705a-103">Recover from a ransomware attack in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="2705a-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="2705a-104">**Applies to**</span></span>
- [<span data-ttu-id="2705a-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="2705a-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="2705a-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="2705a-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="2705a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2705a-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="2705a-108">Även om du vidtar alla försiktighetsåtgärd för att skydda organisationen kan du fortfarande falla offer för en [utpressningstrojanattack.](/windows/security/threat-protection/intelligence/ransomware-malware)</span><span class="sxs-lookup"><span data-stu-id="2705a-108">Even if you take every precaution to protect your organization, you can still fall victim to a [ransomware](/windows/security/threat-protection/intelligence/ransomware-malware) attack.</span></span> <span data-ttu-id="2705a-109">Utpressningstrojaner är en stor verksamhet och attackerna är mycket avancerade.</span><span class="sxs-lookup"><span data-stu-id="2705a-109">Ransomware is big business, and the attacks are very sophisticated.</span></span>

<span data-ttu-id="2705a-110">Med stegen i den här artikeln får du bäst chans att återställa data och stoppa den interna spridningen av smitta.</span><span class="sxs-lookup"><span data-stu-id="2705a-110">The steps in this article will give you the best chance to recover data and stop the internal spread of infection.</span></span> <span data-ttu-id="2705a-111">Innan du börjar bör du tänka på följande:</span><span class="sxs-lookup"><span data-stu-id="2705a-111">Before you get started, consider the following items:</span></span>

- <span data-ttu-id="2705a-112">Det finns ingen garanti för att betalning av utpressningstrojanen returnerar åtkomsten till dina filer.</span><span class="sxs-lookup"><span data-stu-id="2705a-112">There's no guarantee that paying the ransom will return access to your files.</span></span> <span data-ttu-id="2705a-113">Att betala utpressningstrojanen kan faktiskt göra dig till ett mål för mer utpressningstrojaner.</span><span class="sxs-lookup"><span data-stu-id="2705a-113">In fact, paying the ransom can make you a target for more ransomware.</span></span>

  <span data-ttu-id="2705a-114">Om du redan har betalat men du har återskapat utan att använda attackerarens lösning kontaktar du din bank för att se om de kan blockera transaktionen.</span><span class="sxs-lookup"><span data-stu-id="2705a-114">If you already paid, but you recovered without using the attacker's solution, contact your bank to see if they can block the transaction.</span></span>

  <span data-ttu-id="2705a-115">Vi rekommenderar även att du rapporterar utpressningstrojanattacken till olika webbplatser för utpressningstrojaner, bedrägerirapportering och Microsoft enligt beskrivningen senare i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="2705a-115">We also recommend that you report the ransomware attack to law enforcement, scam reporting websites, and Microsoft as described later in this article.</span></span>

- <span data-ttu-id="2705a-116">Det är viktigt att du svarar snabbt på attacken och dess konsekvenser.</span><span class="sxs-lookup"><span data-stu-id="2705a-116">It's important for you respond quickly to the attack and its consequences.</span></span> <span data-ttu-id="2705a-117">Ju längre du väntar, desto mindre troligt är det att du kan återskapa berörda data.</span><span class="sxs-lookup"><span data-stu-id="2705a-117">The longer you wait, the less likely it is that you can recover the affected data.</span></span>

## <a name="step-1-verify-your-backups"></a><span data-ttu-id="2705a-118">Steg 1: Kontrollera dina säkerhetskopior</span><span class="sxs-lookup"><span data-stu-id="2705a-118">Step 1: Verify your backups</span></span>

<span data-ttu-id="2705a-119">Om du har säkerhetskopieringar offline kan du antagligen återställa krypterade **data** efter att du har tagit bort nyttolasten för utpressningstrojan (skadlig kod) från din miljö.</span><span class="sxs-lookup"><span data-stu-id="2705a-119">If you have offline backups, you can probably restore the encrypted data **after** you've removed the ransomware payload (malware) from your environment.</span></span>

<span data-ttu-id="2705a-120">Om du inte har några säkerhetskopior, eller om dina säkerhetskopior också påverkades av utpressningstrojanen, kan du hoppa över det här steget.</span><span class="sxs-lookup"><span data-stu-id="2705a-120">If you don't have backups, or if your backups were also affected by the ransomware, you can skip this step.</span></span>

## <a name="step-2-disable-exchange-activesync-and-onedrive-sync"></a><span data-ttu-id="2705a-121">Steg 2: Inaktivera Exchange ActiveSync och OneDrive-synkronisering</span><span class="sxs-lookup"><span data-stu-id="2705a-121">Step 2: Disable Exchange ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="2705a-122">Det viktiga här är att stoppa uppslaget av datakryptering genom utpressningstrojanen.</span><span class="sxs-lookup"><span data-stu-id="2705a-122">The key point here is to stop the spread of data encryption by the ransomware.</span></span>

<span data-ttu-id="2705a-123">Om du misstänker att e-postmeddelanden är målet för utpressningstrojankryptering inaktiverar du tillfälligt användarnas åtkomst till postlådor.</span><span class="sxs-lookup"><span data-stu-id="2705a-123">If you suspect email as a target of the ransomware encryption, temporarily disable user access to mailboxes.</span></span> <span data-ttu-id="2705a-124">Exchange ActiveSync synkroniserar data mellan enheter och Exchange Online-postlådor.</span><span class="sxs-lookup"><span data-stu-id="2705a-124">Exchange ActiveSync synchronizes data between devices and Exchange Online mailboxes.</span></span>

<span data-ttu-id="2705a-125">Om du vill inaktivera Exchange ActiveSync för en postlåda kan [du gå till Inaktivera Exchange ActiveSync för användare i Exchange Online.](https://support.microsoft.com/help/2795303)</span><span class="sxs-lookup"><span data-stu-id="2705a-125">To disable Exchange ActiveSync for a mailbox, see [How to disable Exchange ActiveSync for users in Exchange Online](https://support.microsoft.com/help/2795303).</span></span>

<span data-ttu-id="2705a-126">Information om hur du inaktiverar andra typer av åtkomst till en postlåda finns i:</span><span class="sxs-lookup"><span data-stu-id="2705a-126">To disable other types of access to a mailbox, see:</span></span>

- <span data-ttu-id="2705a-127">[Aktivera eller inaktivera MAPI för en postlåda.](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi)</span><span class="sxs-lookup"><span data-stu-id="2705a-127">[Enable or disable MAPI for a mailbox](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).</span></span>

- [<span data-ttu-id="2705a-128">Aktivera eller inaktivera åtkomst via POP3 eller IMAP4 för en användare</span><span class="sxs-lookup"><span data-stu-id="2705a-128">Enable or Disable POP3 or IMAP4 access for a user</span></span>](/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

<span data-ttu-id="2705a-129">Om du pausar OneDrive-synkroniseringen skyddas dina molndata från att uppdateras av potentiellt smittade enheter.</span><span class="sxs-lookup"><span data-stu-id="2705a-129">Pausing OneDrive sync will help protect your cloud data from being updated by potentially infected devices.</span></span> <span data-ttu-id="2705a-130">Mer information finns i [Pausa och återuppta synkronisering i OneDrive.](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e)</span><span class="sxs-lookup"><span data-stu-id="2705a-130">For more information, see [How to Pause and Resume sync in OneDrive](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e).</span></span>

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a><span data-ttu-id="2705a-131">Steg 3: Ta bort den skadlig programvara från de berörda enheterna</span><span class="sxs-lookup"><span data-stu-id="2705a-131">Step 3: Remove the malware from the affected devices</span></span>

<span data-ttu-id="2705a-132">Kör en fullständig, aktuell antivirussökning på alla misstänkta datorer och enheter för att identifiera och ta bort den nyttolast som är kopplad till utpressningstrojanen.</span><span class="sxs-lookup"><span data-stu-id="2705a-132">Run a full, current antivirus scan on all suspected computers and devices to detect and remove the payload that's associated with the ransomware.</span></span>

<span data-ttu-id="2705a-133">Glöm inte att skanna enheter som synkroniserar data eller mål för mappade nätverksenheter.</span><span class="sxs-lookup"><span data-stu-id="2705a-133">Don't forget to scan devices that are synchronizing data, or the targets of mapped network drives.</span></span>

<span data-ttu-id="2705a-134">Du kan använda [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) eller Microsoft Security Essentials (för [äldre klienter).](https://www.microsoft.com/download/details.aspx?id=5201)</span><span class="sxs-lookup"><span data-stu-id="2705a-134">You can use [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) or (for older clients) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201).</span></span>

<span data-ttu-id="2705a-135">Ett alternativ som också hjälper dig att ta bort utpressningstrojaner eller skadlig programvara är verktyget För borttagning av skadlig programvara [(MSRT).](https://www.microsoft.com/download/details.aspx?id=9905)</span><span class="sxs-lookup"><span data-stu-id="2705a-135">An alternative that will also help you remove ransomware or malware is the [Malicious Software Removal Tool (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905).</span></span>

<span data-ttu-id="2705a-136">Om de här alternativen inte fungerar kan du prova [Windows Defender Offline eller](https://support.microsoft.com/help/17466) Felsöka problem med att identifiera och ta bort skadlig [programvara.](https://support.microsoft.com/help/4466982)</span><span class="sxs-lookup"><span data-stu-id="2705a-136">If these options don't work, you can try [Windows Defender Offline](https://support.microsoft.com/help/17466) or [Troubleshoot problems with detecting and removing malware](https://support.microsoft.com/help/4466982).</span></span>

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a><span data-ttu-id="2705a-137">Steg 4: Återställa filer på en rensad dator eller enhet</span><span class="sxs-lookup"><span data-stu-id="2705a-137">Step 4: Recover files on a cleaned computer or device</span></span>

<span data-ttu-id="2705a-138">När du har slutfört det föregående steget för att ta bort utpressningstrojanen från miljön (vilket hindrar [](https://support.microsoft.com/help/17128) utpressningstrojanen från att kryptera eller ta bort filer) kan du använda Filhistorik i Windows 10 och Windows 8.1 eller System Protection i Windows 7 för att försöka återställa dina lokala filer och mappar.</span><span class="sxs-lookup"><span data-stu-id="2705a-138">After you've completed the previous step to remove the ransomware payload from your environment (which will prevent the ransomware from encrypting or removing your files), you can use [File History](https://support.microsoft.com/help/17128) in Windows 10 and Windows 8.1 or System Protection in Windows 7 to attempt to recover your local files and folders.</span></span>

<span data-ttu-id="2705a-139">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="2705a-139">**Notes**:</span></span>

- <span data-ttu-id="2705a-140">En del utpressningstrojaner krypterar eller tar bort säkerhetskopiorna, så du kan inte använda Filhistorik eller Systemskydd för att återställa filer.</span><span class="sxs-lookup"><span data-stu-id="2705a-140">Some ransomware will also encrypt or delete the backup versions, so you can't use File History or System Protection to restore files.</span></span> <span data-ttu-id="2705a-141">Om det händer behöver du använda säkerhetskopior på externa enheter eller enheter som inte påverkades av utpressningstrojanen eller OneDrive enligt beskrivningen i nästa avsnitt.</span><span class="sxs-lookup"><span data-stu-id="2705a-141">If that happens, you need use backups on external drives or devices that were not affected by the ransomware or OneDrive as described in the next section.</span></span>

- <span data-ttu-id="2705a-142">Om en mapp är synkroniserad med OneDrive och du inte använder den senaste versionen av Windows kan det finnas vissa begränsningar i Filhistorik.</span><span class="sxs-lookup"><span data-stu-id="2705a-142">If a folder is synchronized to OneDrive and you aren't using the latest version of Windows, there might be some limitations using File History.</span></span>

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a><span data-ttu-id="2705a-143">Steg 5: Återställa filer i OneDrive för företag</span><span class="sxs-lookup"><span data-stu-id="2705a-143">Step 5: Recover your files in your OneDrive for Business</span></span>

<span data-ttu-id="2705a-144">Med Filåterställning i OneDrive för företag kan du återställa hela OneDrive till en föregående tidpunkt under de senaste 30 dagarna.</span><span class="sxs-lookup"><span data-stu-id="2705a-144">Files Restore in OneDrive for Business allows you to restore your entire OneDrive to a previous point in time within the last 30 days.</span></span> <span data-ttu-id="2705a-145">Mer information finns i [Återställa din OneDrive.](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)</span><span class="sxs-lookup"><span data-stu-id="2705a-145">For more information, see [Restore your OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15).</span></span>

## <a name="step-6-recover-deleted-email"></a><span data-ttu-id="2705a-146">Steg 6: Återskapa borttagna e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="2705a-146">Step 6: Recover deleted email</span></span>

<span data-ttu-id="2705a-147">I de sällsynta fall som utpressningstrojanen tog bort alla dina e-postmeddelanden kan du antagligen återställa de borttagna objekten.</span><span class="sxs-lookup"><span data-stu-id="2705a-147">In the rare case that the ransomware deleted all your email, you can probably recover the deleted items.</span></span> <span data-ttu-id="2705a-148">Mer information finns i:</span><span class="sxs-lookup"><span data-stu-id="2705a-148">For more information, see:</span></span>

- [<span data-ttu-id="2705a-149">Återställa borttagna meddelanden i en användares postlåda</span><span class="sxs-lookup"><span data-stu-id="2705a-149">Recover deleted messages in a user's mailbox</span></span>](/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [<span data-ttu-id="2705a-150">Återskapa borttagna objekt i Outlook för Windows</span><span class="sxs-lookup"><span data-stu-id="2705a-150">Recover deleted items in Outlook for Windows</span></span>](https://support.microsoft.com/office/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a><span data-ttu-id="2705a-151">Steg 7: Återaktivera Exchange ActiveSync och OneDrive-synkronisering</span><span class="sxs-lookup"><span data-stu-id="2705a-151">Step 7: Re-enable Exchange ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="2705a-152">När du har rensat dina datorer och enheter och återskapat dina data kan du återaktivera Exchange ActiveSync- och OneDrive-synkronisering som du tidigare [inaktiverade i steg 2.](#step-2-disable-exchange-activesync-and-onedrive-sync)</span><span class="sxs-lookup"><span data-stu-id="2705a-152">After you've cleaned your computers and devices and recovered your data, you can re-enable Exchange ActiveSync and OneDrive sync that you previously disabled in [Step 2](#step-2-disable-exchange-activesync-and-onedrive-sync).</span></span>

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a><span data-ttu-id="2705a-153">Steg 8 (valfritt): Blockera OneDrive-synkronisering för specifika filnamnstillägg</span><span class="sxs-lookup"><span data-stu-id="2705a-153">Step 8 (Optional): Block OneDrive sync for specific file extensions</span></span>

<span data-ttu-id="2705a-154">När du har återställt kan du förhindra att OneDrive för företag-klienter synkroniserar filtyper som påverkades av den här utpressningstrojanen.</span><span class="sxs-lookup"><span data-stu-id="2705a-154">After you've recovered, you can prevent OneDrive for Business clients from synchronizing the file types that were affected by this ransomware.</span></span> <span data-ttu-id="2705a-155">Mer information finns i [Set-SPOTenantSyncClientRestriction](/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span><span class="sxs-lookup"><span data-stu-id="2705a-155">For more information, see [Set-SPOTenantSyncClientRestriction](/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span></span>

## <a name="report-the-attack"></a><span data-ttu-id="2705a-156">Rapportera attacken</span><span class="sxs-lookup"><span data-stu-id="2705a-156">Report the attack</span></span>

### <a name="contact-law-enforcement"></a><span data-ttu-id="2705a-157">Kontaktperson vid rättsendning</span><span class="sxs-lookup"><span data-stu-id="2705a-157">Contact law enforcement</span></span>

<span data-ttu-id="2705a-158">Kontakta dina lokala eller federala rättsbyråer.</span><span class="sxs-lookup"><span data-stu-id="2705a-158">You should contact your local or federal law enforcement agencies.</span></span> <span data-ttu-id="2705a-159">Om du befinner dig i USA kan du exempelvis kontakta det lokala [fältet AVSE,](https://www.fbi.gov/contact-us/field) [IC3](http://www.ic3.gov/complaint/default.aspx) eller [Hemlig tjänst.](http://www.secretservice.gov/)</span><span class="sxs-lookup"><span data-stu-id="2705a-159">For example, if you are in the United States you can contact the [FBI local field office](https://www.fbi.gov/contact-us/field), [IC3](http://www.ic3.gov/complaint/default.aspx) or [Secret Service](http://www.secretservice.gov/).</span></span>

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a><span data-ttu-id="2705a-160">Skicka en rapport till ditt lands webbplats för bedrägerirapportering</span><span class="sxs-lookup"><span data-stu-id="2705a-160">Submit a report to your country's scam reporting website</span></span>

<span data-ttu-id="2705a-161">På webbplatserna för bedrägerirapportering finns information om hur du kan förhindra och undvika bedrägerier.</span><span class="sxs-lookup"><span data-stu-id="2705a-161">Scam reporting websites provide information about how to prevent and avoid scams.</span></span> <span data-ttu-id="2705a-162">De har även mekanismer för att rapportera om du var offer för bedrägeri.</span><span class="sxs-lookup"><span data-stu-id="2705a-162">They also provide mechanisms to report if you were victim of scam.</span></span>

- <span data-ttu-id="2705a-163">Australien: [SCAMwatch](http://www.scamwatch.gov.au/)</span><span class="sxs-lookup"><span data-stu-id="2705a-163">Australia: [SCAMwatch](http://www.scamwatch.gov.au/)</span></span>

- <span data-ttu-id="2705a-164">Kanada: [Canadian Anti-Fraud Centre](http://www.antifraudcentre-centreantifraude.ca/)</span><span class="sxs-lookup"><span data-stu-id="2705a-164">Canada: [Canadian Anti-Fraud Centre](http://www.antifraudcentre-centreantifraude.ca/)</span></span>

- <span data-ttu-id="2705a-165">Frankrike: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)</span><span class="sxs-lookup"><span data-stu-id="2705a-165">France: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)</span></span>

- <span data-ttu-id="2705a-166">Tyskland: [Det första talet i tysklandet für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span><span class="sxs-lookup"><span data-stu-id="2705a-166">Germany: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span></span>

- <span data-ttu-id="2705a-167">Irland: [An Mádo Síochána](http://www.garda.ie/)</span><span class="sxs-lookup"><span data-stu-id="2705a-167">Ireland: [An Garda Síochána](http://www.garda.ie/)</span></span>

- <span data-ttu-id="2705a-168">Nya Zeeland: [Consumer Affairs Scams](http://www.consumeraffairs.govt.nz/scams)</span><span class="sxs-lookup"><span data-stu-id="2705a-168">New Zealand: [Consumer Affairs Scams](http://www.consumeraffairs.govt.nz/scams)</span></span>

- <span data-ttu-id="2705a-169">Storbritannien: [Åtgärdsbedrägerier](http://www.actionfraud.police.uk/)</span><span class="sxs-lookup"><span data-stu-id="2705a-169">United Kingdom: [Action Fraud](http://www.actionfraud.police.uk/)</span></span>

- <span data-ttu-id="2705a-170">USA: [On Guard Online](http://www.onguardonline.gov/)</span><span class="sxs-lookup"><span data-stu-id="2705a-170">United States: [On Guard Online](http://www.onguardonline.gov/)</span></span>

<span data-ttu-id="2705a-171">Om ditt land inte finns med i listan kan du fråga ditt lokala eller federala myndigheter.</span><span class="sxs-lookup"><span data-stu-id="2705a-171">If your country isn't listed, ask your local or federal law enforcement agencies.</span></span>

### <a name="submit-email-messages-to-microsoft"></a><span data-ttu-id="2705a-172">Skicka e-postmeddelanden till Microsoft</span><span class="sxs-lookup"><span data-stu-id="2705a-172">Submit email messages to Microsoft</span></span>

<span data-ttu-id="2705a-173">Du kan rapportera nätfiskemeddelanden som innehåller utpressningstrojaner på flera olika sätt.</span><span class="sxs-lookup"><span data-stu-id="2705a-173">You can report phishing messages that contain ransomware by using one of several methods.</span></span> <span data-ttu-id="2705a-174">Mer informations finns i [Anmäla meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="2705a-174">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2705a-175">Se även</span><span class="sxs-lookup"><span data-stu-id="2705a-175">See also</span></span>

- [<span data-ttu-id="2705a-176">Utpressningstrojaner</span><span class="sxs-lookup"><span data-stu-id="2705a-176">Ransomware</span></span>](/windows/security/threat-protection/intelligence/ransomware-malware)

- [<span data-ttu-id="2705a-177">Svar på utpressningstrojaner – för att betala eller inte betala?</span><span class="sxs-lookup"><span data-stu-id="2705a-177">Ransomware response—to pay or not to pay?</span></span>](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)

- [<span data-ttu-id="2705a-178">NorskSon svarar på utpressningstrojaner med transparens</span><span class="sxs-lookup"><span data-stu-id="2705a-178">Norsk Hydro responds to ransomware attack with transparency</span></span>](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)

- [<span data-ttu-id="2705a-179">Identifiering av utpressningstrojaner och återställa filer i OneDrive</span><span class="sxs-lookup"><span data-stu-id="2705a-179">Ransomware detection and recovering your files in OneDrive</span></span>](https://support.microsoft.com/office/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)

- [<span data-ttu-id="2705a-180">Microsoft Security Intelligence-rapport</span><span class="sxs-lookup"><span data-stu-id="2705a-180">Microsoft Security Intelligence Report</span></span>](https://www.microsoft.com/securityinsights/)

- [<span data-ttu-id="2705a-181">Aktivera eller inaktivera makron i Office-filer</span><span class="sxs-lookup"><span data-stu-id="2705a-181">Enable or disable macros in Office files</span></span>](https://support.microsoft.com/office/12b036fd-d140-4e74-b45e-16fed1a7e5c6)

- [<span data-ttu-id="2705a-182">Rekommenderade inställningar för EOP och Microsoft Defender för Office 365-säkerhet</span><span class="sxs-lookup"><span data-stu-id="2705a-182">Recommended settings for EOP and Microsoft Defender for Office 365 security</span></span>](recommended-settings-for-eop-and-office365.md)

- [<span data-ttu-id="2705a-183">En värdig uppgradering: Nästa generationens säkerhet i Windows 10 bevisar sin motståndskraft mot utpressningstrojaner under 2017</span><span class="sxs-lookup"><span data-stu-id="2705a-183">A worthy upgrade: Next-gen security on Windows 10 proves resilient against ransomware outbreaks in 2017</span></span>](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

- [<span data-ttu-id="2705a-184">Inte mas, Samas: Vad finns i den här utpressningstrojanens modus operandi?</span><span class="sxs-lookup"><span data-stu-id="2705a-184">No mas, Samas: What's in this ransomware's modus operandi?</span></span>](https://www.microsoft.com/security/blog/2016/03/17/no-mas-samas-whats-in-this-ransomwares-modus-operandi/)

- [<span data-ttu-id="2705a-185">Locky-skadlig programvara, tur att undvika det</span><span class="sxs-lookup"><span data-stu-id="2705a-185">Locky malware, lucky to avoid it</span></span>](https://www.microsoft.com/security/blog/2016/02/24/locky-malware-lucky-to-avoid-it/)

- [<span data-ttu-id="2705a-186">MSRT juli 2016: Cerber-utpressningstrojan</span><span class="sxs-lookup"><span data-stu-id="2705a-186">MSRT July 2016: Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/07/12/msrt-july-2016-cerber-ransomware/)

- [<span data-ttu-id="2705a-187">De tre huvudena i Cerberus-liknande Cerber-utpressningstrojaner</span><span class="sxs-lookup"><span data-stu-id="2705a-187">The three heads of the Cerberus-like Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/03/09/the-three-heads-of-the-cerberus-like-cerber-ransomware/)

- [<span data-ttu-id="2705a-188">Troldesh-utpressningstrojanen påverkas av () Da Kod för DaKod</span><span class="sxs-lookup"><span data-stu-id="2705a-188">Troldesh ransomware influenced by (the) Da Vinci code</span></span>](https://www.microsoft.com/security/blog/2016/07/13/troldesh-ransomware-influenced-by-the-da-vinci-code/)