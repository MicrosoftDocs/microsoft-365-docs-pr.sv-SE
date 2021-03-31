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
# <a name="turn-off-directory-synchronization-for-microsoft-365"></a><span data-ttu-id="c7889-103">Inaktivera katalogsynkronisering för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c7889-103">Turn off directory synchronization for Microsoft 365</span></span>
<span data-ttu-id="c7889-104">Du kan använda PowerShell för att inaktivera katalogsynkronisering och konvertera synkroniserade användare till endast molnet.</span><span class="sxs-lookup"><span data-stu-id="c7889-104">You can use PowerShell to turn off directory synchronization and convert your synchronized users to cloud-only.</span></span> <span data-ttu-id="c7889-105">Vi rekommenderar dock inte att du inaktiverar katalogsynkronisering som ett felsökningssteg.</span><span class="sxs-lookup"><span data-stu-id="c7889-105">However, it is not recommended that you turn off directory synchronization as a troubleshooting step.</span></span> <span data-ttu-id="c7889-106">Om du behöver hjälp med att felsöka katalogsynkroniseringen kan du läsa artikeln Åtgärda problem med [katalogsynkronisering för Microsoft 365.](fix-problems-with-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="c7889-106">If you need assistance with troubleshooting directory synchronization, see the [Fixing problems with directory synchronization for Microsoft 365](fix-problems-with-directory-synchronization.md) article.</span></span> 
  
<span data-ttu-id="c7889-107">[Kontakta supporten](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) för företagsprodukter om det behövs.</span><span class="sxs-lookup"><span data-stu-id="c7889-107">[Contact support](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) for business products if needed.</span></span>
  
## <a name="turn-off-directory-synchronization"></a><span data-ttu-id="c7889-108">Inaktivera katalogsynkronisering</span><span class="sxs-lookup"><span data-stu-id="c7889-108">Turn off directory synchronization</span></span>  
<span data-ttu-id="c7889-109">Så här inaktiverar du katalogsynkronisering:</span><span class="sxs-lookup"><span data-stu-id="c7889-109">To turn off Directory synchronization:</span></span>
  
1. <span data-ttu-id="c7889-110">Först installerar du programvaran som krävs och ansluter till din Microsoft 365-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="c7889-110">First, install the required software and connect to your Microsoft 365 subscription.</span></span> <span data-ttu-id="c7889-111">Instruktioner finns i [Ansluta till Microsoft Azure Active Directory-modulen för Windows PowerShell.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="c7889-111">For instructions, see [Connect with the Microsoft Azure Active Directory Module for Windows PowerShell](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
    
2. <span data-ttu-id="c7889-112">Använd [Set-MsolDirSyncEnabled för att](/previous-versions/azure/dn194097(v=azure.100)) inaktivera katalogsynkronisering:</span><span class="sxs-lookup"><span data-stu-id="c7889-112">Use [Set-MsolDirSyncEnabled](/previous-versions/azure/dn194097(v=azure.100)) to disable directory synchronization:</span></span> 
    
  ```powershell
  Set-MsolDirSyncEnabled -EnableDirSync $false
  ```

>[!Note]
><span data-ttu-id="c7889-113">Om du använder det här kommandot måste du vänta 72 timmar innan du kan aktivera katalogsynkroniseringen igen.</span><span class="sxs-lookup"><span data-stu-id="c7889-113">If you use this command, you must wait 72 hours before you can turn directory synchronization back on.</span></span>
>
