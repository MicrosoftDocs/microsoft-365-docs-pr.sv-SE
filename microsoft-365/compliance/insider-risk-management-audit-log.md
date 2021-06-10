---
title: Granskningslogg för Insider-riskhantering
description: Läs mer om granskningsloggen för Insider-riskhantering i Microsoft 365
keywords: Microsoft 365, hantering av insiderrisk, riskhantering, efterlevnad
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: bda9633ab37fd21fd66b3a8a53d4dd522e48ced1
ms.sourcegitcommit: 8b1bd7ca8cd81e4270f0c1e06d2b6ca81804a6aa
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/15/2021
ms.locfileid: "52161816"
---
# <a name="insider-risk-management-audit-log"></a>Granskningslogg för Insider-riskhantering

Med granskningsloggen för Insider-riskhantering kan du hålla dig informerad om de åtgärder som har vidtagits med insider-riskhanteringsfunktioner. Med den här loggen kan du oberoende granska de åtgärder som vidtas av användare som har tilldelats en eller flera rollgrupper för Insider-riskhantering. Granskningsloggen för Insider-riskhantering aktiveras automatiskt i organisationen och kan inte inaktiveras.

![Granskningslogg för Insider-riskhantering](../media/insider-risk-audit-log.png)

Granskningsloggen uppdateras automatiskt och omedelbart när övervakade aktiviteter äger rum och loggen behåller information om aktiviteten i 180 dagar (ungefär sex månader). Efter 180 dagar tas data för aktiviteten bort permanent från loggen.

Exempel på områden som ingår i aktivitetsövervakning:

- Principer
- Ärenden
- Varningar
- Inställningar
- Användare
- Meddelandemallar

