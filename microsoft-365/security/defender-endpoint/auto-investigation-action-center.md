---
title: Besök Åtgärdscenter för att se åtgärder
description: Använd åtgärdscenter för att visa information och resultat efter en automatiserad undersökning
keywords: åtgärd, center, autoir, automatiserad, undersökning, svar, åtgärd
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: how-to
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.date: 01/28/2021
ms.technology: mde
ms.openlocfilehash: af9e9315088a8dd5da9740b33135551d28664ed7
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186119"
---
# <a name="visit-the-action-center-to-see-remediation-actions"></a><span data-ttu-id="bbe50-104">Besök Åtgärdscenter för att se åtgärder</span><span class="sxs-lookup"><span data-stu-id="bbe50-104">Visit the Action center to see remediation actions</span></span>

<span data-ttu-id="bbe50-105">Under och efter en automatiserad undersökning identifieras åtgärdsåtgärder för identifiering av hot.</span><span class="sxs-lookup"><span data-stu-id="bbe50-105">During and after an automated investigation, remediation actions for threat detections are identified.</span></span> <span data-ttu-id="bbe50-106">Beroende på det specifika hot och hur [Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection) för Slutpunkt har konfigurerats för din organisation vidtas vissa åtgärder automatiskt och andra kräver godkännande.</span><span class="sxs-lookup"><span data-stu-id="bbe50-106">Depending on the particular threat and how [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) is configured for your organization, some remediation actions are taken automatically, and others require approval.</span></span> <span data-ttu-id="bbe50-107">Om du är en del av organisationens säkerhetsåtgärdsteam kan du visa väntande och [slutförda](manage-auto-investigation.md#remediation-actions) åtgärder i **Åtgärdscenter.**</span><span class="sxs-lookup"><span data-stu-id="bbe50-107">If you're part of your organization's security operations team, you can view pending and completed [remediation actions](manage-auto-investigation.md#remediation-actions) in the **Action center**.</span></span> 


<span data-ttu-id="bbe50-108">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="bbe50-108">**Applies to:**</span></span>
- [<span data-ttu-id="bbe50-109">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="bbe50-109">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="bbe50-110">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bbe50-110">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="new-a-unified-action-center"></a><span data-ttu-id="bbe50-111">(NY!) Ett enhetligt åtgärdscenter</span><span class="sxs-lookup"><span data-stu-id="bbe50-111">(NEW!) A unified Action center</span></span>


<span data-ttu-id="bbe50-112">Vi är glada att kunna presentera ett nytt, enhetligt åtgärdscenter [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ()!</span><span class="sxs-lookup"><span data-stu-id="bbe50-112">We are pleased to announce a new, unified Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center))!</span></span>

:::image type="content" source="images/mde-action-center-unified.png" alt-text="Åtgärdscenter i Säkerhetscenter för Microsoft 365":::

<span data-ttu-id="bbe50-114">I följande tabell jämförs det nya, enhetliga Åtgärdscenter med föregående Åtgärdscenter.</span><span class="sxs-lookup"><span data-stu-id="bbe50-114">The following table compares the new, unified Action center to the previous Action center.</span></span>

|<span data-ttu-id="bbe50-115">Det nya, enhetliga åtgärdscentret</span><span class="sxs-lookup"><span data-stu-id="bbe50-115">The new, unified Action center</span></span>  |<span data-ttu-id="bbe50-116">Föregående åtgärdscenter</span><span class="sxs-lookup"><span data-stu-id="bbe50-116">The previous Action center</span></span>  |
|---------|---------|
|<span data-ttu-id="bbe50-117">Visar väntande och slutförda åtgärder för enheter och e-post på en plats</span><span class="sxs-lookup"><span data-stu-id="bbe50-117">Lists pending and completed actions for devices and email in one location</span></span> <br/><span data-ttu-id="bbe50-118">([Microsoft Defender för Endpoint](microsoft-defender-endpoint.md) plus Microsoft Defender för Office [365](https://docs.microsoft.com/microsoft-365/security/defender-365-security/office-365-atp))</span><span class="sxs-lookup"><span data-stu-id="bbe50-118">([Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) plus [Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/defender-365-security/office-365-atp))</span></span>|<span data-ttu-id="bbe50-119">Visar väntande och slutförda åtgärder för enheter</span><span class="sxs-lookup"><span data-stu-id="bbe50-119">Lists pending and completed actions for devices</span></span> <br/> <span data-ttu-id="bbe50-120">([Endast Microsoft Defender för slutpunkt)](microsoft-defender-endpoint.md)</span><span class="sxs-lookup"><span data-stu-id="bbe50-120">([Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) only)</span></span>   |
|<span data-ttu-id="bbe50-121">Finns på:</span><span class="sxs-lookup"><span data-stu-id="bbe50-121">Is located at:</span></span><br/>[https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)         |<span data-ttu-id="bbe50-122">Finns på:</span><span class="sxs-lookup"><span data-stu-id="bbe50-122">Is located at:</span></span><br/>[https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center)     |
| <span data-ttu-id="bbe50-123">I Säkerhetscenter för Microsoft 365 väljer du **Åtgärdscenter**.</span><span class="sxs-lookup"><span data-stu-id="bbe50-123">In the Microsoft 365 security center, choose **Action center**.</span></span> <p>:::image type="content" source="images/action-center-nav-new.png" alt-text="Navigera till Åtgärdscenter i Säkerhetscenter för Microsoft 365"::: | <span data-ttu-id="bbe50-125">I Microsoft Defender Säkerhetscenter väljer du **Automatiserade undersökningar**  >  **Åtgärdscenter**.</span><span class="sxs-lookup"><span data-stu-id="bbe50-125">In the Microsoft Defender Security Center, choose **Automated investigations** > **Action center**.</span></span> <p>:::image type="content" source="images/action-center-nav-old.png" alt-text="Navigera till Åtgärdscenter från Microsoft Defender Säkerhetscenter":::  |

<span data-ttu-id="bbe50-127">I det enhetliga åtgärdscentret samlas åtgärdsåtgärder i Defender för Endpoint och Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="bbe50-127">The unified Action center brings together remediation actions across Defender for Endpoint and Defender for Office 365.</span></span> <span data-ttu-id="bbe50-128">Den definierar ett gemensamt språk för alla åtgärder och ger en enhetlig undersökningsupplevelse.</span><span class="sxs-lookup"><span data-stu-id="bbe50-128">It defines a common language for all remediation actions, and provides a unified investigation experience.</span></span> 

<span data-ttu-id="bbe50-129">Du kan använda det enhetliga åtgärdscentret om du har rätt behörigheter och en eller flera av följande prenumerationer:</span><span class="sxs-lookup"><span data-stu-id="bbe50-129">You can use the unified Action center if you have appropriate permissions and one or more of the following subscriptions:</span></span>
- [<span data-ttu-id="bbe50-130">Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="bbe50-130">Defender for Endpoint</span></span>](microsoft-defender-endpoint.md)
- [<span data-ttu-id="bbe50-131">Defender förr Office 365</span><span class="sxs-lookup"><span data-stu-id="bbe50-131">Defender for Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-365-security/office-365-atp)
- [<span data-ttu-id="bbe50-132">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bbe50-132">Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) 

> [!TIP]
> <span data-ttu-id="bbe50-133">Mer information finns i [Krav](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites).</span><span class="sxs-lookup"><span data-stu-id="bbe50-133">To learn more, see [Requirements](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites).</span></span>

## <a name="using-the-action-center"></a><span data-ttu-id="bbe50-134">Använda Åtgärdscenter</span><span class="sxs-lookup"><span data-stu-id="bbe50-134">Using the Action center</span></span>

<span data-ttu-id="bbe50-135">Så här kommer du till det enhetliga åtgärdscentret i det förbättrade säkerhetscentret för Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="bbe50-135">To get to the unified Action center in the improved Microsoft 365 security center:</span></span>
1. <span data-ttu-id="bbe50-136">Gå till Säkerhetscenter för Microsoft 365 ( [https://security.microsoft.com](https://security.microsoft.com) ) och logga in.</span><span class="sxs-lookup"><span data-stu-id="bbe50-136">Go to the Microsoft 365 security center ([https://security.microsoft.com](https://security.microsoft.com)) and sign in.</span></span>
2. <span data-ttu-id="bbe50-137">Välj Åtgärdscenter i **navigeringsfönstret.**</span><span class="sxs-lookup"><span data-stu-id="bbe50-137">In the navigation pane, select **Action center**.</span></span> 

<span data-ttu-id="bbe50-138">När du besöker Åtgärdscenter visas två flikar: **Väntande åtgärder** och **Historik.**</span><span class="sxs-lookup"><span data-stu-id="bbe50-138">When you visit the Action center, you see two tabs: **Pending actions** and **History**.</span></span> <span data-ttu-id="bbe50-139">I följande tabell sammanfattas det du ser på varje flik:</span><span class="sxs-lookup"><span data-stu-id="bbe50-139">The following table summarizes what you'll see on each tab:</span></span>

|<span data-ttu-id="bbe50-140">Tabb</span><span class="sxs-lookup"><span data-stu-id="bbe50-140">Tab</span></span>  |<span data-ttu-id="bbe50-141">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="bbe50-141">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="bbe50-142">**Väntande**</span><span class="sxs-lookup"><span data-stu-id="bbe50-142">**Pending**</span></span>     | <span data-ttu-id="bbe50-143">Visar en lista över åtgärder som kräver uppmärksamhet.</span><span class="sxs-lookup"><span data-stu-id="bbe50-143">Displays a list of actions that require attention.</span></span> <span data-ttu-id="bbe50-144">Du kan godkänna eller avvisa åtgärder en i taget eller markera flera åtgärder om de har samma typ av åtgärd (till exempel **karantänfil).**</span><span class="sxs-lookup"><span data-stu-id="bbe50-144">You can approve or reject actions one at a time, or select multiple actions if they have the same type of action (such as **Quarantine file**).</span></span> <br/><span data-ttu-id="bbe50-145">**TIPS:** Se till att granska och godkänna [(eller avvisa)](manage-auto-investigation.md) väntande åtgärder så snart som möjligt så att automatiserade undersökningar kan slutföras i tid.</span><span class="sxs-lookup"><span data-stu-id="bbe50-145">**TIP**: Make sure to [review and approve (or reject) pending actions](manage-auto-investigation.md) as soon as possible so that your automated investigations can complete in a timely manner.</span></span> |
|<span data-ttu-id="bbe50-146">**Historik**</span><span class="sxs-lookup"><span data-stu-id="bbe50-146">**History**</span></span>     | <span data-ttu-id="bbe50-147">Fungerar som en granskningslogg för åtgärder som har vidtagits, till exempel:</span><span class="sxs-lookup"><span data-stu-id="bbe50-147">Serves as an audit log for actions that were taken, such as:</span></span> <br/><span data-ttu-id="bbe50-148">- Åtgärdsåtgärder som har vidtagits genom automatiska undersökningar</span><span class="sxs-lookup"><span data-stu-id="bbe50-148">- Remediation actions that were taken as a result of automated investigations</span></span> <br><span data-ttu-id="bbe50-149">- Åtgärdsåtgärder som har godkänts av teamet för säkerhetsåtgärder</span><span class="sxs-lookup"><span data-stu-id="bbe50-149">- Remediation actions that were approved by your security operations team</span></span>  <br/><span data-ttu-id="bbe50-150">- Kommandon som körts och åtgärdsåtgärder som tillämpats under Live Response-sessioner</span><span class="sxs-lookup"><span data-stu-id="bbe50-150">- Commands that were run and remediation actions that were applied during Live Response sessions</span></span>  <br/><span data-ttu-id="bbe50-151">- Åtgärdsåtgärder som har vidtagits av skyddsfunktioner för hot i Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="bbe50-151">- Remediation actions that were taken by threat protection features in Microsoft Defender Antivirus</span></span>  <p><span data-ttu-id="bbe50-152">Gör det enkelt att ångra vissa åtgärder (se [Ångra slutförda åtgärder).](manage-auto-investigation.md#undo-completed-actions)</span><span class="sxs-lookup"><span data-stu-id="bbe50-152">Provides a way to undo certain actions (see [Undo completed actions](manage-auto-investigation.md#undo-completed-actions)).</span></span>       |

<span data-ttu-id="bbe50-153">Du kan anpassa, sortera, filtrera och exportera data i Åtgärdscenter.</span><span class="sxs-lookup"><span data-stu-id="bbe50-153">You can customize, sort, filter, and export data in the Action center.</span></span>

:::image type="content" source="images/new-action-center-columnsfilters.png" alt-text="Kolumner och filter i Åtgärdscenter":::

- <span data-ttu-id="bbe50-155">Välj en kolumnrubrik om du vill sortera posterna i stigande eller fallande ordning.</span><span class="sxs-lookup"><span data-stu-id="bbe50-155">Select a column heading to sort items in ascending or descending order.</span></span>
- <span data-ttu-id="bbe50-156">Använd filtret för tidsperiod för att visa data för den senaste dagen, veckan, 30 dagar eller 6 månader.</span><span class="sxs-lookup"><span data-stu-id="bbe50-156">Use the time period filter to view data for the past day, week, 30 days, or 6 months.</span></span>
- <span data-ttu-id="bbe50-157">Välj de kolumner som du vill visa.</span><span class="sxs-lookup"><span data-stu-id="bbe50-157">Choose the columns that you want to view.</span></span>
- <span data-ttu-id="bbe50-158">Ange hur många objekt som ska ingå på varje sida med data.</span><span class="sxs-lookup"><span data-stu-id="bbe50-158">Specify how many items to include on each page of data.</span></span>
- <span data-ttu-id="bbe50-159">Använd filter för att visa endast de objekt som du vill se.</span><span class="sxs-lookup"><span data-stu-id="bbe50-159">Use filters to view just the items you want to see.</span></span>
- <span data-ttu-id="bbe50-160">Välj **Exportera** om du vill exportera resultaten till en CSV-fil.</span><span class="sxs-lookup"><span data-stu-id="bbe50-160">Select **Export** to export results to a .csv file.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="bbe50-161">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="bbe50-161">Next steps</span></span>

- [<span data-ttu-id="bbe50-162">Visa och godkänna åtgärder</span><span class="sxs-lookup"><span data-stu-id="bbe50-162">View and approve remediation actions</span></span>](manage-auto-investigation.md)
- [<span data-ttu-id="bbe50-163">Se den interaktiva guiden: Undersöka och åtgärda hot med Microsoft Defender för Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="bbe50-163">See the interactive guide: Investigate and remediate threats with Microsoft Defender for Endpoint</span></span>](https://aka.ms/MDATP-IR-Interactive-Guide)
 
## <a name="see-also"></a><span data-ttu-id="bbe50-164">Se även</span><span class="sxs-lookup"><span data-stu-id="bbe50-164">See also</span></span>

- [<span data-ttu-id="bbe50-165">Adressera falska positiva/negativa tal i Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="bbe50-165">Address false positives/negatives in Microsoft Defender for Endpoint</span></span>](defender-endpoint-false-positives-negatives.md)
