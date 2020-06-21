---
title: Overifierad avsändare
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Den här artikeln kommer att guida dig om, hur du förhindrar att nätfiskemeddelanden når din postlåda, Outlook.com och Outlook på webben.
ms.openlocfilehash: ed317f5673aa37b91e8c5092eb127b8df6be944e
ms.sourcegitcommit: 2acd9ec5e9d150389975e854c7883efc186a9432
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754838"
---
# <a name="unverified-sender"></a><span data-ttu-id="50425-103">Overifierad avsändare</span><span class="sxs-lookup"><span data-stu-id="50425-103">Unverified Sender</span></span>

> [!NOTE]
> <span data-ttu-id="50425-104">Dessa uppdateringar distribueras nu och kanske inte är tillgängliga för alla användare.</span><span class="sxs-lookup"><span data-stu-id="50425-104">These updates are rolling out now, and might not be available for all users.</span></span> <span data-ttu-id="50425-105">Den här funktionen stöds för enterprise Outlook.com- och Enterprise Outlook Win32-användare.</span><span class="sxs-lookup"><span data-stu-id="50425-105">This feature is supported for Enterprise Outlook.com and Enterprise Outlook Win32 desktop users.</span></span> <span data-ttu-id="50425-106">Den är för närvarande inte tillgänglig för office 365-användare för konsumenter.</span><span class="sxs-lookup"><span data-stu-id="50425-106">It is not currently available for consumer Office 365 users.</span></span>

<span data-ttu-id="50425-107">För att förhindra att nätfiskemeddelanden når din postlåda verifierar Office 365 att avsändarna är de som de säger att de är och markerar misstänkta meddelanden som skräppost.</span><span class="sxs-lookup"><span data-stu-id="50425-107">To prevent phishing messages from reaching your mailbox, Office 365 verifies that the senders are who they say they are and mark suspicious messages as junk email.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="50425-108">När ett meddelande markeras som ett nätfiskebedrägeri visas en varning högst upp på sidan, men alla länkar i meddelandet kan fortfarande öppnas.</span><span class="sxs-lookup"><span data-stu-id="50425-108">When a message is marked as a phishing scam, Outlook displays a warning at the top of the page, but any links in the message can still be opened.</span></span>

## <a name="how-can-i-identify-a-suspicious-message-in-my-inbox"></a><span data-ttu-id="50425-109">Hur kan jag identifiera ett misstänkt meddelande i inkorgen?</span><span class="sxs-lookup"><span data-stu-id="50425-109">How can I identify a suspicious message in my inbox?</span></span>

<span data-ttu-id="50425-110">Outlook visar indikatorer när avsändaren av ett meddelande antingen inte kan identifieras eller deras identitet skiljer sig från vad du ser i från-adressen.</span><span class="sxs-lookup"><span data-stu-id="50425-110">Outlook shows indicators when the sender of a message either can't be identified or their identity is different from what you see in the From address.</span></span>

## <a name="you-see-a--in-the-sender-image"></a><span data-ttu-id="50425-111">Du ser en "?"i avsändaren bilden</span><span class="sxs-lookup"><span data-stu-id="50425-111">You see a '?' in the sender image</span></span>

<span data-ttu-id="50425-112">När Office 365 inte kan verifiera avsändarens identitet med hjälp av e-postautentiseringstekniker visas en '?' i avsändningsavbildningen.</span><span class="sxs-lookup"><span data-stu-id="50425-112">When Office 365 can't verify the identity of the sender using email authentication techniques, a '?' is displayed in the sender image.</span></span>

![Meddelandet klarade inte verifieringen](../../media/message-did-not-pass-verification.jpg)

<span data-ttu-id="50425-114">Alla meddelanden som inte autentiserar är inte skadliga.</span><span class="sxs-lookup"><span data-stu-id="50425-114">Not every message that fails to authenticate is malicious.</span></span> <span data-ttu-id="50425-115">Du bör dock vara försiktig med att interagera med meddelanden som inte autentiserar om du inte känner igen avsändaren.</span><span class="sxs-lookup"><span data-stu-id="50425-115">However, you should be careful about interacting with messages that don't authenticate if you don't recognize the sender.</span></span> <span data-ttu-id="50425-116">Eller, om du känner igen en avsändare som normalt inte har en "?"i avsändaren bilden, men du plötsligt börjar se det, som kan vara ett tecken avsändaren är förfalskad.</span><span class="sxs-lookup"><span data-stu-id="50425-116">Or, if you recognize a sender that normally doesn't have a '?' in the sender image, but you suddenly start seeing it, that could be a sign the sender is being spoofed.</span></span>

## <a name="how-to-manage-which-messages-receive-the-unverified-sender-treatment"></a><span data-ttu-id="50425-117">Så här hanterar du vilka meddelanden som får den overifierade avsändaren</span><span class="sxs-lookup"><span data-stu-id="50425-117">How to manage which messages receive the unverified sender treatment</span></span> 

