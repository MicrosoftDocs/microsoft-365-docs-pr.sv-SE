---
title: Microsoft 365 multi-geo-klient konfiguration
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.collection:
- SPO_Content
- Strat_SP_gtc
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
localization_priority: Normal
description: I den här artikeln lär du dig hur du lägger till satellit platser och konfigurerar klient organisationen för Microsoft 365 multi-geo.
ms.openlocfilehash: 4276d8ff70fed99e74f2cbab29386c81da06d17b
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694480"
---
# <a name="microsoft-365-multi-geo-tenant-configuration"></a>Microsoft 365 multi-geo-klient konfiguration

Innan du konfigurerar klient organisationen för Microsoft 365 multi-geo bör du se till att du har Läs [plan för microsoft 365 multi-geo](plan-for-multi-geo.md). För att följa anvisningarna i den här artikeln behöver du en lista över de geo-platser som du vill aktivera som satellit platser och vilka test användare som du vill etablera för dessa platser.

## <a name="add-the-multi-geo-capabilities-in-your-microsoft-365-plan-to-your-tenant"></a>Lägga till multi-geo-funktioner i ditt Microsoft 365-abonnemang till klient organisationen

För att använda Microsoft 365 multi-geo måste du ha _flera geo-funktioner i Microsoft 365_ -abonnemanget. Arbeta med ditt konto team för att lägga till det här abonnemanget i klient organisationen. Ditt konto team ansluter dig med rätt licensierings specialist och får din klient organisation konfigurerad.

Observera att _multi-geo-funktionerna i Microsoft 365_ -abonnemanget är en tjänst plan på användar nivå. Du behöver en licens för varje användare som du vill ha på en satellit plats. Du kan lägga till fler licenser under tiden när du lägger till användare på satellit platser.

När din klient organisation har etablerats med  _flera geo-funktioner i Microsoft 365_ -abonnemang blir fliken **geo platser** tillgängliga i administrations centret för OneDrive och SharePoint.

## <a name="add-satellite-locations-to-your-tenant"></a>Lägga till satellit platser till din klient organisation

Du måste lägga till en satellit plats för varje Geo-plats där du vill lagra data. Tillgängliga geo-platser visas i följande tabell:

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

![Skärm bild av sidan geo locations i administrations centret för SharePoint](../media/sharepoint-multi-geo-admin-center.png)

Lägga till en satellit plats

1. Öppna SharePoint Online Administrationscenter.

2. Gå till fliken **geo platser** .

3. Klicka på **Lägg till plats**.

4. Välj den plats du vill lägga till och klicka sedan på **Nästa**.

5. Skriv den domän som du vill använda med geo platsen och klicka sedan på **Lägg till**.

6. Klicka på **Stäng**.

Etableringen kan ta från några timmar upp till 72 timmar, beroende på innehavarens storlek. När etableringen av en satellit plats har genomförts får du ett e-postmeddelande. När den nya geo-platsen visas i blått på kartan på fliken **geo locations** i administrations centret för OneDrive kan du fortsätta med att ange användarens önskade data plats till den geo-platsen. 

> [!IMPORTANT]
> Din nya satellit plats konfigureras med standardinställningar. Detta gör att du kan konfigurera den satellit platsen efter behov.

## <a name="setting-users-preferred-data-location"></a>Ange användarens förvalda plats
<span id="_Setting_a_User's" class="anchor"><span id="_Toc508109326" class="anchor"></span></span> 

När du aktiverar de satellitiska platserna kan du uppdatera dina användar konton så att de använder lämplig data plats. Vi rekommenderar att du anger en vald plats för varje användare, även om användaren befinner sig på Central platsen.

> [!IMPORTANT]
> Om en användares önskade data plats är inställt på en plats som inte har kon figurer ATS som en satellit plats eller central plats kommer systemet att standardiseras till den centrala platsen när du konfigurerar OneDrive-och SharePoint-webbplatser och grupp post lådor.

> [!TIP]
> Vi rekommenderar att du påbörjar verifiering med en test användare eller en liten grupp användare innan du rullar ut multi-geo till din bredare organisation.

I Azure Active Directory (Azure AD) finns det två typer av användar objekt: endast molnbaserade användare och synkroniserade användare. Följ instruktionerna för din typ av användare.

### <a name="synchronize-users-preferred-data-location-using-azure-ad-connect"></a>Synkronisera användarens önskade data plats med Azure AD Connect 

Om företagets användare synkroniseras från ett lokalt Active Directory-system till Azure AD måste deras PreferredDataLocation vara ifyllda i AD och synkroniseras till Azure AD.

Följ processen i [Azure Active Directory Connect-synkronisering: konfigurera önskad data plats för Microsoft 365-resurser](/azure/active-directory/hybrid/how-to-connect-sync-feature-preferreddatalocation) för att konfigurera den önskade synkroniseringen av data platsen från din lokala Active Directory Domain Services (AD DS) till Azure AD.

Vi rekommenderar att du anger användarens önskade data plats som en del av standard arbets flödet för skapande av användare.

> [!IMPORTANT]
> För nya användare som inte har OneDrive etablerad kan du vänta minst 24 timmar efter att en användares PDL synkroniserats till Azure AD för att ändringarna ska spridas innan användaren loggar in på OneDrive för företag. (Om du anger önskad data plats innan användaren loggar in för att etablera sin OneDrive för företag säkerställs att användarens nya OneDrive etableras på rätt plats.)

