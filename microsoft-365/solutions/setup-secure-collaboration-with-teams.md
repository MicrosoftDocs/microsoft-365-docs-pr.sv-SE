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
description: Lär dig konfigurera säkert innehållssamarbete i Teams för att skydda dina data baserat på dess känslighet.
ms.openlocfilehash: c92dc6dbf62d3fa0cb00307447b3d5a793830394
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233862"
---
# <a name="set-up-secure-collaboration-with-microsoft-365"></a>Konfigurera säkerhet samarbete med hjälp av Microsoft 365

Att enkelt kunna dela information med rätt personer samtidigt som det förhindrar överorganisation är avgörande för en organisations framgång. Det omfattar att dela känsliga data på ett säkert sätt med bara de som ska ha tillgång till dem. Beroende på projektet kan det t.ex. vara att dela känsliga data med personer utanför organisationen.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWxMmL?autoplay=false]

Vägledningen för samarbetslösningen innehåller två komponenter som kan hjälpa dig:
- Distribuera Microsoft Teams med rätt skyddsnivå för varje projekt
- Konfigurera extern delning med lämpliga säkerhetsinställningar för varje projekt

![Distribuera Teams med lämpligt skydd och konfigurera extern delning med lämpliga säkerhetsinställningar](..\media\solutions-architecture-center\secure-collaboration-overview.png)

Om mångsidiga och lättanvända verktyg för innehållssamarbete inte är tillgängliga kan användarna ofta samarbeta genom att skicka dokument via e-post. Det här är en omedveten och felbeägen samarbetsmetod och kan öka risken för olämplig delning av information. Om personer tycker att det är svårt att dela information kan de återgå till att använda konsumentprodukter som inte styrs av IT. Det kan innebära en ännu större risk.

Med Microsoft 365 kan du distribuera Teams med en mängd olika konfigurationer som hjälper:

- Skydda din immateriella egendom
- Möjliggör enkelt samarbete
- Skapa en balans mellan säkerhet och användbarhet som ökar användarnöjdheten och minskar risken för skuggad IT

De flesta organisationer har en mängd information, med olika känslighetsgrader och olika grader av påverkan på verksamheten, om informationen delas olämpligt. Beroende på hur känslig en viss information är kanske du vill tillåta delning med:

- Alla (oauthenticerade)
- Personer inom organisationen
- Specifika personer i organisationen
- Vissa personer inom och utanför organisationen

Information som marknadsföringsbroschyrer är avsedd att delas brett utanför organisationen. Information som menyer på menyer är inte avsedda för extern delning, men det skulle inte ha någon inverkan på företaget om de delades externt. Den här typen av information behöver lite eller inget skydd.

Samma marknadsföringsbroschyrer, under utveckling, kanske bara delas inom organisationen. I det här fallet kan standardinställningarna för delning i Teams vara tillräckliga.

Information om en ny produkt som är under utveckling kan anses vara känslig, även inom organisationen. I det här fallet kan det vara lämpligt med ett högre skydd. Du kan till exempel begränsa åtkomsten till den här informationen till medlemmar i ett visst team. Beroende på projektet kan du behöva samarbeta med personer utanför organisationen, till exempel en leverantörs- eller partnerorganisation.

Information som är viktig för organisationens framgång eller som har strikta säkerhets- eller efterlevnadskrav kan kräva ännu högre skyddsnivåer.

![Riskskala från låg (utgiven broschyr) till hög (känsliga affärsdata)](../media/solutions-architecture-center/SecureCollaboration-SensitivityAndBusinessImpactofSharing-fromVisio.png)

För alla scenarier som anges ovan kan du använda team i Microsoft Teams för att lagra, dela och samarbeta med informationen. 

Om du vill konfigurera säkert samarbete använder du microsoft 365-funktionerna.

| Produkt eller komponent | Resurs eller funktion | Licensiering |
|:-------|:-----|:-------|
| Microsoft Defender för Office 365 | Säkra bifogade filer för SPO, OneDrive och Teams; Säkra dokument Säkra länkar för Teams    | Microsoft 365 E1, E3 och E5 |
| SharePoint    | Principer för webbplats- och fildelning, webbplatsdelningsbehörigheter, delningslänkar, åtkomstförfrågningar, inställningar för webbplatsgästdelning | Microsoft 365 E1, E3 och E5 |
| Microsoft Teams   | Gäståtkomst, privata team, privata kanaler | Microsoft 365 E1, E3 och E5 |
| Microsoft 365 Efterlevnad  | Känslighetsetiketter    | Microsoft 365 E3 och E5 |

### <a name="using-teams-for-all-kinds-of-data"></a>Använda Teams för alla typer av data

För att hantera åtkomst till information med olika känsligheter har vi utvecklat [tre olika nivåer av skydd för Teams.](configure-teams-three-tiers-protection.md) Du kan anpassa någon av dessa nivåer för att bättre tillgodose behoven eller verksamheten. 

![Miniatyrbild av affischen för Teams logiska arkitektur](../media/solutions-architecture-center/Teams-tiers-of-protection-1.png)


