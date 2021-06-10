---
title: Aktivera villkorsstyrd åtkomst för att bättre skydda användare, enheter och data
description: Aktivera villkorsstyrd åtkomst för att förhindra att program körs om en enhet anses vara riskabel och ett program bedöms vara icke-kompatibelt.
keywords: villkorlig åtkomst, blockera program, säkerhetsnivå, intune,
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
ms.openlocfilehash: 21d17ee789a4757df10e99514f23cfc26b186405
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166203"
---
# <a name="enable-conditional-access-to-better-protect-users-devices-and-data"></a><span data-ttu-id="be71d-104">Aktivera villkorsstyrd åtkomst för att bättre skydda användare, enheter och data</span><span class="sxs-lookup"><span data-stu-id="be71d-104">Enable Conditional Access to better protect users, devices, and data</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="be71d-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="be71d-105">**Applies to:**</span></span>
- [<span data-ttu-id="be71d-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="be71d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="be71d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="be71d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="be71d-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="be71d-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="be71d-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="be71d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-conditionalaccess-abovefoldlink)

<span data-ttu-id="be71d-110">Villkorsstyrd åtkomst är en funktion som hjälper dig att bättre skydda dina användare och företagsinformation genom att se till att endast säkra enheter har åtkomst till program.</span><span class="sxs-lookup"><span data-stu-id="be71d-110">Conditional Access is a capability that helps you better protect your users and enterprise information by making sure that only secure devices have access to applications.</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4byD1]

<span data-ttu-id="be71d-111">Med villkorsstyrd åtkomst kan du styra åtkomsten till företagsinformation utifrån enhetens risknivå.</span><span class="sxs-lookup"><span data-stu-id="be71d-111">With Conditional Access, you can control access to enterprise information based on the risk level of a device.</span></span> <span data-ttu-id="be71d-112">Det här håller betrodda användare på betrodda enheter med hjälp av betrodda program.</span><span class="sxs-lookup"><span data-stu-id="be71d-112">This helps keep trusted users on trusted devices using trusted applications.</span></span>

<span data-ttu-id="be71d-113">Du kan definiera säkerhetsvillkor för vilka enheter och program som kan köra och komma åt information från nätverket genom att tillämpa principer för att stoppa program från att köras tills en enhet återgår till ett kompatibelt tillstånd.</span><span class="sxs-lookup"><span data-stu-id="be71d-113">You can define security conditions under which devices and applications can run and access information from your network by enforcing policies to stop applications from running until a device returns to a compliant state.</span></span> 

<span data-ttu-id="be71d-114">Implementeringen av villkorsstyrd åtkomst i Defender för Endpoint baseras på efterlevnadsprinciper för enheter Microsoft Intune (Intune) och villkorsstyrda åtkomstprinciper för Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="be71d-114">The implementation of Conditional Access in Defender for Endpoint is based on Microsoft Intune (Intune) device compliance policies and Azure Active Directory (Azure AD) conditional access policies.</span></span> 

<span data-ttu-id="be71d-115">Efterlevnadsprincipen används med villkorsstyrd åtkomst för att endast enheter som uppfyller en eller flera policyregler för enhetsefterlevnad ska kunna komma åt program.</span><span class="sxs-lookup"><span data-stu-id="be71d-115">The compliance policy is used with Conditional Access to allow only devices that fulfill one or more device compliance policy rules to access applications.</span></span> 

## <a name="understand-the-conditional-access-flow"></a><span data-ttu-id="be71d-116">Förstå flödet för villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="be71d-116">Understand the Conditional Access flow</span></span>
<span data-ttu-id="be71d-117">Villkorsstyrd åtkomst sätts på plats så att åtkomst till känsligt innehåll blockeras när ett hot visas på en enhet tills hoten har åtgärdats.</span><span class="sxs-lookup"><span data-stu-id="be71d-117">Conditional Access is put in place so that when a threat is seen on a device, access to sensitive content is blocked until the threat is remediated.</span></span> 

