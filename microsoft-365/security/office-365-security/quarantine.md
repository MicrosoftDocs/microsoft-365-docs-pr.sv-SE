---
title: Karantän
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: e9eecdde-dcc2-4283-a820-98d1e740e4f
ms.collection:
- M365-security-compliance
description: Läs mer om värdbaserade karantän för Exchange Online och Exchange Online Protection.
ms.openlocfilehash: ea803a4681a12647f57cf17839d26fb391222364
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2020
ms.locfileid: "42856887"
---
# <a name="quarantine"></a>Karantän

Följande avsnitt innehåller information om den värdbaserade karantänen för både Exchange Online- och Exchange Online Protection (EOP) administratörer och slutanvändare:

- [Vanliga frågor om karantän](quarantine-faq.md) – Ger allmänna frågor och svar om karantänen för både administratörer och slutanvändare

- [Hantera meddelanden och filer i karantän som administratör i Office 365](manage-quarantined-messages-and-files.md): Beskriver hur administratörer kan hitta och släppa alla meddelanden som finns i karantänen i Administrationscenter för Exchange (EAC) och eventuellt rapportera det som ett falskt positivt meddelande (inte skräppost) till Microsoft.

- [Hitta och släpp meddelanden i karantän som användare i Office 365:](find-and-release-quarantined-messages-as-a-user.md)Beskriver hur slutanvändare kan hitta och släppa sina egna skräppostmeddelanden i användargränssnittet för skräppostkarantän och rapportera dem som inte skräppost till Microsoft.

  > [!IMPORTANT]
  > För att komma åt slutanvändarens skräppostkarant karantän måste slutanvändarna ha ett giltigt användar-ID och lösenord för Office 365. EOP-kunder som skyddar lokala postlådor måste vara giltiga e-postanvändare som skapats via katalogsynkronisering eller EAC. Mer information om hur du hanterar användare kan EOP-administratörer referera till [Hantera e-postanvändare i EOP](manage-mail-users-in-eop.md). För fristående EOP-kunder rekommenderar vi att du använder katalogsynkronisering och aktiverar katalogbaserad kantblockering. Mer information finns i [Använda katalogbaserad kantblockering för att avvisa meddelanden som skickas till ogiltiga mottagare](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking).
