---
title: Vanliga frågor och svar om skydd mot förfalskning
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Administratörer kan visa vanliga frågor och svar om skydd mot förfalskning i Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a5843ee7f791fbc2c37914194b153fdd05866d0a
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207003"
---
# <a name="anti-spoofing-protection-faq"></a>Vanliga frågor och svar om skydd mot förfalskning

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Den här artikeln innehåller vanliga frågor och svar om skydd mot förfalskning för Microsoft 365-organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor.

Frågor och svar om skydd mot skräppost finns i Vanliga frågor och [svar om skydd mot skräppost.](anti-spam-protection-faq.md)

Frågor och svar om skydd mot skadlig programvara finns i Vanliga frågor och [svar om skydd mot skadlig programvara](anti-malware-protection-faq-eop.md)

## <a name="why-did-microsoft-choose-to-junk-unauthenticated-inbound-email"></a>Varför valde Microsoft att skräppostavlyssa oauthticerad inkommande e-post?

Microsoft anser att risken för att fortsätta att tillåta oauthenticerad inkommande e-post är högre än risken för att förlora legitima inkommande e-postmeddelanden.

## <a name="does-junking-unauthenticated-inbound-email-cause-legitimate-email-to-be-marked-as-spam"></a>Leder skräppostmeddelanden som inte är behöriga till inkommande e-postmeddelanden till att legitimt e-postmeddelande markeras som skräppost?

När Microsoft aktiverade den här funktionen 2018 hände vissa falska positiva resultat (bra meddelanden markerades som dåliga). Med tiden har dock avsändarna anpassat sig efter kraven. Antalet meddelanden som blivit felidentifierade som förfalskade har blivit tillgängliga för de flesta e-postsökvägar.

Microsoft använder sig först av de nya autentiseringskraven för e-post flera veckor innan de distribuerar dem till kunder. I början förekom störningar men de minskade gradvis.

## <a name="is-spoof-intelligence-available-to-microsoft-365-customers-without-defender-for-office-365"></a>Är förfalskningsinformation tillgänglig för Microsoft 365-kunder utan Defender för Office 365?

Ja. Från och med oktober 2018 är förfalskningsinformation tillgänglig för alla organisationer med postlådor i Exchange Online och fristående EOP-organisationer utan Exchange Online-postlådor.

## <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a>Hur kan jag rapportera spam eller inte spam-meddelanden tillbaka till Microsoft?

Se [Anmäla meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="im-an-admin-and-i-dont-know-all-of-sources-for-messages-in-my-email-domain"></a>Jag är administratör och känner inte till alla källor för meddelanden i min e-postdomän!

Mer [information finns i Du känner inte till alla källor för din e-post.](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email)

## <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization"></a>Vad händer om jag inaktiverar skydd mot förfalskning för min organisation?

Vi rekommenderar inte att du inaktiverar skydd mot förfalskning. Om du inaktiverar skyddet kan fler nätfiske- och skräppostmeddelanden levereras i organisationen. Inte alla nätfiskemeddelanden är förfalskning och inte alla falska meddelanden missas. Din risk är dock högre.

Nu när utökad filtrering för kopplingar är tillgänglig rekommenderar vi inte längre att skydd mot förfalskning inaktiveras när din e-post [dirigeras](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) via en annan tjänst före EOP.

## <a name="does-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a>Innebär skydd mot förfalskning att jag är skyddad från all nätfiske?

Nej, tyvärr inte. Attackerare kommer att anpassa sig till andra tekniker (till exempel komprometterade konton eller konton i gratis e-posttjänster). Skydd mot nätfiske fungerar dock mycket bättre för att identifiera andra typer av nätfiskemetoder. Skyddslageren i EOP är utformade för att fungera tillsammans och bygga på varandra.

## <a name="do-other-large-email-services-block-unauthenticated-inbound-email"></a>Blockerar andra stora e-posttjänster oauthticerad inkommande e-post?

Nästan alla stora e-posttjänster implementerar traditionella SPF-, DKIM- och DMARC-kontroller. Vissa tjänster har andra, striktare kontroller, men det är få som går så långt som EOP för att blockera oauthticerad e-post och behandla dem som falska meddelanden. Men branschen börjar bli mer medveten om problem med oauthenticerad e-post, särskilt på grund av problemet med nätfiske.

## <a name="do-i-still-need-to-enable-the-advanced-spam-filter-setting-spf-record-hard-fail-_markasspamspfrecordhardfail_-if-i-enable-anti-spoofing"></a>Måste jag fortfarande aktivera inställningen För avancerat skräppostfilter med SPF-post: hard fail (_MarkAsSpamSpfRecordHardFail)_ om jag aktiverar skydd mot förfalskning?

Nej. Den här ASF-inställningen är inte längre obligatorisk. Skydd mot förfalskning tar hänsyn till både SPF-hårda misslyckades och en mycket bredare uppsättning villkor. Om du har aktiverat skydd mot förfalskning och **SPF-post: Hard Fail** (_MarkAsSpamSpfRecordHardFail_) aktiverad kommer du antagligen att få mer falska positiva identifieringar.

Vi rekommenderar att du inaktiverar den här funktionen eftersom den nästan inte ger några fler fördelar med att identifiera skräppost och nätfiske, och i stället generera huvudsakligen falska positiva identifieringar. Mer information finns i Avancerade [inställningar för skräppostfilter (ASF) i EOP.](advanced-spam-filtering-asf-options.md)

## <a name="does-sender-rewriting-scheme-help-fix-forwarded-email"></a>Hjälper Sender Rewriting Scheme till att korrigera vidarebefordrad e-post?

SRS korrigerar bara delvis problemet med vidarebefordrad e-post. Genom att skriva om **SMTP-E-POST FRÅN** kan SRS säkerställa att det vidarebefordrade meddelandet skickar SPF vid nästa mål. Eftersom skydd mot förfalskning emellertid baseras  på Från-adressen i kombination med **MAIL FROM-** eller DKIM-signeringsdomänen (eller andra signaler), räcker det inte för att förhindra att vidarebefordrad SRS-e-post markeras som förfalskning.