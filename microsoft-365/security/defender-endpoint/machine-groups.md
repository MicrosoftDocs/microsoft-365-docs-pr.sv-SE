---
title: Skapa och hantera enhetsgrupper i Microsoft Defender för Slutpunkt
description: Skapa enhetsgrupper och ange automatiserade åtgärdsnivåer för dem genom att bekräfta reglerna som gäller för gruppen
keywords: enhetsgrupper, grupper, åtgärd, nivå, regler, aad-grupp, roll, tilldela, rangordna
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d4f62acde4e7d790c7a7c8635f51c99f0823687d
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842776"
---
# <a name="create-and-manage-device-groups"></a>Skapa och hantera enhetsgrupper

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**
- Azure Active Directory
- Office 365

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


I ett företagsscenario tilldelas vanligtvis säkerhetsåtgärdsteam en uppsättning enheter. De här enheterna grupperas tillsammans baserat på en uppsättning attribut, till exempel deras domäner, datornamn eller angivna taggar.

I Microsoft Defender för Slutpunkt kan du skapa enhetsgrupper och använda dem för att:
- Begränsa åtkomsten till relaterade aviseringar och data till specifika Azure AD-användargrupper med [tilldelade RBAC-roller](rbac.md) 
- Konfigurera olika inställningar för automatisk åtgärd för olika uppsättningar av enheter
- Tilldela specifika åtgärdsnivåer att tillämpa under automatiserade undersökningar
- I en undersökning kan du filtrera **listan Enheter till** specifika enhetsgrupper med hjälp av **gruppfiltret.**

Du kan skapa enhetsgrupper i samband med rollbaserad åtkomst (RBAC) för att styra vem som kan vidta särskilda åtgärder eller se information genom att tilldela enhetsgruppen/grupperna till en användargrupp. Mer information finns i Hantera [portalåtkomst med hjälp av rollbaserad åtkomstkontroll.](rbac.md)

>[!TIP]
> Om du vill ha mer detaljerad information om RBAC-programmet läser du: [Is your SOC running flat with RBAC](https://techcommunity.microsoft.com/t5/Windows-Defender-ATP/Is-your-SOC-running-flat-with-limited-RBAC/ba-p/320015).

Som en del av processen med att skapa en enhetsgrupp gör du följande:
- Ställ in nivån för automatisk åtgärd för gruppen. Mer information om åtgärdsnivåer finns i [Använda automatisk undersökning för att undersöka och åtgärda hot.](automated-investigations.md)
- Ange den matchande regel som bestämmer vilken enhetsgrupp som tillhör gruppen baserat på enhetsnamn, domän, taggar och OS-plattform. Om en enhet matchas med andra grupper läggs den bara till i den enhetsgrupp som rangordnas högst.
- Välj den Azure AD-användargrupp som ska ha åtkomst till enhetsgruppen.
- Rangordna enhetsgruppen i förhållande till andra grupper när den har skapats.

>[!NOTE]
>En enhetsgrupp är tillgänglig för alla användare om du inte tilldelar några Azure AD-grupper till den.

## <a name="create-a-device-group"></a>Skapa en enhetsgrupp

1. I navigeringsfönstret väljer du **Inställningar**  >  **Enhetsgrupper**.

2. Klicka **på Lägg till enhetsgrupp**.

3. Ange inställningarna för gruppnamn och automatisering och ange den matchande regeln som avgör vilka enheter som hör till gruppen. Se [Hur den automatiska undersökningen startar](automated-investigations.md#how-the-automated-investigation-starts).

    >[!TIP]
    >Om du vill gruppera enheter efter organisationsenhet kan du konfigurera registernyckeln för gruppanslutningen. Mer information om enhetstaggar finns i [Skapa och hantera enhetstaggar.](machine-tags.md)

4. Förhandsgranska flera enheter som kommer att matchas med den här regeln. Om du är nöjd med regeln klickar du på **fliken Användaråtkomst.**

5. Tilldela de användargrupper som kan komma åt enhetsgruppen som du har skapat.

    >[!NOTE]
    >Du kan bara bevilja åtkomst till Azure AD-användargrupper som har tilldelats RBAC-roller.

6. Klicka på **Stäng**. Konfigurationsändringarna tillämpas.

## <a name="manage-device-groups"></a>Hantera enhetsgrupper

Du kan höja eller sänka rangordningen för en enhetsgrupp så att den får högre eller lägre prioritet vid matchningen. När en enhet matchas med fler än en grupp läggs den bara till i den högst rankade gruppen. Du kan också redigera och ta bort grupper.



>[!WARNING]
>Om du tar bort en enhetsgrupp kan det påverka e-postaviseringsregler. Om en enhetsgrupp konfigureras under en regel för e-postavisering tas den bort från regeln. Om enhetsgruppen är den enda grupp som konfigurerats för en e-postavisering tas e-postaviseringsregeln bort tillsammans med enhetsgruppen.

Som standard är enhetsgrupper tillgängliga för alla användare med portalåtkomst. Du kan ändra standardbeteendet genom att tilldela Azure AD-användargrupper till enhetsgruppen.

Enheter som inte matchas med några grupper läggs till i gruppen Dela upp enheter (standard). Du kan inte ändra rangordningen för gruppen eller ta bort den. Du kan dock ändra åtgärdsnivån för den här gruppen och definiera de Azure AD-användargrupper som har åtkomst till den här gruppen.

>[!NOTE]
> Det kan ta upp till flera minuter att tillämpa ändringar på enhetsgruppskonfigurationen.


### <a name="add-device-group-definitions"></a>Lägga till enhetsgruppsdefinitioner
Enhetsgruppsdefinitioner kan också innehålla flera värden för varje villkor. Du kan ange definitionen för en enda enhetsgrupp för flera taggar, enhetsnamn och domäner.

1. Skapa en ny enhetsgrupp och välj sedan **fliken** Enheter.
2. Lägg till det första värdet för något av villkoren.
3. Välj `+` den här om du vill lägga till fler rader av samma egenskapstyp.

>[!TIP]
> Använd operatorn ELLER mellan rader av samma villkorstyp, som tillåter flera värden per egenskap.
> Du kan lägga till upp till 10 rader (värden) för varje egenskapstyp – tagg, enhetsnamn, domän.

Mer information om hur du länkar till definitioner av enhetsgrupper finns [i Enhetsgrupper – Microsoft 365 säkerhet.](https://sip.security.microsoft.com/homepage)

## <a name="related-topics"></a>Relaterade ämnen

- [Hantera portalåtkomst med hjälp av rollbaserad åtkomstkontroll](rbac.md)
- [Skapa och hantera enhetstaggar](machine-tags.md)
- [Hämta en lista över grupper på klientorganisationsenheten med hjälp Graph API](/graph/api/device-list-memberof)
