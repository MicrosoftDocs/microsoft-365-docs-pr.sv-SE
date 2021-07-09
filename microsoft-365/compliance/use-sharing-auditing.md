---
title: Använda delningsgranskning i granskningsloggen
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
search.appverid:
- SPO160
- MOE150
- BCS160
- MET150
ms.collection:
- M365-security-compliance
- SPO_Content
ms.assetid: 50bbf89f-7870-4c2a-ae14-42635e0cfc01
description: Administratören kan lära sig att använda delningsgranskning i Microsoft 365-granskningsloggen för att identifiera resurser som delas med användare utanför organisationen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 302ad7665c83ee9061b2e1965ef03ec25d0aab58
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/09/2021
ms.locfileid: "53341514"
---
# <a name="use-sharing-auditing-in-the-audit-log"></a>Använda delningsgranskning i granskningsloggen

Delning är en viktig aktivitet i SharePoint online och OneDrive för företag, och används ofta i organisationer. Administratörer kan använda delningsgranskning i granskningsloggen för att avgöra hur delning används i organisationen. 
  
## <a name="the-sharepoint-sharing-schema"></a>Schemat SharePoint delning

Delningshändelser (inte händelser relaterade till delningsprincip och delningslänkar) skiljer sig från fil- och mapprelaterade händelser på ett primärt sätt: en användare utför en åtgärd som påverkar en annan användare. Till exempel när en resurs användare A ger användare B åtkomst till en fil. I det här exemplet är användare A den *agerande användaren* och användare B *är målanvändaren.* I SharePoint filschemat påverkar den agerande användarens åtgärd endast själva filen. När användare A öppnar en fil är den agerande användaren den enda information som behövs i **FileAccessed-händelsen.** För att åtgärda den här skillnaden finns ett separat schema, som kallas SharePoint-delningsschema, som innehåller mer information om delning av händelser.  Det här säkerställer att administratörerna har tillgång till vem som har delat en resurs och användaren som resursen har delats med. 
  
I delningsschemat finns ytterligare två fält i en granskningspost som är relaterad till delningshändelser: 
  
- **TargetUserOrGroupType:** Identifierar om målanvändaren eller gruppen är medlem, gäst, SharePointGroup, säkerhetsgrupp eller partner.

- **TargetUserOrGroupName:** Lagrar UPN eller namn för målanvändaren eller gruppen som en resurs delades med (användare B i föregående exempel). 

De här två fälten kan, förutom andra egenskaper från granskningsloggschemat som Användare, Åtgärd  och Datum, ge information om vilken användare som har delat vilken resurs med vem *och*  *när*. 
  
