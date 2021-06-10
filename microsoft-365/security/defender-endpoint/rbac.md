---
title: Använd rollbaserad åtkomstkontroll för att bevilja finkornig åtkomst till Microsoft Defender Säkerhetscenter
description: Skapa roller och grupper i dina säkerhetsåtgärder för att bevilja åtkomst till portalen.
keywords: rbac, roll, baserad, åtkomst, kontroll, grupper, kontroll, nivå, aad
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
ms.openlocfilehash: d95163bd7caf6e05295fc35b3f9c2bf95230dc83
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071881"
---
# <a name="manage-portal-access-using-role-based-access-control"></a><span data-ttu-id="c78be-104">Hantera portalåtkomst med hjälp av rollbaserad åtkomstkontroll</span><span class="sxs-lookup"><span data-stu-id="c78be-104">Manage portal access using role-based access control</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c78be-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="c78be-105">**Applies to:**</span></span>
- <span data-ttu-id="c78be-106">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="c78be-106">Azure Active Directory</span></span>
- <span data-ttu-id="c78be-107">Office 365</span><span class="sxs-lookup"><span data-stu-id="c78be-107">Office 365</span></span>

> <span data-ttu-id="c78be-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="c78be-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c78be-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="c78be-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-rbac-abovefoldlink)

<span data-ttu-id="c78be-110">Med hjälp av rollbaserad åtkomstkontroll (RBAC) kan du skapa roller och grupper i säkerhetsoperationsteamet för att ge lämplig åtkomst till portalen.</span><span class="sxs-lookup"><span data-stu-id="c78be-110">Using role-based access control (RBAC), you can create roles and groups within your security operations team to grant appropriate access to the  portal.</span></span> <span data-ttu-id="c78be-111">Utifrån de roller och grupper du skapar har du full koll på vad användare med åtkomst till portalen kan se och göra.</span><span class="sxs-lookup"><span data-stu-id="c78be-111">Based on the roles and groups you create, you have fine-grained control over what users with access to the portal can see and do.</span></span> 

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bJ2a]

<span data-ttu-id="c78be-112">Stora geobaserade säkerhetsoperationer grupper använder vanligtvis en tierbaserad modell för att tilldela och auktorisera åtkomst till säkerhetsportaler.</span><span class="sxs-lookup"><span data-stu-id="c78be-112">Large geo-distributed security operations teams typically adopt a tier-based model to assign and authorize access to security portals.</span></span> <span data-ttu-id="c78be-113">Vanliga nivåer omfattar följande tre nivåer:</span><span class="sxs-lookup"><span data-stu-id="c78be-113">Typical tiers include the following three levels:</span></span>

<span data-ttu-id="c78be-114">Tier</span><span class="sxs-lookup"><span data-stu-id="c78be-114">Tier</span></span> | <span data-ttu-id="c78be-115">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="c78be-115">Description</span></span>
:---|:---
<span data-ttu-id="c78be-116">Nivå 1</span><span class="sxs-lookup"><span data-stu-id="c78be-116">Tier 1</span></span> | <span data-ttu-id="c78be-117">**Team/IT-team för lokala säkerhetsåtgärder**</span><span class="sxs-lookup"><span data-stu-id="c78be-117">**Local security operations team / IT team**</span></span> <br> <span data-ttu-id="c78be-118">Gruppen undersöker och undersöker vanligtvis aviseringar som finns inom deras geolokalisering och eskalerar till nivå 2 i fall där en aktiv åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="c78be-118">This team usually triages and investigates alerts contained within their geolocation and escalates to Tier 2 in cases where an active remediation is required.</span></span>
<span data-ttu-id="c78be-119">Nivå 2</span><span class="sxs-lookup"><span data-stu-id="c78be-119">Tier 2</span></span> | <span data-ttu-id="c78be-120">**Teamet för regionala säkerhetsåtgärder**</span><span class="sxs-lookup"><span data-stu-id="c78be-120">**Regional security operations team**</span></span> <br> <span data-ttu-id="c78be-121">Det här teamet kan se alla enheter i deras region och utföra åtgärder.</span><span class="sxs-lookup"><span data-stu-id="c78be-121">This team can see all the devices for their region and perform remediation actions.</span></span>
<span data-ttu-id="c78be-122">Nivå 3</span><span class="sxs-lookup"><span data-stu-id="c78be-122">Tier 3</span></span> | <span data-ttu-id="c78be-123">**Teamet för globala säkerhetsåtgärder**</span><span class="sxs-lookup"><span data-stu-id="c78be-123">**Global security operations team**</span></span> <br> <span data-ttu-id="c78be-124">Det här teamet består av säkerhetsexperter och har behörighet att se och utföra alla åtgärder från portalen.</span><span class="sxs-lookup"><span data-stu-id="c78be-124">This team consists of security experts and are authorized to see and perform all actions from the portal.</span></span>

