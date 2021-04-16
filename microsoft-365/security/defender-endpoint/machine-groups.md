---
title: Skapa och hantera enhetsgrupper i Microsoft Defender för Slutpunkt
description: Skapa enhetsgrupper och ange automatiserade åtgärdsnivåer för dem genom att ange de regler som gäller för gruppen
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
ms.openlocfilehash: acd24e5c87a74bbb32835ec170a121c5c0b6bb33
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860309"
---
# <a name="create-and-manage-device-groups"></a><span data-ttu-id="7a037-104">Skapa och hantera enhetsgrupper</span><span class="sxs-lookup"><span data-stu-id="7a037-104">Create and manage device groups</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="7a037-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="7a037-105">**Applies to:**</span></span>
- <span data-ttu-id="7a037-106">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="7a037-106">Azure Active Directory</span></span>
- <span data-ttu-id="7a037-107">Office 365</span><span class="sxs-lookup"><span data-stu-id="7a037-107">Office 365</span></span>

> <span data-ttu-id="7a037-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="7a037-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7a037-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="7a037-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="7a037-110">I ett företagsscenario tilldelas vanligtvis säkerhetsåtgärdsteam en uppsättning enheter.</span><span class="sxs-lookup"><span data-stu-id="7a037-110">In an enterprise scenario, security operation teams are typically assigned a set of devices.</span></span> <span data-ttu-id="7a037-111">De här enheterna grupperas tillsammans baserat på en uppsättning attribut, till exempel deras domäner, datornamn eller angivna taggar.</span><span class="sxs-lookup"><span data-stu-id="7a037-111">These devices are grouped together based on a set of attributes such as their domains, computer names, or designated tags.</span></span>

<span data-ttu-id="7a037-112">I Microsoft Defender för Slutpunkt kan du skapa enhetsgrupper och använda dem för att:</span><span class="sxs-lookup"><span data-stu-id="7a037-112">In Microsoft Defender for Endpoint, you can create device groups and use them to:</span></span>
- <span data-ttu-id="7a037-113">Begränsa åtkomsten till relaterade aviseringar och data till specifika Azure AD-användargrupper med [tilldelade RBAC-roller](rbac.md)</span><span class="sxs-lookup"><span data-stu-id="7a037-113">Limit access to related alerts and data to specific Azure AD user groups with [assigned RBAC roles](rbac.md)</span></span> 
- <span data-ttu-id="7a037-114">Konfigurera olika inställningar för automatisk åtgärd för olika uppsättningar av enheter</span><span class="sxs-lookup"><span data-stu-id="7a037-114">Configure different auto-remediation settings for different sets of devices</span></span>
- <span data-ttu-id="7a037-115">Tilldela specifika åtgärdsnivåer att tillämpa under automatiserade undersökningar</span><span class="sxs-lookup"><span data-stu-id="7a037-115">Assign specific remediation levels to apply during automated investigations</span></span>
- <span data-ttu-id="7a037-116">I en undersökning kan du filtrera **listan Enheter till** endast vissa enhetsgrupper med hjälp av **filtret** Grupp.</span><span class="sxs-lookup"><span data-stu-id="7a037-116">In an investigation, filter the **Devices list** to just specific device groups by using the **Group** filter.</span></span>

<span data-ttu-id="7a037-117">Du kan skapa enhetsgrupper i samband med rollbaserad åtkomst (RBAC) för att styra vem som kan vidta särskilda åtgärder eller se information genom att tilldela enhetsgruppen/grupperna till en användargrupp.</span><span class="sxs-lookup"><span data-stu-id="7a037-117">You can create device groups in the context of role-based access (RBAC) to control who can take specific action or see information by assigning the device group(s) to a user group.</span></span> <span data-ttu-id="7a037-118">Mer information finns i Hantera [portalåtkomst med hjälp av rollbaserad åtkomstkontroll.](rbac.md)</span><span class="sxs-lookup"><span data-stu-id="7a037-118">For more information, see [Manage portal access using role-based access control](rbac.md).</span></span>

