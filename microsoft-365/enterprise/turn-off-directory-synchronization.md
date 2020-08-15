---
title: Inaktivera profilsynkronisering för Microsoft 365
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
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
ms.assetid: ee5f861e-bd48-4267-83d1-a4ead4b4a00d
description: I den här artikeln hittar du information om hur du använder PowerShell för att inaktivera profilsynkronisering för Microsoft 365.
ms.openlocfilehash: 0bd8591f91dcf20cb1061b3cd93f69511027bab1
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694290"
---
# <a name="turn-off-directory-synchronization-for-microsoft-365"></a>Inaktivera profilsynkronisering för Microsoft 365
Du kan använda PowerShell för att inaktivera Active Directory-synkronisering. Men vi rekommenderar inte att du inaktiverar katalog-synkronisering som ett fel söknings steg. Om du behöver hjälp med att felsöka Active Directory-synkroniseringen kan du läsa artikeln om att [åtgärda problem med Katalogduplicering för Microsoft 365](fix-problems-with-directory-synchronization.md) . 
  
[Kontakta supporten](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) för företags produkter om det behövs.
  
## <a name="turn-off-directory-synchronization"></a>Inaktivera profilsynkronisering  
Så här inaktiverar du synkronisering av kataloger:
  
1. Installera först den program vara som krävs och Anslut till ditt Microsoft 365-abonnemang. Anvisningar finns i [ansluta till Microsoft Azure Active Directory-modulen för Windows PowerShell](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).
    
2. Använd [set-MsolDirSyncEnabled](https://go.microsoft.com/fwlink/p/?LinkId=821939) för att inaktivera Active Directory-synkronisering: 
    
  ```powershell
  Set-MsolDirSyncEnabled -EnableDirSync $false
  ```

>[!Note]
>Om du använder det här kommandot måste du vänta 72 timmar innan du kan aktivera katalog synkronisering.
>
 
