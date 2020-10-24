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
ms.openlocfilehash: d56a2cc47a06be911f1fd38aea3a557c631d2db0
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754112"
---
# <a name="why-you-need-to-use-powershell-for-microsoft-365"></a>Därför måste du använda PowerShell för Microsoft 365

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Med Microsoft 365 Admin Center kan du hantera användar konton och licenser för Microsoft 365. Du kan också hantera dina Microsoft 365-tjänster, till exempel Exchange Online, teams och SharePoint Online. Om du istället använder PowerShell för att hantera de här tjänsterna kan du dra nytta av kommando rads-och skript språk miljö för hastighet, automatisering och andra funktioner.
  
I den här artikeln visar vi hur du använder PowerShell för att hantera Microsoft 365 för att:
  
- Visa ytterligare information som inte visas i administrations centret för Microsoft 365
    
- Konfigurera funktioner och inställningar endast möjligt med PowerShell
    
- Utför Mass åtgärder
    
- Filtrera data
    
- Skriva ut eller spara data
    
- Hantera mellan tjänster
    
Kom ihåg att PowerShell för Microsoft 365 är en uppsättning moduler för Windows PowerShell, som är en kommando rads miljö för Windows-baserade tjänster och plattformar. Den här miljön skapar ett kommando gränssnitts språk som kan utökas med ytterligare moduler. Det är ett sätt att utföra enkla eller komplicerade kommandon eller skript. När du till exempel har installerat PowerShell för Microsoft 365-moduler och ansluter till din Microsoft 365-prenumeration kan du köra följande kommando för att visa alla användar post lådor för Microsoft Exchange Online:
  
```powershell
Get-Mailbox
```

Du kan också hämta listan med post lådor genom att använda administrations centret för Microsoft 365 men inventering av objekten i alla listor för alla dina webb program är inte lätt.
  
PowerShell för Microsoft 365 är utformat för att hjälpa dig att hantera Microsoft 365, inte för att ersätta Microsoft 365 Admin Center. Administratörer måste kunna använda PowerShell för Microsoft 365 eftersom det finns vissa konfigurations procedurer som endast kan utföras via PowerShell för Microsoft 365-kommandon. I de här fallen måste du veta hur du kan:
  
- Installera PowerShell för Microsoft 365-moduler (endast en gång för varje administratörs dator).
    
- Anslut till ditt Microsoft 365-abonnemang (en gång för varje PowerShell-session).
    
- Samla in den information som behövs för att köra de PowerShell för Microsoft 365-kommandon som krävs.
    
- Kör PowerShell för Microsoft 365-kommandon.
    
När du har lärt dig de grundläggande färdigheterna behöver du inte Visa dina post lådor med hjälp av kommandot **Hämta-post låda** . Du behöver inte heller förstå hur du skapar ett nytt kommando, till exempel det omciterade kommandot för att räkna alla objekt i alla listor för alla webbapparna. Microsoft och communityn för administratörer kan hjälpa dig med sådana uppgifter som behövs.
  
## <a name="powershell-for-microsoft-365-can-reveal-information-that-you-cant-see-with-the-microsoft-365-admin-center"></a>PowerShell för Microsoft 365 kan visa information som du inte kan se med administrations centret för Microsoft 365

Administrations centret för Microsoft 365 visar många användbara uppgifter. Men det visar inte all information som kan användas i Microsoft 365 för användare, licenser, post lådor och webbplatser. Här är ett exempel för *användare och grupper* i administrations centret för Microsoft 365:
  
![Exempel på hur användare och grupper visas i administrations centret för Microsoft 365.](../media/o365-powershell-users-and-groups.png)
  
Den här vyn innehåller den information du behöver i många fall. Men det finns tillfällen då du behöver mer. Microsoft 365-licensiering (och de Microsoft 365-funktioner som är tillgängliga för en användare) beror till exempel på användarens geografiska plats. De principer och funktioner som du kan utöka till en användare som bor i USA kanske inte är samma som de som du kan använda för att utöka till en användare i Indien eller Belgien. Följ de här anvisningarna i administrations centret för Microsoft 365 för att fastställa en användares geografiska plats:
  
1. Dubbelklicka på användarens **visnings namn**.
    
