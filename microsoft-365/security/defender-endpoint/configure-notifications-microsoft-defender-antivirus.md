---
title: Konfigurera Microsoft Defender Antivirus meddelanden
description: Lär dig hur du konfigurerar och anpassar både standardmeddelanden och Microsoft Defender Antivirus standardaviseringar på slutpunkter.
keywords: meddelanden, defender, antivirus, slutpunkt, hantering, administratör
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.topic: article
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/16/2021
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: a7a838bb15cd011b750fbfa3d6df100ddf9f713c
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985414"
---
# <a name="configure-microsoft-defender-antivirus-notifications-that-appear-on-endpoints"></a><span data-ttu-id="e3dd8-104">Konfigurera Microsoft Defender Antivirus som visas på slutpunkter</span><span class="sxs-lookup"><span data-stu-id="e3dd8-104">Configure Microsoft Defender Antivirus notifications that appear on endpoints</span></span>

<span data-ttu-id="e3dd8-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="e3dd8-105">**Applies to:**</span></span>

- [<span data-ttu-id="e3dd8-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="e3dd8-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="e3dd8-107">I Windows 10 är programmeddelanden om identifiering och åtgärder av skadlig kod mer robusta, konsekventa och koncisa.</span><span class="sxs-lookup"><span data-stu-id="e3dd8-107">In Windows 10, application notifications about malware detection and remediation are more robust, consistent, and concise.</span></span> <span data-ttu-id="e3dd8-108">Microsoft Defender Antivirus meddelanden visas på slutpunkter när genomsökningar har slutförts och hot identifieras.</span><span class="sxs-lookup"><span data-stu-id="e3dd8-108">Microsoft Defender Antivirus notifications appear on endpoints when scans are completed and threats are detected.</span></span> <span data-ttu-id="e3dd8-109">Meddelanden följer både schemalagda och manuellt utlösta genomsökningar.</span><span class="sxs-lookup"><span data-stu-id="e3dd8-109">Notifications follow both scheduled and manually triggered scans.</span></span> <span data-ttu-id="e3dd8-110">Dessa meddelanden visas också i **meddelandecentret**, och en sammanfattning av genomsökningar och identifieringar av hot visas med jämna mellanrum.</span><span class="sxs-lookup"><span data-stu-id="e3dd8-110">These notifications also appear in the **Notification Center**, and a summary of scans and threat detections appear at regular time intervals.</span></span>

<span data-ttu-id="e3dd8-111">Om du är en del av organisationens säkerhetsteam kan du konfigurera hur meddelanden visas på slutpunkter, till exempel meddelanden som uppmanar till en systemstart eller som anger att ett hot har upptäckts och åtgärdats.</span><span class="sxs-lookup"><span data-stu-id="e3dd8-111">If you're part of your organization's security team, you can configure how notifications appear on endpoints, such as notifications that prompt for a system reboot or that indicate a threat has been detected and remediated.</span></span>

## <a name="configure-antivirus-notifications-using-group-policy-or-the-windows-security-app"></a><span data-ttu-id="e3dd8-112">Konfigurera antivirusmeddelanden med grupprinciper eller Windows-säkerhet programmet</span><span class="sxs-lookup"><span data-stu-id="e3dd8-112">Configure antivirus notifications using Group Policy or the Windows Security app</span></span>

<span data-ttu-id="e3dd8-113">Du kan konfigurera visningen av ytterligare meddelanden, till exempel sammanfattningar av nya identifieringar av hot, [Windows-säkerhet appen](microsoft-defender-security-center-antivirus.md) och med Grupprincip.</span><span class="sxs-lookup"><span data-stu-id="e3dd8-113">You can configure the display of additional notifications, such as recent threat detection summaries, in the [Windows Security app](microsoft-defender-security-center-antivirus.md) and with Group Policy.</span></span>

> [!NOTE]
> <span data-ttu-id="e3dd8-114">I Windows 10 version 1607 kallades funktionen  för Utökade meddelanden och konfigurerades under **Windows Inställningar**  >  **Update & security**  >  **Windows Defender**.</span><span class="sxs-lookup"><span data-stu-id="e3dd8-114">In Windows 10, version 1607 the feature was called **Enhanced notifications** and was configured under **Windows Settings** > **Update & security** > **Windows Defender**.</span></span> <span data-ttu-id="e3dd8-115">I Grupprincipinställningar för alla versioner Windows 10 kallas meddelandefunktionen **Utökade meddelanden.**</span><span class="sxs-lookup"><span data-stu-id="e3dd8-115">In Group Policy settings for all versions of Windows 10, the notification feature is called **Enhanced notifications**.</span></span>

### <a name="use-group-policy-to-disable-additional-notifications"></a><span data-ttu-id="e3dd8-116">Använda grupprinciper för att inaktivera ytterligare meddelanden</span><span class="sxs-lookup"><span data-stu-id="e3dd8-116">Use Group Policy to disable additional notifications</span></span>

1. <span data-ttu-id="e3dd8-117">Öppna [Konsolen för grupprinciphantering](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)) på datorn för grupprinciphantering.</span><span class="sxs-lookup"><span data-stu-id="e3dd8-117">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="e3dd8-118">Högerklicka på det grupprincipobjekt du vill konfigurera och välj sedan **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="e3dd8-118">Right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

