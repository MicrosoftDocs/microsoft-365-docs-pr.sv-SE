---
title: Konfigurera Scheduler för Microsoft 365.
ms.author: v-aiyengar
author: AshaIyengar21
manager: serdars
audience: Admin
ms.topic: article
ms.service: scheduler
localization_priority: Normal
description: Konfigurera Scheduler för Microsoft 365.
ms.openlocfilehash: 79e1596288836770c720cb312580fc706bb7b95f
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/08/2021
ms.locfileid: "52286252"
---
# <a name="setting-up-scheduler-for-microsoft-365"></a>Konfigurera Scheduler för Microsoft 365

Om du vill konfigurera Schemaläggaren för Microsoft 365 är följande förutsättningar:

|**Vad behöver jag?** |**Beskrivning** |
|-------------------|-------------|
|Cortana-postlåda |Innehavaradministratörer måste ange att en postlåda ska fungera som "Cortana"-postlåda (d.v.s. cortana@yourdomain.com).         |
|Exchange Online postlåda |Användarna måste ha en e Exchange Online post och kalender         |
|Scheduler-licens |Information om licensiering och priser finns i [Schemaläggare för Microsoft 365](https://www.microsoft.com/microsoft-365/meeting-scheduler-pricing).        |

## <a name="create-a-mailbox-for-cortana"></a>Skapa en postlåda för Cortana
En Exchange postlåda i klientorganisationen fungerar som Cortana-postlådan för din klientorganisation att skicka och ta emot e-postmeddelanden till och från Cortana. Alla e-postmeddelanden som skickas till Cortana behålls i klientorganisationens Cortana-postlåda baserat på bevarandeprincipen.

- Använd administrationscentret Microsoft 365 skapa en ny postlåda. En 30-dagarsbevarandeprincip rekommenderas. Använd namnet Cortana i postlådans primära SMTP-adress. Namn som "Cortana@yourdomain.com", "CortanaScheduler@contoso.com" eller "Cortana.Scheduler@yourdomain.com" rekommenderas.
- Kontakta Microsoft (scheduler_m365@microsoft.com) för att aktivera Cortana-postlådan. 

> [!IMPORTANT]
> Du måste kontakta Microsoft om du vill konfigurera Cortana-postlådan så att den använder scheduler-tjänsten genom att skicka e-scheduler_m365@microsoft.com. Det kan ta upp till två veckor att aktivera Cortana-postlådan.

## <a name="exchange-online-mailbox"></a>Exchange Online postlåda
Schemaläggaren är ett tillägg till Microsoft 365. Mötesorganisatörer måste ha Exchange Online postlåda och kalender för att Schemaläggaren ska fungera.

## <a name="exchange-requirements"></a>Krav för Exchange

Förutom Schemaläggaren för licensiering måste du ha någon av följande licenser:

- Microsoft 365 E3, A3, E5, A5
- Business Basic, Business, Business Standard, Business Premium
- Office 365 E1, A1, E3, A3, E5, A5
- Business Essentials, Business Premium
- Exchange Online Abonnemang 1- eller abonnemang 2-licens. 

> [!Note]
> **Scheduler för Microsoft 365** är inte tillgängligt för användare av Office 365 som drivs av 21Vianet i Kina. Det är inte heller tillgängligt för användare av Microsoft 365 med det tyska molnet som använder dataförvaltaren tyska Telekom. Det stöds för användare i Tyskland vars dataplats inte finns i det tyska datacentret.
>
>Den här funktionen stöds inte heller för användare av Government Cloud, GCC, Consumer, GCC High eller DoD.
