---
title: Flytta en OneDrive-webbplats till en annan Geo-plats
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.collection:
- Strat_SP_gtc
- SPO_Content
localization_priority: Normal
description: Hitta information om hur du flyttar en OneDrive-webbplats till en annan Geo-plats, inklusive hur du schemalägger webbplatser, flyttar och kommunicerar förväntningar till användarna.
ms.openlocfilehash: 59b3fb47fd195967e7af056c7a71fb4e736471d1
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694295"
---
# <a name="move-a-onedrive-site-to-a-different-geo-location"></a>Flytta en OneDrive-webbplats till en annan Geo-plats 

Med OneDrive geo-flytt kan du flytta en användares OneDrive till en annan Geo-plats. OneDrive geo-flytten utförs av SharePoint Online-administratören eller den globala administratören för Microsoft 365. Innan du påbörjar en geo-flytt med OneDrive bör du meddela användaren vars OneDrive flyttas och rekommenderar att de stänger alla filer under hela flytt tiden. (Om användaren har ett dokument öppet med Office-klienten under flytten måste dokumentet sparas på den nya platsen.) Det går att schemalägga en framtida tid om du vill.

OneDrive-tjänsten använder Azure Blob Storage för att lagra innehåll. Den lagrings-blob som är associerad med användarens OneDrive flyttas från källan till målets Geo-plats inom 40 dagar efter det att OneDrive är tillgängligt för användaren. Åtkomst till användarens OneDrive återställs så snart mål platsen OneDrive är tillgänglig.

Under fönstret OneDrive geo Move (ca 2-6 timmar) är användarens OneDrive skrivskyddad. Användaren kan fortfarande komma åt sina filer via OneDrive-synkroniseringsklienten eller OneDrive-webbplats i SharePoint Online. När OneDrive geo-flytten är klar kopplas användaren automatiskt till deras OneDrive på Geo-platsen när de navigerar till OneDrive i Microsoft 365-Start programmet. Synkroniseringsklienten börjar automatiskt synkronisera från den nya platsen.

