---
title: Finjustera skydd mot nätfiske
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
- MET150
description: Administratörer kan ta reda på orsakerna till och hur ett nätfiskemeddelande kom fram i Microsoft 365 och vad de kan göra för att förhindra fler nätfiskemeddelanden i framtiden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d3abbafce36c589f60eb164fb29c714c980f8b98
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286495"
---
# <a name="tune-anti-phishing-protection"></a>Finjustera skydd mot nätfiske

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Även om Microsoft 365 levereras med en mängd olika funktioner för nätfiske som är aktiverade som standard är det möjligt att vissa nätfiskemeddelanden fortfarande kommer fram till dina postlådor. I det här avsnittet beskrivs vad du kan göra för att upptäcka varför ett nätfiskemeddelande har kommit igenom och vad du kan göra för att justera inställningarna för skydd mot nätfiske i Microsoft 365-organisationen utan att råka göra något _värsta._

## <a name="first-things-first-deal-with-any-compromised-accounts-and-make-sure-you-block-any-more-phishing-messages-from-getting-through"></a>Vi börjar med det första: ta itu med alla komprometterade konton och se till att du blockerar fler nätfiskemeddelanden från att komma igenom

Om en mottagares konto har kapats på grund av nätfiskemeddelandet följer du anvisningarna i Svara på ett komprometterat e-postkonto i [Microsoft 365.](responding-to-a-compromised-email-account.md)

Om microsoft Defender för Office 365 ingår i prenumerationen kan du använda [Office 365 Threat Intelligence](office-365-ti.md) för att identifiera andra användare som också har fått nätfiskemeddelandet. Du har fler alternativ för att blockera nätfiskemeddelanden:

- [Säkra länkar i Microsoft Defender för Office 365](set-up-atp-safe-links-policies.md)

- [Säkra bifogade filer i Microsoft Defender för Office 365](set-up-atp-safe-attachments-policies.md)

- [Principer mot nätfiske i Microsoft Defender för Office 365.](configure-atp-anti-phishing-policies.md) Observera att du tillfälligt  kan öka tröskelvärdena för avancerad nätfiske i principen från **Standard** till **Aggressiv,** Mer **aggressiva** eller **Mest aggressiva.**

Kontrollera att defender för Office 365-funktionerna är påslagna.

## <a name="report-the-phishing-message-to-microsoft"></a>Rapportera nätfiskemeddelandet till Microsoft

Rapportering av nätfiskemeddelanden är användbart när du ska justera de filter som används för att skydda alla kunder i Microsoft 365. Instruktioner finns i Rapportera [meddelanden och filer till Microsoft.](report-junk-email-messages-to-microsoft.md)

## <a name="inspect-the-message-headers"></a>Kontrollera meddelanderubrikerna

Du kan granska rubrikerna i nätfiskemeddelandet för att se om det finns något du kan göra själv för att förhindra att fler nätfiskemeddelanden kommer igenom. Att granska meddelanderubrikerna kan med andra ord hjälpa dig att identifiera de inställningar i organisationen som var ansvariga för att tillåta nätfiskemeddelanden.

Mer specifikt bör du titta i **huvudfältet för X-Forefront-Antispam-Report** i meddelanderubrikerna för uppgifter om hur filtrering av skräppost eller nätfiske i värdet för filtrering av skräppostfiltrering (SFV) visas. Meddelanden som hoppar över filtrering kommer att ha en post, vilket innebär att en av dina inställningar tillät detta meddelande genom att åsidosätta skräppost- eller nätfiskeförsöken som fastställts `SCL:-1` av tjänsten. Mer information om hur du får meddelandehuvuden och en fullständig lista över alla tillgängliga rubriker mot skräppost och nätfiske finns i Rubriker för skräppostskydd i [Microsoft 365.](anti-spam-message-headers.md)

## <a name="best-practices-to-stay-protected"></a>Metodtips för att hålla sig skyddad

- Kör Secure Score varje månad [för](../mtp/microsoft-secure-score.md) att bedöma organisationens säkerhetsinställningar.

- För meddelanden som hamnar i karantän av misstag eller för meddelanden som tillåts via, rekommenderar vi att du söker efter de meddelandena i Hotutforskaren och identifiering [i realtid.](threat-explorer.md) Du kan söka efter avsändare, mottagare eller meddelande-ID. När du har hittat meddelandet går du till information genom att klicka på ämnet. För ett meddelande i karantän kan du se vad "identifieringstekniken" var, så att du kan använda lämplig metod för att åsidosätta den. Om du vill ta fram ett tillåtet meddelande tittar du efter vilken princip som tillåtit meddelandet.

