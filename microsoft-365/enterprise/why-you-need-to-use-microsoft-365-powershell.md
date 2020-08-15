---
title: Därför måste du använda PowerShell för Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: ''
ms.assetid: b3209b1a-40c7-4ede-8e78-8a88bb2adc8a
description: 'Sammanfattning: förstå varför du måste använda PowerShell för att hantera Microsoft 365, i vissa fall mer effektivt och i andra fall efter nödvändighet.'
ms.openlocfilehash: 7220356cd79b03674661ace386fd1d38a7e39587
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694340"
---
# <a name="why-you-need-to-use-powershell-for-microsoft-365"></a>Därför måste du använda PowerShell för Microsoft 365

*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*

Med administrations centret för Microsoft 365 kan du inte bara hantera dina användar konton och licenser för Microsoft 365, men du kan även hantera dina Microsoft 365-tjänster, till exempel Exchange Online, teams och SharePoint Online. Men du kan också hantera de här elementen med PowerShell-kommandon och dra nytta av en kommando rads-och skript språk miljö för hastighet, automatisering och annan kapacitet.
  
I den här artikeln visar vi hur du kan använda PowerShell för att hantera Microsoft 365:
  
- Visa ytterligare information som du inte kan se med administrations centret för Microsoft 365
    
- Konfigurera funktioner och inställningar endast möjligt med PowerShell
    
- Utför Mass åtgärder
    
- Filtrera data
    
- Skriva ut eller spara data
    
- Hantera mellan tjänster
    
Innan du börjar förstår du att PowerShell för Microsoft 365 är en uppsättning moduler för Windows PowerShell, en kommando rads miljö för Windows-baserade tjänster och plattformar. Den här miljön skapar ett gränssnitts språk som kan utökas med ytterligare moduler och ger dig en möjlighet att utföra enkla eller komplexa kommandon eller skript. När du till exempel har installerat PowerShell för Microsoft 365-moduler och ansluter till din Microsoft 365-prenumeration kan du köra det här kommandot för att visa alla användar post lådor för Microsoft Exchange Online:
  
```powershell
Get-Mailbox
```

Det är lätt att hämta listan med post lådor med hjälp av administrations centret för Microsoft 365, men det är lätt att räkna antalet objekt i alla listor för alla dina webb program.
  
Observera att PowerShell för Microsoft 365 är utformat för att utöka och förbättra din förmåga att hantera Microsoft 365, inte för att ersätta Microsoft 365 Admin Center. Som administratör måste du vara minst van vid att använda PowerShell för Microsoft 365 eftersom det finns vissa konfigurations procedurer som bara kan utföras med PowerShell för Microsoft 365-kommandon. I sådana fall måste du förstå hur du kan:
  
- Installera PowerShell för Microsoft 365-moduler (utförs bara en gång för varje administratörs dator).
    
- Anslut till ditt Microsoft 365-abonnemang (utförs en gång för varje PowerShell-session).
    
- Samla in den information som behövs för att köra de PowerShell för Microsoft 365-kommandon som krävs.
    
- Kör PowerShell för Microsoft 365-kommandon.
    
Efter att ha lärt de här grundläggande färdigheterna behöver du inte lista dina post lådor med kommandot **Hämta-post låda** , eller så behöver du inte förstå hur du skapar ett nytt kommando som föregående om du vill räkna alla objekt i alla dina webb program. Microsoft och communityn för administratörer kan hjälpa dig med det som behövs.
  
## <a name="powershell-for-microsoft-365-can-reveal-additional-information-that-you-cannot-see-with-the-microsoft-365-admin-center"></a>PowerShell för Microsoft 365 kan visa ytterligare information som du inte kan se med administrations centret för Microsoft 365

Administrations centret för Microsoft 365 visar mycket värdefull information, men det betyder inte att det visar all den information som Microsoft 365 lagrar på användare, licenser, post lådor och webbplatser. Här är ett exempel på **användare och grupper** i Microsoft 365 Admin Center:
  
