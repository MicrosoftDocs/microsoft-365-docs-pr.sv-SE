---
title: Återställa efter utpressningstrojanattack
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Microsoft 365-administratörer kan lära sig att återställa från en ransomware-attack.
ms.openlocfilehash: 51f5bb365fe707615444c1399479171aa72755e1
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208264"
---
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a><span data-ttu-id="ce368-103">Återhämta sig från en ransomware attack i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ce368-103">Recover from a ransomware attack in Microsoft 365</span></span>

<span data-ttu-id="ce368-104">Även om du vidtar alla försiktighetsåtgärder för att skydda din organisation, kan du fortfarande falla offer för en [ransomware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) attack.</span><span class="sxs-lookup"><span data-stu-id="ce368-104">Even if you take every precaution to protect your organization, you can still fall victim to a [ransomware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) attack.</span></span> <span data-ttu-id="ce368-105">Ransomware är big business, och attackerna är verifiera sofistikerade.</span><span class="sxs-lookup"><span data-stu-id="ce368-105">Ransomware is big business, and the attacks are verify sophisticated.</span></span>

<span data-ttu-id="ce368-106">Stegen i det här avsnittet ger dig den bästa chansen att återställa data som krypterades av ransomware, och hjälper till att stoppa spridningen av infektionen i din organisation.</span><span class="sxs-lookup"><span data-stu-id="ce368-106">The steps in this topic will give you the best chance to recover data that was encrypted by the ransomware, and will help stop the spread of the infection in your organization.</span></span> <span data-ttu-id="ce368-107">Innan du börjar bör du tänka på följande:</span><span class="sxs-lookup"><span data-stu-id="ce368-107">Before you get started, consider the following items:</span></span>

- <span data-ttu-id="ce368-108">Det finns ingen garanti för att betala lösen kommer att returnera tillgång till dina filer.</span><span class="sxs-lookup"><span data-stu-id="ce368-108">There's no guarantee that paying the ransom will return access to your files.</span></span> <span data-ttu-id="ce368-109">Faktum är att betala lösen kan göra dig till ett mål för mer ransomware.</span><span class="sxs-lookup"><span data-stu-id="ce368-109">In fact, paying the ransom can make you a target for more ransomware.</span></span> <span data-ttu-id="ce368-110">Om du redan har betalat, men du lyckades återställa dina filer utan att behöva använda angriparens lösning, bör du ringa din bank för att se om de kan blockera transaktionen.</span><span class="sxs-lookup"><span data-stu-id="ce368-110">If you've already paid, but you were able to successfully recover your files without having to use the attacker's resolution, you should call your bank to see if they can block the transaction.</span></span> <span data-ttu-id="ce368-111">Vi rekommenderar också att du rapporterar ransomware-attacken till brottsbekämpande myndigheter, webbplatser för bedrägerirapportering och Microsoft enligt beskrivningen senare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="ce368-111">We also recommend that you report the ransomware attack to law enforcement, scam reporting websites and Microsoft as described later in this topic.</span></span>

- <span data-ttu-id="ce368-112">Det är mycket viktigt att du reagerar snabbt på attacken och dess konsekvenser.</span><span class="sxs-lookup"><span data-stu-id="ce368-112">It's very important that you respond quickly to the attack and its consequences.</span></span> <span data-ttu-id="ce368-113">Ju längre du väntar, desto mindre sannolikt är det att du kan återställa de berörda data.</span><span class="sxs-lookup"><span data-stu-id="ce368-113">The longer you wait, the less likely it is that you can recover the affected data.</span></span>

## <a name="step-1-verify-your-backups"></a><span data-ttu-id="ce368-114">Steg 1: Verifiera dina säkerhetskopior</span><span class="sxs-lookup"><span data-stu-id="ce368-114">Step 1: Verify your backups</span></span>

<span data-ttu-id="ce368-115">Om du har offlinesäkerhetskopior kan du förmodligen återställa krypterade data **när** du har tagit bort nyttolasten för ransomware (malware) från din miljö.</span><span class="sxs-lookup"><span data-stu-id="ce368-115">If you have offline backups, you can probably restore the encrypted data **after** you've removed the ransomware payload (malware) from your environment.</span></span>

