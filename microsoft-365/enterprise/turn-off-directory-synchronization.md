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
# <a name="turn-off-directory-synchronization-for-microsoft-365"></a><span data-ttu-id="1aba5-103">Inaktivera profilsynkronisering för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1aba5-103">Turn off directory synchronization for Microsoft 365</span></span>
<span data-ttu-id="1aba5-104">Du kan använda PowerShell för att inaktivera Active Directory-synkronisering.</span><span class="sxs-lookup"><span data-stu-id="1aba5-104">You can use PowerShell to turn off directory synchronization.</span></span> <span data-ttu-id="1aba5-105">Men vi rekommenderar inte att du inaktiverar katalog-synkronisering som ett fel söknings steg.</span><span class="sxs-lookup"><span data-stu-id="1aba5-105">However, it is not recommended that you turn off directory synchronization as a troubleshooting step.</span></span> <span data-ttu-id="1aba5-106">Om du behöver hjälp med att felsöka Active Directory-synkroniseringen kan du läsa artikeln om att [åtgärda problem med Katalogduplicering för Microsoft 365](fix-problems-with-directory-synchronization.md) .</span><span class="sxs-lookup"><span data-stu-id="1aba5-106">If you need assistance with troubleshooting directory synchronization, see the [Fixing problems with directory synchronization for Microsoft 365](fix-problems-with-directory-synchronization.md) article.</span></span> 
  
<span data-ttu-id="1aba5-107">[Kontakta supporten](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) för företags produkter om det behövs.</span><span class="sxs-lookup"><span data-stu-id="1aba5-107">[Contact support](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) for business products if needed.</span></span>
  
## <a name="turn-off-directory-synchronization"></a><span data-ttu-id="1aba5-108">Inaktivera profilsynkronisering</span><span class="sxs-lookup"><span data-stu-id="1aba5-108">Turn off directory synchronization</span></span>  
<span data-ttu-id="1aba5-109">Så här inaktiverar du synkronisering av kataloger:</span><span class="sxs-lookup"><span data-stu-id="1aba5-109">To turn off Directory synchronization:</span></span>
  
1. <span data-ttu-id="1aba5-110">Installera först den program vara som krävs och Anslut till ditt Microsoft 365-abonnemang.</span><span class="sxs-lookup"><span data-stu-id="1aba5-110">First, install the required software and connect to your Microsoft 365 subscription.</span></span> <span data-ttu-id="1aba5-111">Anvisningar finns i [ansluta till Microsoft Azure Active Directory-modulen för Windows PowerShell](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="1aba5-111">For instructions, see [Connect with the Microsoft Azure Active Directory Module for Windows PowerShell](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
    
2. <span data-ttu-id="1aba5-112">Använd [set-MsolDirSyncEnabled](https://go.microsoft.com/fwlink/p/?LinkId=821939) för att inaktivera Active Directory-synkronisering:</span><span class="sxs-lookup"><span data-stu-id="1aba5-112">Use [Set-MsolDirSyncEnabled](https://go.microsoft.com/fwlink/p/?LinkId=821939) to disable directory synchronization:</span></span> 
    
  ```powershell
  Set-MsolDirSyncEnabled -EnableDirSync $false
  ```

>[!Note]
><span data-ttu-id="1aba5-113">Om du använder det här kommandot måste du vänta 72 timmar innan du kan aktivera katalog synkronisering.</span><span class="sxs-lookup"><span data-stu-id="1aba5-113">If you use this command, you must wait 72 hours before you can turn directory synchronization back on.</span></span>
>
 