![Exempel på hur användare och grupper visas i administrations centret för Microsoft 365.](../media/o365-powershell-users-and-groups.png)
  
I många avseenden visar detta den information du behöver veta. Men det finns tillfällen då du behöver mer. Microsoft 365-licensiering (och de Microsoft 365-funktioner som är tillgängliga för en användare) beror till exempel på användarens geografiska plats. De principer och funktioner som du kan förlänga till en användare som bor i USA kanske inte är samma som de principer och funktioner som du kan förlänga till en användare som bor i Indien eller i Belgien. Du kan använda administrations centret för Microsoft 365 för att fastställa en användares geografiska plats med de här stegen:
  
1. Dubbelklicka på användarens **visnings namn**.
    
2. I fönstret användar egenskaper klickar du på **information**.
    
3. Klicka på **Ytterligare information**i informations fönstret.
    
4. Bläddra nedåt tills du ser rubriken **land eller region**:
    
     ![Exempel på region informationen för en användare i administrations centret för Microsoft 365.](../media/o365-powershell-usage-location.png)
  
5. Skriv användarens visnings namn och plats på papperet, eller kopiera och klistra in i anteckningar. 
    
Du måste upprepa proceduren för varje användare. För många användare kan det vara en omständlig uppgift. Med PowerShell för Microsoft 365 kan du Visa den här informationen för alla dina användare med följande kommando:
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```


>[!Note]
>PowerShell Core stöder inte Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen och cmdlets med **MSOL** . För att kunna fortsätta använda dessa cmdletar måste du köra dem från Windows PowerShell.
>

Här är ett exempel på skärmen:
  
```powershell
DisplayName                               UsageLocation
-----------                               -------------
Bonnie Kearney                            GB
Fabrice Canel                             BR
Brian Johnson (TAILSPIN)                  US
Anne Wallace                              US
Alex Darrow                               US
David Longmuir                            BR
```

> [!TIP]
>  Tolkningen av detta PowerShell-kommando är: Hämta alla användare i den aktuella Microsoft 365-prenumerationen ( **Get-AzureADUser** ), men Visa bara namn och plats för varje användare ( **Välj DisplayName, UsageLocation** ).
  
Eftersom PowerShell för Microsoft 365 stöder ett kommando gränssnitts språk kan du ytterligare ändra informationen som hämtas från kommandot **Get-AzureADUser** . Om du till exempel vill sortera dessa användare efter deras placering, kan du gruppera alla användare i Brasilien, alla användare i USA, etc. Här är kommandot:
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation | Sort UsageLocation, DisplayName
```

Här är ett exempel på skärmen:
  
```powershell
DisplayName                                 UsageLocation
-----------                                 -------------
David Longmuir                              BR
Fabrice Canel                               BR
Bonnie Kearney                              GB
Alex Darrow                                 US
Anne Wallace                                US
Brian Johnson (TAILSPIN)                    US
```

> [!TIP]
>  Tolkningen av det här PowerShell-kommandot är: Hämta alla användare i den aktuella Microsoft 365-prenumerationen, men Visa bara namn och plats för varje användare och sortera dem först efter deras placering och sedan deras namn ( **Sortera UsageLocation, DisplayName** ).
  
Du kan också använda ytterligare filtrering. Om du till exempel vill visa information om användare som är baserade i Brasilien använder du det här kommandot:
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq "BR"} | Select DisplayName, UsageLocation 
```

Här är ett exempel på skärmen:
  
```powershell
DisplayName                                           UsageLocation
-----------                                           -------------
David Longmuir                                        BR
Fabrice Canel                                         BR
```

> [!TIP]
>  Tolkningen av detta PowerShell-kommando är: Hämta alla användare i den aktuella Microsoft 365-prenumerationen vars plats är Brasilien ( **där {$ \_ . UsageLocation-EQ "BR"}** ) och visar sedan namn och plats för varje användare.
  
 **En snabb anteckning angående större domäner**
  
Om du har en mycket stor domän med tusentals användare kan du prova några av exemplen som vi visar i den här artikeln leda till "begränsning". Det innebär att beroende på saker som dator kraft och tillgänglig nätverks bandbredd, försöker du göra lite för mycket åt gången. Därför kan det vara bra att dela upp några av dessa PowerShell för Microsoft 365-kommandon i två kommandon. Till exempel returnerar det här kommandot alla användar konton och visar namn och plats för var och en av dem:
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```

