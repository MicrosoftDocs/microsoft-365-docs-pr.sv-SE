---
title: Ange programskyddsinställningar för Windows 10-enheter
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 02e74022-44af-414b-9d74-0ebf5c2197f0
description: Lär dig hur du skapar en princip för hantering av app och skydda arbete filer på Windows 10 enheter.
ms.openlocfilehash: 289c6a74f6ccb53f6a833612a7b4a5bcddd3ea56
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278203"
---
# <a name="set-application-protection-settings-for-windows-10-devices"></a><span data-ttu-id="fc1dc-103">Ange programskyddsinställningar för Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="fc1dc-103">Set application protection settings for Windows 10 devices</span></span>

## <a name="create-an-app-management-policy-for-windows-10"></a><span data-ttu-id="fc1dc-104">Skapa en princip för programhantering för Windows 10</span><span class="sxs-lookup"><span data-stu-id="fc1dc-104">Create an app management policy for Windows 10</span></span>

<span data-ttu-id="fc1dc-105">Om dina användare har privata Windows 10-enheter som de utför arbetsuppgifter med kan du skydda data även på de enheterna.</span><span class="sxs-lookup"><span data-stu-id="fc1dc-105">If your users have personal Windows 10 devices on which they perform work tasks, you can protect your data on those devices as well.</span></span>
  
