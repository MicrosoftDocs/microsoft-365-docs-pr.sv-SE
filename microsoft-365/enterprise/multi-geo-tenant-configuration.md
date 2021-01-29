---
title: Konfiguration av Microsoft 365 Multi-Geo-klientorganisation
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
description: I den här artikeln lär du dig hur du lägger till satellitplatser och konfigurerar klientorganisationen för Microsoft 365 Multi-Geo.
ms.openlocfilehash: fb907c02a4714c5a2d8e47245321252e7186a8a7
ms.sourcegitcommit: f3059a0065496623e36e5a084cd2291e6b844597
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/28/2021
ms.locfileid: "50040574"
---
# <a name="microsoft-365-multi-geo-tenant-configuration"></a>Konfiguration av Microsoft 365 Multi-Geo-klientorganisation

Innan du konfigurerar klientorganisationen för Microsoft 365 Multi-Geo bör du läsa Abonnemang för [Microsoft 365 Multi-Geo.](plan-for-multi-geo.md) Om du vill följa stegen i den här artikeln behöver du en lista över de geoplatser som du vill aktivera som satellitplatser och testanvändarna som du vill etablera för dessa platser.

## <a name="add-the-multi-geo-capabilities-in-your-microsoft-365-plan-to-your-tenant"></a>Lägg till Multi-Geo Capabilities i Microsoft 365-abonnemanget i din klientorganisation

Om du vill använda Microsoft 365 Multi-Geo behöver du _Multi-Geo Capabilities i Microsoft 365-abonnemanget._ Arbeta med ditt kontoteam för att lägga till den här planen i klientorganisationen. Ditt kontoteam kommer att ansluta dig till rätt licensieringsspecialist och få din klientorganisation konfigurerad.

Observera att _Multi-Geo Capabilities i Microsoft 365-abonnemanget_ är ett serviceabonnemang på användarnivå. Du behöver en licens för varje användare som du vill vara värd för på en satellitplats. Du kan lägga till fler licenser med tiden när du lägger till användare i satellitplatser.

När klientorganisationen har etablerats med  _Multi-Geo Capabilities i Microsoft 365-abonnemanget_ blir fliken **Geoplatser** tillgänglig i administrationscentret för OneDrive och SharePoint.

## <a name="add-satellite-locations-to-your-tenant"></a>Lägga till satellitplatser i klientorganisationen

Du måste lägga till en satellitplats för varje geoplats där du vill lagra data. Tillgängliga geografiska platser visas i följande tabell:

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

![Skärmbild av sidan geoplatser i administrationscentret för SharePoint](../media/sharepoint-multi-geo-admin-center.png)

Lägga till en satellitplats

1. Öppna SharePoint Online Administrationscenter.

2. Gå till **fliken Geoplatser.**

3. Klicka **på Lägg till plats.**

4. Välj den plats du vill lägga till och klicka sedan på **Nästa.**

5. Ange den domän som du vill använda med geoplatsen och klicka sedan på **Lägg till.**

6. Klicka på **Stäng**.

Etableringen kan ta från ett par timmar upp till 72 timmar, beroende på storleken på klientorganisationen. När etableringen av en satellitplats har slutförts får du en e-postbekräftelse. När den nya geoplatsen visas i blått på kartan på fliken Geoplatser i administrationscentret för OneDrive kan du fortsätta och ange **användarnas** önskade dataplats till den geoplatsen. 

> [!IMPORTANT]
> Din nya satellitplats konfigureras med standardinställningar. Det här gör att du kan konfigurera den satellitplatsen efter dina lokala efterlevnadsbehov.

## <a name="setting-users-preferred-data-location"></a>Ange användarnas föredragna dataplats
<span id="_Setting_a_User's" class="anchor"><span id="_Toc508109326" class="anchor"></span></span> 

När du har aktiverar de satellitplatser som behövs kan du uppdatera användarkontona så att de använder rätt önskad dataplats. Vi rekommenderar att du anger en önskad dataplats för varje användare, även om användaren finns kvar på den centrala platsen.

> [!IMPORTANT]
> Om en användares önskade dataplats anges till en plats som inte har konfigurerats som en satellitplats eller den centrala platsen får systemet som standard den centrala platsen när OneDrive- och SharePoint-webbplatser och grupppostlådor etableras.

> [!TIP]
> Vi rekommenderar att du börjar validera med en testanvändare eller en liten grupp användare innan du distribuerar multi-geo till din bredare organisation.

Det finns två typer av användarobjekt i Azure Active Directory (Azure AD): endast molnanvändare och synkroniserade användare. Följ anvisningarna för din typ av användare.

### <a name="synchronize-users-preferred-data-location-using-azure-ad-connect"></a>Synkronisera användarens föredragna dataplats med hjälp av Azure AD Connect 

Om användarna i ditt företag synkroniseras från ett lokalt Active Directory-system till Azure AD måste deras PreferredDataLocation fyllas i i AD och synkroniseras med Azure AD.

Följ processen i [Azure Active Directory Connect-synkronisering:](/azure/active-directory/hybrid/how-to-connect-sync-feature-preferreddatalocation) Konfigurera önskad dataplats för Microsoft 365-resurser för att konfigurera synkronisering av önskad dataplats från din lokala Active Directory DS (AD DS) till Azure AD.

Vi rekommenderar att du anger användarens föredragna dataplats som en del av ditt vanliga arbetsflöde för att skapa användare.

> [!IMPORTANT]
> För nya användare som inte har någon OneDrive-etablering bör du vänta i minst 24 timmar efter att en användares PDF-fil har synkroniserats med Azure AD för att ändringarna ska spridas innan användarna loggar in i OneDrive för företag. (Genom att ange önskad dataplats innan användaren loggar in för att etablera sin OneDrive för företag säkerställer du att användarens nya OneDrive etableras på rätt plats.)