Det passar utmärkt för mindre domäner. I en stor organisation kan du behöva dela upp det i två kommandon: ett kommando för att lagra användar konto informationen i en variabel och ett annat kommando för att visa nödvändig information. Här är ett exempel:
  
```powershell
$x = Get-AzureADUser
$x | Select DisplayName, UsageLocation
```

Tolkningen av denna uppsättning PowerShell-kommandon är:
- Hämta alla användare i den aktuella Microsoft 365-prenumerationen och lagra informationen i en variabel som heter $x ( **$x = get-AzureADUser** ).
- Visa innehållet i variabeln $x, men inkludera bara namn och plats för varje användare ( **$x | Välj DisplayName, UsageLocation** ).
  
## <a name="microsoft-365-has-features-that-you-can-only-configure-with-powershell-for-microsoft-365"></a>Microsoft 365 har funktioner som du bara kan konfigurera med PowerShell för Microsoft 365

Administrations centret för Microsoft 365 är avsett att ge till gång till de vanligaste eller meningsfulla administrativa uppgifter som gäller för de flesta användare. Med andra ord har Microsoft 365 Admin Center konstruerats så att den typiska administratören kan använda verktyget för att utföra de vanligaste hanterings uppgifterna. Genom den här definitionen innebär det att det finns vissa uppgifter som inte kan utföras med hjälp av administrations centret för Microsoft 365.
  
Administrations centret för Skype för företag – Online innehåller till exempel några få alternativ för att skapa anpassade Mötes inbjudningar:
  
![Exempel på hur anpassade mötesinbjudan visas i administrations centret för Skype för företag – online.](../media/o365-powershell-meeting-invitation.png)
  
Med de här inställningarna kan du lägga till och anpassa Mötes inbjudningar. Men det finns mer information om konfigurations inställningar för möten än att skapa anpassade Mötes inbjudningar. Som standard tillåter möten till exempel:
  
- Anonyma användare får automatisk ingång till varje möte.
    
- Deltagare att spela in i mötet.
    
- Alla användare i organisationen ska utses till presentatörer när de ansluter till mötet.
    
Dessa inställningar är inte tillgängliga från administrations centret för Skype för företag – online. Men du kan styra dem från PowerShell för Microsoft 365. Här är ett kommando som inaktiverar dessa tre inställningar:
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False -AllowConferenceRecording $False -DesignateAsPresenter "None"
```

> [!NOTE]
> Det här kommandot kräver att du installerar [PowerShell-modulen för Skype för företag – Online ](https://www.microsoft.com/download/details.aspx?id=39366). 
  
> [!TIP]
>  Tolkningen av det här PowerShell-kommandot är: för inställningar för nya Skype för företag – Online-möten ( **set-CsMeetingConfiguration** ) inaktiverar du tillåta att anonyma användare får automatisk ingång till möten ( **-AdmitAnonymousUsersByDefault $false** ), inaktiverar möjligheten för deltagare att spela in möten ( **$false-** **DesignateAsPresenter "inget"** ).
  
Om du ändrar dig och vill återställa dessa standardinställningar (alla aktiverade) kör du det här kommandot:
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $True -AllowConferenceRecording $True -DesignateAsPresenter "Company"
```

Det här är bara ett exempel. Det finns andra, som du måste känna till genom att köra PowerShell för Microsoft 365-kommandon.
  
## <a name="powershell-for-microsoft-365-is-great-at-carrying-out-bulk-operations"></a>PowerShell för Microsoft 365 är perfekt när de utför Mass åtgärder

