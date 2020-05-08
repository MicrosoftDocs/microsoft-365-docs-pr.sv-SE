---
title: Konfigurera Teams med tre skyddsnivåer
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
- M365solutions
ms.custom:
- Ent_Architecture
ms.assetid: 1d51bd87-17bf-457c-b698-61821de3afa0
description: Konfigurationsrekommendationer för att skydda filer i Microsoft Teams.
ms.openlocfilehash: 129baed3286e445b9e0e440d4ec7f7a3402d3305
ms.sourcegitcommit: 9c828bc27cd73a1bb85e9fe38d818190025ebb3f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2020
ms.locfileid: "44159437"
---
# <a name="configure-teams-with-three-tiers-of-protection"></a>Konfigurera Teams med tre skyddsnivåer

Artikeln i den här serien får du rekommendationer för att konfigurera team i Microsoft Teams och samhörande SharePoint-webbplatser för filskydd som balanserar säkerhet med smidigt samarbete.

I den här artikeln definieras fyra olika konfigurationer, och först ut är ett offentligt team med de delningsprinciper som är mest öppna. Varje ytterligare konfiguration representerar en meningsfull upptrappning av skyddet, samtidigt som möjligheten att komma åt och samarbeta i filer som lagrats i team begränsas till den relevanta uppsättningen av teammedlemmar. 

Konfigurationerna i den här artikeln överensstämmer med Microsofts rekommendationer för tre skyddsnivåer för data, identiteter och enheter:

- Grundskydd

- känsligt skydd

- Strikt känsligt skydd

Mer information om nivåerna och de funktioner som rekommenderas för varje nivå finns i följande resurser.

