---
title: Planera styrning av organisation och livscykel för Microsoft 365-grupper och Microsoft Teams
ms.reviewer: arvaradh
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Mer information om alternativ för livscykelstyrning för samarbetsverktyg i Microsoft 365
ms.openlocfilehash: ff3a3a60ce49c423410b51dc6fee2137ebf8952a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907934"
---
# <a name="plan-organization-and-lifecycle-governance-for-microsoft-365-groups-and-microsoft-teams"></a>Planera styrning av organisation och livscykel för Microsoft 365-grupper och Microsoft Teams

Microsoft 365-grupper har en omfattande uppsättning verktyg för att implementera de hanteringsfunktioner som din organisation kräver. 

I följande avsnitt beskrivs funktionerna, rekommendationerna för metodtips och vägledning för att ställa rätt frågor för att avgöra kraven för styrning och hur du uppfyller dem.

## <a name="control-who-can-create-microsoft-365-groups"></a>Styra vilka som kan skapa Microsoft 365-grupper

Grupper kan skapas av slutanvändare från flera ändpunkter, inklusive Outlook, SharePoint, Teams och andra miljöer.

![image desc](../media/04.png)

Vi rekommenderar självbetjäning för att ge gruppägare möjlighet och hjälpa användarna att få jobbet gjort enklare. Att begränsa skapandet av grupper och team kan leda till långsammare produktivitet för användare eftersom många Microsoft 365-tjänster kräver att grupper skapas för att tjänsten ska fungera.

Tänk på följande styrningsalternativ för att skapa grupper:

- Om du vill begränsa gruppsnålning [använder du förfalloprinciper](microsoft-365-groups-expiration-policy.md) för grupper för att automatiskt ta bort grupper som inte används.
- Begränsa skapandet av grupper till medlemmar [i en säkerhetsgrupp med dynamiskt](/azure/active-directory/users-groups-roles/groups-create-rule) medlemskap, t.ex. alla heltidsanställda.
- Begränsa skapandet av grupper till en säkerhetsgrupp och kräver att användarna slutför utbildning i organisationens principer för gruppanvändning för att bli medlemmar i säkerhetsgruppen.

Om du vill begränsa vem som kan skapa grupper kan du gå till Hantera vem som kan skapa [Microsoft 365-grupper](manage-creation-of-groups.md) för information om hur du konfigurerar detta.

## <a name="group-delete-restore-and-archiving"></a>Gruppera borttagning, återställning och arkivering

När en Microsoft 365-grupp tas bort behålls den som standard i 30 dagar. Den här 30-dagarsperioden kallas "mjuk borttagning" eftersom du fortfarande kan återställa gruppen. Efter 30 dagar tas gruppen och det tillhörande innehållet bort permanent och kan inte återställas.

Om du har kvarhållningsprinciper för att behålla chatt, filer eller e-post, bevaras de objekten när gruppen har tagits bort. Mer [information finns i Läs mer om](../compliance/retention.md) bevarandeprinciper.

Information om hur du tar bort en grupp men bevarar innehållet från en eller flera av de gruppanslutna tjänsterna finns i Arkivera grupper, grupper och [Yammer.](end-life-cycle-groups-teams-sites-yammer.md)

## <a name="group-naming-policy"></a>Gruppnamnprincip

Med namngivningsprincipen för grupper kan du styra grupperna på två sätt:

- En prefix-/suffixnamnsprincip kan användas för att framtvinga fasta strängar eller Azure AD-attribut i början eller slutet av ett gruppnamn och dess tillhörande e-postadress. På så sätt kan du säkerställa att exempelvis avdelningsnamn eller regioner i gruppnamn tas med.
- En princip för blockerade ord kan säkerställa att vissa ord, till exempel namnen på chefer, inte används i gruppnamn.

Namnprinciper tillämpas när grupper skapas från någon av de gruppanslutna tjänsterna.

Information om hur du använder namnprinciper för grupper finns i Namngivningsprinciper för [Microsoft 365 Grupper.](groups-naming-policy.md)

## <a name="group-expiration-policy"></a>Förfalloprincip för grupp

Du kan ange en förfalloperiod så tas alla grupper som når slutet av perioden bort, och som inte förnyas. Förfallotiden börjar när gruppen skapas eller det datum då den senast förnyades.

När du ställer in grupper så att de upphör att gälla:
- Ägare av gruppen meddelas att förnya gruppen när utgångsdatumet närmar sig.
- Aktiva grupper förnyas automatiskt.
- Alla grupper som inte har förnyats tas bort.
- Alla grupper som tas bort kan återställas inom 30 dagar av gruppägarna eller administratören.

Förfalloprinciper är ett bra sätt att begränsa gruppsnålning genom att se till att grupper som inte längre används tas bort. Information om hur du skapar en förfalloprincip för grupper finns i Förfalloprincip [för Microsoft 365-grupper.](microsoft-365-groups-expiration-policy.md)

## <a name="related-topics"></a>Relaterade ämnen

[Planering av samarbetsstyrning steg för steg](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Skapa din plan för samarbetesstyrning](collaboration-governance-first.md)