### <a name="setting-preferred-data-location-for-cloud-only-users"></a>Ange önskad dataplats för användare endast i molnet 

Om användarna i ditt företag inte synkroniseras från ett lokalt Active Directory-system till Azure AD, vilket innebär att de skapas i Microsoft 365 eller Azure AD, måste PDF-operativsystemet ställas in med Hjälp av Microsoft Azure Active Directory-modulen för Windows PowerShell.

För procedurerna i det här avsnittet [krävs Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen.](https://www.powershellgallery.com/packages/MSOnline/1.1.166.0) Om du redan har den här modulen installerad bör du uppdatera till den senaste versionen.

1.  [Anslut och logga in](/powershell/connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell) med en uppsättning autentiseringsuppgifter som global administratör för klientorganisationen.

2.  Använd [cmdleten Set-MsolUser](https://docs.microsoft.com/powershell/msonline/v1/set-msoluser) för att ange önskad dataplats för var och en av användarna. Till exempel:

    `Set-MsolUser -userprincipalName Robyn.Buckley@Contoso.com -PreferredDatalocation EUR`

    Du kan kontrollera om den rekommenderade dataplatsen har uppdaterats korrekt med hjälp av cmdleten Get-MsolUser. Till exempel:

    `(Get-MsolUser -userprincipalName Robyn.Buckley@Contoso.com).PreferredDatalocation`

![Skärmbild av PowerShell-fönstret med Set-msoluser](../media/multi-geo-tenant-configuration-image3.png)

Vi rekommenderar att du anger användarens föredragna dataplats som en del av ditt vanliga arbetsflöde för att skapa användare.

> [!IMPORTANT]
> För nya användare som inte har någon OneDrive-etablering bör du vänta i minst 24 timmar efter att en användares PDF-fil har angetts för att ändringarna ska spridas innan användaren loggar in på OneDrive. (Genom att ange önskad dataplats innan användaren loggar in för att etablera sin OneDrive för företag säkerställer du att användarens nya OneDrive etableras på rätt plats.)

## <a name="onedrive-provisioning-and-the-effect-of-pdl"></a>OneDrive-etablering och effekten av PDL

Om användaren redan har en OneDrive-webbplats skapad i klientorganisationen flyttas inte deras befintliga OneDrive automatiskt när du anger deras PDF-fil. Information om hur du flyttar en användares OneDrive finns i [Geoflyttning i OneDrive för företag.](move-onedrive-between-geo-locations.md)

> [!NOTE]
> Exchange Online flyttar automatiskt användarens postlåda om PLD-ändringarna och postlåderegion inte längre stämmer överens med geoplatskoden för postlådedatabasen. Mer information finns i Administrera [Exchange Online-postlådor i en miljö med flera geografiska miljöer.](https://docs.microsoft.com/microsoft-365/enterprise/administering-exchange-online-multi-geo)

Om användaren inte har en OneDrive-webbplats i klientorganisationen etableras OneDrive åt dem i enlighet med deras PDL-värde, förutsatt att PDF-talet för användaren matchar en av företagets satellitplatser.

## <a name="configuring-multi-geo-search"></a>Konfigurera multi geosökning

Din multigeobaserade klientorganisation har samlade sökfunktioner som gör att en sökfråga kan returnera resultat från valfri plats i klientorganisationen.

Som standard returnerar sökningar från dessa startpunkter aggregerade resultat, även om varje sökindex finns inom dess relevanta geoplats:

- OneDrive för företag

- Delve

- Start för SharePoint

- Sökcenter

Dessutom kan funktioner för flera geosökning konfigureras för anpassade sökprogram som använder SharePoints sök-API.

I Konfigurera [sökning efter OneDrive för företag – Multi-Geo](configure-search-for-multi-geo.md) finns instruktioner, inklusive eventuella begränsningar och skillnader.

## <a name="validating-the-microsoft-365-multi-geo-configuration"></a>Validera Microsoft 365 Multi-Geo-konfigurationen

Nedan följer några grundläggande användningsfall som du kanske vill inkludera i din valideringsplan innan du allmänt distribuerar Microsoft 365 Multi-Geo till ditt företag. När du har slutfört dessa tester och eventuella ytterligare användningsfall som är relevanta för ditt företag kan du välja att gå vidare och lägga till användare i den första pilotgruppen.

**OneDrive för företag**

Välj OneDrive från appstartaren för Microsoft 365 och bekräfta att du automatiskt dirigeras till rätt geoplats för användaren, baserat på användarens PDF-fil. OneDrive för företag bör nu börja etableras på den platsen. När de har etablerats kan du försöka ladda upp och ladda ned vissa dokument.

**OneDrive-mobilappen**

Logga in på OneDrive-mobilappen med dina autentiseringsuppgifter för testkontot. Bekräfta att du kan se dina OneDrive för företag-filer och kan interagera med dem från din mobila enhet.

**OneDrive-synkroniseringsklient**

Kontrollera att OneDrive-synkroniseringsklienten automatiskt identifierar din geoplats i OneDrive för företag vid inloggning. Om du behöver ladda ned synkroniseringsklienten kan du klicka **på Synkronisera** i OneDrive-biblioteket.

**Office-program**

Bekräfta att du kan komma åt OneDrive för företag genom att logga in från ett Office-program, till exempel Word. Öppna Office-programmet och välj "OneDrive – <TenantName> ". Office identifierar din OneDrive-plats och visar de filer som du kan öppna.

**Delning**

Prova att dela OneDrive-filer. Bekräfta att alla dina SharePoint Online-användare visas i väljaren, oavsett deras geografiska position.
