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
# <a name="additional-information-for-cloud-solution-providers"></a>Ytterligare information för molnlösningsleverantörer

Molnlösningsleverantörer (CSP) som stöd för kunder måste vidta ytterligare åtgärder under migreringen från Microsoft Cloud Deutschland till den nya tyska datacenterområdet.

## <a name="partner-tenant-migration"></a>Migrering av partnerklientorganisation

Partner Microsoft Cloud Deutschland-klientorganisationen kommer inte att migreras. I stället skapas en Office 365 för alla Microsoft-partner i den nya tyska datacenterorganisationen.

Klientorganisationen för CSP-tjänster migreras till den nya tyska datacenterområdet och länkas till den nya klientorganisationen för Office 365-tjänster hos samma partner. Efter kundövergången kan partnern hantera kunden med hjälp av den nya klientorganisationen Office 365 tjänster i den tyska datacenterområdet.

## <a name="missing-subscriptions-in-azure"></a>Prenumerationer saknas i Azure

När [prenumerations- och licensövergången (fas 3)](ms-cloud-germany-transition-phases.md#phase-3-subscription-transfer) har slutförts har molnlösningsleverantörerna inte tillgång till Azure-prenumerationen längre.

Om du vill återställa åtkomst följer du dessa steg för [att förbättra åtkomsten för att hantera alla Azure-prenumerationer och hanteringsgrupper.](/azure/role-based-access-control/elevate-access-global-admin)
