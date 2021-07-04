---
title: Microsoft 365-granskningslösningar
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- m365-security-compliance
- m365solution-audit
- m365initiative-compliance
- m365solution-overview
search.appverid:
- MOE150
- MET150
description: Lär dig att granska användar- och administratörsaktiviteterna i din Microsoft 365-organisation.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d4a753a640b98125bc6ad02bd6043f28336e29b7
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256765"
---
# <a name="auditing-solutions-in-microsoft-365"></a>Granskningslösningar i Microsoft 365

Granskningslösningar i Microsoft 365 tillhandahåller en integrerad lösning som hjälper organisationer att effektivt svara på säkerhetshändelser, undersökningar, interna undersökningar och efterlevnadsåtaganden. Tusentals användar- och administratörsåtgärder som utförs i dussintals Microsoft 365-tjänster och -lösningar spelas i, registreras och behålls i organisationens enhetliga granskningslogg. Granskningsposterna för de här händelserna är sökbara i säkerhets ops, IT-administratörer, insider-riskteam samt efterlevnad och juridiska krav i organisationen. Den här funktionen ger insyn i de aktiviteter som utförs i Microsoft 365-organisationen.

## <a name="microsoft-365-auditing-solutions"></a>Microsoft 365-granskningslösningar

I Microsoft 365 finns två granskningslösningar: Grundläggande granskning och Avancerad granskning.

![Viktiga funktioner för Grundläggande granskning och Avancerad granskning](..\media\AuditingSolutionsComparison.png)

### <a name="basic-audit"></a>Grundläggande granskning

Med Grundläggande granskning kan du logga och söka efter granskade aktiviteter och utföra dina granskningar, IT-, efterlevnads- och juridiska undersökningar.