2. I fönstret användar egenskaper väljer du **information**.
    
3. I informations fönstret väljer du **Ytterligare information**.
    
4. Bläddra tills du hittar rubriken **land eller region**:
    
     ![Exempel på region informationen för en användare i administrations centret för Microsoft 365.](../media/o365-powershell-usage-location.png)
  
5. Skriv användarens visnings namn och plats på papperet, eller kopiera och klistra in i anteckningar.
    
Du måste upprepa proceduren för varje användare. Om du har många användare kan den här processen bli omständlig. Med PowerShell för Microsoft 365 kan du Visa den här informationen för alla användare genom att använda följande kommando:
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```


>[!Note]
>PowerShell Core stöder inte Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen och cmdlets som har *MSOL* i sitt namn. Du måste köra de här cmdletarna från Windows PowerShell.
>

Här är ett exempel på resultatet:
  
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

Tolkningen av detta PowerShell-kommando är: Hämta alla användare i den aktuella Microsoft 365-prenumerationen (**Get-AzureADUser**), men Visa bara namn och plats för varje användare (**Välj DisplayName, UsageLocation**).
  
Eftersom PowerShell för Microsoft 365 har stöd för ett kommando gränssnitts språk kan du ytterligare ändra informationen som erhålls med kommandot **Get-AzureADUser** . Om du till exempel vill sortera dessa användare efter deras placering, kan du gruppera alla brasilianska användare tillsammans, alla användare tillsammans och så vidare. Här är kommandot:
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation | Sort UsageLocation, DisplayName
```

Här är ett exempel på resultatet:
  
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

Tolkningen av det här PowerShell-kommandot är: Hämta alla användare i den aktuella Microsoft 365-prenumerationen, men Visa bara namn och plats för varje användare och sortera dem först efter deras placering och sedan deras namn (**Sortera UsageLocation, DisplayName**).
  
Du kan också använda ytterligare filtrering. Om du till exempel vill visa information om användare som är baserade i Brasilien använder du det här kommandot:
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq "BR"} | Select DisplayName, UsageLocation 
```

Här är ett exempel på resultatet:
  
```powershell
DisplayName                                           UsageLocation
-----------                                           -------------
David Longmuir                                        BR
Fabrice Canel                                         BR
```

Tolkningen av detta PowerShell-kommando är: Hämta alla användare i den aktuella Microsoft 365-prenumerationen vars plats är Brasilien (**där {$ \_ . UsageLocation-EQ "BR"}**) och visar sedan namn och plats för varje användare.
  
 **En kommentar om stora domäner**
  
Om du har en stor domän med tusentals användare kan du prova några av de exempel vi visar i den här artikeln. Beroende på faktorer som dator kraft och tillgänglig nätverks bandbredd kanske du försöker göra för mycket på en gång. Stora organisationer kan dela vissa av dessa PowerShell-operationer i två kommandon.

Följande kommando returnerar till exempel alla användar konton och visar namn och plats för var och en av dem:
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```

Det passar utmärkt för mindre domäner. I en stor organisation kanske du vill dela den operationen i två kommandon: ett kommando för att lagra information om användar kontot i en variabel och ett annat för att visa nödvändig information. Här är ett exempel:
  
```powershell
$x = Get-AzureADUser
$x | Select DisplayName, UsageLocation
```

Tolkningen av denna uppsättning PowerShell-kommandon är:
1. Hämta alla användare i den aktuella Microsoft 365-prenumerationen och lagra informationen i en variabel som heter $x (**$x = get-AzureADUser**).
1.  Visa innehållet i variabeln *$x*, men inkludera bara namn och plats för varje användare (**$x | Välj DisplayName, UsageLocation**).
  
## <a name="microsoft-365-has-features-that-you-can-only-configure-with-powershell-for-microsoft-365"></a>Microsoft 365 har funktioner som du bara kan konfigurera med PowerShell för Microsoft 365

Administrations centret för Microsoft 365 är avsett att ge till gång till vanliga och användbara administrativa uppgifter som gäller för de flesta miljöer. Med andra ord har Microsoft 365 Admin Center konstruerats så att den typiska administratören kan utföra de vanligaste hanterings uppgifterna. Men det finns några uppgifter som inte kan göras i administrations centret.
  
