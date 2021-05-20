---
title: Konfigurera Microsoft Defender Antivirus meddelanden
description: Lär dig hur du konfigurerar och anpassar både standard- och Microsoft Defender Antivirus standardaviseringar på slutpunkter.
keywords: meddelanden, defender, antivirus, slutpunkt, hantering, administratör
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
# <a name="configure-the-notifications-that-appear-on-endpoints"></a><span data-ttu-id="67f24-104">Konfigurera meddelanden som visas på slutpunkter</span><span class="sxs-lookup"><span data-stu-id="67f24-104">Configure the notifications that appear on endpoints</span></span>

<span data-ttu-id="67f24-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="67f24-105">**Applies to:**</span></span>

- [<span data-ttu-id="67f24-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="67f24-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="67f24-107">I Windows 10 är programmeddelanden om identifiering och åtgärder av skadlig kod mer robusta, konsekventa och koncisa.</span><span class="sxs-lookup"><span data-stu-id="67f24-107">In Windows 10, application notifications about malware detection and remediation are more robust, consistent, and concise.</span></span>

<span data-ttu-id="67f24-108">Meddelanden visas på slutpunkter när manuellt utlösta och schemalagda genomsökningar har slutförts och hot identifieras.</span><span class="sxs-lookup"><span data-stu-id="67f24-108">Notifications appear on endpoints when manually triggered and scheduled scans are completed and threats are detected.</span></span> <span data-ttu-id="67f24-109">Dessa meddelanden visas också i **meddelandecentret**, och en sammanfattning av genomsökningar och identifieringar av hot visas med jämna mellanrum.</span><span class="sxs-lookup"><span data-stu-id="67f24-109">These notifications also appear in the **Notification Center**, and a summary of scans and threat detections appear at regular time intervals.</span></span>

<span data-ttu-id="67f24-110">Du kan också konfigurera hur standardmeddelanden visas på slutpunkter, till exempel meddelanden för omstart eller när ett hot har upptäckts och åtgärdats.</span><span class="sxs-lookup"><span data-stu-id="67f24-110">You can also configure how standard notifications appear on endpoints, such as notifications for reboot or when a threat has been detected and remediated.</span></span>

## <a name="configure-the-additional-notifications-that-appear-on-endpoints"></a><span data-ttu-id="67f24-111">Konfigurera ytterligare meddelanden som visas på slutpunkter</span><span class="sxs-lookup"><span data-stu-id="67f24-111">Configure the additional notifications that appear on endpoints</span></span>

<span data-ttu-id="67f24-112">Du kan konfigurera visningen av ytterligare meddelanden, till exempel sammanfattningar av nya identifieringar av hot, [Windows-säkerhet appen](microsoft-defender-security-center-antivirus.md) och med Grupprincip.</span><span class="sxs-lookup"><span data-stu-id="67f24-112">You can configure the display of additional notifications, such as recent threat detection summaries, in the [Windows Security app](microsoft-defender-security-center-antivirus.md) and with Group Policy.</span></span>

> [!NOTE]
> <span data-ttu-id="67f24-113">I Windows 10 version 1607 kallades funktionen  för Utökade meddelanden och kan konfigureras under **Windows Inställningar**  >  **Update & security**  >  **Windows Defender**.</span><span class="sxs-lookup"><span data-stu-id="67f24-113">In Windows 10, version 1607 the feature was called **Enhanced notifications** and could be configured under **Windows Settings** > **Update & security** > **Windows Defender**.</span></span> <span data-ttu-id="67f24-114">I grupprincipinställningar i alla versioner Windows 10 kallas det **utökade meddelanden.**</span><span class="sxs-lookup"><span data-stu-id="67f24-114">In Group Policy settings in all versions of Windows 10, it is called **Enhanced notifications**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="67f24-115">Om du inaktiverar ytterligare meddelanden inaktiveras inte kritiska meddelanden, till exempel aviseringar om identifiering av hot och åtgärder.</span><span class="sxs-lookup"><span data-stu-id="67f24-115">Disabling additional notifications will not disable critical notifications, such as threat detection and remediation alerts.</span></span>

<span data-ttu-id="67f24-116">**Använd Windows-säkerhet för att inaktivera ytterligare meddelanden:**</span><span class="sxs-lookup"><span data-stu-id="67f24-116">**Use the Windows Security app to disable additional notifications:**</span></span>

1. <span data-ttu-id="67f24-117">Öppna Windows-säkerhet genom att klicka på sköldikonen i aktivitetsfältet eller söka efter Säkerhet på **Start-menyn.**</span><span class="sxs-lookup"><span data-stu-id="67f24-117">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="67f24-118">Välj **Virus &** skydd mot hot (eller sköldikonen i den vänstra menyraden) och välj sedan Inställningar för & skydd mot **virus**</span><span class="sxs-lookup"><span data-stu-id="67f24-118">Select **Virus & threat protection** tile (or the shield icon on the left menu bar) and, then select **Virus & threat protection settings**</span></span>

3. <span data-ttu-id="67f24-119">Bläddra till avsnittet **Meddelanden** och klicka på **Ändra aviseringsinställningar**.</span><span class="sxs-lookup"><span data-stu-id="67f24-119">Scroll to the **Notifications** section and click **Change notification settings**.</span></span>

4. <span data-ttu-id="67f24-120">Dra reglaget till **Av** eller **På för** att inaktivera eller aktivera ytterligare meddelanden.</span><span class="sxs-lookup"><span data-stu-id="67f24-120">Slide the switch to **Off** or **On** to disable or enable additional notifications.</span></span>

<span data-ttu-id="67f24-121">**Använd Grupprincip för att inaktivera ytterligare meddelanden:**</span><span class="sxs-lookup"><span data-stu-id="67f24-121">**Use Group Policy to disable additional notifications:**</span></span>

1. <span data-ttu-id="67f24-122">På datorn för grupprinciphantering öppnar du [Konsolen för](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))grupprinciphantering, högerklickar på det grupprincipobjekt du vill konfigurera och klickar på **Redigera.**</span><span class="sxs-lookup"><span data-stu-id="67f24-122">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="67f24-123">Gå till **Datorkonfiguration i redigeraren** för **grupprinciphantering.**</span><span class="sxs-lookup"><span data-stu-id="67f24-123">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="67f24-124">Klicka **på Administrativa mallar**.</span><span class="sxs-lookup"><span data-stu-id="67f24-124">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="67f24-125">Expandera trädet för att **Windows komponenter > Microsoft Defender Antivirus > rapportering.**</span><span class="sxs-lookup"><span data-stu-id="67f24-125">Expand the tree to **Windows components > Microsoft Defender Antivirus > Reporting**.</span></span>

