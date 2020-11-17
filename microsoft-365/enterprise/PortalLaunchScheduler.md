---
title: Starta portalen med hjälp av portalen starta Schemaläggaren
ms.author: jhendr
author: jhendr
manager: pamgreen
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
description: I den här artikeln beskrivs hur du kan starta portalen med hjälp av portalen starta Schemaläggaren
ms.openlocfilehash: a7a007fdd95638109830a8e3689232060f2b9d8b
ms.sourcegitcommit: 2d3e85173c65a9e0ce92624a80ed7a9839f5b8bd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/17/2020
ms.locfileid: "49123589"
---
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a>Starta portalen med hjälp av portalen starta Schemaläggaren

En portal är en SharePoint-webbplats på ditt intranät som har ett stort antal webbplats läsare som använder innehåll på webbplatsen. Att starta din portal i vågor är en viktig del av att säkerställa att användarna har en smidig och snabb åtkomst till en ny SharePoint Online-Portal. 

Att starta i vågor är ett viktigt sätt att samla in din portal, enligt vad som beskrivs i [Planera hur portalen ska lanseras](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide). Med portalen kan du använda Schemaläggaren för att hjälpa dig att följa en nedrullningsbar våg med nedrullnings bara genom att hantera omdirigeringarna för den nya portalen. Under varje vågor kan du samla in feedback och övervaka prestanda under varje enskild installation. Det här är fördelen med att vi tar en långsam introduktion till portalen, vilket ger dig möjligheten att pausa och lösa problem innan du fortsätter med nästa våg, och slutligen säkerställa en positiv upplevelse för dina användare. 

Det finns två typer av omdirigering: 
- dubbelriktad: starta en ny modern SharePoint Online-Portal för att ersätta en befintlig SharePoint-klassiskt eller modern Portal 
- omdirigering av tillfälliga sidor: starta en ny modern SharePoint Online-Portal utan befintlig SharePoint-Portal