- Förfalskning är märkt som nätfiske i Defender för Office 365. Ibland är förfalskning ett då och ibland vill inte användarna ha det i karantän. För att minimera påverkan på användare granskar du med jämna [mellanrum förfalskningsrapporten.](learn-about-spoof-intelligence.md) När du har granskat och gjort nödvändiga åsidosättningar kan du konfigurera  [förfalskningsinformation](set-up-anti-phishing-policies.md#spoof-settings) för att sätta misstänkta meddelanden i karantän i stället för att leverera dem till användarens skräppostmapp.

- Du kan upprepa steget ovan för personifiering (domän eller användare). Personifieringsrapporten finns under Instrumentpanelen för **hantering** \> **av** \> **hot.**

- Granska med jämna mellanrum [rapporten om skydd mot hot.](view-reports-for-atp.md#threat-protection-status-report)

- Vissa kunder tillåter oavsiktligt nätfiskemeddelanden genom att placera sina egna domäner i listan Tillåt avsändare eller Tillåt domän i principer för skräppostskydd. Även om den här konfigurationen tillåter att vissa legitima meddelanden kommer att tillåtas även skadliga meddelanden som normalt blockeras av skräppost- och/eller nätfiskefilter. I stället för att tillåta domänen bör du åtgärda det underliggande problemet.

  Det bästa sättet att hantera legitima meddelanden som blockeras av Microsoft 365 (falska positiva meddelanden) som involverar avsändare i din domän är  att helt och hållet konfigurera SPF-, DKIM- och DMARC-posterna i DNS för alla dina e-postdomäner:

  - Kontrollera att SPF-posten identifierar _alla_ e-postkällor för avsändare i din domän (glöm inte tredjepartstjänster!).

  - Använd hårt fel \- (alla) för att säkerställa att obehöriga avsändare avvisas av e-postsystem som är konfigurerade att göra det. Du kan använda [förfalskningsinformation](learn-about-spoof-intelligence.md) för att identifiera avsändare som använder din domän, så att du kan ta med behöriga avsändare från tredje part i SPF-posten.

  Konfigurationsinstruktioner finns i:

  - [Konfigurera SPF för att förhindra förfalskning](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  - [Använda DKIM för att validera utgående e-post som skickas från din anpassade domän](use-dkim-to-validate-outbound-email.md)

  - [Använda DMARC för att validera e-post](use-dmarc-to-validate-email.md)

- Vi rekommenderar att du levererar e-post för domänen direkt till Microsoft 365, när det är möjligt. Med andra ord, låt Microsoft 365-domänens MX-post peka på Microsoft 365. Exchange Online Protection (EOP) kan ge molnanvändarna det bästa skyddet när deras e-post levereras direkt till Microsoft 365. Om du måste använda ett system för e-postbekräftelse från tredje part framför EOP använder du Utökad filtrering för kopplingar. Instruktioner finns i Utökad [filtrering för kopplingar i Exchange Online.](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)

- Användarna bör använda [tillägget Rapportmeddelande eller](enable-the-report-message-add-in.md) tillägget [Rapport](enable-the-report-phish-add-in.md) nätfiske för att rapportera meddelanden till Microsoft, som kan utbilda vårt system. Administratörer bör också kunna dra nytta av funktionerna [för](admin-submission.md) inskicking av administratör.

- Multifaktorautentisering (MFA) är ett bra sätt att förhindra komprometterade konton. Du bör starkt överväga att aktivera MFA för alla dina användare. Om du vill ha en fasad metod börjar du med att aktivera MFA för känsliga användare (administratörer, chefer osv.) innan du aktiverar MFA för alla. Instruktioner finns i Konfigurera [multifaktorautentisering.](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)

- Vidare vidarebefordransregler till externa mottagare används ofta av attackerare för att extrahera data. Använd informationen **om vidarebefordransregler för postlådor** i [Microsoft Secure Score för](../mtp/microsoft-secure-score.md) att hitta och förhindra vidare vidarebefordransregler till externa mottagare. Mer information finns i för att minska externa klient [vidarebefordransregler med Secure Score.](https://docs.microsoft.com/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score)
