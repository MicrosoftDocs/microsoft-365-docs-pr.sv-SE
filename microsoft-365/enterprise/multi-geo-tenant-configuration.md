---
title: Microsoft 365 Konfiguration för flera geoklienter
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
description: I den här artikeln får du lära dig hur du lägger till satellitplatser och konfigurerar klientorganisationen för Microsoft 365 Multi-Geo.
ms.openlocfilehash: 9176c66e8d0aa7e893ef137131147f8e0c85d3ac
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923654"
---
# <a name="microsoft-365-multi-geo-tenant-configuration"></a>Microsoft 365 Konfiguration för flera geoklienter

Innan du konfigurerar klientorganisationen för Microsoft 365 Multi-Geo bör du läsa [Planera för Microsoft 365 Multi-Geo.](plan-for-multi-geo.md) Om du vill följa stegen i den här artikeln behöver du en lista över de geoplatser som du vill aktivera som satellitplatser och testanvändarna som du vill etablera för dessa platser.

## <a name="add-the-multi-geo-capabilities-in-your-microsoft-365-plan-to-your-tenant"></a>Lägg till Multi-Geo Capabilities i ditt Microsoft 365-abonnemang i din klientorganisation

Om du Microsoft 365 använda Multi-Geo behöver du _Multi-Geo Capabilities Microsoft 365_ plan. Arbeta med kontoteamet för att lägga till planen i klientorganisationen. Ditt kontoteam kopplar dig till rätt licensieringsspecialist och konfigurerar din klientorganisation.

Observera att _Multi-Geo Capabilities i Microsoft 365_ är en serviceplan på användarnivå. Du behöver en licens för varje användare som du vill lagra på en satellitplats. Du kan lägga till fler licenser med tiden när du lägger till användare i satellitplatser.

När klientorganisationen har etablerats med fler geofunktioner i _Microsoft 365-abonnemanget_ blir fliken **Geoplatser** tillgänglig i administrationscentret för OneDrive och SharePoint.

## <a name="add-satellite-locations-to-your-tenant"></a>Lägga till satellitplatser i klientorganisationen

Du måste lägga till en satellitplats för varje geoplats där du vill lagra data. Tillgängliga geografiska platser visas i följande tabell:

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

![Skärmbild av sidan geoplatser i SharePoint administrationscenter](../media/sharepoint-multi-geo-admin-center.png)

Lägga till en satellitplats

1. Öppna SharePoint Online Administrationscenter.

2. Gå till **fliken Geoplatser.**

3. Klicka **på Lägg till plats.**

4. Välj den plats du vill lägga till och klicka sedan på **Nästa.**

5. Ange den domän som du vill använda med geoplatsen och klicka sedan på Lägg **till**.

6. Klicka på **Stäng**.

Etableringen kan ta från några timmar upp till 72 timmar, beroende på storleken på klientorganisationen. När etableringen av en satellitplats har slutförts får du en e-postbekräftelse. När den nya geoplatsen visas i blått på kartan på fliken Geoplatser i administrationscentret för OneDrive kan du fortsätta och ange **användarnas** önskade dataplats till den geoplatsen. 

> [!IMPORTANT]
> Den nya satellitplatsen konfigureras med standardinställningar. Det här gör att du kan konfigurera den satellitplatsen efter dina lokala efterlevnadsbehov.

## <a name="setting-users-preferred-data-location"></a>Ange användarnas önskade dataplats
<span id="_Setting_a_User's" class="anchor"><span id="_Toc508109326" class="anchor"></span></span> 

När du har aktiverar de satellitplatser som krävs kan du uppdatera dina användarkonton till att använda önskad dataplats. Vi rekommenderar att du anger en önskad dataplats för varje användare, även om användaren finns kvar på den centrala platsen.

> [!IMPORTANT]
> Om en användares önskade dataplats är inställd på en plats som inte har konfigurerats som en satellitplats eller den centrala platsen får systemet som standard den centrala platsen vid etablering av OneDrive- och SharePoint-webbplatser och grupppostlådor.

> [!TIP]
> Vi rekommenderar att du börjar validera med en testanvändare eller en liten grupp användare innan du distribuerar multi-geo till din bredare organisation.

I Azure Active Directory (Azure AD) finns det två typer av användarobjekt: endast molnanvändare och synkroniserade användare. Följ anvisningarna för din typ av användare.

### <a name="synchronize-users-preferred-data-location-using-azure-ad-connect"></a>Synkronisera användarens önskade dataplats med hjälp av Azure AD Anslut 

Om ditt företags användare synkroniseras från ett lokalt Active Directory-system till Azure AD måste deras PreferredDataLocation fyllas i i AD och synkroniseras med Azure AD.

Följ processen i [Azure Active Directory Anslut-synkronisering:](/azure/active-directory/hybrid/how-to-connect-sync-feature-preferreddatalocation) Konfigurera önskad dataplats för Microsoft 365-resurser för att konfigurera önskad dataplatssynkronisering från din lokala ACTIVE Directory Domain Services (AD DS) till Azure AD.

Vi rekommenderar att du anger användarens önskade dataplats som en del av standardarbetsflödet för att skapa användare.

> [!IMPORTANT]
> För nya användare som inte OneDrive har etablerats väntar du i minst 24 timmar efter att en användares PDL har synkroniserats till Azure AD för att ändringarna ska spridas innan användaren loggar in på OneDrive för företag. (Om du anger önskad dataplats innan användaren loggar in för att tillhandahålla sin OneDrive för företag säkerställer du att användarens nya OneDrive etableras på rätt plats.)