Historiskt, visuella gränssnitt som Microsoft 365 Admin Center är mest värdefulla när du har en enda åtgärd att utföra. Om du till exempel behöver inaktivera ett användar konto kan du använda administrations centret för Microsoft 365 för att snabbt hitta och avmarkera en kryss ruta. Det kan vara enklare än att utföra en liknande åtgärd i PowerShell.
  
Men om du behöver ändra många saker eller vissa markerade saker i en stor uppsättning andra saker kanske administrations centret för Microsoft 365 inte är det bästa med din tid. Om du till exempel hade ändrat prefix på tusentals telefonnummer eller om du vill ta bort en specifik användare, Katarina Myer, från alla SharePoint Online-webbplatser, hur gör du det i administrations centret för Microsoft 365?
  
I det senare exemplet har du flera hundra SharePoint Online-webbplatser och du vet inte ens vilka Katarina Meyer är medlem. Det innebär att du måste starta i administrations centret för Microsoft 365 och sedan utföra den här proceduren för varje webbplats:
  
1. Klicka på webbplatsens **URL-adress** .
    
2. I rutan **Egenskaper för webbplats samling** klickar du på länken webbplats **adress** för att öppna webbplatsen.
    
3. Klicka på **dela**på webbplatsen.
    
4. I dialog rutan **dela** klickar du på länken som visar alla användare som har behörighet till webbplatsen:
    
     ![Exempel på hur du visar medlemmarna på en SharePoint Online-webbplats i administrations centret för SharePoint Online.](../media/o365-powershell-view-permissions.png)
  
5. Klicka på **Avancerat**i dialog rutan **delas med** .
    
6. Bläddra nedåt i listan med användare, hitta och välj Katarina Myer (förutsatt att han har behörighet till webbplatsen) och klicka sedan på **ta bort användar behörigheter**.
    
Det kan ta lång tid för flera hundra webbplatser.
  
Alternativet är att använda PowerShell för Microsoft 365 och följande kommando för att ta bort Katarina Myer från alla webbplatser:
  
```powershell
Get-SPOSite | ForEach {Remove-SPOUser -Site $_.Url -LoginName "kenmyer@litwareinc.com"}
```

> [!NOTE]
> Det här kommandot kräver att du installerar [SharePoint Online PowerShell-modulen](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps). 
  
> [!TIP]
>  Tolkningen av det här PowerShell-kommandot är: Hämta alla SharePoint-webbplatser i den aktuella Microsoft 365-prenumerationen ( **Get-SPOSite** ) och för varje webbplats tar du bort Katarina Meyer från listan över användare som har åtkomst till den ( **sol{Remove-make-in-site $ \_ . URL – LoginName "kenmyer@litwareinc.com"}** ).
  
Eftersom vi meddelar att Microsoft 365 tar bort Katarina Meyer från alla webbplatser, inklusive de som han inte har åtkomst till, visar kommandot fel för de webbplatser som han för tillfället inte har åtkomst till. Vi kan använda ett ytterligare villkor i det här kommandot för att ta bort Meyer endast från webbplatser som har sin inloggnings lista, men de fel som visas i listan är inte skadliga för själva webbplatserna. Det kan ta några minuter att köra det här kommandot för hundratals webbplatser, i stället för timmar med att arbeta via Microsoft 365 Admin Center.
  
Här är ett annat Mass åtgärds exempel. Använd det här kommandot för att lägga till Håkans Kearney, en ny SharePoint-administratör, på alla webbplatser i organisationen:
  
```powershell
Get-SPOSite | ForEach {Add-SPOUser -Site $_.Url -LoginName "bkearney@litwareinc.com" -Group "Members"}
```

> [!TIP]
>  Tolkningen av det här PowerShell-kommandot är: Hämta alla SharePoint-webbplatser i den aktuella Microsoft 365-prenumerationen och för varje webbplats kan du låta Håkans Kearney Access genom att lägga till hennes inloggnings namn i gruppen medlemmar på webbplatsen ( **sol{Add-makar-site $ \_ . URL – LoginName "bkearney@litwareinc.com" – grupp "medlemmar"}** ).
  
