---
title: Konfigurera aviseringar för Microsoft Defender Antivirus
description: Lär dig hur du konfigurerar och anpassar både standardaviseringar och ytterligare antivirusaviseringar i Microsoft Defender på slutpunkter.
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
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 6e11c9394f250a6f3882183224f53954b1390a23
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274634"
---
# <a name="configure-the-notifications-that-appear-on-endpoints"></a><span data-ttu-id="4e889-104">Konfigurera meddelanden som visas på slutpunkter</span><span class="sxs-lookup"><span data-stu-id="4e889-104">Configure the notifications that appear on endpoints</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="4e889-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="4e889-105">**Applies to:**</span></span>

- [<span data-ttu-id="4e889-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="4e889-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="4e889-107">I Windows 10 är programmeddelanden om identifiering och åtgärder av skadlig kod mer robusta, konsekventa och korta.</span><span class="sxs-lookup"><span data-stu-id="4e889-107">In Windows 10, application notifications about malware detection and remediation are more robust, consistent, and concise.</span></span>

<span data-ttu-id="4e889-108">Meddelanden visas på slutpunkter när manuellt utlösta och schemalagda genomsökningar har slutförts och hot identifieras.</span><span class="sxs-lookup"><span data-stu-id="4e889-108">Notifications appear on endpoints when manually triggered and scheduled scans are completed and threats are detected.</span></span> <span data-ttu-id="4e889-109">Dessa meddelanden visas också i **meddelandecentret**, och en sammanfattning av genomsökningar och identifieringar av hot visas med jämna mellanrum.</span><span class="sxs-lookup"><span data-stu-id="4e889-109">These notifications also appear in the **Notification Center**, and a summary of scans and threat detections appear at regular time intervals.</span></span>

<span data-ttu-id="4e889-110">Du kan också konfigurera hur standardmeddelanden visas på slutpunkter, till exempel meddelanden för omstart eller när ett hot har upptäckts och åtgärdats.</span><span class="sxs-lookup"><span data-stu-id="4e889-110">You can also configure how standard notifications appear on endpoints, such as notifications for reboot or when a threat has been detected and remediated.</span></span>

## <a name="configure-the-additional-notifications-that-appear-on-endpoints"></a><span data-ttu-id="4e889-111">Konfigurera ytterligare meddelanden som visas på slutpunkter</span><span class="sxs-lookup"><span data-stu-id="4e889-111">Configure the additional notifications that appear on endpoints</span></span>

<span data-ttu-id="4e889-112">Du kan konfigurera visningen av ytterligare meddelanden, till exempel sammanfattning av nya identifieringar av hot, i [Windows-säkerhetsappen](microsoft-defender-security-center-antivirus.md) och med Grupprincip.</span><span class="sxs-lookup"><span data-stu-id="4e889-112">You can configure the display of additional notifications, such as recent threat detection summaries, in the [Windows Security app](microsoft-defender-security-center-antivirus.md) and with Group Policy.</span></span>

> [!NOTE]
> <span data-ttu-id="4e889-113">I Windows 10 version 1607  kallades funktionen för Förbättrade meddelanden och kan konfigureras under **Windows Settings** Update  >  **& säkerhet** Windows  >  **Defender.**</span><span class="sxs-lookup"><span data-stu-id="4e889-113">In Windows 10, version 1607 the feature was called **Enhanced notifications** and could be configured under **Windows Settings** > **Update & security** > **Windows Defender**.</span></span> <span data-ttu-id="4e889-114">I grupprincipinställningar i alla versioner av Windows 10 kallas det **utökade meddelanden.**</span><span class="sxs-lookup"><span data-stu-id="4e889-114">In Group Policy settings in all versions of Windows 10, it is called **Enhanced notifications**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4e889-115">Om du inaktiverar ytterligare meddelanden inaktiveras inte kritiska meddelanden, till exempel aviseringar om identifiering av hot och åtgärder.</span><span class="sxs-lookup"><span data-stu-id="4e889-115">Disabling additional notifications will not disable critical notifications, such as threat detection and remediation alerts.</span></span>

<span data-ttu-id="4e889-116">**Använd appen Windows-säkerhet för att inaktivera ytterligare meddelanden:**</span><span class="sxs-lookup"><span data-stu-id="4e889-116">**Use the Windows Security app to disable additional notifications:**</span></span>

1. <span data-ttu-id="4e889-117">Öppna appen Windows-säkerhet genom att klicka på sköldikonen i aktivitetsfältet eller söka efter Defender på **startmenyn.**</span><span class="sxs-lookup"><span data-stu-id="4e889-117">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="4e889-118">Klicka på **&** för skydd mot virus (eller sköldikonen på den vänstra menyraden) och sedan på & för skydd **mot** hot:</span><span class="sxs-lookup"><span data-stu-id="4e889-118">Click the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then the **Virus & threat protection settings** label:</span></span>

    ![Skärmbild av etiketten för & för skydd mot virus i Windows-säkerhetsappen](images/defender/wdav-protection-settings-wdsc.png)

3. <span data-ttu-id="4e889-120">Bläddra till avsnittet **Meddelanden** och klicka på **Ändra aviseringsinställningar**.</span><span class="sxs-lookup"><span data-stu-id="4e889-120">Scroll to the **Notifications** section and click **Change notification settings**.</span></span>

4. <span data-ttu-id="4e889-121">Dra reglaget till **Av** eller **På för** att inaktivera eller aktivera ytterligare meddelanden.</span><span class="sxs-lookup"><span data-stu-id="4e889-121">Slide the switch to **Off** or **On** to disable or enable additional notifications.</span></span>

<span data-ttu-id="4e889-122">**Använd Grupprincip för att inaktivera ytterligare meddelanden:**</span><span class="sxs-lookup"><span data-stu-id="4e889-122">**Use Group Policy to disable additional notifications:**</span></span>

1. <span data-ttu-id="4e889-123">På datorn för grupprinciphantering öppnar du [Konsolen för](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))grupprinciphantering, högerklickar på det grupprincipobjekt du vill konfigurera och klickar på **Redigera.**</span><span class="sxs-lookup"><span data-stu-id="4e889-123">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="4e889-124">Gå till **Datorkonfiguration i redigeraren** för **grupprinciphantering.**</span><span class="sxs-lookup"><span data-stu-id="4e889-124">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="4e889-125">Klicka **på Administrativa mallar**.</span><span class="sxs-lookup"><span data-stu-id="4e889-125">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="4e889-126">Expandera trädet till **Windows-komponenter > Microsoft Defender Antivirus > Reporting**.</span><span class="sxs-lookup"><span data-stu-id="4e889-126">Expand the tree to **Windows components > Microsoft Defender Antivirus > Reporting**.</span></span>

