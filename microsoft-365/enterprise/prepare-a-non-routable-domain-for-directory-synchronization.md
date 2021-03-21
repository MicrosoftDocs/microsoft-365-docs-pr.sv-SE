---
title: Förbereda en icke-dirigerbar domän för katalogsynkronisering
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365E_SetupDirSyncLocalDir
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: e7968303-c234-46c4-b8b0-b5c93c6d57a7
description: Ta reda på vad du kan göra om du har en icke-dirigerbar domän kopplad till dina lokala användarkonton innan du synkroniserar dem med din Microsoft 365-klientorganisation.
ms.openlocfilehash: e4d0e020c5792c610d501c33e8f3d5131b7a1ff0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927402"
---
# <a name="prepare-a-non-routable-domain-for-directory-synchronization"></a><span data-ttu-id="d6112-103">Förbereda en icke-dirigerbar domän för katalogsynkronisering</span><span class="sxs-lookup"><span data-stu-id="d6112-103">Prepare a non-routable domain for directory synchronization</span></span>

<span data-ttu-id="d6112-104">När du synkroniserar din lokala katalog med Microsoft 365 måste du ha en verifierad domän i Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="d6112-104">When you synchronize your on-premises directory with Microsoft 365, you have to have a verified domain in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="d6112-105">Endast de upn-namn (User Principal Names) som är kopplade till den lokala Active Directory Domain Services-domänen (AD DS) synkroniseras.</span><span class="sxs-lookup"><span data-stu-id="d6112-105">Only the User Principal Names (UPNs) that are associated with the on-premises Active Directory Domain Services (AD DS) domain are synchronized.</span></span> <span data-ttu-id="d6112-106">Men ALLA UPN som innehåller en icke-dirigerbar domän, till exempel ".local" (exempel: billa@contoso.local), synkroniseras med en .onmicrosoft.com domän (exempel: billa@contoso.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="d6112-106">However, any UPN that contains a non-routable domain, such as ".local" (example: billa@contoso.local), will be synchronized to an .onmicrosoft.com domain (example: billa@contoso.onmicrosoft.com).</span></span> 

<span data-ttu-id="d6112-107">Om du använder en .local-domän för dina användarkonton i AD DS rekommenderar vi att du ändrar dem till att använda en verifierad domän, till exempel billa@contoso.com, för att synkronisera dem med din Microsoft 365-domän.</span><span class="sxs-lookup"><span data-stu-id="d6112-107">If you currently use a ".local" domain for your user accounts in AD DS, it's recommended that you change them to use a verified domain, such as billa@contoso.com, in order to properly synchronize with your Microsoft 365 domain.</span></span>
  
## <a name="what-if-i-only-have-a-local-on-premises-domain"></a><span data-ttu-id="d6112-108">Vad händer om jag bara har en lokal ".local"-domän?</span><span class="sxs-lookup"><span data-stu-id="d6112-108">What if I only have a ".local" on-premises domain?</span></span>

<span data-ttu-id="d6112-109">Du använder Azure AD Connect för att synkronisera din AD DS till Azure AD-klientorganisationen i din Microsoft 365-klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="d6112-109">You use Azure AD Connect for synchronizing your AD DS to the Azure AD tenant of your Microsoft 365 tenant.</span></span> <span data-ttu-id="d6112-110">Mer information finns i [Integrera lokala identiteter med Azure AD.](/azure/architecture/reference-architectures/identity/azure-ad)</span><span class="sxs-lookup"><span data-stu-id="d6112-110">For more information, see [Integrating your on-premises identities with Azure AD](/azure/architecture/reference-architectures/identity/azure-ad).</span></span>
  
<span data-ttu-id="d6112-111">Azure AD Connect synkroniserar användarnas UPN och lösenord så att användarna kan logga in med samma inloggningsuppgifter som de använder lokalt.</span><span class="sxs-lookup"><span data-stu-id="d6112-111">Azure AD Connect synchronizes your users' UPN and password so that users can sign in with the same credentials they use on-premises.</span></span> <span data-ttu-id="d6112-112">Men Azure AD Connect synkroniserar bara användare med domäner som verifieras av Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d6112-112">However, Azure AD Connect only synchronizes users to domains that are verified by Microsoft 365.</span></span> <span data-ttu-id="d6112-113">Det innebär att domänen också verifieras av Azure AD eftersom Microsoft 365-identiteter hanteras av Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d6112-113">This means that the domain also is verified by Azure AD because Microsoft 365 identities are managed by Azure AD.</span></span> <span data-ttu-id="d6112-114">Med andra ord måste domänen vara en giltig Internetdomän (till exempel .com, .org, .net, .us).</span><span class="sxs-lookup"><span data-stu-id="d6112-114">In other words, the domain has to be a valid Internet domain (such as, .com, .org, .net, .us).</span></span> <span data-ttu-id="d6112-115">Om din interna AD DS endast använder en icke-dirigerbar domän (till exempel ".local") kan den inte matcha den verifierade domänen du har för Microsoft 365-klienten.</span><span class="sxs-lookup"><span data-stu-id="d6112-115">If your internal AD DS only uses a non-routable domain (for example, ".local"), this can't possibly match the verified domain you have for your Microsoft 365 tenant.</span></span> <span data-ttu-id="d6112-116">Du kan åtgärda problemet genom att antingen ändra din primära domän i din lokala AD DS eller genom att lägga till ett eller flera UPN-suffix.</span><span class="sxs-lookup"><span data-stu-id="d6112-116">You can fix this issue by either changing your primary domain in your on-premises AD DS, or by adding one or more UPN suffixes.</span></span>
  
### <a name="change-your-primary-domain"></a><span data-ttu-id="d6112-117">Ändra din primära domän</span><span class="sxs-lookup"><span data-stu-id="d6112-117">Change your primary domain</span></span>

<span data-ttu-id="d6112-118">Ändra din primära domän till en domän som du har verifierat i Microsoft 365, till exempel contoso.com.</span><span class="sxs-lookup"><span data-stu-id="d6112-118">Change your primary domain to a domain you have verified in Microsoft 365, for example, contoso.com.</span></span> <span data-ttu-id="d6112-119">Alla användare som har domänen contoso.local uppdateras sedan till contoso.com.</span><span class="sxs-lookup"><span data-stu-id="d6112-119">Every user that has the domain contoso.local is then updated to contoso.com.</span></span> <span data-ttu-id="d6112-120">Det här är en process som är mycket involverad och en enklare lösning beskrivs i följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="d6112-120">This is a very involved process, however, and an easier solution is described in the following section.</span></span>
  
### <a name="add-upn-suffixes-and-update-your-users-to-them"></a><span data-ttu-id="d6112-121">Lägga till UPN-suffix och uppdatera användarna till dem</span><span class="sxs-lookup"><span data-stu-id="d6112-121">Add UPN suffixes and update your users to them</span></span>

<span data-ttu-id="d6112-122">Du kan lösa problemet med ".local" genom att registrera nya UPN-suffix eller -suffix i AD DS så att de matchar den eller de domäner du verifierade i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d6112-122">You can solve the ".local" problem by registering new UPN suffix or suffixes in AD DS to match the domain (or domains) you verified in Microsoft 365.</span></span> <span data-ttu-id="d6112-123">När du har registrerat det nya suffixet uppdaterar du användarnas UPN så att de ersätter ".local" med det nya domännamnet, så att ett användarkonto ser ut som billa@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="d6112-123">After you register the new suffix, you update the user UPNs to replace the ".local" with the new domain name, for example, so that a user account looks like billa@contoso.com.</span></span>
  
<span data-ttu-id="d6112-124">När du har uppdaterat UPN-namn för att använda den verifierade domänen är du redo att synkronisera din lokala AD DS med Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d6112-124">After you have updated the UPNs to use the verified domain, you are ready to synchronize your on-premises AD DS with Microsoft 365.</span></span>
  
#### <a name="step-1-add-the-new-upn-suffix"></a><span data-ttu-id="d6112-125">Steg 1: Lägg till det nya UPN-suffixet\*\*</span><span class="sxs-lookup"><span data-stu-id="d6112-125">Step 1: Add the new UPN suffix\*\*</span></span>
  
1. <span data-ttu-id="d6112-126">I Serverhanteraren på AD DS-domänkontrollanten väljer **du Verktyg** \> **Active Directory - domäner och förtroenden.**</span><span class="sxs-lookup"><span data-stu-id="d6112-126">On the AD DS domain controller, in the Server Manager choose **Tools** \> **Active Directory Domains and Trusts**.</span></span>
    
    <span data-ttu-id="d6112-127">**Eller om du inte har Windows Server 2012**</span><span class="sxs-lookup"><span data-stu-id="d6112-127">**Or, if you don't have Windows Server 2012**</span></span>
    
    <span data-ttu-id="d6112-128">Tryck **på Windows-tangenten + R** för **att** öppna dialogrutan Kör, skriv Domain.msc och välj sedan **OK.**</span><span class="sxs-lookup"><span data-stu-id="d6112-128">Press **Windows key + R** to open the **Run** dialog, and then type in Domain.msc, and then choose **OK**.</span></span>
    
    ![Välj Active Directory - domäner och förtroenden.](../media/46b6e007-9741-44af-8517-6f682e0ac974.png)
  
2. <span data-ttu-id="d6112-130">I fönstret **Active Directory - domäner och** förtroenden högerklickar du på Active Directory **-** domäner och förtroenden och väljer sedan **Egenskaper**.</span><span class="sxs-lookup"><span data-stu-id="d6112-130">In the **Active Directory Domains and Trusts** window, right-click **Active Directory Domains and Trusts**, and then choose **Properties**.</span></span>
    
    ![Högerklicka på Active Directory - domäner och förtroenden och välj Egenskaper](../media/39d20812-ffb5-4ba9-8d7b-477377ac360d.png)
  
3. <span data-ttu-id="d6112-132">På fliken **UPN-suffix,** i rutan Alternativa **UPN-suffix,** skriver du det nya UPN-suffixet eller -suffixen och väljer sedan **Lägg till** \> **Använd.**</span><span class="sxs-lookup"><span data-stu-id="d6112-132">On the **UPN Suffixes** tab, in the **Alternative UPN Suffixes** box, type your new UPN suffix or suffixes, and then choose **Add** \> **Apply**.</span></span>
    
    ![Lägga till ett nytt UPN-suffix](../media/a4aaf919-7adf-469a-b93f-83ef284c0915.PNG)
  
    <span data-ttu-id="d6112-134">Välj **OK** när du är klar med att lägga till suffix.</span><span class="sxs-lookup"><span data-stu-id="d6112-134">Choose **OK** when you're done adding suffixes.</span></span> 
    
 #### <a name="step-2-change-the-upn-suffix-for-existing-users"></a><span data-ttu-id="d6112-135">Steg 2: Ändra UPN-suffixet för befintliga användare</span><span class="sxs-lookup"><span data-stu-id="d6112-135">Step 2: Change the UPN suffix for existing users</span></span>
  
1. <span data-ttu-id="d6112-136">I Serverhanteraren på AD DS-domänkontrollanten väljer du **Verktyg** \> **Active Directory - användare och datorer.**</span><span class="sxs-lookup"><span data-stu-id="d6112-136">On the AD DS domain controller, in the Server Manager choose **Tools** \> **Active Directory Users and Computers**.</span></span>
    
    <span data-ttu-id="d6112-137">**Eller om du inte har Windows Server 2012**</span><span class="sxs-lookup"><span data-stu-id="d6112-137">**Or, if you don't have Windows Server 2012**</span></span>
    
    <span data-ttu-id="d6112-138">Tryck **på Windows-tangenten + R** för att öppna dialogrutan Kör, skriv Dsa.msc och klicka sedan på **OK** </span><span class="sxs-lookup"><span data-stu-id="d6112-138">Press **Windows key + R** to open the **Run** dialog, and then type in Dsa.msc, and then click **OK**</span></span>
    
2. <span data-ttu-id="d6112-139">Välj en användare, högerklicka och välj sedan **Egenskaper**.</span><span class="sxs-lookup"><span data-stu-id="d6112-139">Select a user, right-click, and then choose **Properties**.</span></span>
    
3. <span data-ttu-id="d6112-140">Välj **det nya** UPN-suffixet i listrutan UPN-suffix på fliken Konto och välj sedan **OK.**</span><span class="sxs-lookup"><span data-stu-id="d6112-140">On the **Account** tab, in the UPN suffix drop-down list, choose the new UPN suffix, and then choose **OK**.</span></span>
    
    ![Lägga till nytt UPN-suffix för en användare](../media/54876751-49f0-48cc-b864-2623c4835563.png)
  
4. <span data-ttu-id="d6112-142">Utför de här stegen för alla användare.</span><span class="sxs-lookup"><span data-stu-id="d6112-142">Complete these steps for every user.</span></span>
    
   
### <a name="use-powershell-to-change-the-upn-suffix-for-all-of-your-users"></a><span data-ttu-id="d6112-143">Använda PowerShell för att ändra UPN-suffixet för alla användare</span><span class="sxs-lookup"><span data-stu-id="d6112-143">Use PowerShell to change the UPN suffix for all of your users</span></span>

<span data-ttu-id="d6112-144">Om du har många användarkonton att uppdatera är det enklare att använda PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d6112-144">If you have a lot of user accounts to update, it's easier to use PowerShell.</span></span> <span data-ttu-id="d6112-145">I följande exempel används cmdletarna [Get-ADUser](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617241(v=technet.10)) och [Set-ADUser](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617215(v=technet.10)) för att ändra alla contoso.local-suffix till contoso.com i AD DS.</span><span class="sxs-lookup"><span data-stu-id="d6112-145">The following example uses the cmdlets [Get-ADUser](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617241(v=technet.10)) and [Set-ADUser](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617215(v=technet.10)) to change all contoso.local suffixes to contoso.com in AD DS.</span></span> 

<span data-ttu-id="d6112-146">Du kan till exempel köra följande PowerShell-kommandon för att uppdatera alla contoso.local-suffix till contoso.com:</span><span class="sxs-lookup"><span data-stu-id="d6112-146">For example, you could run the following PowerShell commands to update all contoso.local suffixes to contoso.com:</span></span>
    
  ```powershell
  $LocalUsers = Get-ADUser -Filter "UserPrincipalName -like '*contoso.local'" -Properties userPrincipalName -ResultSetSize $null
  $LocalUsers | foreach {$newUpn = $_.UserPrincipalName.Replace("@contoso.local","@contoso.com"); $_ | Set-ADUser -UserPrincipalName $newUpn}
  ```

<span data-ttu-id="d6112-147">Mer information om hur du använder Windows PowerShell i AD DS finns i Modulen [Active Directory Windows PowerShell.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617195(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="d6112-147">See [Active Directory Windows PowerShell module](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617195(v=technet.10)) to learn more about using Windows PowerShell in AD DS.</span></span>