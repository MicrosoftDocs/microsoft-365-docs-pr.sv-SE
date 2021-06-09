---
title: Planera för Microsoft 365 Multi-Geo
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.collection:
- Strat_SP_gtc
- SPO_Content
localization_priority: Normal
description: Läs mer Microsoft 365 om Multi-Geo, hur multi-geo fungerar och vilka geoplatser som är tillgängliga för datalagring.
ms.openlocfilehash: 9625d55015cc0f18801d59e82fc8ca7090b3b721
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927538"
---
# <a name="plan-for-microsoft-365-multi-geo"></a>Planera för Microsoft 365 Multi-Geo

Den här vägledningen är utformad för administratörer för multinationella företag som förbereder sin Microsoft 365-klientorganisation så att den utökas till ytterligare områden i enlighet med företagets närvaro för att uppfylla kraven för datalagring.

I en multigeokonfiguration består klientorganisationen Microsoft 365 av en central plats och en eller flera satellitplatser. Det här är en enskild klientorganisation som spänner över flera geografiska platser. Information om klientorganisationen, inklusive geoplatser, finns i Azure Active Directory (Azure AD).

Här är några viktiga multigeotermer som hjälper dig att förstå de grundläggande begreppen i konfigurationen:

-   **Klient** – En organisations representation i Microsoft 365 som normalt har en eller flera domäner kopplade till den (till exempel https://contoso.sharepoint.com) . 

-   **Geoplatser –** De geografiska platser som är tillgängliga för datavärdinformation i Microsoft 365 klientorganisation.

-   **Satellitplatser** – De ytterligare geoplatser som du har konfigurerat för att lagra data i Microsoft 365 klientorganisationen. Flera geoklienter omfattar mer än en geoplats, till exempel Nordamerika och Europa.

-   **Önskad dataplats (PDL)** – Den geoplats där en enskild användares Exchange och OneDrive data lagras. Den kan ställas in av administratören på någon av de geoplatser som har konfigurerats för klientorganisationen. Observera att om du ändrar PDF-filer för en användare som redan har en OneDrive-webbplats flyttas inte användarens OneDrive data till den nya geoplatsen automatiskt. Mer [information finns OneDrive flytta ett bibliotek till en annan](move-onedrive-between-geo-locations.md) geoplats. Om postlådan har Exchange postlåda flyttas den automatiskt till den nya önskade dataplatsen.

Aktivering av Multi-Geo kräver fyra viktiga steg:

1.  Arbeta med kontoteamet och lägg till _Multi-Geo Capabilities i_ Microsoft 365-tjänstabonnemanget.

2.  Välj önskad satellitplats och lägg till dem i klientorganisationen.

3.  Ange användarnas önskade dataplats till önskad satellitplats. När en ny OneDrive eller Exchange postlåda har etablerats för en användare etableras den till användarens PDL.

4.  Migrera användarnas befintliga OneDrive från den centrala platsen till deras önskade dataplats efter behov. (Exchange postlådor migreras automatiskt när du anger en användares PDL.)

Mer information Microsoft 365 finns i Konfigurera Microsoft 365 [Multi-Geo.](multi-geo-tenant-configuration.md)

> [!IMPORTANT]
> Observera att Microsoft 365 Multi-Geo inte är utformat för prestandaoptimering, det är utformat för att uppfylla krav för datalagring. Mer information om prestandaoptimering för Microsoft 365 finns i Nätverksplanering och [prestandajustering för Microsoft 365](https://support.office.com/article/e5f1228c-da3c-4654-bf16-d163daee8848) eller kontakta din supportgrupp.

Du kan konfigurera följande platser till satellitplatser där du kan lagra OneDrive och SharePoint och Exchange postlådor. När du planerar för multi-geo gör du en lista över de platser som du vill lägga till i Microsoft 365 klientorganisationen. Vi rekommenderar att du börjar med en eller två satellitplatser och sedan gradvis expanderar till fler geoplatser, om det behövs.

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

När du konfigurerar multi-geo bör du överväga att använda dig av möjligheten att konsolidera den lokala infrastrukturen medan du migrerar till Microsoft 365. Om du till exempel har lokala anläggningar i Singapore och Malaysia kan du konsolidera dem till APC-satellitplatsen, förutsatt att du kan göra det om du behöver datalagringsplats.

## <a name="best-practices"></a>Metodtips

Vi rekommenderar att du skapar en testanvändare i Microsoft 365 att göra några inledande tester. Vi går igenom några testnings- och verifieringssteg för den här användaren innan du fortsätter att introducera produktionsanvändare Microsoft 365 Multi-Geo.

När du har testat klart med testanvändaren väljer du en pilotgrupp – kanske från IT-avdelningen – som är först med att använda OneDrive och Exchange en ny geoplats. För den första gruppen väljer du användare som ännu inte har OneDrive. Vi rekommenderar inte fler än fem personer i den här initiala gruppen och gradvis expanderar efter en metod för batch-lansering.

Varje användare bör ha en *önskad dataplats* (PDL) inställd så att Microsoft 365 kan avgöra på vilken geoplats de ska OneDrive. Den dataplats användaren föredrar måste matcha en av de valda satellitplatserna eller den centrala platsen. Även om PDL-fältet inte är obligatoriskt, rekommenderar vi att ett PDL-fält anges för alla användare. Arbetsbelastningar för en användare utan en PDL etableras på den centrala platsen.

Skapa en lista över användarna och ta med deras huvudnamn (UPN) och platskoden för rätt önskad dataplats. Inkludera testanvändaren och den första pilotgruppen du börjar med. Du behöver den här listan för konfigurationsprocedurerna.

Om användarna synkroniseras från ett lokalt Active Directory-system till Azure Active Directory måste du ange önskad dataplats som ett Active Directory-attribut och synkronisera det med hjälp av Azure Active Directory Anslut. Du kan inte direkt konfigurera önskad dataplats för synkroniserade användare med Azure AD PowerShell. Anvisningarna för att konfigurera PDL i Active Directory och Synkronisera det behandlas Azure Active Directory Anslut synkronisering: Konfigurera önskad [dataplats för Microsoft 365 resurser](/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation).

Administrationen av en flera geoklienter kan skilja sig från en icke-geoklient, eftersom många av de SharePoint- OneDrive-inställningarna och -tjänsterna är geobaserade. Vi rekommenderar att du går [igenom Administrera en multigeomiljö](administering-a-multi-geo-environment.md) innan du fortsätter med konfigurationen.

Läs [Användarupplevelse i en geomiljö för](multi-geo-user-experience.md) flera personer om du vill ha mer information om slutanvändarmiljön i en geomiljö med flera användare.

Mer information om Teams upplevelse av ett Microsoft 365-geo innehavare finns i Teams upplevelse i ett Microsoft 365 OneDrive och SharePoint Online Multi-Geo aktiverat [innehavare.](/microsoftteams/teams-experience-o365odb-spo-multi-geo)

Information om hur du kommer Microsoft 365 multi-geo finns [i Microsoft 365 Multi-Geo.](multi-geo-tenant-configuration.md)

När du har slutfört konfigurationen ska du komma ihåg att migrera användarnas [OneDrive-bibliotek](move-onedrive-between-geo-locations.md) efter behov så att användarna kan arbeta från sina föredragna dataplatser.

## <a name="related-topics"></a>Relaterade ämnen

[Microsoft 365 Multi-Geo eDiscovery-konfiguration](./multi-geo-ediscovery-configuration.md)