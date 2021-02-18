---
title: Visa och släppa meddelanden i karantän från delade postlådor
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX
description: Användare kan lära sig hur de visar och agerar på meddelanden i karantän som har skickats till delade postlådor som de har behörighet till.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 31fbf9c54c3f28e439f444dde872469918dc29d4
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290147"
---
# <a name="view-and-release-quarantined-messages-from-shared-mailboxes"></a><span data-ttu-id="ebe2b-103">Visa och släppa meddelanden i karantän från delade postlådor</span><span class="sxs-lookup"><span data-stu-id="ebe2b-103">View and release quarantined messages from shared mailboxes</span></span>

> [!NOTE]
> <span data-ttu-id="ebe2b-104">De funktioner som beskrivs i den här artikeln är för närvarande i förhandsversion, är inte tillgängliga för alla och kan komma att ändras.</span><span class="sxs-lookup"><span data-stu-id="ebe2b-104">The features that are described in this article are currently in Preview, aren't available to everyone, and are subject to change.</span></span>

<span data-ttu-id="ebe2b-105">Användare kan hantera meddelanden i karantän där de är en av mottagarna enligt beskrivningen i Hitta och släppa meddelanden i karantän [som användare i EOP.](find-and-release-quarantined-messages-as-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="ebe2b-105">Users can manage quarantined messages where they are one of the recipients as described in [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span> <span data-ttu-id="ebe2b-106">Men hur blir det med delade postlådor där användaren har behörigheten Fullständig åtkomst och Skicka som eller Skicka för till postlådan enligt beskrivningen i Delade postlådor [i Exchange Online?](https://docs.microsoft.com/exchange/collaboration-exo/shared-mailboxes)</span><span class="sxs-lookup"><span data-stu-id="ebe2b-106">But what about shared mailboxes where the user has Full Access and Send As or Send on Behalf permissions to the mailbox as described in [Shared mailboxes in Exchange Online](https://docs.microsoft.com/exchange/collaboration-exo/shared-mailboxes)?</span></span>

<span data-ttu-id="ebe2b-107">Tidigare var möjligheten för användare att hantera meddelanden i karantän som skickas till en delad postlåda obligatoriska administratörer för att lämna automatisk mappning aktiverad för den delade postlådan (den är aktiverad som standard när en administratör ger en användare åtkomst till en annan postlåda).</span><span class="sxs-lookup"><span data-stu-id="ebe2b-107">Previously, the ability for users to manage quarantined messages sent to a shared mailbox required admins to leave automapping enabled for the shared mailbox (it's enabled by default when an admin gives a user access to another mailbox).</span></span> <span data-ttu-id="ebe2b-108">Men prestandan kan drabbas av prestandan, beroende på storleken på och antalet  postlådor som användaren har tillgång till, när Outlook försöker öppna alla postlådor som användaren har åtkomst till.</span><span class="sxs-lookup"><span data-stu-id="ebe2b-108">However, depending on the size and number of mailboxes that the user has access to, performance can suffer as Outlooks tries to open *all* mailboxes that the user has access to.</span></span> <span data-ttu-id="ebe2b-109">Därför väljer många administratörer att ta bort [automatisk mappning för delade postlådor.](https://docs.microsoft.com/outlook/troubleshoot/profiles-and-accounts/remove-automapping-for-shared-mailbox)</span><span class="sxs-lookup"><span data-stu-id="ebe2b-109">For this reason, many admins choose to [remove automapping for shared mailboxes](https://docs.microsoft.com/outlook/troubleshoot/profiles-and-accounts/remove-automapping-for-shared-mailbox).</span></span>

<span data-ttu-id="ebe2b-110">Automatisk mappning krävs nu inte längre för att användare ska kunna hantera meddelanden i karantän som har skickats till delade postlådor.</span><span class="sxs-lookup"><span data-stu-id="ebe2b-110">Now, automapping is no longer required for users to manage quarantined messages that were sent to shared mailboxes.</span></span> <span data-ttu-id="ebe2b-111">Det fungerar bara.</span><span class="sxs-lookup"><span data-stu-id="ebe2b-111">It just works.</span></span> <span data-ttu-id="ebe2b-112">Det finns två olika metoder för att komma åt meddelanden i karantän som har skickats till en delad postlåda:</span><span class="sxs-lookup"><span data-stu-id="ebe2b-112">There are two different methods to access quarantined messages that were sent to a shared mailbox:</span></span>

- <span data-ttu-id="ebe2b-113">Om administratören har aktiverat [skräppost-aviseringar](configure-your-spam-filter-policies.md) för slutanvändare i principer för skräppostskydd kan alla användare som har  åtkomst till slutanvändarens skräppost-aviseringar i den delade postlådan klicka på knappen Granska i meddelandet för att gå till karantän i Säkerhets- & efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="ebe2b-113">If the admin has [enabled end-user spam notifications](configure-your-spam-filter-policies.md) in anti-spam policies, any user that has access to the end-user spam notifications in the shared mailbox can click the **Review** button in the notification to go to quarantine in the Security & Compliance Center.</span></span> <span data-ttu-id="ebe2b-114">Den här metoden gör det bara möjligt för användare att hantera meddelanden i karantän som har skickats till den delade postlådan.</span><span class="sxs-lookup"><span data-stu-id="ebe2b-114">Note that this method only allows users to manage quarantined messages that were sent to the shared mailbox.</span></span> <span data-ttu-id="ebe2b-115">Användare kan inte hantera sina egna karantänmeddelanden i det här sammanhanget.</span><span class="sxs-lookup"><span data-stu-id="ebe2b-115">Users can't manage their own quarantine messages in this context.</span></span>

- <span data-ttu-id="ebe2b-116">Användaren kan [gå till karantänen i säkerhets- & Efterlevnadscenter.](find-and-release-quarantined-messages-as-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="ebe2b-116">The user can [go to the quarantine in the Security & Compliance Center](find-and-release-quarantined-messages-as-a-user.md).</span></span> <span data-ttu-id="ebe2b-117">Som standard visas endast meddelanden som har skickats till användaren.</span><span class="sxs-lookup"><span data-stu-id="ebe2b-117">By default, only messages that were sent to the user are shown.</span></span> <span data-ttu-id="ebe2b-118">Användaren kan ändra sorteringsresultatet **(knappen**  **Meddelande-ID** som standard) till Mottagarens e-postadress, ange den delade postlådans e-postadress och sedan klicka på Uppdatera för att se meddelanden i karantän som har skickats till den delade postlådan. </span><span class="sxs-lookup"><span data-stu-id="ebe2b-118">However, the user can change the **Sort results** (the **Message ID button** by default) to **Recipient email address**, enter the shared mailbox email address, and then click **Refresh** to see the quarantined messages that were sent to the shared mailbox.</span></span>

  ![Sortera meddelanden i karantän efter mottagarens e-postadress.](../../media/quarantine-sort-results-by-recipient-email-address.png)

<span data-ttu-id="ebe2b-120">Oavsett metod kan användarna undvika förvirring genom att lägga till kolumnen **Mottagare för** meddelanden i karantän.</span><span class="sxs-lookup"><span data-stu-id="ebe2b-120">Regardless of the method, users can avoid confusion by including the **Recipient** column for quarantined messages.</span></span> <span data-ttu-id="ebe2b-121">Max antal kolumner som ska visas är 7, så användaren måste klicka på Ändra kolumner, ta bort en  befintlig kolumn (till exempel principtyp), välja Mottagare och sedan klicka på Spara eller Spara som **standard.**  </span><span class="sxs-lookup"><span data-stu-id="ebe2b-121">The maximum number of columns to display is 7, so the user will need to click **Modify columns**, remove an existing column (for example, **Policy type**), select **Recipient**, and then click **Save** or **Save as default**.</span></span>

  ![Ta bort kolumnen Principtyp och lägg till kolumnen Mottagare i karantän.](../../media/quarantine-add-recipient-column.png)

## <a name="things-to-keep-in-mind"></a><span data-ttu-id="ebe2b-123">Saker att tänka på</span><span class="sxs-lookup"><span data-stu-id="ebe2b-123">Things to keep in mind</span></span>

- <span data-ttu-id="ebe2b-124">Den första användaren som agerar på det meddelande i karantän som bestämmer den första användaren av meddelandet för alla som använder den delade postlådan.</span><span class="sxs-lookup"><span data-stu-id="ebe2b-124">The first user to act on the quarantined message decides the fate of the message for everyone who uses the shared mailbox.</span></span> <span data-ttu-id="ebe2b-125">Om till exempel en delad postlåda används av tio användare och en användare väljer att ta bort karantänmeddelandet, tas meddelandet bort för alla tio användare.</span><span class="sxs-lookup"><span data-stu-id="ebe2b-125">For example, if a shared mailbox is accessed by 10 users, and a user decides to delete the quarantine message, the message is deleted for all 10 users.</span></span> <span data-ttu-id="ebe2b-126">Om en användare väljer att släppa meddelandet släpps det till den delade postlådan och är tillgängligt för alla andra användare av den delade postlådan.</span><span class="sxs-lookup"><span data-stu-id="ebe2b-126">Likewise, if a user decides to release the message, it's released to the shared mailbox and is accessible by all other users of the shared mailbox.</span></span>

- <span data-ttu-id="ebe2b-127">Knappen Spärra **avsändare är för** närvarande  inte tillgänglig i den utfällna informationen för meddelanden i karantän som har skickats till den delade postlådan.</span><span class="sxs-lookup"><span data-stu-id="ebe2b-127">Currently, the **Block sender** button is not available in the **Details** flyout for quarantined messages that were sent to the shared mailbox.</span></span>

- <span data-ttu-id="ebe2b-128">För att hantera meddelanden i karantän för den delade postlådan i [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)måste slutanvändaren använda cmdleten [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) med en delad postlådas e-postadress för värdet på parametern _RecipientAddress_ för att identifiera meddelandena.</span><span class="sxs-lookup"><span data-stu-id="ebe2b-128">To manage quarantined messages for the shared mailbox in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell), the end-user will need to use the [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) cmdlet with shared mailbox email address for the value of the _RecipientAddress_ parameter to identify the messages.</span></span> <span data-ttu-id="ebe2b-129">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="ebe2b-129">For example:</span></span>

  ```powershell
  Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com
  ```

  <span data-ttu-id="ebe2b-130">Slutanvändaren kan sedan välja ett meddelande i karantän i listan som du vill visa eller vidta åtgärder för.</span><span class="sxs-lookup"><span data-stu-id="ebe2b-130">Then, the end-user can select a quarantined message from the list to view or take action on.</span></span>

  <span data-ttu-id="ebe2b-131">Det här exemplet visar alla meddelanden i karantän som skickades till den delade postlådan och släpper sedan det första meddelandet i listan från karantän (det första meddelandet i listan är 0, det andra är 1 och så vidare).</span><span class="sxs-lookup"><span data-stu-id="ebe2b-131">This example shows all of the quarantined messages that were sent to the shared mailbox, and then releases the first message in the list from quarantine (the first message in the list is 0, the second is 1, and so on).</span></span>

  ```powershell
  $SharedMessages = Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com | select -ExpandProperty Identity
  $SharedMessages
  Release-QuarantinedMessage -Identity $SharedMessages[0]
  ```

  <span data-ttu-id="ebe2b-132">Detaljerad information om syntax och parametrar finns i följande artiklar:</span><span class="sxs-lookup"><span data-stu-id="ebe2b-132">For detailed syntax and parameter information, see the following topics:</span></span>

  - [<span data-ttu-id="ebe2b-133">Get-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="ebe2b-133">Get-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)
  - [<span data-ttu-id="ebe2b-134">Get-QuarantineMessageHeader</span><span class="sxs-lookup"><span data-stu-id="ebe2b-134">Get-QuarantineMessageHeader</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessageheader)
  - [<span data-ttu-id="ebe2b-135">Preview-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="ebe2b-135">Preview-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage)
  - [<span data-ttu-id="ebe2b-136">Release-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="ebe2b-136">Release-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)
