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
ms.openlocfilehash: 0e1221e533418166b80afd94431414016774f247
ms.sourcegitcommit: bd52f7b662887f552f90c46f69d6a2a42fb66914
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/17/2019
ms.locfileid: "37575787"
---
# <a name="set-application-protection-settings-for-windows-10-devices"></a><span data-ttu-id="e8d29-103">Ange programskyddsinställningar för Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="e8d29-103">Set application protection settings for Windows 10 devices</span></span>

## <a name="create-an-app-management-policy-for-windows-10"></a><span data-ttu-id="e8d29-104">Skapa en princip för programhantering för Windows 10</span><span class="sxs-lookup"><span data-stu-id="e8d29-104">Create an app management policy for Windows 10</span></span>

<span data-ttu-id="e8d29-105">Om dina användare har privata Windows 10-enheter som de utför arbetsuppgifter med kan du skydda data även på de enheterna.</span><span class="sxs-lookup"><span data-stu-id="e8d29-105">If your users have personal Windows 10 devices on which they perform work tasks, you can protect your data on those devices as well.</span></span>
  
1. <span data-ttu-id="e8d29-106">Gå till administratörscenter på <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="e8d29-106">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span> 
    
2. <span data-ttu-id="e8d29-107">I det vänstra navigeringsfältet väljer **du Lägg till** **enhets** \> **principer** \> .</span><span class="sxs-lookup"><span data-stu-id="e8d29-107">On the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>

3. <span data-ttu-id="e8d29-108">I fönstret **Lägg till princip** anger du ett unikt namn för principen.</span><span class="sxs-lookup"><span data-stu-id="e8d29-108">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="e8d29-109">Välj **Programhantering för Windows 10** under **Principtyp**.</span><span class="sxs-lookup"><span data-stu-id="e8d29-109">Under **Policy type**, choose **Application Management for Windows 10**.</span></span>
    
5. <span data-ttu-id="e8d29-110">Välj antingen **personligt** eller **företagsägda**under **enhetstyp**.</span><span class="sxs-lookup"><span data-stu-id="e8d29-110">Under **Device type**, choose either **Personal** or **Company Owned**.</span></span>
    
6. <span data-ttu-id="e8d29-111">**Kryptera arbetsfiler** aktiveras automatiskt.</span><span class="sxs-lookup"><span data-stu-id="e8d29-111">The **Encrypt work files** is turned on automatically.</span></span> 
    
7. <span data-ttu-id="e8d29-112">Ange **Hindra användare från att kopiera företagsdata till personliga filer och tvinga dem att spara arbetsfiler i OneDrive för företag** till **På** om du inte vill att användare ska kunna spara filer på sina datorer.</span><span class="sxs-lookup"><span data-stu-id="e8d29-112">Set **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** to **On** if you don't want the users to save work files on their PC.</span></span> 
    
9. <span data-ttu-id="e8d29-113">Expandera **Återställ data på Windows-enheter**. Vi rekommenderar att du anger den till **På**.</span><span class="sxs-lookup"><span data-stu-id="e8d29-113">Expand **Recover data on Windows devices** and it is recommended that you turn it **On**.</span></span>
    
    <span data-ttu-id="e8d29-p101">Innan du kan bläddra till certifikatet för dataåterställningsagenten måste du skapa ett. Anvisningar finns i [Create and verify an Encrypting File System (EFS) Data Recovery Agent (DRA) certificate](https://go.microsoft.com/fwlink/p/?linkid=853700) (skapa och verifiera ett certifikat för en dataåterställningsagent för kryptering av filsystem).</span><span class="sxs-lookup"><span data-stu-id="e8d29-p101">Before you can browse to the location of the Data Recovery Agent certificate, you have to first create one. For instructions see, [Create and verify an Encrypting File System (EFS) Data Recovery Agent (DRA) certificate](https://go.microsoft.com/fwlink/p/?linkid=853700).</span></span>
    
    <span data-ttu-id="e8d29-p102">Som standard krypteras arbetsfiler med en hemlig nyckel som lagras på enheten och som är kopplad till användarens profil. Endast användaren kan öppna och dekryptera filen. Men om en enhet försvinner eller en användare tas bort kan en fil fastna i ett krypterat tillstånd. Certifikatet för dataåterställningsagenten kan användas av en administratör för att dekryptera filen.</span><span class="sxs-lookup"><span data-stu-id="e8d29-p102">By default, work files are encrypted using a secret key that is stored on the device and associated with the user's profile. Only the user can open and decrypt the file. However, if a device is lost or a user is removed, a file can be stuck in an encrypted state. The Data Recovery Agent (DRA) certificate can be used by an admin to decrypt the file.</span></span>
    
    ![Browse to Data Recovery Agent certificate.](media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. <span data-ttu-id="e8d29-p103">Expandera **Skydda ytterligare nätverks- och molnplatser** om du vill lägga till ytterligare domäner och/eller SharePoint Online-webbplatser för att säkerställa att filerna i samtliga angivna program skyddas. Om du behöver ange mer än ett objekt i ett fält anger du ett semikolon (;) mellan objekten.</span><span class="sxs-lookup"><span data-stu-id="e8d29-p103">Expand **Protect additional network and cloud locations** if you want to add additional domains or SharePoint Online locations to make sure that files in all the listed apps will be protected. If you need to enter more than one item for either field, use a semicolon (;) between the items.</span></span>
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. <span data-ttu-id="e8d29-p104">Bestäm sedan **vem som ska få de här inställningarna** Om du inte vill använda standardsäkerhetsgruppen **Alla användare** väljer du **Ändra** och anger de säkerhetsgrupper som ska få dessa inställningar \> **Välj**.</span><span class="sxs-lookup"><span data-stu-id="e8d29-p104">Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span></span>
    
12. <span data-ttu-id="e8d29-126">Välj **Lägg till** för att spara principen och tilldela den till enheter.</span><span class="sxs-lookup"><span data-stu-id="e8d29-126">Finally, choose **Add** to save the policy, and assign it to devices.</span></span> 