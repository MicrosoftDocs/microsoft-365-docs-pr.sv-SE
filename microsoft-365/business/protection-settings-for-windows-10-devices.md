---
title: Ange programskyddsinställningar för Windows 10-enheter
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 02e74022-44af-414b-9d74-0ebf5c2197f0
description: Lär dig hur du skapar en apphanteringsprincip och skyddar arbetsfiler på Windows 10-enheter.
ms.openlocfilehash: ca6d789e0242975a0395e6cf5653d3f43f819801
ms.sourcegitcommit: 5d11f516e78ea4a74145e19ba2300f0792c8bac1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/19/2019
ms.locfileid: "38715261"
---
# <a name="set-application-protection-settings-for-windows-10-devices"></a><span data-ttu-id="0acc3-103">Ange programskyddsinställningar för Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="0acc3-103">Set application protection settings for Windows 10 devices</span></span>

## <a name="create-an-app-management-policy-for-windows-10"></a><span data-ttu-id="0acc3-104">Skapa en princip för programhantering för Windows 10</span><span class="sxs-lookup"><span data-stu-id="0acc3-104">Create an app management policy for Windows 10</span></span>

<span data-ttu-id="0acc3-105">Om dina användare har privata Windows 10-enheter som de utför arbetsuppgifter med kan du skydda data även på de enheterna.</span><span class="sxs-lookup"><span data-stu-id="0acc3-105">If your users have personal Windows 10 devices on which they perform work tasks, you can protect your data on those devices as well.</span></span>
  
1. <span data-ttu-id="0acc3-106">Gå till administratörscenter på <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="0acc3-106">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span> 
    
2. <span data-ttu-id="0acc3-107">I det vänstra navigeringsfältet väljer **du Lägg till** **enhets** \> **principer** \> .</span><span class="sxs-lookup"><span data-stu-id="0acc3-107">On the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>

3. <span data-ttu-id="0acc3-108">I fönstret **Lägg till princip** anger du ett unikt namn för principen.</span><span class="sxs-lookup"><span data-stu-id="0acc3-108">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="0acc3-109">Välj **Programhantering för Windows 10** under **Principtyp**.</span><span class="sxs-lookup"><span data-stu-id="0acc3-109">Under **Policy type**, choose **Application Management for Windows 10**.</span></span>
    
5. <span data-ttu-id="0acc3-110">Välj antingen **personligt** eller **företagsägda**under **enhetstyp**.</span><span class="sxs-lookup"><span data-stu-id="0acc3-110">Under **Device type**, choose either **Personal** or **Company Owned**.</span></span>
    
6. <span data-ttu-id="0acc3-111">**Kryptera arbetsfiler** aktiveras automatiskt.</span><span class="sxs-lookup"><span data-stu-id="0acc3-111">The **Encrypt work files** is turned on automatically.</span></span> 
    
7. <span data-ttu-id="0acc3-112">Ange **Hindra användare från att kopiera företagsdata till personliga filer och tvinga dem att spara arbetsfiler i OneDrive för företag** till **På** om du inte vill att användare ska kunna spara filer på sina datorer.</span><span class="sxs-lookup"><span data-stu-id="0acc3-112">Set **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** to **On** if you don't want the users to save work files on their PC.</span></span> 
    
9. <span data-ttu-id="0acc3-113">Expandera **återskapa data på Windows-enheter**.</span><span class="sxs-lookup"><span data-stu-id="0acc3-113">Expand **Recover data on Windows devices**.</span></span> <span data-ttu-id="0acc3-114">Vi rekommenderar att du aktiverar den **.**</span><span class="sxs-lookup"><span data-stu-id="0acc3-114">We recommend that you turn it **On**.</span></span>
    
    <span data-ttu-id="0acc3-115">Innan du kan bläddra till certifikatet för dataåterställningsagenten måste du skapa ett.</span><span class="sxs-lookup"><span data-stu-id="0acc3-115">Before you can browse to the location of the Data Recovery Agent certificate, you have to first create one.</span></span> <span data-ttu-id="0acc3-116">Instruktioner finns i [skapa och verifiera ett dra-certifikat (Encrypting File System) för Data Recovery agent (EFS)](https://go.microsoft.com/fwlink/p/?linkid=853700).</span><span class="sxs-lookup"><span data-stu-id="0acc3-116">For instructions, see [Create and verify an Encrypting File System (EFS) Data Recovery Agent (DRA) certificate](https://go.microsoft.com/fwlink/p/?linkid=853700).</span></span>
    
    <span data-ttu-id="0acc3-117">Som standard krypteras arbetsfiler med en hemlig nyckel som lagras på enheten och som är kopplad till användarens profil.</span><span class="sxs-lookup"><span data-stu-id="0acc3-117">By default, work files are encrypted using a secret key that is stored on the device and associated with the user's profile.</span></span> <span data-ttu-id="0acc3-118">Endast användaren kan öppna och dekryptera filen.</span><span class="sxs-lookup"><span data-stu-id="0acc3-118">Only the user can open and decrypt the file.</span></span> <span data-ttu-id="0acc3-119">Men om en enhet försvinner eller en användare tas bort kan en fil fastna i ett krypterat tillstånd.</span><span class="sxs-lookup"><span data-stu-id="0acc3-119">However, if a device is lost or a user is removed, a file can be stuck in an encrypted state.</span></span> <span data-ttu-id="0acc3-120">En administratör kan använda DRA-certifikatet (Data Recovery agent) för att dekryptera filen.</span><span class="sxs-lookup"><span data-stu-id="0acc3-120">An admin can use the Data Recovery Agent (DRA) certificate to decrypt the file.</span></span>
    
    ![Browse to Data Recovery Agent certificate.](media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. <span data-ttu-id="0acc3-122">Expandera **skydda ytterligare nätverk och moln platser** om du vill lägga till ytterligare domäner eller SharePoint Online-platser för att se till att filer i alla listade appar är skyddade.</span><span class="sxs-lookup"><span data-stu-id="0acc3-122">Expand **Protect additional network and cloud locations** if you want to add additional domains or SharePoint Online locations to make sure that files in all the listed apps are protected.</span></span> <span data-ttu-id="0acc3-123">Om du behöver ange mer än ett objekt i ett fält anger du ett semikolon (;) mellan objekten.</span><span class="sxs-lookup"><span data-stu-id="0acc3-123">If you need to enter more than one item for either field, use a semicolon (;) between the items.</span></span>
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. <span data-ttu-id="0acc3-p105">Bestäm sedan **vem som ska få de här inställningarna** Om du inte vill använda standardsäkerhetsgruppen **Alla användare** väljer du **Ändra** och anger de säkerhetsgrupper som ska få dessa inställningar \> **Välj**.</span><span class="sxs-lookup"><span data-stu-id="0acc3-p105">Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span></span>
    
12. <span data-ttu-id="0acc3-127">Välj **Lägg till** för att spara principen och tilldela den till enheter.</span><span class="sxs-lookup"><span data-stu-id="0acc3-127">Finally, choose **Add** to save the policy, and assign it to devices.</span></span> 