### <a name="setting-preferred-data-location-for-cloud-only-users"></a>Ange önskad dataplats endast för användare i molnet 

Om användarna i ditt företag inte synkroniseras från ett lokalt Active Directory-system till Azure AD, vilket innebär att de skapas i Microsoft 365 eller Azure AD, måste PDF-modulen ställas in med hjälp av Microsoft Azure Active Directory-modulen för Windows PowerShell.

I procedurerna i det här [avsnittet krävs Microsoft Azure Active Directory Modul för Windows PowerShell Modul](https://www.powershellgallery.com/packages/MSOnline/1.1.166.0). Om du redan har den här modulen installerad bör du uppdatera till den senaste versionen.

1.  [Anslut och logga in](/powershell/connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell) med en uppsättning autentiseringsuppgifter som global administratör för klientorganisationen.

2.  Använd [cmdleten Set-MsolUser](/powershell/msonline/v1/set-msoluser) för att ange önskad dataplats för var och en av dina användare. Till exempel:

    `Set-MsolUser -userprincipalName Robyn.Buckley@Contoso.com -PreferredDatalocation EUR`

    Du kan kontrollera att den rekommenderade dataplatsen har uppdaterats korrekt med hjälp av Get-MsolUser cmdlet. Till exempel:

    `(Get-MsolUser -userprincipalName Robyn.Buckley@Contoso.com).PreferredDatalocation`

![Skärmbild av PowerShell-fönstret med Set-msoluser](../media/multi-geo-tenant-configuration-image3.png)

Vi rekommenderar att du anger användarens önskade dataplats som en del av standardarbetsflödet för att skapa användare.

> [!IMPORTANT]
> För nya användare som inte OneDrive har etablerats väntar du i minst 24 timmar efter att en användares PDL har angetts för att ändringarna ska spridas innan användaren loggar in i OneDrive. (Om du anger önskad dataplats innan användaren loggar in för att tillhandahålla sin OneDrive för företag säkerställer du att användarens nya OneDrive etableras på rätt plats.)

## <a name="onedrive-provisioning-and-the-effect-of-pdl"></a>OneDrive Etablering och effekten av PDL

Om användaren redan har en OneDrive webbplats som skapats i klientorganisationen flyttas inte användarens befintliga e-OneDrive automatiskt när användaren anger sitt PDL OneDrive. Information om hur du flyttar en användares OneDrive finns [i OneDrive för företag Geo Move](move-onedrive-between-geo-locations.md).

> [!NOTE]
> Exchange Online automatiskt flyttar användarens postlåda om PLD-ändringarna och MailboxRegion inte längre matchar geoplatskoden för postlådedatabasen. Mer information finns i Administrera [Exchange Online postlådor i en geomiljö.](./administering-exchange-online-multi-geo.md)

Om användaren inte har en OneDrive-webbplats i klientorganisationen etableras OneDrive för dem i enlighet med PDL-värdet, under förutsättning att PDL-värdet för användaren matchar en av företagets satellitplatser.

## <a name="configuring-multi-geo-search"></a>Konfigurera multi geosökning

Din geoklientorganisation har samlade sökfunktioner som gör att en sökfråga kan returnera resultat från valfri plats i klientorganisationen.

Som standard returnerar sökningar från dessa startpunkter aggregerade resultat, även om varje sökindex finns inom dess relevanta geoplats:

- OneDrive för företag

- Delve

- SharePoint Home

- Sökcenter

Dessutom kan Multi-Geo-sökning konfigureras för dina anpassade sökprogram som använder sök-API:t SharePoint sökfunktionen.

Läs Konfigurera [sökning efter e OneDrive för företag för multi-geo](configure-search-for-multi-geo.md) för anvisningar, bland annat eventuella begränsningar och skillnader.

## <a name="validating-the-microsoft-365-multi-geo-configuration"></a>Validera konfigurationen Microsoft 365 Multi-Geo

Nedan följer några grundläggande användningsfall som du kanske vill ta med i valideringsplanen innan du distribuerar Microsoft 365 Multi-Geo för ditt företag. När du har utfört testerna och alla andra användningsfall som är relevanta för ditt företag kan du välja att gå vidare och lägga till användare i den första pilotgruppen.

**OneDrive för företag**

Välj OneDrive i Microsoft 365-startprogrammet och bekräfta att du automatiskt dirigeras till lämplig geoplats för användaren, baserat på användarens PDL. OneDrive för företag bör nu börja etableras på den platsen. När den har etablerats kan du försöka ladda upp och ladda ned några dokument.

**OneDrive Mobilapp**

Logga in på OneDrive-mobilappen med dina autentiseringsuppgifter för testkontot. Bekräfta att du kan se dina OneDrive för företag och kan interagera med dem från din mobila enhet.

**OneDrive-synkroniseringsklient**

Kontrollera att den OneDrive automatiskt identifierar din geografiska OneDrive för företag vid inloggning. Om du behöver ladda ned synkroniseringsklienten kan du klicka **på Synkronisera** i OneDrive bibliotek.

**Office program**

Bekräfta att du kan komma OneDrive för företag genom att logga in från ett Office program, till exempel Word. Öppna Office och välj "OneDrive – <TenantName> ". Office identifierar din OneDrive och visar de filer som du kan öppna.

**Delning**

Prova att dela OneDrive filer. Bekräfta att väljaren visar alla dina användare SharePoint onlineanvändare oavsett deras geografiska position.