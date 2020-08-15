---
title: Administrera en multi-geo-miljö
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
description: Administratörer kan läsa mer om hur du administrerar SharePoint-och OneDrive-tjänster i en multi-geo-miljö.
ms.openlocfilehash: 1b6d2cb1cb9511677f717f0e58553abc4473e1ad
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694316"
---
# <a name="administering-a-multi-geo-environment"></a>Administrera en multi-geo-miljö

Här följer en beskrivning av hur Microsoft 365-tjänster fungerar i en multi-geo-miljö.

## <a name="audit-log-search"></a>Gransknings loggs ökning

En enhetlig [Gransknings logg](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c) för alla dina satellit platser finns på Sök sidan för Microsoft 365-gransknings loggen. Du kan se alla Gransknings logg poster från fler än geo platser, till exempel & EUR-aktiviteterna visas i en kalendervy och sedan kan du använda befintliga filter för att visa specifika användares aktiviteter.

## <a name="bcs-secure-store-apps"></a>BCS, säker lagring, appar

BCS, säker lagring och alla program har separata instanser på varje satellit plats, och därför bör SharePoint Online-administratören hantera och konfigurera de här tjänsterna separat från varje satellit plats.

## <a name="ediscovery"></a>eDiscovery 

Som standard kan en eDiscovery-chef eller administratör för en multi-geo-klient leda en eDiscovery endast på den centrala platsen för denna klient organisation. Den globala administratören för Office 365 måste tilldela behörigheter för eDiscovery Manager för att tillåta andra att utföra eDiscovery och tilldela en "region"-parameter i sitt tillämpliga säkerhets filter för efterlevnad för att ange regionen för att genomföra eDiscovery som satellit plats, annars utförs ingen eDiscovery för satellit platsen. Information om hur du konfigurerar filtret för efterlevnad av inställningar för en region finns i [Konfigurera multi-geo-eDiscovery för Office 365](multi-geo-ediscovery-configuration.md).

## <a name="exchange-mailboxes"></a>Exchange-postlådor

Användares Exchange-postlådor flyttas automatiskt när deras PDL ändras. När en ny post låda skapas etableras den till användarens PDL eller på den centrala platsen om inget värde har angetts för användarens PDL.

## <a name="information-protection-ip-data-loss-prevention-dlp-policy"></a>Policy för informations skydd (IP) data förlust skydd (DLP)

