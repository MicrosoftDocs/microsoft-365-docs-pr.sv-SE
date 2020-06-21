---
title: Behörigheter – Microsoft 365 Security & Compliance Center
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 02/14/2020
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
description: Administratörer kan läsa om de behörigheter som är tillgängliga i Microsoft 365 Security & Compliance Center.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e236278fbfaf2ff3c696e294e429cdaf895bbb3a
ms.sourcegitcommit: 3119b2246001ba06af8264508785352dfb894166
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/19/2020
ms.locfileid: "44820578"
---
# <a name="permissions-in-the-security--compliance-center"></a>Behörigheter i Säkerhets- och efterlevnadscentret

Med Security & Compliance Center kan du bevilja behörigheter till personer som utför efterlevnadsuppgifter som enhetshantering, dataförlustskydd, eDiscovery, lagring och så vidare. Dessa personer kan bara utföra de uppgifter som du uttryckligen ger dem åtkomst till. För att komma åt security & Compliance Center måste användarna vara globala administratör eller medlem i en eller flera rollgrupper för säkerhets- & Compliance Center.

Behörigheter i security & Compliance Center baseras på rbac-behörighetsmodellen (Role Based Access Control). Det här är samma behörighetsmodell som används av Exchange, så om du är bekant med Exchange kommer beviljandet av behörigheter i Security & Compliance Center att vara mycket lika. Det är dock viktigt att komma ihåg att rollgrupper för Exchange och & rollgrupper för efterlevnadscenter inte delar medlemskap eller behörigheter. Även om båda har en arbetsgrupp för organisationshantering är de inte desamma. De behörigheter de beviljar och medlemmarna i rollgrupperna är olika. Det finns en lista över rollgrupper för & Compliance Center nedan.

![Sidan Behörigheter i säkerhets- & compliance center](../../media/992c20ca-e82e-497c-9c8d-6fab212deb80.png)

## <a name="relationship-of-members-roles-and-role-groups"></a>Relation mellan medlemmar, roller och rollgrupper

En **roll** ger behörighet att utföra en uppsättning uppgifter. Med rollen Ärendehantering kan du till exempel arbeta med eDiscovery-ärenden.

En **rollgrupp** är en uppsättning roller som gör att personer kan utföra sitt jobb i säkerhets- & Compliance Center. Rollgruppen Efterlevnadsadministratör innehåller till exempel rollerna för ärendehantering, innehållssökning och organisationskonfiguration (plus andra) eftersom någon som är efterlevnadsadministratör behöver behörigheterna för att dessa uppgifter ska kunna utföra sitt jobb.

Security & Compliance Center innehåller standardrollgrupper för de vanligaste uppgifterna och funktionerna som du måste tilldela personer till. Vi rekommenderar att du helt enkelt lägger till enskilda användare som **medlemmar** i standardrollgrupperna.

![Diagram som visar rollgruppernas relation till roller och medlemmar](../../media/2a16d200-968c-4755-98ec-f1862d58cb8b.png)

## <a name="permissions-needed-to-use-features-in-the-security--compliance-center"></a>Behörigheter som krävs för att använda funktioner i Security & Compliance Center

I följande tabell visas standardrollgrupper som är tillgängliga i Security & Compliance Center och de roller som tilldelas rollgrupperna som standard. Om du vill ge en användare behörighet att utföra en efterlevnadsuppgift lägger du till dem i lämplig rollgrupp för & efterlevnadscenter.

Hantera behörigheter i Security & Compliance Center ger användarna endast åtkomst till de efterlevnadsfunktioner som är tillgängliga i Security & Compliance Center själv. Om du vill bevilja behörigheter till andra efterlevnadsfunktioner som inte finns i Security & Compliance Center, till exempel Regler för Exchange-e-postflöde (kallas även transportregler), måste du använda administrationscentret för Exchange.

Om du vill se hur du beviljar åtkomst till Security & Compliance Center läser du [Ge användarna åtkomst till Microsoft 365 Compliance admin center](grant-access-to-the-security-and-compliance-center.md).

