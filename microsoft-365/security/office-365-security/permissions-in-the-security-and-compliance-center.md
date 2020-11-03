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
ms.openlocfilehash: 44d9005b6d76f4d5c9079b055d6a5e3fd6c609d7
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845774"
---
# <a name="permissions-in-the-security--compliance-center"></a>Behörigheter i Säkerhets- och efterlevnadscentret

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Med funktionen för säkerhets & efterlevnad kan du bevilja behörigheter till personer som utför arbets uppgifter som enhets hantering, förhindrande av data förlust, eDiscovery, bevarande och så vidare. De här personerna kan bara utföra de uppgifter som du uttryckligen ger dem åtkomst till. För att komma åt säkerhets & regelefterlevnad måste användare vara en global administratör eller medlem i en eller flera säkerhets & roller för efterlevnadsprinciper.

Behörigheterna för säkerhets & uppfyller kraven för rollen baserad åtkomst kontroll (RBAC). RBAC är samma behörighets modell som används av Exchange, så om du känner till Exchange kan du få behörighet i säkerhets & Compliance Center. Det är viktigt att komma ihåg att de Exchange-roll grupperna och säkerhets & roll grupperna för regelefterlevnad inte delar medlemskap eller behörigheter. Men båda har en roll grupp för organisations hantering och är inte samma sak. De behörigheter de tilldelar och medlemmarna i roll grupperna är olika. Det finns en lista över säkerhets & roll grupper för regelefterlevnad nedan.

![Sidan behörigheter i Center för säkerhets &](../../media/992c20ca-e82e-497c-9c8d-6fab212deb80.png)

## <a name="relationship-of-members-roles-and-role-groups"></a>Relation mellan medlemmar, roller och roll grupper

En **roll** ger behörighet att utföra en uppsättning uppgifter; med rollen för Case-hantering kan folk till exempel arbeta med eDiscovery-ärenden.

En **roll grupp** är en uppsättning roller som gör att användarna kan utföra sitt jobb via säkerhets & Compliance Center. Roll gruppen för regelefterlevnad innehåller till exempel (bland annat roller) rollerna för ärende hantering, innehålls sökning och organisationens konfiguration (plus andra) eftersom någon som är kompatibelt administratörer måste ha behörighet för dessa aktiviteter för att utföra sitt jobb.

Säkerhets & Compliance Center innehåller standard roll grupper för de vanligaste uppgifterna och funktionerna som du måste tilldela personer till. Vi rekommenderar att du lägger till enskilda användare som **medlemmar** i standard roll grupperna.

![Diagram som visar relationen mellan roll grupper och roller och medlemmar](../../media/2a16d200-968c-4755-98ec-f1862d58cb8b.png)

## <a name="permissions-needed-to-use-features-in-the-security--compliance-center"></a>Behörigheter som krävs för att använda funktioner i säkerhets & Compliance Center

I följande tabell visas de standard roll grupper som är tillgängliga i säkerhets & Compliance Center, och de roller som är kopplade till roll grupperna som standard. Om du vill ge behörighet till en användare att utföra en efterföljande uppgift lägger du till dem i roll gruppen för säkerhets & efterlevnad.

Att hantera behörigheter i säkerhets & efterlevnad ger bara användarna åtkomst till de funktioner som är tillgängliga i säkerhets & efterlevnad Center. Om du vill bevilja behörigheter till andra funktioner som inte finns i säkerhets & kompatibilitetstillstånd, till exempel regler för Exchange-flöden (kallas även transport regler), måste du använda administrations centret för Exchange.

Om du vill se hur du beviljar åtkomst till säkerhets & Compliance Center kan du läsa [ge användare åtkomst till Microsoft 365 Compliance Admin Center](grant-access-to-the-security-and-compliance-center.md).

****