1. <span data-ttu-id="fc1dc-106">Logga in på [administratörscenter](https://go.microsoft.com/fwlink/p/?linkid=837890) med globala admin autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="fc1dc-106">Sign in to [admin center](https://go.microsoft.com/fwlink/p/?linkid=837890) with global admin credentials.</span></span> <span data-ttu-id="fc1dc-107">Välj panelen **Administratör** för att gå till administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="fc1dc-107">Choose the **Admin** tile to go to the admin center.</span></span> 
    
2. <span data-ttu-id="fc1dc-108">Välj **enheter** på vänster navigeringsfält \> **principer** \> **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="fc1dc-108">On the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>

3. <span data-ttu-id="fc1dc-109">I fönstret **Lägg till princip** anger du ett unikt namn för principen.</span><span class="sxs-lookup"><span data-stu-id="fc1dc-109">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="fc1dc-110">Välj **Programhantering för Windows 10** under **Principtyp**.</span><span class="sxs-lookup"><span data-stu-id="fc1dc-110">Under **Policy type**, choose **Application Management for Windows 10**.</span></span>
    
5. <span data-ttu-id="fc1dc-111">Välj **Personlig** eller **Företagsägd** under \*\* Enhetstyp \*\*.</span><span class="sxs-lookup"><span data-stu-id="fc1dc-111">Under \*\* Device type \*\*, choose either **Personal** or **Company Owned**.</span></span>
    
6. <span data-ttu-id="fc1dc-112">**Kryptera arbetsfiler** aktiveras automatiskt.</span><span class="sxs-lookup"><span data-stu-id="fc1dc-112">The **Encrypt work files** is turned on automatically.</span></span> 
    
7. <span data-ttu-id="fc1dc-113">Ange **Hindra användare från att kopiera företagsdata till personliga filer och tvinga dem att spara arbetsfiler i OneDrive för företag** till **På** om du inte vill att användare ska kunna spara filer på sina datorer.</span><span class="sxs-lookup"><span data-stu-id="fc1dc-113">Set **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** to **On** if you don't want the users to save work files on their PC.</span></span> 
    
8. <span data-ttu-id="fc1dc-114">Expand **Manage how users access Office files on devices** \> configure the settings how you would like.</span><span class="sxs-lookup"><span data-stu-id="fc1dc-114">Expand **Manage how users access Office files on devices** \> configure the settings how you would like.</span></span> <span data-ttu-id="fc1dc-115">The **Manage how users access Office devices on mobile devices** is **Off** by default, but it is recommended that you turn it **On** and accept the default values.</span><span class="sxs-lookup"><span data-stu-id="fc1dc-115">The **Manage how users access Office devices on mobile devices** is **Off** by default, but it is recommended that you turn it **On** and accept the default values.</span></span> <span data-ttu-id="fc1dc-116">Mer information finns i [tillgängliga inställningar](#available-settings).</span><span class="sxs-lookup"><span data-stu-id="fc1dc-116">See [Available settings](#available-settings)for more information.</span></span> 
    
    <span data-ttu-id="fc1dc-117">Du kan alltid använda länken **Återställ standardinställningar** för att återgå till standardinställningarna.</span><span class="sxs-lookup"><span data-stu-id="fc1dc-117">You can always use the **Reset default settings** link to return to the default setting.</span></span> 
    
9. <span data-ttu-id="fc1dc-118">Expandera **Återställ data på Windows-enheter**. Vi rekommenderar att du anger den till **På**.</span><span class="sxs-lookup"><span data-stu-id="fc1dc-118">Expand **Recover data on Windows devices** and it is recommended that you turn it **On**.</span></span>
    
    <span data-ttu-id="fc1dc-p103">Innan du kan bläddra till certifikatet för dataåterställningsagenten måste du skapa ett. Anvisningar finns i [Create and verify an Encrypting File System (EFS) Data Recovery Agent (DRA) certificate](https://go.microsoft.com/fwlink/p/?linkid=853700) (skapa och verifiera ett certifikat för en dataåterställningsagent för kryptering av filsystem).</span><span class="sxs-lookup"><span data-stu-id="fc1dc-p103">Before you can browse to the location of the Data Recovery Agent certificate, you have to first create one. For instructions see, [Create and verify an Encrypting File System (EFS) Data Recovery Agent (DRA) certificate](https://go.microsoft.com/fwlink/p/?linkid=853700).</span></span>
    
    <span data-ttu-id="fc1dc-p104">Som standard krypteras arbetsfiler med en hemlig nyckel som lagras på enheten och som är kopplad till användarens profil. Endast användaren kan öppna och dekryptera filen. Men om en enhet försvinner eller en användare tas bort kan en fil fastna i ett krypterat tillstånd. Certifikatet för dataåterställningsagenten kan användas av en administratör för att dekryptera filen.</span><span class="sxs-lookup"><span data-stu-id="fc1dc-p104">By default, work files are encrypted using a secret key that is stored on the device and associated with the user's profile. Only the user can open and decrypt the file. However, if a device is lost or a user is removed, a file can be stuck in an encrypted state. The Data Recovery Agent (DRA) certificate can be used by an admin to decrypt the file.</span></span>
    
    ![Browse to Data Recovery Agent certificate.](media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. <span data-ttu-id="fc1dc-p105">Expandera **Skydda ytterligare nätverks- och molnplatser** om du vill lägga till ytterligare domäner och/eller SharePoint Online-webbplatser för att säkerställa att filerna i samtliga angivna program skyddas. Om du behöver ange mer än ett objekt i ett fält anger du ett semikolon (;) mellan objekten.</span><span class="sxs-lookup"><span data-stu-id="fc1dc-p105">Expand **Protect additional network and cloud locations** if you want to add additional domains or SharePoint Online locations to make sure that files in all the listed apps will be protected. If you need to enter more than one item for either field, use a semicolon (;) between the items.</span></span> 
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. <span data-ttu-id="fc1dc-p106">Bestäm sedan **vem som ska få de här inställningarna** Om du inte vill använda standardsäkerhetsgruppen **Alla användare** väljer du **Ändra** och anger de säkerhetsgrupper som ska få dessa inställningar \> **Välj**.</span><span class="sxs-lookup"><span data-stu-id="fc1dc-p106">Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span></span>
    
12. <span data-ttu-id="fc1dc-131">Välj **Lägg till** för att spara principen och tilldela den till enheter.</span><span class="sxs-lookup"><span data-stu-id="fc1dc-131">Finally, choose **Add** to save the policy, and assign it to devices.</span></span> 
    
## <a name="available-settings"></a><span data-ttu-id="fc1dc-132">Tillgängliga inställningar</span><span class="sxs-lookup"><span data-stu-id="fc1dc-132">Available settings</span></span>

<span data-ttu-id="fc1dc-133">Följande inställningar är till för att hantera hur användare kan komma åt Office-arbetsfiler.</span><span class="sxs-lookup"><span data-stu-id="fc1dc-133">The following settings are available to manage how users access Office work files.</span></span>
  
<span data-ttu-id="fc1dc-134">Mer information finns i [Hur mappar skyddsfunktioner i Microsoft 365 Business till Intune-inställningarna](map-protection-features-to-intune-settings.md).</span><span class="sxs-lookup"><span data-stu-id="fc1dc-134">For more information, see [How do protection features in Microsoft 365 Business map to Intune settings](map-protection-features-to-intune-settings.md).</span></span>
  
|<span data-ttu-id="fc1dc-135">**Inställning**</span><span class="sxs-lookup"><span data-stu-id="fc1dc-135">**Setting**</span></span>|<span data-ttu-id="fc1dc-136">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="fc1dc-136">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fc1dc-137">Kräv PIN-kod eller fingeravtryck för åtkomst till Office-program</span><span class="sxs-lookup"><span data-stu-id="fc1dc-137">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="fc1dc-138">Om inställningen är **På** måste användare utöver användarnamn och lösenord, tillhandahålla annan autentisering innan de kan använda Office-programmen på sin mobila enhet.</span><span class="sxs-lookup"><span data-stu-id="fc1dc-138">If this settings is **On** users have to provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="fc1dc-139">Återställ PIN-kod när inloggningen misslyckas så här många gånger</span><span class="sxs-lookup"><span data-stu-id="fc1dc-139">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="fc1dc-140">Om du vill förhindra att obehöriga användare slumpmässigt gissar en PIN-kod. PIN-koden återställs efter det antal felaktiga försök som du anger.</span><span class="sxs-lookup"><span data-stu-id="fc1dc-140">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="fc1dc-141">Kräv att användare loggar in igen efter att Office-appar har varit inaktiva</span><span class="sxs-lookup"><span data-stu-id="fc1dc-141">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="fc1dc-142">Den här inställningen anger hur lång tid användare kan vara inaktiva innan de uppmanas att logga in igen.</span><span class="sxs-lookup"><span data-stu-id="fc1dc-142">This setting determines how long a user can be idle before they are prompted to sign in again.</span></span>  <br/> |
   

