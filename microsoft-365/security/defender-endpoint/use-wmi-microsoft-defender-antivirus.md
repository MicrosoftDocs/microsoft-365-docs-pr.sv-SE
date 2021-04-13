---
title: Konfigurera Microsoft Defender Antivirus med WMI
description: Lär dig hur du konfigurerar och hanterar Microsoft Defender Antivirus med hjälp av WMI-skript för att hämta, ändra och uppdatera inställningar i Microsoft Defender för Slutpunkt.
keywords: wmi, skript, instrument för Windows-hantering, konfiguration
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 8d24a08ae3b8db710ca1727821690e5c87f056c3
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691166"
---
# <a name="use-windows-management-instrumentation-wmi-to-configure-and-manage-microsoft-defender-antivirus"></a><span data-ttu-id="8ac92-104">Använda Windows Management Instrumentation (WMI) för att konfigurera och hantera Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="8ac92-104">Use Windows Management Instrumentation (WMI) to configure and manage Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="8ac92-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="8ac92-105">**Applies to:**</span></span>

- [<span data-ttu-id="8ac92-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="8ac92-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="8ac92-107">WMI (Windows Management Instrumentation) är ett skriptgränssnitt där du kan hämta, ändra och uppdatera inställningar.</span><span class="sxs-lookup"><span data-stu-id="8ac92-107">Windows Management Instrumentation (WMI) is a scripting interface that allows you to retrieve, modify, and update settings.</span></span>

<span data-ttu-id="8ac92-108">Läs mer om WMI på [Microsoft Developer Network System Administration-biblioteket.](/windows/win32/wmisdk/wmi-start-page)</span><span class="sxs-lookup"><span data-stu-id="8ac92-108">Read more about WMI at the [Microsoft Developer Network System Administration library](/windows/win32/wmisdk/wmi-start-page).</span></span>

<span data-ttu-id="8ac92-109">Microsoft Defender Antivirus har ett antal specifika WMI-klasser som kan användas för att utföra de flesta av funktionerna som Grupprincip och andra hanteringsverktyg.</span><span class="sxs-lookup"><span data-stu-id="8ac92-109">Microsoft Defender Antivirus has a number of specific WMI classes that can be used to perform most of the same functions as Group Policy and other management tools.</span></span> <span data-ttu-id="8ac92-110">Många av klasserna kan jämföras med [Defender PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="8ac92-110">Many of the classes are analogous to [Defender PowerShell cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="8ac92-111">Referensbiblioteket [för MSDN Windows Defender WMIv2-providern](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) innehåller tillgängliga WMI-klasser för Microsoft Defender Antivirus och innehåller exempelskript.</span><span class="sxs-lookup"><span data-stu-id="8ac92-111">The [MSDN Windows Defender WMIv2 Provider reference library](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) lists the available WMI classes for Microsoft Defender Antivirus, and includes example scripts.</span></span>

<span data-ttu-id="8ac92-112">Ändringar som görs med WMI påverkar lokala inställningar i slutpunkten där ändringarna distribueras eller görs.</span><span class="sxs-lookup"><span data-stu-id="8ac92-112">Changes made with WMI will affect local settings on the endpoint where the changes are deployed or made.</span></span> <span data-ttu-id="8ac92-113">Det innebär att distributioner av principen med Grupprincip, Microsoft Endpoint Configuration Manager eller Microsoft Intune kan skriva över ändringar som gjorts med WMI.</span><span class="sxs-lookup"><span data-stu-id="8ac92-113">This means that deployments of policy with Group Policy, Microsoft Endpoint Configuration Manager, or Microsoft Intune can overwrite changes made with WMI.</span></span> 

<span data-ttu-id="8ac92-114">Du kan [konfigurera vilka inställningar som kan åsidosättas lokalt med åsidosättningar av lokala policyer.](configure-local-policy-overrides-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="8ac92-114">You can [configure which settings can be overridden locally  with local policy overrides](configure-local-policy-overrides-microsoft-defender-antivirus.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="8ac92-115">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="8ac92-115">Related topics</span></span>

- [<span data-ttu-id="8ac92-116">Referensavsnitt om hanterings- och konfigurationsverktyg</span><span class="sxs-lookup"><span data-stu-id="8ac92-116">Reference topics for management and configuration tools</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="8ac92-117">Microsoft Defender Antivirus i Windows 10</span><span class="sxs-lookup"><span data-stu-id="8ac92-117">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)