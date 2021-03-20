---
title: Arbeta med rapporter
description: ''
keywords: Microsoft Hanterat skrivbord, Microsoft 365, tjänst, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: e509ae63225362613962cd0c366c51239f3d4493
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917688"
---
# <a name="work-with-reports"></a><span data-ttu-id="bf025-103">Arbeta med rapporter</span><span class="sxs-lookup"><span data-stu-id="bf025-103">Work with reports</span></span>

<span data-ttu-id="bf025-104">Microsoft Managed Desktop innehåller flera rapporter och instrumentpaneler som IT-administratörer i organisationen kan använda för att förstå olika aspekter av populationen av enheter.</span><span class="sxs-lookup"><span data-stu-id="bf025-104">Microsoft Managed Desktop provides several reports and dashboards that IT admins in your organization can use to understand various aspects of the population of devices.</span></span><span data-ttu-id="bf025-105">Du hittar rapporter på två platser: i [Microsoft Endpoint Manager och](https://endpoint.microsoft.com) i administrationscentret för Microsoft [365.](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop)</span><span class="sxs-lookup"><span data-stu-id="bf025-105"> You'll find reports in two locations: in [Microsoft Endpoint Manager](https://endpoint.microsoft.com) and in the [Microsoft 365 Admin Center](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop).</span></span> 

## <a name="reports-in-microsoft-endpoint-manager"></a><span data-ttu-id="bf025-106">Rapporter i Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="bf025-106">Reports in Microsoft Endpoint Manager</span></span>

<span data-ttu-id="bf025-107">I Microsoft Endpoint Manager-konsolen samlas rapportering från flera produkter på en och samma plats så att du kan övervaka och undersöka problem med konfiguration och enheter med Azure AD-organisationen ("klientorganisation").</span><span class="sxs-lookup"><span data-stu-id="bf025-107">The Microsoft Endpoint Manager console brings together reporting from several products into a single location to help you monitor and investigate issues with your Azure AD organization ("tenant") configuration and devices.</span></span> <span data-ttu-id="bf025-108">Microsoft Managed Desktop har ett **avsnitt** under Rapporter i huvudmenyn där du kan hitta rapporter som är specifika för hanteringen av de enheter som du har registrerat för Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="bf025-108">Microsoft Managed desktop has a section under **Reports** in the main menu where you can find reports specific to Microsoft Managed Desktop's management of the devices you’ve registered.</span></span>

<span data-ttu-id="bf025-109">De här rapporterna omfattar:</span><span class="sxs-lookup"><span data-stu-id="bf025-109">These reports include:</span></span>
- <span data-ttu-id="bf025-110">**Hanterade enheter**  >  **Funktionsuppdateringar:** Den här vyn visar den övergripande statusen för funktionsuppdateringar för alla dina Microsoft Managed Desktop-enheter.</span><span class="sxs-lookup"><span data-stu-id="bf025-110">**Managed devices** > **Feature updates**: This view shows the overall status of feature updates across your Microsoft Managed Desktop devices.</span></span>
- <span data-ttu-id="bf025-111">**Hanterade enheter**  >  **Office-uppdateringar:** Den här vyn visar den övergripande statusen för Office-uppdateringar för alla dina Microsoft Managed Desktop-enheter.</span><span class="sxs-lookup"><span data-stu-id="bf025-111">**Managed devices** > **Office updates**: This view shows the overall status of Office updates across your Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="bf025-112">På flera platser i Microsoft Endpoint Manager kan du dessutom filtrera rapporter från andra produktgrupper för att specifikt inkludera eller exkludera dina enheter som hanteras av Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="bf025-112">Additionally, in several locations throughout Microsoft Endpoint Manager you can filter reports from other product groups to specifically include or exclude your devices that are managed by Microsoft Managed Desktop.</span></span> <span data-ttu-id="bf025-113">Dessa rapporter har integrerat den här filtreringsfunktionerna:</span><span class="sxs-lookup"><span data-stu-id="bf025-113">These reports have integrated this filtering capability:</span></span>

- [<span data-ttu-id="bf025-114">Alla enheter</span><span class="sxs-lookup"><span data-stu-id="bf025-114">All devices</span></span>](/mem/intune/remote-actions/device-management#get-to-your-devices)
- [<span data-ttu-id="bf025-115">Enhetsefterlevnad</span><span class="sxs-lookup"><span data-stu-id="bf025-115">Device compliance</span></span>](/mem/intune/fundamentals/reports#device-compliance-report-organizational)
- [<span data-ttu-id="bf025-116">Enheter som inte är kompatibla</span><span class="sxs-lookup"><span data-stu-id="bf025-116">Noncompliant devices</span></span>](/mem/intune/fundamentals/reports#noncompliant-devices-report-operational)

> [!NOTE]
> <span data-ttu-id="bf025-117">Anpassade Microsoft-hanterade skrivbordsroller garanterar endast åtkomst till rapporterna från Hanterade Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bf025-117">Custom Microsoft Managed Desktop roles guarantee access only to the Microsoft Managed Desktop reports.</span></span> <span data-ttu-id="bf025-118">Information om hur du kommer åt andra delar av Microsoft Endpoint Manager, till exempel Alla **enheter,** finns i [Rollbaserad åtkomstkontroll med Microsoft Intune.](/mem/intune/fundamentals/role-based-access-control)</span><span class="sxs-lookup"><span data-stu-id="bf025-118">To access other parts of Microsoft Endpoint Manager, such as **All devices**, see [Role-based access control with Microsoft Intune](/mem/intune/fundamentals/role-based-access-control).</span></span> 

## <a name="reports-in-microsoft-365-admin-center"></a><span data-ttu-id="bf025-119">Rapporter i Administrationscenter för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bf025-119">Reports in Microsoft 365 Admin Center</span></span>

<span data-ttu-id="bf025-120">Du kan hitta Microsoft Hanterade skrivbordsinsikter genom att öppna [Microsoft 365 Admin Center](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop)och sedan navigera till Rapporter och välja Microsoft Managed **Desktop.** </span><span class="sxs-lookup"><span data-stu-id="bf025-120">You can find Microsoft Managed Desktop insights reports by opening the [Microsoft 365 Admin Center](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop), and then navigating to **Reports** and selecting **Microsoft Managed Desktop**.</span></span> <span data-ttu-id="bf025-121">Du kan också följa direktlänken till de här rapporterna från fliken **Microsoft Hanterat skrivbord** på startsidan [Microsoft Endpoint Manager.](https://endpoint.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="bf025-121">You can also follow the direct link to these reports from the **Microsoft Managed Desktop** tab on the homepage [Microsoft Endpoint Manager](https://endpoint.microsoft.com).</span></span> 

<span data-ttu-id="bf025-122">De här rapporterna omfattar:</span><span class="sxs-lookup"><span data-stu-id="bf025-122">These reports include:</span></span> 

- <span data-ttu-id="bf025-123">[Användningsinformation](usage-insights.md) – Den här vyn innehåller användningsmått för dina Microsoft Managed Desktop-enheter.</span><span class="sxs-lookup"><span data-stu-id="bf025-123">[Usage insights](usage-insights.md) - This view provides usage metrics for your Microsoft Managed Desktop devices.</span></span>
- <span data-ttu-id="bf025-124">[Insikter om tillförlitlighet](reliability-insights.md) – den här vyn ger dig en hälsosammanfattning av dina hanterade enheter.</span><span class="sxs-lookup"><span data-stu-id="bf025-124">[Reliability insights](reliability-insights.md) - This view provides you with a health summary of your managed devices.</span></span>
- <span data-ttu-id="bf025-125">[Batteriinsikter](battery-insights.md) – I den här vyn visas information om energiförbrukningen i appar och den projekterade batteritiden för enheter i din miljö.</span><span class="sxs-lookup"><span data-stu-id="bf025-125">[Battery insights](battery-insights.md) - This view shows you information about the energy consumption of apps and projected battery life for devices in your environment.</span></span>
- <span data-ttu-id="bf025-126">[Insikter om Windows-säkerhetsuppdateringar](security-update-insights.md) – I den här vyn visas information om status för säkerhetsuppdateringar för dina Microsoft Managed Desktop-enheter.</span><span class="sxs-lookup"><span data-stu-id="bf025-126">[Windows security update insights](security-update-insights.md) - This view shows you information about the status of security updates for your Microsoft Managed Desktop devices.</span></span>

 ## <a name="inventory-data"></a><span data-ttu-id="bf025-127">Lagerdata</span><span class="sxs-lookup"><span data-stu-id="bf025-127">Inventory data</span></span>

<span data-ttu-id="bf025-128">Förutom de andra rapporterna kan du exportera information om de enheter som hanteras av Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="bf025-128">In addition to the other reports, you can export information about the devices managed by Microsoft Managed Desktop.</span></span> <span data-ttu-id="bf025-129">I vyn **Enheter** i området **Enheter i** Microsoft  Endpoint Manager använder du fliken Exportera alla för att hämta en [detaljerad lagerrapport](device-inventory-report.md).</span><span class="sxs-lookup"><span data-stu-id="bf025-129">In the **Devices** view of the **Devices** area of Microsoft Endpoint Manager, use the **Export all** tab to [download a detailed inventory report](device-inventory-report.md).</span></span>