<span data-ttu-id="c78be-125">Defender för Endpoint RBAC har utformats för att stödja din nivå- eller rollbaserade modell och ger dig detaljerad kontroll över vilka roller som kan se, enheter som de kan komma åt och åtgärder de kan vidta.</span><span class="sxs-lookup"><span data-stu-id="c78be-125">Defender for Endpoint RBAC is designed to support your tier- or role-based model of choice and gives you granular control over what roles can see, devices they can access, and actions they can take.</span></span> <span data-ttu-id="c78be-126">RBAC-ramverket är centrerat runt följande kontroller:</span><span class="sxs-lookup"><span data-stu-id="c78be-126">The RBAC framework is centered around the following controls:</span></span>

- <span data-ttu-id="c78be-127">**Kontrollera vem som kan vidta specifika åtgärder**</span><span class="sxs-lookup"><span data-stu-id="c78be-127">**Control who can take specific action**</span></span>
  - <span data-ttu-id="c78be-128">Skapa anpassade roller och kontrollera vad Defender för Slutpunkt-funktioner de kan komma åt med detaljerad information.</span><span class="sxs-lookup"><span data-stu-id="c78be-128">Create custom roles and control what Defender for Endpoint capabilities they can access with granularity.</span></span>
 
- <span data-ttu-id="c78be-129">**Styra vilka som kan se information i viss enhetsgrupp eller -grupp**</span><span class="sxs-lookup"><span data-stu-id="c78be-129">**Control who can see information on specific device group or groups**</span></span>
  - <span data-ttu-id="c78be-130">[Skapa enhetsgrupper](machine-groups.md) med specifika villkor, till exempel namn, taggar, domäner och andra, och tilldela sedan rollåtkomst till dem med hjälp av en viss användargrupp i Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="c78be-130">[Create device groups](machine-groups.md) by specific criteria such as names, tags, domains, and others, then grant role access to them using a specific  Azure Active Directory (Azure AD) user group.</span></span>

<span data-ttu-id="c78be-131">Om du vill implementera rollbaserad åtkomst måste du definiera administratörsroller, tilldela motsvarande behörigheter och tilldela Azure AD-användargrupper tilldelade till rollerna.</span><span class="sxs-lookup"><span data-stu-id="c78be-131">To implement role-based access, you'll need to define admin roles, assign corresponding permissions, and assign Azure AD user groups assigned to the roles.</span></span>


### <a name="before-you-begin"></a><span data-ttu-id="c78be-132">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="c78be-132">Before you begin</span></span>
<span data-ttu-id="c78be-133">Innan du använder RBAC är det viktigt att du förstår de roller som kan bevilja behörigheter och konsekvenserna av att aktivera RBAC.</span><span class="sxs-lookup"><span data-stu-id="c78be-133">Before using RBAC, it's important that you understand the roles that can grant permissions and the consequences of turning on RBAC.</span></span>


> [!WARNING]
> <span data-ttu-id="c78be-134">Innan du aktiverar funktionen är det viktigt att du har en global administratörsroll eller säkerhetsadministratörsroll i Azure AD och att du har dina Azure AD-grupper redo att minska risken med att bli utelåst från portalen.</span><span class="sxs-lookup"><span data-stu-id="c78be-134">Before enabling the feature, it's important that you have a Global Administrator role or Security Administrator role in Azure AD and that you have your Azure AD groups ready to reduce the risk of being locked out of the portal.</span></span> 

