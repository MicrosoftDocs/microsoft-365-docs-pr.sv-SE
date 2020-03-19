---
title: Använd avlistningsportalen för att ta bort dig själv från listan blockerade avsändare i Office 365
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
description: Får du ett felmeddelande när du försöker skicka ett e-postmeddelande till en mottagare vars e-postadress finns i Office 365? Om du anser att du inte ska ta emot felmeddelandet kan du använda avlistningsportalen för att ta bort dig själv från listan med blockerade avsändare i Office 365.
ms.openlocfilehash: 3e131addb391ecbf90d74ad4fdfa65b802c5e1ac
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42808982"
---
# <a name="use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-list"></a><span data-ttu-id="61e6a-104">Använd avlistningsportalen för att ta bort dig själv från listan blockerade avsändare i Office 365</span><span class="sxs-lookup"><span data-stu-id="61e6a-104">Use the delist portal to remove yourself from the Office 365 blocked senders list</span></span>

<span data-ttu-id="61e6a-105">Får du ett felmeddelande när du försöker skicka ett e-postmeddelande till en mottagare vars e-postadress finns i Office 365?</span><span class="sxs-lookup"><span data-stu-id="61e6a-105">Are you getting an error message when you try to send an email to a recipient whose email address is in Office 365?</span></span> <span data-ttu-id="61e6a-106">Om du anser att du inte ska ta emot felmeddelandet kan du använda avlistningsportalen för att ta bort dig själv från listan med blockerade avsändare i Office 365.</span><span class="sxs-lookup"><span data-stu-id="61e6a-106">If you think you should not be receiving the error message, you can use the delist portal to remove yourself from the Office 365 blocked senders list.</span></span>

## <a name="what-is-the-office-365-blocked-senders-list"></a><span data-ttu-id="61e6a-107">Vad är listan över blockerade avsändare i Office 365?</span><span class="sxs-lookup"><span data-stu-id="61e6a-107">What is the Office 365 blocked senders list?</span></span>

<span data-ttu-id="61e6a-108">Microsoft använder listan blockerade avsändare för att skydda sina kunder från skräppost, förfalskning och nätfiskeattacker.</span><span class="sxs-lookup"><span data-stu-id="61e6a-108">Microsoft uses the blocked senders list to protect its customers from spam, spoofing, and phishing attacks.</span></span> <span data-ttu-id="61e6a-109">E-postserverns IP-adress, det vill fram till att den adress som e-postservern använder för att identifiera sig på Internet, har taggats som ett potentiellt hot mot Office 365 av en mängd olika orsaker.</span><span class="sxs-lookup"><span data-stu-id="61e6a-109">Your mail server's IP address, that is, the address your mail server uses to identify itself on the Internet, was tagged as a potential threat to Office 365 for one of a variety of reasons.</span></span> <span data-ttu-id="61e6a-110">När Office 365 lägger till IP-adressen i listan förhindrar den all ytterligare kommunikation mellan IP-adressen och någon av våra kunder via våra datacenter.</span><span class="sxs-lookup"><span data-stu-id="61e6a-110">When Office 365 adds the IP address to the list, it prevents all further communication between the IP address and any of our customers through our datacenters.</span></span>

<span data-ttu-id="61e6a-111">Du vet att du har lagts till i listan när du får ett svar på ett e-postmeddelande som innehåller ett fel som ser ut ungefär så här:</span><span class="sxs-lookup"><span data-stu-id="61e6a-111">You will know you have been added to the list when you receive a response to a mail message that includes an error that looks something like this:</span></span>

> <span data-ttu-id="61e6a-112">550 5.7.606-649 Access nekas, förbjuden att skicka IP [_IP-adress_]; För att begära borttagning https://sender.office.com/ från denna lista besök och följ anvisningarna.</span><span class="sxs-lookup"><span data-stu-id="61e6a-112">550 5.7.606-649 Access denied, banned sending IP [_IP address_]; To request removal from this list please visit https://sender.office.com/ and follow the directions.</span></span> <span data-ttu-id="61e6a-113">Mer information finns i [Rapporter om utebliven leverans via e-post i Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).</span><span class="sxs-lookup"><span data-stu-id="61e6a-113">For more information see [Email non-delivery reports in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).</span></span>

<span data-ttu-id="61e6a-114">där _IP-adress_ är IP-adressen för den dator där e-postservern körs.</span><span class="sxs-lookup"><span data-stu-id="61e6a-114">where  _IP address_ is the IP address of the computer on which the mail server runs.</span></span>

