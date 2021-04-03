---
title: Skapa e-postregler för utpressningstrojan
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Lär dig hur du skapar e-postregler för att förhindra utpressningstrojaner.
ms.openlocfilehash: 96822916753f2f70d481c213e7e31046f7081446
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580504"
---
# <a name="create-email-rules-to-prevent-ransomware"></a><span data-ttu-id="df8e6-103">Skapa e-postregler för att förhindra utpressningstrojaner</span><span class="sxs-lookup"><span data-stu-id="df8e6-103">Create email rules to prevent ransomware</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrWGt?autoplay=false]

<span data-ttu-id="df8e6-104">Microsoft 365 hjälper till att skydda företaget mot utpressningstrojaner genom att förhindra att filer som potentiellt är skadliga, som JavaScript, batchfiler och körbara filer, öppnas i Outlook.</span><span class="sxs-lookup"><span data-stu-id="df8e6-104">Microsoft 365 helps protect your business against ransomware by preventing potentially dangerous files, like JavaScript, batch, and executables, from being opened in Outlook.</span></span> <span data-ttu-id="df8e6-105">Följ de här anvisningarna om du vill öka den här skyddsnivån genom att lägga till regler som blockerar eller varnar för ytterligare typer av filer.</span><span class="sxs-lookup"><span data-stu-id="df8e6-105">To increase this level of protection by adding rules that block or warn you of additional types of files, follow these steps.</span></span>

## <a name="try-it"></a><span data-ttu-id="df8e6-106">Prova!</span><span class="sxs-lookup"><span data-stu-id="df8e6-106">Try it!</span></span>

1. <span data-ttu-id="df8e6-107">Från administrationscentret i [https://admin.microsoft.com](https://admin.microsoft.com) väljer du **Exchange** under **Administrationscenter**.</span><span class="sxs-lookup"><span data-stu-id="df8e6-107">From the admin center at [https://admin.microsoft.com](https://admin.microsoft.com), choose **Exchange** under **Admin centers**.</span></span>
1. <span data-ttu-id="df8e6-108">I menyn till vänster väljer du **E-postflöde**.</span><span class="sxs-lookup"><span data-stu-id="df8e6-108">From the menu on the left, choose **mail flow**.</span></span>
1. <span data-ttu-id="df8e6-109">På fliken Regler väljer du pilen bredvid plustecknet (+) och väljer sedan **Skapa en ny regel.**</span><span class="sxs-lookup"><span data-stu-id="df8e6-109">On the rules tab, choose the arrow next to the plus (+) symbol, and then choose **Create a new rule**.</span></span>
1. <span data-ttu-id="df8e6-110">På sidan **ny regel** anger du ett namn för regeln, bläddrar till slutet och väljer sedan **Fler alternativ**.</span><span class="sxs-lookup"><span data-stu-id="df8e6-110">On the **new rule** page, enter a name for your rule, scroll to the bottom, and then choose **More options**.</span></span>
1. <span data-ttu-id="df8e6-111">Under **Använd den här regeln om** väljer du Valfri **bifogad** fil och väljer sedan **filnamnstillägget innehåller följande ord**.</span><span class="sxs-lookup"><span data-stu-id="df8e6-111">Under **Apply this rule if**, select **Any attachment**, and then select **file extension includes these words**.</span></span>
1. <span data-ttu-id="df8e6-112">I rutan under ange ord eller fraser anger du de filnamnstillägg som du vill att regeln ska tillämpas på, till exempel **filnamnstillägg** som kan innehålla makron.</span><span class="sxs-lookup"><span data-stu-id="df8e6-112">In the box under **specify words or phrases**, enter the file extensions that you want the rule to be applied to, such as file extensions that can contain macros.</span></span> <span data-ttu-id="df8e6-113">Använd plustecknet (+) för att lägga till ett i taget.</span><span class="sxs-lookup"><span data-stu-id="df8e6-113">Use the plus (+) symbol to add them one at a time.</span></span>

    <span data-ttu-id="df8e6-114">Mer information om filtyper finns i [Skydda mot utpressningstrojaner.](../admin/security-and-compliance/secure-your-business-data.md#ransomware)</span><span class="sxs-lookup"><span data-stu-id="df8e6-114">Learn more about file types by reading [Protect against ransomware](../admin/security-and-compliance/secure-your-business-data.md#ransomware).</span></span>

1. <span data-ttu-id="df8e6-115">Rulla nedåt för att granska listan och välj sedan **OK.**</span><span class="sxs-lookup"><span data-stu-id="df8e6-115">Scroll down to review your list, and then choose **OK**.</span></span>
1. <span data-ttu-id="df8e6-116">På sidan **ny regel** väljer du Lägg **till villkor** och sedan ett villkor under **Gör följande.**</span><span class="sxs-lookup"><span data-stu-id="df8e6-116">On the **new rule** page, choose **add condition**, and then choose a condition under **Do the following**.</span></span>
1. <span data-ttu-id="df8e6-117">Det finns många regelalternativ att välja bland, men i det här exemplet väljer vi **att meddela mottagaren med ett meddelande**.</span><span class="sxs-lookup"><span data-stu-id="df8e6-117">You have many rule options to choose from, but in this example we'll choose to **Notify the recipient with a message**.</span></span>
1. <span data-ttu-id="df8e6-118">Ange meddelandetext för meddelandet och välj sedan **OK.**</span><span class="sxs-lookup"><span data-stu-id="df8e6-118">Enter message text for your notification, and then chose **OK**.</span></span>
1. <span data-ttu-id="df8e6-119">Valfritt: På **sidan ny** regel väljer du lägg till undantag **och** anger all information om undantag för regeln, till exempel meddelanden från betrodda avsändare.</span><span class="sxs-lookup"><span data-stu-id="df8e6-119">Optional: On the **new rule** page, choose **add exception**, and enter any details for exceptions to your rule, such as messages from trusted senders.</span></span>
1. <span data-ttu-id="df8e6-120">På sidan ny regel väljer du Spara **och granskar** den sammanfattande informationen för regeln.</span><span class="sxs-lookup"><span data-stu-id="df8e6-120">On the new rule page, choose **Save**, and review the rule summary information provided.</span></span>