---
title: Betrodd avsändare och blockerade avsändarlistor i Exchange Online
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 111ab6b0-2dd2-4a87-a928-4931df6b3c4d
ms.collection:
- M365-security-compliance
description: Som eop-administratör (Exchange Online eller Exchange Online Protection) kan du se till att ett e-postmeddelande som färdas via tjänsten inte markeras som skräppost. Ett sätt att göra detta är att skapa en säker avsändare och blockerade avsändarlistor för personerna i organisationen.
ms.openlocfilehash: 959af558c32e71e5a4cede2aff7bbcd1dbb092e2
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42806049"
---
# <a name="safe-sender-and-blocked-sender-lists-in-exchange-online"></a>Betrodd avsändare och blockerade avsändarlistor i Exchange Online

Som eop-administratör (Exchange Online eller Exchange Online Protection) kan du se till att ett e-postmeddelande som färdas via tjänsten inte markeras som skräppost. Ett sätt att göra detta är att skapa en säker avsändare och blockerade avsändarlistor för personerna i organisationen.

*Se den uppdaterade versionen av tipsen och procedurerna för hur du arbetar med dessa listor som administratör i* Så här förhindrar du att bra [e-post markeras som skräppost i Office 365](prevent-email-from-being-marked-as-spam.md).

Om du inte är administratör och bara vill hantera din egen skräppost i Outlook med hjälp av en lista över betrodda avsändare kan du läsa stegen i[översikten över skräppostfiltret](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089).

## <a name="what-is-the-safe-and-blocked-sender-limits-in-exchange-online"></a>Vilka är de säkra och blockerade avsändargränserna i Exchange Online?

De säkra och blockerade avsändargränserna i Exchange Online skiljer sig från Active Directory- och Outlook-gränserna. De är:

- Säker avsändare gräns: 1.024

- Spärrad avsändaregräns: 500

Obs!

Felet som beskrivs i [KB2590466](https://support.microsoft.com/help/2590466/you-receive-the-error-junk-e-mail-validation-error-in-outlook-web-app)kan uppstå. LÃ¶s problemet genom att avmarkera kryssrutan "Betrodda e-postmeddelanden frÃ¥n mina kontakter". Du kan också minska mängden e-postadresser som finns i standardmappen Kontakter för att få den inom den högsta tillåtna gränsen på 1024 i Exchange Online som är inställt för attributet "MaxSafeSenders". Mer information om det här attributet och cmdleten Ange postlåda finns i följande avsnitt:

[Ange postlåda](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox)

## <a name="see-also"></a>Se även

[Avsändaresfiltrering i Exchange Server](https://docs.microsoft.com/exchange/antispam-and-antimalware/antispam-protection/sender-filtering)