5. <span data-ttu-id="4e889-127">Dubbelklicka på **Inaktivera utökade meddelanden och** ställ in alternativet Aktiverad. </span><span class="sxs-lookup"><span data-stu-id="4e889-127">Double-click **Turn off enhanced notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="4e889-128">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="4e889-128">Click **OK**.</span></span> <span data-ttu-id="4e889-129">Det gör att det inte visas fler meddelanden.</span><span class="sxs-lookup"><span data-stu-id="4e889-129">This will prevent additional notifications from appearing.</span></span>

## <a name="configure-standard-notifications-on-endpoints"></a><span data-ttu-id="4e889-130">Konfigurera standardaviseringar på slutpunkter</span><span class="sxs-lookup"><span data-stu-id="4e889-130">Configure standard notifications on endpoints</span></span>

<span data-ttu-id="4e889-131">Du kan använda grupprinciper för att:</span><span class="sxs-lookup"><span data-stu-id="4e889-131">You can use Group Policy to:</span></span>

- <span data-ttu-id="4e889-132">Visa ytterligare, anpassad text på slutpunkter när användaren behöver utföra en åtgärd</span><span class="sxs-lookup"><span data-stu-id="4e889-132">Display additional, customized text on endpoints when the user needs to perform an action</span></span>
- <span data-ttu-id="4e889-133">Dölj alla meddelanden på slutpunkter</span><span class="sxs-lookup"><span data-stu-id="4e889-133">Hide all notifications on endpoints</span></span>
- <span data-ttu-id="4e889-134">Dölja meddelanden om omstart på slutpunkter</span><span class="sxs-lookup"><span data-stu-id="4e889-134">Hide reboot notifications on endpoints</span></span>

<span data-ttu-id="4e889-135">Att dölja meddelanden kan vara användbart i situationer där du inte kan dölja hela Microsoft Defender Antivirus-gränssnittet.</span><span class="sxs-lookup"><span data-stu-id="4e889-135">Hiding notifications can be useful in situations where you can't hide the entire Microsoft Defender Antivirus interface.</span></span> <span data-ttu-id="4e889-136">Mer information finns i Hindra användare från att se eller interagera med användargränssnittet i [Microsoft Defender Antivirus.](prevent-end-user-interaction-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="4e889-136">See [Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface](prevent-end-user-interaction-microsoft-defender-antivirus.md) for more information.</span></span> 

