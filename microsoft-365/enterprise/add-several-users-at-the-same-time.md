---
title: Lägga till flera användare samtidigt i Microsoft 365 – administratörshjälp
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365P_AddUsersCSV
- O365M_AddUsersCSV
- O365E_AddUsersCSV
search.appverid:
- MET150
- MOP150
- MOE150
- MED150
- GMA150
- MBS150
- GEA150
- BCS160
description: 'Lär dig hur du lägger till flera användare i Microsoft 365 för företag med hjälp av en lista i ett kalkylblad eller en annan CSV-formaterad fil. Här finns en video på YouTube som visar hur du lägger till konton Microsoft 365. I slutet av den här processen kommer varje användare med ett konto att ha en Microsoft 365 postlåda. '
ms.openlocfilehash: 6b3e8d885466e44a4aa23427a54cfc98b2eebdf3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905626"
---
# <a name="add-several-users-at-the-same-time-to-microsoft-365---admin-help"></a>Lägga till flera användare samtidigt i Microsoft 365 – administratörshjälp

Alla i din grupp behöver ett användarkonto innan de kan logga in och komma åt Microsoft 365 tjänster, till exempel e-Office. Om du har många personer kan du lägga till deras konton samtidigt från ett kalkylblad Excel någon annan fil som sparats i CSV-format. [Vet du inte vad CSV-formatet är?](add-several-users-at-the-same-time.md#not-sure-what-csv-format-is)
  
> [!NOTE]
> Om du inte använder det nya administrationscentret för Microsoft 365 kan du aktivera det genom att välja **Prova det nya administrationscentret** längst upp på startsidan.

## <a name="add-multiple-users-in-the-microsoft-365-admin-center"></a>Lägga till flera användare Microsoft 365 administrationscentret

1. Logga in på Microsoft 365 med ditt arbets- eller skolkonto.

2. I administrationscentret väljer du **Användare** \> **aktiva användare.**

3. Välj **Lägg till flera användare.**

4. På panelen **Importera flera användare** kan du ladda ned en CSV-exempelfil med eller utan ifyllda exempeldata.

    Kalkylbladet måste innehålla exakt **samma kolumnrubriker** som exempelrubriken (Användarnamn, Förnamn och så vidare). Om du använder mallen öppnar du den i ett textredigeringsverktyg, till exempel Anteckningar, och överväg att låta alla data på rad 1 vara och bara ange data i rad 2 och nedan.

    Kalkylbladet måste också innehålla värden för användarnamn (t.ex. jens@contoso.com) och ett visningsnamn (t.ex. Jens Persson) för varje användare.

  ```
  User Name,First Name,Last Name,Display Name,Job Title,Department,Office Number,Office Phone,Mobile Phone,Fax,Address,City,State or Province,ZIP or Postal Code,Country or Region
  chris@contoso.com,Chris,Green,Chris Green,IT Manager,Information Technology,123451,123-555-1211,123-555-6641,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  ben@contoso.com,Ben,Andrews,Ben Andrews,IT Manager,Information Technology,123452,123-555-1212,123-555-6642,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  david@contoso.com,David,Longmuir,David Longmuir,IT Manager,Information Technology,123453,123-555-1213,123-555-6643,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  cynthia@contoso.com,Cynthia,Carey,Cynthia Carey,IT Manager,Information Technology,123454,123-555-1214,123-555-6644,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  melissa@contoso.com,Melissa,MacBeth,Melissa MacBeth,IT Manager,Information Technology,123455,123-555-1215,123-555-6645,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  
  ```

5. Ange en filsökväg i rutan eller välj **Bläddra** för att bläddra till CSV-filens plats. Välj sedan **Verifiera**.
  
    Om det finns problem med filen visas de problemen i panelen. Du kan också ladda ned en loggfil.

6. I dialogrutan **Ange användaralternativ** kan du ange inloggningsstatus och välja den produktlicens som tilldelas till alla användare.

7. I dialogrutan **Visa resultat** kan du välja att skicka resultaten till dig själv eller till andra användare (lösenord anges i oformaterad text) och du kan se hur många användare som har skapats och om du måste köpa fler licenser att tilldela till några av de nya användarna.

## <a name="next-steps"></a>Nästa steg

- Nu när de här personerna har konton måste de ladda ned och installera eller installera om [Microsoft 365 eller Office 2016 på en PC eller Mac.](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658) Varje person i din grupp kan installera Microsoft 365 på upp till fem PC- eller Mac-datorer.

- Varje person kan också konfigurera [Office-appar](https://support.office.com/article/7dabb6cb-0046-40b6-81fe-767e0b1f014f) och e-post på en mobil enhet på upp till fem surfplattor och fem telefoner, till exempel iPhone, iPad och telefoner och surfplattor med Android. Tack vare det här kan de redigera Office-filer var de än befinner sig.

    Se [Konfigurera Microsoft 365 för företag](https://support.office.com/article/6a3a29a0-e616-4713-99d1-15eda62d04fa) för en fullständig lista över konfigurationsstegen.

## <a name="more-information-about-how-to-add-users-to-microsoft-365"></a>Mer information om hur du lägger till användare i Microsoft 365

### <a name="not-sure-what-csv-format-is"></a>Är du osäker på vad CSV-formatet är?

En CSV-fil är en fil med kommaavgränsade värden. Du kan skapa eller redigera en sådan fil med en textredigerare eller med ett kalkylprogram, t.ex. Excel.
  
Du kan ladda ned [det här exempelkalkylbladet](https://www.microsoft.com/download/details.aspx?id=45485) som en startpunkt. Kom ihåg Microsoft 365 behöver kolumnrubriker på den första raden så att du inte ersätter dem med något annat. 
  
Spara filen med ett nytt namn och ange CSV-format.
  
![En bild om hur du sparar en fil i Excel i CSV-format](../media/35a86ebe-63ab-4b4d-9a92-e177de33ebae.png)
  
När du sparar filen visas antagligen ett meddelande om att vissa funktioner i arbetsboken kan gå förlorade om du sparar filen i CSV-format. Det är OK. Klicka på **Ja** för att fortsätta.
  
![En bild av frågan som du eventuellt får i Excel och som frågar om du verkligen vill spara filen i CSV-format](../media/51032a81-690c-45ef-bfc5-09ea7f790e98.png)
  
### <a name="tips-for-formatting-your-spreadsheet"></a>Tips på hur du formaterar kalkylbladet

- **Behöver jag samma kolumnrubriker som i exempelkalkylbladet?** Ja. Exempelkalkylbladet innehåller kolumnrubriker på första raden. De här rubrikerna är obligatoriska. För varje användare som du vill lägga till Microsoft 365 skapar du en rad under rubriken. Om du lägger till, ändrar eller tar bort någon kolumnrubrik kanske Microsoft 365 inte kan skapa användare från informationen i filen.

- **Vad gör jag om jag inte har all information som behövs om en användare?** Fälten Användarnamn och Visningsnamn är obligatoriska, och du kan inte lägga till en ny användare om du inte har de uppgifterna. Om du saknar någon annan uppgift, till exempel faxnummer, kan du lägga in ett blanksteg och ett kommatecken för att visa att fältet ska vara tomt.

- **Hur litet eller stort får kalkylbladet vara?** Kalkylbladet måste innehålla minst två rader. One is for the column headings (the user data column label) and one for the user. You cannot have more than 251 rows. If you need to import more than 250 users, you can create more than one spreadsheet.

- **Vilka språk kan jag använda?** När du skapar kalkylbladet kan du ange kolumnetiketter för användardata på alla språk och tecken, men du får inte ändra ordningen på etiketterna, som visas i exemplet. Sedan kan du lägga in data i fälten, på vilket språk och med vilka tecken som helst, och spara filen i Unicode- eller UTF-8-format.

- **Vad gäller om jag lägger till användare från andra länder och regioner?** Skapa ett separat kalkylblad för varje område. Du måste gå igenom guiden Lägg till användare i grupp för varje kalkylblad, och då ange en enda plats för alla användare som ingår i den fil du arbetar med.

- **Finns det någon begränsning för hur många tecken jag kan använda?** I följande tabell visas kolumnetiketter för användardata med motsvarande maximalt antal tecken i exempelkalkylbladet.

|**Kolumnetikett med användardata**|**Maximalt antal tecken**|
|:-----|:-----|
|Användarnamn (obligatoriskt)  <br/> |79 inklusive at-tecknet (@), i det format som name@domain. \<extension\> . Användarens alias får inte vara längre än 50 tecken och domännamn får inte vara längre än 48 tecken.  <br/> |
|Förnamn  <br/> |64  <br/> |
|Efternamn  <br/> |64  <br/> |
|Visningsnamn (obligatoriskt)  <br/> |256  <br/> |
|Befattning  <br/> |64  <br/> |
|Avdelning  <br/> |64  <br/> |
|Kontorsnummer  <br/> |128  <br/> |
|Telefonnr till arbetet  <br/> |64  <br/> |
|Mobiltelefon  <br/> |64  <br/> |
|Fax  <br/> |64  <br/> |
|Adress  <br/> |1023  <br/> |
|Ort  <br/> |128  <br/> |
|Region  <br/> |128  <br/> |
|Postnummer  <br/> |40  <br/> |
|Land eller region  <br/> |128  <br/> |

### <a name="still-having-problems-when-adding-users-to-microsoft-365"></a>Har du fortfarande problem med att lägga till användare i Microsoft 365?

- **Kontrollera en extra gång att kalkylbladet är rätt formaterat.** Kontrollera kolumnrubrikerna och se till att de överensstämmer med rubrikerna i exempelfilen. Se till att du följer reglerna om maximalt antal tecken och att varje fält avgränsas med ett komma.

- **Vänta några minuter om du inte ser de nya Microsoft 365 på en gång.** Det kan ta en stund innan ändringarna har gjorts i alla tjänster i Microsoft 365. 

## <a name="related-articles"></a>Relaterade artiklar

[Lägga till användare individuellt eller flera samtidigt i Microsoft 365](/office365/admin/add-users/add-users)