5. <span data-ttu-id="67f24-126">Dubbelklicka på **Inaktivera utökade meddelanden och** ställ in alternativet Aktiverad. </span><span class="sxs-lookup"><span data-stu-id="67f24-126">Double-click **Turn off enhanced notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="67f24-127">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="67f24-127">Click **OK**.</span></span> <span data-ttu-id="67f24-128">Det gör att det inte visas fler meddelanden.</span><span class="sxs-lookup"><span data-stu-id="67f24-128">This will prevent additional notifications from appearing.</span></span>

## <a name="configure-standard-notifications-on-endpoints"></a><span data-ttu-id="67f24-129">Konfigurera standardaviseringar på slutpunkter</span><span class="sxs-lookup"><span data-stu-id="67f24-129">Configure standard notifications on endpoints</span></span>

<span data-ttu-id="67f24-130">Du kan använda grupprinciper för att:</span><span class="sxs-lookup"><span data-stu-id="67f24-130">You can use Group Policy to:</span></span>

- <span data-ttu-id="67f24-131">Visa ytterligare, anpassad text på slutpunkter när användaren behöver utföra en åtgärd</span><span class="sxs-lookup"><span data-stu-id="67f24-131">Display additional, customized text on endpoints when the user needs to perform an action</span></span>
- <span data-ttu-id="67f24-132">Dölj alla meddelanden på slutpunkter</span><span class="sxs-lookup"><span data-stu-id="67f24-132">Hide all notifications on endpoints</span></span>
- <span data-ttu-id="67f24-133">Dölja meddelanden om omstart på slutpunkter</span><span class="sxs-lookup"><span data-stu-id="67f24-133">Hide reboot notifications on endpoints</span></span>

<span data-ttu-id="67f24-134">Att dölja meddelanden kan vara användbart i situationer där du inte kan dölja Microsoft Defender Antivirus gränssnittet.</span><span class="sxs-lookup"><span data-stu-id="67f24-134">Hiding notifications can be useful in situations where you can't hide the entire Microsoft Defender Antivirus interface.</span></span> <span data-ttu-id="67f24-135">Mer information [finns i Hindra användare från att se Microsoft Defender Antivirus interagera med användargränssnittet.](prevent-end-user-interaction-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="67f24-135">See [Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface](prevent-end-user-interaction-microsoft-defender-antivirus.md) for more information.</span></span> 