>[!TIP]
> <span data-ttu-id="7a037-119">Om du vill ha mer detaljerad information om RBAC-programmet läser du: [Is your SOC running flat with RBAC](https://techcommunity.microsoft.com/t5/Windows-Defender-ATP/Is-your-SOC-running-flat-with-limited-RBAC/ba-p/320015).</span><span class="sxs-lookup"><span data-stu-id="7a037-119">For a comprehensive look into RBAC application, read: [Is your SOC running flat with RBAC](https://techcommunity.microsoft.com/t5/Windows-Defender-ATP/Is-your-SOC-running-flat-with-limited-RBAC/ba-p/320015).</span></span>

<span data-ttu-id="7a037-120">Som en del av processen med att skapa en enhetsgrupp gör du följande:</span><span class="sxs-lookup"><span data-stu-id="7a037-120">As part of the process of creating a device group, you'll:</span></span>
- <span data-ttu-id="7a037-121">Ställ in nivån för automatisk åtgärd för gruppen.</span><span class="sxs-lookup"><span data-stu-id="7a037-121">Set the automated remediation level for that group.</span></span> <span data-ttu-id="7a037-122">Mer information om åtgärdsnivåer finns i [Använda automatisk undersökning för att undersöka och åtgärda hot.](automated-investigations.md)</span><span class="sxs-lookup"><span data-stu-id="7a037-122">For more information on remediation levels, see [Use Automated investigation to investigate and remediate threats](automated-investigations.md).</span></span>
- <span data-ttu-id="7a037-123">Ange den matchande regel som bestämmer vilken enhetsgrupp som tillhör gruppen baserat på enhetsnamn, domän, taggar och OS-plattform.</span><span class="sxs-lookup"><span data-stu-id="7a037-123">Specify the matching rule that determines which device group belongs to the group based on the device name, domain, tags, and OS platform.</span></span> <span data-ttu-id="7a037-124">Om en enhet matchas med andra grupper läggs den bara till i den enhetsgrupp som rangordnas högst.</span><span class="sxs-lookup"><span data-stu-id="7a037-124">If a device is also matched to other groups, it is added only to the highest ranked device group.</span></span>
- <span data-ttu-id="7a037-125">Välj den Azure AD-användargrupp som ska ha åtkomst till enhetsgruppen.</span><span class="sxs-lookup"><span data-stu-id="7a037-125">Select the Azure AD user group that should have access to the device group.</span></span>
- <span data-ttu-id="7a037-126">Rangordna enhetsgruppen i förhållande till andra grupper när den har skapats.</span><span class="sxs-lookup"><span data-stu-id="7a037-126">Rank the device group relative to other groups after it is created.</span></span>

>[!NOTE]
><span data-ttu-id="7a037-127">En enhetsgrupp är tillgänglig för alla användare om du inte tilldelar några Azure AD-grupper till den.</span><span class="sxs-lookup"><span data-stu-id="7a037-127">A device group is accessible to all users if you don’t assign any Azure AD groups to it.</span></span>

## <a name="create-a-device-group"></a><span data-ttu-id="7a037-128">Skapa en enhetsgrupp</span><span class="sxs-lookup"><span data-stu-id="7a037-128">Create a device group</span></span>

1. <span data-ttu-id="7a037-129">I navigeringsfönstret väljer du **Inställningar**  >  **Enhetsgrupper**.</span><span class="sxs-lookup"><span data-stu-id="7a037-129">In the navigation pane, select **Settings** > **Device groups**.</span></span>

2. <span data-ttu-id="7a037-130">Klicka **på Lägg till enhetsgrupp**.</span><span class="sxs-lookup"><span data-stu-id="7a037-130">Click **Add device group**.</span></span>

3. <span data-ttu-id="7a037-131">Ange inställningarna för gruppnamn och automatisering och ange den matchande regeln som avgör vilka enheter som hör till gruppen.</span><span class="sxs-lookup"><span data-stu-id="7a037-131">Enter the group name and automation settings and specify the matching rule that determines which devices belong to the group.</span></span> <span data-ttu-id="7a037-132">Se [Hur den automatiska undersökningen startar](automated-investigations.md#how-the-automated-investigation-starts).</span><span class="sxs-lookup"><span data-stu-id="7a037-132">See [How the automated investigation starts](automated-investigations.md#how-the-automated-investigation-starts).</span></span>

    >[!TIP]
    ><span data-ttu-id="7a037-133">Om du vill gruppera enheter efter organisationsenhet kan du konfigurera registernyckeln för gruppanslutningen.</span><span class="sxs-lookup"><span data-stu-id="7a037-133">If you want to group devices by organizational unit, you can configure the registry key for the group affiliation.</span></span> <span data-ttu-id="7a037-134">Mer information om enhetstaggar finns i [Skapa och hantera enhetstaggar.](machine-tags.md)</span><span class="sxs-lookup"><span data-stu-id="7a037-134">For more information on device tagging, see [Create and manage device tags](machine-tags.md).</span></span>

4. <span data-ttu-id="7a037-135">Förhandsgranska flera enheter som kommer att matchas med den här regeln.</span><span class="sxs-lookup"><span data-stu-id="7a037-135">Preview several devices that will be matched by this rule.</span></span> <span data-ttu-id="7a037-136">Om du är nöjd med regeln klickar du på **fliken Användaråtkomst.**</span><span class="sxs-lookup"><span data-stu-id="7a037-136">If you are satisfied with the rule, click the **User access** tab.</span></span>

5. <span data-ttu-id="7a037-137">Tilldela de användargrupper som kan komma åt enhetsgruppen som du har skapat.</span><span class="sxs-lookup"><span data-stu-id="7a037-137">Assign the user groups that can access the device group you created.</span></span>

    >[!NOTE]
    ><span data-ttu-id="7a037-138">Du kan bara bevilja åtkomst till Azure AD-användargrupper som har tilldelats RBAC-roller.</span><span class="sxs-lookup"><span data-stu-id="7a037-138">You can only grant access to Azure AD user groups that have been assigned to RBAC roles.</span></span>

6. <span data-ttu-id="7a037-139">Klicka på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="7a037-139">Click **Close**.</span></span> <span data-ttu-id="7a037-140">Konfigurationsändringarna tillämpas.</span><span class="sxs-lookup"><span data-stu-id="7a037-140">The configuration changes are applied.</span></span>

## <a name="manage-device-groups"></a><span data-ttu-id="7a037-141">Hantera enhetsgrupper</span><span class="sxs-lookup"><span data-stu-id="7a037-141">Manage device groups</span></span>

<span data-ttu-id="7a037-142">Du kan höja eller sänka rangordningen för en enhetsgrupp så att den får högre eller lägre prioritet vid matchningen.</span><span class="sxs-lookup"><span data-stu-id="7a037-142">You can promote or demote the rank of a device group so that it is given higher or lower priority during matching.</span></span> <span data-ttu-id="7a037-143">När en enhet matchas med fler än en grupp läggs den bara till i den högst rankade gruppen.</span><span class="sxs-lookup"><span data-stu-id="7a037-143">When a device is matched to more than one group, it is added only to the highest ranked group.</span></span> <span data-ttu-id="7a037-144">Du kan också redigera och ta bort grupper.</span><span class="sxs-lookup"><span data-stu-id="7a037-144">You can also edit and delete groups.</span></span>

>[!WARNING]
><span data-ttu-id="7a037-145">Om du tar bort en enhetsgrupp kan det påverka e-postaviseringsregler.</span><span class="sxs-lookup"><span data-stu-id="7a037-145">Deleting a device group may affect email notification rules.</span></span> <span data-ttu-id="7a037-146">Om en enhetsgrupp konfigureras under en regel för e-postavisering tas den bort från regeln.</span><span class="sxs-lookup"><span data-stu-id="7a037-146">If a device group is configured under an email notification rule, it will be removed from that rule.</span></span> <span data-ttu-id="7a037-147">Om enhetsgruppen är den enda grupp som konfigurerats för en e-postavisering tas e-postaviseringsregeln bort tillsammans med enhetsgruppen.</span><span class="sxs-lookup"><span data-stu-id="7a037-147">If the device group is the only group configured for an email notification, that email notification rule will be deleted along with the device group.</span></span>

<span data-ttu-id="7a037-148">Som standard är enhetsgrupper tillgängliga för alla användare med portalåtkomst.</span><span class="sxs-lookup"><span data-stu-id="7a037-148">By default, device groups are accessible to all users with portal access.</span></span> <span data-ttu-id="7a037-149">Du kan ändra standardbeteendet genom att tilldela Azure AD-användargrupper till enhetsgruppen.</span><span class="sxs-lookup"><span data-stu-id="7a037-149">You can change the default behavior by assigning Azure AD user groups to the device group.</span></span>

<span data-ttu-id="7a037-150">Enheter som inte matchas med någon grupp läggs till i gruppen Dela upp enheter (standard).</span><span class="sxs-lookup"><span data-stu-id="7a037-150">Devices that are not matched to any groups are added to Ungrouped devices (default) group.</span></span> <span data-ttu-id="7a037-151">Du kan inte ändra rangordningen för gruppen eller ta bort den.</span><span class="sxs-lookup"><span data-stu-id="7a037-151">You cannot change the rank of this group or delete it.</span></span> <span data-ttu-id="7a037-152">Du kan dock ändra åtgärdsnivån för den här gruppen och definiera de Azure AD-användargrupper som har åtkomst till den här gruppen.</span><span class="sxs-lookup"><span data-stu-id="7a037-152">However, you can change the remediation level of this group, and define the Azure AD user groups that can access this group.</span></span>

>[!NOTE]
> <span data-ttu-id="7a037-153">Det kan ta upp till flera minuter att tillämpa ändringar på enhetsgruppskonfigurationen.</span><span class="sxs-lookup"><span data-stu-id="7a037-153">Applying changes to device group configuration may take up to several minutes.</span></span>

## <a name="related-topics"></a><span data-ttu-id="7a037-154">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="7a037-154">Related topics</span></span>

- [<span data-ttu-id="7a037-155">Hantera portalåtkomst med hjälp av rollbaserad åtkomstkontroll</span><span class="sxs-lookup"><span data-stu-id="7a037-155">Manage portal access using role-based based access control</span></span>](rbac.md)
- [<span data-ttu-id="7a037-156">Skapa och hantera enhetstaggar</span><span class="sxs-lookup"><span data-stu-id="7a037-156">Create and manage device tags</span></span>](machine-tags.md)
- [<span data-ttu-id="7a037-157">Hämta en lista över grupper på klientorganisationsenheten med Hjälp av Graph API</span><span class="sxs-lookup"><span data-stu-id="7a037-157">Get list of tenant device groups using Graph API</span></span>](https://docs.microsoft.com/graph/api/device-list-memberof)
