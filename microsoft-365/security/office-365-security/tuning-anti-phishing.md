---
title: Justera skydd mot nätfiske i Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: Administratörer kan lära sig att identifiera orsakerna till och hur ett phishing-meddelande kom igenom och vad du kan göra för att förhindra fler nätfiskemeddelanden i framtiden.
ms.openlocfilehash: 94c28bf63ad7ba87d06298576cf7989b6848f8e6
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42812606"
---
# <a name="tune-anti-phishing-protection-in-office-365"></a>Justera skydd mot nätfiske i Office 365

Även om Office 365 levereras med en mängd olika anti-phishing-funktioner som är aktiverade som standard, är det möjligt att vissa nätfiskemeddelanden fortfarande kan nå fram till dina postlådor. I det här avsnittet beskrivs vad du kan göra för att upptäcka varför ett nätfiskemeddelande kom igenom och vad du kan göra för att justera inställningarna mot nätinät i din Exchange Online-organisation _utan att av misstag förvärra saker och ting._

## <a name="first-things-first-deal-with-any-compromised-accounts-and-make-sure-you-block-any-more-phishing-messages-from-getting-through"></a>Första saker först: ta itu med alla komprometterade konton och se till att du blockerar fler phishing-meddelanden från att komma igenom

Om en mottagares konto komprometterades som ett resultat av nätfiskemeddelandet följer du stegen i [Svara på ett komprometterat e-postkonto i Office 365](responding-to-a-compromised-email-account.md).

Om din prenumeration innehåller Ett avancerat hotskydd (ATP) kan du använda [Office 365 Threat Intelligence](office-365-ti.md) för att identifiera andra användare som också har fått nätfiskemeddelandet. Du har ytterligare alternativ för att blockera nätfiskemeddelanden:

- [ATP-säkra länkar](set-up-atp-safe-links-policies.md)

- [ATP-säkra tillbehör](set-up-atp-safe-attachments-policies.md)

- [ATP-policyer för bekämpning av nätfiske](set-up-anti-phishing-policies.md). Observera att du tillfälligt kan öka **de avancerade nätfiskets tröskelvärden** i principen från **Standard** till **Aggressiv,** **Mer aggressiv**eller Mest **aggressiv**.

Kontrollera att dessa ATP-funktioner är aktiverade.

## <a name="report-the-phishing-message-to-microsoft"></a>Rapportera nätfiskemeddelandet till Microsoft

Det är bra att rapportera nätfiskemeddelanden när du justerar de filter som används för att skydda alla kunder i Office 365.

