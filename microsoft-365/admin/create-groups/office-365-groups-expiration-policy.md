---
title: Principer för förfallodatum för grupper
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
description: Läs mer om principer för förfallodatum för Microsoft 365-grupper.
ms.openlocfilehash: 0cb67b87a542d021387365802bd5969f4c4332b8
ms.sourcegitcommit: 7f307b4f583b602f11f69adae46d7f3bf6982c65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2020
ms.locfileid: "44064827"
---
# <a name="microsoft-365-group-expiration-policy"></a>Principer för förfallodatum för Microsoft 365-grupp

Med den ökade användningen av Microsoft 365-grupper behöver administratörer och användare ett sätt att rensa oanvända grupper. Principer för förfallodatum kan hjälpa till att ta bort inaktiva grupper från systemet och göra saker renare.

När en grupp upphör att gälla tas även alla tillhörande tjänster (postlådan, Planeraren, SharePoint-webbplatsen, teamet osv.) bort.

När en grupp upphör att gälla är den "mjuk borttagen" vilket innebär att den fortfarande kan återställas i upp till 30 dagar.

Administratörer kan ange en förfalloperiod och alla inaktiva grupper som når slutet av den perioden och som inte förnyas tas bort. Förfallotiden börjar när gruppen skapas eller på det datum då den senast förnyades. Gruppägare skickas automatiskt ett e-postmeddelande före utgången som gör att de kan förnya gruppen för ett annat utgångsdatum. Teams-användare ser beständiga aviseringar i Teams.

Grupper som används aktivt förnyas automatiskt. Någon av följande åtgärder förnyar automatiskt en grupp:
- SharePoint - visa, redigera, ladda ned, flytta, dela eller ladda upp filer.
- Outlook – gå med i grupp-, läs- eller skrivgruppsmeddelande från gruppen och som ett meddelande (Outlook på webben).
- Lag - besöker en lagkanal.

> [!IMPORTANT]
> När du ändrar förfalloprincipen beräknas tjänsten om förfallodatumet för varje grupp. Den börjar alltid räkna från det datum då gruppen skapades och tillämpar sedan den nya förfalloprincipen.

Det är viktigt att veta att förfallodatum är inaktiverat som standard. Administratörer måste aktivera den för sin organisation om de vill använda den.

> [!NOTE]
> Konfigurera och använda principen om förfallodatum för Microsoft 365-grupper kräver att du har men inte nödvändigtvis tilldela Azure AD Premium-licenser för medlemmarna i alla grupper som principen för förfallodatum tillämpas på. Mer information finns under [ Komma igång med Azure Active Directory Premium ](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium).

## <a name="who-can-configure-and-use-the-microsoft-365-groups-expiration-policy"></a>Vem kan konfigurera och använda princip för förfallodatum för Microsoft 365-grupper?

|Roll|Vad de kan göra|
|---------|---------|
|Global administratör (i Azure, företagsadministratören), användaradministratör|Skapa, läsa, uppdatera eller ta bort principinställningarna för förfallodatum för Microsoft 365-grupper.|
|Användare|Förnya eller [återställa](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-restore-deleted) en Microsoft 365-grupp som de äger|

## <a name="how-to-set-the-expiration-policy"></a>Så här ställer du in principen om förfallodatum

Som nämnts ovan är förfallodatumet inaktiverat som standard. En administratör måste aktivera förfalloprincipen och ange att egenskaperna för den ska börja gälla. Om du vill aktivera den går du till **Azure Active Directory (AAD)** > **Grupper** > **förfallodatum**. Här kan du ange standardgruppens livstid och ange hur långt i förväg du vill att den första och andra förfallodatum meddelanden att gå till gruppens ägare.

Gruppens livstid anges i dagar och kan ställas in på 180, 365 eller till ett anpassat värde som du anger. Det anpassade värdet måste vara minst 30 dagar.

Om gruppen inte har någon ägare går e-postmeddelandena för utgångsdatum till en angiven administratör.

Du kan ange principen för alla dina grupper, bara valda grupper eller stänga av den helt genom att välja **Ingen**. Observera att du för närvarande inte kan ha olika principer för olika grupper.

![Skärmbild av inställningar för gruppförfallodatum i Azure Active Directory](../../media/azure-groups-expiration-settings.png)

## <a name="how-expiry-works-with-the-retention-policy"></a>Så här fungerar förfallodatum med bevarandeprincipen

Om du har inställningsbevarandeprincip i Säkerhets- och efterlevnadscenter för grupper fungerar principen för förfallodatum sömlöst med bevarandeprincipen. När en grupp upphör att gälla behålls gruppens konversationer i e-postlådan och filer på gruppwebbplatsen i behållarbehållaren för det specifika antal dagar som definierats i bevarandeprincipen. Användarna kommer dock inte att se gruppen eller dess innehåll efter utgångsdatum.

## <a name="how-and-when-a-group-owner-learns-if-their-groups-are-going-to-expire"></a>Hur och när en gruppägare får reda på om deras grupper kommer att löpa ut

Gruppägare meddelas endast via e-post. Om gruppen skapades via Planner, SharePoint eller någon annan app kommer meddelanden om förfallodatum alltid via e-post. Om gruppen skapades via Teams får gruppägaren ett meddelande om att förnya genom aktivitetsavsnittet. Vi rekommenderar inte att du aktiverar förfallodatum för en grupp om gruppägaren inte har en giltig e-postadress.

30 dagar innan gruppen går ut får gruppägarna (eller de e-postadresser som du har angett för grupper som inte har en ägare) ett e-postmeddelande som gör att de enkelt kan förnya gruppen. Om de inte förnyar det får de ett nytt förnyelsemeddelande 15 dagar före utgångsdatumet. Om de fortfarande inte har förnyat det får de ytterligare ett e-postmeddelande dagen före förfallodatumet.

Om ingen av ägarna eller administratörerna av någon anledning förnyar gruppen innan den upphör att gälla kan administratören fortfarande återställa gruppen i upp till 30 dagar efter utgångsdatumet. Mer information finns i: [Återställ en borttagen Microsoft 365-grupp](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group).

## <a name="related-articles"></a>Relaterade artiklar

[Översikt över bevarandeprinciper](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)

[Tilldela en ny ägare till en överbliven grupp](https://support.microsoft.com/en-us/office/assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732)

[Konfigurera Microsoft 365-gruppers förfallodatum](https://docs.microsoft.com/azure/active-directory/active-directory-groups-lifecycle-azure-portal) '
