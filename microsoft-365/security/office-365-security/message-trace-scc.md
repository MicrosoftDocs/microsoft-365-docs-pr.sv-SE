---
title: Meddelandespårning i Microsoft 365 Defender portalen
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 3e64f99d-ac33-4aba-91c5-9cb4ca476803
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan använda länken för meddelandespårning i e Microsoft 365 Defender portalen för att ta reda på vad som har hänt med meddelandena.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f7b6f7b12086e46c6ad93b60e8c510ea533815a1
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108133"
---
# <a name="message-trace-in-the-microsoft-365-defender-portal"></a>Meddelandespårning i Microsoft 365 Defender portalen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Meddelandespårning i Microsoft 365 Defender e-postmeddelanden när de färdas genom din Exchange Online organisation. Du kan avgöra om ett meddelande har tagits emot, avvisats, skjutits upp eller levererats av tjänsten. Det visar också vilka åtgärder som har vidtagits för meddelandet innan det nått sin slutgiltiga status.

Du kan använda informationen från meddelandespårning för att effektivt svara på användarfrågor om vad som har hänt med meddelanden, felsöka problem i e-postflödet och verifiera principändringar.

> [!NOTE]
> Meddelandespårning i Microsoft 365 Defender-portalen går bara vidare till Meddelandespårning i Exchange administrationscenter. Mer information finns i [Meddelandespårning i det moderna Exchange administrationscentret.](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Du måste vara medlem i rollgrupperna **Organisationshantering,** Efterlevnadshantering eller Supportavdelning i Exchange Online **använda** meddelandespårning.   Mer information finns under [Behörigheter i Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Kommentarer:** Medlemskap i motsvarande Azure Active Directory roll i Administrationscenter för Microsoft 365 ger användarna  nödvändiga behörigheter och behörigheter för andra funktioner i Microsoft 365. Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).

- Det maximala antalet meddelanden som visas i resultatet av en meddelandespårning beror på vilken rapporttyp du valde (mer information finns i avsnittet [Välj](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac#choose-report-type) rapporttyp). [Cmdlet:en Get-HistoricalSearch](/powershell/module/exchange/get-historicalsearch) i Exchange Online PowerShell eller fristående EOP PowerShell returnerar alla meddelanden i resultatet.

## <a name="open-message-trace"></a>Öppna meddelandespårning

I portalen Microsoft 365 Defender ( <https://security.microsoft.com> ) går du till Skicka **e-& samarbete** \> **Exchange meddelandespårning**. Du kan också använda för att gå direkt till sidan <https://admin.exchange.microsoft.com/#/messagetrace> Meddelandespårning.

I det här läget öppnas meddelandespårning i EAC. Mer information finns i [Meddelandespårning i det moderna Exchange administrationscentret.](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac)
