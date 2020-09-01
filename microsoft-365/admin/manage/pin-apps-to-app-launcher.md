---
title: Fästa appar i användarnas start program
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.collection:
- Adm_O365
- M365-subscription-management
ms.service: o365-administration
localization_priority: Normal
description: Som global administratör kan du fästa upp till tre program i användarnas start program.
ms.openlocfilehash: d9b95a20f332a9b1f2f6b0ebba28a70c58677b58
ms.sourcegitcommit: 87449335d9a1124ee82fa2e95e4745155a95a62f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/29/2020
ms.locfileid: "47310881"
---
# <a name="pin-apps-to-your-users-app-launcher"></a><span data-ttu-id="18da7-103">Fästa appar i användarnas start program</span><span class="sxs-lookup"><span data-stu-id="18da7-103">Pin apps to your users' app launcher</span></span>

<span data-ttu-id="18da7-104">Du kan använda kontroller i Azure Active Directory-portalen för att fästa upp till tre appar till Office.com och Start programmet för alla användare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="18da7-104">You can use controls in the Azure Active Directory portal to pin up to three apps to Office.com and the app launcher for all the users in your organization.</span></span> <span data-ttu-id="18da7-105">Du kan också ordna program grupper.</span><span class="sxs-lookup"><span data-stu-id="18da7-105">You can also organize groups of applications.</span></span> <span data-ttu-id="18da7-106">Alla appar du lägger till kan senare avgränsas av användaren när som helst.</span><span class="sxs-lookup"><span data-stu-id="18da7-106">Any app you add can later be unpinned by the user at any time.</span></span> <span data-ttu-id="18da7-107">För att fästa en app för användarna måste du vara ett moln programs administratör eller program administratör i Azure Active Directory eller en global administratör i Office 365.</span><span class="sxs-lookup"><span data-stu-id="18da7-107">To pin an app for your users, you must be a Cloud application administrator, or Application administrator in Azure Active Directory, or a Global administrator in Office 365.</span></span> <span data-ttu-id="18da7-108">Mer information om administratörs roller finns i [Administratörs roller i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) -och [Administratörs roller i Microsoft 365](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="18da7-108">For more information about admin roles, see [admin roles in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) and [admin roles in Microsoft 365](../add-users/about-admin-roles.md).</span></span> 

<span data-ttu-id="18da7-109">Mer information om start ikonen och Office.com finns i [uppfylla start-startprogrammet](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a) och [uppdateringar till office.com och Office 365-programmet starta](https://techcommunity.microsoft.com/t5/office-365-blog/updates-to-office-com-and-the-office-365-app-launcher/ba-p/1150503) blogg inlägg.</span><span class="sxs-lookup"><span data-stu-id="18da7-109">For more information about the app launcher and Office.com, see [meet the app launcher](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a) and [updates to office.com and the-Office 365 app launcher](https://techcommunity.microsoft.com/t5/office-365-blog/updates-to-office-com-and-the-office-365-app-launcher/ba-p/1150503) blog article.</span></span>

## <a name="use-the-azure-active-directory-portal-to-pin-apps"></a><span data-ttu-id="18da7-110">Använda Azure Active Directory-portalen för att fästa appar</span><span class="sxs-lookup"><span data-stu-id="18da7-110">Use the Azure Active Directory portal to pin apps</span></span>

1. <span data-ttu-id="18da7-111">Gå till administrations centret för Microsoft 365 på <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="18da7-111">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>
2. <span data-ttu-id="18da7-112">I det vänstra navigerings fältet väljer du **Visa alla**och under **administrations Center**väljer du **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="18da7-112">In the left nav, choose **Show all**, and under **Admin centers**, choose **Azure Active Directory**.</span></span>
3. <span data-ttu-id="18da7-113">I **Azure Active Directory**väljer du inställningar för **företags program**  >  **User settings**.</span><span class="sxs-lookup"><span data-stu-id="18da7-113">In **Azure Active Directory**, choose **Enterprise applications** > **User settings**.</span></span>
4. <span data-ttu-id="18da7-114">I avsnittet **Inställningar för Office 365** väljer du **Lägg till program**.</span><span class="sxs-lookup"><span data-stu-id="18da7-114">In the **Office 365 Settings** section, choose **Add application**.</span></span>
5. <span data-ttu-id="18da7-115">Välj de program som du vill fästa i användarnas start program och välj sedan **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="18da7-115">Choose the applications you want to pin to the users' app launcher, and then choose **Add**.</span></span>

:::image type="content" source="../../media/add-apps.png" alt-text="Microsoft 365-inställningar för att fästa appar.":::

### <a name="pin-a-custom-app"></a><span data-ttu-id="18da7-117">Fäst en egen app</span><span class="sxs-lookup"><span data-stu-id="18da7-117">Pin a custom app</span></span>

> [!NOTE]
> <span data-ttu-id="18da7-118">Användar gränssnittet anger om du behöver köpa fler Azure AD-licenser för att använda den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="18da7-118">The user interface will indicate if you need need to purchase additional Azure AD licenses to use this feature.</span></span> <span data-ttu-id="18da7-119">Mer information finns i [Azure Active Directory-priser](https://azure.microsoft.com/pricing/details/active-directory/).</span><span class="sxs-lookup"><span data-stu-id="18da7-119">For more information see [Azure Active Directory pricing](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>

1. <span data-ttu-id="18da7-120">I **Azure Active Directory**väljer du **företags program**  >  **nytt program** högst upp på sidan **alla program** .</span><span class="sxs-lookup"><span data-stu-id="18da7-120">In **Azure Active Directory**, choose **Enterprise applications** > **New application** on the top of the **All applications** page.</span></span>
2. <span data-ttu-id="18da7-121">På sidan **Lägg till ett program** väljer du **icke-galleriprogram** eller **skapar ett eget program** om du befinner dig i för hands versionen av Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="18da7-121">On the **Add an application** page, choose **Non-gallery application** or **Create your own application** if you are in the preview version of Azure Active Directory.</span></span> 
3. <span data-ttu-id="18da7-122">Ange ett namn för programmet och sedan tilldela användare på fliken **användare och grupper** .</span><span class="sxs-lookup"><span data-stu-id="18da7-122">Type a name for the application and then assign user in the **Users and groups** tab.</span></span>
4. <span data-ttu-id="18da7-123">Använd fliken **Egenskaper** för att ladda upp en ikon för appen.</span><span class="sxs-lookup"><span data-stu-id="18da7-123">Use the **Properties** tab to upload an icon for the app.</span></span>
5. <span data-ttu-id="18da7-124">Om du vill tilldela en URL till programmet går du till fliken **enkel inloggning** och väljer **länkat** och anger sedan en URL.</span><span class="sxs-lookup"><span data-stu-id="18da7-124">To assign a URL to the app, in the **Single sign-on** tab, choose **Linked** and then enter a URL.</span></span>
6. <span data-ttu-id="18da7-125">Välj **Save**.</span><span class="sxs-lookup"><span data-stu-id="18da7-125">Choose **Save**.</span></span>

## <a name="create-application-collections"></a><span data-ttu-id="18da7-126">Skapa program samlingar</span><span class="sxs-lookup"><span data-stu-id="18da7-126">Create application collections</span></span>

<span data-ttu-id="18da7-127">Du kan också skapa program samlingar för användarna i organisationen.</span><span class="sxs-lookup"><span data-stu-id="18da7-127">You can also create application collections for the users in your organization.</span></span> <span data-ttu-id="18da7-128">Instruktioner finns i [skapa samlingar på portalen mina program i Azure-portalen](https://docs.microsoft.com/azure/active-directory/manage-apps/access-panel-collections).</span><span class="sxs-lookup"><span data-stu-id="18da7-128">For instructions, see [create collections on the My Apps portal in the Azure portal](https://docs.microsoft.com/azure/active-directory/manage-apps/access-panel-collections).</span></span>