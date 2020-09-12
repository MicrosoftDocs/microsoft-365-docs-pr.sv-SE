---
title: Microsoft 365 Mailbox-migreringar
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: Den här artikeln innehåller en kort sammanfattning av migreringar till Microsoft 365-postlådan och en lista över de cmdlets som används för migreringar.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 63080643e4994d6b16e77298907725a827997cef
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546804"
---
# <a name="microsoft-365-mailbox-migrations"></a>Microsoft 365 Mailbox-migreringar

Med en Exchange-baserad hybrid distribution kan kunderna välja att antingen flytta lokala Exchange-postlådor till en [Exchange Online](https://docs.microsoft.com/Exchange/exchange-online) -organisation eller flytta Exchange Online-postlådor till en [Exchange-lokal](https://docs.microsoft.com/Exchange/exchange-server) organisation. Migreringsåtgärder används när post lådor flyttas mellan lokala och Exchange Online-organisationer.

Kunderna kan granska statistik och annan information om migrering av post lådor med följande cmdletar:

- [Get-MoveRequestStatistics](https://docs.microsoft.com/powershell/module/exchange/get-moverequeststatistics): tillhandahåller standard statistik för en användar post låda som innehåller status, Mailbox size, Arkiv post lådans storlek och procent färdigt.
- [Get-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-Mailbox
): innehåller en lista över objekt och attribut för post lådor i organisationen.
- [Get-mottagare](https://docs.microsoft.com/powershell/module/exchange/get-recipient): innehåller en lista med befintliga e-postaktiverade objekt som post lådor, e-postsamta kontakter och distributions grupper.
- [Get-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/get-moverequest): visar en detaljerad status för en pågående post låda.
- [Get-MigrationUser](https://docs.microsoft.com/powershell/module/exchange/get-migrationuser): innehåller information om flytt-och migreringsåtgärder för post lådor.
- [Get-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/get-migrationbatch): visar information om den aktuella migreringsverktyget.
- [Get-MigrationUserStatistics](https://docs.microsoft.com/powershell/module/exchange/get-migrationuserstatistics): innehåller detaljerad information om status för migrering för en viss användare.
- [Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/get-mailboxstatistics): ger information om post lådor, till exempel storlek, antalet meddelanden och den tid som senast används.

Mer information om cmdletar finns i [flytta och migrera cmdlets i Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell).