### <a name="to-use-the-office-365-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a><span data-ttu-id="61e6a-115">Så här använder du avlistningsportalen för Office 365 för att ta bort dig själv från listan blockerade avsändare</span><span class="sxs-lookup"><span data-stu-id="61e6a-115">To use the Office 365 delist portal to remove yourself from the blocked senders list</span></span>

1. <span data-ttu-id="61e6a-116">I en webbläsare går [https://sender.office.com](https://sender.office.com)du till .</span><span class="sxs-lookup"><span data-stu-id="61e6a-116">In a web browser, go to [https://sender.office.com](https://sender.office.com).</span></span>

2. <span data-ttu-id="61e6a-117">Följ instruktionerna på sidan.</span><span class="sxs-lookup"><span data-stu-id="61e6a-117">Follow the instructions on the page.</span></span> <span data-ttu-id="61e6a-118">Kontrollera att du använder den e-postadress som felmeddelandet skickades till och ip-adressen som anges i felmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="61e6a-118">Ensure that you use the email address to which the error message was sent, and the IP address that is specified in the error message.</span></span> <span data-ttu-id="61e6a-119">Du kan bara ange en e-postadress och en IP-adress per besök.</span><span class="sxs-lookup"><span data-stu-id="61e6a-119">You can only enter one email address and one IP address per visit.</span></span>

3. <span data-ttu-id="61e6a-120">Klicka på **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="61e6a-120">Click **Submit**.</span></span>

    <span data-ttu-id="61e6a-121">Portalen skickar ett e-postmeddelande till den e-postadress som du anger.</span><span class="sxs-lookup"><span data-stu-id="61e6a-121">The portal sends an email to the email address that you supply.</span></span> <span data-ttu-id="61e6a-122">E-postmeddelandet kommer att se ![ut ungefär så här: Skärmdump av e-post som tas emot när du skickar en begäran via avlistningsportalen](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)</span><span class="sxs-lookup"><span data-stu-id="61e6a-122">The email will look something like the following: ![Screenshot of email received when you submit a request through the delist portal](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)</span></span>

4. <span data-ttu-id="61e6a-123">Klicka på bekräftelselänken i e-postmeddelandet som skickas till dig av avlistningsportalen.</span><span class="sxs-lookup"><span data-stu-id="61e6a-123">Click the confirmation link in the email sent to you by the delisting portal.</span></span>

    <span data-ttu-id="61e6a-124">Detta tar dig tillbaka till avlistportalen.</span><span class="sxs-lookup"><span data-stu-id="61e6a-124">This brings you back to the delist portal.</span></span>

5. <span data-ttu-id="61e6a-125">Klicka på **Avlista IP**i avlistningsportalen .</span><span class="sxs-lookup"><span data-stu-id="61e6a-125">In the delist portal, click **Delist IP**.</span></span>

    <span data-ttu-id="61e6a-126">När IP-adressen har tagits bort från listan blockerade avsändare levereras e-postmeddelanden från den IP-adressen till mottagare som använder Office 365.</span><span class="sxs-lookup"><span data-stu-id="61e6a-126">After the IP address is removed from the blocked senders list, email messages from that IP address will be delivered to recipients who use Office 365.</span></span> <span data-ttu-id="61e6a-127">Så, se till att du är säker på att e-post som skickas från den IP-adressen inte kommer att vara kränkande eller skadligt; Annars kan IP-adressen blockeras igen.</span><span class="sxs-lookup"><span data-stu-id="61e6a-127">So, make sure you're confident that email sent from that IP address won't be abusive or malicious; otherwise, the IP address might be blocked again.</span></span>

    > [!NOTE]
    > <span data-ttu-id="61e6a-128">Det kan ta upp till 24 timmar eller resultaten kan variera kraftigt innan begränsningar tas bort.</span><span class="sxs-lookup"><span data-stu-id="61e6a-128">It may take up to 24 hours or results can vary widely before restrictions are removed.</span></span>

<span data-ttu-id="61e6a-129">Läs om [Hur du förhindrar att riktiga e-postmeddelanden markeras som skräppost i Office 365](prevent-email-from-being-marked-as-spam.md ) och Styra [utgående skräppost i Office 365](outbound-spam-controls.md) för att förhindra att IP svartlistas.</span><span class="sxs-lookup"><span data-stu-id="61e6a-129">Read about [How to prevent real email from being marked as spam in Office 365](prevent-email-from-being-marked-as-spam.md ) and [Controlling outbound spam in Office 365](outbound-spam-controls.md) to prevent IP from being blacklisted.</span></span>
