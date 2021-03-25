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
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a>Återställ från en utpressningstrojanattack i Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Även om du vidtar alla försiktighetsåtgärd för att skydda organisationen kan du fortfarande falla offer för en [utpressningstrojanattack.](/windows/security/threat-protection/intelligence/ransomware-malware) Utpressningstrojaner är en stor verksamhet och attackerna är mycket avancerade.

Med stegen i den här artikeln får du bäst chans att återställa data och stoppa den interna spridningen av smitta. Innan du börjar bör du tänka på följande:

- Det finns ingen garanti för att betalning av utpressningstrojanen returnerar åtkomsten till dina filer. Att betala utpressningstrojanen kan faktiskt göra dig till ett mål för mer utpressningstrojaner.

  Om du redan har betalat men du har återskapat utan att använda attackerarens lösning kontaktar du din bank för att se om de kan blockera transaktionen.

  Vi rekommenderar även att du rapporterar utpressningstrojanattacken till olika webbplatser för utpressningstrojaner, bedrägerirapportering och Microsoft enligt beskrivningen senare i den här artikeln.

- Det är viktigt att du svarar snabbt på attacken och dess konsekvenser. Ju längre du väntar, desto mindre troligt är det att du kan återskapa berörda data.

## <a name="step-1-verify-your-backups"></a>Steg 1: Kontrollera dina säkerhetskopior

Om du har säkerhetskopieringar offline kan du antagligen återställa krypterade **data** efter att du har tagit bort nyttolasten för utpressningstrojan (skadlig kod) från din miljö.

Om du inte har några säkerhetskopior, eller om dina säkerhetskopior också påverkades av utpressningstrojanen, kan du hoppa över det här steget.

## <a name="step-2-disable-exchange-activesync-and-onedrive-sync"></a>Steg 2: Inaktivera Exchange ActiveSync och OneDrive-synkronisering

Det viktiga här är att stoppa uppslaget av datakryptering genom utpressningstrojanen.

Om du misstänker att e-postmeddelanden är målet för utpressningstrojankryptering inaktiverar du tillfälligt användarnas åtkomst till postlådor. Exchange ActiveSync synkroniserar data mellan enheter och Exchange Online-postlådor.

