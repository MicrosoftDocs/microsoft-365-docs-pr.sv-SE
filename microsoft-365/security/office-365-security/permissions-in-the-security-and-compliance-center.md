---
title: Behörigheter-& Compliance Center
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.AdminRoleGroups
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
description: Administratörer kan läsa mer om vilka behörigheter som är tillgängliga i säkerhets & Compliance Center i Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6c01e70dd693b313ca369901a2d6475961510b6e
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683265"
---
# <a name="permissions-in-the-security--compliance-center"></a>Behörigheter i Säkerhets- och efterlevnadscentret

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Med funktionen för säkerhets & efterlevnad kan du bevilja behörigheter till personer som utför arbets uppgifter som enhets hantering, förhindrande av data förlust, eDiscovery, bevarande och så vidare. De här personerna kan bara utföra de uppgifter som du uttryckligen ger dem åtkomst till. För att komma åt säkerhets & regelefterlevnad måste användare vara en global administratör eller medlem i en eller flera säkerhets & roller för efterlevnadsprinciper.

Behörigheterna för säkerhets & uppfyller kraven för rollen baserad åtkomst kontroll (RBAC). RBAC är samma behörighets modell som används av Exchange, så om du känner till Exchange kan du få behörighet i säkerhets & Compliance Center. Det är viktigt att komma ihåg att de Exchange-roll grupperna och säkerhets & roll grupperna för regelefterlevnad inte delar medlemskap eller behörigheter. Men båda har en roll grupp för organisations hantering och är inte samma sak. De behörigheter de tilldelar och medlemmarna i roll grupperna är olika. Det finns en lista över säkerhets & roll grupper för regelefterlevnad nedan.

![Sidan behörigheter i Center för säkerhets &](../../media/992c20ca-e82e-497c-9c8d-6fab212deb80.png)

## <a name="relationship-of-members-roles-and-role-groups"></a>Relation mellan medlemmar, roller och roll grupper

En **roll** ger behörighet att utföra en uppsättning uppgifter; med rollen för Case-hantering kan folk till exempel arbeta med eDiscovery-ärenden.

En **roll grupp** är en uppsättning roller som gör att användarna kan utföra sina jobb i säkerhets & Compliance Center. Roll gruppen för regelefterlevnad innehåller till exempel (bland annat roller) rollerna för ärende hantering, innehålls sökning och organisationens konfiguration (plus andra) eftersom någon som är kompatibelt administratörer måste ha behörighet för dessa aktiviteter för att utföra sitt jobb.

Säkerhets & Compliance Center innehåller standard roll grupper för de vanligaste uppgifterna och funktionerna som du måste tilldela personer till. Vi rekommenderar att du lägger till enskilda användare som **medlemmar** i standard roll grupperna.

![Diagram som visar relationen mellan roll grupper och roller och medlemmar](../../media/2a16d200-968c-4755-98ec-f1862d58cb8b.png)

## <a name="permissions-needed-to-use-features-in-the-security--compliance-center"></a>Behörigheter som krävs för att använda funktioner i säkerhets & Compliance Center

I följande tabell visas de standard roll grupper som är tillgängliga i säkerhets & Compliance Center, och de roller som är kopplade till roll grupperna som standard. Om du vill ge behörighet till en användare att utföra en efterföljande uppgift lägger du till dem i roll gruppen för säkerhets & efterlevnad.

Att hantera behörigheter i säkerhets & efterlevnad ger bara användarna åtkomst till de funktioner som är tillgängliga i säkerhets & efterlevnad Center. Om du vill bevilja behörigheter till andra funktioner som inte finns i säkerhets & kompatibilitetstillstånd, till exempel regler för Exchange-flöden (kallas även transport regler), måste du använda administrations centret för Exchange.

Om du vill se hur du beviljar åtkomst till säkerhets & Compliance Center kan du läsa [ge användare åtkomst till Microsoft 365 Compliance Admin Center](grant-access-to-the-security-and-compliance-center.md).

****

