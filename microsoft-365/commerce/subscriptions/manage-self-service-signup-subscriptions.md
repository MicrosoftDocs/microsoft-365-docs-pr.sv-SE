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
ms.openlocfilehash: fb70d0c40d4358abc227c8f6ff4a0e0dce1a7265
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48647837"
---
# <a name="manage-self-service-sign-up-subscriptions"></a><span data-ttu-id="953d4-103">Hantera abonnemang för självbetjäning</span><span class="sxs-lookup"><span data-stu-id="953d4-103">Manage self-service sign-up subscriptions</span></span>

## <a name="what-are-self-service-sign-up-subscriptions"></a><span data-ttu-id="953d4-104">Vad är självbetjänings abonnemang?</span><span class="sxs-lookup"><span data-stu-id="953d4-104">What are self-service sign-up subscriptions?</span></span>

<span data-ttu-id="953d4-105">Det finns ett begränsat antal kostnads fria registrerings abonnemang för självbetjäning som användare i organisationen kan registrera sig för.</span><span class="sxs-lookup"><span data-stu-id="953d4-105">There are a limited number of free self-service sign-up subscriptions that users in your organization can sign up for.</span></span> <span data-ttu-id="953d4-106">En användare kan bara registrera sig för och använda ett själv registrerings abonnemang för sig själva.</span><span class="sxs-lookup"><span data-stu-id="953d4-106">A user can only sign up for and use a self-service sign-up subscription for themselves.</span></span> <span data-ttu-id="953d4-107">Dessa abonnemang visas på sidan **produkter** , markeras som **ledigt**och har en kommentar om att "det här är ett kostnads fritt abonnemang som har Aktiver ATS av användare i företaget."</span><span class="sxs-lookup"><span data-stu-id="953d4-107">These subscriptions appear on the **Your products** page, are marked as **Free**, and have a note that says, "This is a free subscription activated by users in your company."</span></span> <span data-ttu-id="953d4-108">Du kan hantera självbetjänings abonnemang genom att hindra användare från att registrera sig och genom att ta bort kostnads fria abonnemang som användare har registrerat sig för.</span><span class="sxs-lookup"><span data-stu-id="953d4-108">You can manage self-service sign-up subscriptions by blocking users from signing up, and by deleting free subscriptions that users have signed up for.</span></span> <span data-ttu-id="953d4-109">Mer information om själv registrering och tillgängliga prenumerationer finns i [använda självbetjänings registrering i din organisation](../../admin/misc/self-service-sign-up.md).</span><span class="sxs-lookup"><span data-stu-id="953d4-109">For more information about self-service sign up and the available subscriptions, see [Using self-service sign up in your organization](../../admin/misc/self-service-sign-up.md).</span></span>

## <a name="how-are-these-subscriptions-different-from-self-service-purchase-subscriptions"></a><span data-ttu-id="953d4-110">Hur skiljer sig abonnemangen från självbetjänings abonnemanget?</span><span class="sxs-lookup"><span data-stu-id="953d4-110">How are these subscriptions different from self-service purchase subscriptions?</span></span>

<span data-ttu-id="953d4-111">Självbetjänings prenumerationer är gratis och finns tillgängliga i en större lista över produkter än abonnemang för egen service.</span><span class="sxs-lookup"><span data-stu-id="953d4-111">Self-service sign-up subscriptions are free, and are available for a larger list of products than self-service purchase subscriptions.</span></span> <span data-ttu-id="953d4-112">När en användare registrerar sig för ett abonnemang för självbetjänings köp är de ansvarig för att betala för det.</span><span class="sxs-lookup"><span data-stu-id="953d4-112">When a user signs up for a self-service purchase subscription, they are responsible for paying for it.</span></span> <span data-ttu-id="953d4-113">Dessutom är självbetjänings-och inköps abonnemang endast tillgängliga för Power Platform-produkter (Power BI, Power app och Power automatiserat).</span><span class="sxs-lookup"><span data-stu-id="953d4-113">Also, self-service purchase subscriptions are only available for Power Platform products (Power BI, Power Apps, and Power Automate).</span></span> <span data-ttu-id="953d4-114">Mer information finns i [vanliga frågor och svar om inköp](self-service-purchase-faq.md).</span><span class="sxs-lookup"><span data-stu-id="953d4-114">For more information, see [Self-service purchase FAQ](self-service-purchase-faq.md).</span></span>

