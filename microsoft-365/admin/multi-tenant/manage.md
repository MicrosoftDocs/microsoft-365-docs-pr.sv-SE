---
title: Hantera flera klient organisationer
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Lär dig hur du använder klient organisationen växlaren och om vyerna för flera innehavare.
ms.openlocfilehash: 0b73665159fbc6ce2d1aa99ba1518dc257d88ec8
ms.sourcegitcommit: 7d4aa58ae9fc893825b6e648fa3f072c3ac59628
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790144"
---
# <a name="multi-tenant-management"></a>Hantering av flera innehavare

Hantering av flera innehavare erbjuder en enhetlig form av hantering som gör det möjligt för administratörer att administrera alla klient organisationer som de sköter från en och samma plats. Om du hanterar flera klient organisationer kan du:

- Flytta snabbt mellan innehavare som du hanterar.
- Utvärdera tjänstens status, produkter och fakturering på flera klient organisationer.
- På sidan **alla innehavare** kan du snabbt se tillståndet hos alla dina klient organisationer, alla öppna tjänst förfrågningar, dina produkter och fakturering och antalet användare hos denna klient organisation.


## <a name="move-between-tenants"></a>Flytta mellan klient organisationer

1. I administrations centret för Microsoft 365 väljer du organisationens namn.

    :::image type="content" source="../../media/macorgswitcher.png" alt-text="Växlaren med flera innehavare.":::

- Från **klient organisationens växlaren** kan du snabbt flytta mellan klient organisationer som du hanterar.

    :::image type="content" source="../../media/yourtenantslist.png" alt-text="Listan med klient organisationer med Sök funktion.":::

## <a name="view-all-tenants-page"></a>Sidan Visa alla innehavare

1. I administrations centret för Microsoft 365 väljer du **alla innehavare** i det vänstra navigerings fältet.
- På sidan **alla innehavare** kan du
  - Bedöm tjänstens hälsa
  - Granska licens användning
  - Sök efter eller Välj den klient organisation som du vill hantera
  - Du kan också fästa dina mest besökta klient organisationer högst upp i listan.


Om du har markerat en klient organisation som favorit är den automatiskt expanderad så att du kan visa statusinformation omedelbart.

## <a name="view-service-health-for-all-accounts"></a>Visa tjänstens hälsa för alla konton

I vyn tjänste hälsa visas om eventuella händelser eller rådgivare påverkar klient organisationerna. Det visar även hur många av dina hanterade klient organisationer som påverkas.

1. I administrations centret för Microsoft 365 väljer du **tjänstens hälsa** i vyn flera innehavare.
2. I den aggregerade vyn **tjänstens hälso** sida kan du även se det totala antalet händelser, det totala antalet rådgivare som påverkar en av de hanterade klient organisationerna och antalet tjänster med aktiva incidenter. Du kan också se hur många av dina innehavare som påverkas av tillbud och rådgivare.
    
    - Du kan använda filter alternativet för att visa problem efter typ eller tjänst

    - Du kan granska problem under **alla tjänster** eller på flikarna **alla problem** .

    :::image type="content" source="../../media/multitenant-servicehealth.png" alt-text="Sidan för hälso tjänst för flera innehavare.":::
1. Välj en incident på fliken **alla tjänster** eller **alla problem** för att få mer information om eventuella händelser på fliken **Översikt** . Välj fliken **påverkade klient organisationer** för att få en lista över berörda klient organisationer.

    :::image type="content" source="../../media/tenantsaffected.png" alt-text="Lista över klient organisationer som påverkas av tjänstens hälso problem.":::

Listan över berörda klient organisationer kan exporteras till CSV-format så att administratörer kan dela den med support team.

## <a name="view-a-single-tenant-in-the-microsoft-365-admin-center"></a>Visa en enskild klient organisation i administrations centret för Microsoft 365

Du kan återgå till administrations centret för Microsoft 365 för alla klient organisationer från sidan **alla innehavare** .

1. På sidan **alla innehavare** väljer du namnet på den innehavare för vilken du vill visa administrations centret.
2. Du dirigeras till administrations centret för denna klient organisation.