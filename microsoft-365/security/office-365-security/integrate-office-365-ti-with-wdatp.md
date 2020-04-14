---
title: Integrera avancerat hotskydd för Office 365 med avancerat hotskydd för Microsoft Defender
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 04/13/2020
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
ms.openlocfilehash: a2634a70bdbdd21efe2c59721e5532500eb4e4cc
ms.sourcegitcommit: 4c6af6530b4997055b8e60bf532e75cbc72fb6c5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/14/2020
ms.locfileid: "43284233"
---
# <a name="integrate-office-365-advanced-threat-protection-with-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="218b6-103">Integrera avancerat hotskydd för Office 365 med avancerat hotskydd för Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="218b6-103">Integrate Office 365 Advanced Threat Protection with Microsoft Defender Advanced Threat Protection</span></span>

<span data-ttu-id="218b6-104">Om du ingår i organisationens säkerhetsteam kan du integrera [Office 365 Advanced Threat Protection](office-365-atp.md) och relaterade undersöknings- och svarsfunktioner med Microsoft Defender Advanced Threat [Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection).</span><span class="sxs-lookup"><span data-stu-id="218b6-104">If you are part of your organization's security team, you can integrate [Office 365 Advanced Threat Protection](office-365-atp.md) and related investigation and response features with [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection).</span></span> <span data-ttu-id="218b6-105">Detta kan hjälpa dig att snabbt förstå om användarnas datorer är i riskzonen när du undersöker hot i Office 365.</span><span class="sxs-lookup"><span data-stu-id="218b6-105">This can help you quickly understand if users' machines are at risk when you are investigating threats in Office 365.</span></span> <span data-ttu-id="218b6-106">När integreringen har aktiverats kan du till exempel se en lista över datorer som används av mottagarna av ett upptäckt e-postmeddelande, samt hur många aviseringar dessa datorer har i Microsoft Defender Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="218b6-106">For example, once integration is enabled, you will be able to see a list of machines that are used by the recipients of a detected email message, as well as how many recent alerts those machines have in Microsoft Defender Advanced Threat Protection.</span></span>
  
<span data-ttu-id="218b6-107">Följande bild visar fliken **Enheter** som visas när Microsoft Defender ATP-integrering är aktiverat:</span><span class="sxs-lookup"><span data-stu-id="218b6-107">The following image shows the **Devices** tab that you'll see when have Microsoft Defender ATP integration enabled:</span></span>
  
![När Microsoft Defender ATP är aktiverat kan du se en lista över enheter med aviseringar.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
<span data-ttu-id="218b6-109">I det här exemplet kan du se att mottagarna av e-postmeddelandet har fyra enheter och en har en avisering.</span><span class="sxs-lookup"><span data-stu-id="218b6-109">In this example, you can see that the recipients of the email message have four devices and one has an alert.</span></span> <span data-ttu-id="218b6-110">Om du klickar på länken för en enhet öppnas sidan i Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="218b6-110">Clicking the link for a device opens its page in the Microsoft Defender Security Center.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="218b6-111">Krav</span><span class="sxs-lookup"><span data-stu-id="218b6-111">Requirements</span></span>

- <span data-ttu-id="218b6-112">Din organisation måste ha Office 365 ATP-abonnemang 2 (eller Office 365 E5) och Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="218b6-112">Your organization must have Office 365 ATP Plan 2 (or Office 365 E5) and Microsoft Defender ATP.</span></span>
    
- <span data-ttu-id="218b6-113">Du måste vara en Global Office 365-administratör eller ha en säkerhetsadministratörsroll (till exempel säkerhetsadministratör) tilldelad i [Säkerhetsefterlevnadscenter &amp; ](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="218b6-113">You must be an Office 365 Global Administrator or have a security administrator role (such as Security Administrator) assigned in the [Security &amp; Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="218b6-114">(Se [behörigheter i &amp; Säkerhetsefterlevnadscenter för Office 365)](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="218b6-114">(See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>
    
- <span data-ttu-id="218b6-115">Du måste ha tillgång till både [Explorer (eller realtidsidentifieringar)](threat-explorer.md) i Security & Compliance Center och Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="218b6-115">You must have access to both [Explorer (or real-time detections)](threat-explorer.md) in the Security & Compliance Center and the Microsoft Defender Security Center.</span></span>
    
## <a name="to-integrate-office-365-atp-with-microsoft-defender-atp"></a><span data-ttu-id="218b6-116">Så här integrerar du Office 365 ATP med Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="218b6-116">To integrate Office 365 ATP with Microsoft Defender ATP</span></span>

<span data-ttu-id="218b6-117">Integrering av Office 365 ATP med Microsoft Defender ATP konfigureras med både Office 365 Security & Compliance Center och Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="218b6-117">Integrating Office 365 ATP with Microsoft Defender ATP is set up by using both the Office 365 Security & Compliance Center AND the Microsoft Defender Security Center.</span></span>
  
1. <span data-ttu-id="218b6-118">Som en global Office 365-administratör eller [https://protection.office.com](https://protection.office.com) säkerhetsadministratör går du till och loggar in.</span><span class="sxs-lookup"><span data-stu-id="218b6-118">As an Office 365 global administrator or a security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span>
    
2. <span data-ttu-id="218b6-119">Välj **Explorer för hothantering** \> **.**</span><span class="sxs-lookup"><span data-stu-id="218b6-119">Choose **Threat management** \> **Explorer**.</span></span><br><span data-ttu-id="218b6-120">![Explorer på menyn Hothantering](../../media/ThreatMgmt-Explorer-nav.png)</span><span class="sxs-lookup"><span data-stu-id="218b6-120">![Explorer in Threat Management menu](../../media/ThreatMgmt-Explorer-nav.png)</span></span><br>
    
3. <span data-ttu-id="218b6-121">I det övre högra hörnet av skärmen väljer du **WDATP-inställningar**.</span><span class="sxs-lookup"><span data-stu-id="218b6-121">In the upper right corner of the screen, choose **WDATP Settings**.</span></span>
    
4. <span data-ttu-id="218b6-122">Aktivera **Anslut till Windows ATP**i dialogrutan Microsoft Defender ATP-anslutning.</span><span class="sxs-lookup"><span data-stu-id="218b6-122">In the Microsoft Defender ATP connection dialog box, turn on **Connect to Windows ATP**.</span></span><br><span data-ttu-id="218b6-123">![Microsoft Defender ATP-anslutning](../../media/Explorer-WDATPConnection-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="218b6-123">![Microsoft Defender ATP connection](../../media/Explorer-WDATPConnection-dialog.png)</span></span><br>
    
5. <span data-ttu-id="218b6-124">Aktivera anslutningen i Microsoft Defender[https://securitycenter.windows.com](https://securitycenter.windows.com)Security Center ( ).</span><span class="sxs-lookup"><span data-stu-id="218b6-124">Enable the connection in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

## <a name="related-topics"></a><span data-ttu-id="218b6-125">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="218b6-125">Related topics</span></span>

[<span data-ttu-id="218b6-126">Hotutredning och hotsvarsfunktioner i Office 365</span><span class="sxs-lookup"><span data-stu-id="218b6-126">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)
  
[<span data-ttu-id="218b6-127">Office 365 Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="218b6-127">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  