## <a name="block-users-from-signing-up"></a><span data-ttu-id="953d4-115">Blockera användare från att registrera sig</span><span class="sxs-lookup"><span data-stu-id="953d4-115">Block users from signing up</span></span>

<span data-ttu-id="953d4-116">Du använder cmdleten [**set-MsolCompanySettings**](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0) med parametern **AllowAdHocSubscriptions** för att kontrol lera om användare ska kunna registrera sig för självbetjänings inloggnings prenumerationer.</span><span class="sxs-lookup"><span data-stu-id="953d4-116">You use the [**Set-MsolCompanySettings**](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0) cmdlet with the **AllowAdHocSubscriptions** parameter to control whether users can sign up for self-service sign-up subscriptions.</span></span> <span data-ttu-id="953d4-117">Mer information finns i [Hur styr jag självbetjänings inställningar?](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)</span><span class="sxs-lookup"><span data-stu-id="953d4-117">For more information, see [How do I control self-service settings?](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)</span></span>

## <a name="delete-a-self-service-sign-up-subscription"></a><span data-ttu-id="953d4-118">Ta bort ett själv registrerings abonnemang</span><span class="sxs-lookup"><span data-stu-id="953d4-118">Delete a self-service sign-up subscription</span></span>

> [!IMPORTANT]
> <span data-ttu-id="953d4-119">När du tar bort ett själv registrerings abonnemang hindrar du alla användare från att komma åt sina data och e-postmeddelanden och ta bort alla data och e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="953d4-119">When you delete a self-service sign-up subscription, you block all users from accessing their data and email and delete all data and email.</span></span>

1. <span data-ttu-id="953d4-120">Gå till sidan fakturering i administrations centret **Billing**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> .</span><span class="sxs-lookup"><span data-stu-id="953d4-120">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="953d4-121">Hitta själv registrerings prenumerationen som du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="953d4-121">Find the self-service sign-up subscription that you want to delete.</span></span> <span data-ttu-id="953d4-122">Välj **ta bort prenumeration**i avsnittet **Settings & Actions** .</span><span class="sxs-lookup"><span data-stu-id="953d4-122">In the **Settings & Actions** section, select **Delete subscription**.</span></span>
3. <span data-ttu-id="953d4-123">Markera kryss rutan i fönstret **ta bort prenumeration** och välj sedan **ta bort abonnemang**.</span><span class="sxs-lookup"><span data-stu-id="953d4-123">In the **Delete subscription** pane, select the check box, then select **Delete subscription**.</span></span>

## <a name="i-have-a-self-service-sign-up-subscription-that-blocks-directory-deletion"></a><span data-ttu-id="953d4-124">Jag har ett självbetjänings abonnemang som hindrar borttagning av kataloger</span><span class="sxs-lookup"><span data-stu-id="953d4-124">I have a self-service sign-up subscription that blocks directory deletion</span></span>

<span data-ttu-id="953d4-125">Självbetjänings-och registrerings produkter som enskilda användare kan registrera sig för och skapa en gäst användare för att verifiera i din Azure AD-katalog.</span><span class="sxs-lookup"><span data-stu-id="953d4-125">The self-service sign-up products that individual users can sign up for also create a guest user for authentication in your Azure AD directory.</span></span> <span data-ttu-id="953d4-126">För att undvika data förlust tar du bort de här själv tjänst produkterna tills de tas bort helt från katalogen.</span><span class="sxs-lookup"><span data-stu-id="953d4-126">To avoid data loss, these self-service products block directory deletions until they're fully deleted from the directory.</span></span> <span data-ttu-id="953d4-127">De kan bara tas bort av Azure AD-administratören. Mer information finns i [ta bort en katalog i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-delete-howto).</span><span class="sxs-lookup"><span data-stu-id="953d4-127">They can be deleted only by the Azure AD admin. For more information, see [Delete a directory in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-delete-howto).</span></span>