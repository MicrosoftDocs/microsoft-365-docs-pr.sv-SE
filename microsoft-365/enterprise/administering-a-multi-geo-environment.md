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
description: Administratörer kan läsa mer om hur de administrerar SharePoint- och OneDrive-tjänster i en geomiljö med flera platser.
ms.openlocfilehash: 213070f2f7a04e15a1e2ac3cd9a3ae697b66a718
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905606"
---
# <a name="administering-a-multi-geo-environment"></a>Administrera en Multi-Geo-Miljö

Här är en titt på hur Microsoft 365-tjänster fungerar i en miljö med flera geografiska miljöer.

## <a name="audit-log-search"></a>Granskningsloggsökning

En enhetlig [granskningslogg](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c) för alla dina satellitplatser är tillgänglig från Microsoft 365 granskningsloggsökningssidan. Du kan se alla granskningsloggposter från geoplatser, till exempel NAM & EUR-användares aktiviteter visas i en organisationsvy och sedan kan du använda befintliga filter för att se särskilda användares aktiviteter.

## <a name="bcs-secure-store-apps"></a>BCS, säker lagring, appar

BCS, Secure Store och Apps har alla separata instanser på varje satellitplats, och Därför bör SharePoint Online-administratören hantera och konfigurera de här tjänsterna separat från varje satellitplats.

## <a name="ediscovery"></a>eDiscovery 

Som standard kan en eDiscovery-hanterare eller administratör för en geoklient för flera platser endast utföra eDiscovery på den klientorganisationens centrala plats. Den globala Administratören för Office 365 måste tilldela eDiscovery Manager-behörigheter så att andra kan utföra eDiscovery och tilldela en "Region"-parameter i sitt tillämpliga säkerhetsfilter för efterlevnad för att ange området för eDiscovery som satellitplats, annars utförs ingen eDiscovery för satellitplatsen. Information om hur du konfigurerar säkerhetsfiltret för efterlevnad för en region [finns i Konfigurera Office 365 Multi-Geo eDiscovery.](multi-geo-ediscovery-configuration.md)

## <a name="exchange-mailboxes"></a>Exchange-postlådor

Användarnas Exchange-postlådor flyttas automatiskt om deras PDL ändras. När en ny postlåda skapas etableras den till användarens PDL eller till den centrala platsen om inget värde har angetts för användarens PDL.

## <a name="information-protection-ip-data-loss-prevention-dlp-policy"></a>DLP-princip (Information Protection – IP) – dataförlustskydd

