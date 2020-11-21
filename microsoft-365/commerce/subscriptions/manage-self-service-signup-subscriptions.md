---
title: Hantera abonnemang för självbetjäning
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- commerce
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Lär dig hur du hanterar kostnads fria abonnemang för självbetjäning för din organisation.
ms.openlocfilehash: 589466908dcda1461011f046b99be21788c1a018
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376311"
---
# <a name="manage-self-service-sign-up-subscriptions"></a><span data-ttu-id="ceb30-103">Hantera abonnemang för självbetjäning</span><span class="sxs-lookup"><span data-stu-id="ceb30-103">Manage self-service sign-up subscriptions</span></span>

## <a name="what-are-self-service-sign-up-subscriptions"></a><span data-ttu-id="ceb30-104">Vad är självbetjänings abonnemang?</span><span class="sxs-lookup"><span data-stu-id="ceb30-104">What are self-service sign-up subscriptions?</span></span>

<span data-ttu-id="ceb30-105">Det finns ett begränsat antal kostnads fria abonnemang för självbetjäning för användarna i din organisation att anmäla sig för.</span><span class="sxs-lookup"><span data-stu-id="ceb30-105">There are a limited number of free self-service sign-up subscriptions available for users in your organization to sign up for.</span></span> <span data-ttu-id="ceb30-106">En användare kan bara registrera sig för och använda ett själv registrerings abonnemang för sig själva.</span><span class="sxs-lookup"><span data-stu-id="ceb30-106">A user can only sign up for and use a self-service sign-up subscription for themselves.</span></span> <span data-ttu-id="ceb30-107">Du hanterar självbetjänings abonnemang genom att hindra användare från att registrera sig och genom att ta bort kostnads fria abonnemang som användare har registrerat sig för.</span><span class="sxs-lookup"><span data-stu-id="ceb30-107">You manage self-service sign-up subscriptions by blocking users from signing up, and by deleting free subscriptions that users have signed up for.</span></span> <span data-ttu-id="ceb30-108">Mer information om själv registrering och tillgängliga prenumerationer finns i [använda självbetjänings registrering i din organisation](../../admin/misc/self-service-sign-up.md).</span><span class="sxs-lookup"><span data-stu-id="ceb30-108">For more information about self-service sign up and the available subscriptions, see [Using self-service sign up in your organization](../../admin/misc/self-service-sign-up.md).</span></span>

## <a name="view-a-list-of-self-service-sign-up-subscriptions"></a><span data-ttu-id="ceb30-109">Visa en lista över självbetjänings abonnemang</span><span class="sxs-lookup"><span data-stu-id="ceb30-109">View a list of self-service sign-up subscriptions</span></span>

1. <span data-ttu-id="ceb30-110">Gå till sidan fakturering i administrations centret **Billing**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> .</span><span class="sxs-lookup"><span data-stu-id="ceb30-110">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="ceb30-111">På fliken **produkter** väljer du filter ikonen och sedan **gratis**.</span><span class="sxs-lookup"><span data-stu-id="ceb30-111">On the **Products** tab, select the filter icon, then select **Free**.</span></span> <span data-ttu-id="ceb30-112">En lista över alla abonnemang för självbetjänings registrering visas.</span><span class="sxs-lookup"><span data-stu-id="ceb30-112">A list of all self-service sign-up subscriptions is displayed.</span></span>

## <a name="how-are-these-subscriptions-different-from-self-service-purchase-subscriptions"></a><span data-ttu-id="ceb30-113">Hur skiljer sig abonnemangen från självbetjänings abonnemanget?</span><span class="sxs-lookup"><span data-stu-id="ceb30-113">How are these subscriptions different from self-service purchase subscriptions?</span></span>

<span data-ttu-id="ceb30-114">Självbetjänings prenumerationer är gratis och finns tillgängliga i en större lista med produkter än självbetjänings abonnemang.</span><span class="sxs-lookup"><span data-stu-id="ceb30-114">Self-service sign-up subscriptions are free and are available for a larger list of products than self-service purchase subscriptions.</span></span> <span data-ttu-id="ceb30-115">När en användare registrerar sig för ett abonnemang för självbetjänings köp är de ansvarig för att betala för det.</span><span class="sxs-lookup"><span data-stu-id="ceb30-115">When a user signs up for a self-service purchase subscription, they're responsible for paying for it.</span></span> <span data-ttu-id="ceb30-116">Självbetjänings abonnemang är endast tillgängliga för Power Platform-produkter (Power BI, Power app och Power autoautomatisera), Project och Visio.</span><span class="sxs-lookup"><span data-stu-id="ceb30-116">Self-service purchase subscriptions are only available for Power Platform products (Power BI, Power Apps, and Power Automate), Project, and Visio.</span></span> <span data-ttu-id="ceb30-117">Mer information finns i [vanliga frågor och svar om inköp](self-service-purchase-faq.md).</span><span class="sxs-lookup"><span data-stu-id="ceb30-117">For more information, see [Self-service purchase FAQ](self-service-purchase-faq.md).</span></span>

