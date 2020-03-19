---
title: Integrera Office 365 Avancerat hotskydd med Microsoft Defender Avancerat hotskydd
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 01/22/2019
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
description: Integrera Office 365 Advanced Threat Protection med Microsoft Defender Advanced Threat Protection för att se mer detaljerad information om hothantering.
ms.openlocfilehash: 8096a950e66ed94d6e056f40b737d89d48cb811e
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42805444"
---
# <a name="integrate-office-365-advanced-threat-protection-with-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="3a09f-103">Integrera Office 365 Avancerat hotskydd med Microsoft Defender Avancerat hotskydd</span><span class="sxs-lookup"><span data-stu-id="3a09f-103">Integrate Office 365 Advanced Threat Protection with Microsoft Defender Advanced Threat Protection</span></span>

<span data-ttu-id="3a09f-104">Om du ingår i organisationens säkerhetsteam kan du integrera [Office 365 Advanced Threat Protection](office-365-atp.md) och relaterade utrednings- och svarsfunktioner med Microsoft Defender Advanced Threat [Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection).</span><span class="sxs-lookup"><span data-stu-id="3a09f-104">If you are part of your organization's security team, you can integrate [Office 365 Advanced Threat Protection](office-365-atp.md) and related investigation and response features with [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection).</span></span> <span data-ttu-id="3a09f-105">Detta kan hjälpa dig att snabbt förstå om användarnas datorer är i riskzonen när du undersöker hot i Office 365.</span><span class="sxs-lookup"><span data-stu-id="3a09f-105">This can help you quickly understand if users' machines are at risk when you are investigating threats in Office 365.</span></span> <span data-ttu-id="3a09f-106">När integreringen har aktiverats kan du till exempel se en lista över datorer som används av mottagarna av ett upptäckt e-postmeddelande, samt hur många senaste aviseringar dessa datorer har i Microsoft Defender Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="3a09f-106">For example, once integration is enabled, you will be able to see a list of machines that are used by the recipients of a detected email message, as well as how many recent alerts those machines have in Microsoft Defender Advanced Threat Protection.</span></span>
  
<span data-ttu-id="3a09f-107">Följande bild visar fliken **Enheter** som visas när microsoft Defender ATP-integrering är aktiverad:</span><span class="sxs-lookup"><span data-stu-id="3a09f-107">The following image shows the **Devices** tab that you'll see when have Microsoft Defender ATP integration enabled:</span></span>
  
![När Microsoft Defender ATP är aktiverat kan du se en lista över datorer med aviseringar.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
<span data-ttu-id="3a09f-109">I det här exemplet kan du se att mottagarna av e-postmeddelandet har fyra enheter och en har en avisering.</span><span class="sxs-lookup"><span data-stu-id="3a09f-109">In this example, you can see that the recipients of the email message have four devices and one has an alert.</span></span> <span data-ttu-id="3a09f-110">Om du klickar på länken för en enhet öppnas sidan i Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="3a09f-110">Clicking the link for a device opens its page in the Microsoft Defender Security Center.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="3a09f-111">Krav</span><span class="sxs-lookup"><span data-stu-id="3a09f-111">Requirements</span></span>

- <span data-ttu-id="3a09f-112">Din organisation måste ha Office 365 ATP Plan 2 (eller Office 365 E5) och Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="3a09f-112">Your organization must have Office 365 ATP Plan 2 (or Office 365 E5) and Microsoft Defender ATP.</span></span>
    
- <span data-ttu-id="3a09f-113">Du måste vara en Global Office 365-administratör eller ha en säkerhetsadministratörsroll (till exempel säkerhetsadministratör) som är tilldelad i [Security &amp; Compliance Center](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="3a09f-113">You must be an Office 365 Global Administrator or have a security administrator role (such as Security Administrator) assigned in the [Security &amp; Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="3a09f-114">(Se [Behörigheter i &amp; Säkerhetsefterlevnadscenter för Office 365](permissions-in-the-security-and-compliance-center.md))</span><span class="sxs-lookup"><span data-stu-id="3a09f-114">(See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>
    
- <span data-ttu-id="3a09f-115">Du måste ha tillgång till både [Explorer (eller realtidsidentifieringar)](threat-explorer.md) i Security & Compliance Center och Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="3a09f-115">You must have access to both [Explorer (or real-time detections)](threat-explorer.md) in the Security & Compliance Center and the Microsoft Defender Security Center.</span></span>
    
## <a name="to-integrate-office-365-atp-with-microsoft-defender-atp"></a><span data-ttu-id="3a09f-116">Så här integrerar du Office 365 ATP med Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="3a09f-116">To integrate Office 365 ATP with Microsoft Defender ATP</span></span>

<span data-ttu-id="3a09f-117">Integrering av Office 365 ATP med Microsoft Defender ATP konfigureras med både Security & Compliance Center och Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="3a09f-117">Integrating Office 365 ATP with Microsoft Defender ATP is set up by using both the Security & Compliance Center AND the Microsoft Defender Security Center.</span></span>
  
1. <span data-ttu-id="3a09f-118">Som en global Office 365-administratör eller [https://protection.office.com](https://protection.office.com) en säkerhetsadministratör går du till och loggar in med ditt arbets- eller skolkonto för Office 365.</span><span class="sxs-lookup"><span data-stu-id="3a09f-118">As an Office 365 global administrator or a security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account for Office 365.</span></span>
    
2. <span data-ttu-id="3a09f-119">Välj **Explorer** **för hothantering** \> .</span><span class="sxs-lookup"><span data-stu-id="3a09f-119">Choose **Threat management** \> **Explorer**.</span></span><br><span data-ttu-id="3a09f-120">![Explorer i menyn Hothantering](../../media/ThreatMgmt-Explorer-nav.png)</span><span class="sxs-lookup"><span data-stu-id="3a09f-120">![Explorer in Threat Management menu](../../media/ThreatMgmt-Explorer-nav.png)</span></span><br>
    
3. <span data-ttu-id="3a09f-121">Välj **WDATP-inställningar**i det övre högra hörnet av skärmen .</span><span class="sxs-lookup"><span data-stu-id="3a09f-121">In the upper right corner of the screen, choose **WDATP Settings**.</span></span>
    
4. <span data-ttu-id="3a09f-122">Aktivera Anslut till Windows ATP i dialogrutan Windows Defender ATP-anslutning.</span><span class="sxs-lookup"><span data-stu-id="3a09f-122">In the Windows Defender ATP connection dialog box, turn on Connect to Windows ATP.</span></span><br>![Microsoft Defender ATP-anslutning](../../media/Explorer-WDATPConnection-dialog.png)<br>
    
5. <span data-ttu-id="3a09f-124">Aktivera anslutningen i Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="3a09f-124">Enable the connection in the Microsoft Defender Security Center.</span></span>

  
## <a name="related-topics"></a><span data-ttu-id="3a09f-125">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="3a09f-125">Related topics</span></span>

[<span data-ttu-id="3a09f-126">Office 365 Hotutredning och svar</span><span class="sxs-lookup"><span data-stu-id="3a09f-126">Office 365 Threat Investigation and Response</span></span>](office-365-ti.md)
  
[<span data-ttu-id="3a09f-127">Office 365 Avancerat hotskydd</span><span class="sxs-lookup"><span data-stu-id="3a09f-127">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  

