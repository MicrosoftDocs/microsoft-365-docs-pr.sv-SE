---
title: Förfalloprincip för Microsoft 365-grupper
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
description: Läs mer om förfalloprinciper för Microsoft 365-grupper.
ms.openlocfilehash: fdef06918ec2c35547c084e5f431aa7bef8d6a8c
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587629"
---
# <a name="microsoft-365-group-expiration-policy"></a>Förfalloprincip för Microsoft 365-grupper

Med den ökade användningen av Microsoft 365-grupper och Microsoft Teams behöver administratörer och användare ett sätt att rensa upp oanvända grupper och team. Förfalloprinciper för Microsoft 365-grupper kan ta bort inaktiva grupper från systemet och göra saker renare.

När en grupp upphör att gälla tas även alla tillhörande tjänster (postlådan, Planner, SharePoint-webbplatsen, teamet osv.) bort.

När en grupp upphör att gälla "mjuk borttagna" vilket innebär att den fortfarande kan återställas i upp till 30 dagar.

Administratörer kan ange en förfalloperiod och alla inaktiva grupper som når slutet av perioden och inte förnyas tas bort. (Detta inkluderar arkiverade team.) Förfallotiden börjar när gruppen skapas eller det datum då den senast förnyades. Gruppägare får automatiskt ett e-postmeddelande före förfallotiden så att de kan förnya gruppen för ett annat utgångsintervall. Teams-användare ser beständiga meddelanden i Teams.

Grupper som aktivt används förnyas automatiskt. När du gör något av följande förnyas en grupp automatiskt:
- SharePoint – visa, redigera, ladda ned, flytta, dela eller ladda upp filer. (Att visa en SharePoint-sida räknas inte som en åtgärd för automatisk förnyelse.)
- Outlook – gå med i gruppen, läsa eller skriva gruppmeddelanden från gruppen och gilla ett meddelande (Outlook på webben).
- Teams – besök en teamkanal.

Observera att den enda Yammer-aktivitet som utlöser automatisk gruppförnyelse är överföringen av ett dokument till SharePoint inom communityn.

> [!IMPORTANT]
> När du ändrar förfalloprincipen beräknas utgångsdatumet för varje grupp om. Den börjar alltid räkna från datumet när gruppen skapades och tillämpar sedan den nya förfalloprincipen.

Det är viktigt att veta att utgångsdatumet är inaktiverat som standard. Administratörer måste aktivera det för organisationen om de vill använda det.

> [!NOTE]
> När du konfigurerar och använder förfalloprincipen för Microsoft 365-grupper behöver du ha, men inte nödvändigtvis, tilldela Azure AD Premium-licenser för medlemmar i alla grupper som förfalloprincipen tillämpas på. Mer information finns under [ Komma igång med Azure Active Directory Premium ](/azure/active-directory/active-directory-get-started-premium).

## <a name="who-can-configure-and-use-the-microsoft-365-groups-expiration-policy"></a>Vem kan konfigurera och använda förfalloprincipen för Microsoft 365-grupper?

|Roll|Vad de kan göra|
|---------|---------|
|Global Office 365-administratör (i Azure, företagsadministratör), användaradministratör|Skapa, läsa, uppdatera eller ta bort förfalloprincipinställningarna för Microsoft 365-grupper.|
|Användare|Förnya eller [återställa](/azure/active-directory/users-groups-roles/groups-restore-deleted) en Microsoft 365-grupp som de äger|

## <a name="how-to-set-the-expiration-policy"></a>Så här ställer du in förfalloprincip

Som ovan är utgångsinställningen inaktiverad som standard. En administratör måste aktivera förfalloprincipen och ange egenskaperna för att den ska gälla. Du aktiverar funktionen genom att gå till **förfallotiden för Azure Active**  >  **Directory-grupper.**  >   Här kan du ange standardlivslängd för gruppen och ange hur långt i förväg du vill att det första och andra förfallomeddelandena ska gå till gruppägaren.

Grupplivslängd anges i dagar och kan anges till 180, 365 eller ett anpassat värde som du anger. Det anpassade värdet måste vara minst 30 dagar.

Om gruppen inte har en ägare skickas förfallomeddelandena till den angivna administratören.

Du kan ange principen för alla grupper, endast markerade grupper (upp till 500), eller inaktivera den helt genom att välja **Ingen**. Observera att du för närvarande inte kan ha olika principer för olika grupper.

![Skärmbild av förfalloinställningar för grupper i Azure Active Directory](../media/azure-groups-expiration-settings.png)

## <a name="how-expiry-works-with-the-retention-policy"></a>Så här fungerar förfalloprincipen med bevarandeprincipen

Om du har ställt in en bevarandeprincip för grupper i Säkerhets- och efterlevnadscenter fungerar förfalloprincipen smidigt med bevarandeprincipen. När en grupp upphör att gälla behålls gruppens postlådekonversationer och filer på gruppwebbplatsen i bevarandebehållaren under det angivna antalet dagar som definieras i bevarandeprincipen. Användare kan däremot inte se gruppen eller dess innehåll efter att den har gått ut.

## <a name="how-and-when-a-group-owner-learns-if-their-groups-are-going-to-expire"></a>Hur och när en gruppägare får veta om deras grupper kommer att upphöra att gälla

Gruppägare meddelas endast via e-post. Om gruppen har skapats via Planner, SharePoint eller någon annan app kommer förfalloaviseringarna alltid via e-post. Om gruppen har skapats via Teams får gruppägaren ett meddelande om att förnya via aktivitetsavsnittet. Vi rekommenderar inte att du aktiverar förfallotid för en grupp om gruppägaren inte har en giltig e-postadress.

Trettio dagar innan gruppen löper ut får gruppägarna (eller de e-postadresser som du angett för grupper som inte har en ägare) ett e-postmeddelande så att de enkelt kan förnya gruppen. Om de inte förnyar den får de ytterligare ett e-postmeddelande om förnyelse 15 dagar före utgångsdatumet. Om de fortfarande inte har förnyat den får de ytterligare en e-postavisering dagen före utgångsdatumet.

Om ingen av ägarna eller administratörerna förnyar gruppen innan den löper ut kan administratören fortfarande återställa gruppen i upp till 30 dagar efter att den upphört. Mer information finns i: [Återställa en borttagna Microsoft 365-grupp](https://support.office.com/article/restore-a-deleted-office-365-group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54).

## <a name="archiving-group-contents"></a>Arkivera gruppinnehåll

Om du har en grupp som du inte längre tänker använda, men du vill behålla dess innehåll, hittar du information i Arkivera [grupper,](end-life-cycle-groups-teams-sites-yammer.md) grupper och Yammer om hur du exporterar information från de olika grupptjänsterna.

## <a name="related-topics"></a>Relaterade ämnen

[Planering av samarbetsstyrning steg för steg](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Skapa din plan för samarbetesstyrning](collaboration-governance-first.md)

[Översikt över bevarandeprinciper](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)

[Tilldela en ny ägare till en överbliven grupp](https://support.office.com/article/86bb3db6-8857-45d1-95c8-f6d540e45732)

[Konfigurera förfallotid för Microsoft 365-grupper](/azure/active-directory/active-directory-groups-lifecycle-azure-portal)
