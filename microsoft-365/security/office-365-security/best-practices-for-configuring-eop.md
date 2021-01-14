---
title: Metodtips för konfiguration av EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: faf1efd1-3b0c-411a-804d-17f37292eac0
description: Följ de här rekommendationerna för en fristående Exchange Online Protection (EOP) för att ställa in dig själv och undvika vanliga konfigurations fel.
ms.openlocfilehash: a229f8a269037296fa2b97ff7211343549b33685
ms.sourcegitcommit: cc354fd54400be0ff0401f60bbe68ed975b69cda
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/14/2021
ms.locfileid: "49864894"
---
# <a name="best-practices-for-configuring-standalone-eop"></a>Metod tips för att konfigurera fristående EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Följ de här rekommendationerna för en fristående Exchange Online Protection (EOP) för att ställa in dig själv och undvika vanliga konfigurations fel. I det här avsnittet förutsätts det att du redan har slutfört installationen. Om du inte har slutfört EOP installations programmet läser du [Konfigurera EOP-tjänsten](set-up-your-eop-service.md).

## <a name="use-a-test-domain"></a>Använda en test domän

Vi rekommenderar att du använder en test domän, en under domän eller en låg volym domän för att pröva tjänst funktioner innan du implementerar dem på din produktions domän.

## <a name="synchronize-recipients"></a>Synkronisera mottagare

Om organisationen har befintliga användar konton i en lokal Active Directory-miljö kan du synkronisera dessa konton med Azure Active Directory i molnet. Du rekommenderas att använda Directory-synkronisering. Om du vill veta mer om fördelarna med att använda katalog synkronisering och hur du konfigurerar den finns i [Hantera e-postanvändare i EOP](manage-mail-users-in-eop.md).

## <a name="recommended-settings"></a>Rekommenderade inställningar

Vi stärker säkerhets organisationerna att anpassa sina säkerhets inställningar för att uppfylla organisationens behov. Ã ven om det är en allmän regel finns det två säkerhets nivåer i EOP och Microsoft Defender för Office 365 som vi rekommenderar: standard och Strict. De här inställningarna visas i [rekommenderade inställningar för EOP och Microsoft Defender för Office 365-säkerhet](recommended-settings-for-eop-and-office365-atp.md).

### <a name="miscellaneousnon-policy-settings"></a>Inställningar för diverse/icke-principer

Dessa inställningar täcker ett antal funktioner utanför säkerhets principer.

****

|Säkerhetsfunktionens namn|Standard|Tillåts|Kommentar|
|---|---|---|---|
|[Konfigurera SPF för att förhindra förfalskning](set-up-spf-in-office-365-to-help-prevent-spoofing.md)|Ja|Ja||
|[Använd DKIM för att validera utgående e-post som skickas från din egna domän i Office 365](use-dkim-to-validate-outbound-email.md)|Ja|Ja||
|[Använda DMARC för att validera e-post i Office 365](use-dmarc-to-validate-email.md)|Ja|Ja|Använd `action=quarantine` för standard och `action=reject` för strikt.|
|Distribuera [tillägget rapportera](enable-the-report-message-add-in.md) eller [rapportera](enable-the-report-phish-add-in.md) tillägg för att förbättra slutanvändarnas rapportering av misstänkt e-post|Ja|Ja||
|Schemalägg skadlig program vara och skräp post|Ja|Ja||
|Automatisk vidarebefordring till externa domäner tillåts inte heller att övervakas|Ja|Ja||
|Enhetlig granskning bör vara aktiverat|Ja|Ja||
|[IMAP-anslutning till post låda](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|Inaktiverad|Inaktiverad||
|[POP-anslutning till post låda](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|Inaktiverad|Inaktiverad||
|Autentiserad SMTP-överföring|Inaktiverad|Inaktiverad|SMTP-överföring med autentiserad klient (kallas även för klient SMTP-sändning eller SMTP-AUTH) krävs för att POP3-och IMAP4-klienter ska kunna skicka e-post.|
|EWS-anslutning till post låda|Inaktiverad|Inaktiverad||
|[PowerShell-anslutning](https://docs.microsoft.com/powershell/exchange/disable-access-to-exchange-online-powershell)|Inaktiverad|Inaktiverad|Tillgängligt för post lådor eller e-postanvändare (användar objekt som returneras av cmdleten [Get-User](https://docs.microsoft.com/powershell/module/exchange/get-user) ).|
|Använd [falska intelligens](learn-about-spoof-intelligence.md) för att lägga till avsändare i din lista över tillåtna|Ja|Ja||
|[Active Directory-baserad kant spärr (DBEB)](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)|Aktiverad|Aktiverad|Domän typ = auktoritär|
|[Konfigurera multifaktorautentisering för alla administratörs konton](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication)|Aktiverad|Aktiverad||
|

## <a name="troubleshooting"></a>Felsökning

Felsöka allmänna problem och trender med hjälp av rapporterna i administrations centret. Hitta specifika data om ett meddelande med hjälp av verktyget för meddelande spårning. Läs mer om rapportering vid [rapportering och meddelande spårning i Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md). Läs mer om verktyget för meddelande spårning [i meddelande spårning i säkerhets & Compliance Center](message-trace-scc.md).

## <a name="report-false-positives-and-false-negatives-to-microsoft"></a>Rapportera falska positiva och falska negativa negativ till Microsoft

För att förbättra filtreringen av skräp post i tjänsten för alla bör du rapportera falsk (e-postadress) och falskt negativ (dålig e-post) till Microsoft för analys. Mer informations finns i [Anmäla meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="create-mail-flow-rules"></a>Skapa regler för e-postflöde

Skapa regler för e-postflöde (kallas även transport regler) eller anpassade filter för att uppfylla företagets behov.

När du distribuerar en ny regel för produktion väljer du först ett av test stegen för att se resultatet av regeln. När du är nöjd med att regeln fungerar på det sätt som är tänkt kan du ändra regel läget för att **tvinga fram**.

När du distribuerar nya regler bör du överväga att lägga till ytterligare åtgärder i **generera incident rapport** för att övervaka regeln.

I hybrid miljöer där din organisation inkluderar både lokalt Exchange och Exchange Online bör du överväga vilka villkor du använder i regler för e-postflöde. Om du vill att reglerna ska gälla för hela organisationen måste du använda villkor som är tillgängliga i både lokalt Exchange och i Exchange Online. De flesta förhållanden är tillgängliga i båda miljöerna, men det finns några som bara är tillgängliga i en enda miljö. Läs mer i [regler för e-postflöden (transport regler) i Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).
