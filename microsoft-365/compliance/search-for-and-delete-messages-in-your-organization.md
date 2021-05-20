---
title: Söka efter och ta bort e-postmeddelanden i din organisation
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
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 3526fd06-b45f-445b-aed4-5ebd37b3762a
description: Använd sök- och rensningsfunktionen i Säkerhets- och efterlevnadscentret för att söka efter och ta bort ett e-postmeddelande från alla postlådor i organisationen.
ms.openlocfilehash: 629b236be3f857da47674cda9350d8b89e6f3445
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537649"
---
# <a name="search-for-and-delete-email-messages"></a>Söka efter och ta bort e-postmeddelanden

**Den här artikeln vänder sig till administratörer. Försöker du hitta objekt i din postlåda som du vill ta bort? Se [Hitta ett meddelande eller objekt med Snabbsökning](https://support.office.com/article/69748862-5976-47b9-98e8-ed179f1b9e4d)**.

Du kan använda funktionen Innehållssökning för att söka efter och ta bort ett e-postmeddelande från alla postlådor i organisationen. Det kan hjälpa dig att hitta och ta bort potentiellt skadlig eller riskfylld e-post, t.ex.:

- Meddelanden som innehåller farliga bilagor eller virus

- Nätfiskemeddelanden

- Meddelanden som innehåller känsliga data

> [!CAUTION]
> Sök- och rensningsfunktionen är en kraftfull funktion som gör att alla som har tilldelats nödvändiga behörigheter kan ta bort e-postmeddelanden från postlådor i organisationen.

## <a name="before-you-begin"></a>Innan du börjar

- För att skapa och köra en innehållssökning måste du vara medlem i rollgruppen **eDiscovery-hanterare** eller ha tilldelats rollen **Efterlevnadssökning** i Säkerhets- och efterlevnadscenter. För att ta bort meddelanden måste du vara medlem i rollgruppen **Organisationshantering** eller ha tilldelats rollen **Sökning och rensning** i Säkerhets- och efterlevnadscenter. Mer information om hur du lägger till användare i en rollgrupp finns i [Tilldela eDiscovery-behörigheter i Säkerhets- och efterlevnadscenter](assign-ediscovery-permissions.md).

  > [!NOTE]
  > Rollgruppen **Organisationshantering** finns både i Exchange Online och i Säkerhets- och Efterlevnadscenter. Det här är separata rollgrupper som ger olika behörigheter. Att vara medlem i **Organisationshantering** i Exchange Online ger inte nödvändiga behörigheter för att ta bort e-postmeddelanden. Om du inte har tilldelat rollen **Sökning och rensning** i Säkerhets- och efterlevnadscenter (antingen direkt eller via en rollgrupp så som **Organisationshantering**) får du ett felmeddelande i steg tre när du kör cmdleten **New-ComplianceSearchAction** med meddelandet: "Det går inte att hitta en parameter som matchar parameternamnet Rensa".

- Du måste använda PowerShell för Säkerhets- och efterlevnadscentret för att ta bort meddelanden. Se [steg 2](#step-2-connect-to-security--compliance-center-powershell) för anvisningar om hur du ansluter.

- Du kan ta bort högst tio objekt per postlåda samtidigt. Eftersom funktionen att söka efter och ta bort meddelanden är avsedd att vara ett verktyg för incidentrespons hjälper den här gränsen till att säkerställa att meddelanden snabbt tas bort från postlådor. Den här funktionen är inte avsedd för att rensa i användarnas postlådor.

- Det maximala antalet postlådor i en innehållssökning som du kan använda för att ta bort objekt genom att göra en söknings- och rensningsåtgärd är 50 000. Om sökningen (som du skapar i [steg 1](#step-1-create-a-content-search-to-find-the-message-to-delete)) söker igenom fler än 50 000 postlådor misslyckas rensningsåtgärden (som du skapar i steg 3). Sökning i fler än 50 000 postlådor i en enda sökning kan inträffa när du konfigurerar sökningen så att den omfattar alla postlådor i organisationen. Denna begränsning gäller fortfarande även om mindre än 50 000 postlådor innehåller objekt som matchar sökfrågan. Se avsnittet [Mer information](#more-information) för mer vägledning om hur du använder sökbehörighetsfilter för att söka efter och rensa objekt från fler än 50 000 postlådor.

- Proceduren i den här artikeln kan endast användas för att ta bort objekt i Exchange Online-postlådor och gemensamma mappar. Du kan inte använda den för att ta bort innehåll från SharePoint- eller OneDrive för företag-webbplatser.

- E-postobjekt i en granskningsuppsättning i ett avancerat eDiscovery-ärende kan inte tas bort med hjälp av procedurerna i den här artikeln. Det beror på att objekt i en granskningsuppsättning lagras på en Azure Storage-plats och inte i livetjänsten. Det innebär att de inte returneras av innehållssökningen som du skapar i steg 1. Om du vill ta bort objekt i en granskningsuppsättning måste du ta bort det Advanced eDiscovery-ärende som innehåller granskningsuppsättningen. Mer information finns i [Stänga eller ta bort ett Advanced eDiscovery-ärende](close-or-delete-case.md).

## <a name="step-1-create-a-content-search-to-find-the-message-to-delete"></a>Steg 1: Skapa en innehållssökning för att hitta meddelandet som ska tas bort

Det första steget är att skapa och köra en innehållssökning för att hitta det meddelande som du vill ta bort från postlådor i organisationen. Du kan skapa sökningen med hjälp av Säkerhets- och efterlevnadscentret eller genom att köra cmdletarna **New-ComplianceSearch** och **Start-ComplianceSearch**. De meddelanden som matchar frågan för den här sökningen tas bort genom körning av kommandot **New-ComplianceSearchAction -Purge** i [steg 3](#step-3-delete-the-message). Mer information om hur du skapar en innehållssökning och konfigurerar sökfrågor finns i följande avsnitt:

- [Innehållssökning i Office 365](content-search.md)

- [Nyckelordsfrågor för innehållssökning](keyword-queries-and-search-conditions.md)

- [New-ComplianceSearch](/powershell/module/exchange/New-ComplianceSearch)

- [Start-ComplianceSearch](/powershell/module/exchange/Start-ComplianceSearch)

> [!NOTE]
> De innehållsplatser som genomsöks i innehållssökningen som du skapar i det här steget får inte innehålla SharePoint- eller OneDrive för företag-webbplatser. Du kan bara ta med postlådor och gemensamma mappar i en innehållssökning som ska användas för e-postmeddelanden. Om innehållssökningen omfattar webbplatser får du ett felmeddelande i steg 3 när du kör cmdleten **New-ComplianceSearchAction**.

### <a name="tips-for-finding-messages-to-remove"></a>Tips på hur du hittar meddelanden som ska tas bort

Sökfrågans mål är att begränsa sökresultatet till endast det eller de meddelanden som du vill ta bort. Här är några tips:

- Om du vet den exakta texten eller frasen som används i meddelandets ämnesrad använder du egenskapen **Ämne** i sökfrågan.

- Om du vet det exakta datumet (eller ett datumintervall) för meddelandet ska du ta med egenskapen **Mottaget** i sökfrågan.

- Om du vet vem som har skickat meddelandet tar du med egenskapen **Från** i sökfrågan.

- Förhandsgranska sökresultatet för att verifiera att sökningen endast returnerade meddelandet (eller meddelandena) som du vill ta bort.

- Använd statistik för sökuppskattning (visas i informationsfönstret för sökningen i Säkerhets- och efterlevnadscentret eller med cmdleten [Get-ComplianceSearch](/powershell/module/exchange/get-compliancesearch)) för att få summan av det totala antalet resultat.

Här följer två exempel på frågor som hittar misstänkta e-postmeddelanden.

- Den här frågan returnerar meddelanden som togs emot av användare mellan 13 april 2016 och 14 april 2016 som innehåller orden ”åtgärd” och ”obligatorisk” i ämnesraden.

  ```powershell
  (Received:4/13/2016..4/14/2016) AND (Subject:'Action required')
  ```

- Den här frågan returnerar meddelanden som skickats av chatsuwloginsset12345@outlook.com som innehåller den exakta frasen ”Uppdatera din kontoinformation” i ämnesraden.

  ```powershell
  (From:chatsuwloginsset12345@outlook.com) AND (Subject:"Update your account information")
  ```

Här är ett exempel på hur du använder en fråga för att skapa och starta en sökning genom att köra cmdletarna **New-ComplianceSearch** och **Start-ComplianceSearch** för att söka i alla postlådor i organisationen:

```powershell
$Search=New-ComplianceSearch -Name "Remove Phishing Message" -ExchangeLocation All -ContentMatchQuery '(Received:4/13/2016..4/14/2016) AND (Subject:"Action required")'
Start-ComplianceSearch -Identity $Search.Identity
```

## <a name="step-2-connect-to-security--compliance-center-powershell"></a>Steg 2: Anslut till Säkerhets- och efterlevnadscenter i PowerShell

Nästa steg är att ansluta till PowerShell för Säkerhets- och efterlevnadscenter för din organisation. Stegvisa anvisningar finns i [Ansluta till PowerShell för Säkerhets- och efterlevnadscenter](/powershell/exchange/connect-to-scc-powershell).

När du har anslutit till PowerShell för Säkerhets- och efterlevnadscenter kör du cmdletarna **New-ComplianceSearch** och **Start-ComplianceSearch** som du förberedde i föregående steg.

## <a name="step-3-delete-the-message"></a>Steg 3: Ta bort meddelandet

När du har skapat och förfinat en innehållssökning för att returnera meddelandet som du vill ta bort och är ansluten till PowerShell för Säkerhets- och efterlevnadscentret, är det sista steget att köra cmdleten **New-ComplianceSearchAction** för att ta bort meddelandet. Du kan ta bort meddelandet med mjuk eller permanent borttagning. Ett mjukt borttaget meddelande flyttas till en användares mapp för återställningsbara objekt och behålls tills kvarhållningsperioden för borttagna objekt löpt ut. Borttagna meddelanden markeras för permanent borttagning från postlådan och tas bort permanent nästa gång postlådan bearbetas av assistenten för hanterade mappar. Om återställning av enstaka objekt har aktiverats för postlådan tas permanent borttagna objekt bort permanent när kvarhållningsperioden för borttagna objekt löpt ut. Om en postlåda sätts på undantag bevaras borttagna meddelanden tills undantaget för objektet upphör att gälla eller tills undantaget har tagits bort från postlådan.

I följande exempel tas sökresultatet som returnerats av en innehållssökning med namnet ”Ta bort nätfiskemeddelande” bort av kommandot med mjuk borttagning.

```powershell
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType SoftDelete
```

Om du vill ta bort objekten som returnerats för innehållssökningen ”Ta bort nätfiskemeddelande” kör du det här kommandot:

```powershell
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType HardDelete
```

När du kör föregående kommando för mjuk eller permanent borttagning av meddelanden, är sökningen som anges av parametern *SearchName* den innehållssökning som du skapade i steg 1.

Mer information finns i [New-ComplianceSearchAction](/powershell/module/exchange/New-ComplianceSearchAction).

## <a name="more-information"></a>Mer information

- **Hur får du status för söknings- och borttagningsåtgärden?**

  Kör **Get-ComplianceSearchAction** för att få status för borttagningsåtgärden. Objektet som skapas när du kör cmdleten **New-ComplianceSearchAction** namnges med hjälp av följande format: `<name of Content Search>_Purge`.

- **Vad händer när du har tagit bort ett meddelande?**

  Ett meddelande som tas bort med kommandot `New-ComplianceSearchAction -Purge -PurgeType HardDelete` flyttas till mappen Rensningar och kan inte nås av användaren. När meddelandet flyttas till mappen Rensningar behålls meddelandet under det borttagna objektets kvarhållningsperiod om återställning av enstaka objekt har aktiverats för postlådan. (I Microsoft 365 är återställning av enstaka objekt aktiverat som standard när en ny postlåda skapas.) När kvarhållningsperioden för det borttagna objektet löper ut, markeras meddelandet för permanent borttagning och rensas från Microsoft 365 nästa gång postlådan bearbetas av assistenten för hanterade mappar.

  Om du använder kommandot `New-ComplianceSearchAction -Purge -PurgeType SoftDelete` flyttas meddelanden till mappen Borttaget i användarens mapp för återställningsbara objekt. Den rensas inte omedelbart i Microsoft 365. Användaren kan återställa meddelanden i mappen Borttaget under den period som angetts för postlådan baserat på kvarhållningsperioden för borttagna objekt. När den här kvarhållningsperioden är slut (eller om användaren rensar meddelandet innan den upphör) flyttas meddelandet till mappen Rensningar och kan inte längre nås av användaren. När meddelandet finns i mappen Rensningar behålls meddelandet under det borttagna objektets kvarhållningsperiod som konfigurerats för postlådan om återställning av enstaka objekt har aktiverats för postlådan. (I Microsoft 365 är återställning av enstaka objekt aktiverat som standard när en ny postlåda skapas.) När kvarhållningsperioden för det borttagna objektet löper ut, markeras meddelandet för permanent borttagning och rensas från Microsoft 365 nästa gång postlådan bearbetas av assistenten för hanterade mappar.

- **Hur gör du om du måste ta bort ett meddelande från fler än 50 000 postlådor?**

  Som tidigare beskrivits kan du utföra en söknings- och rensningsåtgärd på maximalt 50 000 postlådor (även om mindre än 50 000 innehåller objekt som matchar sökfrågan). Om du behöver göra en söknings- och rensningsåtgärd på fler än 50 000 postlådor kan du skapa tillfälliga sökbehörighetsfilter som minskar antalet postlådor som ska sökas igenom till färre än 50 000 postlådor. Om organisationen till exempel innehåller postlådor i olika avdelningar, delstater eller länder, kan du skapa ett behörighetsfilter för postlådesökning baserat på någon av de postlådeegenskaperna för att söka i en delmängd av postlådorna i organisationen. När du har skapat behörighetsfiltret för sökning skapar du sökningen (beskrivs i steg 1) och tar sedan bort meddelandet (beskrivs i steg 3). Sedan kan du redigera filtret och söka efter och rensa meddelanden i en annan uppsättning postlådor. Mer information om hur du skapar behörighetsfilter för sökning finns i [Konfigurera behörighetsfiltrering för innehållssökning](permissions-filtering-for-content-search.md).

- **Tas icke indexerade objekt i sökresultaten bort?**

  Nej, kommandot New-ComplianceSearchAction -Purge tar inte bort icke indexerade objekt.

- **Vad händer om ett meddelande tas bort från en postlåda som har placerats i Lokalt bevarande eller Bevarande av juridiska skäl eller har tilldelats en Microsoft 365-kvarhållningsprincip?**

  När meddelandet rensas och flyttas till mappen Rensningar behålls meddelandet tills varaktigheten för undantaget upphör att gälla. Om varaktigheten för undantaget är obegränsad behålls objekten tills det har tagits bort eller varaktigheten för bevarandeundantaget ändras.

- **Varför är söknings- och borttagningsarbetsflödet uppdelat på olika rollgrupper i säkerhets- och efterlevnadscentret?**

  Som vi tidigare har förklarat måste personen vara medlem i rollgruppen eDiscovery Manager eller ha tilldelats hanteringsrollen för efterlevnadssökning för att kunna söka i postlådor. Om någon vill ta bort meddelanden måste denne vara medlem i rollgruppen Organisationshantering eller ha tilldelats hanteringsrollen för sökning och rensning. På så sätt är det möjligt att styra vem som kan söka i postlådor i organisationen och vem som kan ta bort meddelanden.
