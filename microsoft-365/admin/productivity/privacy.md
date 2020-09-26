---
title: Microsoft produktivitets Poäng – integritet
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
monikerRange: o365-worldwide
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ROBOTS: NOINDEX, NOFOLLOW
description: Hur integritet skyddas med produktivitets poängen.
ms.openlocfilehash: 799d532ca1f0abd5fa6234052d4875a79d629601
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/26/2020
ms.locfileid: "48287332"
---
# <a name="privacy-controls-for-productivity-score"></a>Integritets inställningar för produktivitets Poäng

Produktivitets poäng gör det lättare för organisationer att omvandla hur arbete görs med insikter om hur människor använder Microsoft 365 och de teknik funktioner som har stöd för dem. Poängen reflekterar din organisation&#39;s prestanda i förhållande till anställda och teknik och jämför poängen med organisationer som du vill. Mer information finns i avsnittet om [produktivitets Poäng](productivity-score.md) .

Din integritet är viktig för oss och du kan läsa Microsofts sekretess policy [här](https://privacy.microsoft.com/privacystatement). I produktivitets Poäng finns viktig information som vi tillhandahåller för hur personer i din organisation jobbar. Därför strävar vi också efter att kontrol lera att uppgifterna är åtgärdade på ett meningsfullt sätt utan att kompromissa med förtroendet som du lägger in i USA.

Vi tillhandahåller följande kontroller för att möjliggöra säkrare hantering av data:

- Flexibla administratörs roller för att kontrol lera vem som kan se informationen i produktivitets poängen.
- Anonymisering på användar nivå mått.
- Möjlighet att välja bort en persons upplevelse.

## <a name="flexible-admin-roles-to-control-who-can-see-the-information-in-productivity-score"></a>Flexibla administratörs roller för att styra vem som kan se informationen i produktivitets poängen

För att se hela produktivitets poängen med en administratörs roll, inklusive uppgifter om klient organisations nivå och per användares nivå, bör din roll vara något av följande:

- Global administratör
- Exchange-administratörer
- SharePoint-administratör
- Skype för företag-administratör
- Teams-administratör
- Global läsare
- Rapport läsare

Om du vill bjuda in personer som är ansvariga för ändrings hantering och antagande, men inte är IT-administratörer i upplevelsen, samtidigt som du ger dem till gång till den fullständiga versionen av klient nivåer och användar nivå, kan du ge dem rapporterings läsarens roll.

I den anställdes upplevelse tillhandahåller vi aktivitets information per användare i rutnäts format för varje kategori informations sida. Eftersom den här detalj nivån inte är lämplig för alla potentiella besökare av produktivitets poängen har vi skapat en anpassad roll i Azure AD – översikt över användnings sammandrag – för att ge till gång till en bredare uppsättning besökare inom din organisation till endast aggregerade mått och ingen information per nivå.

:::image type="content" source="../../media/communicationspage.jpg" alt-text="Sidan kommunikation i produktivitets rapporterna.":::

## <a name="anonymization-of-user-level-metrics"></a>Anonymisering på användar nivå mått

Du måste vara global administratör för att data ska samlas in för anonyma rapporter. Då döljs identifierbar information som användare, grupper och webbplats namn i alla rapporter – inklusive produktivitets Poäng och Microsoft 365-användning.

1. Gå till **Inställningar**i administrations centret   >   **Org Settings** och välj **rapporter**på fliken **tjänster** .
2. Välj  **rapporter** och välj sedan om du vill  **Visa anonyma identifierare för användare, grupp och webbplats namn i produktivitets-och användnings rapporter**. Denna inställning tillämpas både på användnings rapporterna och i programmet.
3. Välj  **Spara ändringar**.

:::image type="content" source="../../media/orgsettings_anonymous.jpg" alt-text="Gör användar informationen anonym för rapporter.":::

## <a name="capability-to-opt-out-of-employee-experience"></a>Möjlighet att välja ut en persons upplevelse

Vi kommer även att få möjlighet att välja ut den anställdas erfarenhet av produktivitets poäng till allmän tillgänglighet. Om du aktiverar den här inställningen för att förhindra att någon från din organisation kan visa dessa mått och ta bort din organisation från alla typer av kommunikation, möten, samarbete, innehålls samarbete och rörlighet.

1. Gå till **Inställningar**i administrations centret   >   **Org Settings** och välj **rapporter**på fliken **tjänster** .
2. Välj  **rapporter** och sedan avmarkerar du kryss rutan  **dela organisationens&#39;s-data med produktivitets Poäng för anställda**. Om du vill förstå hur du ändrar inställningar för data delning för slut punkts analys i Intune Configuration Manager klickar du på **Mer information**.
3. Välj  **Spara ändringar**.

:::image type="content" source="../../media/orgsettingspageoptout.jpg" alt-text="Sidan organisations inställningar där du kan välja mellan en persons upplevelse.":::