3. <span data-ttu-id="e3dd8-119">Gå till **Datorkonfiguration i redigeraren** för **grupprinciphantering.**</span><span class="sxs-lookup"><span data-stu-id="e3dd8-119">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

4. <span data-ttu-id="e3dd8-120">Välj **Administrativa mallar**.</span><span class="sxs-lookup"><span data-stu-id="e3dd8-120">Select **Administrative templates**.</span></span>

5. <span data-ttu-id="e3dd8-121">Expandera trädet och visa **Windows komponenter**  >  **Microsoft Defender Antivirus** >\*\*.</span><span class="sxs-lookup"><span data-stu-id="e3dd8-121">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > Reporting\*\*.</span></span>

6. <span data-ttu-id="e3dd8-122">Dubbelklicka på **Inaktivera utökade meddelanden och** ställ in alternativet Aktiverad . </span><span class="sxs-lookup"><span data-stu-id="e3dd8-122">Double-click **Turn off enhanced notifications**, and set the option to **Enabled**.</span></span> <span data-ttu-id="e3dd8-123">Välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="e3dd8-123">Then select **OK**.</span></span> <span data-ttu-id="e3dd8-124">Det gör att det inte visas fler meddelanden.</span><span class="sxs-lookup"><span data-stu-id="e3dd8-124">This will prevent additional notifications from appearing.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e3dd8-125">Om du inaktiverar ytterligare meddelanden inaktiveras inte kritiska meddelanden, till exempel aviseringar om identifiering av hot och åtgärder.</span><span class="sxs-lookup"><span data-stu-id="e3dd8-125">Disabling additional notifications will not disable critical notifications, such as threat detection and remediation alerts.</span></span>

### <a name="use-the-windows-security-app-to-disable-additional-notifications"></a><span data-ttu-id="e3dd8-126">Använd appen Windows-säkerhet för att inaktivera ytterligare meddelanden</span><span class="sxs-lookup"><span data-stu-id="e3dd8-126">Use the Windows Security app to disable additional notifications</span></span>

1. <span data-ttu-id="e3dd8-127">Öppna Windows-säkerhet genom att klicka på sköldikonen i aktivitetsfältet eller söka efter Säkerhet på **Start-menyn.**</span><span class="sxs-lookup"><span data-stu-id="e3dd8-127">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="e3dd8-128">Välj **Virus &** skydd mot hot (eller sköldikonen i den vänstra menyraden) och välj sedan Inställningar för & skydd mot **virus**</span><span class="sxs-lookup"><span data-stu-id="e3dd8-128">Select **Virus & threat protection** tile (or the shield icon on the left menu bar) and, then select **Virus & threat protection settings**</span></span>

