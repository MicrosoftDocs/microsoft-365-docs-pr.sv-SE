---
title: Konfigurera support för tjänstleverantör för hanterad säkerhet
description: Konfigurera MSSP-integreringen med Microsoft Defender för slutpunkten genom att vidta nödvändiga åtgärder
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
ms.openlocfilehash: 6786d423d20ec90c12d2ea712003acc787ed599d
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165255"
---
# <a name="configure-managed-security-service-provider-integration"></a><span data-ttu-id="e1216-104">Konfigurera integrering av tjänstleverantör för hanterad säkerhet</span><span class="sxs-lookup"><span data-stu-id="e1216-104">Configure managed security service provider integration</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e1216-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="e1216-105">**Applies to:**</span></span>
- [<span data-ttu-id="e1216-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="e1216-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e1216-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e1216-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="e1216-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="e1216-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e1216-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="e1216-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)
 
[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="e1216-110">Du måste vidta följande konfigurationssteg för att aktivera mssp-integrering (Managed Security Service Provider).</span><span class="sxs-lookup"><span data-stu-id="e1216-110">You'll need to take the following configuration steps to enable the managed security service provider (MSSP) integration.</span></span>

>[!NOTE]
><span data-ttu-id="e1216-111">Följande termer används i den här artikeln för att skilja mellan tjänsteleverantören och tjänstekonsumenten:</span><span class="sxs-lookup"><span data-stu-id="e1216-111">The following terms are used in this article to distinguish between the service provider and service consumer:</span></span>
> - <span data-ttu-id="e1216-112">MSSP: Säkerhetsorganisationer som erbjuder att övervaka och hantera säkerhetsenheter för en organisation.</span><span class="sxs-lookup"><span data-stu-id="e1216-112">MSSPs: Security organizations that offer to monitor and manage security devices for an organization.</span></span>
> - <span data-ttu-id="e1216-113">MSSP-kunder: Organisationer som engagerar sig i mssp-tjänster.</span><span class="sxs-lookup"><span data-stu-id="e1216-113">MSSP customers: Organizations that engage the services of MSSPs.</span></span>

<span data-ttu-id="e1216-114">Integreringen gör att MSSP kan utföra följande åtgärder:</span><span class="sxs-lookup"><span data-stu-id="e1216-114">The integration will allow MSSPs to take the following actions:</span></span>

- <span data-ttu-id="e1216-115">Få åtkomst till MSSP-kundens Microsoft Defender Säkerhetscenter-portal</span><span class="sxs-lookup"><span data-stu-id="e1216-115">Get access to MSSP customer's Microsoft Defender Security Center portal</span></span>
- <span data-ttu-id="e1216-116">Få e-postaviseringar och</span><span class="sxs-lookup"><span data-stu-id="e1216-116">Get email notifications, and</span></span> 
- <span data-ttu-id="e1216-117">Hämta aviseringar via säkerhetsinformation och händelsehanteringsverktyg (SIEM)</span><span class="sxs-lookup"><span data-stu-id="e1216-117">Fetch alerts through security information and event management (SIEM) tools</span></span>

<span data-ttu-id="e1216-118">Innan MSSP:er kan utföra de här åtgärderna måste MSSP-kunden bevilja åtkomst till sin Defender för Slutpunktsklientorganisation så att MSSP kan komma åt portalen.</span><span class="sxs-lookup"><span data-stu-id="e1216-118">Before MSSPs can take these actions, the MSSP customer will need to grant access to their Defender for Endpoint tenant so that the MSSP can access the portal.</span></span> 
 

<span data-ttu-id="e1216-119">Normalt sett tar MSSP-kunder de inledande konfigurationsstegen för att ge MSSP-åtkomst till sin Windows Defender Security Central-klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="e1216-119">Typically, MSSP customers take the initial configuration steps to grant MSSPs access to their Windows Defender Security Central tenant.</span></span> <span data-ttu-id="e1216-120">När åtkomst har beviljats kan andra konfigurationssteg utföras av antingen kunden för MSSP eller mssp.</span><span class="sxs-lookup"><span data-stu-id="e1216-120">After access is granted, other configuration steps can be done by either the MSSP customer or the MSSP.</span></span>


<span data-ttu-id="e1216-121">I allmänhet måste du vidta följande konfigurationssteg:</span><span class="sxs-lookup"><span data-stu-id="e1216-121">In general, the following configuration steps need to be taken:</span></span>


- <span data-ttu-id="e1216-122">**Bevilja MSSP-åtkomst till Microsoft Defender Säkerhetscenter**</span><span class="sxs-lookup"><span data-stu-id="e1216-122">**Grant the MSSP access to Microsoft Defender Security Center**</span></span> <br>
<span data-ttu-id="e1216-123">Den här åtgärden måste utföras av MSSP-kunden.</span><span class="sxs-lookup"><span data-stu-id="e1216-123">This action needs to be done by the MSSP customer.</span></span> <span data-ttu-id="e1216-124">Det ger MSSP-åtkomst till MSSP-kundens Defender för slutpunktsklientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="e1216-124">It grants the MSSP access to the MSSP customer's Defender for Endpoint tenant.</span></span>
 

- <span data-ttu-id="e1216-125">**Konfigurera aviseringsaviseringar som skickas till MSSP:er**</span><span class="sxs-lookup"><span data-stu-id="e1216-125">**Configure alert notifications sent to MSSPs**</span></span> <br>
<span data-ttu-id="e1216-126">Den här åtgärden kan vidtas av antingen MSSP-kunden eller MSSP.</span><span class="sxs-lookup"><span data-stu-id="e1216-126">This action can be taken by either the MSSP customer or MSSP.</span></span> <span data-ttu-id="e1216-127">Då får MSSP:er veta vilka aviseringar de behöver ta itu med för MSSP-kunden.</span><span class="sxs-lookup"><span data-stu-id="e1216-127">This lets the MSSPs know what alerts they need to address for the MSSP customer.</span></span>

- <span data-ttu-id="e1216-128">**Hämta aviseringar från MSSP-kundens klientorganisation till SIEM-systemet**</span><span class="sxs-lookup"><span data-stu-id="e1216-128">**Fetch alerts from MSSP customer's tenant into SIEM system**</span></span> <br> <span data-ttu-id="e1216-129">Den här åtgärden vidtas av MSSP.</span><span class="sxs-lookup"><span data-stu-id="e1216-129">This action is taken by the MSSP.</span></span> <span data-ttu-id="e1216-130">Med den kan MSSP hämta aviseringar i SIEM-verktyg.</span><span class="sxs-lookup"><span data-stu-id="e1216-130">It allows MSSPs to fetch alerts in SIEM tools.</span></span>

- <span data-ttu-id="e1216-131">**Hämta aviseringar från MSSP-klientens klientorganisation med API:er**</span><span class="sxs-lookup"><span data-stu-id="e1216-131">**Fetch alerts from MSSP customer's tenant using APIs**</span></span> <br>
<span data-ttu-id="e1216-132">Den här åtgärden vidtas av MSSP.</span><span class="sxs-lookup"><span data-stu-id="e1216-132">This action is taken by the MSSP.</span></span> <span data-ttu-id="e1216-133">Det gör att MSSP kan hämta aviseringar med API:er.</span><span class="sxs-lookup"><span data-stu-id="e1216-133">It allows MSSPs to fetch alerts using APIs.</span></span>

## <a name="multi-tenant-access-for-mssps"></a><span data-ttu-id="e1216-134">Åtkomst med flera klientorganisationen för MSSP:er</span><span class="sxs-lookup"><span data-stu-id="e1216-134">Multi-tenant access for MSSPs</span></span>
<span data-ttu-id="e1216-135">Information om hur du implementerar en delegerad åtkomst med flera innehavare finns i Åtkomst för flera innehavare [för tjänstleverantörer av hanterade säkerhetstjänster.](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/multi-tenant-access-for-managed-security-service-providers/ba-p/1533440)</span><span class="sxs-lookup"><span data-stu-id="e1216-135">For information on how to implement a multi-tenant delegated access, see [Multi-tenant access for Managed Security Service Providers](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/multi-tenant-access-for-managed-security-service-providers/ba-p/1533440).</span></span>



## <a name="related-topics"></a><span data-ttu-id="e1216-136">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="e1216-136">Related topics</span></span>
- [<span data-ttu-id="e1216-137">Bevilja MSSP-åtkomst till portalen</span><span class="sxs-lookup"><span data-stu-id="e1216-137">Grant MSSP access to the portal</span></span>](grant-mssp-access.md)
- [<span data-ttu-id="e1216-138">Få åtkomst till kundportalen för MSSP</span><span class="sxs-lookup"><span data-stu-id="e1216-138">Access the MSSP customer portal</span></span>](access-mssp-portal.md)
- [<span data-ttu-id="e1216-139">Konfigurera aviseringsmeddelanden</span><span class="sxs-lookup"><span data-stu-id="e1216-139">Configure alert notifications</span></span>](configure-mssp-notifications.md)
- [<span data-ttu-id="e1216-140">Hämta aviseringar från kundklientorganisationen</span><span class="sxs-lookup"><span data-stu-id="e1216-140">Fetch alerts from customer tenant</span></span>](fetch-alerts-mssp.md)

