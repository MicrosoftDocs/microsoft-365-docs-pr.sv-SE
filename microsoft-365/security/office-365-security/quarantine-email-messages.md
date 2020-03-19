---
title: Karantänmeddelanden i Office 365
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 4c234874-015e-4768-8495-98fcccfc639b
ms.collection:
- M365-security-compliance
description: Karantän i Office 365 innehåller potentiellt farliga eller oönskade meddelanden. Administratörer och slutanvändare kan komma åt karantän.
ms.openlocfilehash: 9c82ba9821c42fe6c3dd78dbcecf63327d176e93
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857315"
---
# <a name="quarantine-in-office-365"></a>Karantän i Office 365

Om du är en Office 365-kund med postlådor i Exchange Online eller en fristående Exchange Online Protection-kund (EOP) utan Exchange Online-postlådor, är karantän tillgänglig för att lagra potentiellt farliga eller oönskade meddelanden.

Policyer mot skadlig kod sätter automatiskt ett meddelande i karantän om *någon* bifogad fil visar sig innehålla skadlig kod. Mer information finns [i Konfigurera principer mot skadlig kod i Office 365](configure-anti-malware-policies.md).

Som standard, anti-spam polisen karantän phishing-meddelanden, och leverera skräppost och bulk e-postmeddelanden till användarens skräppostmapp. Men du kan också skapa och anpassa anti-spam-policyer för att sätta skräppost och massmeddelanden i karantän. Mer information finns [i Konfigurera principer mot skräppost i Office 365](configure-your-spam-filter-policies.md).

Både användare och administratörer kan arbeta med meddelanden i karantän:

- Administratörer kan arbeta med alla typer av meddelanden i karantän för alla användare. Endast administratörer kan arbeta med meddelanden som har satts i karantän som skadlig kod, nätfiske med högt förtroende eller som ett resultat av regler för e-postflöde (kallas även transportregler). Mer information finns i [Hantera meddelanden och filer i karantän som administratör i Office 365](manage-quarantined-messages-and-files.md).

- Användare kan arbeta med meddelanden i karantän där de är mottagare om meddelandet har satts i karantän som skräppost, massmeddelande eller (från och med april 2020) nätfiske. Mer information finns i [Hitta och släppa meddelanden i karantän som användare i Office 365](find-and-release-quarantined-messages-as-a-user.md).

  För att förhindra att användare hanterar sina egna nätfiskemeddelanden i karantän kan administratörer konfigurera en annan åtgärd för **e-nätfiskefiltreringsdomen** i policyer för skräppostskydd. Mer information finns [i Konfigurera principer mot skräppost i Office 365](configure-your-spam-filter-policies.md).

- Administratörer och användare kan rapportera falska positiva identifieringar till Microsoft i karantän.

Mer information om, karantän finns i [Vanliga frågor och svar](quarantine-faq.md)om karantän i karantän .
