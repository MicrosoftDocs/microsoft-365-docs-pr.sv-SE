---
title: Konfigurera säkerhet samarbete med hjälp av Microsoft 365
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-securecollab
- m365solution-overview
ms.custom:
- M365solutions
- seo-marvel-jun2020
f1.keywords: NOCSH
description: Lär dig konfigurera säkert innehållssamarbete i Teams för att skydda dina data utifrån dess känslighet.
ms.openlocfilehash: 804307b3035f0d2246dc0ac541cce2d63506c351
ms.sourcegitcommit: e0a96e08b7dc29e074065e69a2a86fc3cf0dad01
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/06/2021
ms.locfileid: "51591916"
---
# <a name="set-up-secure-collaboration-with-microsoft-365-and-microsoft-teams"></a>Konfigurera säkert samarbete med Microsoft 365 och Microsoft Teams

Att enkelt kunna dela information med rätt personer och förhindra att det går över är avgörande för en organisations framgång. Det handlar bland annat om att dela känsliga data på ett säkert sätt med bara de som ska ha tillgång till dem. Beroende på projektet kan det till exempel vara att dela känsliga data med personer utanför organisationen.

Vägledningen för samarbetslösningen består av två komponenter som hjälper dig:
- Distribuera Microsoft Teams med rätt skyddsnivå för varje projekt
- Konfigurera extern delning med lämpliga säkerhetsinställningar för varje projekt

![Distribuera Teams med lämpligt skydd och konfigurera extern delning med lämpliga säkerhetsinställningar](..\media\solutions-architecture-center\secure-collaboration-overview.png)

Om mångsidiga och lättanvända verktyg för innehållssamarbete inte finns tillgängliga kan användarna ofta samarbeta genom att skicka dokument via e-post. Det här är en omedveten och felbeägen samarbetsmetod och kan öka risken för olämplig delning av information. Om personer tycker att det är svårt att dela information kan de återgå till att använda konsumentprodukter som inte styrs av IT.. Det kan innebära en ännu större risk.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWxMmL?autoplay=false]

Med Microsoft 365 kan du distribuera Teams med en mängd olika konfigurationer som hjälper:

- Skydda din immateriella egendom
- Möjliggör enkelt samarbete
- Skapa en balans mellan säkerhet och användbarhet som ökar användarnöjdheten och minskar risken för skuggad IT

De flesta organisationer har en mängd information, med varierande känslighet och olika grader av påverkan på verksamheten om informationen delas olämpligt. Beroende på hur känslig en viss informationsbit är kanske du vill tillåta delning med:

- Alla (oauthenticerade)
- Personer inom organisationen
- Vissa personer i organisationen
- Vissa personer inom och utanför organisationen

Information som marknadsföringsbroschyrer är avsedda att delas brett utanför organisationen. Information som snabbmenyer är inte avsedda för extern delning, men skulle inte ha någon inverkan på verksamheten om de delades externt. Den här typen av information behöver ett litet eller inget skydd.

Samma marknadsföringsbroschyrer, under utveckling, kanske endast delas inom organisationen. I så fall kanske standardinställningarna för delning i Teams är tillräckliga.

Information om en ny produkt som är under utveckling kan ses som känslig, även inom organisationen. I det här fallet kan det vara lämpligt med ett bättre skydd. Du kan till exempel begränsa åtkomsten till den här informationen till medlemmar i ett visst team. Beroende på projektet kan du behöva samarbeta med personer utanför organisationen, till exempel en leverantörs- eller partnerorganisation.

Information som är avgörande för organisationens framgång eller som har strikta säkerhets- eller efterlevnadskrav kan kräva ännu högre skyddsnivåer.

![Riskskala från låg (utgiven broschyr) till hög (känsliga affärsdata)](../media/solutions-architecture-center/SecureCollaboration-SensitivityAndBusinessImpactofSharing-fromVisio.png)

För alla scenarier som anges ovan kan du använda team i Microsoft Teams för att lagra, dela och samarbeta med informationen. 

Om du vill konfigurera säkert samarbete använder du dessa Funktioner och funktioner i Microsoft 365.

| Produkt eller komponent | Resurs eller funktion | Licensiering |
|:-------|:-----|:-------|
| Microsoft Defender för Office 365 | Säkra bifogade filer för SPO, OneDrive och Teams; Säkra dokument Säkra länkar för Teams    | Microsoft 365 E1, E3 och E5 |
| SharePoint    | Principer för webbplats- och fildelning, webbplatsdelningsbehörigheter, delningslänkar, åtkomstförfrågningar, webbplats gästdelningsinställningar | Microsoft 365 E1, E3 och E5 |
| Microsoft Teams   | Gäståtkomst, privata team, privata kanaler | Microsoft 365 E1, E3 och E5 |
| Microsoft 365 Efterlevnad  | Känslighetsetiketter    | Microsoft 365 E3 och E5 |