|Roll grupp|Beskrivning|Standard roller tilldelade|
|---|---|---|
|**Administratör för efterlevnad**<sup>1</sup>|Medlemmar kan hantera inställningar för enhets hantering, skydd mot data förlust, rapporter och konservering.|Ärende hantering <br/><br/> Administratör för kommunikation kompatibilitet <br/><br/> Analys av kommunikations kompatibilitet <br/><br/> Hantering av villkor för kommunikation <br/><br/> Undersökning av kommunikationen <br/><br/> Visnings program för kommunikation <br/><br/> Leverantör för feedback om data klassificering <br/><br/> Granskning av data klassificering <br/><br/> Hantering av data undersökning <br/><br/> Administratör för efterlevnad <br/><br/> Sökning efter efterlevnad <br/><br/> Enhets hantering <br/><br/> Dispositions hantering <br/><br/> Hantering av DLP-efterlevnad <br/><br/> Låta <br/><br/> IB-kompatibilitetskontrollen <br/><br/> Hantera aviseringar <br/><br/> Organisations konfiguration <br/><br/> RecordManagement <br/><br/> Hantering av bevarande <br/><br/> View-Only gransknings loggar <br/><br/> Hantering av View-Only enheter <br/><br/> View-Only DLP-kompatibilitetskontrollen <br/><br/> View-Only IB-kompatibilitetskontrollen <br/><br/> View-Only hantera aviseringar <br/><br/> View-Only mottagare <br/><br/> View-Only-posthantering <br/><br/> View-Only bevarande hantering <br/><br/> |
|**Administratör för regelefterlevnad**|Medlemmar kan hantera inställningar för enhets hantering, data skydd, skydd mot data förlust, rapporter och konservering.|Administratör för efterlevnad <br/><br/> Sökning efter efterlevnad <br/><br/> Enhets hantering <br/><br/> Hantering av DLP-efterlevnad <br/><br/> Dispositions hantering <br/><br/> IB-kompatibilitetskontrollen <br/><br/> Hantera aviseringar <br/><br/> Organisations konfiguration <br/><br/> RecordManagement <br/><br/> Hantering av bevarande <br/><br/> Etikett administratör för känslighet <br/><br/> View-Only gransknings loggar <br/><br/> Hantering av View-Only enheter <br/><br/> View-Only DLP-kompatibilitetskontrollen <br/><br/> View-Only IB-kompatibilitetskontrollen <br/><br/> View-Only hantera aviseringar <br/><br/> View-Only mottagare <br/><br/> View-Only-posthantering <br/><br/> View-Only bevarande hantering|
|**Innehålls översikt för innehålls Utforskaren**|Visa innehållsfilerna i innehålls Utforskaren.|Innehålls översikt för data klassificering|
|**Listvy för innehålls Utforskaren**|Visa alla objekt i innehålls Utforskaren endast i list format.|Visnings program för data klassificering|
|**Data utredning**|Medlemmar kan utföra sökningar på post lådor, SharePoint-webbplatser och OneDrive-konton.|Kommunikation <br/><br/> Sökning efter efterlevnad <br/><br/> Custodian <br/><br/> Hantering av data undersökning <br/><br/> Ören<br/><br/> Automatisk <br/><br/> RMS-kryptering <br/><br/> Översikt<br/><br/> Sök och ta bort|
|**eDiscovery Manager**|Medlemmar kan utföra sökningar och plats undantag på post lådor, SharePoint Online-webbplatser och OneDrive för företag-platser. Medlemmar kan också skapa och hantera eDiscovery-ärenden, lägga till och ta bort medlemmar i ett ärende, skapa och redigera innehålls sökningar associerade med ett ärende och komma åt ärende data i Avancerad eDiscovery. <br/><br/> En eDiscovery-administratör är medlem i roll gruppen eDiscovery Manager som har tilldelats ytterligare behörigheter. Utöver de uppgifter som en eDiscovery Manager kan utföra kan en eDiscovery-administratör:<ul><li>Visa alla eDiscovery-ärenden i organisationen.</li><li>Hantera ett eDiscovery-fall när de lägger till sig själva som en medlem i ärendet.</li></ul> <br/> Den primära skillnaden mellan en eDiscovery Manager och en eDiscovery-administratör är att en eDiscovery-administratör kan komma åt alla ärenden som visas på sidan **eDiscovery-ärenden** i säkerhets & Compliance Center. En eDiscovery Manager kan bara komma åt de ärenden som de skapar eller fall de är medlemmar i. Mer information om hur du gör en användare till en eDiscovery-administratör finns i [tilldela eDiscovery-behörigheter i säkerhets & Compliance Center](../../compliance/assign-ediscovery-permissions.md).|Ärende hantering <br/><br/> Kommunikation <br/><br/> Sökning efter efterlevnad <br/><br/> Custodian <br/><br/> Ören <br/><br/> Låta <br/><br/> Automatisk <br/><br/> RMS-kryptering <br/><br/> Översikt|
|**Global läsare**|Medlemmar har skrivskyddad åtkomst till rapporter, aviseringar och kan visa all konfiguration och alla inställningar.<br/><br/> Den primära skillnaden mellan global läsare och säkerhets läsare är att en global läsare kan komma åt **konfiguration och inställningar**.|Säkerhets läsare <br/><br/> Etikett läsare med känslighet <br/><br/> Vyn tjänste granskning <br/><br/> View-Only gransknings loggar <br/><br/> Hantering av View-Only enheter <br/><br/> View-Only DLP-kompatibilitetskontrollen <br/><br/> View-Only IB-kompatibilitetskontrollen <br/><br/> View-Only hantera aviseringar <br/><br/> View-Only mottagare <br/><br/> View-Only-posthantering <br/><br/> View-Only bevarande hantering|
|**Insider riskhantering**|Använd den här roll gruppen för att hantera hanteringen av Insider-risker för din organisation i en grupp. Genom att lägga till alla användar konton för administratörer, analytiker och granskare kan du konfigurera Insider riskhantering i en och samma grupp. Den här roll gruppen innehåller alla behörighets roller för hantering av Insider-risker. Det är det enklaste sättet att snabbt komma igång med Insider riskhantering och är en lämplig plats för organisationer som inte behöver särskilda behörigheter definierade för olika grupper av användare.|Ärende hantering <br/><br/> Hanterings administratör för Insider-riskhantering <br/><br/> Hanterings analys för Insider-riskhantering <br/><br/> Insider riskhantering <br/><br/> Tillfälligt bidrag för Insider riskhantering|
|**Insider riskhantering administratörer**|Använd den här roll gruppen för att konfigurera Insider riskhantering och senare att dela Insider-risk administratörer till en definierad grupp. Användare i den här roll gruppen kan skapa, läsa, uppdatera och ta bort Insider riskhantering-principer, globala inställningar och roll grupp tilldelningar.|Ärende hantering <br/><br/> Hanterings administratör för Insider-riskhantering|
|**Hanterings analyser för Insider-riskhantering**|Använd den här gruppen för att tilldela behörigheter till användare som ska fungera som ärenden i Insider-fall. Användare i den här roll gruppen kan komma åt alla frågor om Insider-riskhantering, ärenden och meddelanden. De kan inte komma åt innehålls Utforskaren för Insider-risker.|Ärende hantering <br/><br/> Hanterings analys för Insider-riskhantering|
|**Insider riskhantering**|Använd den här gruppen för att tilldela behörigheter till användare som ska fungera som säkerhets prövade Insider-risker. Användare i den här roll gruppen kan komma åt alla notifieringar om Insider-risker, ärenden, meddelanden och innehålls Utforskaren.|Ärende hantering <br/><br/> Insider riskhantering|
|**IRM-deltagare**|Den här roll gruppen är synlig men används endast i bakgrunds tjänster.|Tillfälligt bidrag för Insider riskhantering|
|**Flödes administratör**|Medlemmar kan övervaka och Visa insikter och rapporter om e-postflöden i säkerhets & Compliance Center. Globala administratörer kan lägga till vanliga användare i den här gruppen, men om användaren inte är medlem i gruppen Exchange-administratörer får användaren inte till gång till Exchange-relaterade uppgifter.|View-Only mottagare|
|**Organisations hantering**<sup>1</sup>|Medlemmar kan kontrol lera behörigheter för att komma åt funktioner i säkerhets & efterlevnad och även hantera inställningar för enhets hantering, skydd mot data förlust, rapporter och konservering. <br/><br/> Användare som inte är globala administratörer måste ha Exchange-administratörer för att se och vidta åtgärder på enheter som hanteras av grundläggande mobilitet och säkerhet för Microsoft 365 (kallades tidigare Mobile Device Management eller MDM). <br/><br/> Globala administratörer läggs automatiskt till som medlemmar i den här roll gruppen.|Gransknings loggar <br/><br/> Ärende hantering <br/><br/> Administratör för efterlevnad <br/><br/> Sökning efter efterlevnad <br/><br/> Enhets hantering <br/><br/> Hantering av DLP-efterlevnad <br/><br/> Låta <br/><br/> IB-kompatibilitetskontrollen <br/><br/> Hantera aviseringar <br/><br/> Organisations konfiguration <br/><br/> Karantän <br/><br/> RecordManagement <br/><br/> Hantering av bevarande <br/><br/> Roll hantering <br/><br/> Sök och ta bort <br/><br/> Säkerhets administratör <br/><br/> Säkerhets läsare <br/><br/> Etikett administratör för känslighet <br/><br/> Etikett läsare med känslighet <br/><br/> Vyn tjänste granskning <br/><br/> View-Only gransknings loggar <br/><br/> Hantering av View-Only enheter <br/><br/> View-Only DLP-kompatibilitetskontrollen <br/><br/> View-Only IB-kompatibilitetskontrollen <br/><br/> View-Only hantera aviseringar <br/><br/> View-Only mottagare <br/><br/> View-Only-posthantering <br/><br/> View-Only bevarande hantering|
|**Karantän administratör**|Medlemmar kan komma åt alla karantän åtgärder. Mer information finns i [Hantera meddelanden och filer i karantän som administratör i EOP](manage-quarantined-messages-and-files.md)|Karantän|
|**Hantering av Arkiv handlingar**|Medlemmar kan hantera och ta bort post innehåll.|RecordManagement|
|**Granskare**|Medlemmar kan bara visa listan med ärenden på sidan eDiscovery-ärenden i säkerhets & Compliance Center. De kan inte skapa, öppna eller hantera ett eDiscovery-ärende. Det primära syftet med den här roll gruppen är att tillåta medlemmar att visa och komma åt ärende data i [Avancerad eDiscovery (klassisk)](../../compliance/office-365-advanced-ediscovery.md) (kallas även för *Avancerad eDiscovery v1* ). <br/><br/> Den här roll gruppen har den mest restriktiva eDiscovery-relaterade behörigheterna.<br/><br/>**Obs!** För närvarande kan användare som är medlemmar i roll gruppen granska inte komma åt data i [Avancerad eDiscovery i Microsoft 365](../../compliance/overview-ediscovery-20.md) (kallas även *Avancerad eDiscovery v2* ). För att lägga till medlemmar i ett ärende i Avancerad eDiscovery v2 så att de kan granska ärende data måste en användare vara medlem i roll gruppen eDiscovery Manager.|Översikt|
|**Säkerhets administratör**|Medlemmar har till gång till ett antal säkerhetsfunktioner i identitets skydds Center, privilegierad identitets hantering, övervaka Microsoft 365-tjänstens tillstånd och säkerhets & Compliance Center. <br/><br/> Den här roll gruppen kanske som standard inte har några medlemmar. Rollen som säkerhets administratör från Azure Active Directory är dock kopplad till den här roll gruppen. Därför ärver den här roll gruppen funktioner och medlemskap för rollen säkerhets administratör från Azure Active Directory. <br/><br/> Om du vill hantera behörigheter centralt kan du lägga till och ta bort grupp medlemmar i administrations centret för Azure Active Directory. Mer information finns i [Administratörs behörigheter i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles). Om du redigerar den här roll gruppen i fältet säkerhets & efterlevnad (medlemskap eller roller) gäller dessa ändringar endast för säkerhets & för regelefterlevnad och inte andra tjänster. <br/><br/> Den här roll gruppen innehåller alla skrivskyddade behörigheter för rollen säkerhets läsare plus ett antal ytterligare administrativa behörigheter för samma tjänster: Azure information Protection, identitets skydds Center, behörig identitets hantering, övervaka Microsoft 365-tjänstens hälsa och säkerhets & Compliance Center.|Gransknings loggar <br/><br/> Enhets hantering <br/><br/> Hantering av DLP-efterlevnad <br/><br/> IB-kompatibilitetskontrollen <br/><br/> Hantera aviseringar <br/><br/> Karantän <br/><br/> Säkerhets administratör <br/><br/> Etikett administratör för känslighet <br/><br/> View-Only gransknings loggar <br/><br/> Hantering av View-Only enheter <br/><br/> View-Only DLP-kompatibilitetskontrollen <br/><br/> View-Only IB-kompatibilitetskontrollen <br/><br/> View-Only hantera aviseringar|
|**Säkerhets ansvarig**|Medlemmar kan hantera säkerhets varningar och även visa rapporter och inställningar för säkerhetsfunktioner.|Sökning efter efterlevnad <br/><br/> Hantera aviseringar <br/><br/> Säkerhets läsare <br/><br/> View-Only gransknings loggar <br/><br/> Hantering av View-Only enheter <br/><br/> View-Only DLP-kompatibilitetskontrollen <br/><br/> View-Only IB-kompatibilitetskontrollen <br/><br/> View-Only hantera aviseringar|
|**Säkerhets läsare**|Medlemmar har skrivskyddad åtkomst till ett antal säkerhetsfunktioner i identitets skydds Center, privilegierad identitets hantering, övervaka Microsoft 365-tjänstens tillstånd och säkerhets & Compliance Center. <br/><br/> Den här roll gruppen kanske som standard inte har några medlemmar. Säkerhets läsar rollen från Azure Active Directory är dock kopplad till den här roll gruppen. Därför ärver den här roll gruppen funktioner och medlemskap för rollen säkerhets läsare från Azure Active Directory. <br/><br/> Om du vill hantera behörigheter centralt kan du lägga till och ta bort grupp medlemmar i administrations centret för Azure Active Directory. Mer information finns i [Administratörs behörigheter i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles). Om du redigerar den här roll gruppen i fältet säkerhets & efterlevnad (medlemskap eller roller) gäller dessa ändringar endast för säkerhets & för regelefterlevnad och inte andra tjänster.|Säkerhets läsare <br/><br/> Etikett läsare med känslighet <br/><br/> Hantering av View-Only enheter <br/><br/> View-Only DLP-kompatibilitetskontrollen <br/><br/> View-Only IB-kompatibilitetskontrollen <br/><br/> View-Only hantera aviseringar|
|**Tjänst garanti användare**|Medlemmar kan komma åt avsnittet tjänster i säkerhets & Compliance Center. Tjänst kontroll tillhandahåller rapporter och dokument som beskriver Microsofts säkerhets rutiner för kunddata som lagras i Microsoft 365. Det tillhandahåller också oberoende gransknings rapporter från tredje part i Microsoft 365. Mer information finns i [tjänst granskning i säkerhets & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/service-assurance).|Vyn tjänste granskning|
|**Granska övervakning**|Medlemmar kan skapa och hantera principer som anger vilka meddelanden som ska granskas i en organisation. Mer information finns i [Konfigurera principer för kommunikations efterlevnad för din organisation](../../compliance/communication-compliance-configure.md).|Kontrol lera administratören|
|