||||
|---|---|---|
|**Rollgrupp**|**Beskrivning**|**Standardroller tilldelade**|
|**Efterlevnadsadministratör**<sup>1</sup>|Medlemmar kan hantera inställningar för enhetshantering, dataförlustskydd, rapporter och bevarande.|Ärendehantering <br/><br/> Administratör för kommunikationsefterlevnad <br/><br/> Analys av kommunikationsefterlevnad <br/><br/> Hantering av ärendehantering för kommunikation <br/><br/> Undersökning av efterlevnad av kommunikation <br/><br/> Visningsprogram för kommunikationsefterlevnad <br/><br/> Feedbackleverantör för dataklassificering <br/><br/> Dataklassificering Feedback Granskare <br/><br/> Hantering av datautredningar <br/><br/> Administratör för efterlevnad <br/><br/> Efterlevnadssökning <br/><br/> Enhetshantering <br/><br/> Dispositionshantering <br/><br/> Hantering av DLP-efterlevnad <br/><br/> Hålla <br/><br/> Hantering av efterlevnad av IB <br/><br/> Hantera aviseringar <br/><br/> Organisationskonfiguration <br/><br/> RecordManagement (Rekordhantverk) <br/><br/> Hantering av kvarhållning <br/><br/> Granskningsloggar med endast visa <br/><br/> Hantering av endast visningsenheter <br/><br/> Hantering av endast vy-DLP-efterlevnad <br/><br/> Hantering av endast visning av IB-efterlevnad <br/><br/> Hantera aviseringar som endast visas <br/><br/> Endast visningsmottagare <br/><br/> Hantering av endast visningspost <br/><br/> Hantering av endast visningsbevarande <br/><br/> |
|**Administratör för efterlevnadsdata**|Medlemmar kan hantera inställningar för enhetshantering, dataskydd, dataförlustskydd, rapporter och bevarande.|Administratör för efterlevnad <br/><br/> Efterlevnadssökning <br/><br/> Hantering av DLP-efterlevnad <br/><br/> Enhetshantering <br/><br/> Dispositionshantering <br/><br/> Hantering av efterlevnad av IB <br/><br/> Hantera aviseringar <br/><br/> Organisationskonfiguration <br/><br/> RecordManagement (Rekordhantverk) <br/><br/> Hantering av kvarhållning <br/><br/> Administratör för känslighetsetikett <br/><br/> Granskningsloggar med endast visa <br/><br/> Hantering av endast vy-DLP-efterlevnad <br/><br/> Hantering av endast visningsenheter <br/><br/> Hantering av endast visning av IB-efterlevnad <br/><br/> Hantera aviseringar som endast visas <br/><br/> Endast visningsmottagare <br/><br/> Hantering av endast visningspost <br/><br/> Hantering av endast visningsbevarande|
|**Innehållsvisaren för innehållsutforskare**|Visa innehållsfilerna i Innehållsutforskaren.|Innehållsvisaren för dataklassificering|
|**Visa loggning för innehållsutforskaren**|Visa alla objekt i Innehållsutforskaren i listformat.|Visningsprogram för dataklassificeringslista|
|**Data Utredare**|Medlemmar kan utföra sökningar på postlådor, SharePoint-webbplatser och OneDrive-konton.|Kommunikation <br/><br/> Efterlevnadssökning <br/><br/> Vårdnadshavare <br/><br/> Hantering av datautredningar <br/><br/> Exportera<br/><br/> Förhandsgranska <br/><br/> RMS dekryptera <br/><br/> Recension<br/><br/> Sök och rensa|
|**eDiscovery-chef**|Medlemmar kan utföra sökningar och spärra på postlådor, SharePoint Online-webbplatser och OneDrive för företag-platser. Medlemmar kan också skapa och hantera eDiscovery-ärenden, lägga till och ta bort medlemmar i ett ärende, skapa och redigera innehållssökningar som är associerade med ett ärende och komma åt ärendedata i Avancerad eDiscovery. <br/><br/> En eDiscovery-administratör är medlem i rollgruppen eDiscovery Manager som har tilldelats ytterligare behörigheter. Förutom de uppgifter som en eDiscovery Manager kan utföra kan en eDiscovery-administratör: <br/>* Visa alla eDiscovery fall i organisationen. <br/>* Hantera alla eDiscovery fall efter att de lägger sig som en medlem av ärendet. <br/><br/> Den primära skillnaden mellan en eDiscovery Manager och en eDiscovery Administrator är att en eDiscovery Administratör kan komma åt alla ärenden som visas på sidan **eDiscovery fall** i Security & Compliance Center. En eDiscovery-chef kan bara komma åt de ärenden som de har skapat eller ärenden som de är medlemmar i. Mer information om hur du gör en användare till eDiscovery Administrator finns [i Tilldela eDiscovery-behörigheter i Security & Compliance Center](../../compliance/assign-ediscovery-permissions.md).|Ärendehantering <br/><br/> Kommunikation <br/><br/> Efterlevnadssökning <br/><br/> Vårdnadshavare <br/><br/> Exportera <br/><br/> Hålla <br/><br/> Förhandsgranska <br/><br/> RMS dekryptera <br/><br/> Recension|
|**Global läsare**|Medlemmar har skrivskyddad åtkomst till rapporter, aviseringar och kan se alla konfigurationer och inställningar.<br/><br/> Den primära skillnaden mellan Global Reader och Security Reader är att en global läsare kan komma åt **konfiguration och inställningar**.|Säkerhetsläsare <br/><br/> Känslighetsetikettläsare <br/><br/> Service assurance-vy <br/><br/> Granskningsloggar med endast visa <br/><br/> Hantering av endast vy-DLP-efterlevnad <br/><br/> Hantering av endast visningsenheter <br/><br/> Hantering av endast visning av IB-efterlevnad <br/><br/> Hantera aviseringar som endast visas <br/><br/> Endast visningsmottagare <br/><br/> Hantering av endast visningspost <br/><br/> Hantering av endast visningsbevarande|
|**Insider riskhantering**|Använd den här rollgruppen för att hantera insiderriskhantering för din organisation i en enda grupp. Genom att lägga till alla användarkonton för utsedda administratörer, analytiker och utredare kan du konfigurera behörigheter för hantering av insiderrisker i en enda grupp. Den här rollgruppen innehåller alla behörighetsroller för insiderriskhantering. Detta är det enklaste sättet att snabbt komma igång med insider riskhantering och är en bra passform för organisationer som inte behöver separata behörigheter som definierats för separata grupper av användare.|Ärendehantering <br/><br/> Administratör för insiderriskhantering <br/><br/> Analys av insiderriskhantering <br/><br/> Utredning om hantering av insiderrisker <br/><br/> Tillfälligt bidrag från Insiderriskhantering|
|**Administratörer för insiderriskhantering**|Använd den här rollgruppen för att först konfigurera insiderriskhantering och senare för att segregera insiderriskadministratörer till en definierad grupp. Användare i den här rollgruppen kan skapa, läsa, uppdatera och ta bort insiderriskhanteringsprinciper, globala inställningar och rollgruppstilldelningar.|Ärendehantering <br/><br/> Administratör för insiderriskhantering|
|**Analytiker på insiderriskhantering**|Använd den här gruppen om du vill tilldela behörigheter till användare som fungerar som insiderriskfallsanalytiker. Användare i den här rollgruppen kan komma åt alla insiderriskhanteringsaviseringar, ärenden och meddelanden mallar. De kan inte komma åt innehållsutforskaren för insiderrisk.|Ärendehantering <br/><br/> Analys av insiderriskhantering|
|**Utredare av insiderriskhantering**|Använd den här gruppen om du vill tilldela behörigheter till användare som fungerar som insiderriskdatautredare. Användare i den här rollgruppen kan komma åt alla aviseringar om riskhantering för insider, ärenden, meddelanden mallar och Innehållsutforskaren för alla fall.|Ärendehantering <br/><br/> Utredning om hantering av insiderrisker|
|**IRM-bidragsgivare**|Den här rollgruppen är synlig, men används endast av bakgrundstjänster.|Tillfälligt bidrag från Insiderriskhantering|
|**MailFlow-administratör**|Medlemmar kan övervaka och visa insikter och rapporter om e-postflöde i Security & Compliance Center. Globala administratörer kan lägga till vanliga användare i den här gruppen, men om användaren inte är medlem i exchange-administratörsgruppen har användaren inte åtkomst till Exchange-administratörsrelaterade uppgifter.|Endast visningsmottagare|
|**Organisationsledning**<sup>1</sup>|Medlemmar kan styra behörigheter för åtkomst till funktioner i Security & Compliance Center och även hantera inställningar för enhetshantering, dataförlustskydd, rapporter och bevarande. <br/><br/> Observera att för att en användare som inte är global administratör ska kunna se listan över enheter som hanteras av MDM för Microsoft 365 och utföra åtgärder på dessa enheter, till exempel att dra tillbaka en enhet från MDM för Microsoft 365, måste användaren vara Exchange-administratör. <br/><br/> Globala administratörer läggs automatiskt till som medlemmar i den här rollgruppen.|Granskningsloggar <br/><br/> Ärendehantering <br/><br/> Administratör för efterlevnad <br/><br/> Efterlevnadssökning <br/><br/> Enhetshantering <br/><br/> Hantering av DLP-efterlevnad <br/><br/> Hålla <br/><br/> Hantering av efterlevnad av IB <br/><br/> Hantera aviseringar <br/><br/> Organisationskonfiguration <br/><br/> Karantän <br/><br/> RecordManagement (Rekordhantverk) <br/><br/> Hantering av kvarhållning <br/><br/> Rollhantering <br/><br/> Sök och rensa <br/><br/> Säkerhetsadministratör <br/><br/> Säkerhetsläsare <br/><br/> Administratör för känslighetsetikett <br/><br/> Känslighetsetikettläsare <br/><br/> Service assurance-vy <br/><br/> Granskningsloggar med endast visa <br/><br/> Hantering av endast vy-DLP-efterlevnad <br/><br/> Hantering av endast visningsenheter <br/><br/> Hantering av endast visning av IB-efterlevnad <br/><br/> Hantera aviseringar som endast visas <br/><br/> Endast visningsmottagare <br/><br/> Hantering av endast visningspost <br/><br/> Hantering av endast visningsbevarande|
|**Karantänadministratör**|Medlemmar kan komma åt alla karantänåtgärder. Mer information finns i [Hantera meddelanden och filer i karantän som administratör i OEOP](manage-quarantined-messages-and-files.md)|Karantän|
|**Hantering av arkivhandlingar**|Medlemmar kan hantera och avyttra postinnehåll.|RecordManagement (Rekordhantverk)|
|**Granskare**|Medlemmar kan bara visa listan över ärenden på sidan eDiscovery-ärenden i Security & Compliance Center. De kan inte skapa, öppna eller hantera ett eDiscovery-ärende. Det primära syftet med den här rollgruppen är att tillåta medlemmar att visa och komma åt ärendedata i [Avancerad eDiscovery (klassisk)](../../compliance/office-365-advanced-ediscovery.md) (kallas även *Advanced eDiscovery v1*). <br/><br/> Den här rollgruppen har de mest restriktiva eDiscovery-relaterade behörigheterna.<br/><br/>**Obs:** För närvarande kan användare som är medlemmar i rollgruppen Granskare inte komma åt data i [Avancerad eDiscovery i Microsoft 365](../../compliance/overview-ediscovery-20.md) (kallas även *Advanced eDiscovery v2*). Om du vill lägga till medlemmar i ett ärende i Avancerad eDiscovery v2 så att de kan granska ärendedata måste en användare vara medlem i rollgruppen eDiscovery Manager.|Recension|
|**Säkerhetsadministratör**|Medlemmar i den här rollgruppen kan inkludera administratörer över flera tjänster samt externa partnergrupper och Microsoft Support. Som standard kanske den här gruppen inte tilldelas några roller. Det kommer dock att vara medlem i rollen Säkerhetsadministratörer i Azure Active Directory och ärver funktionerna i den rollen. Om du vill hantera behörigheter centralt gör du ändringar i den här rollen i administrationscentret för Active Directory i Azure. Mer information finns [i Administratörsrollbehörigheter i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles). <br/><br/> Om du redigerar den här rollgruppen i Security & Compliance Center gäller dessa ändringar endast för Security & Compliance Center och inte andra tjänster, medan ändringar som görs i Administrationscentret för Azure Active Directory påverkar alla tjänster. <br/><br/> Alla skrivskyddade behörigheter för rollen Säkerhetsläsare, plus ett antal ytterligare administrativa behörigheter för samma tjänster: Azure Information Protection, Identity Protection Center, Privileged Identity Management, Monitor Microsoft 365 Service Health och Security & Compliance Center.|Granskningsloggar <br/><br/> Hantering av DLP-efterlevnad <br/><br/> Enhetshantering <br/><br/> Hantering av efterlevnad av IB <br/><br/> Hantera aviseringar <br/><br/> Karantän <br/><br/> Säkerhetsadministratör <br/><br/> Administratör för känslighetsetikett <br/><br/> Granskningsloggar med endast visa <br/><br/> Hantering av endast vy-DLP-efterlevnad <br/><br/> Hantering av endast visningsenheter <br/><br/> Hantering av endast visning av IB-efterlevnad <br/><br/> Hantera aviseringar som endast visas|
|**Säkerhetsoperatör**|Medlemmar kan hantera säkerhetsaviseringar och även visa rapporter och inställningar för säkerhetsfunktioner.|Efterlevnadssökning <br/><br/> Hantera aviseringar <br/><br/> Säkerhetsläsare <br/><br/> Granskningsloggar med endast visa <br/><br/> Hantering av endast vy-DLP-efterlevnad <br/><br/> Hantering av endast visningsenheter <br/><br/> Hantering av endast visning av IB-efterlevnad <br/><br/> Hantera aviseringar som endast visas|
|**Säkerhetsläsare**|Medlemmar har skrivskyddad åtkomst till ett antal säkerhetsfunktioner i Identity Protection Center, Privileged Identity Management, Monitor Microsoft 365 Service Health och Security & Compliance Center. <br/><br/> Medlemskap i den här rollgruppen synkroniseras mellan tjänster och hanteras centralt. Medlemmar i den här rollgruppen kan inkludera administratörer över flera tjänster samt externa partnergrupper och Microsoft Support. Som standard kanske den här gruppen inte tilldelas några roller. Den kommer dock att vara medlem i rollen Säkerhetsläsare i Azure Active Directory och ärver funktionerna i den rollen. Om du vill hantera behörigheter centralt kan du göra ändringar i den här rollen i Administrationscentret för Azure Active Directory – mer information finns [i Administratörsrollbehörigheter i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles). Om du redigerar den här rollgruppen i Security & Compliance Center gäller dessa ändringar endast för Security & Compliance Center och inte andra tjänster, medan ändringar som görs i Administrationscentret för Azure Active Directory påverkar alla tjänster|Säkerhetsläsare <br/><br/> Känslighetsetikettläsare <br/><br/> Hantering av endast vy-DLP-efterlevnad <br/><br/> Hantering av endast visningsenheter <br/><br/> Hantering av endast visning av IB-efterlevnad <br/><br/> Hantera aviseringar som endast visas|
|**Användare av Service Assurance**|Medlemmar kan komma åt avsnittet Service assurance i Security & Compliance Center. Service assurance innehåller rapporter och dokument som beskriver Microsofts säkerhetspraxis för kunddata som lagras i Microsoft 365. Det ger också oberoende granskningsrapporter från tredje part om Microsoft 365. Mer information finns [i Service assurance i Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/service-assurance).|Service assurance-vy|
|**Översyn av tillsyn**|Medlemmar kan skapa och hantera de principer som definierar vilka meddelanden som ska granskas i en organisation. Mer information finns i [Konfigurera principer för kommunikationsefterlevnad för din organisation](../../compliance/communication-compliance-configure.md).|Administratör för tillsynsgranskning|
|

