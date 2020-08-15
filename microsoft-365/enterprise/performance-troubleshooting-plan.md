---
title: Plan för prestanda fel sökning för Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 5/10/2019
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: e241e5d9-b1d8-4f1d-a5c8-4106b7325f8c
ms.collection:
- M365-security-compliance
- Ent_O365
description: Den här artikeln kan hjälpa dig att felsöka prestanda problem i Office 365 och även lösa vanliga problem.
ms.openlocfilehash: 9287e2649a2eb126d723e7436a9178be93087bc0
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694598"
---
# <a name="performance-troubleshooting-plan-for-office-365"></a>Plan för prestanda fel sökning för Office 365

Behöver du veta vad du kan göra för att identifiera och åtgärda fördröjd skrift, hänga och få låga prestanda mellan SharePoint Online, OneDrive för företag, Exchange Online eller Skype för företag – Online samt klient dator? Innan du ringer supporten kan du använda den här artikeln för att felsöka prestanda problem i Office 365 och även lösa vanliga problem.
  
Den här artikeln är ett exempel på ett åtgärds abonnemang som du kan använda för att samla in värdefull information om prestanda problem. Vissa vanligaste problem ingår också i den här artikeln.

Om du inte har använt nätverks prestanda och vill göra en långsiktig plan för att övervaka prestanda mellan klient datorerna och Office 365 kan du ta en titt på [prestanda justering och fel sökning i office 365-administratör och IT-proffs](performance-tuning-using-baselines-and-history.md).
  
## <a name="sample-performance-troubleshooting-action-plan"></a>Exempel på åtgärds plan för prestanda fel sökning

Den här åtgärds planen innehåller två delar; en förberedelse fas och en loggnings fas. Om du har ett problem med prestanda och du måste göra data insamling kan du börja använda det här abonnemanget direkt.
  
### <a name="prepare-the-client-computer"></a>Förbereda klient datorn
  