Administrations centret för Skype för företag – Online innehåller till exempel några få alternativ för att skapa anpassade Mötes inbjudningar:
  
![Exempel på hur anpassade mötesinbjudan visas i administrations centret för Skype för företag – online.](../media/o365-powershell-meeting-invitation.png)
  
Med de här inställningarna kan du lägga till och anpassa Mötes inbjudningar. Men det finns mer information om inställningar för Mötes konfiguration än att skapa anpassade Mötes inbjudningar. Som standard tillåter möten till exempel:
  
- Anonyma användare får automatisk ingång till varje möte.
    
- Deltagare att spela in i mötet.
    
- Alla användare i organisationen ska utses till presentatörer när de ansluter till mötet.
    
Dessa inställningar är inte tillgängliga från administrations centret för Skype för företag – online. Du kan styra dem från PowerShell för Microsoft 365. Här är ett kommando som inaktiverar dessa tre inställningar:
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False -AllowConferenceRecording $False -DesignateAsPresenter "None"
```

> [!NOTE]
> För att köra det här kommandot måste du installera [PowerShell-modulen för Skype för företag – Online ](https://www.microsoft.com/download/details.aspx?id=39366).
  
Tolkningen av detta PowerShell-kommando är:
 
1. I inställningar för nya Skype för företag – Online-möten (**set-CsMeetingConfiguration**) inaktiverar du Tillåt anonyma användare att få automatisk ingång till möten (**-AdmitAnonymousUsersByDefault $false**).
2.  Inaktivera möjligheten för deltagare att spela in möten (**-AllowConferenceRecording $false**).
3. Du behöver inte ange alla användare från organisationen som presentatörer (**-DesignateAsPresenter "ingen"**).
  
Om du vill återställa standardinställningarna (aktivera alternativen) kör du det här kommandot:
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $True -AllowConferenceRecording $True -DesignateAsPresenter "Company"
```

Det finns andra liknande scenarier, vilket är orsaken till att administratörer bör kunna köra PowerShell för Microsoft 365-kommandon.
  
## <a name="powershell-for-microsoft-365-is-great-for-bulk-operations"></a>PowerShell för Microsoft 365 är perfekt för Mass åtgärder

Visuella gränssnitt som Microsoft 365 Admin Center är mest värdefulla när du har en enda åtgärd. Om du till exempel behöver inaktivera ett användar konto kan du använda administrations centret för att snabbt hitta och avmarkera en kryss ruta. Det kan vara enklare än att utföra en liknande åtgärd i PowerShell.
  
Men om du behöver ändra många saker eller vissa markerade saker i en stor uppsättning andra saker kanske administrations centret för Microsoft 365 inte är det bästa verktyget. Säg till exempel att du måste ändra prefix på tusentals telefonnummer eller ta bort de specifika användarna *Katarina Myer* från alla SharePoint Online-webbplatser. Hur gör du det i administrations centret för Microsoft 365?
  
Anta att du har flera hundra SharePoint Online-webbplatser och att du inte vet vilka Katarina Meyer är medlem i. Du skulle behöva börja med administrations centret för Microsoft 365 och sedan utföra den här proceduren för varje webbplats:
  
1. Välj **URL** för webbplatsen.
    
2. I rutan **Egenskaper för webbplats samling** väljer du länken webbplats **adress** för att öppna webbplatsen.
    
3. Välj **dela**på webbplatsen.
    
4. I dialog rutan **dela** väljer du länken som visar alla användare som har behörighet till webbplatsen:
    
     ![Exempel på hur du visar medlemmarna på en SharePoint Online-webbplats i administrations centret för SharePoint Online.](../media/o365-powershell-view-permissions.png)
  
5. I dialog rutan **delas med** väljer du **Avancerat**.
    
6. Bläddra nedåt i listan med användare, hitta och välj Katarina Myer (förutsatt att han har behörighet till webbplatsen) och välj sedan **ta bort användar behörigheter**.
    
Det tar *lång* tid för flera hundra webbplatser.
  
Alternativet är att köra följande kommando i PowerShell för Microsoft 365 för att ta bort Katarina Myer från alla webbplatser:
  
