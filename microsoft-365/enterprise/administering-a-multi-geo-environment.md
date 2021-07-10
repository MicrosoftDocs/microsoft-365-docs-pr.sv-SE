---
title: Administrera en Multi-Geo-Miljö
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
description: Administratörer kan läsa mer om hur man SharePoint och OneDrive tjänster i en miljö med flera platser.
ms.openlocfilehash: 4c5215b855b8ca1840035b39fcfbddde419c13d8
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362324"
---
# <a name="administering-a-multi-geo-environment"></a>Administrera en Multi-Geo-Miljö

Här är en titt på hur Microsoft 365 fungerar i en geomiljö med flera tjänster.

## <a name="administrator-experience"></a>Administratörsupplevelse

I [SharePoint finns](https://admin.microsoft.com/sharepoint) fliken Geoplatser i det vänstra **navigeringsfältet.** I administrationscentret finns en geoplatskarta där du kan visa och hantera dina geografiska platser. På den här sidan kan du lägga till eller ta bort geoplatser för klientorganisationen.

## <a name="audit-log-search"></a>Granskningsloggsökning

En enhetlig [granskningslogg](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c) för alla dina satellitplatser är tillgänglig från Microsoft 365 för granskningsloggsökning. Du kan se alla granskningsloggposter från geoplatser, till exempel NAM & EUR-användares aktiviteter visas i en organisationsvy och sedan kan du använda befintliga filter för att se särskilda användares aktiviteter.

## <a name="bcs-secure-store-apps"></a>BCS, säker lagring, appar

BCS, Secure Store och Apps har alla separata instanser på varje satellitplats, och därför bör SharePoint Online-administratören hantera och konfigurera de här tjänsterna separat från varje satellitplats.

## <a name="compliance-admin-center"></a>Administrationscenter för efterlevnad

Det finns ett centralt efterlevnadscenter för en fler geoklient: [administrationscentret Microsoft 365 efterlevnad.](https://compliance.microsoft.com/)

## <a name="ediscovery"></a>eDiscovery

Som standard kan en eDiscovery-hanterare eller administratör för en geoklient för flera platser endast utföra eDiscovery på den klientorganisationens centrala plats. Den globala Office 365-administratören måste tilldela eDiscovery Manager-behörigheter så att andra kan utföra eDiscovery och tilldela en "Region"-parameter i sitt tillämpliga säkerhetsfilter för efterlevnad för att ange området för eDiscovery som satellitplats, annars utförs ingen eDiscovery för satellitplatsen. Information om hur du konfigurerar efterlevnadssäkerhetsfiltret för en region [finns i Office 365 för multi-geo eDiscovery.](multi-geo-ediscovery-configuration.md)

## <a name="exchange-mailboxes"></a>Exchange postlådor

Användarnas Exchange postlådor flyttas automatiskt om deras PDL ändras. När en ny postlåda skapas etableras den till användarens PDL eller till den centrala platsen om inget värde har angetts för användarens PDL.

## <a name="information-protection-ip-data-loss-prevention-dlp-policy"></a>DLP-princip (Information Protection – IP) – dataförlustskydd

Du kan ange dina IP DLP-principer för OneDrive för företag, SharePoint och Exchange i säkerhets- och efterlevnadscentret, och fastställa principer efter behov för hela klientorganisationen eller för tillämpliga användare. Till exempel: Om du vill välja en princip för en användare på en satellitplats väljer du att tillämpa principen på ett specifikt OneDrive och anger användarens webbadress OneDrive. Allmän [vägledning för hur du skapar DLP-principer](https://support.office.com/article/1966b2a7-d1e2-4d92-ab61-42efbb137f5e) finns i Översikt över principer för dataförlustskydd.

DLP-principerna synkroniseras automatiskt utifrån deras tillämplighet på varje geoplats.

Att implementera principer för skydd mot informationsskydd och dataförlust för alla användare på en geoplats är inte ett alternativ som är tillgängligt i användargränssnittet. I stället måste du välja tillämpliga konton för principen eller tillämpa principen globalt på alla konton.

## <a name="microsoft-powerapps"></a>Microsoft PowerApps

PowerApps som skapats för satellitplatsen använder ändpunkten på den centrala platsen för klientorganisationen. Microsoft PowerApps är inte en Multi-Geo-tjänst. 

## <a name="power-automate"></a>Power Automate

Flöden som skapas för satellitplatsen använder ändpunkten på klientorganisationens standard geoplats.  Power Automate är inte en Multi-Geo-tjänst. 

## <a name="sharepoint-storage-quota"></a>SharePoint lagringskvot

Som standard delar alla geoplatser i en multigeomiljö den tillgängliga lagringskvoten för klientorganisationen.  Du kan också hantera lagringskvoten genom att tilldela en viss kvot för en viss geoplats. Mer information finns i [SharePoint för flera geografiska miljöer.](sharepoint-multi-geo-storage-quota.md)

## <a name="sharing"></a>Delning

Administratörer kan ange och hantera delningsprinciper för var och en av sina platser. I OneDrive och SharePoint-webbplatserna på varje geoplats används bara motsvarande geospecifika delningsinställningar. (Du kan till exempel tillåta [extern delning](https://support.office.com/article/C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85) för den centrala platsen, men inte för din satellitplats eller vice versa.) Observera att delningsinställningarna inte tillåter konfigurering av delningsbegränsningar mellan geografiska platser.

## <a name="stream"></a>Stream

Videor som laddas upp till Stream lagras i OneDrive för den person som laddar upp. Mötesinspelningar lagras i OneDrive för alla deltagare som spelar in mötet.

## <a name="taxonomy"></a>Taxonomi

Vi stöder en enhetlig [taxonomi](/sharepoint/managed-metadata) för företags hanterade metadata på geoplatser, med master på den centrala platsen för företaget. Vi rekommenderar att du hanterar din globala taxonomi från den centrala platsen och bara lägger till platsspecifika termer i satellitplatsens taxonomi. Globala taxonomivillkor synkroniseras till satellitplatserna.

Mer [information och utvecklarvägledning finns i Hantera metadata](/sharepoint/dev/solution-guidance/multigeo-managedmetadata) i en flera geoklienter.

## <a name="user-profile-application"></a>Programmet Användarprofil

Det finns ett [användarprofilprogram](/sharepoint/manage-user-profiles) på varje geoplats. Profilinformationen för varje användare lagras på användarens geoplats och är tillgänglig för administratören för den geoplatsen.

Om du har anpassade profilegenskaper rekommenderar vi att du använder samma profilschema över geografiska områden och fyller i dina anpassade profilegenskaper antingen på alla geoplatser eller där det behövs. Anvisningar om hur du fyller i användarprofildata programmässigt finns i Api:t för uppdatering av [massanvändareprofiler.](/sharepoint/dev/solution-guidance/bulk-user-profile-update-api-for-sharepoint-online)

Mer [information och utvecklarvägledning finns i Arbeta](/sharepoint/dev/solution-guidance/multigeo-userprofileexperience) med användarprofiler i en multigeoklientorganisation.

## <a name="yammer"></a>Yammer

Yammer är inte en Multi-Geo-arbetsbörda. Yammer tråd som lagras Yammer på klientorganisationens centrala plats. Yammer distribuerar en ändring av fillagring som lagrar filer Yammer i SharePoint. Yammer filer som lagras SharePoint i gruppen placeras SharePoint webbplats som är kopplad Yammer gruppen. SharePoint gruppwebbplatser baseras på PDL-logik enligt beskrivningen SharePoint [Webbplatser och grupper](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md#sharepoint-sites-and-groups).