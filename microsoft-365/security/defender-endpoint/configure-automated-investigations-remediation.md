---
title: Konfigurera funktioner för automatisk undersökning och åtgärder
description: Konfigurera automatisk undersökning och åtgärder i Microsoft Defender för Endpoint.
keywords: konfigurera, konfigurera, automatiserad, undersökning, identifiering, aviseringar, åtgärd, svar
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: JoeDavies-MSFT
ms.author: josephd
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: how-to
ms.date: 01/27/2021
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.openlocfilehash: bd86458749db4019bb247a3664748b9891965754
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841355"
---
# <a name="configure-automated-investigation-and-remediation-capabilities-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="1955d-104">Konfigurera funktioner för automatisk undersökning och åtgärder i Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="1955d-104">Configure automated investigation and remediation capabilities in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1955d-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="1955d-105">**Applies to:**</span></span>
- [<span data-ttu-id="1955d-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="1955d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1955d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1955d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="1955d-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="1955d-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="1955d-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="1955d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="1955d-110">Om din organisation använder [Microsoft Defender](/windows/security/threat-protection/) för Slutpunkt (Defender för [Slutpunkt)](/microsoft-365/security/defender-endpoint/automated-investigations) kan automatiska undersöknings- och åtgärdsfunktioner spara din tid och ditt arbete med säkerhetsåtgärder.</span><span class="sxs-lookup"><span data-stu-id="1955d-110">If your organization is using [Microsoft Defender for Endpoint](/windows/security/threat-protection/) (Defender for Endpoint), [automated investigation and remediation capabilities](/microsoft-365/security/defender-endpoint/automated-investigations) can save your security operations team time and effort.</span></span> <span data-ttu-id="1955d-111">Som beskrivs i [det här blogginlägget](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/enhance-your-soc-with-microsoft-defender-atp-automatic/ba-p/848946)efterliknar de här funktionerna de idealiska steg som en säkerhetsanalytiker tar för att undersöka och åtgärda hot.</span><span class="sxs-lookup"><span data-stu-id="1955d-111">As outlined in [this blog post](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/enhance-your-soc-with-microsoft-defender-atp-automatic/ba-p/848946), these capabilities mimic the ideal steps that a security analyst takes to investigate and remediate threats.</span></span> <span data-ttu-id="1955d-112">[Läs mer om automatiserad undersökning och åtgärd.](/microsoft-365/security/defender-endpoint/automated-investigations)</span><span class="sxs-lookup"><span data-stu-id="1955d-112">[Learn more about automated investigation and remediation](/microsoft-365/security/defender-endpoint/automated-investigations).</span></span> 

<span data-ttu-id="1955d-113">Om du vill konfigurera automatisk undersökning och åtgärd</span><span class="sxs-lookup"><span data-stu-id="1955d-113">To configure automated investigation and remediation,</span></span>
1. <span data-ttu-id="1955d-114">[Aktivera funktionerna](#turn-on-automated-investigation-and-remediation). och</span><span class="sxs-lookup"><span data-stu-id="1955d-114">[Turn on the features](#turn-on-automated-investigation-and-remediation); and</span></span> 
2. <span data-ttu-id="1955d-115">[Konfigurera enhetsgrupper](#set-up-device-groups).</span><span class="sxs-lookup"><span data-stu-id="1955d-115">[Set up device groups](#set-up-device-groups).</span></span>

## <a name="turn-on-automated-investigation-and-remediation"></a><span data-ttu-id="1955d-116">Aktivera automatisk undersökning och åtgärd</span><span class="sxs-lookup"><span data-stu-id="1955d-116">Turn on automated investigation and remediation</span></span>

1. <span data-ttu-id="1955d-117">Som global administratör eller säkerhetsadministratör går du till Microsoft Defender Säkerhetscenter ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ) och loggar in.</span><span class="sxs-lookup"><span data-stu-id="1955d-117">As a global administrator or security administrator, go to the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)) and sign in.</span></span>
2. <span data-ttu-id="1955d-118">I navigeringsfönstret väljer du **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="1955d-118">In the navigation pane, choose **Settings**.</span></span>
3. <span data-ttu-id="1955d-119">I avsnittet **Allmänt** väljer du **Avancerade funktioner.**</span><span class="sxs-lookup"><span data-stu-id="1955d-119">In the **General** section, select **Advanced features**.</span></span>
4. <span data-ttu-id="1955d-120">Aktivera både automatisk **undersökning och** matcha **aviseringar automatiskt.**</span><span class="sxs-lookup"><span data-stu-id="1955d-120">Turn on both **Automated Investigation** and **Automatically resolve alerts**.</span></span>

