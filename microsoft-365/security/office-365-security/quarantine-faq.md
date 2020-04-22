---
title: Vanliga frågor och svar om karantän
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
description: Svar på vanliga frågor om karantän i Office 365.
ms.openlocfilehash: 3947fbed2a17380a18320a8bffd08a8178ad2b3f
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634430"
---
# <a name="quarantine-faq"></a>Vanliga frågor och svar om karantän

Det här avsnittet innehåller vanliga frågor och svar om karantän för Microsoft 365-kunder med postlådor i Exchange Online- eller fristående Exchange Online Protection-kunder (EOP) utan Exchange Online-postlådor.

## <a name="q-how-do-i-manage-messages-that-were-quarantined-for-malware"></a>F: Hur hanterar jag meddelanden som har satts i karantän för skadlig kod?

Endast administratörer kan hantera meddelanden som har satts i karantän för skadlig kod. Mer information finns i [Hantera meddelanden och filer i karantän som administratör i Office 365](manage-quarantined-messages-and-files.md).

## <a name="q-how-do-i-quarantine-spam"></a>F: Hur sätter jag skräppost i karantän?

A. Som standard levereras meddelanden som klassificeras som skräppost eller massutskick via skräppostfiltrering till användarens postlåda och flyttas till mappen Skräppost. Men du kan skapa och konfigurera anti-spam-principer för att sätta skräppost eller massmeddelanden i karantän i stället. Mer information finns i [konfigurera anti-spam-policyer i Office 365](configure-your-spam-filter-policies.md).

## <a name="q-how-do-i-give-users-access-to-the-quarantine"></a>F: Hur ger jag användarna åtkomst till karantänen?

A. En användare måste ha ett giltigt konto för att få åtkomst till sina egna meddelanden i karantän. Fristående EOP kräver att användare representeras som e-postanvändare i EOP (skapas eller skapas manuellt via katalogsynkronisering). Mer information om hur du hanterar användare i fristående EOP-miljöer finns [i Hantera e-postanvändare i EOP](manage-mail-users-in-eop.md).

## <a name="q-what-messages-can-end-users-access-in-quarantine"></a>F: Vilka meddelanden kan slutanvändare komma åt i karantän?

A. Användare kan komma åt skräppost, massmeddelanden och (från och med april 2020) nätfiskemeddelanden där de är mottagare. Slutanvändare kan inte komma åt skadlig kod i karantän, nätfiske med högt förtroende eller meddelanden som har satts i karantän på grund av **meddelandet Leverera meddelandet till den värdbaserade karantänåtgärden** i regler för e-postflöde (kallas även transportregler). Mer information om användare som använder meddelanden i karantän finns i [Hitta och släppa meddelanden i karantän som användare i Office 365](find-and-release-quarantined-messages-as-a-user.md).

## <a name="q-how-long-are-messages-kept-in-the-quarantine"></a>F: Hur länge hålls meddelanden i karantän?

A. Du kan konfigurera hur länge skräppost, nätfiske och massmeddelanden hålls i karantän med hjälp av policyer mot skräppost. Standardvärdet är 30 dagar, vilket också är det maximala. Mer information finns [i Konfigurera principer mot skräppost i Office 365](configure-your-spam-filter-policies.md)

För meddelanden som har satts i karantän av e-postflödesregelåtgärden **Leverera meddelandet till den värdbaserade karantänen**hålls meddelandena i karantän i 30 dagar. Du kan inte konfigurera den här varaktigheten.

När tidsperioden har gått ut tas meddelandena bort och kan inte återställas.

## <a name="q-can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a>F: Kan jag släppa eller rapportera mer än ett meddelande i karantän åt gången?

A. I Security & Compliance Center kan du välja och släppa upp till 100 meddelanden åt gången.

Administratörer kan använda cmdleterna [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage) och [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) i Exchange Online PowerShell eller fristående Exchange Online Protection PowerShell för att hitta och släppa meddelanden i karantän i grupp och för att rapportera falska positiva identifieringar i grupp.

## <a name="q-are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a>F: Stöds jokertecken när du söker efter meddelanden i karantän? Kan jag söka efter meddelanden i karantän för en viss domän?

A. Jokertecken stöds inte i Security & Compliance Center. När du till exempel söker efter en avsändare måste du ange den fullständiga e-postadressen. Men du kan använda jokertecken i Exchange Online PowerShell eller Exchange Online Protection PowerShell.

Kör till exempel följande kommando för att hitta skräppostmeddelanden i karantän från alla avsändare i domänen contoso.com:

```powershell
$CQ = Get-QuarantineMessage -Type Spam | where {$_.SenderAddress -like "*@contoso.com"}
```

Kör sedan följande kommando för att släppa dessa meddelanden till alla ursprungliga mottagare:

```powershell
$CQ | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}
```

När du har släppt ett meddelande kan du inte släppa det igen.
