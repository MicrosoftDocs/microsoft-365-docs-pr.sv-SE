---
title: Ta bort licens från delad postlåda
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
ms.reviewer: nicholak
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
- commerce_licensing
search.appverid:
- BCS160
- MET150
- MOE150
description: 'Ta bort en licens från en delad postlåda för att tilldela den till en annan användare eller returnera licensen så att du inte betalar för den. '
ms.openlocfilehash: d33487879506402c5f0de2f7942c3299c5698b73
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706292"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a><span data-ttu-id="f95ef-103">Ta bort en licens från en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="f95ef-103">Remove a license from a shared mailbox</span></span>

<span data-ttu-id="f95ef-104">Delade postlådor kräver vanligtvis inte en licens.</span><span class="sxs-lookup"><span data-stu-id="f95ef-104">Shared mailboxes usually don't require a license.</span></span> <span data-ttu-id="f95ef-105">Följ de här anvisningarna om du vill ta bort en licens från en delad postlåda så att du kan tilldela den till en användare eller returnera licensen så att du inte betalar för en licens som du inte behöver.</span><span class="sxs-lookup"><span data-stu-id="f95ef-105">Follow these instructions to remove a license from a shared mailbox so that you can either assign it to a user or return the license so that you aren't paying for a license you don't need.</span></span>

> [!NOTE]
>
> <span data-ttu-id="f95ef-106">En licens krävs i följande scenarier:</span><span class="sxs-lookup"><span data-stu-id="f95ef-106">A license is required in the following scenarios:</span></span>
>
> 1. <span data-ttu-id="f95ef-107">Den delade postlådan har mer än 50 GB lagringsutrymme som används.</span><span class="sxs-lookup"><span data-stu-id="f95ef-107">The shared mailbox has more than 50 GB of storage in use.</span></span>
> 2. <span data-ttu-id="f95ef-108">Den delade postlådan använder arkivering på plats.</span><span class="sxs-lookup"><span data-stu-id="f95ef-108">The shared mailbox uses in-place archiving.</span></span>
> 3. <span data-ttu-id="f95ef-109">Den delade postlådan ligger i ett bevarande av juridiska skäl.</span><span class="sxs-lookup"><span data-stu-id="f95ef-109">The shared mailbox is placed in litigation hold.</span></span>
> 4. <span data-ttu-id="f95ef-110">Den delade postlådan har en tilldelad Microsoft Defender-licens.</span><span class="sxs-lookup"><span data-stu-id="f95ef-110">The shared mailbox has a Microsoft Defender license assigned.</span></span>

## <a name="remove-the-license"></a><span data-ttu-id="f95ef-111">Ta bort licensen</span><span class="sxs-lookup"><span data-stu-id="f95ef-111">Remove the license</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="f95ef-112">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="f95ef-112">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="f95ef-113">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="f95ef-113">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="f95ef-114">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="f95ef-114">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

::: moniker-end

   > [!NOTE]
   > <span data-ttu-id="f95ef-115">Du måste ta bort licensen från sidan Aktiva användare.</span><span class="sxs-lookup"><span data-stu-id="f95ef-115">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="f95ef-116">Du kan inte ta bort licensen från sidan Delad postlåda eftersom licenser är användarinställningar.</span><span class="sxs-lookup"><span data-stu-id="f95ef-116">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>
  
2. <span data-ttu-id="f95ef-117">Välj den delade postlådan.</span><span class="sxs-lookup"><span data-stu-id="f95ef-117">Select the shared mailbox.</span></span>

3. <span data-ttu-id="f95ef-118">På fliken **Licenser och appar** expanderar du **Licenser** och avmarkerar rutan för den licens du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="f95ef-118">One the **Licenses and Apps** tab, expand **Licenses** and uncheck the box for the license you want to remove.</span></span>

4. <span data-ttu-id="f95ef-119">Välj **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="f95ef-119">Select **Save changes**.</span></span>

5. <span data-ttu-id="f95ef-120">När du återgår till **sidan Aktiva** användare blir statusen för den delade postlådan **Ej licensierad.**</span><span class="sxs-lookup"><span data-stu-id="f95ef-120">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="f95ef-121">Du betalar fortfarande för licensen.</span><span class="sxs-lookup"><span data-stu-id="f95ef-121">You're still paying for the license.</span></span> <span data-ttu-id="f95ef-122">Ta bort licensen från prenumerationen [om du vill sluta betala för den.](../../commerce/licenses/buy-licenses.md)</span><span class="sxs-lookup"><span data-stu-id="f95ef-122">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/buy-licenses.md).</span></span>

## <a name="related-content"></a><span data-ttu-id="f95ef-123">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="f95ef-123">Related content</span></span>

<span data-ttu-id="f95ef-124">[Om delade postlådor](about-shared-mailboxes.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="f95ef-124">[About shared mailboxes](about-shared-mailboxes.md) (article)</span></span>\
<span data-ttu-id="f95ef-125">[Skapa en delad postlåda](create-a-shared-mailbox.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="f95ef-125">[Create a shared mailbox](create-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="f95ef-126">[Konfigurera en delad postlåda](configure-a-shared-mailbox.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="f95ef-126">[Configure a shared mailbox](configure-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="f95ef-127">[Konvertera en användarpostlåda till en delad postlåda](convert-user-mailbox-to-shared-mailbox.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="f95ef-127">[Convert a user mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="f95ef-128">[Lösa problem med delade postlådor](resolve-issues-with-shared-mailboxes.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="f95ef-128">[Resolve issues with shared mailboxes](resolve-issues-with-shared-mailboxes.md) (article)</span></span>
