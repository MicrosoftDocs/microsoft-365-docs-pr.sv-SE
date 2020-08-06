---
title: Förfallo princip för grupper
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Lär dig mer om principer för förfallo datum för Microsoft 365 Groups.
ms.openlocfilehash: bda4bfbbef4e0d145c55b2a49b4d1203c6a7b1f0
ms.sourcegitcommit: 4f82fa7270e7ec6c6dd80329f28612e1f3289b22
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2020
ms.locfileid: "46572145"
---
# <a name="microsoft-365-group-expiration-policy"></a>Utgångs princip för Microsoft 365-gruppen

Med ökad användning av Microsoft 365-grupper behöver administratörer och användare ett sätt att rensa oanvända grupper. Principer för förfallo datum kan hjälpa till att ta bort inaktiva grupper från systemet och göra saker renare.

När en grupp går ut tas alla tillhör ande tjänster (post lådan, Planner, SharePoint-webbplatsen, teamet etc.) också bort.

När en grupp upphör är "mjuk borttagen", vilket innebär att den fortfarande kan återställas i upp till 30 dagar.

Administratörer kan ange en förfallo period och alla inaktiva grupper som når slutet av perioden och som inte förnyas, tas bort. Utgångs perioden börjar när gruppen skapas, eller vid det datum då den senast förnyades. Grupp ägare kommer automatiskt att skicka ett e-postmeddelande innan utgångs datumet gör det möjligt för dem att förnya gruppen för ett annat utgångs intervall. Teams användarna kan se beständiga meddelanden i Teams.

Grupper som aktivt används förnyas automatiskt. En av följande åtgärder kommer automatiskt att förnya en grupp:
- SharePoint – Visa, redigera, ladda ned, flytta, dela eller ladda upp filer.
- Outlook – gå med i gruppen, läsa eller skriva grupp meddelande från gruppen och gilla ett meddelande (Outlook på webben).
- Teams som besöker en Teams-kanal.

> [!IMPORTANT]
> När du ändrar förfallo dagen beräknas utgångs datumet för varje grupp. Det börjar alltid räkna från det datum då gruppen skapades och sedan tillämpas den nya princip policyn.

Det är viktigt att veta att förfallo dagen är inaktive rad som standard. Administratörer måste aktivera den för organisationen om de vill använda den.

> [!NOTE]
> Om du konfigurerar och använder policyn för utgångs datum för Microsoft 365-grupper måste du ha men inte nödvändigt vis tilldela Azure AD Premium-licenser för medlemmar i alla grupper som princip för förfallo tid tillämpas. Mer information finns under [ Komma igång med Azure Active Directory Premium ](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium).

## <a name="who-can-configure-and-use-the-microsoft-365-groups-expiration-policy"></a>Vem kan konfigurera och använda Microsofts 365-grupper giltighets princip?

|Roll|Vad de kan göra|
|---------|---------|
|Global administratör (i Azure, företags administratören), användar administratör|Skapa, läsa, uppdatera och ta bort princip inställningar för förfallo principer för Microsoft 365 Groups.|
|Användare|Förnya eller [återställa](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-restore-deleted) en Microsoft 365-grupp som de äger|

## <a name="how-to-set-the-expiration-policy"></a>Ange förfallo princip

Som vi noterade ovan är förfallo datumet inaktiverat som standard. En administratör måste aktivera policyn för förfallo datum och ställa in egenskaperna för att den ska gälla. Så här aktiverar du funktionen gå till gruppen **Azure Active Directory (AAD)**  >  **Groups**  >  **Expiration**. Här kan du ange standard livstid för gruppen och ange hur långt i förväg du vill att aviseringarna för första och sista giltighets tiden ska gå till gruppens ägare.

Gruppens livs längd anges i dagar och kan anges till 180, 365 eller till ett anpassat värde som du anger. Värdet måste vara minst 30 dagar.

Om gruppen inte har någon ägare skickas e-postmeddelandet till angiven administratör.

Du kan ställa in policyn för alla dina grupper, endast valda grupper eller stänga av den helt och hållet genom att välja **ingen**. Observera att du inte kan använda olika principer för olika grupper.

![Skärm bild av inställningar för förfallo tid för grupper i Azure Active Directory](../../media/azure-groups-expiration-settings.png)

## <a name="how-expiration-and-renewal-work"></a>Så här fungerar förfallo datum och förnyelse

Princip för förfallo tid fungerar så här: 

- Om en månad före utgångs datum kontrollerar systemet om det finns någon grupp aktivitet sedan gruppen skapades eller sedan början av den aktuella förnyelse cykeln.

- Om en tidigare aktivitet identifieras är utgångs datumet Avancerat vid den tidpunkten med det antal dagar som anges i policyn för förfallo dag.

- Om en föregående aktivitet inte hittas fortsätter systemet att titta efter aktivitet fram till utgångs datumet. Om aktiviteten hittas förfaller systemet fram utgångs datumet med angivet belopp vid den tidpunkten.

30 dagar innan gruppen går ut får grupp ägarna (eller de e-postadresser som du har angett för grupper som inte har en ägare) ett e-postmeddelande som gör det enkelt att förnya gruppen. Om de inte förnyar det får de en ny förnyelse via e-post 15 dagar före utgångs datum. Om de fortfarande inte har förnyat det får de ett mer e-postmeddelande dagen innan den upphör att gälla. (När gruppen har förnyats skickas inga fler e-postpåminnelser förrän 30 dagar före det nya utgångs datumet.)

Grupp ägare meddelas via e-post. Om gruppen skapades via Planner, SharePoint eller något annat program kommer giltighets meddelandena alltid att skickas via e-post. Om gruppen skapades via Teams får grupp ägaren ett meddelande om att förnya via avsnittet aktivitet. Du rekommenderas inte att aktivera utgångs datum för en grupp om gruppens ägare inte har en giltig e-postadress.

Om du av någon anledning inte förnyar gruppen innan den upphör att gälla, och automatisk förnyelse inte sker på grund av att den grupp som inte uppfyller kraven automatiskt förnyas, kan administratören återställa gruppen i upp till 30 dagar efter förfallo dagen. Mer information finns i: [återställa en borttagen Microsoft 365-grupp](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group).

## <a name="how-expiry-works-with-retention-policies"></a>Hur upphör ande fungerar med bevarande principer

Om du har en princip för konfigurations lagring i säkerhets-och kompatibilitetstillstånd för grupper fungerar utgångs principen sömlöst med bevarande princip. När en grupp går ut bevaras gruppens konversationer i e-postlådan och filer i grupp webbplatsen bevaras i behållnings behållaren för det angivna antalet dagar som definierats i bevarande principen. Användarna kan inte se gruppen eller dess innehåll efter att det har gått ut.

## <a name="related-articles"></a>Relaterade artiklar

[Översikt över bevarande principer](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)

[Tilldela en ny ägare till en överbliven grupp](https://support.microsoft.com/office/86bb3db6-8857-45d1-95c8-f6d540e45732)

[Konfigurera att Microsoft 365-grupper upphör](https://docs.microsoft.com/azure/active-directory/active-directory-groups-lifecycle-azure-portal)

[Aktivitet baserad automatisk förnyelse](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle)
