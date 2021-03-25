---
title: Skapa och hantera roller för rollbaserad åtkomstkontroll
description: Skapa roller och definiera de behörigheter som tilldelas till rollen som en del av implementeringen av rollbaserad åtkomstkontroll i Microsoft Defender Säkerhetscenter
keywords: användarroller, roller, åtkomst till rbac
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
ms.openlocfilehash: 932fd6ecd7dca66f4cb587b226474109c788c341
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073986"
---
# <a name="create-and-manage-roles-for-role-based-access-control"></a><span data-ttu-id="b731f-104">Skapa och hantera roller för rollbaserad åtkomstkontroll</span><span class="sxs-lookup"><span data-stu-id="b731f-104">Create and manage roles for role-based access control</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b731f-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="b731f-105">**Applies to:**</span></span>
- [<span data-ttu-id="b731f-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="b731f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="b731f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b731f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="b731f-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="b731f-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b731f-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="b731f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-roles-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="create-roles-and-assign-the-role-to-an-azure-active-directory-group"></a><span data-ttu-id="b731f-110">Skapa roller och tilldela rollen till en Azure Active Directory-grupp</span><span class="sxs-lookup"><span data-stu-id="b731f-110">Create roles and assign the role to an Azure Active Directory group</span></span>

<span data-ttu-id="b731f-111">I följande steg får du veta hur du skapar roller i Microsoft Defender Säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="b731f-111">The following steps guide you on how to create roles in Microsoft Defender Security Center.</span></span> <span data-ttu-id="b731f-112">Vi förutsätter att du redan har skapat användargrupper i Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b731f-112">It assumes that you have already created Azure Active Directory user groups.</span></span>

1. <span data-ttu-id="b731f-113">Logga in på [Microsoft Defender Säkerhetscenter med](https://securitycenter.windows.com/) ett konto med en tilldelad säkerhetsadministratör eller global administratörsroll.</span><span class="sxs-lookup"><span data-stu-id="b731f-113">Log in to [Microsoft Defender Security Center](https://securitycenter.windows.com/) using account with a Security administrator or Global administrator role assigned.</span></span>

2. <span data-ttu-id="b731f-114">I navigeringsfönstret väljer du **Inställningar > Roller**.</span><span class="sxs-lookup"><span data-stu-id="b731f-114">In the navigation pane, select **Settings > Roles**.</span></span>

3. <span data-ttu-id="b731f-115">Välj **Lägg till objekt.**</span><span class="sxs-lookup"><span data-stu-id="b731f-115">Select **Add item**.</span></span>

4. <span data-ttu-id="b731f-116">Ange det rollnamn, den beskrivning och de behörigheter som du vill tilldela rollen.</span><span class="sxs-lookup"><span data-stu-id="b731f-116">Enter the role name, description, and permissions you'd like to assign to the role.</span></span>

5. <span data-ttu-id="b731f-117">Välj **Nästa** för att tilldela rollen till en Azure AD-säkerhetsgrupp.</span><span class="sxs-lookup"><span data-stu-id="b731f-117">Select **Next** to assign the role to an Azure AD Security group.</span></span>

6. <span data-ttu-id="b731f-118">Använd filtret för att välja den Azure AD-grupp som du vill lägga till den här rollen i.</span><span class="sxs-lookup"><span data-stu-id="b731f-118">Use the filter to select the Azure AD group that you'd like to add to this role to.</span></span>

7. <span data-ttu-id="b731f-119">**Spara och stäng**.</span><span class="sxs-lookup"><span data-stu-id="b731f-119">**Save and close**.</span></span>

8. <span data-ttu-id="b731f-120">Använd konfigurationsinställningarna.</span><span class="sxs-lookup"><span data-stu-id="b731f-120">Apply the configuration settings.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b731f-121">När du har skapat roller måste du skapa en enhetsgrupp och ge åtkomst till enhetsgruppen genom att tilldela den till en roll som du just har skapat.</span><span class="sxs-lookup"><span data-stu-id="b731f-121">After creating roles, you'll need to create a device group and provide access to the device group by assigning it to a role that you just created.</span></span>

### <a name="permission-options"></a><span data-ttu-id="b731f-122">Behörighetsalternativ</span><span class="sxs-lookup"><span data-stu-id="b731f-122">Permission options</span></span>

- <span data-ttu-id="b731f-123">**Visa data**</span><span class="sxs-lookup"><span data-stu-id="b731f-123">**View data**</span></span>
    - <span data-ttu-id="b731f-124">**Säkerhetsåtgärder** – visa alla data i säkerhetsåtgärder i portalen</span><span class="sxs-lookup"><span data-stu-id="b731f-124">**Security operations** - View all security operations data in the portal</span></span>
    - <span data-ttu-id="b731f-125">**Hantering av hot och sårbarhet** – visa data om hot och sårbarhetshantering i portalen</span><span class="sxs-lookup"><span data-stu-id="b731f-125">**Threat and vulnerability management** - View threat and vulnerability management data in the portal</span></span>

- <span data-ttu-id="b731f-126">**Aktiva åtgärdsåtgärder**</span><span class="sxs-lookup"><span data-stu-id="b731f-126">**Active remediation actions**</span></span>
    - <span data-ttu-id="b731f-127">**Säkerhetsåtgärder** – Vidta svarsåtgärder, godkänna eller stänga väntande åtgärder, hantera tillåtna/blockerade listor för automatisering och indikatorer</span><span class="sxs-lookup"><span data-stu-id="b731f-127">**Security operations** - Take response actions, approve or dismiss pending remediation actions, manage allowed/blocked lists for automation and indicators</span></span>
    - <span data-ttu-id="b731f-128">**Hantering av hot och sårbarhet – Undantagshantering** – Skapa nya undantag och hantera aktiva undantag</span><span class="sxs-lookup"><span data-stu-id="b731f-128">**Threat and vulnerability management - Exception handling** - Create new exceptions and manage active exceptions</span></span>
    - <span data-ttu-id="b731f-129">**Hantering av hot och sårbarhet - Åtgärdshantering** - Skicka in nya åtgärdsförfrågningar, skapa ärenden och hantera befintliga åtgärdsaktiviteter</span><span class="sxs-lookup"><span data-stu-id="b731f-129">**Threat and vulnerability management - Remediation handling** - Submit new remediation requests, create tickets, and manage existing remediation activities</span></span>

- <span data-ttu-id="b731f-130">**Undersökning av aviseringar** – Hantera aviseringar, initiera automatiska undersökningar, köra genomsökningar, samla in undersökningspaket, hantera enhetstaggar och ladda ned endast bärbara körbara filer (PE)</span><span class="sxs-lookup"><span data-stu-id="b731f-130">**Alerts investigation** - Manage alerts, initiate automated investigations, run scans, collect investigation packages, manage device tags, and download only portable executable (PE) files</span></span> 

- <span data-ttu-id="b731f-131">**Hantera systeminställningar för portal** - Konfigurera lagringsinställningar, SIEM och hot-API-inställningar (gäller globalt), avancerade inställningar, automatiska filuppladdningar, roller och enhetsgrupper</span><span class="sxs-lookup"><span data-stu-id="b731f-131">**Manage portal system settings** - Configure storage settings, SIEM and threat intel API settings (applies globally), advanced settings, automated file uploads, roles and device groups</span></span>

    > [!NOTE]
    > <span data-ttu-id="b731f-132">Den här inställningen är endast tillgänglig i rollen Microsoft Defender för slutpunktsadministratör (standard).</span><span class="sxs-lookup"><span data-stu-id="b731f-132">This setting is only available in the Microsoft Defender for Endpoint administrator (default) role.</span></span>

- <span data-ttu-id="b731f-133">**Hantera säkerhetsinställningar i Säkerhetscenter** – Konfigurera inställningar för aviseringssäkerhet, hantera mapp undantas för automatisering, onboard och offboard-enheter, och hantera e-postaviseringar, hantera utvärderingslabb</span><span class="sxs-lookup"><span data-stu-id="b731f-133">**Manage security settings in Security Center** - Configure alert suppression settings, manage folder exclusions for automation, onboard and offboard devices, and manage email notifications, manage evaluation lab</span></span>

- <span data-ttu-id="b731f-134">**Funktioner för livesvar**</span><span class="sxs-lookup"><span data-stu-id="b731f-134">**Live response capabilities**</span></span>
    - <span data-ttu-id="b731f-135">**Grundläggande** kommandon:</span><span class="sxs-lookup"><span data-stu-id="b731f-135">**Basic** commands:</span></span>
        - <span data-ttu-id="b731f-136">Starta en svarssession i livesändning</span><span class="sxs-lookup"><span data-stu-id="b731f-136">Start a live response session</span></span>
        - <span data-ttu-id="b731f-137">Utföra skrivskyddade svarskommandon på en fjärrenhet (exklusive filkopiering och körning)</span><span class="sxs-lookup"><span data-stu-id="b731f-137">Perform read only live response commands on remote device (excluding file copy and execution</span></span>
    - <span data-ttu-id="b731f-138">**Avancerade** kommandon:</span><span class="sxs-lookup"><span data-stu-id="b731f-138">**Advanced** commands:</span></span>
        - <span data-ttu-id="b731f-139">Ladda ned en fil från fjärrenheten via livesvar</span><span class="sxs-lookup"><span data-stu-id="b731f-139">Download a file from the remote device via live response</span></span>
        - <span data-ttu-id="b731f-140">Ladda ned PE- och icke-PE-filer från filsidan</span><span class="sxs-lookup"><span data-stu-id="b731f-140">Download PE and non-PE files from the file page</span></span>
        - <span data-ttu-id="b731f-141">Ladda upp en fil till fjärrenheten</span><span class="sxs-lookup"><span data-stu-id="b731f-141">Upload a file to the remote device</span></span>
        - <span data-ttu-id="b731f-142">Visa ett skript från filbiblioteket</span><span class="sxs-lookup"><span data-stu-id="b731f-142">View a script from the files library</span></span>
        - <span data-ttu-id="b731f-143">Köra ett skript på fjärrenheten från filbiblioteket</span><span class="sxs-lookup"><span data-stu-id="b731f-143">Execute a script on the remote device from the files library</span></span>

<span data-ttu-id="b731f-144">Mer information om tillgängliga kommandon finns i Undersöka [enheter med Live Response.](live-response.md)</span><span class="sxs-lookup"><span data-stu-id="b731f-144">For more information on the available commands, see [Investigate devices using Live response](live-response.md).</span></span>
  
## <a name="edit-roles"></a><span data-ttu-id="b731f-145">Redigera roller</span><span class="sxs-lookup"><span data-stu-id="b731f-145">Edit roles</span></span>

1. <span data-ttu-id="b731f-146">Logga in på [Microsoft Defender Säkerhetscenter med kontot](https://securitycenter.windows.com/) med rollen Säkerhetsadministratör eller Global administratör tilldelad.</span><span class="sxs-lookup"><span data-stu-id="b731f-146">Log in to [Microsoft Defender Security Center](https://securitycenter.windows.com/) using account with Security administrator or Global administrator role assigned.</span></span>

2. <span data-ttu-id="b731f-147">I navigeringsfönstret väljer du **Inställningar > Roller**.</span><span class="sxs-lookup"><span data-stu-id="b731f-147">In the navigation pane, select **Settings > Roles**.</span></span>

3. <span data-ttu-id="b731f-148">Välj den roll som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="b731f-148">Select the role you'd like to edit.</span></span>

4. <span data-ttu-id="b731f-149">Klicka på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="b731f-149">Click **Edit**.</span></span>

5. <span data-ttu-id="b731f-150">Ändra informationen eller grupperna som har tilldelats rollen.</span><span class="sxs-lookup"><span data-stu-id="b731f-150">Modify the details or the groups that are assigned to the role.</span></span> 

6. <span data-ttu-id="b731f-151">Klicka **på Spara och stäng**.</span><span class="sxs-lookup"><span data-stu-id="b731f-151">Click **Save and close**.</span></span>

## <a name="delete-roles"></a><span data-ttu-id="b731f-152">Ta bort roller</span><span class="sxs-lookup"><span data-stu-id="b731f-152">Delete roles</span></span>

1. <span data-ttu-id="b731f-153">Logga in på [Microsoft Defender Säkerhetscenter med kontot](https://securitycenter.windows.com/) med rollen Säkerhetsadministratör eller Global administratör tilldelad.</span><span class="sxs-lookup"><span data-stu-id="b731f-153">Log in to [Microsoft Defender Security Center](https://securitycenter.windows.com/) using account with Security administrator or Global administrator role assigned.</span></span>

2. <span data-ttu-id="b731f-154">I navigeringsfönstret väljer du **Inställningar > Roller**.</span><span class="sxs-lookup"><span data-stu-id="b731f-154">In the navigation pane, select **Settings > Roles**.</span></span>

3. <span data-ttu-id="b731f-155">Välj den roll du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="b731f-155">Select the role you'd like to delete.</span></span>

4. <span data-ttu-id="b731f-156">Klicka på listrutan och välj Ta **bort roll.**</span><span class="sxs-lookup"><span data-stu-id="b731f-156">Click the drop-down button and select **Delete role**.</span></span>

## <a name="related-topic"></a><span data-ttu-id="b731f-157">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="b731f-157">Related topic</span></span>

- [<span data-ttu-id="b731f-158">Grundläggande behörigheter för åtkomst till portalen</span><span class="sxs-lookup"><span data-stu-id="b731f-158">User basic permissions to access the portal</span></span>](basic-permissions.md)
- [<span data-ttu-id="b731f-159">Skapa och hantera enhetsgrupper</span><span class="sxs-lookup"><span data-stu-id="b731f-159">Create and manage device groups</span></span>](machine-groups.md)