### <a name="collaboration-governance"></a>Samarbetsstyrning

Microsoft 365 innehåller många alternativ för att styra din samarbetslösning. Vi rekommenderar att du använder det här distributionsinnehållet tillsammans med [innehållet med samarbetsstyrning](collaboration-governance-overview.md) för att skapa den bästa samarbetslösningen för din organisation.

### <a name="using-teams-for-all-kinds-of-data"></a>Använda Teams för alla typer av data

För att hantera åtkomst till information med olika känsligheter har vi utvecklat tre olika nivåer [av skydd för Teams.](configure-teams-three-tiers-protection.md) Du kan anpassa någon av dessa nivåer för att bättre tillgodose behoven eller verksamheten. 

![Bild av tre skyddsnivåer för Teams](../media/solutions-architecture-center/Teams-tiers-of-protection-1.png)


Dessa nivåer –  *baslinje,* känslig och mycket känslig *–* ökar gradvis skyddet för att förhindra att det uppstår för mycket och potentiellt informationsläckor, som visas i följande tabell.

|-|**Baslinjenivå**|**Känslig nivå**|**Högkänslig nivå**|
|:--|:-----------|:------------|:-------------------|
|Offentligt eller privat team|Antingen|Privat|Privat|
|Oautentiserad delning|Blockerad|Blockerad|Blockerad|
|Fildelning|Tillåten|Tillåten|Endast teamägare kan dela.|
|Teammedlemskap|Vem som helst kan gå med i offentliga team.<br>Godkännande av teamägare krävs för att gå med i privata team.|Godkännande av gruppägare krävs för att gå med.|Godkännande av gruppägare krävs för att gå med.|
|Dokumentkryptering|||Tillgänglig med känslighetsetikett|
|Gästdelning|Tillåten|Kan tillåtas eller blockeras|Kan tillåtas eller blockeras|
|Ohanterade enheter|Ingen begränsning|Endast webbåtkomst|Blockerad|

Konfigurering av dessa nivåer omfattar:

- Konfigurera inställningar i Teams för gäståtkomst och privata kanaler
- Konfigurera inställningar på en grupps associerade SharePoint-webbplats för intern delning och gästdelning, åtkomstförfrågningar och delningslänkar
- För känsliga *och* *mycket känsliga nivåer,* konfigurera känslighetsetiketter för att klassificera teamen och kontrollera gästdelning och åtkomst från ohanterade enheter
- För den *mycket känsliga* nivån konfigurerar du en känslighetsetikett för att kryptera de dokument den tillämpas på

Börja med baslinjenivån och lägg sedan  till  team som använder känslig och mycket känslig nivå för att skydda informationen i organisationen. Se följande resurser för att komma igång:

- [Konfigurera teams med grundläggande skydd](configure-teams-baseline-protection.md)
- [Konfigurera team med skydd för känslig data](configure-teams-sensitive-protection.md)
- [Konfigurera team med skydd för mycket känslig data](configure-teams-highly-sensitive-protection.md)

Om du har ett mycket känsligt projekt som kräver ytterligare skydd mot delning även inom organisationen kan du konfigurera ett team som använder en egen känslighetsetikett för att kryptera filer så att bara teammedlemmar kan läsa dem. Mer [information finns i Konfigurera ett team med](secure-teams-security-isolation.md) säkerhetsisolering.

### <a name="sharing-with-people-outside-your-organization"></a>Dela med personer utanför organisationen

Du kan behöva [dela information om känsligheten med personer utanför din organisation](collaborate-with-people-outside-your-organization.md). Det kan vara allt från att dela ett dokument med en enskild person till att samarbeta i ett större projekt med en stor partnerorganisation eller med medarbetare från hela världen. I Microsoft 365 kan detta intervall av extern delning göras enkelt och med lämpliga säkerhetsåtgärder för att skydda känslig information.

De här resurserna hjälper dig att komma igång med att konfigurera din miljö för samarbete med personer utanför organisationen:

- [Samarbeta i dokument](collaborate-on-documents.md) för att dela enskilda filer med mappar.
- [Samarbeta på en webbplats](collaborate-in-site.md) för att samarbeta med gäster på en SharePoint-webbplats.
- [Samarbeta som ett team](collaborate-as-team.md) för att samarbeta med gäster i ett team.