```powershell
Get-SPOSite | ForEach {Remove-SPOUser -Site $_.Url -LoginName "kenmyer@litwareinc.com"}
```

> [!NOTE]
> Det här kommandot kräver att du installerar [SharePoint Online PowerShell-modulen](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps). 
  
Tolkningen av det här PowerShell-kommandot är: Hämta alla SharePoint-webbplatser i den aktuella Microsoft 365-prenumerationen (**Get-SPOSite**) och för varje webbplats tar du bort Katarina Meyer från listan över användare som har åtkomst till den (**sol{Remove-Makers-site $ \_ . URL – LoginName "kenmyer \@ litwareinc.com"}**).
  
Vi berättar för Microsoft 365 att ta bort Katarina Meyer från alla webbplatser, inklusive de som han saknar åtkomst till. Därför visas fel för de webbplatser som han saknar åtkomst till. Vi kan använda ett ytterligare villkor i det här kommandot för att ta bort Katarina Meyer endast från webbplatser som har sin inloggnings lista. Men felen som returneras gör att själva webbplatserna inte skadas. Det kan ta några minuter att köra det här kommandot för hundratals webbplatser, i stället för timmar med att arbeta via Microsoft 365 Admin Center.
  
Här är ett annat Mass Operations exempel. Använd det här kommandot för att lägga till *Håkans Kearney*, en ny SharePoint-administratör, på alla webbplatser i organisationen:
  
```powershell
Get-SPOSite | ForEach {Add-SPOUser -Site $_.Url -LoginName "bkearney@litwareinc.com" -Group "Members"}
```

Tolkningen av det här PowerShell-kommandot är: Hämta alla SharePoint-webbplatser i den aktuella Microsoft 365-prenumerationen och för varje webbplats kan Håkans Kearney Access genom att lägga till hennes inloggnings namn i gruppen medlemmar på webbplatsen (**sol{Add-makar-site $ \_ . URL – LoginName "bkearney \@ litwareinc.com"-grupp "medlemmar"}**).
  
## <a name="powershell-for-microsoft-365-is-great-at-filtering-data"></a>PowerShell för Microsoft 365 är ett bra sätt att filtrera data

Administrations centret för Microsoft 365 tillhandahåller flera olika sätt att filtrera data för att enkelt hitta en viss del av informationen. Med Exchange blir det till exempel enkelt att filtrera på en användares post låda i praktiskt taget. Här är en lista med post lådor för alla användare som bor i staden Bloomington:
  
![Exempel på en avancerad sökning i administrations centret för Microsoft 365 för listan med post lådor för alla användare som bor i staden Bloomington.](../media/o365-powershell-advanced-search.png)
  
I administrations centret för Exchange kan du även kombinera filter villkor. Du kan till exempel hitta post lådorna för alla personer som bor i Bloomington och arbeta på ekonomi avdelningen.
  
Men det finns begränsningar för vad du kan göra i administrations centret för Exchange. Du kan till exempel enkelt hitta post lådorna för personer som bor i Bloomington *eller* San Diego, eller post lådorna för alla som inte bor i Bloomington.
  
Du kan använda följande PowerShell för Microsoft 365-kommando för att hämta en lista med post lådor för alla personer som bor i Bloomington eller San Diego:
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and ($_.City -eq "San Diego" -or $_.City -eq "Bloomington")} | Select DisplayName, City
```

Här är ett exempel på resultatet:
  
```powershell
DisplayName                              City
-----------                              ----
Alex Darrow                              San Diego
Bonnie Kearney                           San Diego
Julian Isla                              Bloomington
Rob Young                                Bloomington
```

Tolkningen av detta PowerShell-kommando är: Hämta alla användare i den aktuella Microsoft 365-prenumerationen som har en post låda i staden San-Diego eller Bloomington (**där {$ \_ . En-EQ "UserMailbox"-och ($ \_ . City-EQ "San Diego"-eller $ \_ . City-EQ "Bloomington")}**) och visar sedan namnet och staden för var och en av dem (**Välj DisplayName, ort**).
  
Och här är kommandot för att visa alla post lådor för personer som bor var som helst utom Bloomington:
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and $_.City -ne "Bloomington"} | Select DisplayName, City
```

