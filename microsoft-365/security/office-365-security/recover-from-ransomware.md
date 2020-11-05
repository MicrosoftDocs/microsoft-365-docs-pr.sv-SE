---
title: Återställa efter utpressningstrojanattack
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.article: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Microsoft 365-administratörer kan läsa mer om hur man återställer från en utpressnings tro Jan attack.
ms.openlocfilehash: de1cddbdf1c2b3ffeb8fd74a8f0d31e815eb1b70
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920614"
---
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a>Återställ från en utpressnings tro Jan attack i Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Även om du gör alla försiktighets åtgärder för att skydda din organisation kan du fortfarande falla ned till en [utpressnings tro Jan](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) attack. Utpressnings tro vara är stort företag och de är mycket avancerade.

Stegen i den här artikeln ger dig den bästa chansen att återställa data och stoppa det interna spridningen av infektion. Tänk på följande innan du börjar:

- Det är inte säkert att betala utpressnings tro återkommer till dina filer. Det kan vara enklare för dig att betala utpressnings tro.

  Om du redan har betalat men återställt utan att använda angriparens lösning kontaktar du din bank för att se om de kan blockera transaktionen.

  Vi rekommenderar också att du rapporterar utpressnings tro Jan attack för att genomdriva, bedrägeri rapporterings webbplatser och Microsoft enligt beskrivningen längre ned i den här artikeln.

- Det är viktigt att du svarar snabbt på angreppen och dess konsekvenser. Det längre du väntar, det mindre troligt att du kan återställa de data som påverkas.

## <a name="step-1-verify-your-backups"></a>Steg 1: kontrol lera säkerhets kopiorna

Om du har säkerhets kopiering offline kan du troligt vis återställa krypterade data **när** du har tagit bort utpressnings Tronas nytto Last (malware) från din miljö.

Om du inte har säkerhets kopior, eller om dina säkerhets kopior också påverkas av utpressnings tro Jan, kan du hoppa över det här steget.

## <a name="step-2-disable-exchange-activesync-and-onedrive-sync"></a>Steg 2: inaktivera synkronisering av Exchange ActiveSync och OneDrive

Huvud punkten här är att stoppa spridningen av data kryptering av utpressnings tro janheten.

Om du misstänker att e-post är ett mål för utpressnings krypteringen kan du tillfälligt inaktivera användar åtkomst till post lådor. Exchange ActiveSync synkroniserar data mellan enheter och Exchange Online-postlådor.

