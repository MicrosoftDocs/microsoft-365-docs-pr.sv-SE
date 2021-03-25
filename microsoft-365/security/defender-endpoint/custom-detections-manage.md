---
title: Visa och hantera regler för anpassad identifiering i Microsoft Defender ATP
ms.reviewer: ''
description: Lär dig hur du visar och hanterar anpassade identifieringsregler
keywords: anpassade identifieringar, visa, hantera, aviseringar, redigera, köra på begäran, identifieringsregler, avancerad sökning, sökning, fråga, svarsåtgärder, mdatp, microsoft defender atp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f6a7fc4d4141b19f9c5129eea9b89943d07695b2
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165783"
---
# <a name="view-and-manage-custom-detection-rules"></a><span data-ttu-id="51305-104">Visa och hantera anpassade identifieringsregler</span><span class="sxs-lookup"><span data-stu-id="51305-104">View and manage custom detection rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="51305-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="51305-105">**Applies to:**</span></span>
- [<span data-ttu-id="51305-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="51305-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="51305-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="51305-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="51305-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="51305-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="51305-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="51305-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="51305-110">Hantera dina befintliga [anpassade identifieringsregler för](custom-detection-rules.md) att säkerställa att de effektivt hittar hot och vidtar åtgärder.</span><span class="sxs-lookup"><span data-stu-id="51305-110">Manage your existing [custom detection rules](custom-detection-rules.md) to ensure they are effectively finding threats and taking actions.</span></span> <span data-ttu-id="51305-111">Lär dig hur du visar listan med regler, kontrollerar deras tidigare körningar och granskar aviseringarna som de har utlöst.</span><span class="sxs-lookup"><span data-stu-id="51305-111">Explore how to view the list of rules, check their previous runs, and review the alerts they have triggered.</span></span> <span data-ttu-id="51305-112">Du kan även köra en regel på begäran och ändra den.</span><span class="sxs-lookup"><span data-stu-id="51305-112">You can also run a rule on demand and modify it.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="51305-113">Behörighet som krävs</span><span class="sxs-lookup"><span data-stu-id="51305-113">Required permissions</span></span>

<span data-ttu-id="51305-114">För att skapa eller hantera anpassade identifieringar [måste din roll](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) ha behörighet att hantera **säkerhetsinställningar.**</span><span class="sxs-lookup"><span data-stu-id="51305-114">To create or manage custom detections, [your role](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) needs to have the **manage security settings** permission.</span></span>

## <a name="view-existing-rules"></a><span data-ttu-id="51305-115">Visa befintliga regler</span><span class="sxs-lookup"><span data-stu-id="51305-115">View existing rules</span></span>

<span data-ttu-id="51305-116">Om du vill visa alla befintliga anpassade identifieringsregler går du **till Inställningar**  >  **anpassade identifieringar**.</span><span class="sxs-lookup"><span data-stu-id="51305-116">To view all existing custom detection rules, navigate to **Settings** > **Custom detections**.</span></span> <span data-ttu-id="51305-117">På sidan visas alla regler med följande körningsinformation:</span><span class="sxs-lookup"><span data-stu-id="51305-117">The page lists all the rules with the following run information:</span></span>

- <span data-ttu-id="51305-118">**Senaste körningen**– när en regel senast körts för att söka efter frågematchningar och generera aviseringar</span><span class="sxs-lookup"><span data-stu-id="51305-118">**Last run**—when a rule was last run to check for query matches and generate alerts</span></span>
- <span data-ttu-id="51305-119">**Status för senaste körningen**– om en regel kördes som den ska</span><span class="sxs-lookup"><span data-stu-id="51305-119">**Last run status**—whether a rule ran successfully</span></span>
- <span data-ttu-id="51305-120">**Nästa körning**– nästa schemalagda körning</span><span class="sxs-lookup"><span data-stu-id="51305-120">**Next run**—the next scheduled run</span></span>
- <span data-ttu-id="51305-121">**Status**– om en regel har aktiverats eller inaktiverats</span><span class="sxs-lookup"><span data-stu-id="51305-121">**Status**—whether a rule has been turned on or off</span></span>

## <a name="view-rule-details-modify-rule-and-run-rule"></a><span data-ttu-id="51305-122">Visa regeldetaljer, ändra regel och köra regel</span><span class="sxs-lookup"><span data-stu-id="51305-122">View rule details, modify rule, and run rule</span></span>

<span data-ttu-id="51305-123">Om du vill visa omfattande information om en anpassad identifieringsregel väljer du namnet på regeln i listan med regler **i Inställningar**  >  **Anpassade identifieringar.**</span><span class="sxs-lookup"><span data-stu-id="51305-123">To view comprehensive information about a custom detection rule, select the name of rule from the list of rules in **Settings** > **Custom detections**.</span></span> <span data-ttu-id="51305-124">En sida om den valda regeln visar följande information:</span><span class="sxs-lookup"><span data-stu-id="51305-124">A page about the selected rule displays the following information:</span></span>

- <span data-ttu-id="51305-125">Allmän information om regeln, inklusive information om aviseringen, körningsstatus och omfattning</span><span class="sxs-lookup"><span data-stu-id="51305-125">General information about the rule, including the details of the alert, run status, and scope</span></span>
- <span data-ttu-id="51305-126">Lista med utlösta aviseringar</span><span class="sxs-lookup"><span data-stu-id="51305-126">List of triggered alerts</span></span>
- <span data-ttu-id="51305-127">Lista över utlösande åtgärder</span><span class="sxs-lookup"><span data-stu-id="51305-127">List of triggered actions</span></span>

<span data-ttu-id="51305-128">![Sidan Anpassad identifieringsregel](images/atp-custom-detection-rule-details.png)</span><span class="sxs-lookup"><span data-stu-id="51305-128">![Custom detection rule page](images/atp-custom-detection-rule-details.png)</span></span><br>
<span data-ttu-id="51305-129">*Sidan Anpassad identifieringsregel*</span><span class="sxs-lookup"><span data-stu-id="51305-129">*Custom detection rule page*</span></span>

<span data-ttu-id="51305-130">Du kan också utföra följande åtgärder på regeln från den här sidan:</span><span class="sxs-lookup"><span data-stu-id="51305-130">You can also take the following actions on the rule from this page:</span></span>

- <span data-ttu-id="51305-131">**Kör**– kör regeln direkt.</span><span class="sxs-lookup"><span data-stu-id="51305-131">**Run**—run the rule immediately.</span></span> <span data-ttu-id="51305-132">Den här åtgärden återställer också intervallet för nästa körning.</span><span class="sxs-lookup"><span data-stu-id="51305-132">This action also resets the interval for the next run.</span></span>
- <span data-ttu-id="51305-133">**Redigera**– ändra regeln utan att ändra frågan</span><span class="sxs-lookup"><span data-stu-id="51305-133">**Edit**—modify the rule without changing the query</span></span>
- <span data-ttu-id="51305-134">**Ändra fråga**– redigera frågan under avancerad sökning</span><span class="sxs-lookup"><span data-stu-id="51305-134">**Modify query**—edit the query in advanced hunting</span></span>
- <span data-ttu-id="51305-135">**Aktivera**  /  **Inaktivera –** aktivera regeln eller hindra den från att köras</span><span class="sxs-lookup"><span data-stu-id="51305-135">**Turn on** / **Turn off**—enable the rule or stop it from running</span></span>
- <span data-ttu-id="51305-136">**Ta** bort – inaktivera regeln och ta bort den</span><span class="sxs-lookup"><span data-stu-id="51305-136">**Delete**—turn off the rule and remove it</span></span>

>[!TIP]
><span data-ttu-id="51305-137">Om du snabbt vill visa information och vidta åtgärder för ett objekt i en tabell använder du urvalskolumnen [&#10003;] till vänster om tabellen.</span><span class="sxs-lookup"><span data-stu-id="51305-137">To quickly view information and take action on an item in a table, use the selection column [&#10003;] at the left of the table.</span></span>

## <a name="related-topics"></a><span data-ttu-id="51305-138">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="51305-138">Related topics</span></span>
- [<span data-ttu-id="51305-139">Översikt över anpassade identifieringar</span><span class="sxs-lookup"><span data-stu-id="51305-139">Custom detections overview</span></span>](overview-custom-detections.md)
- [<span data-ttu-id="51305-140">Skapa identifieringsregler</span><span class="sxs-lookup"><span data-stu-id="51305-140">Create detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="51305-141">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="51305-141">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="51305-142">Visa och ordna aviseringar</span><span class="sxs-lookup"><span data-stu-id="51305-142">View and organize alerts</span></span>](alerts-queue.md)
