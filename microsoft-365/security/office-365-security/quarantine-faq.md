---
title: Vanliga frågor om meddelanden i karantän
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Administratörer kan visa vanliga frågor och svar om meddelanden i karantän i Exchange Online Protection (EOP).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0d21ae67295d0186546783fd56bb602742db0649
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430853"
---
# <a name="quarantined-messages-faq"></a>Vanliga frågor om meddelanden i karantän

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Det här avsnittet innehåller vanliga frågor och svar om e-postmeddelanden i karantän för Microsoft 365-organisationer med post lådor i Exchange Online eller fristående organisationer för Exchange Online Protection (EOP) utan Exchange Online-postlådor.

Frågor och svar om skydd mot skräp post finns i [vanliga frågor om skydd mot skräp post](anti-spam-protection-faq.md).

Frågor och svar om skydd mot skadlig program vara finns i [vanliga frågor om skydd mot skadlig program vara](anti-malware-protection-faq-eop.md).

Frågor och svar om skydd mot förfalskning finns i [vanliga frågor](anti-spoofing-protection-faq.md)och svar om skydd mot förfalskning.

## <a name="how-do-i-manage-messages-that-were-quarantined-for-malware"></a>Hur hanterar jag meddelanden som satts i karantän för skadlig program vara?

Endast administratörer kan hantera meddelanden som satts i karantän för skadlig program vara. Mer information finns i [Hantera meddelanden och filer i karantän som administratör](manage-quarantined-messages-and-files.md).

## <a name="how-do-i-quarantine-spam"></a>Hur kan jag skicka skräp post?

Standardinställningen är att meddelanden som klassificeras som skräp post eller Mass utskick via skräp post skickas till användarens post låda och flyttas till mappen skräp post. Du kan till och med skapa och konfigurera principer för skräp post till Mass utskick och e-postmeddelanden. Mer information finns i [Konfigurera principer för skräppostskydd i EOP](configure-your-spam-filter-policies.md).

## <a name="how-do-i-give-users-access-to-the-quarantine"></a>Hur ger jag användare åtkomst till karantänen?

En användare måste ha ett giltigt konto för att få åtkomst till sina egna meddelanden i karantän. Fristående EOP kräver att användarna representeras som e-postanvändare i EOP (skapas eller skapas manuellt via katalog-synkronisering). Mer information om hur du hanterar användare i fristående EOP miljöer finns i [Hantera e-postanvändare i EOP](manage-mail-users-in-eop.md).

## <a name="what-messages-can-end-users-access-in-quarantine"></a>Vilka meddelanden kan användare få åtkomst till i karantän?

Användare kan få åtkomst till skräp post, Mass utskick och (från april 2020) nät fiske meddelanden där de är mottagare. Slutanvändare kan inte komma åt skadlig program vara i karantän, högsäker nät fiske eller meddelanden som satts i karantän på grund av att **meddelandet levererades till den värdbaserade karantäns** åtgärden i regler för e-postflöde (kallas även transport regler). Mer information om användare som har åtkomst till karantän meddelanden finns i [hitta och släppa meddelanden i karantän som en användare](find-and-release-quarantined-messages-as-a-user.md).

## <a name="how-long-are-messages-kept-in-the-quarantine"></a>Hur länge lagras meddelanden i karantänen?

Du kan konfigurera hur länge skräp post, nät fiske och Mass utskick av e-post ska sparas i karantänen genom att använda principer för skräp post. Standardvärdet är 30 dagar, vilket också är det största. Mer information finns i [Konfigurera principer för skräp post meddelanden i EOP](configure-your-spam-filter-policies.md)

För meddelanden som har placerats i karantän av åtgärden för e-postflödes regeln **skickas meddelandet till den värdbaserade karantänen**, men meddelandena bevaras i karantän i 30 dagar. Du kan inte konfigurera varaktigheten.

När tids perioden går ut tas meddelanden bort och kan inte återställas.

## <a name="can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a>Kan jag släppa eller rapportera mer än ett meddelande i karantän åt gången?

I säkerhets & Compliance Center kan du välja och släppa upp till 100 meddelanden åt gången.

Administratörer kan använda cmdletarna [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) och [release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) i Exchange Online PowerShell eller fristående EOP PowerShell för att hitta och släppa upp insatta meddelanden i gruppen, samt för att rapportera falsk positiv identifiering i bulk.

## <a name="are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a>Stöds jokertecken vid sökning efter meddelanden i karantän? Kan jag söka efter meddelanden i karantän för en viss domän?

Jokertecken stöds inte i säkerhets & Compliance Center. Om du till exempel söker efter en avsändare måste du ange den fullständiga e-postadressen. Men du kan använda jokertecken i Exchange Online PowerShell eller fristående EOP PowerShell.

Kör till exempel följande kommando för att hitta skräp post i karantänen från alla avsändare i domänen contoso.com:

```powershell
$CQ = Get-QuarantineMessage -Type Spam | where {$_.SenderAddress -like "*@contoso.com"}
```

Kör sedan följande kommando för att släppa dessa meddelanden till alla ursprungliga mottagare:

```powershell
$CQ | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}
```

När du har släppt ett meddelande kan du inte frigöra det igen.