## <a name="set-up-device-groups"></a><span data-ttu-id="1955d-121">Konfigurera enhetsgrupper</span><span class="sxs-lookup"><span data-stu-id="1955d-121">Set up device groups</span></span>

1. <span data-ttu-id="1955d-122">I Microsoft Defender Säkerhetscenter ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ), på **sidan Inställningar,** under **Behörigheter** väljer du **Enhetsgrupper**.</span><span class="sxs-lookup"><span data-stu-id="1955d-122">In the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)), on the **Settings** page, under **Permissions**, select **Device groups**.</span></span>
2. <span data-ttu-id="1955d-123">Välj **+ Lägg till enhetsgrupp.**</span><span class="sxs-lookup"><span data-stu-id="1955d-123">Select **+ Add device group**.</span></span>
3. <span data-ttu-id="1955d-124">Skapa minst en enhetsgrupp enligt följande:</span><span class="sxs-lookup"><span data-stu-id="1955d-124">Create at least one device group, as follows:</span></span>
   - <span data-ttu-id="1955d-125">Ange ett namn och en beskrivning för enhetsgruppen.</span><span class="sxs-lookup"><span data-stu-id="1955d-125">Specify a name and description for the device group.</span></span>
   - <span data-ttu-id="1955d-126">I listan **Automationsnivå** väljer du en nivå, till exempel Fullständigt – åtgärda **hot automatiskt.**</span><span class="sxs-lookup"><span data-stu-id="1955d-126">In the **Automation level list**, select a level, such as **Full – remediate threats automatically**.</span></span> <span data-ttu-id="1955d-127">Automationsnivån avgör om åtgärder vidtas automatiskt eller bara efter godkännande.</span><span class="sxs-lookup"><span data-stu-id="1955d-127">The automation level determines whether remediation actions are taken automatically, or only upon approval.</span></span> <span data-ttu-id="1955d-128">Mer information finns i [Automatiseringsnivåer i automatiserad undersökning och åtgärd.](automation-levels.md)</span><span class="sxs-lookup"><span data-stu-id="1955d-128">To learn more, see [Automation levels in automated investigation and remediation](automation-levels.md).</span></span>
   - <span data-ttu-id="1955d-129">I avsnittet **Medlemmar** använder du ett eller flera villkor för att identifiera och inkludera enheter.</span><span class="sxs-lookup"><span data-stu-id="1955d-129">In the **Members** section, use one or more conditions to identify and include devices.</span></span>
   - <span data-ttu-id="1955d-130">På fliken **Användaråtkomst** väljer du de [Azure Active Directory som](/azure/active-directory/fundamentals/active-directory-manage-groups?context=azure/active-directory/users-groups-roles/context/ugr-context) ska ha åtkomst till enhetsgruppen som du skapar.</span><span class="sxs-lookup"><span data-stu-id="1955d-130">On the **User access** tab, select the [Azure Active Directory groups](/azure/active-directory/fundamentals/active-directory-manage-groups?context=azure/active-directory/users-groups-roles/context/ugr-context) who should have access to the device group you're creating.</span></span>
4. <span data-ttu-id="1955d-131">Välj **Klar** när du är klar med att konfigurera enhetsgruppen.</span><span class="sxs-lookup"><span data-stu-id="1955d-131">Select **Done** when you're finished setting up your device group.</span></span>

## <a name="next-steps"></a><span data-ttu-id="1955d-132">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="1955d-132">Next steps</span></span>

- [<span data-ttu-id="1955d-133">Gå till Åtgärdscenter om du vill visa väntande och slutförda åtgärdsåtgärder</span><span class="sxs-lookup"><span data-stu-id="1955d-133">Visit the Action Center to view pending and completed remediation actions</span></span>](/microsoft-365/security/defender-endpoint/auto-investigation-action-center#the-action-center)
- [<span data-ttu-id="1955d-134">Granska och godkänna väntande åtgärder</span><span class="sxs-lookup"><span data-stu-id="1955d-134">Review and approve pending actions</span></span>](/microsoft-365/security/defender-endpoint/manage-auto-investigation)

## <a name="see-also"></a><span data-ttu-id="1955d-135">Se även</span><span class="sxs-lookup"><span data-stu-id="1955d-135">See also</span></span>

- [<span data-ttu-id="1955d-136">Åtgärda falska positiva/negativa i Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="1955d-136">Address false positives/negatives in Microsoft Defender for Endpoint</span></span>](defender-endpoint-false-positives-negatives.md)