Här är ett exempel på resultatet:
  
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

Tolkningen av detta PowerShell-kommando är: Hämta alla användare i den aktuella Microsoft 365-prenumerationen som har en post låda som inte finns i staden Bloomington (**där {$ \_ . En-EQ "UserMailbox"-and $ \_ . City-Ne "Bloomington"}**) och visar sedan namnet och staden för varje.
  
### <a name="use-wildcards"></a>Använda jokertecken

Du kan också använda jokertecken i dina PowerShell-filter för att matcha delar av ett namn. Anta till exempel att du letar efter ett användar konto. Allt du kan komma ihåg är att användarens efter namn var *Anderson* eller kanske *Henderson* eller *Jorgenson*.
  
Du kan spåra användaren i administrations centret för Microsoft 365 genom att använda sökverktyget och utföra tre olika sökningar:
  
- En för  *Anderson* 
    
- En för  *Henderson* 
    
- En för  *Jorgenson* 
    
Eftersom alla tre av namnen slutar med "son" kan du se till att PowerShell visar alla användare vars namn slutar på "son". Här är kommandot:
  
```powershell
Get-User -Filter '{LastName -like "*son"}'
```

Tolkningen av det här PowerShell-kommandot är: Hämta alla användare i den aktuella Microsoft 365-prenumerationen, men Använd ett filter som bara visar de användare vars senaste namn slutar på "son" (**-filter ' {efter namn-like " \* son"} '**). En \* uppsättning tecken som är bokstäver i användarens efter namn.
  
## <a name="powershell-for-microsoft-365-makes-it-easy-to-print-or-save-data"></a>Med PowerShell för Microsoft 365 blir det enkelt att skriva ut eller spara data

Med administrations centret för Microsoft 365 kan du Visa listor med data. Här är ett exempel på administrations centret för Skype för företag – online som visar en lista över användare som har Aktiver ATS för Skype för företag – online:
  
![Exempel på administrations centret för Skype för företag – online som visar en lista över användare som har Aktiver ATS för Skype för företag – online.](../media/o365-powershell-lync-users.png)
  
Om du vill spara informationen i en fil måste du klistra in den i ett dokument eller ett Excel-kalkylblad. Något av fallen kan kräva ytterligare formatering. Administrations centret för Microsoft 365 kan dessutom inte skriva ut den lista som visas direkt.
  
Som tur är kan du använda PowerShell för att inte bara visa listan men för att spara den i en fil som enkelt kan importeras till Excel. Här är ett exempel kommando för att spara användar data för Skype för företag – Online i en CSV-fil (kommaseparerade värden), som enkelt kan importeras som en tabell i ett Excel-kalkylblad:
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Export-Csv -Path "C:\Logs\SfBUsers.csv" -NoTypeInformation
```

Här är ett exempel på resultatet:
  
![Exempel på en tabell som importer ATS till ett Excel-kalkylblad för användare av Skype för företag – online som sparats i en fil med kommateckenavgränsade värden.](../media/o365-powershell-data-in-excel.png)
  
Tolkningen av detta PowerShell-kommando är: Hämta alla Skype för företag – Online-användare i den aktuella Microsoft 365-prenumerationen (**Get-CsOnlineUser**); Hämta bara användar namn, UPN och plats (**Välj DisplayName, userPrincipalName, UsageLocation**); och spara sedan informationen i en CSV-fil som heter C: \\ loggar \\SfBUsers.csv (**export-csv-Path "C: \\ loggar \\SfBUsers.csv"-NoTypeInformation**).
  
Du kan också använda alternativen för att spara denna lista som en XML-fil eller en HTML-sida. Med ytterligare PowerShell-kommandon kan du faktiskt spara det direkt som en Excel-fil med eventuell anpassad formatering.
  
Du kan också skicka utdata från ett PowerShell-kommando som visar en lista direkt till standard skrivaren i Windows. Här är ett exempel kommando:
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Out-Printer
```

Så här ser det utskrivna dokumentet ut:
  
![Exempel på ett utskrivet dokument som fick ett PowerShell-kommando skickat direkt till standard skrivaren i Windows.](../media/o365-powershell-printed-data.png)
  
