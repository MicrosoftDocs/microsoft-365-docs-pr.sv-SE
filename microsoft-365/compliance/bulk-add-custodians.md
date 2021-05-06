---
title: Importera biblioteks till ett Advanced eDiscovery ärende
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
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Med importverktyget kan du snabbt lägga till flera objekt och deras associerade datakällor till ett ärende i Advanced eDiscovery.
ms.openlocfilehash: 98ff3690fe7fd8c956fce436585014ef0db82a26
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/04/2021
ms.locfileid: "52161802"
---
# <a name="import-custodians-to-an-advanced-ediscovery-case"></a>Importera biblioteks till ett Advanced eDiscovery ärende

I Advanced eDiscovery fall där många dokumentrepresentanter ingår kan du importera flera dokumentrepresentanter samtidigt genom att använda en CSV-fil som innehåller den information som behövs för att lägga till dem i ett ärende.

## <a name="import-custodians"></a>Importera sn3:ar

1. Öppna Advanced eDiscovery och välj **fliken Datakällor.**

2. Klicka på **Lägg till datakälla** Importera  >  **snianer**.

3. På den **utfällsbara sidan Importera** dokumentrepresentanter klickar du på Ladda ned en **tom mall för** att ladda ned en dokumentmall i CSV-fil.

   ![Ladda ned en CSV-mall från den utfällsbara sidan Importera dokumentrepresentanter](../media/ImportCustodians1.png)

