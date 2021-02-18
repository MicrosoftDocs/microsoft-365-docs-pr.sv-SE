---
title: Zap (Zero-hour auto purge)
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 96deb75f-64e8-4c10-b570-84c99c674e15
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan ta reda på hur ZAP (Zero-Hour Auto Purge) retroaktivt kan flytta skickade meddelanden i en Exchange Online-postlåda till mappen Skräppost eller karantänen som retroaktivt visar sig vara skräppost eller nätfiske.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5fd41cf45ad2a49d74684ae3e20dded5c1b8f034
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287311"
---
# <a name="zero-hour-auto-purge-zap-in-exchange-online"></a>Zap (Zero-hour auto purge) i Exchange Online

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="basic-features-of-zap"></a>Grundläggande funktioner i ZAP

I Microsoft 365-organisationer med postlådor i Exchange Online är ZAP (Zero-hour Auto Purge) en funktion för e-postskydd som retroaktivt identifierar och neutralerar skadliga nätfiske-, skräppost- eller skadlig programvara som redan har levererats till Exchange Online-postlådor.

ZAP fungerar inte i fristående Exchange Online Protection-miljöer (EOP) som skyddar lokala Exchange-postlådor.

## <a name="how-zap-works"></a>Så här fungerar ZAP

Signaturer för skräppost och skadlig programvara uppdateras dagligen i tjänsten. Användare kan dock fortfarande ta emot skadliga meddelanden av en mängd olika orsaker, till exempel om innehållet har lokaliserats efter att det har levererats till användarna. ZAP åtgärdar det här problemet genom att kontinuerligt övervaka uppdateringar av signaturer för skräppost och skadlig programvara i tjänsten. ZAP kan hitta och ta bort meddelanden som redan finns i en användares postlåda.

ZAP-åtgärden är smidig för användaren. De meddelas inte om ett meddelande identifieras och flyttas.

[Listor över betrodda](create-safe-sender-lists-in-office-365.md)avsändare, e-postflödesregler (kallas även transportregler), inkorgsregler och ytterligare filter har företräde framför ZAP. På liknande sätt som i e-postflödet innebär det att även om tjänsten bestämmer att det levererade meddelandet behöver ZAP så ageras meddelandet inte på grund av konfigurationen betrodda avsändare. Det här är en annan orsak till att vara försiktig med att konfigurera meddelanden så att filtrering kringgås.

### <a name="malware-zap"></a>Malware ZAP

För **lästa eller olästa meddelanden** som innehåller skadlig programvara efter leverans sätts det meddelande som innehåller den bifogade filen för skadlig programvara i karantän. Endast administratörer kan visa och hantera meddelanden om skadlig programvara från karantän.

Malware ZAP är aktiverat som standard i principer för skydd mot skadlig programvara. Mer information finns i Konfigurera [principer för skadlig programvara i EOP.](configure-anti-malware-policies.md)

### <a name="phish-zap"></a>Phish ZAP

För **lästa eller olästa** meddelanden som identifieras som nätfiske efter leverans beror  ZAP-resultatet på den åtgärd som har konfigurerats för en filtrering av nätfiskemeddelanden i den tillämpliga principen för skräppostskydd. Tillgängliga filtreringsåtgärder för nätfiske och deras möjliga ZAP-resultat beskrivs i följande lista:

- Lägg till text för **X-Header,** **Lägga till text** i den första ämnesraden: ZAP vidtar ingen åtgärd för meddelandet.

- **Flytta meddelandet till Skräppost:** ZAP flyttar meddelandet till mappen Skräppost så länge skräppostregeln är aktiverad för postlådan (standardinställningen är aktiverad). Mer information finns i Konfigurera [skräppostinställningar för Exchange Online-postlådor i Microsoft 365.](configure-junk-email-settings-on-exo-mailboxes.md)

- **Omdirigera meddelandet till e-postadress,** **Ta bort meddelande,** **sätt meddelande** i karantän: ZAP sätt meddelandet i karantän.

Som standard är phish ZAP aktiverat i principer för skydd  mot skräppost och standardåtgärden för filtrering av nätfiskemeddelanden är karantänmeddelande, vilket innebär att zap sätts i karantänen för meddelandet som standard.

Mer information om konfigurering av skräppostfiltreringsprinciper finns i [Konfigurera principer för skydd mot skräppost i Microsoft 365.](configure-your-spam-filter-policies.md)

### <a name="spam-zap"></a>Spam ZAP

För **olästa** meddelanden som identifieras som skräppost efter leverans beror ZAP-resultatet  på den åtgärd som har konfigurerats för skräppostfiltreringens bedömning i den tillämpliga policyn för skräppostskydd. Tillgängliga filtreringsåtgärder för skräppost och deras möjliga ZAP-resultat beskrivs i följande lista:

