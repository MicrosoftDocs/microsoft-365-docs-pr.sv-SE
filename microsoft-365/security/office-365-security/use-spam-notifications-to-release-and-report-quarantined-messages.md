---
title: Skräppostmeddelanden från slutanvändare i Office 36
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
- MET150
ms.assetid: 56de4ed5-b0aa-4195-9f46-033d7cc086bc
ms.collection:
- M365-security-compliance
description: När en administratör aktiverar skräppostmeddelanden från slutanvändare i anti-spam-principer får meddelandemottagarna regelbundna meddelanden om sina meddelanden i karantän.
ms.openlocfilehash: 67dbf311c37ae61c007b78110522033d79c0b161
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857156"
---
# <a name="end-user-spam-notifications-in-office-365"></a>Skräppostmeddelanden från slutanvändare i Office 365

Karantän innehåller potentiellt farliga eller oönskade meddelanden i Office 365-organisationer med postlådor i Exchange Online- eller fristående Exchange Online Protection -organisationer (EOP) utan Exchange Online-postlådor. Mer information finns [i Karantän i Office 365](quarantine-email-messages.md).

Som standard inaktiveras skräppostmeddelanden för slutanvändare i anti-spam-principer. När en administratör [aktiverar skräppostmeddelanden från slutanvändare](configure-your-spam-filter-policies.md)får meddelandemottagarna regelbundna meddelanden om sina meddelanden som sattes i karantän som skräppost, massmeddelanden eller (från och med april 2020) nätfiske.

> [!NOTE]
> I oktober 2019 tog vi bort möjligheten att släppa meddelanden i karantän direkt från slutanvändarnas skräppostmeddelanden. I stället kan användarna nu gå till Office 365 Security & Compliance Center för att släppa sina meddelanden i karantän (antingen direkt eller genom att klicka på **Granska** i meddelandet). Mer information finns i [Hitta och släpp meddelanden i karantän som användare i Office 365](find-and-release-quarantined-messages-as-a-user.md). <br/><br/> Meddelanden som har satts i karantän som nätfiske med högt förtroende, skadlig kod eller postflödesregler (kallas även transportregler) är endast tillgängliga för administratörer. Mer information finns i [Sök efter och släpp meddelanden i karantän som administratör i Office 365](find-and-release-quarantined-messages-as-an-administrator.md).

Ett skräppostmeddelande från slutanvändaren innehåller följande information för varje meddelande i karantän:

- **Avsändare:** Skicka namn och e-postadress för meddelandet i karantän.

- **Ämne**: Ämnesradstexten i meddelandet i karantän.

- **Datum**: Datum och tid (i UTC) som meddelandet sattes i karantän.

- **Blockera avsändare:** Klicka på den här länken om du vill lägga till avsändaren i listan Blockerade avsändare.

- **Granska:** Klicka på den här länken om du vill ansluta karantänen i säkerhets- & Compliance Center, där du kan frigöra, ta bort eller rapportera dina meddelanden i karantän.

![Exempel på skräppost anmälan från slutanvändare](../../media/end-user-spam-notification.png)
