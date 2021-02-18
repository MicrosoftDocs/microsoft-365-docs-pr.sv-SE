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
description: Administratörer kan lära sig mer om karantän i Exchange Online Protection (EOP) som kan hålla skadliga eller oönskade meddelanden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 47742008af9c1cd0a0a17df9e43ebc0228a825b0
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288771"
---
# <a name="quarantined-email-messages-in-eop"></a>E-postmeddelanden i karantän i EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående Exchange Online Protection (EOP) utan Exchange Online-postlådor är karantän tillgänglig för potentiellt farligt eller oönskade meddelanden.

Mot skadlig programvara sätts ett meddelande i karantän automatiskt om *en* bifogad fil innehåller skadlig programvara. Mer information finns i Konfigurera [principer för skadlig programvara i EOP.](configure-anti-malware-policies.md)

Som standard sätts nätfiskemeddelanden i karantän och du får skräppost och massutskick till användarens skräppostmapp. Men du kan också skapa och anpassa principer för skräppostskydd för att sätta skräppost i karantän och massutskick. Mer information finns i [Konfigurera principer för skräppostskydd i EOP](configure-your-spam-filter-policies.md).

Både användare och administratörer kan arbeta med meddelanden i karantän:

- Administratörer kan arbeta med alla typer av meddelanden i karantän för alla användare. Endast administratörer kan arbeta med meddelanden som har satts i karantän som skadlig kod, nätfiske med hög konfidens eller som ett resultat av e-postflödesregler (kallas även transportregler). Mer information finns i [Hantera meddelanden och filer i karantän som administratör i EOP](manage-quarantined-messages-and-files.md).

- Användare kan arbeta med meddelanden i karantän där de är mottagare om meddelandet har satts i karantän som skräppost, massutskick eller (från och med april 2020) nätfiske. Mer information finns i [Hitta och släppa meddelanden i karantän som användare i EOP.](find-and-release-quarantined-messages-as-a-user.md)

  Administratörer kan konfigurera en annan åtgärd för filtrering av nätfiskemeddelanden  i karantän för att hindra användare från att hantera sina egna nätfiskemeddelanden. Mer information finns i [Konfigurera principer för skräppostskydd i EOP](configure-your-spam-filter-policies.md).

- Administratörer och användare kan rapportera falska positiva resultat till Microsoft i karantän.

Mer information om karantän finns i Vanliga frågor [och svar om karantän.](quarantine-faq.md)
