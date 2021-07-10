---
title: Samla in information om eDiscovery-diagnostik
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Lär dig hur du samlar in eDiscovery-diagnostikinformation för ett Microsoft Support-ärende.
ms.openlocfilehash: b2441e0b7af8a82e24a8acca9e000e954e1c8964
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362600"
---
# <a name="collect-ediscovery-diagnostic-information"></a>Samla in information om eDiscovery-diagnostik

Ibland behöver Microsofts supporttekniker specifik information om ditt problem när du öppnar ett supportfall som är relaterat till Core eDiscovery eller Advanced eDiscovery. Den här artikeln innehåller vägledning om hur du samlar in diagnostikinformation som supporttekniker kan undersöka och lösa problem. Vanligtvis behöver du inte samla in den här informationen förrän du ombeds att göra det av en Microsoft-supporttekniker.

> [!IMPORTANT]
> Utdata från cmdlets och diagnostisk information som beskrivs i den här artikeln kan innehålla känslig information om rättstvister eller interna undersökningar i organisationen. Innan du skickar rådata för diagnostikinformation till Microsoft Support bör du granska informationen och göra om känslig information (till exempel namn eller annan information om parter i en rättstvist eller undersökning) genom att ersätta den med `XXXXXXX` . Om du använder den här metoden anger det också för Microsoft Support-teknikern att informationen har omactats.

## <a name="collect-diagnostic-information-for-core-ediscovery"></a>Samla in diagnostikinformation för bas-eDiscovery

Insamling av diagnostikinformation för Core eDiscovery är cmdlet-baserad, så du måste använda Security & Compliance Center PowerShell. Följande PowerShell-exempel kör cmdlets och sparar sedan utdata i en viss textfil. I de flesta supportärenden behöver du bara köra något av dessa kommandon.

Om du vill köra följande cmdlets [ansluter du till </span> Säkerhets- & Compliance Center PowerShell.](/powershell/exchange/connect-to-scc-powershell) När du är ansluten kör du ett eller flera av följande kommandon och ersätter platshållarna med de faktiska objektnamnen.

När du har granskat den genererade textfilen och omformaterat känslig information skickar du den till Microsoft Support-tekniker som arbetar på ditt ärende.

> [!NOTE]
> Du kan även köra kommandona i det här avsnittet för  att samla in diagnostikinformation för de sökningar och exporter som visas på sidan Innehållssökning i Microsoft 365 Efterlevnadscenter.

### <a name="collect-information-about-searches"></a>Samla in information om sökningar

Följande kommando samlar in information som är användbar när du undersöker problem med en innehållssökning eller en sökning som är kopplad till ett Grundläggande eDiscovery-ärende.

```powershell
Get-ComplianceSearch "<Search name>" | FL > "ComplianceSearch.txt"
```

### <a name="collect-information-about-search-actions"></a>Samla in information om sökåtgärder

Följande kommando samlar in information för att undersöka problem med att förhandsgranska, exportera eller rensa resultatet av en innehållssökning eller en sökning kopplad till ett Core eDiscovery-ärende. Du kan identifiera namnet på sökåtgärden genom att klicka på en export som visas på **fliken Exporter.** Identifiera namnen på förhandsgransknings- och rensningsåtgärderna genom att köra **cmdlet:en Get-ComplianceSearchAction** för att visa en lista över alla åtgärder. Formatet för sökåtgärdsnamnet är uppbyggt av att lägga till `_Preview` , eller efter namnet på motsvarande `_Export` `_Purge` sökning.

```powershell
Get-ComplianceSearchAction "<Search action name>" | FL > "ComplianceSearchAction.txt"
```

### <a name="collect-information-about-ediscovery-holds"></a>Samla in information om eDiscovery-kvarhåller

Om ett undantag för eDiscovery som är kopplat till ett Core eDiscovery-ärende inte fungerar som förväntat, kör du följande kommando för att samla in information om principen för undantag och tillhörande regel för undantag för eDiscovery. Principen *Case hold name* i följande kommando är samma som namnet på eDiscovery-holden. Du kan identifiera det här namnet på **flikarna Som** innehåller i Core eDiscovery-ärendet.

```powershell
Get-CaseHoldPolicy "<Case hold policy name>" | %{"--CaseHoldPolicy--";$_|FL;"--CaseHoldRule--";Get-CaseHoldRule -Policy $_.Name | FL} > "eDiscoveryCaseHold.txt"
```

### <a name="collect-all-case-information"></a>Samla in all ärendeinformation

Ibland står det inte vilken information som krävs av Microsoft Support för att undersöka problemet. I det här fallet kan du samla in all diagnostikinformation för ett grundläggande e-dataidentifieringsfall. Namnet *på core-eDiscovery-ärendet* i följande kommando är samma som namnet på ett ärende som visas på sidan **Core eDiscovery** i Microsoft 365 Efterlevnadscenter.

```powershell
Get-ComplianceCase "<Core eDiscovery case name>"| %{$_|fl;"`t==Searches==";Get-ComplianceSearch -Case $_.Name | FL;"`t==Search Actions==";Get-ComplianceSearchAction -Case $_.Name |FL;"`t==Holds==";Get-CaseHoldPolicy -Case $_.Name | %{$_|FL;"`t`t ==$($_.Name) Rules==";Get-CaseHoldRule -Policy $_.Name | FL}} > "eDiscoveryCase.txt"
```

## <a name="collect-diagnostic-information-for-advanced-ediscovery"></a>Samla in diagnostikinformation för Advanced eDiscovery

På **Inställningar** i ett Advanced eDiscovery kan du snabbt kopiera diagnostisk information för ärendet. Diagnostikinformationen sparas i Urklipp så att du kan klistra in den i en textfil och skicka den till Microsoft Support.

1. Gå till [https://compliance.microsoft.com](https://compliance.microsoft.com/) och klicka sedan på Visa > **eDiscovery-> Avancerat.**

2. Markera ett ärende och klicka sedan **på Inställningar** ärendet.

3. Klicka **på Markera under** **Ärendeinformation.**

4. På den utfällade sidan klickar **du på Kopiera diagnostikinformation** för att kopiera informationen till Urklipp.

5. Öppna en textfil (i Anteckningar) och klistra sedan in informationen i textfilen.

6. Spara textfilen och ge den ett namn som `AeD Diagnostic Info YYYY.MM.DD` liknar den (till exempel `AeD Diagnostic Info 2020.11.03` ).

När du har granskat filen och skickat den till Microsofts supporttekniker som arbetar på ditt ärende.