<span data-ttu-id="50425-118">Om du är Office 365-kund kan du hantera den här funktionen via Office 365 Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="50425-118">If you are an Office 365 customer you can manage this feature through the Office 365 Security & Compliance Center.</span></span>

- <span data-ttu-id="50425-119">I Security & Compliance Center kan globala administratörer eller säkerhetsadministratörer aktivera eller inaktivera funktionen genom skydd mot förfalskning enligt anti-Phish-principen.</span><span class="sxs-lookup"><span data-stu-id="50425-119">In the Security & Compliance Center, global or security administrators can turn the feature on or off, through anti-spoofing protection under the Anti-Phish policy.</span></span> <span data-ttu-id="50425-120">Dessutom kan du använda cmdleten **Set-AntiPhishPolicy** i Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="50425-120">Additionally, you can use the **Set-AntiPhishPolicy** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="50425-121">Mer information finns [i Skydd mot nätfiske i Office 365](anti-phishing-protection.md) och [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/set-antiphishpolicy).</span><span class="sxs-lookup"><span data-stu-id="50425-121">For details, see [Anti-phishing protection in Office 365](anti-phishing-protection.md) and [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/set-antiphishpolicy).</span></span>

    ![Redigera oautentiserade avsändare i det grafiska gränssnittet.](../../media/unverified-sender-article-editing-unauthenticated-senders.jpg)

