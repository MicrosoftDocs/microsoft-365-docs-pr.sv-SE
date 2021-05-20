---
title: Konfigurera Microsoft Defender Antivirus meddelanden
description: Lär dig hur du konfigurerar och anpassar både standard- och Microsoft Defender Antivirus meddelanden om slutpunkter.
keywords: meddelanden, försvarare, antivirus, slutpunkt, hantering, admin
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/17/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: f885b6d7991e4175cd14be5bbe9e0a7c96b1580f
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572351"
---
# <a name="configure-the-notifications-that-appear-on-endpoints"></a><span data-ttu-id="c3ca9-104">Konfigurera meddelandena som visas på slutpunkter</span><span class="sxs-lookup"><span data-stu-id="c3ca9-104">Configure the notifications that appear on endpoints</span></span>

<span data-ttu-id="c3ca9-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="c3ca9-105">**Applies to:**</span></span>

- [<span data-ttu-id="c3ca9-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="c3ca9-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="c3ca9-107">I Windows 10 program meddelanden om identifiering och reparation av skadlig kod mer robusta, konsekventa och koncisa.</span><span class="sxs-lookup"><span data-stu-id="c3ca9-107">In Windows 10, application notifications about malware detection and remediation are more robust, consistent, and concise.</span></span>

<span data-ttu-id="c3ca9-108">Meddelanden visas på slutpunkter när de utlöses manuellt och schemalagda genomsökningar slutförs och hot upptäcks.</span><span class="sxs-lookup"><span data-stu-id="c3ca9-108">Notifications appear on endpoints when manually triggered and scheduled scans are completed and threats are detected.</span></span> <span data-ttu-id="c3ca9-109">Dessa meddelanden visas också i **Meddelandecenter och** en sammanfattning av genomsökningar och hot identifieringar visas med jämna mellanrum.</span><span class="sxs-lookup"><span data-stu-id="c3ca9-109">These notifications also appear in the **Notification Center**, and a summary of scans and threat detections appear at regular time intervals.</span></span>

<span data-ttu-id="c3ca9-110">Du kan också konfigurera hur standardaviseringar visas på slutpunkter, till exempel meddelanden för omstart eller när ett hot har upptäckts och åtgärdats.</span><span class="sxs-lookup"><span data-stu-id="c3ca9-110">You can also configure how standard notifications appear on endpoints, such as notifications for reboot or when a threat has been detected and remediated.</span></span>

## <a name="configure-the-additional-notifications-that-appear-on-endpoints"></a><span data-ttu-id="c3ca9-111">Konfigurera de ytterligare meddelanden som visas på slutpunkter</span><span class="sxs-lookup"><span data-stu-id="c3ca9-111">Configure the additional notifications that appear on endpoints</span></span>

<span data-ttu-id="c3ca9-112">Du kan konfigurera visningen av ytterligare meddelanden, till exempel de senaste sammanfattningarna av hotidentifiering, [i Windows-säkerhet-appen](microsoft-defender-security-center-antivirus.md) och med Grupprincip.</span><span class="sxs-lookup"><span data-stu-id="c3ca9-112">You can configure the display of additional notifications, such as recent threat detection summaries, in the [Windows Security app](microsoft-defender-security-center-antivirus.md) and with Group Policy.</span></span>

> [!NOTE]
> <span data-ttu-id="c3ca9-113">I Windows 10, version 1607, kallades funktionen **förbättrade meddelanden** och kunde konfigureras under **Windows Inställningar** Update  >  **& säkerhets**  >  **Windows Defender**.</span><span class="sxs-lookup"><span data-stu-id="c3ca9-113">In Windows 10, version 1607 the feature was called **Enhanced notifications** and could be configured under **Windows Settings** > **Update & security** > **Windows Defender**.</span></span> <span data-ttu-id="c3ca9-114">I grupprincipinställningar i alla versioner Windows 10 kallas det **förbättrade meddelanden**.</span><span class="sxs-lookup"><span data-stu-id="c3ca9-114">In Group Policy settings in all versions of Windows 10, it is called **Enhanced notifications**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c3ca9-115">Om du inaktiverar ytterligare meddelanden inaktiveras inte kritiska meddelanden, till exempel aviseringar om hot identifiering och reparation.</span><span class="sxs-lookup"><span data-stu-id="c3ca9-115">Disabling additional notifications will not disable critical notifications, such as threat detection and remediation alerts.</span></span>

<span data-ttu-id="c3ca9-116">**Använd appen Windows-säkerhet för att inaktivera ytterligare meddelanden:**</span><span class="sxs-lookup"><span data-stu-id="c3ca9-116">**Use the Windows Security app to disable additional notifications:**</span></span>

1. <span data-ttu-id="c3ca9-117">Öppna appen Windows-säkerhet genom att klicka på sköldikonen i Aktivitetsfältet eller söka på Start-menyn för **Säkerhet**.</span><span class="sxs-lookup"><span data-stu-id="c3ca9-117">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="c3ca9-118">Välj **Virus & hotskyddspanelen** (eller sköldikonen på den vänstra menyraden) och **välj sedan Virus & inställningar för skydd mot hot**</span><span class="sxs-lookup"><span data-stu-id="c3ca9-118">Select **Virus & threat protection** tile (or the shield icon on the left menu bar) and, then select **Virus & threat protection settings**</span></span>

3. <span data-ttu-id="c3ca9-119">Bläddra till avsnittet **Meddelanden** och klicka på **Ändra meddelandeinställningar**.</span><span class="sxs-lookup"><span data-stu-id="c3ca9-119">Scroll to the **Notifications** section and click **Change notification settings**.</span></span>

4. <span data-ttu-id="c3ca9-120">Skjut omkopplaren till **Av** eller **På för** att inaktivera eller aktivera ytterligare meddelanden.</span><span class="sxs-lookup"><span data-stu-id="c3ca9-120">Slide the switch to **Off** or **On** to disable or enable additional notifications.</span></span>

<span data-ttu-id="c3ca9-121">**Använd grupprincip för att inaktivera ytterligare meddelanden:**</span><span class="sxs-lookup"><span data-stu-id="c3ca9-121">**Use Group Policy to disable additional notifications:**</span></span>

1. <span data-ttu-id="c3ca9-122">Öppna konsolen Grupprinciphantering på datorn [grupprinciphantering](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))och högerklicka på det grupprincipobjekt som du vill konfigurera och klicka på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="c3ca9-122">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="c3ca9-123">Gå till **Datorkonfiguration i Redigeraren** **för grupprinciphantering**.</span><span class="sxs-lookup"><span data-stu-id="c3ca9-123">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="c3ca9-124">Klicka **på Administrativa mallar**.</span><span class="sxs-lookup"><span data-stu-id="c3ca9-124">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="c3ca9-125">Expandera trädet **Windows komponenter > Microsoft Defender Antivirus > rapportering**.</span><span class="sxs-lookup"><span data-stu-id="c3ca9-125">Expand the tree to **Windows components > Microsoft Defender Antivirus > Reporting**.</span></span>

