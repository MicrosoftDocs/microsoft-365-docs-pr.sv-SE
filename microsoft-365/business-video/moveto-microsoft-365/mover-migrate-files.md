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
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Lär dig hur du migrerar Google-filer till Microsoft 365 för företag med hjälp av Mover.
ms.openlocfilehash: 99040e4846aba084f40536e88f0aed70998f48be
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928204"
---
# <a name="migrate-google-files-to-microsoft-365-for-business"></a>Migrera Google-filer till Microsoft 365 för företag 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4MhaD?autoplay=false]

När du flyttar över till Microsoft 365 för företag bör du migrera dina filer från Google Drive. Du kan använda appen Mover för att flytta filer från personliga och delade enheter. Mer information finns i [Mover Cloud Migration](https://docs.microsoft.com/sharepointmigration/mover-plan-migration)

> [!NOTE]
> Mover gör en kopia av filerna och flyttar kopiorna till Microsoft 365 för företag. De ursprungliga filerna finns också kvar i Google Drives.

## <a name="before-you-start"></a>Innan du börjar

Alla användare bör ha loggat in på Microsoft 365 för företag och konfigurera onedrive för företag. Det gör du genom att [gå till office.com,](https://office.com)logga in med microsft 365 för företag-autentiseringsuppgifter och sedan välja OneDrive.

## <a name="try-it"></a>Prova!

### <a name="install-mover"></a>Installera Mover

1. Logga in på administratörskonsolen för Google Workspace [på admin.google.com.](https://admin.google.com)

1. Välj **Appar,** **Google Workspace Marketplace-appar** och lägg sedan till app i listan **Domäninstallation.**

1. Sök efter Mover och markera den.

1. Välj **Domäninstallation** och sedan **Fortsätt.**

1. Granska behörigheterna, markera kryssrutan för att godkänna villkoren och välj **sedan** Tillåt, välj **Nästa** och sedan **Klar.**

### <a name="create-connectors-and-run-the-migration"></a>Skapa kopplingar och köra migreringen

1. Återgå till **Google Workspace Marketplace-appar.**
1. Uppdatera webbläsaren och välj **appen Mover.**
1. Rulla nedåt och välj den universella navigeringslänken.
1. Välj **Auktorisera ny** koppling, **leta upp G Suite (administratör)** och välj **Auktorisera.**
1. Ändra **visningsnamnet om** du vill och välj sedan **Godkänn.**
1. Välj ett administratörskonto för Google, granska behörigheterna och välj **sedan Tillåt.**

    Mover visar antalet teamenheter och användarenheter som identifierats. 

1. Under **Välj mål** väljer du Godkänn ny **koppling,** letar reda på Office **365** och väljer **Auktorisera.**
1. Om du vill ge behörigheter till Mover-appen i Azure Active Directory går du till [aka.ms/Office365MoverAuth.](https://aka.ms/Office365MoverAuth)
1. Välj **Office 365 Mover,** **Behörigheter,** **Bevilja administratörsmedgivande för ditt företag.**
1. Välj ditt konto, granska behörigheterna och välj **Acceptera.**
1. Välj **Egenskaper** och kontrollera att **användartilldelning krävs?** är aktiverat.
1. Gå tillbaka till appen Mover, ändra visningsnamn **,** välj **Godkänn** om du vill och välj sedan ett Microsoft-administratörskonto.

    Mover informerar dig om antalet SharePoint Online-webbplatser (eller SPO-webbplatser) och användare som upptäckts.
1. Välj **Fortsätt migrering, välj** Lägg till **användare** och sedan Identifiera automatiskt och Lägg **till användare.**

    Appen Mover försöker mappa enheter från källsökvägen i Google till målsökvägen i Microsoft 365. 

    Om en enhet inte mappas automatiskt lägger du till målsökvägen till en CSV-fil som vi senare använder för att migrera den delade enheten till ett SharePoint-dokumentbibliotek. 

1. I det här fallet har vi lagt till en SharePoint-webbplats som heter Migrerade filer och antecknat URL-adressen för dokumentsidan. 
1. Sedan skapade vi en CSV-fil med formatet Källsökväg, Målsökväg och Taggar. 

    Mer information finns [i aka.ms/movercsv.](https://docs.microsoft.com/sharepointmigration/mover-create-migration-csv)

    När du lägger till URL:en för målsökvägen tar du bort allt efter Delade dokument, till exempel fungerar inte den här fullständiga URL:en: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`

    Ändra den till: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`

1. När CSV-filen är klar väljer **du** Migreringsåtgärder, Lägg till **i migrering,** Välj **en fil att ladda upp.**
1. Gå till CSV-filen, markera den och välj sedan **Öppna.**
1. Välj den användare som kör de filer du vill migrera och välj sedan **Starta migrering av användare.**
1. Granska migreringsinformationen, välj när migreringen ska starta, godkänn **villkoren** och välj sedan **Fortsätt.**

Appen Mover meddelar dig när migreringen är klar.