> [!NOTE]
> <span data-ttu-id="67f24-136">Om du döljer meddelanden visas det bara i slutpunkter där principen har distribuerats.</span><span class="sxs-lookup"><span data-stu-id="67f24-136">Hiding notifications will only occur on endpoints to which the policy has been deployed.</span></span> <span data-ttu-id="67f24-137">Meddelanden om åtgärder som måste vidtas (till exempel en omstart) visas fortfarande på Microsoft Endpoint Manager Endpoint Protection [och instrumentpanelen för övervakning.](/configmgr/protect/deploy-use/monitor-endpoint-protection)</span><span class="sxs-lookup"><span data-stu-id="67f24-137">Notifications related to actions that must be taken (such as a reboot) will still appear on the [Microsoft Endpoint Manager Endpoint Protection monitoring dashboard and reports](/configmgr/protect/deploy-use/monitor-endpoint-protection).</span></span> 

<span data-ttu-id="67f24-138">Se [Anpassa Windows-säkerhet för din organisation](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) för anvisningar om hur du lägger till anpassad kontaktinformation i meddelanden som användarna ser på sina datorer.</span><span class="sxs-lookup"><span data-stu-id="67f24-138">See [Customize the Windows Security app for your organization](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) for instructions to add custom contact information to the notifications that users see on their machines.</span></span>

<span data-ttu-id="67f24-139">**Använd grupprinciper för att dölja meddelanden:**</span><span class="sxs-lookup"><span data-stu-id="67f24-139">**Use Group Policy to hide notifications:**</span></span>

1. <span data-ttu-id="67f24-140">På datorn för grupprinciphantering öppnar du [Konsolen](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))för grupprinciphantering, högerklickar på det grupprincipobjekt du vill konfigurera och klickar på **Redigera.**</span><span class="sxs-lookup"><span data-stu-id="67f24-140">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure, and click **Edit**.</span></span>

2. <span data-ttu-id="67f24-141">I **redigeraren för grupprinciphantering går** du till **Datorkonfiguration och** klickar på **Administrativa mallar**.</span><span class="sxs-lookup"><span data-stu-id="67f24-141">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="67f24-142">Expandera trädet och visa **Windows i > Microsoft Defender Antivirus > klientgränssnittet.**</span><span class="sxs-lookup"><span data-stu-id="67f24-142">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span> 

4. <span data-ttu-id="67f24-143">Dubbelklicka på **Ignorera alla meddelanden** och ange alternativet **Aktiverad**.</span><span class="sxs-lookup"><span data-stu-id="67f24-143">Double-click **Suppress all notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="67f24-144">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="67f24-144">Click **OK**.</span></span> <span data-ttu-id="67f24-145">Det gör att det inte visas fler meddelanden.</span><span class="sxs-lookup"><span data-stu-id="67f24-145">This will prevent additional notifications from appearing.</span></span>

<span data-ttu-id="67f24-146">**Använd Grupprincip för att dölja meddelanden om omstart:**</span><span class="sxs-lookup"><span data-stu-id="67f24-146">**Use Group Policy to hide reboot notifications:**</span></span>

1. <span data-ttu-id="67f24-147">På datorn för grupprinciphantering öppnar du [Konsolen för](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))grupprinciphantering, högerklickar på det grupprincipobjekt du vill konfigurera och klickar på **Redigera.**</span><span class="sxs-lookup"><span data-stu-id="67f24-147">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="67f24-148">Gå till **Datorkonfiguration i redigeraren** för **grupprinciphantering.**</span><span class="sxs-lookup"><span data-stu-id="67f24-148">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="67f24-149">Klicka **på Administrativa mallar**.</span><span class="sxs-lookup"><span data-stu-id="67f24-149">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="67f24-150">Expandera trädet och visa **Windows i > Microsoft Defender Antivirus > klientgränssnittet.**</span><span class="sxs-lookup"><span data-stu-id="67f24-150">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span>

5. <span data-ttu-id="67f24-151">Dubbelklicka på Ignorera **meddelanden vid omstart och** ställ in alternativet **Aktiverad**.</span><span class="sxs-lookup"><span data-stu-id="67f24-151">Double-click **Suppresses reboot notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="67f24-152">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="67f24-152">Click **OK**.</span></span> <span data-ttu-id="67f24-153">Det gör att det inte visas fler meddelanden.</span><span class="sxs-lookup"><span data-stu-id="67f24-153">This will prevent additional notifications from appearing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="67f24-154">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="67f24-154">Related topics</span></span>

- [<span data-ttu-id="67f24-155">Microsoft Defender Antivirus i Windows 10</span><span class="sxs-lookup"><span data-stu-id="67f24-155">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="67f24-156">Konfigurera slutanvändares interaktion med Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="67f24-156">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md)
