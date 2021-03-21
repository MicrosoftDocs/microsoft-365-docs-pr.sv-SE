---
title: Starta portalen med hjälp av Portal Launch Scheduler
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
description: I den här artikeln beskrivs hur du kan starta portalen med hjälp av Portal Launch Scheduler
ms.openlocfilehash: e39f00dbc63ae7f1dcaf907d9c67df2c1683efc6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926148"
---
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a>Starta portalen med hjälp av Portal Launch Scheduler

En portal är en SharePoint-webbplats i ditt intranät som har många användare som använder innehåll på webbplatsen. Att lansera portalen i vågor är en viktig del av att se till att användarna får en smidig och fungerande upplevelse av att komma åt en ny SharePoint Online-portal. 

Att starta i vågor är ett viktigt sätt att distribuera portalen, enligt beskrivningen i Planera lanseringen av portalen [i SharePoint Online.](./planportallaunchroll-out.md?view=o365-worldwide) Portal Launch Scheduler har utformats för att hjälpa dig att följa en fas-/fas-utrullningsmetod genom att hantera omdirigeringarna för den nya portalen. Under varje vågor kan du samla in feedback från användare och övervaka prestanda under varje distributionsvåg. Detta har fördelen med att långsamt introducera portalen, vilket ger dig möjlighet att pausa och lösa problem innan du fortsätter med nästa omgång, och i slutänden säkerställa en positiv upplevelse för dina användare. 

Det finns två typer av omdirigering: 
- dubbelriktad: starta en ny modern SharePoint Online-portal för att ersätta en befintlig klassisk eller modern SharePoint-portal 
- Tillfällig sidomdirigering: starta en ny modern SharePoint Online-portal utan en befintlig SharePoint-portal

Schemaläggaren för portalstart är endast tillgänglig för att starta moderna SharePoint Online-portaler (dvs. kommunikationswebbplatser). Lanseringar måste schemaläggas minst 7 dagar i förväg. Antalet vågor som krävs bestäms av det förväntade antalet användare. Innan du schemalägger en portalstart måste verktyget Siddiagnostik för [SharePoint](./page-diagnostics-for-spo.md) köras för att kontrollera att startsidan på portalen är felfri. I slutet av portalens start kan alla användare med behörighet till webbplatsen få åtkomst till den nya webbplatsen. 

Om du vill ha mer information om hur du startar en lyckad portal följer du de grundläggande principerna, metoderna och rekommendationerna i Skapa, starta och [underhålla en felfri portal.](/sharepoint/portal-health) 

> [!NOTE]
> Den här funktionen är inte tillgänglig för Office 365 Germany-, Office 365-abonnemang som drivs av 21Vianet (Kina) eller Microsoft 365 för amerikanska myndigheter.

## <a name="app-setup-and-connecting-to-sharepoint-online"></a>Appkonfiguration och anslutning till SharePoint Online
1. [Ladda ned den senaste versionen av SharePoint Online Management Shell.](https://go.microsoft.com/fwlink/p/?LinkId=255251)

    > [!NOTE]
    > Om du har installerat en tidigare version av SharePoint Online Management Shell går du till Lägga till eller ta bort program och avinstallerar "SharePoint Online Management Shell". <br>På sidan Download Center väljer du språk och klickar sedan på knappen Ladda ned. Du uppmanas att välja mellan att ladda ned en x64- och x86-MSI-fil. Ladda ned x64-filen om du kör 64-bitarsversionen av Windows eller x86-filen om du kör 32-bitarsversionen. Om du inte vet, se Vilken [version av Windows-operativsystemet använder jag?](https://support.microsoft.com/help/13443/windows-which-operating-system). När filen har laddats ned kör du den och följer anvisningarna i Installationsguiden.

2. Anslut till SharePoint som [global administratör eller SharePoint-administratör](/sharepoint/sharepoint-admin-role) i Microsoft 365. Mer information finns i Komma [igång med SharePoint Online Management Shell.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)


## <a name="view-any-existing-portal-launch-setups"></a>Visa eventuella befintliga startinställningar för portalen

Så här ser du om det finns befintliga konfigurationer för portalstart:

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

## <a name="schedule-a-portal-launch-on-the-site"></a>Schemalägga en portalstart på webbplatsen

Antalet vågor som krävs beror på den förväntade startstorleken. 
- Mindre än 10 000 användare: 1 omgång
- 10k-till-30k-användare: 3 vågor 
- 30k+ till 100 000 användare: 5 vågor
- Fler än 100 000 användare: 5 vågor och kontakta ditt Microsoft-kontoteam

### <a name="steps-for-bidirectional-redirection"></a>Steg för dubbelriktad omdirigering

Dubbelriktad omdirigering innebär att en ny modern SharePoint Online-portal lanseras så att en befintlig klassisk eller modern SharePoint-portal ersätts. Användare i aktiva vågor omdirigeras till den nya webbplatsen oavsett om de navigerar till den gamla eller nya webbplatsen. Användare i en icke-lanserad omgång som försöker komma åt den nya webbplatsen omdirigeras tillbaka till den gamla webbplatsen tills deras omgång startar. 

Vi stöder endast omdirigering mellan standardhemsidan på den gamla webbplatsen och standardhemsidan på den nya webbplatsen. Om du har administratörer eller ägare som behöver åtkomst till de gamla och nya webbplatserna utan att omdirigeras, se till att de listas med `WaveOverrideUsers` parametern.

Så här migrerar du användare från en befintlig SharePoint-webbplats till en ny SharePoint-webbplats på ett stegat sätt:

1. Kör följande kommando för att ange portalstartsvågar.
   
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

2. Bekräfta verifieringen. Det kan ta 5–10 minuter innan omdirigeringen slutförs i hela tjänsten. 

### <a name="steps-for-redirection-to-temporary-page"></a>Steg för omdirigering till tillfällig sida

Tillfällig sidomdirigering bör användas när det inte finns någon befintlig SharePoint-portal. Användare dirigeras till en ny modern SharePoint Online-portal på ett enhetligt sätt. Om en användare går i en omgång som inte har startats omdirigeras de till en tillfällig sida (alla URL-adresser). 

1. Kör följande kommando för att ange portalstartsvågar.
   
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

2. Bekräfta verifieringen. Det kan ta 5–10 minuter innan omdirigeringen slutförs i hela tjänsten. 

## <a name="pause-or-restart-a-portal-launch-on-the-site"></a>Pausa eller starta om en portalstart på webbplatsen

1. Kör följande kommando för att pausa en pågående portalstart och tillfälligt förhindra att kommande omgångsförlopp uppstår:

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl <object>
   ```
2. Verifiera att alla användare omdirigeras till den gamla webbplatsen. 

3. Om du vill starta om en portalstart som har pausats kör du följande kommando:

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl <object>
   ```
   
4. Kontrollera att omdirigeringen nu har återställts. 

## <a name="delete-a-portal-launch-on-the-site"></a>Ta bort en portalstart på webbplatsen

1. Kör följande kommando för att ta bort en portalstart som är schemalagd eller pågår för en webbplats.

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

2. Verifiera att ingen omdirigering sker för alla användare.

## <a name="learn-more"></a>Mer information
[Planera lanseringsplanen för portalen i SharePoint Online](./planportallaunchroll-out.md)