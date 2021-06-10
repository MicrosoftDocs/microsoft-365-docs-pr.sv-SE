---
title: Tillämpa Av-skyddsuppdateringar för Microsoft Defender på inuella slutpunkter
description: Definiera när och hur uppdateringar ska tillämpas för slutpunkter som inte har uppdaterats på ett tag.
keywords: uppdateringar, skydd, inaktuella, gamla och inaktuella uppdateringar
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
ms.openlocfilehash: 4199f55488ef0dc5989af88e8be83a3d51190d1f
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275066"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-scans-for-endpoints-that-are-out-of-date"></a><span data-ttu-id="adab9-104">Hantera uppdateringar och genomsökningar för slutpunkter som utgått för Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="adab9-104">Manage Microsoft Defender Antivirus updates and scans for endpoints that are out of date</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="adab9-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="adab9-105">**Applies to:**</span></span>

- [<span data-ttu-id="adab9-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="adab9-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="adab9-107">Microsoft Defender Antivirus kan du definiera hur länge en slutpunkt kan undvika en uppdatering eller hur många genomsökningar den kan missa innan den krävs för att uppdatera och söka igenom sig själv.</span><span class="sxs-lookup"><span data-stu-id="adab9-107">Microsoft Defender Antivirus lets you define how long an endpoint can avoid an update or how many scans it can miss before it is required to update and scan itself.</span></span> <span data-ttu-id="adab9-108">Det är särskilt användbart i miljöer där enheter inte ofta är anslutna till ett företags- eller externt nätverk eller enheter som inte används dagligen.</span><span class="sxs-lookup"><span data-stu-id="adab9-108">This is especially useful in environments where devices are not often connected to a corporate or external network, or devices that are not used on a daily basis.</span></span>

<span data-ttu-id="adab9-109">En anställd som använder en viss dator har till exempel en paus i tre dagar och loggar inte in på datorn under den tiden.</span><span class="sxs-lookup"><span data-stu-id="adab9-109">For example, an employee that uses a particular PC is on break for three days and does not log on to their PC during that time.</span></span>

<span data-ttu-id="adab9-110">När användaren återgår till arbetet och loggar in på sin dator Microsoft Defender Antivirus direkt de senaste skyddsuppdateringarna och kör en genomsökning.</span><span class="sxs-lookup"><span data-stu-id="adab9-110">When the user returns to work and logs on to their PC, Microsoft Defender Antivirus will immediately check and download the latest protection updates, and run a scan.</span></span>

## <a name="set-up-catch-up-protection-updates-for-endpoints-that-havent-updated-for-a-while"></a><span data-ttu-id="adab9-111">Konfigurera uppdateringar av uppdateringsskydd för slutpunkter som inte har uppdaterats på ett tag</span><span class="sxs-lookup"><span data-stu-id="adab9-111">Set up catch-up protection updates for endpoints that haven't updated for a while</span></span>

<span data-ttu-id="adab9-112">Om Microsoft Defender Antivirus inte laddat ned skyddsuppdateringar under en viss period kan du konfigurera det så att den automatiskt kontrollerar och hämtar den senaste uppdateringen vid nästa inloggning.</span><span class="sxs-lookup"><span data-stu-id="adab9-112">If Microsoft Defender Antivirus did not download protection updates for a specified period, you can set it up to automatically check and download the latest update at the next log on.</span></span> <span data-ttu-id="adab9-113">Det här är användbart om [du har inaktiverat automatiska uppdateringsnedladdningar vid start](manage-event-based-updates-microsoft-defender-antivirus.md)globalt.</span><span class="sxs-lookup"><span data-stu-id="adab9-113">This is useful if you have [globally disabled automatic update downloads on startup](manage-event-based-updates-microsoft-defender-antivirus.md).</span></span>

### <a name="use-configuration-manager-to-configure-catch-up-protection-updates"></a><span data-ttu-id="adab9-114">Använda Konfigurationshanteraren för att konfigurera uppdateringar av upp- och uppslagsskyddet</span><span class="sxs-lookup"><span data-stu-id="adab9-114">Use Configuration Manager to configure catch-up protection updates</span></span>

1.  <span data-ttu-id="adab9-115">Öppna den Microsoft Endpoint Manager programkonsol på datorn som du vill ändra  (klicka på Tillgångar och efterlevnad i navigeringsfönstret till vänster och expandera trädet till Översikt Endpoint Protection Program mot skadlig  >    >  **programvara**)</span><span class="sxs-lookup"><span data-stu-id="adab9-115">On your Microsoft Endpoint Manager console, open the antimalware policy you want to change (click **Assets and Compliance** in the navigation pane on the left, then expand the tree to **Overview** > **Endpoint Protection** > **Antimalware Policies**)</span></span>

2.  <span data-ttu-id="adab9-116">Gå till avsnittet **Säkerhetsintelligensuppdateringar** och konfigurera följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="adab9-116">Go to the **Security intelligence updates** section and configure the following settings:</span></span>

    1. <span data-ttu-id="adab9-117">Ange **Tvinga en säkerhetsintelligensuppdatering om klientdatorn är offline för fler än två schemalagda uppdateringar i följd** till **Ja.**</span><span class="sxs-lookup"><span data-stu-id="adab9-117">Set **Force a security intelligence update if the client computer is offline for more than two consecutive scheduled updates** to **Yes**.</span></span>
    2. <span data-ttu-id="adab9-118">För  **Om Konfigurationshanteraren** används som källa för säkerhetsintelligensuppdateringar... anger du före vilka timmar skyddsuppdateringarna som levereras av Konfigurationshanteraren ska anses vara in datera.</span><span class="sxs-lookup"><span data-stu-id="adab9-118">For the  **If Configuration Manager is used as a source for security intelligence updates...**, specify the hours before which the protection updates delivered by Configuration Manager should be considered out-of-date.</span></span> <span data-ttu-id="adab9-119">Det här leder till att nästa uppdateringsplats används, baserat på den definierade [reservkällordningen.](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)</span><span class="sxs-lookup"><span data-stu-id="adab9-119">This will cause the next update location to be used, based on the defined [fallback source order](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order).</span></span>

3. <span data-ttu-id="adab9-120">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="adab9-120">Click **OK**.</span></span>

4.  <span data-ttu-id="adab9-121">[Distribuera den uppdaterade principen som vanligt](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).</span><span class="sxs-lookup"><span data-stu-id="adab9-121">[Deploy the updated policy as usual](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).</span></span>

### <a name="use-group-policy-to-enable-and-configure-the-catch-up-update-feature"></a><span data-ttu-id="adab9-122">Använda grupprinciper för att aktivera och konfigurera uppdateringsfunktionen</span><span class="sxs-lookup"><span data-stu-id="adab9-122">Use Group Policy to enable and configure the catch-up update feature</span></span>

1. <span data-ttu-id="adab9-123">På datorn för grupprinciphantering öppnar du [Konsolen för](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))grupprinciphantering, högerklickar på det grupprincipobjekt du vill konfigurera och klickar på **Redigera.**</span><span class="sxs-lookup"><span data-stu-id="adab9-123">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="adab9-124">Gå till **Datorkonfiguration i redigeraren** för **grupprinciphantering.**</span><span class="sxs-lookup"><span data-stu-id="adab9-124">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="adab9-125">Klicka **på Principer** och sedan på Administrativa **mallar.**</span><span class="sxs-lookup"><span data-stu-id="adab9-125">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="adab9-126">Expandera trädet så att **det Windows komponenter > Microsoft Defender Antivirus > Signaturuppdateringar**.</span><span class="sxs-lookup"><span data-stu-id="adab9-126">Expand the tree to **Windows components > Microsoft Defender Antivirus > Signature Updates**.</span></span>