## <a name="powershell-for-microsoft-365-is-great-at-filtering-data"></a>PowerShell för Microsoft 365 är ett bra sätt att filtrera data

Administrations centret för Microsoft 365 tillhandahåller flera olika sätt att filtrera data så att du snabbt och enkelt kan hitta en viss del av informationen. Med Exchange blir det till exempel enkelt att filtrera på en användares post låda i praktiskt taget. Här är en lista med post lådor för alla användare som bor i staden Bloomington:
  
![Exempel på en avancerad sökning i administrations centret för Microsoft 365 för listan med post lådor för alla användare som bor i staden Bloomington.](../media/o365-powershell-advanced-search.png)
  
I administrations centret för Exchange kan du även kombinera filter villkor. Du kan till exempel hitta post lådorna för alla personer som bor i Bloomington och som arbetar på ekonomi avdelningen. 
  
Men det finns begränsningar i administrations centret för Exchange. Du kanske till exempel vill hitta post lådorna för personer som bor i Bloomington eller San Diego eller post lådorna för alla personer som inte bor i Bloomington. 
  
Med PowerShell för Microsoft 365 kan du hämta en lista med post lådor för alla personer som bor i städer med Bloomington eller San Diego med det här kommandot:
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and ($_.City -eq "San Diego" -or $_.City -eq "Bloomington")} | Select DisplayName, City
```

Här är ett exempel på skärmen:
  
```powershell
DisplayName                              City
-----------                              ----
Alex Darrow                              San Diego
Bonnie Kearney                           San Diego
Julian Isla                              Bloomington
Rob Young                                Bloomington
```

> [!TIP]
>  Tolkningen av detta PowerShell-kommando är: Hämta alla användare i den aktuella Microsoft 365-prenumerationen som har en post låda i städer med antingen San-Diego eller Bloomington ( **där {$ \_ . En-EQ "UserMailbox"-och ($ \_ . City-EQ "San Diego"-eller $ \_ . City-EQ "Bloomington")}** ) och visar sedan namnet och staden för var och en av dem ( **Välj DisplayName, ort** ).
  
Så här gör du för att visa alla post lådor för personer som bor var som helst förutom Bloomington:
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and $_.City -ne "Bloomington"} | Select DisplayName, City
```

Här är ett exempel på skärmen:
  
```powershell
DisplayName                               City
-----------                               ----
MOD Administrator                         Redmond
Alex Darrow                               San Diego
Allie Bellew                              Bellevue
Anne Wallace                              Louisville
Aziz Hassouneh                            Cairo
Belinda Newman                            Charlotte
Bonnie Kearney                            San Diego
David Longmuir                            Waukesha
Denis Dehenne                             Birmingham
Garret Vargas                             Seattle
Garth Fort                                Tulsa
Janet Schorr                              Bellevue
```

> [!TIP]
>  Tolkningen av detta PowerShell-kommando är: Hämta alla användare i den aktuella Microsoft 365-prenumerationen som har en post låda som inte finns i staden Bloomington ( **där {$ \_ . En-EQ "UserMailbox"-and $ \_ . City-Ne "Bloomington"}** ) och visar sedan namnet och staden för varje.
  
Du kan också använda jokertecken i dina PowerShell-filter för att matcha delar av ett namn. Anta till exempel att du letar efter ett användar konto och alla du kan komma ihåg är att deras efter namn var Anderson eller kanske Henderson eller att det var Jorgenson.
  
Du kan spåra användaren i administrations centret för Microsoft 365 genom att använda sökverktyget och utföra tre olika sökningar:
  
- En för  *Anderson* 
    
- En för  *Henderson* 
    
- En för  *Jorgenson* 
    
Eftersom alla tre av namnen slutar med "son" kan du se till att PowerShell visar alla användare vars namn slutar på "son". Här är kommandot:
  
```powershell
Get-User -Filter '{LastName -like "*son"}'
```

