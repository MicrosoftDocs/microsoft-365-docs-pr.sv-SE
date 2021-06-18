---
title: Dölja Microsoft Defender Antivirus gränssnittet
description: Du kan dölja panel för skydd mot virus och hot Windows-säkerhet appen.
keywords: nedlåst gränssnitt, huvudlöst läge, dölja app, dölja inställningar, dölja gränssnitt
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: ff0e134d38288b12cbc46dc3ca5f103fbf8c7ad9
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007675"
---
# <a name="prevent-users-from-seeing-or-interacting-with-the-microsoft-defender-antivirus-user-interface"></a><span data-ttu-id="3f960-104">Hindra användare från att se eller interagera Microsoft Defender Antivirus användargränssnittet</span><span class="sxs-lookup"><span data-stu-id="3f960-104">Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="3f960-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="3f960-105">**Applies to:**</span></span>

- [<span data-ttu-id="3f960-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="3f960-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="3f960-107">Du kan använda Grupprincip för att hindra användare i slutpunkter från att se Microsoft Defender Antivirus gränssnitt.</span><span class="sxs-lookup"><span data-stu-id="3f960-107">You can use Group Policy to prevent users on endpoints from seeing the Microsoft Defender Antivirus interface.</span></span> <span data-ttu-id="3f960-108">Du kan också förhindra att genomsökningar pausas.</span><span class="sxs-lookup"><span data-stu-id="3f960-108">You can also prevent them from pausing scans.</span></span>

## <a name="hide-the-microsoft-defender-antivirus-interface"></a><span data-ttu-id="3f960-109">Dölja Microsoft Defender Antivirus gränssnittet</span><span class="sxs-lookup"><span data-stu-id="3f960-109">Hide the Microsoft Defender Antivirus interface</span></span>

<span data-ttu-id="3f960-110">I Windows 10 version 1703 döljs Microsoft Defender Antivirus-meddelanden och skyddspanelen för Virus & förhindras från att visas i Windows-säkerhet-appen.</span><span class="sxs-lookup"><span data-stu-id="3f960-110">In Windows 10, versions 1703, hiding the interface will hide Microsoft Defender Antivirus notifications and prevent the Virus & threat protection tile from appearing in the Windows Security app.</span></span>

<span data-ttu-id="3f960-111">Med inställningen **aktiverad:**</span><span class="sxs-lookup"><span data-stu-id="3f960-111">With the setting set to **Enabled**:</span></span>

:::image type="content" source="../../media/wdav-headless-mode-1703.png" alt-text="Windows-säkerhet utan sköldikonen och avsnittet om skydd mot virus och hot":::

<span data-ttu-id="3f960-113">Med inställningen inställd på **Inaktiverad** eller ej konfigurerad:</span><span class="sxs-lookup"><span data-stu-id="3f960-113">With the setting set to **Disabled** or not configured:</span></span>

:::image type="content" source="../../media/wdav-headless-mode-1703.png" alt-text="Skärmbild av Windows-säkerhet med avsnitten sköldikon och skydd mot hot":::

>[!NOTE]
><span data-ttu-id="3f960-115">Om du döljer gränssnittet förhindras Microsoft Defender Antivirus meddelanden från att visas på slutpunkten.</span><span class="sxs-lookup"><span data-stu-id="3f960-115">Hiding the interface will also prevent Microsoft Defender Antivirus notifications from appearing on the endpoint.</span></span> <span data-ttu-id="3f960-116">Microsoft Defender för slutpunktsmeddelanden visas fortfarande.</span><span class="sxs-lookup"><span data-stu-id="3f960-116">Microsoft Defender for Endpoint notifications will still appear.</span></span> <span data-ttu-id="3f960-117">Du kan också [individuellt konfigurera meddelanden som visas på slutpunkter](configure-notifications-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="3f960-117">You can also individually [configure the notifications that appear on endpoints](configure-notifications-microsoft-defender-antivirus.md)</span></span>

<span data-ttu-id="3f960-118">I tidigare Windows 10 döljs klientgränssnittet i Windows Defender inställningar.</span><span class="sxs-lookup"><span data-stu-id="3f960-118">In earlier versions of Windows 10, the setting will hide the Windows Defender client interface.</span></span> <span data-ttu-id="3f960-119">Om användaren försöker öppna den får de ett varningsmeddelande där det står "Systemadministratören har begränsad åtkomst till den här appen".</span><span class="sxs-lookup"><span data-stu-id="3f960-119">If the user attempts to open it, they will receive a warning that says, "Your system administrator has restricted access to this app."</span></span>

:::image type="content" source="../../media/wdav-headless-mode-1607.png" alt-text="Varningsmeddelande när huvudlöst läge är aktiverat i Windows 10, tidigare versioner än 1703":::

## <a name="use-group-policy-to-hide-the-microsoft-defender-av-interface-from-users"></a><span data-ttu-id="3f960-121">Använda grupprinciper för att dölja Microsoft Defender AV-gränssnittet för användare</span><span class="sxs-lookup"><span data-stu-id="3f960-121">Use Group Policy to hide the Microsoft Defender AV interface from users</span></span>

1. <span data-ttu-id="3f960-122">På hanteringsdatorn för grupprinciper öppnar du [Konsolen](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)för grupprinciphantering, högerklickar på det grupprincipobjekt du vill konfigurera och klickar på **Redigera.**</span><span class="sxs-lookup"><span data-stu-id="3f960-122">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="3f960-123">Med **grupprinciphanteringsredigeraren går** du till **Datorkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="3f960-123">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="3f960-124">Klicka **på Administrativa mallar**.</span><span class="sxs-lookup"><span data-stu-id="3f960-124">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="3f960-125">Expandera trädet och visa **Windows i > Microsoft Defender Antivirus > klientgränssnittet.**</span><span class="sxs-lookup"><span data-stu-id="3f960-125">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span>

5. <span data-ttu-id="3f960-126">Dubbelklicka på inställningen Aktivera **huvudlöst gränssnittsläge** och ange alternativet **Aktiverad**.</span><span class="sxs-lookup"><span data-stu-id="3f960-126">Double-click the **Enable headless UI mode** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="3f960-127">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="3f960-127">Click **OK**.</span></span> 

<span data-ttu-id="3f960-128">Mer [information om hur du hindrar användare från att](configure-local-policy-overrides-microsoft-defender-antivirus.md) ändra skydd på datorer finns i Hindra användare från att ändra principinställningar lokalt.</span><span class="sxs-lookup"><span data-stu-id="3f960-128">See [Prevent users from locally modifying policy settings](configure-local-policy-overrides-microsoft-defender-antivirus.md) for more options on preventing users form modifying protection on their PCs.</span></span>

## <a name="prevent-users-from-pausing-a-scan"></a><span data-ttu-id="3f960-129">Hindra användare från att pausa en genomsökning</span><span class="sxs-lookup"><span data-stu-id="3f960-129">Prevent users from pausing a scan</span></span>

<span data-ttu-id="3f960-130">Du kan förhindra att användare pausar genomsökningar, vilket kan vara användbart för att säkerställa att schemalagda eller on-demand-sökningar inte avbryts av användarna.</span><span class="sxs-lookup"><span data-stu-id="3f960-130">You can prevent users from pausing scans, which can be helpful to ensure scheduled or on-demand scans are not interrupted by users.</span></span>

> [!NOTE]
> <span data-ttu-id="3f960-131">Den här inställningen stöds inte på Windows 10.</span><span class="sxs-lookup"><span data-stu-id="3f960-131">This setting is not supported on Windows 10.</span></span>

### <a name="use-group-policy-to-prevent-users-from-pausing-a-scan"></a><span data-ttu-id="3f960-132">Använda grupprinciper för att hindra användare från att pausa en genomsökning</span><span class="sxs-lookup"><span data-stu-id="3f960-132">Use Group Policy to prevent users from pausing a scan</span></span>

1. <span data-ttu-id="3f960-133">På hanteringsdatorn för grupprinciper öppnar du [Konsolen](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)för grupprinciphantering, högerklickar på det grupprincipobjekt du vill konfigurera och klickar på **Redigera.**</span><span class="sxs-lookup"><span data-stu-id="3f960-133">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="3f960-134">Med **grupprinciphanteringsredigeraren går** du till **Datorkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="3f960-134">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="3f960-135">Klicka **på Administrativa mallar**.</span><span class="sxs-lookup"><span data-stu-id="3f960-135">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="3f960-136">Expandera trädet för att **Windows komponenter**  >  **Microsoft Defender Antivirus**  >  **Sök**.</span><span class="sxs-lookup"><span data-stu-id="3f960-136">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

5. <span data-ttu-id="3f960-137">Dubbelklicka på inställningen Tillåt **användare att pausa genomsökning** och ange alternativet **Inaktiverad**.</span><span class="sxs-lookup"><span data-stu-id="3f960-137">Double-click the **Allow users to pause scan** setting and set the option to **Disabled**.</span></span> <span data-ttu-id="3f960-138">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="3f960-138">Click **OK**.</span></span> 

## <a name="related-articles"></a><span data-ttu-id="3f960-139">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="3f960-139">Related articles</span></span>

- [<span data-ttu-id="3f960-140">Konfigurera meddelanden som visas på slutpunkter</span><span class="sxs-lookup"><span data-stu-id="3f960-140">Configure the notifications that appear on endpoints</span></span>](configure-notifications-microsoft-defender-antivirus.md)

- [<span data-ttu-id="3f960-141">Konfigurera slutanvändares interaktion med Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="3f960-141">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md)

- [<span data-ttu-id="3f960-142">Microsoft Defender Antivirus i Windows 10</span><span class="sxs-lookup"><span data-stu-id="3f960-142">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)