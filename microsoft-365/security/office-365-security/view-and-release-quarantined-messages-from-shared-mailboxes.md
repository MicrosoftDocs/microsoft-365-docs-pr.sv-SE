---
title: Visa och släppa meddelanden i karantän från delade post lådor
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX
description: Användare kan lära sig att visa och hantera meddelanden i karantän som skickades till delade post lådor.
ms.openlocfilehash: 0c165395edc3a3032ece603cb8d9aac875443d7d
ms.sourcegitcommit: 26c2f01d6f88f6c288b04f9f08062d68dd1e67e1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/04/2020
ms.locfileid: "49570967"
---
# <a name="view-and-release-quarantined-messages-from-shared-mailboxes"></a><span data-ttu-id="67124-103">Visa och släppa meddelanden i karantän från delade post lådor</span><span class="sxs-lookup"><span data-stu-id="67124-103">View and release quarantined messages from shared mailboxes</span></span>

> [!NOTE]
> <span data-ttu-id="67124-104">De funktioner som beskrivs i den här artikeln är för närvarande i för hands versionen, är inte tillgängliga för alla och kan komma att ändras.</span><span class="sxs-lookup"><span data-stu-id="67124-104">The features that are described in this article are currently in Preview, aren't available to everyone, and are subject to change.</span></span>