<span data-ttu-id="ce368-116">Om du inte har säkerhetskopior, eller om dina säkerhetskopior också påverkades av ransomware, kan du hoppa över det här steget.</span><span class="sxs-lookup"><span data-stu-id="ce368-116">If you don't have backups, or if your backups were also affected by the ransomware, you can skip this step.</span></span>

## <a name="step-2-disable-activesync-and-onedrive-sync"></a><span data-ttu-id="ce368-117">Steg 2: Inaktivera ActiveSync- och OneDrive-synkronisering</span><span class="sxs-lookup"><span data-stu-id="ce368-117">Step 2: Disable ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="ce368-118">Den viktigaste punkten här är att stoppa spridningen av datakryptering av ransomware.</span><span class="sxs-lookup"><span data-stu-id="ce368-118">The key point here is to stop the spread of data encryption by the ransomware.</span></span>

<span data-ttu-id="ce368-119">Om du misstänker att e-post är ett mål bör du tillfälligt inaktivera användaråtkomst till postlådor.</span><span class="sxs-lookup"><span data-stu-id="ce368-119">If you suspect that email is a target, you should temporarily disable user access to mailboxes.</span></span> <span data-ttu-id="ce368-120">Exchange ActiveSync används av mobila enheter för att synkronisera data mellan enheten och Exchange Online-postlådan.</span><span class="sxs-lookup"><span data-stu-id="ce368-120">Exchange ActiveSync is used by mobile devices to synchronize data between the device and the Exchange Online mailbox.</span></span>

