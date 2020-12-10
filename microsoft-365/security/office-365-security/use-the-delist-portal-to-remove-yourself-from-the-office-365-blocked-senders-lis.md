---
title: Ta bort från listan Spärrade avsändare
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/18/2016
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0bcecdd4-3343-4cc0-9e58-e19d4de515e8
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: I den här artikeln får du lära dig hur du använder list portalen för att ta bort dig själv från listan med spärrade avsändare i Microsoft 365.
ms.openlocfilehash: 0c87d467db004a50502402b05eb0fa3283aa46c5
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/10/2020
ms.locfileid: "49614768"
---
# <a name="use-the-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a><span data-ttu-id="53027-103">Använda avlistningsportalen för att ta bort dig själv från listan med spärrade avsändare</span><span class="sxs-lookup"><span data-stu-id="53027-103">Use the delist portal to remove yourself from the blocked senders list</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="53027-104">Får du ett fel meddelande när du försöker skicka ett e-postmeddelande till en mottagare vars e-postadress finns i Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="53027-104">Are you getting an error message when you try to send an email to a recipient whose email address is in Microsoft 365?</span></span> <span data-ttu-id="53027-105">Om du tror att du inte ska få fel meddelandet kan du ta bort dig själv från listan med spärrade avsändare genom att använda List portalen.</span><span class="sxs-lookup"><span data-stu-id="53027-105">If you think you should not be receiving the error message, you can use the delist portal to remove yourself from the blocked senders list.</span></span>

## <a name="what-is-the-blocked-senders-list"></a><span data-ttu-id="53027-106">Vad är listan med spärrade avsändare?</span><span class="sxs-lookup"><span data-stu-id="53027-106">What is the blocked senders list?</span></span>

<span data-ttu-id="53027-107">Microsoft använder listan Spärrade avsändare för att skydda sina kunder mot skräp post, förfalskningar och nätfiske-attacker.</span><span class="sxs-lookup"><span data-stu-id="53027-107">Microsoft uses the blocked senders list to protect its customers from spam, spoofing, and phishing attacks.</span></span> <span data-ttu-id="53027-108">Din e-postservers IP-adress, det vill säga den adress som din e-postserver använder för att identifiera sig på Internet, har taggats som ett potentiellt hot mot Microsoft 365 på en av många olika anledningar.</span><span class="sxs-lookup"><span data-stu-id="53027-108">Your mail server's IP address, that is, the address your mail server uses to identify itself on the Internet, was tagged as a potential threat to Microsoft 365 for one of a variety of reasons.</span></span> <span data-ttu-id="53027-109">När Microsoft 365 lägger till IP-adressen i listan förhindrar den all kommunikation mellan IP-adressen och våra kunder via våra data Center.</span><span class="sxs-lookup"><span data-stu-id="53027-109">When Microsoft 365 adds the IP address to the list, it prevents all further communication between the IP address and any of our customers through our datacenters.</span></span>

<span data-ttu-id="53027-110">Du vet att du har lagts till i listan när du får ett svar på ett e-postmeddelande som innehåller ett fel som ser ut ungefär så här:</span><span class="sxs-lookup"><span data-stu-id="53027-110">You will know you have been added to the list when you receive a response to a mail message that includes an error that looks something like this:</span></span>

> <span data-ttu-id="53027-111">550 5.7.606-649 åtkomst nekad, tillåts inte skickande IP [_IP-adress_]; För att begära borttagning från den här listan <https://sender.office.com/> , gå till och följ instruktionerna.</span><span class="sxs-lookup"><span data-stu-id="53027-111">550 5.7.606-649 Access denied, banned sending IP [_IP address_]; To request removal from this list please visit <https://sender.office.com/> and follow the directions.</span></span> <span data-ttu-id="53027-112">Mer information finns i [rapportera om icke-postleveranser för e-post i Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).</span><span class="sxs-lookup"><span data-stu-id="53027-112">For more information see [Email non-delivery reports in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).</span></span>

<span data-ttu-id="53027-113">där  _IP-adress_ är IP-adressen för den dator där e-postservern körs.</span><span class="sxs-lookup"><span data-stu-id="53027-113">where  _IP address_ is the IP address of the computer on which the mail server runs.</span></span>