- [Identitets- och enhetsskydd för Office 365](https://docs.microsoft.com/office365/enterprise/microsoft-cloud-it-architecture-resources#identity-and-device-protection-for-office-365)

- [Lösningar för filskydd i Office 365](https://docs.microsoft.com/office365/enterprise/microsoft-cloud-it-architecture-resources#file-protection-solutions-in-office-365)

## <a name="three-tiers-at-a-glance"></a>En snabb titt på tre nivåer

I tabellen nedan sammanfattas konfigurationerna för respektive nivå. Använd de här konfigurationerna som utgångspunkt och justera konfigurationerna efter behoven i din organisation. Du kanske inte behöver alla nivåer.

||**Grundläggande (offentlig)**|**Grundläggande (privat)**|**Känslig**|**Strikt känsligt**|
|:-----|:-----|:-----|:-----|:-----|
|Privat eller offentligt team|Offentlig|Privat|Privat|Privat|
|Vem har åtkomst?|Alla i organisationen, t. ex. B2B-användare.|Endast teammedlemmar. Andra kan begära åtkomst till den associerade webbplatsen.|Endast teammedlemmar.|Endast teammedlemmar.|
|Privata kanaler|Ägare och medlemmar kan skapa privata kanaler|Ägare och medlemmar kan skapa privata kanaler|Endast ägare kan skapa privata kanaler|Endast ägare kan skapa privata kanaler|
|Gäståtkomst på webbplatsnivå|**Nya och befintliga gäster** (standard)|**Nya och befintliga gäster** (standard)|**Nya och befintliga gäster** eller **bara personer i din organisation** beroende på teambehov.|**Nya och befintliga gäster** eller **bara personer i din organisation** beroende på teambehov.|
|Inställningar för webbplatsdelning|**Webbplatsägare och medlemmar, och personer med redigeringsbehörighet kan dela filer och mappar, men endast webbplatsägare kan dela webbplatsen**.|**Webbplatsägare och medlemmar, och personer med redigeringsbehörighet kan dela filer och mappar, men endast webbplatsägare kan dela webbplatsen**.|**Webbplatsägare och medlemmar, och personer med redigeringsbehörighet kan dela filer och mappar, men endast webbplatsägare kan dela webbplatsen**.|**Endast webbplatsägare kan dela filer, mappar och webbplatsen**.<br>Åtkomstförfrågningar **Av**.|
|Åtkomst på ohanterad enhet för webbplatsnivå|**Full åtkomst från skrivbordsappar, mobilappar och webb** (standard).|**Full åtkomst från skrivbordsappar, mobilappar och webb** (standard).|**Tillåt begränsad, webbaserad åtkomst**.|**Blockera åtkomst**.|
|Standardtyp för delningslänk|**Endast personer i organisationen**|**Endast personer i organisationen**|**Särskilda personer**|**Personer med åtkomst**|
|Känslighetsetiketter|Inga|Inga|Känslighetsetikett som används för att klassificera teamet och styra gästdelning och ohanterad enhetsåtkomst.|Känslighetsetikett som används för att klassificera teamet och styra gästdelning och ohanterad enhetsåtkomst. Etikett kan också användas på filer för att kryptera filer.|

En variant av det strikt känsliga alternativet [Teams med säkerhetsisolering](secure-teams-security-isolation.md) använder en unik känslighetsetikett för ett team, vilket ger ytterligare säkerhet. Du kan använda den här etiketten för att kryptera filer och bara medlemmar i teamet kan läsa dem.

Grundskyddet omfattar offentliga och privata team. Offentliga team kan upptäckas och användas av alla i organisationen. Privata team kan bara identifieras och användas av medlemmar i teamet. Båda dessa konfigurationer begränsar delning av den associerade SharePoint-webbplatsen till teamägare för att hjälpa till med hantering av behörigheter.

Team för känsligt och mycket känsligt skydd är privata team där delning och förfrågningar om åtkomst för den associerade webbplatsen är begränsade och känslighetsetiketter används för att ange principer för gästdelning, enhetsåtkomst och innehållskryptering.

## <a name="sensitivity-labels"></a>Känslighetsetiketter

Nivåerna känsligt och strikt känsligt använder känslighetsetiketter för att skydda teamet och dess filer. För att implementera dessa nivåer måste du aktivera [känslighetsetiketter för att skydda innehåll i Microsoft Teams, Office 365-grupper och SharePoint-webbplatser](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).

Medan grundnivån inte kräver känslighetsetiketter kan du överväga att skapa en "allmän" etikett och sedan begära att alla grupper har etiketter. På så sätt ser du till att användarna kan välja känsligheten när de skapar ett team. Om du planerar att distribuera nivåerna känsligt och strikt känsligt rekommenderar vi att du skapar en allmän etikett som du kan använda för team på grundnivån och för filer som inte är känsliga.

Om du är nybörjare inför att använda känslighetsetiketter rekommenderar vi att du läser [kom igång med känslighetsetiketter](https://docs.microsoft.com/microsoft-365/compliance/get-started-with-sensitivity-labels) för att komma igång. 

Om du redan har rullat ut känslighetsetiketter i din organisation bör du fundera på hur etiketterna som används i nivåerna känsligt och strikt känsligt passar med din övergripande etikettstrategi. 

## <a name="sharing-the-sharepoint-site"></a>Dela SharePoint-webbplatsen.

Varje team har en associerad SharePoint-webbplats där dokument lagras. (Det här är fliken **filer** i en Teams-kanal.) SharePoint-webbplatsen behåller sin egen behörighetshantering, men är länkad till teambehörigheter. Teamägare medföljer som webbplatsägare och teammedlemmar tas med som webbplatsmedlemmar i den associerade webbplatsen.

De resulterande behörigheterna tillåter följande:

- Teamägare kan administrera webbplatsen och har fullständig kontroll över webbplatsens innehåll.
- Teammedlemmar kan skapa och redigera filer på webbplatsen. 

Som standard kan teamägare och medlemmar dela webbplatsen med personer utanför teamet utan att lägga till dem i teamet. Vi rekommenderar inte detta eftersom det komplicerar användarhantering och kan leda till att personer som inte är teammedlemmar har tillgång till teamfiler utan att teamägare inser det. För att förhindra detta med början från grundnivån av skydd, rekommenderar vi att endast ägare får dela webbplatsen direkt.

Även om det inte finns något alternativ för skrivskydd i Teams, har SharePoint-webbplatsen det. Om du har intressenter i partnergrupper som behöver kunna se teamfiler men inte redigera dem, överväg att lägga till dem direkt till SharePoint-webbplatsen med läsbehörigheter.

## <a name="sharing-files-and-folders"></a>Dela filer och mappar

Som standard kan både ägare och medlemmar i teamet dela filer och mappar med personer utanför teamet. Detta kan inkludera personer utanför din organisation om du har tillåtet gästdelning. I alla tre nivåer uppdaterar vi standardtypen för delningslänkar för att undvika oavsiktlig överdelning. I nivån strikt känsligt begränsar vi sådan delning till teamägare.

## <a name="guest-sharing"></a>Gästdelning

Om du vill samarbeta med personer utanför organisationen rekommenderar vi att du konfigurerar [SharePoint-och OneDrive-integrering med Azure AD B2B](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview) för bästa delnings- och administrationsupplevelse.

Gästdelning i Teams är inaktiverat som standard, men delning för Office 365-grupper (där teammedlemskap lagras) och SharePoint är aktiverat. Vi aktiverar delning i Teams på grundnivån, och du kan stänga av den om det behövs i nivåerna känsligt och strikt känsligt genom att använda en känslighetsetikett.

Känslighetsetiketten påverkar bara gästdelning för teamet. Inställningar för gästdelning för den associerade SharePoint-webbplatsen styrs separat och vi har justerat de två inställningarna för nivåerna känsligt och strikt känsligt.

I nivån strikt känsligt konfigurerar vi känsligheten för att kryptera de filer som de används i. Om du vill att gäster ska få tillgång till dessa filer måste du ge dem behörighet när du skapar etiketten.

Vi rekommenderar starkt att du lämnar gästdelning för grundnivån och för nivåerna känsligt och strikt känsligt om du behöver samarbeta med personer utanför din organisation. Med funktionerna för gästdelning i Microsoft 365 får du en mycket säkrare och mer styrd delning än att skicka filer som bifogade filer i e-postmeddelanden. Det minskar också risken för skuggad IT där användarna använder sig av okontrollerade konsumentprodukter för att dela med legitima externa medarbetare.

Se följande referenser för att skapa en säker och produktiv gästdelningsmiljö för din organisation:

- [Metodtips för att dela filer och mappar med oautentiserade användare](best-practices-anonymous-sharing.md)
- [Begränsa oavsiktlig exponering för filer när de delas med personer utanför organisationen](share-limit-accidental-exposure.md)
- [Skapa en säker miljö för gästdelning](create-secure-guest-sharing-environment.md)

## <a name="access-from-unmanaged-devices"></a>Åtkomst från ohanterade enheter

För nivåerna känsligt och strikt känsligt begränsar vi åtkomst till SharePoint-innehåll med känslighetsetiketter. Med villkorad åtkomst i Azure AD finns många alternativ för att bestämma hur användare får åtkomst till Microsoft 365, inklusive begränsningar utifrån plats, risker, kompatibilitetsstatus för enheter och andra faktorer. Vi rekommenderar att du läser [Vad är villkorad åtkomst?](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) och fundera på vilka tilläggsprinciper som passar bäst för din organisation.

## <a name="next-step"></a>Nästa steg

Börja med [att konfigurera grundnivån för skydd](configure-teams-baseline-protection.md). Om det behövs kan du lägga till [känsligt skydd](configure-teams-sensitive-protection.md) och [strikt känsligt skydd](configure-teams-highly-sensitive-protection.md) ovanpå grundnivån.

## <a name="see-also"></a>Se även

[Säkerhet och efterlevnad för Microsoft Teams](https://docs.microsoft.com/microsoftteams/security-compliance-overview)

[Aviseringsregler i säkerhets- och efterlevnadscentret](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)
