---
title: Skräppost-aviseringar för slutanvändare i Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
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
description: Administratörer kan läsa mer om skräppost-aviseringar för slutanvändare för meddelanden i karantän i Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9cff91be399bd98eb7e6e5a2a6d91a4a8bb602ec
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51069905"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a>Använda skräppost-aviseringar för användare för att släppa och rapportera meddelanden i karantän

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående Exchange Online Protection-organisationer (EOP) utan Exchange Online-postlådor lagrar karantänen potentiellt farliga eller oönskade meddelanden. Mer information finns i [Meddelanden i karantän i EOP.](quarantine-email-messages.md)

Som standard är skräppost-aviseringar för slutanvändare inaktiverade i principerna för skräppostskydd. När en administratör aktiverar [skräppost-aviseringar](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)för slutanvändare får mottagare (inklusive delade postlådor med automatisk mappning aktiverat) periodiska aviseringar om meddelanden som har satts i karantän som skräppost, massutskick eller (från och med april 2020) nätfiske.

För delade postlådor stöds skräppost-aviseringar för slutanvändare endast för användare som får behörigheten FullAccess till den delade postlådan. Mer information finns i Använda [EAC för att redigera delegering av delad postlåda.](/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation)

Skräppost-avisering för slutanvändare stöds inte för grupper.

> [!NOTE]
> Meddelanden som har satts i karantän som nätfiske, skadlig kod eller genom e-postflödesregler (kallas även transportregler) är bara tillgängliga för administratörer. Mer information finns i [Hantera meddelanden och filer i karantän som administratör i EOP](manage-quarantined-messages-and-files.md).

En skräppost-avisering för slutanvändaren innehåller följande information för varje meddelande i karantän:

- **Avsändare**: Skicka meddelandets namn och e-postadress.

- **Ämne**: Ämnesraden i det i karantän-meddelandet.

- **Datum:** Datum och tid (i UTC) då meddelandet satt i karantän.

- **Spärra avsändare:** Klicka på den här länken om du vill lägga till avsändaren i listan Spärrade avsändare. Mer information finns i Spärra [en e-postavsändare.](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4)

- **Version:** För skräppost (inte nätfiske) kan du släppa meddelandet här utan att gå till karantänen för & säkerhets- och efterlevnadscenter.

- **Granska**&: Klicka på den här länken för att gå till karantän i säkerhets- och efterlevnadscentret, där du kan visa , släppa, ta bort eller rapportera dina meddelanden i karantän (beroende på varför meddelandet satt i karantän). Mer information finns i [Hitta och släppa meddelanden i karantän som en användare i EOP.](find-and-release-quarantined-messages-as-a-user.md)

![Exempel på skräppost-avisering för slutanvändare](../../media/end-user-spam-notification.png)

> [!NOTE]
> Spärrade avsändare kan fortfarande skicka e-post till dig. Alla meddelanden från den här avsändaren som skickar dem till din postlåda flyttas omedelbart till mappen Skräppost. Framtida meddelanden från den här avsändaren hamnar i mappen Skräppost eller till slutanvändares karantän. Om du vill ta bort dessa meddelanden vid ankomst i stället för att kvartiler kan du använda e-postflödesregler [(kallas](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) även transportregler) för att ta bort meddelandena när de anländer.