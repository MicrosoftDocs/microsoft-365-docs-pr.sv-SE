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
description: Lär dig hur du konfigurerar säkra innehålls samarbete i Teams för att skydda dina data baserat på dess känslighet.
ms.openlocfilehash: f65657125fef8b8cf7e4e229d70d8fe211153392
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613590"
---
# <a name="set-up-secure-collaboration-with-microsoft-365"></a>Konfigurera säkerhet samarbete med hjälp av Microsoft 365

Det är enkelt att dela information med rätt personer när du hindrar överdelningen till en organisations framgångar. Det innebär att du kan dela känslig information på ett säkert sätt med bara de som ska ha åtkomst till det. Beroende på projektet kan det vara bra att dela känslig information med personer utanför organisationen.

Den här vägledningen för samarbets lösningar innehåller två komponenter som hjälper dig att:
- Distribuera Microsoft Teams med rätt skydds nivå för varje projekt
- Konfigurera extern delning med lämpliga säkerhets inställningar för varje projekt

![Distribuera Teams med lämpligt skydd och konfigurera extern delning med lämpliga säkerhets inställningar](..\media\solutions-architecture-center\secure-collaboration-overview.png)

Om det är mångsidigt och lättanvända verktyg för innehålls samarbete inte är tillgängligt kan användarna ofta samar beta via e-post. Det här är ett omständligt och felkänsligt samarbets sätt och kan öka risken för olämplig delning av information. Om folk tycker att informationen är för svår kan de återgå till att använda konsument produkter som inte styrs av den. Detta kan innebära en ännu större risk.

Med Microsoft 365 kan du distribuera Teams med en mängd olika konfigurationer som hjälper:

- Skydda immateriella rättigheter
- Aktivera enkelt samarbete
- Skapa en avvägning mellan säkerhet och användbarhet som förbättrar användarnas tillfredsställelse och minskar risken för att skugga det

De flesta organisationer har en mängd olika typer av information, med varierande grad av känsligheten och varierande grad av affärs påverkan om informationen inte är korrekt delad. Beroende på känsligheten hos ett visst informations stycke kanske du vill tillåta delning med:

- Alla (ej autentiserade)
- Personer i organisationen
- Specifika personer inom organisationen
- Specifika personer inom och utanför organisationen

Information som marknadsförings broschyrer är avsedda att delas utanför organisationen. Information som cafeteria-menyer är inte avsedd för extern delning, men har ingen rörelse påverkan om de delades externt. Dessa typer av information kräver lite eller inget skydd.

Samma marknadsförings broschyrer under utveckling kan bara delas i organisationen. I det här fallet kanske teamets standardinställningar för delning är tillräckligt.

Information om en ny produkt som är under utveckling kan anses vara känslig, även inom organisationen. Ett högre skydd kan vara lämpligt i det här fallet. Du kan till exempel begränsa åtkomsten till den här informationen till medlemmar i ett visst team. Beroende på projektet kan du behöva samar beta med personer utanför organisationen, till exempel en leverantör eller partner organisation.

Information som är kritisk för din organisations framgångar eller har strikt säkerhets-eller efterföljandekrav kan kräva ännu högre skydds nivåer.

![Risk skala från Low (släppt broschyr) till hög (känslig företags information)](../media/solutions-architecture-center/SecureCollaboration-SensitivityAndBusinessImpactofSharing-fromVisio.png)

För alla scenarier ovan kan du använda Teams i Microsoft Teams för att lagra, dela och samar beta med informationen. 

För att konfigurera säkra samarbeten använder du dessa Microsoft 365-funktioner och-funktioner.

| Produkt eller komponent | Resurs eller funktion | Licensiering |
|:-------|:-----|:-------|
| Microsoft Defender för Office 365 | Säkra bifogade filer för SPO, OneDrive och Teams; Säkra dokument; Säkra Länkar för team    | Microsoft 365 E1, E3 och E5 |
| SharePoint    | Principer för webbplats-och fildelning, webbplats delnings behörigheter, dela länkar, åtkomst förfrågningar, inställningar för gäst delning för webbplatser | Microsoft 365 E1, E3 och E5 |
| Microsoft Teams   | Gäst åtkomst, privata team, privata kanaler | Microsoft 365 E1, E3 och E5 |
| Microsoft 365 Efterlevnad  | Känslighetsetiketter    | Microsoft 365 E3 och E5 |

### <a name="using-teams-for-all-kinds-of-data"></a>Använda Teams för alla typer av data

För att hantera åtkomst till information med olika sensitivities har vi utvecklat [tre olika nivåer av skydd för Teams](configure-teams-three-tiers-protection.md). Du kan anpassa dessa nivåer för att bättre kunna hantera behoven eller ditt företag. 

![Miniatyrbild av affischen för Teams logiska arkitektur](../media/solutions-architecture-center/Teams-tiers-of-protection-1.png)


