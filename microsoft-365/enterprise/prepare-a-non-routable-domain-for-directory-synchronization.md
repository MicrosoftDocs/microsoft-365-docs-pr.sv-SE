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
# <a name="prepare-a-non-routable-domain-for-directory-synchronization"></a>Förbereda en icke-dirigerbar domän för katalogsynkronisering

När du synkroniserar din lokala katalog med Microsoft 365 måste du ha en verifierad domän i Azure Active Directory (Azure AD). Endast de upn-namn (User Principal Names) som är kopplade till den lokala Active Directory Domain Services-domänen (AD DS) synkroniseras. Men ALLA UPN som innehåller en icke-dirigerbar domän, till exempel ".local" (exempel: billa@contoso.local), synkroniseras med en .onmicrosoft.com domän (exempel: billa@contoso.onmicrosoft.com). 

Om du använder en .local-domän för dina användarkonton i AD DS rekommenderar vi att du ändrar dem till att använda en verifierad domän, till exempel billa@contoso.com, för att synkronisera dem med din Microsoft 365-domän.
  
## <a name="what-if-i-only-have-a-local-on-premises-domain"></a>Vad händer om jag bara har en lokal ".local"-domän?

Du använder Azure AD Connect för att synkronisera din AD DS till Azure AD-klientorganisationen i din Microsoft 365-klientorganisation. Mer information finns i [Integrera lokala identiteter med Azure AD.](/azure/architecture/reference-architectures/identity/azure-ad)
  
Azure AD Connect synkroniserar användarnas UPN och lösenord så att användarna kan logga in med samma inloggningsuppgifter som de använder lokalt. Men Azure AD Connect synkroniserar bara användare med domäner som verifieras av Microsoft 365. Det innebär att domänen också verifieras av Azure AD eftersom Microsoft 365-identiteter hanteras av Azure AD. Med andra ord måste domänen vara en giltig Internetdomän (till exempel .com, .org, .net, .us). Om din interna AD DS endast använder en icke-dirigerbar domän (till exempel ".local") kan den inte matcha den verifierade domänen du har för Microsoft 365-klienten. Du kan åtgärda problemet genom att antingen ändra din primära domän i din lokala AD DS eller genom att lägga till ett eller flera UPN-suffix.
  
### <a name="change-your-primary-domain"></a>Ändra din primära domän

Ändra din primära domän till en domän som du har verifierat i Microsoft 365, till exempel contoso.com. Alla användare som har domänen contoso.local uppdateras sedan till contoso.com. Det här är en process som är mycket involverad och en enklare lösning beskrivs i följande avsnitt.
  
### <a name="add-upn-suffixes-and-update-your-users-to-them"></a>Lägga till UPN-suffix och uppdatera användarna till dem

Du kan lösa problemet med ".local" genom att registrera nya UPN-suffix eller -suffix i AD DS så att de matchar den eller de domäner du verifierade i Microsoft 365. När du har registrerat det nya suffixet uppdaterar du användarnas UPN så att de ersätter ".local" med det nya domännamnet, så att ett användarkonto ser ut som billa@contoso.com.
  
När du har uppdaterat UPN-namn för att använda den verifierade domänen är du redo att synkronisera din lokala AD DS med Microsoft 365.
  
#### <a name="step-1-add-the-new-upn-suffix"></a>Steg 1: Lägg till det nya UPN-suffixet**
  
1. I Serverhanteraren på AD DS-domänkontrollanten väljer **du Verktyg** \> **Active Directory - domäner och förtroenden.**
    
    **Eller om du inte har Windows Server 2012**
    
    Tryck **på Windows-tangenten + R** för **att** öppna dialogrutan Kör, skriv Domain.msc och välj sedan **OK.**
    
    ![Välj Active Directory - domäner och förtroenden.](../media/46b6e007-9741-44af-8517-6f682e0ac974.png)
  
2. I fönstret **Active Directory - domäner och** förtroenden högerklickar du på Active Directory **-** domäner och förtroenden och väljer sedan **Egenskaper**.
    
    ![Högerklicka på Active Directory - domäner och förtroenden och välj Egenskaper](../media/39d20812-ffb5-4ba9-8d7b-477377ac360d.png)
  
3. På fliken **UPN-suffix,** i rutan Alternativa **UPN-suffix,** skriver du det nya UPN-suffixet eller -suffixen och väljer sedan **Lägg till** \> **Använd.**
    
    ![Lägga till ett nytt UPN-suffix](../media/a4aaf919-7adf-469a-b93f-83ef284c0915.PNG)
  
    Välj **OK** när du är klar med att lägga till suffix. 
    
 #### <a name="step-2-change-the-upn-suffix-for-existing-users"></a>Steg 2: Ändra UPN-suffixet för befintliga användare
  
1. I Serverhanteraren på AD DS-domänkontrollanten väljer du **Verktyg** \> **Active Directory - användare och datorer.**
    
    **Eller om du inte har Windows Server 2012**
    
    Tryck **på Windows-tangenten + R** för att öppna dialogrutan Kör, skriv Dsa.msc och klicka sedan på **OK** 
    
2. Välj en användare, högerklicka och välj sedan **Egenskaper**.
    
3. Välj **det nya** UPN-suffixet i listrutan UPN-suffix på fliken Konto och välj sedan **OK.**
    
    ![Lägga till nytt UPN-suffix för en användare](../media/54876751-49f0-48cc-b864-2623c4835563.png)
  
4. Utför de här stegen för alla användare.
    
   
### <a name="use-powershell-to-change-the-upn-suffix-for-all-of-your-users"></a>Använda PowerShell för att ändra UPN-suffixet för alla användare

Om du har många användarkonton att uppdatera är det enklare att använda PowerShell. I följande exempel används cmdletarna [Get-ADUser](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617241(v=technet.10)) och [Set-ADUser](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617215(v=technet.10)) för att ändra alla contoso.local-suffix till contoso.com i AD DS. 

Du kan till exempel köra följande PowerShell-kommandon för att uppdatera alla contoso.local-suffix till contoso.com:
    
  ```powershell
  $LocalUsers = Get-ADUser -Filter "UserPrincipalName -like '*contoso.local'" -Properties userPrincipalName -ResultSetSize $null
  $LocalUsers | foreach {$newUpn = $_.UserPrincipalName.Replace("@contoso.local","@contoso.com"); $_ | Set-ADUser -UserPrincipalName $newUpn}
  ```

Mer information om hur du använder Windows PowerShell i AD DS finns i Modulen [Active Directory Windows PowerShell.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617195(v=technet.10))