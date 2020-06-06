---
title: Finjustera skydd mot nätfiske
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
description: Administratörer kan lära sig att identifiera orsakerna till och hur ett nätfiskemeddelande kom fram i Microsoft 365 och vad de ska göra för att förhindra fler nätfiskemeddelanden i framtiden.
ms.openlocfilehash: b7a68eb3ab3cf7dbb7156059416cca04d80bb3a8
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/05/2020
ms.locfileid: "44588446"
---
# <a name="tune-anti-phishing-protection"></a>Finjustera skydd mot nätfiske

Även om Microsoft 365 levereras med en mängd olika funktioner mot nätfiske som är aktiverade som standard, är det möjligt att vissa nätfiskemeddelanden fortfarande kan komma fram till dina postlådor. I det här avsnittet beskrivs vad du kan göra för att ta reda på varför ett nätfiskemeddelande kom fram och vad du kan göra för att justera inställningarna mot nätfiske i din Microsoft 365-organisation utan att _göra det värre_.

## <a name="first-things-first-deal-with-any-compromised-accounts-and-make-sure-you-block-any-more-phishing-messages-from-getting-through"></a>Första saker först: ta itu med eventuella komprometterade konton och se till att du blockerar fler nätfiskemeddelanden från att komma igenom

Om en mottagares konto har komprometterats till följd av nätfiskemeddelandet följer du stegen i [Att svara på ett komprometterat e-postkonto i Microsoft 365](responding-to-a-compromised-email-account.md).

Om din prenumeration innehåller Atp (Advanced Threat Protection) kan du använda [Office 365 Threat Intelligence](office-365-ti.md) för att identifiera andra användare som också har fått nätfiskemeddelandet. Du har ytterligare alternativ för att blockera nätfiskemeddelanden:

- [Säkra ATP-länkar](set-up-atp-safe-links-policies.md)

- [ATP säkra bilagor](set-up-atp-safe-attachments-policies.md)

- [ATP:s principer för phishing-phishing i Microsoft 365](configure-atp-anti-phishing-policies.md). Observera att du tillfälligt kan öka **tröskelvärdena för avancerat nätfiske** i principen från **Standard** till **Aggressiv,** **Mer aggressiv**eller **Mest aggressiva**.

Kontrollera att dessa ATP-funktioner är aktiverade.

## <a name="report-the-phishing-message-to-microsoft"></a>Rapportera nätfiskemeddelandet till Microsoft

Att rapportera nätfiskemeddelanden är användbart för att justera de filter som används för att skydda alla kunder i Microsoft 365. Instruktioner finns i [Rapportera meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="inspect-the-message-headers"></a>Kontrollera meddelanderubrikerna

Du kan undersöka rubrikerna i nätfiskemeddelandet för att se om det finns något du kan göra själv för att förhindra att fler nätfiskemeddelanden kommer fram. Med andra ord kan granskningen av meddelandenrubrikerna hjälpa dig att identifiera alla inställningar i organisationen som var ansvariga för att tillåta nätfiskemeddelandena.

Specifikt bör du kontrollera fältet **X-Forefront-Antispam-Report-huvud** i meddelanderubrikerna för indikationer på överhoppad skräppost eller phish-filtrering i värdet För skräppostfiltrering (SFV). Meddelanden som hoppar över filtrering kommer att ha en post `SCL:-1` i , vilket innebär att en av dina inställningar tillåts detta meddelande genom att åsidosätta spam eller phish domar som bestämdes av tjänsten. Mer information om hur du får meddelanderubriker och en fullständig lista över alla tillgängliga rubriker mot skräppost och anti-phish finns [i Rubriker för skräppostmeddelanden i Microsoft 365](anti-spam-message-headers.md).

## <a name="best-practices-to-stay-protected"></a>Bästa praxis för att skydda

- Kör [Säkerhetspoäng](../mtp/microsoft-secure-score.md) varje månad för att bedöma organisationens säkerhetsinställningar.

- Granska regelbundet [spoof-intelligensrapporten](learn-about-spoof-intelligence.md) och [konfigurera falska underrättelser](set-up-anti-phishing-policies.md#spoof-settings) för att sätta misstänkta meddelanden i **karantän** i stället för att leverera dem till användarens skräppostmapp.

- Granska rapporten [Status för hotskydd](view-reports-for-atp.md#threat-protection-status-report)med jämna mellanrum .

- Vissa kunder tillåter oavsiktligt nätfiskemeddelanden genom att placera sina egna domäner i listan Tillåt avsändare eller Tillåt domän i policyer mot skräppost. Om du väljer att göra detta måste du vara mycket försiktig. Även om denna konfiguration kommer att tillåta vissa legitima meddelanden genom, kommer det också att tillåta skadliga meddelanden som normalt skulle blockeras av spam och / eller phish filter.

  Det bästa sättet att hantera legitima meddelanden som blockeras av Microsoft 365 (falskt positiva) som involverar avsändare i domänen är att helt och fullständigt konfigurera SPF-, DKIM- och DMARC-postposterna i DNS för _alla_ dina e-postdomäner:

  - Kontrollera att SPF-posten identifierar _alla_ e-postkällor för avsändare på domänen (glöm inte tjänster från tredje part!).

  - Använd hårddisken ( \- ) för att säkerställa att obehöriga avsändare avvisas av e-postsystem som är konfigurerade för att göra det. Du kan använda [falska underrättelser](learn-about-spoof-intelligence.md) för att identifiera avsändare som använder din domän så att du kan inkludera auktoriserade avsändare från tredje part i SPF-posten.

  Instruktioner för konfiguration finns i:
  
  - [Konfigurera SPF för att förhindra förfalskning](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  - [Använda DKIM för att validera utgående e-post som skickas från din anpassade domän](use-dkim-to-validate-outbound-email.md)

  - [Använda DMARC för att validera e-post](use-dmarc-to-validate-email.md)

- När det är möjligt rekommenderar vi att du levererar e-post till din domän direkt till Microsoft 365. Med andra ord, peka din Microsoft 365 domän MX post till Microsoft 365. Exchange Online Protection (EOP) kan ge det bästa skyddet för dina molnanvändare när deras e-post levereras direkt till Microsoft 365. Om du måste använda ett e-posthygiensystem från tredje part framför EOP använder du Förbättrad filtrering för kontakter. Instruktioner finns i [Förbättrad filtrering för anslutningsappar i Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

- Multifaktorautentisering (MFA) är ett bra sätt att förhindra komprometterade konton. Du bör starkt överväga att aktivera MFA för alla dina användare. För en stegvis metod, börja med att aktivera MFA för dina mest känsliga användare (administratörer, chefer, etc.) innan du aktiverar MFA för alla. Instruktioner finns i [Konfigurera multifaktorautentisering](../../admin/security-and-compliance/set-up-multi-factor-authentication.md).

- Vidarebefordringsregler till externa mottagare används ofta av angripare för att extrahera data. Använd informationen **om vidarebefordrade postlåda** i [Microsoft Secure Score](../mtp/microsoft-secure-score.md) för att hitta och till och med förhindra vidarekopplingsregler till externa mottagare. Mer information finns i [Förmildrande regler](https://docs.microsoft.com/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score)för extern vidarebefordran av klienter med säker poäng .
