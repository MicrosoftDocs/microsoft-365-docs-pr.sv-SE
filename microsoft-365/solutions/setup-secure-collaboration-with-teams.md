---
title: Konfigurera säkerhet samarbete med hjälp av Microsoft 365
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-securecollab
- m365solution-overview
ms.custom: ''
f1.keywords: NOCSH
description: Lär dig hur du konfigurerar teams för att skydda dina data baserat på dess känslighet
ms.openlocfilehash: ef49e788805139bf82fa5b1b43d2a87323640820
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/30/2020
ms.locfileid: "46527714"
---
# <a name="set-up-secure-collaboration-with-microsoft-365"></a>Konfigurera säkerhet samarbete med hjälp av Microsoft 365

Att enkelt kunna dela information med rätt personer samtidigt som det förhindrar överdelning är nyckeln till en organisations framgång. Detta inkluderar att kunna dela känsliga data på ett säkert sätt med endast dem som ska ha tillgång till dem. Beroende på projektet kan det handla om att dela känsliga data med personer utanför organisationen.

Den här lösningsvägledningen innehåller två komponenter som hjälper dig att:
- Distribuera Microsoft Teams med rätt skyddsnivå för varje projekt
- Konfigurera extern delning med lämpliga säkerhetsinställningar för varje projekt

![Distribuera team med lämpligt skydd och konfigurera extern delning med lämpliga säkerhetsinställningar](..\media\solutions-architecture-center\secure-collaboration-overview.png)

Om det inte finns några mångsidiga och lätt att använda samarbetsverktyg samarbetar användarna ofta genom att skicka dokument via e-post. Detta är en tråkig och felbenägen samarbetsmetod och kan öka risken för olämpligt informationsutbyte. Om människor tycker att det är för svårt att dela information kan de återgå till att använda konsumentprodukter som inte styrs av IT. Detta kan innebära en ännu större risk.

Med Microsoft 365 kan du distribuera Teams med en mängd olika konfigurationer som hjälper:

- Skydda dina immateriella rättigheter
- Möjliggör enkelt samarbete
- Skapa en balans mellan säkerhet och användbarhet som ökar användarnas tillfredsställelse och minskar risken för skugg-IT

De flesta organisationer har en mängd information, med varierande grad av känslighet och varierande grad av inverkan på verksamheten om informationen delas på ett olämpligt sätt. Beroende på känsligheten hos en viss information kan du tillåta delning med:

- Alla (oautentiserade)
- Människor inom organisationen
- Specifika personer inom organisationen
- Specifika personer inom och utanför organisationen

Information såsom marknadsföringsbroschyrer är avsedda för att dela i stort sett utanför organisationen. Information som kafeteria menyer är inte avsedda för extern delning, men skulle inte ha någon inverkan på verksamheten om de delades externt. Dessa typer av information behöver lite eller inget skydd.

Samma marknadsföringsbroschyrer, under utveckling, kan bara delas inom organisationen. I det här fallet kan standarddelningsinställningarna i Teams vara tillräckliga.

Information om en ny produkt som är under utveckling kan anses vara känslig, även inom organisationen. En högre grad av skydd kan vara lämpligt i detta fall. Du kan begränsa åtkomsten till den här informationen till medlemmar i ett visst team, till exempel. Beroende på projektet kan du behöva samarbeta med personer utanför organisationen, till exempel en leverantör eller partnerorganisation.

Information som är avgörande för organisationens framgång, eller som har stränga säkerhetskrav eller efterlevnadskrav kan kräva ännu högre skyddsnivå.

![Riskskala från låg (utgiven broschyr) till hög (känsliga affärsdata)](../media/solutions-architecture-center/SecureCollaboration-SensitivityAndBusinessImpactofSharing-fromVisio.png)

För alla scenarier som anges ovan kan du använda team i Microsoft Teams för att lagra, dela och samarbeta med informationen. 

Om du vill konfigurera säker collabration använder du dessa funktioner och funktioner i Microsoft 365.

| Produkt eller komponent | Resurs eller funktion | Licensiering |
|:-------|:-----|:-------|
| Office 365 Avancerat skydd | ATP Säkra bilagor för SPO, OneDrive och teams; ATP säkra dokument; ATP säkra länkar för team    | Microsoft 365 E1, E3 och E5 |
| SharePoint    | Webbplats- och fildelningsprinciper, behörigheter för webbplatsdelning, Delningslänkar, Åtkomstbegäranden, Inställningar för delning av webbplatsgäst | Microsoft 365 E1, E3 och E5 |
| Microsoft Teams   | Gäståtkomst, privata team, privata kanaler | Microsoft 365 E1, E3 och E5 |
| Microsoft 365 Efterlevnad  | Känslighetsetiketter    | Microsoft 365 E3 och E5 |

### <a name="using-teams-for-all-kinds-of-data"></a>Använda Teams för alla typer av data

För att hantera åtkomst till information med olika känslighet har vi utvecklat [tre olika skyddsnivåer för Teams.](configure-teams-three-tiers-protection.md) Du kan anpassa någon av dessa nivåer för att bättre tillgodose behoven eller ditt företag. 

