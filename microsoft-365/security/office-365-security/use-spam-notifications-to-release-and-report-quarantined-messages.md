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
ms.openlocfilehash: bb347f7fd3d3793b563714e8116316b30165ef9a
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287551"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a>Använda skräppost-aviseringar för användare för att släppa och rapportera meddelanden i karantän

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående Exchange Online Protection-organisationer (EOP) utan Exchange Online-postlådor lagrar karantänen potentiellt farliga eller oönskade meddelanden. Mer information finns i meddelanden [i karantän i EOP.](quarantine-email-messages.md)

Som standard är skräppost-aviseringar för slutanvändare inaktiverade i principerna för skydd mot skräppost. När en administratör aktiverar [skräppost-aviseringar](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)för slutanvändare får mottagare (inklusive delade postlådor med automatisk mappning aktiverat) periodiska meddelanden om meddelanden som har satts i karantän som skräppost, massutskick eller (från och med april 2020) nätfiske.

För delade postlådor stöds skräppost-aviseringar för slutanvändare endast för användare som beviljas behörigheten FullAccess till den delade postlådan. Mer information finns i Använda [EAC för att redigera delegering av delade postlådor.](https://docs.microsoft.com/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation)

Skräppost-avisering för slutanvändare stöds inte för grupper.

> [!NOTE]
> Meddelanden som satts i karantän som nätfiske, skadlig kod eller genom e-postflödesregler (kallas även transportregler) är bara tillgängliga för administratörer. Mer information finns i [Hantera meddelanden och filer i karantän som administratör i EOP](manage-quarantined-messages-and-files.md).

En skräppost-avisering för slutanvändaren innehåller följande information för varje meddelande i karantän:

- **Avsändare:** Skicka meddelandets namn och e-postadress i karantän.

- **Ämne:** Ämnesraden i det meddelande som sätts i karantän.

- **Datum:** Datum och tid (i UTC) då meddelandet satts i karantän.

- **Spärra avsändare:** Klicka på den här länken om du vill lägga till avsändaren i listan Spärrade avsändare. Mer information finns i Spärra [en e-postavsändare.](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4)

- **Version:** För skräppost (inte nätfiske) kan du släppa meddelandet här utan att behöva sätta i karantän för & Efterlevnadscenter.

- **Granska**&: Klicka på den här länken för att gå till karantän i Säkerhets- och efterlevnadscenter, där du kan visa (beroende på varför meddelandet har satts i karantän), släppa, ta bort eller rapportera meddelanden i karantän. Mer information finns i [Hitta och släppa meddelanden i karantän som användare i EOP.](find-and-release-quarantined-messages-as-a-user.md)

![Exempel på skräppost-avisering för slutanvändare](../../media/end-user-spam-notification.png)

> [!NOTE]
> En spärrad avsändare kan fortfarande skicka e-post till dig. Alla meddelanden från den här avsändaren som skickar dem till din postlåda flyttas omedelbart till mappen Skräppost. Framtida meddelanden från den här avsändaren hamnar i mappen Skräppost eller till slutanvändaren. Om du vill ta bort dessa meddelanden vid ankomst i stället för att kvartilila dem kan du använda e-postflödesregler [(kallas](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) även transportregler) för att ta bort meddelandena när de kommer in.
