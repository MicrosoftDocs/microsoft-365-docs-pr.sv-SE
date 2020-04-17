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
description: Administratörer kan lära sig att identifiera orsakerna till och hur ett nätfiskemeddelande kom fram och vad de ska göra för att förhindra fler nätfiskemeddelanden i framtiden.
ms.openlocfilehash: 93fdc17379627a2d595a3861ae3f8f1f9dcefeeb
ms.sourcegitcommit: 9ed3283dd6dd959faeca5c22613f9126261b9590
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2020
ms.locfileid: "43528995"
---
# <a name="tune-anti-phishing-protection-in-office-365"></a>Justera skydd mot nätfiske i Office 365

Även om Office 365 levereras med en mängd olika funktioner mot nätfiske som är aktiverade som standard, är det möjligt att vissa nätfiskemeddelanden fortfarande kan komma fram till dina postlådor. I det här avsnittet beskrivs vad du kan göra för att ta reda på varför ett nätfiskemeddelande kom fram och vad du kan göra för att justera inställningarna mot nätfiske i Exchange Online-organisationen utan att _göra det värre_av misstag .

## <a name="first-things-first-deal-with-any-compromised-accounts-and-make-sure-you-block-any-more-phishing-messages-from-getting-through"></a>Första saker först: ta itu med eventuella komprometterade konton och se till att du blockerar fler nätfiskemeddelanden från att komma igenom

Om en mottagares konto har komprometterats till följd av nätfiskemeddelandet följer du stegen i [Att svara på ett komprometterat e-postkonto i Office 365](responding-to-a-compromised-email-account.md).

Om din prenumeration innehåller Atp (Advanced Threat Protection) kan du använda [Office 365 Threat Intelligence](office-365-ti.md) för att identifiera andra användare som också har fått nätfiskemeddelandet. Du har ytterligare alternativ för att blockera nätfiskemeddelanden:

- [ATP säkra länkar](set-up-atp-safe-links-policies.md)

- [ATP säkra bilagor](set-up-atp-safe-attachments-policies.md)

- [ATP:s principer för phishing-phishing i Office 365](configure-atp-anti-phishing-policies.md). Observera att du tillfälligt kan öka **tröskelvärdena för avancerat nätfiske** i principen från **Standard** till **Aggressiv,** **Mer aggressiv**eller **Mest aggressiva**.

Kontrollera att dessa ATP-funktioner är aktiverade.

## <a name="report-the-phishing-message-to-microsoft"></a>Rapportera nätfiskemeddelandet till Microsoft

Att rapportera nätfiskemeddelanden är användbart när du justerar de filter som används för att skydda alla kunder i Office 365. Instruktioner finns i [Rapportera meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="inspect-the-message-headers"></a>Kontrollera meddelanderubrikerna

Du kan undersöka rubrikerna i nätfiskemeddelandet för att se om det finns något du kan göra själv för att förhindra att fler nätfiskemeddelanden kommer fram. Med andra ord kan granskningen av meddelandenrubrikerna hjälpa dig att identifiera alla inställningar i organisationen som var ansvariga för att tillåta nätfiskemeddelandena.

Specifikt bör du kontrollera fältet **X-Forefront-Antispam-Report-huvud** i meddelanderubrikerna för indikationer på överhoppad skräppost eller phish-filtrering i värdet För skräppostfiltrering (SFV). Meddelanden som hoppar över filtrering `SCL:-1`kommer att ha en post i , vilket innebär att en av dina inställningar tillåts detta meddelande genom att åsidosätta spam eller phish domar som bestämdes av tjänsten. Mer information om hur du får meddelanderubriker och en fullständig lista över alla tillgängliga rubriker mot skräppost och anti-phish finns [i Rubriker för skräppostmeddelanden i Office 365](anti-spam-message-headers.md).

## <a name="best-practices-to-stay-protected"></a>Bästa praxis för att skydda

- Kör [Säkerhetspoäng](../mtp/microsoft-secure-score.md) varje månad för att bedöma office 365-organisationens säkerhetsinställningar.

- Granska regelbundet [spoof-intelligensrapporten](learn-about-spoof-intelligence.md) och [konfigurera falska underrättelser](set-up-anti-phishing-policies.md#spoof-settings) för att sätta misstänkta meddelanden i **karantän** i stället för att leverera dem till användarens skräppostmapp.

- Granska rapporten [Status för hotskydd](view-reports-for-atp.md#threat-protection-status-report)med jämna mellanrum .

- Vissa kunder tillåter oavsiktligt nätfiskemeddelanden genom att placera sina egna domäner i listorna Tillåten avsändare eller Tillåten domän i policyer mot skräppost. Om du väljer att göra detta måste du vara mycket försiktig. Även om den här konfigurationen tillåter vissa legitima meddelanden genom, kommer det också att tillåta skadliga meddelanden som normalt skulle blockeras av Office 365 spam och / eller phish filter.

  Det bästa sättet att hantera legitima meddelanden som blockeras av Office 365 (falskt positiva identifieringar) som involverar avsändare i domänen är att helt och fullständigt konfigurera SPF-, DKIM- och DMARC-postposterna i DNS för _alla_ dina e-postdomäner i Office 365:

  - Kontrollera att SPF-posten identifierar _alla_ e-postkällor för avsändare på domänen (glöm inte tjänster från tredje part!).

  - Använd hårddisken\-( ) för att säkerställa att obehöriga avsändare avvisas av e-postsystem som är konfigurerade för att göra det. Du kan använda [falska underrättelser](learn-about-spoof-intelligence.md) för att identifiera avsändare som använder din domän så att du kan inkludera auktoriserade avsändare från tredje part i SPF-posten.

  Instruktioner för konfiguration finns i:
  
  - [Konfigurera SPF i Office 365 för att förhindra förfalskning](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  - [Använd DKIM för att validera utgående e-post som skickas från din egna domän i Office 365](use-dkim-to-validate-outbound-email.md)

  - [Använda DMARC för att validera e-post i Office 365](use-dmarc-to-validate-email.md)

- När det är möjligt rekommenderar vi att du levererar e-post till din domän direkt till Office 365. Med andra ord pekar du din Office 365-domäns MX-post till Office 365. Exchange Online Protection (EOP) kan ge det bästa skyddet för dina molnanvändare när deras e-post levereras direkt till Office 365. Om du måste använda ett e-posthygiensystem från tredje part framför EOP använder du Förbättrad filtrering för kontakter. Instruktioner finns i [Förbättrad filtrering för anslutningsappar i Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

- Multifaktorautentisering (MFA) är ett bra sätt att förhindra komprometterade konton. Du bör starkt överväga att aktivera MFA för alla dina användare. För en stegvis metod, börja med att aktivera MFA för dina mest känsliga användare (administratörer, chefer, etc.) innan du aktiverar MFA för alla. Instruktioner finns i [Konfigurera multifaktorautentisering](../../admin/security-and-compliance/set-up-multi-factor-authentication.md).

- Vidarebefordringsregler till externa mottagare används ofta av angripare för att extrahera data. Använd informationen **om vidarebefordrade postlåda** i [Microsoft Secure Score](../mtp/microsoft-secure-score.md) för att hitta och till och med förhindra vidarekopplingsregler till externa mottagare. Mer information finns i [Förmildrande regler](https://blogs.technet.microsoft.com/office365security/mitigating-client-external-forwarding-rules-with-secure-score/)för extern vidarebefordran av klienter med säker poäng .
