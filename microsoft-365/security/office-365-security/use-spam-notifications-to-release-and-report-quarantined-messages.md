---
title: Skräppostmeddelanden för slutanvändare i Office 36
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
description: När en administratör aktiverar skräppostmeddelanden för slutanvändare i policyer mot skräppost får mottagarna av meddelanden periodiska meddelanden om sina meddelanden i karantän.
ms.openlocfilehash: 6cde4681d7ea3ef5795201e9a2816b7224ad36f6
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895065"
---
# <a name="end-user-spam-notifications-in-office-365"></a>Skräppostmeddelanden för slutanvändare i Office 365

Karantänen innehåller potentiellt farliga eller oönskade meddelanden i Office 365-organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor. Mer information finns [i Karantän i Office 365](quarantine-email-messages.md).

Som standard inaktiveras skräppostmeddelanden för slutanvändare i policyer mot skräppost. När en administratör [aktiverar skräppostmeddelanden](configure-your-spam-filter-policies.md)för slutanvändare får meddelandemottagarna regelbundna meddelanden om sina meddelanden som har satts i karantän som skräppost, massmeddelande eller (från och med april 2020) nätfiske.

> [!NOTE]
> I oktober 2019 tog vi bort möjligheten att släppa meddelanden i karantän direkt från skräppostmeddelanden från slutanvändaren. I stället kan användare nu gå till Office 365 Security & Compliance Center för att släppa sina meddelanden i karantän (antingen direkt eller genom att klicka på **Granska** i meddelandet). Mer information finns i [Hitta och släppa meddelanden i karantän som användare i Office 365](find-and-release-quarantined-messages-as-a-user.md). <br/><br/> Meddelanden som har satts i karantän som nätfiske, skadlig kod eller via regler för e-postflöde (kallas även transportregler) är endast tillgängliga för administratörer. Mer information finns i [Hantera meddelanden och filer i karantän som administratör i Office 365](manage-quarantined-messages-and-files.md).

Ett skräppostmeddelande för slutanvändare innehåller följande information för varje meddelande i karantän:

- **Avsändare**: Skicka namn och e-postadress för det i karantänmeddelandet.

- **Ämne**: Ämnesradens text i det i karantänsmeddelandet.

- **Datum**: Datum och tid (i UTC) som meddelandet sattes i karantän.

- **Blockera avsändare:** Klicka på den här länken om du vill lägga till avsändaren i listan Blockerade avsändare.

- **Granska**: Klicka på den här länken om du vill gå till karantänen i Security & Compliance Center, där du kan släppa, ta bort eller rapportera dina meddelanden i karantän.

![Exempel på skräppostmeddelanden för slutanvändare](../../media/end-user-spam-notification.png)
