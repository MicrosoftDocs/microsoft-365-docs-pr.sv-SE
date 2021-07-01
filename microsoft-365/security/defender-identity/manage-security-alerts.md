---
title: Microsoft Defender för identitetssäkerhetsvarningar i Microsoft 365 Defender
description: Lär dig hur du hanterar och granskar säkerhetsvarningar som utfärdats av Microsoft Defender för identitet i Microsoft 365 Defender
ms.date: 05/20/2021
ms.topic: how-to
author: dcurwin
ms.author: dacurwin
ms.service: microsoft-defender-for-identity
manager: raynew
ms.openlocfilehash: c81f14b92b285359bda7e291bd8d3a8b636ae54d
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228969"
---
# <a name="defender-for-identity-security-alerts-in-microsoft-365-defender"></a><span data-ttu-id="b3118-103">Defender för identitetssäkerhetsvarningar i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b3118-103">Defender for Identity security alerts in Microsoft 365 Defender</span></span>

<span data-ttu-id="b3118-104">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="b3118-104">**Applies to:**</span></span>

- <span data-ttu-id="b3118-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b3118-105">Microsoft 365 Defender</span></span>
- <span data-ttu-id="b3118-106">Defender för identitet</span><span class="sxs-lookup"><span data-stu-id="b3118-106">Defender for Identity</span></span>

<span data-ttu-id="b3118-107">I den här artikeln förklaras grunderna i hur du arbetar med Microsoft Defender för identitetssäkerhetsvarningar [Microsoft 365 säkerhetscenter.](/microsoft-365/security/defender/overview-security-center) [](/defender-for-identity)</span><span class="sxs-lookup"><span data-stu-id="b3118-107">This article explains the basics of how to work with [Microsoft Defender for Identity](/defender-for-identity) security alerts in the [Microsoft 365 security center](/microsoft-365/security/defender/overview-security-center).</span></span>