> [!NOTE]
> <sup>1.</sup> Den här rollgruppen tilldelar inte medlemmarna de behörigheter som krävs för att söka i granskningsloggen eller för att använda rapporter som kan innehålla Exchange-data, till exempel DLP- eller ATP-rapporterna. Om du vill söka i granskningsloggen eller visa alla rapporter måste en användare tilldelas behörigheter i Exchange Online. Detta beror på att den underliggande cmdlet som används för att söka i granskningsloggen är en Exchange Online-cmdlet. Globala administratörer kan söka i granskningsloggen och visa alla rapporter eftersom de automatiskt läggs till som medlemmar i rollgruppen Organisationshantering i Exchange Online. Mer information finns [i Sök i granskningsloggen i Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).

## <a name="roles-in-the-security--compliance-center"></a>Roller i Security & Compliance Center

I följande tabell visas de tillgängliga rollerna och de rollgrupper som de har tilldelats som standard.

Observera att följande roller inte tilldelas rollgruppen Organisationshantering som standard:

- Kommunikation
- Administratör för kommunikationsefterlevnad
- Analys av kommunikationsefterlevnad
- Hantering av ärendehantering för kommunikation
- Undersökning av efterlevnad av kommunikation
- Visningsprogram för kommunikationsefterlevnad
- Vårdnadshavare
- Innehållsvisaren för dataklassificering
- Feedbackleverantör för dataklassificering
- Dataklassificering Feedback Granskare
- Visningsprogram för dataklassificeringslista
- Hantering av datautredningar
- Dispositionshantering
- Exportera
- Administratör för insiderriskhantering
- Analys av insiderriskhantering
- Utredning om hantering av insiderrisker
- Tillfälligt bidrag från Insiderriskhantering
- Förhandsgranska
- Recension
- RMS dekryptera
- Administratör för tillsynsgranskning