|Roll grupp|Beskrivning|Standard roller tilldelade|
|---|---|---|
|**Kommunikationer**|Ger behörighet till alla arbets boks roller för kommunikation: administratör, analytiker, prövares och användare.|Ärende hantering <p> Administratör för kommunikation kompatibilitet <p> Analys av kommunikations kompatibilitet <p> Hantering av villkor för kommunikation <p> Undersökning av kommunikationen <p> Visnings program för kommunikation <p> Leverantör för feedback om data klassificering <p> View-Only fall|
|**Administratörer för kommunikation överensstämmelse**|Administratörer för kommunikation som kan skapa och redigera principer och definiera globala inställningar.|Administratör för kommunikation kompatibilitet <p> Hantering av villkor för kommunikation|
|**Analys av kommunikationer**|Analys av kommunikations efterlevnad som kan undersöka princip matchningar, Visa meddelande-metadata och vidta åtgärder.|Analys av kommunikations kompatibilitet <p> Hantering av villkor för kommunikation|
|**Undersöknings prövare**|En analys av kommunikationen som kan undersöka princip matchningar, Visa meddelande innehåll och vidta åtgärder.|Ärende hantering <p> Analys av kommunikations kompatibilitet <p> Hantering av villkor för kommunikation <p> Undersökning av kommunikationen <p> Leverantör för feedback om data klassificering <p> View-Only fall|
|**Visnings program för kommunikation**|Visnings program för kommunikation som kan komma åt tillgängliga rapporter och widgetar.|Hantering av villkor för kommunikation <p> Visnings program för kommunikation|
|**Administratör för efterlevnad**<sup>1</sup>|Medlemmar kan hantera inställningar för enhets hantering, skydd mot data förlust, rapporter och konservering.|Ärende hantering <p> Administratör för kommunikation kompatibilitet <p> Analys av kommunikations kompatibilitet <p> Hantering av villkor för kommunikation <p> Undersökning av kommunikationen <p> Visnings program för kommunikation <p> Leverantör för feedback om data klassificering <p> Granskning av data klassificering <p> Hantering av data undersökning <p> Administratör för efterlevnad <p> Sökning efter efterlevnad <p> Enhets hantering <p> Dispositions hantering <p> Hantering av DLP-efterlevnad <p> Låta <p> IB-kompatibilitetskontrollen <p> Hantera aviseringar <p> Organisations konfiguration <p> RecordManagement <p> Hantering av bevarande <p> View-Only gransknings loggar <p> Hantering av View-Only enheter <p> View-Only DLP-kompatibilitetskontrollen <p> View-Only IB-kompatibilitetskontrollen <p> View-Only hantera aviseringar <p> View-Only mottagare <p> View-Only-posthantering <p> View-Only bevarande hantering|
|**Administratör för regelefterlevnad**|Medlemmar kan hantera inställningar för enhets hantering, data skydd, skydd mot data förlust, rapporter och konservering.|Administratör för efterlevnad <p> Sökning efter efterlevnad <p> Enhets hantering <p> Hantering av DLP-efterlevnad <p> Dispositions hantering <p> IB-kompatibilitetskontrollen <p> Hantera aviseringar <p> Organisations konfiguration <p> RecordManagement <p> Hantering av bevarande <p> Etikett administratör för känslighet <p> View-Only gransknings loggar <p> Hantering av View-Only enheter <p> View-Only DLP-kompatibilitetskontrollen <p> View-Only IB-kompatibilitetskontrollen <p> View-Only hantera aviseringar <p> View-Only mottagare <p> View-Only-posthantering <p> View-Only bevarande hantering|
|**Administratörer för Autentiseringshanteraren**|Hantera skapa och ändra mall.|Administration av Compliance Manager <p> Utvärderings chef <p> Bidrag för regelefterlevnad <p> Läsare för regelefterlevnad|
|**Bedömare för Compliance Manager**|Skapa utvärderingar, implementera förbättrings åtgärder och uppdatera test status för förbättrings åtgärder.|Utvärderings chef <p> Bidrag för regelefterlevnad <p> Läsare för regelefterlevnad|
|**Deltagare i Compliance Manager**|Skapa utvärderingar och utför arbete för att implementera förbättrings åtgärder.|Bidrag för regelefterlevnad <p> Läsare för regelefterlevnad|
|**Läsare för regelefterlevnad**|Visa allt innehåll i överensstämmelse hanteraren förutom för administratörs funktioner.|Läsare för regelefterlevnad|
|**Innehålls översikt för innehålls Utforskaren**|Visa innehållsfilerna i innehålls Utforskaren.|Innehålls översikt för data klassificering|
|**Listvy för innehålls Utforskaren**|Visa alla objekt i innehålls Utforskaren endast i list format.|Visnings program för data klassificering|
|**Data utredning**|Medlemmar kan utföra sökningar på post lådor, SharePoint-webbplatser och OneDrive-konton.|Kommunikation <p> Sökning efter efterlevnad <p> Custodian <p> Hantering av data undersökning <p> Ören<p> Automatisk <p> RMS-kryptering <p> Översikt<p> Sök och ta bort|
|**eDiscovery Manager**|Medlemmar kan utföra sökningar och plats undantag på post lådor, SharePoint Online-webbplatser och OneDrive för företag-platser. Medlemmar kan också skapa och hantera eDiscovery-ärenden, lägga till och ta bort medlemmar i ett ärende, skapa och redigera innehålls sökningar associerade med ett ärende och komma åt ärende data i Avancerad eDiscovery. <p> En eDiscovery-administratör är medlem i roll gruppen eDiscovery Manager som har tilldelats ytterligare behörigheter. Utöver de uppgifter som en eDiscovery Manager kan utföra kan en eDiscovery-administratör:<ul><li>Visa alla eDiscovery-ärenden i organisationen.</li><li>Hantera ett eDiscovery-fall när de lägger till sig själva som en medlem i ärendet.</li></ul> <p> Den primära skillnaden mellan en eDiscovery Manager och en eDiscovery-administratör är att en eDiscovery-administratör kan komma åt alla ärenden som visas på sidan **eDiscovery-ärenden** i säkerhets & Compliance Center. En eDiscovery Manager kan bara komma åt de ärenden som de skapar eller fall de är medlemmar i. Mer information om hur du gör en användare till en eDiscovery-administratör finns i [tilldela eDiscovery-behörigheter i säkerhets & Compliance Center](../../compliance/assign-ediscovery-permissions.md).|Ärende hantering <p> Kommunikation <p> Sökning efter efterlevnad <p> Custodian <p> Ören <p> Låta <p> Automatisk <p> RMS-kryptering <p> Översikt|
|**Global läsare**|Medlemmar har skrivskyddad åtkomst till rapporter, aviseringar och kan visa all konfiguration och alla inställningar.<p> Den primära skillnaden mellan global läsare och säkerhets läsare är att en global läsare kan komma åt **konfiguration och inställningar**.|Säkerhets läsare <p> Etikett läsare med känslighet <p> Vyn tjänste granskning <p> View-Only gransknings loggar <p> Hantering av View-Only enheter <p> View-Only DLP-kompatibilitetskontrollen <p> View-Only IB-kompatibilitetskontrollen <p> View-Only hantera aviseringar <p> View-Only mottagare <p> View-Only-posthantering <p> View-Only bevarande hantering|
|**Insider riskhantering**|Använd den här roll gruppen för att hantera hanteringen av Insider-risker för din organisation i en grupp. Genom att lägga till alla användar konton för administratörer, analytiker och granskare kan du konfigurera Insider riskhantering i en och samma grupp. Den här roll gruppen innehåller alla behörighets roller för hantering av Insider-risker. Det är det enklaste sättet att snabbt komma igång med Insider riskhantering och är en lämplig plats för organisationer som inte behöver särskilda behörigheter definierade för olika grupper av användare.|Ärende hantering <p> Hanterings administratör för Insider-riskhantering <p> Hanterings analys för Insider-riskhantering <p> Insider riskhantering <p> Tillfälligt bidrag för Insider riskhantering <p> Endast Visa Skift läge|
|**Insider riskhantering administratörer**|Använd den här roll gruppen för att konfigurera Insider riskhantering och senare att dela Insider-risk administratörer till en definierad grupp. Användare i den här roll gruppen kan skapa, läsa, uppdatera och ta bort Insider riskhantering-principer, globala inställningar och roll grupp tilldelningar.|Ärende hantering <p> Hanterings administratör för Insider-riskhantering <p> Endast Visa Skift läge|
|**Hanterings analyser för Insider-riskhantering**|Använd den här gruppen för att tilldela behörigheter till användare som ska fungera som ärenden i Insider-fall. Användare i den här roll gruppen kan komma åt alla frågor om Insider-riskhantering, ärenden och meddelanden. De kan inte komma åt innehålls Utforskaren för Insider-risker.|Ärende hantering <p> Hanterings analys för Insider-riskhantering <p> Endast Visa Skift läge|
|**Insider riskhantering**|Granskare av Insider riskhantering som kan visa gransknings loggar för åtgärder som utförs av analytiker, forskare och administratörer.|Översikt över Insider-riskhantering|
|**Insider riskhantering**|Använd den här gruppen för att tilldela behörigheter till användare som ska fungera som säkerhets prövade Insider-risker. Användare i den här roll gruppen kan komma åt alla notifieringar om Insider-risker, ärenden, meddelanden och innehålls Utforskaren.|Ärende hantering <p> Insider riskhantering <p> Endast Visa Skift läge|
|**IRM-deltagare**|Den här roll gruppen är synlig men används endast i bakgrunds tjänster.|Tillfälligt bidrag för Insider riskhantering|
|**Flödes administratör**|Medlemmar kan övervaka och Visa insikter och rapporter om e-postflöden i säkerhets & Compliance Center. Globala administratörer kan lägga till vanliga användare i den här gruppen, men om användaren inte är medlem i gruppen Exchange-administratörer får användaren inte till gång till Exchange-relaterade uppgifter.|View-Only mottagare|
|**Organisations hantering**<sup>1</sup>|Medlemmar kan kontrol lera behörigheter för att komma åt funktioner i säkerhets & efterlevnad och även hantera inställningar för enhets hantering, skydd mot data förlust, rapporter och konservering. <p> Användare som inte är globala administratörer måste ha Exchange-administratörer för att se och vidta åtgärder på enheter som hanteras av grundläggande mobilitet och säkerhet för Microsoft 365 (kallades tidigare Mobile Device Management eller MDM). <p> Globala administratörer läggs automatiskt till som medlemmar i den här roll gruppen.|Gransknings loggar <p> Ärende hantering <p> Administratör för efterlevnad <p> Sökning efter efterlevnad <p> Enhets hantering <p> Hantering av DLP-efterlevnad <p> Låta <p> IB-kompatibilitetskontrollen <p> Hantera aviseringar <p> Organisations konfiguration <p> Karantän <p> RecordManagement <p> Hantering av bevarande <p> Roll hantering <p> Sök och ta bort <p> Säkerhets administratör <p> Säkerhets läsare <p> Etikett administratör för känslighet <p> Etikett läsare med känslighet <p> Vyn tjänste granskning <p> Tagga deltagare <p> Taggredigerare <p> Taggkontrollen <p> View-Only gransknings loggar <p> Hantering av View-Only enheter <p> View-Only DLP-kompatibilitetskontrollen <p> View-Only IB-kompatibilitetskontrollen <p> Endast Visa Skift läge <p> View-Only hantera aviseringar <p> View-Only mottagare <p> View-Only-posthantering <p> View-Only bevarande hantering|
|**Karantän administratör**|Medlemmar kan komma åt alla karantän åtgärder. Mer information finns i [Hantera meddelanden och filer i karantän som administratör i EOP](manage-quarantined-messages-and-files.md)|Karantän|
|**Integritets hantering**|Hantera åtkomst kontroll för integritets hanterings lösning i Microsoft 365 Compliance Center.|Integritets administration <p> Översikt över integritets hantering <p> Undersökning av integritets hantering <p> Permanent bidrag till integritets hantering <p> Tillfälligt bidrag till integritets hantering <p> Sekretess hanterings visning|
|**Administratörer för integritets hantering**|Administratörer av integritets hanterings lösning som kan skapa och redigera principer och definiera globala inställningar.|Integritets administration|
|**Analytiker för integritets hantering**|En analys av en lösning för integritets hantering som kan undersöka princip matchningar, Visa meddelanden och vidta åtgärder.|Översikt över integritets hantering|
|**Deltagare i integritets hantering**|Hantera deltagar åtkomst för frågor om integritets hantering.|Permanent bidrag till integritets hantering <p> Tillfälligt bidrag till integritets hantering|
|**Integritets utredning**|Analyser av integritets hanterings lösning som kan undersöka princip matchningar, Visa meddelande innehåll och vidta åtgärder.|Undersökning av integritets hantering|
|**Visnings program för integritets hantering**|Visning av integritets hanterings lösning som kan komma åt tillgängliga instrument paneler och widgetar.|Sekretess hanterings visning|
|**Hantering av Arkiv handlingar**|Medlemmar kan konfigurera alla aspekter av hantering av Arkiv handlingar, inklusive bevarande etiketter och dispositions granskningar.|RecordManagement <p> Hantering av bevarande <p> Dispositions hantering|
|**Granskare**|Medlemmar kan bara visa listan med ärenden på sidan eDiscovery-ärenden i säkerhets & Compliance Center. De kan inte skapa, öppna eller hantera ett eDiscovery-ärende. Det primära syftet med den här roll gruppen är att tillåta medlemmar att visa och komma åt ärende data i [Avancerad eDiscovery (klassisk)](../../compliance/office-365-advanced-ediscovery.md) (kallas även för *Avancerad eDiscovery v1*). <p> Den här roll gruppen har den mest restriktiva eDiscovery-relaterade behörigheterna. <p> **Obs!** För närvarande kan användare som är medlemmar i roll gruppen granska inte komma åt data i [Avancerad eDiscovery i Microsoft 365](../../compliance/overview-ediscovery-20.md) (kallas även *Avancerad eDiscovery v2*). För att lägga till medlemmar i ett ärende i Avancerad eDiscovery v2 så att de kan granska ärende data måste en användare vara medlem i roll gruppen eDiscovery Manager.|Översikt|
|**Säkerhets administratör**|Medlemmar har till gång till ett antal säkerhetsfunktioner i identitets skydds Center, privilegierad identitets hantering, övervaka Microsoft 365-tjänstens tillstånd och säkerhets & Compliance Center. <p> Den här roll gruppen kanske som standard inte har några medlemmar. Rollen som säkerhets administratör från Azure Active Directory är dock kopplad till den här roll gruppen. Därför ärver den här roll gruppen funktioner och medlemskap för rollen säkerhets administratör från Azure Active Directory. <p> Om du vill hantera behörigheter centralt kan du lägga till och ta bort grupp medlemmar i administrations centret för Azure Active Directory. Mer information finns i [Administratörs behörigheter i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles). Om du redigerar den här roll gruppen i fältet säkerhets & efterlevnad (medlemskap eller roller) gäller dessa ändringar endast för säkerhets & för regelefterlevnad och inte andra tjänster. <p> Den här roll gruppen innehåller alla skrivskyddade behörigheter för rollen säkerhets läsare plus ett antal ytterligare administrativa behörigheter för samma tjänster: Azure information Protection, identitets skydds Center, behörig identitets hantering, övervaka Microsoft 365-tjänstens hälsa och säkerhets & Compliance Center.|Gransknings loggar <p> Enhets hantering <p> Hantering av DLP-efterlevnad <p> IB-kompatibilitetskontrollen <p> Hantera aviseringar <p> Karantän <p> Säkerhets administratör <p> Etikett administratör för känslighet <p> Tagga deltagare <p> Taggredigerare <p> Taggkontrollen <p> View-Only gransknings loggar <p> Hantering av View-Only enheter <p> View-Only DLP-kompatibilitetskontrollen <p> View-Only IB-kompatibilitetskontrollen <p> View-Only hantera aviseringar|
|**Säkerhets ansvarig**|Medlemmar kan hantera säkerhets varningar och även visa rapporter och inställningar för säkerhetsfunktioner.|Sökning efter efterlevnad <p> Hantera aviseringar <p> Säkerhets läsare <p> Tagga deltagare <p> Taggkontrollen <p> View-Only gransknings loggar <p> Hantering av View-Only enheter <p> View-Only DLP-kompatibilitetskontrollen <p> View-Only IB-kompatibilitetskontrollen <p> View-Only hantera aviseringar|
|**Säkerhets läsare**|Medlemmar har skrivskyddad åtkomst till ett antal säkerhetsfunktioner i identitets skydds Center, privilegierad identitets hantering, övervaka Microsoft 365-tjänstens tillstånd och säkerhets & Compliance Center. <p> Den här roll gruppen kanske som standard inte har några medlemmar. Säkerhets läsar rollen från Azure Active Directory är dock kopplad till den här roll gruppen. Därför ärver den här roll gruppen funktioner och medlemskap för rollen säkerhets läsare från Azure Active Directory. <p> Om du vill hantera behörigheter centralt kan du lägga till och ta bort grupp medlemmar i administrations centret för Azure Active Directory. Mer information finns i [Administratörs behörigheter i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles). Om du redigerar den här roll gruppen i fältet säkerhets & efterlevnad (medlemskap eller roller) gäller dessa ändringar endast för säkerhets & för regelefterlevnad och inte andra tjänster.|Säkerhets läsare <p> Etikett läsare med känslighet <p> Taggkontrollen <p> Hantering av View-Only enheter <p> View-Only DLP-kompatibilitetskontrollen <p> View-Only IB-kompatibilitetskontrollen <p> View-Only hantera aviseringar|
|**Tjänst garanti användare**|Medlemmar kan komma åt avsnittet tjänster i säkerhets & Compliance Center. Tjänst kontroll tillhandahåller rapporter och dokument som beskriver Microsofts säkerhets rutiner för kunddata som lagras i Microsoft 365. Det tillhandahåller också oberoende gransknings rapporter från tredje part i Microsoft 365. Mer information finns i [tjänst granskning i säkerhets & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/service-assurance).|Vyn tjänste granskning|
|**Granska övervakning**|Medlemmar kan skapa och hantera principer som anger vilka meddelanden som ska granskas i en organisation. Mer information finns i [Konfigurera principer för kommunikations efterlevnad för din organisation](../../compliance/communication-compliance-configure.md).|Kontrol lera administratören|
|