### <a name="to-use-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a><span data-ttu-id="53027-114">Så här använder du en List Portal för att ta bort dig själv från listan Spärrade avsändare</span><span class="sxs-lookup"><span data-stu-id="53027-114">To use delist portal to remove yourself from the blocked senders list</span></span>

1. <span data-ttu-id="53027-115">Gå till i en webbläsare <https://sender.office.com> .</span><span class="sxs-lookup"><span data-stu-id="53027-115">In a web browser, go to <https://sender.office.com>.</span></span>

2. <span data-ttu-id="53027-116">Följ instruktionerna på sidan.</span><span class="sxs-lookup"><span data-stu-id="53027-116">Follow the instructions on the page.</span></span> <span data-ttu-id="53027-117">Kontrol lera att du använder den e-postadress som fel meddelandet skickades till och den IP-adress som anges i fel meddelandet.</span><span class="sxs-lookup"><span data-stu-id="53027-117">Ensure that you use the email address to which the error message was sent, and the IP address that is specified in the error message.</span></span> <span data-ttu-id="53027-118">Du kan bara ange en e-postadress och en IP-adress per besök.</span><span class="sxs-lookup"><span data-stu-id="53027-118">You can only enter one email address and one IP address per visit.</span></span>

3. <span data-ttu-id="53027-119">Klicka på **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="53027-119">Click **Submit**.</span></span>

    <span data-ttu-id="53027-120">Portalen skickar ett e-postmeddelande till den e-postadress som du anger.</span><span class="sxs-lookup"><span data-stu-id="53027-120">The portal sends an email to the email address that you supply.</span></span> <span data-ttu-id="53027-121">E-postmeddelandet ser ut ungefär så här: ![ skärm bild av e-post som tas emot när du skickar en begäran via List portalen](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)</span><span class="sxs-lookup"><span data-stu-id="53027-121">The email will look something like the following: ![Screenshot of email received when you submit a request through the delist portal](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)</span></span>

4. <span data-ttu-id="53027-122">Klicka på bekräftelse länken i e-postmeddelandet som skickas till dig via den nedvisande portalen.</span><span class="sxs-lookup"><span data-stu-id="53027-122">Click the confirmation link in the email sent to you by the delisting portal.</span></span>

    <span data-ttu-id="53027-123">Då kommer du tillbaka till Portal för att avlista.</span><span class="sxs-lookup"><span data-stu-id="53027-123">This brings you back to the delist portal.</span></span>

5. <span data-ttu-id="53027-124">I listan avlistas klickar du på **avlistaa IP**.</span><span class="sxs-lookup"><span data-stu-id="53027-124">In the delist portal, click **Delist IP**.</span></span>

    <span data-ttu-id="53027-125">När IP-adressen tas bort från listan med spärrade avsändare levereras e-postmeddelanden från den IP-adressen till mottagarna som använder Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="53027-125">After the IP address is removed from the blocked senders list, email messages from that IP address will be delivered to recipients who use Microsoft 365.</span></span> <span data-ttu-id="53027-126">Därför bör du kontrol lera att e-postmeddelandet som skickas från den IP-adressen inte är grovt eller skadligt. Annars kan IP-adressen blockeras igen.</span><span class="sxs-lookup"><span data-stu-id="53027-126">So, make sure you're confident that email sent from that IP address won't be abusive or malicious; otherwise, the IP address might be blocked again.</span></span>

    > [!NOTE]
    > <span data-ttu-id="53027-127">Det kan ta upp till 24 timmar eller resultat kan variera innan restriktioner tas bort.</span><span class="sxs-lookup"><span data-stu-id="53027-127">It may take up to 24 hours or results can vary widely before restrictions are removed.</span></span>

<span data-ttu-id="53027-128">Se [skapa listor med säkra avsändare i EOP](create-safe-sender-lists-in-office-365.md) och [utgående spam i EOP](outbound-spam-controls.md) för att förhindra att IP blockeras.</span><span class="sxs-lookup"><span data-stu-id="53027-128">See [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md) and [Outbound spam protection in EOP](outbound-spam-controls.md) to prevent an IP from being blocked.</span></span>