5. <span data-ttu-id="adab9-127">Dubbelklicka på inställningen **Definiera det antal** dagar efter vilken en uppdatering av säkerhetsintelligens krävs och ange alternativet **Aktiverad.**</span><span class="sxs-lookup"><span data-stu-id="adab9-127">Double-click the **Define the number of days after which a catch-up security intelligence update is required** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="adab9-128">Ange efter hur många dagar du vill att Microsoft Defender AV ska söka efter och hämta den senaste skyddsuppdateringen.</span><span class="sxs-lookup"><span data-stu-id="adab9-128">Enter the number of days after which you want Microsoft Defender AV to check for and download the latest protection update.</span></span>

6. <span data-ttu-id="adab9-129">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="adab9-129">Click **OK**.</span></span>

### <a name="use-powershell-cmdlets-to-configure-catch-up-protection-updates"></a><span data-ttu-id="adab9-130">Använda PowerShell-cmdlets för att konfigurera uppdateringar av uppslagsskyddet</span><span class="sxs-lookup"><span data-stu-id="adab9-130">Use PowerShell cmdlets to configure catch-up protection updates</span></span>

<span data-ttu-id="adab9-131">Använd följande cmdlets:</span><span class="sxs-lookup"><span data-stu-id="adab9-131">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -SignatureUpdateCatchupInterval
```

<span data-ttu-id="adab9-132">Se [Använda PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) för att konfigurera och köra Microsoft Defender Antivirus- och [Defender-cmdlets för](/powershell/module/defender/) mer information om hur du använder PowerShell med Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="adab9-132">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md)  and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-configure-catch-up-protection-updates"></a><span data-ttu-id="adab9-133">Använd Windows instruktion (WMI) för att konfigurera uppdateringar av uppslagsskyddet</span><span class="sxs-lookup"><span data-stu-id="adab9-133">Use Windows Management Instruction (WMI) to configure catch-up protection updates</span></span>

<span data-ttu-id="adab9-134">Använd [ **metoden** Set för **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) för följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="adab9-134">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
SignatureUpdateCatchupInterval
```