Du kan ställa in dina IP DLP-principer för OneDrive för företag, SharePoint och Exchange i säkerhets-och kompatibilitetstillstånd, scope-principer som behövs för hela klient organisationen eller för tillämpliga användare. Om du till exempel vill välja en princip för en användare på en satellit plats väljer du att tillämpa principen på en viss OneDrive och ange användarens OneDrive-URL. Se [Översikt över principer för skydd mot data förlust](https://support.office.com/article/1966b2a7-d1e2-4d92-ab61-42efbb137f5e) för allmänna rikt linjer för att skapa DLP-principer.

DLP-principerna synkroniseras automatiskt baserat på deras tillämplighets för varje Geo-plats.

Att implementera principer för informations skydd och skydd mot data förlust till alla användare på en Geo-plats är inte ett tillgängligt alternativ i användar gränssnittet, i stället måste du välja de konton som gäller för principen eller tillämpa policyn globalt på alla konton.

## <a name="microsoft-flow"></a>Microsoft-flöde

Flöden som skapas för satellit platsen använder slut punkten som finns på klient organisationens standardinställning för geo.  Microsoft Flow är inte en multi-geo-tjänst. 

## <a name="microsoft-powerapps"></a>Microsoft PowerApps

PowerApps som skapats för satellit platsen använder slut punkten som finns på klient organisationens centrala plats. Microsoft PowerApps är inte en multi-geo-tjänst. 

## <a name="onedrive-administrator-experience"></a>OneDrive-administratörens upplevelse

[Administrations centret för OneDrive](https://admin.onedrive.com) har en flik för **geo platser** i det vänstra navigerings fältet med en Geo-plats karta där du kan visa och hantera dina geo-platser. Använd den här sidan om du vill lägga till eller ta bort geo-platser för din klient organisation.

## <a name="security-and-compliance-admin-center"></a>Administrations-och efterföljandekrav

Det finns ett centralt kompatibilitetstillstånd för en multi-geo-klient organisation: [Microsoft 365 Security & Compliance Center](https://protection.office.com/?rfr=AdminCenter\#/homepage).

## <a name="sharepoint-storage-quota"></a>SharePoint-lagringsenhet

Som standard delar alla geo-platser i en multi-geo-miljö den tillgängliga lagrings kvoten för innehavare.  Du kan också hantera lagrings kvoten genom att tilldela en specifik kvot för en viss Geo-plats. Mer information finns i [SharePoint-lagringslösningar i multi-geo-miljöer](sharepoint-multi-geo-storage-quota.md).

## <a name="sharing"></a>Delning

Administratörer kan ange och hantera delnings principer för var och en av deras platser. OneDrive-och SharePoint-webbplatserna på varje Geo-plats gäller endast motsvarande geo-specifika delnings inställningar. (Du kan till exempel tillåta [extern delning](https://support.office.com/article/C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85) för din centrala plats men inte för din satellit plats eller tvärtom.) Observera att delnings inställningarna inte tillåter konfigurering av delnings begränsningar mellan geo-platser.

## <a name="taxonomy"></a>Hybridtaxonomi

Vi har stöd för en enhetlig [taxonomi](https://docs.microsoft.com/sharepoint/managed-metadata) för företags hanterade metadata på Geo-platser, med att befälhavaren finns på den centrala platsen för ditt företag. Vi rekommenderar att du hanterar din globala taxonomi från den centrala platsen och bara lägger till sitespecifika termer i platsens taxonomi. Globala taxonomielement synkroniseras till satellit platserna.

Se [Hantera metadata i en multi-geo-klient organisation](https://docs.microsoft.com/sharepoint/dev/solution-guidance/multigeo-managedmetadata) för ytterligare information och råd om utvecklings utveckling.

## <a name="user-profile-application"></a>Användar profil program

Det finns ett [användar profil program](https://docs.microsoft.com/sharepoint/manage-user-profiles) på varje Geo-plats. Varje användares profil information finns på deras Geo plats och tillgänglig för administratören för den geo-platsen.

Om du har anpassade profil egenskaper rekommenderar vi att du använder samma profil schema i olika länder och fyller dina anpassade profil egenskaper på alla geo platser eller där så behövs. Vägledning för hur du fyller i användar profil data via programmering finns i [Mass uppdaterings API för profilerna](https://docs.microsoft.com/sharepoint/dev/solution-guidance/bulk-user-profile-update-api-for-sharepoint-online).

Se [arbeta med användar profiler i en multi-geo-klient organisation](https://docs.microsoft.com/sharepoint/dev/solution-guidance/multigeo-userprofileexperience) för att få mer information och för utvecklings vägledning.

## <a name="video-portal"></a>Video Portal

I en multi-geo-klient organisation är O365-videoportalen endast från standard Geo och alla användare omdirigeras till den centrala portal-URL: en. Dessutom används Remote media service (RMS) för den regionen, enligt följande baserat på din centrala plats.

Strömmen är för närvarande tillgänglig i följande regioner:

- Nord Amerika, i USA 
- Europa
- Asien Stilla havet

Strömmen är emellertid ännu inte tillgänglig i följande regioner som för närvarande stöds för Microsoft 365-Video, och därför kommer vi att använda den RMS som finns i närmaste region som stöds.

- Australien
- Kanada
- Indien
- Storbritannien

## <a name="yammer"></a>Yammer

Yammer är inte en multi-geo-arbets belastning. Yammer-trådar som lagras i Yammer placeras i innehavarens centrala plats. Yammer tar bort en ändring av fil lagrings utrymme som lagrar Yammer-filer i SharePoint. Yammer-filer som lagras i SharePoint kommer att placera SharePoint-webbplatsen kopplad till Yammer-gruppen. SharePoint-gruppwebbplatser baseras på PDL-logik enligt beskrivningen i [SharePoint-webbplatser och-grupper](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md#sharepoint-sites-and-groups).
