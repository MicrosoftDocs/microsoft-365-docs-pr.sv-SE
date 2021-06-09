---
title: Enhetsnamn
description: Hur Microsoft Hanterat skrivbord hanterar enhetsnamn
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: adf4809e0d8dc29f170475435b19092abf2062fd
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893982"
---
# <a name="device-names"></a><span data-ttu-id="7321b-103">Enhetsnamn</span><span class="sxs-lookup"><span data-stu-id="7321b-103">Device names</span></span>

<span data-ttu-id="7321b-104">Microsoft Hanterat skrivbord använder Windows Autopilot, Azure Active Directory och Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="7321b-104">Microsoft Managed Desktop uses Windows Autopilot, Azure Active Directory, and Microsoft Intune.</span></span> <span data-ttu-id="7321b-105">För att de här tjänsterna ska kunna samarbeta smidigt måste enheterna ha konsekventa och standardiserade namn.</span><span class="sxs-lookup"><span data-stu-id="7321b-105">For these services to work together seamlessly, devices need consistent, standardized names.</span></span> <span data-ttu-id="7321b-106">Microsoft Hanterat skrivbord ett standardiserat namnformat (av formuläret *MMD-%SLUMP11)* när enheter registreras.</span><span class="sxs-lookup"><span data-stu-id="7321b-106">Microsoft Managed Desktop applies a standardized name format (of the form *MMD-%RAND11*) when devices are enrolled.</span></span> <span data-ttu-id="7321b-107">Windows Autopilot tilldelar dessa namn.</span><span class="sxs-lookup"><span data-stu-id="7321b-107">Windows Autopilot assigns these names.</span></span> <span data-ttu-id="7321b-108">Mer information om Autopilot finns i [First-run-upplevelsen med Autopilot och registreringsstatussidan.](../get-started/esp-first-run.md)</span><span class="sxs-lookup"><span data-stu-id="7321b-108">For more information about Autopilot, see [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span></span>

## <a name="automated-name-changes"></a><span data-ttu-id="7321b-109">Automatiserade namnändringar</span><span class="sxs-lookup"><span data-stu-id="7321b-109">Automated name changes</span></span>

<span data-ttu-id="7321b-110">Om en enhet byter namn senare Microsoft Hanterat skrivbord automatiskt namnet till ett nytt namn i standardiserat format.</span><span class="sxs-lookup"><span data-stu-id="7321b-110">If a device gets renamed later, Microsoft Managed Desktop will automatically rename it to a new name in the standardized format.</span></span> <span data-ttu-id="7321b-111">Den här processen sker var fjärde timme.</span><span class="sxs-lookup"><span data-stu-id="7321b-111">This process occurs every four hours.</span></span> <span data-ttu-id="7321b-112">Namnändringen sker nästa gång användaren startar om enheten.</span><span class="sxs-lookup"><span data-stu-id="7321b-112">The name change takes place the next time the user restarts the device.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7321b-113">Om din miljö är beroende av specifika enhetsnamn (t.ex. för att stödja en viss nätverkskonfiguration) bör du undersöka olika alternativ för att ta bort beroendet innan du registrerar Microsoft Hanterat skrivbord.</span><span class="sxs-lookup"><span data-stu-id="7321b-113">If your environment depends on specific device names (for example, to support a particular network configuration), you should investigate options to remove that dependency before enrolling in Microsoft Managed Desktop.</span></span> <span data-ttu-id="7321b-114">Om du måste behålla namnsambandet kan [](../working-with-managed-desktop/admin-support.md) du skicka en begäran via administratörsportalen för att inaktivera namnändringsfunktionen och använda önskat namnformat.</span><span class="sxs-lookup"><span data-stu-id="7321b-114">If you must keep the name dependency, you can submit a request through the [Admin portal](../working-with-managed-desktop/admin-support.md) to disable the renaming function and use your desired name format.</span></span>