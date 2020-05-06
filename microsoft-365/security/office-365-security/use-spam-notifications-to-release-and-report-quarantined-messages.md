---
title: Skräppostmeddelanden för slutanvändare i Microsoft 365
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
ms.custom:
- seo-marvel-apr2020
description: I den här artikeln får du lära dig mer om skräppostmeddelanden för slutanvändare för meddelanden i karantän.
ms.openlocfilehash: 2a865130bf1fa0c09b5b68254fb604795b204c22
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035004"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a>Använda skräppostmeddelanden för att släppa och rapportera meddelanden i karantän

Karantänen lagrar potentiellt farliga eller oönskade meddelanden i Microsoft 365-organisationer med postlådor i Exchange Online eller fristående Exchange Online Protection-organisationer (EOP) utan Exchange Online-postlådor. Mer information finns i [Karantän i Office 365](quarantine-email-messages.md).

Som standard inaktiveras skräppostmeddelanden för slutanvändare i policyer mot skräppost. När en administratör [aktiverar skräppostmeddelanden](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)för slutanvändare får mottagarna regelbundna meddelanden om sina meddelanden som har satts i karantän som skräppost, massmeddelande eller (från och med april 2020) nätfiske.

> [!NOTE]
> Meddelanden som har satts i karantän som nätfiske, skadlig kod eller via regler för e-postflöde (kallas även transportregler) är endast tillgängliga för administratörer. Mer information finns i [Hantera meddelanden och filer i karantän som administratör i Office 365](manage-quarantined-messages-and-files.md).

Ett skräppostmeddelande för slutanvändare innehåller följande information för varje meddelande i karantän:

- **Avsändare**: Skicka namn och e-postadress för det i karantänmeddelandet.

- **Ämne**: Ämnesradens text i det i karantänsmeddelandet.

- **Datum**: Datum och tid (i UTC) som meddelandet sattes i karantän.

- **Blockera avsändare:** Klicka på den här länken om du vill lägga till avsändaren i listan Blockerade avsändare. Mer information finns i [Blockera en e-postavsändare i Outlook](https://support.office.com/article/b29fd867-cac9-40d8-aed1-659e06a706e4).

- **Släpp:** För spam (inte phish) meddelanden, kan du släppa meddelandet här utan att gå till Karantän Security & Compliance Center.

- **Granska**: Klicka på den här länken om du vill gå till Karantän i Security & Compliance Center, där du kan släppa, ta bort eller rapportera dina meddelanden i karantän. Mer information finns i [Hitta och släppa meddelanden i karantän som användare i Office 365](find-and-release-quarantined-messages-as-a-user.md).

![Exempel på skräppostmeddelanden för slutanvändare](../../media/end-user-spam-notification.png)
