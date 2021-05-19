---
title: Hantera prenumerationer på självbetjäning
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_subscriptions
search.appverid: MET150
description: Lär dig hur du hanterar kostnadsfria registreringsprenumerationer för självbetjäning för din organisation.
ms.date: 03/17/2021
ms.openlocfilehash: 741c9e0b45f127ffc0753b34982073f90c525d5b
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52536076"
---
# <a name="manage-self-service-sign-up-subscriptions"></a><span data-ttu-id="1e417-103">Hantera prenumerationer på självbetjäning</span><span class="sxs-lookup"><span data-stu-id="1e417-103">Manage self-service sign-up subscriptions</span></span>

## <a name="what-are-self-service-sign-up-subscriptions"></a><span data-ttu-id="1e417-104">Vad är självbetjäning för registrering av prenumerationer?</span><span class="sxs-lookup"><span data-stu-id="1e417-104">What are self-service sign-up subscriptions?</span></span>

<span data-ttu-id="1e417-105">Det finns ett begränsat antal kostnadsfria registreringsprenumerationer på självbetjäning som användarna i organisationen kan registrera sig för.</span><span class="sxs-lookup"><span data-stu-id="1e417-105">There are a limited number of free self-service sign-up subscriptions available for users in your organization to sign up for.</span></span> <span data-ttu-id="1e417-106">En användare kan bara registrera sig själv och använda en självbetjäningsprenumeration.</span><span class="sxs-lookup"><span data-stu-id="1e417-106">A user can only sign up for and use a self-service sign-up subscription for themselves.</span></span> <span data-ttu-id="1e417-107">Du hanterar prenumerationer på registrering via självbetjäning genom att blockera användare från att registrera sig och genom att ta bort kostnadsfria prenumerationer som användare har registrerat sig för.</span><span class="sxs-lookup"><span data-stu-id="1e417-107">You manage self-service sign-up subscriptions by blocking users from signing up, and by deleting free subscriptions that users have signed up for.</span></span> <span data-ttu-id="1e417-108">Mer information om självbetjäning för registrering och tillgängliga prenumerationer finns i Registrera [dig med självbetjäning i din organisation.](../../admin/misc/self-service-sign-up.md)</span><span class="sxs-lookup"><span data-stu-id="1e417-108">For more information about self-service sign up and the available subscriptions, see [Using self-service sign up in your organization](../../admin/misc/self-service-sign-up.md).</span></span>

## <a name="view-a-list-of-self-service-sign-up-subscriptions"></a><span data-ttu-id="1e417-109">Visa en lista över självbetjäning för registrering av prenumerationer</span><span class="sxs-lookup"><span data-stu-id="1e417-109">View a list of self-service sign-up subscriptions</span></span>

1. <span data-ttu-id="1e417-110">I administrationscentret går du till sidan **Fakturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Dina produkter</a>.</span><span class="sxs-lookup"><span data-stu-id="1e417-110">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="1e417-111">På fliken **Produkter** väljer du filterikonen och sedan **Gratis**.</span><span class="sxs-lookup"><span data-stu-id="1e417-111">On the **Products** tab, select the filter icon, then select **Free**.</span></span> <span data-ttu-id="1e417-112">En lista med alla prenumerationer på självbetjäning visas.</span><span class="sxs-lookup"><span data-stu-id="1e417-112">A list of all self-service sign-up subscriptions is displayed.</span></span>

## <a name="how-are-these-subscriptions-different-from-self-service-purchase-subscriptions"></a><span data-ttu-id="1e417-113">Hur skiljer sig de här prenumerationerna från prenumerationer på självbetjäning?</span><span class="sxs-lookup"><span data-stu-id="1e417-113">How are these subscriptions different from self-service purchase subscriptions?</span></span>

<span data-ttu-id="1e417-114">Självbetjäning för registrering av prenumerationer är kostnadsfria och är tillgängliga för en större lista med produkter än prenumerationer för självbetjäning.</span><span class="sxs-lookup"><span data-stu-id="1e417-114">Self-service sign-up subscriptions are free and are available for a larger list of products than self-service purchase subscriptions.</span></span> <span data-ttu-id="1e417-115">När en användare registrerar sig för en prenumeration på självbetjäning är de ansvariga för att betala för den.</span><span class="sxs-lookup"><span data-stu-id="1e417-115">When a user signs up for a self-service purchase subscription, they're responsible for paying for it.</span></span> <span data-ttu-id="1e417-116">Prenumerationer på självbetjäning är endast tillgängliga för Power Platform-produkter (Power BI, Power Apps och Power Automate), Project och Visio.</span><span class="sxs-lookup"><span data-stu-id="1e417-116">Self-service purchase subscriptions are only available for Power Platform products (Power BI, Power Apps, and Power Automate), Project, and Visio.</span></span> <span data-ttu-id="1e417-117">Mer information finns i Vanliga frågor [och svar om självbetjäning för köp.](self-service-purchase-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="1e417-117">For more information, see [Self-service purchase FAQ](self-service-purchase-faq.yml).</span></span>

