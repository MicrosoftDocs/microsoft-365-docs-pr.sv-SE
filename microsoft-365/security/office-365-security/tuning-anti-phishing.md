---
title: Finjustera skydd mot nätfiske
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: Administratörer kan lära sig att identifiera varför och hur ett nät fiske meddelande gick igenom i Microsoft 365 och vad man bör göra för att förhindra fler nät fiske meddelanden i framtiden.
ms.openlocfilehash: c62d09a1cf8b586b5c1d4393d7316d6d6d0cc96d
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201681"
---
# <a name="tune-anti-phishing-protection"></a>Finjustera skydd mot nätfiske

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Ã ven om Microsoft 365 kommer med en mängd anti-nätfiske-funktioner som är aktiverade som standard, är det möjligt att vissa nät fiske meddelanden ändå kan komma fram till dina post lådor. I det här avsnittet beskrivs vad du kan göra för att ta reda på varför ett nät fiske meddelande hamnade och vad du kan göra för att justera inställningarna för nät fiske i din Microsoft 365-organisation _utan att göra saker ännu värre_.

## <a name="first-things-first-deal-with-any-compromised-accounts-and-make-sure-you-block-any-more-phishing-messages-from-getting-through"></a>Först: hantera alla kompromissade konton och kontrol lera att du blockerar fler nät fiske meddelanden från att komma igenom

Om en mottagares konto har komprometterats som ett resultat av nät fiske meddelandet följer du stegen i [svara på ett anslaget e-postkonto i Microsoft 365](responding-to-a-compromised-email-account.md).

Om ditt abonnemang inkluderar Avancerat skydd (ATP) kan du använda [Office 365 Threat Intelligence](office-365-ti.md) för att identifiera andra användare som också har tagit emot nät fiske meddelandet. Du har ytterligare alternativ för att blockera nät fiske meddelanden:

- [Säkra ATP-länkar](set-up-atp-safe-links-policies.md)

- [Säkra filer för ATP](set-up-atp-safe-attachments-policies.md)

- [ATP anti-phishing-principer i Microsoft 365](configure-atp-anti-phishing-policies.md). Observera att du kan tillfälligt öka de **avancerade nät fiske trösklarna** i principen från **standard** till **aggressivt**, **mer aggressivt**eller **de flesta aggressivt**.

Kontrol lera att dessa ATP-funktioner är aktiverade.

## <a name="report-the-phishing-message-to-microsoft"></a>Rapportera nät fiske meddelandet till Microsoft