Dessa nivåer- *bas linje*, *känsligt* och *mycket känsligt* – gradvis öka skyddet för att förhindra överdelning och potentiellt informations läckage enligt följande tabell.

|-|**Bas linje nivå**|**Känslig nivå**|**Känslig nivå**|
|:--|:-----------|:------------|:-------------------|
|Offentligt eller privat team|Respektive|Privat|Privat|
|Oautentiserad delning|Blockering|Blockering|Blockering|
|Fildelning|Möjlighet|Möjlighet|Endast team ägare kan dela.|
|Grupp medlemskap|Vem som helst kan gå med i offentliga team.<br>Team ägar godkännande krävs för att ansluta till privata team.|Team ägar godkännande krävs för att gå med.|Team ägar godkännande krävs för att gå med.|
|Dokument kryptering|||Med känslighets etikett|
|Gästdelning|Möjlighet|Kan tillåtas eller blockeras|Kan tillåtas eller blockeras|
|Ohanterade enheter|Ingen begränsning|Åtkomst via webben|Blockering|

Konfigurering av dessa nivåer inbegriper:

- Konfigurera inställningar i Teams för gäst åtkomst och privata kanaler
- Konfigurera inställningar i ett Teams SharePoint-webbplats för intern gäst delning, åtkomst förfrågningar och delnings länkar
- För *känslig* och *mycket känslig* nivå, konfigurering av känslighets etiketter för att klassificera team och styra gäst delning och åtkomst från ohanterade enheter
- För att det ska vara *känsligt* , konfigurera en känslighets etikett för att kryptera de dokument som den tillämpas på

Börja med original nivån och Lägg sedan till Teams som använder *känslig* och *mycket känslig* nivå för att skydda informationen i organisationen. För att komma igång:

- [Konfigurera teams med grundläggande skydd](configure-teams-baseline-protection.md)
- [Konfigurera team med skydd för känslig data](configure-teams-sensitive-protection.md)
- [Konfigurera team med skydd för mycket känslig data](configure-teams-highly-sensitive-protection.md)

Om du har ett mycket känsligt projekt som kräver att du skyddar dig även inom din organisation kan du konfigurera ett team som använder sin egen känslighets etikett för att kryptera filer så att bara grupp medlemmar kan läsa dem. Mer information finns i [Konfigurera ett team med säkerhets isolering](secure-teams-security-isolation.md) .

### <a name="sharing-with-people-outside-your-organization"></a>Dela med personer utanför organisationen

Du kan behöva [dela information om känsligheten med personer utanför organisationen](collaborate-with-people-outside-your-organization.md). Detta kan variera från att dela ett dokument med en enda person för att samar beta i ett stort projekt med en stor partner organisation eller Freelancer från hela världen. I Microsoft 365 kan det här urvalet av extern delning enkelt göras och med lämpliga säkerhets åtgärder för att skydda känslig information.

De här resurserna hjälper dig att komma igång med att konfigurera miljön för att samar beta med personer utanför organisationen:

- [Samar beta i dokument](collaborate-on-documents.md) för att dela enskilda filer av mappar.
- [Samar beta på en webbplats](collaborate-in-site.md) för samarbete med gäster på en SharePoint-webbplats.
- [Samar beta som ett team](collaborate-as-team.md) för samarbete med gästerna i ett team.

Beroende på hur känslig informationen som delas kan du lägga till skydd för att förhindra överdelning. De här resurserna hjälper dig att komma igång med din organisation:

- [Metodtips för att dela filer och mappar med oautentiserade användare](best-practices-anonymous-sharing.md)
- [Begränsa oavsiktlig exponering för filer när de delas med personer utanför organisationen](share-limit-accidental-exposure.md)
- [Skapa en säker miljö för gästdelning](create-secure-guest-sharing-environment.md)

Om du har ett stort projekt med en partner organisation kan du använda Azure rättighets hantering för att hantera gästerna i en grupp som du har konfigurerat för projektet. Mer information finns i [skapa ett B2B-extra nät med hanterade gäster](b2b-extranet.md) .

## <a name="deploy-the-secure-collaboration-solution"></a>Distribuera den säkra samarbets lösningen

När du är redo att distribuera den här lösningen kan du gå vidare med de här stegen:
1. Konfigurera de [tre skydds nivåerna för Teams](configure-teams-three-tiers-protection.md).
2. Konfigurera inställningar för att [dela information om känsligheten med personer utanför organisationen](collaborate-with-people-outside-your-organization.md).

## <a name="see-also"></a>Se även

[Dokumentation för Microsoft 365 Säkerhetscenter](https://docs.microsoft.com/microsoft-365/security)

[Dokumentation för Microsoft 365 Efterlevnadscenter](https://docs.microsoft.com/microsoft-365/compliance)

[Välkommen till Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/Teams-overview)