<span data-ttu-id="67124-105">Användare kan hantera meddelanden i karantän där de är en av mottagarna enligt beskrivningen i [hitta och släppa meddelanden i karantän som en användare i EOP](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="67124-105">Users can manage quarantined messages where they are one of the recipients as described in [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span> <span data-ttu-id="67124-106">Men vad händer med delade post lådor där användaren har fullständig åtkomst och behörigheten skicka som eller skicka för ombud till post lådan enligt beskrivningen i [delade post lådor i Exchange Online](https://docs.microsoft.com/exchange/collaboration-exo/shared-mailboxes)?</span><span class="sxs-lookup"><span data-stu-id="67124-106">But what about shared mailboxes where the user has Full Access and Send As or Send on Behalf permissions to the mailbox as described in [Shared mailboxes in Exchange Online](https://docs.microsoft.com/exchange/collaboration-exo/shared-mailboxes)?</span></span>

<span data-ttu-id="67124-107">Tidigare var det möjligt för användarna att hantera meddelanden i karantän som skickas till en delad post låda som krävs för att den delade post lådan ska vara aktive rad (den är aktive rad som standard när en administratör ger en användare åtkomst till en annan post låda).</span><span class="sxs-lookup"><span data-stu-id="67124-107">Previously, the ability for users to manage quarantined messages sent to a shared mailbox required admins to leave automapping enabled for the shared mailbox (it's enabled by default when an admin gives a user access to another mailbox).</span></span> <span data-ttu-id="67124-108">Beroende på storleken och antalet post lådor som användaren har till gång till kan prestandan bli lidande för att ett försök görs att öppna *alla* post lådor som användaren har till gång till.</span><span class="sxs-lookup"><span data-stu-id="67124-108">However, depending on the size and number of mailboxes that the user has access to, performance can suffer as Outlooks tries to open *all* mailboxes that the user has access to.</span></span> <span data-ttu-id="67124-109">Av den anledningen väljer många administratörer att [ta bort Automappning för delade post lådor](https://docs.microsoft.com/outlook/troubleshoot/profiles-and-accounts/remove-automapping-for-shared-mailbox).</span><span class="sxs-lookup"><span data-stu-id="67124-109">For this reason, many admins choose to [remove automapping for shared mailboxes](https://docs.microsoft.com/outlook/troubleshoot/profiles-and-accounts/remove-automapping-for-shared-mailbox).</span></span>

<span data-ttu-id="67124-110">Nu behöver du inte längre mappa automatiskt för att användare ska kunna hantera meddelanden i karantän som skickades till delade post lådor.</span><span class="sxs-lookup"><span data-stu-id="67124-110">Now, automapping is no longer required for users to manage quarantined messages that were sent to shared mailboxes.</span></span> <span data-ttu-id="67124-111">Det fungerar bara.</span><span class="sxs-lookup"><span data-stu-id="67124-111">It just works.</span></span> <span data-ttu-id="67124-112">Det finns två olika sätt att komma åt karantän meddelanden som skickades till en delad post låda:</span><span class="sxs-lookup"><span data-stu-id="67124-112">There are two different methods to access quarantined messages that were sent to a shared mailbox:</span></span>

- <span data-ttu-id="67124-113">Om administratören har [aktiverat aviseringar om slutanvändare](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies) i principer för skräp post kan alla användare som har till gång till skräp post meddelanden i den delade post lådan Klicka på knappen **Granska** i meddelandet för att gå till karantän i säkerhets & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="67124-113">If the admin has [enabled end-user spam notifications](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies) in anti-spam policies, any user that has access to the end-user spam notifications in the shared mailbox can click the **Review** button in the notification to go to quarantine in the Security & Compliance Center.</span></span> <span data-ttu-id="67124-114">Observera att den här metoden endast tillåter användare att hantera meddelanden som skickats till den delade post lådan.</span><span class="sxs-lookup"><span data-stu-id="67124-114">Note that this method only allows users to manage quarantined messages that were sent to the shared mailbox.</span></span> <span data-ttu-id="67124-115">Användarna kan inte hantera sina egna karantän meddelanden i den här kontexten.</span><span class="sxs-lookup"><span data-stu-id="67124-115">Users can't manage their own quarantine messages in this context.</span></span>

- <span data-ttu-id="67124-116">Användaren kan [gå till karantänen i säkerhets & Compliance Center](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="67124-116">The user can [go to the quarantine in the Security & Compliance Center](find-and-release-quarantined-messages-as-a-user.md).</span></span> <span data-ttu-id="67124-117">Som standard visas bara meddelanden som skickades till användaren.</span><span class="sxs-lookup"><span data-stu-id="67124-117">By default, only messages that were sent to the user are shown.</span></span> <span data-ttu-id="67124-118">Men användaren kan ändra **sorterings resultaten** ( **knappen meddelande-ID** som standard) till **mottagarens e-postadress**, skriva in e-postadressen för den delade post lådan och klicka på **Uppdatera** för att se de meddelanden i karantänen som skickades till den delade post lådan.</span><span class="sxs-lookup"><span data-stu-id="67124-118">However, the user can change the **Sort results** (the **Message ID button** by default) to **Recipient email address**, enter the shared mailbox email address, and then click **Refresh** to see the quarantined messages that were sent to the shared mailbox.</span></span>

  ![Sortera meddelanden i karantänen efter mottagarens e-postadress.](../../media/quarantine-sort-results-by-recipient-email-address.png)

<span data-ttu-id="67124-120">Oavsett hur du använder den här metoden kan användarna undvika förvirring genom att lägga till kolumnen **mottagare** för meddelanden i karantän.</span><span class="sxs-lookup"><span data-stu-id="67124-120">Regardless of the method, users can avoid confusion by including the **Recipient** column for quarantined messages.</span></span> <span data-ttu-id="67124-121">Det maximala antalet kolumner som ska visas är 7, så användaren måste klicka på **Ändra kolumner**, ta bort en befintlig kolumn (till exempel en **typ av princip**), välja **mottagare** och sedan klicka på **Spara** eller **Spara som standard**.</span><span class="sxs-lookup"><span data-stu-id="67124-121">The maximum number of columns to display is 7, so the user will need to click **Modify columns**, remove an existing column (for example, **Policy type**), select **Recipient**, and then click **Save** or **Save as default**.</span></span>

  ![Ta bort kolumnen princip typ och Lägg till kolumnen mottagare i karantän.](../../media/quarantine-add-recipient-column.png)

## <a name="things-to-keep-in-mind"></a><span data-ttu-id="67124-123">Saker att tänka på</span><span class="sxs-lookup"><span data-stu-id="67124-123">Things to keep in mind</span></span>

- <span data-ttu-id="67124-124">Den första användaren som ska agera på det satta meddelandet bestämmer överskrivning av meddelandet för alla som använder den delade post lådan.</span><span class="sxs-lookup"><span data-stu-id="67124-124">The first user to act on the quarantined message decides the fate of the message for everyone who uses the shared mailbox.</span></span> <span data-ttu-id="67124-125">Om till exempel en delad post låda används av 10 användare och en användare bestämmer sig för att ta bort karantän meddelandet raderas meddelandet för alla tio användarna.</span><span class="sxs-lookup"><span data-stu-id="67124-125">For example, if a shared mailbox is accessed by 10 users, and a user decides to delete the quarantine message, the message is deleted for all 10 users.</span></span> <span data-ttu-id="67124-126">Om en användare väljer att släppa meddelandet släpps det på den delade post lådan och är tillgänglig för alla andra användare av den delade post lådan.</span><span class="sxs-lookup"><span data-stu-id="67124-126">Likewise, if a user decides to release the message, it's released to the shared mailbox and is accessible by all other users of the shared mailbox.</span></span>

- <span data-ttu-id="67124-127">För närvarande, om en användare väljer flera meddelanden som skickats till den delade post lådan, returneras följande missvisande fel när användaren klickar på **släpp meddelanden** eller **ta bort meddelanden** i den utfällbara **Mass åtgärden** :</span><span class="sxs-lookup"><span data-stu-id="67124-127">Currently, if a user selects multiple quarantined messages that were sent to the shared mailbox, the following misleading errors are returned when the user clicks **Release messages** or **Delete messages** in the **Bulk actions** flyout:</span></span>

  > <span data-ttu-id="67124-128">Du har inte behörighet att frigöra alla markerade meddelanden i karantän.</span><span class="sxs-lookup"><span data-stu-id="67124-128">You do not have permission to release all selected quarantined messages.</span></span>
  >
  > <span data-ttu-id="67124-129">Du har inte behörighet att ta bort alla markerade meddelanden i karantänen.</span><span class="sxs-lookup"><span data-stu-id="67124-129">You do not have permission to delete all selected quarantined messages.</span></span>

  <span data-ttu-id="67124-130">Oavsett felet utförs åtgärden på meddelandet och felet kan ignoreras.</span><span class="sxs-lookup"><span data-stu-id="67124-130">Regardless of the error, the action is taken on the messages, and the error can be ignored.</span></span>

  ![Falskt fel vid Mass fri släppning eller borttagning av meddelanden som skickas till en delad post låda.](../../media/quarantine-bulk-action-error.png)

- <span data-ttu-id="67124-132">För närvarande går det inte att använda knappen **Blockera avsändare** för **infällbara meddelanden** som skickats till den delade post lådan.</span><span class="sxs-lookup"><span data-stu-id="67124-132">Currently, the **Block sender** button is not available in the **Details** flyout for quarantined messages that were sent to the shared mailbox.</span></span>

- <span data-ttu-id="67124-133">Om _du vill_ hantera meddelanden i karantän för den delade post lådan i [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)måste slutanvändaren använda cmdleten [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) för att identifiera meddelandena.</span><span class="sxs-lookup"><span data-stu-id="67124-133">To manage quarantined messages for the shared mailbox in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell), the end-user will need to use the [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) cmdlet with shared mailbox email address for the value of the _RecipientAddress_ parameter to identify the messages.</span></span> <span data-ttu-id="67124-134">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="67124-134">For example:</span></span>

  ```powershell
  Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com
  ```

  <span data-ttu-id="67124-135">Sedan kan slutanvändaren välja ett meddelande i karantän i listan för att visa eller vidta en åtgärd.</span><span class="sxs-lookup"><span data-stu-id="67124-135">Then, the end-user can select a quarantined message from the list to view or take action on.</span></span>

  <span data-ttu-id="67124-136">I det här exemplet visas alla karantän meddelanden som skickats till den delade post lådan och sedan släpps det första meddelandet i listan från karantän (det första meddelandet i listan är 0, det andra är 1 o.s.v.).</span><span class="sxs-lookup"><span data-stu-id="67124-136">This example shows all of the quarantined messages that were sent to the shared mailbox, and then releases the first message in the list from quarantine (the first message in the list is 0, the second is 1, and so on).</span></span>

  ```powershell
  $SharedMessages = Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com | select -ExpandProperty Identity
  $SharedMessages
  Release-QuarantinedMessage -Identity $SharedMessages[0]
  ```

  <span data-ttu-id="67124-137">Detaljerad information om syntax och parametrar finns i följande artiklar:</span><span class="sxs-lookup"><span data-stu-id="67124-137">For detailed syntax and parameter information, see the following topics:</span></span>

  - [<span data-ttu-id="67124-138">Get-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="67124-138">Get-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)
  - [<span data-ttu-id="67124-139">Get-QuarantineMessageHeader</span><span class="sxs-lookup"><span data-stu-id="67124-139">Get-QuarantineMessageHeader</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessageheader)
  - [<span data-ttu-id="67124-140">För hands version – QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="67124-140">Preview-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage)
  - [<span data-ttu-id="67124-141">Utgivning-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="67124-141">Release-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)
