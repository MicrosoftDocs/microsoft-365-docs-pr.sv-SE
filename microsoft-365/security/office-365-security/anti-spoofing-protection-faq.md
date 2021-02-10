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
ms.openlocfilehash: 2d0805b5ca9e951234679ed8b3d03b6bdfced2be
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/10/2021
ms.locfileid: "50175901"
---
# <a name="anti-spoofing-protection-faq"></a>Vanliga frågor och svar om skydd mot förfalskning

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Den här artikeln innehåller vanliga frågor och svar om skydd mot förfalskning för Microsoft 365-organisationer med postlådor i Exchange Online eller fristående Exchange Online Protection-organisationer (EOP) utan Exchange Online-postlådor.

Frågor och svar om skydd mot skräppost finns i Vanliga frågor och svar om skydd mot [skräppost.](anti-spam-protection-faq.md)

Frågor och svar om skydd mot skadlig programvara finns i Vanliga frågor och svar om skydd [mot skadlig programvara](anti-malware-protection-faq-eop.md)

## <a name="why-did-microsoft-choose-to-junk-unauthenticated-inbound-email"></a>Varför valde Microsoft att skräppost av oautisk inkommande e-post?

Microsoft anser att risken för att fortsätta tillåta oauticerad inkommande e-post är högre än risken för att legitima inkommande e-postmeddelanden förloras.

## <a name="does-junking-unauthenticated-inbound-email-cause-legitimate-email-to-be-marked-as-spam"></a>Leder skräppost oautisk inkommande e-post till att legitim e-post markeras som skräppost?

När Microsoft aktiverade den här funktionen 2018 har vissa felaktiga positiva resultat inträffat (bra meddelanden markerades som dåliga). Men med tiden har avsändarna anpassat sig efter kraven. Antalet meddelanden som blev felidentifierade som falska blev tillgängliga för de flesta e-postsökvägar.

Microsoft införde först de nya autentiseringskraven för e-post flera veckor innan de distribuerade till kunder. I början förekom störningar men de minskade gradvis.

## <a name="is-spoof-intelligence-available-to-microsoft-365-customers-without-defender-for-office-365"></a>Är förfalskningsinformation tillgänglig för Microsoft 365-kunder utan Defender för Office 365?

Ja. Från och med oktober 2018 är förfalskningsinformation tillgänglig för alla organisationer med postlådor i Exchange Online och fristående EOP-organisationer utan Exchange Online-postlådor.

## <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a>Hur kan jag rapportera spam eller inte spam-meddelanden tillbaka till Microsoft?

Se [Anmäla meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="im-an-admin-and-i-dont-know-all-of-sources-for-messages-in-my-email-domain"></a>Jag är administratör och jag känner inte till alla källor för meddelanden i min e-postdomän!

Se [att du inte känner till alla källor för din e-post.](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email)

## <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization"></a>Vad händer om jag inaktiverar skydd mot förfalskning för min organisation?

Vi rekommenderar inte att du inaktiverar förfalskningsskydd. Om du inaktiverar skyddet kan fler nätfiske- och skräppostmeddelanden levereras i organisationen. Nätfiske är inte alla förfalskningsmeddelanden och du kommer inte att missa alla falska meddelanden. Din risk är dock högre.

Nu när Utökad filtrering för kopplingar är tillgänglig rekommenderar vi inte längre att skydd mot förfalskning inaktiveras när din e-post [dirigeras](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) genom en annan tjänst innan EOP.

## <a name="does-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a>Innebär skydd mot förfalskning att jag skyddas från all nätfiske?

Nej, tyvärr inte. Attackerare kommer att anpassa sig till andra tekniker (till exempel komprometterade konton eller konton i kostnadsfria e-posttjänster). Skydd mot nätfiske fungerar dock mycket bättre för att identifiera andra typer av nätfiskemetoder. Skyddslageren i EOP är utformade så att de fungerar tillsammans och bygger på varandra.

## <a name="do-other-large-email-services-block-unauthenticated-inbound-email"></a>Blockerar andra stora e-posttjänster oauticerad inkommande e-post?

Nästan alla stora e-posttjänster implementerar traditionella SPF-, DKIM- och DMARC-kontroller. Vissa tjänster har andra, striktare kontroller, men det är få som går så långt som EOP för att blockera oautisk e-post och behandla dem som falska meddelanden. Men branschen börjar bli mer medvetna om problem med oauticerad e-post, särskilt på grund av problemet med nätfiske.

## <a name="do-i-still-need-to-enable-the-advanced-spam-filter-setting-spf-record-hard-fail-_markasspamspfrecordhardfail_-if-i-enable-anti-spoofing"></a>Måste jag fortfarande aktivera inställningen Advanced Spam Filter (SPF-post: Hard Fail)_(MarkAsSpamSpfRecordHardFail)_ om jag aktiverar förfalskningskydd?

Nej. Den här ASF-inställningen är inte längre obligatorisk. Skydd mot förfalskning tar hänsyn till både SPF-fel och en mycket bredare uppsättning kriterier. Om du har aktiverat skydd mot förfalskning och **SPF-post: Hard Fail** (_MarkAsSpamSpfRecordHardFail_) aktiverad kommer du antagligen att få mer falska positiva identifieringar.

Vi rekommenderar att du inaktiverar den här funktionen eftersom den i princip inte ger några ytterligare fördelar när det gäller identifiering av skräppost eller nätfiske, och i stället generera huvudsakligen falska positiva identifieringar. Mer information finns i avancerade [inställningar för skräppostfilter (ASF) i EOP.](advanced-spam-filtering-asf-options.md)

## <a name="does-sender-rewriting-scheme-help-fix-forwarded-email"></a>Kan vidarebefordrad e-post åtgärdas med hjälp av avsändarschemat?

SRS korrigerar bara delvis problemet med vidarebefordrad e-post. Genom att skriva om SMTP **MAIL FROM** kan SRS säkerställa att det vidarebefordrade meddelandet skickar SPF till nästa mål. Men eftersom antiförfalskning baseras på från-adressen i kombination med **MAIL FROM-** eller DKIM-signeringsdomänen (eller andra signaler), räcker det inte med att förhindra att vidarebefordrad SRS-e-post markeras som förfalskning. 