> [!TIP]
>  Tolkningen av det här PowerShell-kommandot är: Hämta alla användare i den aktuella Microsoft 365-prenumerationen, men Använd ett filter som bara visar de användare vars senaste namn slutar med "son" ( **-filter ' {efter namn-like " \* son"} '** ). En \* uppsättning tecken som är bokstäver i användarens efter namn.
  
## <a name="powershell-for-microsoft-365-makes-it-easy-to-print-or-save-data"></a>Med PowerShell för Microsoft 365 blir det enkelt att skriva ut eller spara data

Med administrations centret för Microsoft 365 kan du Visa listor med data. Här är ett exempel på administrations centret för Skype för företag – online som visar en lista över användare som har Aktiver ATS för Skype för företag – online:
  
![Exempel på administrations centret för Skype för företag – online som visar en lista över användare som har Aktiver ATS för Skype för företag – online.](../media/o365-powershell-lync-users.png)
  
Om du vill spara informationen i en fil måste du kopiera och klistra in den i ett dokument eller Excel. I båda fallen kan kopieringen behöva ytterligare formatering. Administrations centret för Microsoft 365 kan dessutom inte skriva ut den lista som visas direkt.
  
Som tur är kan du använda PowerShell för att inte bara visa listan, utan att spara den i en fil som enkelt kan importeras till Excel. Här är ett exempel kommando för att spara användar data för Skype för företag – Online i en CSV-fil (kommaseparerade värden), en fil som enkelt kan importeras som en tabell i ett Excel-kalkylblad:
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Export-Csv -Path "C:\Logs\SfBUsers.csv" -NoTypeInformation
```

Här är ett exempel på skärmen:
  
![Exempel på en tabell som importer ATS till ett Excel-kalkylblad för användare av Skype för företag – online som sparats i en CSV-fil (kommaseparerade värden).](../media/o365-powershell-data-in-excel.png)
  
> [!TIP]
>  Tolkningen av detta PowerShell-kommando är: Hämta alla Skype för företag – Online-användare i den aktuella Microsoft 365-prenumerationen ( **Get-CsOnlineUser** ), skaffa endast användar namn, UPN och plats ( **Välj DisplayName, userPrincipalName, UsageLocation** ) och spara sedan informationen i CSV-filen med namnet C: \\ loggar \\SfBUsers.csv ( **export-CSV-Path "C: \\ logs \\SfBUsers.csv"-NoTypeInformation** ).
  
Du kan också använda alternativen för att spara denna lista som en XML-fil eller som en HTML-sida. Med ytterligare PowerShell-kommandon kan du faktiskt spara det direkt som en Excel-fil med eventuell anpassad formatering. 
  
Du kan också skicka utdata från ett PowerShell-kommando som visar en lista direkt till standard skrivaren i Windows. Här är ett exempel kommando:
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Out-Printer
```

Så här ser det utskrivna dokumentet ut:
  
![Exempel på ett utskrivet dokument som visade att ett PowerShell-kommando visas direkt på standard skrivaren i Windows.](../media/o365-powershell-printed-data.png)
  
> [!TIP]
>  Tolkningen av det här PowerShell-kommandot är: Hämta alla Skype för företag – Online-användare i den aktuella Microsoft 365-prenumerationen, Hämta endast användar namn, UPN och plats och skicka sedan informationen till standard skrivaren för Windows ( **ut-skrivaren** ).
  
Det utskrivna dokumentet har samma enkla formatering som visas i PowerShell-Kommandotolken, men när du har skapat ett PowerShell-kommando som visar det du behöver lägger du till **| Ut-skrivaren** till slutet av kommandot för att få en pappers kopia att arbeta från.
  
## <a name="powershell-for-microsoft-365-lets-you-manage-across-server-products"></a>Med PowerShell för Microsoft 365 kan du hantera olika Server produkter

De olika komponenter som utgör Microsoft 365 är utformade för att fungera tillsammans. Anta till exempel att du lägger till en ny användare i Microsoft 365 och anger den informationen som användarens avdelning och telefonnummer när du gör det. Denna information kommer att vara tillgänglig om du använder någon av Microsoft 365-tjänsterna: Skype för företag – Online, Exchange eller SharePoint Online.
  
