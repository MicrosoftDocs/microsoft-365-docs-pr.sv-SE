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
description: Administratörer kan läsa mer om varför och hur nätfiskemeddelanden kom fram i Microsoft 365 och vad de kan göra för att förhindra fler nätfiskemeddelanden i framtiden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1772a0329825b8808352892c8d99f0d7680112f5
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207224"
---
# <a name="tune-anti-phishing-protection"></a>Finjustera skydd mot nätfiske

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Även om Microsoft 365 levereras med en mängd olika funktioner mot nätfiske som är aktiverade som standard är det möjligt att vissa nätfiskemeddelanden fortfarande kan komma fram till dina postlådor. I det här avsnittet beskrivs vad du kan göra för att upptäcka varför ett nätfiskemeddelande har kommit igenom och vad du kan göra för att justera inställningarna för skydd mot nätfiske i din Microsoft 365-organisation utan att råka skada _saker._

## <a name="first-things-first-deal-with-any-compromised-accounts-and-make-sure-you-block-any-more-phishing-messages-from-getting-through"></a>En sak i första hand: ta itu med alla komprometterade konton och se till att du blockerar nätfiskemeddelanden så att de inte kommer igenom

Om en mottagares konto har kapats som ett resultat av nätfiskemeddelandet följer du anvisningarna i Svara på ett komprometterat e-postkonto [i Microsoft 365.](responding-to-a-compromised-email-account.md)

Om Microsoft Defender för Office 365 ingår i prenumerationen kan du använda Hotinformation för [Office 365](office-365-ti.md) för att identifiera andra användare som också har fått nätfiskemeddelandet. Du har fler alternativ för att blockera nätfiskemeddelanden:

- [Säkra länkar i Microsoft Defender för Office 365](set-up-safe-links-policies.md)

- [Säkra bifogade filer i Microsoft Defender för Office 365](set-up-safe-attachments-policies.md)

- [Principer för skydd mot nätfiske i Microsoft Defender för Office 365.](configure-atp-anti-phishing-policies.md) Observera att du tillfälligt kan öka avancerade tröskelvärden **för nätfiske** i principen från **Standard** till **Aggressiv**, Mer **aggressiva** eller **Mest aggressiva.**

Kontrollera att dessa Defender för Office 365-funktioner är påslagna.

## <a name="report-the-phishing-message-to-microsoft"></a>Rapportera nätfiskemeddelandet till Microsoft

Rapportering av nätfiskemeddelanden är användbart när du ska justera de filter som används för att skydda alla kunder i Microsoft 365. Anvisningar finns i [Artikeln om att rapportera meddelanden och filer till Microsoft.](report-junk-email-messages-to-microsoft.md)

## <a name="inspect-the-message-headers"></a>Kontrollera meddelanderubrikerna

Du kan granska rubrikerna i nätfiskemeddelandet för att se om det finns något du kan göra själv för att förhindra att fler nätfiskemeddelanden kommer igenom. Att granska meddelanderubrikerna kan med andra ord hjälpa dig att identifiera de inställningar i organisationen som var ansvariga för att tillåta nätfiskemeddelanden.

Mer specifikt bör du titta i huvudfältet **för X-Forefront-Antispam-Report** i meddelanderubrikerna för uppgifter om hoppat över filtrering för skräppost eller nätfiske i värdet för Filtrering av skräppost (SFV). Meddelanden som hoppar över filtrering har en post på , vilket innebär att en av dina inställningar tillät detta meddelande genom att åsidosätta skräppost- eller nätfiskeutbrotten som fastställts `SCL:-1` av tjänsten. Mer information om hur du får meddelanderubriker och en fullständig lista över alla tillgängliga rubriker mot skräppost och nätfiske finns i Rubriker för skräppostskydd i [Microsoft 365.](anti-spam-message-headers.md)

## <a name="best-practices-to-stay-protected"></a>Metodtips för att hålla sig skyddad

- Kör Secure Score månadsvis [för](../defender/microsoft-secure-score.md) att utvärdera organisationens säkerhetsinställningar.

- För meddelanden som hamnar i karantän av misstag, eller för meddelanden som tillåts via, rekommenderar vi att du söker efter dessa meddelanden i Hotutforskaren och [identifieringar i realtid.](threat-explorer.md) Du kan söka efter avsändare, mottagare eller meddelande-ID. När du har hittat meddelandet går du till information genom att klicka på ämnet. Om du har ett meddelande i karantän kan du se vilken "identifieringsteknik" som fanns, så att du kan använda rätt metod för att åsidosätta den. I ett tillåtet meddelande kan du se vilken princip som tillåtit meddelandet.

