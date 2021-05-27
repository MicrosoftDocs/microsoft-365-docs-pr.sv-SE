---
title: Konfigurera Teams med tre säkerhetsnivåer för delning av filer
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
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
- m365solution-securecollab
- m365solution-scenario
ms.custom:
- Ent_Architecture
- seo-marvel-jun2020
ms.assetid: 1d51bd87-17bf-457c-b698-61821de3afa0
recommendations: false
description: Lär dig hur du konfigurerar Teams för bättre säkerhet vid delning av filer med hjälp av tre skyddsnivåer, och balansera säkerhet med att kunna samarbete enkelt.
ms.openlocfilehash: 34351b202575302e2929db48d7807b91e4308905
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683409"
---
# <a name="configure-teams-with-three-tiers-of-protection"></a>Konfigurera Teams med tre skyddsnivåer

Artikeln i den här serien får du rekommendationer för att konfigurera team i Microsoft Teams och samhörande SharePoint-webbplatser för filskydd som balanserar säkerhet med smidigt samarbete.

I den här artikeln definieras fyra olika konfigurationer, och först ut är ett offentligt team med de delningsprinciper som är mest öppna. Varje ytterligare konfiguration representerar en meningsfull upptrappning av skyddet, samtidigt som möjligheten att komma åt och samarbeta i filer som lagrats i team begränsas till den relevanta uppsättningen av teammedlemmar. 

Konfigurationerna i den här artikeln överensstämmer med Microsofts rekommendationer för tre skyddsnivåer för data, identiteter och enheter:

- Grundskydd

- känsligt skydd

- Strikt känsligt skydd

Mer information om nivåerna och de funktioner som rekommenderas för varje nivå finns i [Microsoft Cloud för Enterprise Architects-illustrationer](./cloud-architecture-models.md)


## <a name="three-tiers-at-a-glance"></a>En snabb titt på tre nivåer

I tabellen nedan sammanfattas konfigurationerna för respektive nivå. Använd de här konfigurationerna som utgångspunkt och justera konfigurationerna efter behoven i din organisation. Du kanske inte behöver alla nivåer.

|-|Grundläggande (offentlig)|Grundläggande (privat)|Känslig|Strikt känsligt|
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

Nivåerna känsligt och strikt känsligt använder känslighetsetiketter för att skydda teamet och dess filer. För att implementera dessa nivåer måste du aktivera [känslighetsetiketter för att skydda innehåll i Microsoft Teams, Office 365-grupper och SharePoint-webbplatser](../compliance/sensitivity-labels-teams-groups-sites.md).

Medan grundnivån inte kräver känslighetsetiketter kan du överväga att skapa en "allmän" etikett och sedan begära att alla grupper har etiketter. På så sätt ser du till att användarna kan välja känsligheten när de skapar ett team. Om du planerar att distribuera nivåerna känsligt och strikt känsligt rekommenderar vi att du skapar en allmän etikett som du kan använda för team på grundnivån och för filer som inte är känsliga.

Om du är nybörjare inför att använda känslighetsetiketter rekommenderar vi att du läser [kom igång med känslighetsetiketter](../compliance/get-started-with-sensitivity-labels.md) för att komma igång. 

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

Om du vill samarbeta med personer utanför organisationen rekommenderar vi att du konfigurerar [SharePoint-och OneDrive-integrering med Azure AD B2B](/sharepoint/sharepoint-azureb2b-integration-preview) för bästa delnings- och administrationsupplevelse.

Gästdelning i Teams är inaktiverat som standard, men delning för Office 365-grupper (där teammedlemskap lagras) och SharePoint är aktiverat. Vi aktiverar delning i Teams på grundnivån, och du kan stänga av den om det behövs i nivåerna känsligt och strikt känsligt genom att använda en känslighetsetikett.

Känslighetsetiketten påverkar bara gästdelning för teamet. Inställningar för gästdelning för den associerade SharePoint-webbplatsen styrs separat och vi har justerat de två inställningarna för nivåerna känsligt och strikt känsligt.

