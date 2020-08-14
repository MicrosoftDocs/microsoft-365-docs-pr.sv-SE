---
title: Planera organisation och livscykler för Microsoft 365-grupper och Microsoft Teams
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
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Lean-alternativ för hantering av livs cykeln för samarbets verktyg i Microsoft 365
ms.openlocfilehash: 2a2f14bf439ec69e4609d22783fb14d1d5cb8e70
ms.sourcegitcommit: 66f1f430b3dcae5f46cb362a32d6fb7da4cff5c1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662857"
---
# <a name="plan-organization-and-lifecycle-governance-for-microsoft-365-groups-and-microsoft-teams"></a>Planera organisation och livscykler för Microsoft 365-grupper och Microsoft Teams

Microsoft 365-grupper har många verktyg för att implementera de styrnings funktioner som din organisation behöver. 

I följande avsnitt beskrivs funktionerna, rekommenderar de bästa metoderna och ger vägledning för att ställa rätt frågor för att fastställa kraven för styrning och hur de ska mötas.

## <a name="control-who-can-create-microsoft-365-groups"></a>Kontrol lera vilka som kan skapa Microsoft 365-grupper

Grupper kan skapas av slutanvändare från flera slut punkter inklusive Outlook, SharePoint, team och andra miljöer.

![bild DESC](../media/04.png)

Vi rekommenderar starkt att du använder sig själv för att stärka grupp ägarna och hjälpa användare att få jobbet gjort lättare. Om du begränsar grupp-och grupp skapande kan användarna bli långsamma eftersom många Microsoft 365-tjänster kräver att grupper skapas för att tjänsten ska fungera.

Överväg följande styr alternativ för att skapa grupper:

- Om du vill begränsa grupp sprawl kan du använda [grupper för förfallo principer](microsoft-365-groups-expiration-policy.md) för att automatiskt ta bort grupper som inte används.
- Begränsa grupp skapande till medlemmar i en [säkerhets grupp med dynamiskt medlemskap](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule) som innehåller, till exempel, alla heltids anställda.
- Begränsa grupp skapande till en säkerhets grupp och Kräv att användare ska kunna slutföra utbildning i organisationens principer för grup användning för att bli medlemmar i säkerhets gruppen.

Om du vill begränsa vem som kan skapa grupper läser du [Hantera vilka som kan skapa Microsoft 365-grupper](manage-creation-of-groups.md) för information om hur du konfigurerar detta.

## <a name="group-delete-restore-and-archiving"></a>Grupp borttagning, återställning och arkivering

När en Microsoft 365-grupp tas bort sparas den som standard i 30 dagar. Den här 30-dagarsperioden kallas "mjuk borttagning" eftersom du fortfarande kan återställa gruppen. Efter 30 dagar tas gruppen och det tillhörande innehållet bort permanent och kan inte återställas.

Om du har bevarande principer för att behålla chatt, filer eller e-post bevaras dessa objekt efter att gruppen har tagits bort. Läs [mer om bevarande principer](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) .

Om du vill ta bort en grupp men behålla innehållet från en eller flera av de gruppanslutna tjänsterna läser du [arkivera grupper, team och Yammer](end-life-cycle-groups-teams-sites-yammer.md) efter information.

## <a name="group-naming-policy"></a>Namn princip för grupper

En namn princip för grupper kan hjälpa dig att styra grupper på två sätt:

- En princip för prefix/namnsuffix kan användas för att tvinga fasta strängar eller Azure AD-attribut i början eller slutet av ett grupp namn och dess associerade e-postadress. Genom att göra detta kan du se till exempel avdelnings namn eller områden i grupp namn.
- En princip för blockerade ord kan säkerställa att vissa ord, till exempel namn på chefer, inte används i grupp namn.

Namngivnings principer tillämpas när grupper skapas från någon av de gruppanslutna tjänsterna.

Om du bestämmer dig för att använda namngivnings principer för grupper kan du läsa mer i [Microsoft 365 grupper för namngivnings principer](groups-naming-policy.md).

## <a name="group-expiration-policy"></a>Policy för giltighets tid för grupp

Du kan ange en förfallo period och alla grupper som når slutet av perioden och som inte förnyas, tas bort. Utgångs perioden börjar när gruppen skapas, eller vid det datum då den senast förnyades.

När du har ställt in grupper som förfaller:
- Ägarna till gruppen meddelas om att förnya gruppen efter att ha gått ut nära.
- Aktiva grupper förnyas automatiskt.
- Alla grupper som inte är förnyade raderas.
- Alla grupper som tas bort kan återställas inom 30 dagar av grupp ägarna eller administratören.

Principer för förfallo dag är ett bra sätt att begränsa gruppens sprawl genom att se till att grupper som inte längre används tas bort. Om du vill skapa en giltighets princip för en grupp kan du läsa [Microsoft 365-gruppens förfallo princip](microsoft-365-groups-expiration-policy.md).
