---
title: Arbeta med rapporter
description: De olika rapporterna som är tillgängliga i Microsoft Hanterat skrivbord
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 28035a9f0a669c1daa7526d0b1fefac52a77c81a
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2021
ms.locfileid: "52729974"
---
# <a name="work-with-reports"></a><span data-ttu-id="64a5e-104">Arbeta med rapporter</span><span class="sxs-lookup"><span data-stu-id="64a5e-104">Work with reports</span></span>

<span data-ttu-id="64a5e-105">Microsoft Hanterat skrivbord flera rapporter och instrumentpaneler som IT-administratörer i organisationen kan använda för att förstå olika aspekter av populationen av enheter.</span><span class="sxs-lookup"><span data-stu-id="64a5e-105">Microsoft Managed Desktop provides several reports and dashboards that IT admins in your organization can use to understand various aspects of the population of devices.</span></span><span data-ttu-id="64a5e-106">Du hittar rapporter på två platser: i Microsoft Endpoint Manager [och](https://endpoint.microsoft.com) i [Microsoft 365 Administrationscenter](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop).</span><span class="sxs-lookup"><span data-stu-id="64a5e-106"> You'll find reports in two locations: in [Microsoft Endpoint Manager](https://endpoint.microsoft.com) and in the [Microsoft 365 Admin Center](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop).</span></span> 

## <a name="reports-in-microsoft-endpoint-manager"></a><span data-ttu-id="64a5e-107">Rapporter i Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="64a5e-107">Reports in Microsoft Endpoint Manager</span></span>

<span data-ttu-id="64a5e-108">I Microsoft Endpoint Manager-konsolen samlas rapportering från flera produkter på en enda plats så att du kan övervaka och undersöka problem med din konfiguration och enheter med Azure AD-organisationen ("klientorganisation").</span><span class="sxs-lookup"><span data-stu-id="64a5e-108">The Microsoft Endpoint Manager console brings together reporting from several products into a single location to help you monitor and investigate issues with your Azure AD organization ("tenant") configuration and devices.</span></span> <span data-ttu-id="64a5e-109">Microsoft Managed Desktop har ett **avsnitt** under Rapporter i huvudmenyn där du kan hitta rapporter som är Microsoft Hanterat skrivbord för hantering av enheter som du har registrerat.</span><span class="sxs-lookup"><span data-stu-id="64a5e-109">Microsoft Managed desktop has a section under **Reports** in the main menu where you can find reports specific to Microsoft Managed Desktop's management of the devices you’ve registered.</span></span>

<span data-ttu-id="64a5e-110">De här rapporterna omfattar:</span><span class="sxs-lookup"><span data-stu-id="64a5e-110">These reports include:</span></span>
- <span data-ttu-id="64a5e-111">**Hanterade enheter**  >  **Funktionsuppdateringar:** Den här vyn visar den övergripande statusen för funktionsuppdateringar på alla Microsoft Hanterat skrivbord enheter.</span><span class="sxs-lookup"><span data-stu-id="64a5e-111">**Managed devices** > **Feature updates**: This view shows the overall status of feature updates across your Microsoft Managed Desktop devices.</span></span>
- <span data-ttu-id="64a5e-112">**Hanterade enheter**  >  **Office uppdateringar:** I den här vyn visas den övergripande statusen Office uppdateringar på alla Microsoft Hanterat skrivbord enheter.</span><span class="sxs-lookup"><span data-stu-id="64a5e-112">**Managed devices** > **Office updates**: This view shows the overall status of Office updates across your Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="64a5e-113">På flera platser i hela Microsoft Endpoint Manager kan du dessutom filtrera rapporter från andra produktgrupper för att specifikt inkludera eller exkludera dina enheter som hanteras av Microsoft Hanterat skrivbord.</span><span class="sxs-lookup"><span data-stu-id="64a5e-113">Additionally, in several locations throughout Microsoft Endpoint Manager you can filter reports from other product groups to specifically include or exclude your devices that are managed by Microsoft Managed Desktop.</span></span> <span data-ttu-id="64a5e-114">Dessa rapporter har integrerat den här filtreringsfunktionerna:</span><span class="sxs-lookup"><span data-stu-id="64a5e-114">These reports have integrated this filtering capability:</span></span>

- [<span data-ttu-id="64a5e-115">Alla enheter</span><span class="sxs-lookup"><span data-stu-id="64a5e-115">All devices</span></span>](/mem/intune/remote-actions/device-management#get-to-your-devices)
- [<span data-ttu-id="64a5e-116">Enhetsefterlevnad</span><span class="sxs-lookup"><span data-stu-id="64a5e-116">Device compliance</span></span>](/mem/intune/fundamentals/reports#device-compliance-report-organizational)
- [<span data-ttu-id="64a5e-117">Enheter som inte är kompatibla</span><span class="sxs-lookup"><span data-stu-id="64a5e-117">Noncompliant devices</span></span>](/mem/intune/fundamentals/reports#noncompliant-devices-report-operational)

> [!NOTE]
> <span data-ttu-id="64a5e-118">Anpassade Microsoft Hanterat skrivbord-roller garanterar att du bara har Microsoft Hanterat skrivbord åtkomst till rapporterna.</span><span class="sxs-lookup"><span data-stu-id="64a5e-118">Custom Microsoft Managed Desktop roles guarantee access only to the Microsoft Managed Desktop reports.</span></span> <span data-ttu-id="64a5e-119">Information om hur du kommer Microsoft Endpoint Manager, **till** exempel Alla enheter, finns i [Rollbaserad åtkomstkontroll med Microsoft Intune.](/mem/intune/fundamentals/role-based-access-control)</span><span class="sxs-lookup"><span data-stu-id="64a5e-119">To access other parts of Microsoft Endpoint Manager, such as **All devices**, see [Role-based access control with Microsoft Intune](/mem/intune/fundamentals/role-based-access-control).</span></span> 


 ## <a name="inventory-data"></a><span data-ttu-id="64a5e-120">Lagerdata</span><span class="sxs-lookup"><span data-stu-id="64a5e-120">Inventory data</span></span>

<span data-ttu-id="64a5e-121">Förutom de andra rapporterna kan du exportera information om de enheter som hanteras av Microsoft Hanterat skrivbord.</span><span class="sxs-lookup"><span data-stu-id="64a5e-121">In addition to the other reports, you can export information about the devices managed by Microsoft Managed Desktop.</span></span> <span data-ttu-id="64a5e-122">I vyn **Enheter** i området **Enheter i** Microsoft Endpoint Manager använder du fliken **Exportera alla** för att hämta en [detaljerad lagerrapport](device-inventory-report.md).</span><span class="sxs-lookup"><span data-stu-id="64a5e-122">In the **Devices** view of the **Devices** area of Microsoft Endpoint Manager, use the **Export all** tab to [download a detailed inventory report](device-inventory-report.md).</span></span>