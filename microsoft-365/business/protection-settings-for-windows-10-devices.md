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
ms.openlocfilehash: acf19a72d994185a35b2e425f8334a73a121ee10
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26982829"
---
# <a name="set-application-protection-settings-for-windows-10-devices"></a><span data-ttu-id="7c4a7-103">Ange programskyddsinställningar för Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="7c4a7-103">Set application protection settings for Windows 10 devices</span></span>

## <a name="create-an-app-management-policy-for-windows-10"></a><span data-ttu-id="7c4a7-104">Skapa en princip för programhantering för Windows 10</span><span class="sxs-lookup"><span data-stu-id="7c4a7-104">Create an app management policy for Windows 10</span></span>

<span data-ttu-id="7c4a7-105">Om dina användare har privata Windows 10-enheter som de utför arbetsuppgifter med kan du skydda data även på de enheterna.</span><span class="sxs-lookup"><span data-stu-id="7c4a7-105">If your users have personal Windows 10 devices on which they perform work tasks, you can protect your data on those devices as well.</span></span>
  
1. <span data-ttu-id="7c4a7-p101">Logga in på [Microsoft 365 Business](https://portal.office.com) som global administratör. Välj panelen **Administratör** för att gå till administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="7c4a7-p101">Sign in to [Microsoft 365 Business](https://portal.office.com) with global admin credentials. Choose the **Admin** tile to go to the admin center.</span></span> 
    
2. <span data-ttu-id="7c4a7-108">På kortet **Enhetsprinciper** i administrationsportalen väljer du **Lägg till princip**.</span><span class="sxs-lookup"><span data-stu-id="7c4a7-108">On the **Device policies** card of the admin portal, choose **Add policy**.</span></span>
    
    ![Device policies card in the admin center.](media/27c12b61-d112-4348-b557-4f3e46204797.png)
  
3. <span data-ttu-id="7c4a7-110">I fönstret **Lägg till princip** anger du ett unikt namn för principen.</span><span class="sxs-lookup"><span data-stu-id="7c4a7-110">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="7c4a7-111">Välj **Programhantering för Windows 10** under **Principtyp**.</span><span class="sxs-lookup"><span data-stu-id="7c4a7-111">Under **Policy type**, choose **Application Management for Windows 10**.</span></span>
    
5. <span data-ttu-id="7c4a7-112">Välj **Personlig** eller **Företagsägd** under \*\* Enhetstyp \*\*.</span><span class="sxs-lookup"><span data-stu-id="7c4a7-112">Under \*\* Device type \*\*, choose either **Personal** or **Company Owned**.</span></span>
    
6. <span data-ttu-id="7c4a7-113">**Kryptera arbetsfiler** aktiveras automatiskt.</span><span class="sxs-lookup"><span data-stu-id="7c4a7-113">The **Encrypt work files** is turned on automatically.</span></span> 
    
7. <span data-ttu-id="7c4a7-114">Ange **Hindra användare från att kopiera företagsdata till personliga filer och tvinga dem att spara arbetsfiler i OneDrive för företag** till **På** om du inte vill att användare ska kunna spara filer på sina datorer.</span><span class="sxs-lookup"><span data-stu-id="7c4a7-114">Set **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** to **On** if you don't want the users to save work files on their PC.</span></span> 
    
8. <span data-ttu-id="7c4a7-p102">Expandera **hantera hur användare kan komma åt Office-filer på enheter som** \> hur du vill konfigurera. **Hantera hur användare kommer åt kontorsenheter på mobila enheter** är **inaktiverat** som standard, men det rekommenderas att du **aktiverar det** och acceptera standardvärdena. Mer information finns i [tillgängliga inställningar](protection-settings-for-windows-10-devices.md#bkmk_settings) .</span><span class="sxs-lookup"><span data-stu-id="7c4a7-p102">Expand **Manage how users access Office files on devices** \> configure the settings how you would like. The **Manage how users access Office devices on mobile devices** is **Off** by default, but it is recommended that you turn it **On** and accept the default values. See [Available settings](protection-settings-for-windows-10-devices.md#bkmk_settings) for more information.</span></span> 
    
    <span data-ttu-id="7c4a7-118">Du kan alltid använda länken **Återställ standardinställningar** för att återgå till standardinställningarna.</span><span class="sxs-lookup"><span data-stu-id="7c4a7-118">You can always use the **Reset default settings** link to return to the default setting.</span></span> 
    
9. <span data-ttu-id="7c4a7-119">Expandera **Återställ data på Windows-enheter**. Vi rekommenderar att du anger den till **På**.</span><span class="sxs-lookup"><span data-stu-id="7c4a7-119">Expand **Recover data on Windows devices** and it is recommended that you turn it **On**.</span></span>
    
    <span data-ttu-id="7c4a7-p103">Innan du kan bläddra till certifikatet för dataåterställningsagenten måste du skapa ett. Anvisningar finns i [Create and verify an Encrypting File System (EFS) Data Recovery Agent (DRA) certificate](https://go.microsoft.com/fwlink/p/?linkid=853700) (skapa och verifiera ett certifikat för en dataåterställningsagent för kryptering av filsystem).</span><span class="sxs-lookup"><span data-stu-id="7c4a7-p103">Before you can browse to the location of the Data Recovery Agent certificate, you have to first create one. For instructions see, [Create and verify an Encrypting File System (EFS) Data Recovery Agent (DRA) certificate](https://go.microsoft.com/fwlink/p/?linkid=853700).</span></span>
    
    <span data-ttu-id="7c4a7-p104">Som standard krypteras arbetsfiler med en hemlig nyckel som lagras på enheten och som är kopplad till användarens profil. Endast användaren kan öppna och dekryptera filen. Men om en enhet försvinner eller en användare tas bort kan en fil fastna i ett krypterat tillstånd. Certifikatet för dataåterställningsagenten kan användas av en administratör för att dekryptera filen.</span><span class="sxs-lookup"><span data-stu-id="7c4a7-p104">By default, work files are encrypted using a secret key that is stored on the device and associated with the user's profile. Only the user can open and decrypt the file. However, if a device is lost or a user is removed, a file can be stuck in an encrypted state. The Data Recovery Agent (DRA) certificate can be used by an admin to decrypt the file.</span></span>
    
    ![Browse to Data Recovery Agent certificate.](media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. <span data-ttu-id="7c4a7-p105">Expandera **Skydda ytterligare nätverks- och molnplatser** om du vill lägga till ytterligare domäner och/eller SharePoint Online-webbplatser för att säkerställa att filerna i samtliga angivna program skyddas. Om du behöver ange mer än ett objekt i ett fält anger du ett semikolon (;) mellan objekten.</span><span class="sxs-lookup"><span data-stu-id="7c4a7-p105">Expand **Protect additional network and cloud locations** if you want to add additional domains or SharePoint Online locations to make sure that files in all the listed apps will be protected. If you need to enter more than one item for either field, use a semicolon (;) between the items.</span></span> 
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. <span data-ttu-id="7c4a7-p106">Bestäm sedan **vem som ska få de här inställningarna** Om du inte vill använda standardsäkerhetsgruppen **Alla användare** väljer du **Ändra** och anger de säkerhetsgrupper som ska få dessa inställningar \> **Välj**.</span><span class="sxs-lookup"><span data-stu-id="7c4a7-p106">Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span></span>
    
12. <span data-ttu-id="7c4a7-132">Välj **Lägg till** för att spara principen och tilldela den till enheter.</span><span class="sxs-lookup"><span data-stu-id="7c4a7-132">Finally, choose **Add** to save the policy, and assign it to devices.</span></span> 
    
## <a name="available-settings"></a><span data-ttu-id="7c4a7-133">Tillgängliga inställningar</span><span class="sxs-lookup"><span data-stu-id="7c4a7-133">Available settings</span></span>

<span data-ttu-id="7c4a7-134">Följande inställningar är till för att hantera hur användare kan komma åt Office-arbetsfiler.</span><span class="sxs-lookup"><span data-stu-id="7c4a7-134">The following settings are available to manage how users access Office work files.</span></span>
  
<span data-ttu-id="7c4a7-135">Mer information finns i [Hur mappar skyddsfunktioner i Microsoft 365 Business till Intune-inställningarna](map-protection-features-to-intune-settings.md).</span><span class="sxs-lookup"><span data-stu-id="7c4a7-135">For more information, see [How do protection features in Microsoft 365 Business map to Intune settings](map-protection-features-to-intune-settings.md).</span></span>
  
|<span data-ttu-id="7c4a7-136">**Inställning**</span><span class="sxs-lookup"><span data-stu-id="7c4a7-136">**Setting**</span></span>|<span data-ttu-id="7c4a7-137">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="7c4a7-137">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7c4a7-138">Kräv PIN-kod eller fingeravtryck för åtkomst till Office-program</span><span class="sxs-lookup"><span data-stu-id="7c4a7-138">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="7c4a7-139">Om inställningen är **På** måste användare utöver användarnamn och lösenord, tillhandahålla annan autentisering innan de kan använda Office-programmen på sin mobila enhet.</span><span class="sxs-lookup"><span data-stu-id="7c4a7-139">If this settings is **On** users have to provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="7c4a7-140">Återställ PIN-kod när inloggningen misslyckas så här många gånger</span><span class="sxs-lookup"><span data-stu-id="7c4a7-140">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="7c4a7-141">Om du vill förhindra att obehöriga användare slumpmässigt gissar en PIN-kod. PIN-koden återställs efter det antal felaktiga försök som du anger.</span><span class="sxs-lookup"><span data-stu-id="7c4a7-141">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="7c4a7-142">Kräv att användare loggar in igen efter att Office-appar har varit inaktiva</span><span class="sxs-lookup"><span data-stu-id="7c4a7-142">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="7c4a7-143">Den här inställningen anger hur lång tid användare kan vara inaktiva innan de uppmanas att logga in igen.</span><span class="sxs-lookup"><span data-stu-id="7c4a7-143">This setting determines how long a user can be idle before they are prompted to sign in again.</span></span>  <br/> |
   