<span data-ttu-id="be71d-118">Flödet börjar med enheter som ser ut att ha en låg, medelstor eller hög risk.</span><span class="sxs-lookup"><span data-stu-id="be71d-118">The flow begins with devices being seen to have a low, medium, or high risk.</span></span> <span data-ttu-id="be71d-119">Dessa riskbestämningar skickas sedan till Intune.</span><span class="sxs-lookup"><span data-stu-id="be71d-119">These risk determinations are then sent to Intune.</span></span> 

<span data-ttu-id="be71d-120">Beroende på hur du konfigurerar principer i Intune kan villkorsstyrd åtkomst konfigureras så att principen tillämpas när vissa villkor uppfylls.</span><span class="sxs-lookup"><span data-stu-id="be71d-120">Depending on how you configure policies in Intune, Conditional Access can be set up so that when certain conditions are met, the policy is applied.</span></span>

<span data-ttu-id="be71d-121">Du kan till exempel konfigurera Intune att använda villkorsstyrd åtkomst på enheter som innebär hög risk.</span><span class="sxs-lookup"><span data-stu-id="be71d-121">For example, you can configure Intune to apply Conditional Access on devices that have a high risk.</span></span>

<span data-ttu-id="be71d-122">I Intune används en princip för enhetsefterlevnad tillsammans med villkorlig åtkomst i Azure AD för att blockera åtkomst till program.</span><span class="sxs-lookup"><span data-stu-id="be71d-122">In Intune, a device compliance policy is used in conjunction with Azure AD Conditional Access to block access to applications.</span></span> <span data-ttu-id="be71d-123">Parallellt startas en automatiserad undersökning och åtgärdsprocess.</span><span class="sxs-lookup"><span data-stu-id="be71d-123">In parallel, an automated investigation and remediation process is launched.</span></span>

 <span data-ttu-id="be71d-124">En användare kan fortfarande använda enheten medan automatisk undersökning och åtgärd pågår, men åtkomsten till företagsdata blockeras tills hoten har åtgärdats helt.</span><span class="sxs-lookup"><span data-stu-id="be71d-124">A user can still use the device while the automated investigation and remediation is taking place, but access to enterprise data is blocked until the threat is fully remediated.</span></span> 

<span data-ttu-id="be71d-125">Om du vill lösa risken som finns på en enhet måste du returnera enheten till ett kompatibelt tillstånd.</span><span class="sxs-lookup"><span data-stu-id="be71d-125">To resolve the risk found on a device, you'll need to return the device to a compliant state.</span></span> <span data-ttu-id="be71d-126">En enhet återgår till ett kompatibelt tillstånd när den saknar risk.</span><span class="sxs-lookup"><span data-stu-id="be71d-126">A device returns to a compliant state when there is no risk seen on it.</span></span> 

<span data-ttu-id="be71d-127">Det finns tre sätt att hantera en risk:</span><span class="sxs-lookup"><span data-stu-id="be71d-127">There are three ways to address a risk:</span></span>
1. <span data-ttu-id="be71d-128">Använd manuell eller automatiserad åtgärd.</span><span class="sxs-lookup"><span data-stu-id="be71d-128">Use Manual or automated remediation.</span></span>
2. <span data-ttu-id="be71d-129">Lös aktiva aviseringar på enheten.</span><span class="sxs-lookup"><span data-stu-id="be71d-129">Resolve active alerts on the device.</span></span> <span data-ttu-id="be71d-130">Då tas risken bort från enheten.</span><span class="sxs-lookup"><span data-stu-id="be71d-130">This will remove the risk from the device.</span></span>
3. <span data-ttu-id="be71d-131">Du kan ta bort enheten från de aktiva principerna och därför kommer villkorsstyrd åtkomst inte att tillämpas på enheten.</span><span class="sxs-lookup"><span data-stu-id="be71d-131">You can remove the device from the active policies and consequently, Conditional Access will not be applied on the device.</span></span> 

<span data-ttu-id="be71d-132">Manuell åtgärd kräver en sekops-administratör för att undersöka en avisering och ta itu med risken som visas på enheten.</span><span class="sxs-lookup"><span data-stu-id="be71d-132">Manual remediation requires a secops admin to investigate an alert and address the risk seen on the device.</span></span> <span data-ttu-id="be71d-133">Den automatiska korrigeringen konfigureras via konfigurationsinställningarna i följande avsnitt, [Konfigurera villkorsstyrd åtkomst.](configure-conditional-access.md)</span><span class="sxs-lookup"><span data-stu-id="be71d-133">The automated remediation is configured through configuration settings provided in the following section, [Configure Conditional Access](configure-conditional-access.md).</span></span>

