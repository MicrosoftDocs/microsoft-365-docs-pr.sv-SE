---
title: Redigera eller ange program skydds inställningar för Windows 10-enheter
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- Win10AppPolicy
- O365E_Win10AppPolicy
- BCS365_Win10AppPolicy
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 02e74022-44af-414b-9d74-0ebf5c2197f0
description: Lär dig hur du skapar eller redigerar program hanterings principer och skyddar arbetsfiler på användarnas privata Windows 10-enheter.
ms.openlocfilehash: f85a59649e43c141b62091337b842a490d411833
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289208"
---
# <a name="set-or-edit-application-protection-settings-for-windows-10-devices"></a><span data-ttu-id="80b95-103">Ange eller redigera inställningar för program skydd för Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="80b95-103">Set or edit application protection settings for Windows 10 devices</span></span>

<span data-ttu-id="80b95-104">Den här artikeln gäller Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="80b95-104">This article applies to Microsoft 365 Business Premium.</span></span>

## <a name="edit-an-app-management-policy-for-windows-10"></a><span data-ttu-id="80b95-105">Redigera en program hanterings princip för Windows 10</span><span class="sxs-lookup"><span data-stu-id="80b95-105">Edit an app management policy for Windows 10</span></span>

1. <span data-ttu-id="80b95-106">Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="80b95-106">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span>     
2. <span data-ttu-id="80b95-107">Välj principer för **enheter** i det vänstra navigerings fältet \> **Policies** .</span><span class="sxs-lookup"><span data-stu-id="80b95-107">On the left nav, choose **Devices** \> **Policies** .</span></span>
1. <span data-ttu-id="80b95-108">Välj en befintlig Windows-programprincip och sedan **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="80b95-108">Choose an existing Windows app policy and then **Edit**.</span></span>
1. <span data-ttu-id="80b95-109">Välj **Redigera** bredvid en inställning som du vill ändra och **Spara**sedan.</span><span class="sxs-lookup"><span data-stu-id="80b95-109">Choose **Edit** next to a setting you want to change and then **Save**.</span></span>

## <a name="create-an-app-management-policy-for-windows-10"></a><span data-ttu-id="80b95-110">Skapa en princip för programhantering för Windows 10</span><span class="sxs-lookup"><span data-stu-id="80b95-110">Create an app management policy for Windows 10</span></span>

<span data-ttu-id="80b95-111">Om dina användare har privata Windows 10-enheter som de utför arbetsuppgifter med kan du skydda data även på de enheterna.</span><span class="sxs-lookup"><span data-stu-id="80b95-111">If your users have personal Windows 10 devices on which they perform work tasks, you can protect your data on those devices as well.</span></span>
  