Att rapportera nät fiske meddelanden är användbart när du vill justera filtren som används för att skydda alla kunder i Microsoft 365. Anvisningar finns i [rapportera meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="inspect-the-message-headers"></a>Kontrol lera meddelande rubrikerna

Du kan granska meddelande huvudena för nät fiske meddelandet för att se om det finns något du kan göra för att förhindra att fler nät fiske meddelanden kommer fram. Med andra ord kan du med hjälp av meddelande rubrikerna se vilka inställningar i organisationen som är ansvariga för att tillåta nät fiske meddelanden.

Om du vill kan du kontrol lera om fältet **X-antispam-rapport** huvud i meddelande rubrikerna inte har hoppat över skräp post eller PHISH i SFV-värdet. Meddelanden som hoppar över filtrering kommer att ha en inmatning `SCL:-1` , vilket innebär att en av dina inställningar tillåter det här meddelandet genom att åsidosätta skräp post eller Phish verdicts som bestämts av tjänsten. Mer information om hur du hämtar meddelande rubriker och en fullständig lista över alla tillgängliga skräp post-och Phish meddelande rubriker finns i [meddelande rubriker för skräp post i Microsoft 365](anti-spam-message-headers.md).

## <a name="best-practices-to-stay-protected"></a>Metod tips för att skydda dig

- Per månad kan du använda [säkert Poäng](../mtp/microsoft-secure-score.md) för att utvärdera organisationens säkerhets inställningar.

- För meddelanden som slutar med misstag eller för meddelanden som tillåts genom rekommenderar vi att du söker efter dessa meddelanden i [Threat Explorer och identifieringar i real tid](threat-explorer.md). Du kan söka efter avsändare, mottagare eller meddelande-ID. När du har hittat meddelandet går du till uppgifter genom att klicka på ämnet. Om du har ett meddelande i karantän kan du titta på "identifierings teknik", så att du kan använda lämplig metod för att åsidosätta. För ett tillåtet meddelande, se efter vilken princip som får meddelandet. 

- Falsk e-post är märkt som Phish i ATP. Ibland är falska förfalskningar ofarliga och ibland vill användarna inte att den ska placeras i karantän. Om du vill minimera effekten för användarna kan du regelbundet granska [förfalsknings intelligens-rapporten](learn-about-spoof-intelligence.md). När du har granskat och gjort nödvändiga åsidosättningar kan du vara säker på att [Konfigurera förfalsknings intelligens](set-up-anti-phishing-policies.md#spoof-settings) mot **Quarantine** -misstänkta meddelanden i stället för att skicka dem till användarens mapp för skräp post.

- Du kan upprepa ovanstående steg för personifiering (domän eller användare). Personifieringsnivå hittas under **Threat Management** \> **instrument panels** \> **insikter**för hot Management.

- Gå regelbundet igenom [status rapporten för hotet skydd](view-reports-for-atp.md#threat-protection-status-report).

- Vissa kunder oavsiktligt tillåter nät fiske meddelanden genom att lägga till sina egna domäner i listan Tillåt avsändare eller Tillåt domän i principer för skräp post. Även om den här konfigurationen tillåter vissa legitima meddelanden via, tillåter den också skadliga meddelanden som normalt skulle blockeras av skräp post och/eller Phish filtren. I stället för att tillåta domänen bör du korrigera det underliggande problemet.

  Det bästa sättet att hantera legitima meddelanden som blockeras av Microsoft 365 (falska positiva positivt) som involverar avsändare i din domän är att fullständigt och helt konfigurera SPF-, DKIM-och DMARC-posterna i DNS för _alla_ dina e-postdomäner:

  - Kontrol lera att din SPF-post identifierar _alla_ källor till e-post för avsändare i din domän (Glöm inte tjänster från tredje part).

  - Använd hårda fel ( \- alla) för att se till att obehöriga avsändare nekas via e-postsystem som är konfigurerade för detta. Du kan använda [falsk intelligens](learn-about-spoof-intelligence.md) för att identifiera avsändare som använder din domän så att du kan ta med auktoriserade tredjeparts avsändare i SPF-posten.

  Anvisningar för konfiguration finns i:
  
  - [Konfigurera SPF för att förhindra förfalskning](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  - [Använda DKIM för att validera utgående e-post som skickas från din anpassade domän](use-dkim-to-validate-outbound-email.md)

  - [Använda DMARC för att validera e-post](use-dmarc-to-validate-email.md)

- När det är möjligt rekommenderar vi att du skickar e-post till din domän direkt till Microsoft 365. Med andra ord pekar du din Microsoft 365-domäns MX-post till Microsoft 365. Exchange Online Protection (EOP) ger det bästa skyddet för dina moln användare när deras e-post levereras direkt till Microsoft 365. Om du måste använda ett system för e-posthygien från tredje part framför EOP kan du använda förbättrad filtrering för kopplingar. Anvisningar finns i [utökad filtrering för kopplingar i Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

- Användarna bör [rapportera meddelanden](enable-the-report-message-add-in.md) till Microsoft, vilket kan träna vårt system. Administratörer bör också utnyttja [administrativa](admin-submission.md) uppgifter.

- Multifaktorautentisering är ett bra sätt att förhindra att konton skadas. Du bör starkt överväga att aktivera MFA för alla dina användare. Börja med att aktivera MFA för dina mest känsliga användare (administratörer, chefer o.s.v.) innan du aktiverar MFA för alla. Anvisningar finns i [Konfigurera multifaktorautentisering](../../admin/security-and-compliance/set-up-multi-factor-authentication.md).

- Regler för vidarebefordran till externa mottagare används ofta av angripare för att extrahera data. Använd informationen i **avsnittet granska vidarebefordran av post lådor** i [Microsofts säkra Poäng](../mtp/microsoft-secure-score.md) för att hitta och till och med förhindra regler för vidarebefordran till externa mottagare. Mer information finns i [begränsa regler för extern vidarebefordring med klienter med säkra Poäng](https://docs.microsoft.com/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score).