## <a name="block-users-from-signing-up"></a><span data-ttu-id="1e417-118">Blockera användare från att registrera sig</span><span class="sxs-lookup"><span data-stu-id="1e417-118">Block users from signing up</span></span>

<span data-ttu-id="1e417-119">Du använder cmdleten [**Set-MsolCompanySettings**](/powershell/module/msonline/set-msolcompanysettings?preserve-view=true&view=azureadps-1.0) med parametern **AllowAdHocSubscriptions** för att styra om användare kan registrera sig för självbetjäningsprenumerationer.</span><span class="sxs-lookup"><span data-stu-id="1e417-119">You use the [**Set-MsolCompanySettings**](/powershell/module/msonline/set-msolcompanysettings?preserve-view=true&view=azureadps-1.0) cmdlet with the **AllowAdHocSubscriptions** parameter to control whether users can sign up for self-service sign-up subscriptions.</span></span> <span data-ttu-id="1e417-120">Mer information finns i [Hur styr jag självbetjäningsuppgifter?](/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)</span><span class="sxs-lookup"><span data-stu-id="1e417-120">For more information, see [How do I control self-service settings?](/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)</span></span>

## <a name="delete-a-self-service-sign-up-subscription"></a><span data-ttu-id="1e417-121">Ta bort en prenumeration med självbetjäning</span><span class="sxs-lookup"><span data-stu-id="1e417-121">Delete a self-service sign-up subscription</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1e417-122">När du tar bort en prenumeration på självbetjäning blockerar du alla användare från att komma åt sina data och sin e-post och ta bort alla data och e-post.</span><span class="sxs-lookup"><span data-stu-id="1e417-122">When you delete a self-service sign-up subscription, you block all users from accessing their data and email and delete all data and email.</span></span>

1. <span data-ttu-id="1e417-123">I administrationscentret går du till sidan **Fakturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Dina produkter</a>.</span><span class="sxs-lookup"><span data-stu-id="1e417-123">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="1e417-124">På fliken **Produkter** väljer du filterikonen och sedan **Gratis**.</span><span class="sxs-lookup"><span data-stu-id="1e417-124">On the **Products** tab, select the filter icon, then select **Free**.</span></span>
3. <span data-ttu-id="1e417-125">Välj den självbetjäning för registrering av prenumeration som du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="1e417-125">Select the self-service sign-up subscription that you want to delete.</span></span> 
4. <span data-ttu-id="1e417-126">Välj Ta bort prenumeration i avsnittet Prenumerationer **och betalningsinställningar på** sidan **prenumerationsinformation.**</span><span class="sxs-lookup"><span data-stu-id="1e417-126">On the subscription details page, in the **Subscriptions and payment settings** section, select **Delete subscription**.</span></span>
5. <span data-ttu-id="1e417-127">I fönstret **Ta bort** prenumeration markerar du kryssrutan och väljer sedan Ta **bort prenumeration.**</span><span class="sxs-lookup"><span data-stu-id="1e417-127">In the **Delete subscription** pane, select the check box, then select **Delete subscription**.</span></span>

## <a name="i-have-a-self-service-sign-up-subscription-that-blocks-directory-deletion"></a><span data-ttu-id="1e417-128">Jag har en prenumeration med självbetjäning som blockerar katalogborttagning</span><span class="sxs-lookup"><span data-stu-id="1e417-128">I have a self-service sign-up subscription that blocks directory deletion</span></span>

<span data-ttu-id="1e417-129">Självbetjäning för registrering av produkter som enskilda användare kan registrera sig för skapar även en gästanvändare för autentisering i din Azure AD-katalog.</span><span class="sxs-lookup"><span data-stu-id="1e417-129">The self-service sign-up products that individual users can sign up for also create a guest user for authentication in your Azure AD directory.</span></span> <span data-ttu-id="1e417-130">För att undvika dataförlust blockerar dessa självbetjäningsprodukter katalogborttagningar tills de helt tas bort från katalogen.</span><span class="sxs-lookup"><span data-stu-id="1e417-130">To avoid data loss, these self-service products block directory deletions until they're fully deleted from the directory.</span></span> <span data-ttu-id="1e417-131">De kan bara tas bort av Azure AD-administratören. Mer information finns i Ta [bort en katalog i Azure Active Directory](/azure/active-directory/users-groups-roles/directory-delete-howto).</span><span class="sxs-lookup"><span data-stu-id="1e417-131">They can only be deleted by the Azure AD admin. For more information, see [Delete a directory in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-delete-howto).</span></span>
