---
title: Återskapa borttagna objekt i en användar post låda
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BCS160
ms.assetid: eb15194b-63ec-41b0-8d90-1823d3f558e4
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-apr2020
description: Den här artikeln innehåller information som administratörer kan använda för att återställa borttagna objekt om de inte har tagits bort permanent från post lådan.
ms.openlocfilehash: a4755e592182d93c37a241958ba37c95d1565cdc
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694403"
---
# <a name="recover-deleted-items-in-a-user-mailbox"></a>Återskapa borttagna objekt i en användar post låda

**Den här artikeln gäller för administratörer. Försöker du återställa borttagna objekt i din egen post låda?** Prova något av följande:
- [Återskapa borttagna objekt i Outlook för Windows](https://support.office.com/article/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)
- [Återskapa borttagna objekt eller e-post i Outlook Web App](https://support.office.com/article/c3d8fc15-eeef-4f1c-81df-e27964b7edd4)
- [Återställa borttagna e-postmeddelanden i Outlook på webben](https://support.office.com/article/a8ca78ac-4721-4066-95dd-571842e9fb11)
- [Outlook.com](https://go.microsoft.com/fwlink/p/?LinkID=623435)
   
Tog en användare permanent att ta bort objekt från post lådan i Outlook? Användaren vill ha tillbaka dem men kan inte återställa dem. Du kanske kan återställa borttagna objekt om de inte har tagits bort permanent från användarens post låda. Det gör du genom att använda eDiscovery-verktyget i Exchange Online för att söka efter borttagna e-postmeddelanden och andra objekt – och till exempel kontakter, kalender möten och uppgifter – i en användares post låda. Om du hittar borttagna objekt kan du exportera dem till en PST-fil (kallas även för en Outlook-datafil) som användaren sedan kan använda för att återställa objekten till post lådan.
  
Här är de här stegen för att återställa borttagna objekt i en användares post låda. Hur lång tid tar det? Första gången kan det ta 20 eller 30 minuter att slutföra alla stegen, beroende på hur många objekt du försöker återställa.
  
> [!NOTE]
> Du måste vara Exchange- **administratör** eller **Global administratör** i Microsoft 365 eller vara medlem i roll gruppen organisations hantering i Exchange Online för att kunna utföra stegen i den här artikeln. Mer information finns i [Om Microsoft 365-administratörsroller](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d). 
  
## <a name="step-1-assign-yourself-ediscovery-permissions"></a>Steg 1: tilldela dig själv eDiscovery-behörigheter
<a name="step1"> </a>

Det första steget är att tilldela dig själv nödvändiga behörigheter i Exchange Online, så att du kan använda det på plats eDiscovery för att söka i en användares post låda. Du behöver bara göra detta en gång. Om du behöver söka efter en annan post låda i framtiden kan du hoppa över det här steget.
  
1. [Här loggar du in i Microsoft 365 för företag](https://support.microsoft.com/office/where-to-sign-into-microsoft-365-for-business-e9eb7d51-5430-4929-91ab-6157c5a050b4) med ditt arbets-eller skol konto. 
    
2. Välj ikonen för Start programmet Start ![ ikonen i Microsoft 365 ](../media/7502f4ec-3c9a-435d-a7b4-b9cda85189a7.png) i det övre vänstra hörnet och klicka på **administratör**.
    
3. I det vänstra navigerings fältet i administrations centret för Microsoft 365 expanderar du **administrations**Center och klickar sedan på **Exchange**.
    
    ![Listan administrations Center](../media/7d308eb7-ba63-4156-a845-3770facc5de4.PNG)
  
4. I Exchange Admin Center klickar du på **behörigheter**och sedan på **Administratörs roller**.
    
5. I listvyn väljer du **identifierings hantering**och klickar sedan på **Redigera** ![ redigerings ikon ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) .
    
    ![Lägga till dig själv i roll gruppen identifierings hantering i UK](../media/e5c98e93-d6a0-40c5-a143-bac956eedaa7.png)
  
6. Klicka på **Lägg**till ikon under **medlemmar**i **roll gruppen** ![ ](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) .
    
7. I **Välj medlemmar**väljer du dig själv från listan med namn, klickar på **Lägg till**och sedan på **OK**.
    
    > [!NOTE]
    > Du kan också lägga till en grupp som du är medlem i, till exempel organisations hantering eller TenantAdmins. Om du lägger till en grupp tilldelas andra medlemmar i gruppen de behörigheter som krävs för att köra eDiscovery-verktyget på plats. 
  
8. Klicka på **Spara**i **roll grupp**.
    
9. Logga ut från Microsoft 365.
    
    Du måste logga ut innan du börjar nästa steg så att den nya behörigheten börjar gälla.
    
> [!CAUTION]
> Medlemmar i roll gruppen identifierings hantering kan komma åt känsligt meddelande innehåll. Detta inkluderar sökning i alla post lådor i organisationen, för att förhandsgranska Sök resultaten (och andra objekt i post lådan), kopiera resultatet till en identifierings post låda och exportera Sök resultatet till en PST-fil. 
  
[Return to top](recover-deleted-items-in-a-mailbox.md)
  
## <a name="step-2-search-the-users-mailbox-for-deleted-items"></a>Steg 2: Sök efter borttagna objekt i användarens post låda
<a name="step2"> </a>

När du kör en eDiscovery-sökning på plats tas mappen återställnings bara objekt i den post låda som du söker automatiskt med i sökningen. Mappen återställnings bara objekt är den plats där permanent borttagna objekt lagras tills de tas bort (permanent borttagna) från post lådan. Om ett objekt inte har rensats bör du kunna hitta det med hjälp av eDiscovery-verktyget på plats.
  
1. [Här loggar du in i Microsoft 365 för företag](https://support.microsoft.com/office/where-to-sign-into-microsoft-365-for-business-e9eb7d51-5430-4929-91ab-6157c5a050b4) med ditt arbets-eller skol konto. 
    
2. Välj ikonen för Start programmet Start ![ ikonen i Microsoft 365 ](../media/7502f4ec-3c9a-435d-a7b4-b9cda85189a7.png) i det övre vänstra hörnet och klicka på **administratör**.
    
3. I det vänstra navigerings fältet i administrations centret för Microsoft 365 expanderar du **admin**och klickar sedan på **Exchange**.
    
4. Klicka på **hantering av efterlevnad**i administrations centret för Exchange, klicka på **i ett eDiscovery- &amp; undantag**och klicka sedan på **ny**ikon för att ![ lägga till ](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) .
    
    ![Klicka på lokal eDiscovery och håll ned på sidan Compliance Management i UK](../media/9d9ff0f5-b9be-45b8-8b5e-6037a856b0a8.png)
  
5. Skriv ett namn för sökningen (till exempel namnet på den användare som du återställer e-post för) på sidan **namn och beskrivning** och klicka sedan på **Nästa**.
    
6. Klicka på **Ange post lådor att söka efter**på sidan **post lådor** och klicka sedan på **Lägg till** ![ ikonen Lägg till ](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) .
    
    ![Klicka på Ange post lådor för att söka efter en specifik-postlåda](../media/83879a40-5e5c-49a8-be3b-c0023d197588.png)
  
7. Leta reda på och välj namnet på den användare som du återställer det borttagna e-postmeddelandet för, klicka på **Lägg till**och sedan på **OK**.
    
8. Klicka på **Nästa**.
    
    Sidan **Sök fråga** visas. Här definierar du Sök villkoren som hjälper dig att hitta de saknade objekten i användarens post låda. 
    
9. Fyll i följande fält på sidan **Sök fråga** : 
    
  - **Ta med allt innehåll** Välj det här alternativet om du vill inkludera allt innehåll i användarens post låda i Sök resultatet. Om du väljer det här alternativet kan du inte ange fler Sök villkor. 
    
  - **Filter utifrån villkor** Välj det här alternativet om du vill ange Sök villkor, inklusive nyckelord, start-och slutdatum, avsändare och mottagar adresser samt meddelande typer. 
    
    ![Skapa en sökning utifrån villkor som nyckelord, datum intervall, mottagare och meddelande typer](../media/ee47b833-9122-46a0-85e6-fcbe25be0dd5.png)
  
|**Fält**|**Använd detta för att...**|
|:-----|:-----|
|![Nummer ett i en rosa cirkel](../media/a4da261d-2516-48c5-b58a-9c452b9086b8.png)           <br/> |Ange nyckelord, datum intervall, mottagare och meddelande typer.  <br/> |
|![Nummer två i en rosa cirkel.](../media/de3c1ab4-4f01-4026-b1ba-3265bdb32a89.png)           <br/> |Sök efter meddelanden med nyckelord eller fraser och Använd logiska operatorer som **och** eller **eller**.  <br/> |
|![Nummer tre i en rosa cirkel.](../media/60fa378c-6ac1-4cbd-a782-2fa7ca619dc6.png)           <br/> |Sök efter meddelanden som skickats eller tagits emot inom ett datum intervall.  <br/> |
|![Nummer 4 i en rosa cirkel.](../media/1a0ff2ce-0942-405a-94e3-9bfeb1e5059e.png)           <br/> |Sök efter meddelanden som tas emot från eller skickas till vissa personer.  <br/> |
|![Nummer fem i en rosa cirkel.](../media/878cc815-0165-49ba-a1ee-9236e5980403.png)           <br/> |Sök efter alla meddelande typer eller Välj specifika.  <br/> |
   
   > [!TIP]
   >  Här är några tips om hur du skapar en Sök fråga för att hitta saknade objekt. Försök att få så mycket information från användaren som hjälper dig att skapa en Sök fråga så att du kan hitta det du letar efter. Om du inte är säker på hur du hittar ett meddelande som saknas kan du använda alternativet **Inkludera allt innehåll** . Sök resultatet inkluderar alla objekt i användarens mapp för återställnings bara objekt, inklusive den dolda mappen (kallas mappen rensar) som innehåller objekt som har tömts av användaren. Sedan kan du gå till steg 3, kopiera resultatet till en Discovery-postlåda och titta på meddelandet i den dolda mappen. Om du vet ungefär när det saknade meddelandet ursprungligen skickades eller togs emot av användaren använder du alternativen **Ange start datum** och **Ange slutdatum** för att ange ett datum intervall. Då returneras alla meddelanden som skickas eller tas emot av användaren inom det datum intervallet. Att ange ett datum intervall är ett mycket bra sätt att begränsa Sök resultaten. Om du vet vem som har skickat den saknade e-postmeddelandet, Använd rutan **från** för att ange den avsändaren. Om du vill begränsa Sök resultaten till olika typer av post lådor klickar du på **Välj meddelande typer**, klickar på **Välj meddelande typer för att söka**och väljer sedan en specifik meddelande typ att söka efter. Du kan till exempel bara söka efter Kalender objekt eller kontakter. Här är en skärm bild av de olika meddelande typer som du kan söka efter; Standardinställningen är att söka efter alla meddelande typer. 
  
   Klicka på **Nästa** när du är klar med sidan **Sök fråga** . 
    
10. På sidan **in-Place Hold-inställningar** klickar du på **Slutför** för att starta sökningen. För att återställa borttagna e-postmeddelanden finns det ingen anledning att hålla användarens post låda stoppad. 
    
    När du har startat sökningen visar Exchange en uppskattning av den totala storleken och antalet objekt som returneras av sökningen baserat på de kriterier du angett.
    
11. Välj den sökning du just har skapat och klicka på **Uppdatera** ![ uppdatering ](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) för att uppdatera informationen som visas i informations fönstret. Statusen för **uppskattningen lyckades** indikerar att sökningen är klar. Dessutom visar Exchange en uppskattning av det totala antalet objekt (och storlek) som hittats i sökningen baserat på Sök villkoren du angav i steg 9. 
    
12. Klicka på **Förhandsgranska Sök Resultat** i informations fönstret för att visa de objekt som hittades. Det här kan hjälpa dig att identifiera de objekt som du letar efter. Om du hittar de objekt du försöker återställa går du till steg 4 för att exportera Sök resultaten till en PST-fil. 
    
    ![Klicka på Förhandsgranska Sök Resultat för att visa det objekt du försöker återställa](../media/a2cea921-dafa-45d6-97d4-ae45a226b8d3.png)
  
13. Om du inte hittar det du letar efter kan du ändra Sök villkoren genom att välja Sök, klicka på **Redigera** ![ Redigera ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) -ikonen och sedan klicka på **Sök fråga**. Ändra Sök villkoren och kör sedan sökningen igen.
    
[Return to top](recover-deleted-items-in-a-mailbox.md)
  
## <a name="optional-step-3-copy-the-search-results-to-a-discovery-mailbox"></a>Skriver Steg 3: kopiera Sök resultatet till en identifierings post låda
<a name="step3"> </a>

Om du inte kan hitta ett objekt genom att förhandsgranska Sök resultaten eller om du vill se vilka objekt som finns i användarens mapp för återställnings bara objekt kan du kopiera Sök resultaten till en särskild post låda (kallas för en identifierings post låda) och sedan öppna den post lådan i Outlook på webben för att visa de faktiska objekten. Det bästa skälet till att kopiera Sök resultaten är att visa objekten i användarens mapp för återställnings bara objekt. Mer än troligt vis finns objektet du försöker återställa finns i undermappen rensar. 
  
1. I Exchange Admin Center går du till **hantering** \> **av efterlevnadsprincip på plats &amp; **.
    
2. I listan med sökningar väljer du den sökning som du skapade i steg 2.
    
3. Klicka på **Sök** ![ ](../media/c94e8591-7044-4650-a0d1-c57c0633ab4f.png) och sedan på **Kopiera Sök Resultat** i list rutan. 
    
    ![Klicka på Sök och sedan på Kopiera Sök Resultat](../media/7888df82-94b4-4e44-8a53-f66854dc7c86.png)
  
4. Klicka på **Bläddra**på sidan **Kopiera Sök Resultat** .
    
    ![Lämna kryss rutor omarkerade när borttagna objekt återställs](../media/37f27999-a5b2-4fed-87e2-bad6dc23cdae.png)
  
5. Klicka på **post låda för identifierings sökning**under **visnings namn**och klicka sedan på **OK**.
    
    ![Kopiera Sök resultatet till post lådan för standard sökning](../media/36e8ef47-0035-4982-9ed6-426719c5f9ec.png)
  
    > [!NOTE]
    > Identifierings post lådan är en standard Sök brev låda som skapas automatiskt i din Microsoft 365-organisation. 
  
6. Klicka på **Kopiera** på sidan **Kopiera Sök Resultat** för att starta processen för att kopiera Sök resultatet till post lådan för identifierings sökning. 
    
    ![Klicka på Kopiera för att kopiera Sök resultatet till post lådan för identifierings sökning](../media/71307a9d-f7a1-4e01-ae37-1d49040cc3fd.png)
  
7. Klicka på **Uppdatera** ![ uppdatering ](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) för att uppdatera informationen om den kopierings status som visas i informations fönstret. 
    
8. När kopieringen är klar klickar du på **Öppna** för att öppna post lådan för identifierings sökning för att Visa Sök resultaten. 
    
    ![Klicka på öppna för att gå till post lådan för identifierings sökning för att Visa Sök resultaten](../media/6cc81e0f-ceed-4464-9040-79b6f920de35.png)
  
    Sök resultatet som kopierats till post lådan för identifierings sökning placeras i en mapp som har samma namn som den eDiscovery-sökning som finns på plats. Du kan klicka på en mapp för att visa objekten i den mappen.
    
    ![Sök resultat i post lådan för identifierings sökning; objekt i mappen rensningar kan endast återställas av en administratör](../media/2ef8e5fb-3e63-4f62-938e-307efe9f6998.gif)
  
    När du kör en sökning genomsöks också användarens mapp för återställnings bara objekt. Det innebär att om objekt i mappen för att återställa objekt motsvarar Sök villkoren inkluderas de i Sök resultaten. Objekt i mappen borttagningar är objekt som användaren permanent tar bort (genom att ta bort ett objekt från mappen Borttaget eller genom att klicka på **SKIFT + DELETE**. En användare kan använda verktyget Återställ borttagna objekt i Outlook eller Outlook på webben för att återskapa objekt i mappen Borttaget. Objekt i mappen rensar är objekt som användaren har rensat med verktyget Återställ borttagna objekt eller objekt som de rensades automatiskt av en princip som lagts till i post lådan. I båda fallen kan bara administratörer återskapa objekt i mappen rensningar. 
    
    > [!TIP]
    > Om en användare inte kan hitta ett borttaget objekt med hjälp av verktyget återställnings bara objekt, men objektet är fortfarande återställbart (vilket innebär att det inte har tagits bort permanent från post lådan) är det mer än troligt i mappen rensningar. Se till att du letar i mappen rensningar för det borttagna objekt som du försöker återställa för en användare. 
  
[Return to top](recover-deleted-items-in-a-mailbox.md)
  
## <a name="step-4-export-the-search-results-to-a-pst-file"></a>Steg 4: exportera Sök resultatet till en PST-fil
<a name="step4"> </a>

När du hittar objektet du försöker återställa för en användare är nästa steg att exportera resultaten från den sökning du körde i steg 2 till en PST-fil. Användaren kommer att använda den här PST-filen i nästa steg för att återställa det borttagna objektet till post lådan.
  
1. I Exchange Admin Center går du till **hantering** \> **av efterlevnadsprincip på plats &amp; **.
    
2. I listan med sökningar väljer du den sökning som du skapade i steg 2.
    
3. Klicka på **Exportera till en PST-fil**.
    
    ![Klicka på Exportera till en PST-fil](../media/4e59ae17-4541-43f4-a6d1-1f8b9ba9404b.png)
  
4. Om du uppmanas att installera verktyget för eDiscovery-export klickar du på **Kör**.
    
5. I export verktyget för det här eDiscovery-programmet klickar du på **Bläddra** och anger den plats där du vill ladda ned PST-filen. 
    
    ![Export verktyget för eDiscovery-PST](../media/17274d27-992e-4034-8133-8f793f554e6c.png)
  
    Du kan ignorera alternativen för att aktivera avduplicering och ta med sökbara objekt.
    
6. Klicka på **Start** för att ladda ned PST-filen till datorn. 
    
    I import **verktyget för eDiscovery-PST** visas statusinformation om exporten. När exporten är klar kan du komma åt filen på den plats där den laddades ned. 
    
[Return to top](recover-deleted-items-in-a-mailbox.md)
  
## <a name="step-5-restore-the-recovered-items-to-the-users-mailbox"></a>Steg 5: återställa återställda objekt till användarens post låda
<a name="step5"> </a>

Det sista steget är att använda PST-filen som exporterades i steg 4 för att återställa de återställda objekten till användarens post låda. När du har skickat PST-filen till användaren utförs resten av det här steget av användaren för att öppna PST-filen och sedan flytta de återställda objekten till en annan mapp i post lådan. Stegvisa anvisningar kan du också skicka en länk till det här avsnittet: [öppna och Stäng Outlook-datafiler (. pst)](https://support.office.com/article/381b776d-7511-45a0-953a-0935c79d24f2). Eller så kan du skicka en länk till användaren [Återställ borttagna objekt till en post låda med hjälp av en PST-fil](recover-deleted-items-in-a-mailbox.md#restoredeleteditems) nedan och be dem att utföra de här stegen. 
  
 **Skicka PST-filen till användaren**
  
Det sista steget som du måste utföra när du skickar PST-filen som exporterades i steg 4 till användaren. Det finns några olika sätt att göra detta:
  
- Bifoga PST-filen i ett e-postmeddelande. Om Outlook är konfigurerat för att blockera PST-filer måste du zippa filen och sedan bifoga den i meddelandet. Så här gör du:
    
1. Bläddra till PST-filen i Utforskaren i Windows.
    
2. Högerklicka på filen och välj sedan **Skicka till** \> **komprimerad mapp**. Windows skapar en ny zip-fil och ger den ett identiskt namn som PST-fil.
    
3. Bifoga den komprimerade PST-filen i ett e-postmeddelande och skicka den till användaren, som sedan kan expandera filen genom att klicka på den.
    
- Kopiera PST-filen till en delad mapp som användaren kan komma åt och hämta.
    
Stegen i nästa avsnitt utförs av användaren för att återställa borttagna objekt till post lådan.
  
 <a name="restoredeleteditems"></a>
**Återställa borttagna objekt till en post låda med hjälp av en PST-fil**
  
Du måste använda Outlook-programmet för att återställa ett borttaget objekt med hjälp av en PST-fil. Du kan inte använda Outlook Web App eller Outlook på webben för att öppna en PST-fil.
  
1. Klicka på fliken **Arkiv** i Outlook 2013 eller Outlook 2016. 
    
2. Klicka på **Öppna &amp; export**och sedan på **Öppna Outlook-datafil**.
    
3. Bläddra till den plats där du sparade PST-filen som administratören skickade.
    
4. Markera PST-filen och klicka på **Öppna**.
    
    PST-filen visas i det vänstra navigerings fältet i Outlook.
    
    ![PST-filen visas i det vänstra navigerings fältet i Outlook](../media/c9389392-d08a-4aa7-848c-4986d448b0f2.png)
  
5. Klicka på pilarna för att expandera PST-filen och mapparna under den för att hitta det objekt du vill återställa.
    
    ![Leta i mappen rensningar för det objekt som du vill återställa](../media/d4e372d9-ac23-4e95-8639-d8da690fefa7.png)
  
    > [!TIP]
    > Leta i mappen rensningar för det objekt du vill återställa. Det här är en dold mapp där borttagna objekt flyttas till. Det objekt som administratören har återskapat finns i den här mappen. 
  
6. Högerklicka på objektet som du vill återställa och klicka sedan på **Flytta** \> **andra mappen**.
    
    ![Klicka på flytta och välj sedan annan mapp](../media/090063df-2aa0-444a-8e47-abd6fe6cf7a8.png)
  
7. Om du vill flytta objektet till Inkorgen klickar du på **Inkorgen**och sedan på **OK**.
    
    **Tips:** Gör något av följande om du vill återställa andra typer av objekt: 
    
  - Om du vill återställa ett Kalender objekt högerklickar du på det och klickar sedan på **Flytta** \> **annan** \> **kalendermapp**.
    
  - Om du vill återställa en kontakt högerklickar du på den och klickar sedan på **Flytta** \> **andra** \> **kontakter**.
    
  - Om du vill återställa en uppgift högerklickar du på den och klickar sedan på **Flytta** \> **andra mappaktiviteter** \> **Tasks**.
    
![Välj en mapp för att flytta andra typer av objekt](../media/f8290131-43f2-46f1-bc07-228c2d83b96c.png)
  
   > [!NOTE]
   > Kalender objekt, kontakter och uppgifter placeras direkt i mappen rensa och inte i en mapp för kalender, kontakter eller uppgifter. Du kan sortera efter **typ** för att gruppera liknande typer av objekt. 
    
8. När du är klar med att återställa borttagna objekt högerklickar du på PST-filen i det vänstra navigerings fältet och väljer **Stäng "namn på PST-fil"**.
    
[Return to top](recover-deleted-items-in-a-mailbox.md)
  
## <a name="more-information"></a>Mer information
<a name="moreinfo"> </a>

- Det kan vara möjligt för en användare att återställa ett permanent borttaget objekt om objektets lagrings period för borttagna artiklar inte har gått ut. Som administratör kan du ha angett hur länge objekt i mappen för återställnings bara objekt är tillgängliga för återställning. Det kan till exempel finnas en policy som tar bort allt som finns i en användares borttagna objekt-mappen i 30 dagar, och en annan princip som gör att användare kan återskapa objekt i mappen för återställnings bara objekt i upp till en annan 14 dagar. Men efter den här 14 dagarna kan du fortfarande kunna återskapa ett objekt i en användares post låda genom att följa procedurerna i det här avsnittet.
    
- Användare kan återställa ett borttaget objekt om det inte har tagits bort och om den lagrings tid för borttaget objekt inte har gått ut. Om du vill hjälpa användare att återställa borttagna objekt i post lådan pekar du på något av följande avsnitt:
    
  - [Återskapa borttagna objekt i Outlook för Windows](https://support.office.com/article/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)
    
  - [Återskapa borttagna objekt i Outlook 2010](https://support.office.com/article/cd9dfe12-8e8c-4a21-bbbf-4bd103a3f1fe)
    
  - [Återskapa borttagna objekt eller e-post i Outlook Web App](https://support.office.com/article/c3d8fc15-eeef-4f1c-81df-e27964b7edd4)
    
  - [Återställa borttagna e-postmeddelanden i Outlook på webben](https://support.office.com/article/a8ca78ac-4721-4066-95dd-571842e9fb11)
    
  - [Återställa en borttagen kontakt i Outlook](https://support.office.com/article/51c83288-6888-4dcd-8c99-4932daabf643)
    
  - [Återställa borttagna e-postmeddelanden i Outlook.com](https://go.microsoft.com/fwlink/p/?LinkID=623435)
    
[Return to top](recover-deleted-items-in-a-mailbox.md)
  

