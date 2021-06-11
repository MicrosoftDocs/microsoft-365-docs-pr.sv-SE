---
title: Administratörsgranskning för rapporterade meddelanden
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: Lär dig hur du granskar meddelanden som rapporteras och ger feedback till användarna.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 217f5ebb1692d68b5dc70988888bf78d4bd36a0c
ms.sourcegitcommit: d0c160e89e17f451199bc4a85699effd2d935213
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/11/2021
ms.locfileid: "52893734"
---
# <a name="admin-review-for-reported-messages"></a><span data-ttu-id="83724-103">Administratörsgranskning för rapporterade meddelanden</span><span class="sxs-lookup"><span data-stu-id="83724-103">Admin review for reported messages</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!NOTE]
> <span data-ttu-id="83724-104">Informationen i den här artikeln gäller en förhandsversion av en produkt som kan komma att ändras väsentligt innan den släpps till kommersiellt bruk.</span><span class="sxs-lookup"><span data-stu-id="83724-104">The information in this article relates to a preview product that may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="83724-105">Det här dokumentet tillhandahålls endast för utvärderings- och utforskningssyfte.</span><span class="sxs-lookup"><span data-stu-id="83724-105">This document is provided for evaluation and exploration purposes only.</span></span>

<span data-ttu-id="83724-106">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="83724-106">**Applies to**</span></span>
- [<span data-ttu-id="83724-107">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="83724-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="83724-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="83724-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="83724-109">I Microsoft 365 organisationer med Exchange Online-postlådor och Microsoft Defender för Office 365 kan administratörer nu skicka tillbaka mallade meddelanden till slutanvändarna när de har granskat rapporterade meddelanden.</span><span class="sxs-lookup"><span data-stu-id="83724-109">In Microsoft 365 organizations with Exchange Online mailboxes and Microsoft Defender for Office 365, admins can now send templated messages back to end users after they review reported messages.</span></span> <span data-ttu-id="83724-110">Det kan anpassas för din organisation och utifrån administratörens bedömning också.</span><span class="sxs-lookup"><span data-stu-id="83724-110">This can be customized for your organization and based on your admin's verdict as well.</span></span>

<span data-ttu-id="83724-111">Den här funktionen är utformad för att ge feedback till användarna men påverkar inte bedömningarna av meddelanden i systemet.</span><span class="sxs-lookup"><span data-stu-id="83724-111">This feature is designed to give feedback to your users but does not change the verdicts of messages in the system.</span></span> <span data-ttu-id="83724-112">Om du vill hjälpa Microsoft att uppdatera och förbättra filter måste du skicka meddelanden för analys med hjälp av [administratörsinskick.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="83724-112">To help Microsoft update and improve its filters, you will need to submit messages for analysis using [Admin submission](admin-submission.md).</span></span>

<span data-ttu-id="83724-113">Du kan bara markera och meddela användarna om [granskningsresultat](report-false-positives-and-false-negatives.md)om meddelandet har rapporterats som falskt positivt eller falskt negativa.</span><span class="sxs-lookup"><span data-stu-id="83724-113">You will only be able to mark and notify users of review results if the message was reported as a [false positives or false negatives](report-false-positives-and-false-negatives.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="83724-114">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="83724-114">What do you need to know before you begin?</span></span>

- <span data-ttu-id="83724-115">Du öppnar Microsoft 365 Defender-portalen på <https://security.microsoft.com/> .</span><span class="sxs-lookup"><span data-stu-id="83724-115">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="83724-116">Använd för att gå **direkt till sidan** Inskickade <https://security.microsoft.com/reportsubmission> material.</span><span class="sxs-lookup"><span data-stu-id="83724-116">To go directly to the **Submissions** page, use <https://security.microsoft.com/reportsubmission>.</span></span>

- <span data-ttu-id="83724-117">Du måste vara medlem i någon av följande rollgrupper för att kunna ändra konfigurationen för användarinskick:</span><span class="sxs-lookup"><span data-stu-id="83724-117">To modify the configuration for User submissions, you need to be a member of one of the following role groups:</span></span>
  - <span data-ttu-id="83724-118">Organisationshantering eller säkerhetsadministratör i [Microsoft 365 Defender-portalen](permissions-microsoft-365-security-center.md).</span><span class="sxs-lookup"><span data-stu-id="83724-118">Organization Management or Security Administrator in the [Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>
  - <span data-ttu-id="83724-119">Organisationshantering i [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="83724-119">Organization Management in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="83724-120">Du behöver också åtkomst till Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="83724-120">You'll also need access to Exchange Online PowerShell.</span></span> <span data-ttu-id="83724-121">Om kontot som du försöker använda inte har åtkomst till Exchange Online PowerShell visas felmeddelandet Ange en e-postadress i *din domän.*</span><span class="sxs-lookup"><span data-stu-id="83724-121">If the account that you're trying to use doesn't have access to Exchange Online PowerShell, you'll receive an error that says *Specify an email address in your domain*.</span></span> <span data-ttu-id="83724-122">Mer information om hur du aktiverar eller inaktiverar åtkomst till Exchange Online PowerShell finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="83724-122">For more information about enabling or disabling access to Exchange Online PowerShell, see the following topics:</span></span>
  - [<span data-ttu-id="83724-123">Aktivera eller inaktivera åtkomst till Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="83724-123">Enable or disable access to Exchange Online PowerShell</span></span>](/powershell/exchange/disable-access-to-exchange-online-powershell)
  - [<span data-ttu-id="83724-124">Klientåtkomstregler i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="83724-124">Client Access Rules in Exchange Online</span></span>](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="configure-the-messages-used-to-notify-users"></a><span data-ttu-id="83724-125">Konfigurera meddelanden som används för att meddela användarna</span><span class="sxs-lookup"><span data-stu-id="83724-125">Configure the messages used to notify users</span></span>

1. <span data-ttu-id="83724-126">I Microsoft 365 Defender-portalen går du till Principer för **&-&** e-& principer för hot andra avsnittet \>  \>  \>  \> **Användarrapporterade meddelandeinställningar**.</span><span class="sxs-lookup"><span data-stu-id="83724-126">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Threat policies** \> **Others** section \> **User reported message settings**.</span></span>

2. <span data-ttu-id="83724-127">Om du vill ange avsändarens visningsnamn på sidan Användarinskickade användare markerar du kryssrutan för  Ange Office 365-e-postadress som ska användas som avsändare under avsnittet E-postaviseringar för **administratörsgranskningsresultat** och anger det namn du vill använda. </span><span class="sxs-lookup"><span data-stu-id="83724-127">On the **User submissions** page, if you want to specify the sender display name, check the box for **Specify Office 365 email address to use as sender** under the **Email notifications for admin review results** section, and enter in the name you wish to use.</span></span> <span data-ttu-id="83724-128">Det här är den e-postadress som visas i Outlook svar skickas till.</span><span class="sxs-lookup"><span data-stu-id="83724-128">This is the email address that will be visible in Outlook and where replies will go to.</span></span>

3. <span data-ttu-id="83724-129">Om du vill anpassa någon av mallarna klickar du på Anpassa **e-postavisering**.</span><span class="sxs-lookup"><span data-stu-id="83724-129">If you want to customize any of the templates, click **Customize email notification**.</span></span> <span data-ttu-id="83724-130">I den här utfällningen kan du bara anpassa följande:</span><span class="sxs-lookup"><span data-stu-id="83724-130">In this flyout, you will be able to customize only the following:</span></span>
    - <span data-ttu-id="83724-131">Fiske</span><span class="sxs-lookup"><span data-stu-id="83724-131">Phishing</span></span>
    - <span data-ttu-id="83724-132">Skräppost</span><span class="sxs-lookup"><span data-stu-id="83724-132">Junk</span></span>
    - <span data-ttu-id="83724-133">Inga hot hittades</span><span class="sxs-lookup"><span data-stu-id="83724-133">No threats found</span></span>
    - <span data-ttu-id="83724-134">Utbildning om information</span><span class="sxs-lookup"><span data-stu-id="83724-134">Awareness training</span></span>
    - <span data-ttu-id="83724-135">Sidfot</span><span class="sxs-lookup"><span data-stu-id="83724-135">Footer</span></span>

4. <span data-ttu-id="83724-136">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="83724-136">When you're finished, click **Save**.</span></span> <span data-ttu-id="83724-137">Om du vill ta bort dessa värden **klickar du på** Ta bort på sidan Användarinskick.</span><span class="sxs-lookup"><span data-stu-id="83724-137">To clear these values, click **Discard** on the User submissions page.</span></span>
