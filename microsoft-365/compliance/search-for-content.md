---
title: Söka efter innehåll
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.assetid: df2d1e0f-b476-42c9-aade-4a260b24f193
description: Använd verktyget eDiscovery för innehållssökning i Säkerhets- och efterlevnadscenter för & för att snabbt hitta e-post i Exchange-postlådor, dokument på SharePoint-webbplatser och OneDrive-platser och snabbmeddelandekonversationer i Skype för företag.
ms.openlocfilehash: a70c234331d1329fb80f32fb81762391a862d487
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226065"
---
# <a name="search-for-content-using-the-content-search-tool"></a>Söka efter innehåll med hjälp av verktyget Innehållssökning

Använd verktyget Innehållssökning i Säkerhets- och efterlevnadscenter för & för att snabbt hitta e-post i Exchange-postlådor, dokument på SharePoint-webbplatser och OneDrive-platser och snabbmeddelandekonversationer i Skype för företag. Du kan använda verktyget för innehållssökning för att söka efter e-post, dokument och snabbmeddelandekonversationer i samarbetsverktyg som Microsoft Teams och Microsoft 365 Grupper.

## <a name="search-for-content"></a>Söka efter innehåll

Det första steget är att börja använda verktyget Innehållssökning för att välja innehållsplatser för att söka och konfigurera en nyckelordsfråga för att söka efter specifika objekt. Du kan också lämna frågan tom och returnera alla objekt på målplatserna.

- [Skapa och köra](content-search.md) en innehållssökning

- [Funktionsreferens] för innehållssökning (content-search-reference.md)

- [Skapa sökfrågor och använda villkor för](keyword-queries-and-search-conditions.md) att begränsa sökningen

- [Konfigurera filtrering av sökbehörigheter](permissions-filtering-for-content-search.md) så att en eDiscovery-hanterare bara kan söka i delmängd av postlådor eller webbplatser i organisationen

- [Köra en sökning i en ID-lista](csv-file-for-an-id-list-content-search.md) för att söka efter specifika e-postmeddelanden

- [Söka i molnbaserade postlådor](search-cloud-based-mailboxes-for-on-premises-users.md) efter lokala användare i Microsoft 365

- [Visa nyckelordsstatistik](view-keyword-statistics-for-content-search.md) för resultatet av en sökning och förfina sedan frågan om det behövs

- [Sök efter data från tredje](use-content-search-to-search-third-party-data-that-was-imported.md) part som organisationen har importerat till Microsoft 365

- [Massredigera](bulk-edit-content-searches.md) frågan och innehållsplatser för flera sökningar

- [Försök att försöka med en innehållssökning](retry-failed-content-search.md) igen för att lösa ett innehållsplatsfel

- [Behåll mottagare av hemlig kopia](/exchange/policy-and-compliance/holds/preserve-bcc-recipients-and-group-members) så att du kan söka efter dem

## <a name="perform-actions-on-content-you-find"></a>Utföra åtgärder på innehåll som du hittar

När du har kört en sökning och förfint den efter behov är nästa steg att göra något med resultatet som returneras av sökningen. Du kan exportera och ladda ned resultaten till din lokala dator eller vid e-postattacker på organisationen kan du ta bort resultatet av en sökning från användarnas postlådor.

- [Exportera resultatet av en innehållssökning och ladda](export-search-results.md) ned dem till din lokala dator

- [Söka efter och ta bort e-postmeddelanden,](search-for-and-delete-messages-in-your-organization.md) t.ex. meddelanden som innehåller virus, skadliga bifogade filer eller nätfiskemeddelanden

- [Exportera en rapport](export-a-content-search-report.md) om resultatet av en innehållssökning, utan att exportera de faktiska resultaten

## <a name="learn-more-about-content-search"></a>Läs mer om innehållssökning

Innehållssökning är enkelt att använda, men är också ett kraftfullt verktyg. Bakom kulisserna är det mycket igång. Ju mer du vet om den och förstår dess beteende och begränsningar, desto mer lyckad blir det att du använder den för organisationens behov av sökning och undersökning. Läs mer om:

- [Delvis indexerade objekt i Exchange och SharePoint](partially-indexed-items-in-content-search.md) samt hur du inkluderar eller exkluderar dem när du exporterar och laddar ned sökresultat

- [Undersök delvis indexerade objekt](investigating-partially-indexed-items-in-ediscovery.md) och fastställ din organisations exponering för dem

- [Begränsningar för verktyget Innehållssökning,](limits-for-content-search.md)till exempel det maximala antalet sökningar som du kan köra samtidigt och det maximala antalet innehållsplatser du kan ta med i en enda sökning

- [Uppskattade och faktiska sökresultat och](differences-between-estimated-and-actual-ediscovery-search-results.md) orsaker till varför det kan finnas skillnader mellan dem när du exporterar och laddar ned sökresultat

- [Avduplicering i sökresultat](de-duplication-in-ediscovery-search-results.md) som du kan aktivera när du exporterar e-postmeddelanden som är resultatet av en sökning

## <a name="use-scripts-for-advanced-scenarios"></a>Använda skript för avancerade scenarier

Ibland behöver du utföra mer avancerade, komplexa och återkommande innehållssökningsuppgifter. I dessa fall är det enklare och snabbt att använda PowerShell-kommandon i Säkerhets- & Kompatibilitetscenter. För att göra det enklare har vi skapat ett antal PowerShell-skript för säkerhets- och &-efterlevnadscenter som hjälper dig slutföra sökrelaterade uppgifter med komplext innehåll.

- [Söka i specifika postlådor och webbplatsmappar](use-content-search-for-targeted-collections.md) (kallas även *riktad samling) när du är säker på att de objekt som svarar på ett ärende finns i den mappen

- [Söka i postlådan OneDrive platsen](search-the-mailbox-and-onedrive-for-business-for-a-list-of-users.md) för en lista över användare

- [Skapa, rapportera om och ta bort flera sökningar för](create-report-on-and-delete-multiple-content-searches.md) att snabbt och effektivt identifiera och söka efter data

- [Klona en innehållssökning](clone-a-content-search.md) och jämför snabbt resultaten av olika nyckelordssökningsfrågor på samma innehållsplatser. eller använda skriptet för att spara tid genom att inte behöva ange ett stort antal innehållsplatser på nytt när du skapar en ny sökning