Dessa nivåer –  *baslinje,* känslig och mycket känslig *–* ökar gradvis skydden som förhindrar att det uppstår för mycket och potentiellt informationsläckage, som visas i följande tabell.

|-|**Baslinjenivå**|**Känslig nivå**|**Högkänslig nivå**|
|:--|:-----------|:------------|:-------------------|
|Offentligt eller privat team|Antingen|Privat|Privat|
|Oautentiserad delning|Blockerad|Blockerad|Blockerad|
|Fildelning|Tillåten|Tillåten|Endast teamägare kan dela.|
|Teammedlemskap|Alla kan ansluta till offentliga team.<br>Godkännande av teamägare krävs för att gå med i privata team.|Godkännande av gruppägare krävs för att gå med.|Godkännande av gruppägare krävs för att gå med.|
|Dokumentkryptering|||Tillgänglig med känslighetsetikett|
|Gästdelning|Tillåten|Kan tillåtas eller blockeras|Kan tillåtas eller blockeras|
|Ohanterade enheter|Ingen begränsning|Endast webbåtkomst|Blockerad|

Konfigurering av dessa nivåer omfattar:

- Konfigurera inställningar i Teams för gäståtkomst och privata kanaler
- Konfigurera inställningar på en grupps associerade SharePoint-webbplats för intern delning och gästdelning, åtkomstförfrågningar och delningslänkar
- För de *känsliga* och *mycket känsliga* nivåerna konfigurerar du känslighetsetiketter för att klassificera teamen och kontrollera gästdelning och åtkomst från ohanterade enheter
- För den *mycket känsliga* nivån konfigurerar du en känslighetsetikett för att kryptera de dokument som den används i

Börja med baslinjenivån och lägg sedan  till  team som använder de känsliga och mycket känsliga nivåerna för att skydda informationen i organisationen. Se följande resurser för att komma igång:

- [Konfigurera teams med grundläggande skydd](configure-teams-baseline-protection.md)
- [Konfigurera team med skydd för känslig data](configure-teams-sensitive-protection.md)
- [Konfigurera team med skydd för mycket känslig data](configure-teams-highly-sensitive-protection.md)

Om du har ett mycket känsligt projekt som kräver ytterligare skydd mot delning även inom organisationen kan du konfigurera ett team som använder sin egen känslighetsetikett för att kryptera filer så att bara gruppmedlemmar kan läsa dem. Mer [information finns i Konfigurera ett team med säkerhetsisolering.](secure-teams-security-isolation.md)

### <a name="sharing-with-people-outside-your-organization"></a>Dela med personer utanför organisationen

Du kan behöva [dela känsligheten med personer utanför organisationen.](collaborate-with-people-outside-your-organization.md) Det kan vara allt från att dela ett dokument med en enda person till att samarbeta i ett större projekt med en stor partnerorganisation eller med användare från hela världen. I Microsoft 365 kan detta intervall av extern delning göras enkelt och med lämpliga säkerhetsåtgärder för att skydda känslig information.

De här resurserna hjälper dig att komma igång med att konfigurera miljön för samarbete med personer utanför organisationen:

- [Samarbeta i dokument](collaborate-on-documents.md) för att dela enskilda filer med mappar.
- [Samarbeta på en webbplats](collaborate-in-site.md) för att samarbeta med gäster på en SharePoint-webbplats.
- [Samarbeta som ett team](collaborate-as-team.md) för att samarbeta med gäster i ett team.

Beroende på hur känslig informationen är kan du lägga till säkerhetsåtgärder för att förhindra att den delas. Med de här resurserna kan du konfigurera de skydd du behöver för organisationen:

- [Metodtips för att dela filer och mappar med oautentiserade användare](best-practices-anonymous-sharing.md)
- [Begränsa oavsiktlig exponering för filer när de delas med personer utanför organisationen](share-limit-accidental-exposure.md)
- [Skapa en säker miljö för gästdelning](create-secure-guest-sharing-environment.md)

Om du har ett större projekt med en partnerorganisation kan du använda hantering av Azure-berättigande till att hantera gäster från den organisationen i ett team som du har ställt in för projektet. Mer [information finns i Skapa ett B2B-extranät med hanterade](b2b-extranet.md) gäster.

## <a name="deploy-the-secure-collaboration-solution"></a>Distribuera en säker samarbetslösning

När du är redo att distribuera den här lösningen fortsätter du med följande steg:
1. Konfigurera de [tre olika skyddsnivåerna för Teams.](configure-teams-three-tiers-protection.md)
2. Konfigurera inställningar för [att dela information om känsligheten för personer utanför organisationen.](collaborate-with-people-outside-your-organization.md)

## <a name="see-also"></a>Se även

[Dokumentation för Microsoft 365 Säkerhetscenter](https://docs.microsoft.com/microsoft-365/security)

[Dokumentation för Microsoft 365 Efterlevnadscenter](https://docs.microsoft.com/microsoft-365/compliance)

[Välkommen till Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/Teams-overview)
