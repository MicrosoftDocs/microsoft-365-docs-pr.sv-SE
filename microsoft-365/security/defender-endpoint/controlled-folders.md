---
title: Skydda viktiga mappar från utpressningstrojaner från att kryptera filer med kontrollerad mappåtkomst
description: Filer i standardmappar kan skyddas från att ändras av skadliga program. Förhindra utpressningstrojaner från att kryptera dina filer.
keywords: Reglerad mappåtkomst, windows 10, windows defender, utpressningstrojaner, skydda, filer, mappar
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
audience: ITPro
ms.date: 06/10/2021
ms.reviewer: v-maave
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: c60620d2a589c8473764b810d1fcb0e24f674451
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904062"
---
# <a name="protect-important-folders-with-controlled-folder-access"></a><span data-ttu-id="889a0-105">Skydda viktiga mappar med kontrollerad mappåtkomst</span><span class="sxs-lookup"><span data-stu-id="889a0-105">Protect important folders with controlled folder access</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="889a0-106">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="889a0-106">**Applies to:**</span></span>
- [<span data-ttu-id="889a0-107">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="889a0-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="889a0-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="889a0-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="889a0-109">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="889a0-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="889a0-110">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="889a0-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-controlled-folder-access"></a><span data-ttu-id="889a0-111">Vad är reglerad mappåtkomst?</span><span class="sxs-lookup"><span data-stu-id="889a0-111">What is controlled folder access?</span></span>

<span data-ttu-id="889a0-112">Kontrollerad mappåtkomst skyddar dina värdefulla data från skadliga appar och hot, till exempel utpressningstrojaner.</span><span class="sxs-lookup"><span data-stu-id="889a0-112">Controlled folder access helps protect your valuable data from malicious apps and threats, such as ransomware.</span></span> <span data-ttu-id="889a0-113">Kontrollerad mappåtkomst skyddar dina data genom att kontrollera appar mot en lista med kända, betrodda appar.</span><span class="sxs-lookup"><span data-stu-id="889a0-113">Controlled folder access protects your data by checking apps against a list of known, trusted apps.</span></span> <span data-ttu-id="889a0-114">Stöds i Windows Server 2019 och Windows 10-klienter. Reglerad mappåtkomst kan aktiveras med Windows-säkerhet-appen, Microsoft Endpoint Configuration Manager- eller Intune-appen (för hanterade enheter).</span><span class="sxs-lookup"><span data-stu-id="889a0-114">Supported on Windows Server 2019 and Windows 10 clients, controlled folder access can be turned on using the Windows Security App, Microsoft Endpoint Configuration Manager, or Intune (for managed devices).</span></span> 

> [!NOTE]
> <span data-ttu-id="889a0-115">Skriptmotorer är inte betrodda och du kan inte ge dem åtkomst till skyddade skyddade mappar.</span><span class="sxs-lookup"><span data-stu-id="889a0-115">Scripting engines are not trusted and you cannot allow them access to controlled protected folders.</span></span>  <span data-ttu-id="889a0-116">Till exempel är PowerShell inte betrott genom reglerad mappåtkomst, även om du tillåter det med [certifikat- och filindikatorer.](/microsoft-365/security/defender-endpoint/indicator-certificates)</span><span class="sxs-lookup"><span data-stu-id="889a0-116">For example, PowerShell is not trusted by controlled folder access, even if you allow with [certificate and file indicators](/microsoft-365/security/defender-endpoint/indicator-certificates).</span></span> 

<span data-ttu-id="889a0-117">Reglerad mappåtkomst fungerar bäst med [Microsoft Defender](microsoft-defender-endpoint.md)för Endpoint , som ger dig detaljerad rapportering om kontrollerad mappåtkomsthändelser och -block som en del av de vanliga scenarierna för [aviseringsundersökning.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="889a0-117">Controlled folder access works best with [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md), which gives you detailed reporting into controlled folder access events and blocks as part of the usual [alert investigation scenarios](investigate-alerts.md).</span></span>

> [!TIP]
> <span data-ttu-id="889a0-118">Styrda mappåtkomstblock genererar inte aviseringar i [kön Aviseringar.](alerts-queue.md)</span><span class="sxs-lookup"><span data-stu-id="889a0-118">Controlled folder access blocks don't generate alerts in the [Alerts queue](alerts-queue.md).</span></span> <span data-ttu-id="889a0-119">Du kan dock visa information om kontrollerade mappåtkomstblock i [](advanced-hunting-overview.md)tidslinjevyn på [enheten,](investigate-machines.md)medan du använder avancerad sökning eller med [anpassade identifieringsregler.](custom-detection-rules.md)</span><span class="sxs-lookup"><span data-stu-id="889a0-119">However, you can view information about controlled folder access blocks in the [device timeline view](investigate-machines.md), while using [advanced hunting](advanced-hunting-overview.md), or with [custom detection rules](custom-detection-rules.md).</span></span>

## <a name="how-does-controlled-folder-access-work"></a><span data-ttu-id="889a0-120">Hur fungerar kontrollerad mappåtkomst?</span><span class="sxs-lookup"><span data-stu-id="889a0-120">How does controlled folder access work?</span></span>

<span data-ttu-id="889a0-121">Reglerad mappåtkomst fungerar bara genom att betrodda program får åtkomst till skyddade mappar.</span><span class="sxs-lookup"><span data-stu-id="889a0-121">Controlled folder access works by only allowing trusted apps to access protected folders.</span></span> <span data-ttu-id="889a0-122">Skyddade mappar anges när reglerad mappåtkomst konfigureras.</span><span class="sxs-lookup"><span data-stu-id="889a0-122">Protected folders are specified when controlled folder access is configured.</span></span> <span data-ttu-id="889a0-123">Vanligtvis används mappar, till exempel de som används för dokument, bilder, nedladdningar och så vidare, i listan med styrda mappar.</span><span class="sxs-lookup"><span data-stu-id="889a0-123">Typically, commonly used folders, such as those used for documents, pictures, downloads, and so on, are included in the list of controlled folders.</span></span> 

<span data-ttu-id="889a0-124">Reglerad mappåtkomst fungerar med en lista över betrodda appar.</span><span class="sxs-lookup"><span data-stu-id="889a0-124">Controlled folder access works with a list of trusted apps.</span></span> <span data-ttu-id="889a0-125">Appar som ingår i listan med betrodda program fungerar som förväntat.</span><span class="sxs-lookup"><span data-stu-id="889a0-125">Apps that are included in the list of trusted software work as expected.</span></span> <span data-ttu-id="889a0-126">Appar som inte finns med i listan hindras från att göra ändringar i filer i skyddade mappar.</span><span class="sxs-lookup"><span data-stu-id="889a0-126">Apps that are not included in the list are prevented from making any changes to files inside protected folders.</span></span> 

<span data-ttu-id="889a0-127">Appar läggs till i listan baserat på deras plats och rykte.</span><span class="sxs-lookup"><span data-stu-id="889a0-127">Apps are added to the list based upon their prevalence and reputation.</span></span> <span data-ttu-id="889a0-128">Appar som är mycket vanliga i hela organisationen och som aldrig har visat något beteende som anses vara skadligt är betrodda.</span><span class="sxs-lookup"><span data-stu-id="889a0-128">Apps that are highly prevalent throughout your organization and that have never displayed any behavior deemed malicious are considered trustworthy.</span></span> <span data-ttu-id="889a0-129">Apparna läggs till automatiskt i listan.</span><span class="sxs-lookup"><span data-stu-id="889a0-129">Those apps are added to the list automatically.</span></span>

<span data-ttu-id="889a0-130">Appar kan också läggas till manuellt i listan över betrodda med hjälp av Konfigurationshanteraren eller Intune.</span><span class="sxs-lookup"><span data-stu-id="889a0-130">Apps can also be added manually to the trusted list by using Configuration Manager or Intune.</span></span> <span data-ttu-id="889a0-131">Ytterligare åtgärder, till exempel [att lägga till en filindikator](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file) för en app, kan utföras från Säkerhetscenter-konsolen.</span><span class="sxs-lookup"><span data-stu-id="889a0-131">Additional actions, such as [adding a file indicator](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file) for an app, can be performed from the Security Center Console.</span></span>

## <a name="why-controlled-folder-access-is-important"></a><span data-ttu-id="889a0-132">Varför kontrollerad mappåtkomst är viktigt</span><span class="sxs-lookup"><span data-stu-id="889a0-132">Why controlled folder access is important</span></span>

<span data-ttu-id="889a0-133">Kontrollerad mappåtkomst är särskilt användbart när du vill skydda dina dokument och information från [utpressningstrojaner.](https://www.microsoft.com/wdsi/threats/ransomware)</span><span class="sxs-lookup"><span data-stu-id="889a0-133">Controlled folder access is especially useful in helping to protect your documents and information from [ransomware](https://www.microsoft.com/wdsi/threats/ransomware).</span></span> <span data-ttu-id="889a0-134">I en utpressningstrojanattack kan dina filer krypteras och hållas kvar.</span><span class="sxs-lookup"><span data-stu-id="889a0-134">In a ransomware attack, your files can get encrypted and held hostage.</span></span> <span data-ttu-id="889a0-135">Med kontrollerad mappåtkomst på plats visas ett meddelande på datorn där ett program försökte göra ändringar i en fil i en skyddad mapp.</span><span class="sxs-lookup"><span data-stu-id="889a0-135">With controlled folder access in place, a notification appears on the computer where an app attempted to make changes to a file in a protected folder.</span></span> <span data-ttu-id="889a0-136">Du kan [anpassa meddelandet med](customize-attack-surface-reduction.md#customize-the-notification) företagets information och kontaktinformation.</span><span class="sxs-lookup"><span data-stu-id="889a0-136">You can [customize the notification](customize-attack-surface-reduction.md#customize-the-notification) with your company details and contact information.</span></span> <span data-ttu-id="889a0-137">Du kan också aktivera reglerna individuellt för att anpassa vilka tekniker som ska övervakas av funktionen.</span><span class="sxs-lookup"><span data-stu-id="889a0-137">You can also enable the rules individually to customize what techniques the feature monitors.</span></span>

<span data-ttu-id="889a0-138">De [skyddade mapparna](#review-controlled-folder-access-events-in-windows-event-viewer) omfattar vanliga systemmappar (inklusive startsekvenser) och du kan [lägga till fler mappar.](customize-controlled-folders.md#protect-additional-folders)</span><span class="sxs-lookup"><span data-stu-id="889a0-138">The [protected folders](#review-controlled-folder-access-events-in-windows-event-viewer) include common system folders (including boot sectors), and you can [add more folders](customize-controlled-folders.md#protect-additional-folders).</span></span> <span data-ttu-id="889a0-139">Du kan också [tillåta att appar](customize-controlled-folders.md#allow-specific-apps-to-make-changes-to-controlled-folders) får åtkomst till de skyddade mapparna.</span><span class="sxs-lookup"><span data-stu-id="889a0-139">You can also [allow apps](customize-controlled-folders.md#allow-specific-apps-to-make-changes-to-controlled-folders) to give them access to the protected folders.</span></span>

<span data-ttu-id="889a0-140">Du kan använda [granskningsläge för](audit-windows-defender.md) att utvärdera hur kontrollerad mappåtkomst skulle påverka organisationen om det var aktiverat.</span><span class="sxs-lookup"><span data-stu-id="889a0-140">You can use [audit mode](audit-windows-defender.md) to evaluate how controlled folder access would impact your organization if it were enabled.</span></span> <span data-ttu-id="889a0-141">Du kan också gå till webbplatsen Windows Defender Test på [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) för att bekräfta att funktionen fungerar och se hur den fungerar.</span><span class="sxs-lookup"><span data-stu-id="889a0-141">You can also visit the Windows Defender Test ground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the feature is working and see how it works.</span></span>

<span data-ttu-id="889a0-142">Kontrollerad mappåtkomst stöds i följande versioner av Windows:</span><span class="sxs-lookup"><span data-stu-id="889a0-142">Controlled folder access is supported on the following versions of Windows:</span></span>
- <span data-ttu-id="889a0-143">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) och senare</span><span class="sxs-lookup"><span data-stu-id="889a0-143">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) and later</span></span>
- [<span data-ttu-id="889a0-144">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="889a0-144">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

## <a name="windows-system-folders-are-protected-by-default"></a><span data-ttu-id="889a0-145">Windows skydda systemmappar som standard</span><span class="sxs-lookup"><span data-stu-id="889a0-145">Windows system folders are protected by default</span></span>

<span data-ttu-id="889a0-146">Windows-systemmappar skyddas som standard tillsammans med flera andra mappar:</span><span class="sxs-lookup"><span data-stu-id="889a0-146">Windows system folders are protected by default, along with several other folders:</span></span> 

- `c:\Users\<username>\Documents`
- `c:\Users\Public\Documents`
- `c:\Users\<username>\Pictures`
- `c:\Users\Public\Pictures`
- `c:\Users\Public\Videos`
- `c:\Users\<username>\Videos`
- `c:\Users\<username>\Music`
- `c:\Users\Public\Music`
- `c:\Users\<username>\Favorites`

> [!NOTE]
> <span data-ttu-id="889a0-147">Du kan konfigurera ytterligare mappar som skyddade, men du kan inte Windows bort systemmappar som är skyddade som standard.</span><span class="sxs-lookup"><span data-stu-id="889a0-147">You can configure additional folders as protected, but you cannot remove the Windows system folders that are protected by default.</span></span>

## <a name="requirements-for-controlled-folder-access"></a><span data-ttu-id="889a0-148">Krav för kontrollerad mappåtkomst</span><span class="sxs-lookup"><span data-stu-id="889a0-148">Requirements for controlled folder access</span></span>

<span data-ttu-id="889a0-149">Reglerad mappåtkomst kräver [Microsoft Defender Antivirus skydd i realtid.](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="889a0-149">Controlled folder access requires enabling [Microsoft Defender Antivirus real-time protection](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus).</span></span>

## <a name="review-controlled-folder-access-events-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="889a0-150">Granska händelser i kontrollerad mappåtkomst i Microsoft 365 Defender-portalen</span><span class="sxs-lookup"><span data-stu-id="889a0-150">Review controlled folder access events in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="889a0-151">Defender för Endpoint tillhandahåller detaljerad rapportering om händelser och block som en del av dess scenarier [för aviseringsundersökning](investigate-alerts.md) i Microsoft 365 Defender-portalen.</span><span class="sxs-lookup"><span data-stu-id="889a0-151">Defender for Endpoint provides detailed reporting into events and blocks as part of its [alert investigation scenarios](investigate-alerts.md) in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="889a0-152">(Se [Microsoft Defender för slutpunkt i Microsoft 365 Defender](../defender/microsoft-365-security-center-mde.md).)</span><span class="sxs-lookup"><span data-stu-id="889a0-152">(See [Microsoft Defender for Endpoint in Microsoft 365 Defender](../defender/microsoft-365-security-center-mde.md).)</span></span>

<span data-ttu-id="889a0-153">Du kan fråga Microsoft Defender efter Slutpunktsdata med hjälp av [Avancerad sökning](/microsoft-365/security/defender-endpoint/advanced-hunting-windows-defender-advanced-threat-protection).</span><span class="sxs-lookup"><span data-stu-id="889a0-153">You can query Microsoft Defender for Endpoint data by using [Advanced hunting](/microsoft-365/security/defender-endpoint/advanced-hunting-windows-defender-advanced-threat-protection).</span></span> <span data-ttu-id="889a0-154">Om du använder granskningsläge kan [](advanced-hunting-overview.md) [du](audit-windows-defender.md)använda avancerad sökning för att se hur styrda inställningar för mappåtkomst skulle påverka din miljö om de var aktiverade.</span><span class="sxs-lookup"><span data-stu-id="889a0-154">If you're using [audit mode](audit-windows-defender.md), you can use [advanced hunting](advanced-hunting-overview.md) to see how controlled folder access settings would affect your environment if they were enabled.</span></span>

<span data-ttu-id="889a0-155">Exempelfråga:</span><span class="sxs-lookup"><span data-stu-id="889a0-155">Example query:</span></span>

```PowerShell
DeviceEvents
| where ActionType in ('ControlledFolderAccessViolationAudited','ControlledFolderAccessViolationBlocked')
```

## <a name="review-controlled-folder-access-events-in-windows-event-viewer"></a><span data-ttu-id="889a0-156">Granska styrda mappåtkomsthändelser i Windows Loggboken</span><span class="sxs-lookup"><span data-stu-id="889a0-156">Review controlled folder access events in Windows Event Viewer</span></span>

<span data-ttu-id="889a0-157">Du kan granska Windows händelseloggen för att se händelser som skapas när reglerad mappåtkomstblock (eller granskningar) i en app:</span><span class="sxs-lookup"><span data-stu-id="889a0-157">You can review the Windows event log to see events that are created when controlled folder access blocks (or audits) an app:</span></span>

1. <span data-ttu-id="889a0-158">Ladda ned [utvärderingspaketet](https://aka.ms/mp7z2w) och extrahera filen *cfa-events.xml* till en lättillgänglig plats på enheten.</span><span class="sxs-lookup"><span data-stu-id="889a0-158">Download the [Evaluation Package](https://aka.ms/mp7z2w) and extract the file *cfa-events.xml* to an easily accessible location on the device.</span></span>
2. <span data-ttu-id="889a0-159">Skriv **Loggboken** på Start-menyn för att öppna Windows Loggboken.</span><span class="sxs-lookup"><span data-stu-id="889a0-159">Type **Event viewer** in the Start menu to open the Windows Event Viewer.</span></span>
3. <span data-ttu-id="889a0-160">I den vänstra panelen under **Åtgärder väljer** du Importera **anpassad vy...**.</span><span class="sxs-lookup"><span data-stu-id="889a0-160">On the left panel, under **Actions**, select **Import custom view...**.</span></span>
4. <span data-ttu-id="889a0-161">Navigera till den plats där *du* cfa-events.xmloch markera den.</span><span class="sxs-lookup"><span data-stu-id="889a0-161">Navigate to where you extracted *cfa-events.xml* and select it.</span></span> <span data-ttu-id="889a0-162">Du kan också [kopiera XML direkt.](event-views.md)</span><span class="sxs-lookup"><span data-stu-id="889a0-162">Alternatively, [copy the XML directly](event-views.md).</span></span>
5. <span data-ttu-id="889a0-163">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="889a0-163">Select **OK**.</span></span>

<span data-ttu-id="889a0-164">I följande tabell visas händelser som är relaterade till kontrollerad mappåtkomst:</span><span class="sxs-lookup"><span data-stu-id="889a0-164">The following table shows events related to controlled folder access:</span></span>

|<span data-ttu-id="889a0-165">Händelse-ID</span><span class="sxs-lookup"><span data-stu-id="889a0-165">Event ID</span></span> | <span data-ttu-id="889a0-166">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="889a0-166">Description</span></span> |
|:---|:---|
|<span data-ttu-id="889a0-167">5007</span><span class="sxs-lookup"><span data-stu-id="889a0-167">5007</span></span> | <span data-ttu-id="889a0-168">Händelse när inställningar ändras</span><span class="sxs-lookup"><span data-stu-id="889a0-168">Event when settings are changed</span></span> |
|<span data-ttu-id="889a0-169">1124</span><span class="sxs-lookup"><span data-stu-id="889a0-169">1124</span></span> | <span data-ttu-id="889a0-170">Granskad kontrollerad mappåtkomsthändelse</span><span class="sxs-lookup"><span data-stu-id="889a0-170">Audited controlled folder access event</span></span> | 
|<span data-ttu-id="889a0-171">1123</span><span class="sxs-lookup"><span data-stu-id="889a0-171">1123</span></span> | <span data-ttu-id="889a0-172">Blockerad reglerad mappåtkomsthändelse</span><span class="sxs-lookup"><span data-stu-id="889a0-172">Blocked controlled folder access event</span></span> |

## <a name="view-or-change-the-list-of-protected-folders"></a><span data-ttu-id="889a0-173">Visa eller ändra listan med skyddade mappar</span><span class="sxs-lookup"><span data-stu-id="889a0-173">View or change the list of protected folders</span></span>

<span data-ttu-id="889a0-174">Du kan använda Windows-säkerhet för att visa listan med mappar som skyddas av reglerad mappåtkomst.</span><span class="sxs-lookup"><span data-stu-id="889a0-174">You can use the Windows Security app to view the list of folders that are protected by controlled folder access.</span></span> 

1. <span data-ttu-id="889a0-175">Öppna Windows 10-appen på Windows-säkerhet enhet.</span><span class="sxs-lookup"><span data-stu-id="889a0-175">On your Windows 10 device, open the Windows Security app.</span></span>
2. <span data-ttu-id="889a0-176">Välj **Skydd mot virus och hot**.</span><span class="sxs-lookup"><span data-stu-id="889a0-176">Select **Virus & threat protection**.</span></span>
3. <span data-ttu-id="889a0-177">Under **Utpressningstrojanskydd** väljer du **Hantera utpressningstrojanskydd**.</span><span class="sxs-lookup"><span data-stu-id="889a0-177">Under **Ransomware protection**, select **Manage ransomware protection**.</span></span>
4. <span data-ttu-id="889a0-178">Om reglerad mappåtkomst är inaktiverad måste du aktivera den.</span><span class="sxs-lookup"><span data-stu-id="889a0-178">If controlled folder access is turned off, you'll need to turn it on.</span></span> <span data-ttu-id="889a0-179">Välj **skyddade mappar**.</span><span class="sxs-lookup"><span data-stu-id="889a0-179">Select **protected folders**.</span></span>
5. <span data-ttu-id="889a0-180">Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="889a0-180">Do one of the following steps:</span></span>
   - <span data-ttu-id="889a0-181">Om du vill lägga till en mapp väljer **du + Lägg till en skyddad mapp**.</span><span class="sxs-lookup"><span data-stu-id="889a0-181">To add a folder, select **+ Add a protected folder**.</span></span>
   - <span data-ttu-id="889a0-182">Om du vill ta bort en mapp markerar du den och väljer sedan Ta **bort**.</span><span class="sxs-lookup"><span data-stu-id="889a0-182">To remove a folder, select it, and then select **Remove**.</span></span> 

> [!NOTE]
> <span data-ttu-id="889a0-183">[Windows-systemmappar](#windows-system-folders-are-protected-by-default) är skyddade som standard och du kan inte ta bort dem från listan.</span><span class="sxs-lookup"><span data-stu-id="889a0-183">[Windows system folders](#windows-system-folders-are-protected-by-default) are protected by default, and you cannot remove them from the list.</span></span>


