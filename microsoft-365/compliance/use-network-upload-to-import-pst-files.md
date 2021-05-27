---
title: Använda nätverksuppladdning för att importera organisationens PST-filer
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
- MED150
- MET150
ms.assetid: 103f940c-0468-4e1a-b527-cc8ad13a5ea6
description: 'För administratörer: Lär dig hur du använder nätverksuppladdning för att massimportera flera PST-filer till användarpostlådor i Microsoft 365.'
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ebbc9b080bf42ef309741dc8bfa4283df9776902
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684007"
---
# <a name="use-network-upload-to-import-your-organizations-pst-files-to-microsoft-365"></a>Använda nätverksuppladdning för att importera organisationens PST-filer till Microsoft 365

> [!NOTE]
> Den här artikeln är avsedd för administratörer. Försöker du importera PST-filer till din egen postlåda? Se [Importera e-post, kontakter och kalender från en Outlook .pst-fil](https://go.microsoft.com/fwlink/p/?LinkID=785075)
  
Här hittar du de stegvisa instruktioner som krävs för att använda nätverksuppladdning för att massimportera flera PST-filer till Microsoft 365-postlådor. Vanliga frågor och svar om hur du använder nätverksuppladdning för att massimportera PST-filer till Microsoft 365-postlådor finns i [Vanliga frågor och svar om hur du använder nätverksuppladdning för att importera PST-filer](./faqimporting-pst-files-to-office-365.yml#using-network-upload-to-import-pst-files).
  
[Steg 1: Kopiera SAS-URL och installera AzCopy](#step-1-copy-the-sas-url-and-install-azcopy)

[Steg 2: Ladda upp PST-filerna till Microsoft 365](#step-2-upload-your-pst-files-to-office-365)

[(Valfritt) Steg 3: Visa en lista över de PST-filer som har laddats upp](#optional-step-3-view-a-list-of-the-pst-files-uploaded-to-office-365)

[Steg 4: Skapa mappningsfilen för PST-import](#step-4-create-the-pst-import-mapping-file)

[Steg 5: Skapa ett PST-importjobb](#step-5-create-a-pst-import-job)

[Steg 6: Filtrera data och starta PST-importjobbet](#step-6-filter-data-and-start-the-pst-import-job)

Du behöver bara utföra steg 1 en gång för att importera PST-filer till Microsoft 365-postlådor. När du har utfört de här stegen följer du steg 2 till steg 6 varje gång du vill ladda upp och importera en uppsättning PST-filer.

## <a name="before-you-import-pst-files"></a>Innan du importerar PST-filer
  
- Du måste vara tilldelad rollen Import/export av postlåda i Exchange Online för att kunna importera PST-filer till Microsoft 365-postlådor. Som standard är den här rollen inte tilldelad någon rollgrupp i Exchange Online. Du kan lägga till rollen Import/export av postlåda i rollgruppen Organisationshantering. Eller så kan du skapa en rollgrupp, tilldela rollen Import/export av postlåda och sedan lägga till dig själv som medlem. Mer information finns i avsnitten ”Lägg till en roll i rollgrupp” och ”Skapa en rollgrupp” i [Hantera rollgrupper](/Exchange/permissions-exo/role-groups).

    Om du ska skapa importjobb i Microsoft 365 Efterlevnadscenter måste dessutom något av följande stämma:

  - Du har tilldelats rollen E-postmottagare i Exchange Online. Som standard är den här rollen tilldelad rollgrupperna Organisationshantering och Hantering av mottagare.

    Eller

  - Du måste vara global administratör i din organisation.

  > [!TIP]
    > Överväg att skapa en ny rollgrupp i Exchange Online som är specifikt avsedd att användas för importering av PST-filer. För den lägsta nivån av behörighet som krävs för att importera PST-filer tilldelar du rollerna Import/export av postlåda och E-postmottagare till den nya rollgruppen och lägger sedan till medlemmar.
  
- Den enda metoden som stöds för att importera PST-filer till Microsoft 365 är att använda AzCopy-verktyget enligt beskrivningen i den här artikeln. Du kan inte använda Azure Storage Explorer för att ladda upp PST-filer direkt till Azure Storage-området.

- Du måste lagra de PST-filer du vill importera till Microsoft 365 på en filserver eller i en delad mapp i organisationen. I steg 2 kör du AzCopy-verktyget för att ladda upp PST-filer som lagras på en filserver eller i en delad mapp till Microsoft 365.

- Stora PST-filer kan påverka prestandan för PST-importprocessen. Vi rekommenderar därför att varje PST-fil du laddar upp till Azure Storage-platsen i steg 2 inte är större än 20 GB.

- I den här proceduren ingår att kopiera och spara en kopia av en URL som innehåller en åtkomstnyckel. Den här informationen används i steg 2 för att ladda upp PST-filerna och i steg 3 om du vill visa en lista över de PST-filer som laddats upp till Office 365. Se till att vidta försiktighetsåtgärder för att skydda denna URL på samma sätt som du skyddar lösenord eller annan säkerhetsrelaterad information. Du kan till exempel spara den i ett lösenordsskyddat Microsoft Word-dokument eller på en krypterad USB-enhet. I avsnittet [Mer information](#more-information) finns ett exempel på den här kombinerade URL:en och nyckeln.

- Du kan importera PST-filer till en inaktiv postlåda i Office 365. Det gör du genom att ange GUID för den inaktiva postlådan i parametern  `Mailbox` i mappningsfilen för PST-import. Mer information finns i steg 4 på fliken **Instruktioner** i den här artikeln.

- I en Exchange-hybriddistribution kan du importera PST-filer till en molnbaserad arkivpostlåda för en användare vars primära postlåda är lokal. Det gör du genom att göra följande i mappningsfilen för PST-import:

  - Ange e-postadressen för användarens lokala postlåda i parametern  `Mailbox`.

  - Ange värdet **TRUE** i parametern  `IsArchive`.

    Mer information finns i [steg 4](#step-4-create-the-pst-import-mapping-file).

- När PST-filer har importerats aktiveras inställningen för kvarhållningsundantag för postlådan på obestämd tid. Det innebär att den kvarhållningsprincip som tilldelats postlådan inte bearbetas förrän du inaktiverar kvarhållningsundantaget eller anger ett datum då undantaget ska inaktiveras. Varför gör vi det här? Om meddelanden som importerats till en postlåda är gamla kanske de tas bort permanent (rensas) eftersom deras kvarhållningsperiod har upphört att gälla baserat på de kvarhållningsinställningar som har konfigurerats för postlådan. Om ett kvarhållningsundantag tillämpas för postlådan ger det postlådans ägare tid att hantera de nya importerade meddelandena eller dig tid att ändra kvarhållningsinställningarna för postlådan. I avsnittet [Mer information](#more-information) i den här artikeln finns förslag på hur du hanterar kvarhållningsundantaget.

- Som standard är den största meddelandestorleken som kan tas emot av en Microsoft 365-postlåda 35 MB. Det beror på att standardvärdet för egenskapen  *MaxReceiveSize*  för en postlåda är inställt på 35 MB. Gränsen för den största storleken för mottagna meddelanden i Microsoft 365 är 150 MB. Så om du importerar en PST-fil som innehåller ett objekt som är större än 35 MB ändrar Office 365-importtjänsten automatiskt värdet för egenskapen  *MaxReceiveSize*  för målpostlådan till 150 MB. Tack vare detta kan meddelanden på upp till 150 MB importeras till användarnas postlådor.

    > [!TIP]
    > Om du vill identifiera storleken för mottagna meddelanden för en postlåda kan du köra det här kommandot i Exchange Online PowerShell:  `Get-Mailbox <user mailbox> | FL MaxReceiveSize`.

- En översikt över PST-importprocessen finns i [Så här fungerar importeringsprocessen](#how-the-import-process-works) i den här artikeln.

## <a name="step-1-copy-the-sas-url-and-install-azcopy"></a>Steg 1: Kopiera SAS-URL och installera AzCopy

Det första steget är att ladda ned och installera AzCopy-verktyget, som är det verktyg du kör i steg 2 för att ladda upp PST-filer till Office 365. Du kopierar även SAS-URL:en för organisationen. Denna URL är en kombination av nätverks-URL:en för Azure Storage-platsen i Microsoft-molnet för din organisation och en SAS-nyckel (signatur för delad åtkomst). Den här nyckeln ger dig nödvändiga behörigheter för att ladda upp PST-filer till Azure Storage-platsen. Se till att vidta försiktighetsåtgärder för att skydda SAS-URL:en. Den är unik för din organisation och används i steg 2.

> [!IMPORTANT]
> För att importera PST-filer med nätverksuppladdningsmetoden och kommandosyntaxen som beskrivs i den här artikeln måste du använda den version av AzCopy som kan laddas ned i steg 6b i följande procedur. Du kan också ladda ned samma version av AzCopy [här](https://aka.ms/downloadazcopy). Det går inte att använda en annan version av AzCopy.
  
1. Gå till <https://compliance.microsoft.com> och logga in med autentiseringsuppgifterna för ett administratörskonto i organisationen.

2. Klicka på **Informationsstyrning** \>**Importera** i vänster fönsterruta i Microsoft 365 Efterlevnadscenter.

    > [!NOTE]
    > Du måste ha tilldelats rätt behörigheter för att komma åt sidan **Importera** i Microsoft 365 Efterlevnadscenter. Mer information finns i avsnittet **Innan du börjar**. 

3. På fliken **Importera** klickar du på ikonen ![Lägg till](../media/ITPro-EAC-AddIcon.gif) **Nytt importjobb**.

    Guiden för importjobb visas.

4. Skriv ett namn för PST-importjobbet och klicka sedan på **Nästa**. Använd gemener, siffror, bindestreck och understreck. Du kan inte använda versaler eller blanksteg i namnet.

5. På sidan **Vill du ladda upp eller skicka dina data?** klickar du på **Ladda upp data** och sedan på **Nästa**.

    ![Klicka på Ladda upp data, så skapas ett importjobb för nätverksuppladdning](../media/e59f9dc3-ccde-44ff-ac38-c4e39d76ae85.png)
  
6. På sidan **Importera data** gör du följande två saker:

    ![Kopiera SAS-URL:en och ladda ned AzCopy-verktyget på sidan Importera data](../media/74411014-ec4b-4e25-9065-404c934cce17.png)
  
    1. I steg 2 klickar du på **Visa SAS-URL för uppladdning över nätverket**. När SAS-URL:en visas klickar du på **Kopiera till Urklipp** och klistrar sedan in och sparar den i en fil så att du kan komma åt den senare.

    2. I steg 3 klickar du på **Ladda ned Azure AzCopy** och laddar ned och installerar AzCopy-verktyget. I popup-fönstret klickar du på **Kör**, så installeras AzCopy.

   > [!NOTE]
   > Du kan lämna sidan **Importera data** öppen (ifall du behöver kopiera SAS-URL:en igen) eller klicka på **Avbryt** och stänga den. 

## <a name="step-2-upload-your-pst-files-to-office-365"></a>Steg 2: Ladda upp PST-filerna till Office 365

Nu är du redo att använda verktyget AzCopy.exe för att ladda upp PST-filer till Office 365. Med det här verktyget laddar du upp och lagrar PST-filer på en Azure Storage-plats i Microsoft-molnet. Som tidigare beskrivits finns Azure Storage-platsen som du laddar upp PST-filerna till i samma regionala Microsoft-datacenter som din organisation. För att slutföra det här steget måste PST-filerna finnas i en filresurs eller på en filserver i din organisation. Det här kallas för källkatalogen i den här proceduren. Varje gång du kör AzCopy-verktyget kan du ange en annan källkatalog.

> [!NOTE]
> Som tidigare nämnts ska varje PST-fil som du laddar upp till Azure Storage-platsen inte vara större än 20 GB. PST-filer som är större än 20 GB kan påverka prestandan för PST-importprocessen som du startar i steg 6. Dessutom måste varje PST-fil ha ett unikt namn.

1. Öppna Kommandotolken på den lokala datorn.

2. Gå till katalogen där du installerade verktyget AzCopy.exe i steg 1. Om du installerade verktyget på standardplatsen går du till `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy`.

3. Kör följande kommando och ladda upp PST-filerna till Office 365.

    ```powershell
    AzCopy.exe /Source:<Location of PST files> /Dest:<SAS URL> /V:<Log file location> /Y
    ```

    > [!IMPORTANT]
    > Du måste ange en katalog som källplats i det föregående kommandot. Du kan inte ange en enskild PST-fil. Alla PST-filer i källkatalogen laddas upp.

    I följande tabell beskrivs parametrarna för AzCopy.exe och deras obligatoriska värden. Den information du hämtade i föregående steg används i värdena för dessa parametrar.

    | Parameter | Beskrivning | Exempel |
    |:-----|:-----|:-----|
    | `/Source:` <br/> |Anger källkatalogen i din organisation som innehåller PST-filerna som ska laddas upp till Office 365.  <br/> Se till att omge värdet för den här parametern med dubbla citattecken (" ").  <br/> | `/Source:"\\FILESERVER01\PSTs"` <br/> |
    | `/Dest:` <br/> |Anger den SAS-URL du hämtade i steg 1.  <br/> Se till att omge värdet för den här parametern med dubbla citattecken (" ").<br/><br/>**Obs!** Om du använder SAS-URL:en i ett skript eller en batchfil måste du se upp med vissa tecken som måste markeras så att de tolkas rätt. Du måste till exempel ändra `%` till `%%` och ändra `&` till `^&`.<br/><br/>**Tips!** (Valfritt) Du kan ange en undermapp på Azure Storage-platsen som PST-filerna ska laddas upp till. Det gör du genom att lägga till en plats för en undermapp (efter ”ingestiondata”) i SAS-URL:en. I det första exemplet anges inte en undermapp. Det innebär att PST-filerna laddas upp till roten (med namnet  *ingestiondata*) på Azure Storage-platsen. I det andra exemplet laddas PST-filerna upp till en undermapp (med namnet  *PSTFiles*) i roten för Azure Storage-platsen.  <br/> | `/Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"` <br/> Eller  <br/>  `/Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata/PSTFiles?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"` <br/> |
    | `/V:` <br/> |Skriver utförliga statusmeddelanden till en loggfil. Som standard heter den utförliga loggfilen AzCopyVerbose.log i %LocalAppData%\Microsoft\Azure\AzCopy. Om du anger en befintlig filplats för det här alternativet läggs den utförliga loggen till i den filen.  <br/> Se till att omge värdet för den här parametern med dubbla citattecken (" ").  <br/> | `/V:"c:\Users\Admin\Desktop\Uploadlog.log"` <br/> |
    | `/S` <br/> |Den här valfria växeln anger rekursivt läge så att AzCopy-verktyget kopierar PST-filer som finns i undermappar i källkatalogen som anges av parametern  `/Source:`.  <br/> **Obs!** Om du tar med den här växeln har PST-filer i undermappar ett annat filsökvägsnamn på Azure Storage-platsen när de har laddats upp. Du måste ange den exakta filsökvägen i CSV-filen som du skapar i steg 4.  <br/> | `/S` <br/> |
    | `/Y` <br/> |Med den här obligatoriska växeln kan du använda SAS-tokens endast för skrivning när du laddar upp PST-filerna till Azure Storage-platsen. SAS-URL:en du hämtade i steg 1 (och angav i parametern  `/Dest:`) är en SAS-URL endast för skrivning, och det är därför du måste ta med den här växeln. En SAS-URL endast för skrivning hindrar dig inte från att använda Azure Storage Explorer för att visa en lista med PST-filer som laddats upp till Azure Storage-platsen.  <br/> | `/Y` <br/> |

Här är ett exempel på syntaxen för verktyget AzCopy.exe med faktiska värden för varje parameter:

```powershell
  AzCopy.exe /Source:"\\FILESERVER1\PSTs" /Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D" /V:"c:\Users\Admin\Desktop\AzCopy1.log" /Y
```

När du har kört kommandot visas statusmeddelanden som visar förloppet för uppladdningen av PST-filerna. Ett slutgiltigt statusmeddelande visar det totala antalet filer som har laddats upp.

> [!TIP]
> När du har kört kommandot AzCopy.exe och kontrollerat att alla parametrar är korrekta sparar du en kopia av kommandoradssyntaxen i samma (skyddade) fil där du kopierade informationen du hämtade i steg 1. Sedan kan du kopiera och klistra in det här kommandot i Kommandotolken varje gång du vill köra verktyget AzCopy.exe för att ladda upp PST-filer till Office 365. Det enda värdena du kan behöva ändra är värdena för parametern `/Source:`. Det här varierar beroende på källkatalogen där PST-filerna finns.

## <a name="optional-step-3-view-a-list-of-the-pst-files-uploaded-to-office-365"></a>(Valfritt) Steg 3: Visa en lista över de PST-filer som har laddats upp till Office 365

Som ett valfritt steg kan du installera och använda Microsoft Azure Storage Explorer (som är ett kostnadsfritt verktyg med öppen källkod) för att visa listan över PST-filer som du har laddat upp till Azure-blobben. Det finns två goda anledningar att göra detta:
  
- Kontrollera att PST-filer från den delade mappen eller filservern i organisationen har laddats upp till Azure-blobben.

- Kontrollera filnamnet (och sökvägen för undermappen om du har lagt till en sådan) för varje PST-fil som laddats upp till Azure-blobben. Det här är användbart när du skapar PST-mappningsfilen i nästa steg eftersom du måste ange både mappsökväg och filnamn för varje PST-fil. Genom att kontrollera de här namnen kan du minska potentiella fel i PST-mappningsfilen.

Det fristående Azure Storage Explorer-programmet är vanligtvis tillgängligt. Du kan hämta den senaste versionen med hjälp av länken i följande procedur.
  
> [!IMPORTANT]
> Du kan inte använda Azure Storage Explorer för att ladda upp eller ändra PST-filer. Den enda metoden som stöds för att importera PST-filer är att använda AzCopy. Du kan inte heller ta bort PST-filer som du har laddat upp till Azure-blobben. Om du försöker ta bort en PST-fil får du ett felmeddelande om att du inte har den behörighet som krävs. Observera att alla PST-filer automatiskt tas bort från ditt Azure Storage-område. Om inga importjobb pågår tas alla PST-filer i containern **ingestiondata** bort 30 dagar efter det att det senaste importjobbet skapades.
  
Så här installerar du Azure Storage Explorer och ansluter till ditt Azure Storage-område:
  
1. Ladda ned och installera [Microsoft Azure Storage Explorer-verktyget](https://go.microsoft.com/fwlink/p/?LinkId=544842).

2. Starta Microsoft Azure Storage Explorer.

3. På sidan **Välj resurs** går du till dialogrutan **Anslut till Azure Storage** och klickar på **Blobcontainer**.
  
4. På sidan för att **välja autentiseringsmetod** väljer du alternativet för **SAS (signatur för delad åtkomst)** och klickar sedan på **Nästa**.

5. På sidan **Ange anslutningsinformation** klistrar du in SAS-URL:en du hämtade i steg 1 i rutan under **SAS-webbadress för blobcontainer**. Klicka sedan på **Nästa**. När du har klistrat in SAS-URL:en fylls rutan under **Visningsnamn** automatiskt i med **ingestiondata**.

6. På sidan **Sammanfattning** kan du granska anslutningsinformationen och sedan klicka på **Anslut**.

    Containern **ingestiondata** öppnas. Den innehåller de PST-filer du laddade upp i steg 2. Containern **ingestiondata** finns under **Lagringskonton** \> **(Anslutna containrar)** \> **Blobcontainrar**. 
  
7. När du är klar med Microsoft Azure Storage Explorer högerklickar du på **ingestiondata** och klickar sedan på **Koppla från** för att koppla från ditt Azure Storage-område. Annars får du ett felmeddelande nästa gång du försöker ansluta.
  
## <a name="step-4-create-the-pst-import-mapping-file"></a>Steg 4: Skapa mappningsfilen för PST-import

När PST-filerna har laddats upp till Azure Storage-platsen för din organisation är nästa steg att skapa en fil med kommateckenavgränsade fält (CSV-fil) som anger vilka användarpostlådor PST-filerna ska importeras till.Du kommer skicka den här CSV-filen i nästa steg där du skapar ett PST-importärende.
  
1. [Ladda ned en kopia av mappningsfilen för PST-import](https://go.microsoft.com/fwlink/p/?LinkId=544717).

2. Öppna eller spara CSV-filen på den lokala datorn. I följande exempel visas en slutförd mappningsfil för PST-import (öppnad i Anteckningar). Det är mycket enklare att använda Microsoft Excel för att redigera CSV-filen.

    ```console
    Workload,FilePath,Name,Mailbox,IsArchive,TargetRootFolder,ContentCodePage,SPFileContainer,SPManifestContainer,SPSiteUrl
    Exchange,,annb.pst,annb@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,annb_archive.pst,annb@contoso.onmicrosoft.com,TRUE,,,,,
    Exchange,,donh.pst,donh@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,donh_archive.pst,donh@contoso.onmicrosoft.com,TRUE,,,,,
    Exchange,PSTFiles,pilarp.pst,pilarp@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,PSTFiles,pilarp_archive.pst,pilarp@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,PSTFiles,tonyk.pst,tonyk@contoso.onmicrosoft.com,FALSE,,,,,
    Exchange,PSTFiles,tonyk_archive.pst,tonyk@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,PSTFiles,zrinkam.pst,zrinkam@contoso.onmicrosoft.com,FALSE,,,,,
    Exchange,PSTFiles,zrinkam_archive.pst,zrinkam@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    ```

    Den första raden, eller rubrikraden, i CSV-filen innehåller de parametrar som ska användas av PST-importtjänsten för att importera PST-filerna till användarpostlådorna. Varje parameternamn avgränsas med ett kommatecken. Varje rad under rubrikraden representerar parametervärdena för importering av en PST-fil till en viss postlåda. Du behöver en rad för varje PST-fil som du vill importera till en användarpostlåda. CSV-mappningsfilen kan innehålla högst 500 rader. Om du vill importera fler än 500 PST-filer måste du skapa flera mappningsfiler och skapa flera importjobb i steg 5.

    > [!NOTE]
    > Ändra inget i rubrikraden, inklusive SharePoint-parametrarna. De ignoreras under PST-importprocessen. Kom ihåg att ersätta platshållardata i mappningsfilen med dina faktiska data.

3. Använd informationen i följande tabell och fyll i CSV-filen med den information som krävs.

    | Parameter | Beskrivning | Exempel |
    |:-----|:-----|:-----|
    | `Workload` <br/> |Anger vilken tjänst som data ska importeras till. Om du vill importera PST-filer till användarpostlådor använder du  `Exchange`.  <br/> | `Exchange` <br/> |
    | `FilePath` <br/> |Anger mappens plats på den Azure Storage-plats som du har laddat upp PST-filerna till i steg 2.  <br/> Om du inte tog med ett valfritt undermappnamn i SAS-URL:en i parametern  `/Dest:` i steg 2 låter du den här parametern vara tom i CSV-filen. Om du har lagt till ett undermappnamn anger du det i den här parametern (se det andra exemplet). Värdet för den här parametern är skiftlägeskänsligt.  <br/> Ta hur som helst  *inte*  med ”ingestiondata” i värdet för parametern  `FilePath`.  <br/><br/> **Viktigt!** Filsökvägsnamnet måste ha samma skiftläge som det du använde om du angav ett valfritt undermappnamn i SAS-URL:en i parametern  `/Dest:` i steg 2. Om du till exempel använde  `PSTFiles` för undermappens namn i steg 2 och sedan använder  `pstfiles` i parametern  `FilePath` i CSV-filen kommer importen för PST-filen att misslyckas. Se till att använda samma skiftläge i båda fallen.  <br/> |(lämna tomt)  <br/> Eller  <br/>  `PSTFiles` <br/> |
    | `Name` <br/> |Anger namnet på PST-filen som ska importeras till användarpostlådan. Värdet för den här parametern är skiftlägeskänsligt. Filnamnet för varje PST-fil i mappningsfilen för ett importjobb måste vara unikt. <br/> <br/>**Viktigt!** PST-filnamnet i CSV-filen måste ha samma skiftläge som PST-filen som har laddats upp till Azure Storage-platsen i steg 2. Om du till exempel använder  `annb.pst` i parametern  `Name` i CSV-filen, men namnet på den faktiska PST-filen är `AnnB.pst` kommer importen för PST-filen att misslyckas. Se till att PST-namnet i CSV-filen har samma skiftläge som den faktiska PST-filen.  <br/> | `annb.pst` <br/> |
    | `Mailbox` <br/> |Anger e-postadressen för postlådan som PST-filen ska importeras till. Du kan inte ange en gemensam mapp eftersom PST-importtjänsten inte stöder importering av PST-filer till gemensamma mappar.  <br/> För att importera en PST-fil till en inaktiv postlåda måste du ange postlådans GUID för den här parametern. Om du vill hämta detta GUID kör du följande PowerShell-kommando i Exchange Online:  `Get-Mailbox <identity of inactive mailbox> -InactiveMailboxOnly | FL Guid` <br/> <br/>**Obs!** Ibland kan du ha flera postlådor med samma e-postadress, där en postlåda är en aktiv postlåda och den andra är i ett mjukt borttaget (eller inaktivt) tillstånd. I sådana fall måste du ange postlådans GUID för att unikt identifiera postlådan som PST-filen ska importeras till. Om du vill hämta detta GUID för aktiva postlådor kör du följande PowerShell-kommando:  `Get-Mailbox <identity of active mailbox> | FL Guid`. Om du vill hämta GUID för mjukt borttagna (eller inaktiva) postlådor kör du det här kommandot:  `Get-Mailbox <identity of soft-deleted or inactive mailbox> -SoftDeletedMailbox | FL Guid`.  <br/> | `annb@contoso.onmicrosoft.com` <br/> Eller  <br/>  `2d7a87fe-d6a2-40cc-8aff-1ebea80d4ae7` <br/> |
    | `IsArchive` <br/> | Anger om PST-filen ska importeras till användarens arkivpostlåda. Det finns två alternativ:  <br/><br/>**FALSE:** Importerar PST-filen till användarens primära postlåda.  <br/> **TRUE:** Importerar PST-filen till användarens arkivpostlåda. Detta förutsätter att [användarens arkivpostlåda har aktiverats](enable-archive-mailboxes.md). <br/><br/>Om du anger  `TRUE` för den här parametern och användarens arkivpostlåda inte är aktiverad kommer importen för den användaren att misslyckas. Om en import misslyckas för en användare (på grund av att denna egenskap har angetts som  `TRUE` men arkivet inte är aktiverat), påverkas inte importen för övriga användare.  <br/>  Om du lämnar parametern tom importeras PST-filen till användarens primära postlåda.  <br/> <br/>**Obs!** Om du vill importera en PST-fil till en molnbaserad arkivpostlåda för en användare vars primära postlåda är lokal, anger du  `TRUE` för den här parametern och anger e-postadressen till användarens lokala postlåda för parametern  `Mailbox`.  <br/> | `FALSE` <br/> Eller  <br/>  `TRUE` <br/> |
    | `TargetRootFolder` <br/> | Anger postlådans mapp som PST-filen importeras till.  <br/> <br/> Om du lämnar den här parametern tom importeras PST-filen till en ny mapp med namnet **Imported** (Importerat) på rotnivån för postlådan (samma nivå som Inkorgen och de andra standardmapparna i postlådan).  <br/> <br/> Om du anger  `/` importeras mapparna och objekten i PST-filen högst upp i mappstrukturen i målpostlådan eller arkivet. Om det finns en mapp i målpostlådan (till exempel standardmappar som Inkorgen, Skickat och Borttaget) slås objekten i den mappen i PST-filen ihop med den befintliga mappen i målpostlådan. Om PST-filen till exempel innehåller en inkorgsmapp importeras objekten i den mappen till inkorgsmappen i målpostlådan. Nya mappar skapas om de inte finns i målpostlådans mappstruktur.  <br/><br/>  Om du anger  `/<foldername>` importeras objekt och mappar i PST-filen till en mapp med namnet  *\<foldername\>*  . Om du till exempel använder  `/ImportedPst` importeras objekt till en mapp med namnet **ImportedPst**. Den här mappen finns på samma nivå som Inkorgen i användarens postlåda.  <br/><br/> **Tips!** Överväg att köra några testbatchar och experimentera med den här parametern så att du kan avgöra den bästa platsen för mappen som PST-filerna ska importeras till.  <br/> |(lämna tomt)  <br/> Eller  <br/>  `/` <br/> Eller  <br/>  `/ImportedPst` <br/> |
    | `ContentCodePage` <br/> |Den här valfria parametern anger ett numeriskt värde för teckentabellen som ska användas för import av PST-filer i ANSI-filformatet. Den här parametern används för att importera PST-filer från kinesiska, japanska och koreanska (CJK) organisationer eftersom dessa språk normalt använder en teckenuppsättning med dubbla byte (DBCS) för teckenkodning. Om den här parametern inte används för att importera PST-filer för språk som använder DBCS för postlådemappnamn är mappnamnen ofta förvrängda efter att de importerats.  <br/><br/> En lista med värden som stöds för den här parametern finns i artikeln om [identifierare för teckentabeller](/windows/win32/intl/code-page-identifiers).  <br/> <br/>**Obs!** Som tidigare nämnts är det här en valfri parameter och du behöver inte ta med den i CSV-filen. Eller så kan du ta med den och lämna värdet tomt för en eller flera rader.  <br/> |(lämna tomt)  <br/> Eller  <br/>  `932` (som är identifieraren för teckentabellen för ANSI/OEM för japanska)  <br/> |
    | `SPFileContainer` <br/> |Lämna den här parametern tom för PST-import.  <br/> |Ej tillämpligt  <br/> |
    | `SPManifestContainer` <br/> |Lämna den här parametern tom för PST-import.  <br/> |Ej tillämpligt  <br/> |
    | `SPSiteUrl` <br/> |Lämna den här parametern tom för PST-import.  <br/> |Ej tillämpligt  <br/> |

## <a name="step-5-create-a-pst-import-job"></a>Steg 5: Skapa ett PST-importjobb

Nästa steg är att skapa PST-importjobbet i importtjänsten i Microsoft 365. Som tidigare beskrivits skickar du in mappningsfilen för PST-import som du skapade i steg 4. När du har skapat jobbet analyserar Microsoft 365 data i PST-filerna. Du får sedan möjlighet att filtrera de data som faktiskt importeras till postlådorna som anges i mappningsfilen för PST-import (se [steg 6](#step-6-filter-data-and-start-the-pst-import-job)).
  
1. Gå till <https://compliance.microsoft.com> och logga in med autentiseringsuppgifterna för ett administratörskonto i organisationen.

2. Klicka på **Informationsstyrning > Importera** i vänster fönsterruta i Microsoft 365 Efterlevnadscenter.

3. På fliken **Importera** klickar du på ikonen ![Lägg till](../media/ITPro-EAC-AddIcon.gif) **Nytt importjobb**.

   > [!NOTE]
   > Du måste ha tilldelats rätt behörigheter för att komma **importsidan** i Microsoft 365 Efterlevnadscenter och skapa ett importjobb. Mer information finns i avsnittet **Innan du börjar**. 

4. Skriv ett namn för PST-importjobbet och klicka sedan på **Nästa**. Använd gemener, siffror, bindestreck och understreck. Du kan inte använda versaler eller blanksteg i namnet.

5. På sidan **Vill du ladda upp eller skicka dina data?** klickar du på **Ladda upp data** och sedan på **Nästa**.
  
6. I steg 4 på sidan **Importera data** klickar du på kryssrutorna **Jag har laddat upp filerna** och **Jag har tillgång till mappningsfilen**. Klicka sedan på **Nästa**.

    ![Klicka på de två kryssrutorna i steg 4](../media/9f2427e8-3af2-4e27-95e6-a9f08430d3d8.png)
  
7. På sidan **Välj mappningsfilen** klickar du på **Välj mappningsfil** när du vill skicka CSV-mappningsfilen som du skapade i steg 4.

    ![Klicka på Välj mappningsfil när du vill skicka CSV-filen som du har skapat för importjobbet](../media/d30b1d73-80bb-491e-a642-a21673d06889.png)
  
8. När namnet på CSV-filen visas under **Namn på mappningsfil** klickar du på **Validera** och kontrollerar om det finns några fel i CSV-filen.

    ![Klicka på Validera och sök efter fel i CSV-filen](../media/4680999d-5538-4059-b878-2736a5445037.png)
  
    CSV-filen måste valideras för att kunna skapa ett PST-importjobb. Filnamnet ändras till grönt när den har validerats. Om valideringen misslyckas klickar du på länken **Visa logg**. En rapport över valideringsfel öppnas med ett felmeddelande för varje rad i filen som misslyckades.

   > [!NOTE]
   > Som tidigare beskrivits kan en mappningsfil ha maximalt 500 rader. Valideringen misslyckas om mappningsfilen innehåller fler än 500 rader. Om du vill importera fler än 500 PST-filer måste du skapa flera mappningsfiler och flera importjobb.

9. När mappningsfilen har validerats läser du villkorsdokumentet och klickar sedan på kryssrutan.

10. Klicka på **Spara** när du vill skicka jobbet. Klicka sedan på **Stäng** när jobbet har skapats.

    En utfällbar statussida visas med statusen **Analysen pågår**. Det nya importjobbet visas i listan på sidan för att **importera PST-filer**.

11. Klicka på **Uppdatera** ![Uppdateringsikon](../media/O365-MDM-Policy-RefreshIcon.gif) om du vill uppdatera statusinformationen som visas i kolumnen **Status**. När analysen är klar och data är redo att importeras ändras statusen till **Analysen är klar**.

    Du kan klicka på importjobbet om du vill visa den utfällbara statussidan som innehåller mer detaljerad information om importjobbet, till exempel status för varje PST-fil i mappningsfilen.

## <a name="step-6-filter-data-and-start-the-pst-import-job"></a>Steg 6: Filtrera data och starta PST-importjobbet

När du har skapat importjobbet i steg 5 analyserar Microsoft 365 data i PST-filerna (på ett säkert sätt) genom att identifiera åldern på objekten och de olika meddelandetyperna som ingår i PST-filerna. När analysen är klar och data är redo att importeras kan du importera alla data som finns i PST-filerna, eller så kan du trimma data som importeras genom att ställa in ett filter som bestämmer vilka data som ska importeras.
  
1. På fliken **Importera** i Efterlevnadscenter för Microsoft 365 markerar du de importjobb som du skapade i steg 5 och klickar sedan på **Importera till Office 365**.
  
   Sidan **Filtrera data** visas. Den innehåller datainsikter från analysen som har utförts på PST-filerna av Office 365, bland annat information om åldern på data. I det här läget kan du filtrera de data som ska importeras eller importera alla data som de är. 

    ![Du kan trimma data i PST-filerna eller importera allt](../media/287fc030-99e9-417b-ace7-f64617ea5d4e.png)
  
2. Gör något av följande:

   1. Om du vill trimma de data du importerar klickar du på **Ja, jag vill filtrera innan jag importerar**.

      Detaljerade stegvisa instruktioner om hur du filtrerar data i PST-filerna och sedan startar importjobbet finns i [Filtrera data vid import av PST-filer till Office 365](filter-data-when-importing-pst-files.md).

      Eller

   2. Om du vill importera alla data i PST-filerna klickar du på **Nej, jag vill importera allt** och klickar sedan på **Nästa**.

3. Om du väljer att importera alla data klickar du på **Importera data**, så startas importjobbet. 

   Status för importjobbet visas på sidan för att **importera PST-filer**. Klicka på ![Uppdateringsikon](../media/O365-MDM-Policy-RefreshIcon.gif) **Uppdatera** om du vill uppdatera statusinformationen som visas i kolumnen **Status**. Klicka på importjobbet om du vill visa den utfällbara statussidan med statusinformation om varje PST-fil som importeras.

## <a name="more-information"></a>Mer information

- Varför ska jag importera PST-filer till Microsoft 365?

  - Det är ett bra sätt att importera organisationens meddelandedata för arkivering till Microsoft 365.

  - Användarna kan komma åt dessa data från alla enheter eftersom de lagras i molnet.

  - Det hjälper dig att uppfylla efterlevnadsbehoven i din organisation genom att låta dig använda efterlevnadsfunktioner i Microsoft 365 för data från de PST-filerna som du har importerat. Detta inkluderar:

  - Aktivering av [arkivpostlådor](enable-archive-mailboxes.md) och [automatiskt expanderande arkivering](enable-unlimited-archiving.md) så att användarna får ytterligare lagringsutrymme för postlådan för att lagra de data du har importerat.

  - Placering av postlådor i [Bevarande av juridiska skäl](./create-a-litigation-hold.md) för att bevara de data du har importerat.

  - Användning av Microsoft [eDiscovery-verktyg](search-for-content.md) för att söka i de data du har importerat.

  - Användning av [Microsoft 365-kvarhållningsprinciper](retention.md) för att styra hur länge de data du har importerat ska kvarhållas och vilka åtgärder som ska vidtas efter att kvarhållningsperioden upphör att gälla.

  - Sökning i [granskningsloggen](search-the-audit-log-in-security-and-compliance.md) efter postlåderelaterade händelser som påverkar de data du har importerat.

  - Importering av data till [inaktiva postlådor](create-and-manage-inactive-mailboxes.md) för att arkivera data i efterlevnadssyfte. 

  - Användning av [principer för dataförlustskydd](dlp-learn-about-dlp.md) för att förhindra att känsliga data läcker ut utanför organisationen.
  
- Här är ett exempel på URL:en för signatur för delad åtkomst (SAS) som hämtas i steg 1. Det här exemplet innehåller även syntaxen för det kommando du kör i verktyget AzCopy.exe för att ladda upp PST-filer. Se till att vidta försiktighetsåtgärder för att skydda den här SAS-URL:en på samma sätt som du skyddar lösenord eller annan säkerhetsrelaterad information.

    ```console
    SAS URL: https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D

    AzCopy.exe /Source:<Location of PST files> /Dest:<SAS URL> /V:<Log file location> /Y

    EXAMPLES

    This example uploads PST files to the root of the Azure storage location:

    AzCopy.exe /Source:"\\FILESERVER1\PSTs" /Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D" /V:"c:\Users\Admin\Desktop\AzCopy1.log" /Y
    
    This example uploads PST files to a subfolder named PSTFiles  in the Azure storage location:

    AzCopy.exe /Source:"\\FILESERVER1\PSTs" /Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata/PSTFiles?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D" /V:"c:\Users\Admin\Desktop\AzCopy1.log" /Y
    ```

- Som tidigare beskrivits aktiverar Office 365-importtjänsten inställningen för kvarhållningsundantag (på obestämd tid) efter att PST-filer har importerats till en postlåda. Det innebär att egenskapen  *RetentionHoldEnabled*  är inställd på  **True** så att kvarhållningsprincipen som tilldelats postlådan inte bearbetas. Det ger postlådans ägare tid att hantera de nya importerade meddelandena genom att förhindra att en borttagnings- eller arkiveringsprincip tar bort eller arkiverar äldre meddelanden. Här är några steg du kan vidta för att hantera det här kvarhållningsundantaget:

   - Efter en viss tid kan du inaktivera kvarhållningsundantaget genom att köra kommandot **Set-Mailbox -RetentionHoldEnabled $false**. Anvisningar finns i artikeln om att [tillämpa kvarhållningsundantag för en postlåda](/exchange/security-and-compliance/messaging-records-management/mailbox-retention-hold).

   - Du kan konfigurera kvarhållningsundantaget så att det inaktiveras på ett datum i framtiden. Det gör du genom att köra kommandot **Set-Mailbox -EndDateForRetentionHold *datum***. Anta till exempel att dagens datum är den 1 juni 2016 och du vill att kvarhållningsundantaget ska inaktiveras om 30 dagar. Då kör du följande kommando:  **Set-Mailbox -EndDateForRetentionHold 7/1/2016**. I det här scenariot låter du egenskapen  **RetentionHoldEnabled**  vara inställd på  *True*. Mer information finns i [Set-Mailbox](/powershell/module/exchange/set-mailbox).

   - Du kan ändra inställningarna för den kvarhållningsprincip som tilldelats postlådan så att äldre objekt som har importerats inte genast tas bort eller flyttas till användarens arkivpostlåda. Du kan till exempel förlänga kvarhållningsåldern för en borttagnings- eller arkiveringsprincip som tilldelats till postlådan. I det här scenariot inaktiverar du kvarhållningsundantaget för postlådan när du har ändrat inställningarna för kvarhållningsprincipen. Mer information finns i [Konfigurera en princip för arkivering och borttagning för postlådor i din organisation](set-up-an-archive-and-deletion-policy-for-mailboxes.md).

### <a name="how-the-import-process-works"></a>Så här fungerar importeringsprocessen
  
Du kan använda alternativet för nätverksuppladdning och Office 365-importtjänsten för att massimportera PST-filer till användarnas postlådor. Nätverksuppladdning innebär att du laddar upp PST-filer till ett tillfälligt lagringsområde i Microsoft-molnet. Sedan kopierar Office 365-importtjänsten PST-filerna från lagringsområdet till målanvändarpostlådorna.
  
Här är en bild och beskrivning av nätverksuppladdningsprocessen för att importera PST-filer till postlådor i Office 365.
  
![Arbetsflödet för nätverksuppladdningsprocessen för att importera PST-filer till Office 365](../media/9e05a19e-1e7a-4f1f-82df-9118f51588c4.png)
  
1. **Ladda ned PST-importverktyget och nyckeln till en privat Azure Storage-plats:** Det första steget är att ladda ned kommandoradsverktyget AzCopy och en åtkomstnyckel som används för att ladda upp PST-filerna till en Azure Storage-plats i Microsoft-molnet. Du hittar dem på sidan **import** i Microsoft 365 Efterlevnadscenter. Nyckeln, som kallas för en SAS-nyckel (signatur för säker åtkomst), ger dig nödvändiga behörigheter för att ladda upp PST-filer till en privat och säker Azure Storage-plats. Den här åtkomstnyckeln är unik för din organisation och hjälper till att förhindra obehörig åtkomst till dina PST-filer när de har laddats upp till Microsoft-molnet. Organisationen behöver inte ha en separat Azure-prenumeration för att importera PST-filer. 

2. **Ladda upp PST-filerna till Azure Storage-platsen:** Nästa steg är att använda verktyget AzCopy.exe (laddas ned i steg 1) för att ladda upp och lagra PST-filerna på en Azure Storage-plats som finns i samma regionala Microsoft-datacenter som din organisation. För att kunna ladda upp de PST-filer som du vill importera måste de finnas i en filresurs eller på en filserver i din organisation.

    Som ett valfritt steg kan du välja att visa listan med PST-filer när de har laddats upp till Azure Storage-platsen.

3. **Skapa en mappningsfil för PST-import:** När PST-filerna har laddats upp till Azure Storage-platsen är nästa steg att skapa en fil med kommateckenavgränsade fält (CSV-fil) som anger vilka användarpostlådor PST-filerna ska importeras till. Observera att en PST-fil kan importeras till en användares primära postlåda eller arkivpostlåda. Office 365-importtjänsten använder informationen i CSV-filen för att importera PST-filerna.

4. **Skapa ett PST-importjobb:** Nästa steg är att skapa ett PST-importjobb på sidan för att **importera PST-filer** i Microsoft 365 Efterlevnadscenter och skicka mappningsfilen för PST-import som skapades i föregående steg. När du har skapat importjobbet analyserar Microsoft 365 data i PST-filerna och du får sedan möjlighet att ställa in filter som styr vilka data som faktiskt ska importeras till postlådorna som anges i mappningsfilen för PST-import. 

5. **Filtrera PST-data som ska importeras till postlådor:** När importjobbet har skapts och startats analyserar Microsoft 365 data i PST-filerna (på ett säkert sätt) genom att identifiera åldern på objekten och de olika meddelandetyperna som ingår i PST-filerna. När analysen är klar och data är redo att importeras kan du importera alla data som finns i PST-filerna, eller så kan du trimma data som importeras genom att ställa in ett filter som bestämmer vilka data som ska importeras.

6. **Starta PST-importjobbet:** När importjobbet har startats använder Microsoft 365 informationen i mappningsfilen för PST-import för att importera PST-filerna från Azure Storage-platsen till användarnas postlådor. Statusinformation om importjobbet (inklusive information om varje PST-fil som importeras) visas på sidan för att **importera PST-filer** i Microsoft 365 Efterlevnadscenter. När importjobbet är klart blir jobbets status **Slutfört**.
