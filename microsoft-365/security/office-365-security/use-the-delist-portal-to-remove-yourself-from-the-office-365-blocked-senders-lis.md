---
title: Ta bort dig själv från listan blockerade avsändare
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
ms.custom:
- seo-marvel-apr2020
description: I den här artikeln får du lära dig hur du använder avlistningsportalen för att ta bort dig själv från listan blockerade avsändare från Microsoft 365.
ms.openlocfilehash: 700382a494865b80116cfd8419213ed43b35b8a1
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034992"
---
# <a name="use-the-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a><span data-ttu-id="b434e-103">Använda avlistningsportalen för att ta bort dig själv från listan med spärrade avsändare</span><span class="sxs-lookup"><span data-stu-id="b434e-103">Use the delist portal to remove yourself from the blocked senders list</span></span>

<span data-ttu-id="b434e-104">Får du ett felmeddelande när du försöker skicka ett e-postmeddelande till en mottagare vars e-postadress finns i Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="b434e-104">Are you getting an error message when you try to send an email to a recipient whose email address is in Microsoft 365?</span></span> <span data-ttu-id="b434e-105">Om du tycker att du inte ska få felmeddelandet kan du använda avlistningsportalen för att ta bort dig själv från listan blockerade avsändare.</span><span class="sxs-lookup"><span data-stu-id="b434e-105">If you think you should not be receiving the error message, you can use the delist portal to remove yourself from the blocked senders list.</span></span>

## <a name="what-is-the-blocked-senders-list"></a><span data-ttu-id="b434e-106">Vad är listan med blockerade avsändare?</span><span class="sxs-lookup"><span data-stu-id="b434e-106">What is the blocked senders list?</span></span>

<span data-ttu-id="b434e-107">Microsoft använder listan blockerade avsändare för att skydda sina kunder från skräppost, förfalskning och nätfiskeattacker.</span><span class="sxs-lookup"><span data-stu-id="b434e-107">Microsoft uses the blocked senders list to protect its customers from spam, spoofing, and phishing attacks.</span></span> <span data-ttu-id="b434e-108">Din e-postservers IP-adress, det villa om den adress som e-postservern använder för att identifiera sig på Internet, har taggats som ett potentiellt hot mot Microsoft 365 av olika anledningar.</span><span class="sxs-lookup"><span data-stu-id="b434e-108">Your mail server's IP address, that is, the address your mail server uses to identify itself on the Internet, was tagged as a potential threat to Microsoft 365 for one of a variety of reasons.</span></span> <span data-ttu-id="b434e-109">När Microsoft 365 lägger till IP-adressen i listan förhindrar det all ytterligare kommunikation mellan IP-adressen och någon av våra kunder via våra datacenter.</span><span class="sxs-lookup"><span data-stu-id="b434e-109">When Microsoft 365 adds the IP address to the list, it prevents all further communication between the IP address and any of our customers through our datacenters.</span></span>

<span data-ttu-id="b434e-110">Du vet att du har lagts till i listan när du får ett svar på ett e-postmeddelande som innehåller ett felmeddelande som ser ut ungefär så här:</span><span class="sxs-lookup"><span data-stu-id="b434e-110">You will know you have been added to the list when you receive a response to a mail message that includes an error that looks something like this:</span></span>

> <span data-ttu-id="b434e-111">550 5.7.606-649 Tillträde nekad, förbjuden att skicka IP [_IP-adress_]; För att begära borttagning https://sender.office.com/ från denna lista besök och följ anvisningarna.</span><span class="sxs-lookup"><span data-stu-id="b434e-111">550 5.7.606-649 Access denied, banned sending IP [_IP address_]; To request removal from this list please visit https://sender.office.com/ and follow the directions.</span></span> <span data-ttu-id="b434e-112">Mer information finns i [Rapporter om utebliven post i Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).</span><span class="sxs-lookup"><span data-stu-id="b434e-112">For more information see [Email non-delivery reports in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).</span></span>

<span data-ttu-id="b434e-113">där _IP-adressen_ är IP-adressen för den dator där e-postservern körs.</span><span class="sxs-lookup"><span data-stu-id="b434e-113">where  _IP address_ is the IP address of the computer on which the mail server runs.</span></span>