Skicka nätfiskemeddelandet _som en bifogad fil_ i ett nytt, annars tomt meddelande för att **phish@office365.microsoft.com**. Vidarebefordra inte bara det ursprungliga meddelandet. Annars kan vi inte undersöka de ursprungliga meddelanderubrikerna. Du kan också använda tillägget [Rapportmeddelande](https://docs.microsoft.com/office365/securitycompliance/enable-the-report-message-add-in) i Outlook eller Outlook på webben (tidigare känt som Outlook Web App).

Mer information finns i [Skicka meddelanden om skräppost, icke-skräppost och nätfisketill Microsoft för analys](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).

## <a name="inspect-the-message-headers"></a>Granska meddelanderubrikerna

Du kan undersöka rubrikerna i nätfiskemeddelandet för att se om det finns något som du kan göra själv för att förhindra att fler nätfiskemeddelanden kommer igenom. Med andra ord kan du med andra ord identifiera alla inställningar i organisationen som var ansvariga för att tillåta nätfiskemeddelanden.

Specifikt bör du kontrollera fältet **X-Forefront-Antispam-Report** i meddelanderubrikerna för indikationer på överhoppad skräppost eller phish-filtrering i sfv-värdet (Spam Filtering Verdict). Meddelanden som hoppar över filtrering kommer `SCL:-1`att ha en post på , vilket innebär en av dina inställningar tillåts detta meddelande genom att åsidosätta spam eller phish domar som bestämdes av tjänsten. Mer information om hur du får meddelanderubriker och en fullständig lista över alla tillgängliga anti-spam- och anti-phish-meddelanderubriker finns i [Anti-spam-meddelanderubriker](https://docs.microsoft.com/office365/SecurityCompliance/anti-spam-message-headers).

## <a name="best-practices-to-stay-protected"></a>Metodtips för att skydda

- På månadsbasis kör du [Secure Score](../mtp/microsoft-secure-score.md) för att bedöma din Office 365-organisations säkerhetsinställningar.

- Granska regelbundet [rapporten Spoof intelligence](learn-about-spoof-intelligence.md) och aktivera skydd mot förfalskning i [anti-phishing-principen](learn-about-spoof-intelligence.md#configuring-the-anti-spoofing-policy) för att **karantän** misstänkta meddelanden i stället för att leverera dem till användarens skräppostmapp.

- Granska regelbundet [rapporten Statusför hotskydd](view-reports-for-atp.md#threat-protection-status-report).

- Vissa kunder tillåter oavsiktligt nätfiskemeddelanden genom att placera sina egna domäner i listan Tillåt avsändare eller Tillåt i anti-spam-principer. Om du väljer att göra detta måste du vara mycket försiktig. Även om den här konfigurationen tillåter vissa legitima meddelanden igenom, kommer det också att tillåta skadliga meddelanden som normalt skulle blockeras av Office 365 spam och / eller phish filter.

  Det bästa sättet att hantera legitima meddelanden som blockeras av Office 365 (falska positiva) som involverar avsändare i domänen är att helt och hållet konfigurera SPF-, DKIM- och DMARC-posterna i DNS för _alla_ dina e-postdomäner i Office 365:

  - Kontrollera att din SPF-post identifierar _alla_ källor till e-post för avsändare i domänen (glöm inte tjänster från tredje part!).

  - Använd hårda\-fel () för att säkerställa att obehöriga avsändare avvisas av e-postsystem som är konfigurerade för att göra det. Du kan använda [falska information](https://docs.microsoft.com/office365/securitycompliance/learn-about-spoof-intelligence) för att identifiera avsändare som använder domänen så att du kan inkludera auktoriserade avsändare från tredje part i SPF-posten.

  Instruktioner för konfigurationsinstruktioner finns i:
  
  - [Konfigurera SPF i Office 365 för att förhindra förfalskning](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  - [Använda DKIM för att validera utgående e-post som skickas från din anpassade domän i Office 365](use-dkim-to-validate-outbound-email.md)

  - [Använda DMARC för att validera e-post i Office 365](use-dmarc-to-validate-email.md)

- När det är möjligt rekommenderar vi att du levererar e-post till din domän direkt till Office 365. Med andra ord pekar du mx-posten i Office 365-domänen till Office 365. Exchange Online Protection (EOP) kan ge det bästa skyddet för dina molnanvändare när deras e-post levereras direkt till Office 365. Om du måste använda ett e-posthygiensystem från tredje part framför EOP, se till att du har följt vägledningen [här](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-mail-flow-using-third-party-cloud).

- Multi faktor autentisering (MFA) är ett riktigt bra sätt att förhindra komprometterade konton. Du bör starkt överväga att aktivera MFA för alla dina användare. För en stegvis metod, börja med att aktivera MFA för dina mest känsliga användare (administratörer, chefer, etc.) innan du aktiverar MFA för alla. Instruktioner finns i [Konfigurera multifaktorautentisering](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication).

- Vidarebefordring av regler till externa mottagare används ofta av angripare för att extrahera data. Använd information om vidarebefordran av **granskningspostlådan** i [Microsoft Secure Score](../mtp/microsoft-secure-score.md) för att hitta och till och med förhindra vidarebefordran av regler till externa mottagare. Mer information finns i [Förmildrande regler](https://blogs.technet.microsoft.com/office365security/mitigating-client-external-forwarding-rules-with-secure-score/)för extern vidarebefordran av klient med säker poäng .