<span data-ttu-id="c78be-135">När du loggar in på Microsoft Defender Säkerhetscenter får du antingen fullständig åtkomst eller skrivskydd.</span><span class="sxs-lookup"><span data-stu-id="c78be-135">When you first log in to Microsoft Defender Security Center, you're granted either full access or read only access.</span></span> <span data-ttu-id="c78be-136">Fullständig åtkomst ges till användare med roller som säkerhetsadministratör eller global administratör i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c78be-136">Full access rights are granted to users with Security Administrator or Global Administrator roles in Azure AD.</span></span> <span data-ttu-id="c78be-137">Skrivskyddad åtkomst ges till användare med rollen Säkerhetsläsare i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c78be-137">Read only access is granted to users with a Security Reader role in Azure AD.</span></span> 

<span data-ttu-id="c78be-138">Någon med rollen Defender för global administratör för Slutpunkt har obegränsad åtkomst till alla enheter, oavsett vilken enhetsgruppsassociatorganisation och tilldelningar av Azure AD-användargrupper som ingår i dem.</span><span class="sxs-lookup"><span data-stu-id="c78be-138">Someone with a Defender for Endpoint Global administrator role has unrestricted access to all devices, regardless of their device group association and the Azure AD user groups assignments</span></span>

> [!WARNING]
> <span data-ttu-id="c78be-139">Till en början kan endast användare med global administratör eller säkerhetsadministratör för Azure AD skapa och tilldela roller i Microsoft Defender Säkerhetscenter och därför är det viktigt att ha rätt grupper redo i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c78be-139">Initially, only those with Azure AD Global Administrator or Security Administrator rights will be able to create and assign roles in Microsoft Defender Security Center, therefore, having the right groups ready in Azure AD is important.</span></span>
>
> <span data-ttu-id="c78be-140">**Om du slår på rollbaserad åtkomstkontroll förlorar användare med skrivskyddad behörighet (till exempel användare som tilldelats rollen Azure AD-säkerhetsläsare) åtkomsten tills de tilldelas till en roll.**</span><span class="sxs-lookup"><span data-stu-id="c78be-140">**Turning on role-based access control will cause users with read-only permissions (for example, users assigned to Azure AD Security reader role) to lose access until they are assigned to a role.**</span></span> 
>
><span data-ttu-id="c78be-141">Användare med administratörsbehörigheter tilldelas automatiskt den inbyggda standardrollen Defender för slutpunktens globala administratörsroll med fullständiga behörigheter.</span><span class="sxs-lookup"><span data-stu-id="c78be-141">Users with admin permissions are automatically assigned the default built-in Defender for Endpoint global administrator role with full permissions.</span></span> <span data-ttu-id="c78be-142">När du har valt att använda RBAC kan du tilldela ytterligare användare som inte är globala Azure AD- eller säkerhetsadministratörer till rollen Global administratör i Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="c78be-142">After opting in to use RBAC, you can assign additional users that are not Azure AD Global or Security Administrators to the Defender for Endpoint global administrator role.</span></span> 
>
> <span data-ttu-id="c78be-143">När du har valt att använda RBAC kan du inte återgå till de inledande rollerna som när du först loggade in på portalen.</span><span class="sxs-lookup"><span data-stu-id="c78be-143">After opting in to use RBAC, you cannot revert to the initial roles as when you first logged into the portal.</span></span> 



## <a name="related-topic"></a><span data-ttu-id="c78be-144">Relaterat ämne</span><span class="sxs-lookup"><span data-stu-id="c78be-144">Related topic</span></span>
- [<span data-ttu-id="c78be-145">Skapa och hantera enhetsgrupper i Microsoft Defender för Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="c78be-145">Create and manage device groups in Microsoft Defender for Endpoint</span></span>](machine-groups.md)
