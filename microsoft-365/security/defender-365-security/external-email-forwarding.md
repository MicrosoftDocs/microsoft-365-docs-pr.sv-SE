---
title: Konfigurera och kontrollera extern vidarebefordran av e-post, automatisk vidarebefordran, 5.7.520 Åtkomst nekad, inaktivera extern vidarebefordran, Administratören har inaktiverat extern vidarebefordran, utgående princip för skydd mot skräppost
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: .
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0f42da077ca84341824fad01fcb23eae976336a1
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071442"
---
# <a name="control-automatic-external-email-forwarding-in-microsoft-365"></a><span data-ttu-id="1ede1-103">Kontrollera automatisk vidarebefordran av e-post i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1ede1-103">Control automatic external email forwarding in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="1ede1-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="1ede1-104">**Applies to**</span></span>
- [<span data-ttu-id="1ede1-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="1ede1-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="1ede1-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="1ede1-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="1ede1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1ede1-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="1ede1-108">Som administratör kan du behöva begränsa eller styra automatiskt vidarebefordrade meddelanden till externa mottagare (mottagare utanför organisationen).</span><span class="sxs-lookup"><span data-stu-id="1ede1-108">As an admin, you might have company requirements to restrict or control automatically forwarded messages to external recipients (recipients outside of your organization).</span></span> <span data-ttu-id="1ede1-109">Vidarebefordran av e-post kan vara användbart, men kan också utgöra en säkerhetsrisk på grund av att information kan lämnas ut.</span><span class="sxs-lookup"><span data-stu-id="1ede1-109">Email forwarding can be a useful, but can also pose a security risk due to the potential disclosure of information.</span></span> <span data-ttu-id="1ede1-110">Attacker kan använda den här informationen för att attack mot organisationen eller partnern.</span><span class="sxs-lookup"><span data-stu-id="1ede1-110">Attackers might use this information to attack your organization or partners.</span></span>


<span data-ttu-id="1ede1-111">Följande typer av automatisk vidarebefordran är tillgängliga i Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="1ede1-111">The following types of automatic forwarding are available in Microsoft 365:</span></span>

- <span data-ttu-id="1ede1-112">Användare kan konfigurera [inkorgsregler](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) så att meddelanden automatiskt vidarebefordras till externa avsändare (avsiktligt eller som ett resultat av ett komprometterat konto).</span><span class="sxs-lookup"><span data-stu-id="1ede1-112">Users can configure [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) to automatically forward messages to external senders (deliberately or as a result of a compromised account).</span></span>

- <span data-ttu-id="1ede1-113">Administratörer kan konfigurera [vidarebefordran av postlådor](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (s.k. _SMTP-vidarebefordran)_ så att meddelanden vidarebefordras automatiskt till externa mottagare.</span><span class="sxs-lookup"><span data-stu-id="1ede1-113">Admins can configure [mailbox forwarding](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (also known as _SMTP forwarding_) to automatically forward messages to external recipients.</span></span> <span data-ttu-id="1ede1-114">Administratören kan välja om meddelanden ska vidarebefordras eller behålla kopior av vidarebefordrade meddelanden i postlådan.</span><span class="sxs-lookup"><span data-stu-id="1ede1-114">The admin can choose whether to simply forward messages, or keep copies of forwarded messages in the mailbox.</span></span>

<span data-ttu-id="1ede1-115">Du kan använda principer för utgående skräppostfilter för att styra automatisk vidarebefordran till externa mottagare.</span><span class="sxs-lookup"><span data-stu-id="1ede1-115">You can use outbound spam filter policies to control automatic forwarding to external recipients.</span></span> <span data-ttu-id="1ede1-116">Det finns tre inställningar:</span><span class="sxs-lookup"><span data-stu-id="1ede1-116">Three settings are available:</span></span>

- <span data-ttu-id="1ede1-117">**Automatiskt:** Automatisk extern vidarebefordran blockeras.</span><span class="sxs-lookup"><span data-stu-id="1ede1-117">**Automatic**: Automatic external forwarding is blocked.</span></span> <span data-ttu-id="1ede1-118">Intern automatisk vidarebefordran av meddelanden fortsätter att fungera.</span><span class="sxs-lookup"><span data-stu-id="1ede1-118">Internal automatic forwarding of messages will continue to work.</span></span> <span data-ttu-id="1ede1-119">Detta är standardinställningen.</span><span class="sxs-lookup"><span data-stu-id="1ede1-119">This is the default setting.</span></span>
- <span data-ttu-id="1ede1-120">**På:** Automatisk extern vidarebefordran är tillåtet och inte begränsat.</span><span class="sxs-lookup"><span data-stu-id="1ede1-120">**On**: Automatic external forwarding is allowed and not restricted.</span></span>
- <span data-ttu-id="1ede1-121">**Av:** Automatisk extern vidarebefordran inaktiveras och resulterar i en rapport om utebliven leverans (kallas även NDR-rapport eller icke-leveranskavsändarmeddelande) till avsändaren.</span><span class="sxs-lookup"><span data-stu-id="1ede1-121">**Off**: Automatic external forwarding is disabled and will result in a non-delivery report (also known as an NDR or bounce message) to the sender.</span></span>

<span data-ttu-id="1ede1-122">Anvisningar om hur du konfigurerar de här inställningarna finns i [Konfigurera utgående skräppostfiltrering i EOP.](configure-the-outbound-spam-policy.md)</span><span class="sxs-lookup"><span data-stu-id="1ede1-122">For instructions on how to configure these settings, see [Configure outbound spam filtering in EOP](configure-the-outbound-spam-policy.md).</span></span>

> [!NOTE]
>
> - <span data-ttu-id="1ede1-123">Om du inaktiverar automatisk vidarebefordran inaktiveras alla inkorgsregler (användare) eller vidarebefordran av postlådor (administratörer) som omdirigerar meddelanden till externa adresser.</span><span class="sxs-lookup"><span data-stu-id="1ede1-123">Disabling automatic forwarding disables any Inbox rules (users) or mailbox forwarding (admins) that redirect messages to external addresses.</span></span>
>
> - <span data-ttu-id="1ede1-124">Automatisk vidarebefordran av meddelanden mellan interna användare påverkas inte av inställningarna i principer för utgående skräppostfilter.</span><span class="sxs-lookup"><span data-stu-id="1ede1-124">Automatic forwarding of messages between internal users isn't affected by the settings in outbound spam filter policies.</span></span>
>
> - <span data-ttu-id="1ede1-125">Du kan se information om användare som automatiskt vidarebefordrar meddelanden till externa mottagare i rapporten [Automatiskt vidarebefordrade meddelanden.](mfi-auto-forwarded-messages-report.md)</span><span class="sxs-lookup"><span data-stu-id="1ede1-125">You can see information about users that are automatically forwarding messages to external recipients in the [Auto-forwarded messages report](mfi-auto-forwarded-messages-report.md).</span></span>

## <a name="how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls"></a><span data-ttu-id="1ede1-126">Hur principinställningarna för utgående skräppostfilter fungerar med andra automatiska kontroller för vidarebefordran av e-post</span><span class="sxs-lookup"><span data-stu-id="1ede1-126">How the outbound spam filter policy settings work with other automatic email forwarding controls</span></span>

<span data-ttu-id="1ede1-127">Som administratör kanske du redan har konfigurerat andra kontroller för att tillåta eller blockera automatisk vidarebefordran av e-post.</span><span class="sxs-lookup"><span data-stu-id="1ede1-127">As an admin, you might have already configured other controls to allow or block automatic email forwarding.</span></span> <span data-ttu-id="1ede1-128">Ett exempel:</span><span class="sxs-lookup"><span data-stu-id="1ede1-128">For example:</span></span>

- <span data-ttu-id="1ede1-129">[Fjärrdomäner](/exchange/mail-flow-best-practices/remote-domains/remote-domains) för att tillåta eller blockera automatisk vidarebefordran av e-post till vissa eller alla externa domäner.</span><span class="sxs-lookup"><span data-stu-id="1ede1-129">[Remote domains](/exchange/mail-flow-best-practices/remote-domains/remote-domains) to allow or block automatic email forwarding to some or all external domains.</span></span>

- <span data-ttu-id="1ede1-130">Villkor och åtgärder i [Exchange-e-postflödesregler](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (kallas även transportregler) för att identifiera och blockera automatiskt vidarebefordrade meddelanden till externa mottagare.</span><span class="sxs-lookup"><span data-stu-id="1ede1-130">Conditions and actions in Exchange [mail flow rules](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) to detect and block automatically forwarded messages to external recipients.</span></span>

<span data-ttu-id="1ede1-131">Fjärrdomäninställningar och e-postflödesregler är oberoende av inställningarna i principer för utgående skräppostfilter.</span><span class="sxs-lookup"><span data-stu-id="1ede1-131">Remote domain settings and mail flow rules are independent of the settings in outbound spam filter policies.</span></span> <span data-ttu-id="1ede1-132">Ett exempel:</span><span class="sxs-lookup"><span data-stu-id="1ede1-132">For example:</span></span>

- <span data-ttu-id="1ede1-133">Du tillåter automatisk vidarebefordran för en fjärrdomän, men du blockerar automatisk vidarebefordran i principer för utgående skräppostfilter.</span><span class="sxs-lookup"><span data-stu-id="1ede1-133">You allow automatic forwarding for a remote domain, but you block automatic forwarding in outbound spam filter policies.</span></span> <span data-ttu-id="1ede1-134">I det här exemplet blockeras automatiskt vidarebefordrade meddelanden.</span><span class="sxs-lookup"><span data-stu-id="1ede1-134">In this example, automatically forwarded messages are blocked.</span></span>

- <span data-ttu-id="1ede1-135">Du tillåter automatisk vidarebefordran i principer för utgående skräppostfilter, men du använder e-postflödesregler eller fjärrdomäninställningar för att blockera automatiskt vidarebefordrad e-post.</span><span class="sxs-lookup"><span data-stu-id="1ede1-135">You allow automatic forwarding in outbound spam filter policies, but you use mail flow rules or remote domain settings to block automatically forwarded email.</span></span> <span data-ttu-id="1ede1-136">I det här exemplet blockerar e-postflödesregler eller fjärrdomäninställningar automatiskt vidarebefordrade meddelanden.</span><span class="sxs-lookup"><span data-stu-id="1ede1-136">In this example, the mail flow rules or remote domain settings will block automatically forwarded messages.</span></span>

<span data-ttu-id="1ede1-137">Det här funktionsoberoendet gör att du (till exempel) tillåter automatisk vidarebefordran i principer för utgående skräppostfilter, men använder fjärrdomäner för att styra externa domäner som användare kan vidarebefordra meddelanden till.</span><span class="sxs-lookup"><span data-stu-id="1ede1-137">This feature independence allows you to (for example) allow automatic forwarding in outbound spam filter policies, but use remote domains to control the external domains that users can forward messages to.</span></span>

## <a name="blocked-email-forwarding-messages"></a><span data-ttu-id="1ede1-138">Blockerade vidarebefordran av e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="1ede1-138">Blocked email forwarding messages</span></span>

<span data-ttu-id="1ede1-139">När ett meddelande identifieras som automatiskt vidarebefordrat, och  policyn för utgående skräppostfilter blockerar den aktiviteten, returneras meddelandet till avsändaren i en NDR som innehåller följande information: [](configure-the-outbound-spam-policy.md)</span><span class="sxs-lookup"><span data-stu-id="1ede1-139">When a message is detected as automatically forwarded, and the [outbound spam filter](configure-the-outbound-spam-policy.md) policy *blocks* that activity, the message is returned to the sender in an NDR that contains the following information:</span></span>

`5.7.520 Access denied, Your organization does not allow external forwarding. Please contact your administrator for further assistance. AS(7555)`