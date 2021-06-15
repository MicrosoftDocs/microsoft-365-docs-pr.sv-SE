---
title: Distribuera och aktivera Microsoft Defender Antivirus
description: Distribuera Microsoft Defender Antivirus för att skydda slutpunkterna med Microsoft Intune, Microsoft Endpoint Configuration Manager, Grupprincip, PowerShell-cmdlets eller WMI.
keywords: distribuera, aktivera Microsoft Defender Antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 01/06/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: a847e65adb0402d4c5f98e19424677ccdc1011da
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925749"
---
# <a name="deploy-and-enable-microsoft-defender-antivirus"></a><span data-ttu-id="b249e-104">Distribuera och aktivera Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="b249e-104">Deploy and enable Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="b249e-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="b249e-105">**Applies to:**</span></span>

- [<span data-ttu-id="b249e-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="b249e-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="b249e-107">Beroende på vilket hanteringsverktyg du använder kan du behöva särskilt aktivera eller konfigurera Microsoft Defender Antivirus skydd.</span><span class="sxs-lookup"><span data-stu-id="b249e-107">Depending on the management tool you are using, you may need to specifically enable or configure Microsoft Defender Antivirus protection.</span></span> 

<span data-ttu-id="b249e-108">I tabellen i [Distribuera,](deploy-manage-report-microsoft-defender-antivirus.md#ref2) hantera och rapportera om Microsoft Defender Antivirus finns instruktioner om hur du aktiverar skydd med Microsoft Intune, Microsoft Endpoint Configuration Manager, Grupprincip, Active Directory, Microsoft Azure, PowerShell-cmdlets och WMI (Windows Management Instruction).</span><span class="sxs-lookup"><span data-stu-id="b249e-108">See the table in [Deploy, manage, and report on Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md#ref2) for instructions on how to enable protection with Microsoft Intune, Microsoft Endpoint Configuration Manager, Group Policy, Active Directory, Microsoft Azure, PowerShell cmdlets, and Windows Management Instruction (WMI).</span></span>

<span data-ttu-id="b249e-109">Vissa scenarier kräver mer vägledning om hur du distribuerar eller konfigurerar Microsoft Defender Antivirus skydd, till exempel VDI-miljöer (Virtual Desktop Infrastructure).</span><span class="sxs-lookup"><span data-stu-id="b249e-109">Some scenarios require more guidance on how to successfully deploy or configure Microsoft Defender Antivirus protection, such as Virtual Desktop Infrastructure (VDI) environments.</span></span>

<span data-ttu-id="b249e-110">Resten av artikeln i det här avsnittet innehåller råd från alla till slutet och metodtips för att konfigurera Microsoft Defender Antivirus på virtuella maskiner i en [VDI- eller fjärrskrivbordstjänster (RDS).](deployment-vdi-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="b249e-110">The remaining article in this section provides end-to-end advice and best practices for [setting up Microsoft Defender Antivirus on virtual machines (VMs) in a VDI or Remote Desktop Services (RDS) environment](deployment-vdi-microsoft-defender-antivirus.md).</span></span>

## <a name="related-articles"></a><span data-ttu-id="b249e-111">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="b249e-111">Related articles</span></span>

- [<span data-ttu-id="b249e-112">Microsoft Defender Antivirus i Windows 10</span><span class="sxs-lookup"><span data-stu-id="b249e-112">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="b249e-113">Distribuera, hantera uppdateringar och rapportera Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="b249e-113">Deploy, manage updates, and report on Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)
- [<span data-ttu-id="b249e-114">Distributionsguide för Microsoft Defender Antivirus i en VDI-miljö (Virtual Desktop Infrastructure)</span><span class="sxs-lookup"><span data-stu-id="b249e-114">Deployment guide for Microsoft Defender Antivirus in a virtual desktop infrastructure (VDI) environment</span></span>](deployment-vdi-microsoft-defender-antivirus.md)