Du kan ange dina IP DLP-principer för OneDrive för företag, SharePoint och Exchange i Säkerhets- och efterlevnadscenter, där principer för hela klientorganisationen eller tillämpliga användare behövs. Till exempel: Om du vill välja en princip för en användare på en satellitplats väljer du för att tillämpa principen på en specifik OneDrive och anger användarens OneDrive-URL. Allmän [vägledning för hur du skapar DLP-principer](https://support.office.com/article/1966b2a7-d1e2-4d92-ab61-42efbb137f5e) finns i Översikt över principer för dataförlustskydd.

DLP-principerna synkroniseras automatiskt utifrån deras tillämplighet på varje geoplats.

Att implementera principer för skydd mot informationsskydd och dataförlust för alla användare på en geoplats är inte ett alternativ som är tillgängligt i användargränssnittet. I stället måste du välja tillämpliga konton för principen eller tillämpa principen globalt på alla konton.

## <a name="microsoft-flow"></a>Microsoft Flow

Flöden som skapas för satellitplatsen använder ändpunkten på klientorganisationens standard geoplats.  Microsoft Flow är inte en Multi-Geo-tjänst. 

## <a name="microsoft-powerapps"></a>Microsoft PowerApps

PowerApps som skapats för satellitplatsen använder ändpunkten på den centrala platsen för klientorganisationen. Microsoft PowerApps är inte en Multi-Geo-tjänst. 

## <a name="onedrive-administrator-experience"></a>OneDrive-administratörsupplevelse

I [administrationscentret för OneDrive](https://admin.onedrive.com) finns fliken **Geoplatser** i det vänstra navigeringsfältet. I det finns en geoplatskarta där du kan visa och hantera dina geografiska platser. På den här sidan kan du lägga till eller ta bort geoplatser för klientorganisationen.

## <a name="security-and-compliance-admin-center"></a>Administrationscenter för säkerhet och efterlevnad

Det finns ett centralt efterlevnadscenter för flera geoklienter: [Microsoft 365 Säkerhets- & efterlevnadscenter.](https://protection.office.com/?rfr=AdminCenter\#/homepage)

## <a name="sharepoint-storage-quota"></a>SharePoint-lagringskvot

Som standard delar alla geoplatser i en multigeomiljö den tillgängliga lagringskvoten för klientorganisationen.  Du kan också hantera lagringskvoten genom att tilldela en viss kvot för en viss geoplats. Mer information finns i [SharePoint-lagringskvoter i geomiljöer.](sharepoint-multi-geo-storage-quota.md)

## <a name="sharing"></a>Delning

Administratörer kan ange och hantera delningsprinciper för var och en av sina platser. OneDrive- och SharePoint-webbplatserna på varje geoplats används bara för motsvarande geospecifika delningsinställningar. (Du kan till exempel tillåta [extern delning](https://support.office.com/article/C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85) för den centrala platsen, men inte för din satellitplats eller vice versa.) Observera att delningsinställningarna inte tillåter konfigurering av delningsbegränsningar mellan geografiska platser.

## <a name="taxonomy"></a>Taxonomi

Vi stöder en enhetlig [taxonomi](/sharepoint/managed-metadata) för företags hanterade metadata på geoplatser, med master på den centrala platsen för företaget. Vi rekommenderar att du hanterar din globala taxonomi från den centrala platsen och bara lägger till platsspecifika termer i satellitplatsens taxonomi. Globala taxonomivillkor synkroniseras till satellitplatserna.

Mer [information och utvecklarvägledning finns i Hantera metadata](/sharepoint/dev/solution-guidance/multigeo-managedmetadata) i en flera geoklienter.

## <a name="user-profile-application"></a>Programmet Användarprofil

Det finns ett [användarprofilprogram](/sharepoint/manage-user-profiles) på varje geoplats. Profilinformationen för varje användare lagras på användarens geoplats och är tillgänglig för administratören för den geoplatsen.

Om du har anpassade profilegenskaper rekommenderar vi att du använder samma profilschema över geografiska områden och fyller i dina anpassade profilegenskaper antingen på alla geoplatser eller där det behövs. Anvisningar om hur du fyller i användarprofildata programmässigt finns i Api:t för uppdatering av [massanvändareprofiler.](/sharepoint/dev/solution-guidance/bulk-user-profile-update-api-for-sharepoint-online)

Mer [information och utvecklarvägledning finns i Arbeta](/sharepoint/dev/solution-guidance/multigeo-userprofileexperience) med användarprofiler i en multigeoklientorganisation.

## <a name="video-portal"></a>Videoportal

I en multigeoklientorganisation används O365-videoportalen endast från standard geo, och alla användare omdirigeras till url:en till den centrala portalen. Remote Media Service (RMS) för det området kommer därför att användas, enligt följande baserat på din centrala plats.

Stream är för närvarande tillgängligt i följande regioner:

- Nordamerika, med USA som värd 
- Europa
- Asien och Stilla havet

Stream är dock ännu inte tillgängligt i följande regioner som stöds för Microsoft 365 Video, och därför använder vi den RMS som är i den region som ligger närmast stödd för dessa lokala instanser.

- Australien
- Kanada
- Indien
- Storbritannien

## <a name="yammer"></a>Yammer

Yammer är inte en geonivåarbetsbelastning. De Yammer-trådar som lagras i Yammer placeras på klientorganisationens centrala plats. Yammer rullnings en ändring för fillagring som kommer att lagra Yammer-filer i SharePoint. Yammer-filer som lagras i SharePoint placeras på SharePoint-webbplatsen som är kopplad till Yammer-gruppen. SharePoint-gruppwebbplatser baseras på PDL-logik enligt Beskrivning i [SharePoint-webbplatser och -grupper.](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md#sharepoint-sites-and-groups)