3. <span data-ttu-id="e3dd8-129">Bläddra till avsnittet **Meddelanden** och välj **Ändra aviseringsinställningar**.</span><span class="sxs-lookup"><span data-stu-id="e3dd8-129">Scroll to the **Notifications** section and select **Change notification settings**.</span></span>

4. <span data-ttu-id="e3dd8-130">Dra reglaget till **Av** eller **På för** att inaktivera eller aktivera ytterligare meddelanden.</span><span class="sxs-lookup"><span data-stu-id="e3dd8-130">Slide the switch to **Off** or **On** to disable or enable additional notifications.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e3dd8-131">Om du inaktiverar ytterligare meddelanden inaktiveras inte kritiska meddelanden, till exempel aviseringar om identifiering av hot och åtgärder.</span><span class="sxs-lookup"><span data-stu-id="e3dd8-131">Disabling additional notifications will not disable critical notifications, such as threat detection and remediation alerts.</span></span>

## <a name="configure-standard-notifications-on-endpoints-using-group-policy"></a><span data-ttu-id="e3dd8-132">Konfigurera standardaviseringar på slutpunkter med grupprincip</span><span class="sxs-lookup"><span data-stu-id="e3dd8-132">Configure standard notifications on endpoints using Group Policy</span></span>

<span data-ttu-id="e3dd8-133">Du kan använda grupprinciper för att:</span><span class="sxs-lookup"><span data-stu-id="e3dd8-133">You can use Group Policy to:</span></span>

- <span data-ttu-id="e3dd8-134">Visa ytterligare, anpassad text på slutpunkter när användaren behöver utföra en åtgärd</span><span class="sxs-lookup"><span data-stu-id="e3dd8-134">Display additional, customized text on endpoints when the user needs to perform an action</span></span>
- <span data-ttu-id="e3dd8-135">Dölj alla meddelanden på slutpunkter</span><span class="sxs-lookup"><span data-stu-id="e3dd8-135">Hide all notifications on endpoints</span></span>
- <span data-ttu-id="e3dd8-136">Dölja meddelanden om omstart på slutpunkter</span><span class="sxs-lookup"><span data-stu-id="e3dd8-136">Hide reboot notifications on endpoints</span></span>

<span data-ttu-id="e3dd8-137">Att dölja meddelanden kan vara användbart i situationer där du inte kan dölja Microsoft Defender Antivirus gränssnittet.</span><span class="sxs-lookup"><span data-stu-id="e3dd8-137">Hiding notifications can be useful in situations where you can't hide the entire Microsoft Defender Antivirus interface.</span></span> <span data-ttu-id="e3dd8-138">Mer information [finns i Hindra användare från att se Microsoft Defender Antivirus interagera med användargränssnittet.](prevent-end-user-interaction-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="e3dd8-138">See [Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface](prevent-end-user-interaction-microsoft-defender-antivirus.md) for more information.</span></span> <span data-ttu-id="e3dd8-139">Om du döljer meddelanden visas det bara i slutpunkter där principen har distribuerats.</span><span class="sxs-lookup"><span data-stu-id="e3dd8-139">Hiding notifications will only occur on endpoints to which the policy has been deployed.</span></span> <span data-ttu-id="e3dd8-140">Meddelanden om åtgärder som måste vidtas (till exempel en omstart) visas fortfarande på Microsoft Endpoint Manager Endpoint Protection [och instrumentpanelen för övervakning.](/configmgr/protect/deploy-use/monitor-endpoint-protection)</span><span class="sxs-lookup"><span data-stu-id="e3dd8-140">Notifications related to actions that must be taken (such as a reboot) will still appear on the [Microsoft Endpoint Manager Endpoint Protection monitoring dashboard and reports](/configmgr/protect/deploy-use/monitor-endpoint-protection).</span></span> 

<span data-ttu-id="e3dd8-141">Om du vill lägga till anpassad kontaktinformation i slutpunktsaviseringar går du [till Anpassa Windows-säkerhet för din organisation.](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)</span><span class="sxs-lookup"><span data-stu-id="e3dd8-141">To add custom contact information to endpoint notifications, see [Customize the Windows Security app for your organization](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center).</span></span>

