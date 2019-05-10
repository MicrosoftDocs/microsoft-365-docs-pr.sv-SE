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
ms.openlocfilehash: f649454417dceae05255df6b37760af99c0b8d4f
ms.sourcegitcommit: db1dfb2df2c2f7beced3b57bc772d106c189e88a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2019
ms.locfileid: "33660430"
---
# <a name="set-application-protection-settings-for-windows-10-devices"></a>Ange programskyddsinställningar för Windows 10-enheter

## <a name="create-an-app-management-policy-for-windows-10"></a>Skapa en princip för programhantering för Windows 10

Om dina användare har privata Windows 10-enheter som de utför arbetsuppgifter med kan du skydda data även på de enheterna.
  
1. Gå till administratörscenter på <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>. 
    
2. Välj **enheter** på vänster navigeringsfält \> **principer** \> **Lägg till**.

3. I fönstret **Lägg till princip** anger du ett unikt namn för principen. 
    
4. Välj **Programhantering för Windows 10** under **Principtyp**.
    
5. Välj **personlig** eller **Ägs av företaget**under **enhetstyp**.
    
6. **Kryptera arbetsfiler** aktiveras automatiskt. 
    
7. Ange **Hindra användare från att kopiera företagsdata till personliga filer och tvinga dem att spara arbetsfiler i OneDrive för företag** till **På** om du inte vill att användare ska kunna spara filer på sina datorer. 
    
9. Expandera **Återställ data på Windows-enheter**. Vi rekommenderar att du anger den till **På**.
    
    Innan du kan bläddra till certifikatet för dataåterställningsagenten måste du skapa ett. Anvisningar finns i [Create and verify an Encrypting File System (EFS) Data Recovery Agent (DRA) certificate](https://go.microsoft.com/fwlink/p/?linkid=853700) (skapa och verifiera ett certifikat för en dataåterställningsagent för kryptering av filsystem).
    
    Som standard krypteras arbetsfiler med en hemlig nyckel som lagras på enheten och som är kopplad till användarens profil. Endast användaren kan öppna och dekryptera filen. Men om en enhet försvinner eller en användare tas bort kan en fil fastna i ett krypterat tillstånd. Certifikatet för dataåterställningsagenten kan användas av en administratör för att dekryptera filen.
    
    ![Browse to Data Recovery Agent certificate.](media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. Expandera **Skydda ytterligare nätverks- och molnplatser** om du vill lägga till ytterligare domäner och/eller SharePoint Online-webbplatser för att säkerställa att filerna i samtliga angivna program skyddas. Om du behöver ange mer än ett objekt i ett fält anger du ett semikolon (;) mellan objekten.
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. Bestäm sedan **vem som ska få de här inställningarna** Om du inte vill använda standardsäkerhetsgruppen **Alla användare** väljer du **Ändra** och anger de säkerhetsgrupper som ska få dessa inställningar \> **Välj**.
    
12. Välj **Lägg till** för att spara principen och tilldela den till enheter. 