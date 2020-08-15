---
title: Resurs begränsningar i Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: I den här artikeln hittar du information om resurs begränsningar för de olika programmen i Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6053740d41b02461432243c8527391a4f8ae22ea
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694743"
---
# <a name="resource-limits"></a><span data-ttu-id="b597c-103">Resurs begränsningar</span><span class="sxs-lookup"><span data-stu-id="b597c-103">Resource Limits</span></span>

<span data-ttu-id="b597c-104">Resurs gränser tillämpas med kvoter (gränser) och begränsning.</span><span class="sxs-lookup"><span data-stu-id="b597c-104">Resource limits are enforced using quotas (limits) and throttling.</span></span> <span data-ttu-id="b597c-105">Azure Active Directory (Azure AD) och de enskilda Microsoft 365-tjänsterna använder båda.</span><span class="sxs-lookup"><span data-stu-id="b597c-105">Azure Active Directory (Azure AD) and the individual Microsoft 365 services use both.</span></span> <span data-ttu-id="b597c-106">Gränser är tjänstespecifika och förändras när nya funktioner läggs till.</span><span class="sxs-lookup"><span data-stu-id="b597c-106">Limits are service-specific and change over time as new capabilities are added.</span></span> <span data-ttu-id="b597c-107">Information om de aktuella gränserna för de olika tjänsterna finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="b597c-107">For details on the current limits for the various services, see the following topics:</span></span>

- [<span data-ttu-id="b597c-108">Azure AD-tjänst begränsningar och restriktioner</span><span class="sxs-lookup"><span data-stu-id="b597c-108">Azure AD service limits and restrictions</span></span>](https://docs.microsoft.com/azure/azure-resource-manager/management/azure-subscription-service-limits)
- [<span data-ttu-id="b597c-109">Begränsningar för Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b597c-109">Exchange Online Limits</span></span>](https://technet.microsoft.com/library/exchange-online-limits.aspx)
- [<span data-ttu-id="b597c-110">Begränsningar för Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="b597c-110">Exchange Online Protection Limits</span></span>](https://technet.microsoft.com/library/exchange-online-protection-limits.aspx)
- [<span data-ttu-id="b597c-111">Program begränsningar och begränsningar för SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b597c-111">SharePoint Online software boundaries and limits</span></span>](https://support.office.com/article/SharePoint-Online-software-boundaries-and-limits-8F34FF47-B749-408B-ABC0-B605E1F6D498)
- [<span data-ttu-id="b597c-112">Skype för Business-begränsningar</span><span class="sxs-lookup"><span data-stu-id="b597c-112">Skype for Business Limits</span></span>](https://technet.microsoft.com/library/skype-for-business-online-limits.aspx)
- [<span data-ttu-id="b597c-113">Stöd för Yammer REST API och hastighet</span><span class="sxs-lookup"><span data-stu-id="b597c-113">Yammer REST API and Rate Limits</span></span>](https://developer.yammer.com/docs/rest-api-rate-limits)
- [<span data-ttu-id="b597c-114">Fil storleks begränsningar i Sway</span><span class="sxs-lookup"><span data-stu-id="b597c-114">File Size Limits in Sway</span></span>](https://support.office.com/article/File-size-limits-in-Sway-4db21bc6-b42b-499f-9272-66e089db109f)

<span data-ttu-id="b597c-115">Utöver dessa gränser används flera olika begränsnings mekanismer i hela Azure AD och Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b597c-115">In addition to these limits, several throttling mechanisms are used throughout Azure AD and Microsoft 365.</span></span> <span data-ttu-id="b597c-116">Begränsning av tjänsten är särskilt viktigt, eftersom nätverks resurserna i Microsofts Data Center är optimerade för de breda kunder som använder tjänsterna.</span><span class="sxs-lookup"><span data-stu-id="b597c-116">Throttling within the service is especially important, given that network resources in Microsoft's datacenters are optimized for the broad set of customers that use the services.</span></span> <span data-ttu-id="b597c-117">Begränsnings mekanismer är bland annat:</span><span class="sxs-lookup"><span data-stu-id="b597c-117">Throttling mechanisms include:</span></span>

- <span data-ttu-id="b597c-118">Azure AD-och Microsoft 365-funktioner användarens nivå begränsning, som begränsar antalet transaktioner eller samtidiga samtal (med skript eller kod) som kan utföras av en enskild användare.</span><span class="sxs-lookup"><span data-stu-id="b597c-118">Azure AD and Microsoft 365 feature user-level throttling, which limit the number of transactions or concurrent calls (by script or code) that can be performed by a single user.</span></span>
- <span data-ttu-id="b597c-119">En standard princip för PowerShell-begränsning tilldelas varje klient organisation när han eller hon skapas.</span><span class="sxs-lookup"><span data-stu-id="b597c-119">A default PowerShell throttling policy is assigned to each tenant at tenant creation.</span></span> <span data-ttu-id="b597c-120">Dessa inställningar påverkar andra objekt, till exempel det högsta antalet samtidiga PowerShell-sessioner som kan öppnas av en enda administratör.</span><span class="sxs-lookup"><span data-stu-id="b597c-120">These settings affect other items, such as the maximum number of simultaneous PowerShell sessions that can be opened by a single administrator.</span></span>
- <span data-ttu-id="b597c-121">Varje Exchange Online-kund har en standard princip för Exchange Web Services (EWS) som är justerad för EWS-klient operationer och begränsning som gäller för alla Outlook-klienter.</span><span class="sxs-lookup"><span data-stu-id="b597c-121">Each Exchange Online customer has a default Exchange Web Services (EWS) policy that is tuned for EWS client operations, and throttling that applies to all Outlook clients.</span></span>
