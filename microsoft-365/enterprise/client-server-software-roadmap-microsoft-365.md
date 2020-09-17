---
title: Klient-och Server program översikt för Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/10/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom: it-pro
description: Översikten för konfiguration av klient-och serverprogram för Microsoft 365.
ms.openlocfilehash: 898464222b8296cee3ab12fe7351295f39a23736
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950574"
---
# <a name="client-and-server-software-roadmap-for-microsoft-365"></a>Klient-och Server program översikt för Microsoft 365

De flesta företag och organisationer har en heterogen miljö med flera versioner av operativsystem, klientprogramvara och serverprogram. Microsoft 365 för Enterprise innehåller de säkraste versionerna av dessa viktigaste komponenter i IT-infrastrukturen med produktivitets funktioner som är avsedda att utnyttja moln teknologier.

Om du vill maximera företags värdet för Microsoft 365 för Enterprise-integrerad produkt serie kan du börja planera och implementera en strategi för att migrera utgåvor av:

- Office-klienten som är installerad på dina datorer till Microsoft 365-applikationer för företag
- Office-servrar som är installerade på dina servrar till motsvarande tjänster i Microsoft 365
- Windows 7 och Windows 8.1 på dina enheter till Windows 10 Enterprise

>[!Note]
>Windows 7 upphörde med sin support den **14 januari 2020**. Mer information finns [här](https://support.microsoft.com/help/4057281/windows-7-support-will-end-on-january-14-2020).
>

Om du genomför de här migreringarna över tiden får organisationen närmare den [moderna arbets platsen](https://www.microsoft.com/microsoft-365/blog/2018/04/27/making-it-simpler-with-a-modern-workplace/), en säker och integrerad miljö som låser upp samarbete och kreativitet i organisationen, vilka alla är aktiverade och har stöd för Microsoft 365 för företag.

## <a name="migration-for-microsoft-office-client-products"></a>Migrering av Microsoft Office-klientprodukter

Oavsett om din organisation är stor eller liten, kanske du använder en kombination av äldre versioner av Office-klientprodukter, t.ex. Word, Excel och PowerPoint. Dessa äldre versioner:

- Kan [uppdateras](https://support.office.com/article/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5) med de senaste säkerhetsuppdateringarna och supportkorrigeringarna, men processen är ibland manuell och kan kanske inte skalas i hela organisationen.
- Har inte anpassats optimalt till att använda Microsofts molntekniker som hjälper dig att transformera din verksamhet digitalt.
- Innehåller inga nya funktioner.

Microsoft 365 för Enterprise innehåller Microsoft 365-appar för företag, en version av Office-klientprodukter som är tillgängliga med en Microsoft-365 för företag-licens och är installerad och uppdateras från Microsoft Cloud. Microsoft 365-applikationer för företag innehåller säkerhetsuppdateringar och de senaste funktionerna. Mer information finns i [Om Microsoft 365-applikationer för företag](https://docs.microsoft.com/deployoffice/about-microsoft-365-apps).

### <a name="office-2007"></a>Office 2007

För Office 2007-versioner har supporten redan upphört. Mer information finns i [Supporten för Office 2007 upphör](https://docs.microsoft.com/deployoffice/office-2007-end-support-roadmap).

I stället för att uppgradera datorer som kör Office 2007 med Office 2010, Office 2013 eller Office 2016, kan du:

1. Skaffa och tilldela en Microsoft 365-licens till dina användare.
2. Avinstallera Office 2007 på deras datorer.
3. Installera Microsoft 365-applikationer för företag, antingen separat eller tillsammans med en IT-distribution. Mer information finns i [distributions guide för Microsoft 365-appar](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps).

Microsoft 365-applikationer för företag installerar uppdateringar automatiskt och använder molnbaserade tjänster för förbättrad säkerhet och produktivitet.

### <a name="office-2010"></a>Office 2010

För Office 2010-versioner upphör supporten **13 oktober 2020**. Mer information finns i [Supporten för Office 2010 upphör](https://docs.microsoft.com/deployoffice/office-2010-end-support-roadmap).

I stället för att uppgradera datorerna som kör Office 2010 med Office 2013 eller Office 2016, där båda måste uppdateras manuellt, kan du:

1. Skaffa och tilldela en Microsoft 365-licens till dina användare.
2. Avinstallera Office 2010 på deras datorer.
3. Installera Microsoft 365-applikationer för företag, antingen separat eller tillsammans med en IT-distribution. Mer information finns i [distributions guide för Microsoft 365-appar](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps).

Microsoft 365-applikationer för företag installerar både säkerhetsuppdateringar och nya funktionsuppdateringar automatiskt och använder molnbaserade tjänster i Microsoft 365 för förbättrad säkerhet och produktivitet.

### <a name="office-2013-and-office-2016"></a>Office 2013 och Office 2016 

Det har ännu inte fastställts när supporten för Office 2013- och Office 2016-versionerna upphör. I likhet med Office 2010 måste du dock fortfarande [installera säkerhetsuppdateringar](https://support.office.com/article/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5), vilka kanske inte kan anpassas efter storleken på din organisation.

I stället för att fortsätta att uppdatera datorerna med de senaste säkerhetsuppdateringarna för Office 2013 eller Office 2016, eller uppdatera datorerna från Office 2013 till Office 2016, kan du:

1. Skaffa och tilldela en Microsoft 365-licens till dina användare.
2. Avinstallera Office 2013 eller Office 2016 på deras datorer.
3. Installera Microsoft 365-applikationer för företag, antingen separat eller tillsammans med en IT-distribution. Mer information finns i [distributions guide för Microsoft 365-appar](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps).

Microsoft 365-applikationer för företag installerar både säkerhetsuppdateringar och nya funktionsuppdateringar automatiskt och använder molnbaserade tjänster i Microsoft 365 för förbättrad säkerhet och produktivitet.

## <a name="migration-for-microsoft-office-server-products"></a>Migrering för Microsoft Office-serverprodukter

Oavsett om din organisation är stor eller liten, kanske du använder en kombination av äldre versioner av Office-serverprodukter, t.ex. Exchange Server och SharePoint Server. Dessa äldre versioner:

- Bör uppdateras med de senaste säkerhetsuppdateringarna och supportkorrigeringarna. I vissa fall släpps sådana uppdateringar varje månad.
- Har inte anpassats optimalt till att använda Microsofts molntekniker som hjälper dig att transformera din verksamhet digitalt.
- Innehåller inte nya produktivitetsprogram, t.ex. Microsoft Teams.
- Innehåller inte de senaste säkerhetsfunktionerna, till exempel Advanced Threat Protection i Exchange.

Microsoft 365 för Enterprise innehåller molnbaserade versioner av Office Server-tjänster som använder vissa av de verktyg som lokala versioner av Office Server-program, till exempel webbläsare och Outlook-klienten. Tjänsternas säkerhet uppdateras ständigt utan att IT-avdelningen behöver agera, vilket sparar tid när lokala servrar ska underhållas och uppdateras. Tjänsterna har också nya funktionsförbättringar som inte finns i Office-serverprogrammen.

Information om hur du migrerar användare och data för specifika Microsoft 365-arbets belastningar:

- Användar post lådor från Exchange Server till Exchange Online, se [Flytta post lådor mellan lokala och Exchange Online-organisationer](https://docs.microsoft.com/exchange/hybrid-deployment/move-mailboxes).
- SharePoint-data från SharePoint Server till SharePoint Online läser du [migrera innehållet till Microsoft 365](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online).
- Skype för företag – Online till Microsoft Teams, se [rikt linjer för migrering och interoperabilitet](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).

### <a name="office-server-2007"></a>Office-server 2007

För serverprodukter i Office 2007-versionen har supporten redan upphört. Mer information finns i följande artiklar:

- [Översikt över supporten som upphör för Exchange 2007](exchange-2007-end-of-support.md)
- [Översikt över supporten som upphör för SharePoint Server 2007](sharepoint-2007-end-of-support.md)
- [Översikt över supporten som upphör för Project Server 2007](project-server-2007-end-of-support.md)
- [Översikt över supporten som upphör för Office Communications-server](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/upgrade)
- [Översikt över supporten som upphör för PerformancePoint Server 2007](pps-2007-end-of-support.md)

I stället för att uppgradera dina serverprodukter i Office 2007-versionen med serverprodukter i Office 2010, Office 2013 eller Office 2016 kan du:

1. Migrera data på dina Office 2007-servrar till Microsoft 365. Om du behöver hjälp med detta kontaktar du en Microsoft-partner.
2. Distribuera de nya funktionerna och arbetsprocesserna till användarna.
3. När du inte längre behöver någon lokal server som kör Office 2007-serverprodukter, kan du inaktivera den.

### <a name="office-server-2010"></a>Office-server 2010

Upphörande av support för [Exchange Server 2010](exchange-2010-end-of-support.md) är **13 oktober 2020**.

Upphörande av support för [SharePoint Server 2010](upgrade-from-sharepoint-2010.md) är **13 april 2021**.

I stället för att uppgradera dessa serverprodukter i Office 2010-versionen med serverprodukter i Office 2013 eller Office 2016, kan du:

1. Migrera data på Office 2010-servrar till Microsoft 365. Om du behöver hjälp med detta kan du läsa [FastTrack för Microsoft 365](https://fasttrack.microsoft.com/microsoft365), eller kontakta en Microsoft-partner.
2. Distribuera de nya funktionerna och arbetsprocesserna till användarna.
3. När du inte längre behöver någon lokal server som kör Office 2010-serverprodukter, kan du inaktivera den.

### <a name="office-server-2013"></a>Office-server 2013

Det har ännu inte fastställts när supporten upphör för serverprodukter i Office 2013-versionen. I stället för att uppgradera dina serverprodukter i Office 2013-versionen med serverprodukter i Office 2016, kan du:

1. Migrera data på dina Office 2013-servrar till Microsoft 365. Om du behöver hjälp med detta kan du läsa [FastTrack för Microsoft 365](https://fasttrack.microsoft.com/microsoft365), eller kontakta en Microsoft-partner.
2. Distribuera de nya funktionerna och arbetsprocesserna till användarna.
3. När du inte längre behöver någon lokal server som kör Office 2013-serverprodukter, kan du inaktivera den.

### <a name="office-server-2016"></a>Office-server 2016

Det har ännu inte fastställts när supporten upphör för serverprodukter i Office 2016-versionen. Om du vill använda den molnbaserade tjänsten och förbättringarna för att transformera ditt företag digitalt, kan du:

1. Migrera data på dina Office 2016-servrar till Microsoft 365. Om du behöver hjälp med detta kan du läsa [FastTrack för Microsoft 365](https://fasttrack.microsoft.com/microsoft365), eller kontakta en Microsoft-partner.
2. Distribuera de nya funktionerna och arbetsprocesserna till användarna.
3. När du inte längre behöver någon lokal server som kör Office 2016-serverprodukter, kan du inaktivera den.

## <a name="migration-for-microsoft-windows-7-and-81"></a>Migrering för Microsoft Windows 7 och 8.1

Windows 7 upphörde med sin support den **14 januari 2020**. Om du vill migrera enheter som kör Windows 7 eller Windows 8.1 kan du utföra en på-plats-uppgradering.

Fler metoder finns i [Distributionsscenarier för Windows 10](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios). Du kan också [planera för distribution av Windows 10](https://aka.ms/planforwin10deployment) på egen hand.

## <a name="summary-of-options-for-office-2010-clients-and-servers-and-windows-7"></a>Sammanfattning av alternativ för Office 2010-klienter/servrar och Windows 7

En visuell sammanfattning av alternativen att uppgradera, migrera och flytta till molnet för dessa produkter finns på [affischen supportens upphörande](../downloads/Office2010Windows7EndOfSupport.pdf).

[![Bild på affischen för supportens upphörande för Office 2010-klienter/servrar och Windows 7](../media/microsoft-365-overview/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

Den här miniatyren med en sida är ett snabbt sätt att förstå olika sökvägar som du kan vidta för att förhindra att Office 2010-klient-och serverprodukter och Windows 7 når supporten, med önskade sökvägar och resulterande destinations stöd i Microsoft 365 för företag markerat.

Du kan också [ladda ner denna affisch](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) och skriva ut den i formaten Letter, Legal och Tabloid (11 x 17).

## <a name="transition-your-entire-organization"></a>En övergång för hela organisationen

Om du vill få en bättre bild av hur du kan flytta hela organisationen till produkterna och tjänsterna i Microsoft 365 för företag kan du studera [övergångsaffischen](../downloads/transition-org-to-m365.pdf).

[![Bild på affischen för övergång till Microsoft 365](../media/microsoft-365-overview/transition-org-to-m365.png)](../downloads/transition-org-to-m365.pdf)

Med den här affischen på två sidor kan du snabbt inventera din befintliga infrastruktur och få vägledning i hur du flyttar till motsvarande produkt eller tjänst i Microsoft 365 för företag. Den innehåller Windows- och Office-produkter samt andra infrastruktur- och säkerhetselement, som exempelvis enhetshantering, identitet, information och skydd mot hot.

Du kan också [ladda ner denna affisch](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/transition-org-to-m365.pdf) och skriva ut den i formaten Letter, Legal och Tabloid (11 x 17).

## <a name="how-microsoft-does-microsoft-365-for-enterprise"></a>Så här fungerar Microsoft 365 för företag

Se hur IT-experter på Microsoft migrerade företaget till Microsoft 365 för företag med dessa resurser:

- [Distribuera och uppdatera Microsoft 365-appar för företag](https://www.microsoft.com/itshowcase/Article/Content/757/Deploying-and-updating-Microsoft-Office-365-ProPlus)
- [Microsoft migrerar 150 000 postlådor till Exchange Online](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)
- [SharePoint till molnet: Se hur Microsoft har utfört sin egen migrering](https://www.microsoft.com/itshowcase/Article/Content/691/SharePoint-to-the-cloud-Learn-how-Microsoft-ran-its-own-migration)
- [Distribution av Windows 10 på Microsoft som en på-plats-uppgradering](https://www.microsoft.com/itshowcase/Article/Content/668/Deploying-Windows-10-at-Microsoft-as-an-inplace-upgrade)
- [Distribution av Windows 10: Tips och tricks från Microsoft IT](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT) (video)