Tolkningen av detta PowerShell-kommando är: Hämta alla Skype för företag – Online-användare i den aktuella Microsoft 365-prenumerationen; få bara användar namn, UPN och plats; och skicka sedan informationen till standard skrivaren i Windows (**ut-skrivaren**).
  
Det utskrivna dokumentet har samma enkla formatering som visas i PowerShell-Kommandotolken. Om du vill ha en pappers kopia lägger du bara till **| Slut på skrivare** till slutet av kommandot.
  
## <a name="powershell-for-microsoft-365-lets-you-manage-across-server-products"></a>Med PowerShell för Microsoft 365 kan du hantera olika Server produkter

De komponenter som utgör Microsoft 365 är utformade för att fungera tillsammans. Anta till exempel att du lägger till en ny användare i Microsoft 365 och att du anger information som användarens avdelning och telefonnummer. Denna information kommer att vara tillgänglig om du kommer åt användarens information i någon av Microsoft 365-tjänsterna: Skype för företag – Online, Exchange eller SharePoint.
  
Men det är för gemensam information som omfattar produkterna. Produktspecifika uppgifter, till exempel information om en användares Exchange-postlåda, är normalt inte tillgänglig i hela sviten. Information om till exempel att en användares post låda är aktive rad eller inte är tillgänglig i administrations centret för Exchange.
  
Anta att du vill skapa en rapport som visar följande information för alla dina användare:
  
- Användarens visnings namn
    
- Om användaren är licensierad för Microsoft 365
    
- Om användarens Exchange-postlåda har Aktiver ATS
    
- Om användaren är aktive rad för Skype för företag – Online
    
Du kan inte enkelt tillverka en sådan rapport i administrations centret för Microsoft 365. I stället måste du skapa ett separat dokument för att lagra informationen, till exempel ett Excel-kalkylblad. Hämta sedan alla användar namn och licensierings information från administrations centret för Microsoft 365, hämta information från administrations centret för Exchange, få information om Skype för företag – Online från administrations centret för Skype för företag – Online och kombinera den informationen.
  
Alternativet är att använda ett PowerShell-skript för att kompilera rapporten åt dig.
  
Följande exempel skript är mer komplicerat än de kommandon du har sett hittills i den här artikeln. Men det visar potentialen för att använda PowerShell för att skapa informations vyer som är svåra att se. Så här kompilerar och visar du den lista du behöver:
  
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

Här är ett exempel på resultatet:
  
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

1. Hämta alla användare i den aktuella Microsoft 365-prenumerationen och lagra informationen i en variabel som heter *$x* (**$x = get-AzureADUser**).
1. Starta en loop som körs över alla användare i variabeln $x $i (**fram$x)**.  
1. Definiera en variabel som heter *$y* och lagra användarens post lådans information (**$y = Get-Mailbox-Identity $i. UserPrincipalName**).
1. Lägga till en ny egenskap i användar informationen som heter *IsMailBoxEnabled*. Ange värdet för egenskapen IsMailBoxEnabled i användarens post låda (**$i | Add-Member-MemberType NoteProperty-Name IsMailBoxEnabled-value $y. IsMailBoxEnabled**).
1. Definiera en variabel som heter *$y*och lagra användarens information om Skype för företag – Online (**$y = Get-CsOnlineUser-Identity $i. UserPrincipalName**).
1. Lägga till en ny egenskap i användar informationen som heter *EnabledForSfB*. Ange värdet för egenskapen Enabled för användarens online-information för Skype för företag (**$i | Add-Member-MemberType NoteProperty EnabledForSfB-värde $y. enabled**).
1. Visa listan med användare, men bara ange deras namn, om de är licensierade och de två nya egenskaperna som visar om sin post låda är aktive rad och om den är aktive rad för Skype för företag – Online (**$x | Välj DisplayName, Ärlicensierad, IsMailboxEnabled, EnabledforSfB**).
  
## <a name="see-also"></a>Se även

[Börja använda PowerShell för Microsoft 365](getting-started-with-microsoft-365-powershell.md)
  
[Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Använda Windows PowerShell för att skapa rapporter i Microsoft 365](use-windows-powershell-to-create-reports-in-microsoft-365.md)
