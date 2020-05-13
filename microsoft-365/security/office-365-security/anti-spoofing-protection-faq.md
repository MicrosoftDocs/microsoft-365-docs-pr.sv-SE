---
title: Skydd mot förfalskning frågor och svar
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
description: Administratörer kan visa vanliga frågor och svar om anti-förfalskningsskydd i Exchange Online Protection (EOP).
ms.openlocfilehash: 603293dd00100e3b93a225d94f2ed8fd9baae6a5
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209101"
---
# <a name="anti-spoofing-protection-faq"></a>Skydd mot förfalskning frågor och svar

Det här avsnittet innehåller vanliga frågor och svar om anti-förfalskningsskydd för Microsoft 365-organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor.

Frågor och svar om skydd mot skräppost finns i [Vanliga frågor om skydd mot skräppost](anti-spam-protection-faq.md).

Frågor och svar om skydd mot skadlig kod finns i [Vanliga frågor om skydd mot skadlig kod](anti-malware-protection-faq-eop.md)

## <a name="why-did-microsoft-choose-to-junk-unauthenticated-inbound-email"></a>Varför valde Microsoft att skräpa upp oautentiserade inkommande e-post?

På grund av effekterna av nätfiskeattacker, och eftersom e-postautentisering har funnits i över 15 år, anser Microsoft att risken för att fortsätta att tillåta oautentiserade inkommande e-post är högre än risken att förlora legitim inkommande e-post.

## <a name="does-junking-unauthenticated-inbound-email-cause-legitimate-email-to-be-marked-as-spam"></a>Har skräp oautentiserade inkommande e-post orsaka legitima e-post som skall markeras som spam?

När Microsoft aktiverade den här funktionen under 2018 hände vissa falska positiva identifieringar (bra meddelanden markerades som dåliga). Med tiden blev dock avsändare anpassade till de nya kraven för avsändandeautentisering och antalet meddelanden som felaktigt identifierades som falska försumbara för de flesta e-postsökvägar.

Microsoft själv antog först de nya kraven för e-postautentisering flera veckor innan de distribuerade den till kunder. I början förekom störningar men de minskade gradvis.

## <a name="is-spoof-intelligence-available-to-microsoft-365-customers-without-atp"></a>Är falska underrättelser tillgängliga för Microsoft 365-kunder utan ATP?

Ja. Från och med oktober 2018 är falska underrättelser tillgängliga för alla organisationer med postlådor i Exchange Online och fristående EOP-organisationer utan Exchange Online-postlådor.

Anti-spoofing-teknik distribuerades ursprungligen endast till organisationer som hade Office 365 Enterprise E5-prenumerationer eller Office 365 Advanced Threat Protection (Office 365 ATP) för sin prenumeration.

## <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a>Hur kan jag rapportera spam eller inte spam-meddelanden tillbaka till Microsoft?

Se [Anmäla meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="im-an-admin-and-i-dont-know-all-of-sources-for-messages-in-my-email-domain"></a>Jag är administratör och jag vet inte alla källor för meddelanden i min e-domän!

Se [Du vet inte alla källor för din e-post](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email).

## <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization"></a>Vad händer om jag inaktiverar förfalskningsskydd för min organisation?

Vi rekommenderar inte detta eftersom du exponeras för fler missade nätfiske- och skräppostmeddelanden. Allt nätfiske är inte förfalskningar och alla förfalskningar missas inte. Men du löper högre risk än en kund som aktiverar förfalskningsskydd.

Nu när [förbättrad filtrering för anslutningar](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) är tillgängligt rekommenderar vi inte längre att du stänger av förfalskningsskydd om MX-posten pekar på en annan server eller tjänst innan du levererar e-post till EOP.

## <a name="does-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a>Betyder anti-spoofing skydd att jag kommer att skyddas från alla nätfiske?

Tyvärr, nej. Angripare anpassar sig för att använda andra tekniker (till exempel komprometterade konton eller konton i kostnadsfria e-posttjänster). Skydd mot nätfiske fungerar dock mycket bättre för att upptäcka dessa andra typer av nätfiskemetoder. Skyddslagren i EOP är utformade fungerar tillsammans och bygger ovanpå varandra.

## <a name="do-other-large-email-services-block-unauthenticated-inbound-email"></a>Blockerar andra stora e-posttjänster oautentiserade inkommande e-post?

Nästan alla stora e-posttjänster implementerar traditionella SPF-, DKIM- och DMARC-kontroller. Vissa tjänster har andra, striktare kontroller, men få går så långt som EOP för att blockera oautentiserade e-post och behandla dem som falska meddelanden. Branschen blir dock mer medveten om problem med oautentiserade e-postmeddelanden, särskilt på grund av problemet med nätfiske.

## <a name="do-i-still-need-to-enable-the-advanced-spam-filter-setting-spf-record-hard-fail-_markasspamspfrecordhardfail_-if-i-enable-anti-spoofing"></a>Måste jag fortfarande aktivera den avancerade spam filter inställningen "SPF post: hard fail"_(MarkAsSpamSpfRecordHardFail)_ om jag aktiverar anti-spoofing?

Nej. Denna ASF-inställning behövs inte längre eftersom anti-spoofing inte bara anser SPF hårt misslyckas, men en mycket bredare uppsättning kriterier. Om du har aktiverat skydd mot förfalskning och **SPF-post: Hard Fail** (_MarkAsSpamSpfRecordHardFail_) aktiverad kommer du antagligen att få mer falska positiva identifieringar.

Vi rekommenderar att du inaktiverar den här funktionen eftersom den nästan inte ger någon ytterligare fördel för att upptäcka skräppost eller nätfiskemeddelanden, och i stället skulle generera mestadels falska positiva identifieringar. Mer information finns i [ASF-inställningar (Advanced Spam Filter) i EOP](advanced-spam-filtering-asf-options.md).

## <a name="does-sender-rewriting-scheme-help-fix-forwarded-email"></a>Hjälper Sender Rewriting Scheme till att åtgärda vidarebefordrad e-post?

SRS korrigerar bara delvis problemet med vidarebefordrad e-post. Genom att skriva om SMTP **MAIL FRÅN**kan SRS se till att det vidarebefordrade meddelandet passerar SPF vid nästa mål. Men eftersom anti-spoofing baseras på **Från-adressen** i kombination med domänen **MAIL FROM** eller DKIM-signering (eller andra signaler), räcker det inte att förhindra att SRS vidarebefordrade e-post markeras som förfalskad.