### <a name="to-use-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a><span data-ttu-id="b434e-114">Så här använder du avlistningsportalen för att ta bort dig själv från listan över blockerade avsändare</span><span class="sxs-lookup"><span data-stu-id="b434e-114">To use delist portal to remove yourself from the blocked senders list</span></span>

1. <span data-ttu-id="b434e-115">Gå till [https://sender.office.com](https://sender.office.com)i en webbläsare .</span><span class="sxs-lookup"><span data-stu-id="b434e-115">In a web browser, go to [https://sender.office.com](https://sender.office.com).</span></span>

2. <span data-ttu-id="b434e-116">Följ instruktionerna på sidan.</span><span class="sxs-lookup"><span data-stu-id="b434e-116">Follow the instructions on the page.</span></span> <span data-ttu-id="b434e-117">Se till att du använder den e-postadress som felmeddelandet skickades till och den IP-adress som anges i felmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="b434e-117">Ensure that you use the email address to which the error message was sent, and the IP address that is specified in the error message.</span></span> <span data-ttu-id="b434e-118">Du kan bara ange en e-postadress och en IP-adress per besök.</span><span class="sxs-lookup"><span data-stu-id="b434e-118">You can only enter one email address and one IP address per visit.</span></span>

3. <span data-ttu-id="b434e-119">Klicka på **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="b434e-119">Click **Submit**.</span></span>

    <span data-ttu-id="b434e-120">Portalen skickar ett e-postmeddelande till den e-postadress som du anger.</span><span class="sxs-lookup"><span data-stu-id="b434e-120">The portal sends an email to the email address that you supply.</span></span> <span data-ttu-id="b434e-121">E-postmeddelandet ser ut ![ungefär så här: Skärmdump av e-post som tas emot när du skickar en begäran via avlisteportalen](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)</span><span class="sxs-lookup"><span data-stu-id="b434e-121">The email will look something like the following: ![Screenshot of email received when you submit a request through the delist portal](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)</span></span>

4. <span data-ttu-id="b434e-122">Klicka på bekräftelselänken i e-postmeddelandet som skickas till dig av avlistningsportalen.</span><span class="sxs-lookup"><span data-stu-id="b434e-122">Click the confirmation link in the email sent to you by the delisting portal.</span></span>

    <span data-ttu-id="b434e-123">Detta tar dig tillbaka till avlisteportalen.</span><span class="sxs-lookup"><span data-stu-id="b434e-123">This brings you back to the delist portal.</span></span>

5. <span data-ttu-id="b434e-124">Klicka på **Avlistnings-IP**i avlistningsportalen .</span><span class="sxs-lookup"><span data-stu-id="b434e-124">In the delist portal, click **Delist IP**.</span></span>

    <span data-ttu-id="b434e-125">När IP-adressen har tagits bort från listan över blockerade avsändare levereras e-postmeddelanden från den IP-adressen till mottagare som använder Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b434e-125">After the IP address is removed from the blocked senders list, email messages from that IP address will be delivered to recipients who use Microsoft 365.</span></span> <span data-ttu-id="b434e-126">Se därför till att du är säker på att e-post som skickas från den IP-adressen inte kommer att vara stötande eller skadligt. Annars kan IP-adressen blockeras igen.</span><span class="sxs-lookup"><span data-stu-id="b434e-126">So, make sure you're confident that email sent from that IP address won't be abusive or malicious; otherwise, the IP address might be blocked again.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b434e-127">Det kan ta upp till 24 timmar eller resultaten kan variera kraftigt innan begränsningar tas bort.</span><span class="sxs-lookup"><span data-stu-id="b434e-127">It may take up to 24 hours or results can vary widely before restrictions are removed.</span></span>

<span data-ttu-id="b434e-128">Se [Skapa listor över betrodda avsändare i Office 365](create-safe-sender-lists-in-office-365.md) och Skydd för skräppost från [utgående information i Office 365](outbound-spam-controls.md) för att förhindra att IP-åtkomst blir svartlistat.</span><span class="sxs-lookup"><span data-stu-id="b434e-128">See [Create safe sender lists in Office 365](create-safe-sender-lists-in-office-365.md) and [Outbound spam protection in Office 365](outbound-spam-controls.md) to prevent IP from being blacklisted.</span></span>