<span data-ttu-id="adab9-135">Mer information och tillåtna parametrar finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="adab9-135">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="adab9-136">Windows Defender WMIv2-API:er</span><span class="sxs-lookup"><span data-stu-id="adab9-136">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="set-the-number-of-days-before-protection-is-reported-as-out-of-date"></a><span data-ttu-id="adab9-137">Ange antalet dagar innan skydd rapporteras som inställt</span><span class="sxs-lookup"><span data-stu-id="adab9-137">Set the number of days before protection is reported as out-of-date</span></span>

<span data-ttu-id="adab9-138">Du kan också ange hur många dagar Microsoft Defender Antivirus skydd betraktas som gammalt eller in uppdaterat.</span><span class="sxs-lookup"><span data-stu-id="adab9-138">You can also specify the number of days after which Microsoft Defender Antivirus protection is considered old or out-of-date.</span></span> <span data-ttu-id="adab9-139">Efter det angivna antalet dagar rapporterar klienten sig själv som in datera och visar ett fel för användaren av datorn.</span><span class="sxs-lookup"><span data-stu-id="adab9-139">After the specified number of days, the client will report itself as out-of-date, and show an error to the user of the PC.</span></span> <span data-ttu-id="adab9-140">Det kan också orsaka att Microsoft Defender Antivirus försöker ladda ned en uppdatering [](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)från andra källor (baserat på den definierade reservkällordningen), till exempel när du använder MMPC som sekundär källa när du har angett WSUS eller Microsoft Update som den första källan.</span><span class="sxs-lookup"><span data-stu-id="adab9-140">It may also cause Microsoft Defender Antivirus to attempt to download an update from other sources (based on the defined [fallback source order](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)), such as when using MMPC as a secondary source after setting WSUS or Microsoft Update as the first source.</span></span>

### <a name="use-group-policy-to-specify-the-number-of-days-before-protection-is-considered-out-of-date"></a><span data-ttu-id="adab9-141">Använda grupprincip för att ange antalet dagar innan skydd anses vara in uppdaterat</span><span class="sxs-lookup"><span data-stu-id="adab9-141">Use Group Policy to specify the number of days before protection is considered out-of-date</span></span>

1.  <span data-ttu-id="adab9-142">På hanteringsdatorn för grupprinciper öppnar du [Konsolen](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))för grupprinciphantering, högerklickar på det grupprincipobjekt du vill konfigurera och klickar på **Redigera.**</span><span class="sxs-lookup"><span data-stu-id="adab9-142">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

3.  <span data-ttu-id="adab9-143">Gå till **Datorkonfiguration i redigeraren** för **grupprinciphantering.**</span><span class="sxs-lookup"><span data-stu-id="adab9-143">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

4.  <span data-ttu-id="adab9-144">Klicka **på Principer** och sedan på Administrativa **mallar.**</span><span class="sxs-lookup"><span data-stu-id="adab9-144">Click **Policies** then **Administrative templates**.</span></span>

