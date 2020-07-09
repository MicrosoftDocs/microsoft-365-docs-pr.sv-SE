---
title: Integrera Office 365 ATP med Microsoft Defender Avancerat skydd
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 07/08/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 414fa693-d7b7-4a1d-a387-ebc3b6a52889
ms.collection:
- M365-security-compliance
description: Integrera office 365 avancerat skydd mot hot med Microsoft Defender Advanced Threat Protection för att se mer detaljerad information om hothantering.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bfb87edd24a22033b3771ba0fd3c4f1afbbc988e
ms.sourcegitcommit: 41bc923bb31598cea8f02923792c1cd786e39616
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086721"
---
# <a name="integrate-office-365-advanced-threat-protection-with-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="a01a1-103">Integrera avancerat hotskydd för Office 365 med Microsoft Defender avancerat hotskydd</span><span class="sxs-lookup"><span data-stu-id="a01a1-103">Integrate Office 365 Advanced Threat Protection with Microsoft Defender Advanced Threat Protection</span></span>

<span data-ttu-id="a01a1-104">[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) (Office 365 ATP) kan konfigureras för att fungera med [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection) (Microsoft Defender ATP).</span><span class="sxs-lookup"><span data-stu-id="a01a1-104">[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) (Office 365 ATP) can be configured to work with [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection) (Microsoft Defender ATP).</span></span>

<span data-ttu-id="a01a1-105">Genom att integrera Office 365 ATP med Microsoft Defender ATP kan säkerhetsoperationsteamet övervaka och vidta åtgärder snabbt om användarnas enheter är i riskzonen.</span><span class="sxs-lookup"><span data-stu-id="a01a1-105">Integrating Office 365 ATP with Microsoft Defender ATP can help your security operations team monitor and take action quickly if users' devices are at risk.</span></span> <span data-ttu-id="a01a1-106">När integreringen till exempel är aktiverad kan säkerhetsoperationsteamet se de enheter som kan påverkas av ett upptäckt e-postmeddelande, samt hur många aviseringar dessa enheter har nyligen i Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="a01a1-106">For example, once integration is enabled, your security operations team will be able to see the devices that are potentially affected by a detected email message, as well as how many recent alerts those devices have in Microsoft Defender ATP.</span></span> 

<span data-ttu-id="a01a1-107">Följande bild visar hur fliken **Enheter** ser ut om Microsoft Defender ATP-integrering aktiverad:</span><span class="sxs-lookup"><span data-stu-id="a01a1-107">The following image depicts what the **Devices** tab looks like have Microsoft Defender ATP integration enabled:</span></span>
  
![När Microsoft Defender ATP är aktiverat kan du se en lista över enheter med aviseringar.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
<span data-ttu-id="a01a1-109">I det här exemplet kan du se att mottagarna av det identifierade e-postmeddelandet har fyra enheter och en har en avisering.</span><span class="sxs-lookup"><span data-stu-id="a01a1-109">In this example, you can see that the recipients of the detected email message have four devices and one has an alert.</span></span> <span data-ttu-id="a01a1-110">Om du klickar på länken för en enhet öppnas sidan i Microsoft Defender Security Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).</span><span class="sxs-lookup"><span data-stu-id="a01a1-110">Clicking the link for a device opens its page in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

