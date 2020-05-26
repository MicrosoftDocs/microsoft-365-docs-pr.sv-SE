---
title: Metodtips för konfiguration av EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: faf1efd1-3b0c-411a-804d-17f37292eac0
description: Följ de här rekommendationerna om bästa praxis för fristående Exchange Online Protection (EOP) för att ställa in dig själv för framgång och undvika vanliga konfigurationsfel.
ms.openlocfilehash: ade41b5343e19f75658f01e6c395c470e230b315
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/23/2020
ms.locfileid: "44351933"
---
# <a name="best-practices-for-configuring-standalone-eop"></a>Metodtips för att konfigurera fristående EOP

Följ de här rekommendationerna om bästa praxis för fristående Exchange Online Protection (EOP) för att ställa in dig själv för framgång och undvika vanliga konfigurationsfel. Det här avsnittet förutsätter att du redan har slutfört installationsprocessen. Om du inte har slutfört EOP-installationen läser du [Konfigurera din EOP-tjänst](set-up-your-eop-service.md).

## <a name="use-a-test-domain"></a>Använda en testdomän

Vi rekommenderar att du använder en testdomän, underdomän eller lågvolymdomän för att prova tjänstfunktioner innan du implementerar dem på dina produktionsdomäner med högre volym.

## <a name="synchronize-recipients"></a>Synkronisera mottagare

Om din organisation har befintliga användarkonton i en lokal Active Directory-miljö kan du synkronisera dessa konton till Azure Active Directory i molnet. Användning av katalogsynkronisering rekommenderas. Mer information om fördelarna med att använda katalogsynkronisering och stegen för att konfigurera den finns [i Hantera e-postanvändare i EOP](manage-mail-users-in-eop.md).

## <a name="recommended-settings"></a>Rekommenderade inställningar

Vi ger säkerhetsadministratörer möjlighet att anpassa sina säkerhetsinställningar för att tillgodose organisationens behov. Även om det i regel finns två säkerhetsnivåer i EOP och Office 365 ATP som vi rekommenderar: Standard och Strikt. De här inställningarna visas i [de rekommenderade inställningarna för EOP- och Office 365 ATP-säkerhet](recommended-settings-for-eop-and-office365-atp.md).

### <a name="miscellaneousnon-policy-settings"></a>Inställningar för diverse/icke-princip

De här inställningarna täcker en rad funktioner som ligger utanför säkerhetsprinciper.

|||||
|---|---|---|---|
|**Namn på säkerhetsfunktionen**|**Standard**|**Strikt**|**Kommentar**|
|[Konfigurera SPF för att förhindra förfalskning](set-up-spf-in-office-365-to-help-prevent-spoofing.md)|Ja|Ja||
|[Använd DKIM för att validera utgående e-post som skickas från din egna domän i Office 365](use-dkim-to-validate-outbound-email.md)|Ja|Ja||
|[Använda DMARC för att validera e-post i Office 365](use-dmarc-to-validate-email.md)|Ja|Ja|Används `action=quarantine` för Standard och för `action=reject` Strikt.|
|Distribuera [tillägget Rapportmeddelande](enable-the-report-message-add-in.md) för att förbättra slutanvändarens rapportering av misstänkt e-post|Ja|Ja||
|Schemalägg rapporter om skadlig kod och skräppost|Ja|Ja||
|Automatisk vidarebefordran till externa domäner bör inte tillåtas eller övervakas|Ja|Ja||
|Enhetlig granskning bör aktiveras|Ja|Ja||
|[IMAP-anslutning till postlåda](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|Inaktiverad|Inaktiverad||
|[POP-anslutning till postlåda](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|Inaktiverad|Inaktiverad||
|Autentiserat SMTP-inlämnande|Inaktiverad|Inaktiverad|Autentiserade smtp-klientöverföring (kallas även klient-SMTP-inlämning eller SMTP AUTH) krävs för att POP3- och IMAP4-klienter ska kunna skicka e-post.|
|EWS-anslutning till postlåda|Inaktiverad|Inaktiverad||
|[PowerShell-anslutning](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)|Inaktiverad|Inaktiverad|Tillgänglig för postlådeanvändare eller [e-postanvändare](https://docs.microsoft.com/powershell/module/exchange/get-user) (användarobjekt som returneras av cmdleten Hämta användare).|
|Använd [falska underrättelser](learn-about-spoof-intelligence.md) för att vitlista avsändare när det är möjligt|Ja|Ja||
|[Katalogbaserad kantblockering (DBEB)](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)|Aktiverad|Aktiverad|Domäntyp = Auktoritär|
|[Konfigurera multifaktorautentisering för alla administratörskonton](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication)|Aktiverad|Aktiverad||
|

## <a name="troubleshooting"></a>Felsökning

Felsöka allmänna problem och trender med hjälp av rapporterna i administrationscentret. Hitta en punktspecifika data om ett meddelande med hjälp av meddelandespårningsverktyget. Läs mer om rapportering vid [rapportering och meddelandespårning i Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md). Läs mer om meddelandespårningsverktyget vid [meddelandespårning i Security & Compliance Center](message-trace-scc.md).

## <a name="report-false-positives-and-false-negatives-to-microsoft"></a>Rapportera falska positiva identifieringar och falska negativ till Microsoft

För att förbättra skräppostfiltrering i tjänsten för alla, bör du rapportera falska positiva (bra e-post markerad som dålig) och falska negativ (dålig e-post tillåten) till Microsoft för analys. Mer informations finns i [Anmäla meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="create-mail-flow-rules"></a>Skapa regler för e-postflöde

Skapa regler för e-postflöde (kallas även transportregler) eller anpassade filter för att uppfylla dina affärsbehov.

När du distribuerar en ny regel till produktion väljer du ett av testlägena först för att se effekten av regeln. När du är övertygad om att regeln fungerar på det sätt som är avsett ändrar du regelläget så att **det framtvingar**.

När du distribuerar nya regler bör du överväga att lägga till ytterligare åtgärder **i generera incidentrapport** för att övervaka regeln i praktiken.

I hybridmiljöer där din organisation innehåller både lokala Exchange- och Exchange Online bör du tänka på de villkor som du använder i reglerna för e-postflöde. Om du vill att reglerna ska gälla för hela organisationen måste du använda villkor som är tillgängliga både i lokala Exchange och Exchange Online. De flesta villkor är tillgängliga i båda miljöerna, men det finns några som bara är tillgängliga i den ena eller den andra miljön. Läs mer på [Regler för e-postflöde (transportregler) i Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).