5.  <span data-ttu-id="adab9-145">Expandera trädet för att **Windows komponenter > Microsoft Defender Antivirus > signaturuppdateringar** och konfigurera följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="adab9-145">Expand the tree to **Windows components > Microsoft Defender Antivirus > Signature Updates** and configure the following settings:</span></span>

    1.  <span data-ttu-id="adab9-146">Dubbelklicka på **Definiera antalet dagar innan definitioner av spionprogram anses vara inaktiva och** ställ in alternativet Aktiverad . </span><span class="sxs-lookup"><span data-stu-id="adab9-146">Double-click **Define the number of days before spyware definitions are considered out of date** and set the option to **Enabled**.</span></span> <span data-ttu-id="adab9-147">Ange efter hur många dagar som Microsoft Defender AV ska överväga att använda spionprogramssäkerhetsinformation.</span><span class="sxs-lookup"><span data-stu-id="adab9-147">Enter the number of days after which you want Microsoft Defender AV to consider spyware Security intelligence to be out-of-date.</span></span>

    2. <span data-ttu-id="adab9-148">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="adab9-148">Click **OK**.</span></span>

    3.  <span data-ttu-id="adab9-149">Dubbelklicka på **Definiera antalet dagar innan virusdefinitioner anses vara inaktiva och** ange alternativet **Aktiverad.**</span><span class="sxs-lookup"><span data-stu-id="adab9-149">Double-click **Define the number of days before virus definitions are considered out of date** and set the option to **Enabled**.</span></span> <span data-ttu-id="adab9-150">Ange efter hur många dagar du vill att Microsoft Defender AV ska överväga att virussäkerhetsinformation är in datera.</span><span class="sxs-lookup"><span data-stu-id="adab9-150">Enter the number of days after which you want Microsoft Defender AV to consider virus Security intelligence to be out-of-date.</span></span>

    4. <span data-ttu-id="adab9-151">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="adab9-151">Click **OK**.</span></span>


## <a name="set-up-catch-up-scans-for-endpoints-that-have-not-been-scanned-for-a-while"></a><span data-ttu-id="adab9-152">Konfigurera snabbsökningar för slutpunkter som inte har sökts igenom på ett tag</span><span class="sxs-lookup"><span data-stu-id="adab9-152">Set up catch-up scans for endpoints that have not been scanned for a while</span></span>

<span data-ttu-id="adab9-153">Du kan ange antalet schemalagda genomsökningar i följd som kan missas innan Microsoft Defender Antivirus tvinga fram en genomsökning.</span><span class="sxs-lookup"><span data-stu-id="adab9-153">You can set the number of consecutive scheduled scans that can be missed before Microsoft Defender Antivirus will force a scan.</span></span>

<span data-ttu-id="adab9-154">Processen för att aktivera den här funktionen är:</span><span class="sxs-lookup"><span data-stu-id="adab9-154">The process for enabling this feature is:</span></span>

1. <span data-ttu-id="adab9-155">Konfigurera minst en schemalagd sökning (se [avsnittet Schemalägga genomsökningar).](scheduled-catch-up-scans-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="adab9-155">Set up at least one scheduled scan (see the [Schedule scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md) topic).</span></span>
2. <span data-ttu-id="adab9-156">Aktivera funktionen för genomsökning av uppläsning.</span><span class="sxs-lookup"><span data-stu-id="adab9-156">Enable the catch-up scan feature.</span></span>
3. <span data-ttu-id="adab9-157">Definiera antalet genomsökningar som kan hoppas över innan en uppläsning sker.</span><span class="sxs-lookup"><span data-stu-id="adab9-157">Define the number of scans that can be skipped before a catch-up scan occurs.</span></span>

<span data-ttu-id="adab9-158">Den här funktionen kan aktiveras för både fullständiga och snabba genomsökningar.</span><span class="sxs-lookup"><span data-stu-id="adab9-158">This feature can be enabled for both full and quick scans.</span></span>

### <a name="use-group-policy-to-enable-and-configure-the-catch-up-scan-feature"></a><span data-ttu-id="adab9-159">Använda grupprinciper för att aktivera och konfigurera genomsökningsfunktionen</span><span class="sxs-lookup"><span data-stu-id="adab9-159">Use Group Policy to enable and configure the catch-up scan feature</span></span>

1.  <span data-ttu-id="adab9-160">Se till att du har ställt in minst en schemalagd sökning.</span><span class="sxs-lookup"><span data-stu-id="adab9-160">Ensure you have set up at least one scheduled scan.</span></span>

2.  <span data-ttu-id="adab9-161">På hanteringsdatorn för grupprinciper öppnar du [Konsolen](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))för grupprinciphantering, högerklickar på det grupprincipobjekt du vill konfigurera och klickar på **Redigera.**</span><span class="sxs-lookup"><span data-stu-id="adab9-161">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