Om du vill inaktivera Exchange ActiveSync för en postlåda kan [du gå till Inaktivera Exchange ActiveSync för användare i Exchange Online.](https://support.microsoft.com/help/2795303)

Information om hur du inaktiverar andra typer av åtkomst till en postlåda finns i:

- [Aktivera eller inaktivera MAPI för en postlåda.](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi)

- [Aktivera eller inaktivera åtkomst via POP3 eller IMAP4 för en användare](/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

Om du pausar OneDrive-synkroniseringen skyddas dina molndata från att uppdateras av potentiellt smittade enheter. Mer information finns i [Pausa och återuppta synkronisering i OneDrive.](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e)

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a>Steg 3: Ta bort den skadlig programvara från de berörda enheterna

Kör en fullständig, aktuell antivirussökning på alla misstänkta datorer och enheter för att identifiera och ta bort den nyttolast som är kopplad till utpressningstrojanen.

Glöm inte att skanna enheter som synkroniserar data eller mål för mappade nätverksenheter.

Du kan använda [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) eller Microsoft Security Essentials (för [äldre klienter).](https://www.microsoft.com/download/details.aspx?id=5201)

Ett alternativ som också hjälper dig att ta bort utpressningstrojaner eller skadlig programvara är verktyget För borttagning av skadlig programvara [(MSRT).](https://www.microsoft.com/download/details.aspx?id=9905)

Om de här alternativen inte fungerar kan du prova [Windows Defender Offline eller](https://support.microsoft.com/help/17466) Felsöka problem med att identifiera och ta bort skadlig [programvara.](https://support.microsoft.com/help/4466982)

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a>Steg 4: Återställa filer på en rensad dator eller enhet

När du har slutfört det föregående steget för att ta bort utpressningstrojanen från miljön (vilket hindrar [](https://support.microsoft.com/help/17128) utpressningstrojanen från att kryptera eller ta bort filer) kan du använda Filhistorik i Windows 10 och Windows 8.1 eller System Protection i Windows 7 för att försöka återställa dina lokala filer och mappar.

**Anmärkningar**:

- En del utpressningstrojaner krypterar eller tar bort säkerhetskopiorna, så du kan inte använda Filhistorik eller Systemskydd för att återställa filer. Om det händer behöver du använda säkerhetskopior på externa enheter eller enheter som inte påverkades av utpressningstrojanen eller OneDrive enligt beskrivningen i nästa avsnitt.

- Om en mapp är synkroniserad med OneDrive och du inte använder den senaste versionen av Windows kan det finnas vissa begränsningar i Filhistorik.

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a>Steg 5: Återställa filer i OneDrive för företag

Med Filåterställning i OneDrive för företag kan du återställa hela OneDrive till en föregående tidpunkt under de senaste 30 dagarna. Mer information finns i [Återställa din OneDrive.](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)

## <a name="step-6-recover-deleted-email"></a>Steg 6: Återskapa borttagna e-postmeddelanden

I de sällsynta fall som utpressningstrojanen tog bort alla dina e-postmeddelanden kan du antagligen återställa de borttagna objekten. Mer information finns i:

- [Återställa borttagna meddelanden i en användares postlåda](/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [Återskapa borttagna objekt i Outlook för Windows](https://support.microsoft.com/office/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a>Steg 7: Återaktivera Exchange ActiveSync och OneDrive-synkronisering

När du har rensat dina datorer och enheter och återskapat dina data kan du återaktivera Exchange ActiveSync- och OneDrive-synkronisering som du tidigare [inaktiverade i steg 2.](#step-2-disable-exchange-activesync-and-onedrive-sync)

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a>Steg 8 (valfritt): Blockera OneDrive-synkronisering för specifika filnamnstillägg

När du har återställt kan du förhindra att OneDrive för företag-klienter synkroniserar filtyper som påverkades av den här utpressningstrojanen. Mer information finns i [Set-SPOTenantSyncClientRestriction](/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)

## <a name="report-the-attack"></a>Rapportera attacken

### <a name="contact-law-enforcement"></a>Kontaktperson vid rättsendning

Kontakta dina lokala eller federala rättsbyråer. Om du befinner dig i USA kan du exempelvis kontakta det lokala [fältet AVSE,](https://www.fbi.gov/contact-us/field) [IC3](http://www.ic3.gov/complaint/default.aspx) eller [Hemlig tjänst.](http://www.secretservice.gov/)

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a>Skicka en rapport till ditt lands webbplats för bedrägerirapportering

På webbplatserna för bedrägerirapportering finns information om hur du kan förhindra och undvika bedrägerier. De har även mekanismer för att rapportera om du var offer för bedrägeri.

- Australien: [SCAMwatch](http://www.scamwatch.gov.au/)

- Kanada: [Canadian Anti-Fraud Centre](http://www.antifraudcentre-centreantifraude.ca/)

- Frankrike: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)

- Tyskland: [Det första talet i tysklandet für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)

- Irland: [An Mádo Síochána](http://www.garda.ie/)

- Nya Zeeland: [Consumer Affairs Scams](http://www.consumeraffairs.govt.nz/scams)

- Storbritannien: [Åtgärdsbedrägerier](http://www.actionfraud.police.uk/)

- USA: [On Guard Online](http://www.onguardonline.gov/)

Om ditt land inte finns med i listan kan du fråga ditt lokala eller federala myndigheter.

### <a name="submit-email-messages-to-microsoft"></a>Skicka e-postmeddelanden till Microsoft

Du kan rapportera nätfiskemeddelanden som innehåller utpressningstrojaner på flera olika sätt. Mer informations finns i [Anmäla meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="see-also"></a>Se även

- [Utpressningstrojaner](/windows/security/threat-protection/intelligence/ransomware-malware)

- [Svar på utpressningstrojaner – för att betala eller inte betala?](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)

- [NorskSon svarar på utpressningstrojaner med transparens](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)

- [Identifiering av utpressningstrojaner och återställa filer i OneDrive](https://support.microsoft.com/office/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)

- [Microsoft Security Intelligence-rapport](https://www.microsoft.com/securityinsights/)

- [Aktivera eller inaktivera makron i Office-filer](https://support.microsoft.com/office/12b036fd-d140-4e74-b45e-16fed1a7e5c6)

- [Rekommenderade inställningar för EOP och Microsoft Defender för Office 365-säkerhet](recommended-settings-for-eop-and-office365.md)

- [En värdig uppgradering: Nästa generationens säkerhet i Windows 10 bevisar sin motståndskraft mot utpressningstrojaner under 2017](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

- [Inte mas, Samas: Vad finns i den här utpressningstrojanens modus operandi?](https://www.microsoft.com/security/blog/2016/03/17/no-mas-samas-whats-in-this-ransomwares-modus-operandi/)

- [Locky-skadlig programvara, tur att undvika det](https://www.microsoft.com/security/blog/2016/02/24/locky-malware-lucky-to-avoid-it/)

- [MSRT juli 2016: Cerber-utpressningstrojan](https://www.microsoft.com/security/blog/2016/07/12/msrt-july-2016-cerber-ransomware/)

- [De tre huvudena i Cerberus-liknande Cerber-utpressningstrojaner](https://www.microsoft.com/security/blog/2016/03/09/the-three-heads-of-the-cerberus-like-cerber-ransomware/)

- [Troldesh-utpressningstrojanen påverkas av () Da Kod för DaKod](https://www.microsoft.com/security/blog/2016/07/13/troldesh-ransomware-influenced-by-the-da-vinci-code/)