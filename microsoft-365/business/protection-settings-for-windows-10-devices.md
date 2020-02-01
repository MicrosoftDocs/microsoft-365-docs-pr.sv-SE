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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 02e74022-44af-414b-9d74-0ebf5c2197f0
description: Lär dig hur du skapar en apphanteringsprincip och skyddar arbetsfiler på Windows 10-enheter.
ms.openlocfilehash: 703f63fc1c90966eb8412886e82670af3e9d6f62
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41593545"
---
# <a name="set-application-protection-settings-for-windows-10-devices"></a>Ange programskyddsinställningar för Windows 10-enheter

## <a name="create-an-app-management-policy-for-windows-10"></a>Skapa en princip för programhantering för Windows 10

Om dina användare har privata Windows 10-enheter som de utför arbetsuppgifter med kan du skydda data även på de enheterna.
  
1. Gå till admin <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>center på . 
    
2. Välj \> **Enhetsprinciper** \> Lägg **** **till**på den vänstra naven .

3. I fönstret **Lägg till princip** anger du ett unikt namn för principen. 
    
4. Välj **Programhantering för Windows 10** under **Principtyp**.
    
5. Under **Enhetstyp**väljer du antingen **Personligt** eller **Företagsägt**.
    
6. **Kryptera arbetsfiler** aktiveras automatiskt. 
    
7. Ange **Hindra användare från att kopiera företagsdata till personliga filer och tvinga dem att spara arbetsfiler i OneDrive för företag** till **På** om du inte vill att användare ska kunna spara filer på sina datorer. 
    
9. Expandera **Återskapa data på Windows-enheter**. Vi rekommenderar att du slår **på**den .
    
    Innan du kan bläddra till certifikatet för dataåterställningsagenten måste du skapa ett. Instruktioner finns i [Skapa och verifiera ett EFS-certifikat (Encrypting File System) Data Recovery Agent (DRA).](https://go.microsoft.com/fwlink/p/?linkid=853700)
    
    Som standard krypteras arbetsfiler med en hemlig nyckel som lagras på enheten och som är kopplad till användarens profil. Endast användaren kan öppna och dekryptera filen. Men om en enhet försvinner eller en användare tas bort kan en fil fastna i ett krypterat tillstånd. En administratör kan använda LICENSen För Data Recovery Agent (DRA) för att dekryptera filen.
    
    ![Browse to Data Recovery Agent certificate.](media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. Expandera **Skydda ytterligare nätverks- och molnplatser** om du vill lägga till ytterligare domäner eller SharePoint Online-platser för att se till att filer i alla listade appar skyddas. Om du behöver ange mer än ett objekt i ett fält anger du ett semikolon (;) mellan objekten.
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. Bestäm sedan **vem som ska få de här inställningarna** Om du inte vill använda standardsäkerhetsgruppen **Alla användare** väljer du **Ändra** och anger de säkerhetsgrupper som ska få dessa inställningar \> **Välj**.
    
12. Välj **Lägg till** för att spara principen och tilldela den till enheter. 