5. <span data-ttu-id="c3ca9-126">Dubbelklicka **på Inaktivera förbättrade meddelanden** och ställ in alternativet på **Aktiverad**.</span><span class="sxs-lookup"><span data-stu-id="c3ca9-126">Double-click **Turn off enhanced notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="c3ca9-127">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="c3ca9-127">Click **OK**.</span></span> <span data-ttu-id="c3ca9-128">Detta förhindrar att ytterligare meddelanden visas.</span><span class="sxs-lookup"><span data-stu-id="c3ca9-128">This will prevent additional notifications from appearing.</span></span>

## <a name="configure-standard-notifications-on-endpoints"></a><span data-ttu-id="c3ca9-129">Konfigurera standardmeddelanden på slutpunkter</span><span class="sxs-lookup"><span data-stu-id="c3ca9-129">Configure standard notifications on endpoints</span></span>

<span data-ttu-id="c3ca9-130">Du kan använda Grupprincip för att:</span><span class="sxs-lookup"><span data-stu-id="c3ca9-130">You can use Group Policy to:</span></span>

- <span data-ttu-id="c3ca9-131">Visa ytterligare, anpassad text på slutpunkter när användaren behöver utföra en åtgärd</span><span class="sxs-lookup"><span data-stu-id="c3ca9-131">Display additional, customized text on endpoints when the user needs to perform an action</span></span>
- <span data-ttu-id="c3ca9-132">Dölja alla meddelanden på slutpunkter</span><span class="sxs-lookup"><span data-stu-id="c3ca9-132">Hide all notifications on endpoints</span></span>
- <span data-ttu-id="c3ca9-133">Dölja omstartsmeddelanden på slutpunkter</span><span class="sxs-lookup"><span data-stu-id="c3ca9-133">Hide reboot notifications on endpoints</span></span>

<span data-ttu-id="c3ca9-134">Att dölja aviseringar kan vara användbart i situationer där du inte kan dölja hela Microsoft Defender Antivirus gränssnittet.</span><span class="sxs-lookup"><span data-stu-id="c3ca9-134">Hiding notifications can be useful in situations where you can't hide the entire Microsoft Defender Antivirus interface.</span></span> <span data-ttu-id="c3ca9-135">Se [Förhindra att användare ser eller interagerar med Microsoft Defender Antivirus för](prevent-end-user-interaction-microsoft-defender-antivirus.md) mer information.</span><span class="sxs-lookup"><span data-stu-id="c3ca9-135">See [Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface](prevent-end-user-interaction-microsoft-defender-antivirus.md) for more information.</span></span> 