## <a name="block-users-from-signing-up"></a><span data-ttu-id="ceb30-118">Blockera användare från att registrera sig</span><span class="sxs-lookup"><span data-stu-id="ceb30-118">Block users from signing up</span></span>

<span data-ttu-id="ceb30-119">Du använder cmdleten [**set-MsolCompanySettings**](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0&preserve-view=true) med parametern **AllowAdHocSubscriptions** för att kontrol lera om användare ska kunna registrera sig för självbetjänings inloggnings prenumerationer.</span><span class="sxs-lookup"><span data-stu-id="ceb30-119">You use the [**Set-MsolCompanySettings**](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0&preserve-view=true) cmdlet with the **AllowAdHocSubscriptions** parameter to control whether users can sign up for self-service sign-up subscriptions.</span></span> <span data-ttu-id="ceb30-120">Mer information finns i [Hur styr jag självbetjänings inställningar?](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)</span><span class="sxs-lookup"><span data-stu-id="ceb30-120">For more information, see [How do I control self-service settings?](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)</span></span>

## <a name="delete-a-self-service-sign-up-subscription"></a><span data-ttu-id="ceb30-121">Ta bort ett själv registrerings abonnemang</span><span class="sxs-lookup"><span data-stu-id="ceb30-121">Delete a self-service sign-up subscription</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ceb30-122">När du tar bort ett själv registrerings abonnemang hindrar du alla användare från att komma åt sina data och e-postmeddelanden och ta bort alla data och e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="ceb30-122">When you delete a self-service sign-up subscription, you block all users from accessing their data and email and delete all data and email.</span></span>

1. <span data-ttu-id="ceb30-123">Gå till sidan fakturering i administrations centret **Billing**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> .</span><span class="sxs-lookup"><span data-stu-id="ceb30-123">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="ceb30-124">På fliken **produkter** väljer du filter ikonen och sedan **gratis**.</span><span class="sxs-lookup"><span data-stu-id="ceb30-124">On the **Products** tab, select the filter icon, then select **Free**.</span></span>
3. <span data-ttu-id="ceb30-125">Välj det själv registrerings abonnemang som du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="ceb30-125">Select the self-service sign-up subscription that you want to delete.</span></span> 
4. <span data-ttu-id="ceb30-126">På sidan prenumerations information i avsnittet **prenumerationer och betalnings inställningar** väljer du **ta bort abonnemang**.</span><span class="sxs-lookup"><span data-stu-id="ceb30-126">On the subscription details page, in the **Subscriptions and payment settings** section, select **Delete subscription**.</span></span>
5. <span data-ttu-id="ceb30-127">Markera kryss rutan i fönstret **ta bort prenumeration** och välj sedan **ta bort abonnemang**.</span><span class="sxs-lookup"><span data-stu-id="ceb30-127">In the **Delete subscription** pane, select the check box, then select **Delete subscription**.</span></span>

## <a name="i-have-a-self-service-sign-up-subscription-that-blocks-directory-deletion"></a><span data-ttu-id="ceb30-128">Jag har ett självbetjänings abonnemang som hindrar borttagning av kataloger</span><span class="sxs-lookup"><span data-stu-id="ceb30-128">I have a self-service sign-up subscription that blocks directory deletion</span></span>

<span data-ttu-id="ceb30-129">Självbetjänings-och registrerings produkter som enskilda användare kan registrera sig för och skapa en gäst användare för att verifiera i din Azure AD-katalog.</span><span class="sxs-lookup"><span data-stu-id="ceb30-129">The self-service sign-up products that individual users can sign up for also create a guest user for authentication in your Azure AD directory.</span></span> <span data-ttu-id="ceb30-130">För att undvika data förlust tar du bort de här själv tjänst produkterna tills de tas bort helt från katalogen.</span><span class="sxs-lookup"><span data-stu-id="ceb30-130">To avoid data loss, these self-service products block directory deletions until they're fully deleted from the directory.</span></span> <span data-ttu-id="ceb30-131">De kan bara tas bort av Azure AD-administratören. Mer information finns i [ta bort en katalog i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-delete-howto).</span><span class="sxs-lookup"><span data-stu-id="ceb30-131">They can only be deleted by the Azure AD admin. For more information, see [Delete a directory in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-delete-howto).</span></span>