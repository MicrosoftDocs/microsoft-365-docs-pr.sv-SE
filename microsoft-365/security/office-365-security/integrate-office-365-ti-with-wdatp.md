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
description: Integrera Office 365 Avancerat skydd med Microsoft Defender Avancerat skydd för att visa mer detaljerad information om Threat Management.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0906b8b44922084a65999dd9ab10a09c827605c2
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201977"
---
# <a name="integrate-office-365-advanced-threat-protection-with-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="8fc4a-103">Integrera Office 365 Avancerat skydd med Microsoft Defender Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="8fc4a-103">Integrate Office 365 Advanced Threat Protection with Microsoft Defender Advanced Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="8fc4a-104">[Office 365 Avancerat skydd](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) (Office 365 ATP) kan konfigureras så att det fungerar med [Microsoft Defender Avancerat skydd](https://docs.microsoft.com/windows/security/threat-protection) (Microsoft Defender ATP).</span><span class="sxs-lookup"><span data-stu-id="8fc4a-104">[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) (Office 365 ATP) can be configured to work with [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection) (Microsoft Defender ATP).</span></span>

<span data-ttu-id="8fc4a-105">Integrering av Office 365 ATP med Microsoft Defender ATP kan hjälpa din säkerhets åtgärds grupp övervakning och vidta åtgärder snabbt om användarnas enheter löper risk.</span><span class="sxs-lookup"><span data-stu-id="8fc4a-105">Integrating Office 365 ATP with Microsoft Defender ATP can help your security operations team monitor and take action quickly if users' devices are at risk.</span></span> <span data-ttu-id="8fc4a-106">När integrationen är aktive rad kan till exempel din säkerhets åtgärds grupp se vilka enheter som eventuellt påverkas av ett identifierat e-postmeddelande, samt hur många aviseringar om dessa enheter har i Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="8fc4a-106">For example, once integration is enabled, your security operations team will be able to see the devices that are potentially affected by a detected email message, as well as how many recent alerts those devices have in Microsoft Defender ATP.</span></span> 

<span data-ttu-id="8fc4a-107">Följande bild visar vad fliken **enheter** ser ut som har Microsoft Defender ATP-integrering aktive rad:</span><span class="sxs-lookup"><span data-stu-id="8fc4a-107">The following image depicts what the **Devices** tab looks like have Microsoft Defender ATP integration enabled:</span></span>
  
![När Microsoft Defender ATP är aktiverat kan du se en lista med enheter med aviseringar.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
<span data-ttu-id="8fc4a-109">I det här exemplet kan du se att mottagarna av det identifierade e-postmeddelandet har fyra enheter och en har en avisering.</span><span class="sxs-lookup"><span data-stu-id="8fc4a-109">In this example, you can see that the recipients of the detected email message have four devices and one has an alert.</span></span> <span data-ttu-id="8fc4a-110">Om du klickar på länken för en enhet öppnas den i Microsoft Defender säkerhets Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).</span><span class="sxs-lookup"><span data-stu-id="8fc4a-110">Clicking the link for a device opens its page in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

