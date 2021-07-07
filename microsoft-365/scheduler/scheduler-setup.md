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
ms.openlocfilehash: f44dc509e28c19c320418c28dda6146331669cde
ms.sourcegitcommit: 8b0718f5607ab509092cb80bda854010d885c54f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53314482"
---
# <a name="setting-up-scheduler-for-microsoft-365"></a>Konfigurera Schemaläggaren för Microsoft 365


Om du vill konfigurera Schemaläggaren för Microsoft 365 är följande förutsättningar:

| Vad behöver jag? | Beskrivning |
|-------------------|-------------|
|Cortana postlåda |Innehavaradministratörer måste ange att en postlåda ska fungera som "Cortana"-postlåda (d.v.s. cortana@yourdomain.com).         |
|Exchange Online postlåda |Användarna måste ha en e Exchange Online post och kalender         |
|Scheduler-licens |Information om licensiering och priser finns i [Schemaläggare för Microsoft 365](https://www.microsoft.com/en-us/microsoft-365/meeting-scheduler-pricing).        |

## <a name="create-a-mailbox-for-cortana"></a>Skapa en postlåda för Cortana

En Exchange postlåda i klientorganisationen fungerar som den Cortana postlådan för din klientorganisation att skicka och ta emot e-postmeddelanden till och Cortana. Alla e-postmeddelanden som Cortana till andra sparas i klientorganisationens Cortana baserat på bevarandeprincipen.

- Använd Administrationscenter för Microsoft 365 för att skapa en användarpostlåda. En 30-dagarsbevarandeprincip rekommenderas. 
- Använd namnet Cortana i postlådans primära SMTP-adress. Namn som "Cortana@yourdomain.com", "CortanaScheduler@contoso.com" eller "Cortana. Scheduler@yourdomain.com' rekommenderas.

## <a name="designate-the-mailbox-as-the-scheduler-assistant"></a>Ange postlådan som Schemaläggarassistenten

När en unik postlåda Cortana schemaläggaren har skapats måste du utse postlådan till Microsoft 365 postlådan. När du har angett Cortana Scheduler-postlådan blir den tillgänglig för att schemalägga möten för dina användare.

För att utse Cortana Scheduler-postlådan måste en behörig administratör köra ett PowerShell-kommando med en rad. 

1. Anslut att Microsoft 365 köra utrymme för din organisation med fjärr-PowerShell.

2. Kör följande PowerShell-skript för att ange postlådan för Scheduler:

    ```powershell
    Set-mailbox cortana@contoso.com -SchedulerAssistant:$true
    ```
    
    När du har kört kommandot "uppsättning" på Cortana Scheduler-postlådan ställs en ny "PersistedCapability" in för postlådan som anger att den här postlådan är "SchedulerAssistant".

> [!NOTE]
> Följ de här anvisningarna för att ansluta din organisation till PowerShell om du inte har gjort det tidigare: Anslut [att Microsoft 365 med PowerShell](../enterprise/connect-to-microsoft-365-powershell.md).

Om du vill ta reda på vilken postlåda i organisationen som är inställd Cortana – Schemaläggaren kör du funktionen Hämta:

```powershell
Get-mailbox | where {$_.PersistedCapabilities -Match "SchedulerAssistant"}
```

> [!IMPORTANT]
> Det kan ta upp till två timmar för Scheduler-postlådan att slutföra den fullständiga etableringen för att ange funktionen SchedulerAssistant.

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
> **Scheduler for Microsoft 365** is currently available for worldwide multi-tenants, only in English.</br>
>
> Det är inte tillgängligt för användare av Office 365 som drivs av 21Vianet i Kina eller användare av Microsoft 365 med det tyska molnet som använder dataförvaltarens tyska Telekom. Det stöds för användare i Tyskland vars dataplats inte finns i det tyska datacentret.
>
> Den här funktionen stöds inte heller för användare av Government Cloud, GCC, Consumer, GCC High eller DoD.