I nivån strikt känsligt konfigurerar vi känsligheten för att kryptera de filer som de används i. Om du vill att gäster ska få tillgång till dessa filer måste du ge dem behörighet när du skapar etiketten.

Vi rekommenderar starkt att du lämnar gästdelning för grundnivån och för nivåerna känsligt och strikt känsligt om du behöver samarbeta med personer utanför din organisation. Med funktionerna för gästdelning i Microsoft 365 får du en mycket säkrare och mer styrd delning än att skicka filer som bifogade filer i e-postmeddelanden. Det minskar också risken för skuggad IT där användarna använder sig av okontrollerade konsumentprodukter för att dela med legitima externa medarbetare.

Se följande referenser för att skapa en säker och produktiv gästdelningsmiljö för din organisation:

- [Metodtips för att dela filer och mappar med oautentiserade användare](best-practices-anonymous-sharing.md)
- [Begränsa oavsiktlig exponering för filer när de delas med personer utanför organisationen](share-limit-accidental-exposure.md)
- [Skapa en säker miljö för gästdelning](create-secure-guest-sharing-environment.md)

## <a name="access-from-unmanaged-devices"></a>Åtkomst från ohanterade enheter

För nivåerna känsligt och strikt känsligt begränsar vi åtkomst till SharePoint-innehåll med känslighetsetiketter. Med villkorad åtkomst i Azure AD finns många alternativ för att bestämma hur användare får åtkomst till Microsoft 365, inklusive begränsningar utifrån plats, risker, kompatibilitetsstatus för enheter och andra faktorer. Vi rekommenderar att du läser [Vad är villkorad åtkomst?](/azure/active-directory/conditional-access/overview) och fundera på vilka tilläggsprinciper som passar bäst för din organisation.

Observera att gäster ofta inte har enheter som hanteras av din organisation. Om du tillåter gäster på någon av nivåerna bör du fundera på vilka typer av enheter de använder för att komma åt grupper och webbplatser och ange principer för ohanterad enhet därefter.

### <a name="control-device-access-across-microsoft-365"></a>Kontrollera enhetsåtkomst i Microsoft 365

Inställningen för ohanterade enheter bland känslighetsetiketterna påverkar bara SharePoint-åtkomst. Om du vill utöka kontrollen av ohanterade enheter så den gäller utanför SharePoint kan du istället [Skapa en villkorsstyrd åtkomstprincip för Azure Active Directory för alla program och tjänster i din organisation](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device). Om du vill konfigurera den här principen specifikt för [Microsoft 365-tjänster](/azure/active-directory/conditional-access/concept-conditional-access-cloud-apps#office-365)ska du välja molnappen för **Office 365** under **Molnappar eller åtgärder**.

![Skärmbild av Office 365-molnappen i en Azure Active Directory-princip för villkorsstyrd åtkomst](https://docs.microsoft.com/sharepoint/sharepointonline/media/azure-ca-office365-policy.png)

En princip som påverkar alla Microsoft 365-tjänster kan leda till bättre säkerhet och en bättre upplevelse för användarna. Om du till exempel blockerar åtkomst till ohanterade enheter i SharePoint kan användarna komma åt chatten i en grupp med en ohanterad enhet, men förlorar åtkomst när de försöker komma åt fliken **Filer**. Med hjälp av Office 365-molnappen undviker du problem med [Tjänstberoenden](/azure/active-directory/conditional-access/service-dependencies).

## <a name="next-step"></a>Nästa steg

Börja med [att konfigurera grundnivån för skydd](configure-teams-baseline-protection.md). Om det behövs kan du lägga till [känsligt skydd](configure-teams-sensitive-protection.md) och [strikt känsligt skydd](configure-teams-highly-sensitive-protection.md) ovanpå grundnivån.

## <a name="see-also"></a>Se även

[Säkerhet och efterlevnad för Microsoft Teams](/microsoftteams/security-compliance-overview)

[Aviseringsregler i säkerhets- och efterlevnadscentret](../compliance/alert-policies.md)
