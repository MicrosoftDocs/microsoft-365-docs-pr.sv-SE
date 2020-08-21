---
title: Skydd mot förfalskning frågor och svar
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Administratörer kan se vanliga frågor och svar om skydd mot förfalskning i Exchange Online Protection (EOP).
ms.openlocfilehash: 66dbedaf638154c4a35359a4e5bc66c326c04d1e
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826679"
---
# <a name="anti-spoofing-protection-faq"></a>Skydd mot förfalskning frågor och svar

Det här avsnittet innehåller vanliga frågor och svar om skydd mot förfalskning för Microsoft 365-organisationer med post lådor i Exchange Online eller fristående organisationer för Exchange Online Protection (EOP) utan Exchange Online-postlådor.

Frågor och svar om skydd mot skräp post finns i [vanliga frågor om skydd mot skräp post](anti-spam-protection-faq.md).

Frågor och svar om skydd mot skadlig program vara finns i [vanliga frågor om skydd mot skadlig program vara](anti-malware-protection-faq-eop.md)

## <a name="why-did-microsoft-choose-to-junk-unauthenticated-inbound-email"></a>Varför väljer Microsoft att skicka skräp post som inte verifierats som overifierat?

På grund av nät fiske attackerens påverkan, och eftersom e-postautentisering har varit nära över 15 år, anser Microsoft att risken att fortsätta tillåta overifierad inkommande e-post är högre än risken att du förlorar legitim inkommande e-post.

## <a name="does-junking-unauthenticated-inbound-email-cause-legitimate-email-to-be-marked-as-spam"></a>Orsakar skräp post av oautentiserad e-post att legitim e-post markeras som skräp post?

När Microsoft aktiverade den här funktionen i 2018 skedde vissa falska positiva (goda meddelanden). Men över tiden har avsändarna justerats efter de nya kraven för avsändare och antalet meddelanden som identifierats som falsk är försumbart för de flesta e-postsök vägar.

Microsoft antog först de nya e-postautentiseringskravna flera veckor innan de distribueras till kunderna. I början förekom störningar men de minskade gradvis.

## <a name="is-spoof-intelligence-available-to-microsoft-365-customers-without-atp"></a>Är Spoof-intelligens tillgänglig för Microsoft 365-kunder utan ATP?

Ja. Från och med oktober 2018 är Spoof-intelligens tillgänglig för alla organisationer med post lådor i Exchange Online och fristående EOP-organisationer utan Exchange Online-postlådor.

Skydd mot dataförfalskning distribuerades ursprungligen endast till organisationer som hade Office 365 Enterprise, E5-prenumerationer eller Office 365 Advanced Threat Protection-tilläggsprogrammet (Office 365 ATP) för deras abonnemang.

## <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a>Hur kan jag rapportera spam eller inte spam-meddelanden tillbaka till Microsoft?

Se [Anmäla meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="im-an-admin-and-i-dont-know-all-of-sources-for-messages-in-my-email-domain"></a>Jag är administratör och jag känner inte till alla källor för meddelanden i min e-post-domän!

Se [att du inte känner till alla källor för din e-post](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email).

## <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization"></a>Vad händer om jag inaktiverar skydd mot förfalskning för min organisation?

Vi rekommenderar inte detta eftersom du exponeras för fler missade nätfiske- och skräppostmeddelanden. Allt nätfiske är inte förfalskningar och alla förfalskningar missas inte. Men du löper högre risk än en kund som aktiverar förfalskningsskydd.

Nu när det finns [förbättrade filter för kopplingar](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) är det inte längre möjligt att inaktivera skydd mot förfalskning om din MX-post pekar på en annan server eller tjänst innan du skickar e-post till EOP.

## <a name="does-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a>Innebär skydd mot förfalskning att jag skyddas från alla nätfiske?

Tyvärr, nej. Angripare anpassas till Använd annan teknik (till exempel äventyrade konton eller konton i gratis e-posttjänster). Skydd mot nätfiske fungerar dock bättre för att upptäcka dessa andra typer av nät fiske metoder. Skydds lagren i EOP är utformade för att fungera tillsammans och bygga ovanpå varandra.

## <a name="do-other-large-email-services-block-unauthenticated-inbound-email"></a>Blockerar andra stora e-posttjänster oautentiserad e-post?

Nästan alla stora e-posttjänster implementerar traditionella SPF-, DKIM-och DMARC-kontroller. Vissa tjänster har andra, mer strikta kontroller, men få lika mycket som EOP för att blockera overifierad e-post och behandla dem som falska meddelanden. Men industrin blir mer medveten om problem med overifierad e-post, särskilt på grund av problemet med nätfiske.

## <a name="do-i-still-need-to-enable-the-advanced-spam-filter-setting-spf-record-hard-fail-_markasspamspfrecordhardfail_-if-i-enable-anti-spoofing"></a>Måste jag ändå aktivera avancerade inställningar för skräp post filtret "SPF record: hårda fail" (_MarkAsSpamSpfRecordHardFail_) om jag aktiverar mot förfalskning?

Nej. Den här ASF-inställningen är inte längre nödvändig eftersom anti-förfalskning inte bara tar till SPF-hårda fel, men en mycket större uppsättning villkor. Om du har aktiverat skydd mot förfalskning och **SPF-post: Hard Fail** (_MarkAsSpamSpfRecordHardFail_) aktiverad kommer du antagligen att få mer falska positiva identifieringar.

Vi rekommenderar att du inaktiverar den här funktionen eftersom den inte har någon ytterligare förmån för att upptäcka skräp post eller nätfiske och skulle i stället generera mest falska positiva positiv. Mer information finns i [Avancerade inställningar för skräp post filter (ASF) i EOP](advanced-spam-filtering-asf-options.md).

## <a name="does-sender-rewriting-scheme-help-fix-forwarded-email"></a>Hjälper avsändarens schema att åtgärda vidarebefordrade e-postmeddelanden?

SRS korrigerar bara delvis problemet med vidarebefordrad e-post. Genom att skriva om SMTP **-e-post från**kan SRS säkerställa att det vidarebefordrade meddelandet skickar SPF vid nästa destination. Eftersom anti-förfalskning är baserat på **från** -adressen i kombination med **e-post från** eller DKIM (eller andra signaler) är det emellertid inte tillräckligt för att förhindra att e-post med SRS-meddelanden markeras som falsk.