> [!NOTE]
> <span data-ttu-id="4e889-137">Om du döljer meddelanden visas det bara i slutpunkter där principen har distribuerats.</span><span class="sxs-lookup"><span data-stu-id="4e889-137">Hiding notifications will only occur on endpoints to which the policy has been deployed.</span></span> <span data-ttu-id="4e889-138">Meddelanden om åtgärder som måste vidtas (till exempel en omstart) visas fortfarande på instrumentpanelen och rapporterna för slutpunktsskydd [i Microsoft Endpoint Manager.](/configmgr/protect/deploy-use/monitor-endpoint-protection)</span><span class="sxs-lookup"><span data-stu-id="4e889-138">Notifications related to actions that must be taken (such as a reboot) will still appear on the [Microsoft Endpoint Manager Endpoint Protection monitoring dashboard and reports](/configmgr/protect/deploy-use/monitor-endpoint-protection).</span></span> 

<span data-ttu-id="4e889-139">Se [Anpassa Windows-säkerhetsappen för din organisation](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) för anvisningar om hur du lägger till anpassad kontaktinformation i meddelanden som användarna ser på sina datorer.</span><span class="sxs-lookup"><span data-stu-id="4e889-139">See [Customize the Windows Security app for your organization](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) for instructions to add custom contact information to the notifications that users see on their machines.</span></span>

<span data-ttu-id="4e889-140">**Använd grupprinciper för att dölja meddelanden:**</span><span class="sxs-lookup"><span data-stu-id="4e889-140">**Use Group Policy to hide notifications:**</span></span>

1. <span data-ttu-id="4e889-141">På datorn för grupprinciphantering öppnar du [Konsolen](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))för grupprinciphantering, högerklickar på det grupprincipobjekt du vill konfigurera och klickar på **Redigera.**</span><span class="sxs-lookup"><span data-stu-id="4e889-141">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure, and click **Edit**.</span></span>

2. <span data-ttu-id="4e889-142">I **redigeraren för grupprinciphantering går** du till **Datorkonfiguration och** klickar på **Administrativa mallar**.</span><span class="sxs-lookup"><span data-stu-id="4e889-142">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="4e889-143">Expandera trädet till **Windows-komponenter > Microsoft Defender Antivirus> klientgränssnittet**.</span><span class="sxs-lookup"><span data-stu-id="4e889-143">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span> 

4. <span data-ttu-id="4e889-144">Dubbelklicka på **Ignorera alla meddelanden** och ange alternativet **Aktiverad**.</span><span class="sxs-lookup"><span data-stu-id="4e889-144">Double-click **Suppress all notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="4e889-145">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="4e889-145">Click **OK**.</span></span> <span data-ttu-id="4e889-146">Det gör att det inte visas fler meddelanden.</span><span class="sxs-lookup"><span data-stu-id="4e889-146">This will prevent additional notifications from appearing.</span></span>

<span data-ttu-id="4e889-147">**Använd Grupprincip för att dölja meddelanden om omstart:**</span><span class="sxs-lookup"><span data-stu-id="4e889-147">**Use Group Policy to hide reboot notifications:**</span></span>

1. <span data-ttu-id="4e889-148">På datorn för grupprinciphantering öppnar du [Konsolen för](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))grupprinciphantering, högerklickar på det grupprincipobjekt du vill konfigurera och klickar på **Redigera.**</span><span class="sxs-lookup"><span data-stu-id="4e889-148">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="4e889-149">Gå till **Datorkonfiguration i redigeraren** för **grupprinciphantering.**</span><span class="sxs-lookup"><span data-stu-id="4e889-149">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="4e889-150">Klicka **på Administrativa mallar**.</span><span class="sxs-lookup"><span data-stu-id="4e889-150">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="4e889-151">Expandera trädet till **Windows-komponenter > Microsoft Defender Antivirus> klientgränssnittet**.</span><span class="sxs-lookup"><span data-stu-id="4e889-151">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span>

5. <span data-ttu-id="4e889-152">Dubbelklicka på Ignorera **meddelanden vid omstart och** ställ in alternativet **Aktiverad**.</span><span class="sxs-lookup"><span data-stu-id="4e889-152">Double-click **Suppresses reboot notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="4e889-153">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="4e889-153">Click **OK**.</span></span> <span data-ttu-id="4e889-154">Det gör att det inte visas fler meddelanden.</span><span class="sxs-lookup"><span data-stu-id="4e889-154">This will prevent additional notifications from appearing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4e889-155">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="4e889-155">Related topics</span></span>

- [<span data-ttu-id="4e889-156">Microsoft Defender Antivirus i Windows 10</span><span class="sxs-lookup"><span data-stu-id="4e889-156">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="4e889-157">Konfigurera interaktion med slutanvändare med Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="4e889-157">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md)