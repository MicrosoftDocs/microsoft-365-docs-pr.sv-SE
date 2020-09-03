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
ms.openlocfilehash: 86681cbca6f0899268ce11e233e8781619cb18e3
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332322"
---
# <a name="microsoft-365-mailbox-migrations"></a><span data-ttu-id="40d56-103">Microsoft 365 Mailbox-migreringar</span><span class="sxs-lookup"><span data-stu-id="40d56-103">Microsoft 365 mailbox migrations</span></span>

<span data-ttu-id="40d56-104">Med en Exchange-baserad hybrid distribution kan kunderna välja att antingen flytta lokala Exchange-postlådor till en [Exchange Online](https://docs.microsoft.com/Exchange/exchange-online) -organisation eller flytta Exchange Online-postlådor till en [Exchange-lokal](https://docs.microsoft.com/Exchange/exchange-server) organisation.</span><span class="sxs-lookup"><span data-stu-id="40d56-104">With an Exchange-based hybrid deployment, customers can choose to either move on-premises Exchange mailboxes to an [Exchange Online](https://docs.microsoft.com/Exchange/exchange-online) organization or move Exchange Online mailboxes to an [Exchange on-premises](https://docs.microsoft.com/Exchange/exchange-server) organization.</span></span> <span data-ttu-id="40d56-105">Migreringsåtgärder används när post lådor flyttas mellan lokala och Exchange Online-organisationer.</span><span class="sxs-lookup"><span data-stu-id="40d56-105">Migration batches are used when moving mailboxes between on-premises and Exchange Online organizations.</span></span>

<span data-ttu-id="40d56-106">Kunderna kan granska statistik och annan information om migrering av post lådor med följande cmdletar:</span><span class="sxs-lookup"><span data-stu-id="40d56-106">Customers can review statistics and other information about mailbox migrations with the following cmdlets:</span></span>

- <span data-ttu-id="40d56-107">[Get-MoveRequestStatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MoveRequestStatistics?view=exchange-ps): tillhandahåller standard statistik för en användar post låda som innehåller status, Mailbox size, Arkiv post lådans storlek och procent färdigt.</span><span class="sxs-lookup"><span data-stu-id="40d56-107">[Get-MoveRequestStatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MoveRequestStatistics?view=exchange-ps): Provides default statistics for a user mailbox, which includes the status, mailbox size, archive mailbox size, and percentage complete.</span></span>
- <span data-ttu-id="40d56-108">[Get-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-Mailbox?view=exchange-ps
): innehåller en lista över objekt och attribut för post lådor i organisationen.</span><span class="sxs-lookup"><span data-stu-id="40d56-108">[Get-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-Mailbox?view=exchange-ps
): Provides a summary list of mailbox objects and attributes in the organization.</span></span>
- <span data-ttu-id="40d56-109">[Get-mottagare](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient?view=exchange-ps): innehåller en lista med befintliga e-postaktiverade objekt som post lådor, e-postsamta kontakter och distributions grupper.</span><span class="sxs-lookup"><span data-stu-id="40d56-109">[Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient?view=exchange-ps): Provides a list of existing mail-enabled objects such as mailboxes, mail users, contacts, and distribution groups.</span></span>
- <span data-ttu-id="40d56-110">[Get-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MoveRequest?view=exchange-ps): visar en detaljerad status för en pågående post låda.</span><span class="sxs-lookup"><span data-stu-id="40d56-110">[Get-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MoveRequest?view=exchange-ps): Provides a detailed status of an ongoing mailbox migration.</span></span>
- <span data-ttu-id="40d56-111">[Get-MigrationUser](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationUser?view=exchange-ps): innehåller information om flytt-och migreringsåtgärder för post lådor.</span><span class="sxs-lookup"><span data-stu-id="40d56-111">[Get-MigrationUser](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationUser?view=exchange-ps): Provides information about the mailbox move and migration users.</span></span>
- <span data-ttu-id="40d56-112">[Get-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationBatch?view=exchange-ps): visar information om den aktuella migreringsverktyget.</span><span class="sxs-lookup"><span data-stu-id="40d56-112">[Get-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationBatch?view=exchange-ps): Provides information on the status of current migration batch.</span></span>
- <span data-ttu-id="40d56-113">[Get-MigrationUserStatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationUserStatistics?view=exchange-ps): innehåller detaljerad information om status för migrering för en viss användare.</span><span class="sxs-lookup"><span data-stu-id="40d56-113">[Get-MigrationUserStatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationUserStatistics?view=exchange-ps): Provides detailed information about the migration status for a specific user.</span></span>
- <span data-ttu-id="40d56-114">[Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-MailboxStatistics?view=exchange-ps): ger information om post lådor, till exempel storlek, antalet meddelanden och den tid som senast används.</span><span class="sxs-lookup"><span data-stu-id="40d56-114">[Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-MailboxStatistics?view=exchange-ps): Provides information about mailboxes, such as size, the number of messages, and the last accessed time.</span></span>

<span data-ttu-id="40d56-115">Mer information om cmdletar finns i [flytta och migrera cmdlets i Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="40d56-115">For more information about cmdlets, see [Move and Migration cmdlets in Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps).</span></span>