![Miniatyrbild av affischen för Teams logiska arkitektur](../media/solutions-architecture-center/Teams-tiers-of-protection-1.png)


Dessa nivåer - *baslinje,* *känslig*och *mycket känslig* - ökar gradvis de skydd som hjälper till att förhindra överdelning och potentiellt informationsläckage, som visas i följande tabell.

||**Baslinjenivå**|**Känslig nivå**|**Mycket känslig nivå**|
|:--|:-----------|:------------|:-------------------|
|Offentligt eller privat team|Antingen|Privat|Privat|
|Oautentiserad delning|Blockerade|Blockerade|Blockerade|
|Fildelning|Tillåtet|Tillåtet|Endast gruppägare kan dela.|
|Lagmedlemskap|Vem som helst kan gå med i offentliga team.<br>Teamägare godkännande krävs för att gå med i privata team.|Teamägare godkännande krävs för att gå med.|Teamägare godkännande krävs för att gå med.|
|Dokumentkryptering|||Finns med känslighetsetikett|
|Gästdelning|Tillåtet|Kan tillåtas eller blockeras|Kan tillåtas eller blockeras|
|Ohanterade enheter|Ingen begränsning|Endast webbåtkomst|Blockerade|

Konfigurera dessa nivåer innebär:

- Konfigurera inställningar i Teams för gäståtkomst och privata kanaler
- Konfigurera inställningar på ett teams associerade SharePoint-webbplats för intern delning och gästdelning, åtkomstbegäranden och delningslänkar
- För *känsliga* och *mycket känsliga* nivåer konfigurerar du känslighetsetiketter för att klassificera teamen och styr gästdelning och åtkomst från ohanterade enheter
- För den *mycket känsliga* nivån konfigurerar du en känslighetsetikett för att kryptera de dokument som den används på

Börja med baslinjenivån och lägg sedan till team som använder de *känsliga* och *mycket känsliga* nivåerna efter behov för att skydda informationen i organisationen. Se de här resurserna för att komma igång:

- [Konfigurera teams med grundläggande skydd](configure-teams-baseline-protection.md)
- [Konfigurera team med skydd för känslig data](configure-teams-sensitive-protection.md)
- [Konfigurera team med skydd för mycket känslig data](configure-teams-highly-sensitive-protection.md)

Om du har ett mycket känsligt projekt som kräver ytterligare skydd mot delning även inom organisationen kan du konfigurera ett team som använder sin egen känslighetsetikett för att kryptera filer så att endast gruppmedlemmar kan läsa dem. Mer information [finns i Konfigurera ett team med säkerhetsisolering.](secure-teams-security-isolation.md)

### <a name="sharing-with-people-outside-your-organization"></a>Dela med personer utanför organisationen

Du kan behöva [dela information om eventuell känslighet med personer utanför organisationen](collaborate-with-people-outside-your-organization.md). Detta kan vara allt från att dela ett enda dokument med en enda person till att samarbeta i ett större projekt med en stor partnerorganisation eller frilansare från hela världen. I Microsoft 365 kan det här utbudet av extern delning göras enkelt och med lämpliga skyddsåtgärder för att skydda din känsliga information.

De här resurserna hjälper dig att komma igång med att konfigurera din miljö för att samarbeta med personer utanför organisationen:

- [Samarbeta i dokument](collaborate-on-documents.md) för att dela enskilda filer i mappar.
- [Samarbeta på en webbplats](collaborate-in-site.md) för att samarbeta med gäster på en SharePoint-webbplats.
- [Samarbeta som ett team](collaborate-as-team.md) för att samarbeta med gäster i ett team.

Beroende på hur känslig informationen är kan du lägga till skyddsåtgärder för att förhindra överdelning. Dessa resurser hjälper dig att ställa in de skydd som du behöver för din organisation:

- [Metodtips för att dela filer och mappar med oautentiserade användare](best-practices-anonymous-sharing.md)
- [Begränsa oavsiktlig exponering för filer när de delas med personer utanför organisationen](share-limit-accidental-exposure.md)
- [Skapa en säker miljö för gästdelning](create-secure-guest-sharing-environment.md)

Om du har ett större projekt med en partnerorganisation kan du använda Azure Entitlement Management för att hantera gäster från den organisationen i ett team som du har konfigurerat för projektet. Mer information finns i [Skapa ett B2B-extranät med hanterade gäster.](b2b-extranet.md)

## <a name="deploy-the-secure-collaboration-solution"></a>Distribuera lösningen för säkert samarbete

När du är redo att distribuera den här lösningen fortsätter du med följande steg:
1. Konfigurera de [tre olika skyddsnivåerna för Teams](configure-teams-three-tiers-protection.md).
2. Konfigurera inställningar för [att dela information om eventuell känslighet med personer utanför organisationen](collaborate-with-people-outside-your-organization.md).

## <a name="see-also"></a>Se även

[Dokumentation för Microsoft 365 Säkerhetscenter](https://docs.microsoft.com/microsoft-365/security)

[Dokumentation för Microsoft 365 Efterlevnadscenter](https://docs.microsoft.com/microsoft-365/compliance)

[Välkommen till Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/Teams-overview)
