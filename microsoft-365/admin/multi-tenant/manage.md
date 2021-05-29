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
description: Lär dig hur du använder vyerna för klientbyte och flera innehavare som ger dig möjlighet att hantera klientorganisationen från en enda plats.
ms.openlocfilehash: e0bf6c872d4998c0cd0263fd8474ac5e9c99ef14
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706160"
---
# <a name="multi-tenant-management"></a>Hantering av flera innehavare

Hantering av flera klientorganisationener erbjuder en enhetlig form av hantering som ger Microsoft 365 partneradministratörer möjlighet att administrera alla klientorganisationen de hanterar från en enda plats. Om du är en partner som hanterar flera klientorganisationar kan du:

- Flytta snabbt mellan klientorganisationar som du hanterar.
- Utvärdera tjänstehälsa, produkter och fakturering för flera klientorganisationar.
- På sidan **Alla klientorganisationen** kan du snabbt se hälsotillståndet för alla klientorganisationens tjänster, alla öppna tjänstförfrågningar, dina produkter och fakturering samt antalet användare i klientorganisationen.

## <a name="move-between-tenants"></a>Flytta mellan klientorganisationen

1. Välj Microsoft 365 i administrationscentret.

    :::image type="content" source="../../media/macorgswitcher.png" alt-text="Omkopplare för flera innehavare.":::

- Från **innehavarbytet** kan du snabbt växla mellan klientorganisationen som du hanterar.

    :::image type="content" source="../../media/yourtenantslist.png" alt-text="Klientorganisationens lista med sökfunktioner.":::

## <a name="view-all-tenants-page"></a>Visa alla klientorganisationssidor

1. Välj Microsoft 365 alla innehavare i det vänstra **navigeringsfältet i administrationscentret.**
- På **sidan Alla innehavare** kan du
  - Utvärdera tjänstens hälsa
  - Granska licensanvändning
  - Sök efter eller välj den klientorganisation du vill hantera
  - Du kan också fästa den klientorganisation du besöker oftast överst i listan.

Om du har markerat en klientorganisation som favorit expanderas den automatiskt så att du direkt kan visa statusinformation.

## <a name="view-service-health-for-all-accounts"></a>Visa tjänsthälsa för alla konton

I vyn Tjänstens hälsa visas om några incidenter eller rådgivningar påverkar klientorganisationen. Där ser du även hur många av dina hanterade klientorganisationar som påverkas.

1. I Microsoft 365 flerklientsvy i administrationscentret väljer du **Tjänstens hälsa.**
2. På sidan **Tjänstens** hälsa i den sammantagna vyn kan du även se det totala antalet incidenter, det totala antalet rådgivningar som påverkar någon av de hanterade klientorganisationen och antalet tjänster med aktiva incidenter. Du kan också se hur många av dina klienter som påverkas av incidenter och rådgivningar.

    - Du kan använda filteralternativet för att visa problem per typ av problem eller tjänst

    - Du kan granska problem under **Alla tjänster eller** fliken **Alla** problem.

    :::image type="content" source="../../media/multitenant-servicehealth.png" alt-text="Hälsosida för tjänsten för flera innehavare.":::
1. Välj en händelse på **fliken Alla tjänster** eller Alla **ärenden** om du vill ha mer information om en händelse på **fliken** Översikt. Välj fliken **Klientorganisation som påverkas** för att visa en lista över de berörda klientorganisationen.

    :::image type="content" source="../../media/tenantsaffected.png" alt-text="Lista över klientorganisationen som påverkas av ett problem med tjänstens hälsa.":::

Listan över berörda klientorganisationen kan exporteras till CSV-format så att administratörer kan dela den med supportteam.

## <a name="view-a-single-tenant-in-the-microsoft-365-admin-center"></a>Visa en enskild klientorganisation Microsoft 365 administrationscentret

Du kan gå Microsoft 365 administrationscentret för någon av klientorganisationen på **sidan Alla** klienter.

1. På **sidan Alla innehavare** väljer du det klientnamn som du vill visa administrationscentret för.
2. Du dirigeras till administrationscentret för den klientorganisationen.