> [!NOTE]
> <sup>1</sup> den här roll gruppen tilldelar inte medlemmar de behörigheter som krävs för att söka i gransknings loggen eller använda rapporter som kan innehålla Exchange-data, till exempel DLP-eller Defender för Office 365-rapporter. För att söka i gransknings loggen eller för att visa alla rapporter måste en användare tilldelas behörigheter i Exchange Online. Det här beror på att den underliggande cmdlet som används för att söka i gransknings loggen är en Exchange Online-cmdlet. Globala administratörer kan söka i gransknings loggen och Visa alla rapporter eftersom de automatiskt läggs till som medlemmar i roll gruppen organisations hantering i Exchange Online. Mer information finns i [söka i gransknings loggen i säkerhets & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).

## <a name="roles-in-the-security--compliance-center"></a>Roller i säkerhets & efterlevnad

I följande tabell visas de tillgängliga rollerna och roll grupperna som de har tilldelats som standard.

Observera att följande roller inte är tilldelade till roll gruppen organisations hantering som standard:

- Kommunikation
- Administratör för kommunikation kompatibilitet
- Analys av kommunikations kompatibilitet
- Hantering av villkor för kommunikation
- Undersökning av kommunikationen
- Visnings program för kommunikation
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
- Insider riskhantering
- Tillfälligt bidrag för Insider riskhantering
- Automatisk
- Översikt
- RMS-kryptering
- Kontrol lera administratören

