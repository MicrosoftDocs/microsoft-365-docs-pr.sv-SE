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
ms.openlocfilehash: 929492742fd140654bd13be8165093ee10647c6d
ms.sourcegitcommit: da34ac08c7d029c2c42d4428d0bb03fd57c448be
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/12/2020
ms.locfileid: "48999597"
---
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a>Starta portalen med hjälp av portalen starta Schemaläggaren

Du kan starta portalen med hjälp av portalen med att starta Schemaläggaren genom att först validera klient organisationens möjlighet att konfigurera en vågor för en ny portal. Därefter kan administratören verifiera en omdirigering av förfrågningar, baserat på förekomsten av en användare i aktiva vågor.

Om du vill ha mer information om hur du startar en lyckad Portal följer du de grundläggande principerna, metoderna och rekommendationerna i [skapa, starta och underhålla en felfri Portal](https://go.microsoft.com/fwlink/?linkid=2105838). 

## <a name="app-setup"></a>Installations program
1. Avinstallera om det finns en befintlig `Microsoft.Online.SharePoint.PowerShell` från datorn via kontroll panelen.
2. På PowerShell-pass `Install-Module -Name Microsoft.Online.SharePoint.PowerShell` .

## <a name="connect-to-sharepoint-online"></a>Ansluta till SharePoint Online
1. Öppna [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) i Windows.
2. Anslut till din klient organisation som administratör.
   - `Connect-SPOService -Url "https://*-admin.sharepoint.com" -Credential "username”`
3.  Ange lösen ordet när du uppmanas att göra det.

## <a name="command-to-get-an-existing-setup"></a>Kommando för att hämta en befintlig installation

Så här visar du befintliga Portal start konfigurationer:

1. Skicka `Get-SPOPortalLaunchWaves  -LaunchSiteUrl  https://*.sharepoint.com/sites/newsite` .
2. Skicka ytterligare en parameter `-DisplayFormat Raw` om du vill se Wave-samlingen formaterad som ett RAW-indataformat.

## <a name="commands-for-bi-directional-redirection"></a>Kommandon för omdirigering till dubbelriktad

Så här migrerar du gamla webbplats användare till den nya webbplatsen:

1. Skapa Portal lansera vågor.
   - Det här gäller endast i test fasen tidigt.
   - Om du vill testa effekten av ändringen omedelbart kontrollerar du att den första vågen `LaunchDateUtc` är inställd på dagens datum. Om du inte anger den här flaggan får du ett fel meddelande. Det här felet beror på att startas i en produktion på minst 7 dagar i förväg.

  `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/newsite" -RedirectionType Bidirectional -RedirectUrl "https://*.sharepoint.com/sites/oldsite" -ExpectedNumberOfUsers LessThan10kUsers -WaveOverrideUsers "*@microsoft.com" -Waves ' [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. Slutför verifiering.
  - Det kan ta upp till fem minuter innan omdirigeringen slutför sin konfiguration via tjänsten, så vänta tills du fortsätter.
  - Om du loggar in med användaren angiven som `WaveOverrideUsers` visas inga ändringar. Du bör hålla dig uppdaterad på den plats där du navigerade.
  - Logga in med en användare som är en del av *VISNINGS SG1*.
    - Gå till den gamla webbplatsen och omdirigera till den nya webbplatsen.
    - Navigera till den nya webbplatsen och du bör vara på den nya webbplatsen.
    - Logga med användare i *visnings program SG2* och navigera till den gamla webbplatsen och håll kontakten med den gamla webbplatsen.
    - Gå till den nya webbplatsen och omdirigera till den gamla webbplatsen.

3. Pausa Portal lansering.
  - Om du behöver pausa start vågor kan du pausa dem för "x" antal dagar. `Status`Om du ställer in flaggan på paus förhindras alla kommande våg förlopp. 
  - `Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.
  - Detta bekräftar att alla användare omdirigeras till den gamla webbplatsen.

4. Starta om portalen. 
  - `Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.
  - Kontrol lera att omdirigeringen nu har återställts.

5. Ta bort en portal start-konfiguration.
  - `Remove-SPOPortalLaunchWaves -LaunchSiteUrl https://*.sharepoint.com/sites/NewSite`.
  - Verifiera att ingen omdirigering sker för alla användare.

## <a name="commands-for-redirection-to-temporary-page"></a>Kommandon för omdirigering till tillfällig sida

Följ de här anvisningarna om du inte har någon föregående webbplats och vill utesluta användare som inte är i vågor från att landa på den nya Portal sidan.

Skapa en tillfällig sida på någon av webbplatserna:

1. Skapa en portal-starta Wave.
   - `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/NewSite" -RedirectionType ToTemporaryPage -RedirectUrl "https://*.sharepoint.com/sites/OldSite" -ExpectedNumberOfUsers From10kTo30kUsers -WaveOverrideUsers *@microsoft.com -Waves [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. Slutför verifiering.

  - Vänta fem minuter innan du fortsätter eftersom det kan ta upp till fem minuter att slutföra åtgärden.
  - Logga med den användare som är en del av *VISNINGS SG1* och:
     - Gå till den nya webbplatsen, så ska du vara på den nya webbplatsen.
     - Gå till den tillfälliga sidan och se till att du är på Temp-sidan.
  - Logga med den användare som är en del av *VISNINGS SG2* och:
     - Gå till den nya webbplatsen och omdirigera till den tillfälliga sidan.
     - Gå till den tillfälliga sidan och se till att du är på Temp-sidan.

3. Ta bort en portal start-konfiguration.
  - `Remove-SPOPortalLaunchWaves - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.
  - Verifiera att ingen omdirigering sker för alla användare.

## <a name="learn-more"></a>Mer information
[Planera hur portalen ska lanseras i SharePoint Online](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out)