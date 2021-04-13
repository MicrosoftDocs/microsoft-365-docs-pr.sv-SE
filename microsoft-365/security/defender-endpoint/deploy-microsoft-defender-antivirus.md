---
title: Distribuera och aktivera Microsoft Defender Antivirus
description: Distribuera Microsoft Defender Antivirus för att skydda slutpunkterna med Microsoft Intune, Microsoft Endpoint Configuration Manager, Grupprincip, PowerShell-cmdlets eller WMI.
keywords: distribuera, aktivera, Microsoft Defender Antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 01/06/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: efc2aa0f48cb2bc55e729b65c892a07b74c1bc46
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691496"
---
# <a name="deploy-and-enable-microsoft-defender-antivirus"></a><span data-ttu-id="d488d-104">Distribuera och aktivera Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="d488d-104">Deploy and enable Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d488d-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="d488d-105">**Applies to:**</span></span>

- [<span data-ttu-id="d488d-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="d488d-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="d488d-107">Beroende på vilket hanteringsverktyg du använder kan du behöva aktivera eller konfigurera Microsoft Defender Antivirus protection.</span><span class="sxs-lookup"><span data-stu-id="d488d-107">Depending on the management tool you are using, you may need to specifically enable or configure Microsoft Defender Antivirus protection.</span></span> 

<span data-ttu-id="d488d-108">Se tabellen i [Distribuera,](deploy-manage-report-microsoft-defender-antivirus.md#ref2) hantera och rapportera om Microsoft Defender Antivirus för anvisningar om hur du aktiverar skydd med Microsoft Intune, Microsoft Endpoint Configuration Manager, Grupprincip, Active Directory, Microsoft Azure, PowerShell-cmdlets och Windows Management Instruction (WMI).</span><span class="sxs-lookup"><span data-stu-id="d488d-108">See the table in [Deploy, manage, and report on Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md#ref2) for instructions on how to enable protection with Microsoft Intune, Microsoft Endpoint Configuration Manager, Group Policy, Active Directory, Microsoft Azure, PowerShell cmdlets, and Windows Management Instruction (WMI).</span></span>

<span data-ttu-id="d488d-109">Vissa scenarier kräver mer vägledning om hur du distribuerar eller konfigurerar Microsoft Defender Antivirus-skydd, till exempel VDI-miljöer (Virtual Desktop Infrastructure).</span><span class="sxs-lookup"><span data-stu-id="d488d-109">Some scenarios require more guidance on how to successfully deploy or configure Microsoft Defender Antivirus protection, such as Virtual Desktop Infrastructure (VDI) environments.</span></span>

<span data-ttu-id="d488d-110">I den återstående artikeln i det här avsnittet får du tips och metodtips för att konfigurera Microsoft Defender Antivirus på virtuella maskiner (VMs) i en [VDI- eller REMOTE Desktop Services-miljö (RDS).](deployment-vdi-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="d488d-110">The remaining article in this section provides end-to-end advice and best practices for [setting up Microsoft Defender Antivirus on virtual machines (VMs) in a VDI or Remote Desktop Services (RDS) environment](deployment-vdi-microsoft-defender-antivirus.md).</span></span>

## <a name="related-articles"></a><span data-ttu-id="d488d-111">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="d488d-111">Related articles</span></span>

- [<span data-ttu-id="d488d-112">Microsoft Defender Antivirus i Windows 10</span><span class="sxs-lookup"><span data-stu-id="d488d-112">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="d488d-113">Distribuera, hantera uppdateringar och rapportera om Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="d488d-113">Deploy, manage updates, and report on Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)
- [<span data-ttu-id="d488d-114">Distributionsguide för Microsoft Defender Antivirus i en VDI-miljö (Virtual Desktop Infrastructure)</span><span class="sxs-lookup"><span data-stu-id="d488d-114">Deployment guide for Microsoft Defender Antivirus in a virtual desktop infrastructure (VDI) environment</span></span>](deployment-vdi-microsoft-defender-antivirus.md)