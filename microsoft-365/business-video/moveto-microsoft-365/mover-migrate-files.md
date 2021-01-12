---
title: 'Migrera Google-filer till Microsoft 365 för företag '
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Lär dig hur du migrerar Google-filer till Microsoft 365 för företag med flytt firman.
ms.openlocfilehash: a6f9dbf7803cb552c23b6c6abb13d13d6f3eda5d
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794701"
---
# <a name="migrate-google-files-to-microsoft-365-for-business"></a>Migrera Google-filer till Microsoft 365 för företag 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4MhaD?autoplay=false]

När du flyttar till Microsoft 365 för företag ska du migrera dina filer från Google Drive. Du kan använda appen kraft för att flytta filer från personliga och delade enheter. Mer information finns i [migrera moln migrering](https://docs.microsoft.com/sharepointmigration/mover-plan-migration)

> [!NOTE]
> En kopia av filerna kopieras och kopiorna flyttas till Microsoft 365 för företag. Originalfilerna sparas också i Google Drives.

## <a name="before-you-start"></a>Innan du börjar

Alla användare ska ha loggat in på Microsoft 365 för företag och ställa in sin OneDrive för företag. Det gör du genom att gå till [Office.com](https://office.com), logga in med ditt Microsft 365 för företag-autentiseringsuppgifter och sedan välja OneDrive.

## <a name="try-it"></a>Prova!

### <a name="install-mover"></a>Installera flyttat

1. Logga in på din Google Workspace-administratörskonsolen på [admin.Google.com](https://admin.google.com).

1. Välj **appar**, **Google Workspace Marketplace-appar** och **Lägg sedan till program i domän installations listan**.

1. Leta efter flytt firman och välj den.

1. Välj **Domain install** och sedan **Continue**.

1. Granska behörigheterna, markera kryss rutan för att godkänna villkoren och välj sedan **Tillåt**, Välj **Nästa** och sedan **färdig**.

### <a name="create-connectors-and-run-the-migration"></a>Skapa kopplingar och kör migreringen

1. Återvänd till **Google Workspace Marketplace-appar**.
1. Uppdatera webbläsaren och välj programmet **Flytta** .
1. Bläddra nedåt och välj den universella navigerings länken.
1. Välj **Godkänn ny koppling**, leta reda på **G Suite (administratör)** och välj **auktorisera**.
1. Ändra **visnings namnet**, om du vill och välj sedan **Verifiera**.
1. Välj ett Google admin-konto, granska behörigheterna och välj sedan **Tillåt**.

    Kraft Drive visar antalet grupp enheter och användar enheter som identifieras. 

1. Under **Välj mål** väljer du **Godkänn ny koppling**, letar reda på **Office 365** och väljer **auktorisera**.
1. Om du vill ge behörighet till programmet flytta i din Azure Active Directory navigerar du till [aka.MS/Office365MoverAuth](https://aka.ms/Office365MoverAuth).
1. Välj **Office 365 flytt firma**, **behörigheter**, **bevilja administratörs medgivande för ditt företag**.
1. Välj ditt konto, granska behörigheterna och välj **acceptera**.
1. Välj **Egenskaper** och kontrol lera att **användar tilldelning krävs?** är aktiverat.
1. Gå tillbaka till programmet kraft, ändra **visnings namnet** om du vill, Välj **Godkänn** och välj sedan ett Microsoft administratörs konto.

    Med den här funktionen får du information om antalet SharePoint Online-webbplatser (eller SPO) och användare som identifieras.
1. Välj **Fortsätt migreringen**, Välj **Lägg till användare** och **Upptäck och Lägg sedan till användare automatiskt**.

    Programmet kör automatiskt försöker mappa enheter från käll Sök vägen i Google till mål Sök vägen i Microsoft 365. 

    Om en enhet inte mappas automatiskt lägger du till mål Sök vägen till en CSV-fil som du senare kommer att använda för att migrera den delade enheten till ett SharePoint-dokumentbibliotek. 

1. I det här fallet har vi lagt till en SharePoint-webbplats som heter migrerade filer och noterat URL-adressen till sidan dokument. 
1. En CSV-fil skapas sedan med käll Sök vägens format, mål Sök väg och taggar. 

    Mer information finns i [aka.MS/movercsv](https://docs.microsoft.com/sharepointmigration/mover-create-migration-csv).

    När du lägger till URL-adressen för mål Sök vägen tar du bort allt efter delade dokument, till exempel att denna fullständiga URL inte fungerar: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`

    Ändra den till: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`

1. När CSV-filen är klar väljer du **migreringsåtgärder**, **lägger till i migrering**, **väljer en fil som ska laddas upp**.
1. Gå till CSV-filen, markera den och välj sedan **Öppna**.
1. Markera de användar enheter vars filer du vill migrera och välj sedan **Starta migrering av användare**.
1. Granska migrations informationen, Välj när du vill starta migreringen, Godkänn **villkoren och** Välj sedan **Fortsätt**.

Programmet flytta över dig när migreringen är slutförd.