Information om hur du inaktiverar Exchange ActiveSync för en post låda finns i [så här inaktiverar du Exchange ActiveSync för användare i Exchange Online](https://support.microsoft.com/help/2795303).

Information om hur du inaktiverar andra typer av åtkomst till en post låda finns i:

- [Aktivera eller inaktivera MAPI för en post låda](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).

- [Aktivera eller inaktivera POP3-eller IMAP4-åtkomst för en användare](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

Om du pausar OneDrive-synkronisering kommer dina moln data att skyddas från potentiellt infekterade enheter. Mer information finns i [så här pausar och återupptar du synkronisering på OneDrive](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e).

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a>Steg 3: ta bort skadlig kod från berörda enheter

Kör en fullständig, aktuell Antivirus sökning på alla misstänkta datorer och enheter för att upptäcka och ta bort nytto lasten som är associerad med utpressnings tjänsten.

Glöm inte att skanna enheter som synkroniserar data eller målen med mappade nätverks enheter.

Du kan använda [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) eller (för äldre klienter) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201).

Ett alternativ som du kan använda för att ta bort utpressnings tro Jan eller skadlig [program vara (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905).

Om de här alternativen inte fungerar kan du prova [Windows Defender Offline](https://support.microsoft.com/help/17466) eller [Felsöka problem med att upptäcka och ta bort skadlig kod](https://support.microsoft.com/help/4466982).

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a>Steg 4: återställa filer på en ren dator eller enhet

När du har slutfört föregående steg för att ta bort utpressnings tro janheten från din miljö (som hindrar utpressnings tro från att kryptera eller ta bort filer) kan du använda [fil historik](https://support.microsoft.com/help/17128) i Windows 10 och Windows 8,1 eller system skydd i Windows 7 för att försöka återställa dina lokala filer och mappar.

**Anmärkningar** :

- Vissa utpressnings Jan program kommer också att kryptera eller ta bort säkerhets kopior, så du kan inte använda fil historik eller system skydd för att återställa filer. Om det inträffar behöver du använda säkerhets kopior på externa enheter eller enheter som inte påverkades av utpressnings tro Jan eller OneDrive enligt beskrivningen i nästa avsnitt.

- Om en mapp synkroniseras med OneDrive och du inte använder den senaste versionen av Windows, kan det finnas vissa begränsningar i fil historiken.

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a>Steg 5: återställa filer i OneDrive för företag

Med återställning av filer i OneDrive för företag kan du återställa hela OneDrive till en tidigare tidpunkt inom de senaste 30 dagarna. Mer information finns i [återställa OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15).

## <a name="step-6-recover-deleted-email"></a>Steg 6: återställa borttagna e-postmeddelanden

I det sällsynta fallet att undertecknings program varan tagit bort all e-post kan du troligt vis återställa borttagna objekt. Mer information finns i:

- [Återställa borttagna meddelanden i en användares post låda](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [Återskapa borttagna objekt i Outlook för Windows](https://support.microsoft.com/office/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a>Steg 7: återaktivera Exchange ActiveSync och OneDrive-synkronisering

När du har rensat dina datorer och enheter och återställt dina data kan du återaktivera Exchange ActiveSync-och OneDrive-synkronisering som du tidigare inaktiverat i [steg 2](#step-2-disable-exchange-activesync-and-onedrive-sync).

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a>Steg 8 (valfritt): Blockera OneDrive-synkronisering för specifika fil namns tillägg

När du har återställt kan du förhindra att OneDrive för företag-klienter synkroniserar de filtyper som påverkades av den här utpressnings tro varan. Mer information finns i [set-SPOTenantSyncClientRestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)

## <a name="report-the-attack"></a>Rapportera angreppet

### <a name="contact-law-enforcement"></a>Kontakta juridisk användning

Du bör kontakta den lokala eller federala polismyndigheten. Om du till exempel är i USA kan du kontakta [FBI lokala fält](https://www.fbi.gov/contact-us/field), [IC3](http://www.ic3.gov/complaint/default.aspx) eller [hemliga tjänsten](http://www.secretservice.gov/).

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a>Skicka en rapport till ditt lands webbplats för bedrägeri rapportering

Webbplatser för bluff rapportering ger information om hur du undviker och undviker bedrägerier. De tillhandahåller också mekanismer för att rapportera om du har blivit utsatt för bedrägeri.

- Australien: [SCAMwatch](http://www.scamwatch.gov.au/)

- Kanada: [kanadensiska centrum för bedrägeri bekämpning](http://www.antifraudcentre-centreantifraude.ca/)

- Frankrike: [Agence nation Ale de la sécurité des Systèmes D'information](http://www.ssi.gouv.fr/)

- Tyskland: [Bundesamt für Sicherheit i der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)

- Irland: [en Garda Síochána](http://www.garda.ie/)

- Nya Zeeland: [konsument frågor](http://www.consumeraffairs.govt.nz/scams)

- Storbritannien: [bedrägeri åtgärd](http://www.actionfraud.police.uk/)

- USA: [on Guard online](http://www.onguardonline.gov/)

Om ditt land inte finns med i listan kan du fråga dina myndigheter för kommuner och myndigheter.

### <a name="submit-email-messages-to-microsoft"></a>Skicka e-postmeddelanden till Microsoft

Du kan rapportera nät fiske meddelanden som innehåller utpressnings tro Jan med någon av flera olika metoder. Mer informations finns i [Anmäla meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="see-also"></a>Se även

- [Utpressningstrojaner](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware)

- [Utpressnings tro-och-svar – betalar eller inte betalar?](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)

- [Norsk Hydro svarar på utpressnings tro Jan attack med öppenhet](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)

- [Identifiering av utpressnings tro Jan och återställa dina filer i OneDrive](https://support.microsoft.com/office/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)

- [Microsoft Security Intelligence-rapport](https://www.microsoft.com/securityinsights/)

- [Aktivera eller inaktivera makron i Office-filer](https://support.microsoft.com/office/12b036fd-d140-4e74-b45e-16fed1a7e5c6)

- [Rekommenderade inställningar för EOP och Microsoft Defender för Office 365-säkerhet](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp)

- [En minnes-uppgradering: nästa generations säkerhet i Windows 10 visar att det är elastiskt mot utpressnings brott i 2017](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

- [Ingen Mas, samas: Vad är den här utpressnings tro Jans modus-operandi?](https://www.microsoft.com/security/blog/2016/03/17/no-mas-samas-whats-in-this-ransomwares-modus-operandi/)

- [Lås skadlig kod, Lucky för att undvika det](https://www.microsoft.com/security/blog/2016/02/24/locky-malware-lucky-to-avoid-it/)

- [MSRT juli 2016: Cerber utpressnings tro Jan](https://www.microsoft.com/security/blog/2016/07/12/msrt-july-2016-cerber-ransomware/)

- [De tre huvudena på Cerberus-liknande Cerber](https://www.microsoft.com/security/blog/2016/03/09/the-three-heads-of-the-cerberus-like-cerber-ransomware/)

- [Troldesh utpressnings Jan attack som påverkas av (den) da Vinci-koden](https://www.microsoft.com/security/blog/2016/07/13/troldesh-ransomware-influenced-by-the-da-vinci-code/)
