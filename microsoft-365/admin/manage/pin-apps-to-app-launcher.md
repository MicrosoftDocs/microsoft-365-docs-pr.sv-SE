---
title: Fästa appar i användarnas startprogram
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
description: Som global administratör kan du fästa upp till tre program i användarnas startprogram.
ms.openlocfilehash: 965fcbbb3f0e22074e3f6c5476d65ade98fea94c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915224"
---
# <a name="pin-apps-to-your-users-app-launcher"></a><span data-ttu-id="d4fd8-103">Fästa appar i användarnas startprogram</span><span class="sxs-lookup"><span data-stu-id="d4fd8-103">Pin apps to your users' app launcher</span></span>

<span data-ttu-id="d4fd8-104">Du kan använda kontroller i Azure Active Directory-portalen för att fästa upp till tre program i Office.com och startprogrammet för alla användare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="d4fd8-104">You can use controls in the Azure Active Directory portal to pin up to three apps to Office.com and the app launcher for all the users in your organization.</span></span> <span data-ttu-id="d4fd8-105">Du kan också ordna grupper med program.</span><span class="sxs-lookup"><span data-stu-id="d4fd8-105">You can also organize groups of applications.</span></span> <span data-ttu-id="d4fd8-106">Alla appar som du lägger till kan när som helst tas bort av användaren.</span><span class="sxs-lookup"><span data-stu-id="d4fd8-106">Any app you add can later be unpinned by the user at any time.</span></span> <span data-ttu-id="d4fd8-107">Om du vill fästa ett program för användarna måste du vara molnprogramsadministratör eller programadministratör i Azure Active Directory eller global administratör i Office 365.</span><span class="sxs-lookup"><span data-stu-id="d4fd8-107">To pin an app for your users, you must be a Cloud application administrator, or Application administrator in Azure Active Directory, or a Global administrator in Office 365.</span></span> <span data-ttu-id="d4fd8-108">Mer information om administratörsroller finns i [administratörsroller i Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) och [administratörsroller i Microsoft 365.](../add-users/about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="d4fd8-108">For more information about admin roles, see [admin roles in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) and [admin roles in Microsoft 365](../add-users/about-admin-roles.md).</span></span> 

<span data-ttu-id="d4fd8-109">Mer information om startprogrammet och Office.com finns [](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a) i möt startprogrammet och uppdateringar av office.com och bloggartikeln [om Office 365-startprogrammet.](https://techcommunity.microsoft.com/t5/office-365-blog/updates-to-office-com-and-the-office-365-app-launcher/ba-p/1150503)</span><span class="sxs-lookup"><span data-stu-id="d4fd8-109">For more information about the app launcher and Office.com, see [meet the app launcher](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a) and [updates to office.com and the-Office 365 app launcher](https://techcommunity.microsoft.com/t5/office-365-blog/updates-to-office-com-and-the-office-365-app-launcher/ba-p/1150503) blog article.</span></span>

## <a name="use-the-azure-active-directory-portal-to-pin-apps"></a><span data-ttu-id="d4fd8-110">Fästa appar med Azure Active Directory-portalen</span><span class="sxs-lookup"><span data-stu-id="d4fd8-110">Use the Azure Active Directory portal to pin apps</span></span>

1. <span data-ttu-id="d4fd8-111">Gå till administrationscentret för Microsoft 365 på <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="d4fd8-111">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>
2. <span data-ttu-id="d4fd8-112">I det vänstra navigeringsfältet **väljer du Visa alla** och under **Administratörscentra** väljer du **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="d4fd8-112">In the left nav, choose **Show all**, and under **Admin centers**, choose **Azure Active Directory**.</span></span>
3. <span data-ttu-id="d4fd8-113">Välj **Användarinställningar för** företagsprogram **i** Azure Active  >  **Directory**.</span><span class="sxs-lookup"><span data-stu-id="d4fd8-113">In **Azure Active Directory**, choose **Enterprise applications** > **User settings**.</span></span>
4. <span data-ttu-id="d4fd8-114">I avsnittet **Office 365-inställningar** väljer du Lägg **till program.**</span><span class="sxs-lookup"><span data-stu-id="d4fd8-114">In the **Office 365 Settings** section, choose **Add application**.</span></span>
5. <span data-ttu-id="d4fd8-115">Välj de program som du vill fästa i användarnas startprogram och välj sedan Lägg **till.**</span><span class="sxs-lookup"><span data-stu-id="d4fd8-115">Choose the applications you want to pin to the users' app launcher, and then choose **Add**.</span></span>

:::image type="content" source="../../media/add-apps.png" alt-text="Microsoft 365-inställningar för att fästa appar.":::

### <a name="pin-a-custom-app"></a><span data-ttu-id="d4fd8-117">Fästa ett anpassat program</span><span class="sxs-lookup"><span data-stu-id="d4fd8-117">Pin a custom app</span></span>

> [!NOTE]
> <span data-ttu-id="d4fd8-118">Användargränssnittet anger om du behöver köpa ytterligare Azure AD-licenser för att använda den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="d4fd8-118">The user interface will indicate if you need need to purchase additional Azure AD licenses to use this feature.</span></span> <span data-ttu-id="d4fd8-119">Mer information finns i [Azure Active Directory-priser.](https://azure.microsoft.com/pricing/details/active-directory/)</span><span class="sxs-lookup"><span data-stu-id="d4fd8-119">For more information see [Azure Active Directory pricing](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>

1. <span data-ttu-id="d4fd8-120">I **Azure Active Directory** väljer du   >  **Företagsprogram Nytt** program högst upp på **sidan Alla** program.</span><span class="sxs-lookup"><span data-stu-id="d4fd8-120">In **Azure Active Directory**, choose **Enterprise applications** > **New application** on the top of the **All applications** page.</span></span>
2. <span data-ttu-id="d4fd8-121">På sidan **Lägg till ett** program väljer  du Program som inte **finns** i galleriet eller Skapa ett eget program om du använder förhandsversionen av Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d4fd8-121">On the **Add an application** page, choose **Non-gallery application** or **Create your own application** if you are in the preview version of Azure Active Directory.</span></span> 
3. <span data-ttu-id="d4fd8-122">Skriv ett namn för programmet och tilldela sedan användare på **fliken Användare och** grupper.</span><span class="sxs-lookup"><span data-stu-id="d4fd8-122">Type a name for the application and then assign user in the **Users and groups** tab.</span></span>
4. <span data-ttu-id="d4fd8-123">Använd fliken **Egenskaper** för att ladda upp en ikon för programmet.</span><span class="sxs-lookup"><span data-stu-id="d4fd8-123">Use the **Properties** tab to upload an icon for the app.</span></span>
5. <span data-ttu-id="d4fd8-124">Om du vill tilldela en URL till appen väljer **du Linked på** fliken Enkel inloggning och anger sedan en URL-adress. </span><span class="sxs-lookup"><span data-stu-id="d4fd8-124">To assign a URL to the app, in the **Single sign-on** tab, choose **Linked** and then enter a URL.</span></span>
6. <span data-ttu-id="d4fd8-125">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="d4fd8-125">Choose **Save**.</span></span>

## <a name="create-application-collections"></a><span data-ttu-id="d4fd8-126">Skapa programsamlingar</span><span class="sxs-lookup"><span data-stu-id="d4fd8-126">Create application collections</span></span>

<span data-ttu-id="d4fd8-127">Du kan också skapa programsamlingar för användarna i organisationen.</span><span class="sxs-lookup"><span data-stu-id="d4fd8-127">You can also create application collections for the users in your organization.</span></span> <span data-ttu-id="d4fd8-128">Instruktioner finns i [Skapa samlingar på portalen Mina appar i Azure Portal.](/azure/active-directory/manage-apps/access-panel-collections)</span><span class="sxs-lookup"><span data-stu-id="d4fd8-128">For instructions, see [create collections on the My Apps portal in the Azure portal](/azure/active-directory/manage-apps/access-panel-collections).</span></span>