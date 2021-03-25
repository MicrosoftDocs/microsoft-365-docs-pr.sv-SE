---
title: Få åtkomst till Microsoft Defender Säkerhetscenter-kundportalen för MICROSOFT Defender
description: Få åtkomst till Microsoft Defender Säkerhetscenter-kundportalen för MICROSOFT Defender
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
ms.openlocfilehash: 97122decede91e8b4f059b3b66999ac12b300172
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164863"
---
# <a name="access-the-microsoft-defender-security-center-mssp-customer-portal"></a><span data-ttu-id="d0896-104">Få åtkomst till Microsoft Defender Säkerhetscenter-kundportalen för MICROSOFT Defender</span><span class="sxs-lookup"><span data-stu-id="d0896-104">Access the Microsoft Defender Security Center MSSP customer portal</span></span>

<span data-ttu-id="d0896-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="d0896-105">**Applies to:**</span></span>
- [<span data-ttu-id="d0896-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="d0896-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d0896-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d0896-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d0896-108">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="d0896-108">**Applies to:**</span></span>

- [<span data-ttu-id="d0896-109">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="d0896-109">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="d0896-110">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="d0896-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d0896-111">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="d0896-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)




>[!NOTE] 
><span data-ttu-id="d0896-112">Dessa steg riktar sig till MSSP.</span><span class="sxs-lookup"><span data-stu-id="d0896-112">These set of steps are directed towards the MSSP.</span></span> 

<span data-ttu-id="d0896-113">Som standard har MSSP-kunder åtkomst till sin Microsoft Defender Säkerhetscenter-klientorganisation via följande URL: `https://securitycenter.windows.com` .</span><span class="sxs-lookup"><span data-stu-id="d0896-113">By default, MSSP customers access their Microsoft Defender Security Center tenant through the following URL: `https://securitycenter.windows.com`.</span></span>
 

<span data-ttu-id="d0896-114">MssP:er måste emellertid använda en klientspecifik URL i följande format: för åtkomst till  `https://securitycenter.windows.com?tid=customer_tenant_id` mssp-kundportalen.</span><span class="sxs-lookup"><span data-stu-id="d0896-114">MSSPs however, will need to use a tenant-specific URL in the following format:  `https://securitycenter.windows.com?tid=customer_tenant_id` to access the MSSP customer portal.</span></span> 

<span data-ttu-id="d0896-115">I allmänhet måste MSSP:er läggas till i var och en av de Azure AD för MSSP-kunder som de tänker hantera.</span><span class="sxs-lookup"><span data-stu-id="d0896-115">In general, MSSPs will need to be added to each of the MSSP customer's Azure AD that they intend to manage.</span></span>


<span data-ttu-id="d0896-116">Använd följande steg för att hämta klientorganisations-ID för MSSP-kunder och använd sedan ID:t för att få åtkomst till den klientspecifika URL:en:</span><span class="sxs-lookup"><span data-stu-id="d0896-116">Use the following steps to obtain the MSSP customer tenant ID and then use the ID to access the tenant-specific URL:</span></span>

1. <span data-ttu-id="d0896-117">Som MSSP loggar du in på Azure AD med dina autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="d0896-117">As an MSSP, login to Azure AD with your credentials.</span></span> 

2. <span data-ttu-id="d0896-118">Växla katalog till MSSP-kundens klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="d0896-118">Switch directory to the MSSP customer's tenant.</span></span>

3.  <span data-ttu-id="d0896-119">Välj **Azure Active Directory > Egenskaper**.</span><span class="sxs-lookup"><span data-stu-id="d0896-119">Select **Azure Active Directory > Properties**.</span></span> <span data-ttu-id="d0896-120">Klientorganisations-ID finns i fältet Katalog-ID.</span><span class="sxs-lookup"><span data-stu-id="d0896-120">You'll find the tenant ID in the Directory ID field.</span></span> 

4. <span data-ttu-id="d0896-121">Få åtkomst till MSSP-kundportalen genom att `customer_tenant_id` ersätta värdet i följande URL: `https://securitycenter.windows.com?tid=customer_tenant_id` .</span><span class="sxs-lookup"><span data-stu-id="d0896-121">Access the MSSP customer portal by replacing the `customer_tenant_id` value in the following URL: `https://securitycenter.windows.com?tid=customer_tenant_id`.</span></span>


## <a name="related-topics"></a><span data-ttu-id="d0896-122">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="d0896-122">Related topics</span></span>
- [<span data-ttu-id="d0896-123">Bevilja MSSP-åtkomst till portalen</span><span class="sxs-lookup"><span data-stu-id="d0896-123">Grant MSSP access to the portal</span></span>](grant-mssp-access.md)
- [<span data-ttu-id="d0896-124">Konfigurera aviseringsmeddelanden</span><span class="sxs-lookup"><span data-stu-id="d0896-124">Configure alert notifications</span></span>](configure-mssp-notifications.md)
- [<span data-ttu-id="d0896-125">Hämta aviseringar från kundklientorganisationen</span><span class="sxs-lookup"><span data-stu-id="d0896-125">Fetch alerts from customer tenant</span></span>](fetch-alerts-mssp.md)