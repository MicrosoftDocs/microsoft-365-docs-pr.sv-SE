---
title: Hantera flera klientorganisationer
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
description: Lär dig hur du använder klientorganisationens omkopplare och om vyer för flera innehavare.
ms.openlocfilehash: 21b51a5e0c79496bf73e60c04aea68def3cf8ad6
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580888"
---
# <a name="multi-tenant-management"></a>Hantering av flera innehavare

Hantering för flera innehavare erbjuder en enhetlig form av hantering som gör att administratörer kan administrera alla klientorganisationen de hanterar från en enda plats. Om du hanterar flera klientorganisationsklienter kan du:

- Flytta snabbt mellan klientorganisationar som du hanterar.
- Utvärdera tjänstehälsa, produkter och fakturering för flera klientorganisationar.
- På sidan **Alla klientorganisationen** kan du snabbt se hälsotillståndet för alla klientorganisationens tjänster, alla öppna tjänstförfrågningar, dina produkter och fakturering samt antalet användare i klientorganisationen.


## <a name="move-between-tenants"></a>Flytta mellan klientorganisationen

1. Välj organisationsnamnet i administrationscentret för Microsoft 365.

    :::image type="content" source="../../media/macorgswitcher.png" alt-text="Omkopplare för flera innehavare.":::

- Från **innehavarbytet** kan du snabbt växla mellan klientorganisationen som du hanterar.

    :::image type="content" source="../../media/yourtenantslist.png" alt-text="Klientorganisationens lista med sökfunktioner.":::

## <a name="view-all-tenants-page"></a>Visa alla klientorganisationssidor

1. I det vänstra navigeringsfältet i administrationscentret för Microsoft 365 väljer du **Alla innehavare.**
- På **sidan Alla innehavare** kan du
  - Utvärdera tjänstens hälsa
  - Granska licensanvändning
  - Sök efter eller välj den klientorganisation du vill hantera
  - Du kan också fästa den klientorganisation du besöker oftast överst i listan.


Om du har markerat en klientorganisation som favorit expanderas den automatiskt så att du direkt kan visa statusinformation.

## <a name="view-service-health-for-all-accounts"></a>Visa tjänsthälsa för alla konton

I vyn Tjänstens hälsa visas om några incidenter eller rådgivningar påverkar klientorganisationen. Där ser du även hur många av dina hanterade klientorganisationar som påverkas.

1. Välj Tjänstens hälsa i flerklientsvyn i administrationscentret för Microsoft 365.
2. På sidan **Tjänstens** hälsa i den sammantagna vyn kan du även se det totala antalet incidenter, det totala antalet rådgivningar som påverkar någon av de hanterade klientorganisationen och antalet tjänster med aktiva incidenter. Du kan också se hur många av dina klienter som påverkas av incidenter och rådgivningar.
    
    - Du kan använda filteralternativet för att visa problem per typ av problem eller tjänst

    - Du kan granska problem under **Alla tjänster eller** fliken **Alla** problem.

    :::image type="content" source="../../media/multitenant-servicehealth.png" alt-text="Hälsosida för tjänsten för flera innehavare.":::
1. Välj en händelse på **fliken Alla tjänster** eller Alla **ärenden** om du vill ha mer information om en händelse på **fliken** Översikt. Välj fliken **Klientorganisation som påverkas** för att visa en lista över de berörda klientorganisationen.

    :::image type="content" source="../../media/tenantsaffected.png" alt-text="Lista över klientorganisationen som påverkas av ett problem med tjänstens hälsa.":::

Listan över berörda klientorganisationen kan exporteras till CSV-format så att administratörer kan dela den med supportteam.

## <a name="view-a-single-tenant-in-the-microsoft-365-admin-center"></a>Visa en enskild klientorganisation i Administrationscenter för Microsoft 365

Du kan gå tillbaka till administrationscentret för Microsoft 365 för valfri klientorganisation på **sidan Alla klienter.**

1. På **sidan Alla innehavare** väljer du det klientnamn som du vill visa administrationscentret för.
2. Du dirigeras till administrationscentret för den klientorganisationen.