Beroende på hur känslig informationen är kan du lägga till säkerhetsåtgärder för att förhindra att en för stor del delas. Med de här resurserna kan du konfigurera de skydd du behöver för organisationen:

- [Metodtips för att dela filer och mappar med oautentiserade användare](best-practices-anonymous-sharing.md)
- [Begränsa oavsiktlig exponering för filer när de delas med personer utanför organisationen](share-limit-accidental-exposure.md)
- [Skapa en säker miljö för gästdelning](create-secure-guest-sharing-environment.md)

Om du har ett större projekt med en partnerorganisation kan du använda hantering av Azure-berättigande till att hantera gäster från den organisationen i ett team som du har ställt in för projektet. Mer [information finns i Skapa ett B2B-extranät med](b2b-extranet.md) hanterade gäster.



## <a name="training-for-administrators"></a>Utbildning för administratörer

Dessa utbildningsmoduler från Microsoft Learn kan hjälpa dig att lära dig mer om funktionerna för samarbete, styrning och identitet i Teams och SharePoint.

#### <a name="teams"></a>Teams

|Utbildning:|Hantera teamsamarbete med Microsoft Teams|
|:---|:---|
|![Utbildningsikon för Teams-samarbete](../media/manage-team-collaboration-with-microsoft-teams.svg)|I Hantera teamsamarbete med Microsoft Teams introduceras funktioner i Microsoft Teams, det centrala navet för teamsamarbete i Microsoft 365. Du får lära dig hur du kan använda Teams för att underlätta samarbete och kommunikation inom organisationen, både lokalt och på en rad olika enheter, från datorer till surfplattor och telefoner, samtidigt som du utnyttjar alla funktionerna i Office 365-programmen. Du får en förståelse för hur Teams tillhandahåller en omfattande och flexibel miljö för samarbete mellan program och enheter. Den här utbildningsvägen kan hjälpa dig att förbereda för Microsoft 365 Certified: Teams Administrator Associate-certifiering.<br><br>2 t 17 min - Utbildningsväg - 5 moduler|

> [!div class="nextstepaction"]
> [Starta >](/learn/modules/m365-teams-collab-prepare-deployment/introduction/)

#### <a name="sharepoint"></a>SharePoint

|Utbildning:|Samarbeta med SharePoint i Microsoft 365|
|:---|:---|
|![SharePoint-utbildningsikon](../media/collaborate-with-sharepoint-in-microsoft-365.svg)|I Hantera delat innehåll med Microsoft SharePoint introduceras funktioner och funktioner i SharePoint, och hur det fungerar med Microsoft 365. Du får lära dig mer om de olika typerna av SharePoint-webbplatser, inklusive navplatser, samt informationsskydd, rapportering och övervakning. Du får också lära dig hur du använder fil- och mappdelning i SharePoint för att optimera samarbete, dela filer externt och hur du hanterar SharePoint-webbplatser i administrationscentret för SharePoint. Den här utbildningsvägen kan hjälpa dig att förbereda för certifieringen Microsoft 365 Certified: Teamwork Administrator Associate.<br><br>1 t 14 min - Utbildningsväg - 4 moduler|

> [!div class="nextstepaction"]
> [Starta >](/learn/modules/m365-teams-sharepoint-plan-sharepoint/introduction/)

#### <a name="information-protection"></a>Informationsskydd

|Utbildning:|Skydda företagsinformation med Microsoft 365|
|:---|:---|
|![Utbildningsikon för Teams infoskydd](../media/protect-enterprise-information-microsoft-365.svg)|Det är svårare än någonsin att skydda och skydda organisationens information. I utbildningsvägen Skydda företagsinformation med Microsoft 365 diskuteras hur du skyddar känslig information från att oavsiktligt skriva över eller felaktigt använda data, hur du identifierar och klassificerar data, hur du skyddar dem med känslighetsetiketter och hur du både övervakar och analyserar din känsliga information för att skydda mot förlust. Den här utbildningsvägen kan hjälpa dig att förbereda för Microsoft 365 Certified: Security Administrator Associate och Microsoft 365 Certified: Enterprise Administration Expert-certifieringar.<br><br>1 t - Utbildningsväg - 5 moduler|

> [!div class="nextstepaction"]
> [Starta >](/learn/modules/m365-security-info-overview/introduction/)

#### <a name="identity-and-access"></a>Identitet och åtkomst

