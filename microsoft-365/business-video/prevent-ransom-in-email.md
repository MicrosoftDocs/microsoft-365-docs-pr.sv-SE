---
title: Skapa e-postregler för utpressnings tro Jan
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
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
description: Lär dig hur du skapar e-postregler för att förhindra utpressnings tro Jan.
ms.openlocfilehash: 85898480438225848fc09db9a9c507045f8a182c
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702446"
---
# <a name="create-email-rules-to-prevent-ransomware"></a><span data-ttu-id="a8314-103">Skapa e-postregler för att förhindra utpressnings tro Jan</span><span class="sxs-lookup"><span data-stu-id="a8314-103">Create email rules to prevent ransomware</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrWGt?autoplay=false]

<span data-ttu-id="a8314-104">Microsoft 365 hjälper till att skydda ditt företag mot utpressningar genom att förhindra farliga filer, till exempel Java Script, batch och körbar, från att öppnas i Outlook.</span><span class="sxs-lookup"><span data-stu-id="a8314-104">Microsoft 365 helps protect your business against ransomware by preventing potentially dangerous files, like JavaScript, batch, and executables, from being opened in Outlook.</span></span> <span data-ttu-id="a8314-105">Följ de här stegen om du vill öka den här skydds nivån genom att lägga till regler som blockerar eller varnar för ytterligare typer av filer.</span><span class="sxs-lookup"><span data-stu-id="a8314-105">To increase this level of protection by adding rules that block or warn you of additional types of files, follow these steps.</span></span>

## <a name="try-it"></a><span data-ttu-id="a8314-106">Prova!</span><span class="sxs-lookup"><span data-stu-id="a8314-106">Try it!</span></span>

1. <span data-ttu-id="a8314-107">I administrations centret [https://admin.microsoft.com](https://admin.microsoft.com) går du till och väljer **Exchange** under **administrations Center**.</span><span class="sxs-lookup"><span data-stu-id="a8314-107">From the admin center at [https://admin.microsoft.com](https://admin.microsoft.com), choose **Exchange** under **Admin centers**.</span></span>
1. <span data-ttu-id="a8314-108">I menyn till vänster väljer du **e-postflöde**.</span><span class="sxs-lookup"><span data-stu-id="a8314-108">From the menu on the left, choose **mail flow**.</span></span>
1. <span data-ttu-id="a8314-109">På fliken regler väljer du pilen bredvid plus tecknet (+) och väljer sedan **skapa en ny regel**.</span><span class="sxs-lookup"><span data-stu-id="a8314-109">On the rules tab, choose the arrow next to the plus (+) symbol, and then choose **Create a new rule**.</span></span>
1. <span data-ttu-id="a8314-110">Ange ett namn för regeln på sidan **ny regel** , rulla längst ned och välj sedan **fler alternativ**.</span><span class="sxs-lookup"><span data-stu-id="a8314-110">On the **new rule** page, enter a name for your rule, scroll to the bottom, and then choose **More options**.</span></span>
1. <span data-ttu-id="a8314-111">Under **Använd den här regeln om** markerar du **en bifogad** fil och väljer sedan **fil namns tillägget**.</span><span class="sxs-lookup"><span data-stu-id="a8314-111">Under **Apply this rule if**, select **Any attachment**, and then select **file extension includes these words**.</span></span>
1. <span data-ttu-id="a8314-112">I rutan under **Ange ord eller fraser** anger du det fil namns tillägg som du vill att regeln ska tillämpas på, till exempel fil namns tillägg som kan innehålla makron.</span><span class="sxs-lookup"><span data-stu-id="a8314-112">In the box under **specify words or phrases**, enter the file extensions that you want the rule to be applied to, such as file extensions that can contain macros.</span></span> <span data-ttu-id="a8314-113">Använd plus tecknet (+) för att lägga till ett i taget.</span><span class="sxs-lookup"><span data-stu-id="a8314-113">Use the plus (+) symbol to add them one at a time.</span></span>

    <span data-ttu-id="a8314-114">Läs mer om filtyper genom att läsa [skydda mot utpressnings tro Jan](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/secure-your-business-data#ransomware).</span><span class="sxs-lookup"><span data-stu-id="a8314-114">Learn more about file types by reading [Protect against ransomware](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/secure-your-business-data#ransomware).</span></span>

1. <span data-ttu-id="a8314-115">Bläddra nedåt och välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="a8314-115">Scroll down to review your list, and then choose **OK**.</span></span>
1. <span data-ttu-id="a8314-116">På sidan **ny regel** väljer du **Lägg till villkor** och väljer sedan ett villkor under **gör följande**.</span><span class="sxs-lookup"><span data-stu-id="a8314-116">On the **new rule** page, choose **add condition**, and then choose a condition under **Do the following**.</span></span>
1. <span data-ttu-id="a8314-117">Du har många regel alternativ att välja bland, men i det här exemplet väljer vi att **meddela mottagaren med ett meddelande**.</span><span class="sxs-lookup"><span data-stu-id="a8314-117">You have many rule options to choose from, but in this example we'll choose to **Notify the recipient with a message**.</span></span>
1. <span data-ttu-id="a8314-118">Ange meddelande text för din avisering och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="a8314-118">Enter message text for your notification, and then chose **OK**.</span></span>
1. <span data-ttu-id="a8314-119">Valfritt: Välj **Lägg till undantag** på sidan **ny regel** och ange eventuellt information för undantag till din regel, till exempel meddelanden från betrodda avsändare.</span><span class="sxs-lookup"><span data-stu-id="a8314-119">Optional: On the **new rule** page, choose **add exception**, and enter any details for exceptions to your rule, such as messages from trusted senders.</span></span>
1. <span data-ttu-id="a8314-120">På sidan ny regel väljer du **Spara** och läser den sammanfattade regel informationen.</span><span class="sxs-lookup"><span data-stu-id="a8314-120">On the new rule page, choose **Save**, and review the rule summary information provided.</span></span>