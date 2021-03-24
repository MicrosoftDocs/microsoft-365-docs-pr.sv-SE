---
title: Använda Microsoft Defender för Office 365 tillsammans med Microsoft Defender för Endpoint
f1.keywords:
- NOCSH
keywords: integrera, Microsoft Defender, ATP
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 01/21/2021
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Använd Microsoft Defender för Office 365 tillsammans med Microsoft Defender för Endpoint om du vill ha mer detaljerad information om hot mot dina enheter och e-postinnehåll.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bac2414419d673f261d0d0162d8ae742385fd4eb
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073281"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="74ed0-104">Använda Microsoft Defender för Office 365 tillsammans med Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="74ed0-104">Use Microsoft Defender for Office 365 together with Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="74ed0-105">[Microsoft Defender för Office 365](defender-for-office-365.md) kan konfigureras för att fungera med [Microsoft Defender för slutpunkt.](/windows/security/threat-protection)</span><span class="sxs-lookup"><span data-stu-id="74ed0-105">[Microsoft Defender for Office 365](defender-for-office-365.md) can be configured to work with [Microsoft Defender for Endpoint](/windows/security/threat-protection).</span></span>

<span data-ttu-id="74ed0-106">Genom att integrera Microsoft Defender för Office 365 med Microsoft Defender för Endpoint kan du hjälpa din säkerhetsåtgärdsgrupp att övervaka och vidta åtgärder snabbt om användarnas enheter är i risktagande.</span><span class="sxs-lookup"><span data-stu-id="74ed0-106">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint can help your security operations team monitor and take action quickly if users' devices are at risk.</span></span> <span data-ttu-id="74ed0-107">När integration har aktiverats kan teamet för säkerhetsåtgärder till exempel se de enheter som eventuellt påverkas av ett upptäckt e-postmeddelande, samt hur många aviseringar som nyligen har genererats för dessa enheter i Microsoft Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="74ed0-107">For example, once integration is enabled, your security operations team will be able to see the devices that are potentially affected by a detected email message, as well as how many recent alerts were generated for those devices in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="74ed0-108">I följande bild visas hur fliken **Enheter ser** ut när du har aktiverat Microsoft Defender för slutpunktsintegrering:</span><span class="sxs-lookup"><span data-stu-id="74ed0-108">The following image depicts what the **Devices** tab looks like when you have Microsoft Defender for Endpoint integration enabled:</span></span>