- **Aktiverad som standard**. Grundläggande granskning är aktiverat som standard för alla organisationer med rätt abonnemang. Det innebär att poster för granskade aktiviteter förs in och är sökbara. Den enda konfiguration som krävs är att tilldela nödvändiga behörigheter för att få åtkomst till granskningsloggens sökverktyg (och motsvarande cmdlet) och kontrollera att användaren har tilldelats rätt licens för avancerade granskningsfunktioner.
- **Tusentals sökbara granskningshändelser**. Du kan söka efter en rad granskade aktiviteter som inträffar i de flesta Microsoft 365-tjänsterna i din organisation. En del av en lista över de aktiviteter du kan söka efter finns i [Granskade aktiviteter](search-the-audit-log-in-security-and-compliance.md#audited-activities). En lista över tjänster och funktioner som stöder granskade aktiviteter finns i [Granskningslogg record type](/office/office-365-management-api/office-365-management-activity-api-schema#auditlogrecordtype).
- **Verktyg för granskningssökning i Microsoft 365 Efterlevnadscenter**. Använd verktyget Sökning i granskningslogg i Microsoft 365 Efterlevnadscenter för att söka efter granskningsposter. Du kan söka efter specifika aktiviteter, efter aktiviteter som utförts av specifika användare och aktiviteter som inträffat med ett datumintervall. Här är en skärmbild av verktyget för granskningssökning i efterlevnadscentret.

   ![Verktyg för Sökning i granskningslogg i Microsoft 365 Efterlevnadscenter.](../media/AuditLogSearchToolMCC.png)

- **Search-UnifiedAuditLog cmdlet**. Du kan också använda cmdleten **Search-UnifiedAuditLog** i Exchange Online PowerShell (den underliggande cmdleten för sökverktyget) för att söka efter granskningshändelser eller använda i ett skript. Mer information finns i:

  - [Search-UnifiedAuditLog cmdlet referens](/powershell/module/exchange/search-unifiedauditlog)
  - [Använd ett PowerShell-skript för att söka i granskningsloggen](audit-log-search-script.md)

- **Exportera granskningsposter till en CSV-**. När du har kört verktyget Sökning i granskningslogg* i efterlevnadscentret kan du exportera granskningsposterna som returneras av sökningen till en CSV-fil. Då kan du använda Microsoft Excel för att sortera och filtrera på olika egenskaper för granskningsposterna. Du kan också använda transformeringsfunktionen i Excel Power Query för att dela upp varje egenskap i AuditData JSON-objektet i en egen kolumn. På så sätt kan du visa och jämföra liknande data för olika händelser. Mer information finns i [Exportera, konfigurera och visa granskningsloggposter](export-view-audit-log-records.md).

- **Åtkomst till granskningsloggar via Office 365 Management Activity-API**. En tredje metod för att komma åt och hämta granskningsposter är att använda Office 365 Management Activity API. Det innebär att organisationen kan behålla granskningsdata under längre perioder än standardvärdena på 90 dagar och importera sina granskningsdata till en SIEM-lösning. Mer information finns i [referensen för Office 365 Management Activity-API](/office/office-365-management-api/office-365-management-activity-api-reference).

- **90 dagar-kvarhållning för granskningsloggar**. När en granskad aktivitet utförs av en användare eller administratör skapas en granskningspost som lagras i granskningsloggen för organisationen. I Grundläggande granskning behålls poster i 90 dagar, vilket innebär att du kan söka efter aktiviteter som inträffat under de senaste tre månaderna.

### <a name="advanced-audit"></a>Avancerad granskning

Avancerad granskning bygger på funktionerna i Grundläggande granskning genom att tillhandahålla kvarhållningsprinciper för granskningsloggar, längre kvarhållning av granskningsposter, viktiga händelser med hög värde och högre bandbreddsåtkomst till Office 365 Management Activity-API.

- **Kvarhållningsprinciper för granskningsloggar**. Du kan skapa anpassade kvarhållningsprinciper för granskningsloggar om du vill bevara andra granskningsposter under en längre period upp till ett år (och upp till tio år för användare med obligatorisk tilläggslicens). Du kan skapa en princip om du vill behålla granskningsposter baserat på tjänsten där de granskade aktiviteterna inträffar, specifika granskade aktiviteter eller användaren som utför en granskad aktivitet.

- **Längre kvarhållning av granskningsposter**. Granskningsposter för Exchange, SharePoint och Azure Active Directory bevaras som standard i ett år. Granskningsposter för alla andra aktiviteter behålls som standard i 90 dagar. Du kan också använda kvarhållningsprinciper för granskningsloggar för att konfigurera längre kvarhållningsperioder.

- **Avgörande händelser med högt värde.**. Granskningsposter för avgörande händelser ka hjälpa organisationer att utföra tekniska undersökningar och efterlevnadsundersökningar genom att ge synlighet till viktiga händelser som när e-postobjekt har använts, besvarats och vidarebefordrats eller när och vad en användare har sökt efter i Exchange Online och SharePoint Online. De här viktiga händelserna kan hjälpa dig att undersöka möjliga intrång och avgöra intrångets omfattning.

- **Högre bandbredd till Office 365 Management Activity-API**. Avancerad granskning ger organisationer mer bandbredd för åtkomst till granskningsloggar via Office 365 Management Activity API. Även om alla organisationer (som har Grundläggande granskning eller Avancerad granskning) till en början har tilldelats en baslinje med 2 000 förfrågningar per minut, ökar den här gränsen dynamiskt beroende på antalet användare i organisationen och deras licensprenumeration. Det leder till att organisationer med Avancerad granskning får två gånger så mycket bandbredd som organisationer med Grundläggande granskning.

Mer information om avancerade granskningsfunktioner finns i [Avancerad granskning i Microsoft 365](advanced-audit.md).

## <a name="comparison-of-key-capabilities"></a>Jämförelse av viktiga funktioner

I följande tabell jämförs de viktigaste funktionerna i Grundläggande granskning och Avancerad granskning. Alla grundläggande granskningsfunktioner ingår i Avancerad granskning.

|Funktion|Grundläggande granskning|Avancerad granskning|
|:------|:-------------|:-------------|
|Aktiverad som standard|![Stöds](../media/check-mark.png)|![Stöds](../media/check-mark.png)|
|Tusentals sökbara granskningshändelser|![Stöds](../media/check-mark.png)|![Stöds](../media/check-mark.png)|
|Verktyg för granskningssökning i Microsoft 365 Efterlevnadscenter |![Stöds](../media/check-mark.png)|![Stöds](../media/check-mark.png)|
|Search-UnifiedAuditLog cmdlet|![Stöds](../media/check-mark.png)|![Stöds](../media/check-mark.png)|
|Exportera granskningsposter till en CSV-fil|![Stöds](../media/check-mark.png)|![Stöds](../media/check-mark.png)|
|Åtkomst till granskningsloggar via Office 365 Management Activity-API <sup>1</sup>|![Stöds](../media/check-mark.png)|![Stöds](../media/check-mark.png)</sup>|
|90 dagar-kvarhållning för granskningsloggar|![Stöds](../media/check-mark.png)|![Stöds](../media/check-mark.png)|
|1 år-kvarhållning för granskningsloggar||![Stöds](../media/check-mark.png)|
|10 år-kvarhållning för granskningsloggar <sup>2</sup>||![Stöds](../media/check-mark.png)|
|Kvarhållningsprinciper för granskningsloggar||![Stöds](../media/check-mark.png)|
|Avgörande händelser med högt värde||![Stöds](../media/check-mark.png)|
||||
> [!NOTE]
> <sup>1</sup> Avancerad granskning ger högre bandbreddsåtkomst till Office 365 Management Activity API, som ger snabbare åtkomst till granskningsdata.<br/><sup>2</sup> Utöver den licensiering som krävs för avancerad granskning (som beskrivs i nästa avsnitt) måste en användare tilldelas en licens för 10 års granskningslogglagring för att behålla sina granskningsposter i 10 år.

## <a name="licensing-requirements"></a>Licensieringskrav

I följande avsnitt identifieras licenseringskraven för Grundläggande granskning och Avancerad granskning. Grundläggande granskningsfunktioner ingår i Avancerad granskning.

### <a name="basic-audit"></a>Grundläggande granskning

- Microsoft 365 Enterprise E3-abonnemang
- Microsoft 365 Business Premium
- Microsoft 365 Education A3-abonnemang
- Microsoft 365 för myndigheter G3--abonnemang
- Microsoft 365 för myndigheter G1--abonnemang
- Office 365 Enterprise E3--abonnemang
- Office 365 Enterprise E1--abonnemang
- Office 365 Education A1-abonnemang
- Office 365 Education A3-abonnemang

### <a name="advanced-audit"></a>Avancerad granskning

- Microsoft 365 Enterprise E5-abonnemang
- Microsoft 365 Enterprise E3-abonnemang + Microsoft 365 E5 Compliance-tillägg.
- Microsoft 365 Enterprise E3-abonnemang + Microsoft 365 E5 eDiscovery and Audit-tillägg.
- Microsoft 365 Education A5-abonnemang
- Microsoft 365 Education A3-abonnemang + Microsoft 365 A5 Compliance-tillägg.
- Microsoft 365 Education A3-abonnemang + Microsoft 365 A5 eDiscovery and Audit-tillägg.
- Microsoft 365 för myndigheter G5--abonnemang
- Microsoft 365 för myndigheter G5-abonnemang + Microsoft 365 G5 Compliance-tillägg.
- Microsoft 365 för myndigheter G5-abonnemang + Microsoft 365 G5 eDiscovery and Audit-tillägg.
- Office 365 Enterprise E5-abonnemang
- Office 365 Education A5-abonnemang
- Office 365 Enterprise, E3-abonnemang + Office 365 Advanced Compliance-tillägg (inte längre tillgängligt för nya abonnemang)

## <a name="set-up-microsoft-365-auditing-solutions"></a>Konfigurera Microsoft 365-granskningslösningar

Läs följande riktlinjer för konfiguration för att komma igång med granskningslösningarna i Microsoft 365.

### <a name="set-up-basic-audit"></a>Konfigurera Grundläggande granskning

Det första steget är att konfigurera Grundläggande granskning och sedan börja köra granskningsloggsökningar.

![Arbetsflöde för att konfigurera Avancerad granskning för användare](../media/BasicAuditingWorkflow.png)

1. Kontrollera att organisationen har ett abonnemang som har stöd för Grundläggande granskning och, om tillämpligt, ett abonnemang som har stöd för Avancerad granskning.

2. Tilldela behörigheter i Exchange Online till personer i organisationen som använder verktyget för granskningsloggsökning i Microsoft 365 Efterlevnadscenter eller använd cmdleten **Search-UnifiedAuditLog**. Mer specifikt måste användare ha tilldelats rollen Skrivskyddade granskningsloggar eller Granskningsloggar i Exchange Online.

3. Söka i granskningsloggen. När du har slutfört steg 1 och steg 2 kan användare i organisationen använda verktyget för granskningsloggsökning (eller motsvarande cmdlet) för att söka efter granskade aktiviteter.

Se [Konfigurera Grundläggande granskning](set-up-basic-audit.md) för mer detaljerade instruktioner.

### <a name="set-up-advanced-audit"></a>Konfigurera Avancerad granskning

Om organisationen har ett abonnemang som har stöd för avancerad granskning utför du stegen nedan för att konfigurera och använda de ytterligare funktionerna i Avancerad granskning.

![Arbetsflöde för att konfigurera Avancerad granskning för användare](../media/AdvancedAuditWorkflow.png)

1. Konfigurera Avancerad granskning för användare. Det här steget består av följande uppgifter:

   - Verifiera att användarna har tilldelats rätt licens eller tilläggslicens för Avancerad granskning.
  
   - Appen/tjänstplanen Advanced Auditing måste vara aktiverad för dessa användare.
  
   - Aktivera granskning av viktiga händelser och sedan aktivera app-/tjänstplanen för avancerad granskning för dessa användare.

2. Aktivera viktiga händelser som ska loggas när användare utför sökningar i Exchange Online och SharePoint Online.

3. Konfigurera kvarhållningsprinciper för granskningsloggar. Utöver standardprincipen som behåller granskningsposter för Exchange, SharePoint och Azure AD i ett år kan du skapa ytterligare kvarhållningsprinciper för granskningsloggar så att de uppfyller kraven för organisationens säkerhetsåtgärder, IT- och efterlevnadsgrupper.

4. Sök efter viktiga händelser och andra aktiviteter när du genomför undersökningar. När du har slutfört steg 1 och steg 2 kan du söka i granskningsloggen efter viktiga händelser och andra aktiviteter under undersökningar av nedsatt säkerhet och andra typer av säkerhets- eller efterlevnadsundersökningar.

Se [Konfigurera Avancerad granskning](set-up-advanced-audit.md) för mer detaljerade instruktioner.

## <a name="training"></a>Utbildning

Genom att utbilda teamet, IT-administratörer och efterlevnadsteamet i grunderna för Grundläggande granskning och Avancerad granskning kan organisationen komma igång snabbare med granskning, med hjälp av undersökningar. Microsoft 365 innehåller följande resurs som hjälper användarna i organisationen att komma igång med granskning: [Beskriv eDiscovery- och granskningsfunktionerna i Microsoft 365](/learn/modules/describe-ediscovery-capabilities-of-microsoft-365).