> [!TIP]
> <span data-ttu-id="a01a1-111">**[Läs mer om Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (kallas även Microsoft Defender ATP-portalen.)</span><span class="sxs-lookup"><span data-stu-id="a01a1-111">**[Learn more about the Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (also referred to as the Microsoft Defender ATP portal.)</span></span>
  
## <a name="requirements"></a><span data-ttu-id="a01a1-112">Krav</span><span class="sxs-lookup"><span data-stu-id="a01a1-112">Requirements</span></span>

- <span data-ttu-id="a01a1-113">Din organisation måste ha Office 365 ATP-abonnemang 2 (eller Office 365 E5) och Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="a01a1-113">Your organization must have Office 365 ATP Plan 2 (or Office 365 E5) and Microsoft Defender ATP.</span></span>
    
- <span data-ttu-id="a01a1-114">Du måste vara global administratör eller ha en säkerhetsadministratörsroll (till exempel säkerhetsadministratör) tilldelad i [ &amp; Säkerhetsefterlevnadscenter](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="a01a1-114">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in the [Security &amp; Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="a01a1-115">(Se [behörigheter i &amp; Säkerhetsefterlevnadscenter](permissions-in-the-security-and-compliance-center.md))</span><span class="sxs-lookup"><span data-stu-id="a01a1-115">(See [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>
    
- <span data-ttu-id="a01a1-116">Du måste ha tillgång till både [Explorer (eller realtidsidentifieringar)](threat-explorer.md) i Security & Compliance Center och Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="a01a1-116">You must have access to both [Explorer (or real-time detections)](threat-explorer.md) in the Security & Compliance Center and the Microsoft Defender Security Center.</span></span>
    
## <a name="to-integrate-office-365-atp-with-microsoft-defender-atp"></a><span data-ttu-id="a01a1-117">Så här integrerar du Office 365 ATP med Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="a01a1-117">To integrate Office 365 ATP with Microsoft Defender ATP</span></span>

<span data-ttu-id="a01a1-118">Integrering av Office 365 ATP med Microsoft Defender ATP konfigureras med både Security & Compliance Center och Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="a01a1-118">Integrating Office 365 ATP with Microsoft Defender ATP is set up by using both the Security & Compliance Center AND the Microsoft Defender Security Center.</span></span>
  
1. <span data-ttu-id="a01a1-119">Som global administratör eller säkerhetsadministratör går du till [https://protection.office.com](https://protection.office.com) och loggar in.</span><span class="sxs-lookup"><span data-stu-id="a01a1-119">As a global administrator or a security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="a01a1-120">(Detta tar dig till Säkerhets- & Compliance Center för Office 365.)</span><span class="sxs-lookup"><span data-stu-id="a01a1-120">(This takes you to the Office 365 Security & Compliance Center.)</span></span>
    
2. <span data-ttu-id="a01a1-121">Välj **Hothanteringsutforskaren**i navigeringsfönstret  >  **Explorer**.</span><span class="sxs-lookup"><span data-stu-id="a01a1-121">In the navigation pane, choose **Threat management** > **Explorer**.</span></span><br><span data-ttu-id="a01a1-122">![Explorer på menyn Hothantering](../../media/ThreatMgmt-Explorer-nav.png)</span><span class="sxs-lookup"><span data-stu-id="a01a1-122">![Explorer in Threat Management menu](../../media/ThreatMgmt-Explorer-nav.png)</span></span><br>
    
3. <span data-ttu-id="a01a1-123">I det övre högra hörnet av skärmen väljer du **WDATP-inställningar**.</span><span class="sxs-lookup"><span data-stu-id="a01a1-123">In the upper right corner of the screen, choose **WDATP Settings**.</span></span>
    
4. <span data-ttu-id="a01a1-124">Aktivera **Anslut till Windows ATP**i dialogrutan Microsoft Defender ATP-anslutning .</span><span class="sxs-lookup"><span data-stu-id="a01a1-124">In the Microsoft Defender ATP connection dialog box, turn on **Connect to Windows ATP**.</span></span><br><span data-ttu-id="a01a1-125">![Microsoft Defender ATP-anslutning](../../media/Explorer-WDATPConnection-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="a01a1-125">![Microsoft Defender ATP connection](../../media/Explorer-WDATPConnection-dialog.png)</span></span><br>
    
5. <span data-ttu-id="a01a1-126">Gå till Microsoft Defender Security Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).</span><span class="sxs-lookup"><span data-stu-id="a01a1-126">Go to the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

6. <span data-ttu-id="a01a1-127">Välj **Inställningar**i navigeringsfältet .</span><span class="sxs-lookup"><span data-stu-id="a01a1-127">In the navigation bar, choose **Settings**.</span></span> <span data-ttu-id="a01a1-128">Välj sedan Avancerade **funktioner**under **Allmänt**.</span><span class="sxs-lookup"><span data-stu-id="a01a1-128">Then, under **General**, choose **Advanced features**.</span></span>

7. <span data-ttu-id="a01a1-129">Bläddra ned till **Office 365 Threat Intelligence-anslutning**och aktivera anslutningen.</span><span class="sxs-lookup"><span data-stu-id="a01a1-129">Scroll down to **Office 365 Threat Intelligence connection**, and turn the connection on.</span></span><br/><span data-ttu-id="a01a1-130">![Informationsanslutning till Hotinformation i Office 365](../../media/mdatp-oatptoggle.png)</span><span class="sxs-lookup"><span data-stu-id="a01a1-130">![Office 365 threat intelligence connection](../../media/mdatp-oatptoggle.png)</span></span><br>

## <a name="related-articles"></a><span data-ttu-id="a01a1-131">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="a01a1-131">Related articles</span></span>

[<span data-ttu-id="a01a1-132">Funktioner för utredning och svar av hot i Office 365</span><span class="sxs-lookup"><span data-stu-id="a01a1-132">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)
  
[<span data-ttu-id="a01a1-133">Office 365 Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="a01a1-133">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="a01a1-134">Microsoft Defender Avancerat skydd.</span><span class="sxs-lookup"><span data-stu-id="a01a1-134">Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection)