> [!NOTE]
> <sup>1</sup> den här roll gruppen tilldelar inte medlemmar de behörigheter som krävs för att söka i gransknings loggen eller använda rapporter som kan innehålla Exchange-data, till exempel DLP-eller Defender för Office 365-rapporter. För att söka i gransknings loggen eller för att visa alla rapporter måste en användare tilldelas behörigheter i Exchange Online. Det här beror på att den underliggande cmdlet som används för att söka i gransknings loggen är en Exchange Online-cmdlet. Globala administratörer kan söka i gransknings loggen och Visa alla rapporter eftersom de automatiskt läggs till som medlemmar i roll gruppen organisations hantering i Exchange Online. Mer information finns i [söka i gransknings loggen i säkerhets & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).

## <a name="roles-in-the-security--compliance-center"></a>Roller i säkerhets & efterlevnad

I följande tabell visas de tillgängliga rollerna och roll grupperna som de har tilldelats som standard.

Observera att följande roller inte är tilldelade till roll gruppen organisations hantering som standard:

- Administratör för angrepps Simulator
- Författare för angrepps Simulator
- Kommunikation
- Administratör för kommunikation kompatibilitet
- Analys av kommunikations kompatibilitet
- Hantering av villkor för kommunikation
- Undersökning av kommunikationen
- Visnings program för kommunikation
- Administration av Compliance Manager
- Utvärderings chef
- Bidrag för regelefterlevnad
- Läsare för regelefterlevnad
- Custodian
- Innehålls översikt för data klassificering
- Leverantör för feedback om data klassificering
- Granskning av data klassificering
- Visnings program för data klassificering
- Hantering av data undersökning
- Dispositions hantering
- Ören
- Hanterings administratör för Insider-riskhantering
- Hanterings analys för Insider-riskhantering
- Översikt över Insider-riskhantering
- Insider riskhantering
- Permanent bidrag för Insider-riskhantering
- Tillfälligt bidrag för Insider riskhantering
- Automatisk
- Integritets administration
- Översikt över integritets hantering
- Undersökning av integritets hantering
- Permanent bidrag till integritets hantering
- Tillfälligt bidrag till integritets hantering
- Sekretess hanterings visning
- Översikt
- RMS-kryptering
- Kontrol lera administratören