|Utbildning:|Skydda identitet och åtkomst med Azure Active Directory|
|:---|:---|
|![Ikon för identitets- och åtkomstutbildning](../media/protect-identity-and-access-with-microsoft-365.svg)|Utbildningsvägen för identitet och åtkomst omfattar de senaste identitets- och åtkomsttekniker, verktyg för att förstärka autentisering och vägledning om identitetsskydd i organisationen. Med microsofts teknik för åtkomst och identitet kan du skydda organisationens identitet, oavsett om den är lokal eller i molnet, och ge dina användare möjlighet att arbeta säkert från valfri plats. Den här utbildningsvägen kan hjälpa dig att förbereda för Microsoft 365 Certified: Security Administrator Associate och Microsoft 365 Certified: Enterprise Administration Expert-certifieringar.<br><br>2 t 52 min - Utbildningsväg - 6 moduler|

> [!div class="nextstepaction"]
> [Starta >](/learn/modules/m365-identity-overview/introduction/)

## <a name="training-for-end-users"></a>Utbildning för slutanvändare

Dessa utbildningsmoduler kan hjälpa användarna att använda Teams, grupper och SharePoint för samarbete i Microsoft 365.

|Teams|SharePoint|
|:---|:---|
|![Ikon för att konfigurera och anpassa teamets utbildning](../media/set-up-customize-team-training.png)<br>**[Konfigurera och anpassa ditt team](https://support.microsoft.com/office/702a2977-e662-4038-bef5-bdf8ee47b17b)**|![SharePoint-ikon för utbildning om delning och synkronisering](../media/sharepoint-share-sync-training.png)<br>**[Dela och synkronisera](https://support.microsoft.com/office/98cb2ff2-c27e-42ea-b055-c2d895f8a5de)**|
|![Utbildningsikon för att ladda upp och hitta filer i Teams](../media/smc-teams-upload-find-files-training.png)<br>**[Ladda upp och söka efter filer](https://support.microsoft.com/office/57b669db-678e-424e-b0a0-15d19215cb12)**||
|![Ikonen Samarbeta i team och kanaler](../media/teams-collaborate-channels-training.png)<br>**[Samarbeta i team och kanaler](https://support.microsoft.com/office/c3d63c10-77d5-4204-a566-53ddcf723b46)**|||

## <a name="illustrations"></a>Illustrationer

De här illustrationerna hjälper dig att förstå hur grupper och team interagerar med andra tjänster i Microsoft 365 och vilka styrnings- och efterlevnadsfunktioner som är tillgängliga för att hjälpa dig att hantera de här tjänsterna i organisationen.

### <a name="groups-in-microsoft-365-for-it-architects"></a>Grupper i Microsoft 365 för IT-arkitekter
Det IT-arkitekter behöver veta om grupper i Microsoft 365

|**Objekt**|**Beskrivning**|
|:-----|:-----|
|[![Miniatyrbild av infografiken för grupper](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) <br/> [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx) <br> Uppdaterad i juni 2019|De här illustrationerna beskriver de olika typerna av grupper, hur de skapas och hanteras samt några rekommendationer för styrning.|

### <a name="microsoft-teams-and-related-productivity-services-in-microsoft-365-for-it-architects"></a>Microsoft Teams och relaterade produktivitetstjänster i Microsoft 365 för IT-arkitekter
Den logiska arkitekturen för produktivitetstjänster i Microsoft 365, med Microsoft Teams i spetsen.

|**Objekt**|**Beskrivning**|
|:-----|:-----|
|[![Miniatyrbild av affischen för Teams logiska arkitektur](../downloads/msft-teams-logical-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-teams-logical-architecture.pdf) <br/> [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-teams-logical-architecture.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-teams-logical-architecture.vsdx)  <br>Uppdaterad i april 2019   |Microsoft erbjuder ett utbud av produktivitetstjänster som samverkar för att tillhandahålla samarbetsupplevelser med funktioner för datastyrning, säkerhet och efterlevnad. <br/> <br/>Den här serien med illustrationer ger en översikt över produktivitetstjänsternas logiska arkitektur för företagsarkitekter, med Microsoft Teams i spetsen.|

## <a name="deploy-the-secure-collaboration-solution"></a>Distribuera en säker lösning för samarbete

När du är redo att distribuera den här lösningen fortsätter du med följande steg:
1. Konfigurera de [tre olika skyddsnivåerna för Teams](configure-teams-three-tiers-protection.md).
2. Konfigurera inställningar för [att dela information om känsligheten med personer utanför organisationen](collaborate-with-people-outside-your-organization.md).

## <a name="see-also"></a>Se även

[Dokumentation för Microsoft 365 Säkerhetscenter](../security/index.yml)

[Dokumentation för Microsoft 365 Efterlevnadscenter](../compliance/index.yml)

[Välkommen till Microsoft Teams](/MicrosoftTeams/Teams-overview)