Det finns en annan schemaegenskap som är viktig för delningsartikeln. När du exporterar granskningsloggsökningsresultat **lagrar kolumnen Information** i den exporterade CSV-filen information om delningshändelser. När en användare till exempel delar en webbplats med en annan användare sker detta genom att han/hon lägger till målanvändaren i en SharePoint grupp. Kolumnen **Information** samlar in den här informationen för att skapa sammanhang för administratörer. I [steg 2](#step-2-use-the-powerquery-editor-to-format-the-exported-audit-log) finns anvisningar om hur du parsar informationen i **kolumnen Information.**

## <a name="sharepoint-sharing-events"></a>SharePoint delningshändelser

Delning definieras av när en användare (den *agerande* användaren) vill dela en resurs med en annan användare *(målanvändaren).* Granskningsposter som är relaterade till att dela en resurs med en extern användare (en användare som finns utanför organisationen och inte har ett gästkonto i organisationens Azure Active Directory) identifieras med följande händelser som loggas i granskningsloggen:

- **SharingInvitationCreated:** En användare i organisationen försökte dela en resurs (förmodligen en webbplats) med en extern användare. Det leder till att en extern delningsinbjudan skickas till målanvändaren. Ingen åtkomst till resursen beviljas i det här läget.

- **SharingInvitationAccepted:** Den externa användaren har accepterat delningsinbjudan som skickats av den agerande användaren och har nu åtkomst till resursen.

- **AnonymousLinkCreated:** En anonym länk (även kallad "Alla"-länk) skapas för en resurs. Eftersom en anonym länk kan skapas och sedan kopieras är det lämpligt att anta att alla dokument som har en anonym länk har delats med en målanvändare.

- **AnonymousLinkUsed:** Som namnet antyder loggas händelsen när en anonym länk används för att komma åt en resurs. 

- **SecureLinkCreated:** En användare har skapat en länk för "specifika personer" för att dela en resurs med en viss person. Den här målanvändaren kan vara någon utanför organisationen. Den person som resursen delas med identifieras i granskningsposten för **händelsen AddedToSecureLink.** Tidsstämplarna för dessa två händelser är nästan identiska.

- **AddedToSecureLink:** En användare har lagts till i en länk för specifika personer. Använd fältet **TargetUserOrGroupName** i den här händelsen för att identifiera användaren som lagts till i motsvarande länk för personer. Den här målanvändaren kan vara någon utanför organisationen.

## <a name="sharing-auditing-work-flow"></a>Arbetsflöde för delning av granskning
  
När en användare (den agerande användaren) vill dela en resurs med en annan användare (målanvändaren), SharePoint (eller OneDrive för företag) kontrollerar han/hon först om målanvändarens e-postadress redan är kopplad till ett användarkonto i organisationens katalog. Om målanvändaren finns i katalogen (och har ett motsvarande gästanvändarkonto) SharePoint följande:
  
-  Tilldelar omedelbart målanvändaren behörigheter för åtkomst till resursen genom att lägga till målanvändaren i rätt SharePoint och loggar en **AddedToGroup-händelse.** 
    
- Skickar ett delningsmeddelande till målanvändareens e-postadress.
    
- Loggar en **SharingSet-händelse.** Den här händelsen har ett eget namn som är "Delad fil, mapp eller webbplats" **under** Aktiviteter för delning och åtkomstbegäran i väljaren för granskningsloggens sökverktyg. Se skärmbilden i [Steg 1.](#step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file) 
    
Om målanvändaren inte har ett användarkonto i katalogen gör SharePoint följande: 
    
   - Loggar någon av följande händelser, baserat på hur resursen delas:
   
      - **AnonymousLinkCreated**
   
      - **SecureLinkCreated**
   
      - **AddedToSecureLink** 

      - **SharingInvitationCreated** (händelsen loggas bara när den delade resursen är en webbplats)
    
   - När målanvändaren accepterar delningsinbjudan som skickas till honom/hon (genom att klicka på länken i inbjudan) loggar SharePoint en **SharingInvitationAccepted-händelse** och tilldelar målanvändaren behörigheter för åtkomst till resursen. Om målanvändaren skickas en anonym länk loggas **händelsen AnonymousLinkUsed** när målanvändaren använder länken för åtkomst till resursen. För säkra länkar loggas **en FileAccessed-händelse** när en extern användare använder länken för att komma åt resursen.

Ytterligare information om målanvändaren loggas också, till exempel identiteten för användaren som inbjudan är till och användaren som accepterar inbjudan. I vissa fall kan de här användarna (eller e-postadresserna) vara olika. 

## <a name="how-to-identify-resources-shared-with-external-users"></a>Identifiera resurser som delas med externa användare

Ett vanligt krav för administratörer är att skapa en lista över alla resurser som har delats med användare utanför organisationen. Med delningsgranskning i Office 365 kan administratörer skapa den här listan. Gör så här:
  
### <a name="step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file"></a>Steg 1: Sök efter delningshändelser och exportera resultaten till en CSV-fil

Det första steget är att söka i granskningsloggen efter delningshändelser. Mer information (inklusive vilka behörigheter som krävs) för att söka i granskningsloggen finns i Söka i granskningsloggen i [& Säkerhets- och efterlevnadscenter.](search-the-audit-log-in-security-and-compliance.md)
  
1. Gå till <https://compliance.microsoft.com>.

2. Logga in med ditt arbets- eller skolkonto.

3. Klicka på Granska i Microsoft 365 Efterlevnadscenter vänstra **fönsterrutan.**

    Sidan **Granska** visas.

4. Under **Aktiviteter** klickar du på **Aktiviteter för delning och åtkomstbegäran** för att söka efter delningsrelaterade händelser. 

    ![Under Aktiviteter väljer du Aktiviteter för delning och åtkomstbegäran](../media/46bb25b7-1eb2-4adf-903a-cc9ab58639f9.png)
  
5. Välj ett datum- och tidsintervall för att hitta delningshändelserna som inträffat under perioden. 

6. Klicka **på Sök** för att köra sökningen. 

7. När sökningen har körts och resultatet visas klickar du på Exportera **resultat Ladda** ned \> **alla resultat.**

    När du har valt exportalternativ uppmanas du att öppna eller spara CSV-filen i ett meddelande längst ned i fönstret.

8. Klicka **på** \> **Spara som** och spara CSV-filen i en mapp på den lokala datorn. 

### <a name="step-2-use-the-powerquery-editor-to-format-the-exported-audit-log"></a>Steg 2: Använda PowerQuery-redigeraren för att formatera den exporterade granskningsloggen

Nästa steg är att använda transformeringsfunktionen JSON i Power Query-redigeraren i Excel för att dela upp varje egenskap i kolumnen **Information** (som består av ett JSON-objekt med flera egendom) i en egen kolumn. Då kan du filtrera kolumner för att visa poster som är relaterade till delning

Stegvisa instruktioner finns i ”Steg 2: Formatera den exporterade granskningsloggen med Power Query-redigeraren” i [Exportera, konfigurera och visa granskningsloggposter](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor).

### <a name="step-3-filter-the-csv-file-for-resources-shared-with-external-users"></a>Steg 3: Filtrera CSV-filen efter resurser som delas med externa användare

Nästa steg är att filtrera CSV-filen efter de olika delningsrelaterade händelser som tidigare beskrivits [i SharePoint för delningshändelser.](#sharepoint-sharing-events) Alternativt kan du filtrera kolumnen **TargetUserOrGroupType** för att visa alla poster där egenskapens värde är **Gäst.** 

När du har följt instruktionerna i föregående steg för att förbereda CSV-filen med hjälp av PowerQuery-redigeraren gör du följande:
    
1. Öppna Excel som du skapade i steg 2. 

2. På fliken **Start** klickar du på **Sortera & filter** och sedan på **Filtrera**.
    
3. I **listrutan &** Sortera och filtrera  i kolumnen Åtgärder avmarkerar du alla val, markerar en eller flera av följande delningsrelaterade händelser och klickar sedan på **Ok.**
 
   - **SharingInvitationCreated**
   
   - **AnonymousLinkCreated**
   
   - **SecureLinkCreated**
   
   - **AddedToSecureLink** 
    
    Excel visas raderna för de händelser du har markerat.
    
4. Gå till kolumnen **TargetUserOrGroupType och** markera den. 
    
5. I **listrutan & Sortera** och filtrera avmarkerar du alla val, väljer sedan **TargetUserOrGroupType:Guest** och klickar på **Ok.**
    
    Nu Excel rader för delningshändelser OCH var målanvändaren finns utanför organisationen, eftersom externa användare identifieras av värdet **TargetUserOrGroupType:Guest.** 
  
> [!TIP]
> För de granskningsposter som visas identifierar **kolumnen ObjectId** den resurs som delades med målanvändaren. till exempel  `ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx` .
