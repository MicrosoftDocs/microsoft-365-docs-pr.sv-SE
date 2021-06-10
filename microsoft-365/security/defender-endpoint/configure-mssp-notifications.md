---
title: Konfigurera aviseringsaviseringar som skickas till MSSP:er
description: Konfigurera aviseringsaviseringar som skickas till MSSP:er
keywords: hanterad säkerhetstjänstleverantör, mssp, konfigurera, integrering
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 67f7081e72b5ecc8bdb077f0537cf0cf92df38b9
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166059"
---
# <a name="configure-alert-notifications-that-are-sent-to-mssps"></a><span data-ttu-id="0fd34-104">Konfigurera aviseringsaviseringar som skickas till MSSP:er</span><span class="sxs-lookup"><span data-stu-id="0fd34-104">Configure alert notifications that are sent to MSSPs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0fd34-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="0fd34-105">**Applies to:**</span></span>
- [<span data-ttu-id="0fd34-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="0fd34-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0fd34-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0fd34-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="0fd34-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="0fd34-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="0fd34-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="0fd34-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)


>[!NOTE]
><span data-ttu-id="0fd34-110">Det här steget kan utföras av antingen MSSP-kunden eller MSSP.</span><span class="sxs-lookup"><span data-stu-id="0fd34-110">This step can be done by either the MSSP customer or MSSP.</span></span> <span data-ttu-id="0fd34-111">MSSP måste ges rätt behörighet för att konfigurera detta för MSSP-kundens räkning.</span><span class="sxs-lookup"><span data-stu-id="0fd34-111">MSSPs must be granted the appropriate permissions to configure this on behalf of the MSSP customer.</span></span>

<span data-ttu-id="0fd34-112">När åtkomst till portalen har beviljats kan aviseringsregler skapas så att e-postmeddelanden skickas till MSSP när aviseringar som är associerade med klientorganisationen skapas och anger att villkoren uppfylls.</span><span class="sxs-lookup"><span data-stu-id="0fd34-112">After access the portal is granted, alert notification rules can to be created so that emails are sent to MSSPs when alerts associated with the tenant are created and set conditions are met.</span></span>

 
<span data-ttu-id="0fd34-113">Mer information finns i [Skapa regler för aviseringsmeddelanden.](configure-email-notifications.md#create-rules-for-alert-notifications)</span><span class="sxs-lookup"><span data-stu-id="0fd34-113">For more information, see [Create rules for alert notifications](configure-email-notifications.md#create-rules-for-alert-notifications).</span></span>
 

<span data-ttu-id="0fd34-114">Dessa kryssrutor måste vara markerade:</span><span class="sxs-lookup"><span data-stu-id="0fd34-114">These check boxes must be checked:</span></span>
- <span data-ttu-id="0fd34-115">**Inkludera organisationsnamn** – kundnamnet läggs till i e-postaviseringar</span><span class="sxs-lookup"><span data-stu-id="0fd34-115">**Include organization name** - The customer name will be added to email notifications</span></span>
- <span data-ttu-id="0fd34-116">**Inkludera klientspecifik portallänk** – URL för aviseringslänk har klientspecifik parameter (tid=target_tenant_id) som ger direkt åtkomst till målklientorganisationens portal</span><span class="sxs-lookup"><span data-stu-id="0fd34-116">**Include tenant-specific portal link** - Alert link URL will have tenant specific parameter (tid=target_tenant_id) that allows direct access to target tenant portal</span></span>


## <a name="related-topics"></a><span data-ttu-id="0fd34-117">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="0fd34-117">Related topics</span></span>
- [<span data-ttu-id="0fd34-118">Bevilja MSSP åtkomst till portalen</span><span class="sxs-lookup"><span data-stu-id="0fd34-118">Grant MSSP access to the portal</span></span>](grant-mssp-access.md)
- [<span data-ttu-id="0fd34-119">Få åtkomst till MSSP-kundportalen</span><span class="sxs-lookup"><span data-stu-id="0fd34-119">Access the MSSP customer portal</span></span>](access-mssp-portal.md)
- [<span data-ttu-id="0fd34-120">Hämta varningar från kundens klientorganisation</span><span class="sxs-lookup"><span data-stu-id="0fd34-120">Fetch alerts from customer tenant</span></span>](fetch-alerts-mssp.md)
