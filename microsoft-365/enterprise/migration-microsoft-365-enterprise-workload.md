---
title: Migrering till Microsoft 365 Enterprise
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Gå igenom processen att migrera versioner av Microsoft Office, Office-servrar och Windows till Microsoft 365 Enterprise för hela organisationen.
ms.openlocfilehash: 9fd35e4595b19d5ddd3db0f64ea7dedf303d6818
ms.sourcegitcommit: dbbdeca5a6cd048e1bde9e820a8b8a0d6022c7a2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/14/2020
ms.locfileid: "43504059"
---
# <a name="migration-to-microsoft-365-enterprise"></a>Migrering till Microsoft 365 Enterprise

De flesta företag och organisationer har en heterogen miljö med flera versioner av operativsystem, klientprogramvara och serverprogram. Microsoft 365 Enterprise innehåller de säkraste versionerna av dessa nyckelkomponenter i IT-infrastrukturen, med produktivitetsfunktioner som är utformade för att dra nytta av molntekniken.

Om du vill maximera affärsvärdet för Microsoft 365 Enterprise integrerade utbud av produkter, kan du börja planera och implementera en strategi för att migrera versioner av:

- Office-klienten som är installerad på dina datorer till Office 365 ProPlus
- Office-servrar som är installerade på servrarna till motsvarande tjänster i Office 365
- Windows 7 och Windows 8.1 på dina enheter till Windows 10 Enterprise