****

|Roll|Beskrivning|Standard roll grupp tilldelningar|
|---|---|---|
|**Gransknings loggar**|Aktivera och konfigurera granskning för organisationen, Visa organisationens gransknings rapporter och exportera sedan rapporterna till en fil.|Organisationshantering <br/><br/> Säkerhets administratör|
|**Ärende hantering**|Skapa, redigera, ta bort och kontrol lera åtkomsten till eDiscovery-ärenden.|Administratör för efterlevnad <br/><br/> eDiscovery Manager <br/><br/> Hantering av insiderrisk <br/><br/> Insider riskhantering administratörer <br/><br/> Hanterings analyser för Insider-riskhantering <br/><br/> Insider riskhantering <br/><br/> Organisationshantering|
|**Kommunikation**|Hantera all kommunikation med Custodians som identifieras i ett avancerat eDiscovery-fodral.  Skapa undantags meddelanden, vänta med påminnelser och eskaleringar till hantering. Spåra custodian bekräftelse av undantags meddelanden och hantera åtkomst till custodian-portalen som används av varje custodian i ett fall för att spåra kommunikation för de fall då de identifierades som en custodian.|eDiscovery Manager|
|**Administratör för kommunikation kompatibilitet**|Används för att hantera principer i funktionen för kommunikations kompatibilitet.|Administratör för efterlevnad|
|**Analys av kommunikations kompatibilitet**|Används för att utföra undersökningar, åtgärdade meddelande överträdelser i funktionen för kommunikations kompatibilitet. Det går endast att visa metadata för meddelanden.|Administratör för efterlevnad|
|**Hantering av villkor för kommunikation**|Används för att komma åt ärenden för kommunikation.|Administratör för efterlevnad|
|**Undersökning av kommunikationen**|Används för att utföra undersökningar, reparation och granska meddelande överträdelser i funktionen för kommunikations kompatibilitet. Kan visa metadata för meddelanden.|Administratör för efterlevnad|
|**Visnings program för kommunikation**|Används för att komma åt rapporter och widgetar i funktionen för kommunikations kompatibilitet.||
|**Administratör för efterlevnad**|Visa och redigera inställningar och rapporter för funktioner för efterlevnad.|Administratör för efterlevnad <br/><br/> Administratör för regelefterlevnad <br/><br/> Organisationshantering|
|**Sökning efter efterlevnad**|Gör sökningar i post lådor och få en uppskattning av resultaten.|Administratör för efterlevnad <br/><br/> Administratör för regelefterlevnad <br/><br/> eDiscovery Manager <br/><br/> Organisationshantering <br/><br/> Säkerhets ansvarig|
|**Custodian**|Identifiera och hantera Custodians för avancerade eDiscovery-ärenden och Använd informationen från Azure Active Directory och andra källor för att hitta data källor som är kopplade till Custodians. Associera andra data källor, till exempel post lådor, SharePoint-webbplatser och team med Custodians i ett fall.  Placera en laglig spärr på de data källor som är associerade med Custodians för att bevara innehållet i kontexten för ett ärende.|eDiscovery Manager|
|**Innehålls översikt för data klassificering**|Visa på-plats åter givning av filer i innehålls Utforskaren.|Innehålls översikt för innehålls Utforskaren|
|**Leverantör för feedback om data klassificering**|Gör det möjligt att ge feedback till klassificerare i innehålls Utforskaren.|Administratör för efterlevnad|
|**Granskning av data klassificering**|Gör att du kan granska feedback från klassificerare i feedback Explorer.|Administratör för efterlevnad|
|**Visnings program för data klassificering**|Visa listan med filer i innehålls Utforskaren.|Listvy för innehålls Utforskaren|
|**Hantering av data undersökning**|Skapa, redigera, ta bort och kontrol lera åtkomsten till data undersökningar.|Administratör för efterlevnad <br/><br/> Data utredning|
|**Enhets hantering**|Visa och redigera inställningar och rapporter för enhets hanterings funktioner.|Administratör för efterlevnad <br/><br/> Administratör för regelefterlevnad <br/><br/> Organisationshantering <br/><br/> Säkerhets administratör|
|**Dispositions hantering**|Kontrol lera behörigheter för att komma åt manuell disposition i säkerhets & Compliance Center.|Administratör för efterlevnad <br/><br/> Administratör för regelefterlevnad|
|**Hantering av DLP-efterlevnad**|Visa och redigera inställningar och rapporter för principer för data förlust skydd (DLP).|Administratör för efterlevnad <br/><br/> Administratör för regelefterlevnad <br/><br/> Organisationshantering <br/><br/> Säkerhets administratör|
|**Ören**|Exportera post låda och webbplats innehåll som returneras från sökningar.|eDiscovery Manager|
|**Låta**|Placera innehåll i post lådor, webbplatser och gemensamma mappar i parkerat. När det parkeras sparas en kopia av innehållet på en säker plats. Innehålls ägare kan fortfarande ändra eller ta bort det ursprungliga innehållet.|Administratör för efterlevnad <br/><br/> eDiscovery Manager <br/><br/> Organisationshantering|
|**IB-kompatibilitetskontrollen**|Visa, skapa, ta bort, ändra och testa principer för informations barriärer.|Administratör för efterlevnad <br/><br/> Administratör för regelefterlevnad <br/><br/> Organisationshantering <br/><br/> Säkerhets administratör|
|**Hanterings administratör för Insider-riskhantering**|Skapa, redigera, ta bort och kontrol lera åtkomsten till hantering av Insider-risker.|Hantering av insiderrisk <br/><br/> Insider riskhantering administratörer|
|**Hanterings analys för Insider-riskhantering**|Få till gång till alla viktiga frågor om hanterings aviseringar, ärenden och meddelanden.|Hantering av insiderrisk <br/><br/> Hanterings analyser för Insider-riskhantering|
|**Insider riskhantering**|Få åtkomst till alla meddelanden om Insider riskhantering, ärenden, mallar och innehålls Utforskaren för alla ärenden.|Hantering av insiderrisk <br/><br/> Insider riskhantering|
|**Tillfälligt bidrag för Insider riskhantering**|Den här roll gruppen är synlig men används endast i bakgrunds tjänster.|IRM-deltagare|
|**Hantera aviseringar**|Visa och redigera inställningar och rapporter för aviseringar.|Administratör för efterlevnad <br/><br/> Administratör för regelefterlevnad <br/><br/> Organisationshantering <br/><br/> Säkerhets administratör <br/><br/> Säkerhets ansvarig|
|**Organisations konfiguration**|Köra, Visa och exportera gransknings rapporter och hantera efterlevnadsprinciper för DLP, enheter och konservering.|Administratör för efterlevnad <br/><br/> Administratör för regelefterlevnad <br/><br/> Organisationshantering|
|**Automatisk**|Visa en lista med objekt som returneras från innehålls sökningar och öppna varje objekt i listan för att visa dess innehåll.|eDiscovery Manager|
|**Karantän**|Gör det möjligt att visa och släppa e-postmeddelanden i karantän.|Karantän administratör <br/><br/> Säkerhets administratör <br/><br/> Organisationshantering|
|**RecordManagement**|Visa och redigera konfiguration och rapporter för funktionen för post hantering.|Administratör för efterlevnad <br/><br/> Administratör för regelefterlevnad <br/><br/> Organisationshantering <br/><br/> Hantering av Arkiv handlingar|
|**Hantering av bevarande**|Hantera bevarande principer.|Administratör för efterlevnad <br/><br/> Administratör för regelefterlevnad <br/><br/> Organisationshantering|
|**Översikt**|Använd Avancerad eDiscovery för att spåra, tagga, analysera och testa dokument som har kopplats till dem.|eDiscovery Manager <br/><br/> Granskare|
|**RMS-kryptering**|Dekryptera RMS-skyddat innehåll när du exporterar Sök resultat.|eDiscovery Manager|
|**Roll hantering**|Hantera roll grupp medlemskap och skapa eller ta bort anpassade roll grupper.|Organisationshantering|
|**Sök och ta bort**|Gör det möjligt för personer att ta bort data som matchar villkoren i en innehålls sökning.|Organisationshantering|
|**Säkerhets administratör**|Visa och redigera konfiguration och rapporter för säkerhetsfunktioner.|Organisationshantering <br/><br/> Säkerhets administratör|
|**Säkerhets läsare**|Visa konfiguration och rapporter för säkerhetsfunktionerna.|Organisationshantering <br/><br/> Säkerhets ansvarig <br/><br/> Säkerhets läsare|
|**Etikett administratör för känslighet**|Visa, skapa, ändra och ta bort känslighets etiketter.|Administratör för regelefterlevnad <br/><br/> Organisationshantering <br/><br/> Säkerhets administratör|
|**Etikett läsare med känslighet**|Visa konfiguration och användning av känslighets etiketter.|Global läsare <br/><br/> Organisationshantering <br/><br/> Säkerhets läsare|
|**Vyn tjänste granskning**|Ladda ned tillgängliga dokument från avsnittet service Assurance. Innehållet inkluderar oberoende granskning, efterlevnad av dokumentation och säkerhetsrelaterade vägledning för användning av Microsoft 365-funktioner för att hantera efterlevnad och säkerhets risker.|Tjänst garanti användare <br/><br/> Organisationshantering|
|**Kontrol lera administratören**|Hantera gransknings principer för administratörer, inklusive vilka meddelanden som ska granskas och vilka som ska kunna genomföra granskningen.|Granska övervakning|
|**Gransknings loggar endast för visning**|Visa och exportera gransknings rapporter. Eftersom dessa rapporter kan innehålla känslig information bör du endast tilldela den här rollen till personer med ett explicit behov av att visa den här informationen.|Administratör för efterlevnad <br/><br/> Administratör för regelefterlevnad <br/><br/> Organisationshantering <br/><br/> Säkerhets administratör <br/><br/> Säkerhets ansvarig|
|**Hantera endast enheter**|Visa konfiguration och rapporter för funktionen enhets hantering.|Administratör för efterlevnad <br/><br/> Administratör för regelefterlevnad <br/><br/> Organisationshantering <br/><br/> Säkerhets administratör <br/><br/> Säkerhets ansvarig <br/><br/> Säkerhets läsare|
|**Skrivskyddad DLP Compliance Management**|Visa inställningar för och rapporter för principer för skydd mot data förlust (DLP).|Administratör för efterlevnad <br/><br/> Administratör för regelefterlevnad <br/><br/> Organisationshantering <br/><br/> Säkerhets administratör <br/><br/> Säkerhets ansvarig <br/><br/> Säkerhets läsare|
|**Skrivskyddad hantering i IB**|Visa konfiguration och rapporter för funktionen för informations hinder.|Administratör för efterlevnad <br/><br/> Administratör för regelefterlevnad <br/><br/> Organisationshantering <br/><br/> Säkerhets administratör <br/><br/> Säkerhets ansvarig <br/><br/> Säkerhets läsare|
|**Visa endast hantera aviseringar**|Visa konfiguration och rapporter för funktionen Hantera aviseringar.|Säkerhets administratör <br/><br/> Säkerhets ansvarig <br/><br/> Säkerhets läsare <br/><br/> Administratör för efterlevnad <br/><br/> Administratör för regelefterlevnad <br/><br/> Organisationshantering|
|**Endast visning-mottagare**|Visa information om användare och grupper.|Flödes administratör <br/><br/> Administratör för efterlevnad <br/><br/> Administratör för regelefterlevnad <br/><br/> Organisationshantering|
|**Skrivskyddad post hantering**|Visa konfiguration och rapporter för funktionen för post hantering.|Administratör för efterlevnad <br/><br/> Administratör för regelefterlevnad <br/><br/> Organisationshantering|
|**Skrivskyddad hantering av bevarande**|Visa konfiguration och rapporter för funktionen för bevarande hantering.|Administratör för regelefterlevnad <br/><br/> Organisationshantering <br/><br/> Administratör för efterlevnad|
|