Du kan använda Schemaläggaren för att starta moderna SharePoint online-portaler, till exempel kommunikations webbplatser och moderna grupp webbplatser. Lanseringar måste schemaläggas minst 7 dagar i förväg. Antalet vågor som behövs bestäms av det förväntade antalet användare. Innan du schemalägger en portal start måste du köra [verktyget kör diagnostik för SharePoint](https://aka.ms/perftool) för att kontrol lera att start sidan på portalen är felfri. I slutet av Portal start kommer alla användare som har behörighet till webbplatsen att få åtkomst till den nya webbplatsen. 

Om du vill ha mer information om hur du startar en lyckad Portal följer du de grundläggande principerna, metoderna och rekommendationerna i [skapa, lansera och underhålla en felfri Portal](https://docs.microsoft.com/sharepoint/portal-health). 

> [!NOTE]
> Den här funktionen är inte tillgänglig för Office 365 Germany, Office 365 drivs av 21Vianet (Kina) eller Microsoft 365 amerikansk myndighets plan.

## <a name="app-setup-and-connecting-to-sharepoint-online"></a>Program inställningar och ansluta till SharePoint Online
1. [Ladda ner den senaste SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).

    > [!NOTE]
    > Om du har installerat en tidigare version av SharePoint Online Management Shell går du till Lägg till eller ta bort program och avinstallerar SharePoint Online Management Shell. <br>På sidan Download Center väljer du ditt språk och klickar sedan på knappen Ladda ned. Du uppmanas att välja mellan att ladda ner en x64-och x86. msi-fil. Ladda ner x64-filen om du kör 64-bitars versionen av Windows eller x86-filen om du kör 32-bitars versionen. Om du inte vet kan du läsa [vilken version av operativ systemet Windows använder jag?](https://support.microsoft.com/help/13443/windows-which-operating-system). När fil hämtningen är klar kör du den och följer anvisningarna i installations guiden.

2. Anslut till SharePoint som [Global administratör eller SharePoint-administratör](/sharepoint/sharepoint-admin-role) i Microsoft 365. Mer information finns i [komma igång med SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).


## <a name="view-any-existing-portal-launch-setups"></a>Visa befintliga Portal Start Inställningar

Så här ser du om det finns befintliga konfigurationer för Portal start:

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

## <a name="schedule-a-portal-launch-on-the-site"></a>Schemalägga en portal lansering på webbplatsen

Antalet vågor är beroende av den förväntade start storleken. 
- Mindre än 10 000 användare: 1 våg
- 10 k till 30k användare: 3 vågor 
- 30k + till 100K användare: 5 vågor
- Fler än 100K användare: 5 vågor och kontakta ditt Microsoft-gruppteam

### <a name="steps-for-bi-directional-redirection"></a>Steg för omdirigering till dubbelriktad

Med dubbelriktad omdirigering kan du starta en ny modern SharePoint Online-Portal för att ersätta en befintlig SharePoint-klassiskt eller modern Portal. Användare i aktiva vågor omdirigeras till den nya webbplatsen oavsett om de navigerar till den gamla eller nya webbplatsen. Användare i en icke-lanserad våg som försöker komma åt den nya webbplatsen omdirigeras tillbaka till den gamla platsen tills dess att de har startats. Om du har administratörer eller ägare som behöver komma åt de gamla och nya platserna utan att behöva omdirigeras kontrollerar du att de visas med hjälp av `WaveOverrideUsers` parametern. 

Så här migrerar du användare från en befintlig SharePoint-webbplats till en ny SharePoint-webbplats:

1. Kör följande kommando för att ange hur portalen ska lanseras.
   
   ```PowerShell
    New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType Bidirectional -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
    ```

Exempel:
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType Bidirectional -RedirectUrl "https://contoso.sharepoint.com/teams/oldsite" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
[{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
{Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
{Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. Slutför verifiering. Det kan ta 5-10 minuter för omdirigeringen att slutföra sin konfiguration via tjänsten. 

### <a name="steps-for-redirection-to-temporary-page"></a>Steg för omdirigering till tillfällig sida

Omdirigering av tillfälliga sidor ska användas när det inte finns någon befintlig SharePoint-Portal. Användare dirigeras till en ny modern SharePoint Online-Portal på ett stadium sätt. Om en användare har en Wave-åtgärd som inte har startats kommer de att omdirigeras till en tillfällig sida (valfri URL). 

1. Kör följande kommando för att ange hur portalen ska lanseras.
   
      ```PowerShell
    New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType ToTemporaryPage -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
    ```

Exempel:
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType ToTemporaryPage -RedirectUrl "https://portal.contoso.com/UnderConstruction.aspx" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
[{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
{Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
{Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. Slutför verifiering. Det kan ta 5-10 minuter för omdirigeringen att slutföra sin konfiguration via tjänsten. 
   - `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/newsite" -RedirectionType Bidirectional -RedirectUrl "https://*.sharepoint.com/sites/oldsite" -ExpectedNumberOfUsers LessThan10kUsers -WaveOverrideUsers "*@microsoft.com" -Waves ' [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

## <a name="pause-or-restart-a-portal-launch-on-the-site"></a>Pausa eller starta om en portal lansering på webbplatsen

1. Om du vill pausa en pågående Portal start och tillfälligt förhindra att kommande våg förlopp inträffar kör du följande kommando:

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl <object>
   ```
2. Verifiera att alla användare omdirigeras till den gamla webbplatsen. 

3. Om du vill starta om en portal lansering som har pausats kör du följande kommando:

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl <object>
   ```
   
4. Kontrol lera att omdirigeringen nu har återställts. 

## <a name="delete-a-portal-launch-on-the-site"></a>Ta bort en portal lansering på webbplatsen
1. Skapa en portal-starta Wave.
  - `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/NewSite" -RedirectionType ToTemporaryPage -RedirectUrl "https://*.sharepoint.com/sites/OldSite" -ExpectedNumberOfUsers From10kTo30kUsers -WaveOverrideUsers *@microsoft.com -Waves [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. Kör följande kommando för att ta bort en portal som är schemalagd eller pågående för en webbplats.

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

3. Verifiera att ingen omdirigering sker för alla användare.

## <a name="learn-more"></a>Mer information
[Planera hur portalen ska lanseras i SharePoint Online](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out)
