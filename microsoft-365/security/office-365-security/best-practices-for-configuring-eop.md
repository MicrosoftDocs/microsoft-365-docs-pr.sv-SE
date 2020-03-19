---
title: Metodtips för konfigurera EOP och Office 365 ATP
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: faf1efd1-3b0c-411a-804d-17f37292eac0
description: Följ dessa rekommendationer för bästa praxis för Exchange Online Protection (EOP) för att ställa in dig själv för framgång och undvika vanliga konfigurationsfel.
ms.openlocfilehash: b4b1f02e3b034b7e89d605a2164b6add3f20dae5
ms.sourcegitcommit: 3d17c1d6b80672719b1878e2f321f0de39595226
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/11/2020
ms.locfileid: "42805867"
---
# <a name="best-practices-for-configuring-eop-and-office-365-atp"></a>Metodtips för konfigurera EOP och Office 365 ATP

Följ dessa rekommendationer för bästa praxis för Exchange Online Protection (EOP) för att ställa in dig själv för framgång och undvika vanliga konfigurationsfel. Det här avsnittet förutsätter att du redan har slutfört installationen. Om du inte har slutfört EOP-installationen läser du [Konfigurera eOP-tjänsten](set-up-your-eop-service.md).

## <a name="use-a-test-domain"></a>Använda en testdomän

Vi rekommenderar att du använder en testdomän, underdomän eller lågvolymdomän för att prova servicefunktioner innan du implementerar dem på dina produktionsdomäner med högre volym.

## <a name="synchronize-recipients"></a>Synkronisera mottagare

Om din organisation har befintliga användarkonton i en lokal Active Directory-miljö kan du synkronisera dessa konton till Azure Active Directory i molnet. Användning av katalogsynkronisering rekommenderas. Mer information om fördelarna med att använda katalogsynkronisering och stegen för att konfigurera den finns i [Hantera e-postanvändare i EOP](manage-mail-users-in-eop.md).

## <a name="recommended-settings"></a>Rekommenderade inställningar

Vi ger säkerhetsadministratörer möjlighet att anpassa sina säkerhetsinställningar för att tillgodose organisationens behov. Även om det i allmänhet finns två säkerhetsnivåer i EOP och Office 365 ATP som vi rekommenderar: Standard och Strikt. De här inställningarna visas i de [rekommenderade inställningarna för EOP- och Office 365 ATP-säkerhet](recommended-settings-for-eop-and-office365-atp.md).

### <a name="miscellaneousnon-policy-settings"></a>Inställningar för diverse/icke-princip

De här inställningarna täcker en rad funktioner som ligger utanför säkerhetsprinciper.

|Namn på säkerhetsfunktioner|Standard|Strikt|Kommentar|
|---------|---------|---------|---------|
|[Konfigurera SPF i Office 365 för att förhindra förfalskning](set-up-spf-in-office-365-to-help-prevent-spoofing.md)|Ja|Ja||
|[Använda DKIM för att validera utgående e-post som skickas från din anpassade domän i Office 365](use-dkim-to-validate-outbound-email.md)|Ja|Ja||
|[Använda DMARC för att validera e-post i Office 365](use-dmarc-to-validate-email.md)|Ja|Ja|Använd action=quarantine för Standard och action=avvisa för Strikt.|
|Distribuera rapportmeddelandetillägg för att förbättra slutanvändarrapporteringen för misstänkta e-postmeddelanden|Ja|Ja||
|Schemalägg rapporter om skadlig programvara och skräppost|Ja|Ja||
|Automatisk vidarebefordran till externa domäner bör inte tillåtas eller övervakas|Ja|Ja||
|Enhetlig revision bör aktiveras|Ja|Ja||
|[IMAP-anslutning till postlåda](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|Inaktiverad|Inaktiverad||
|[POP-anslutning till postlåda](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|Inaktiverad|Inaktiverad||
|SMTP Autentiserad inlämning till postlåda|Inaktiverad|Inaktiverad||
|EWS-anslutning till postlåda|Inaktiverad|Inaktiverad||
|[PowerShell-anslutning](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)|Inaktiverad|Inaktiverad|Tillgänglig för postlådeanvändare eller e-postanvändare (användarobjekt som returneras av Cmdlet en [get-användare).](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-user)|
|Använd Spoof Intelligence för att vitlista avsändare när det är möjligt|Ja|Ja||
|Katalogbaserad kantblockering (DBEB)|Aktiverat|Aktiverat|Domäntyp = Auktoritär|
|[Konfigurera multifaktorautentisering för alla administratörskonton](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication)|Aktiverat|Aktiverat||

## <a name="troubleshooting"></a>Felsökning

Felsöka allmänna problem och trender med hjälp av rapporterna i administrationscentret. Hitta enstaka punktspecifika data om ett meddelande med hjälp av meddelandespårningsverktyget. Läs mer om rapportering på [Rapportering och meddelandespårning i Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md). Läs mer om meddelandespårningsverktyget på [Meddelandespårning i Security & Compliance Center](message-trace-scc.md).

## <a name="reporting-false-positive-and-false-negatives-to-microsoft"></a>Rapportera falska positiva och falska negativ till Microsoft

Administratörer bör skicka falska negativ (spam) och falska positiva (icke-spam) till Microsoft via vår administratör inlagor portal. E-postmeddelanden, filer och webbadresser kan skickas in för att hjälpa administratörer att avgöra varför vi levererade eller inte levererade meddelanden till slutanvändare. Mer information finns i Så här skickar du [misstänkt skräppost, phish, webbadresser och filer till Microsoft för Office 365-skanning](admin-submission.md).

Slutanvändare kan också direkt rapportera falska negativ (spam) och falska positiva (icke-spam) till Microsoft för analys när de inte håller med domar som ges. Mer information finns i [Skicka in meddelanden om skräppost, icke-skräppost och nätfiske till Microsoft för analys](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).

## <a name="create-mail-flow-rules"></a>Skapa regler för e-postflöde

Skapa regler för e-postflöde eller anpassade filter för att uppfylla dina affärsbehov.

När du distribuerar en ny regel till produktion väljer du ett av testlägena först för att se regelns effekt. När du är övertygad om att regeln fungerar på det sätt som är avsett ändrar du regelläget för att **framtvinga**.

När du distribuerar nya regler bör du överväga att lägga till ytterligare åtgärd för **generera incidentrapport** för att övervaka regeln i aktion.

I hybridmiljöer där din organisation innehåller både lokalt Exchange och Office 365 bör du tänka på de villkor som du använder i regler för e-postflöde. Om du vill att reglerna ska gälla för hela organisationen måste du använda villkor som är tillgängliga i både lokalt Exchange och Office 365. Även om de flesta förhållanden är tillgängliga i båda miljöerna finns det några som bara är tillgängliga i en eller annan miljö. Läs mer på [Regler för e-postflöde (transportregler) i Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).
