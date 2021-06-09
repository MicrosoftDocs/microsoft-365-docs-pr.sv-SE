---
title: Inaktivera katalogsynkronisering för Microsoft 365
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
description: I den här artikeln hittar du information om hur du använder PowerShell för att inaktivera katalogsynkronisering för Microsoft 365.
ms.openlocfilehash: 26f8729078ea06657ced565db780b57c7e537aa4
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445714"
---
# <a name="turn-off-directory-synchronization-for-microsoft-365"></a>Inaktivera katalogsynkronisering för Microsoft 365
Du kan använda PowerShell för att inaktivera katalogsynkronisering och konvertera synkroniserade användare till endast molnet. Vi rekommenderar dock inte att du inaktiverar katalogsynkronisering som ett felsökningssteg. Om du behöver hjälp med att felsöka katalogsynkroniseringen kan [du läsa artikeln Åtgärda problem med Microsoft 365](fix-problems-with-directory-synchronization.md) katalogsynkronisering. 
  
[Kontakta supporten](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) för företagsprodukter om det behövs.
  
## <a name="turn-off-directory-synchronization"></a>Inaktivera katalogsynkronisering  
Så här inaktiverar du katalogsynkronisering:
  
1. Först installerar du programvaran som krävs och ansluter till din Microsoft 365 prenumeration. Instruktioner finns i [Anslut med modulen Microsoft Azure Active Directory för Windows PowerShell](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).
    
2. Använd [Set-MsolDirSyncEnabled för att](/previous-versions/azure/dn194097(v=azure.100)) inaktivera katalogsynkronisering: 
    
  ```powershell
  Set-MsolDirSyncEnabled -EnableDirSync $false
  ```

>[!Note]
>Om du använder det här kommandot måste du vänta 72 timmar innan du kan aktivera katalogsynkroniseringen igen.
>
