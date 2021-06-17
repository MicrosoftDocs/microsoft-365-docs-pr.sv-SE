---
title: Ytterligare information för molnlösningsleverantörer
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 'Sammanfattning: Ytterligare information för molnlösningsleverantörer som är relevant för migreringen från Microsoft Cloud Deutschland.'
ms.openlocfilehash: 843552c55acba57c5c2da4a1a885d65cb4e59d84
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984922"
---
# <a name="additional-information-for-cloud-solution-providers"></a><span data-ttu-id="3b32b-103">Ytterligare information för molnlösningsleverantörer</span><span class="sxs-lookup"><span data-stu-id="3b32b-103">Additional information for Cloud Solution Providers</span></span>

<span data-ttu-id="3b32b-104">Molnlösningsleverantörer (CSP) som stöd för kunder måste vidta ytterligare åtgärder under migreringen från Microsoft Cloud Deutschland till den nya tyska datacenterområdet.</span><span class="sxs-lookup"><span data-stu-id="3b32b-104">Cloud Solution Providers (CSPs) supporting customers  need to take additional steps during the migration from Microsoft Cloud Deutschland to the new German datacenter region.</span></span>

## <a name="partner-tenant-migration"></a><span data-ttu-id="3b32b-105">Migrering av partnerklientorganisation</span><span class="sxs-lookup"><span data-stu-id="3b32b-105">Partner tenant migration</span></span>

<span data-ttu-id="3b32b-106">Partner Microsoft Cloud Deutschland-klientorganisationen kommer inte att migreras.</span><span class="sxs-lookup"><span data-stu-id="3b32b-106">Partner Microsoft Cloud Deutschland tenants won't be migrated.</span></span> <span data-ttu-id="3b32b-107">I stället skapas en Office 365 för alla Microsoft-partner i den nya tyska datacenterorganisationen.</span><span class="sxs-lookup"><span data-stu-id="3b32b-107">Instead, a new Office 365 services tenant will be created for each Microsoft Partner in the new German datacenter region.</span></span>

<span data-ttu-id="3b32b-108">Klientorganisationen för CSP-tjänster migreras till den nya tyska datacenterområdet och länkas till den nya klientorganisationen för Office 365-tjänster hos samma partner.</span><span class="sxs-lookup"><span data-stu-id="3b32b-108">CSP customer tenants will be migrated to the new German datacenter region and be linked to the new Office 365 services tenant of the same partner.</span></span> <span data-ttu-id="3b32b-109">Efter kundövergången kan partnern hantera kunden med hjälp av den nya klientorganisationen Office 365 tjänster i den tyska datacenterområdet.</span><span class="sxs-lookup"><span data-stu-id="3b32b-109">After customer transition, the partner can manage the customer using the new Office 365 services tenant in the German datacenter region.</span></span>

## <a name="missing-subscriptions-in-azure"></a><span data-ttu-id="3b32b-110">Prenumerationer saknas i Azure</span><span class="sxs-lookup"><span data-stu-id="3b32b-110">Missing subscriptions in Azure</span></span>

<span data-ttu-id="3b32b-111">När [prenumerations- och licensövergången (fas 3)](ms-cloud-germany-transition-phases.md#phase-3-subscription-transfer) har slutförts har molnlösningsleverantörerna inte tillgång till Azure-prenumerationen längre.</span><span class="sxs-lookup"><span data-stu-id="3b32b-111">After [the subscription and license transition (phase 3)](ms-cloud-germany-transition-phases.md#phase-3-subscription-transfer) has been completed, Cloud Solution Providers will not have access to the Azure subscription anymore.</span></span>

<span data-ttu-id="3b32b-112">Om du vill återställa åtkomst följer du dessa steg för [att förbättra åtkomsten för att hantera alla Azure-prenumerationer och hanteringsgrupper.](/azure/role-based-access-control/elevate-access-global-admin)</span><span class="sxs-lookup"><span data-stu-id="3b32b-112">To recover access, follow these steps to [elevate access to manage all Azure subscriptions and management groups](/azure/role-based-access-control/elevate-access-global-admin).</span></span>
