---
title: Förbereda en icke-dirigerbart domän för Active Directory-synkronisering
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
description: Lär dig vad du kan göra om du har en icke-dirigerbar domän kopplad till dina lokala användare innan du synkroniserar med Microsoft 365.
ms.openlocfilehash: 835beffb77c495179991fbb4388ecd9ee804ec91
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46696648"
---
# <a name="prepare-a-non-routable-domain-for-directory-synchronization"></a><span data-ttu-id="79a02-103">Förbereda en icke-dirigerbart domän för Active Directory-synkronisering</span><span class="sxs-lookup"><span data-stu-id="79a02-103">Prepare a non-routable domain for directory synchronization</span></span>
<span data-ttu-id="79a02-104">När du synkroniserar en lokal katalog med Microsoft 365 måste du ha en verifierad domän i Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="79a02-104">When you synchronize your on-premises directory with Microsoft 365 you have to have a verified domain in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="79a02-105">Endast UPN-namnen (User huvud namn) som är kopplade till den lokala domänen synkroniseras.</span><span class="sxs-lookup"><span data-stu-id="79a02-105">Only the User Principal Names (UPN) that are associated with the on-premises domain are synchronized.</span></span> <span data-ttu-id="79a02-106">Alla UPN som innehåller en icke-routad domän, till exempel. local (som billa@contoso. local) synkroniseras till en. onmicrosoft.com-domän (som billa@contoso.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="79a02-106">However, any UPN that contains an non-routable domain, for example .local (like billa@contoso.local), will be synchronized to an .onmicrosoft.com domain (like billa@contoso.onmicrosoft.com).</span></span> 

<span data-ttu-id="79a02-107">Om du för närvarande använder en. lokala domän för dina användar konton i Active Directory Domain Services (AD DS) rekommenderar vi att du ändrar dem till att använda en verifierad domän (till exempel billa@contoso.com) för att synkronisera med din Microsoft 365-domän korrekt.</span><span class="sxs-lookup"><span data-stu-id="79a02-107">If you currently use a .local domain for your user accounts in Active Directory Domain Services (AD DS) it's recommended that you change them to use a verified domain (like billa@contoso.com) in order to properly sync with your Microsoft 365 domain.</span></span>
  
## <a name="what-if-i-only-have-a-local-on-premises-domain"></a><span data-ttu-id="79a02-108">Vad händer om jag bara har en lokalt lokal domän?</span><span class="sxs-lookup"><span data-stu-id="79a02-108">What if I only have a .local on-premises domain?</span></span>

<span data-ttu-id="79a02-109">Det senaste verktyget som du kan använda för att synkronisera AD DS till Azure AD heter Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="79a02-109">The most recent tool you can use for synchronizing your AD DS to Azure AD is named Azure AD Connect.</span></span> <span data-ttu-id="79a02-110">Mer information finns i [integrera dina lokala identiteter med Azure AD](https://docs.microsoft.com/azure/architecture/reference-architectures/identity/azure-ad).</span><span class="sxs-lookup"><span data-stu-id="79a02-110">For more information, see [Integrating your on-premises identities with Azure AD](https://docs.microsoft.com/azure/architecture/reference-architectures/identity/azure-ad).</span></span>
  
<span data-ttu-id="79a02-111">Azure AD Connect synkroniserar användarnas UPN och lösen ord så att användare kan logga in med samma inloggnings uppgifter som de använder lokalt.</span><span class="sxs-lookup"><span data-stu-id="79a02-111">Azure AD Connect synchronizes your users' UPN and password so that users can sign in with the same credentials they use on-premises.</span></span> <span data-ttu-id="79a02-112">Azure AD Connect kan bara synkronisera användare till domäner som verifieras av Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="79a02-112">However, Azure AD Connect only synchronizes users to domains that are verified by Microsoft 365.</span></span> <span data-ttu-id="79a02-113">Detta innebär att domänen också verifieras av Azure AD eftersom Microsoft 365-identiteter hanteras av Azure AD.</span><span class="sxs-lookup"><span data-stu-id="79a02-113">This means that the domain also is verified by Azure AD because Microsoft 365 identities are managed by Azure AD.</span></span> <span data-ttu-id="79a02-114">Med andra ord måste domänen vara en giltig Internet-domän (till exempel. com,. org, .net,. USA osv.).</span><span class="sxs-lookup"><span data-stu-id="79a02-114">In other words, the domain has to be a valid Internet domain (for example, .com, .org, .net, .us, etc.).</span></span> <span data-ttu-id="79a02-115">Om den interna AD DS-tjänsten endast använder en icke-dirigerbart domän (till exempel. lokal) kan detta inte matcha den verifierade domän som du har på Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="79a02-115">If your internal AD DS only uses a non-routable domain (for example, .local), this can't possibly match the verified domain you have on Microsoft 365.</span></span> <span data-ttu-id="79a02-116">Du kan åtgärda det här problemet genom att antingen ändra din primära domän i din lokala AD DS, eller genom att lägga till ett eller flera UPN-suffix.</span><span class="sxs-lookup"><span data-stu-id="79a02-116">You can fix this issue by either changing your primary domain in your on premises AD DS, or by adding one or more UPN suffixes.</span></span>
  
### <a name="change-your-primary-domain"></a><span data-ttu-id="79a02-117">**Ändra din primära domän**</span><span class="sxs-lookup"><span data-stu-id="79a02-117">**Change your primary domain**</span></span>

<span data-ttu-id="79a02-118">Ändra din primära domän till en domän som du har verifierat i Microsoft 365, till exempel contoso.com.</span><span class="sxs-lookup"><span data-stu-id="79a02-118">Change your primary domain to a domain you have verified in Microsoft 365, for example, contoso.com.</span></span> <span data-ttu-id="79a02-119">Alla användare som har domänen contoso. local har sedan uppdaterats till contoso.com.</span><span class="sxs-lookup"><span data-stu-id="79a02-119">Every user that has the domain contoso.local is then updated to contoso.com.</span></span> <span data-ttu-id="79a02-120">Anvisningar finns i [hur domän namn byte fungerar](https://go.microsoft.com/fwlink/p/?LinkId=624174).</span><span class="sxs-lookup"><span data-stu-id="79a02-120">For instructions, see [How Domain Rename Works](https://go.microsoft.com/fwlink/p/?LinkId=624174).</span></span> <span data-ttu-id="79a02-121">Det här är ett mycket praktiskt tillvägagångs sätt och en enklare lösning beskrivs i följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="79a02-121">This is a very involved process, however, and an easier solution is described in the following section.</span></span>
  
### <a name="add-upn-suffixes-and-update-your-users-to-them"></a><span data-ttu-id="79a02-122">**Lägga till UPN-suffix och uppdatera användarna till dem**</span><span class="sxs-lookup"><span data-stu-id="79a02-122">**Add UPN suffixes and update your users to them**</span></span>

<span data-ttu-id="79a02-123">Du kan lösa det lokala problemet genom att registrera nya UPN-suffix eller suffix i AD DS för att matcha den eller de domäner som du verifierade i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="79a02-123">You can solve the .local problem by registering new UPN suffix or suffixes in AD DS to match the domain (or domains) you verified in Microsoft 365.</span></span> <span data-ttu-id="79a02-124">När du har registrerat det nya suffixet uppdaterar du användar-UPN för att ersätta. local med det nya domän namnet till exempel så att ett användar konto ser ut som billa@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="79a02-124">After you register the new suffix, you update the user UPNs to replace the .local with the new domain name for example so that a user account looks like billa@contoso.com.</span></span>
  
<span data-ttu-id="79a02-125">När du har uppdaterat UPN-värdet för att använda den verifierade domänen är du klar att synkronisera din lokala AD DS med Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="79a02-125">After you have updated the UPNs to use the verified domain, you are ready to synchronize your on-premises AD DS with Microsoft 365.</span></span>
  
 <span data-ttu-id="79a02-126">**Steg 1: Lägg till det nya UPN-suffixet**</span><span class="sxs-lookup"><span data-stu-id="79a02-126">**Step 1: Add the new UPN suffix**</span></span>
  
1. <span data-ttu-id="79a02-127">Välj **verktyg** \> **Active Directory-domäner och förtroenden**i Server hanteraren på AD DS-domänkontrollanten.</span><span class="sxs-lookup"><span data-stu-id="79a02-127">On the AD DS domain controller, in the Server Manager choose **Tools** \> **Active Directory Domains and Trusts**.</span></span>
    
    <span data-ttu-id="79a02-128">**Om du inte har Windows Server 2012**</span><span class="sxs-lookup"><span data-stu-id="79a02-128">**Or, if you don't have Windows Server 2012**</span></span>
    
    <span data-ttu-id="79a02-129">Tryck på **Windows-tangenten + R** för att öppna dialog rutan **Kör** och skriv sedan in Domain. msc och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="79a02-129">Press **Windows key + R** to open the **Run** dialog, and then type in Domain.msc, and then choose **OK**.</span></span>
    
    ![Välj Active Directory-domäner och förtroenden.](../media/46b6e007-9741-44af-8517-6f682e0ac974.png)
  
2. <span data-ttu-id="79a02-131">I fönstret **Active Directory-domäner och förtroenden** högerklickar du på **Active Directory-domäner och förtroenden**och väljer sedan **Egenskaper**.</span><span class="sxs-lookup"><span data-stu-id="79a02-131">On the **Active Directory Domains and Trusts** window, right-click **Active Directory Domains and Trusts**, and then choose **Properties**.</span></span>
    
    ![Högerklicka på Active Directory-domäner och förtroenden och välj egenskaper](../media/39d20812-ffb5-4ba9-8d7b-477377ac360d.png)
  
3. <span data-ttu-id="79a02-133">På fliken **UPN-suffix** , i rutan **alternativa UPN-suffix** , skriver du in det nya UPN-suffixet eller suffixen och väljer sedan **Lägg till** \> **Apply**.</span><span class="sxs-lookup"><span data-stu-id="79a02-133">On the **UPN Suffixes** tab, in the **Alternative UPN Suffixes** box, type your new UPN suffix or suffixes, and then choose **Add** \> **Apply**.</span></span>
    
    ![Lägga till ett nytt UPN-suffix](../media/a4aaf919-7adf-469a-b93f-83ef284c0915.PNG)
  
    <span data-ttu-id="79a02-135">Välj **OK** när du är klar med att lägga till suffix.</span><span class="sxs-lookup"><span data-stu-id="79a02-135">Choose **OK** when you're done adding suffixes.</span></span> 
    
 <span data-ttu-id="79a02-136">**Steg 2: ändra UPN-suffix för befintliga användare**</span><span class="sxs-lookup"><span data-stu-id="79a02-136">**Step 2: Change the UPN suffix for existing users**</span></span>
  
1. <span data-ttu-id="79a02-137">Välj **verktyg** \> **Active Directory-användare och datorer**i Server hanteraren på AD DS-domänkontrollanten.</span><span class="sxs-lookup"><span data-stu-id="79a02-137">On the AD DS domain controller, in the Server Manager choose **Tools** \> **Active Directory Users and Computers**.</span></span>
    
    <span data-ttu-id="79a02-138">**Om du inte har Windows Server 2012**</span><span class="sxs-lookup"><span data-stu-id="79a02-138">**Or, if you don't have Windows Server 2012**</span></span>
    
    <span data-ttu-id="79a02-139">Tryck på **Windows-tangenten + R** för att öppna dialog rutan **Kör** och skriv sedan in DSA. msc och klicka sedan på **OK** .</span><span class="sxs-lookup"><span data-stu-id="79a02-139">Press **Windows key + R** to open the **Run** dialog, and then type in Dsa.msc, and then click **OK**</span></span>
    
2. <span data-ttu-id="79a02-140">Välj en användare, högerklicka och välj sedan **Egenskaper**.</span><span class="sxs-lookup"><span data-stu-id="79a02-140">Select a user, right-click, and then choose **Properties**.</span></span>
    
3. <span data-ttu-id="79a02-141">Välj det nya UPN-suffixet i list rutan UPN-suffix på fliken **konto** och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="79a02-141">On the **Account** tab, in the UPN suffix drop-down list, choose the new UPN suffix, and then choose **OK**.</span></span>
    
    ![Lägga till ett nytt UPN-suffix för en användare](../media/54876751-49f0-48cc-b864-2623c4835563.png)
  
4. <span data-ttu-id="79a02-143">Utför de här stegen för alla användare.</span><span class="sxs-lookup"><span data-stu-id="79a02-143">Complete these steps for every user.</span></span>
    
   
### <a name="you-can-also-use-windows-powershell-to-change-the-upn-suffix-for-all-users"></a><span data-ttu-id="79a02-144">**Du kan också använda Windows PowerShell för att ändra UPN-suffix för alla användare**</span><span class="sxs-lookup"><span data-stu-id="79a02-144">**You can also use Windows PowerShell to change the UPN suffix for all users**</span></span>

<span data-ttu-id="79a02-145">Om du har många användare att uppdatera är det enklare att använda Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="79a02-145">If you have a lot of users to update, it is easier to use Windows PowerShell.</span></span> <span data-ttu-id="79a02-146">I följande exempel används cmdletarna [Get-ADUser](https://go.microsoft.com/fwlink/p/?LinkId=624312) och [set-ADUser](https://go.microsoft.com/fwlink/p/?LinkId=624313) för att ändra alla contoso. local-suffix till contoso.com.</span><span class="sxs-lookup"><span data-stu-id="79a02-146">The following example uses the cmdlets [Get-ADUser](https://go.microsoft.com/fwlink/p/?LinkId=624312) and [Set-ADUser](https://go.microsoft.com/fwlink/p/?LinkId=624313) to change all contoso.local suffixes to contoso.com.</span></span> 

<span data-ttu-id="79a02-147">Foe-exempel kan du köra följande Windows PowerShell-kommandon för att uppdatera alla contoso. local-suffix till contoso.com:</span><span class="sxs-lookup"><span data-stu-id="79a02-147">Foe example, you could run the following Windows PowerShell commands to update all contoso.local suffixes to contoso.com:</span></span>
    
  ```powershell
  $LocalUsers = Get-ADUser -Filter "UserPrincipalName -like '*contoso.local'" -Properties userPrincipalName -ResultSetSize $null
  $LocalUsers | foreach {$newUpn = $_.UserPrincipalName.Replace("@contoso.local","@contoso.com"); $_ | Set-ADUser -UserPrincipalName $newUpn}
  ```

<span data-ttu-id="79a02-148">Se [Active Directory Windows PowerShell-modulen](https://go.microsoft.com/fwlink/p/?LinkId=624314) för att få mer information om hur du använder Windows POWERSHELL i AD DS.</span><span class="sxs-lookup"><span data-stu-id="79a02-148">See [Active Directory Windows PowerShell module](https://go.microsoft.com/fwlink/p/?LinkId=624314) to learn more about using Windows PowerShell in AD DS.</span></span> 

