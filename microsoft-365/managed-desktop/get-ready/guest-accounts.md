---
title: Förutsättningar för gäst konton
description: Konfigurations rikt linjer för gäst konton och hur du justerar dem
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: d8953e9f451daa02671a1e1544f2dfe6649ab1b3
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073246"
---
# <a name="prerequisites-for-guest-accounts"></a><span data-ttu-id="1aa21-104">Förutsättningar för gäst konton</span><span class="sxs-lookup"><span data-stu-id="1aa21-104">Prerequisites for guest accounts</span></span>

<span data-ttu-id="1aa21-105">Microsoft Managed Desktop kräver följande inställningar i din Azure AD-organisation för gäst konto åtkomst.</span><span class="sxs-lookup"><span data-stu-id="1aa21-105">Microsoft Managed Desktop requires the following settings in your Azure AD organization for guest account access.</span></span> <span data-ttu-id="1aa21-106">Du kan justera dessa inställningar på [Azure-portalen](https://portal.azure.com) under **externa identiteter/externa samarbete** :</span><span class="sxs-lookup"><span data-stu-id="1aa21-106">You can adjust these settings at the [Azure portal](https://portal.azure.com) under **External Identities / External collaboration** :</span></span>

-   <span data-ttu-id="1aa21-107">**Administratörer och användare i rollen inbjudna för gäst kan bjuda** in till **Ja**</span><span class="sxs-lookup"><span data-stu-id="1aa21-107">**Admins and users in the guest inviter role can invite** set to **Yes**</span></span>
-   <span data-ttu-id="1aa21-108">För **samarbets begränsningar** väljer du något av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="1aa21-108">For **Collaboration restrictions** , choose any of these options:</span></span>
    -   <span data-ttu-id="1aa21-109">Om du väljer **Tillåt att inbjudningar skickas till valfri domän (inklusive den mest omfattande)** behöver ingen annan konfiguration göras.</span><span class="sxs-lookup"><span data-stu-id="1aa21-109">If you select **Allow invitations to be sent to any domain (most inclusive)** , no other configuration required.</span></span>
    -   <span data-ttu-id="1aa21-110">Om du väljer **Neka för angivna domäner** kontrollerar du att Microsoft.com inte finns med i listan i mål domänerna.</span><span class="sxs-lookup"><span data-stu-id="1aa21-110">If you select **Deny invitations to the specified domains** , make sure that Microsoft.com isn’t listed in the target domains.</span></span>
    -   <span data-ttu-id="1aa21-111">Om du väljer **Tillåt endast inbjudningar till angivna domäner (mest restriktiv)** kontrollerar du att Microsoft.com *finns* med i listan i mål domänerna.</span><span class="sxs-lookup"><span data-stu-id="1aa21-111">If you select **Allow invitations only to the specified domains (most restrictive)** , make sure that Microsoft.com *is* listed in the target domains.</span></span>

<span data-ttu-id="1aa21-112">Om du ställer in begränsningar som interagerar med de här inställningarna ska du se till att exkludera Azure Active Directory **moderna arbets plats tjänst konton**.</span><span class="sxs-lookup"><span data-stu-id="1aa21-112">If you set restrictions that interact with these settings, make sure to exclude the Azure Active Directory **Modern Workplace Service Accounts**.</span></span> <span data-ttu-id="1aa21-113">Om du till exempel har en policy för villkorsstyrd åtkomst som hindrar gäst konton från att komma åt Intune-portalen utesluter du gruppen **moderna arbets plats tjänst konton** från den här principen.</span><span class="sxs-lookup"><span data-stu-id="1aa21-113">For example, if you have a conditional access policy that prevents guest accounts from accessing the Intune portal, exclude the **Modern Workplace Service Accounts** group from this policy.</span></span>

