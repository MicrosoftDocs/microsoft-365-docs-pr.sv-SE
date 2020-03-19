---
title: Förfalloprincip för Office 365-grupper
ms.reviewer: arvaradh
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: get-started-article
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
description: Läs mer om förfalloprinciper för Office 365-grupper.
ms.openlocfilehash: c4c2f7b98247cc81b3fadc561f92084f9bd39c96
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42808678"
---
# <a name="office-365-group-expiration-policy"></a>Förfalloprincip för Office 365-grupper

Med den ökade användningen av Office 365-grupper behöver administratörer och användare ett sätt att rensa oanvända grupper. Förfallodatumprinciper kan hjälpa till att ta bort inaktiva grupper från systemet och göra saker renare.

När en grupp upphör att gälla tas även alla tillhörande tjänster (postlådan, Planner, SharePoint-webbplatsen osv.) bort.

När en grupp går ut är den "mjukborttagen" vilket innebär att den fortfarande kan återställas i upp till 30 dagar.

Administratörer kan ange en förfallotid och alla inaktiva grupper som når slutet av den perioden och som inte förnyas tas bort. Förfallotiden börjar när gruppen skapas eller det datum då den senast förnyades. Gruppägare skickas automatiskt ett e-postmeddelande före förfallodagen som gör att de kan förnya gruppen för ett annat utgångsdatum. Teamanvändare ser beständiga meddelanden i Teams.

Grupper som används aktivt förnyas automatiskt. Någon av följande åtgärder förnyar automatiskt en grupp:
- SharePoint - visa, redigera, ladda ned, flytta, dela eller ladda upp filer.
- Outlook - gå med i grupp, läsa eller skriva gruppmeddelande från gruppen och gilla ett meddelande (Outlook på webben).
- Team - besöker en lagkanal.

> [!IMPORTANT]
> När du ändrar förfalloprincipen beräknas tjänsten om utgångsdatumet för varje grupp. Den börjar alltid räkna från det datum då gruppen skapades och tillämpar sedan den nya förfalloprincipen.

Det är viktigt att veta att förfallodatumet är inaktiverat som standard. Administratörer måste aktivera den för sin klient om de vill använda den.

> [!NOTE]
> För att konfigurera och använda förfalloprincipen för Office 365-grupper måste du inneha men inte nödvändigtvis tilldela Azure AD Premium-licenser för medlemmarna i alla grupper som förfalloprincipen tillämpas på. Mer information finns under [ Komma igång med Azure Active Directory Premium ](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium).

## <a name="who-can-configure-and-use-the-office-365-groups-expiration-policy"></a>Vem kan konfigurera och använda förfalloprincipen för Office 365-grupper?

|Roll|Vad de kan göra|
|---------|---------|
|Office 365 global admin (i Azure, företagsadministratören), Användaradministratör|Skapa, läsa, uppdatera eller ta bort principinställningarna för Office 365-grupper.|
|Användare|Förnya eller [återställa](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-restore-deleted) en Office 365-grupp som de äger|

## <a name="how-to-set-the-expiration-policy"></a>Så här ställer du in förfalloprincipen

Som nämnts ovan är utgången inaktiverad som standard. En administratör måste aktivera förfalloprincipen och ange egenskaper för att den ska börja gälla. Om du vill aktivera det går till **Azure Active Directory (AAD)** > **Grupper** > **förfallodatum**. Här kan du ange standardgruppens livstid och ange hur långt i förväg du vill att det första och andra förfallodatumet ska gå till gruppägaren.

Gruppens livstid anges i dagar och kan ställas in på 180, 365 eller till ett anpassat värde som du anger. Det anpassade värdet måste vara minst 30 dagar.

Om gruppen inte har någon ägare går förfallodatumet till en angiven administratör.

Du kan ange principen för alla dina grupper, bara valda grupper eller inaktivera den helt genom att välja **Ingen**. Observera att du för närvarande inte kan ha olika principer för olika grupper.

![Skärmbild av förfalloinställningar för grupper i Azure Active Directory](../../media/azure-groups-expiration-settings.png)

## <a name="how-expiry-works-with-the-retention-policy"></a>Hur utfall fungerar med bevarandeprincipen

Om du har inställningslagringsprincip i Säkerhets- och efterlevnadscenter för grupper fungerar förfalloprincipen sömlöst med bevarandeprincip. När en grupp upphör att gälla behålls gruppens konversationer i e-postrutan och filer på gruppplatsen i behållarbehållaren för det specifika antal dagar som definierats i bevarandeprincipen. Användarna kommer inte att se gruppen, eller dess innehåll, efter utgångsdatum dock.

## <a name="how-and-when-a-group-owner-learns-if-their-groups-are-going-to-expire"></a>Hur och när en gruppägare får veta om deras grupper ska upphöra att gälla

Gruppägare meddelas endast via e-post. Om gruppen skapades via Planner, SharePoint eller någon annan app kommer förfalloanmälningarna alltid via e-post. Om gruppen skapades via Teams får gruppägaren ett meddelande om att förnya via aktivitetsavsnittet. Vi rekommenderar inte att du aktiverar förfallodatum för en grupp om gruppägaren inte har en giltig e-postadress.

30 dagar innan gruppen går ut får gruppägarna (eller de e-postadresser som du har angett för grupper som inte har en ägare) ett e-postmeddelande som gör det enkelt möjligt för dem att förnya gruppen. Om de inte förnyar det får de ett nytt e-postmeddelande för förnyelse 15 dagar före utgången. Om de fortfarande inte har förnyat det får de ytterligare ett e-postmeddelande dagen före utgången.

Om ingen av ägarna eller administratörerna av någon anledning förnyar gruppen innan den upphör att gälla kan administratören fortfarande återställa gruppen i upp till 30 dagar efter utgången. Mer information finns i: [Återställa en borttagen Office 365-grupp](https://support.office.com/article/restore-a-deleted-office-365-group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54).

## <a name="related-articles"></a>Relaterade artiklar

[Översikt över bevarandeprinciper](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)

[Tilldela en ny ägare till en överbliven grupp](https://support.office.com/article/86bb3db6-8857-45d1-95c8-f6d540e45732)

[Konfigurera Office 365-grupper svara](https://docs.microsoft.com/azure/active-directory/active-directory-groups-lifecycle-azure-portal)
