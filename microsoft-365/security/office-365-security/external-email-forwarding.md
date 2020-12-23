---
title: Konfigurera och kontrol lera extern e-postvidarekoppling, automatisk vidarebefordran, 5.7.520 åtkomst nekad, inaktivera extern vidarebefordran, administratören har inaktiverat extern vidarebefordran, utgående princip för skräp post
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: .
ms.openlocfilehash: f75504941e8481d35458ad2ae6b5e8a72c5e8c8c
ms.sourcegitcommit: a49338bde6923b13132c7b9e4c6bb75c14163c72
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/23/2020
ms.locfileid: "49728194"
---
# <a name="control-automatic-external-email-forwarding-in-microsoft-365"></a><span data-ttu-id="76e19-103">Kontrol lera automatisk extern e-postvidarebefordran i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="76e19-103">Control automatic external email forwarding in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="76e19-104">Som administratör kan du ha företags krav för att begränsa eller kontrol lera automatiskt vidarebefordrade meddelanden till externa mottagare (mottagare utanför organisationen).</span><span class="sxs-lookup"><span data-stu-id="76e19-104">As an admin, you might have company requirements to restrict or control automatically forwarded messages to external recipients (recipients outside of your organization).</span></span> <span data-ttu-id="76e19-105">Vidarebefordran av e-post kan vara en användbar funktion, men kan också utgöra en säkerhets risk på grund av eventuell information.</span><span class="sxs-lookup"><span data-stu-id="76e19-105">Email forwarding can be a useful feature, but can also pose a security risk due to the potential disclosure of information.</span></span> <span data-ttu-id="76e19-106">Angripare kan använda den här informationen för att attackera din organisation eller dina partners.</span><span class="sxs-lookup"><span data-stu-id="76e19-106">Attackers might use this information to attack your organization or partners.</span></span>

<span data-ttu-id="76e19-107">Följande typer av automatisk vidarebefordran är tillgängliga i Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="76e19-107">The following types of automatic forwarding are available in Microsoft 365:</span></span>

- <span data-ttu-id="76e19-108">Användare kan konfigurera [regler för Inkorgen](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) för att automatiskt vidarebefordra meddelanden till externa avsändare (avsiktligt eller som ett resultat av ett komprometterat konto).</span><span class="sxs-lookup"><span data-stu-id="76e19-108">Users can configure [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) to automatically forward messages to external senders (deliberately or as a result of a compromised account).</span></span>