Procedurerna i den här artikeln kräver [PowerShell-modulen för Microsoft SharePoint Online](https://www.microsoft.com/download/details.aspx?id=35588).

## <a name="communicating-to-your-users"></a>Kommunicera med användarna

När du flyttar OneDrive-webbplatser mellan geo platser är det viktigt att du kommunicerar med dina användare vad du kan förvänta dig. Detta kan hjälpa till att minska användarnas förvirring och samtal till din supportavdelning. Skicka e-post till dina användare innan du flyttar och meddela dem följande information:

- När flytten förväntas starta och hur lång tid det förväntas ta
- Vilken Geo-plats deras OneDrive flyttas till och URL-adressen till den nya platsen
- De bör stänga sina filer och inte göra ändringar under flytten.
- Fil behörigheter och delning ändras inte som ett resultat av flytten.
- Vad du kan förvänta dig av [användar gränssnittet i en multi-geo-miljö](multi-geo-user-experience.md)

Glöm inte att skicka ett e-postmeddelande till dina användare när flytten har slutförts och du kan fortsätta arbeta på OneDrive.

## <a name="scheduling-onedrive-site-moves"></a>Schemalägga flytt av OneDrive-webbplatser

Du kan schemalägga flytt av OneDrive-webbplatser i förväg (beskrivs längre fram i den här artikeln). Vi rekommenderar att du börjar med ett fåtal användare för att verifiera dina arbets flöden och kommunikations strategier. När du är van vid processen kan du schemalägga flytten så här:

- Du kan schemalägga upp till 4 000 i taget.
- När flytten börjar kan du schemalägga mer, med högst 4 000 i kön och när som helst.
- Den maximala storleken på ett OneDrive som kan flyttas är 1 terabyte (1 TB).

## <a name="moving-a-onedrive-site"></a>Flytta en OneDrive-webbplats

För att göra en OneDrive geo-flyttning måste klient administratören först ange användarens önskade data plats (PDL) på lämplig Geo-plats. När PDL har ställts in väntar du i minst 24 timmar innan uppdatering av PDL ska synkroniseras på de geo platserna innan OneDrive geo-flytten börjar.

När du använder cmdlets för geo Move ansluter du till SPO-tjänsten på användarens aktuella OneDrive-Geo-plats med följande syntax:

`Connect-SPOService -url https://<tenantName>-admin.sharepoint.com`

Om du till exempel vill flytta OneDrive för användaren ' Matt@contosoenergy.onmicrosoft.com ' ansluter du till det EUR SharePoint Admin Center som användarens OneDrive finns i Geo-platsen i EUR:

`Connect-SPOSservice -url https://contosoenergyeur-admin.sharepoint.com`

![Skärm bild av PowerShell-fönstret som visar cmdleten Connect-sposervice](../media/move-onedrive-between-geo-locations-image1.png)

## <a name="validating-the-environment"></a>Verifiera miljön

Innan du påbörjar en geo-flytt med OneDrive rekommenderar vi att du validerar miljön.

För att säkerställa att alla geo platser är kompatibla kör du:

`Get-SPOGeoMoveCrossCompatibilityStatus`

Du kommer att se en lista över dina geo platser och om innehållet kan flyttas mellan betecknas som "kompatibel". Om kommandot returnerar "inkompatibelt" kan du försöka med att bekräfta statusen senare.

Om OneDrive innehåller en under webbplats kan du till exempel inte flytta den. Du kan använda cmdleten Start-SPOUserAndContentMove med parametern-ValidationOnly för att kontrol lera om OneDrive kan flyttas:

`Start-SPOUserAndContentMove -UserPrincipalName <UPN> -DestinationDataLocation <DestinationDataLocation> -ValidationOnly`

Detta returnerar framgång om OneDrive är klar att flyttas eller inte fungerar om det finns en laglig plats eller under webbplats som kan förhindra flytten. När du har verifierat att OneDrive är klar att flyttas kan du börja flytta.

## <a name="start-a-onedrive-geo-move"></a>Starta en OneDrive geo-flyttning

Starta flytten genom att köra:  

`Start-SPOUserAndContentMove -UserPrincipalName <UserPrincipalName> -DestinationDataLocation <DestinationDataLocation>`

Med dessa parametrar:

-   _UserPrincipalName_ – UPN för den användare vars OneDrive flyttas.

-   _DestinationDataLocation_ – Geo-plats dit OneDrive måste flyttas. Det ska vara samma som användarens förvalda plats.

Om du till exempel vill flytta OneDrive för matt@contosoenergy.onmicrosoft.com från EUR till Australien kör du:

`Start-SPOUserAndContentMove -UserPrincipalName matt@contosoenergy.onmicrosoft.com -DestinationDataLocation AUS`

![Skärm bild av PowerShell-fönstret med start-SPOUserAndContentMove cmdlet](../media/move-onedrive-between-geo-locations-image2.png)

Om du vill schemalägga en geo-flytt senare kan du använda en av följande parametrar:

-   _PreferredMoveBeginDate_ – flytten kommer sannolikt att börja vid den här tidpunkten. Tid måste anges i UTC (Coordinated Universal Time).

-   _PreferredMoveEndDate_ – flytten kommer sannolikt att genomföras efter den angivna tiden, på bästa möjliga sätt. Tid måste anges i UTC (Coordinated Universal Time). 

## <a name="cancel-a-onedrive-geo-move"></a>Avbryta en OneDrive geo-flyttning 

Du kan stoppa geo-flytten för en användares OneDrive, förutsatt att flytten inte pågår eller slutförs med hjälp av cmdleten:

`Stop-SPOUserAndContentMove – UserPrincipalName <UserPrincipalName>`

Där _userPrincipalName_ är UPN för den användare vars OneDrive-flytt du vill stoppa.

## <a name="determining-current-status"></a>Aktuell status bestäms

Du kan kontrol lera statusen för en OneDrive geo Move in eller ut ur den geo som du är ansluten till med hjälp av cmdleten Get-SPOUserAndContentMoveState.

Flytt status beskrivs i följande tabell.

<table>
<thead>
<tr class="header">
<th align="left"><strong>Status</strong></th>
<th align="left"><strong>Beskrivning</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">NotStarted</td>
<td align="left">Flytten har inte påbörjats.</td>
</tr>
<tr class="even">
<td align="left">Inaktivitet (<em>ej tillämpligt</em>)</td>
<td align="left">Flytten pågår i något av följande lägen: verifiering (1/4), säkerhets kopiering (2/4), återställning (3/4), rensning (4/4).</td>
</tr>
<tr class="odd">
<td align="left">Bra</td>
<td align="left">Flyttningen har slutförts.</td>
</tr>
<tr class="even">
<td align="left">Misslyckades</td>
<td align="left">Det gick inte att flytta.</td>
</tr>
</tbody>
</table>

Använd parametern UserPrincipalName för att hitta statusen för en viss användares flyttning:

`Get-SPOUserAndContentMoveState -UserPrincipalName <UPN>`

Om du vill hitta statusen för alla flyttningar i eller från den Geo-plats som du är ansluten till använder du parametern MoveState med något av följande värden: NotStarted, pågående, lyckades, misslyckades, alla.

`Get-SPOUserAndContentMoveState -MoveState <value>`

Du kan också lägga till `-Verbose` parametern för mer detaljerade beskrivningar av flytt läget.

## <a name="user-experience"></a>Användar upplevelse

Användare av OneDrive bör uppmärksammas i minimalt avbrott om deras OneDrive flyttas till en annan Geo-plats. Om du tar bort ett kort känsligt tillstånd under flytten fortsätter befintliga länkar och behörigheter att fungera som förväntat när flytten är klar.

### <a name="onedrive-for-business"></a>OneDrive för företag

När flytten pågår är användarens OneDrive skrivskyddad. När flytten är klar dirigeras användaren till OneDrive på den nya geo-platsen när de navigerar till OneDrive-startprogrammet för Microsoft 365 eller en webbläsare.

### <a name="permissions-on-onedrive-content"></a>Behörigheter för OneDrive-innehåll

Användare med behörigheter till OneDrive-innehåll kommer att fortsätta att ha åtkomst till innehållet under flytten och när det är klart.

### <a name="onedrive-sync-client"></a>OneDrive-synkroniseringsklient 

OneDrive-synkroniseringsklienten kommer automatiskt att upptäcka och överföra synkronisering till den nya OneDrive-platsen när OneDrive geo-flyttningen är klar. Användaren behöver inte logga in igen eller vidta någon annan åtgärd.  (Version 17.3.6943.0625 eller senare krävs för synkroniseringsklient.)

Om en användare uppdaterar en fil när en OneDrive geo-flyttning pågår meddelar synkroniseringsklienten dem att fil överföringar är väntande när flytten pågår.

### <a name="sharing-links"></a>Dela länkar 

När OneDrive geo-flytten är klar omdirigeras de befintliga delade länkarna för de filer som flyttas automatiskt till den nya geo-platsen.

### <a name="onenote-experience"></a>OneNote-upplevelse 

I OneNote Win32-klient-och UWP (Universal) identifieras och sömlöst synkronisera antecknings böcker automatiskt när OneDrive geo-flytten är klar. Användaren behöver inte logga in igen eller vidta någon annan åtgärd. Den enda synliga indikatorn för användaren är att synkronisering av bärbara datorer Miss lyckas när OneDrive geo-flytt pågår. Den här funktionen finns i följande OneNote-klient versioner:

-   OneNote Win32 – version 16.0.8326.2096 (och senare)

-   OneNote UWP – version 16.0.8431.1006 (och senare)

-   OneNote-mobilapp – version 16.0.8431.1011 (och senare)

### <a name="teams-app"></a>Teams-appen

När OneDrive geo-flytt är klar har användarna åtkomst till sina OneDrive-filer i Teams-appen. Dessutom fortsätter filer som delas via Teams chatt från sina OneDrive innan de geo-flytten fungerar när flytten är klar.

### <a name="onedrive-for-business-mobile-app-ios"></a>OneDrive för företag – mobilappen (iOS) 

När OneDrive geo är klart måste användaren logga ut och logga in igen på iOS-mobilappen för att synkronisera med den nya OneDrive-platsen.

### <a name="existing-followed-groups-and-sites"></a>Befintliga grupper och webbplatser som följs

Följda webbplatser och grupper visas i användarens OneDrive oavsett Geo-plats. Webbplatser och grupper som finns på en annan Geo-plats öppnas på en separat flik.

### <a name="delve-geo-url-updates"></a>Uppdateringar för Delve geo URL

Användare skickas till den Delve-geo som motsvarar sin PDL först efter det att OneDrive har flyttats till den nya geoen.
