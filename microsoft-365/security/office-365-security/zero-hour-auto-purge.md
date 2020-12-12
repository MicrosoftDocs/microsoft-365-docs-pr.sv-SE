---
title: Autorensning för nollor (ZAP)
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
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
description: Administratörer kan lära sig hur nollställning av automatisk rensning (ZAP) kan flytta levererade meddelanden retroaktivt i en Exchange Online-postlåda till mappen skräp post eller karantän som kan vara skräp post eller nätfiske.
ms.openlocfilehash: 7b43fb46adacfe1e9f1e7e622122df90e747ff44
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659435"
---
# <a name="zero-hour-auto-purge-zap-in-exchange-online"></a>Automatisk rensning av nollor (ZAP) i Exchange Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="basic-features-of-zap"></a>Grundläggande funktioner i ZAP

I Microsoft 365-organisationer med post lådor i Exchange Online, är nollställning autorensning en e-postskydds funktion som upptäcker och neutraliserar skadlig nät fiske, skräp post eller skadliga meddelanden som redan har levererats till Exchange Online-postlådor.

ZAP fungerar inte i fristående Exchange Online Protection-miljöer (EOP) som skyddar lokala Exchange-postlådor.

## <a name="how-zap-works"></a>Så fungerar ZAP

Alla signaturer för skräp post och skadlig program vara uppdateras i real tid per dag. Men användare kan ändå ta emot skadliga meddelanden av olika anledningar, inklusive om innehållet är lite fritt efter att du har levererats till användarna. ZAP löser det här problemet genom att fort löp ande övervaka uppdateringar av signaturer för skräp post och skadlig program vara i tjänsten. ZAP kan hitta och ta bort meddelanden som redan finns i en användares post låda.

Åtgärden ZAP är sömlös för användaren. de meddelas inte om ett meddelande identifieras och flyttas.

[Listor för betrodda avsändare](create-safe-sender-lists-in-office-365.md), regler för e-postflöde (kallas även transport regler), regler för Inkorgen eller ytterligare filter har högre prioritet än ZAP. På samma sätt som i e-postflödet innebär det att även om tjänsten bestämmer det leverans behov som krävs för att skicka meddelandet, kan meddelandet inte aktive ras på grund av konfigurationen för betrodda avsändare. Det här är en annan anledning till att vara försiktig när du konfigurerar meddelanden för att kringgå filtrering.

### <a name="malware-zap"></a>Malware, ZAP

För **lästa och olästa meddelanden** som visar att det finns skadlig kod efter leverans får du ett meddelande som innehåller den bifogade filen. Endast administratörer kan visa och hantera meddelanden om skadlig program vara från karantän.

Malware, ZAP är aktiverat som standard i principer mot skadlig program vara. Mer information finns i [Konfigurera principer för skydd mot skadlig program vara i EOP](configure-anti-malware-policies.md).

### <a name="phish-zap"></a>Phish ZAP

För **lästa och olästa meddelanden** som identifieras som nätfiske efter leveransen beror ZAP-resultatet av den åtgärd som är konfigurerad för en Verdict för **nätfiske** . De tillgängliga Verdict-åtgärderna för filtrering för nätfiske och deras potentiella ZAP-resultat beskrivs i följande lista:

- **Lägga till X-rubrik**, **före ämnesrad med text**: ZAP gör ingen åtgärd för meddelandet.

