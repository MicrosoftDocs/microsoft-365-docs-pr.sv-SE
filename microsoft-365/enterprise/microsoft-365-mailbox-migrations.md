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
# <a name="microsoft-365-mailbox-migrations"></a><span data-ttu-id="710b0-103">Microsoft 365 Mailbox-migreringar</span><span class="sxs-lookup"><span data-stu-id="710b0-103">Microsoft 365 mailbox migrations</span></span>

<span data-ttu-id="710b0-104">Med en Exchange-baserad hybrid distribution kan kunderna välja att antingen flytta lokala Exchange-postlådor till en [Exchange Online](https://docs.microsoft.com/Exchange/exchange-online) -organisation eller flytta Exchange Online-postlådor till en [Exchange-lokal](https://docs.microsoft.com/Exchange/exchange-server) organisation.</span><span class="sxs-lookup"><span data-stu-id="710b0-104">With an Exchange-based hybrid deployment, customers can choose to either move on-premises Exchange mailboxes to an [Exchange Online](https://docs.microsoft.com/Exchange/exchange-online) organization or move Exchange Online mailboxes to an [Exchange on-premises](https://docs.microsoft.com/Exchange/exchange-server) organization.</span></span> <span data-ttu-id="710b0-105">Migreringsåtgärder används när post lådor flyttas mellan lokala och Exchange Online-organisationer.</span><span class="sxs-lookup"><span data-stu-id="710b0-105">Migration batches are used when moving mailboxes between on-premises and Exchange Online organizations.</span></span>

<span data-ttu-id="710b0-106">Kunderna kan granska statistik och annan information om migrering av post lådor med följande cmdletar:</span><span class="sxs-lookup"><span data-stu-id="710b0-106">Customers can review statistics and other information about mailbox migrations with the following cmdlets:</span></span>

- <span data-ttu-id="710b0-107">[Get-MoveRequestStatistics](https://docs.microsoft.com/powershell/module/exchange/get-moverequeststatistics): tillhandahåller standard statistik för en användar post låda som innehåller status, Mailbox size, Arkiv post lådans storlek och procent färdigt.</span><span class="sxs-lookup"><span data-stu-id="710b0-107">[Get-MoveRequestStatistics](https://docs.microsoft.com/powershell/module/exchange/get-moverequeststatistics): Provides default statistics for a user mailbox, which includes the status, mailbox size, archive mailbox size, and percentage complete.</span></span>
- <span data-ttu-id="710b0-108">[Get-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-Mailbox
): innehåller en lista över objekt och attribut för post lådor i organisationen.</span><span class="sxs-lookup"><span data-stu-id="710b0-108">[Get-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-Mailbox
): Provides a summary list of mailbox objects and attributes in the organization.</span></span>
- <span data-ttu-id="710b0-109">[Get-mottagare](https://docs.microsoft.com/powershell/module/exchange/get-recipient): innehåller en lista med befintliga e-postaktiverade objekt som post lådor, e-postsamta kontakter och distributions grupper.</span><span class="sxs-lookup"><span data-stu-id="710b0-109">[Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient): Provides a list of existing mail-enabled objects such as mailboxes, mail users, contacts, and distribution groups.</span></span>
- <span data-ttu-id="710b0-110">[Get-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/get-moverequest): visar en detaljerad status för en pågående post låda.</span><span class="sxs-lookup"><span data-stu-id="710b0-110">[Get-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/get-moverequest): Provides a detailed status of an ongoing mailbox migration.</span></span>
- <span data-ttu-id="710b0-111">[Get-MigrationUser](https://docs.microsoft.com/powershell/module/exchange/get-migrationuser): innehåller information om flytt-och migreringsåtgärder för post lådor.</span><span class="sxs-lookup"><span data-stu-id="710b0-111">[Get-MigrationUser](https://docs.microsoft.com/powershell/module/exchange/get-migrationuser): Provides information about the mailbox move and migration users.</span></span>
- <span data-ttu-id="710b0-112">[Get-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/get-migrationbatch): visar information om den aktuella migreringsverktyget.</span><span class="sxs-lookup"><span data-stu-id="710b0-112">[Get-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/get-migrationbatch): Provides information on the status of current migration batch.</span></span>
- <span data-ttu-id="710b0-113">[Get-MigrationUserStatistics](https://docs.microsoft.com/powershell/module/exchange/get-migrationuserstatistics): innehåller detaljerad information om status för migrering för en viss användare.</span><span class="sxs-lookup"><span data-stu-id="710b0-113">[Get-MigrationUserStatistics](https://docs.microsoft.com/powershell/module/exchange/get-migrationuserstatistics): Provides detailed information about the migration status for a specific user.</span></span>
- <span data-ttu-id="710b0-114">[Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/get-mailboxstatistics): ger information om post lådor, till exempel storlek, antalet meddelanden och den tid som senast används.</span><span class="sxs-lookup"><span data-stu-id="710b0-114">[Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/get-mailboxstatistics): Provides information about mailboxes, such as size, the number of messages, and the last accessed time.</span></span>

<span data-ttu-id="710b0-115">Mer information om cmdletar finns i [flytta och migrera cmdlets i Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="710b0-115">For more information about cmdlets, see [Move and Migration cmdlets in Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell).</span></span>