> [!NOTE]
> <span data-ttu-id="c3ca9-136">Att dölja meddelanden kommer bara att ske på punkter som principen har distribuerats till.</span><span class="sxs-lookup"><span data-stu-id="c3ca9-136">Hiding notifications will only occur on endpoints to which the policy has been deployed.</span></span> <span data-ttu-id="c3ca9-137">Meddelanden relaterade till åtgärder som måste vidtas (till exempel en omstart) visas fortfarande på [Microsoft Endpoint Manager Endpoint Protection övervakningspanelen och rapporterna](/configmgr/protect/deploy-use/monitor-endpoint-protection).</span><span class="sxs-lookup"><span data-stu-id="c3ca9-137">Notifications related to actions that must be taken (such as a reboot) will still appear on the [Microsoft Endpoint Manager Endpoint Protection monitoring dashboard and reports](/configmgr/protect/deploy-use/monitor-endpoint-protection).</span></span> 

<span data-ttu-id="c3ca9-138">Se [Anpassa Windows-säkerhet för din organisation för instruktioner](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) om hur du lägger till anpassad kontaktinformation i de aviseringar som användarna ser på sina datorer.</span><span class="sxs-lookup"><span data-stu-id="c3ca9-138">See [Customize the Windows Security app for your organization](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) for instructions to add custom contact information to the notifications that users see on their machines.</span></span>

<span data-ttu-id="c3ca9-139">**Använd Grupprincip för att dölja meddelanden:**</span><span class="sxs-lookup"><span data-stu-id="c3ca9-139">**Use Group Policy to hide notifications:**</span></span>

1. <span data-ttu-id="c3ca9-140">Öppna konsolen Grupprinciphantering på datorn [grupprinciphantering](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), högerklicka på det grupprincipobjekt som du vill konfigurera och klicka på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="c3ca9-140">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure, and click **Edit**.</span></span>

2. <span data-ttu-id="c3ca9-141">Gå till **Datorkonfiguration i Redigeraren** **för grupprinciphantering** och klicka **på Administrativa mallar**.</span><span class="sxs-lookup"><span data-stu-id="c3ca9-141">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="c3ca9-142">Expandera trädet Windows **komponenter > Microsoft Defender Antivirus > klientgränssnittet**.</span><span class="sxs-lookup"><span data-stu-id="c3ca9-142">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span> 

4. <span data-ttu-id="c3ca9-143">Dubbelklicka **på Ignorera alla meddelanden** och ange alternativet **Aktiverad**.</span><span class="sxs-lookup"><span data-stu-id="c3ca9-143">Double-click **Suppress all notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="c3ca9-144">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="c3ca9-144">Click **OK**.</span></span> <span data-ttu-id="c3ca9-145">Detta förhindrar att ytterligare meddelanden visas.</span><span class="sxs-lookup"><span data-stu-id="c3ca9-145">This will prevent additional notifications from appearing.</span></span>

<span data-ttu-id="c3ca9-146">**Använd Grupprincip för att dölja omstartsmeddelanden:**</span><span class="sxs-lookup"><span data-stu-id="c3ca9-146">**Use Group Policy to hide reboot notifications:**</span></span>

1. <span data-ttu-id="c3ca9-147">Öppna konsolen Grupprinciphantering på datorn [grupprinciphantering](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))och högerklicka på det grupprincipobjekt som du vill konfigurera och klicka på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="c3ca9-147">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="c3ca9-148">Gå till **Datorkonfiguration i Redigeraren** **för grupprinciphantering**.</span><span class="sxs-lookup"><span data-stu-id="c3ca9-148">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="c3ca9-149">Klicka **på Administrativa mallar**.</span><span class="sxs-lookup"><span data-stu-id="c3ca9-149">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="c3ca9-150">Expandera trädet Windows **komponenter > Microsoft Defender Antivirus > klientgränssnittet**.</span><span class="sxs-lookup"><span data-stu-id="c3ca9-150">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span>

5. <span data-ttu-id="c3ca9-151">Dubbelklicka **på Ignorerar omstartsmeddelanden** och ställer in alternativet till **Aktiverad**.</span><span class="sxs-lookup"><span data-stu-id="c3ca9-151">Double-click **Suppresses reboot notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="c3ca9-152">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="c3ca9-152">Click **OK**.</span></span> <span data-ttu-id="c3ca9-153">Detta förhindrar att ytterligare meddelanden visas.</span><span class="sxs-lookup"><span data-stu-id="c3ca9-153">This will prevent additional notifications from appearing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c3ca9-154">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="c3ca9-154">Related topics</span></span>

- [<span data-ttu-id="c3ca9-155">Microsoft Defender Antivirus i Windows 10</span><span class="sxs-lookup"><span data-stu-id="c3ca9-155">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="c3ca9-156">Konfigurera slutanvändarinteraktion med Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="c3ca9-156">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md)