- **Flytta meddelande till skräp post**: ZAP flyttar meddelandet till mappen skräp post så länge skräp post regeln är aktive rad på post lådan (den är aktive rad som standard). Mer information finns i [Konfigurera inställningar för skräp post i Exchange Online-postlådor i Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

- **Omdirigera meddelande till e-postadress**, **ta bort meddelande**, **karantän meddelande**: ZAP karantänen.

Phish ZAP är som standard aktive rad i principer för skräp post och standard åtgärden för Verdict för **nät fiske** meddelanden är **karantän meddelande**, vilket innebär att Phish ZAP mellanstår meddelandet som standard.

Mer information om hur du konfigurerar verdicts för skräp post finns i [Konfigurera principer för skräp post filtrering i Microsoft 365](configure-your-spam-filter-policies.md).

### <a name="spam-zap"></a>Spam

För **olästa meddelanden** som identifieras som skräp post efter leverans beror ZAP-resultatet av den åtgärd som är konfigurerad för filtrering av **skräp post** filter i den aktuella principen för skräp post Verdict. De tillgängliga Verdict-åtgärderna för filtrering av skräp post och deras möjliga ZAP-resultat beskrivs i följande lista:

- **Lägga till X-rubrik**, **före ämnesrad med text**: ZAP gör ingen åtgärd för meddelandet.

- **Flytta meddelande till skräp post**: ZAP flyttar meddelandet till mappen skräp post så länge skräp post regeln är aktive rad på post lådan (den är aktive rad som standard). Mer information finns i [Konfigurera inställningar för skräp post i Exchange Online-postlådor i Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

- **Omdirigera meddelande till e-postadress**, **ta bort meddelande**, **karantän meddelande**: ZAP karantänen. Slutanvändare kan visa och hantera sina egna meddelanden i Inkorgen.

Som standard är skräppost-ZAP aktiverat i principer för skräp post, och standard åtgärden för **skräp** post filtrering Verdict är **att flytta meddelandet till mappen skräp post**, vilket innebär att skräp posten är som standard **avläst** meddelanden till mappen skräp post.

Mer information om hur du konfigurerar verdicts för skräp post finns i [Konfigurera principer för skräp post filtrering i Microsoft 365](configure-your-spam-filter-policies.md).

### <a name="zap-considerations-for-microsoft-defender-for-office-365"></a>ZAP-överväganden för Microsoft Defender för Office 365

ZAP kommer inte att placera något meddelande som bearbetas i processen för [dynamisk leverans](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies) i den säkra bilage genomsökningen eller där EOP malware filter redan har ersatt bilagan med **varnings meddelandet Text.txt** -filen. Om en nätfiske eller skräp post tas emot för dessa typer av meddelanden och filtrerings Verdict i policyn för skräp post är inställd på att vidta vissa åtgärder på meddelandet (flytta till skräp post, omdirigering, ta bort eller karantän) återställs den till åtgärden "flytta till skräp post".

## <a name="how-to-see-if-zap-moved-your-message"></a>Så här ser du om ZAP har flyttat ditt meddelande

Om du vill ta reda på om ZAP har flyttat ditt meddelande kan du använda antingen [status rapport](view-email-security-reports.md#threat-protection-status-report) eller hot kontroll i [real tid](threat-explorer.md). Observera att ZAP inte loggas i gransknings loggarna för Exchange-postlådan.

## <a name="zap-faq"></a>VANLIGA FRÅGOR OM ZAP

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a>Vad händer om ett legitimt meddelande flyttas till mappen skräp post?

Du bör följa den vanliga rapporterings processen för [falska positiva](report-junk-email-messages-to-microsoft.md)verifieringar. Det enda skälet till att meddelandet flyttas från inkorgen till mappen skräp post, eftersom tjänsten har fastställt att meddelandet har tagits bort eller är skadligt.

### <a name="what-if-i-use-the-quarantine-folder-instead-of-the-junk-mail-folder"></a>Vad händer om jag använder mappen karantän i stället för mappen skräp post?

ZAP utför en åtgärd på ett meddelande baserat på konfigurationen för skydd mot skräp post enligt beskrivningen ovan.

### <a name="what-if-im-using-safe-senders-mail-flow-rules-or-allowedblocked-sender-lists"></a>Vad händer om jag använder betrodda avsändare, e-postflödes regler eller tillåtna/blockerade avsändar listor?

Säkra avsändare, regler för e-postflöde eller blockering och Tillåt organisations inställningar gäller. Dessa meddelanden är exkluderade från ZAP eftersom tjänsten gör det du konfigurerade att göra. Det här är en annan anledning till att vara försiktig när du konfigurerar meddelanden för att kringgå filtrering.

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a>Vad händer om ett meddelande flyttas till en annan mapp (till exempel regler för Inkorgen)?

ZAP fungerar fortfarande så länge meddelandet inte har tagits bort, eller så länge det finns en åtgärd som inte redan har använts. Om du till exempel har ställt in en karantän och ett meddelande redan finns i skräp posten vidtar ZAP åtgärd för att sätta in ett karantän meddelande.

### <a name="how-does-zap-affect-mailboxes-on-hold"></a>Hur påverkar ZAP post lådor?

ZAP startar inte karantän meddelanden från post lådor med undantag. ZAP kan flytta meddelanden till mappen skräp post baserat på den åtgärd som har kon figurer ATS för skräp post eller nätfiske-Verdict i policyer för borttagning.

Mer information om undantag i Exchange Online finns [i-platsens undantag och rättsliga undantag i Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds).
