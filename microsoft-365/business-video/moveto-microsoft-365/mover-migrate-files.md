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
description: Lär dig hur du migrerar Google-filer till Microsoft 365 för företag med hjälp av Mover.
ms.openlocfilehash: 6feabff7e36e84f7dba56e74333648325cf43920
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913580"
---
# <a name="migrate-google-files-to-microsoft-365-for-business"></a>Migrera Google-filer till Microsoft 365 för företag 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4MhaD?autoplay=false]

När du flyttar Microsoft 365 för företag ska du migrera dina filer från Google Drive. Du kan använda appen Mover för att flytta filer från personliga och delade enheter. Mer information finns i [Mover Cloud Migration.](/sharepointmigration/mover-plan-migration)

> [!NOTE]
> Mover gör en kopia av filerna och flyttar kopiorna till Microsoft 365 för företag. De ursprungliga filerna finns även kvar i Google Drives.

## <a name="before-you-start"></a>Innan du börjar

Alla användare bör ha loggat in på Microsoft 365 för företag och ställt in OneDrive för företag. Det gör du genom att [gå office.com](https://office.com), logga in med dina inloggningsuppgifter Microsoft 365 för företag och sedan välja OneDrive.

## <a name="try-it"></a>Prova själv!

### <a name="install-mover"></a>Installera Mover

1. Logga in på administratörskonsolen för Google Workspace [admin.google.com](https://admin.google.com).

1. Välj **Appar Google** Workspace  >  **Marketplace-appar Lägg** till app i listan För installation av  >  **domän**.

1. Sök efter Mover och markera den.

1. Välj **Domäninstallation** och sedan **Fortsätt.**

1. Granska behörigheterna, markera kryssrutan för att godkänna villkoren och välj sedan **Tillåt**, välj **Nästa** och sedan **Klar**.

### <a name="create-connectors-and-run-the-migration"></a>Skapa kopplingar och köra migreringen

1. Återgå till **Google Workspace Marketplace-appar**.
1. Uppdatera webbläsaren och välj **appen Mover.**
1. Rulla nedåt och välj den universella navigeringslänken.
1. Välj **Auktorisera ny** anslutning , **leta reda på G Suite (administratör)** och välj **Auktorisera**.
1. Om du **vill kan** du ändra visningsnamnet och sedan **välja Godkänn.**
1. Välj ett Google-administratörskonto, granska behörigheterna och välj sedan **Tillåt**.

    Mover visar antalet teamenheter och användare kör den upptäckt. 

1. Under **Välj destination** väljer du Authorize New **Connector**, **Office 365** och väljer **Authorize**.
1. Om du vill ge behörigheter till appen Mover i Azure Active Directory navigerar du till [aka.ms/Office365MoverAuth](https://aka.ms/Office365MoverAuth).
1. Välj **Office 365 – Mover**, **Behörigheter**, **Bevilja administratörsmedgivande för ditt företag**.
1. Välj ditt konto, granska behörigheterna och välj **Acceptera**.
1. Välj **Egenskaper** och kontrollera att **Användartilldelning krävs?** är aktiverat.
1. Gå tillbaka till appen Mover, ändra **visningsnamnet**, om du vill, välj **Auktorisera** och välj sedan ett Microsoft-administratörskonto.

    Mover informerar dig om antalet SharePoint (eller SPO) webbplatser och användare som upptäckts.
1. Välj **Fortsätt migreringskonfiguration**, välj **Lägg till användare** och sedan Upptäck och lägg till användare **automatiskt.**

    Appen Mover försöker mappa enheter från källsökvägen i Google till målsökvägen i Microsoft 365. 

    Om en enhet inte mappas automatiskt lägger du till dess målsökväg i en CSV-fil, som vi använder senare för att migrera den delade enheten till ett SharePoint-dokumentbibliotek. 

1. I det här fallet har vi lagt SharePoint webbplats med namnet Migrerade filer och antecknat WEBBADRESSen för dokumentsidan. 
1. Sedan skapade vi en CSV-fil med formatet Källsökväg, Målsökväg och Taggar. 

    Mer information finns [i aka.ms/movercsv](/sharepointmigration/mover-create-migration-csv).

    När du lägger till URL:en för målsökväg tar du bort allt efter Delade dokument. Den här fullständiga URL:en fungerar till exempel inte: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`

    Ändra den till: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`

1. När CSV-filen är klar väljer du **Migreringsåtgärder , Lägg** **till i migrering**, Välj en fil att ladda **upp.**
1. Navigera till CSV-filen, markera den och välj **öppna**.
1. Välj den användare som kör de filer du vill migrera och välj **sedan Starta migrering av användare.**
1. Granska migreringsinformationen, välj när migreringen ska starta, godkänn **villkoren och** välj sedan **Fortsätt.**

Du får ett meddelande i appen Mover när migreringsprocessen är klar.