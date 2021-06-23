---
title: Automatisk rensning utan timme i Microsoft Defender för Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 06/22/2021
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
description: Zap (Zero-hour auto purge) flyttar retroaktivt alla meddelanden i en Exchange Online-postlåda till mappen Skräppost eller karantän som visar sig vara skräppost eller nätfiske efter leveransen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fdfc39b8bd18d33f95b85028e3661008a17a1209
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083506"
---
# <a name="zero-hour-auto-purge-zap-in-exchange-online"></a>ZAP (Zero-hour auto purge) i Exchange Online

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

## <a name="zero-hour-auto-purge-zap-basics"></a>Grundläggande om autorensning (ZAP) på nolltimmar

I Microsoft 365 organisationer med postlådor i Exchange Online är ZAP (zero-hour auto purge) en funktion för e-postskydd som retroaktivt identifierar och neutralerar skadliga nätfiske-, skräppost- eller skadlig programvara som redan har levererats till Exchange Online-postlådor.

ZAP fungerar inte i fristående EOP Exchange Online Protection miljöer (EOP) som skyddar lokala e-postlådor Exchange postlådor.

## <a name="how-zap-works"></a>Så här fungerar ZAP

Signaturer för skräppost och skadlig programvara uppdateras dagligen i tjänsten i realtid. Användare kan dock fortfarande ta emot skadliga meddelanden av en mängd olika orsaker, till exempel om innehållet är upptaget efter att det levererats till användarna. ZAP åtgärdar det här problemet genom att kontinuerligt övervaka uppdateringar av signaturer för skräppost och skadlig programvara i tjänsten. ZAP kan hitta och ta bort meddelanden som redan finns i en användares postlåda.

ZAP-åtgärden är smidig för användaren. de meddelas inte om ett meddelande identifieras och flyttas.

[Valv distributionslistor](create-safe-sender-lists-in-office-365.md)har e-postflödesregler (kallas även transportregler), inkorgsregler eller ytterligare filter företräde framför ZAP. På ungefär samma sätt som i e-postflödet innebär det att även om tjänsten bestämmer att det levererade meddelandet behöver ZAP, så ageras meddelandet inte på grund av konfigurationen betrodda avsändare. Det här är en annan anledning till att vara försiktig med att konfigurera meddelanden för att kringgå filtrering.

### <a name="zero-hour-auto-purge-zap-for-malware"></a>ZAP (Zero-hour auto purge) för skadlig programvara

För **lästa eller olästa meddelanden** som innehåller skadlig programvara efter leverans sätts det meddelande som innehåller den bifogade filen i skadlig programvara i karantän av ZAP. Endast administratörer kan visa och hantera meddelanden om skadlig programvara från karantän.

ZAP för skadlig programvara är aktiverat som standard i principer mot skadlig programvara. Mer information finns i Konfigurera [principer för skydd mot skadlig programvara i EOP.](configure-anti-malware-policies.md)

### <a name="zero-hour-auto-purge-zap-for-phishing"></a>Zap (Zero-hour auto purge) för nätfiske

För lästa eller **olästa** meddelanden som identifieras som nätfiske efter leverans beror  ZAP-resultatet på åtgärden som är konfigurerad för en filtrering av nätfiskemeddelanden i gällande policy mot skräppost. Tillgängliga filtreringsåtgärder för nätfiske och deras möjliga ZAP-resultat beskrivs i följande lista:

- **Lägg till ämnesraden X-Header**, Förbereda ämnesraden med **text** **,** Omdirigera meddelandet till e-postadress **,** Ta bort meddelande: ZAP vidtar ingen åtgärd för meddelandet.