>[!Note]
>Windows 7 upphörde med sin support den **14 januari 2020**. Mer information finns [här](https://support.microsoft.com/help/4057281/windows-7-support-will-end-on-january-14-2020).
>

Om du gör alla dessa migreringar över tid kommer din organisation närmare en [modern arbetsplats](https://www.microsoft.com/microsoft-365/blog/2018/04/27/making-it-simpler-with-a-modern-workplace/) samt en säker och integrerad miljö som frigör samarbete och kreativitet i organisationen, vilket är möjligt med Microsoft 365 Enterprise. 

Information om hur du migrerar användare och data för vissa Office 365-arbetsbelastningar:

- Information om användarpostlådor från Exchange Server till Exchange Online finns i [Arbetsbelastning för Exchange Online](exchangeonline-workload.md).
- Information om SharePoint-data från SharePoint Server till SharePoint Online finns i [Arbetsbelastning för SharePoint Online](sharepoint-online-onedrive-workload.md).
- Information om Skype för företag – Online till Microsoft Teams finns i [Arbetsbelastning för Microsoft Teams](teams-workload.md).

## <a name="migration-for-microsoft-office-client-products"></a>Migrering av Microsoft Office-klientprodukter

Oavsett om din organisation är stor eller liten, kanske du använder en kombination av äldre versioner av Office-klientprodukter, t.ex. Word, Excel och PowerPoint. Dessa äldre versioner:

- Kan [uppdateras](https://support.office.com/article/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5) med de senaste säkerhetsuppdateringarna och supportkorrigeringarna, men processen är ibland manuell och kan kanske inte skalas i hela organisationen.
- Har inte anpassats optimalt till att använda Microsofts molntekniker som hjälper dig att transformera din verksamhet digitalt.
- Innehåller inga nya funktioner.
 
Microsoft 365 Enterprise innehåller Office 365 ProPlus, en version av Office-klientprodukter som är tillgängliga med en Microsoft 365 Enterprise-licens och installeras och uppdateras från Microsoft Cloud. Office 365 ProPlus innehåller säkerhetsuppdateringar och de senaste funktionerna. Se [Om Office 365 ProPlus i företaget](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise) för mer information.

### <a name="office-2007"></a>Office 2007

För Office 2007-versioner har supporten redan upphört. Mer information finns i [Supporten för Office 2007 upphör](https://docs.microsoft.com/deployoffice/office-2007-end-support-roadmap).

I stället för att uppgradera datorer som kör Office 2007 med Office 2010, Office 2013 eller Office 2016, kan du:

1. Skaffa och tilldela en Microsoft 365-licens till dina användare.
2. Avinstallera Office 2007 på deras datorer.
3. Installera Office 365 ProPlus, antingen separat eller tillsammans med en IT-distribution. Mer information finns i [Fas 4: Office 365 ProPlus](office365proplus-infrastructure.md).

Office 365 ProPlus installerar uppdateringar automatiskt och kan använda molnbaserade tjänster i Office 365 för förbättrad säkerhet och produktivitet.

### <a name="office-2010"></a>Office 2010

För Office 2010-versioner upphör supporten **13 oktober 2020**. Mer information finns i [Supporten för Office 2010 upphör](https://docs.microsoft.com/deployoffice/office-2010-end-support-roadmap).

I stället för att uppgradera datorerna som kör Office 2010 med Office 2013 eller Office 2016, där båda måste uppdateras manuellt, kan du: 

1. Skaffa och tilldela en Microsoft 365-licens till dina användare.
2. Avinstallera Office 2010 på deras datorer.
3. Installera Office 365 ProPlus, antingen separat eller tillsammans med en IT-distribution. Mer information finns i [Fas 4: Office 365 ProPlus](office365proplus-infrastructure.md).

Office 365 ProPlus installerar både säkerhetsuppdateringar och nya funktionsuppdateringar automatiskt och använder molnbaserade tjänster i Microsoft 365 för förbättrad säkerhet och produktivitet.

### <a name="office-2013-and-office-2016"></a>Office 2013 och Office 2016 

Det har ännu inte fastställts när supporten för Office 2013- och Office 2016-versionerna upphör. I likhet med Office 2010 måste du dock fortfarande [installera säkerhetsuppdateringar](https://support.office.com/article/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5), vilka kanske inte kan anpassas efter storleken på din organisation.

I stället för att fortsätta att uppdatera datorerna med de senaste säkerhetsuppdateringarna för Office 2013 eller Office 2016, eller uppdatera datorerna från Office 2013 till Office 2016, kan du:

1. Skaffa och tilldela en Microsoft 365-licens till dina användare.
2. Avinstallera Office 2013 eller Office 2016 på deras datorer.
3. Installera Office 365 ProPlus, antingen separat eller tillsammans med en IT-distribution. Mer information finns i [Fas 4: Office 365 ProPlus](office365proplus-infrastructure.md).

Office 365 ProPlus installerar både säkerhetsuppdateringar och nya funktionsuppdateringar automatiskt och använder molnbaserade tjänster i Microsoft 365 för förbättrad säkerhet och produktivitet.

## <a name="migration-for-microsoft-office-server-products"></a>Migrering för Microsoft Office-serverprodukter

Oavsett om din organisation är stor eller liten, kanske du använder en kombination av äldre versioner av Office-serverprodukter, t.ex. Exchange Server och SharePoint Server. Dessa äldre versioner:

- Bör uppdateras med de senaste säkerhetsuppdateringarna och supportkorrigeringarna. I vissa fall släpps sådana uppdateringar varje månad.
- Har inte anpassats optimalt till att använda Microsofts molntekniker som hjälper dig att transformera din verksamhet digitalt.
- Innehåller inte nya produktivitetsprogram, t.ex. Microsoft Teams.
- Innehåller inte de senaste säkerhetsfunktionerna, till exempel Advanced Threat Protection i Exchange.

Microsoft 365 Enterprise innehåller Office 365, som inkluderar molnbaserade versioner av Office-servertjänster med vissa verktyg som lokala versioner av Office-serverprogram, till exempel webbläsare och Outlook-klienten. Tjänsternas säkerhet uppdateras ständigt utan att IT-avdelningen behöver agera, vilket sparar tid när lokala servrar ska underhållas och uppdateras. Tjänsterna har också nya funktionsförbättringar som inte finns i Office-serverprogrammen. 

### <a name="office-server-2007"></a>Office-server 2007

För serverprodukter i Office 2007-versionen har supporten redan upphört. Mer information finns i följande artiklar:

- [Översikt över supporten som upphör för Exchange 2007](https://docs.microsoft.com/office365/enterprise/exchange-2007-end-of-support)
- [Översikt över supporten som upphör för SharePoint Server 2007](https://docs.microsoft.com/office365/enterprise/sharepoint-2007-end-of-support)
- [Översikt över supporten som upphör för Project Server 2007](https://docs.microsoft.com/office365/enterprise/project-server-2007-end-of-support)
- [Översikt över supporten som upphör för Office Communications-server](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/upgrade)
- [Översikt över supporten som upphör för PerformancePoint Server 2007](https://docs.microsoft.com/office365/enterprise/pps-2007-end-of-support)

I stället för att uppgradera dina serverprodukter i Office 2007-versionen med serverprodukter i Office 2010, Office 2013 eller Office 2016 kan du:

1. Migrera data på Office 2007-servrar till Office 365. Om du behöver hjälp med detta kontaktar du en Microsoft-partner.
2. Distribuera de nya funktionerna och arbetsprocesserna till användarna.
3. När du inte längre behöver någon lokal server som kör Office 2007-serverprodukter, kan du inaktivera den.

### <a name="office-server-2010"></a>Office-server 2010

Upphörande av support för [Exchange Server 2010](https://docs.microsoft.com/office365/enterprise/exchange-2010-end-of-support) är **13 oktober 2020**.

Upphörande av support för [SharePoint Server 2010](https://docs.microsoft.com/office365/enterprise/upgrade-from-sharepoint-2010) är **13 april 2021**.

I stället för att uppgradera dessa serverprodukter i Office 2010-versionen med serverprodukter i Office 2013 eller Office 2016, kan du:

1. Migrera data på Office 2010-servrar till Microsoft 365. Om du behöver hjälp med detta kan du läsa [FastTrack för Microsoft 365](https://fasttrack.microsoft.com/microsoft365), eller kontakta en Microsoft-partner.
2. Distribuera de nya funktionerna och arbetsprocesserna till användarna.
3. När du inte längre behöver någon lokal server som kör Office 2010-serverprodukter, kan du inaktivera den.

### <a name="office-server-2013"></a>Office-server 2013

Det har ännu inte fastställts när supporten upphör för serverprodukter i Office 2013-versionen. I stället för att uppgradera dina serverprodukter i Office 2013-versionen med serverprodukter i Office 2016, kan du:

1. Migrera data på Office 2013-servrar till Office 365. Om du behöver hjälp med detta kan du läsa [FastTrack för Microsoft 365](https://fasttrack.microsoft.com/microsoft365), eller kontakta en Microsoft-partner.
2. Distribuera de nya funktionerna och arbetsprocesserna till användarna.
3. När du inte längre behöver någon lokal server som kör Office 2013-serverprodukter, kan du inaktivera den.

### <a name="office-server-2016"></a>Office-server 2016

Det har ännu inte fastställts när supporten upphör för serverprodukter i Office 2016-versionen. Om du vill använda den molnbaserade tjänsten och förbättringarna för att transformera ditt företag digitalt, kan du:

1. Migrera data på dina Office 2016-servrar till Office 365. Om du behöver hjälp med detta kan du läsa [FastTrack för Microsoft 365](https://fasttrack.microsoft.com/microsoft365), eller kontakta en Microsoft-partner.
2. Distribuera de nya funktionerna och arbetsprocesserna till användarna.
3. När du inte längre behöver någon lokal server som kör Office 2016-serverprodukter, kan du inaktivera den.

## <a name="migration-for-microsoft-windows-7-and-81"></a>Migrering för Microsoft Windows 7 och 8.1

Windows 7 upphörde med sin support den **14 januari 2020**. Om du vill migrera enheter som kör Windows 7 eller Windows 8.1 kan du utföra en [på-plats-uppgradering](https://docs.microsoft.com/microsoft-365/enterprise/windows10-deploy-inplaceupgrade). 

Fler metoder finns i [Distributionsscenarier för Windows 10](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios). Du kan också [planera för distribution av Windows 10](https://aka.ms/planforwin10deployment) på egen hand.

## <a name="summary-of-options-for-office-2010-clients-and-servers-and-windows-7"></a>Sammanfattning av alternativ för Office 2010-klienter/servrar och Windows 7

En visuell sammanfattning av alternativen att uppgradera, migrera och flytta till molnet för dessa produkter finns på [affischen supportens upphörande](../media/migration-microsoft-365-enterprise-workload/Office2010Windows7EndOfSupport.pdf).

[![Bild på affischen för supportens upphörande för Office 2010-klienter/servrar och Windows 7](../media/migration-microsoft-365-enterprise-workload/office2010-windows7-end-of-support.png)](../media/migration-microsoft-365-enterprise-workload/Office2010Windows7EndOfSupport.pdf)

Med den här affischen kan du snabbt se olika sökvägar som du kan ta för att förhindra att du inte får någon support för klient- och serverprodukter i Office 2010 och Windows 7, med prioriterade sökvägar och resulterande support i Microsoft 365 Enterprise markerade.

Du kan också [ladda ner denna affisch](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/migration-microsoft-365-enterprise-workload/Office2010Windows7EndOfSupport.pdf) och skriva ut den i formaten Letter, Legal och Tabloid (11 x 17).

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Hur Microsoft använder Microsoft 365 Enterprise

Se hur IT-experter på Microsoft migrerade företaget till Microsoft 365 Enterprise med följande resurser: 

- [Distribuera och uppdatera Microsoft Office 365 ProPlus](https://www.microsoft.com/itshowcase/Article/Content/757/Deploying-and-updating-Microsoft-Office-365-ProPlus)
- [Microsoft migrerar 150 000 postlådor till Exchange Online](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)
- [SharePoint till molnet: Se hur Microsoft har utfört sin egen migrering](https://www.microsoft.com/itshowcase/Article/Content/691/SharePoint-to-the-cloud-Learn-how-Microsoft-ran-its-own-migration)
- [Distribution av Windows 10 på Microsoft som en på-plats-uppgradering](https://www.microsoft.com/itshowcase/Article/Content/668/Deploying-Windows-10-at-Microsoft-as-an-inplace-upgrade)
- [Distribution av Windows 10: Tips och tricks från Microsoft IT](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT) (video)

## <a name="transition-your-entire-organization"></a>En övergång för hela organisationen

Om du vill få en bättre bild av hur du kan flytta hela organisationen till produkterna och tjänsterna i Microsoft 365 Enterprise kan du studera [övergångsaffischen](../media/deploy-microsoft-365-enterprise/transition-org-to-m365.pdf).

[![Bild på affischen för övergång till Microsoft 365](../media/deploy-microsoft-365-enterprise/transition-org-to-m365.png)](../media/deploy-microsoft-365-enterprise/transition-org-to-m365.pdf)

Med den här affischen på två sidor kan du snabbt inventera din befintliga infrastruktur och få vägledning när du flyttar till motsvarande produkt eller tjänst i Microsoft 365 Enterprise. Den innehåller Windows- och Office-produkter samt andra infrastruktur- och säkerhetselement, som exempelvis enhetshantering, identitet, information och skydd mot hot.

Du kan också [ladda ner denna affisch](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/deploy-microsoft-365-enterprise/transition-org-to-m365.pdf) och skriva ut den i formaten Letter, Legal och Tabloid (11 x 17).

## <a name="result"></a>Resultat

Din organisation har migrerat äldre versioner av Microsoft Office, Office-servrar och Windows till Microsoft 365 Enterprise.