Om du vill visa och exportera data från granskningsloggen måste användarna tilldelas rollgrupperna *Insider-riskhantering* eller *Insider-riskhanteringsgranskningar.* Mer information om rollgrupper i Insider-riskhantering finns i [Komma igång med insider-riskhantering steg 1: Aktivera behörigheter.](insider-risk-management-configure.md#step-1-enable-permissions-for-insider-risk-management)

>[!NOTE]
>Insider-granskningsloggen för riskhantering är inte kopplad till Microsoft 365, de är oberoende granskningssystem och samlar in information om separata aktiviteter. Om du inaktiverar Microsoft 365 påverkar inte aktivitetgranskning inom Insider-riskhantering.

## <a name="view-activity-in-the-insider-risk-audit-log"></a>Visa aktivitet i granskningsloggen för Insider-risker

Du kan visa övervakad funktionsaktivitet för Insider-riskhantering genom att gå till och välja länken granskningslogg för **Insider-risker** i det övre högra området på någon flik för Insider-riskhantering. Som standard visas följande information för Insider-riskhanteringsaktiviteter:

- **Aktivitet:** En beskrivning av en användares aktivitet i Insider-riskhanteringslösningen.
- **Kategori:** Området eller objektet där aktiviteten utfördes. Du ser till exempel Principer *som kategorin* när aktiviteter för principändring utfördes.
- **Aktivitet som utförs av:** Användarnamnet för användaren som utförde aktiviteten.
- **Datum:** Datum och tid då aktiviteten utfördes. Datum och tid är det lokala datum och den tid som gäller för din organisation.

Om du vill ha mer information om en loggad aktivitet väljer du aktiviteten för att visa fönstret med aktivitetsinformation. Det här fönstret innehåller ytterligare information om aktiviteten.

## <a name="columns-and-filtering"></a>Kolumner och filtrering

För att det ska vara enklare för granskare att granska loggad aktivitet stöds filtrering i **Insider-granskningsloggen för risker.** För grundläggande filtrering är kökolumner tillgängliga att lägga till i vyn för att ge olika pivoter på filer och meddelanden. Du kan filtrera aktiviteter efter **fälten Kategori, Datumintervall** **och** Aktivitet.

Om du vill lägga till eller ta bort kolumnrubriker för aktivitetskön använder du kontrollen **Anpassa** kolumner och väljer kolumnalternativ. De här kolumnerna mappas till vanliga villkor som stöds i **Insider-granskningsloggen** för risker och listas senare i den här artikeln.

## <a name="audit-log-export"></a>Granskningsloggexport

Användare som har tilldelats rollgrupperna *Insider-riskhantering* eller Insider-riskhanteringsgarna kan exportera all aktivitet i granskningsloggen till en .csv-fil (kommaavgränsade värden) genom att välja  **Exportera** på sidan Granskningslogg för **Insider-risk.** Beroende på aktiviteten kanske vissa fält för en aktivitet inte gäller för aktiviteten, och dessa fält visas som tomma i den exporterade filen.

Filen innehåller aktivitetsinformation för följande fält:

- **Aktivitet som utförs av:** Användarnamnet för den användare som ändrar ett objektvärde. Användare som anges här har tilldelats en eller flera av följande rollgrupper för [insider-riskhantering:](insider-risk-management-configure.md#step-1-enable-permissions-for-insider-risk-management) *Insider-riskhantering,* *Insider-riskhanteringsadministratörer,* Insider-riskhanteringsanalytiker, *Insider-riskhanteringsadministratörer.*  Varje rollgrupp har olika behörighetsnivåer för att hantera Insider-riskfunktioner.
- **Aktivitet:** Den aktivitet som ett objekt har tagits med. Värden *visas, tas bort, läggs till, redigerad princip, ärende, användare, avisering* *och Inställningar.*
- **Tillagt:** Objekt som lagts till under aktiviteten, till exempel användare, filtyper eller domäner.
- **Aviseringsvolym:** Nivån på aviseringsvolymen som definierats i inställningarna för Insider-riskhantering.
- **Belopp**: De anpassade indikatormängderna som valts för närvarande för en princip.
- **Tillgångs-ID:** Tillgångs-ID för den prioriterade fysiska tillgång som aktiviteten utfördes på.
- **Kategori:** Kategorin för objektet har ändrats. Värdena är *principer, ärenden, användare, aviseringar, Inställningar och* *meddelandemallar.*
- **Datum:** Datum och tid, som visas i organisationens lokala datum och tid.
- **Beskrivning**: Beskrivningen som användaren indata för objektet som ageras på (t.ex. en princip eller en prioritetsgrupp).
- **DLP-princip:** DLP-principen (Data Loss Prevention) som valts för att utlösa inkludering i en princip för insider-riskhantering.
- **Indikator:** Indikatorn i inställningarna för Insider-risker som aktiviteten utfördes på (t.ex. att lägga till eller ta bort en indikator).
- **Meddelandemall:** Meddelandemallen som aktiviteten utfördes på.
- **Antal dagar: Det** principaktiveringsfönster som definierats i inställningarna för Insider-risker.
- **Antal filer: Filvolymgränsen** som definierats i inställningarna för Insider-riskhantering.
- **Principmall**: Principmallen som indikatorerna agerade på hör till.
- **Föregående belopp:** Tidigare valda anpassade indikatormängder för en princip.
- **Prioritet för användargrupp:** Den prioritetsgrupp som aktiviteten utfördes i.
- **Borttaget:** Objekt som har tagits bort under aktiviteten, till exempel användare, filtyper eller domäner.
- **Avsändare**: Avsändarfältet i meddelandemallen som aktiviteten utfördes på.
- **Målprincip:** Principen som aktiviteten utfördes på (som att lägga till en användare till eller ta bort en användare från).
- **Brödtext i mall:** Meddelandetexten i meddelandemallen som aktiviteten utfördes på.
- **Mallämne:** Ämnesfältet i meddelandemallen som aktiviteten utfördes på.
- **Användare:** Användaren som aktiviteten utfördes på.