### <a name="setting-preferred-data-location-for-cloud-only-users"></a>Ange önskad data plats för endast molnet 

Om företagets användare inte synkroniseras från ett lokalt Active Directory-system till Azure AD, vilket innebär att de skapas i Microsoft 365 eller Azure AD, måste PDL ställas in med Microsoft Azure Active Directory-modulen för Windows PowerShell.

Procedurerna i det här avsnittet kräver [Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen](https://www.powershellgallery.com/packages/MSOnline/1.1.166.0). Om du redan har den här modulen installerad, se till att uppdatera till den senaste versionen.

1.  [Anslut och logga](/powershell/connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell) in med en uppsättning globala administratörs uppgifter för din klient organisation.

2.  Använd cmdleten [set-MsolUser](https://docs.microsoft.com/powershell/msonline/v1/set-msoluser) för att ange den önskade data platsen för varje användare. Till exempel:

    `Set-MsolUser -userprincipalName Robyn.Buckley@Contoso.com -PreferredDatalocation EUR`

    Du kan kontrol lera att den önskade data platsen har uppdaterats korrekt med cmdleten Get-MsolUser. Till exempel:

    `(Get-MsolUser -userprincipalName Robyn.Buckley@Contoso.com).PreferredDatalocation`

![Skärm bild av PowerShell-fönstret med set-MsolUser](../media/multi-geo-tenant-configuration-image3.png)

Vi rekommenderar att du anger användarens önskade data plats som en del av standard arbets flödet för skapande av användare.

> [!IMPORTANT]
> För nya användare som inte har OneDrive etablerad väntar du minst 24 timmar efter att en användares PDL har ställts in för att ändringarna ska spridas innan användaren loggar in på OneDrive. (Om du anger önskad data plats innan användaren loggar in för att etablera sin OneDrive för företag säkerställs att användarens nya OneDrive etableras på rätt plats.)

## <a name="onedrive-provisioning-and-the-effect-of-pdl"></a>OneDrive-etablering och effekten av PDL

Om användaren redan har en OneDrive-webbplats skapad i klient organisationen, flyttas inte deras befintliga OneDrive automatiskt. Information om hur du flyttar en användares OneDrive finns i [för OneDrive för företag – för flytt](move-onedrive-between-geo-locations.md) Följ instruktionerna i flytta OneDrive mellan geo platser. (Observera att användarens Exchange-postlåda flyttas automatiskt när du ställer in användarens PDL.)

Om användaren inte har en OneDrive-webbplats i klient organisationen tillhandahålls OneDrive för dem i enlighet med deras PDL-värde, under antagandet att användaren matchar ett av företagets satellit platser.

## <a name="configuring-multi-geo-search"></a>Konfigurera multi-geo-sökning

Din multi-geo-klient har aggregerade Sök funktioner som gör att Sök frågor kan returnera resultat från valfri plats inom innehavaren.

Som standard returnerar sökningar från dessa start punkter sammansatta resultat, även om varje Sök index finns inom dess relevanta Geo-plats:

- OneDrive för företag

- Delve

- Start sidan för SharePoint

- Sök Center

Dessutom kan flera geo-Sök funktioner konfigureras för dina anpassade Sök program som använder SharePoint Search API.

Läs igenom [Konfigurera Sök efter OneDrive för företag multi-geo](configure-search-for-multi-geo.md) för instruktioner, inklusive begränsningar och skillnader.

## <a name="validating-the-microsoft-365-multi-geo-configuration"></a>Verifiera Microsoft 365 multi-geo-konfigurationen

Nedan följer några grundläggande användnings fall som du kanske vill ta med i verifierings planen innan du kan lansera Microsoft 365 multi-geo för ditt företag. När du har slutfört de här testerna och eventuella andra användnings fall som är relevanta för ditt företag kan du välja att gå vidare till att lägga till användarna i den första pilot gruppen.

**OneDrive för företag**

Välj OneDrive från Microsoft 365-Start programmet och bekräfta att du dirigeras automatiskt till rätt Geo-plats för användaren, baserat på användarens PDL. OneDrive för företag ska nu börja etablera på den platsen. När du har etablerat det kan du försöka ladda upp och ladda ned vissa dokument.

**OneDrive-mobilapp**

Logga in på din OneDrive-mobilapp med autentiseringsuppgifterna för ditt testkonto. Kontrol lera att du kan se dina OneDrive för företag-filer och kan interagera med dem från din mobila enhet.

**OneDrive-synkroniseringsklient**

Bekräfta att OneDrive-synkroniseringsklienten automatiskt identifierar din OneDrive för företag-Geo plats när du loggar in. Om du behöver hämta synkroniseringsklienten kan du klicka på **Synkronisera** i OneDrive-biblioteket.

**Office-program**

Kontrol lera att du kan komma åt OneDrive för företag genom att logga in från ett Office-program, till exempel Word. Öppna Office-programmet och välj "OneDrive – <TenantName> ". Office identifierar din OneDrive-plats och visar de filer som du kan öppna.

**Delning**

Försök dela OneDrive-filer. Kontrol lera att person väljaren visar alla dina SharePoint Online-användare oavsett deras Geo-plats.
