---
title: E-postmeddelanden i karantän
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 4c234874-015e-4768-8495-98fcccfc639b
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan läsa mer om karantän i Exchange Online Protection (EOP) som kan vara skadlig eller oönskade meddelanden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bd748871cc09905f9878d5917351b1c185cc1106
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207158"
---
# <a name="quarantined-email-messages-in-eop"></a>E-postmeddelanden i karantän i EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

I Microsoft 365-organisationer som har postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor är karantän tillgänglig för potentiellt skadliga eller oönskade meddelanden.

Principer för skydd mot skadlig programvara sätt automatiskt ett meddelande i karantän *om en* bifogad fil påträffas som innehåller skadlig programvara. Mer information finns i Konfigurera [principer för skydd mot skadlig programvara i EOP.](configure-anti-malware-policies.md)

Som standard sätts skräppostprinciper i karantän för nätfiskemeddelanden och skickar skräppost och massutskick till användarens skräppostmapp. Men du kan också skapa och anpassa principer för skräppostskydd för att sätta skräppost i karantän och massutskick. Mer information finns i [Konfigurera principer för skräppostskydd i EOP](configure-your-spam-filter-policies.md).

Både användare och administratörer kan arbeta med meddelanden i karantän:

- Administratörer kan arbeta med alla typer av meddelanden i karantän för alla användare. Endast administratörer kan arbeta med meddelanden som har satts i karantän som skadlig kod, nätfiske med hög säkerhet eller som ett resultat av e-postflödesregler (kallas även transportregler). Mer information finns i [Hantera meddelanden och filer i karantän som administratör i EOP](manage-quarantined-messages-and-files.md).

- Användare kan arbeta med meddelanden i karantän där de är mottagare om meddelandet satts i karantän som skräppost, massutskick eller nätfiske (från och med april 2020). Mer information finns i [Hitta och släppa meddelanden i karantän som en användare i EOP.](find-and-release-quarantined-messages-as-a-user.md)

  För att hindra användare från att hantera sina egna nätfiskemeddelanden  i karantän kan administratörer konfigurera en annan åtgärd för filtrering av nätfiske-e-postmeddelanden med filtrering av skräppost. Mer information finns i [Konfigurera principer för skräppostskydd i EOP](configure-your-spam-filter-policies.md).

- Administratörer och användare kan rapportera falska positiva resultat till Microsoft i karantän.

Mer information om karantän finns i Vanliga frågor [och svar om karantän.](quarantine-faq.md)
