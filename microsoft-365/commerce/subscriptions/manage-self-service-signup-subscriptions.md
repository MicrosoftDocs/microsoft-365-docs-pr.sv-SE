---
title: Hantera registreringsprenumerationer för självbetjäning
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
description: Läs om hur du hanterar kostnadsfria registreringsprenumerationer för självbetjäning för din organisation.
ms.openlocfilehash: 81c67292a394c62d6057022babb88aa8796b9b3d
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44403252"
---
# <a name="manage-self-service-sign-up-subscriptions"></a><span data-ttu-id="e7228-103">Hantera registreringsprenumerationer för självbetjäning</span><span class="sxs-lookup"><span data-stu-id="e7228-103">Manage self-service sign-up subscriptions</span></span>

## <a name="what-are-self-service-sign-up-subscriptions"></a><span data-ttu-id="e7228-104">Vad är självbetjäningsprenumerationer?</span><span class="sxs-lookup"><span data-stu-id="e7228-104">What are self-service sign-up subscriptions?</span></span>

<span data-ttu-id="e7228-105">Det finns ett begränsat antal kostnadsfria registreringsprenumerationer för självbetjäning som användare i organisationen kan registrera sig för.</span><span class="sxs-lookup"><span data-stu-id="e7228-105">There are a limited number of free self-service sign-up subscriptions that users in your organization can sign up for.</span></span> <span data-ttu-id="e7228-106">En användare kan bara registrera sig för och använda en självbetjäningsprenumeration för sig själva.</span><span class="sxs-lookup"><span data-stu-id="e7228-106">A user can only sign up for and use a self-service sign-up subscription for themselves.</span></span> <span data-ttu-id="e7228-107">Dessa prenumerationer visas på sidan **Dina produkter,** markeras som **Kostnadsfria**och har en anteckning som säger: "Det här är en kostnadsfri prenumeration som aktiveras av användare i företaget."</span><span class="sxs-lookup"><span data-stu-id="e7228-107">These subscriptions appear on the **Your products** page, are marked as **Free**, and have a note that says, "This is a free subscription activated by users in your company."</span></span> <span data-ttu-id="e7228-108">Du kan hantera självbetjäningsprenumerationer genom att blockera användare från att registrera sig och genom att ta bort kostnadsfria prenumerationer som användarna har registrerat sig för.</span><span class="sxs-lookup"><span data-stu-id="e7228-108">You can manage self-service sign-up subscriptions by blocking users from signing up, and by deleting free subscriptions that users have signed up for.</span></span> <span data-ttu-id="e7228-109">Mer information om självbetjäningsanmäla och tillgängliga prenumerationer finns [i Använda självbetjäningsanmäla i organisationen](../../admin/misc/self-service-sign-up.md).</span><span class="sxs-lookup"><span data-stu-id="e7228-109">For more information about self-service sign up and the available subscriptions, see [Using self-service sign up in your organization](../../admin/misc/self-service-sign-up.md).</span></span>

## <a name="how-are-these-subscriptions-different-from-self-service-purchase-subscriptions"></a><span data-ttu-id="e7228-110">Hur skiljer sig dessa prenumerationer från självbetjäningsköpsprenumerationer?</span><span class="sxs-lookup"><span data-stu-id="e7228-110">How are these subscriptions different from self-service purchase subscriptions?</span></span>

<span data-ttu-id="e7228-111">Självbetjäningsprenumerationer är kostnadsfria och är tillgängliga för en större lista över produkter än självbetjäningsköpsprenumerationer.</span><span class="sxs-lookup"><span data-stu-id="e7228-111">Self-service sign-up subscriptions are free, and are available for a larger list of products than self-service purchase subscriptions.</span></span> <span data-ttu-id="e7228-112">När en användare registrerar sig för en prenumeration på självbetjäningsköp ansvarar de för att betala för den.</span><span class="sxs-lookup"><span data-stu-id="e7228-112">When a user signs up for a self-service purchase subscription, they are responsible for paying for it.</span></span> <span data-ttu-id="e7228-113">Prenumerationer på självbetjäningsköp är också endast tillgängliga för Power Platform-produkter (Power BI, Power Apps och Power Automate).</span><span class="sxs-lookup"><span data-stu-id="e7228-113">Also, self-service purchase subscriptions are only available for Power Platform products (Power BI, Power Apps, and Power Automate).</span></span> <span data-ttu-id="e7228-114">Mer information finns i [Vanliga frågor och svar om självbetjäningsköp](self-service-purchase-faq.md).</span><span class="sxs-lookup"><span data-stu-id="e7228-114">For more information, see [Self-service purchase FAQ](self-service-purchase-faq.md).</span></span>