- Förfalskning är märkt som nätfiske i Defender för Office 365. Ibland är förfalskning den, och ibland vill inte användare ha den i karantän. Om du vill minimera påverkan på användare bör du regelbundet [granska förfalskningsrapporten](learn-about-spoof-intelligence.md). När du har granskat och gjort nödvändiga åsidosättningar kan du vara  säker på att konfigurera [förfalskningsinformation](set-up-anti-phishing-policies.md#spoof-settings) till karantän för misstänkta meddelanden i stället för att leverera dem till användarens skräppostmapp.

- Du kan upprepa steget ovan för Personifiering (domän eller användare). Personifieringsrapporten finns under **Instrumentpanelinsikter för** \>  \> **hothantering.**

- Gå regelbundet igenom [rapporten om hotskyddsstatus](view-reports-for-mdo.md#threat-protection-status-report).

- Vissa kunder tillåter oavsiktligt nätfiskemeddelanden genom att placera sina egna domäner i listan Tillåt avsändare eller Tillåt domän i principer för skräppostskydd. Även om den här konfigurationen tillåter vissa legitima meddelanden via, tillåter den även skadliga meddelanden som normalt skulle blockeras av skräppost- och/eller nätfiskefilter. I stället för att tillåta domänen bör du korrigera det underliggande problemet.

  Det bästa sättet att hantera legitima meddelanden som blockeras av Microsoft 365 (falska positiva meddelanden) som involverar avsändare på din domän är  att helt och hållet konfigurera SPF-, DKIM- och DMARC-posterna i DNS för alla dina e-postdomäner:

  - Kontrollera att SPF-posten  identifierar alla e-postkällor för avsändare i din domän (glöm inte tredjepartstjänster!).

  - Använd hard fail (all) för att säkerställa att obehöriga avsändare \- avvisas av e-postsystem som är konfigurerade för att göra det. Du kan använda [förfalskningsinformation](learn-about-spoof-intelligence.md) för att identifiera avsändare som använder din domän, så att du kan inkludera behöriga avsändare från tredje part i SPF-posten.

  Konfigurationsinstruktioner finns i:

  - [Konfigurera SPF för att förhindra förfalskning](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  - [Använda DKIM för att validera utgående e-post som skickas från din anpassade domän](use-dkim-to-validate-outbound-email.md)

  - [Använda DMARC för att validera e-post](use-dmarc-to-validate-email.md)

- Vi rekommenderar att du levererar e-post för domänen direkt till Microsoft 365, när det är möjligt. Med andra ord, peka Microsoft 365-domänens MX-post till Microsoft 365. Exchange Online Protection (EOP) ger bästa möjliga skydd för dina molnanvändare när deras e-post levereras direkt till Microsoft 365. Om du måste använda ett e-posthanteringssystem från tredje part framför EOP använder du Utökad filtrering för kopplingar. Instruktioner finns i [Utökad filtrering för kopplingar i Exchange Online.](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)

- Användarna bör använda [tilläggen Rapportmeddelande](enable-the-report-message-add-in.md) eller Rapportera nätfiske för att rapportera meddelanden till Microsoft, som kan träna vårt system. [](enable-the-report-phish-add-in.md) Administratörer bör också kunna dra nytta av funktionerna [för](admin-submission.md) administrationsinskickande.

- Multifaktorautentisering (MFA) är ett bra sätt att förhindra komprometterade konton. Du bör starkt överväga att aktivera MFA för alla dina användare. Om du vill ha en fasad metod börjar du med att aktivera MFA för känsliga användare (administratörer, chefer osv.) innan du aktiverar MFA för alla. Anvisningar finns i [Konfigurera multifaktorautentisering.](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)

- Regler för vidarebefordran till externa mottagare används ofta av attackerare för att extrahera data. Använd informationen **om vidare vidarebefordran av postlådor** i [Microsoft Secure Score](../defender/microsoft-secure-score.md) för att hitta och även förhindra vidare vidarebefordran av regler till externa mottagare. Mer information finns i [Mitigating Client External Forwarding Rules med Secure Score.](/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score)