- Hitta en klient dator som kan återskapa prestanda problem. Den här datorn kommer att användas under fel sökning.
- Skriv ned de steg som orsakar prestanda problemet så att du är redo när det kommer tid att testa.
- Installera verktyg för insamling och inspelning av information:
  - Installera [Netmon 3,4](https://www.microsoft.com/download/details.aspx?id=4865) (eller Använd ett likvärdigt verktyg för nätverks spårning).
  - Installera den kostnads fria Basic-versionen av [HTTPWatch](https://www.httpwatch.com/download/) (eller Använd ett likvärdigt verktyg för nätverks spårning).
  - Använd en skärm bild eller kör de problem registreringar (PSR.exe) som medföljer Windows Vista och senare för att kunna registrera de steg du ska vidta under testningen.

### <a name="log-the-performance-issue"></a>Logga prestanda problem
  
- Stäng alla främmande Internet webbläsare.
- Starta problem registrering eller en annan skärm inspelning.
- Starta Netmon (verktyget för nätverks spårning).
- Rensa DNS-cachen på klient datorn från kommando raden genom att skriva ipconfig/flushdns.
- Starta en ny webbläsarsession och aktivera HTTPWatch.
- Valfritt: om du testar Exchange Online kör du verktyget Exchange-klient prestanda analys från administratörs konsolen för Office 365.
- Återskapa de exakta stegen som orsakar prestanda problem.
- Stoppa Netmon eller andra verktygets spårning.
- Kör en spårnings väg till Office 365-prenumerationen på kommando raden genom att skriva följande kommando och sedan trycka på RETUR:

  ``` cmd
  tracert <subscriptionname>.onmicrosoft.com
  ```

- Stoppa problem registrering och spara videon. Se till att ange datum och tid för inspelningen och om det visar bra eller dålig prestanda.
- Spara spårningsfilerna. Glöm inte att ange datum och tid för inspelningen och om det visar bra eller dålig prestanda.

Om du inte är bekant med att köra de verktyg som nämns i den här artikeln, oroa dig inte, eftersom vi tillhandahåller de här stegen. Om du är van vid att göra den här typen av nätverks fångst kan du hoppa till [hur du samlar in original planer](performance-tuning-using-baselines-and-history.md#how-to-collect-baselines), som beskriver hur du filtrerar och läser loggar.
  
### <a name="flush-the-dns-cache-first"></a>Rensa DNS-cachen först

Varför? Genom att ta bort DNS-cachen du startar testerna med en ren. Om du rensar cacheminnet återställs innehållet i DNS-matcharen till de senaste posterna. Kom ihåg att en tömning inte tar bort hosts File-poster. Om du använder värd fil poster på en gång bör du kopiera dessa poster till en fil i en annan katalog och sedan tömma HOST-filen.
  
#### <a name="flush-your-dns-resolver-cache"></a>Rensa DNS-matcharens cache
  
1. Öppna kommando tolken (starta antingen **Start** \> **Run** \> **cmd** eller Windows- **tangenten** \> **cmd**).
2. Skriv följande kommando och tryck på RETUR:

    ``` cmd
    ipconfig /flushdns
    ```

## <a name="netmon"></a>Netmon

Microsofts verktyg för nätverks övervakning ([Netmon](https://www.microsoft.com/download/details.aspx?id=4865)) analyserar paket, det vill säga trafik, som passerar mellan datorer i nätverket. Genom att använda Netmon för att spåra trafik med Office 365 kan du ta reda på, Visa och läsa paket rubriker, identifiera mellanliggande enheter, kontrol lera viktiga inställningar på nätverks maskin vara, söka efter tappade paket och följa flödet för trafik mellan datorer i företagets nätverk och Office 365. Eftersom den faktiska bröd texten är krypterad, det vill säga att det (skickas på port 443 via SSL/TLS, går det inte att läsa filerna som skickas. I stället får du en ofiltrerad spårning av sökvägen som paketet tar för att spåra problem beteendet.
  
Se till att du inte använder ett filter för tillfället. I stället kan du gå igenom stegen och demonstrera problemet innan du stoppar spårningen och sparandet.
  
När du har installerat Netmon 3,4 öppnar du verktyget och följer de här stegen:
  
### <a name="take-a-netmon-trace-and-reproduce-the-issue"></a>Ta en Netmon spårning och återskapa problemet
  
1. Starta Netmon 3,4.
Det finns tre fönster på **Start** sidan: **senaste insamlarna**, **Välj nätverk**och **komma igång med Microsoft Network Monitor 3,4. Meddelande**. På panelen Välj nätverk får du också en lista över de standardnätverk som du kan avbilda från. Kontrol lera att nätverkskort är markerade här.

2. Klicka på **ny Capture** högst upp på **Start** sidan. Då läggs en ny flik till på **Start** sidans flik med " **Capture 1**".
![Netmon användar gränssnitt med de nya knapparna Capture, start och stopp markerat.](../media/d4527d84-62ec-4301-82d5-e0166ff71f20.PNG)

3. Om du vill skapa en enkel Capture klickar du på **Starta** i verktygsfältet.

4. Återskapa de steg som orsakar ett prestanda problem.

5. Klicka på **sluta** \> **File** \> **Spara som**. Kom ihåg att ange datum och tid med tidszon och omnämnande om den visar dåligt eller bra prestanda.

## <a name="httpwatch"></a>HTTPWatch

[HTTPWatch](https://www.httpwatch.com/download/) kommer att debiteras och en gratis utgåva. Den kostnads fria Basic-versionen omfattar allt du behöver för det här testet. HTTPWatch övervakar nätverks trafik och sid inläsnings tid direkt från webbläsarfönstret. HTTPWatch är ett plugin-program till Internet Explorer som grafiskt beskriver prestanda. Analysen kan sparas och visas i HTTPWatch Studio.
  
> [!NOTE]
> Om du använder en annan webbläsare, till exempel Firefox, Google Chrome, eller om du inte kan installera HTTPWatch i Internet Explorer, öppnar du ett nytt webbläsarfönster och trycker på F12 på tangent bordet. Du bör se verktygsfältet utvecklingsverktyg längst ned i webbläsaren. Om du använder Opera trycker du på CTRL + SKIFT + I för webb kontroll och klickar sedan på fliken **nätverk** och utför testningen nedan. Informationen är lite annorlunda, men Läs tiden visas fortfarande i millisekunder. > HTTPWatch är också användbart för problem med sid laddnings tider i SharePoint Online.
  
### <a name="run-httpwatch-and-reproduce-the-issue"></a>Kör HTTPWatch och återskapa problemet
  
HTTPWatch är ett webb läsar program som visar verktyget i webbläsaren är lite olika för varje version av Internet Explorer. Vanligt vis kan du hitta HTTPWatch under kommando fältet i Internet Explorer-webbläsaren. Om du inte ser plugin-programmet HTTPWatch i webbläsarfönstret kan du kontrol lera webbläsarens version genom att klicka på **Hjälp** \> **om**eller i senare versioner av Internet Explorer, klicka på kugg hjuls symbolen och **om Internet Explorer**. Om du vill starta **kommando** fältet högerklickar du på Meny raden i Internet Explorer och klickar på **kommando fält**.

Förr har HTTPWatch associerats med både kommandona och Explorer-fälten, så när du har installerat visas inte ikonen direkt (även efter omstart **) och**verktygsfälten för ikonen. Kom ihåg att verktygsfält kan anpassas och att alternativ kan läggas till i dem.

![Internet Explorers kommando verktygsfält med ikonen HTTPWatch.](../media/198590b0-d7b1-4bff-a6ad-e4ec3a1e83df.png)
  
1. Starta HTTPWatch i ett fönster i Internet Explorer. Den kommer att visas dock i webbläsaren längst ned i fönstret. Klicka på **spela in**.

2. Återskapa de exakta stegen i prestanda problemet. Klicka på **stopp** -knappen i HTTPWatch.

3. **Spara** HTTPWatch eller **Skicka via e-post**. Kom ihåg att namnge filen så att den innehåller datum-och tidsinformation och en indikation på om din Watch innehåller en demonstration av bra eller dålig prestanda.

![HTTPWatch visar fliken nätverk för en sid belastning på Start sidan för Office 365.](../media/021a2c64-d581-49fd-adf4-4c364f589d75.PNG)

Denna skärm bild är från den professionella versionen av HTTPWatch. Du kan öppna spår som gjorts i grund versionen på en dator med en Professional-version och läsa den där. Ytterligare information kan komma att finnas med i den här metoden.

## <a name="problem-steps-recorder"></a>Problem registrering

Med problem registrering eller PSR.exe kan du spela in frågor medan de inträffar. Det är ett mycket användbart verktyg och lätt att köra.
  
### <a name="run-problem-steps-recorder-psrexe-to-record-your-work"></a>Kör problem registrering (PSR.exe) för att registrera ditt arbete
  
1. Använd antingen **Start** \> **Run** \> **PSR.exe** \> **OK**, eller klicka på **Windows-tangenten** \> **PSR.exe** \> och sedan på RETUR.

2. När fönstret för små PSR.exe visas klickar du på **Starta post** och återger de steg som orsakar prestanda problemet. Du kan lägga till kommentarer genom att klicka på **Lägg till kommentarer**.

3. Klicka på **stoppa inspelning** när du har slutfört stegen. Om prestanda problemet beror på en sida kan du vänta på att sidan ska renderas innan inspelningen stoppas.

4. Klicka på **Spara**.

![En skärm bild av problem registrering eller PSR.exe.](../media/8542b0aa-a3ff-4718-8dc4-43f5521c6c34.PNG)
  
Datum och tid registreras för dig. Detta länkar fso till din Netmon trace and HTTPWatch i tid, och hjälper till med fel sökning av precision. Datum och tid i fso-posten kan visa att en minut har passerat mellan inloggningen och webb adressen och en ofullständig åter givning av administratörs webbplatsen.
  
## <a name="read-your-traces"></a>Läs dina spårningar

Det går inte att lära sig allt om nätverks-och prestanda fel sökning som någon behöver veta med hjälp av en artikel. Det tar en bra upplevelse med prestanda och kunskap om hur nätverket fungerar och hur vanligt utförs. Men det går att runda av en lista över de vanligaste problemen och visa hur verktyg kan göra det lättare för dig att eliminera de vanligaste problemen.
  
Om du vill ta en vana att hämta färdigheter för dina Office 365-webbplatser är det ingen bättre lärare än att skapa spår av sid laddas regelbundet och läsa upp dem. Om du till exempel har en chans kan du läsa in en Office 365-tjänst och spåra processen. Filtrera spårning för DNS-trafik eller Sök efter namnet på den tjänst du bläddrade till med FrameData. Sök igenom spåret för att få en uppfattning om vad som händer när tjänsten laddas. Det här hjälper dig att få reda på hur normal sid inläsning bör se ut, och vid fel sökning, särskilt med prestanda kan det vara en bra idé att jämföra dina dåliga spår.
  
I Netmon används Microsoft IntelliSense i fältet visnings filter. IntelliSense för att fylla på en intelligent kod är att det Stick där du skriver i en period och alla tillgängliga alternativ visas i en listruta. Om du till exempel är oroar för skalning med TCP-fönster kan du hitta ett filter (till exempel  `.protocol.tcp.window < 100` ) på det här sättet.
  
![Skärm bild av NetMon som visar att IntelliSense används i filter fältet.](../media/75a56c11-9a60-47ee-a100-aabdfb1ba10f.PNG)
  
Netmon-spår kan ha mycket trafik i dem. Om du inte har erfarenhet av att läsa dem är det troligt att du är bekymrad för att öppna spåret första gången. Det första du ska göra är att skilja signalen från bakgrunds ljudet i spåret. Du testade mot Office 365 och det är det du vill se. Om du använder för att bläddra igenom spår kanske du inte behöver den här listan.
  
Trafiken mellan din klient och Office 365 skickas via TLS, vilket betyder att bröd texten är krypterad och inte kan läsas i en allmän Netmon-spårning. Din prestanda analys behöver inte veta informationen i paketet. Det är dock mycket intressant i paket rubriker och information som de innehåller.
  
### <a name="tips-to-get-a-good-trace"></a>Tips för att få en god spårning
  
- Få reda på värdet på klient datorns IPv4-eller IPv6-adress. Du kan hämta det från kommando tolken genom att skriva **ipconfig** och sedan trycka på RETUR. Om du känner till den här adressen får du en överblick över om trafiken i spåret direkt avser din klient dator. Om det finns en känd proxyserver skickar du ping till den och får också IP-adressen.

- Rensa DNS-matcharens cache och om möjligt stänga alla webbläsare utom den där du kör testerna. Om du inte kan göra det här, till exempel om stöd använder ett visst webbläsarbaserat verktyg för att visa klient datorns dator, måste du vara beredd på att filtrera spårningen.

- Leta reda på den Office 365-tjänst du använder under en upptaget spårning. Om du aldrig eller sällan ser din trafik förut är det här ett användbart steg för att avgränsa prestanda problem från annat nätverks brus. Det finns några olika sätt att göra detta. Direkt före provet kan du använda _ping_ eller _PsPing_ mot URL-adressen för den specifika tjänsten ( `ping outlook.office365.com` `psping -4 microsoft-my.sharepoint.com:443` till exempel). Du kan också enkelt hitta det ping-eller PsPing i en Netmon-spårning (med dess process namn). Då får du en plats att börja titta på.

Om du bara använder Netmon spårning när problemet uppstår är det också. Använd ett filter som eller för att orientera dig själv `ContainsBin(FrameData, ASCII, "office")` `ContainsBin(FrameData, ASCII, "outlook")` . Du kan spela in ett RAM nummer från spårnings filen. Du kanske också vill bläddra i fönstret _Sammanfattning av ram_ längst till höger och leta efter kolumnen KONVERSATIONS-ID. Det finns ett nummer som visas där för ID för den här specifika konversationen som du också kan spela in och titta på i isolering senare. Kom ihåg att ta bort filtret innan du använder någon annan filtrering.

> [!TIP]
> Netmon har många användbara inbyggda filter. Prova knappen **Ladda filter** högst upp i fönstret _Visa_ filter.
  
![Hitta din IP-adress genom att använda PSPing på kommando raden på klient datorn.](../media/4c43ac67-e28e-4536-842d-7add7aa28847.PNG)
  
![Netmon spårning från klienten som visar samma PSPing-kommando via filtret TCP. Flaggor. syn = = 1.](../media/0ae7ef7d-e003-4d01-a006-dc49bd1fcef2.PNG)
  
Bekanta dig med din trafik och lär dig att hitta den information du behöver. Om du till exempel vill ta reda på vilket paket i spårningen har den första referensen till Office 365-tjänsten du använder (som "Outlook").

Om du tar Office 365 Outlook online som ett exempel inleds trafiken ungefär så här:
  
- DNS-standardfråga och DNS-svar för outlook.office365.com med matchande QueryIDs. Det är viktigt att notera tids förskjutningen för den här funktionen, samt var i världen Office 365 global DNS skickar begäran om namn matchning. Helst som möjligt, i stället för världen över.

- En HTTP-begäran vars status rapport flyttats permanent (301)

- RWS trafik inklusive RWS Connect-begäranden och anslutande svar. (Det här är en fjärran sluten Winsock-anslutning åt dig.)

- En TCP SYN-och TCP SYN-konversation. Många inställningar i denna konversation påverkar din prestanda.

- Sedan en serie TLS: TLS-trafik där TLS-handskakning och samtal till TLS-certifikat sker. (Kom ihåg att data krypteras via SSL/TLS.)

Alla delar av trafiken är viktiga och anslutna, men små delar av spårningen innehåller information som är särskilt viktig när det gäller prestanda fel sökning, så vi fokuserar på dessa områden. Eftersom vi har tillräckligt med Office 365-felsöknings prestanda på Microsoft för att sammanställa en tio i topp-lista med vanliga problem, fokuserar vi på dessa problem och hur du använder de verktyg som krävs för att roota dem.
  
Om du inte har installerat dem är det möjligt att använda flera verktyg i matrisen. Där det är möjligt. Det finns länkar till installations punkterna. Listan innehåller vanliga verktyg för nätverks spårning, till exempel [Netmon](https://www.microsoft.com/download/details.aspx?id=4865) och [wireshark](https://www.wireshark.org/), men Använd ett spårnings verktyg som du är van vid och där du är van vid att filtrera nätverks trafik. Kom ihåg följande när du testar:
  
- *Stänga dina webbläsare och testa med bara en webbläsare*  -det här minskar den allmänna trafik som du fångar in. Det gör det enklare att spåra.
- *Rensa DNS-matcharens cache på klient datorn*  -det ger dig en ren bakifrån när du börjar ta din Capture för en renare spårning.

## <a name="common-issues"></a>Vanliga problem

Några vanliga problem och hur du hittar dem i din nätverks spårning.

### <a name="tcp-windows-scaling"></a>TCP Windows skalning

Finns i tillståndet SYN-SYN/ACK. Legacy-eller åldrande hård vara kanske inte utnyttja Windows skalning i TCP.  Utan korrekta inställningar för TCP-skalning i Windows fylls standardbufferten för 16 bitar i TCP-huvudena i millisekunder.  Trafiken kan inte fortsätta att skickas tills klienten får en bekräftelse på att de ursprungliga uppgifterna har tagits emot, vilket orsakar fördröjningar.

#### <a name="tools"></a>Verktyg

- Netmon
- Wireshark

#### <a name="what-to-look-for"></a>Vad du kan söka efter

Leta efter SYN-SYN/ACK-trafik i nätverks spårningen.  Använd ett filter som i Netmon  `tcp.flags.syn == 1` . Det här filtret är detsamma i wireshark.  

![Filtrera i Netmon eller wireshark för syn paket för båda verktygen: TCP. Flaggor. syn = = 1.](../media/4b9a12a1-c915-43c8-ac2f-a679d0435a29.PNG)

Observera att för varje SYN det finns ett SrcPort-nummer (Source port) som matchas i mål porten (DstPort) för den relaterade bekräftelsen (SYN/ACK).

Om du vill visa Windows skalnings värde som används av nätverks anslutningen expanderar du först SYN och sedan relaterad SYN/ACK.  

![Bild som visar hur du kan matcha SrcPort till DstPort i en spårning för att få tiden delta.](../media/6a4ca573-0253-4fbd-93e8-92821ee1c351.png)  

### <a name="tcp-idle-time-settings"></a>TCP Idle Time-inställningar

Historiskt, de flesta perimeternätverk är konfigurerade för tillfälliga anslutningar, vilket innebär att inaktiva anslutningar normalt upphör. Inaktiva TCP-sessioner kan avslutas av proxyservrar och brand väggar med fler än 100 till 300 sekunder. Det här är problematiskt för Outlook online eftersom det skapar och använder långa anslutningar, oavsett om de är inaktiva eller inte.  

När anslutningar avbryts av proxy-eller brand Väggs enheter informeras klienten inte och ett försök att använda Outlook online innebär att en klient dator försöker att Revive anslutningen innan du skapar en ny. Det kan hända att du låser dig i produkt, uppmaning eller låg prestanda på sidan.

#### <a name="tools"></a>Verktyg

- Netmon
- Wireshark

#### <a name="what-to-look-for"></a>Vad du kan söka efter

I Netmon kan du titta i fältet tids förskjutning för en rund resa. En rund resa är tiden mellan klienten som skickar en begäran till servern och får ett svar tillbaka. Kontrol lera mellan klienten och utgångs punkten (ex. Klient- \> proxy) eller klienten till Office 365 (klient-- \> Office 365). Du kan se detta i många typer av paket.

Filtret i Netmon kan till exempel se ut som  `.Protocol.IPv4.Address == 10.102.14.112 AND .Protocol.IPv4.Address == 10.201.114.12` eller, i wireshark  `ip.addr == 10.102.14.112 &amp;&amp; ip.addr == 10.201.114.12` .  

> [!TIP]
> Vet du inte om IP-adressen i spårningen tillhör din DNS-Server? Pröva att leta upp det på kommando raden. Klicka på **Starta** \> **Kör** \> och skriv **cmd**, eller tryck på **Windows-tangenten** \> och skriv **cmd**. Skriv in vid uppmaningen  `nslookup <the IP address from the network trace>` . Testa genom att använda nslookup mot din egen dators IP-adress. > du vill se en lista med IP-adressintervall för Microsoft kan du läsa [Office 365 URL: er och IP](https://technet.microsoft.com/library/hh373144.aspx)-adressintervall.

Om det uppstår ett problem bör du vänta lång tids förskjutning för att det ska visas i det här fallet (Outlook online), särskilt i TLS: TLS-paket som visar omslagen av program data (till exempel i Netmon kan du hitta program data paket via  `.Protocol.TLS AND Description == "TLS:TLS Rec Layer-1 SSL Application Data"` ). Du bör se en smidig fördelad tid i hela sessionen. Om du ser långa fördröjningar när du uppdaterar Outlook online kan det bero på att det finns en snabb uppsättning att skicka.

### <a name="latencyround-trip-time"></a>Tid för fördröjning/rund resa

Fördröjning är ett mått som kan ändra ett par beroende på många variabler, sådana uppgraderingar av åldrande enheter, lägga till ett stort antal användare i ett nätverk och procent av total bandbredd som används av andra aktiviteter på en nätverks anslutning.

Det finns bandbredds kalkylatorer för Office 365 på den här sidan [för nätverks planering och prestanda justering för office 365](network-planning-and-performance.md) .  

Behöver du mäta hastigheten på din anslutning, eller din Internet leverantörs bandbredd? Prova den här webbplatsen (eller platserna som den): [speedtest officiella webbplatsen](https://www.speedtest.net/)eller fråga din favorit sökmotor efter fras **hastigheten**.

#### <a name="tools"></a>Verktyg

- Utför
- PsPing
- Netmon
- Wireshark

#### <a name="what-to-look-for"></a>Vad du kan söka efter

Om du vill följa upp svars tiden i en spårning kan du ha spelat in klient datorns IP-adress och IP-adressen för DNS-servern i Office 365. Detta används för enklare spårnings filtrering. Om du ansluter via en proxyserver behöver du klient datorns IP-adress, proxyserverns IP-adress och Office 365 DNS IP-adress för att det ska bli enklare.  

En ping-begäran som skickas till outlook.office365.com anger namnet på det data Center som tar emot begäran, även om ping  *kanske*  inte kan ansluta för att skicka varumärkes paketet i följd. Om du använder PsPing (ett gratis verktyg för nedladdning) och specifikt för porten (443) och kanske använder IPv4 (-4) får du en genomsnittlig tids fördröjning för skickade paket. Det här kommer att fungera för andra URL-adresser i Office 365-tjänsterna `psping -4 yourSite.sharepoint.com:443` . Du kan faktiskt ange ett antal ping-nummer för att få ett större prov för medelvärdet, pröva något som liknar `psping -4 -n 20 yourSite-my.sharepoint.com:443` .  

> [!NOTE]
> PsPing skickar inte ICMP-paket. Det pingar med TCP-paket över en viss port, så att du kan använda vilken som helst som är öppen. I Office 365, som använder SSL/TLS, kan du försöka med att bifoga porten: 443 till din PsPing.

![Skärm bild som visar en ping-lösning för outlook.office365.com och en PSPing med 443 som gör samma sak, men som även rapporterar en normal till en version av 6,5.](../media/c64339f2-2c96-45b8-b168-c2a060430266.PNG)

Om du läste in sidan långsam Office 365 när du utför en nätverks spårning bör du filtrera en Netmon eller wireshark trace för `DNS` . Det här är en av de adresser vi letar efter.  

Här är de här stegen för att filtrera Netmon för att hämta IP-adressen (och ta en titt på DNS-fördröjningen). I det här exemplet används outlook.office365.com, men du kan även använda URL-adressen till en SharePoint Online-klient organisation (till exempel hithere.sharepoint.com).  

1. Skicka ping till URL `ping outlook.office365.com` -adressen och ange namn och IP-adress för DNS-servern som ping-begäran skickades till i resultatet.
2. Nätverks spårning öppnar sidan, eller utför åtgärden som ger dig prestanda problem, eller, om du ser en hög latens för ping, sig själv, spåra det.
3. Öppna spårningen i Netmon och filtret för DNS (det här filtret fungerar också i wireshark, men är känslig för Skift läge `-- dns` ). Eftersom du vet namnet på DNS-servern från din ping kan du också filtrera fler snabbt i Netmon så här: `DNS AND ContainsBin(FrameData, ASCII, "namnorthwest")` , som ser ut så här i wireshark DNS och-ram innehåller "namnorthwest".<br/>Öppna svars paketet och klicka på **DNS** i fönstret Netmon **ram information** för att utöka för att få mer information. I DNS-informationen hittar du IP-adressen till den DNS-server som begäran gick till i Office 365. Du behöver följande IP-adress för nästa steg (verktyget PsPing). Ta bort filtret och högerklicka på DNS-svaret i Netmon (**ram sammanfattningar** \> **Sök efter konversationer** \> **DNS**) för att visa DNS-frågan och svaret sida vid sida.
4. I NetMon går det också att anteckna tids förskjutnings kolumnen mellan DNS-begäran och svaret. I nästa steg är det lätt att installera och använda [PsPing](https://technet.microsoft.com/sysinternals/jj729731.aspx) verktyg som är väldigt praktiskt, både för att ICMP ofta blockeras på brand väggar och eftersom PsPing kan spåra svars tiden i millisekunder. PsPing slutför en TCP-anslutning till en adress och port (i vårt exempel Open port 443).
5. Installera PsPing.
6. Öppna en kommando tolk (starta \> kör \> typen CMD eller Windows-nyckelbaserad \> cmd) och Byt katalog till den katalog där du installerade PsPing för att köra kommandot PsPing. I mina exempel kan du se att jag har gjort en ' perf '-mapp i roten av C. Du kan göra samma sak för snabb åtkomst.
7. Skriv kommandot så att du gör PsPing mot IP-adressen för Office 365 DNS-servern från din tidigare Netmon-spårning, inklusive Port numret, till exempel `psping -n 20 132.245.24.82:445` . Då får du ett prov på 20 pingar och genomsnittlig fördröjning när PsPingen upphör.

Om du kommer till Office 365 via en proxyserver är stegen lite annorlunda. Du ska först PsPing till din proxyserver för att få ett genomsnittligt fördröjnings värde i millisekunder för proxy/utgående och tillbaka, och sedan antingen köra PsPing på proxyservern eller på en dator med en direkt Internet anslutning för att få det värde som saknas (det som gäller för Office 365 och tillbaka).  

Om du väljer att köra PsPing från proxyservern har du två millisekunder-värden: klient dator till proxyserver eller utgångs punkt samt proxyserver till Office 365. Nu är du klar! Dessutom kan du registrera värden.  

Om du kör PsPing på en annan klient dator som har en direkt anslutning till Internet kommer du att ha två millisekunder-värden: klient dator till proxyserver eller utgångs punkt samt klient dator till Office 365. I det här fallet subtraherar du värdet på klient datorn till proxyservern eller utgångs punkten från värdet på klient datorn till Office 365 och du kommer att ha alla söknummer från klient datorn till proxyservern eller utgångs punkten och från proxyservern eller utgångs punkten för Office 365.

Men om du kan hitta en klient dator på den påverkade plats som är direktansluten, eller kringgår proxyn, kan du välja att se om problemet återskapas där och börjar med.

Fördröjning, som den visas i en Netmon-spårning, kan de extra millisekunderna läggas till, om det finns tillräckligt med dem under en given session.  

![Allmän svars tid i Netmon, med kolumnen Netmon standard tid för att delta i ram översikten.](../media/7ad17380-8527-4bc2-9b9b-6310cf19ba6b.PNG)

> [!NOTE]
> Din IP-adress kan skilja sig från de IP-adresser som visas här, till exempel kan dina ping returnera något mer precis som 157.56.0.0/16 eller ett liknande område. En lista över områden som används av Office 365 finns i [URL: er och IP-adressintervall för office 365](https://technet.microsoft.com/library/hh373144.aspx).

Kom ihåg att utöka alla noder (det finns en knapp högst upp) om du vill söka efter, till exempel 132,245.

### <a name="proxy-authentication"></a>Proxyautentisering

Det här gäller bara för dig om du reser via en proxyserver. Annars kan du hoppa över de här stegen. När du arbetar korrekt bör proxyautentisering ske i millisekunder. Dålig prestanda visas inte under de högsta användnings perioderna (till exempel).  

Om proxyautentisering är på, varje gång du gör en ny TCP-anslutning till Office 365 för att få information måste du gå igenom en autentiseringsprocess bakom kulisserna. Om du till exempel byter från kalender till e-post i Outlook online verifieras. Och i SharePoint Online, om en sida visar media eller data från flera webbplatser eller platser verifierar du för varje annan TCP-anslutning som behövs för att återge data.  

I Outlook online kan det uppstå långsamma inläsnings tider när du växlar mellan kalender och post låda eller långsam sida i SharePoint Online. Men det finns andra problem som inte finns med här.

Proxyautentisering är en inställning för din utgående proxyserver. Om det orsakar ett problem med Office 365 måste du kontakta nätverks gruppen.  

#### <a name="tools"></a>Verktyg

- Netmon
- Wireshark

#### <a name="what-to-look-for"></a>Vad du kan söka efter

Proxyautentisering sker när en ny TCP-session måste vara Spuninst, vanligt vis för att begära filer eller information från servern eller för att tillhandahålla info. Till exempel kan du se proxyautentisering med HTTP GET-eller HTTP POST-begäranden. Om du vill visa ramarna där du autentiserar förfrågningar i spårningen lägger du till kolumnen NTLMSSP Summary i Netmon och filtrera efter  `.property.NTLMSSPSummary` . Du kan se hur lång tid det tar genom att lägga till kolumnen tid delta.

Så här lägger du till en kolumn i Netmon:

1. Högerklicka på en kolumn, till exempel **Beskrivning**.
2. Klicka på **Välj kolumner**.
3. Leta _NTLMSSP Summary_ reda på NTLMSSP _och klicka på_ **Lägg till**.
4. Flytta de nya kolumnerna till plats före eller efter kolumnen _Beskrivning_ så att du kan läsa dem sida vid sida.
5. Klicka på **OK**.

Även om du inte lägger till kolumnen, fungerar filtret Netmon. Men din fel sökning blir mycket enklare om du kan se vilken fas av en verifiering du befinner dig i.

När du letar efter en instans av proxyautentisering bör du studera alla ramar där det finns ett NTLM-anrop, eller så finns ett verifierings meddelande. Om det behövs högerklickar du på det specifika värdet för trafik och söker efter konversationer \> TCP. Observera de tidsbesparande värdena i dessa konversationer.

![Netmon-spårning med proxyautentisering, filtrerad efter konversation.](../media/b640f176-0a52-4bbb-972e-60fb3d6aece2.PNG)

En fyra sekunders fördröjning i proxyautentisering som den visas i wireshark. Fältet **tid delta från föregående** kolumn har gjorts genom att högerklicka på ett fält med samma namn i ram informationen och välja Lägg till som kolumn.  <br/> ![I wireshark kan kolumnen "tid delta från föregående visades ram" göras genom att högerklicka på fältet med samma namn i ram informationen och välja Lägg till som kolumn.](../media/f5b7bde4-8067-4ee0-bc7f-e9062ce1ba6f.PNG)

### <a name="dns-performance"></a>DNS-prestanda

Namn matchning fungerar bäst och mest snabbt när det sker så nära klientens land som möjligt.

Om DNS-namnmatchning tar plats kan det lägga till sekunder på sid inläsningar. Det bästa är att namn matchning sker under 100ms. Om du inte gör det bör du göra ytterligare undersökningar.

> [!TIP]
> Vet du inte hur klient anslutningen fungerar i Office 365? Ta en titt på referens dokumentet för klient anslutningen [här](https://technet.microsoft.com/library/dn741250.aspx).

#### <a name="tools"></a>Verktyg

- Netmon
- Wireshark
- PsPing

#### <a name="what-to-look-for"></a>Vad du kan söka efter

Att analysera DNS-prestanda är vanligt vis ett annat jobb för en nätverks spårning. PsPing är emellertid också användbart för att säga upp eller ut, en möjlig orsak.

DNS-trafik är baserad på TCP-och UDP-begäranden och svar markeras tydligt med ett ID som hjälper dig att matcha en viss begäran med dess särskilda svar. DNS-trafik visas när till exempel SharePoint Online använder ett nätverks namn eller en URL-adress på en webb sida. Som en tumregel är det mesta av den här trafiken förutom när zoner överför, körs över UDP.

I både Netmon och wireshark är det mest grundläggande filtret som du kan använda för att titta på DNS-trafik `dns` . Se till att använda gemener när du anger filter. Kom ihåg att tömma din DNS-matchare innan du börjar återskapa problemet på klient datorn. Om du till exempel har en långsam sid inläsning i SharePoint Online för start sidan bör du stänga alla webbläsare, öppna en ny webbläsare, starta spårning, tömma DNS-matcharen och gå till SharePoint Online-webbplatsen. När hela sidan är löst bör du stoppa och spara spårningen.

![Ett grundläggande filter för DNS i Netmon är DNS.](../media/1bebc118-ca13-45f3-803f-ab73e7af401d.png)

Du vill visa tids förskjutningen här. Och det kan vara bra att lägga till kolumnen **tidsdelta** till Netmon som du kan göra genom att utföra de här stegen:

1. Högerklicka på en kolumn, till exempel **Beskrivning**.
2. Klicka på **Välj kolumner**.
3. Sök efter _tid delta_ i listan och klicka på **Lägg till**.
4. Flytta den nya kolumnen till plats före eller efter kolumnen _Beskrivning_ så att du kan läsa dem sida vid sida.
5. Klicka på **OK**.

Om du hittar en fråga om ränta kan du isolera den genom att högerklicka på frågan i ram informations panelen och välja **hitta konversations** \> **-DNS**. Observera att panelen nätverks konversationer går direkt till den specifika konversationen i loggen över UDP-trafik.

![En Netmon spårning av Outlook online-hämtning filtrerad efter DNS och Använd hitta konversationer och sedan DNS för att begränsa resultatet.](../media/763cf20e-7b48-4a37-9449-c9978cfe118b.PNG)

I wireshark kan du göra en kolumn för DNS-tid. Ta med dig spåret (eller öppna en spårning) i wireshark och filtrera efter `dns` , eller, mer praktiskt,  `dns.time` . Klicka på en DNS-fråga och expandera sedan informationen i panelen  `Domain Name System (response)` . Du ser ett fält för tid (till exempel `[Time: 0.001111100 seconds]` . Högerklicka på den här gången och välj **Använd som kolumn**. Då får du en **tids** kolumn för snabbare sortering av spårningen. Klicka på den nya kolumnen för att sortera efter fallande värden för att se vilket DNS-samtal som tog för det senaste.

[En genom gång av SharePoint Online filtrerad i wireshark efter (gemener) DNS. Time, med tiden från informationen i en kolumn och sorterad i stigande ordning.](../media/1439dcc2-12ff-4ee2-9ef3-1484cf79c384.PNG)

Om du vill ha mer information om DNS-matchningstid kan du försöka med en PsPing mot DNS-porten som används av TCP (till exempel  `psping <IP address of DNS server>:53` ). Ser du ett prestanda problem ändå? Om du gör det är problemet troligen mer troligt för ett problem med nätverks problem än ett visst DNS-program som du använder för att utföra en lösning. Det är också värt att nämna att ett ping till outlook.office365.com anger var DNS-namnmatchning för Outlook online äger rum (till exempel outlook-namnorthwest.office365.com).

Om problemet verkar vara DNS-specifikt kan det vara nödvändigt att kontakta IT-avdelningen för att titta på DNS-konfigurationer och DNS-vidarebefordrare för att ytterligare undersöka det här problemet.

### <a name="proxy-scalability"></a>Skalbarhet för proxyserver

Tjänster som Outlook online i Office 365 tilldelar klienter flera långsiktiga anslutningar. Därför kan varje användare använda fler anslutningar som kräver längre livs längd.  

#### <a name="tools"></a>Verktyg

Beräkna  

#### <a name="what-to-look-for"></a>Vad du kan söka efter

Det finns inget fel söknings verktyg för nätverk. I stället baseras det på bandbredds beräkningar och andra variabler.  

### <a name="tcp-max-segment-size"></a>Max storlek för TCP-segment

Finns i tillståndet SYN-SYN/ACK.  Gör den här kontrollen i alla prestanda nätverks spårningar som du har gjort för att säkerställa att TCP-paketen är konfigurerade för att medföra maximal mängd data.

Målet är att se en MSS på 1460 byte för överföring av data. Om du befinner dig bakom en proxyserver, eller om du använder en NAT, kom ihåg att köra det här testet från klient till proxy/utgång/NAT och från proxy/utgång/NAT till Office 365 för bästa resultat. Det här är olika TCP-sessioner.

#### <a name="tools"></a>Verktyg

Netmon

#### <a name="what-to-look-for"></a>Vad du kan söka efter

TCP Max segment storlek (MSS) är en annan parameter för den tre-vägshandskakning i nätverks spårningen, vilket innebär att du hittar de data du behöver i tillståndet SYN-SYN/ACK. MSS är ganska lätt att se.

Öppna alla prestanda nätverks spårningar som du har och leta reda på anslutningen du är nyfiken på, eller som demonstrerar prestanda problemet.

> [!NOTE]
> Om du tittar på en spårning och behöver hitta den trafik som är relevant för konversationen, filtrerar du efter IP-adressen för klienten eller IP för proxyservern eller utgångs punkten eller både och. Nu måste du skicka ping till den URL som du testar för IP-adressen för Office 365 i spåret och filtrera efter den.

Titta på den andra-handen för spårningen? Prova att använda filter för att orientera dig. I Netmon kör du en sökning baserat på URL-adressen, till exempel `Containsbin(framedata, ascii, "sphybridExample")` , och antecknar ram numret.

I wireshark används till exempel  `frame contains "sphybridExample"` . Om du märker att du har hittat Remote Winsock (RWS)-trafik (det kan visas som [PSH, ACK] i wireshark), kom ihåg att RWS-anslutningar kan ses inom kort innan relevanta SYN-SYN/bekräftelse, enligt beskrivningen ovan.

I det här läget kan du spela in RAM numret, släppa filtret, klicka på **all trafik** i fönstret för nätverks konversationer i Netmon för att se närmaste syn.

Om du inte har fått någon av IP-adresserna samtidigt som spårningen, kan du hitta din URL i spårningen ( `sphybridExample-my.sharepoint.com` till exempel) för att filtrera efter.

Leta reda på anslutningen i spåret som du är intresse rad av. Du kan göra det genom att antingen Skanna spårningen, genom att filtrera efter IP-adresser, eller genom att välja specifika Konversations-ID med hjälp av fönstret för nätverks konversationer i Netmon. När du har hittat SYN-paketet expanderar du TCP (i Netmon) eller Transmission Control Protocol (i wireshark) i panelen ram information. Expandera TCP-alternativ och MaxSegmentSize. Leta reda på den relaterade SYN-ACK-ramen och expandera TCP-alternativen och MaxSegmentSize. Den mindre av de två värdena blir den maximala storleken på segmentet. I den här bilden använder jag den inbyggda kolumnen i Netmon som heter TCP-felsökning.  

![Nätverks spårning filtrerad i Netmon med de inbyggda kolumnerna.](../media/e073df13-71f8-497a-83b4-bb9f70bd9833.PNG)

Den inbyggda kolumnen visas överst i panelen **ram information** . (Om du vill växla tillbaka till normalvyn klickar du på **kolumner** igen och väljer tidszon **.)**

![Var du hittar List rutan kolumner för fel söknings alternativ för TCP (överst i ram sammanfattningen).](../media/64fd4baa-a872-4f07-b959-752d7d37fd62.PNG)

Här är en filtrerad spårning i wireshark. Det finns ett filter som är specifikt för MSS-värdet ( `tcp.options.mss` ). Ramarna för en SYN-, SYN-/ACK-handskakning är länkade längst ned i wireshark-motsvarigheten till ram detaljer (så ram 47 ACK, länkar till 46 SYN/ACK, länkar till 43 SYN) för att det ska bli enklare.

![Spårning filtrerad i wireshark med TCP. Options. MSS för max segment storlek (MSS).](../media/51e278db-801b-48bc-9b68-87cf92f03fd6.PNG)

Om du behöver kontrol lera den **selektiva bekräftelsen** (Nästa ämne i matrisen) stänger du inte spårningen!

### <a name="selective-acknowledgment"></a>Selektiv bekräftelse

Finns i tillståndet SYN-SYN/ACK. Måste rapporteras enligt både SYN och SYN/ACK. Selektiv bekräftelse (säck) möjliggör smidig återöverföring av data när ett paket eller paket går ut. Enheter kan inaktivera denna funktion, vilket kan leda till prestanda problem.

Om du befinner dig bakom en proxyserver, eller om du använder en NAT, kom ihåg att köra det här testet från klient till proxy/utgång/NAT och från proxy/utgång/NAT till Office 365 för bästa resultat. Det här är olika TCP-sessioner.

#### <a name="tools"></a>Verktyg

Netmon

#### <a name="what-to-look-for"></a>Vad du kan söka efter

Selektiv bekräftelse (säck) är en annan parameter i tillståndet SYN-SYN/ACK. Du kan filtrera spårningen för SYN-och SYN många olika sätt.

Leta reda på anslutningen i spåret som du är intresse rad av genom att skanna in spårning, filtrering av IP-adresser eller genom att klicka på ett Konversations-ID med hjälp av fönstret för nätverks konversationer i Netmon. När du har hittat SYN-paketet expanderar du TCP i Netmon eller Transmission Control Protocol i wireshark i avsnittet ram Detaljer. Expandera TCP-alternativen och sedan SÄCKAR. Leta reda på den relaterade SYN-ACK-ramen och expandera TCP-alternativen och dess SÄCKAR-fält. Gör vissa SÄCKAR tillåtna i både SYN och SYN/ACK. Här är de här SÄCKAR-värdena som de visas i både Netmon och wireshark.

![Selektiv bekräftelse (säck) i Netmon som ett resultat av TCP. Flags. syn = = 1.](../media/216f556f-5031-4ed2-b066-a0d9b3251fa2.PNG)

![SÄCKAR som visas i wireshark med filtret TCP. Flags. syn = = 1.](../media/0a6e26e5-43dc-403b-adc9-3349a55f4e4b.PNG)

### <a name="dns-geolocation"></a>DNS-språkplats

Var i världen Office 365 försöker lösa ditt DNS-samtal påverkar din anslutnings hastighet.

När den första DNS-sökningen är slutförd i Outlook online kommer platsen för den DNS-servern att användas för att ansluta till närmaste Data Center. Du ansluts till en Outlook online-certifikatutfärdare, som använder stamnätet för att ansluta till data centret (dC) där dina data lagras. Det här är snabbare.

När du ansluter till SharePoint Online kommer en användare som reser utomlands att dirigeras till deras aktiva data Center-det är den domänkontrollant vars plats är baserad på sin SPO-klientens hem-bas (så var en domänkontrollant i USA om användaren har en amerikansk grund).

Lync Online har aktiva noder på mer än en domänkontrollant åt gången. När förfrågningar skickas för Lync Online-instanser bestäms var i världen begäran kom från och returnerar IP-adresser från den närmaste regionala domänkontrollanten där Lync Online är aktivt.

> [!TIP]
> Behöver du veta mer om hur klienter ansluter till Office 365? Ta en titt på artikeln om referens för [klient anslutningar](https://technet.microsoft.com/library/dn741250.aspx) (och dess hjälp grafik).

#### <a name="tools"></a>Verktyg

- Utför
- PsPing

#### <a name="what-to-look-for"></a>Vad du kan söka efter

Begäran om namn matchning från klientens DNS-servrar till Microsofts DNS-servrar bör i de flesta fall resultera i att Microsoft DNS returnerar IP-adressen för ett regionalt Data Center (dC). Vad innebär det för dig? Om ditt Office-kontor är i Bangalore, Indien, men du reser i USA, kan Microsofts DNS-servrar bli dina IP-adresser till data Center i USA – ett regionalt Data Center. Om e-post behövs från Outlook kommer denna information att bedrivas mellan Microsoft Quick netcentre-nätverket.

DNS fungerar snabbast när namn matchning görs så nära användarens plats som möjligt. Om du är i Europa vill du gå till en Microsoft DNS i Europa och (helst) med ett Data Center i Europa. Prestanda från en klient i Europa till DNS och ett Data Center i Amerika blir långsammare.

Kör pingverktyget mot outlook.office365.com för att avgöra var i världen din DNS-begäran dirigeras. Om du är i Europa bör du se ett svar från något liknande outlook-emeawest.office365.com. I Amerika förväntar jag något liknande outlook-namnorthwest.office365.com.

Öppna kommando tolken på klient datorn (via Start kommando \> för \> cmd eller Windows \> -tangenten Cmd). Skriv ping outlook.office365.com och tryck på RETUR. Kom ihåg att ange-4 om du vill skicka ping via IPv4. Det kan hända att du inte får ett svar från ICMP-paketen, men du bör se namnet på den DNS som begäran cirkulerats till. Om du vill se svars numret för den här anslutningen försöker du med PsPing IP-adress till den server som returneras av ping.  

![Ping på outlook.office365.com som visar upplösning i Outlook-namnorthwest.](../media/06c944d5-6159-43ec-aa31-757770695e8b.PNG)

![PSPing till IP-adressen som returneras av ping till outlook.office365.com med genomsnittlig fördröjning på 28 millisekunder.](../media/f2b25a75-1a87-4479-b8a7-fa4375683507.PNG)

### <a name="office-365-application-troubleshooting"></a>Office 365-program fel sökning

#### <a name="tools"></a>Verktyg

- Netmon
- HTTPWatch
- F12-konsol i webbläsaren

Vi täcker inte verktyg som används för programspecifik fel sökning i den här nätverksmappen artikeln. Men du hittar resurser som du  *kan*  använda [på den här sidan](https://support.office.com/article/Network-planning-and-performance-tuning-for-Office-365-e5f1228c-da3c-4654-bf16-d163daee8848).

## <a name="related-topics"></a>Närliggande ämnen

[Hantera slut punkter för Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
  
[Vanliga frågor om Office 365-slut punkter](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)