- Lägg till text för **X-Header,** **Lägga till text** i den första ämnesraden: ZAP vidtar ingen åtgärd för meddelandet.

- **Flytta meddelandet till Skräppost:** ZAP flyttar meddelandet till mappen Skräppost så länge skräppostregeln är aktiverad för postlådan (standardinställningen är aktiverad). Mer information finns i Konfigurera [skräppostinställningar för Exchange Online-postlådor i Microsoft 365.](configure-junk-email-settings-on-exo-mailboxes.md)

- **Omdirigera meddelandet till e-postadress,** **Ta bort meddelande,** **sätt meddelande** i karantän: ZAP sätt meddelandet i karantän. Slutanvändarna kan visa och hantera sina egna meddelanden i karantänen för skräppost.

Som standard har ZAP för skräppost aktiverats i principer  för skräppostskydd, och standardåtgärden för filtrering  av skräppost är Flytta meddelanden till mappen **Skräppost,** vilket innebär att ZAP i skräppostmappen flyttar olästa meddelanden till mappen Skräppost som standard.

Mer information om konfigurering av skräppostfiltreringsprinciper finns i [Konfigurera principer för skydd mot skräppost i Microsoft 365.](configure-your-spam-filter-policies.md)

### <a name="zap-considerations-for-microsoft-defender-for-office-365"></a>ZAP-överväganden för Microsoft Defender för Office 365

ZAP sätt inte i karantän ett meddelande [](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies) som bearbetas med dynamisk leverans vid genomsökning av säkra bifogade filer, eller där EOP-filtrering av skadlig programvara redan har ersatt den bifogade filen med Text.txt **fil.** Om en nätfiske- eller skräppostsignal tas emot för den här typen av meddelanden, och filtreringen i skräppostprincipen är inställd på att vidta någon åtgärd för meddelandet (Flytta till Skräppost, Omdirigera, Ta bort eller Karantän) använder ZAP som standard åtgärden Flytta till skräppost.

## <a name="how-to-see-if-zap-moved-your-message"></a>Så här ser du om ZAP har flyttat ditt meddelande

Om du vill avgöra om ZAP har [](view-email-security-reports.md#threat-protection-status-report) flyttat ditt meddelande kan du använda antingen rapporten status för skydd mot hot [eller Hotutforskaren (och identifieringar i realtid).](threat-explorer.md) Observera att ZAP inte loggas i granskningsloggarna för Exchange-postlådor som en systemåtgärd.

## <a name="zap-faq"></a>ZAP VANLIGA FRÅGOR OCH SVAR

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a>Vad händer om ett legitimt meddelande flyttas till mappen Skräppost?

Du bör följa den vanliga rapporteringsprocessen för [falska positiva resultat.](report-junk-email-messages-to-microsoft.md) Den enda orsaken till att meddelandet flyttas från Inkorgen till mappen Skräppost är att tjänsten har fastställt att meddelandet är skräppost eller skadligt.

### <a name="what-if-i-use-the-quarantine-folder-instead-of-the-junk-mail-folder"></a>Vad händer om jag använder mappen Karantän i stället för skräppostmappen?

ZAP kommer att vidta åtgärder på ett meddelande baserat på konfigurationen av dina principer för skydd mot skräppost enligt beskrivningen tidigare i den här artikeln.

### <a name="what-if-im-using-safe-senders-mail-flow-rules-or-allowedblocked-sender-lists"></a>Vad händer om jag använder betrodda avsändare, e-postflödesregler eller listor med tillåtna/blockerade avsändare?

Betrodda avsändare, e-postflödesregler eller blockering och organisationens inställningar har företräde. Dessa meddelanden är undantagna från ZAP eftersom tjänsten gör vad du konfigurerat den för. Det här är en annan orsak till att vara försiktig med att konfigurera meddelanden så att filtrering kringgås.

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a>Vad händer om ett meddelande flyttas till en annan mapp (t.ex. inkorgsregler)?

ZAP fungerar fortfarande så länge meddelandet inte har tagits bort, eller så länge samma, eller starkare, åtgärder inte redan har tillämpats. Om till exempel principen för nätfiske är inställd på att sätta i karantän och meddelandet redan finns i skräpposten kommer ZAP att vidta åtgärder för att sätta meddelandet i karantän.

### <a name="how-does-zap-affect-mailboxes-on-hold"></a>Hur påverkar ZAP postlådor som är väntande?

ZAP sätts inte i karantän för meddelanden från postlådor som är väntande. ZAP kan flytta meddelanden till mappen Skräppost baserat på åtgärder som konfigurerats för skräppost eller nätfiskeförsök i principer mot skräppost.

Mer information om bevarande i Exchange Online finns i Bevarande av juridiska skäl på plats i [Exchange Online.](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds)
