---
title: E-postmeddelanden i karantän
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
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
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan lära sig mer om karantän i Exchange Online Protection (EOP) som innehåller potentiellt farliga eller oönskade meddelanden.
ms.openlocfilehash: 71a5f32fe6888d751bf2c4020fca4df671ac96d1
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208288"
---
# <a name="quarantined-email-messages-in-eop"></a>E-postmeddelanden i karantän i EOP

I Microsoft 365-organisationer med postlådor i Exchange Online- eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor är karantän tillgänglig för att lagra potentiellt farliga eller oönskade meddelanden.

Policyer mot skadlig kod sätter automatiskt ett meddelande i karantän om *någon* bifogad fil visar sig innehålla skadlig kod. Mer information finns i [Konfigurera principer mot skadlig kod i EOP](configure-anti-malware-policies.md).

Som standard, anti-spam polisen karantän phishing-meddelanden, och leverera skräppost och bulk e-postmeddelanden till användarens skräppostmapp. Men du kan också skapa och anpassa anti-spam-policyer för att sätta skräppost och massmeddelanden i karantän. Mer information finns [i Konfigurera principer mot skräppost i EOP](configure-your-spam-filter-policies.md).

Både användare och administratörer kan arbeta med meddelanden i karantän:

- Administratörer kan arbeta med alla typer av meddelanden i karantän för alla användare. Endast administratörer kan arbeta med meddelanden som har satts i karantän som skadlig kod, nätfiske med högt förtroende eller som ett resultat av regler för e-postflöde (kallas även transportregler). Mer information finns i [Hantera meddelanden och filer i karantän som administratör i EOP](manage-quarantined-messages-and-files.md).

- Användare kan arbeta med meddelanden i karantän där de är mottagare om meddelandet har satts i karantän som skräppost, massmeddelande eller (från och med april 2020) nätfiske. Mer information finns i [Hitta och släppa meddelanden i karantän som användare i EOP](find-and-release-quarantined-messages-as-a-user.md).

  För att förhindra att användare hanterar sina egna nätfiskemeddelanden i karantän kan administratörer konfigurera en annan åtgärd för **e-nätfiskefiltreringsdomen** i policyer för skräppostskydd. Mer information finns [i Konfigurera principer mot skräppost i EOP](configure-your-spam-filter-policies.md).

- Administratörer och användare kan rapportera falska positiva identifieringar till Microsoft i karantän.

Mer information om, karantän finns i [Vanliga frågor och svar](quarantine-faq.md)om karantän i karantän .