3.  <span data-ttu-id="adab9-162">Gå till **Datorkonfiguration i redigeraren** för **grupprinciphantering.**</span><span class="sxs-lookup"><span data-stu-id="adab9-162">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

4.  <span data-ttu-id="adab9-163">Klicka **på Principer** och sedan på Administrativa **mallar.**</span><span class="sxs-lookup"><span data-stu-id="adab9-163">Click **Policies** then **Administrative templates**.</span></span>

5.  <span data-ttu-id="adab9-164">Expandera trädet för att **Windows komponenter > Microsoft Defender Antivirus > genomsökning** och konfigurera följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="adab9-164">Expand the tree to **Windows components > Microsoft Defender Antivirus > Scan** and configure the following settings:</span></span>

    1.  <span data-ttu-id="adab9-165">Om du har ställt in schemalagda snabbsökningar dubbelklickar du på inställningen Aktivera snabbsökning för snabbsökning och ställer in alternativet **Aktiverad.** </span><span class="sxs-lookup"><span data-stu-id="adab9-165">If you have set up scheduled quick scans, double-click the **Turn on catch-up quick scan** setting and set the option to **Enabled**.</span></span> 
    2. <span data-ttu-id="adab9-166">Om du har ställt in schemalagda fullständiga  genomsökningar dubbelklickar du på inställningen Aktivera snabbsökning och ställer in alternativet **Aktiverad.**</span><span class="sxs-lookup"><span data-stu-id="adab9-166">If you have set up scheduled full scans, double-click the **Turn on catch-up full scan** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="adab9-167">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="adab9-167">Click **OK**.</span></span>
    3. <span data-ttu-id="adab9-168">Dubbelklicka på inställningen Definiera antalet dagar efter vilket en uppläsningssökning **måste göras** och ställ in alternativet på **Aktiverad**.</span><span class="sxs-lookup"><span data-stu-id="adab9-168">Double-click the **Define the number of days after which a catch-up scan is forced** setting and set the option to **Enabled**.</span></span> 
    4. <span data-ttu-id="adab9-169">Ange antalet genomsökningar som kan missas innan en genomsökning körs automatiskt när användaren nästa loggar in på datorn.</span><span class="sxs-lookup"><span data-stu-id="adab9-169">Enter the number of scans that can be missed before a scan will be automatically run when the user next logs on to the PC.</span></span> <span data-ttu-id="adab9-170">Vilken typ av genomsökning som körs bestäms av Ange vilken genomsökningstyp som ska användas för en schemalagd sökning **(se** [avsnittet Schemalägg genomsökningar).](scheduled-catch-up-scans-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="adab9-170">The type of scan that is run is determined by the **Specify the scan type to use for a scheduled scan** (see the [Schedule scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md) topic).</span></span> <span data-ttu-id="adab9-171">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="adab9-171">Click **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="adab9-172">Grupprincipinställningstiteln refererar till antalet dagar.</span><span class="sxs-lookup"><span data-stu-id="adab9-172">The Group Policy setting title refers to the number of days.</span></span> <span data-ttu-id="adab9-173">Inställningen tillämpas dock på antalet genomsökningar (inte dagar) innan uppläsningen körs.</span><span class="sxs-lookup"><span data-stu-id="adab9-173">The setting, however, is applied to the number of scans (not days) before the catch-up scan will be run.</span></span>

### <a name="use-powershell-cmdlets-to-configure-catch-up-scans"></a><span data-ttu-id="adab9-174">Använda PowerShell-cmdlets för att konfigurera genomsökningar för uppläsning</span><span class="sxs-lookup"><span data-stu-id="adab9-174">Use PowerShell cmdlets to configure catch-up scans</span></span>

<span data-ttu-id="adab9-175">Använd följande cmdlets:</span><span class="sxs-lookup"><span data-stu-id="adab9-175">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -DisableCatchupFullScan
Set-MpPreference -DisableCatchupQuickScan

```

<span data-ttu-id="adab9-176">Se [Använda PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) för att hantera Microsoft Defender Antivirus- och [Defender-cmdlets](/powershell/module/defender/) för mer information om hur du använder PowerShell med Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="adab9-176">See [Use PowerShell cmdlets to manage Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md)  and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-configure-catch-up-scans"></a><span data-ttu-id="adab9-177">Konfigurera Windows (WMI) (Management Instruction) för att konfigurera genomsökningar av uppläsningar</span><span class="sxs-lookup"><span data-stu-id="adab9-177">Use Windows Management Instruction (WMI) to configure catch-up scans</span></span>

<span data-ttu-id="adab9-178">Använd [ **metoden** Set för **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) för följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="adab9-178">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
DisableCatchupFullScan
DisableCatchupQuickScan
```

<span data-ttu-id="adab9-179">Mer information och tillåtna parametrar finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="adab9-179">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="adab9-180">Windows Defender WMIv2-API:er</span><span class="sxs-lookup"><span data-stu-id="adab9-180">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


### <a name="use-configuration-manager-to-configure-catch-up-scans"></a><span data-ttu-id="adab9-181">Använda Konfigurationshanteraren för att konfigurera genomsökningar för uppläsning</span><span class="sxs-lookup"><span data-stu-id="adab9-181">Use Configuration Manager to configure catch-up scans</span></span>

1.  <span data-ttu-id="adab9-182">Öppna den Microsoft Endpoint Manager programkonsol på datorn som du vill ändra  (klicka på Tillgångar och efterlevnad i navigeringsfönstret till vänster och expandera trädet till Översikt Endpoint Protection Program mot skadlig  >    >  **programvara**)</span><span class="sxs-lookup"><span data-stu-id="adab9-182">On your Microsoft Endpoint Manager console, open the antimalware policy you want to change (click **Assets and Compliance** in the navigation pane on the left, then expand the tree to **Overview** > **Endpoint Protection** > **Antimalware Policies**)</span></span>

2.  <span data-ttu-id="adab9-183">Gå till avsnittet **Schemalagda genomsökningar** och Tvinga en genomsökning av den **valda genomsökningstypen om klientdatorn är offline...** till **Ja.**</span><span class="sxs-lookup"><span data-stu-id="adab9-183">Go to the **Scheduled scans** section and **Force a scan of the selected scan type if client computer is offline...** to **Yes**.</span></span> 

3. <span data-ttu-id="adab9-184">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="adab9-184">Click **OK**.</span></span>

4.  <span data-ttu-id="adab9-185">[Distribuera den uppdaterade principen som vanligt](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).</span><span class="sxs-lookup"><span data-stu-id="adab9-185">[Deploy the updated policy as usual](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).</span></span>

## <a name="related-articles"></a><span data-ttu-id="adab9-186">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="adab9-186">Related articles</span></span>

- [<span data-ttu-id="adab9-187">Distribuera Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="adab9-187">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)
- [<span data-ttu-id="adab9-188">Hantera Microsoft Defender Antivirus uppdateringar och använda baslinjer</span><span class="sxs-lookup"><span data-stu-id="adab9-188">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="adab9-189">Hantera när skyddsuppdateringar ska hämtas och tillämpas</span><span class="sxs-lookup"><span data-stu-id="adab9-189">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md)
- [<span data-ttu-id="adab9-190">Hantera händelsebaserade uppdateringar</span><span class="sxs-lookup"><span data-stu-id="adab9-190">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md)
- [<span data-ttu-id="adab9-191">Hantera uppdateringar för mobila enheter och virtuella datorer(VM)</span><span class="sxs-lookup"><span data-stu-id="adab9-191">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [<span data-ttu-id="adab9-192">Microsoft Defender Antivirus i Windows 10</span><span class="sxs-lookup"><span data-stu-id="adab9-192">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)