Men det är för gemensam information som omfattar produkterna. Produktspecifika information – till exempel kan information om en användares Exchange-postlåda inte vara tillgänglig i hela paketet. Om du till exempel vill veta om en användares post låda är aktive rad eller inte är den informationen bara tillgänglig i administrations centret för Exchange. 
  
Anta att du vill skapa en rapport som visar följande information för alla dina användare:
  
- Användarens visnings namn
    
- Om användaren är licensierad för Microsoft 365
    
- Om användarens Exchange-postlåda har Aktiver ATS
    
- Om användaren är aktive rad för Skype för företag – Online
    
Du kan för närvarande inte använda administrations centret för Microsoft 365 för att enkelt skapa en sådan rapport. I stället måste du skapa ett separat dokument för att lagra informationen, till exempel ett Excel-kalkylblad, och få alla användar namn och licensierings information från administrations centret för Microsoft 365, hämta information om post lådor från administrations centret för Exchange, få information om Skype för företag – Online från administrations centret för Skype för företag – Online och sedan sortera och kombinera den informationen.
  
Alternativet är att använda ett PowerShell-skript för att kompilera rapporten åt dig.
  
Följande exempel skript är mer komplicerat än de kommandon du har sett hittills i den här artikeln. Men det visar potentialen för att använda PowerShell för att skapa vyer av information som är mycket svår att göra. Här är det skript som kan kompilera och visa en nödvändig lista:
  
```powershell
$x = Get-AzureADUser

foreach ($i in $x)
    {
      $y = Get-Mailbox -Identity $i.UserPrincipalName
      $i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled

      $y = Get-CsOnlineUser -Identity $i.UserPrincipalName
      $i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled
    }

$x | Select DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB
```

Här är ett exempel på skärmen:
  
```powershell
DisplayName             IsLicensed   IsMailboxEnabled   EnabledForSfB
-----------             ----------   ----------------   --------------
Bonnie Kearney          True         True               True
Fabrice Canel           True         True               True
Brian Johnson           False        True               False
Anne Wallace            True         True               True
Alex Darrow             True         True               True
David Longmuir          True         True               True
Katy Jordan             False        True               False
Molly Dempsey           False        True               False
```

Tolkningen av det här PowerShell-skriptet är:  

- Hämta alla användare i den aktuella Microsoft 365-prenumerationen och lagra informationen i en variabel som heter $x ( **$x = get-AzureADUser** ).
- Starta en loop som körs över alla användare i variabeln som heter $x **$i (fram$x)** .  
- Definiera en variabel som heter $y och lagra användarens post lådans information ( **$y = Get-Mailbox-Identity $i. UserPrincipalName** ).
- Lägga till en ny egenskap i användar informationen som heter IsMailBoxEnabled och ange värdet för egenskapen IsMailBoxEnabled för användarens post låda ( **$i | Add-member-MemberType NoteProperty IsMailboxEnabled-Value $y. IsMailboxEnabled** ).
- Definiera en variabel som heter $y och lagra användarens information om Skype för företag – Online ( **$y = get-CsOnlineUser-Identity $i. UserPrincipalName** ).
- Lägga till en ny egenskap i användar informationen med namnet EnabledForSfB och ange värdet för egenskapen Enabled för användarens information om Skype för företag – Online ( **$i | Add-member-MemberType NoteProperty EnabledForSfB-Value $y. enabled** ).
- Visa listan med användare, men bara ange deras namn, om de är licensierade och de två nya egenskaperna som visar om sin post låda är aktive rad och om den är aktive rad för Skype för företag – Online ( **$x | Välj DisplayName, Ärlicensierad, IsMailboxEnabled, EnabledforSfB** ).
  
## <a name="see-also"></a>Se även

[Komma igång med PowerShell för Microsoft 365](getting-started-with-microsoft-365-powershell.md)
  
[Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Använda Windows PowerShell för att skapa rapporter i Microsoft 365](use-windows-powershell-to-create-reports-in-microsoft-365.md)

