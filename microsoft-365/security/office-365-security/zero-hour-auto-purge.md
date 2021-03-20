---
title: Automatisk rensning (ZAP) på nolltimmar
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
description: Administratörer kan ta reda på hur ZAP (Zero-hour Auto Purge) retroaktivt kan flytta skickade meddelanden i en Exchange Online-postlåda till mappen Skräppost eller karantän som retroaktivt visar sig vara skräppost eller nätfiske.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b5744fdd4ce371f62fcb4b07a4cbcd003405c3db
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907982"
---
# <a name="zero-hour-auto-purge-zap-in-exchange-online"></a>Zap (Zero-hour auto purge) i Exchange Online

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="basic-features-of-zap"></a>Grundläggande funktioner i ZAP

I Microsoft 365-organisationer med postlådor i Exchange Online är ZAP (zero-hour auto purge) en funktion för e-postskydd som retroaktivt identifierar och neutralerar skadliga nätfiske-, skräppost- och skadlig programvara som redan har levererats till Exchange Online-postlådor.

ZAP fungerar inte i fristående Exchange Online Protection-miljöer (EOP) som skyddar lokala Exchange-postlådor.

## <a name="how-zap-works"></a>Så här fungerar ZAP

Signaturer för skräppost och skadlig programvara uppdateras dagligen i tjänsten i realtid. Användare kan dock fortfarande ta emot skadliga meddelanden av en mängd olika orsaker, till exempel om innehållet är upptaget efter att det levererats till användarna. ZAP åtgärdar det här problemet genom att kontinuerligt övervaka uppdateringar av signaturer för skräppost och skadlig programvara i tjänsten. ZAP kan hitta och ta bort meddelanden som redan finns i en användares postlåda.

ZAP-åtgärden är smidig för användaren. de meddelas inte om ett meddelande identifieras och flyttas.

[Listor över betrodda](create-safe-sender-lists-in-office-365.md)avsändare, e-postflödesregler (kallas även transportregler), inkorgsregler eller ytterligare filter har företräde framför ZAP. På ungefär samma sätt som i e-postflödet innebär det att även om tjänsten bestämmer att det levererade meddelandet behöver ZAP, så ageras meddelandet inte på grund av konfigurationen betrodda avsändare. Det här är en annan anledning till att vara försiktig med att konfigurera meddelanden för att kringgå filtrering.

### <a name="malware-zap"></a>Malware ZAP

För **lästa eller olästa meddelanden** som innehåller skadlig programvara efter leverans sätts det meddelande som innehåller den bifogade filen i skadlig programvara i karantän av ZAP. Endast administratörer kan visa och hantera meddelanden om skadlig programvara från karantän.

Malware ZAP aktiveras som standard i principer för skydd mot skadlig programvara. Mer information finns i Konfigurera [principer för skydd mot skadlig programvara i EOP.](configure-anti-malware-policies.md)

### <a name="phish-zap"></a>Phish ZAP

För lästa eller **olästa** meddelanden som identifieras som nätfiske efter leverans beror  ZAP-resultatet på åtgärden som är konfigurerad för en filtrering av nätfiskemeddelanden i gällande policy mot skräppost. Tillgängliga filtreringsåtgärder för nätfiske och deras möjliga ZAP-resultat beskrivs i följande lista:

- **Lägg till ämnesraden X-Header**, Förbereda ämnesraden med **text** **,** Omdirigera meddelandet till e-postadress **,** Ta bort meddelande: ZAP vidtar ingen åtgärd för meddelandet.

- **Flytta meddelandet till skräppost:** ZAP flyttar meddelandet till mappen Skräppost så länge skräppostregeln är aktiverad för postlådan (den är aktiverad som standard). Mer information finns i Konfigurera [inställningar för skräppost i Exchange Online-postlådor i Microsoft 365.](configure-junk-email-settings-on-exo-mailboxes.md)

- **Sätt meddelande i** karantän: ZAP sätt meddelandet i karantän.

Som standard är phish ZAP aktiverat i principer för skräppostskydd och standardåtgärden för filtrering av nätfiskemeddelanden är karantänmeddelande, vilket innebär att zap sätts i karantän för meddelandet som standard.  

Mer information om konfigurering av skräppostfiltreringsprinciper [finns i Konfigurera principer mot skräppost i Microsoft 365.](configure-your-spam-filter-policies.md)

### <a name="spam-zap"></a>Spam ZAP

För **olästa** meddelanden som identifieras som skräppost efter leverans beror ZAP-resultatet  på åtgärden som är konfigurerad för skräppostfiltreringen i tillämplig skyddsprincip. Tillgängliga filtreringsåtgärder för skräppost och deras möjliga ZAP-resultat beskrivs i följande lista:

- **Lägg till ämnesraden X-Header**, Förbereda ämnesraden med **text** **,** Omdirigera meddelandet till e-postadress **,** Ta bort meddelande: ZAP vidtar ingen åtgärd för meddelandet.

