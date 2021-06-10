---
title: Skapa och hantera enhetsgrupper i Microsoft Defender för Slutpunkt
description: Skapa enhetsgrupper och ange automatiserade åtgärdsnivåer för dem genom att bekräfta reglerna som gäller för gruppen
keywords: enhetsgrupper, grupper, åtgärd, nivå, regler, aad-grupp, roll, tilldela, rangordna
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
ms.openlocfilehash: d4f62acde4e7d790c7a7c8635f51c99f0823687d
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842776"
---
# <a name="create-and-manage-device-groups"></a><span data-ttu-id="92363-104">Skapa och hantera enhetsgrupper</span><span class="sxs-lookup"><span data-stu-id="92363-104">Create and manage device groups</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="92363-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="92363-105">**Applies to:**</span></span>
- <span data-ttu-id="92363-106">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="92363-106">Azure Active Directory</span></span>
- <span data-ttu-id="92363-107">Office 365</span><span class="sxs-lookup"><span data-stu-id="92363-107">Office 365</span></span>

> <span data-ttu-id="92363-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="92363-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="92363-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="92363-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="92363-110">I ett företagsscenario tilldelas vanligtvis säkerhetsåtgärdsteam en uppsättning enheter.</span><span class="sxs-lookup"><span data-stu-id="92363-110">In an enterprise scenario, security operation teams are typically assigned a set of devices.</span></span> <span data-ttu-id="92363-111">De här enheterna grupperas tillsammans baserat på en uppsättning attribut, till exempel deras domäner, datornamn eller angivna taggar.</span><span class="sxs-lookup"><span data-stu-id="92363-111">These devices are grouped together based on a set of attributes such as their domains, computer names, or designated tags.</span></span>

<span data-ttu-id="92363-112">I Microsoft Defender för Slutpunkt kan du skapa enhetsgrupper och använda dem för att:</span><span class="sxs-lookup"><span data-stu-id="92363-112">In Microsoft Defender for Endpoint, you can create device groups and use them to:</span></span>
- <span data-ttu-id="92363-113">Begränsa åtkomsten till relaterade aviseringar och data till specifika Azure AD-användargrupper med [tilldelade RBAC-roller](rbac.md)</span><span class="sxs-lookup"><span data-stu-id="92363-113">Limit access to related alerts and data to specific Azure AD user groups with [assigned RBAC roles](rbac.md)</span></span> 
- <span data-ttu-id="92363-114">Konfigurera olika inställningar för automatisk åtgärd för olika uppsättningar av enheter</span><span class="sxs-lookup"><span data-stu-id="92363-114">Configure different auto-remediation settings for different sets of devices</span></span>
- <span data-ttu-id="92363-115">Tilldela specifika åtgärdsnivåer att tillämpa under automatiserade undersökningar</span><span class="sxs-lookup"><span data-stu-id="92363-115">Assign specific remediation levels to apply during automated investigations</span></span>
- <span data-ttu-id="92363-116">I en undersökning kan du filtrera **listan Enheter till** specifika enhetsgrupper med hjälp av **gruppfiltret.**</span><span class="sxs-lookup"><span data-stu-id="92363-116">In an investigation, filter the **Devices list** to specific device groups by using the **Group** filter.</span></span>

<span data-ttu-id="92363-117">Du kan skapa enhetsgrupper i samband med rollbaserad åtkomst (RBAC) för att styra vem som kan vidta särskilda åtgärder eller se information genom att tilldela enhetsgruppen/grupperna till en användargrupp.</span><span class="sxs-lookup"><span data-stu-id="92363-117">You can create device groups in the context of role-based access (RBAC) to control who can take specific action or see information by assigning the device group(s) to a user group.</span></span> <span data-ttu-id="92363-118">Mer information finns i Hantera [portalåtkomst med hjälp av rollbaserad åtkomstkontroll.](rbac.md)</span><span class="sxs-lookup"><span data-stu-id="92363-118">For more information, see [Manage portal access using role-based access control](rbac.md).</span></span>