> [!TIP]
> <span data-ttu-id="8fc4a-111">**[Läs mer om Microsoft Defender säkerhets Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (kallas även Microsoft Defender ATP-portalen.)</span><span class="sxs-lookup"><span data-stu-id="8fc4a-111">**[Learn more about the Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (also referred to as the Microsoft Defender ATP portal.)</span></span>
  
## <a name="requirements"></a><span data-ttu-id="8fc4a-112">Krav</span><span class="sxs-lookup"><span data-stu-id="8fc4a-112">Requirements</span></span>

- <span data-ttu-id="8fc4a-113">Din organisation måste ha Office 365 ATP-abonnemang 2 (eller Office 365 E5) och Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="8fc4a-113">Your organization must have Office 365 ATP Plan 2 (or Office 365 E5) and Microsoft Defender ATP.</span></span>
    
- <span data-ttu-id="8fc4a-114">Du måste vara global administratör eller ha en säkerhets administratörs roll (till exempel säkerhets administratör) som är tilldelad i [ &amp; Säkerhetscenter](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="8fc4a-114">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in the [Security &amp; Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="8fc4a-115">(Se [behörigheter i säkerhets &amp; kontroll Center](permissions-in-the-security-and-compliance-center.md))</span><span class="sxs-lookup"><span data-stu-id="8fc4a-115">(See [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>
    
- <span data-ttu-id="8fc4a-116">Du måste ha till gång till både [Explorer (eller real tids identifieringar)](threat-explorer.md) i säkerhets & efterlevnaden för säkerhet och Microsoft Defender säkerhets Center.</span><span class="sxs-lookup"><span data-stu-id="8fc4a-116">You must have access to both [Explorer (or real-time detections)](threat-explorer.md) in the Security & Compliance Center and the Microsoft Defender Security Center.</span></span>
    
## <a name="to-integrate-office-365-atp-with-microsoft-defender-atp"></a><span data-ttu-id="8fc4a-117">Integrera Office 365 ATP med Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="8fc4a-117">To integrate Office 365 ATP with Microsoft Defender ATP</span></span>

<span data-ttu-id="8fc4a-118">Integrering av Office 365 ATP med Microsoft Defender ATP konfigureras med hjälp av både säkerhets & och Microsoft Defender säkerhets Center.</span><span class="sxs-lookup"><span data-stu-id="8fc4a-118">Integrating Office 365 ATP with Microsoft Defender ATP is set up by using both the Security & Compliance Center AND the Microsoft Defender Security Center.</span></span>
  
1. <span data-ttu-id="8fc4a-119">Som global administratör eller säkerhets administratör går du till [https://protection.office.com](https://protection.office.com) och loggar in.</span><span class="sxs-lookup"><span data-stu-id="8fc4a-119">As a global administrator or a security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="8fc4a-120">(Du kommer till Office 365 Security & Compliance Center.)</span><span class="sxs-lookup"><span data-stu-id="8fc4a-120">(This takes you to the Office 365 Security & Compliance Center.)</span></span>
    
2. <span data-ttu-id="8fc4a-121">Välj **Threat Management**  >  **Explorer**i navigerings fönstret.</span><span class="sxs-lookup"><span data-stu-id="8fc4a-121">In the navigation pane, choose **Threat management** > **Explorer**.</span></span><br><span data-ttu-id="8fc4a-122">![Utforskaren i Threat Management-menyn](../../media/ThreatMgmt-Explorer-nav.png)</span><span class="sxs-lookup"><span data-stu-id="8fc4a-122">![Explorer in Threat Management menu](../../media/ThreatMgmt-Explorer-nav.png)</span></span><br>
    
3. <span data-ttu-id="8fc4a-123">I det övre högra hörnet av skärmen väljer du **WDATP inställningar**.</span><span class="sxs-lookup"><span data-stu-id="8fc4a-123">In the upper right corner of the screen, choose **WDATP Settings**.</span></span>
    
4. <span data-ttu-id="8fc4a-124">I dialog rutan Microsoft Defender ATP-anslutning aktiverar **du Anslut till Windows ATP**.</span><span class="sxs-lookup"><span data-stu-id="8fc4a-124">In the Microsoft Defender ATP connection dialog box, turn on **Connect to Windows ATP**.</span></span><br><span data-ttu-id="8fc4a-125">![Microsoft Defender ATP-anslutning](../../media/Explorer-WDATPConnection-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="8fc4a-125">![Microsoft Defender ATP connection](../../media/Explorer-WDATPConnection-dialog.png)</span></span><br>
    
5. <span data-ttu-id="8fc4a-126">Gå till Microsoft Defender säkerhets Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).</span><span class="sxs-lookup"><span data-stu-id="8fc4a-126">Go to the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

6. <span data-ttu-id="8fc4a-127">I navigerings fältet väljer du **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="8fc4a-127">In the navigation bar, choose **Settings**.</span></span> <span data-ttu-id="8fc4a-128">Under **Allmänt**väljer du **avancerade funktioner**.</span><span class="sxs-lookup"><span data-stu-id="8fc4a-128">Then, under **General**, choose **Advanced features**.</span></span>

7. <span data-ttu-id="8fc4a-129">Rulla ned till **Office 365 Threat Intelligence-anslutning**och slå på anslutningen.</span><span class="sxs-lookup"><span data-stu-id="8fc4a-129">Scroll down to **Office 365 Threat Intelligence connection**, and turn the connection on.</span></span><br/><span data-ttu-id="8fc4a-130">![Anslutning till Office 365 Threat Intelligence](../../media/mdatp-oatptoggle.png)</span><span class="sxs-lookup"><span data-stu-id="8fc4a-130">![Office 365 threat intelligence connection](../../media/mdatp-oatptoggle.png)</span></span><br>

## <a name="related-articles"></a><span data-ttu-id="8fc4a-131">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="8fc4a-131">Related articles</span></span>

[<span data-ttu-id="8fc4a-132">Hot-och svars funktioner i Office 365</span><span class="sxs-lookup"><span data-stu-id="8fc4a-132">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)
  
[<span data-ttu-id="8fc4a-133">Office 365 Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="8fc4a-133">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="8fc4a-134">Microsoft Defender Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="8fc4a-134">Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection)
