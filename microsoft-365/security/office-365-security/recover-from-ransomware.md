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
description: Microsoft 365 administratörer kan ta reda på hur de kan återställa efter utpressningstrojaner.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6c3664cb2a60a7173e345de4abaddefefea6e2b1
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/09/2021
ms.locfileid: "53341442"
---
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a><span data-ttu-id="0e145-103">Återställ från en utpressningstrojanattack i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0e145-103">Recover from a ransomware attack in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="0e145-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="0e145-104">**Applies to**</span></span>
- [<span data-ttu-id="0e145-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="0e145-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="0e145-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="0e145-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="0e145-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0e145-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="0e145-108">Även om du vidtar alla försiktighetsåtgärd för att skydda organisationen kan du fortfarande falla offer för en [utpressningstrojanattack.](/windows/security/threat-protection/intelligence/ransomware-malware)</span><span class="sxs-lookup"><span data-stu-id="0e145-108">Even if you take every precaution to protect your organization, you can still fall victim to a [ransomware](/windows/security/threat-protection/intelligence/ransomware-malware) attack.</span></span> <span data-ttu-id="0e145-109">Utpressningstrojaner är en stor verksamhet och attackerna är mycket avancerade.</span><span class="sxs-lookup"><span data-stu-id="0e145-109">Ransomware is big business, and the attacks are very sophisticated.</span></span>

<span data-ttu-id="0e145-110">Med stegen i den här artikeln får du bäst chans att återställa data och stoppa den interna spridningen av smitta.</span><span class="sxs-lookup"><span data-stu-id="0e145-110">The steps in this article will give you the best chance to recover data and stop the internal spread of infection.</span></span> <span data-ttu-id="0e145-111">Innan du börjar bör du tänka på följande:</span><span class="sxs-lookup"><span data-stu-id="0e145-111">Before you get started, consider the following items:</span></span>

- <span data-ttu-id="0e145-112">Det finns ingen garanti för att betalning av utpressningstrojanen returnerar åtkomsten till dina filer.</span><span class="sxs-lookup"><span data-stu-id="0e145-112">There's no guarantee that paying the ransom will return access to your files.</span></span> <span data-ttu-id="0e145-113">Att betala utpressningstrojanen kan faktiskt göra dig till ett mål för mer utpressningstrojaner.</span><span class="sxs-lookup"><span data-stu-id="0e145-113">In fact, paying the ransom can make you a target for more ransomware.</span></span>

  <span data-ttu-id="0e145-114">Om du redan har betalat men du har återskapat utan att använda attackerarens lösning kontaktar du din bank för att se om de kan blockera transaktionen.</span><span class="sxs-lookup"><span data-stu-id="0e145-114">If you already paid, but you recovered without using the attacker's solution, contact your bank to see if they can block the transaction.</span></span>

  <span data-ttu-id="0e145-115">Vi rekommenderar även att du rapporterar utpressningstrojanattacken till olika webbplatser för utpressningstrojaner, bedrägerirapportering och Microsoft enligt beskrivningen senare i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="0e145-115">We also recommend that you report the ransomware attack to law enforcement, scam reporting websites, and Microsoft as described later in this article.</span></span>

- <span data-ttu-id="0e145-116">Det är viktigt att du svarar snabbt på attacken och dess konsekvenser.</span><span class="sxs-lookup"><span data-stu-id="0e145-116">It's important for you respond quickly to the attack and its consequences.</span></span> <span data-ttu-id="0e145-117">Ju längre du väntar, desto mindre troligt är det att du kan återskapa berörda data.</span><span class="sxs-lookup"><span data-stu-id="0e145-117">The longer you wait, the less likely it is that you can recover the affected data.</span></span>

## <a name="step-1-verify-your-backups"></a><span data-ttu-id="0e145-118">Steg 1: Kontrollera dina säkerhetskopior</span><span class="sxs-lookup"><span data-stu-id="0e145-118">Step 1: Verify your backups</span></span>

<span data-ttu-id="0e145-119">Om du har säkerhetskopieringar offline kan du antagligen återställa krypterade **data** efter att du har tagit bort nyttolasten för utpressningstrojan (skadlig kod) från din miljö.</span><span class="sxs-lookup"><span data-stu-id="0e145-119">If you have offline backups, you can probably restore the encrypted data **after** you've removed the ransomware payload (malware) from your environment.</span></span>

<span data-ttu-id="0e145-120">Om du inte har några säkerhetskopior, eller om dina säkerhetskopior också påverkades av utpressningstrojanen, kan du hoppa över det här steget.</span><span class="sxs-lookup"><span data-stu-id="0e145-120">If you don't have backups, or if your backups were also affected by the ransomware, you can skip this step.</span></span>

## <a name="step-2-disable-exchange-activesync-and-onedrive-sync"></a><span data-ttu-id="0e145-121">Steg 2: Inaktivera Exchange ActiveSync och OneDrive-synkronisering</span><span class="sxs-lookup"><span data-stu-id="0e145-121">Step 2: Disable Exchange ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="0e145-122">Det viktiga här är att stoppa uppslaget av datakryptering genom utpressningstrojanen.</span><span class="sxs-lookup"><span data-stu-id="0e145-122">The key point here is to stop the spread of data encryption by the ransomware.</span></span>

<span data-ttu-id="0e145-123">Om du misstänker att e-postmeddelanden är målet för utpressningstrojankryptering inaktiverar du tillfälligt användarnas åtkomst till postlådor.</span><span class="sxs-lookup"><span data-stu-id="0e145-123">If you suspect email as a target of the ransomware encryption, temporarily disable user access to mailboxes.</span></span> <span data-ttu-id="0e145-124">Exchange ActiveSync synkroniserar data mellan enheter och Exchange Online postlådor.</span><span class="sxs-lookup"><span data-stu-id="0e145-124">Exchange ActiveSync synchronizes data between devices and Exchange Online mailboxes.</span></span>

<span data-ttu-id="0e145-125">Information om hur Exchange ActiveSync en postlåda finns i [Inaktivera Exchange ActiveSync för användare i Exchange Online](https://support.microsoft.com/help/2795303).</span><span class="sxs-lookup"><span data-stu-id="0e145-125">To disable Exchange ActiveSync for a mailbox, see [How to disable Exchange ActiveSync for users in Exchange Online](https://support.microsoft.com/help/2795303).</span></span>

<span data-ttu-id="0e145-126">Information om hur du inaktiverar andra typer av åtkomst till en postlåda finns i:</span><span class="sxs-lookup"><span data-stu-id="0e145-126">To disable other types of access to a mailbox, see:</span></span>

- <span data-ttu-id="0e145-127">[Aktivera eller inaktivera MAPI för en postlåda.](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi)</span><span class="sxs-lookup"><span data-stu-id="0e145-127">[Enable or disable MAPI for a mailbox](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).</span></span>

- [<span data-ttu-id="0e145-128">Aktivera eller inaktivera åtkomst via POP3 eller IMAP4 för en användare</span><span class="sxs-lookup"><span data-stu-id="0e145-128">Enable or Disable POP3 or IMAP4 access for a user</span></span>](/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

<span data-ttu-id="0e145-129">Om du pausar OneDrive-synkronisering enheter skyddas dina molndata från att uppdateras av potentiellt smittade enheter.</span><span class="sxs-lookup"><span data-stu-id="0e145-129">Pausing OneDrive sync will help protect your cloud data from being updated by potentially infected devices.</span></span> <span data-ttu-id="0e145-130">Mer information finns i [Pausa och återuppta synkronisering i OneDrive](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e).</span><span class="sxs-lookup"><span data-stu-id="0e145-130">For more information, see [How to Pause and Resume sync in OneDrive](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e).</span></span>

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a><span data-ttu-id="0e145-131">Steg 3: Ta bort den skadlig programvara från de berörda enheterna</span><span class="sxs-lookup"><span data-stu-id="0e145-131">Step 3: Remove the malware from the affected devices</span></span>

<span data-ttu-id="0e145-132">Kör en fullständig, aktuell antivirussökning på alla misstänkta datorer och enheter för att identifiera och ta bort den nyttolast som är kopplad till utpressningstrojanen.</span><span class="sxs-lookup"><span data-stu-id="0e145-132">Run a full, current antivirus scan on all suspected computers and devices to detect and remove the payload that's associated with the ransomware.</span></span>

<span data-ttu-id="0e145-133">Glöm inte att skanna enheter som synkroniserar data eller mål för mappade nätverksenheter.</span><span class="sxs-lookup"><span data-stu-id="0e145-133">Don't forget to scan devices that are synchronizing data, or the targets of mapped network drives.</span></span>

<span data-ttu-id="0e145-134">Du kan använda [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) eller (för äldre klienter) [Microsoft Security Essentials.](https://www.microsoft.com/download/details.aspx?id=5201)</span><span class="sxs-lookup"><span data-stu-id="0e145-134">You can use [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) or (for older clients) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201).</span></span>

<span data-ttu-id="0e145-135">Ett alternativ som också hjälper dig att ta bort utpressningstrojaner eller skadlig programvara är verktyget För borttagning av skadlig programvara [(MSRT).](https://www.microsoft.com/download/details.aspx?id=9905)</span><span class="sxs-lookup"><span data-stu-id="0e145-135">An alternative that will also help you remove ransomware or malware is the [Malicious Software Removal Tool (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905).</span></span>

<span data-ttu-id="0e145-136">Om de här alternativen inte fungerar kan du prova att Windows Defender Offline eller [Felsöka](https://support.microsoft.com/help/17466) problem med att identifiera [och ta bort skadlig programvara.](https://support.microsoft.com/help/4466982)</span><span class="sxs-lookup"><span data-stu-id="0e145-136">If these options don't work, you can try [Windows Defender Offline](https://support.microsoft.com/help/17466) or [Troubleshoot problems with detecting and removing malware](https://support.microsoft.com/help/4466982).</span></span>

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a><span data-ttu-id="0e145-137">Steg 4: Återställa filer på en rensad dator eller enhet</span><span class="sxs-lookup"><span data-stu-id="0e145-137">Step 4: Recover files on a cleaned computer or device</span></span>

<span data-ttu-id="0e145-138">När du har slutfört det föregående steget för att ta bort utpressningstrojanen från miljön (vilket förhindrar [](https://support.microsoft.com/help/17128) utpressningstrojaner från att kryptera eller ta bort filer) kan du använda Filhistorik i Windows 10 och Windows 8.1 eller System Protection i Windows 7 för att försöka återställa dina lokala filer och mappar.</span><span class="sxs-lookup"><span data-stu-id="0e145-138">After you've completed the previous step to remove the ransomware payload from your environment (which will prevent the ransomware from encrypting or removing your files), you can use [File History](https://support.microsoft.com/help/17128) in Windows 10 and Windows 8.1 or System Protection in Windows 7 to attempt to recover your local files and folders.</span></span>

<span data-ttu-id="0e145-139">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="0e145-139">**Notes**:</span></span>

- <span data-ttu-id="0e145-140">En del utpressningstrojaner krypterar eller tar bort säkerhetskopiorna, så du kan inte använda Filhistorik eller Systemskydd för att återställa filer.</span><span class="sxs-lookup"><span data-stu-id="0e145-140">Some ransomware will also encrypt or delete the backup versions, so you can't use File History or System Protection to restore files.</span></span> <span data-ttu-id="0e145-141">Om det händer behöver du använda säkerhetskopior på externa enheter eller enheter som inte påverkades av utpressningstrojanen eller OneDrive enligt beskrivningen i nästa avsnitt.</span><span class="sxs-lookup"><span data-stu-id="0e145-141">If that happens, you need use backups on external drives or devices that were not affected by the ransomware or OneDrive as described in the next section.</span></span>

- <span data-ttu-id="0e145-142">Om en mapp är synkroniserad OneDrive mapp och du inte använder den senaste versionen av Windows kan det finnas vissa begränsningar i Filhistorik.</span><span class="sxs-lookup"><span data-stu-id="0e145-142">If a folder is synchronized to OneDrive and you aren't using the latest version of Windows, there might be some limitations using File History.</span></span>

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a><span data-ttu-id="0e145-143">Steg 5: Återskapa filerna i OneDrive för företag</span><span class="sxs-lookup"><span data-stu-id="0e145-143">Step 5: Recover your files in your OneDrive for Business</span></span>

<span data-ttu-id="0e145-144">Med Filåterställning OneDrive för företag du återställa hela OneDrive till en föregående tidpunkt inom de senaste 30 dagarna.</span><span class="sxs-lookup"><span data-stu-id="0e145-144">Files Restore in OneDrive for Business allows you to restore your entire OneDrive to a previous point in time within the last 30 days.</span></span> <span data-ttu-id="0e145-145">Mer information finns i [Återställ din OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15).</span><span class="sxs-lookup"><span data-stu-id="0e145-145">For more information, see [Restore your OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15).</span></span>

## <a name="step-6-recover-deleted-email"></a><span data-ttu-id="0e145-146">Steg 6: Återskapa borttagna e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="0e145-146">Step 6: Recover deleted email</span></span>

<span data-ttu-id="0e145-147">I de sällsynta fall som utpressningstrojanen tog bort alla dina e-postmeddelanden kan du antagligen återställa de borttagna objekten.</span><span class="sxs-lookup"><span data-stu-id="0e145-147">In the rare case that the ransomware deleted all your email, you can probably recover the deleted items.</span></span> <span data-ttu-id="0e145-148">Mer information finns i:</span><span class="sxs-lookup"><span data-stu-id="0e145-148">For more information, see:</span></span>

- [<span data-ttu-id="0e145-149">Återställa borttagna meddelanden i en användares postlåda</span><span class="sxs-lookup"><span data-stu-id="0e145-149">Recover deleted messages in a user's mailbox</span></span>](/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [<span data-ttu-id="0e145-150">Återskapa borttagna objekt i Outlook för Windows</span><span class="sxs-lookup"><span data-stu-id="0e145-150">Recover deleted items in Outlook for Windows</span></span>](https://support.microsoft.com/office/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a><span data-ttu-id="0e145-151">Steg 7: Återaktivera Exchange ActiveSync och OneDrive-synkronisering</span><span class="sxs-lookup"><span data-stu-id="0e145-151">Step 7: Re-enable Exchange ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="0e145-152">När du har rensat dina datorer och enheter och återskapat dina data kan du återaktivera Exchange ActiveSync och OneDrive-synkronisering som du tidigare inaktiverade [i steg 2.](#step-2-disable-exchange-activesync-and-onedrive-sync)</span><span class="sxs-lookup"><span data-stu-id="0e145-152">After you've cleaned your computers and devices and recovered your data, you can re-enable Exchange ActiveSync and OneDrive sync that you previously disabled in [Step 2](#step-2-disable-exchange-activesync-and-onedrive-sync).</span></span>

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a><span data-ttu-id="0e145-153">Steg 8 (valfritt): Blockera OneDrive-synkronisering för specifika filnamnstillägg</span><span class="sxs-lookup"><span data-stu-id="0e145-153">Step 8 (Optional): Block OneDrive sync for specific file extensions</span></span>

<span data-ttu-id="0e145-154">När du har återställt kan du förhindra OneDrive för företag-klienter från att synkronisera de filtyper som påverkades av den här utpressningstrojanen.</span><span class="sxs-lookup"><span data-stu-id="0e145-154">After you've recovered, you can prevent OneDrive for Business clients from synchronizing the file types that were affected by this ransomware.</span></span> <span data-ttu-id="0e145-155">Mer information finns i [Set-SPOTenantSyncClientRestriction](/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span><span class="sxs-lookup"><span data-stu-id="0e145-155">For more information, see [Set-SPOTenantSyncClientRestriction](/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span></span>

## <a name="report-the-attack"></a><span data-ttu-id="0e145-156">Rapportera attacken</span><span class="sxs-lookup"><span data-stu-id="0e145-156">Report the attack</span></span>

### <a name="contact-law-enforcement"></a><span data-ttu-id="0e145-157">Kontaktperson vid rättsendning</span><span class="sxs-lookup"><span data-stu-id="0e145-157">Contact law enforcement</span></span>

<span data-ttu-id="0e145-158">Kontakta dina lokala eller federala rättsbyråer.</span><span class="sxs-lookup"><span data-stu-id="0e145-158">You should contact your local or federal law enforcement agencies.</span></span> <span data-ttu-id="0e145-159">Om du befinner dig i USA kan du exempelvis kontakta det lokala [fältet AVSE,](https://www.fbi.gov/contact-us/field) [IC3](http://www.ic3.gov/complaint/default.aspx) eller [Hemlig tjänst.](http://www.secretservice.gov/)</span><span class="sxs-lookup"><span data-stu-id="0e145-159">For example, if you are in the United States you can contact the [FBI local field office](https://www.fbi.gov/contact-us/field), [IC3](http://www.ic3.gov/complaint/default.aspx) or [Secret Service](http://www.secretservice.gov/).</span></span>

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a><span data-ttu-id="0e145-160">Skicka en rapport till ditt lands webbplats för bedrägerirapportering</span><span class="sxs-lookup"><span data-stu-id="0e145-160">Submit a report to your country's scam reporting website</span></span>

<span data-ttu-id="0e145-161">På webbplatserna för bedrägerirapportering finns information om hur du kan förhindra och undvika bedrägerier.</span><span class="sxs-lookup"><span data-stu-id="0e145-161">Scam reporting websites provide information about how to prevent and avoid scams.</span></span> <span data-ttu-id="0e145-162">De har även mekanismer för att rapportera om du var offer för bedrägeri.</span><span class="sxs-lookup"><span data-stu-id="0e145-162">They also provide mechanisms to report if you were victim of scam.</span></span>

- <span data-ttu-id="0e145-163">Australien: [SCAMwatch](http://www.scamwatch.gov.au/)</span><span class="sxs-lookup"><span data-stu-id="0e145-163">Australia: [SCAMwatch](http://www.scamwatch.gov.au/)</span></span>

- <span data-ttu-id="0e145-164">Kanada: [Canadian Anti-Fraud Centre](http://www.antifraudcentre-centreantifraude.ca/)</span><span class="sxs-lookup"><span data-stu-id="0e145-164">Canada: [Canadian Anti-Fraud Centre](http://www.antifraudcentre-centreantifraude.ca/)</span></span>

- <span data-ttu-id="0e145-165">Frankrike: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)</span><span class="sxs-lookup"><span data-stu-id="0e145-165">France: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)</span></span>

- <span data-ttu-id="0e145-166">Tyskland: [Det första talet i tysklandet für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span><span class="sxs-lookup"><span data-stu-id="0e145-166">Germany: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span></span>

- <span data-ttu-id="0e145-167">Irland: [An Mádo Síochána](http://www.garda.ie/)</span><span class="sxs-lookup"><span data-stu-id="0e145-167">Ireland: [An Garda Síochána](http://www.garda.ie/)</span></span>

- <span data-ttu-id="0e145-168">Nya Zeeland: [Consumer Affairs Scams](http://www.consumeraffairs.govt.nz/scams)</span><span class="sxs-lookup"><span data-stu-id="0e145-168">New Zealand: [Consumer Affairs Scams](http://www.consumeraffairs.govt.nz/scams)</span></span>

- <span data-ttu-id="0e145-169">Switzerland [Nationales Zentrum für Cybersicherheit NCSC](https://www.ncsc.admin.ch/ncsc/de/home.html)</span><span class="sxs-lookup"><span data-stu-id="0e145-169">Switzerland [Nationales Zentrum für Cybersicherheit NCSC](https://www.ncsc.admin.ch/ncsc/de/home.html)</span></span>

- <span data-ttu-id="0e145-170">Storbritannien: [Åtgärdsbedrägerier](http://www.actionfraud.police.uk/)</span><span class="sxs-lookup"><span data-stu-id="0e145-170">United Kingdom: [Action Fraud](http://www.actionfraud.police.uk/)</span></span>

- <span data-ttu-id="0e145-171">USA: [On Guard Online](http://www.onguardonline.gov/)</span><span class="sxs-lookup"><span data-stu-id="0e145-171">United States: [On Guard Online](http://www.onguardonline.gov/)</span></span>

<span data-ttu-id="0e145-172">Om ditt land inte finns med i listan kan du fråga ditt lokala eller federala myndigheter.</span><span class="sxs-lookup"><span data-stu-id="0e145-172">If your country isn't listed, ask your local or federal law enforcement agencies.</span></span>

### <a name="submit-email-messages-to-microsoft"></a><span data-ttu-id="0e145-173">Skicka e-postmeddelanden till Microsoft</span><span class="sxs-lookup"><span data-stu-id="0e145-173">Submit email messages to Microsoft</span></span>

<span data-ttu-id="0e145-174">Du kan rapportera nätfiskemeddelanden som innehåller utpressningstrojaner på flera olika sätt.</span><span class="sxs-lookup"><span data-stu-id="0e145-174">You can report phishing messages that contain ransomware by using one of several methods.</span></span> <span data-ttu-id="0e145-175">Mer informations finns i [Anmäla meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="0e145-175">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="additional-ransomware-resources"></a><span data-ttu-id="0e145-176">Ytterligare resurser för utpressningstrojaner</span><span class="sxs-lookup"><span data-stu-id="0e145-176">Additional ransomware resources</span></span>

[<span data-ttu-id="0e145-177">Översikt över utpressningstrojaner som drivs av människor</span><span class="sxs-lookup"><span data-stu-id="0e145-177">Human-operated ransomware overview</span></span>](/security/compass/human-operated-ransomware)

[<span data-ttu-id="0e145-178">Skydda snabbt mot utpressningstrojaner och utpressning</span><span class="sxs-lookup"><span data-stu-id="0e145-178">Rapidly protect against ransomware and extortion</span></span>](/security/compass/protect-against-ransomware)

<span data-ttu-id="0e145-179">[Den senaste Microsoft Säkerhetsinsikter PDF-filen)](https://www.microsoft.com/securityinsights/) (sök efter "utpressningstrojaner")</span><span class="sxs-lookup"><span data-stu-id="0e145-179">[The latest Microsoft Security Intelligence Report PDF)](https://www.microsoft.com/securityinsights/) (search for "ransomware")</span></span>

<span data-ttu-id="0e145-180">**Utpressningstrojan: En genomgående och pågående hotrapport** i noden **Hotanalys** i Microsoft 365 Defender portalen</span><span class="sxs-lookup"><span data-stu-id="0e145-180">**Ransomware: A pervasive and ongoing threat** report in the **Threat analytics node** of the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="0e145-181">Microsoft 365 skydd:</span><span class="sxs-lookup"><span data-stu-id="0e145-181">Microsoft 365 protection:</span></span>

- [<span data-ttu-id="0e145-182">Identifiering av utpressningstrojaner och återställning av filer i OneDrive</span><span class="sxs-lookup"><span data-stu-id="0e145-182">Ransomware detection and recovering your files in OneDrive</span></span>](https://support.microsoft.com/office/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)
- [<span data-ttu-id="0e145-183">Aktivera eller inaktivera makron i Office filer</span><span class="sxs-lookup"><span data-stu-id="0e145-183">Enable or disable macros in Office files</span></span>](https://support.microsoft.com/office/12b036fd-d140-4e74-b45e-16fed1a7e5c6)
- [<span data-ttu-id="0e145-184">Rekommenderade inställningar för EOP och Microsoft Defender för Office 365 säkerhet</span><span class="sxs-lookup"><span data-stu-id="0e145-184">Recommended settings for EOP and Microsoft Defender for Office 365 security</span></span>](recommended-settings-for-eop-and-office365.md)

<span data-ttu-id="0e145-185">Blogginlägg för Microsoft Security-teamet:</span><span class="sxs-lookup"><span data-stu-id="0e145-185">Microsoft Security team blog posts:</span></span>

- [<span data-ttu-id="0e145-186">Att bli flexibel genom att förstå riskerna för cybersäkerhet: del 4 – navigering mot aktuella hot (maj 2021)</span><span class="sxs-lookup"><span data-stu-id="0e145-186">Becoming resilient by understanding cybersecurity risks: Part 4—navigating current threats (May 2021)</span></span>](https://www.microsoft.com/security/blog/2021/05/26/becoming-resilient-by-understanding-cybersecurity-risks-part-4-navigating-current-threats/)

  <span data-ttu-id="0e145-187">Se **avsnittet Utpressningstrojaner.**</span><span class="sxs-lookup"><span data-stu-id="0e145-187">See the **Ransomware** section.</span></span>

- [<span data-ttu-id="0e145-188">Human-operated ransomware attacks: A preventable disaster (March 2020)</span><span class="sxs-lookup"><span data-stu-id="0e145-188">Human-operated ransomware attacks: A preventable disaster (March 2020)</span></span>](https://www.microsoft.com/security/blog/2020/03/05/human-operated-ransomware-attacks-a-preventable-disaster/)
- [<span data-ttu-id="0e145-189">Svar på utpressningstrojaner – för att betala eller inte betala? (december 2019)</span><span class="sxs-lookup"><span data-stu-id="0e145-189">Ransomware response—to pay or not to pay? (December 2019)</span></span>](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)
- [<span data-ttu-id="0e145-190">NorskSon svarar på utpressningstrojaner med transparens (december 2019)</span><span class="sxs-lookup"><span data-stu-id="0e145-190">Norsk Hydro responds to ransomware attack with transparency (December 2019)</span></span>](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)
- [<span data-ttu-id="0e145-191">En värdig uppgradering: nästa generations säkerhet på Windows 10 bevisar flexibelt mot utpressningstrojaner under 2017 (januari 2018)</span><span class="sxs-lookup"><span data-stu-id="0e145-191">A worthy upgrade: Next-gen security on Windows 10 proves resilient against ransomware outbreaks in 2017 (January 2018)</span></span>](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

