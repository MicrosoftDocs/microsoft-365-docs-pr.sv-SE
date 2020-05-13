---
title: Nolltimmars automatisk rensning (ZAP)
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
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
description: Administratörer kan lära sig mer om hur automatisk rensning av nolltimmar (ZAP) retroaktivt kan flytta levererade meddelanden i en Exchange Online-postlåda till mappen Skräppost eller karantän som retroaktivt visar sig vara skräppost eller nätfiske.
ms.openlocfilehash: 643063139f5d65b0271fd14ee5a2d1ca1f42ad1a
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208446"
---
# <a name="zero-hour-auto-purge-zap-in-exchange-online"></a>Zero-hour automatisk rensning (ZAP) i Exchange Online

## <a name="overview"></a>Översikt

I Microsoft 365-organisationer med postlådor i Exchange Online är automatisk rensning av nolltimmar (ZAP) en e-postskyddsfunktion som retroaktivt identifierar och neutraliserar meddelanden om skadligt nätfiske, skräppost eller skadlig kod som redan har levererats till Exchange Online-postlådor.

ZAP fungerar inte i fristående EOP-miljöer (Exchange Online Protection) som skyddar lokala Exchange-postlådor.

## <a name="how-zap-works"></a>Hur ZAP fungerar

Spam och malware signaturer uppdateras i tjänsten i realtid på en daglig basis. Användare kan dock fortfarande ta emot skadliga meddelanden av olika skäl, bland annat om innehållet är weaponized efter att ha levererats till användare. ZAP åtgärdar det här problemet genom att kontinuerligt övervaka uppdateringar av spam- och malware-signaturerna i tjänsten. ZAP kan hitta och ta bort meddelanden som redan finns i en användares postlåda.

ZAP-åtgärden är sömlös för användaren. De meddelas inte om ett meddelande identifieras och flyttas.

[Säkra avsändarelistor](create-safe-sender-lists-in-office-365.md), e-postflödesregler (kallas även transportregler), inkorgsregler eller ytterligare filter har företräde framför ZAP. I likhet med vad som händer i e-postflödet innebär det att även om tjänsten bestämmer att det levererade meddelandet behöver ZAP, så har meddelandet inte agerat på grund av konfigurationen för betrodda avsändare. Detta är ytterligare en anledning att vara försiktig med att konfigurera meddelanden för att kringgå filtrering.

### <a name="malware-zap"></a>Malware ZAP

För **lästa eller olästa meddelanden** som visar sig innehålla skadlig kod efter leverans sätter ZAP meddelandet som innehåller den bifogade koden i karantän. Endast administratörer kan visa och hantera meddelanden om skadlig kod från karantänen.

Malware ZAP är aktiverat som standard i anti-malware politik. Mer information finns i [Konfigurera principer mot skadlig kod i EOP](configure-anti-malware-policies.md).

### <a name="phish-zap"></a>Phish ZAP

För **lästa eller olästa meddelanden** som identifieras som phish efter leverans beror ZAP-resultatet på vilken åtgärd som har konfigurerats för en **phishing-e-postfiltreringsdom** i tillämplig policy mot skräppost. De tillgängliga filtreringsutlåtandesåtgärderna för phish och deras möjliga ZAP-resultat beskrivs i följande lista:

- **Lägg till X-Header**, **Prepend ämnesrad med text:** ZAP vidtar ingen åtgärd på meddelandet.

