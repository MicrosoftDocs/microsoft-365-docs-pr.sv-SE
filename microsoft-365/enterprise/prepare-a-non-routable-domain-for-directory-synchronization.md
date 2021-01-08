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
description: Lär dig vad du kan göra om du har en icke-dirigerbart domän kopplad till dina lokala användar konton innan du synkroniserar dem med din Microsoft 365-klient.
ms.openlocfilehash: dcd941bbae159afeb0cf6ef4f5acbaf409966295
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780338"
---
# <a name="prepare-a-non-routable-domain-for-directory-synchronization"></a>Förbereda en icke-dirigerbar domän för katalogsynkronisering

När du synkroniserar en lokal katalog med Microsoft 365 måste du ha en verifierad domän i Azure Active Directory (Azure AD). Endast UPN (User Principal Name) som är kopplade till den lokala Active Directory Domain Services-domänen (AD DS) synkroniseras. Alla UPN som innehåller en icke-dirigerbart domän, till exempel ". local" (exempel: billa@contoso. local), synkroniseras till en. onmicrosoft.com-domän (exempel: billa@contoso.onmicrosoft.com). 

Om du använder en ". local"-domän för dina användar konton i AD DS rekommenderar vi att du ändrar dem till att använda en verifierad domän, till exempel billa@contoso.com, för att kunna synkroniseras korrekt med din Microsoft 365-domän.
  
## <a name="what-if-i-only-have-a-local-on-premises-domain"></a>Vad händer om jag bara har en "lokalt" lokal domän?

Du använder Azure AD Connect för att synkronisera din AD DS till Azure AD-innehavaren av din Microsoft 365-klient. Mer information finns i [integrera dina lokala identiteter med Azure AD](https://docs.microsoft.com/azure/architecture/reference-architectures/identity/azure-ad).
  
Azure AD Connect synkroniserar användarnas UPN och lösen ord så att användare kan logga in med samma inloggnings uppgifter som de använder lokalt. Azure AD Connect kan bara synkronisera användare till domäner som verifieras av Microsoft 365. Detta innebär att domänen också verifieras av Azure AD eftersom Microsoft 365-identiteter hanteras av Azure AD. Med andra ord måste domänen vara en giltig Internet-domän (till exempel. com,. org, .net,. us). Om den interna AD DS-tjänsten endast använder en icke-dirigerbart domän (till exempel ". lokal"), kan detta inte matcha den verifierade domän som du har för Microsoft 365-klienten. Du kan åtgärda det här problemet genom att antingen ändra din primära domän i din lokala AD DS, eller genom att lägga till ett eller flera UPN-suffix.
  
### <a name="change-your-primary-domain"></a>Ändra din primära domän

Ändra din primära domän till en domän som du har verifierat i Microsoft 365, till exempel contoso.com. Alla användare som har domänen contoso. local har sedan uppdaterats till contoso.com. Det här är ett mycket praktiskt tillvägagångs sätt och en enklare lösning beskrivs i följande avsnitt.
  
### <a name="add-upn-suffixes-and-update-your-users-to-them"></a>Lägga till UPN-suffix och uppdatera användarna till dem

Du kan lösa problemet ". local" genom att registrera nya UPN-suffix eller suffix i AD DS för att matcha den eller de domäner som du verifierade i Microsoft 365. När du har registrerat det nya suffixet uppdaterar du användar-UPN för att ersätta ". local" med det nya domän namnet, till exempel så att ett användar konto ser ut som billa@contoso.com.
  
När du har uppdaterat UPN-värdet för att använda den verifierade domänen är du klar att synkronisera din lokala AD DS med Microsoft 365.
  
#### <a name="step-1-add-the-new-upn-suffix"></a>Steg 1: Lägg till det nya UPN-suffixet * *
  
1. Välj **verktyg** \> **Active Directory-domäner och förtroenden** i Server hanteraren på AD DS-domänkontrollanten.
    
    **Om du inte har Windows Server 2012**
    
    Tryck på **Windows-tangenten + R** för att öppna dialog rutan **Kör** och skriv sedan in Domain. msc och välj sedan **OK**.
    
    ![Välj Active Directory-domäner och förtroenden.](../media/46b6e007-9741-44af-8517-6f682e0ac974.png)
  
2. I fönstret **Active Directory-domäner och förtroenden** högerklickar du på **Active Directory-domäner och förtroenden** och väljer sedan **Egenskaper**.
    
    ![Högerklicka på Active Directory-domäner och förtroenden och välj egenskaper](../media/39d20812-ffb5-4ba9-8d7b-477377ac360d.png)
  
3. På fliken **UPN-suffix** , i rutan **alternativa UPN-suffix** , skriver du in det nya UPN-suffixet eller suffixen och väljer sedan **Lägg till** \> .
    
    ![Lägga till ett nytt UPN-suffix](../media/a4aaf919-7adf-469a-b93f-83ef284c0915.PNG)
  
    Välj **OK** när du är klar med att lägga till suffix. 
    
 #### <a name="step-2-change-the-upn-suffix-for-existing-users"></a>Steg 2: ändra UPN-suffix för befintliga användare
  
1. Välj **verktyg** \> **Active Directory-användare och datorer** i Server hanteraren på AD DS-domänkontrollanten.
    
    **Om du inte har Windows Server 2012**
    
    Tryck på **Windows-tangenten + R** för att öppna dialog rutan **Kör** och skriv sedan in DSA. msc och klicka sedan på **OK** .
    
2. Välj en användare, högerklicka och välj sedan **Egenskaper**.
    
3. Välj det nya UPN-suffixet i list rutan UPN-suffix på fliken **konto** och välj sedan **OK**.
    
    ![Lägga till ett nytt UPN-suffix för en användare](../media/54876751-49f0-48cc-b864-2623c4835563.png)
  
4. Utför de här stegen för alla användare.
    
   
### <a name="use-powershell-to-change-the-upn-suffix-for-all-of-your-users"></a>Använda PowerShell för att ändra UPN-suffix för alla dina användare

Om du har många användar konton som ska uppdateras är det enklare att använda PowerShell. I följande exempel används cmdletarna [Get-ADUser](https://go.microsoft.com/fwlink/p/?LinkId=624312) och [set-ADUser](https://go.microsoft.com/fwlink/p/?LinkId=624313) för att ändra alla contoso. local-suffix till contoso.com i AD DS. 

Du kan till exempel köra följande PowerShell-kommandon för att uppdatera alla contoso. lokala suffix till contoso.com:
    
  ```powershell
  $LocalUsers = Get-ADUser -Filter "UserPrincipalName -like '*contoso.local'" -Properties userPrincipalName -ResultSetSize $null
  $LocalUsers | foreach {$newUpn = $_.UserPrincipalName.Replace("@contoso.local","@contoso.com"); $_ | Set-ADUser -UserPrincipalName $newUpn}
  ```

Se [Active Directory Windows PowerShell-modulen](https://go.microsoft.com/fwlink/p/?LinkId=624314) för att få mer information om hur du använder Windows POWERSHELL i AD DS. 

