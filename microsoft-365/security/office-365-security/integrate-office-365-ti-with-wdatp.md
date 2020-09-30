---
title: Använda Microsoft Defender för Office 365 tillsammans med Microsoft Defender för slut punkten
f1.keywords:
- NOCSH
keywords: integrering, Microsoft Defender, ATP
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 09/29/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Använd Microsoft Defender för Office 365 tillsammans med Microsoft Defender Avancerat skydd för att få mer detaljerad information om hot mot dina enheter och e-postinnehåll.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2c95e15c3cf16547843f9d2976dbf9df0d5747c0
ms.sourcegitcommit: 6b1d0bea86ced26cae51695c0077adce8bcff3c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/30/2020
ms.locfileid: "48309243"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="e751e-104">Använda Microsoft Defender för Office 365 tillsammans med Microsoft Defender Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="e751e-104">Use Microsoft Defender for Office 365 together with Microsoft Defender Advanced Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="e751e-105">[Microsoft Defender för Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) kan konfigureras så att det fungerar med [Microsoft Defender för slut punkten](https://docs.microsoft.com/windows/security/threat-protection).</span><span class="sxs-lookup"><span data-stu-id="e751e-105">[Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) can be configured to work with [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection).</span></span>

<span data-ttu-id="e751e-106">Att integrera Microsoft Defender för Office 365 med Microsoft Defender för slut punkten kan hjälpa din säkerhets åtgärds grupp övervakning och vidta åtgärder snabbt om användarnas enheter löper risk.</span><span class="sxs-lookup"><span data-stu-id="e751e-106">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint can help your security operations team monitor and take action quickly if users' devices are at risk.</span></span> <span data-ttu-id="e751e-107">När integrationen är aktive rad kan till exempel din säkerhets åtgärds grupp se vilka enheter som eventuellt påverkas av ett identifierat e-postmeddelande, samt hur många senaste aviseringar som genererades för dessa enheter i Microsoft Defender för slut punkter.</span><span class="sxs-lookup"><span data-stu-id="e751e-107">For example, once integration is enabled, your security operations team will be able to see the devices that are potentially affected by a detected email message, as well as how many recent alerts were generated for those devices in Microsoft Defender for Endpoint.</span></span> 

<span data-ttu-id="e751e-108">I följande bild visas hur fliken **enheter** ser ut som har Microsoft Defender för slut punkts integrering aktiverat:</span><span class="sxs-lookup"><span data-stu-id="e751e-108">The following image depicts what the **Devices** tab looks like have Microsoft Defender for Endpoint integration enabled:</span></span>
  
![När Microsoft Defender för slut punkt är aktiverat kan du se en lista med enheter med aviseringar.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
<span data-ttu-id="e751e-110">I det här exemplet kan du se att mottagarna av det identifierade e-postmeddelandet har fyra enheter och en har en avisering.</span><span class="sxs-lookup"><span data-stu-id="e751e-110">In this example, you can see that the recipients of the detected email message have four devices and one has an alert.</span></span> <span data-ttu-id="e751e-111">Om du klickar på länken för en enhet öppnas den i Microsoft Defender säkerhets Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).</span><span class="sxs-lookup"><span data-stu-id="e751e-111">Clicking the link for a device opens its page in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

> [!TIP]
> <span data-ttu-id="e751e-112">**[Läs mer om Microsoft Defender säkerhets Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (kallas även Microsoft Defender ATP-portalen.)</span><span class="sxs-lookup"><span data-stu-id="e751e-112">**[Learn more about the Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (also referred to as the Microsoft Defender ATP portal.)</span></span>
  
## <a name="requirements"></a><span data-ttu-id="e751e-113">Krav</span><span class="sxs-lookup"><span data-stu-id="e751e-113">Requirements</span></span>

- <span data-ttu-id="e751e-114">Din organisation måste ha Microsoft Defender för Office 365 (eller Office 365 E5) och Microsoft Defender för slut punkt.</span><span class="sxs-lookup"><span data-stu-id="e751e-114">Your organization must have Microsoft Defender for Office 365 (or Office 365 E5) and Microsoft Defender for Endpoint.</span></span>
    
- <span data-ttu-id="e751e-115">Du måste vara global administratör eller ha en säkerhets administratörs roll (till exempel säkerhets administratör) som är tilldelad i [ &amp; Säkerhetscenter](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="e751e-115">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in the [Security &amp; Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="e751e-116">(Se [behörigheter i säkerhets &amp; kontroll Center](permissions-in-the-security-and-compliance-center.md))</span><span class="sxs-lookup"><span data-stu-id="e751e-116">(See [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>
    
- <span data-ttu-id="e751e-117">Du måste ha till gång till både [Explorer (eller real tids identifieringar)](threat-explorer.md) i säkerhets & efterlevnaden för säkerhet och Microsoft Defender säkerhets Center.</span><span class="sxs-lookup"><span data-stu-id="e751e-117">You must have access to both [Explorer (or real-time detections)](threat-explorer.md) in the Security & Compliance Center and the Microsoft Defender Security Center.</span></span>
    
## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="e751e-118">Integrera Microsoft Defender för Office 365 med Microsoft Defender för slut punkt</span><span class="sxs-lookup"><span data-stu-id="e751e-118">To integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="e751e-119">Att integrera Microsoft Defender för Office 365 med Microsoft Defender för slut punkten är inställt på både säkerhets & och Microsoft Defender säkerhets Center.</span><span class="sxs-lookup"><span data-stu-id="e751e-119">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint is set up by using both the Security & Compliance Center AND the Microsoft Defender Security Center.</span></span>
  
1. <span data-ttu-id="e751e-120">Som global administratör eller säkerhets administratör går du till [https://protection.office.com](https://protection.office.com) och loggar in.</span><span class="sxs-lookup"><span data-stu-id="e751e-120">As a global administrator or a security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="e751e-121">(Du kommer till Office 365 Security & Compliance Center.)</span><span class="sxs-lookup"><span data-stu-id="e751e-121">(This takes you to the Office 365 Security & Compliance Center.)</span></span>
    
2. <span data-ttu-id="e751e-122">Välj **Threat Management**  >  **Explorer**i navigerings fönstret.</span><span class="sxs-lookup"><span data-stu-id="e751e-122">In the navigation pane, choose **Threat management** > **Explorer**.</span></span><br><span data-ttu-id="e751e-123">![Utforskaren i Threat Management-menyn](../../media/ThreatMgmt-Explorer-nav.png)</span><span class="sxs-lookup"><span data-stu-id="e751e-123">![Explorer in Threat Management menu](../../media/ThreatMgmt-Explorer-nav.png)</span></span><br>
    
3. <span data-ttu-id="e751e-124">I det övre högra hörnet av skärmen väljer du **WDATP inställningar**.</span><span class="sxs-lookup"><span data-stu-id="e751e-124">In the upper right corner of the screen, choose **WDATP Settings**.</span></span>
    
4. <span data-ttu-id="e751e-125">I dialog rutan Microsoft Defender för slut punkts anslutning aktiverar **du Anslut till Windows ATP**.</span><span class="sxs-lookup"><span data-stu-id="e751e-125">In the Microsoft Defender for Endpoint connection dialog box, turn on **Connect to Windows ATP**.</span></span><br><span data-ttu-id="e751e-126">![Microsoft Defender för slut punkts anslutning](../../media/Explorer-WDATPConnection-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="e751e-126">![Microsoft Defender for Endpoint connection](../../media/Explorer-WDATPConnection-dialog.png)</span></span><br>
    
5. <span data-ttu-id="e751e-127">Gå till Microsoft Defender säkerhets Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).</span><span class="sxs-lookup"><span data-stu-id="e751e-127">Go to the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

6. <span data-ttu-id="e751e-128">I navigerings fältet väljer du **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="e751e-128">In the navigation bar, choose **Settings**.</span></span> <span data-ttu-id="e751e-129">Under **Allmänt**väljer du **avancerade funktioner**.</span><span class="sxs-lookup"><span data-stu-id="e751e-129">Then, under **General**, choose **Advanced features**.</span></span>

7. <span data-ttu-id="e751e-130">Rulla ned till **Office 365 Threat Intelligence-anslutning**och slå på anslutningen.</span><span class="sxs-lookup"><span data-stu-id="e751e-130">Scroll down to **Office 365 Threat Intelligence connection**, and turn the connection on.</span></span><br/><span data-ttu-id="e751e-131">![Anslutning till Office 365 Threat Intelligence](../../media/mdatp-oatptoggle.png)</span><span class="sxs-lookup"><span data-stu-id="e751e-131">![Office 365 threat intelligence connection](../../media/mdatp-oatptoggle.png)</span></span><br>

## <a name="related-articles"></a><span data-ttu-id="e751e-132">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="e751e-132">Related articles</span></span>

[<span data-ttu-id="e751e-133">Hot-och svars funktioner i Office 365</span><span class="sxs-lookup"><span data-stu-id="e751e-133">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)
  
[<span data-ttu-id="e751e-134">Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="e751e-134">Microsoft Defender for Office 365</span></span>](office-365-atp.md)
  
[<span data-ttu-id="e751e-135">Microsoft Defender för slut punkt</span><span class="sxs-lookup"><span data-stu-id="e751e-135">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection)