- **Flytta meddelande till skräppost:** ZAP flyttar meddelandet till mappen Skräppost, så länge skräppostregeln är aktiverad i postlådan (den är aktiverad som standard). Mer information finns i [Konfigurera inställningar för skräppost på Exchange Online-postlådor i Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

- **Omdirigera meddelande till e-postadress**, **Ta bort meddelande**, Karantän **meddelande:** ZAP karantän meddelandet.

Som standard är phish ZAP aktiverat i anti-spam-principer, och standardåtgärden för **phishing-e-postfiltreringsdomen** är **karantänmeddelande**, vilket innebär att phish ZAP sätter meddelandet i karantän som standard.

Mer information om hur du konfigurerar domar för skräppostfiltrering finns [i Konfigurera policyer mot skräppost i Microsoft 365](configure-your-spam-filter-policies.md).

### <a name="spam-zap"></a>Spam ZAP

För **olästa meddelanden** som identifieras som skräppost efter leverans beror ZAP-resultatet på vilken åtgärd som har konfigurerats för spam-filtreringsdomen i tillämplig anti-spam-policy. **Spam** De tillgängliga filtreringsutlåtandesåtgärderna för skräppost och deras möjliga ZAP-resultat beskrivs i följande lista:

- **Lägg till X-Header**, **Prepend ämnesrad med text:** ZAP vidtar ingen åtgärd på meddelandet.

- **Flytta meddelande till skräppost:** ZAP flyttar meddelandet till mappen Skräppost, så länge skräppostregeln är aktiverad i postlådan (den är aktiverad som standard). Mer information finns i [Konfigurera inställningar för skräppost på Exchange Online-postlådor i Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

- **Omdirigera meddelande till e-postadress**, **Ta bort meddelande**, Karantän **meddelande:** ZAP karantän meddelandet. Slutanvändare kan visa och hantera sina egna meddelanden i karantän.

Som standard är spam ZAP aktiverat i anti-spam politik, och standardåtgärden för **spam** filtrering dom är **Flytta meddelande till skräppost mapp**, vilket innebär spam ZAP flyttar **olästa** meddelanden till skräppost mappen som standard.

Mer information om hur du konfigurerar domar för skräppostfiltrering finns [i Konfigurera policyer mot skräppost i Microsoft 365](configure-your-spam-filter-policies.md).

### <a name="zap-considerations-for-office-365-advanced-threat-protection-office-365-atp"></a>ZAP-överväganden för avancerat skydd mot Office 365 (Office 365 ATP)

ZAP kommer inte att sätta något meddelande i karantän som håller på att [skannas](dynamic-delivery-and-previewing.md) dynamisk leverans, eller där filtrering av skadlig kod redan har ersatt den bifogade filen med filen **Malware Alert Text.txt.** Om en phish eller spam signal tas emot för dessa typer av meddelanden, och filtrering dom i anti-spam politik är inställd på att vidta vissa åtgärder på meddelandet (Flytta till Skräp, Omdirigera, Ta bort, Karantän) då ZAP kommer standard till en "Flytta till Skräp" åtgärd.

## <a name="how-to-see-if-zap-moved-your-message"></a>Så här ser du om ZAP har flyttat meddelandet

För att avgöra om ZAP har flyttat meddelandet kan du använda [antingen rapporten Status för hotskydd](view-email-security-reports.md#threat-protection-status-report) eller Hot Explorer [(och identifiering i realtid)](threat-explorer.md). Observera att ZAP som en systemåtgärd inte är inloggad i granskningsloggarna för Exchange-postlådan.

## <a name="zap-faq"></a>FRÅGOR OM ZAP

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a>Vad händer om ett legitimt meddelande flyttas till mappen Skräppost?

Du bör följa den normala rapporteringsprocessen för [falska positiva identifieringar](report-junk-email-messages-to-microsoft.md). Den enda anledningen till att meddelandet skulle flyttas från inkorgen till mappen Skräppost skulle bero på att tjänsten har fastställt att meddelandet var skräppost eller skadligt.

### <a name="what-if-i-use-the-quarantine-folder-instead-of-the-junk-mail-folder"></a>Vad gör jag om jag använder karantänmappen i stället för mappen Skräppost?

ZAP kommer att vidta åtgärder för ett meddelande baserat på konfigurationen din anti-spam politik som beskrivs tidigare i det här avsnittet.

### <a name="what-if-im-using-safe-senders-mail-flow-rules-or-allowedblocked-sender-lists"></a>Vad händer om jag använder betrodda avsändare, regler för e-postflöde eller tillåtna/blockerade avsändarelistor?

Betrodda avsändare, regler för e-postflöde eller blockera och tillåta organisationsinställningar har företräde. Dessa meddelanden är undantagna från ZAP eftersom tjänsten gör vad du konfigurerat den att göra. Detta är ytterligare en anledning att vara försiktig med att konfigurera meddelanden för att kringgå filtrering.

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a>Vad händer om ett meddelande flyttas till en annan mapp (t.ex. inkorgsregler)?

ZAP fungerar fortfarande så länge meddelandet inte har tagits bort, eller så länge som samma, eller starkare, åtgärder inte redan har tillämpats. Om phish-principen till exempel är inställd på karantän och användaren eller administratören redan har skräppost, kommer karantän att vidta åtgärder för att sätta filen i karantän.

### <a name="does-zap-change-the-message-header"></a>Har ZAP ändra meddelandet huvudet?

En ZAP-åtgärd gör inga ändringar i meddelandehuvudet.

### <a name="how-does-zap-affect-mailboxes-on-hold"></a>Hur påverkar ZAP postlådor som är spärrade?

ZAP sätter inte meddelanden i karantän från spärrade postlådor. ZAP kan flytta meddelanden till mappen Skräppost baserat på den åtgärd som har konfigurerats för en skräppost- eller nätfiskedom i policyer mot skräppost.

Mer information om spärrar i Exchange Online finns [i Hold and Litigation Hold i Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds).