- **Flytta meddelandet till skräppost:** ZAP flyttar meddelandet till mappen Skräppost så länge skräppostregeln är aktiverad för postlådan (den är aktiverad som standard). Mer information finns i Konfigurera [inställningar för skräppost i Exchange Online-postlådor i Microsoft 365.](configure-junk-email-settings-on-exo-mailboxes.md)

- **Sätt meddelande i** karantän: ZAP sätt meddelandet i karantän. Slutanvändarna kan visa och hantera sina egna meddelanden i karantänen för skräppost.

Som standard har ZAP för skräppost aktiverats i principer  för skydd mot skräppost, och standardåtgärden för  filtrering av skräppost är Flytta meddelanden till mappen **Skräppost,** vilket innebär att ZAP flyttar olästa meddelanden till mappen Skräppost som standard.

Mer information om konfigurering av skräppostfiltreringsprinciper [finns i Konfigurera principer mot skräppost i Microsoft 365.](configure-your-spam-filter-policies.md)

### <a name="zap-considerations-for-microsoft-defender-for-office-365"></a>ZAP-överväganden för Microsoft Defender för Office 365

ZAP sätt inte i karantän något meddelande [](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies) som pågår i processen för dynamisk leverans i genomsökning av säkra bifogade filer, eller där EOP-filtrering av skadlig programvara redan har ersatt den bifogade filen med Text.txtfil.  Om en nätfiske- eller skräppostsignal tas emot för dessa typer av meddelanden, och filtreringen av bedömning i principen mot skräppost är inställd på att vidta någon åtgärd för meddelandet (Flytta till Skräppost, Omdirigera, Ta bort eller Karantän) använder ZAP en "Flytta till skräppost"-åtgärd.

## <a name="how-to-see-if-zap-moved-your-message"></a>Så här ser du om ZAP har flyttat ditt meddelande

Om du vill avgöra om ZAP har [](view-email-security-reports.md#threat-protection-status-report) flyttat ditt meddelande kan du använda antingen rapporten om hotskyddsstatus eller [Threat Explorer (och identifieringar i realtid).](threat-explorer.md) Observera att ZAP inte loggas i granskningsloggarna för Exchange-postlådor som en systemåtgärd.

## <a name="zap-faq"></a>VANLIGA FRÅGOR OM ZAP

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a>Vad händer om ett legitimt meddelande flyttas till mappen Skräppost?

Du bör följa den vanliga rapporteringsprocessen för [falska positiva resultat.](report-junk-email-messages-to-microsoft.md) Den enda orsaken till att meddelandet flyttas från Inkorgen till mappen Skräppost är att tjänsten har fastställt att meddelandet är skräppost eller skadligt.

### <a name="what-if-i-use-the-quarantine-folder-instead-of-the-junk-mail-folder"></a>Vad händer om jag använder mappen Karantän i stället för skräppostmappen?

ZAP kommer att vidta åtgärder för ett meddelande baserat på konfigurationen av dina principer för skydd mot skräppost enligt beskrivningen ovan i den här artikeln.

### <a name="what-if-im-using-safe-senders-mail-flow-rules-or-allowedblocked-sender-lists"></a>Vad händer om jag använder betrodda avsändare, e-postflödesregler eller listor över tillåtna/blockerade avsändare?

Betrodda avsändare, e-postflödesregler eller spärra och tillåta att organisationsinställningar har företräde. Dessa meddelanden är undantagna från ZAP eftersom tjänsten gör vad du har konfigurerat den för. Det här är en annan anledning till att vara försiktig med att konfigurera meddelanden för att kringgå filtrering.

### <a name="what-are-the-licensing-requirements-for-zap-to-work"></a>Vilka licenskrav gäller för att ZAP ska fungera?

Det finns inga begränsningar för licenser. ZAP fungerar för alla postlådor som finns på Exchange Online. ZAP fungerar inte i fristående Exchange Online Protection-miljöer (EOP) som skyddar lokala Exchange-postlådor.

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a>Vad händer om ett meddelande flyttas till en annan mapp (t.ex. inkorgsregler)?

ZAP fungerar fortfarande så länge meddelandet inte har tagits bort, eller så länge samma, eller starkare, åtgärder inte redan har tillämpats. Om till exempel principen för nätfiske är inställd på att sätta i karantän och meddelandet redan finns i skräpposten kommer ZAP att vidta åtgärder för att sätta i karantän meddelandet.

### <a name="how-does-zap-affect-mailboxes-on-hold"></a>Hur påverkar ZAP postlådorna?

ZAP sätts inte i karantän för meddelanden från postlådor. ZAP kan flytta meddelanden till mappen Skräppost baserat på åtgärder som är konfigurerade för skräppost eller nätfiske mot skräppost.

Mer information om bevarande i Exchange Online finns i Bevarande av juridiska skäl och bevarande [av juridiska skäl i Exchange Online.](/Exchange/security-and-compliance/in-place-and-litigation-holds)