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
ms.openlocfilehash: 29afb66dd90be3917d576a7533900e21a91966c0
ms.sourcegitcommit: 6007dbe2cf758c683de399f94023122c678bcada
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/14/2020
ms.locfileid: "44224715"
---
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a>Återhämta sig från en ransomware attack i Microsoft 365

Även om du vidtar alla försiktighetsåtgärder för att skydda din organisation, kan du fortfarande falla offer för en [ransomware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) attack. Ransomware är big business, och attackerna är verifiera sofistikerade.

Stegen i det här avsnittet ger dig den bästa chansen att återställa data som krypterades av ransomware, och hjälper till att stoppa spridningen av infektionen i din organisation. Innan du börjar bör du tänka på följande:

- Det finns ingen garanti för att betala lösen kommer att returnera tillgång till dina filer. Faktum är att betala lösen kan göra dig till ett mål för mer ransomware. Om du redan har betalat, men du lyckades återställa dina filer utan att behöva använda angriparens lösning, bör du ringa din bank för att se om de kan blockera transaktionen. Vi rekommenderar också att du rapporterar ransomware-attacken till brottsbekämpande myndigheter, webbplatser för bedrägerirapportering och Microsoft enligt beskrivningen senare i det här avsnittet.

- Det är mycket viktigt att du reagerar snabbt på attacken och dess konsekvenser. Ju längre du väntar, desto mindre sannolikt är det att du kan återställa de berörda data.

## <a name="step-1-verify-your-backups"></a>Steg 1: Verifiera dina säkerhetskopior

Om du har offlinesäkerhetskopior kan du förmodligen återställa krypterade data **när** du har tagit bort nyttolasten för ransomware (malware) från din miljö.

Om du inte har säkerhetskopior, eller om dina säkerhetskopior också påverkades av ransomware, kan du hoppa över det här steget.

## <a name="step-2-disable-activesync-and-onedrive-sync"></a>Steg 2: Inaktivera ActiveSync- och OneDrive-synkronisering

Den viktigaste punkten här är att stoppa spridningen av datakryptering av ransomware.

Om du misstänker att e-post är ett mål bör du tillfälligt inaktivera användaråtkomst till postlådor. Exchange ActiveSync används av mobila enheter för att synkronisera data mellan enheten och Exchange Online-postlådan.