>[!TIP]
> <span data-ttu-id="92363-119">Om du vill ha mer detaljerad information om RBAC-programmet läser du: [Is your SOC running flat with RBAC](https://techcommunity.microsoft.com/t5/Windows-Defender-ATP/Is-your-SOC-running-flat-with-limited-RBAC/ba-p/320015).</span><span class="sxs-lookup"><span data-stu-id="92363-119">For a comprehensive look into RBAC application, read: [Is your SOC running flat with RBAC](https://techcommunity.microsoft.com/t5/Windows-Defender-ATP/Is-your-SOC-running-flat-with-limited-RBAC/ba-p/320015).</span></span>

<span data-ttu-id="92363-120">Som en del av processen med att skapa en enhetsgrupp gör du följande:</span><span class="sxs-lookup"><span data-stu-id="92363-120">As part of the process of creating a device group, you'll:</span></span>
- <span data-ttu-id="92363-121">Ställ in nivån för automatisk åtgärd för gruppen.</span><span class="sxs-lookup"><span data-stu-id="92363-121">Set the automated remediation level for that group.</span></span> <span data-ttu-id="92363-122">Mer information om åtgärdsnivåer finns i [Använda automatisk undersökning för att undersöka och åtgärda hot.](automated-investigations.md)</span><span class="sxs-lookup"><span data-stu-id="92363-122">For more information on remediation levels, see [Use Automated investigation to investigate and remediate threats](automated-investigations.md).</span></span>
- <span data-ttu-id="92363-123">Ange den matchande regel som bestämmer vilken enhetsgrupp som tillhör gruppen baserat på enhetsnamn, domän, taggar och OS-plattform.</span><span class="sxs-lookup"><span data-stu-id="92363-123">Specify the matching rule that determines which device group belongs to the group based on the device name, domain, tags, and OS platform.</span></span> <span data-ttu-id="92363-124">Om en enhet matchas med andra grupper läggs den bara till i den enhetsgrupp som rangordnas högst.</span><span class="sxs-lookup"><span data-stu-id="92363-124">If a device is also matched to other groups, it's added only to the highest ranked device group.</span></span>
- <span data-ttu-id="92363-125">Välj den Azure AD-användargrupp som ska ha åtkomst till enhetsgruppen.</span><span class="sxs-lookup"><span data-stu-id="92363-125">Select the Azure AD user group that should have access to the device group.</span></span>
- <span data-ttu-id="92363-126">Rangordna enhetsgruppen i förhållande till andra grupper när den har skapats.</span><span class="sxs-lookup"><span data-stu-id="92363-126">Rank the device group relative to other groups after it's created.</span></span>

>[!NOTE]
><span data-ttu-id="92363-127">En enhetsgrupp är tillgänglig för alla användare om du inte tilldelar några Azure AD-grupper till den.</span><span class="sxs-lookup"><span data-stu-id="92363-127">A device group is accessible to all users if you don’t assign any Azure AD groups to it.</span></span>

## <a name="create-a-device-group"></a><span data-ttu-id="92363-128">Skapa en enhetsgrupp</span><span class="sxs-lookup"><span data-stu-id="92363-128">Create a device group</span></span>

1. <span data-ttu-id="92363-129">I navigeringsfönstret väljer du **Inställningar**  >  **Enhetsgrupper**.</span><span class="sxs-lookup"><span data-stu-id="92363-129">In the navigation pane, select **Settings** > **Device groups**.</span></span>

2. <span data-ttu-id="92363-130">Klicka **på Lägg till enhetsgrupp**.</span><span class="sxs-lookup"><span data-stu-id="92363-130">Click **Add device group**.</span></span>

3. <span data-ttu-id="92363-131">Ange inställningarna för gruppnamn och automatisering och ange den matchande regeln som avgör vilka enheter som hör till gruppen.</span><span class="sxs-lookup"><span data-stu-id="92363-131">Enter the group name and automation settings and specify the matching rule that determines which devices belong to the group.</span></span> <span data-ttu-id="92363-132">Se [Hur den automatiska undersökningen startar](automated-investigations.md#how-the-automated-investigation-starts).</span><span class="sxs-lookup"><span data-stu-id="92363-132">See [How the automated investigation starts](automated-investigations.md#how-the-automated-investigation-starts).</span></span>

    >[!TIP]
    ><span data-ttu-id="92363-133">Om du vill gruppera enheter efter organisationsenhet kan du konfigurera registernyckeln för gruppanslutningen.</span><span class="sxs-lookup"><span data-stu-id="92363-133">If you want to group devices by organizational unit, you can configure the registry key for the group affiliation.</span></span> <span data-ttu-id="92363-134">Mer information om enhetstaggar finns i [Skapa och hantera enhetstaggar.](machine-tags.md)</span><span class="sxs-lookup"><span data-stu-id="92363-134">For more information on device tagging, see [Create and manage device tags](machine-tags.md).</span></span>

4. <span data-ttu-id="92363-135">Förhandsgranska flera enheter som kommer att matchas med den här regeln.</span><span class="sxs-lookup"><span data-stu-id="92363-135">Preview several devices that will be matched by this rule.</span></span> <span data-ttu-id="92363-136">Om du är nöjd med regeln klickar du på **fliken Användaråtkomst.**</span><span class="sxs-lookup"><span data-stu-id="92363-136">If you're satisfied with the rule, click the **User access** tab.</span></span>

5. <span data-ttu-id="92363-137">Tilldela de användargrupper som kan komma åt enhetsgruppen som du har skapat.</span><span class="sxs-lookup"><span data-stu-id="92363-137">Assign the user groups that can access the device group you created.</span></span>

    >[!NOTE]
    ><span data-ttu-id="92363-138">Du kan bara bevilja åtkomst till Azure AD-användargrupper som har tilldelats RBAC-roller.</span><span class="sxs-lookup"><span data-stu-id="92363-138">You can only grant access to Azure AD user groups that have been assigned to RBAC roles.</span></span>

6. <span data-ttu-id="92363-139">Klicka på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="92363-139">Click **Close**.</span></span> <span data-ttu-id="92363-140">Konfigurationsändringarna tillämpas.</span><span class="sxs-lookup"><span data-stu-id="92363-140">The configuration changes are applied.</span></span>

## <a name="manage-device-groups"></a><span data-ttu-id="92363-141">Hantera enhetsgrupper</span><span class="sxs-lookup"><span data-stu-id="92363-141">Manage device groups</span></span>

<span data-ttu-id="92363-142">Du kan höja eller sänka rangordningen för en enhetsgrupp så att den får högre eller lägre prioritet vid matchningen.</span><span class="sxs-lookup"><span data-stu-id="92363-142">You can promote or demote the rank of a device group so that it's given higher or lower priority during matching.</span></span> <span data-ttu-id="92363-143">När en enhet matchas med fler än en grupp läggs den bara till i den högst rankade gruppen.</span><span class="sxs-lookup"><span data-stu-id="92363-143">When a device is matched to more than one group, it's added only to the highest ranked group.</span></span> <span data-ttu-id="92363-144">Du kan också redigera och ta bort grupper.</span><span class="sxs-lookup"><span data-stu-id="92363-144">You can also edit and delete groups.</span></span>



>[!WARNING]
><span data-ttu-id="92363-145">Om du tar bort en enhetsgrupp kan det påverka e-postaviseringsregler.</span><span class="sxs-lookup"><span data-stu-id="92363-145">Deleting a device group may affect email notification rules.</span></span> <span data-ttu-id="92363-146">Om en enhetsgrupp konfigureras under en regel för e-postavisering tas den bort från regeln.</span><span class="sxs-lookup"><span data-stu-id="92363-146">If a device group is configured under an email notification rule, it will be removed from that rule.</span></span> <span data-ttu-id="92363-147">Om enhetsgruppen är den enda grupp som konfigurerats för en e-postavisering tas e-postaviseringsregeln bort tillsammans med enhetsgruppen.</span><span class="sxs-lookup"><span data-stu-id="92363-147">If the device group is the only group configured for an email notification, that email notification rule will be deleted along with the device group.</span></span>

<span data-ttu-id="92363-148">Som standard är enhetsgrupper tillgängliga för alla användare med portalåtkomst.</span><span class="sxs-lookup"><span data-stu-id="92363-148">By default, device groups are accessible to all users with portal access.</span></span> <span data-ttu-id="92363-149">Du kan ändra standardbeteendet genom att tilldela Azure AD-användargrupper till enhetsgruppen.</span><span class="sxs-lookup"><span data-stu-id="92363-149">You can change the default behavior by assigning Azure AD user groups to the device group.</span></span>

<span data-ttu-id="92363-150">Enheter som inte matchas med några grupper läggs till i gruppen Dela upp enheter (standard).</span><span class="sxs-lookup"><span data-stu-id="92363-150">Devices that aren't matched to any groups are added to Ungrouped devices (default) group.</span></span> <span data-ttu-id="92363-151">Du kan inte ändra rangordningen för gruppen eller ta bort den.</span><span class="sxs-lookup"><span data-stu-id="92363-151">You cannot change the rank of this group or delete it.</span></span> <span data-ttu-id="92363-152">Du kan dock ändra åtgärdsnivån för den här gruppen och definiera de Azure AD-användargrupper som har åtkomst till den här gruppen.</span><span class="sxs-lookup"><span data-stu-id="92363-152">However, you can change the remediation level of this group, and define the Azure AD user groups that can access this group.</span></span>

>[!NOTE]
> <span data-ttu-id="92363-153">Det kan ta upp till flera minuter att tillämpa ändringar på enhetsgruppskonfigurationen.</span><span class="sxs-lookup"><span data-stu-id="92363-153">Applying changes to device group configuration may take up to several minutes.</span></span>


### <a name="add-device-group-definitions"></a><span data-ttu-id="92363-154">Lägga till enhetsgruppsdefinitioner</span><span class="sxs-lookup"><span data-stu-id="92363-154">Add device group definitions</span></span>
<span data-ttu-id="92363-155">Enhetsgruppsdefinitioner kan också innehålla flera värden för varje villkor.</span><span class="sxs-lookup"><span data-stu-id="92363-155">Device group definitions can also include multiple values for each condition.</span></span> <span data-ttu-id="92363-156">Du kan ange definitionen för en enda enhetsgrupp för flera taggar, enhetsnamn och domäner.</span><span class="sxs-lookup"><span data-stu-id="92363-156">You can set multiple tags, device names, and domains to the definition of a single device group.</span></span>

1. <span data-ttu-id="92363-157">Skapa en ny enhetsgrupp och välj sedan **fliken** Enheter.</span><span class="sxs-lookup"><span data-stu-id="92363-157">Create a new device group, then select **Devices** tab.</span></span>
2. <span data-ttu-id="92363-158">Lägg till det första värdet för något av villkoren.</span><span class="sxs-lookup"><span data-stu-id="92363-158">Add the first value for one of the conditions.</span></span>
3. <span data-ttu-id="92363-159">Välj `+` den här om du vill lägga till fler rader av samma egenskapstyp.</span><span class="sxs-lookup"><span data-stu-id="92363-159">Select `+` to add more rows of the same property type.</span></span>

>[!TIP]
> <span data-ttu-id="92363-160">Använd operatorn ELLER mellan rader av samma villkorstyp, som tillåter flera värden per egenskap.</span><span class="sxs-lookup"><span data-stu-id="92363-160">Use the 'OR' operator between rows of the same condition type, which allows multiple values per property.</span></span>
> <span data-ttu-id="92363-161">Du kan lägga till upp till 10 rader (värden) för varje egenskapstyp – tagg, enhetsnamn, domän.</span><span class="sxs-lookup"><span data-stu-id="92363-161">You can add up to 10 rows (values) for each property type - tag, device name, domain.</span></span>

<span data-ttu-id="92363-162">Mer information om hur du länkar till definitioner av enhetsgrupper finns [i Enhetsgrupper – Microsoft 365 säkerhet.](https://sip.security.microsoft.com/homepage)</span><span class="sxs-lookup"><span data-stu-id="92363-162">For more information on linking to device groups definitions, see [Device groups - Microsoft 365 security](https://sip.security.microsoft.com/homepage).</span></span>

## <a name="related-topics"></a><span data-ttu-id="92363-163">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="92363-163">Related topics</span></span>

- [<span data-ttu-id="92363-164">Hantera portalåtkomst med hjälp av rollbaserad åtkomstkontroll</span><span class="sxs-lookup"><span data-stu-id="92363-164">Manage portal access using role-based based access control</span></span>](rbac.md)
- [<span data-ttu-id="92363-165">Skapa och hantera enhetstaggar</span><span class="sxs-lookup"><span data-stu-id="92363-165">Create and manage device tags</span></span>](machine-tags.md)
- [<span data-ttu-id="92363-166">Hämta en lista över grupper på klientorganisationsenheten med hjälp Graph API</span><span class="sxs-lookup"><span data-stu-id="92363-166">Get list of tenant device groups using Graph API</span></span>](/graph/api/device-list-memberof)