![När Microsoft Defender för slutpunkt är aktiverat visas en lista över enheter med aviseringar.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

<span data-ttu-id="74ed0-110">I det här exemplet kan du se att mottagarna av det identifierade e-postmeddelandet har fyra enheter och en har en avisering.</span><span class="sxs-lookup"><span data-stu-id="74ed0-110">In this example, you can see that the recipients of the detected email message have four devices and one has an alert.</span></span> <span data-ttu-id="74ed0-111">När du klickar på länken för en enhet öppnas sidan i Microsoft Defender Säkerhetscenter ( <https://securitycenter.windows.com> ).</span><span class="sxs-lookup"><span data-stu-id="74ed0-111">Clicking the link for a device opens its page in the Microsoft Defender Security Center (<https://securitycenter.windows.com>).</span></span>

> [!TIP]
> <span data-ttu-id="74ed0-112">**[Läs mer om Microsoft Defender Säkerhetscenter](/windows/security/threat-protection/microsoft-defender-atp/use)** (kallas även Microsoft Defender för Slutpunktsportalen).</span><span class="sxs-lookup"><span data-stu-id="74ed0-112">**[Learn more about the Microsoft Defender Security Center](/windows/security/threat-protection/microsoft-defender-atp/use)** (also referred to as the Microsoft Defender for Endpoint portal.)</span></span>

## <a name="requirements"></a><span data-ttu-id="74ed0-113">Krav</span><span class="sxs-lookup"><span data-stu-id="74ed0-113">Requirements</span></span>

- <span data-ttu-id="74ed0-114">Din organisation måste ha Microsoft Defender för Office 365 (eller Office 365 E5) och Microsoft Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="74ed0-114">Your organization must have Microsoft Defender for Office 365 (or Office 365 E5) and Microsoft Defender for Endpoint.</span></span>

- <span data-ttu-id="74ed0-115">Du måste vara global administratör eller ha en säkerhetsadministratörsroll (till exempel säkerhetsadministratör) som har [tilldelats i & Säkerhets- och efterlevnadscenter.](https://protection.office.com)</span><span class="sxs-lookup"><span data-stu-id="74ed0-115">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="74ed0-116">(Se [Behörigheter i säkerhets- & Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md))</span><span class="sxs-lookup"><span data-stu-id="74ed0-116">(See [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>

- <span data-ttu-id="74ed0-117">Du måste ha tillgång till både [Utforskaren (eller](threat-explorer.md) identifieringar i realtid) i säkerhets- & säkerhets- och efterlevnadscentret för Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="74ed0-117">You must have access to both [Explorer (or real-time detections)](threat-explorer.md) in the Security & Compliance Center and the Microsoft Defender Security Center.</span></span>

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="74ed0-118">Integrera Microsoft Defender för Office 365 med Microsoft Defender för slutpunkt</span><span class="sxs-lookup"><span data-stu-id="74ed0-118">To integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="74ed0-119">Integrering av Microsoft Defender för Office 365 med Microsoft Defender för slutpunkt konfigureras med hjälp av både Säkerhets- och &-efterlevnadscenter och Microsoft Defender Säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="74ed0-119">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint is set up by using both the Security & Compliance Center AND the Microsoft Defender Security Center.</span></span>

1. <span data-ttu-id="74ed0-120">Som global administratör eller säkerhetsadministratör går du till <https://protection.office.com> och loggar in.</span><span class="sxs-lookup"><span data-stu-id="74ed0-120">As a global administrator or a security administrator, go to <https://protection.office.com> and sign in.</span></span> <span data-ttu-id="74ed0-121">(Då kommer du till Säkerhets- & Säkerhets- & Office 365.)</span><span class="sxs-lookup"><span data-stu-id="74ed0-121">(This takes you to the Office 365 Security & Compliance Center.)</span></span>

2. <span data-ttu-id="74ed0-122">Välj Hothanteringsutforskaren **i** \> **navigeringsfönstret.**</span><span class="sxs-lookup"><span data-stu-id="74ed0-122">In the navigation pane, choose **Threat management** \> **Explorer**.</span></span>

   ![Utforskaren på menyn Hantering av hot](../../media/ThreatMgmt-Explorer-nav.png)

3. <span data-ttu-id="74ed0-124">I skärmens övre högra hörn väljer du **Defender för Slutpunktsinställningar (MDE-inställningar).**</span><span class="sxs-lookup"><span data-stu-id="74ed0-124">In the upper right corner of the screen, choose **Defender for Endpoint Settings (MDE Settings)**.</span></span>

4. <span data-ttu-id="74ed0-125">I dialogrutan Anslutning till Microsoft Defender för slutpunkt aktiverar du **Anslut till Microsoft Defender för Slutpunkt.**</span><span class="sxs-lookup"><span data-stu-id="74ed0-125">In the Microsoft Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span>

   ![Microsoft Defender för Slutpunktsanslutning](../../media/Explorer-WDATPConnection-dialog.png)

5. <span data-ttu-id="74ed0-127">Gå till Microsoft Defender Säkerhetscenter ( <https://securitycenter.windows.com> ).</span><span class="sxs-lookup"><span data-stu-id="74ed0-127">Go to the Microsoft Defender Security Center (<https://securitycenter.windows.com>).</span></span>

6. <span data-ttu-id="74ed0-128">Välj Inställningar i **navigeringsfältet.**</span><span class="sxs-lookup"><span data-stu-id="74ed0-128">In the navigation bar, choose **Settings**.</span></span> <span data-ttu-id="74ed0-129">Välj sedan **Avancerade funktioner** under **Allmänt.**</span><span class="sxs-lookup"><span data-stu-id="74ed0-129">Then, under **General**, choose **Advanced features**.</span></span>

7. <span data-ttu-id="74ed0-130">Bläddra ned till **Office 365 Threat Intelligence-anslutning** och aktivera anslutningen.</span><span class="sxs-lookup"><span data-stu-id="74ed0-130">Scroll down to **Office 365 Threat Intelligence connection**, and turn the connection on.</span></span>

   ![Office 365-anslutning för hotinformation](../../media/mdatp-oatptoggle.png)

## <a name="related-articles"></a><span data-ttu-id="74ed0-132">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="74ed0-132">Related articles</span></span>

[<span data-ttu-id="74ed0-133">Funktioner för undersökning av hot och svar i Office 365</span><span class="sxs-lookup"><span data-stu-id="74ed0-133">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)

[<span data-ttu-id="74ed0-134">Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="74ed0-134">Microsoft Defender for Office 365</span></span>](defender-for-office-365.md)

[<span data-ttu-id="74ed0-135">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="74ed0-135">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection)