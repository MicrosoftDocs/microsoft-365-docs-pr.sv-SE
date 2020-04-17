---
title: Vanliga frågor om skydd mot förfalskning
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
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Vanliga frågor och svar för administratörer om anti-förfalskningsskydd i Exchange Online och fristående Exchange Online Protection (EOP).
ms.openlocfilehash: b39e48fd57b899e6296d40ab10aac265cb4165a3
ms.sourcegitcommit: 9ed3283dd6dd959faeca5c22613f9126261b9590
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2020
ms.locfileid: "43529893"
---
# <a name="anti-spoofing-protection-faq-in-office-365"></a>Vanliga frågor om skydd mot förfalskning i Office 365

Det här avsnittet innehåller vanliga frågor och svar om anti-förfalskningsskydd för Office 365-kunder med postlådor i Exchange Online eller fristående Exchange Online Protection (EOP) kunder utan Exchange Online-postlådor.

Frågor och svar om skydd mot skräppost finns i [Vanliga frågor om skydd mot skräppost](anti-spam-protection-faq.md).

Frågor och svar om skydd mot skadlig kod finns [i Vanliga frågor om skydd mot skadlig kod i Office 365](anti-malware-protection-faq-eop.md)

## <a name="why-did-microsoft-choose-to-junk-unauthenticated-inbound-email"></a>Varför valde Microsoft att skräpa upp oautentiserade inkommande e-post?

På grund av effekterna av nätfiskeattacker, och eftersom e-postautentisering har funnits i över 15 år, anser Microsoft att risken för att fortsätta att tillåta oautentiserade inkommande e-post är högre än risken att förlora legitim inkommande e-post.

## <a name="does-junking-unauthenticated-inbound-email-cause-legitimate-email-to-be-marked-as-spam"></a>Har skräp oautentiserade inkommande e-post orsaka legitima e-post som skall markeras som spam?

När Microsoft aktiverade den här funktionen under 2018 hände vissa falska positiva identifieringar (bra meddelanden markerades som dåliga). Med tiden blev dock avsändare anpassade till de nya kraven för avsändandeautentisering och antalet meddelanden som felaktigt identifierades som falska försumbara för de flesta e-postsökvägar.

Microsoft själv antog först de nya kraven för e-postautentisering flera veckor innan de distribuerade den till kunder. I början förekom störningar men de minskade gradvis.

## <a name="is-spoof-intelligence-available-to-office-365-customers-without-atp"></a>Är falska underrättelser tillgängliga för Office 365-kunder utan ATP?

Ja. Från och med oktober 2018 är falska underrättelser tillgängliga för alla organisationer med Exchange Online-postlådor och fristående EOP-organisationer utan Exchange Online-postlådor.

Anti-spoofing-teknik distribuerades ursprungligen till organisationer som hade Office 365 Enterprise E5-prenumerationer eller Office 365 Advanced Threat Protection (ATP) för sin prenumeration.

## <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a>Hur kan jag rapportera spam eller inte spam-meddelanden tillbaka till Microsoft?

Se [Anmäla meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="im-an-admin-and-i-dont-know-all-of-sources-for-messages-in-my-email-domain"></a>Jag är administratör och jag vet inte alla källor för meddelanden i min e-domän!

Se [Du vet inte alla källor för din e-post](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email).

## <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization"></a>Vad händer om jag inaktiverar förfalskningsskydd för min organisation?

Vi rekommenderar inte detta eftersom du exponeras för fler missade nätfiske- och skräppostmeddelanden. Allt nätfiske är inte förfalskningar och alla förfalskningar missas inte. Men du löper högre risk än en kund som aktiverar förfalskningsskydd.

Nu när [förbättrad filtrering för anslutningar](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) är tillgängligt rekommenderar vi inte längre att du stänger av förfalskningsskydd om MX-posten pekar på en annan server eller tjänst innan du levererar e-post till EOP.

## <a name="does-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a>Betyder anti-spoofing skydd att jag kommer att skyddas från alla nätfiske?

Tyvärr, nej. Angripare anpassar sig för att använda andra tekniker (till exempel komprometterade konton eller konton i kostnadsfria e-posttjänster). Skydd mot nätfiske fungerar dock mycket bättre för att upptäcka dessa andra typer av nätfiskemetoder. Skyddslagren i Office 365 är utformade tillsammans och bygger ovanpå varandra.

## <a name="do-other-large-email-services-block-unauthenticated-inbound-email"></a>Blockerar andra stora e-posttjänster oautentiserade inkommande e-post?

Nästan alla stora e-posttjänster implementerar traditionella SPF-, DKIM- och DMARC-kontroller. Vissa tjänster har andra, striktare kontroller, men få går så långt som till Office 365 för att blockera oautentiserade e-postmeddelanden och behandla dem som falska meddelanden. Branschen blir dock mer medveten om problem med oautentiserade e-postmeddelanden, särskilt på grund av problemet med nätfiske.

## <a name="do-i-still-need-to-enable-the-advanced-spam-filter-setting-spf-record-hard-fail-_markasspamspfrecordhardfail_-if-i-enable-anti-spoofing"></a>Måste jag fortfarande aktivera den avancerade spam filter inställningen "SPF post: hard fail"_(MarkAsSpamSpfRecordHardFail)_ om jag aktiverar anti-spoofing?

Nej. Denna ASF-inställning behövs inte längre eftersom anti-spoofing inte bara anser SPF hårt misslyckas, men en mycket bredare uppsättning kriterier. Om du har aktiverat skydd mot förfalskning och **SPF-post: Hard Fail** (_MarkAsSpamSpfRecordHardFail_) aktiverad kommer du antagligen att få mer falska positiva identifieringar.

Vi rekommenderar att du inaktiverar den här funktionen eftersom den nästan inte ger någon ytterligare fördel för att upptäcka skräppost eller nätfiskemeddelanden, och i stället skulle generera mestadels falska positiva identifieringar. Mer information finns i [Inställningar för avancerat spamfilter (ASF) i Office 365](advanced-spam-filtering-asf-options.md).

## <a name="does-sender-rewriting-scheme-help-fix-forwarded-email"></a>Hjälper Sender Rewriting Scheme till att åtgärda vidarebefordrad e-post?

SRS korrigerar bara delvis problemet med vidarebefordrad e-post. Genom att skriva om SMTP **MAIL FRÅN**kan SRS se till att det vidarebefordrade meddelandet passerar SPF vid nästa mål. Men eftersom anti-spoofing baseras på **Från-adressen** i kombination med domänen **MAIL FROM** eller DKIM-signering (eller andra signaler), räcker det inte att förhindra att SRS vidarebefordrade e-post markeras som förfalskad.