<span data-ttu-id="b3118-108">Defender för identitetsaviseringar integreras inbyggt i [Microsoft 365 säkerhetscenter](https://security.microsoft.com) med ett dedikerat sidformat för identitetsavisering.</span><span class="sxs-lookup"><span data-stu-id="b3118-108">Defender for Identity alerts are natively integrated into the [Microsoft 365 security center](https://security.microsoft.com) with a dedicated Identity alert page format.</span></span> <span data-ttu-id="b3118-109">Det här markerar det första steget i resan att [introducera hela Microsoft Defender för identitetsupplevelse i Microsoft 365 Defender](/defender-for-identity/defender-for-identity-in-microsoft-365-defender).</span><span class="sxs-lookup"><span data-stu-id="b3118-109">This marks the first step in the journey to [introduce the full Microsoft Defender for Identity experience into Microsoft 365 Defender](/defender-for-identity/defender-for-identity-in-microsoft-365-defender).</span></span>

<span data-ttu-id="b3118-110">Den nya sidan med identitetsavisering ger Microsoft Defender för identitetskunder bättre signalberikande över domäner och nya automatiska identitetssvarsfunktioner.</span><span class="sxs-lookup"><span data-stu-id="b3118-110">The new Identity alert page gives Microsoft Defender for Identity customers better cross-domain signal enrichment and new automated identity response capabilities.</span></span> <span data-ttu-id="b3118-111">Det säkerställer att du håller dig säker och hjälper till att förbättra effektiviteten i dina säkerhetsåtgärder.</span><span class="sxs-lookup"><span data-stu-id="b3118-111">It ensures that you stay secure and helps improve the efficiency of your security operations.</span></span>

<span data-ttu-id="b3118-112">En av fördelarna med att undersöka aviseringar [via Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender) är att Microsoft Defender för identitetsaviseringar är ytterligare korrelerad med information som hämtas från var och en av de andra produkterna i programsviten.</span><span class="sxs-lookup"><span data-stu-id="b3118-112">One of the benefits of investigating alerts through [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender) is that Microsoft Defender for Identity alerts are further correlated with information obtained from each of the other products in the suite.</span></span> <span data-ttu-id="b3118-113">Dessa förbättrade aviseringar är konsekventa med de Microsoft 365 Defender aviseringsformat som kommer från [Microsoft Defender för Office 365](/microsoft-365/security/office-365-security) och Microsoft Defender för [slutpunkt.](/microsoft-365/security/defender-endpoint)</span><span class="sxs-lookup"><span data-stu-id="b3118-113">These enhanced alerts are consistent with the other Microsoft 365 Defender alert formats originating from [Microsoft Defender for Office 365](/microsoft-365/security/office-365-security) and [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint).</span></span> <span data-ttu-id="b3118-114">På den nya sidan slipper du navigera till en annan produktportal och undersöker aviseringar som är associerade med identitet.</span><span class="sxs-lookup"><span data-stu-id="b3118-114">The new page effectively eliminates the need to navigate to another product portal to investigate alerts associated with identity.</span></span>

<span data-ttu-id="b3118-115">Aviseringar som kommer från Defender för identitet kan nu utlösa funktionerna för automatiserad undersökning och svar [(AIR)](/microsoft-365/security/defender/m365d-autoir) i Microsoft 365 Defender, inklusive automatisk åtgärd av aviseringar och minskning av verktyg och processer som kan bidra till den misstänkta aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="b3118-115">Alerts originating from Defender for Identity can now trigger the [Microsoft 365 Defender automated investigation and response (AIR)](/microsoft-365/security/defender/m365d-autoir) capabilities, including automatically remediating alerts and the mitigation of tools and processes that can contribute to the suspicious activity.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b3118-116">Som en del av de Microsoft 365 Defender har vissa alternativ och information ändrats från sin plats i Defender för identitetsportalen.</span><span class="sxs-lookup"><span data-stu-id="b3118-116">As part of the convergence with Microsoft 365 Defender, some options and details have changed from their location in the Defender for Identity portal.</span></span> <span data-ttu-id="b3118-117">Läs informationen nedan för att ta reda på var du hittar både de välbekanta och nya funktionerna.</span><span class="sxs-lookup"><span data-stu-id="b3118-117">Please read the details below to discover where to find both the familiar and new features.</span></span>

## <a name="review-security-alerts"></a><span data-ttu-id="b3118-118">Granska säkerhetsvarningar</span><span class="sxs-lookup"><span data-stu-id="b3118-118">Review security alerts</span></span>

<span data-ttu-id="b3118-119">Aviseringar kan nås från flera platser,  bland annat sidan Aviseringar, sidan  **Incidenter,** sidorna för enskilda enheter och från **sidan Avancerad** sökning.</span><span class="sxs-lookup"><span data-stu-id="b3118-119">Alerts can be accessed from multiple locations, including the **Alerts** page, the **Incidents** page, the pages of individual **Devices**, and from the **Advanced hunting** page.</span></span> <span data-ttu-id="b3118-120">I det här exemplet granskar vi **sidan Aviseringar.**</span><span class="sxs-lookup"><span data-stu-id="b3118-120">In this example, we'll review the **Alerts page**.</span></span>

<span data-ttu-id="b3118-121">I [säkerhetscentret Microsoft 365 du](https://security.microsoft.com/)till **Incidenter, & aviseringar** och sedan till **Aviseringar.**</span><span class="sxs-lookup"><span data-stu-id="b3118-121">In the [Microsoft 365 security center](https://security.microsoft.com/), go to **Incidents & alerts** and then to **Alerts**.</span></span>

![Gå till Incidenter och aviseringar och sedan Aviseringar](../../media/defender-identity/incidents-alerts.png)

<span data-ttu-id="b3118-123">Om du vill visa aviseringar från Defender för identitet väljer du **Filter** längst upp till höger och **sedan** Microsoft **Defender** för identitet under Tjänstkällor och väljer **Använd:**</span><span class="sxs-lookup"><span data-stu-id="b3118-123">To see alerts from Defender for Identity, on the top-right select **Filter**, and then under **Service sources** select **Microsoft Defender for Identity**, and select **Apply**:</span></span>

![Filter för Defender för identitetshändelser](../../media/defender-identity/filter-defender-for-identity.png)

<span data-ttu-id="b3118-125">Aviseringarna visas med information i följande **kolumner:** Aviseringsnamn , **Taggar** **,** Allvarlighetsgrad **,** Undersökningstillstånd **,** **Status**, Kategori , **Identifieringskälla** **,** Påverkade tillgångar **,** Första **aktivitet och Senaste aktivitet**.</span><span class="sxs-lookup"><span data-stu-id="b3118-125">The alerts are displayed with information in the following columns: **Alert name**, **Tags**, **Severity**, **Investigation state**, **Status**, **Category**, **Detection source**, **Impacted assets**, **First activity**, and **Last activity**.</span></span>

![Defender för identitetshändelser](../../media/defender-identity/filtered-alerts.png)

## <a name="manage-alerts"></a><span data-ttu-id="b3118-127">Hantera varningar</span><span class="sxs-lookup"><span data-stu-id="b3118-127">Manage alerts</span></span>

<span data-ttu-id="b3118-128">Om du klickar **på aviseringsnamnet** för en avisering går du till sidan med information om aviseringen.</span><span class="sxs-lookup"><span data-stu-id="b3118-128">If you click the **Alert name** for one of the alerts, you'll go to the page with details about the alert.</span></span> <span data-ttu-id="b3118-129">I den vänstra rutan visas en sammanfattning av Vad **har hänt:**</span><span class="sxs-lookup"><span data-stu-id="b3118-129">In the left pane, you'll see a summary of **What happened**:</span></span>

![Vad hände i aviseringen](../../media/defender-identity/what-happened.png)

<span data-ttu-id="b3118-131">Ovanför rutan **Vad hände** finns knapparna för **kontona ,** **Målvärd** och **Källvärd** för aviseringen.</span><span class="sxs-lookup"><span data-stu-id="b3118-131">Above the **What happened** box are buttons for the **Accounts**, **Destination Host** and **Source Host** of the alert.</span></span> <span data-ttu-id="b3118-132">För andra aviseringar kan du se knappar för information om ytterligare värdar, konton, IP-adresser, domäner och säkerhetsgrupper.</span><span class="sxs-lookup"><span data-stu-id="b3118-132">For other alerts, you might see buttons for details about additional hosts, accounts, IP addresses, domains, and security groups.</span></span> <span data-ttu-id="b3118-133">Välj någon av dem för att få mer information om enheterna som ingår.</span><span class="sxs-lookup"><span data-stu-id="b3118-133">Select any of them to get more details about the entities involved.</span></span>

<span data-ttu-id="b3118-134">I det högra fönstret visas **aviseringsinformationen.**</span><span class="sxs-lookup"><span data-stu-id="b3118-134">On the right pane, you'll see the **Alert details**.</span></span> <span data-ttu-id="b3118-135">Här kan du se mer information och utföra flera uppgifter:</span><span class="sxs-lookup"><span data-stu-id="b3118-135">Here you can see more details and perform several tasks:</span></span>

- <span data-ttu-id="b3118-136">**Klassificera den här aviseringen** – Här kan du ange den här aviseringen som **en Sant-avisering** eller **Falskt-avisering**</span><span class="sxs-lookup"><span data-stu-id="b3118-136">**Classify this alert** - Here you can designate this alert as a **True alert** or **False alert**</span></span>

    ![Klassificera avisering](../../media/defender-identity/classify-alert.png)

- <span data-ttu-id="b3118-138">**Aviseringstillstånd** **– I Ange** klassificering kan du klassificera aviseringen som **Sant** eller **Falskt.**</span><span class="sxs-lookup"><span data-stu-id="b3118-138">**Alert state** - In **Set Classification**, you can classify the alert as **True** or **False**.</span></span> <span data-ttu-id="b3118-139">I **Tilldelad till** kan du tilldela aviseringen till dig själv eller ta bort den.</span><span class="sxs-lookup"><span data-stu-id="b3118-139">In **Assigned to**, you can assign the alert to yourself or unassign it.</span></span>

    ![Aviseringstillstånd](../../media/defender-identity/alert-state.png)

- <span data-ttu-id="b3118-141">Aviseringsinformation **–** **Under** Aviseringsinformation hittar du mer information om den specifika aviseringen, följer en länk till dokumentation om typen av avisering, ser vilken händelse aviseringen är kopplad till, granskar alla automatiska undersökningar kopplade till den här aviseringstypen och ser vilka enheter och användare som påverkas.</span><span class="sxs-lookup"><span data-stu-id="b3118-141">**Alert details** - Under **Alert details**, you can find more information about the specific alert, follow a link to documentation about the type of alert, see which incident the alert is associated with, review any automated investigations linked to this alert type, and see the impacted devices and users.</span></span>

    ![Aviseringsinformation](../../media/defender-identity/alert-details.png)

- <span data-ttu-id="b3118-143">**Kommentarer & –** här kan du lägga till dina kommentarer i aviseringen och se historiken för alla åtgärder som är associerade med aviseringen.</span><span class="sxs-lookup"><span data-stu-id="b3118-143">**Comments & history** - Here you can add your comments to the alert, and see the history of all actions associated with the alert.</span></span>

    ![Kommentarer och historik](../../media/defender-identity/comments-history.png)

- <span data-ttu-id="b3118-145">**Hantera avisering** – Om du **väljer Hantera** avisering går du till ett fönster där du kan redigera:</span><span class="sxs-lookup"><span data-stu-id="b3118-145">**Manage alert** - If you select **Manage alert**, you'll go to a pane that will allow you to edit the:</span></span>
  - <span data-ttu-id="b3118-146">**Status** – Du kan välja **Ny**, **Löst** eller **Pågår.**</span><span class="sxs-lookup"><span data-stu-id="b3118-146">**Status** - You can choose **New**, **Resolved** or **In progress**.</span></span>
  - <span data-ttu-id="b3118-147">**Klassificering** – du kan välja **True alert eller** False **alert.**</span><span class="sxs-lookup"><span data-stu-id="b3118-147">**Classification** - You can choose **True alert** or **False alert**.</span></span>
  - <span data-ttu-id="b3118-148">**Kommentar** – Du kan lägga till en kommentar om aviseringen.</span><span class="sxs-lookup"><span data-stu-id="b3118-148">**Comment** - You can add a comment about the alert.</span></span>

    <span data-ttu-id="b3118-149">Om du väljer de tre punkterna bredvid Hantera avisering  kan du kontakta en hotexpert **,** exportera aviseringen till en Excel-fil eller Länka till **en annan händelse**.</span><span class="sxs-lookup"><span data-stu-id="b3118-149">If you select the three dots next to **Manage alert**, you can **Consult a threat expert**, **Export** the alert to an Excel file, or **Link to another incident**.</span></span>

    ![Hantera avisering](../../media/defender-identity/manage-alert.png)

    > [!NOTE]
    > <span data-ttu-id="b3118-151">I Excel finns nu två länkar: Visa **i Microsoft Defender** för identitet **och visa i Microsoft 365 Defender.**</span><span class="sxs-lookup"><span data-stu-id="b3118-151">In the Excel file, you now have two links available: **View in Microsoft Defender for Identity** and **View in Microsoft 365 Defender**.</span></span> <span data-ttu-id="b3118-152">Varje länk tar dig till relevant portal och ger information om aviseringen där.</span><span class="sxs-lookup"><span data-stu-id="b3118-152">Each link will bring you to the relevant portal, and provide information about the alert there.</span></span>

## <a name="see-also"></a><span data-ttu-id="b3118-153">Se även</span><span class="sxs-lookup"><span data-stu-id="b3118-153">See also</span></span>

- [<span data-ttu-id="b3118-154">Undersök aviseringar i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b3118-154">Investigate alerts in Microsoft 365 Defender</span></span>](../defender/investigate-alerts.md)
