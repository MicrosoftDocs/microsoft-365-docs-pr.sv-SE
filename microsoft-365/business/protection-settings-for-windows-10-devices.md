---
title: Ange programskyddsinställningar för Windows 10-enheter
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
description: Lär dig hur du skapar en apphanteringsprincip och skyddar arbetsfiler på användarnas personliga Windows 10-enheter.
ms.openlocfilehash: df10470c6bd7aad2f35700a267c4d24d949f569c
ms.sourcegitcommit: 2d664a95b9875f0775f0da44aca73b16a816e1c3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/01/2020
ms.locfileid: "44470876"
---
# <a name="set-application-protection-settings-for-windows-10-devices"></a><span data-ttu-id="206fe-103">Ange programskyddsinställningar för Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="206fe-103">Set application protection settings for Windows 10 devices</span></span>

<span data-ttu-id="206fe-104">Den här artikeln gäller Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="206fe-104">This article applies to Microsoft 365 Business Premium.</span></span>

## <a name="create-an-app-management-policy-for-windows-10"></a><span data-ttu-id="206fe-105">Skapa en princip för programhantering för Windows 10</span><span class="sxs-lookup"><span data-stu-id="206fe-105">Create an app management policy for Windows 10</span></span>

<span data-ttu-id="206fe-106">Om dina användare har privata Windows 10-enheter som de utför arbetsuppgifter med kan du skydda data även på de enheterna.</span><span class="sxs-lookup"><span data-stu-id="206fe-106">If your users have personal Windows 10 devices on which they perform work tasks, you can protect your data on those devices as well.</span></span>
  
1. <span data-ttu-id="206fe-107">Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="206fe-107">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span> 
    
2. <span data-ttu-id="206fe-108">Välj **Enhetsprinciper** \> **Policies** \> **lägg till**på den vänstra navigeringsknappen .</span><span class="sxs-lookup"><span data-stu-id="206fe-108">On the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>

3. <span data-ttu-id="206fe-109">I fönstret **Lägg till princip** anger du ett unikt namn för principen.</span><span class="sxs-lookup"><span data-stu-id="206fe-109">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="206fe-110">Välj **Programhantering för Windows 10** under **Principtyp**.</span><span class="sxs-lookup"><span data-stu-id="206fe-110">Under **Policy type**, choose **Application Management for Windows 10**.</span></span>
    
5. <span data-ttu-id="206fe-111">Under **Enhetstyp**väljer du antingen **Person eller** **Företagsägda**.</span><span class="sxs-lookup"><span data-stu-id="206fe-111">Under **Device type**, choose either **Personal** or **Company Owned**.</span></span>
    
6. <span data-ttu-id="206fe-112">**Kryptera arbetsfiler** aktiveras automatiskt.</span><span class="sxs-lookup"><span data-stu-id="206fe-112">The **Encrypt work files** is turned on automatically.</span></span> 
    
7. <span data-ttu-id="206fe-113">Ange **Hindra användare från att kopiera företagsdata till personliga filer och tvinga dem att spara arbetsfiler i OneDrive för företag** till **På** om du inte vill att användare ska kunna spara filer på sina datorer.</span><span class="sxs-lookup"><span data-stu-id="206fe-113">Set **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** to **On** if you don't want the users to save work files on their PC.</span></span> 
    
9. <span data-ttu-id="206fe-114">Expandera **Återställ data på Windows-enheter**.</span><span class="sxs-lookup"><span data-stu-id="206fe-114">Expand **Recover data on Windows devices**.</span></span> <span data-ttu-id="206fe-115">Vi rekommenderar att du slår **på**den .</span><span class="sxs-lookup"><span data-stu-id="206fe-115">We recommend that you turn it **On**.</span></span>
    
    <span data-ttu-id="206fe-116">Innan du kan bläddra till certifikatet för dataåterställningsagenten måste du skapa ett.</span><span class="sxs-lookup"><span data-stu-id="206fe-116">Before you can browse to the location of the Data Recovery Agent certificate, you have to first create one.</span></span> <span data-ttu-id="206fe-117">Instruktioner finns i [Skapa och verifiera ett EFS-certifikat (Encrypting File System) Data Recovery Agent ..](https://go.microsoft.com/fwlink/p/?linkid=853700)</span><span class="sxs-lookup"><span data-stu-id="206fe-117">For instructions, see [Create and verify an Encrypting File System (EFS) Data Recovery Agent (DRA) certificate](https://go.microsoft.com/fwlink/p/?linkid=853700).</span></span>
    
    <span data-ttu-id="206fe-118">Som standard krypteras arbetsfiler med en hemlig nyckel som lagras på enheten och som är kopplad till användarens profil.</span><span class="sxs-lookup"><span data-stu-id="206fe-118">By default, work files are encrypted using a secret key that is stored on the device and associated with the user's profile.</span></span> <span data-ttu-id="206fe-119">Endast användaren kan öppna och dekryptera filen.</span><span class="sxs-lookup"><span data-stu-id="206fe-119">Only the user can open and decrypt the file.</span></span> <span data-ttu-id="206fe-120">Men om en enhet försvinner eller en användare tas bort kan en fil fastna i ett krypterat tillstånd.</span><span class="sxs-lookup"><span data-stu-id="206fe-120">However, if a device is lost or a user is removed, a file can be stuck in an encrypted state.</span></span> <span data-ttu-id="206fe-121">En administratör kan använda DRA-certifikatet (Data Recovery Agent) för att dekryptera filen.</span><span class="sxs-lookup"><span data-stu-id="206fe-121">An admin can use the Data Recovery Agent (DRA) certificate to decrypt the file.</span></span>
    
    ![Browse to Data Recovery Agent certificate.](../media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. <span data-ttu-id="206fe-123">Expandera **Skydda ytterligare nätverks- och molnplatser** om du vill lägga till ytterligare domäner eller SharePoint Online-platser för att se till att filerna i alla appar i listan är skyddade.</span><span class="sxs-lookup"><span data-stu-id="206fe-123">Expand **Protect additional network and cloud locations** if you want to add additional domains or SharePoint Online locations to make sure that files in all the listed apps are protected.</span></span> <span data-ttu-id="206fe-124">Om du behöver ange mer än ett objekt i ett fält anger du ett semikolon (;) mellan objekten.</span><span class="sxs-lookup"><span data-stu-id="206fe-124">If you need to enter more than one item for either field, use a semicolon (;) between the items.</span></span>
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](../media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. <span data-ttu-id="206fe-p105">Bestäm sedan **vem som ska få de här inställningarna** Om du inte vill använda standardsäkerhetsgruppen **Alla användare** väljer du **Ändra** och anger de säkerhetsgrupper som ska få dessa inställningar \> **Välj**.</span><span class="sxs-lookup"><span data-stu-id="206fe-p105">Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span></span>
    
12. <span data-ttu-id="206fe-128">Välj **Lägg till** för att spara principen och tilldela den till enheter.</span><span class="sxs-lookup"><span data-stu-id="206fe-128">Finally, choose **Add** to save the policy, and assign it to devices.</span></span> 
