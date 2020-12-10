---
title: Utgångs princip för Microsoft 365-gruppen
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
description: Lär dig mer om principer för förfallo datum för Microsoft 365 Groups.
ms.openlocfilehash: d55cc7fff939cb07ae2eba92de411e8f0d088885
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613660"
---
# <a name="microsoft-365-group-expiration-policy"></a>Utgångs princip för Microsoft 365-gruppen

Med ökad användning av Microsoft 365-grupper och Microsoft Teams behöver administratörer och användare ett sätt att rensa oanvända grupper och team. En utgångs policy för Microsoft 365 Groups kan hjälpa till att ta bort inaktiva grupper från systemet och göra saker renare.

När en grupp går ut tas alla tillhör ande tjänster (post lådan, Planner, SharePoint-webbplatsen, teamet etc.) också bort.

När en grupp upphör är "mjuk borttagen", vilket innebär att den fortfarande kan återställas i upp till 30 dagar.

Administratörer kan ange en förfallo period och alla inaktiva grupper som når slutet av perioden och som inte förnyas, tas bort. (Detta inkluderar arkiverade team.) Utgångs perioden börjar när gruppen skapas, eller vid det datum då den senast förnyades. Grupp ägare kommer automatiskt att skicka ett e-postmeddelande innan utgångs datumet gör det möjligt för dem att förnya gruppen för ett annat utgångs intervall. Teams användarna kan se beständiga meddelanden i Teams.

Grupper som aktivt används förnyas automatiskt. En av följande åtgärder kommer automatiskt att förnya en grupp:
- SharePoint – Visa, redigera, ladda ned, flytta, dela eller ladda upp filer. (Visning av en SharePoint-sida räknas inte som en åtgärd för automatisk förnyelse.)
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
|Global administratör för Office 365 (i Azure, företags administratören), användar administratör|Skapa, läsa, uppdatera och ta bort princip inställningar för förfallo principer för Microsoft 365 Groups.|
|Användare|Förnya eller [återställa](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-restore-deleted) en Microsoft 365-grupp som de äger|

## <a name="how-to-set-the-expiration-policy"></a>Ange förfallo princip

Som vi noterade ovan är förfallo datumet inaktiverat som standard. En administratör måste aktivera policyn för förfallo datum och ställa in egenskaperna för att den ska gälla. Gå till gruppen **Azure Active Directory**-grupper för att aktivera den  >    >  . Här kan du ange standard livstid för gruppen och ange hur långt i förväg du vill att aviseringarna för första och sista giltighets tiden ska gå till gruppens ägare.

Gruppens livs längd anges i dagar och kan anges till 180, 365 eller till ett anpassat värde som du anger. Värdet måste vara minst 30 dagar.

Om gruppen inte har någon ägare skickas e-postmeddelandet till den angivna administratören.

Du kan ställa in policyn för alla dina grupper, endast valda grupper eller stänga av den helt och hållet genom att välja **ingen**. Observera att du inte kan använda olika principer för olika grupper.

![Skärm bild av inställningar för förfallo tid för grupper i Azure Active Directory](../media/azure-groups-expiration-settings.png)

## <a name="how-expiry-works-with-the-retention-policy"></a>Hur giltighets tiden fungerar med bevarande principen

Om du har konfigurerat en bevarande princip för grupper i säkerhets-och kompatibilitetstillstånd fungerar principens förfallo dag sömlöst med bevarande princip. När en grupp upphör sparas gruppens post lådans konversationer och filer i grupp webbplatsen i behållnings behållaren för det angivna antalet dagar som definierats i bevarande principen. Användarna kan inte se gruppen eller dess innehåll efter att det har gått ut.

## <a name="how-and-when-a-group-owner-learns-if-their-groups-are-going-to-expire"></a>Hur och när en grupp ägare lär sig om deras grupper upphör att gälla

Grupp ägare meddelas bara via e-post. Om gruppen skapades via Planner, SharePoint eller något annat program kommer giltighets meddelandena alltid att skickas via e-post. Om gruppen skapades via Teams får grupp ägaren ett meddelande om att förnya via avsnittet aktivitet. Du rekommenderas inte att aktivera utgångs datum för en grupp om gruppens ägare inte har en giltig e-postadress.

30 dagar innan gruppen går ut får grupp ägarna (eller de e-postadresser som du har angett för grupper som inte har en ägare) ett e-postmeddelande som gör det enkelt att förnya gruppen. Om de inte förnyar det får de en ny förnyelse via e-post 15 dagar före utgångs datum. Om de fortfarande inte har förnyat det får de ett mer e-postmeddelande dagen innan den upphör att gälla.

Om du av någon anledning inte förnyar gruppen innan den upphör kan administratören återställa gruppen i upp till 30 dagar efter förfallo dagen. Mer information finns i: [återställa en borttagen Microsoft 365-grupp](https://support.office.com/article/restore-a-deleted-office-365-group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54).

## <a name="archiving-group-contents"></a>Arkivera grupp innehåll

Om du har en grupp som du inte längre planerar att använda, men du vill behålla dess [innehåll, kan du läsa om](end-life-cycle-groups-teams-sites-yammer.md) hur du exporterar information från de olika grupp tjänsterna.

## <a name="related-topics"></a>Relaterade ämnen

[Planerings steg-för-steg-samarbete för samarbets styrning](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Skapa en plan för hantering av samarbete](collaboration-governance-first.md)

[Översikt över bevarande principer](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)

[Tilldela en ny ägare till en överbliven grupp](https://support.office.com/article/86bb3db6-8857-45d1-95c8-f6d540e45732)

[Konfigurera att Microsoft 365-grupper upphör](https://docs.microsoft.com/azure/active-directory/active-directory-groups-lifecycle-azure-portal)