1. <span data-ttu-id="80b95-112">Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="80b95-112">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span> 
2. <span data-ttu-id="80b95-113">Välj principer för **enheter** i det vänstra navigerings fältet \> **Policies** \> **Add**.</span><span class="sxs-lookup"><span data-stu-id="80b95-113">On the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>
3. <span data-ttu-id="80b95-114">I fönstret **Lägg till princip** anger du ett unikt namn för principen.</span><span class="sxs-lookup"><span data-stu-id="80b95-114">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
4. <span data-ttu-id="80b95-115">Välj **Programhantering för Windows 10** under **Principtyp**.</span><span class="sxs-lookup"><span data-stu-id="80b95-115">Under **Policy type**, choose **Application Management for Windows 10**.</span></span>
5. <span data-ttu-id="80b95-116">Välj antingen **personligt** eller **företag som ägs**under **enhets typ**.</span><span class="sxs-lookup"><span data-stu-id="80b95-116">Under **Device type**, choose either **Personal** or **Company Owned**.</span></span>
6. <span data-ttu-id="80b95-117">**Kryptera arbetsfiler** aktiveras automatiskt.</span><span class="sxs-lookup"><span data-stu-id="80b95-117">The **Encrypt work files** is turned on automatically.</span></span> 
7. <span data-ttu-id="80b95-118">Ange **Hindra användare från att kopiera företagsdata till personliga filer och tvinga dem att spara arbetsfiler i OneDrive för företag** till **På** om du inte vill att användare ska kunna spara filer på sina datorer.</span><span class="sxs-lookup"><span data-stu-id="80b95-118">Set **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** to **On** if you don't want the users to save work files on their PC.</span></span> 
9. <span data-ttu-id="80b95-119">Expandera **Recover data på Windows-enheter**.</span><span class="sxs-lookup"><span data-stu-id="80b95-119">Expand **Recover data on Windows devices**.</span></span> <span data-ttu-id="80b95-120">Vi rekommenderar att du **aktiverar det.**</span><span class="sxs-lookup"><span data-stu-id="80b95-120">We recommend that you turn it **On**.</span></span>
    <span data-ttu-id="80b95-121">Innan du kan bläddra till certifikatet för dataåterställningsagenten måste du skapa ett.</span><span class="sxs-lookup"><span data-stu-id="80b95-121">Before you can browse to the location of the Data Recovery Agent certificate, you have to first create one.</span></span> <span data-ttu-id="80b95-122">Instruktioner finns i [skapa och bekräfta ett dra-certifikat](https://go.microsoft.com/fwlink/p/?linkid=853700)(Encrypting File System).</span><span class="sxs-lookup"><span data-stu-id="80b95-122">For instructions, see [Create and verify an Encrypting File System (EFS) Data Recovery Agent (DRA) certificate](https://go.microsoft.com/fwlink/p/?linkid=853700).</span></span>
    
    <span data-ttu-id="80b95-123">Som standard krypteras arbetsfiler med en hemlig nyckel som lagras på enheten och som är kopplad till användarens profil.</span><span class="sxs-lookup"><span data-stu-id="80b95-123">By default, work files are encrypted using a secret key that is stored on the device and associated with the user's profile.</span></span> <span data-ttu-id="80b95-124">Endast användaren kan öppna och dekryptera filen.</span><span class="sxs-lookup"><span data-stu-id="80b95-124">Only the user can open and decrypt the file.</span></span> <span data-ttu-id="80b95-125">Men om en enhet försvinner eller en användare tas bort kan en fil fastna i ett krypterat tillstånd.</span><span class="sxs-lookup"><span data-stu-id="80b95-125">However, if a device is lost or a user is removed, a file can be stuck in an encrypted state.</span></span> <span data-ttu-id="80b95-126">En administratör kan använda certifikatet för att dekryptera filen.</span><span class="sxs-lookup"><span data-stu-id="80b95-126">An admin can use the Data Recovery Agent (DRA) certificate to decrypt the file.</span></span>
    
    ![Browse to Data Recovery Agent certificate.](../media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. <span data-ttu-id="80b95-128">Expandera **skydda ytterligare nätverks-och moln platser** om du vill lägga till fler domäner eller platser i SharePoint Online för att se till att filer i alla program i listan är skyddade.</span><span class="sxs-lookup"><span data-stu-id="80b95-128">Expand **Protect additional network and cloud locations** if you want to add additional domains or SharePoint Online locations to make sure that files in all the listed apps are protected.</span></span> <span data-ttu-id="80b95-129">Om du behöver ange mer än ett objekt i ett fält anger du ett semikolon (;) mellan objekten.</span><span class="sxs-lookup"><span data-stu-id="80b95-129">If you need to enter more than one item for either field, use a semicolon (;) between the items.</span></span>
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](../media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. <span data-ttu-id="80b95-p104">Bestäm sedan **vem som ska få de här inställningarna** Om du inte vill använda standardsäkerhetsgruppen **Alla användare** väljer du **Ändra** och anger de säkerhetsgrupper som ska få dessa inställningar \> **Välj**.</span><span class="sxs-lookup"><span data-stu-id="80b95-p104">Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span></span>
12. <span data-ttu-id="80b95-133">Välj **Lägg till** för att spara principen och tilldela den till enheter.</span><span class="sxs-lookup"><span data-stu-id="80b95-133">Finally, choose **Add** to save the policy, and assign it to devices.</span></span> 
