---
title: Hello World för Microsoft 365 Defender REST API
description: Lär dig hur du skapar en app och använder en token för att komma åt Microsoft 365 Defender-API:er
keywords: app, token, access, aad, app, programregistrering, powershell, skript, global administratör, behörighet, microsoft 365 defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: ffdcf91da6b5def7d63e5fdb8ff51ddbdb1ec550
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072754"
---
# <a name="hello-world-for-microsoft-365-defender-rest-api"></a>Hello World för Microsoft 365 Defender REST API

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**

- Microsoft 365 Defender

> [!IMPORTANT]
> En del information gäller förinstallerad produkt som kan ha ändrats mycket innan den släpps kommersiellt. Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.

## <a name="get-incidents-using-a-simple-powershell-script"></a>Få incidenter med ett enkelt PowerShell-skript

Det bör ta 5 till 10 minuter att slutföra projektet. Den här tidsberäkningen omfattar registrering av programmet och att använda koden från PowerShell-exempelskriptet.

### <a name="register-an-app-in-azure-active-directory"></a>Registrera en app i Azure Active Directory

1. Logga in i [Azure](https://portal.azure.com) som en användare med **rollen Global** administratör.

2. Gå till **Azure Active Directory**  >  **Appregistreringar**  >  **Ny registrering.**

   ![Bild av Microsoft Azure navigering till registrering av program](../../media/atp-azure-new-app2.png)

3. Välj ett namn på din ansökan i registreringsformuläret och välj sedan **Registrera**. Det är valfritt att välja en omdirigerings-URI. Du behöver ingen för att slutföra det här exemplet.

4. På programsidan väljer du **API-behörigheter** Lägg till  >    >  **behörighets-API:er** som min organisation använder >, skriver **Microsoft Threat Protection** och väljer Microsoft Threat Protection . Appen kan nu komma åt Microsoft 365 Defender.

   > [!TIP]
   > *Microsoft Threat Protection* är ett tidigare namn Microsoft 365 Defender och visas inte i den ursprungliga listan. Du måste börja skriva namnet i textrutan för att det ska visas.
   ![Bild av val av API-behörighet](../../media/apis-in-my-org-tab.PNG)

   - Välj **Programbehörigheter**  >  **Incident.Read.All och** välj Lägg till **behörigheter.**

   ![Bild av val av API-åtkomst och API](../../media/request-api-permissions.PNG)

5. Välj **Bevilja administratörsmedgivande**. Varje gång du lägger till en behörighet måste du välja **Ge administratörsmedgivande** för att den ska gälla.

    ![Bild av bevilja behörigheter](../../media/grant-consent.PNG)

6. Gör programmet hemligt. Välj **Certifikat & , lägg** till en beskrivning av hemligheten och välj sedan Lägg **till**.

    > [!TIP]
    > När du har **valt Lägg** till väljer du kopiera **det genererade hemliga värdet**. Du kommer inte att kunna hämta det hemliga värdet när du har lämnat.

    ![Bild av skapa programnyckel](../../media/webapp-create-key2.png)

7. Spela in ditt program-ID och ditt klient-ID på ett säkert ställe. De visas under Översikt **på** din programsida.

   ![Bild på skapad app-ID](../../media/app-and-tenant-ids.png)

### <a name="get-a-token-using-the-app-and-use-the-token-to-access-the-api"></a>Hämta en token med appen och använd token för att få åtkomst till API:t

Mer information om hur Azure Active Directory tokens finns i självstudiekursen [för Azure AD.](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)

> [!IMPORTANT]
> Även om exemplet i den här demoappen uppmuntrar dig att  klistra in i ditt hemliga värde för teständamål ska du aldrig hårdkoda hemligheter i ett program som körs i produktion. En tredje part kan använda din hemligt för att komma åt resurser. Du kan skydda dina apphemligheter med hjälp av [Azure Key Vault.](/azure/key-vault/general/about-keys-secrets-certificates) Ett praktiskt exempel på hur du kan skydda din app finns i Hantera hemligheter i [dina serverappar med Azure Key Vault.](/learn/modules/manage-secrets-with-azure-key-vault/)

1. Kopiera skriptet nedan och klistra in det i din favorittextredigerare. Spara som **Get-Token.ps1**. Du kan även köra koden som den är i PowerShell ISE, men du bör spara den eftersom vi måste köra den igen när vi använder skriptet för hämtning av incidenter i nästa avsnitt.

    Det här skriptet genererar en token och sparar den i arbetsmappen under namnet *Latest-token.txt*.

    ```PowerShell
    # This script gets the app context token and saves it to a file named "Latest-token.txt" under the current directory.
    # Paste in your tenant ID, client ID and app secret (App key).

    $tenantId = '' # Paste your directory (tenant) ID here
    $clientId = '' # Paste your application (client) ID here
    $appSecret = '' # # Paste your own app secret here to test, then store it in a safe place!

    $resourceAppIdUri = 'https://api.security.microsoft.com'
    $oAuthUri = "https://login.windows.net/$tenantId/oauth2/token"
    $authBody = [Ordered] @{
      resource = $resourceAppIdUri
      client_id = $clientId
      client_secret = $appSecret
      grant_type = 'client_credentials'
    }
    $authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
    $token = $authResponse.access_token
    Out-File -FilePath "./Latest-token.txt" -InputObject $token
    return $token
    ```

#### <a name="validate-the-token"></a>Verifiera token

1. Kopiera och klistra in den token du fått i [JWT för](https://jwt.ms) att avkoda den.
1. *JWT* står för *JSON Web Token*. Den avkodade token innehåller ett antal JSON-formaterade objekt eller anspråk. Kontrollera att rollerna *som* anges i den avkodade token innehåller de önskade behörigheterna.

    På följande bild kan du se en avkodad token som köpts från en app, med ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` , och ```AdvancedHunting.Read.All``` behörigheter:

    ![Bild jwt.ms](../../media/api-jwt-ms.png)

### <a name="get-a-list-of-recent-incidents"></a>Få en lista över de senaste incidenterna

Skriptet nedan använderGet-Token.ps1 **få** åtkomst till API:et. Sedan hämtas en lista över incidenter som uppdaterades senast inom 48 timmar och sparar listan som en JSON-fil.

> [!IMPORTANT]
> Spara skriptet i samma mapp som du sparade **Get-Token.ps1**.

```PowerShell
# This script returns incidents last updated within the past 48 hours.

$token = ./Get-Token.ps1

# Get incidents from the past 48 hours.
# The script may appear to fail if you don't have any incidents in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-48).ToString("o")

# This URL contains the type of query and the time filter we created above.
# Note that `$filter` does not refer to a local variable in our script --
# it's actually an OData operator and part of the API's syntax.
$url = "https://api.security.microsoft.com/api/incidents?$filter=lastUpdateTime+ge+$dateTime"

# Set the webrequest headers
$headers = @{
    'Content-Type' = 'application/json'
    'Accept' = 'application/json'
    'Authorization' = "Bearer $token"
}

# Send the request and get the results.
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop

# Extract the incidents from the results.
$incidents =  ($response | ConvertFrom-Json).value | ConvertTo-Json -Depth 99

# Get a string containing the execution time. We concatenate that string to the name 
# of the output file to avoid overwriting the file on consecutive runs of the script.
$dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}

# Save the result as json
$outputJsonPath = "./Latest Incidents $dateTimeForFileName.json"

Out-File -FilePath $outputJsonPath -InputObject $incidents
```

Nu är allt klart! Du har lyckats:

- Skapat och registrerat ett program.
- Har gett det programmet behörighet att läsa aviseringar.
- Ansluten till API:t.
- Använde ett PowerShell-skript för att returnera incidenter som uppdaterats de senaste 48 timmarna.

## <a name="related-articles"></a>Relaterade artiklar

- [Microsoft 365 Översikt över Defender-API:er](api-overview.md)
- [Komma åt Microsoft 365 Defender-API:er](api-access.md)
- [Skapa en app för åtkomst Microsoft 365 Defender utan användare](api-create-app-web.md)
- [Skapa en app för att Microsoft 365 Defender-API:er för en användares räkning](api-create-app-user-context.md)
- [Skapa en app med partner med flera klientorganisationens åtkomst Microsoft 365 Defender-API:er](api-partner-access.md)
- [Hantera hemligheter i dina serverappar med Azure-tangentvalvet](/learn/modules/manage-secrets-with-azure-key-vault/)
- [OAuth 2.0-auktorisering för användar inloggning och API-åtkomst](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)