- <span data-ttu-id="50425-123">Om en administratör har identifierat ett falskt positivt och en avsändare inte ska få den overifierade avsändaren behandling, kan en av följande åtgärder vidtas för att lägga till avsändaren till Spoof Intelligence spoof tillåta lista:</span><span class="sxs-lookup"><span data-stu-id="50425-123">If an admin has identified a false positive, and a sender should not be receiving the unverified sender treatment, one of the following actions can be taken to add the sender to the Spoof Intelligence spoof allow list:</span></span>

  - <span data-ttu-id="50425-124">Lägg till domänparet via Spoof Intelligence Insight.</span><span class="sxs-lookup"><span data-stu-id="50425-124">Add the domain pair through the Spoof Intelligence Insight.</span></span> <span data-ttu-id="50425-125">Mer information finns i [Genomgång: falska underrättelseinsikt](walkthrough-spoof-intelligence-insight.md).</span><span class="sxs-lookup"><span data-stu-id="50425-125">For details, see [Walkthrough: spoof intelligence insight](walkthrough-spoof-intelligence-insight.md).</span></span>

  - <span data-ttu-id="50425-126">Lägg till domänparet via cmdleten **Set-PhishFilterPolicy** i Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="50425-126">Add the domain pair through the **Set-PhishFilterPolicy** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="50425-127">Mer information finns i [Ange-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-phishfilterpolicy) och [Konfigurera Office 365 ATP-principer för nätfiske och nätfiske.](set-up-anti-phishing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="50425-127">For details, see [Set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-phishfilterpolicy) and [Set up Office 365 ATP anti-phishing and anti-phishing policies](set-up-anti-phishing-policies.md).</span></span>

<span data-ttu-id="50425-128">Dessutom tillämpar vi inte den overifierade avsändaren om meddelandet levererades till Inkorgen via regler för e-postflöde (kallas även transportregler) eller safe domain list (policyer mot skräppost).</span><span class="sxs-lookup"><span data-stu-id="50425-128">Additionally, we don't apply the unverified sender treatment if the message was delivered to the Inbox via mail flow rules (also known as transport rules) or the Safe Domain List (anti-spam policies).</span></span>

## <a name="how-to-manage-the-via-tag"></a><span data-ttu-id="50425-129">Så här hanterar du taggen "via"</span><span class="sxs-lookup"><span data-stu-id="50425-129">How to manage the 'via' tag</span></span> 

<span data-ttu-id="50425-130">Om du är Office 365-kund kan du hantera den här funktionen via Office 365 Security & Compliance Center, på samma sätt som du hanterar den overifierade avsändande behandlingen.</span><span class="sxs-lookup"><span data-stu-id="50425-130">If you are an Office 365 customer you can manage this feature through the Office 365 Security & Compliance center, the same way that you manage the unverified sender treatment.</span></span> <span data-ttu-id="50425-131">Om du lägger till avsändaren i spoof Intelligence spoof tillåta lista, "via" behandling kommer inte att tillämpas.</span><span class="sxs-lookup"><span data-stu-id="50425-131">If you add the sender to the Spoof Intelligence spoof allow list, the 'via' treatment will not be applied.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="50425-132">Vanliga frågor och svar</span><span class="sxs-lookup"><span data-stu-id="50425-132">Frequently asked questions</span></span>

### <a name="what-criteria-does-outlookcom-and-outlook-win32-desktop-use-to-add-the--and-the-via-properties"></a><span data-ttu-id="50425-133">Vilka kriterier använder Outlook.com och Outlook Win32-skrivbordet för att lägga till egenskaperna "?" och "via"?</span><span class="sxs-lookup"><span data-stu-id="50425-133">What criteria does Outlook.com and Outlook Win32 desktop use to add the '?' and the 'via' properties?</span></span>

<span data-ttu-id="50425-134">För avsändarens avsändare: Outlook.com kräver att meddelandet skickar antingen SPF- eller DKIM-autentisering och tar emot antingen ett dmarc-pass eller ett sammansatt autentiseringspass från Office 365 Spoof Intelligence.</span><span class="sxs-lookup"><span data-stu-id="50425-134">For the '?' in the sender image:  Outlook.com requires that the message pass either SPF or DKIM authentication and receive either a dmarc pass, or a composite authentication pass from Office 365 Spoof Intelligence.</span></span> <span data-ttu-id="50425-135">Mer information finns [i Konfigurera SPF i Office 365 för att förhindra förfalskning](set-up-spf-in-office-365-to-help-prevent-spoofing.md) och användning av [DKIM för att validera utgående e-post som skickas från din anpassade domän i Office 365](use-dkim-to-validate-outbound-email.md).</span><span class="sxs-lookup"><span data-stu-id="50425-135">For details, see [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md) and [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).</span></span>

<span data-ttu-id="50425-136">För via-taggen: Om domänen i från-adressen skiljer sig från domänen i DKIM-signaturen eller SMTP-MAIL FRÅN visas Outlook.com domänen i ett av dessa två fält (föredrar DKIM-signaturen).</span><span class="sxs-lookup"><span data-stu-id="50425-136">For the via tag: If the domain in the From address is different from the domain in the DKIM signature or the SMTP MAIL FROM, Outlook.com displays the domain in one of those two fields (preferring the DKIM signature).</span></span>

### <a name="how-do-i-remove-the--without-utilizing-the-spoof-intelligence-spoof-allow-list"></a><span data-ttu-id="50425-137">Hur tar jag bort "?"?</span><span class="sxs-lookup"><span data-stu-id="50425-137">How do I remove the '?' without utilizing the Spoof Intelligence spoof allow list?</span></span>

<span data-ttu-id="50425-138">För avsändarens avsändare: Som avsändare bör du autentisera meddelandet med antingen SPF eller DKIM.</span><span class="sxs-lookup"><span data-stu-id="50425-138">For the '?' in the sender image: As a sender, you should authenticate your message with either SPF or DKIM.</span></span>

<span data-ttu-id="50425-139">För via-taggen: Som avsändare bör du se till att antingen domänen i DKIM-signaturen eller SMTP MAIL FROM är samma som, eller är en underdomän för, domänen i Från-adressen.</span><span class="sxs-lookup"><span data-stu-id="50425-139">For the via tag: As a sender, you should ensure that either the domain in the DKIM signature or the SMTP MAIL FROM is the same as, or is a subdomain of, the domain in the From address.</span></span>

### <a name="do-outlookcom-and-outlook-win32-desktop-show-this-for-every-message-that-doesnt-pass-authentication"></a><span data-ttu-id="50425-140">Visar Outlook.com och Outlook Win32-skrivbordet detta för varje meddelande som inte skickar autentisering?</span><span class="sxs-lookup"><span data-stu-id="50425-140">Do Outlook.com and Outlook Win32 desktop show this for every message that doesn't pass authentication?</span></span>

<span data-ttu-id="50425-141">Inte nödvändigtvis.</span><span class="sxs-lookup"><span data-stu-id="50425-141">Not necessarily.</span></span> <span data-ttu-id="50425-142">Office 365 kan ha andra egenskaper i meddelandet för att autentisera avsändaren.</span><span class="sxs-lookup"><span data-stu-id="50425-142">Office 365 may have other properties within the message to authenticate the sender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="50425-143">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="50425-143">Related topics</span></span>

[<span data-ttu-id="50425-144">Skydda ditt Outlook.com e-postkonto</span><span class="sxs-lookup"><span data-stu-id="50425-144">Help protect your Outlook.com email account</span></span>](https://support.microsoft.com/office/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

[<span data-ttu-id="50425-145">Hur man hanterar nätfiske i Outlook.com</span><span class="sxs-lookup"><span data-stu-id="50425-145">How to deal with phishing in Outlook.com</span></span>](https://support.microsoft.com/office/0d882ea5-eedc-4bed-aebc-079ffa1105a3)

[<span data-ttu-id="50425-146">Filtrera skräppost och skräppost i Outlook på webben</span><span class="sxs-lookup"><span data-stu-id="50425-146">Filter junk email and spam in Outlook on the web</span></span>](https://support.microsoft.com/office/db786e79-54e2-40cc-904f-d89d57b7f41d)