||||
|---|---|---|
|**Roll**|**Beskrivning**|**Standardrollgrupptilldelningar**|
|**Granskningsloggar**|Aktivera och konfigurera granskning för organisationen, visa organisationens granskningsrapporter och exportera sedan rapporterna till en fil.|Organisationshantering <br/><br/> Säkerhetsadministratör|
|**Ärendehantering**|Skapa, redigera, ta bort och kontrollera åtkomsten till eDiscovery-ärenden.|Administratör för efterlevnad <br/><br/> eDiscovery-chef <br/><br/> Hantering av insiderrisk <br/><br/> Administratörer för insiderriskhantering <br/><br/> Analytiker på insiderriskhantering <br/><br/> Utredare av insiderriskhantering <br/><br/> Organisationshantering|
|**Kommunikation**|Hantera all kommunikation med de vårdnadshavare som identifierats i ett avancerat eDiscovery-fall.  Skapa spärra meddelanden, håll upp påminnelser och eskalering till hantering. Spåra förvaringsinstitut bekräftelse av spärra meddelanden och hantera åtkomst till depåhållare portal som används av varje vårdnadshavare i ett fall för att spåra kommunikation för de fall där de identifierades som en förvaringsinstitut.|eDiscovery-chef|
|**Administratör för kommunikationsefterlevnad**|Används för att hantera principer i funktionen Kommunikationsefterlevnad.|Administratör för efterlevnad|
|**Analys av kommunikationsefterlevnad**|Används för att utföra undersökning, reparation av meddelandeöverträdelser i funktionen Kommunikationsefterlevnad. Det går bara att visa metadata för meddelandemeta.|Administratör för efterlevnad|
|**Hantering av ärendehantering för kommunikation**|Används för att komma åt ärenden om kommunikationsefterlevnad.|Administratör för efterlevnad|
|**Undersökning av efterlevnad av kommunikation**|Används för att utföra undersöknings-, reparations- och granskningsfel i funktionen Kommunikationsefterlevnad. Kan visa metadata och meddelande från meddelanden.|Administratör för efterlevnad|
|**Visningsprogram för kommunikationsefterlevnad**|Används för att komma åt rapporter och widgetar i funktionen Kommunikationsefterlevnad.||
|**Administratör för efterlevnad**|Visa och redigera inställningar och rapporter för efterlevnadsfunktioner.|Administratör för efterlevnad <br/><br/> Administratör för efterlevnadsdata <br/><br/> Organisationshantering|
|**Efterlevnadssökning**|Gör sökningar över postlådor och få en uppskattning av resultaten.|Administratör för efterlevnad <br/><br/> Administratör för efterlevnadsdata <br/><br/> eDiscovery-chef <br/><br/> Organisationshantering <br/><br/> Säkerhetsoperatör|
|**Vårdnadshavare**|Identifiera och hantera vårdnadshavare för avancerade eDiscovery-ärenden och använd informationen från Azure Active Directory och andra källor för att hitta datakällor som är associerade med vårdnadshavare. Associera andra datakällor som postlådor, SharePoint-webbplatser och Teams med vårdnadshavare i ett ärende.  Placera en juridisk spärr på de datakällor som är associerade med vårdnadshavare för att bevara innehållet i samband med ett ärende.|eDiscovery-chef|
|**Innehållsvisaren för dataklassificering**|Visa återgivning på plats av filer i Innehållsutforskaren.|Innehållsvisaren för innehållsutforskare|
|**Feedbackleverantör för dataklassificering**|Gör det möjligt att ge feedback till klassificerare i innehållsutforskaren.|Administratör för efterlevnad|
|**Dataklassificering Feedback Granskare**|Gör det möjligt att granska feedback från klassificerare i feedback explorer.|Administratör för efterlevnad|
|**Visningsprogram för dataklassificeringslista**|Visa listan över filer i innehållsutforskaren.|Visa loggning för innehållsutforskaren|
|**Hantering av datautredningar**|Skapa, redigera, ta bort och kontrollera åtkomsten till dataundersökningar.|Administratör för efterlevnad <br/><br/> Data Utredare|
|**Enhetshantering**|Visa och redigera inställningar och rapporter för enhetshanteringsfunktioner.|Administratör för efterlevnad <br/><br/> Administratör för efterlevnadsdata <br/><br/> Organisationshantering <br/><br/> Säkerhetsadministratör|
|**Dispositionshantering**|Kontrollbehörigheter för åtkomst till manuell disposition i Security & Compliance Center.|Administratör för efterlevnad <br/><br/> Administratör för efterlevnadsdata|
|**Hantering av DLP-efterlevnad**|Visa och redigera inställningar och rapporter för DLP-principer (Data Loss Prevention).|Administratör för efterlevnad <br/><br/> Administratör för efterlevnadsdata <br/><br/> Organisationshantering <br/><br/> Säkerhetsadministratör|
|**Exportera**|Exportera postlåda och webbplatsinnehåll som returneras från sökningar.|eDiscovery-chef|
|**Hålla**|Placera innehåll i postlådor, webbplatser och gemensamma mappar. När det är spärrat lagras en kopia av innehållet på en säker plats. Innehållsägare kan fortfarande ändra eller ta bort det ursprungliga innehållet.|Administratör för efterlevnad <br/><br/> eDiscovery-chef <br/><br/> Organisationshantering|
|**Hantering av efterlevnad av IB**|Visa, skapa, ta bort, ändra och testa principer för informationsbarriär.|Administratör för efterlevnad <br/><br/> Administratör för efterlevnadsdata <br/><br/> Organisationshantering <br/><br/> Säkerhetsadministratör|
|**Administratör för insiderriskhantering**|Skapa, redigera, ta bort och kontrollera åtkomsten till insiderriskhanteringsfunktionen.|Hantering av insiderrisk <br/><br/> Administratörer för insiderriskhantering|
|**Analys av insiderriskhantering**|Få tillgång till alla åtkomstberedskap, ärenden och meddelanden mallar.|Hantering av insiderrisk <br/><br/> Analytiker på insiderriskhantering|
|**Utredning om hantering av insiderrisker**|Få tillgång till alla varningar om hantering av insiderrisker, ärenden, meddelanden mallar och Content Explorer för alla fall.|Hantering av insiderrisk <br/><br/> Utredare av insiderriskhantering|
|**Tillfälligt bidrag från Insiderriskhantering**|Den här rollgruppen är synlig, men används endast av bakgrundstjänster.|IRM-bidragsgivare|
|**Hantera aviseringar**|Visa och redigera inställningar och rapporter för aviseringar.|Administratör för efterlevnad <br/><br/> Administratör för efterlevnadsdata <br/><br/> Organisationshantering <br/><br/> Säkerhetsadministratör <br/><br/> Säkerhetsoperatör|
|**Organisationskonfiguration**|Kör, visa och exportera granskningsrapporter och hantera efterlevnadsprinciper för DLP, enheter och bevarande.|Administratör för efterlevnad <br/><br/> Administratör för efterlevnadsdata <br/><br/> Organisationshantering|
|**Förhandsgranska**|Visa en lista över objekt som returneras från innehållssökningar och öppna varje objekt från listan för att visa dess innehåll.|eDiscovery-chef|
|**Karantän**|Gör det möjligt att visa och släppa e-post i karantän.|Karantänadministratör <br/><br/> Säkerhetsadministratör <br/><br/> Organisationshantering|
|**RecordManagement (Rekordhantverk)**|Visa och redigera konfigurationen och rapporterna för funktionen Posthantering.|Administratör för efterlevnad <br/><br/> Administratör för efterlevnadsdata <br/><br/> Organisationshantering <br/><br/> Hantering av arkivhandlingar|
|**Hantering av kvarhållning**|Hantera bevarandeprinciper.|Administratör för efterlevnad <br/><br/> Administratör för efterlevnadsdata <br/><br/> Organisationshantering|
|**Recension**|Använd Avancerad eDiscovery för att spåra, tagga, analysera och testa dokument som har tilldelats dem.|eDiscovery-chef <br/><br/> Granskare|
|**RMS dekryptera**|Dekryptera RMS-skyddat innehåll när du exporterar sökresultat.|eDiscovery-chef|
|**Rollhantering**|Hantera rollgruppsmedlemskap och skapa eller ta bort anpassade rollgrupper.|Organisationshantering|
|**Sök och rensa**|Gör det möjligt för personer att ta bort data som matchar villkoren för en innehållssökning.|Organisationshantering|
|**Säkerhetsadministratör**|Visa och redigera konfigurationen och rapporterna för säkerhetsfunktioner.|Organisationshantering <br/><br/> Säkerhetsadministratör|
|**Säkerhetsläsare**|Visa konfiguration och rapporter för säkerhetsfunktioner.|Organisationshantering <br/><br/> Säkerhetsoperatör <br/><br/> Säkerhetsläsare|
|**Administratör för känslighetsetikett**|Visa, skapa, ändra och ta bort känslighetsetiketter.|Administratör för efterlevnadsdata <br/><br/> Organisationshantering <br/><br/> Säkerhetsadministratör|
|**Känslighetsetikettläsare**|Visa konfiguration och användning av känslighetsetiketter.|Global läsare <br/><br/> Organisationshantering <br/><br/> Säkerhetsläsare|
|**Service assurance-vy**|Ladda ned tillgängliga dokument från avsnittet Service Assurance. Innehållet innehåller oberoende granskning, efterlevnadsdokumentation och förtroenderelaterad vägledning för att använda Microsoft 365-funktioner för att hantera regelefterlevnad och säkerhetsrisker.|Användare av Service Assurance <br/><br/> Organisationshantering|
|**Administratör för tillsynsgranskning**|Hantera riktlinjer för tillsynsgranskning, inklusive vilka meddelanden som ska granskas och vem som ska utföra granskningen.|Översyn av tillsyn|
|**Granskningsloggar med endast visa**|Visa och exportera granskningsrapporter. Eftersom dessa rapporter kan innehålla känslig information bör du bara tilldela den här rollen till personer med ett uttryckligt behov av att visa den här informationen.|Administratör för efterlevnad <br/><br/> Administratör för efterlevnadsdata <br/><br/> Organisationshantering <br/><br/> Säkerhetsadministratör <br/><br/> Säkerhetsoperatör|
|**Hantering av endast visningsenheter**|Visa konfigurationen och rapporterna för enhetshanteringsfunktionen.|Administratör för efterlevnad <br/><br/> Administratör för efterlevnadsdata <br/><br/> Organisationshantering <br/><br/> Säkerhetsadministratör <br/><br/> Säkerhetsoperatör <br/><br/> Säkerhetsläsare|
|**Hantering av endast vy-DLP-efterlevnad**|Visa inställningar och rapporter för DLP-principer (Data Loss Prevention).|Administratör för efterlevnad <br/><br/> Administratör för efterlevnadsdata <br/><br/> Organisationshantering <br/><br/> Säkerhetsadministratör <br/><br/> Säkerhetsoperatör <br/><br/> Säkerhetsläsare|
|**Hantering av endast visning av IB-efterlevnad**|Visa konfigurationen och rapporterna för funktionen Informationsbarriärer.|Administratör för efterlevnad <br/><br/> Administratör för efterlevnadsdata <br/><br/> Organisationshantering <br/><br/> Säkerhetsadministratör <br/><br/> Säkerhetsoperatör <br/><br/> Säkerhetsläsare|
|**Hantera aviseringar som endast visas**|Visa konfigurationen och rapporterna för funktionen Hantera aviseringar.|Säkerhetsadministratör <br/><br/> Säkerhetsoperatör <br/><br/> Säkerhetsläsare <br/><br/> Administratör för efterlevnad <br/><br/> Administratör för efterlevnadsdata <br/><br/> Organisationshantering|
|**Endast visningsmottagare**|Visa information om användare och grupper.|MailFlow-administratör <br/><br/> Administratör för efterlevnad <br/><br/> Administratör för efterlevnadsdata <br/><br/> Organisationshantering|
|**Hantering av endast visningspost**|Visa konfiguration och rapporter för funktionen Posthantering.|Administratör för efterlevnad <br/><br/> Administratör för efterlevnadsdata <br/><br/> Organisationshantering|
|**Hantering av endast visningsbevarande**|Visa konfigurationen och rapporterna för funktionen Bevarandehantering.|Administratör för efterlevnadsdata <br/><br/> Organisationshantering <br/><br/> Administratör för efterlevnad|
|