<span data-ttu-id="be71d-134">När risken tas bort via manuell eller automatisk åtgärd återgår enheten till en kompatibel status och åtkomst till program beviljas.</span><span class="sxs-lookup"><span data-stu-id="be71d-134">When the risk is removed either through manual or automated remediation, the device returns to a compliant state and access to applications is granted.</span></span>

<span data-ttu-id="be71d-135">I följande exempelsekvens av händelser förklaras villkorsstyrd åtkomst i praktiken:</span><span class="sxs-lookup"><span data-stu-id="be71d-135">The following example sequence of events explains Conditional Access in action:</span></span>

1. <span data-ttu-id="be71d-136">En användare öppnar en skadlig fil och Defender för Endpoint flaggar enheten som högrisk.</span><span class="sxs-lookup"><span data-stu-id="be71d-136">A user opens a malicious file and Defender for Endpoint flags the device as high risk.</span></span>
2. <span data-ttu-id="be71d-137">Utvärderingen med hög risk överförs till Intune.</span><span class="sxs-lookup"><span data-stu-id="be71d-137">The high risk assessment is passed along to Intune.</span></span> <span data-ttu-id="be71d-138">Parallellt initieras en automatiserad undersökning för att åtgärda det identifierade hotet.</span><span class="sxs-lookup"><span data-stu-id="be71d-138">In parallel, an automated investigation is initiated to remediate the identified threat.</span></span> <span data-ttu-id="be71d-139">En manuell åtgärd kan också utföras för att åtgärda det identifierade hotet.</span><span class="sxs-lookup"><span data-stu-id="be71d-139">A manual remediation can also be done to remediate the identified threat.</span></span>
3. <span data-ttu-id="be71d-140">Baserat på principen som skapats i Intune markeras enheten som inte kompatibel.</span><span class="sxs-lookup"><span data-stu-id="be71d-140">Based on the policy created in Intune, the device is marked as not compliant.</span></span> <span data-ttu-id="be71d-141">Utvärderingen meddelas sedan till Azure AD genom intune-principen för villkorsstyrd åtkomst.</span><span class="sxs-lookup"><span data-stu-id="be71d-141">The assessment is then communicated to Azure AD by the Intune Conditional Access policy.</span></span> <span data-ttu-id="be71d-142">I Azure AD används motsvarande princip för att blockera åtkomst till program.</span><span class="sxs-lookup"><span data-stu-id="be71d-142">In Azure AD, the corresponding policy is applied to block access to applications.</span></span>
4. <span data-ttu-id="be71d-143">Den manuella eller automatiserade undersökningen och korrigeringen slutförs och hot tas bort.</span><span class="sxs-lookup"><span data-stu-id="be71d-143">The manual or automated investigation and remediation is completed and the threat is removed.</span></span> <span data-ttu-id="be71d-144">Defender för Endpoint ser att det inte finns någon risk på enheten och Intune bedömer enheten som kompatibel.</span><span class="sxs-lookup"><span data-stu-id="be71d-144">Defender for Endpoint sees that there is no risk on the device and Intune assesses the device to be in a compliant state.</span></span> <span data-ttu-id="be71d-145">Azure AD tillämpar principen som ger åtkomst till program.</span><span class="sxs-lookup"><span data-stu-id="be71d-145">Azure AD applies the policy which allows access to applications.</span></span>
5. <span data-ttu-id="be71d-146">Användare kan nu komma åt program.</span><span class="sxs-lookup"><span data-stu-id="be71d-146">Users can now access applications.</span></span>

 
## <a name="related-topic"></a><span data-ttu-id="be71d-147">Relaterat ämne</span><span class="sxs-lookup"><span data-stu-id="be71d-147">Related topic</span></span>
- [<span data-ttu-id="be71d-148">Konfigurera villkorsstyrd åtkomst i Microsoft Defender för Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="be71d-148">Configure Conditional Access in Microsoft Defender for Endpoint</span></span>](configure-conditional-access.md)