- **Flytta meddelandet till skräppost:** ZAP flyttar meddelandet till mappen Skräppost så länge skräppostregeln är aktiverad för postlådan (den är aktiverad som standard). Mer information finns i [Konfigurera inställningar för skräppost Exchange Online postlådor i Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

- **Sätt meddelande i** karantän: ZAP sätt meddelandet i karantän.

Som standard är ZAP för nätfiske aktiverat i principer för  skydd mot skräppost, och standardåtgärden för filtrering av nätfiskemeddelanden är karantänmeddelande, vilket betyder ZAP för att sätta meddelandet i karantän för nätfiske som standard.

Mer information om konfigurering av skräppostfiltrering av filtreringsprinciper finns i [Konfigurera principer mot skräppost i Microsoft 365.](configure-your-spam-filter-policies.md)

### <a name="zero-hour-auto-purge-zap-for-high-confidence-phishing"></a>ZAP (Zero-hour auto purge) för nätfiske med hög säkerhet

För **lästa eller olästa** meddelanden som identifieras som nätfiske efter leverans sätts meddelandet i karantän av ZAP. Endast administratörer kan visa och hantera meddelanden med hög säkerhet från karantän.

ZAP för hög konfidens är aktiverat som standard. Mer information finns i [Skydda som standard i Office 365](secure-by-default.md).

### <a name="zero-hour-auto-purge-zap-for-spam"></a>ZAP (Zero-hour auto purge) för skräppost

För **olästa** meddelanden som identifieras som skräppost efter leverans beror ZAP-resultatet  på åtgärden som är konfigurerad för skräppostfiltreringen i tillämplig skyddsprincip. Tillgängliga filtreringsåtgärder för skräppost och deras möjliga ZAP-resultat beskrivs i följande lista:

- **Lägg till ämnesraden X-Header**, Förbereda ämnesraden med **text** **,** Omdirigera meddelandet till e-postadress **,** Ta bort meddelande: ZAP vidtar ingen åtgärd för meddelandet.

- **Flytta meddelandet till skräppost:** ZAP flyttar meddelandet till mappen Skräppost så länge skräppostregeln är aktiverad för postlådan (den är aktiverad som standard). Mer information finns i [Konfigurera inställningar för skräppost Exchange Online postlådor i Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

- **Sätt meddelande i** karantän: ZAP sätt meddelandet i karantän. Slutanvändarna kan visa och hantera sina egna meddelanden i karantänen för skräppost.

Som standard har ZAP för skräppost aktiverats i principer  för skydd mot skräppost, och standardåtgärden för  filtrering av skräppost är Flytta meddelanden till mappen **Skräppost,** vilket innebär att ZAP flyttar olästa meddelanden till mappen Skräppost som standard.

Mer information om konfigurering av skräppostfiltrering av filtreringsprinciper finns i [Konfigurera principer mot skräppost i Microsoft 365.](configure-your-spam-filter-policies.md)

### <a name="zero-hour-auto-purge-zap-considerations-for-microsoft-defender-for-office-365"></a>ZAP-överväganden (Zero-hour auto purge) för Microsoft Defender för Office 365

ZAP sätt inte i karantän ett meddelande [](safe-attachments.md#dynamic-delivery-in-safe-attachments-policies) som pågår i processen för dynamisk leverans i genomsökning av bifogade filer i Valv, eller där EOP-filtrering av skadlig programvara redan har ersatt den bifogade filen med **Text.txtfil.** Om en nätfiske- eller skräppostsignal tas emot för dessa typer av meddelanden, och filtreringen av bedömning i principen mot skräppost är inställd på att vidta någon åtgärd för meddelandet (Flytta till Skräppost, Omdirigera, Ta bort eller Karantän) använder ZAP en "Flytta till skräppost"-åtgärd.

## <a name="how-to-see-if-zap-moved-your-message"></a>Så här ser du om ZAP har flyttat ditt meddelande

Om du vill avgöra om ZAP har [](view-email-security-reports.md#threat-protection-status-report) flyttat ditt meddelande kan du använda antingen rapporten om hotskyddsstatus eller [Threat Explorer (och identifieringar i realtid).](threat-explorer.md) Observera att ZAP inte loggas i Exchange postlådegranskningsloggar som en systemåtgärd.

## <a name="zero-hour-auto-purge-zap-faq"></a>Vanliga frågor om autorensning (ZAP) (Zero-hour auto purge)

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a>Vad händer om ett legitimt meddelande flyttas till mappen Skräppost?

Du bör följa den vanliga rapporteringsprocessen för [falska positiva resultat.](report-junk-email-messages-to-microsoft.md) Den enda orsaken till att meddelandet flyttas från Inkorgen till mappen Skräppost är att tjänsten har fastställt att meddelandet är skräppost eller skadligt.

### <a name="what-if-i-use-the-quarantine-folder-instead-of-the-junk-mail-folder"></a>Vad händer om jag använder mappen Karantän i stället för skräppostmappen?

ZAP kommer att vidta åtgärder för ett meddelande baserat på konfigurationen av dina principer för skydd mot skräppost enligt beskrivningen ovan i den här artikeln.

### <a name="what-if-im-using-safe-senders-mail-flow-rules-or-allowedblocked-sender-lists"></a>Vad händer om jag använder betrodda avsändare, e-postflödesregler eller listor över tillåtna/blockerade avsändare?

Valv avsändare, e-postflödesregler eller blockera och tillåta att organisationsinställningar prioriteras. Dessa meddelanden är undantagna från ZAP eftersom tjänsten gör vad du har konfigurerat den för. Det här är en annan anledning till att vara försiktig med att konfigurera meddelanden för att kringgå filtrering.

### <a name="what-are-the-licensing-requirements-for-zero-hour-auto-purge-zap-to-work"></a>Vilka licenskrav gäller för att ZAP (Zero-hour auto purge) ska fungera?

Det finns inga begränsningar för licenser. ZAP fungerar för alla postlådor som finns på Exchange online. ZAP fungerar inte i fristående EOP Exchange Online Protection miljöer (EOP) som skyddar lokala e-postlådor Exchange postlådor.

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a>Vad händer om ett meddelande flyttas till en annan mapp (t.ex. inkorgsregler)?

Automatisk rensning utan timme fungerar fortfarande så länge meddelandet inte har tagits bort, eller så länge samma, eller starkare, åtgärd inte redan har tillämpats. Om till exempel principen för nätfiske är inställd på att sätta i karantän och meddelandet redan finns i skräpposten kommer ZAP att vidta åtgärder för att sätta i karantän meddelandet.

### <a name="how-does-zap-affect-mailboxes-on-hold"></a>Hur påverkar ZAP postlådorna?

En automatisk rensning utan timme sätt meddelanden från postlådor i karantän. ZAP kan flytta meddelanden till mappen Skräppost baserat på åtgärder som är konfigurerade för skräppost eller nätfiske mot skräppost.

Mer information om bevarande i Exchange Online finns i Bevarande av juridiska skäl på plats [i Exchange Online.](/Exchange/security-and-compliance/in-place-and-litigation-holds)
