---
title: Hej världen för Microsoft Threat Protection REST API
description: Lär dig hur du skapar en app och använder ett token för att komma åt API för skydd mot Microsoft Threat Protection
keywords: app, token, Access, AAD, program, program registrering, PowerShell, skript, global administratör, behörighet
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: d9aafc43fb08d9e8b3a427805ba58490afee6297
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650583"
---
# <a name="hello-world-for-microsoft-threat-protection-rest-api"></a>Hej världen för Microsoft Threat Protection REST API 

**Gäller för:**
- Microsoft Hotskydd

>[!IMPORTANT] 
>Vissa uppgifter gäller för FÖRLANSERADE produkter som kan komma att ändras väsentligt innan de saluförs. Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på informationen som tillhandahålls här.


## <a name="get-incidents-using-a-simple-powershell-script"></a>Få incidenter med hjälp av ett enkelt PowerShell-skript

### <a name="how-long-it-takes-to-go-through-this-example"></a>Hur lång tid tar det för det här exemplet?
Det tar bara fem minuter i två steg:
- Program registrering
- Använda exempel: kräver bara kopiera/klistra in ett kort PowerShell-skript

### <a name="do-i-need-a-permission-to-connect"></a>Behöver jag en behörighet för att ansluta?
För program registrerings fasen måste du ha en **Global administratörs** roll i din Azure Active Directory (Azure AD)-klient organisation.

### <a name="step-1---create-an-app-in-azure-active-directory"></a>Steg 1 – Skapa ett program i Azure Active Directory

1. Logga in på [Azure](https://portal.azure.com) med din **globala administratörs** användare.

2. Navigera till **Azure Active Directory**-  >  **programregistreringar**  >  **ny registrering**. 

   ![Bild av Microsoft Azure och navigering till program registrering](../../media/atp-azure-new-app2.png)

3. I registrerings formuläret väljer du ett namn för ansökan och väljer sedan **Registrera**.

4. Ge ditt program åtkomst till Microsoft Defender ATP och ge det behörigheten **läsa alla händelser** :

   - På din program sida väljer du **API-behörigheter**  >  **Add permission**  >  **API min organisation använder** > ange **Microsoft Threat Protection** och välj ett **skydd mot Microsoft Threat**.

   >[!NOTE]
   >Microsoft Threat Protection visas inte i den ursprungliga listan. Du måste börja skriva dess namn i text rutan för att se det.

   ![Bild av API-åtkomst och API-val](../../media/apis-in-my-org-tab.PNG)

   - Välj **program behörigheter**  >  **incident. Läs. alla** > Välj i **lägga till behörigheter**

   ![Bild av API-åtkomst och API-val](../../media/request-api-permissions.PNG)

   >[!IMPORTANT]
   >Du måste välja relevanta behörigheter. 

     Till exempel:

     - Ta reda på vilken behörighet du behöver genom att titta i avsnittet **behörigheter** i det API du är intresse rad av.

5. Välj **bevilja administratörs tillåtelse**

    - >[!NOTE]
      > Varje gång du lägger till behörighet måste du välja **medgivande** för att den nya behörigheten ska börja gälla.

    ![Bild av beviljande behörigheter](../../media/grant-consent.PNG)

6. Lägg till en hemlighet i programmet.

    - Välj **certifikat & hemligheter**, Lägg till en beskrivning för hemligheten och välj **Lägg till**.

    >[!IMPORTANT]
    > När du har valt **Lägg till** **kopierar du det genererade hemliga värdet**. Du kommer inte att kunna hämta efter att du har lämnat!

    ![Bild av Create app-tangenten](../../media/webapp-create-key2.png)

7. Skriv in ditt program-ID och ditt klient-ID:

   - Gå till **Översikt** och kopiera följande på program sidan:

   ![Bild av ID för skapat program](../../media/app-and-tenant-ids.png)


Åstadkomma! Du har registrerat ett program.

### <a name="step-2---get-a-token-using-the-app-and-use-this-token-to-access-the-api"></a>Steg 2-Hämta ett token med programmet och Använd denna token för att komma åt API: t.

-   Kopiera skriptet nedan till PowerShell ISE eller till en text redigerare och spara det som "**Get-Token.ps1**"
-   Om du kör det här skriptet skapas ett token och det sparas i arbetsmappen under namnet "**Latest-token.txt**".

```
# That code gets the App Context Token and save it to a file named "Latest-token.txt" under the current directory
# Paste below your Tenant ID, App ID and App Secret (App key).

$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application secret here

$resourceAppIdUri = 'https://api.security.microsoft.com'
$oAuthUri = "https://login.windows.net/$TenantId/oauth2/token"
$authBody = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}
$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$token = $authResponse.access_token
Out-File -FilePath "./Latest-token.txt" -InputObject $token
return $token
```

-   Sanity:<br>
Kör skriptet.<br>
I webbläsaren går du till: https://jwt.ms/ <br>
Kopiera token (innehållet i Latest-token.txt filen).<br>
Klistra in i den övre rutan.<br>
Leta efter avsnittet "roller". Hitta ```Incidents.Read.All``` rollen.<br>
Exemplet nedan är från ett program som har ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` och ```AdvancedHunting.Read.All``` behörigheter.

![Bild jwt.ms](../../media/api-jwt-ms.png)

### <a name="lets-get-the-incidents"></a>Här kan du få ett problem!

-   Skriptet nedan använder **Get-Token.ps1** för att få åtkomst till API: t och får de händelser som senast uppdaterades tidigare 48 timmar.
-   Spara det här skriptet i samma mapp som du sparade föregående skript **Get-Token.ps1**. 
-   Skriptet en JSON-fil med data i samma mapp som skripten.

```
# Returns Incidents last updated in the past 48 hours.

$token = ./Get-Token.ps1       #run the script Get-Token.ps1  - make sure you are running this script from the same folder of Get-Token.ps1

# Get Incidents from the last 48 hours. Make sure you have incidents in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-48).ToString("o")

# The URL contains the type of query and the time filter we created above
$url = "https://api.security.microsoft.com/api/incidents?$filter=lastUpdateTime+ge+$dateTime"

# Set the WebRequest headers
$headers = @{ 
    'Content-Type' = 'application/json'
    'Accept' = 'application/json'
    'Authorization' = "Bearer $token"
}

# Send the webrequest and get the results. 
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop

# Extract the incidents from the results. 
$incidents =  ($response | ConvertFrom-Json).value | ConvertTo-Json -Depth 99

# Get string with the execution time. We concatenate that string to the output file to avoid overwrite the file
$dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}    

# Save the result as json
$outputJsonPath = "./Latest Incidents $dateTimeForFileName.json"     

Out-File -FilePath $outputJsonPath -InputObject $incidents 
```

Nu är du klar! Du har precis lyckats:
-   Skapad och registrerad och Application
-   Behörighet för det programmet att läsa aviseringar
-   Anslöt till API
-   Använde ett PowerShell-skript för att returnera incidenter som skapats under de senaste 48 timmarna



## <a name="related-topic"></a>Närliggande ämne
- [Komma åt API: erna för skydd mot Microsoft Threat](api-access.md)
- [Åtkomst till Microsoft Threat Protection med program kontext](api-create-app-web.md)
- [Åtkomst till Microsoft Threat Protection med användar kontext](api-create-app-user-context.md)
