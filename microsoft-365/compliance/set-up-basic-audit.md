---
title: Konfigurera grundläggande granskning i Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-audit
- m365initiative-compliance
- m365solution-scenario
search.appverid:
- MOE150
- MET150
description: I den här artikeln beskrivs hur du ställer in Grundläggande granskning så att du kan börja söka efter granskningsaktiviteter som utförs av användare och administratörer i organisationen.
ms.openlocfilehash: 59b5c85003ef0e19f7d3dd7417f764f446244652
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52564835"
---
# <a name="set-up-basic-audit-in-microsoft-365"></a>Konfigurera grundläggande granskning i Microsoft 365

Med grundläggande granskning i Microsoft 365 kan du söka efter granskningsposter för aktiviteter som utförts Microsoft 365 olika tjänster av användare och administratörer. Eftersom Enkel granskning är aktiverat som standard för de flesta Microsoft 365- och Office 365-organisationer finns det bara några saker du behöver göra innan du och andra i organisationen kan söka i granskningsloggen.

I den här artikeln beskrivs följande steg för att konfigurera grundläggande granskning.

![Steg för att konfigurera grundläggande granskning](../media/BasicAuditingWorkflow.png)

De här stegen omfattar att säkerställa korrekt organisationsprenumerationer och användarlicensiering som krävs för att generera och bevara granskningsposter och tilldela behörigheter till gruppmedlemmar i dina säkerhetsåtgärder, IT-, efterlevnads- och juridiska grupper så att du kan söka i granskningsloggen.

Mer information finns i [Grundläggande granskning i Microsoft 365](auditing-solutions-overview.md#basic-audit).

## <a name="step-1-verify-organization-subscription-and-user-licensing"></a>Steg 1: Kontrollera organisationens prenumeration och användarlicensiering

Licensiering för grundläggande granskning kräver en lämplig organisationsprenumeration som ger åtkomst till verktyget för granskningsloggsökning och licensiering per användare som krävs för att logga och behålla granskningsposter.

När en granskad aktivitet utförs av en användare eller administratör skapas en granskningspost som lagras i granskningsloggen för organisationen. I Grundläggande granskning behålls och är granskningsposter sökbara i granskningsloggen i 90 dagar.

En lista över prenumerations- och licenskrav för grundläggande granskning finns i [Granskningslösningar i Microsoft 365](auditing-solutions-overview.md#licensing-requirements).

## <a name="step-2-assign-permissions-to-search-the-audit-log"></a>Steg 2: Tilldela behörigheter för att söka i granskningsloggen

Administratörer och medlemmar i undersökningsgrupper måste ha tilldelats rollen View-Only granskningsloggar eller granskningsloggar i Exchange Online att söka i granskningsloggen. Som standard tilldelas de här rollerna till rollgrupperna Efterlevnadshantering och Organisationshantering på sidan **Behörigheter** i administrationscentret för Exchange. Globala administratörer i Office 365 och Microsoft 365 läggs automatiskt till som medlemmar i rollgruppen Organisationshantering i Exchange Online. Om du vill ge en användare möjlighet att söka i granskningsloggen med den lägsta graden av behörighet kan du skapa en anpassad rollgrupp i Exchange Online, lägga till rollen Skrivskyddade granskningsloggar eller Granskningsloggar och sedan lägga till användaren som medlem i den nya rollgruppen. Mer information finns i [Hantera rollgrupper i Exchange Online](/Exchange/permissions-exo/role-groups).

Följande skärmbild visar de två granskningsrelaterade rollerna som tilldelats rollgruppen Organisationshantering i Exchange administrationscenter.

![Granska roller som tilldelats rollgrupp i Exchange Online](../media/EACAuditRoles.png)

## <a name="step-3-search-the-audit-log"></a>Steg 3: Söka i granskningsloggen

Nu är du redo att söka i granskningsloggen i Microsoft 365 efterlevnadscenter.

1. Gå till <https://compliance.microsoft.com> och logga in med ett konto som har tilldelats lämpliga granskningsbehörigheter.

2. I det vänstra navigeringsfönstret i Microsoft 365, klickar du på **Visa alla och** sedan på **Granska.**

3. På **sidan Granskning** konfigurerar du sökningen enligt följande villkor på **fliken** Sök. 

   ![Konfigurationsinställningar för granskningsloggsökning](../media/AuditLogSearchToolMCCCallouts.png)

   1. **Datum- och tidsintervall**. Välj ett datum- och tidsintervall för att visa händelser som inträffat under perioden. Datum och tid visas i lokal tid. De senaste sju dagarna är valda som standard.
  
   2. **Aktiviteter**. Välj de aktiviteter du vill söka efter. Använd sökrutan för att söka efter aktiviteter som du vill lägga till i listan. En delvis lista över granskade aktiviteter finns i [Granskade aktiviteter.](search-the-audit-log-in-security-and-compliance.md#audited-activities) Lämna rutan tom för att returnera poster för alla granskade aktiviteter.
  
   3. **Användare.**  Klicka i den här rutan och börja skriva namnet på de användare som du vill visa sökresultat för. I resultatlistan visas granskningsloggposterna för de markerade aktiviteter som utförts av de användare du väljer i den här rutan. Lämna rutan tom för att returnera poster för alla användare (och tjänstkonton) i organisationen.
  
   4. **Fil, mapp eller webbplats**. Skriv en del av eller hela fil- eller mappnamnet för att söka efter aktivitet relaterad till filen i mappen som innehåller det angivna nyckelordet. Du kan också ange en URL-adress till en fil eller mapp. Om du använder URL-adressen till en fil eller mapp ska du se till att skriva den fullständiga URL-sökvägen. Om du skriver en del av URL:en får du inte skriva några specialtecken eller blanksteg. Lämna rutan tom för att returnera poster för alla filer eller mappar i organisationen.

4. Klicka **på Sök** för att köra sökningen.

En ny sida visas som visar att granskningsloggsökningen körs. När sökningen är klar visas granskningsposter på sidan. Klicka på en post för att visa en utfällsida med detaljerade egenskaper.

Mer detaljerade anvisningar finns i Söka [i granskningsloggen i efterlevnadscentret.](search-the-audit-log-in-security-and-compliance.md)