<span data-ttu-id="ce368-121">Information om hur du inaktiverar ActiveSync för en postlåda finns i [Inaktivera Exchange ActiveSync för användare i Exchange Online](https://support.microsoft.com/help/2795303/how-to-disable-exchange-activesync-for-users-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="ce368-121">To disable ActiveSync for a mailbox, see [How to disable Exchange ActiveSync for users in Exchange Online](https://support.microsoft.com/help/2795303/how-to-disable-exchange-activesync-for-users-in-office-365).</span></span>

<span data-ttu-id="ce368-122">Om du vill inaktivera andra typer av åtkomst till en postlåda läser du:</span><span class="sxs-lookup"><span data-stu-id="ce368-122">To disable other types of access to a mailbox, see:</span></span>

- <span data-ttu-id="ce368-123">[Aktivera eller inaktivera MAPI för en postlåda](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).</span><span class="sxs-lookup"><span data-stu-id="ce368-123">[Enable or disable MAPI for a mailbox](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).</span></span>

- [<span data-ttu-id="ce368-124">Aktivera eller inaktivera POP3- eller IMAP4-åtkomst för en användare</span><span class="sxs-lookup"><span data-stu-id="ce368-124">Enable or Disable POP3 or IMAP4 access for a user</span></span>](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

<span data-ttu-id="ce368-125">Om du pausar OneDrive-synkronisering kan du skydda molndata från att uppdateras av potentiellt infekterade enheter.</span><span class="sxs-lookup"><span data-stu-id="ce368-125">Pausing OneDrive sync will help protect your cloud data from being updated by potentially infected devices.</span></span> <span data-ttu-id="ce368-126">Mer information finns [i Så här pausar och återupptar du synkroniseringen i OneDrive](https://support.office.com/article/2152bfa4-a2a5-4d3a-ace8-92912fb4421e).</span><span class="sxs-lookup"><span data-stu-id="ce368-126">For more information, see [How to Pause and Resume sync in OneDrive](https://support.office.com/article/2152bfa4-a2a5-4d3a-ace8-92912fb4421e).</span></span>

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a><span data-ttu-id="ce368-127">Steg 3: Ta bort skadlig kod från de berörda enheterna</span><span class="sxs-lookup"><span data-stu-id="ce368-127">Step 3: Remove the malware from the affected devices</span></span>

<span data-ttu-id="ce368-128">Kör en fullständig antivirussökning med de senaste uppdateringarna på alla misstänkta datorer och enheter för att identifiera och ta bort nyttolasten som är associerad med ransomware.</span><span class="sxs-lookup"><span data-stu-id="ce368-128">Run a full antivirus scan with the latest updates on all suspected computers and devices to detect and remove the payload that's associated with the ransomware.</span></span> <span data-ttu-id="ce368-129">Glöm inte enheter som synkroniserar data eller målet för mappade nätverksenheter (dessa datorer och enheter måste också skannas).</span><span class="sxs-lookup"><span data-stu-id="ce368-129">Don't forget devices that are synchronizing data, or the target of mapped network drives (those computers and devices need to be scanned, too).</span></span>

<span data-ttu-id="ce368-130">Du kan använda [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) eller (för äldre klienter) Microsoft [Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201).</span><span class="sxs-lookup"><span data-stu-id="ce368-130">You can use [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) or (for older clients) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201).</span></span>

<span data-ttu-id="ce368-131">Ett alternativ som också hjälper dig att ta bort ransomware eller skadlig kod är [Malicious Software Removal Tool (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905).</span><span class="sxs-lookup"><span data-stu-id="ce368-131">An alternative that will also help you remove ransomware or malware is the [Malicious Software Removal Tool (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905).</span></span>

<span data-ttu-id="ce368-132">Om de här alternativen inte fungerar kan du prova [Windows Defender Offline](https://support.microsoft.com/help/17466/windows-defender-offline-help-protect-my-pc) eller [felsöka problem med att identifiera och ta bort skadlig kod](https://support.microsoft.com/help/4466982/windows-10-troubleshoot-problems-with-detecting-and-removing-malware).</span><span class="sxs-lookup"><span data-stu-id="ce368-132">If these options don't work, you can try [Windows Defender Offline](https://support.microsoft.com/help/17466/windows-defender-offline-help-protect-my-pc) or [Troubleshoot problems with detecting and removing malware](https://support.microsoft.com/help/4466982/windows-10-troubleshoot-problems-with-detecting-and-removing-malware).</span></span>

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a><span data-ttu-id="ce368-133">Steg 4: Återställa filer på en rengjord dator eller enhet</span><span class="sxs-lookup"><span data-stu-id="ce368-133">Step 4: Recover files on a cleaned computer or device</span></span>

<span data-ttu-id="ce368-134">När du har slutfört föregående steg för att ta bort ransomware nyttolasten från din miljö (vilket kommer att hindra ransomware från att kryptera eller ta bort dina filer), kan du använda [Filhistorik](https://support.microsoft.com/help/17128/windows-8-file-history) i Windows 10 och Windows 8.1 eller Systemskydd i Windows 7 för att försöka återställa dina lokala filer och mappar.</span><span class="sxs-lookup"><span data-stu-id="ce368-134">After you've completed the previous step to remove the ransomware payload from your environment (which will prevent the ransomware from encrypting or removing your files), you can use [File History](https://support.microsoft.com/help/17128/windows-8-file-history) in Windows 10 and Windows 8.1 or System Protection in Windows 7 to attempt to recover your local files and folders.</span></span>

<span data-ttu-id="ce368-135">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="ce368-135">**Notes**:</span></span>

- <span data-ttu-id="ce368-136">Vissa ransomware krypterar eller tar bort de säkerhetskopierade versionerna, så du kan inte använda Filhistorik eller Systemskydd för att återställa filer.</span><span class="sxs-lookup"><span data-stu-id="ce368-136">Some ransomware will also encrypt or delete the backup versions, so you can't use File History or System Protection to restore files.</span></span> <span data-ttu-id="ce368-137">Om det händer måste du använda säkerhetskopior på externa enheter eller enheter som inte påverkades av ransomware eller OneDrive enligt beskrivningen i nästa avsnitt.</span><span class="sxs-lookup"><span data-stu-id="ce368-137">If that happens, you need use backups on external drives or devices that were not affected by the ransomware or OneDrive as described in the next section.</span></span>

- <span data-ttu-id="ce368-138">Om en mapp synkroniseras med OneDrive och du inte använder den senaste versionen av Windows kan det finnas vissa begränsningar med filhistorik.</span><span class="sxs-lookup"><span data-stu-id="ce368-138">If a folder is synchronized to OneDrive and you aren't using the latest version of Windows, there might be some limitations using File History.</span></span>

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a><span data-ttu-id="ce368-139">Steg 5: Återställa dina filer i Din OneDrive för företag</span><span class="sxs-lookup"><span data-stu-id="ce368-139">Step 5: Recover your files in your OneDrive for Business</span></span>

<span data-ttu-id="ce368-140">Med Filåterställning i OneDrive för företag kan du återställa hela OneDrive till en tidigare tidpunkt inom de senaste 30 dagarna.</span><span class="sxs-lookup"><span data-stu-id="ce368-140">Files Restore in OneDrive for Business allows you to restore your entire OneDrive to a previous point in time within the last 30 days.</span></span> <span data-ttu-id="ce368-141">Mer information finns i [Återställa OneDrive](https://support.office.com/article/fa231298-759d-41cf-bcd0-25ac53eb8a15).</span><span class="sxs-lookup"><span data-stu-id="ce368-141">For more information, see [Restore your OneDrive](https://support.office.com/article/fa231298-759d-41cf-bcd0-25ac53eb8a15).</span></span>

## <a name="step-6-recover-deleted-email"></a><span data-ttu-id="ce368-142">Steg 6: Återställa borttaget e-postmeddelande</span><span class="sxs-lookup"><span data-stu-id="ce368-142">Step 6: Recover deleted email</span></span>

<span data-ttu-id="ce368-143">I det sällsynta fallet att ransomware bort alla dina e-postmeddelanden, kan du förmodligen återställa de borttagna objekten.</span><span class="sxs-lookup"><span data-stu-id="ce368-143">In the rare case that the ransomware deleted all your email, you can probably recover the deleted items.</span></span> <span data-ttu-id="ce368-144">Mer information finns i:</span><span class="sxs-lookup"><span data-stu-id="ce368-144">For more information, see:</span></span>

- [<span data-ttu-id="ce368-145">Återställa borttagna meddelanden i en användares postlåda</span><span class="sxs-lookup"><span data-stu-id="ce368-145">Recover deleted messages in a user's mailbox</span></span>](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [<span data-ttu-id="ce368-146">Återställa borttagna objekt i Outlook för Windows</span><span class="sxs-lookup"><span data-stu-id="ce368-146">Recover deleted items in Outlook for Windows</span></span>](https://support.office.com/article/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a><span data-ttu-id="ce368-147">Steg 7: Återaktivera Synkronisering av Exchange ActiveSync och OneDrive</span><span class="sxs-lookup"><span data-stu-id="ce368-147">Step 7: Re-enable Exchange ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="ce368-148">När du har rensat datorer och enheter och återställt dina data kan du återaktivera ActiveSync- och OneDrive-synkronisering som du tidigare inaktiverat i [steg 2](#step-2-disable-activesync-and-onedrive-sync).</span><span class="sxs-lookup"><span data-stu-id="ce368-148">After you've cleaned your computers and devices and recovered your data, you can re-enable ActiveSync and OneDrive sync that you previously disabled in [Step 2](#step-2-disable-activesync-and-onedrive-sync).</span></span>

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a><span data-ttu-id="ce368-149">Steg 8 (valfritt): Blockera OneDrive-synkronisering för specifika filtillägg</span><span class="sxs-lookup"><span data-stu-id="ce368-149">Step 8 (Optional): Block OneDrive sync for specific file extensions</span></span>

<span data-ttu-id="ce368-150">När du har återställt kan du förhindra att OneDrive för företag-klienter synkroniserar de filtyper som påverkades av det här ransomware.After you've recovered, you can prevent OneDrive for Business clients from synchronizing the file types that were affected by this ransomware.</span><span class="sxs-lookup"><span data-stu-id="ce368-150">After you've recovered, you can prevent OneDrive for Business clients from synchronizing the file types that were affected by this ransomware.</span></span> <span data-ttu-id="ce368-151">Mer information finns i [Set-SPOTenantSyncClientRestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span><span class="sxs-lookup"><span data-stu-id="ce368-151">For more information, see [Set-SPOTenantSyncClientRestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span></span>

## <a name="report-the-attack"></a><span data-ttu-id="ce368-152">Rapportera attacken</span><span class="sxs-lookup"><span data-stu-id="ce368-152">Report the attack</span></span>

### <a name="contact-law-enforcement"></a><span data-ttu-id="ce368-153">Kontakta polisen</span><span class="sxs-lookup"><span data-stu-id="ce368-153">Contact law enforcement</span></span>

<span data-ttu-id="ce368-154">Du bör kontakta din lokala eller federala brottsbekämpande organ.</span><span class="sxs-lookup"><span data-stu-id="ce368-154">You should contact your local or federal law enforcement agencies.</span></span> <span data-ttu-id="ce368-155">Om du till exempel befinner dig i USA kan du kontakta [FBI:s lokala fältkontor,](https://www.fbi.gov/contact-us/field) [IC3](http://www.ic3.gov/complaint/default.aspx) eller [Secret Service](http://www.secretservice.gov/).</span><span class="sxs-lookup"><span data-stu-id="ce368-155">For example, if you are in the United States you can contact the [FBI local field office](https://www.fbi.gov/contact-us/field), [IC3](http://www.ic3.gov/complaint/default.aspx) or [Secret Service](http://www.secretservice.gov/).</span></span>

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a><span data-ttu-id="ce368-156">Skicka en rapport till ditt lands webbplats för bluffrapportering</span><span class="sxs-lookup"><span data-stu-id="ce368-156">Submit a report to your country's scam reporting website</span></span>

<span data-ttu-id="ce368-157">Bluff rapportering webbplatser ger information om hur man kan förebygga och undvika bedrägerier.</span><span class="sxs-lookup"><span data-stu-id="ce368-157">Scam reporting websites provide information about how to prevent and avoid scams.</span></span> <span data-ttu-id="ce368-158">De ger också mekanismer för att rapportera om du var offer för bluff.</span><span class="sxs-lookup"><span data-stu-id="ce368-158">They also provide mechanisms to report if you were victim of scam.</span></span>

- <span data-ttu-id="ce368-159">Australien: [SCAMwatch](http://www.scamwatch.gov.au/)</span><span class="sxs-lookup"><span data-stu-id="ce368-159">Australia: [SCAMwatch](http://www.scamwatch.gov.au/)</span></span>

- <span data-ttu-id="ce368-160">Kanada: [Kanadensiska bedrägeribekämpning Centre](http://www.antifraudcentre-centreantifraude.ca/)</span><span class="sxs-lookup"><span data-stu-id="ce368-160">Canada: [Canadian Anti-Fraud Centre](http://www.antifraudcentre-centreantifraude.ca/)</span></span>

- <span data-ttu-id="ce368-161">Frankrike: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)</span><span class="sxs-lookup"><span data-stu-id="ce368-161">France: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)</span></span>

- <span data-ttu-id="ce368-162">Tyskland: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span><span class="sxs-lookup"><span data-stu-id="ce368-162">Germany: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span></span>

- <span data-ttu-id="ce368-163">Irland: [En Garda Síochána](http://www.garda.ie/)</span><span class="sxs-lookup"><span data-stu-id="ce368-163">Ireland: [An Garda Síochána](http://www.garda.ie/)</span></span>

- <span data-ttu-id="ce368-164">Nya Zeeland: [Konsumentfrågor Scams](http://www.consumeraffairs.govt.nz/scams)</span><span class="sxs-lookup"><span data-stu-id="ce368-164">New Zealand: [Consumer Affairs Scams](http://www.consumeraffairs.govt.nz/scams)</span></span>

- <span data-ttu-id="ce368-165">Storbritannien: [Action Fraud](http://www.actionfraud.police.uk/)</span><span class="sxs-lookup"><span data-stu-id="ce368-165">United Kingdom: [Action Fraud](http://www.actionfraud.police.uk/)</span></span>

- <span data-ttu-id="ce368-166">USA: [På guard online](http://www.onguardonline.gov/)</span><span class="sxs-lookup"><span data-stu-id="ce368-166">United States: [On Guard Online](http://www.onguardonline.gov/)</span></span>

<span data-ttu-id="ce368-167">Om ditt land inte finns med i listan frågar du dina lokala eller federala brottsbekämpande organ.</span><span class="sxs-lookup"><span data-stu-id="ce368-167">If your country isn't listed, ask your local or federal law enforcement agencies.</span></span>

### <a name="submit-email-messages-to-microsoft"></a><span data-ttu-id="ce368-168">Skicka e-postmeddelanden till Microsoft</span><span class="sxs-lookup"><span data-stu-id="ce368-168">Submit email messages to Microsoft</span></span>

<span data-ttu-id="ce368-169">Du kan rapportera nätfiskemeddelanden som innehåller utpressningsartiklar med hjälp av någon av flera metoder.</span><span class="sxs-lookup"><span data-stu-id="ce368-169">You can report phishing message that contain ransomware by using one of several methods.</span></span> <span data-ttu-id="ce368-170">Mer informations finns i [Anmäla meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="ce368-170">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ce368-171">Se även</span><span class="sxs-lookup"><span data-stu-id="ce368-171">See also</span></span>

- [<span data-ttu-id="ce368-172">Ransomware (lösenköp)</span><span class="sxs-lookup"><span data-stu-id="ce368-172">Ransomware</span></span>](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware)

- [<span data-ttu-id="ce368-173">Ransomware svar-att betala eller inte betala?</span><span class="sxs-lookup"><span data-stu-id="ce368-173">Ransomware response—to pay or not to pay?</span></span>](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)

- [<span data-ttu-id="ce368-174">Norsk Hydro svarar på ransomware attack med öppenhet</span><span class="sxs-lookup"><span data-stu-id="ce368-174">Norsk Hydro responds to ransomware attack with transparency</span></span>](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)

- [<span data-ttu-id="ce368-175">Ransomware identifiering och återställa dina filer i OneDrive</span><span class="sxs-lookup"><span data-stu-id="ce368-175">Ransomware detection and recovering your files in OneDrive</span></span>](https://support.office.com/article/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)

- [<span data-ttu-id="ce368-176">Microsofts säkerhetsinformationsrapport</span><span class="sxs-lookup"><span data-stu-id="ce368-176">Microsoft Security Intelligence Report</span></span>](https://www.microsoft.com/securityinsights/)

- [<span data-ttu-id="ce368-177">Aktivera eller inaktivera makron i Office-filer</span><span class="sxs-lookup"><span data-stu-id="ce368-177">Enable or disable macros in Office files</span></span>](https://support.office.com/article/12b036fd-d140-4e74-b45e-16fed1a7e5c6)

- [<span data-ttu-id="ce368-178">Rekommenderade inställningar för EOP- och Office 365 ATP-säkerhet</span><span class="sxs-lookup"><span data-stu-id="ce368-178">Recommended settings for EOP and Office 365 ATP security</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp)

- [<span data-ttu-id="ce368-179">En värdig uppgradering: Nästa generations säkerhet på Windows 10 visar sig vara motståndskraftig mot ransomware utbrott i 2017</span><span class="sxs-lookup"><span data-stu-id="ce368-179">A worthy upgrade: Next-gen security on Windows 10 proves resilient against ransomware outbreaks in 2017</span></span>](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

- [<span data-ttu-id="ce368-180">Ingen mas, Samas: Vad finns i denna ransomware modus operandi?</span><span class="sxs-lookup"><span data-stu-id="ce368-180">No mas, Samas: What's in this ransomware's modus operandi?</span></span>](https://www.microsoft.com/security/blog/2016/03/17/no-mas-samas-whats-in-this-ransomwares-modus-operandi/)

- [<span data-ttu-id="ce368-181">Locky malware, tur att undvika det</span><span class="sxs-lookup"><span data-stu-id="ce368-181">Locky malware, lucky to avoid it</span></span>](https://www.microsoft.com/security/blog/2016/02/24/locky-malware-lucky-to-avoid-it/)

- [<span data-ttu-id="ce368-182">MSRT juli 2016: Cerber ransomware</span><span class="sxs-lookup"><span data-stu-id="ce368-182">MSRT July 2016: Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/07/12/msrt-july-2016-cerber-ransomware/)

- [<span data-ttu-id="ce368-183">De tre cheferna för Cerberus-liknande Cerber ransomware</span><span class="sxs-lookup"><span data-stu-id="ce368-183">The three heads of the Cerberus-like Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/03/09/the-three-heads-of-the-cerberus-like-cerber-ransomware/)

- [<span data-ttu-id="ce368-184">Troldesh ransomware påverkas av (den) Da Vinci-koden</span><span class="sxs-lookup"><span data-stu-id="ce368-184">Troldesh ransomware influenced by (the) Da Vinci code</span></span>](https://www.microsoft.com/security/blog/2016/07/13/troldesh-ransomware-influenced-by-the-da-vinci-code/)