## <a name="block-users-from-signing-up"></a><span data-ttu-id="e7228-115">Blockera användare från att registrera sig</span><span class="sxs-lookup"><span data-stu-id="e7228-115">Block users from signing up</span></span>

<span data-ttu-id="e7228-116">Du använder cmdleten [**Set-MsolCompanySettings**](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0) med parametern **AllowAdHocSubscriptions** för att styra om användare kan registrera sig för självbetjäningsanteckningsprenumerationer.</span><span class="sxs-lookup"><span data-stu-id="e7228-116">You use the [**Set-MsolCompanySettings**](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0) cmdlet with the **AllowAdHocSubscriptions** parameter to control whether users can sign up for self-service sign-up subscriptions.</span></span> <span data-ttu-id="e7228-117">Mer information finns i [Hur kontrollerar jag självbetjäningsinställningarna?](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)</span><span class="sxs-lookup"><span data-stu-id="e7228-117">For more information, see [How do I control self-service settings?](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)</span></span>

## <a name="delete-a-self-service-sign-up-subscription"></a><span data-ttu-id="e7228-118">Ta bort en prenumeration på självbetjäningsanmälning</span><span class="sxs-lookup"><span data-stu-id="e7228-118">Delete a self-service sign-up subscription</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e7228-119">När du tar bort en prenumeration för självbetjäningsanmälning blockerar du alla användare från att komma åt deras data och e-post och ta bort alla data och e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="e7228-119">When you delete a self-service sign-up subscription, you block all users from accessing their data and email and delete all data and email.</span></span>

1. <span data-ttu-id="e7228-120">Gå till sidan **Billing**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Faktureringsprodukter</a> i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="e7228-120">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="e7228-121">Hitta den självbetjäningsprenumeration som du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="e7228-121">Find the self-service sign-up subscription that you want to delete.</span></span> <span data-ttu-id="e7228-122">Välj **Ta bort prenumeration**i avsnittet Inställningar & **Åtgärder** .</span><span class="sxs-lookup"><span data-stu-id="e7228-122">In the **Settings & Actions** section, select **Delete subscription**.</span></span>
3. <span data-ttu-id="e7228-123">Markera kryssrutan i fönstret **Ta bort prenumeration** och välj sedan Ta bort **prenumeration**.</span><span class="sxs-lookup"><span data-stu-id="e7228-123">In the **Delete subscription** pane, select the check box, then select **Delete subscription**.</span></span>

## <a name="i-have-a-self-service-sign-up-subscription-that-blocks-directory-deletion"></a><span data-ttu-id="e7228-124">Jag har en självbetjäningsprenumeration som blockerar borttagning av katalog</span><span class="sxs-lookup"><span data-stu-id="e7228-124">I have a self-service sign-up subscription that blocks directory deletion</span></span>

<span data-ttu-id="e7228-125">De självbetjäningsannonsprodukter som enskilda användare kan registrera sig för skapar också en gästanvändare för autentisering i din Azure AD-katalog.</span><span class="sxs-lookup"><span data-stu-id="e7228-125">The self-service sign-up products that individual users can sign up for also create a guest user for authentication in your Azure AD directory.</span></span> <span data-ttu-id="e7228-126">För att undvika dataförlust blockerar dessa självbetjäningsprodukter katalogborttagningar tills de tas bort helt från katalogen.</span><span class="sxs-lookup"><span data-stu-id="e7228-126">To avoid data loss, these self-service products block directory deletions until they're fully deleted from the directory.</span></span> <span data-ttu-id="e7228-127">De kan bara tas bort av Azure AD-administratören. Mer information finns [i Ta bort en katalog i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-delete-howto).</span><span class="sxs-lookup"><span data-stu-id="e7228-127">They can be deleted only by the Azure AD admin. For more information, see [Delete a directory in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-delete-howto).</span></span>