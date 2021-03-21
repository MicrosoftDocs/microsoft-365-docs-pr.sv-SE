---
title: Ta bort dig själv från listan med spärrade avsändare
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/18/2016
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0bcecdd4-3343-4cc0-9e58-e19d4de515e8
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: I den här artikeln får du lära dig hur du använder delist-portalen för att ta bort dig själv från listan med spärrade avsändare i Microsoft 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: aef3a5946dee9df7d12232c179f23386db459e06
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921114"
---
# <a name="use-the-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a><span data-ttu-id="a867a-103">Använda avlistningsportalen för att ta bort dig själv från listan med spärrade avsändare</span><span class="sxs-lookup"><span data-stu-id="a867a-103">Use the delist portal to remove yourself from the blocked senders list</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a867a-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="a867a-104">**Applies to**</span></span>
- [<span data-ttu-id="a867a-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="a867a-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="a867a-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="a867a-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="a867a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a867a-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="a867a-108">Får du ett felmeddelande när du försöker skicka ett e-postmeddelande till en mottagare vars e-postadress finns i Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="a867a-108">Are you getting an error message when you try to send an email to a recipient whose email address is in Microsoft 365?</span></span> <span data-ttu-id="a867a-109">Om du anser att du inte borde få felmeddelandet kan du använda delist-portalen för att ta bort dig själv från listan med spärrade avsändare.</span><span class="sxs-lookup"><span data-stu-id="a867a-109">If you think you should not be receiving the error message, you can use the delist portal to remove yourself from the blocked senders list.</span></span>

## <a name="what-is-the-blocked-senders-list"></a><span data-ttu-id="a867a-110">Vad är listan med spärrade avsändare?</span><span class="sxs-lookup"><span data-stu-id="a867a-110">What is the blocked senders list?</span></span>

<span data-ttu-id="a867a-111">Microsoft använder listan med spärrade avsändare för att skydda sina kunder mot skräppost, förfalskning och nätfiske.</span><span class="sxs-lookup"><span data-stu-id="a867a-111">Microsoft uses the blocked senders list to protect its customers from spam, spoofing, and phishing attacks.</span></span> <span data-ttu-id="a867a-112">E-postserverns IP-adress, det vill säga den adress som din e-postserver använder för att identifiera sig på Internet, har märkts som ett potentiellt hot mot Microsoft 365 av en av en mängd olika orsaker.</span><span class="sxs-lookup"><span data-stu-id="a867a-112">Your mail server's IP address, that is, the address your mail server uses to identify itself on the Internet, was tagged as a potential threat to Microsoft 365 for one of a variety of reasons.</span></span> <span data-ttu-id="a867a-113">När Microsoft 365 lägger till IP-adressen i listan förhindrar det all vidare kommunikation mellan IP-adressen och någon av våra kunder via våra datacenter.</span><span class="sxs-lookup"><span data-stu-id="a867a-113">When Microsoft 365 adds the IP address to the list, it prevents all further communication between the IP address and any of our customers through our datacenters.</span></span>

<span data-ttu-id="a867a-114">Du vet att du har lagts till i listan när du får ett svar på ett e-postmeddelande som innehåller ett fel som ser ut ungefär så här:</span><span class="sxs-lookup"><span data-stu-id="a867a-114">You will know you have been added to the list when you receive a response to a mail message that includes an error that looks something like this:</span></span>

> <span data-ttu-id="a867a-115">550 5.7.606-649 Access denied, banned sending IP [_IP address_]; Om du vill begära borttagning från listan besöker <https://sender.office.com/> du den och följer anvisningarna.</span><span class="sxs-lookup"><span data-stu-id="a867a-115">550 5.7.606-649 Access denied, banned sending IP [_IP address_]; To request removal from this list please visit <https://sender.office.com/> and follow the directions.</span></span> <span data-ttu-id="a867a-116">Mer information finns i Rapporter [om utebliven leverans av e-post i Exchange Online.](/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online)</span><span class="sxs-lookup"><span data-stu-id="a867a-116">For more information see [Email non-delivery reports in Exchange Online](/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).</span></span>

<span data-ttu-id="a867a-117">där  _IP-adress_ är IP-adressen för den dator där e-postservern körs.</span><span class="sxs-lookup"><span data-stu-id="a867a-117">where  _IP address_ is the IP address of the computer on which the mail server runs.</span></span>

### <a name="to-use-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a><span data-ttu-id="a867a-118">Så här tar du bort dig själv från listan med spärrade avsändare med hjälp av delist-portalen</span><span class="sxs-lookup"><span data-stu-id="a867a-118">To use delist portal to remove yourself from the blocked senders list</span></span>

1. <span data-ttu-id="a867a-119">Öppna en webbläsare och gå till <https://sender.office.com> .</span><span class="sxs-lookup"><span data-stu-id="a867a-119">In a web browser, go to <https://sender.office.com>.</span></span>

2. <span data-ttu-id="a867a-120">Följ instruktionerna på sidan.</span><span class="sxs-lookup"><span data-stu-id="a867a-120">Follow the instructions on the page.</span></span> <span data-ttu-id="a867a-121">Kontrollera att du använder den e-postadress som felmeddelandet skickades till och den IP-adress som anges i felmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="a867a-121">Ensure that you use the email address to which the error message was sent, and the IP address that is specified in the error message.</span></span> <span data-ttu-id="a867a-122">Du kan bara ange en e-postadress och en IP-adress per besök.</span><span class="sxs-lookup"><span data-stu-id="a867a-122">You can only enter one email address and one IP address per visit.</span></span>

3. <span data-ttu-id="a867a-123">Klicka **på Skicka**.</span><span class="sxs-lookup"><span data-stu-id="a867a-123">Click **Submit**.</span></span>

    <span data-ttu-id="a867a-124">Portalen skickar ett e-postmeddelande till den e-postadress som du skickar.</span><span class="sxs-lookup"><span data-stu-id="a867a-124">The portal sends an email to the email address that you supply.</span></span> <span data-ttu-id="a867a-125">E-postmeddelandet ser ut ungefär så här: Skärmbild av e-postmeddelandet som tas ![ emot när du skickar en begäran via delist-portalen](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)</span><span class="sxs-lookup"><span data-stu-id="a867a-125">The email will look something like the following: ![Screenshot of email received when you submit a request through the delist portal](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)</span></span>

4. <span data-ttu-id="a867a-126">Klicka på bekräftelselänken i det e-postmeddelande som delisteringsportalen skickar till dig.</span><span class="sxs-lookup"><span data-stu-id="a867a-126">Click the confirmation link in the email sent to you by the delisting portal.</span></span>

    <span data-ttu-id="a867a-127">Då kommer du tillbaka till delist-portalen.</span><span class="sxs-lookup"><span data-stu-id="a867a-127">This brings you back to the delist portal.</span></span>

5. <span data-ttu-id="a867a-128">Klicka på Delist IP i **delist-portalen.**</span><span class="sxs-lookup"><span data-stu-id="a867a-128">In the delist portal, click **Delist IP**.</span></span>

    <span data-ttu-id="a867a-129">När IP-adressen tas bort från listan med spärrade avsändare levereras e-postmeddelanden från IP-adressen till mottagare som använder Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a867a-129">After the IP address is removed from the blocked senders list, email messages from that IP address will be delivered to recipients who use Microsoft 365.</span></span> <span data-ttu-id="a867a-130">Se därför till att du är säker på att e-post som skickas från den IP-adressen inte är olämplig eller skadlig. Annars kan IP-adressen vara blockerad igen.</span><span class="sxs-lookup"><span data-stu-id="a867a-130">So, make sure you're confident that email sent from that IP address won't be abusive or malicious; otherwise, the IP address might be blocked again.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a867a-131">Det kan ta upp till 24 timmar eller resultaten kan variera kraftigt innan begränsningarna tas bort.</span><span class="sxs-lookup"><span data-stu-id="a867a-131">It may take up to 24 hours or results can vary widely before restrictions are removed.</span></span>

<span data-ttu-id="a867a-132">Se [Skapa listor över betrodda avsändare i EOP-](create-safe-sender-lists-in-office-365.md) och [utgående skräppostskydd](outbound-spam-controls.md) i EOP om du vill förhindra att en IP blockeras.</span><span class="sxs-lookup"><span data-stu-id="a867a-132">See [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md) and [Outbound spam protection in EOP](outbound-spam-controls.md) to prevent an IP from being blocked.</span></span>