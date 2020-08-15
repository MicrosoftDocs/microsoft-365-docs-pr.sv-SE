---
title: Rapporterings funktioner i Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-analytics
f1.keywords:
- NOCSH
description: Lär dig mer om olika rapporterings funktioner i Microsoft 365, inklusive Azure Active Directory och Exchange Online.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 104d587ea87a61a66b73aa1441170f37e082a72f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694752"
---
# <a name="microsoft-365-reporting-features"></a>Rapporterings funktioner i Microsoft 365

Rapporterings funktioner i Microsoft 365 tillhandahåller olika gransknings rapporter för Azure Active Directory (Azure AD), Exchange Online, enhets hantering, kontroll av tillsyn och data förlust skydd (DLP). Dessa rapporter är olika och skiljer sig från aktivitets rapporterna för Microsoft 365.

## <a name="microsoft-365-reports-dashboard"></a>Instrument panel för Microsoft 365-rapporter

Instrument panelen rapporter i för hands versionen av Microsoft 365 Admin Center visar användnings aktivitet i Microsoft 365. Microsoft 365 globala administratörer eller en Exchange Online-, SharePoint Online-eller Skype för företag-administratör kan få detaljerad insyn i användningen av den tjänsten. Till exempel antalet användare i en viss Microsoft 365-tjänst, antalet användare som har aktiverat Microsoft 365-program för företag (tidigare kallat Office 365 ProPlus) och hur mycket e-post som flödar genom organisationen. Rapporter är tillgängliga för de senaste 7, 30, 90 och 180 dagar.

Följande rapporter är tillgängliga:

- [Rapport om e-postaktivitet](https://support.office.com/article/Office-365-Reports-in-the-admin-center-preview--Email-activity-1cbe2c00-ca65-4fb9-9663-1bbfa58ebe44)
- [Microsoft Office-aktiveringar](https://support.office.com/article/Office-365-Reports-in-the-admin-center-preview--Microsoft-Office-activations-87c24ae2-82e0-4d1e-be01-c3bcc3f18c60)
- [Rapport om SharePoint Online-webbplats](https://support.office.com/article/Office-365-Reports-in-the-admin-center-preview--SharePoint-site-usage-4ecfb843-e5d5-464d-8bf6-7ed512a9b213)
- [Rapport om OneDrive för företag](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Preview--OneDrive-for-Business-usage-0de3b312-c4e8-4e4b-a02d-32b2f726a680)
- [Yammer-aktivitets rapport](https://support.office.com/article/View-the-Yammer-Activity-report-in-the-Office-365-admin-center-preview-c7c9f938-5b8e-4d52-b1a2-c7c32cb2312a)
- [Aktivitets rapport för Skype för företag](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online-reporting/activity-report)
- [Rapport om peer-to-peer-aktivitet i Skype för företag](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online-reporting/peer-to-peer-activity-report)
- [Rapport om konferens i Skype för företag](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online-reporting/conference-organizer-activity-report)
- [Aktivitets rapport för konferens deltagare i Skype för företag](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online-reporting/conference-participant-activity-report)

Mer information finns i avsnittet [aktivitets rapporter i administrations centret för Microsoft 365](https://support.office.com/article/activity-reports-in-the-office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263).

## <a name="azure-ad-reports"></a>Azure AD-rapporter

Microsoft 365 använder Azure AD för identifiering och identitets hantering. Microsoft 365-administratörer använder rapporter som genererats av Azure för att identifiera ovanlig aktivitet och obehörig åtkomst till deras data. Du kan använda Access-och användnings rapporter i Azure AD för att få en överblick över katalogens integritet och säkerhet. Med den här informationen kan du identifiera och minska eventuella säkerhets risker.

Azure AD-rapporter kan exporteras till Microsoft Excel och korreleras med andra data från Microsoft 365. Resultatet av en gransknings loggs ökning kan till exempel ge insyn i Access-, verifierings-och program nivå aktiviteter. Avancerade rapporter om avvikelse och Resursanvändning är tillgängliga med Azure AD Premium. De här avancerade rapporterna hjälper till att förbättra dina säkerhets Posture och hjälper dig att reagera på potentiella hot genom att använda analyser om åtkomst till enheter och användning av program. Mer information finns i [Azure Active Directory-rapportering](https://docs.microsoft.com/azure/active-directory/reports-monitoring/overview-reports/).

## <a name="exchange-online-audit-reports"></a>Gransknings rapporter för Exchange Online

Gransknings rapporter för Exchange Online innehåller information om åtkomst till post lådor och ändringar gjorda av administratörer till din Exchange Online-klient organisation. Med granskning av post låda kan du använda aktiviteterna i följande tabell för att köra rapporter och exportera gransknings loggar för Exchange Online.

> [!NOTE]
> Du måste aktivera gransknings loggning för post lådor för varje post låda så att de granskade händelserna sparas i gransknings loggen för den post lådan. Om gransknings loggning för post lådan inte är aktiverat för en post låda sparas inte händelser för den post lådan i gransknings loggen och visas inte i gransknings rapporterna för post lådan. Mer information finns i [aktivera granskning av post låda](https://support.office.com/article/Enable-mailbox-auditing-in-Office-365-aaca8987-5b62-458b-9882-c28476a66918).

| Uppgift | Beskrivning |
|----------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Köra en rapport om en post låda med icke-ägare](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/non-owner-mailbox-access-report) | Visar listan över post lådor som används av någon annan än ägaren till post lådan. Rapporten innehåller information om vem som har åtkomst till post lådan, vilka åtgärder de har gjort i post lådan och om åtgärderna lyckades. |
| [Exportera gransknings loggar för post lådor](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/export-mailbox-audit-logs) | Gransknings loggar för post lådor innehåller information om åtkomst och åtgärder i en post låda som tas av en annan användare än post lådans ägare. Administratörer kan ange post lådor tillsammans med ett datum intervall för att skapa rapporter. Loggarna exporteras i XML, bifogade till ett meddelande och skickas till specifika användare enligt administratören. |
| [Köra en administratörs grupp rapport](https://docs.microsoft.com/Office365/SecurityCompliance/eop/run-an-administrator-role-group-report-in-eop-eop) | Administratörs roll gruppen tilldelar användarna administratörs behörighet. Dessa privilegier gör att användare kan utföra administrativa uppgifter som Återställ lösen ord, skapa eller ändra post lådor och tilldela administratörs behörigheter till andra användare. I rapporten administratörs grupp visas ändringar av roll grupper, inklusive tillägg och borttagning av medlemmar. |
| [Visa administratörs gransknings loggen](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/view-administrator-audit-log) | I rapporten administratörs Gransknings logg visas alla funktioner för att skapa, uppdatera och ta bort som utförs av administratörer i Exchange Online. Logg poster innehåller information om vilken cmdlet som kördes, vilka parametrar som användes, vem som körde cmdleten och vilka objekt som påverkades. |
| [Innehålls sökning för post låda](https://docs.microsoft.com/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery) | Innehåller information om eventuella ändringar i eDiscovery-inställningar på plats eller på plats. |
| [Exportera administratörs gransknings loggen](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/search-role-group-changes) | Administratörs gransknings loggen registrerar specifika administrativa åtgärder som att skapa, uppdatera och ta bort i Exchange Online. Resultaten från loggen exporteras till XML och administratörer kan välja att skicka den här loggen till en uppsättning användare. |
| [Köra en rapport med tvist i en post låda](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/per-mailbox-litigation-hold-report) | Innehåller information om eventuella ändringar av inställnings inställningar för tvister. |
| [Visa och exportera gransknings loggen för extern administratör](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/view-external-admin-audit-log) | Innehåller information om åtgärder som utförs av externa administratörer. Posterna innehåller information om vilken cmdlet som kördes, vilka parametrar som användes och vilka åtgärder som skapar, ändrar eller tar bort objekt i Exchange Online. |

## <a name="device-compliance-reports"></a>Kompatibilitetsrapport för enheter

Du hanterar och skyddar mobila enheter som är anslutna till ditt abonnemang med hjälp av Microsoft 365 Mobile Device Management (MDM). Mobila enheter som används för att komma åt e-post, kalender, kontakter och dokument spelar en betydande del av att de anställda kan arbeta när som helst och var de än är. Det är viktigt att du skyddar organisationens information. Du använder Microsoft 365 MDM för att ange säkerhets principer och åtkomst regler för enheter. Om du förlorar eller stulna kan du också använda Microsoft 365 MDM för att rensa mobila enheter.

MDM-rapporter ger en översikt över principer som ställts in av en organisation för att skydda mobila enheter som har till gång till Microsoft 365-data. I rapporten kan du filtrera enheter efter kompatibilitetsstatus, rapporterade överträdelser, blockerade enheter och hur många enheter som rensas genom säkerhets principer. Mer information finns i [Översikt över hantering av mobila enheter för Microsoft 365](https://support.microsoft.com/office/overview-of-mobile-device-management-mdm-for-microsoft-365-faa7d8e5-645d-4d59-839c-c8d4c1869e4a).

## <a name="data-loss-prevention"></a>Förhindra data förlust

DLP-principer hjälper till att hantera säkerheten och informations flödet i en organisation. Du kan konfigurera principer för att blockera åtkomst till innehåll, kryptera data eller meddela användare om princip-och policy överträdelser med hjälp av program för DLP-principer. DLP-rapporter ger en inblick i antalet principer och regel matchningar, åsidosättningar och falska positiva verifieringar.

Du använder administrations centret för Microsoft 365 för att visa information om antalet meddelanden som upptäckts av dina DLP-principer. DLP-rapporter ger insikter i princip-och regel matchningar för skickade och mottagna e-postmeddelanden. Du kan också visa antalet matchningar, åsidosättningar och falska positiva godkännanden för varje policy under de senaste 24 timmarna med Exchange Admin Center. Om du laddar ned en Excel-rapport kan du Visa ännu mer information, till exempel vem som skickade ett meddelande, den dag och vilken princip matchning som har utlösts. Mer information finns i [Visa rapporter om identifieringar av DLP-principer](https://docs.microsoft.com/previous-versions/exchange-server/exchange-150/jj889415(v=exchg.150)).

## <a name="auditing-in-yammer-enterprise"></a>Granskning i Yammer Enterprise

I Yammer Enterprise kan administratörer exportera användar aktivitets data från deras Yammer-nätverk via [API för data export för Yammer](https://support.office.com/article/export-data-from-yammer-enterprise-b303d8f3-007d-4ad4-81f8-54fb1ecfb3f2), eller manuellt via administrations sidan för Yammer-nätverk. Möjligheten att exportera loggar är begränsad till nätverks administratörer i Yammer. (Alla Microsoft 365-globala administratörer är Yammer-nätverks administratörer.)

Följande data kan exporteras:

| Datafil | Beskrivning |
|----------------------------|-------------------------------------------------------------------------|
| Users.csv | Alla nya, pågående och upphävda användare i nätverket |
| Messages.csv | Alla meddelanden i nätverket |
| Files.csv (metadata) | Metadata som fil namn, fil-API-URL, överföra ID, uppladdat hos, etc. |
| Files.csv (originalfiler) | Zip-fil för originalfilerna som laddats upp av användare till Yammer |
| Topics.csv | Avsnitt som skapats i nätverket |
| Pages.csv | Sidor som skapats av användare i nätverket |
| Admins.csv | Alla verifierade administratörer i nätverket |
| Networks.csv | Alla externa Yammer-nätverk |

Yammer Enterprise-data är också tillgängliga via aktivitets rapporterna för Microsoft 365. Dessutom fungerar Yammer aktivt för att exponera ytterligare loggning via API: et för Microsoft 365 Management Activity och på förmågan att komma över data med Power BI. Se [Office-översikten](https://fasttrack.microsoft.com/roadmap?filters=yammer) för mer information om dessa funktioner.