****

|Roll|Beskrivning|Standard roll grupp tilldelningar|
|---|---|---|
|**Administratör för angrepps Simulator**|Används för att skapa och hantera alla aspekter av anslags simulerings kampanjer.||
|**Författare för angrepps Simulator**|Används för att skapa och hantera nytto Last-nyttolaster som kan distribueras av angrepps Simulator administratören.||
|**Gransknings loggar**|Aktivera och konfigurera granskning för organisationen, Visa organisationens gransknings rapporter och exportera sedan rapporterna till en fil.|Organisationshantering <p> Säkerhets administratör|
|**Ärende hantering**|Skapa, redigera, ta bort och kontrol lera åtkomsten till eDiscovery-ärenden.|Administratör för efterlevnad <p> eDiscovery Manager <p> Hantering av insiderrisk <p> Insider riskhantering administratörer <p> Hanterings analyser för Insider-riskhantering <p> Insider riskhantering <p> Organisationshantering|
|**Kommunikation**|Hantera all kommunikation med Custodians som identifieras i ett avancerat eDiscovery-fodral.  Skapa undantags meddelanden, vänta med påminnelser och eskaleringar till hantering. Spåra custodian bekräftelse av undantags meddelanden och hantera åtkomst till custodian-portalen som används av varje custodian i ett fall för att spåra kommunikation för de fall då de identifierades som en custodian.|eDiscovery Manager|
|**Administratör för kommunikation kompatibilitet**|Används för att hantera principer i funktionen för kommunikations kompatibilitet.|Administratör för efterlevnad|
|**Analys av kommunikations kompatibilitet**|Används för att utföra undersökningar, åtgärdade meddelande överträdelser i funktionen för kommunikations kompatibilitet. Det går endast att visa metadata för meddelanden.|Administratör för efterlevnad|
|**Hantering av villkor för kommunikation**|Används för att komma åt ärenden för kommunikation.|Administratör för efterlevnad|
|**Undersökning av kommunikationen**|Används för att utföra undersökningar, reparation och granska meddelande överträdelser i funktionen för kommunikations kompatibilitet. Kan visa metadata för meddelanden.|Administratör för efterlevnad|
|**Visnings program för kommunikation**|Används för att komma åt rapporter och widgetar i funktionen för kommunikations kompatibilitet.||
|**Administratör för efterlevnad**|Visa och redigera inställningar och rapporter för funktioner för efterlevnad.|Administratör för efterlevnad <p> Administratör för regelefterlevnad <p> Organisationshantering|
|**Administration av Compliance Manager**|Hantera skapa och ändra mall.|Administratörer för Autentiseringshanteraren|
|**Utvärderings chef**|Skapa utvärderingar, implementera förbättrings åtgärder och uppdatera test status för förbättrings åtgärder.|Administratörer för Autentiseringshanteraren <p> Bedömare för Compliance Manager|
|**Bidrag för regelefterlevnad**|Skapa utvärderingar och utför arbete för att implementera förbättrings åtgärder.|Administratörer för Autentiseringshanteraren <p> Bedömare för Compliance Manager <p> Deltagare i Compliance Manager|
|**Läsare för regelefterlevnad**|Visa allt innehåll i överensstämmelse hanteraren förutom för administratörs funktioner.|Administratörer för Autentiseringshanteraren <p> Bedömare för Compliance Manager <p> Deltagare i Compliance Manager <p> Läsare för regelefterlevnad|
|**Sökning efter efterlevnad**|Gör sökningar i post lådor och få en uppskattning av resultaten.|Administratör för efterlevnad <p> Administratör för regelefterlevnad <p> eDiscovery Manager <p> Organisationshantering <p> Säkerhets ansvarig|
|**Custodian**|Identifiera och hantera Custodians för avancerade eDiscovery-ärenden och Använd informationen från Azure Active Directory och andra källor för att hitta data källor som är kopplade till Custodians. Associera andra data källor, till exempel post lådor, SharePoint-webbplatser och team med Custodians i ett fall.  Placera en laglig spärr på de data källor som är associerade med Custodians för att bevara innehållet i kontexten för ett ärende.|eDiscovery Manager|
|**Innehålls översikt för data klassificering**|Visa på-plats åter givning av filer i innehålls Utforskaren.|Innehålls översikt för innehålls Utforskaren|
|**Leverantör för feedback om data klassificering**|Gör det möjligt att ge feedback till klassificerare i innehålls Utforskaren.|Administratör för efterlevnad|
|**Granskning av data klassificering**|Gör att du kan granska feedback från klassificerare i feedback Explorer.|Administratör för efterlevnad|
|**Visnings program för data klassificering**|Visa listan med filer i innehålls Utforskaren.|Listvy för innehålls Utforskaren|
|**Hantering av data undersökning**|Skapa, redigera, ta bort och kontrol lera åtkomsten till data undersökningar.|Administratör för efterlevnad <p> Data utredning|
|**Enhets hantering**|Visa och redigera inställningar och rapporter för enhets hanterings funktioner.|Administratör för efterlevnad <p> Administratör för regelefterlevnad <p> Organisationshantering <p> Säkerhets administratör|
|**Dispositions hantering**|Visa och vidta en åtgärd på innehåll som har nått slutet av dess bevarande period. <p> | Administratör för regelefterlevnad|
|**Hantering av DLP-efterlevnad**|Visa och redigera inställningar och rapporter för principer för data förlust skydd (DLP).|Administratör för efterlevnad <p> Administratör för regelefterlevnad <p> Organisationshantering <p> Säkerhets administratör|
|**Ören**|Exportera post låda och webbplats innehåll som returneras från sökningar.|eDiscovery Manager|
|**Låta**|Placera innehåll i post lådor, webbplatser och gemensamma mappar i parkerat. När det parkeras sparas en kopia av innehållet på en säker plats. Innehålls ägare kan fortfarande ändra eller ta bort det ursprungliga innehållet.|Administratör för efterlevnad <p> eDiscovery Manager <p> Organisationshantering|
|**IB-kompatibilitetskontrollen**|Visa, skapa, ta bort, ändra och testa principer för informations barriärer.|Administratör för efterlevnad <p> Administratör för regelefterlevnad <p> Organisationshantering <p> Säkerhets administratör|
|**Hanterings administratör för Insider-riskhantering**|Skapa, redigera, ta bort och kontrol lera åtkomsten till hantering av Insider-risker.|Hantering av insiderrisk <p> Insider riskhantering administratörer|
|**Hanterings analys för Insider-riskhantering**|Få till gång till alla viktiga frågor om hanterings aviseringar, ärenden och meddelanden.|Hantering av insiderrisk <p> Hanterings analyser för Insider-riskhantering|
|**Översikt över Insider-riskhantering**|Tillåt visning av gransknings historik för Insider-risker.|Insider riskhantering|
|**Insider riskhantering**|Få åtkomst till alla meddelanden om Insider riskhantering, ärenden, mallar och innehålls Utforskaren för alla ärenden.|Hantering av insiderrisk <p> Insider riskhantering|
|**Permanent bidrag för Insider-riskhantering**|Den här roll gruppen är synlig men används endast i bakgrunds tjänster.|IRM-deltagare|
|**Tillfälligt bidrag för Insider riskhantering**|Den här roll gruppen är synlig men används endast i bakgrunds tjänster.|IRM-deltagare|
|**Hantera aviseringar**|Visa och redigera inställningar och rapporter för aviseringar.|Administratör för efterlevnad <p> Administratör för regelefterlevnad <p> Organisationshantering <p> Säkerhets administratör <p> Säkerhets ansvarig|
|**Organisations konfiguration**|Köra, Visa och exportera gransknings rapporter och hantera efterlevnadsprinciper för DLP, enheter och konservering.|Administratör för efterlevnad <p> Administratör för regelefterlevnad <p> Organisationshantering|
|**Automatisk**|Visa en lista med objekt som returneras från innehålls sökningar och öppna varje objekt i listan för att visa dess innehåll.|eDiscovery Manager|
|**Integritets administration**|Används för att hantera principer i integritets hanterings lösningen och som har till gång till alla funktioner i lösningen.|Integritets hantering <p> Administratörer för integritets hantering|
|**Översikt över integritets hantering**|Används för att utföra undersökningar, åtgärd vid meddelande brott i integritets hanterings lösning. Metadata kan endast visas för meddelanden.|Integritets hantering <p> Analytiker för integritets hantering|
|**Undersökning av integritets hantering**|Används för att utföra undersökningar, reparation, Granska meddelande brott i integritets lösning. Kan visa meddelanden om metadata & fullständigt meddelande.|Integritets hantering <p> Integritets utredning|
|**Permanent bidrag till integritets hantering**|Används för att komma åt sekretess hanteringen som permanent deltagare.|Integritets hantering <p> Deltagare i integritets hantering|
|**Tillfälligt bidrag till integritets hantering**|Används för att komma åt sekretess hanteringen som en tillfällig deltagare.|Integritets hantering <p> Deltagare i integritets hantering|
|**Sekretess hanterings visning**|Används för att komma åt instrument paneler & widget i integritets hanterings lösning.|PrivacyManagement <p> Visnings program för integritets hantering|
|**Karantän**|Gör det möjligt att visa och släppa e-postmeddelanden i karantän.|Karantän administratör <p> Säkerhets administratör <p> Organisationshantering|
|**RecordManagement**|Visa och redigera konfigurationen för funktionen för hantering av Arkiv handlingar.|Administratör för efterlevnad <p> Administratör för regelefterlevnad <p> Organisationshantering <p> Hantering av Arkiv handlingar|
|**Hantering av bevarande**|Hantera bevarande principer, bevarande etiketter och bevarande etikett principer.|Administratör för efterlevnad <p> Administratör för regelefterlevnad <p> Organisationshantering <p> Hantering av Arkiv handlingar|
|**Översikt**|Använd Avancerad eDiscovery för att spåra, tagga, analysera och testa dokument som har kopplats till dem.|eDiscovery Manager <p> Granskare|
|**RMS-kryptering**|Dekryptera RMS-skyddat innehåll när du exporterar Sök resultat.|eDiscovery Manager|
|**Roll hantering**|Hantera roll grupp medlemskap och skapa eller ta bort anpassade roll grupper.|Organisationshantering|
|**Sök och ta bort**|Gör det möjligt för personer att ta bort data som matchar villkoren i en innehålls sökning.|Organisationshantering|
|**Säkerhets administratör**|Visa och redigera konfiguration och rapporter för säkerhetsfunktioner.|Organisationshantering <p> Säkerhets administratör|
|**Säkerhets läsare**|Visa konfiguration och rapporter för säkerhetsfunktionerna.|Organisationshantering <p> Säkerhets ansvarig <p> Säkerhets läsare|
|**Etikett administratör för känslighet**|Visa, skapa, ändra och ta bort känslighets etiketter.|Administratör för regelefterlevnad <p> Organisationshantering <p> Säkerhets administratör|
|**Etikett läsare med känslighet**|Visa konfiguration och användning av känslighets etiketter.|Global läsare <p> Organisationshantering <p> Säkerhets läsare|
|**Vyn tjänste granskning**|Ladda ned tillgängliga dokument från avsnittet service Assurance. Innehållet inkluderar oberoende granskning, efterlevnad av dokumentation och säkerhetsrelaterade vägledning för användning av Microsoft 365-funktioner för att hantera efterlevnad och säkerhets risker.|Tjänst garanti användare <p> Organisationshantering|
|**Kontrol lera administratören**|Hantera handledande principer, inklusive vilka meddelanden som ska granskas och vem som bör göra recensionen.|Granska övervakning|
|**Tagga deltagare**|Visa och uppdatera medlemskap för befintliga användar flaggor.|Organisationshantering <p> Säkerhets administratör <p> Säkerhets ansvarig|
|**Taggredigerare**|Visa, uppdatera, skapa och ta bort användar koder.|Organisationshantering <p> Säkerhets administratör|
|**Taggkontrollen**|Skrivskyddad åtkomst till befintliga användar koder.|Säkerhets läsare|
|**Gransknings loggar endast för visning**|Visa och exportera gransknings rapporter. Eftersom dessa rapporter kan innehålla känslig information bör du endast tilldela den här rollen till personer med ett explicit behov av att visa den här informationen.|Administratör för efterlevnad <p> Administratör för regelefterlevnad <p> Organisationshantering <p> Säkerhets administratör <p> Säkerhets ansvarig|
|**Endast visnings fall**||Efterlevnad av kommunikation <p> Undersöknings prövare <p> Administratör för efterlevnad <p> Hantering av insiderrisk <p> Insider riskhantering administratörer <p> Hanterings analyser för Insider-riskhantering <p> Insider RiskManagement-undersökare <p> Organisationshantering|
|**Hantera endast enheter**|Visa konfiguration och rapporter för funktionen enhets hantering.|Administratör för efterlevnad <p> Administratör för regelefterlevnad <p> Organisationshantering <p> Säkerhets administratör <p> Säkerhets ansvarig <p> Säkerhets läsare|
|**Skrivskyddad DLP Compliance Management**|Visa inställningar för och rapporter för principer för skydd mot data förlust (DLP).|Administratör för efterlevnad <p> Administratör för regelefterlevnad <p> Organisationshantering <p> Säkerhets administratör <p> Säkerhets ansvarig <p> Säkerhets läsare|
|**Skrivskyddad hantering i IB**|Visa konfiguration och rapporter för funktionen för informations hinder.|Administratör för efterlevnad <p> Administratör för regelefterlevnad <p> Organisationshantering <p> Säkerhets administratör <p> Säkerhets ansvarig <p> Säkerhets läsare|
|**Visa endast hantera aviseringar**|Visa konfiguration och rapporter för funktionen Hantera aviseringar.|Säkerhets administratör <p> Säkerhets ansvarig <p> Säkerhets läsare <p> Administratör för efterlevnad <p> Administratör för regelefterlevnad <p> Organisationshantering|
|**Endast visning-mottagare**|Visa information om användare och grupper.|Flödes administratör <p> Administratör för efterlevnad <p> Administratör för regelefterlevnad <p> Organisationshantering|
|**Skrivskyddad post hantering**|Visa konfigurationen för funktionen för hantering av Arkiv handlingar.|Administratör för efterlevnad <p> Administratör för regelefterlevnad <p> Organisationshantering|
|**Skrivskyddad hantering av bevarande**|Visa konfigureringen av bevarande principer, bevarande etiketter och bevarande etikett principer.|Administratör för regelefterlevnad <p> Organisationshantering <p> Administratör för efterlevnad|
|