Information om hur du inaktiverar ActiveSync för en postlåda finns i [Inaktivera Exchange ActiveSync för användare i Exchange Online](https://support.microsoft.com/help/2795303/how-to-disable-exchange-activesync-for-users-in-office-365).

Om du vill inaktivera andra typer av åtkomst till en postlåda läser du:

- [Aktivera eller inaktivera MAPI för en postlåda](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).

- [Aktivera eller inaktivera POP3- eller IMAP4-åtkomst för en användare](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

Om du pausar OneDrive-synkronisering kan du skydda molndata från att uppdateras av potentiellt infekterade enheter. Mer information finns [i Så här pausar och återupptar du synkroniseringen i OneDrive](https://support.office.com/article/2152bfa4-a2a5-4d3a-ace8-92912fb4421e).

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a>Steg 3: Ta bort skadlig kod från de berörda enheterna

Kör en fullständig antivirussökning med de senaste uppdateringarna på alla misstänkta datorer och enheter för att identifiera och ta bort nyttolasten som är associerad med ransomware. Glöm inte enheter som synkroniserar data eller målet för mappade nätverksenheter (dessa datorer och enheter måste också skannas).

Du kan använda [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) eller (för äldre klienter) Microsoft [Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201).

Ett alternativ som också hjälper dig att ta bort ransomware eller skadlig kod är [Malicious Software Removal Tool (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905).

Om de här alternativen inte fungerar kan du prova [Windows Defender Offline](https://support.microsoft.com/help/17466/windows-defender-offline-help-protect-my-pc) eller [felsöka problem med att identifiera och ta bort skadlig kod](https://support.microsoft.com/help/4466982/windows-10-troubleshoot-problems-with-detecting-and-removing-malware).

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a>Steg 4: Återställa filer på en rengjord dator eller enhet

När du har slutfört föregående steg för att ta bort ransomware nyttolasten från din miljö (vilket kommer att hindra ransomware från att kryptera eller ta bort dina filer), kan du använda [Filhistorik](https://support.microsoft.com/help/17128/windows-8-file-history) i Windows 10 och Windows 8.1 eller Systemskydd i Windows 7 för att försöka återställa dina lokala filer och mappar.

**Anmärkningar**:

- Vissa ransomware krypterar eller tar bort de säkerhetskopierade versionerna, så du kan inte använda Filhistorik eller Systemskydd för att återställa filer. Om det händer måste du använda säkerhetskopior på externa enheter eller enheter som inte påverkades av ransomware eller OneDrive enligt beskrivningen i nästa avsnitt.

- Om en mapp synkroniseras med OneDrive och du inte använder den senaste versionen av Windows kan det finnas vissa begränsningar med filhistorik.

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a>Steg 5: Återställa dina filer i Din OneDrive för företag

Med Filåterställning i OneDrive för företag kan du återställa hela OneDrive till en tidigare tidpunkt inom de senaste 30 dagarna. Mer information finns i [Återställa OneDrive](https://support.office.com/article/fa231298-759d-41cf-bcd0-25ac53eb8a15).

## <a name="step-6-recover-deleted-email"></a>Steg 6: Återställa borttaget e-postmeddelande

I det sällsynta fallet att ransomware bort alla dina e-postmeddelanden, kan du förmodligen återställa de borttagna objekten. Mer information finns i:

- [Återställa borttagna meddelanden i en användares postlåda](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [Återställa borttagna objekt i Outlook för Windows](https://support.office.com/article/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a>Steg 7: Återaktivera Synkronisering av Exchange ActiveSync och OneDrive

När du har rensat datorer och enheter och återställt dina data kan du återaktivera ActiveSync- och OneDrive-synkronisering som du tidigare inaktiverat i [steg 2](#step-2-disable-activesync-and-onedrive-sync).

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a>Steg 8 (valfritt): Blockera OneDrive-synkronisering för specifika filtillägg

När du har återställt kan du förhindra att OneDrive för företag-klienter synkroniserar de filtyper som påverkades av det här ransomware.After you've recovered, you can prevent OneDrive for Business clients from synchronizing the file types that were affected by this ransomware. Mer information finns i [Set-SPOTenantSyncClientRestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)

## <a name="report-the-attack"></a>Rapportera attacken

### <a name="contact-law-enforcement"></a>Kontakta polisen

Du bör kontakta din lokala eller federala brottsbekämpande organ. Om du till exempel befinner dig i USA kan du kontakta [FBI:s lokala fältkontor,](https://www.fbi.gov/contact-us/field) [IC3](http://www.ic3.gov/complaint/default.aspx) eller [Secret Service](http://www.secretservice.gov/).

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a>Skicka en rapport till ditt lands webbplats för bluffrapportering

Bluff rapportering webbplatser ger information om hur man kan förebygga och undvika bedrägerier. De ger också mekanismer för att rapportera om du var offer för bluff.

- Australien: [SCAMwatch](http://www.scamwatch.gov.au/)

- Kanada: [Kanadensiska bedrägeribekämpning Centre](http://www.antifraudcentre-centreantifraude.ca/)

- Frankrike: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)

- Tyskland: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)

- Irland: [En Garda Síochána](http://www.garda.ie/)

- Nya Zeeland: [Konsumentfrågor Scams](http://www.consumeraffairs.govt.nz/scams)

- Storbritannien: [Action Fraud](http://www.actionfraud.police.uk/)

- USA: [På guard online](http://www.onguardonline.gov/)

Om ditt land inte finns med i listan frågar du dina lokala eller federala brottsbekämpande organ.

### <a name="submit-email-messages-to-microsoft"></a>Skicka e-postmeddelanden till Microsoft

Du kan rapportera nätfiskemeddelanden som innehåller utpressningsartiklar med hjälp av någon av flera metoder. Mer informations finns i [Anmäla meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="see-also"></a>Se även

- [Ransomware (lösenköp)](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware)

- [Ransomware svar-att betala eller inte betala?](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)

- [Norsk Hydro svarar på ransomware attack med öppenhet](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)

- [Ransomware identifiering och återställa dina filer i OneDrive](https://support.microsoft.com/en-us/office/ransomware-detection-and-recovering-your-files-0d90ec50-6bfd-40f4-acc7-b8c12c73637f)

- [Microsofts säkerhetsinformationsrapport](https://www.microsoft.com/securityinsights/)

- [Aktivera eller inaktivera makron i Office-filer](https://support.office.com/article/12b036fd-d140-4e74-b45e-16fed1a7e5c6)

- [Rekommenderade inställningar för EOP- och Office 365 ATP-säkerhet](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp)

- [En värdig uppgradering: Nästa generations säkerhet på Windows 10 visar sig vara motståndskraftig mot ransomware utbrott i 2017](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

- [Ingen mas, Samas: Vad finns i denna ransomware modus operandi?](https://www.microsoft.com/security/blog/2016/03/17/no-mas-samas-whats-in-this-ransomwares-modus-operandi/)

- [Locky malware, tur att undvika det](https://www.microsoft.com/security/blog/2016/02/24/locky-malware-lucky-to-avoid-it/)

- [MSRT juli 2016: Cerber ransomware](https://www.microsoft.com/security/blog/2016/07/12/msrt-july-2016-cerber-ransomware/)

- [De tre cheferna för Cerberus-liknande Cerber ransomware](https://www.microsoft.com/security/blog/2016/03/09/the-three-heads-of-the-cerberus-like-cerber-ransomware/)

- [Troldesh ransomware påverkas av (den) Da Vinci-koden](https://www.microsoft.com/security/blog/2016/07/13/troldesh-ransomware-influenced-by-the-da-vinci-code/)