- <span data-ttu-id="76e19-109">Administratörer kan konfigurera [vidarebefordran av post lådor](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (kallas även för _SMTP-vidarekoppling_) för att automatiskt vidarebefordra meddelanden till externa mottagare.</span><span class="sxs-lookup"><span data-stu-id="76e19-109">Admins can configure [mailbox forwarding](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (also known as _SMTP forwarding_) to automatically forward messages to external recipients.</span></span> <span data-ttu-id="76e19-110">Administratören kan välja om du bara vill vidarekoppla meddelanden eller Spara kopior av vidarebefordrade meddelanden i post lådan.</span><span class="sxs-lookup"><span data-stu-id="76e19-110">The admin can choose whether to simply forward messages, or keep copies of forwarded messages in the mailbox.</span></span>

<span data-ttu-id="76e19-111">Du kan använda filter principer för utgående e-post för att styra automatisk vidarebefordran till externa mottagare.</span><span class="sxs-lookup"><span data-stu-id="76e19-111">You can use outbound spam filter policies to control automatic forwarding to external recipients.</span></span> <span data-ttu-id="76e19-112">Tre inställningar är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="76e19-112">Three settings are available:</span></span>

- <span data-ttu-id="76e19-113">**Automatisk**: Automatisk extern vidarebefordran är blockerad.</span><span class="sxs-lookup"><span data-stu-id="76e19-113">**Automatic**: Automatic external forwarding is blocked.</span></span> <span data-ttu-id="76e19-114">Intern automatisk vidarebefordran av meddelanden fortsätter att fungera.</span><span class="sxs-lookup"><span data-stu-id="76e19-114">Internal automatic forwarding of messages will continue to work.</span></span> <span data-ttu-id="76e19-115">Detta är standardinställningen.</span><span class="sxs-lookup"><span data-stu-id="76e19-115">This is the default setting.</span></span>
- <span data-ttu-id="76e19-116">**Den**: Automatisk extern vidarebefordran är tillåten och inte begränsad.</span><span class="sxs-lookup"><span data-stu-id="76e19-116">**On**: Automatic external forwarding is allowed and not restricted.</span></span>
- <span data-ttu-id="76e19-117">**Av**: Automatisk extern vidarebefordran är inaktiverat och resulterar i en rapport om utebliven leverans (kallas även för ett NDR-eller studs meddelande) för avsändaren.</span><span class="sxs-lookup"><span data-stu-id="76e19-117">**Off**: Automatic external forwarding is disabled and will result in a non-delivery report (also known as an NDR or bounce message) to the sender.</span></span>

<span data-ttu-id="76e19-118">Anvisningar om hur du konfigurerar dessa inställningar finns i [Konfigurera utgående skräp post filtrering i EOP](configure-the-outbound-spam-policy.md).</span><span class="sxs-lookup"><span data-stu-id="76e19-118">For instructions on how to configure these settings, see [Configure outbound spam filtering in EOP](configure-the-outbound-spam-policy.md).</span></span>

> [!NOTE]
>
> - <span data-ttu-id="76e19-119">Om du inaktiverar automatisk vidarebefordring inaktive ras eventuella regler för Inkorgen (användare) eller vidarebefordran av post lådor som omdirigerar meddelanden till externa adresser.</span><span class="sxs-lookup"><span data-stu-id="76e19-119">Disabling automatic forwarding disables any Inbox rules (users) or mailbox forwarding (admins) that redirect messages to external addresses.</span></span>
>
> - <span data-ttu-id="76e19-120">Automatisk vidarebefordran av meddelanden mellan interna användare påverkas inte av inställningarna i principer för skräp post filter.</span><span class="sxs-lookup"><span data-stu-id="76e19-120">Automatic forwarding of messages between internal users isn't affected by the settings in outbound spam filter policies.</span></span>
>
> - <span data-ttu-id="76e19-121">Du kan se information om användare som automatiskt vidarebefordrar meddelanden till externa mottagare i [rapporten för automatiskt vidarebefordrade meddelanden](mfi-auto-forwarded-messages-report.md).</span><span class="sxs-lookup"><span data-stu-id="76e19-121">You can see information about users that are automatically forwarding messages to external recipients in the [Auto-forwarded messages report](mfi-auto-forwarded-messages-report.md).</span></span>

## <a name="how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls"></a><span data-ttu-id="76e19-122">Så fungerar princip inställningarna för utgående skräp post med andra kontroller för automatisk e-postvidarekoppling</span><span class="sxs-lookup"><span data-stu-id="76e19-122">How the outbound spam filter policy settings work with other automatic email forwarding controls</span></span>

<span data-ttu-id="76e19-123">Som administratör kan du ha konfigurerat andra kontroller för att tillåta eller blockera automatisk vidarebefordran av e-post.</span><span class="sxs-lookup"><span data-stu-id="76e19-123">As an admin, you might have already configured other controls to allow or block automatic email forwarding.</span></span> <span data-ttu-id="76e19-124">Ett exempel:</span><span class="sxs-lookup"><span data-stu-id="76e19-124">For example:</span></span>

- <span data-ttu-id="76e19-125">[Fjärrdomäner](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) för att tillåta eller blockera automatisk vidarebefordran av e-post till vissa eller alla externa domäner.</span><span class="sxs-lookup"><span data-stu-id="76e19-125">[Remote domains](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) to allow or block automatic email forwarding to some or all external domains.</span></span>

- <span data-ttu-id="76e19-126">Villkor och åtgärder i regler för Exchange [-postflöde](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (kallas även transport regler) för att identifiera och blockera automatiskt vidarebefordrade meddelanden till externa mottagare.</span><span class="sxs-lookup"><span data-stu-id="76e19-126">Conditions and actions in Exchange [mail flow rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) to detect and block automatically forwarded messages to external recipients.</span></span>

<span data-ttu-id="76e19-127">Inställningar för fjärrdomäner och e-postflöde är oberoende av inställningarna i principer för skräp post filter.</span><span class="sxs-lookup"><span data-stu-id="76e19-127">Remote domain settings and mail flow rules are independent of the settings in outbound spam filter policies.</span></span> <span data-ttu-id="76e19-128">Ett exempel:</span><span class="sxs-lookup"><span data-stu-id="76e19-128">For example:</span></span>

- <span data-ttu-id="76e19-129">Du tillåter automatisk vidarebefordring för en fjärran sluten domän, men du blockerar automatisk vidarebefordran i filter principer för utgående e-post.</span><span class="sxs-lookup"><span data-stu-id="76e19-129">You allow automatic forwarding for a remote domain, but you block automatic forwarding in outbound spam filter policies.</span></span> <span data-ttu-id="76e19-130">I det här exemplet blockeras automatiskt vidarebefordrade meddelanden.</span><span class="sxs-lookup"><span data-stu-id="76e19-130">In this example, automatically forwarded messages are blocked.</span></span>

- <span data-ttu-id="76e19-131">Du tillåter automatisk vidarebefordran i principer för skräp post filter, men du använder regler för e-post och domän inställningar för att blockera automatiskt vidarebefordrade e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="76e19-131">You allow automatic forwarding in outbound spam filter policies, but you use mail flow rules or remote domain settings to block automatically forwarded email.</span></span> <span data-ttu-id="76e19-132">I det här exemplet blockerar inställningarna för e-postflöden eller fjärrdomäner automatiskt vidarebefordrade meddelanden.</span><span class="sxs-lookup"><span data-stu-id="76e19-132">In this example, the mail flow rules or remote domain settings will block automatically forwarded messages.</span></span>

<span data-ttu-id="76e19-133">Med den här funktionen kan du (till exempel) tillåta automatisk vidarebefordran i filter principer för utgående e-post, men Använd fjärrdomäner för att styra vilka externa domäner användarna kan vidarekoppla meddelanden till.</span><span class="sxs-lookup"><span data-stu-id="76e19-133">This feature independence allows you to (for example) allow automatic forwarding in outbound spam filter policies, but use remote domains to control the external domains that users can forward messages to.</span></span>

## <a name="the-blocked-email-forwarding-message"></a><span data-ttu-id="76e19-134">Meddelande om blockerad e-post</span><span class="sxs-lookup"><span data-stu-id="76e19-134">The blocked email forwarding message</span></span>

<span data-ttu-id="76e19-135">När ett meddelande identifieras som automatiskt vidarebefordrat och organisations principen *blockerar* den aktiviteten, returneras meddelandet till avsändaren i en NDR som innehåller följande information:</span><span class="sxs-lookup"><span data-stu-id="76e19-135">When a message is detected as automatically forwarded, and the organizational policy *blocks* that activity, the message is returned to the sender in an NDR that contains the following information:</span></span>

`5.7.520 Access denied, Your organization does not allow external forwarding. Please contact your administrator for further assistance. AS(7555)`
