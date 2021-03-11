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
description: Läs mer om Microsoft 365 Multi-Geo, hur multi-geo fungerar och vilka geoplatser som är tillgängliga för datalagring.
ms.openlocfilehash: ce8b752cc6a335249f9d8e03289fd16b04756ce9
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/10/2021
ms.locfileid: "50712348"
---
# <a name="plan-for-microsoft-365-multi-geo"></a>Planera för Microsoft 365 Multi-Geo

Den här vägledningen är utformad för administratörer för multinationella företag som förbereder sin Microsoft 365-klientorganisation för att expanderas till ytterligare geografiska områden i enlighet med företagets närvaro för att uppfylla kraven för datalagring.

I en multi-geokonfiguration består Microsoft 365-innehavaren av en central plats och en eller flera satellitplatser. Det här är en enda klientorganisation som spänner över flera geografiska platser. Information om klientorganisationen, inklusive geoplatser, finns i Azure Active Directory (Azure AD).

Här är några viktiga multigeotermer som hjälper dig att förstå de grundläggande begreppen i konfigurationen:

-   **Klientorganisation** – en organisations representation i Microsoft 365 som normalt har en eller flera domäner kopplade till sig (till https://contoso.sharepoint.com) exempel. 

-   **Geoplatser – De** geografiska platser som är tillgängliga för datavärden i en Microsoft 365-klientorganisation.

-   **Satellitplatser –** De ytterligare geoplatser som du har konfigurerat för att lagra data i Microsoft 365-klienten. Flera geoklienter sträcker sig över mer än en geoplats, till exempel Nordamerika och Europa.

-   **Önskad dataplats (PDL)** – Den geografiska plats där en enskild användares Exchange- och OneDrive-data lagras. Det här kan ställas in av administratören på någon av de geoplatser som har konfigurerats för klientorganisationen. Observera att om du ändrar PDF-adresserna för en användare som redan har en OneDrive-webbplats flyttas inte deras OneDrive-data till den nya geografiska platsen automatiskt. Mer information [finns i Flytta ett OneDrive-bibliotek till](move-onedrive-between-geo-locations.md) en annan geoplats. Om postlådan har en Exchange-postlåda flyttas den automatiskt till den nya önskade dataplatsen.

Aktivering av Multi-Geo kräver fyra viktiga steg:

1.  Arbeta med ditt kontoteam och lägg till _Multi-Geo Capabilities i Microsoft 365-tjänstabonnemanget._

2.  Välj önskad satellitplats och lägg till dem i klientorganisationen.

3.  Ställ in användarnas föredragna dataplats till önskad satellitplats. När en ny OneDrive-webbplats eller Exchange-postlåda etableras för en användare etableras den till användarens PDA-fil.

4.  Migrera användarnas befintliga OneDrive-webbplatser från den centrala platsen till deras önskade dataplats efter behov. (Exchange-postlådor migreras automatiskt när du anger en användares PDL.)

Mer [information om dessa steg finns i Konfigurera Microsoft 365 Multi-Geo.](multi-geo-tenant-configuration.md)

> [!IMPORTANT]
> Observera att Microsoft 365 Multi-Geo inte är utformat för prestandaoptimering, utan har utformats för att uppfylla krav på datalagring. Mer information om prestandaoptimering för Microsoft 365 finns i Nätverksplanering och prestandajustering för [Microsoft 365](https://support.office.com/article/e5f1228c-da3c-4654-bf16-d163daee8848) eller kontakta din supportgrupp.

Du kan konfigurera följande platser till satellitplatser där du kan lagra OneDrive- och SharePoint-webbplatser och Exchange-postlådor. Gör en lista över platser som du vill lägga till i Microsoft 365-klientorganisationen när du planerar för flera platser. Vi rekommenderar att du börjar med en eller två satellitplatser och gradvis utökar till fler geoplatser om det behövs.

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

När du konfigurerar multi-geo bör du överväga att använda dig av möjligheten att konsolidera den lokala infrastrukturen under migreringen till Microsoft 365. Om du till exempel har lokala anläggningar i Singapore och Malaysia kan du konsolidera dem till APC-satellitplatsen, förutsatt att du kan göra det med krav på datalagring.

## <a name="best-practices"></a>Metodtips

Vi rekommenderar att du skapar en testanvändare i Microsoft 365 för att göra några inledande tester. Vi går igenom några testnings- och verifieringssteg med den här användaren innan du fortsätter att introducera produktionsanvändare i Microsoft 365 Multi-Geo.

När testanvändaren är klar med testningen väljer du en pilotgrupp – kanske från IT-avdelningen – för att vara först med att använda OneDrive och Exchange på en ny geoplats. I den här första gruppen väljer du användare som ännu inte har en OneDrive. Vi rekommenderar inte fler än fem personer i den här initiala gruppen och expanderar gradvis efter en metod för batch-lansering.

Varje användare bör ha en *önskad dataplats* (PDL) inställd så att Microsoft 365 kan avgöra på vilken geoplats de ska tillhandahålla OneDrive på. Den dataplats användaren föredrar måste matcha en av dina valda satellitplatser eller den centrala platsen. Även om PDL-fältet inte är obligatoriskt rekommenderar vi att ett PDF-dokument anges för alla användare. Arbetsbelastningar för en användare utan PDA-adress etableras på den centrala platsen.

Skapa en lista över användarna och ta med deras huvudnamn (UPN) och platskoden för rätt önskad dataplats. Ta med testanvändaren och den första pilotgruppen att börja med. Du behöver den här listan för konfigurationsprocedurerna.

Om användarna synkroniseras från ett lokalt Active Directory-system till Azure Active Directory måste du ange önskad dataplats som ett Active Directory-attribut och synkronisera det med hjälp av Azure Active Directory Connect. Du kan inte direkt konfigurera önskad dataplats för synkroniserade användare med hjälp av Azure AD PowerShell. Stegen för att konfigurera PDF-filer i Active Directory och synkronisera det tas upp i [Azure Active Directory Connect-synkroniseringen: Konfigurera önskad dataplats för Microsoft 365-resurser.](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation)

Administrationen av en flera geoklienter kan skilja sig från en icke-geoklientorganisation, eftersom många av SharePoint- och OneDrive-inställningarna och -tjänsterna är multigeobaserade. Vi rekommenderar att du granskar [Administrera en miljö med flera geoinställningar](administering-a-multi-geo-environment.md) innan du fortsätter med konfigurationen.

Läs [användarupplevelsen i en geomiljö med flera](multi-geo-user-experience.md) miljöer för mer information om slutanvändarna i en miljö med flera geodata.

Mer information om Teams-upplevelsen i en Microsoft 365 Multi-Geo-innehavare finns i Teams-upplevelsen i ett [Microsoft 365 OneDrive- och SharePoint Online Multi-Geo-aktiverat innehavare.](https://docs.microsoft.com/microsoftteams/teams-experience-o365odb-spo-multi-geo)

Information om hur du konfigurerar Microsoft 365 Multi-Geo finns i [Konfigurera Microsoft 365 Multi-Geo.](multi-geo-tenant-configuration.md)

När du har slutfört konfigurationen bör du komma ihåg att migrera användarnas [OneDrive-bibliotek](move-onedrive-between-geo-locations.md) efter behov så att användarna kan arbeta från sina föredragna dataplatser.

## <a name="related-topics"></a>Relaterade ämnen

[Microsoft 365 Multi-Geo eDiscovery-konfiguration](https://docs.microsoft.com/microsoft-365/enterprise/multi-geo-ediscovery-configuration)
