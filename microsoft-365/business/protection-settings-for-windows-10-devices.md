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
# <a name="set-application-protection-settings-for-windows-10-devices"></a>Ange programskyddsinställningar för Windows 10-enheter

## <a name="create-an-app-management-policy-for-windows-10"></a>Skapa en princip för programhantering för Windows 10

Om dina användare har privata Windows 10-enheter som de utför arbetsuppgifter med kan du skydda data även på de enheterna.
  
1. Logga in på [administratörscenter](https://go.microsoft.com/fwlink/p/?linkid=837890) med globala admin autentiseringsuppgifter. Välj panelen **Administratör** för att gå till administrationscentret. 
    
2. Välj **enheter** på vänster navigeringsfält \> **principer** \> **Lägg till**.

3. I fönstret **Lägg till princip** anger du ett unikt namn för principen. 
    
4. Välj **Programhantering för Windows 10** under **Principtyp**.
    
5. Välj **Personlig** eller **Företagsägd** under ** Enhetstyp **.
    
6. **Kryptera arbetsfiler** aktiveras automatiskt. 
    
7. Ange **Hindra användare från att kopiera företagsdata till personliga filer och tvinga dem att spara arbetsfiler i OneDrive för företag** till **På** om du inte vill att användare ska kunna spara filer på sina datorer. 
    
8. Expand **Manage how users access Office files on devices** \> configure the settings how you would like. The **Manage how users access Office devices on mobile devices** is **Off** by default, but it is recommended that you turn it **On** and accept the default values. Mer information finns i [tillgängliga inställningar](#available-settings). 
    
    Du kan alltid använda länken **Återställ standardinställningar** för att återgå till standardinställningarna. 
    
9. Expandera **Återställ data på Windows-enheter**. Vi rekommenderar att du anger den till **På**.
    
    Innan du kan bläddra till certifikatet för dataåterställningsagenten måste du skapa ett. Anvisningar finns i [Create and verify an Encrypting File System (EFS) Data Recovery Agent (DRA) certificate](https://go.microsoft.com/fwlink/p/?linkid=853700) (skapa och verifiera ett certifikat för en dataåterställningsagent för kryptering av filsystem).
    
    Som standard krypteras arbetsfiler med en hemlig nyckel som lagras på enheten och som är kopplad till användarens profil. Endast användaren kan öppna och dekryptera filen. Men om en enhet försvinner eller en användare tas bort kan en fil fastna i ett krypterat tillstånd. Certifikatet för dataåterställningsagenten kan användas av en administratör för att dekryptera filen.
    
    ![Browse to Data Recovery Agent certificate.](media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. Expandera **Skydda ytterligare nätverks- och molnplatser** om du vill lägga till ytterligare domäner och/eller SharePoint Online-webbplatser för att säkerställa att filerna i samtliga angivna program skyddas. Om du behöver ange mer än ett objekt i ett fält anger du ett semikolon (;) mellan objekten. 
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. Bestäm sedan **vem som ska få de här inställningarna** Om du inte vill använda standardsäkerhetsgruppen **Alla användare** väljer du **Ändra** och anger de säkerhetsgrupper som ska få dessa inställningar \> **Välj**.
    
12. Välj **Lägg till** för att spara principen och tilldela den till enheter. 
    
## <a name="available-settings"></a>Tillgängliga inställningar

Följande inställningar är till för att hantera hur användare kan komma åt Office-arbetsfiler.
  
Mer information finns i [Hur mappar skyddsfunktioner i Microsoft 365 Business till Intune-inställningarna](map-protection-features-to-intune-settings.md).
  
|**Inställning**|**Beskrivning**|
|:-----|:-----|
|Kräv PIN-kod eller fingeravtryck för åtkomst till Office-program  <br/> |Om inställningen är **På** måste användare utöver användarnamn och lösenord, tillhandahålla annan autentisering innan de kan använda Office-programmen på sin mobila enhet.  <br/> |
|Återställ PIN-kod när inloggningen misslyckas så här många gånger  <br/> |Om du vill förhindra att obehöriga användare slumpmässigt gissar en PIN-kod. PIN-koden återställs efter det antal felaktiga försök som du anger.  <br/> |
|Kräv att användare loggar in igen efter att Office-appar har varit inaktiva  <br/> |Den här inställningen anger hur lång tid användare kan vara inaktiva innan de uppmanas att logga in igen.  <br/> |
   