4. Lägg till ljudinformation i CSV-filen och spara den på din lokala dator. Mer information om vilka egenskaper som krävs i [CSV-filen](#custodian-csv-file) finns i csv-filens insv-fil.

5. När du har förberett CSV-filen med den dokumentade informationen går du tillbaka till fliken **Datakällor** och klickar på Lägg till **datakälla**  >  **Importera dokumentianer** igen.

6. På den **utfällliga** sidan  Importera dokumentrepresentanter klickar du på Bläddra och laddar sedan upp CSV-filen som innehåller den dokumentade informationen.

   När CSV-filen har laddats  upp skapas och visas på fliken  Jobb. Jobbet validerar de registrerades och deras associerade datakällor och lägger sedan till dem på **sidan Datakällor** för ärendet.

## <a name="custodian-csv-file"></a>Csv-fil för dokument

När du har laddat ned MALLEN CSV-dokument kan du lägga till dokumentrepresentanter och deras datakälla i varje rad. Se till att du inte ändrar kolumnnamnen i rubrikraden. Använd kolumnerna typ av arbetsbelastning och arbetsbelastning för att koppla andra datakällor till en vårdnadshavare.

| Kolumnnamn|Beskrivning|
|:------- |:------------------------------------------------------------|
|**10-postkontakt**     |Den insertsiskans UPN-e-postadress. Till exempel sarad@contoso.onmicrosoft.com.           |
|**Exchange Aktiverad** | SANT/FALSKT-värde för att inkludera eller inte inkludera den som är den som förser postlådan med sitt namn.      |
|**OneDrive Aktiverad** | SANT/FALSKT-värde om du vill inkludera eller inte inkludera den som har OneDrive för företag konto. |
|**Is OnHold**        | SANT/FALSKT anger om de verkliga datakällorna ska vara i förvaring. <sup>1</sup>     |
|**Typ av arbetsbelastning1**         |Strängvärde som anger vilken typ av datakälla som ska associeras med den som ska associeras. Möjliga värden inkluderar: <br/>- ExchangeMailbox<br/> - SharePointSite<br/>- TeamsMailbox<br/>- TeamsSite<br/> - YammerMailbox<br/>- Yammer-webbplats |
|**Workload1 Location**     | Beroende på typ av arbetsbelastning är det här datakällans plats. Till exempel e-postadressen för en Exchange postlåda eller URL-adressen för en SharePoint webbplats. |
|||

> [!NOTE]
> <sup>1</sup> Du kan placera högst 1 000 postlådor och 100 platser i förvaring med hjälp av importprocessen och CSV-filen. Du kan använda den här processen för att lägga till fler än 1 000 personer till ett ärende, men begränsningarna för förvaring gäller fortfarande. Mer information om begränsningar för begränsningar av begränsningar för [begränsningar finns i Advanced eDiscovery](limits-ediscovery20.md#hold-limits).

Här är ett exempel på en CSV-fil med dokumentinformation:<br/><br/>

|10-postkontakt      | Exchange Aktiverad | OneDrive Aktiverad | Is OnHold | Typ av arbetsbelastning1 | Workload1 Location             |
| ----------------- | ---------------- | ---------------- | --------- | -------------- | ------------------------------ |
|robinc@onmicrosoft.contoso.com | TRUE             | TRUE             | TRUE      | SharePointSite | https://contoso.sharepoint.com |
|pillarp@onmicrosoft.contoso.com | TRUE             | TRUE             | TRUE      | |  |
||||||

## <a name="custodian-and-data-source-validation"></a>Kontroll av datakälla och datakälla

När du har laddat upp den uppsvända CSV Advanced eDiscovery filen gör du följande:

1. Verifierar de som har godkänt den och deras datakällor.

2. Indexerar alla datakällor för varje dokumentägare och placerar dem i förvaring (om egenskapen **Is OnHold** i CSV-filen är inställd på SANT).

### <a name="custodian-validation"></a>Insidningsvalidering

För närvarande stöder vi endast import av biblioteksmedlemmar som ingår i organisationens Azure Active Directory (Azure AD).

Det dokumentariska importverktyget söker efter och verifierar dokumentrepresentanter med HJÄLP av UPN-värdet i kolumnen **Förnamnkontaktepost** i CSV-filen. Om någon har verifierat en datakälla läggs den till automatiskt i ärendet och listas på fliken **Datakällor** för ärendet. Om en vårdnadshavare inte kan verifieras visas de i felloggen för det BulkAddCustodian-jobb som finns på fliken Jobb för ärendet.  Ej registrerade bibliotek läggs inte till i ärendet eller visas på **fliken Datakällor.**

### <a name="data-source-validation"></a>Datakällverifiering

När brevlådor valideras och läggs till i ärendet läggs varje primär postlåda och OneDrive konto som är kopplat till en vårdnadshavare till.

Men om någon av de andra datakällorna (t.ex. SharePoint-webbplatser, Microsoft Teams-, Microsoft 365-grupper eller Yammer-grupper) som är kopplade till en användare inte kan hittas, tilldelas inga av dem till den verifieradeianen och värdet Verifierad visas i kolumnen **Status** bredvid den som är godkänd på fliken **Datakällor.** 

Så här lägger du till verifierade datakällor för en vårdnadshavare:

1. På fliken **Datakällor** väljer du en dokumenterare som innehåller datakällor som inte är verifierade.

2. På den utfällliga sidan  för den verifierade person som ingår bläddrar du till avsnittet Förfallna platser för att visa både verifierade och icke verifierade datakällor som är associerade med verifierare.

3. Klicka **på** Redigera högst upp på den utfällliga sidan om du vill ta bort ogiltiga datakällor eller lägga till nya.

4. När du tar bort oberäknade datakällor eller  lägger till en ny, visas värdet Aktiv i kolumnen **Status** för den vårdnadshavare som inte har något värde på **fliken Datakällor.** Om du vill lägga till källor som tidigare såg ut att vara ogiltiga följer du åtgärdsstegen nedan för att manuellt lägga till dem till en vårdnadshavare.

### <a name="remediating-invalid-data-sources"></a>Åtgärda ogiltiga datakällor

Så här lägger du till och associerar en datakälla som tidigare var ogiltig:

1. På fliken **Datakällor väljer** du en vårdnadshavare att manuellt lägga till och associera en datakälla som tidigare var ogiltig.

2. Klicka **på** Redigera högst upp på den utfällliga sidan om du vill associera postlådor, webbplatser, Teams eller Yammer postgrupper med den tor just nu. Det gör du genom **att** klicka på Redigera bredvid rätt dataplatstyp.

3. Klicka **på** Nästa för att visa **sidan Inställningar för** håll och konfigurera inställningen för att vänta för de datakällor du lagt till.

4. Klicka **på Nästa** för att visa sidan Granska **granskare** och klicka sedan på **Skicka för** att spara ändringarna.