### <a name="use-group-policy-to-hide-notifications"></a><span data-ttu-id="e3dd8-142">Använda grupprinciper för att dölja meddelanden</span><span class="sxs-lookup"><span data-stu-id="e3dd8-142">Use Group Policy to hide notifications</span></span>

1. <span data-ttu-id="e3dd8-143">Öppna [Konsolen för grupprinciphantering](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)) på datorn för grupprinciphantering.</span><span class="sxs-lookup"><span data-stu-id="e3dd8-143">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="e3dd8-144">Högerklicka på det grupprincipobjekt du vill konfigurera och välj sedan **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="e3dd8-144">Right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

3. <span data-ttu-id="e3dd8-145">I **redigeraren för grupprinciphantering** går du **till Datorkonfiguration** och väljer sedan **Administrativa mallar**.</span><span class="sxs-lookup"><span data-stu-id="e3dd8-145">In the **Group Policy Management Editor** go to **Computer configuration** and then select **Administrative templates**.</span></span>

4. <span data-ttu-id="e3dd8-146">Expandera trädet till en **Windows Microsoft Defender Antivirus**  >    >  **klientgränssnittet**.</span><span class="sxs-lookup"><span data-stu-id="e3dd8-146">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Client interface**.</span></span> 

5. <span data-ttu-id="e3dd8-147">Dubbelklicka på **Ignorera alla meddelanden** och ange alternativet **Aktiverad**.</span><span class="sxs-lookup"><span data-stu-id="e3dd8-147">Double-click **Suppress all notifications** and set the option to **Enabled**.</span></span> 

6. <span data-ttu-id="e3dd8-148">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="e3dd8-148">Select **OK**.</span></span> <span data-ttu-id="e3dd8-149">Det gör att det inte visas fler meddelanden.</span><span class="sxs-lookup"><span data-stu-id="e3dd8-149">This will prevent additional notifications from appearing.</span></span>

### <a name="use-group-policy-to-hide-reboot-notifications"></a><span data-ttu-id="e3dd8-150">Använd grupprinciper för att dölja meddelanden om omstart</span><span class="sxs-lookup"><span data-stu-id="e3dd8-150">Use Group Policy to hide reboot notifications</span></span>

1. <span data-ttu-id="e3dd8-151">Öppna [Konsolen för grupprinciphantering](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)) på datorn för grupprinciphantering.</span><span class="sxs-lookup"><span data-stu-id="e3dd8-151">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="e3dd8-152">Högerklicka på det grupprincipobjekt du vill konfigurera och välj sedan **Redigera.**</span><span class="sxs-lookup"><span data-stu-id="e3dd8-152">Right-click the Group Policy Object you want to configure and then select **Edit**.</span></span>

2. <span data-ttu-id="e3dd8-153">Gå till **Datorkonfiguration i redigeraren** för **grupprinciphantering.**</span><span class="sxs-lookup"><span data-stu-id="e3dd8-153">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="e3dd8-154">Klicka **på Administrativa mallar**.</span><span class="sxs-lookup"><span data-stu-id="e3dd8-154">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="e3dd8-155">Expandera trädet till en **Windows Microsoft Defender Antivirus**  >    >  **klientgränssnittet**.</span><span class="sxs-lookup"><span data-stu-id="e3dd8-155">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Client interface**.</span></span>

5. <span data-ttu-id="e3dd8-156">Dubbelklicka på Ignorera **meddelanden vid omstart och** ställ in alternativet **Aktiverad**.</span><span class="sxs-lookup"><span data-stu-id="e3dd8-156">Double-click **Suppresses reboot notifications** and set the option to **Enabled**.</span></span> 

5. <span data-ttu-id="e3dd8-157">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="e3dd8-157">Select **OK**.</span></span> <span data-ttu-id="e3dd8-158">Det gör att det inte visas fler meddelanden.</span><span class="sxs-lookup"><span data-stu-id="e3dd8-158">This will prevent additional notifications from appearing.</span></span>

