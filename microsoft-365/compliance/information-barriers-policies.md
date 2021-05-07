---
title: Definiera informationsbarriärsprinciper
description: Lär dig att definiera principer för informationsbarriärer i Microsoft Teams.
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
localization_priority: None
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b245a0f7ca0845024fec0c498aca4c7d447f14ad
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162324"
---
# <a name="define-information-barrier-policies"></a>Definiera informationsbarriärsprinciper

Om det finns informationsbarriärer kan du definiera principer som förhindrar att vissa användarsegment kommunicerar med varandra, eller att specifika segment bara kommunicerar med vissa andra segment. Informationsbarriärpolicyer kan hjälpa din organisation att följa relevanta branschstandarder och bestämmelser och undvika potentiella inkonflikter i intresse. Mer information finns i [Informationsbarriärer](information-barriers.md).

Den här artikeln beskriver hur du planerar, definierar, implementerar och hanterar principer för informationsbarriärer. Flera steg är inblandade och arbetsflödet är uppdelat i flera delar. Läs igenom förutsättningarna och [hela processen](#prerequisites) innan du börjar definiera (eller redigera) informationsbarriärprinciper.

> [!TIP]
> Den här artikeln innehåller [ett exempelscenario](#example-contosos-departments-segments-and-policies) och en [nedladdningsbar Excel som](https://github.com/MicrosoftDocs/OfficeDocs-O365SecComp/raw/public/SecurityCompliance/media/InfoBarriers-PowerShellGenerator.xlsx) hjälper dig att planera och definiera principer för informationsbarriärer.

## <a name="concepts-of-information-barrier-policies"></a>Begrepp som gäller informationsbarriärprinciper

När du definierar principer för informationsbarriärer arbetar du med användarkontoattribut, segment, blockerings- och/eller "tillåt"-principer och principprogram.

- Användarkontoattribut definieras i Azure Active Directory (eller Exchange Online). Attributen kan omfatta avdelning, befattning, plats, gruppnamn och annan jobbprofilinformation. 
- Segment är uppsättningar av användare som har definierats i säkerhets- & Säkerhets- och efterlevnadscenter med ett valt **användarkontoattribut**. (Se listan [över attribut som stöds](information-barriers-attributes.md).)
- Informationsbarriärpolicyer bestämmer kommunikationsbegränsningar eller begränsningar. När du definierar principer för informationsbarriärer väljer du mellan två typer av principer:
    - "Blockera" principer hindrar ett segment från att kommunicera med ett annat segment.
    - Med "Tillåt" principer kan ett segment bara kommunicera med vissa andra segment.
- Policyprogrammet utförs när alla principer för informationsbarriärer har definierats och du är redo att tillämpa dem i din organisation.

## <a name="the-work-flow-at-a-glance"></a>Arbetsflödet i korthet

| Fas | Vad som är inblandat |
|:--------|:------------------|
| [Kontrollera att kraven uppfylls](#prerequisites) | - Kontrollera att du har de [licenser och behörigheter som krävs](information-barriers.md#required-licenses-and-permissions)<br/>- Kontrollera att katalogen innehåller data för segmenterade användare<br/>- Aktivera begränsad katalogsökning för Microsoft Teams<br/>– kontrollera att granskningsloggning är aktiverat<br/>- Kontrollera att Exchange adressboksprinciper inte finns på plats<br/>- Använda PowerShell (exempel ges)<br/>– Ge administratörsmedgivande Microsoft Teams (stegen ingår) |
| [Del 1: Segmentanvändare i organisationen](#part-1-segment-users) | – Fastställa vilka principer som krävs<br/>- Skapa en lista med segment som du vill definiera<br/>- Identifiera vilka attribut du ska använda<br/>- Definiera segment som principfilter |
| [Del 2: Definiera principer för informationsbarriärer](#part-2-define-information-barrier-policies) | - Definiera dina principer (gäller inte ännu)<br/>- Välj mellan två typer (block eller tillåt) |
| [Del 3: Tillämpa principer för informationsbarriärer](#part-3-apply-information-barrier-policies) | - Ställ in principer på aktiv status<br/>- Kör principprogrammet<br/>- Visa principstatus |
| (Vid behov) [Redigera ett segment eller en princip](information-barriers-edit-segments-policies.md) | - Redigera ett segment<br/>– redigera eller ta bort en princip<br/>- Köra principprogrammet igen<br/>- Visa principstatus |
| (Vid behov) [Felsökning](information-barriers-troubleshooting.md)| - Vidta åtgärder när saker inte fungerar som förväntat|

## <a name="prerequisites"></a>Förutsättningar

Kontrollera att följande [krav uppfylls,](information-barriers.md#required-licenses-and-permissions)utöver de licenser och behörigheter som krävs:

- Katalogdata – Kontrollera att organisationens struktur återspeglas i katalogdata. För att kunna vidta den här åtgärden ska du se till att användarkontoattribut, till exempel gruppmedlemskap, avdelningsnamn osv. fylls i korrekt i Azure Active Directory (eller Exchange Online). Mer information finns i följande resurser:
  - [Attribut för informationsbarriärsprinciper](information-barriers-attributes.md)
  - [Lägga till eller uppdatera en användares profilinformation med hjälp av Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)
  - [Konfigurera användarkontoegenskaper med Office 365 PowerShell](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md)

- Begränsad katalogsökning – Innan du definierar din organisations första informationsbarriärprincip måste du aktivera begränsad [katalogsökning i Microsoft Teams.](/MicrosoftTeams/teams-scoped-directory-search) Vänta i minst 24 timmar efter att du har aktiverar begränsad katalogsökning innan du anger eller definierar principer för informationsbarriärer.

- EXO-licens – IB-principer fungerar bara om målanvändarna har tilldelats en EXO-licens.

- Granskningsloggning – Du måste aktivera granskningsloggning för att du ska kunna slå upp status för ett principprogram. Vi rekommenderar att du aktiverar granskning innan du börjar definiera segment eller principer. Mer information finns i [Aktivera eller inaktivera granskningsloggsökning.](turn-audit-log-search-on-or-off.md)

- Inga adressboksprinciper – Innan du definierar och tillämpar principer för informationsbarriärer kontrollerar du att Exchange principer för adressboken finns. Informationsbarriärer baseras på adressboksprinciper, men de två typerna av principer är inte kompatibla. Om du har sådana principer ska du se till att [ta bort dina adressboksprinciper](/exchange/address-books/address-book-policies/remove-an-address-book-policy) först. När principer för informationsbarriärer har aktiverats och du  har aktiverat hierarkisk adressbok kan [](/exchange/address-books/hierarchical-address-books/hierarchical-address-books) alla användare som inte ingår i informationsbarriärsegmenten se den hierarkiska adressboken i Exchange online.

- PowerShell – För närvarande definieras och hanteras informationsbarriärprinciper i Office 365 Säkerhets- & Säkerhetscenter med PowerShell-cmdlets. Även om flera exempel finns i den här artikeln måste du vara bekant med PowerShell-cmdlets och parametrar. Du behöver också Azure PowerShell modulen.
    - [Anslut säkerhets- & Säkerhets- och efterlevnadscenter PowerShell](/powershell/exchange/connect-to-scc-powershell)
    - [Installera Azure PowerShell modulen](/powershell/azure/install-az-ps?view=azps-2.3.2)

- Administratörsmedgivande om informationsbarriärer i Microsoft Teams – När dina IB-principer finns kan de ta bort användare som inte är IB-efterlevnad från grupper (dvs. Teams-kanaler, som baseras på grupper). Den här konfigurationen ser till att organisationen fortfarande följer principer och bestämmelser. Använd följande procedur för att göra det möjligt för informationsbarriärprinciper att fungera som förväntat i Microsoft Teams.

   1. Förutsättningar: Installationen Azure PowerShell från [installationen Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps).

   1. Kör följande PowerShell-cmdlets:

      ```powershell
      Connect-AzAccount -Tenant "<yourtenantdomain.com>"  //for example: Connect-AzAccount -Tenant "Contoso.onmicrosoft.com"
      $appId="bcf62038-e005-436d-b970-2a472f8c1982" 
      $sp=Get-AzADServicePrincipal -ServicePrincipalName $appId
      if ($sp -eq $null) { New-AzADServicePrincipal -ApplicationId $appId }
      Start-Process  "https://login.microsoftonline.com/common/adminconsent?client_id=$appId"
      ```

   1. När du uppmanas till det loggar du in med ditt arbets- eller skolkonto för Office 365.

   1. Granska **informationen i** dialogrutan Behörigheter som krävs och välj sedan **Acceptera**. De behörigheter som begärs av Appen ges nedan.
      
      > [!div class="mx-imgBorder"]
      > ![bild](https://user-images.githubusercontent.com/8932063/107690955-b1772300-6c5f-11eb-9527-4235de860b27.png)


När alla krav uppfylls går du till nästa avsnitt.

> [!TIP]
> I den här artikeln finns ett exempelscenario som kan vara till hjälp när du förbereder planen. [Se Contosos avdelningar, segment och principer.](#example-contosos-departments-segments-and-policies)<p>Dessutom finns det en nedladdningsbar Excel som hjälper dig att planera och definiera dina segment och principer (och skapa PowerShell-cmdlets). [Hämta arbetsboken](https://github.com/MicrosoftDocs/OfficeDocs-O365SecComp/raw/public/SecurityCompliance/media/InfoBarriers-PowerShellGenerator.xlsx).

## <a name="part-1-segment-users"></a>Del 1: Segmentanvändare

Under den här fasen kan du fastställa vilka informationsbarriärprinciper som behövs, skapa en lista med segment som du vill definiera och sedan definiera dina segment.

### <a name="determine-what-policies-are-needed"></a>Bestäm vilka principer som krävs

Vilka är de grupper i din organisation som behöver informationsbarriärer och regler gällande juridiska bestämmelser? Skapa en lista. Finns det några grupper som ska hindras från att kommunicera med en annan grupp? Finns det några grupper som endast ska kunna kommunicera med en eller två andra grupper? Tänk på de principer du behöver som tillhör en av två grupper:

- Blockeringsprinciper hindrar en grupp från att kommunicera med en annan grupp.
- Med "Tillåt" principer kan en grupp kommunicera med endast vissa andra, specifika grupper.

När du har en första lista över grupper och principer kan du fortsätta och identifiera de segment som du behöver.

### <a name="identify-segments"></a>Identifiera segment

Gör en lista med segment för din organisation, utöver den första listan med principer. Användare som omfattas av informationsbarriärer bör tillhöra ett segment. Planera dina segment noggrant så att en användare bara kan vara i ett segment. Varje segment kan bara ha en policy för informationsbarriärer tillämpade.

> [!IMPORTANT]
> En användare kan bara vara i ett segment.

Bestäm vilka attribut i organisationens katalogdata som du ska använda för att definiera segment. Du kan använda *Department*, *MemberOf* eller någon av attributen som stöds. Kontrollera att du har värden i attributet som du väljer för användare. [Se listan över attribut som stöds för informationsbarriärer.](information-barriers-attributes.md)

> [!IMPORTANT]
> **Innan du går vidare till nästa avsnitt kontrollerar du att katalogdata** har värden för attribut som du kan använda för att definiera segment . Om dina katalogdata inte har värden för de attribut du vill använda måste användarkontona uppdateras så att informationen inkluderas innan du kan fortsätta med informationsbarriärer. Om du behöver hjälp med detta kan du gå till följande resurser:<br/>- [Konfigurera användarkontoegenskaper med Office 365 PowerShell](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md)<br/>- [Lägga till eller uppdatera en användares profilinformation med hjälp av Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)

### <a name="define-segments-using-powershell"></a>Definiera segment med PowerShell

Användare påverkas inte av att definiera segment. Den anger bara steget för att principer för informationsbarriärer ska definieras och sedan tillämpas.

1. Använd **cmdleten New-OrganizationSegment** med parametern **UserGroupFilter** som motsvarar [det attribut](information-barriers-attributes.md) du vill använda.

    | Syntax | Exempel |
    |:---------|:----------|
    | `New-OrganizationSegment -Name "segmentname" -UserGroupFilter "attribute -eq 'attributevalue'"` |`New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"` <p>I det här exemplet definieras ett segment *som kallas* PERSONAL med *hr,* ett värde i *attributet* Avdelning. **Ekv-delen** av cmdleten refererar till "lika med". (Alternativt kan du använda **-ne för** att betyda "inte lika med". Se [Använda "lika med" och "inte lika med" i segmentdefinitioner](#using-equals-and-not-equals-in-segment-definitions).) |

    När du har kört varje cmdlet visas en lista med information om det nya segment. Det kan till exempel vara segmenttypen, vem som skapade eller senast ändrade det och så vidare. 

2. Upprepa proceduren för varje segment som du vill definiera.

    > [!IMPORTANT]
    > **Kontrollera att segmenten inte överlappar**. Varje användare som kommer att påverkas av informationsbarriärer bör tillhöra ett (och endast ett) segment. Ingen användare ska tillhöra två eller fler segment. (Se [exempel: Contosos definierade segment i](#contosos-defined-segments) den här artikeln.)

När du har definierat dina segment kan du fortsätta att [definiera principer för informationsbarriärer.](#part-2-define-information-barrier-policies)

### <a name="using-equals-and-not-equals-in-segment-definitions"></a>Använda "lika med" och "inte lika med" i segmentdefinitioner

I följande exempel definierar vi ett segment så att "Avdelning är lika med PERSONAL". 

| Exempel | Obs! |
|:----------|:-------|
|`New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"` | Observera att i det här exemplet innehåller segmentdefinitionen en parameter som kallas **-eq**. |

Du kan också definiera segment med parametern "not equals" (kallas **-ne)** som visas i följande tabell:

| Syntax | Exempel |
|:---------|:----------|
| `New-OrganizationSegment -Name "NotSales" -UserGroupFilter "Department -ne 'Sales'"` | I det här exemplet har vi definierat ett segment *som kallas NotSales* som inkluderar alla som inte finns i *Försäljning.* **-ne-delen** av cmdleten refererar till "inte lika med". |

Förutom att definiera segment som använder "lika med" eller "inte lika med" kan du definiera ett segment med hjälp av båda parametrarna "lika med" och "inte lika med". Du kan också definiera komplexa gruppfilter med hjälp av logiska *OCH-* och *ELLER-operatorer.*

| Syntax | Exempel |
|:---------|:----------|
| `New-OrganizationSegment -Name "LocalFTE" -UserGroupFilter "Location -eq 'Local'" -and "Position -ne 'Temporary'"` | I det här exemplet har vi definierat ett segment som kallas *LocalFTE* som innehåller personer som finns lokalt och vars positioner inte anges som *tillfälliga.* |
| `New-OrganizationSegment -Name "Segment1" -UserGroupFilter "MemberOf -eq 'group1@contoso.com'' -and MemberOf -ne 'group3@contoso.com'"`| I det här exemplet har vi definierat ett segment som kallas *Segment1* och som omfattar personer som är medlemmar i group1@contoso.com och inte medlemmar i group3@contoso.com. |
| `New-OrganizationSegment -Name "Segment2" -UserGroupFilter "MemberOf -eq 'group2@contoso.com' -or MemberOf -ne 'group3@contoso.com'"` | I det här exemplet har vi definierat ett segment som kallas *Segment2* och som omfattar personer som är medlemmar i group2@contoso.com och inte medlemmar i group3@contoso.com. |
| `New-OrganizationSegment -Name "Segment1and2" -UserGroupFilter "(MemberOf -eq 'group1@contoso.com' -or MemberOf -eq 'group2@contoso.com') -and MemberOf -ne 'group3@contoso.com'"`| I det här exemplet har vi definierat ett segment som kallas *Segment1and2* som inkluderar personer medlemmar i group1@contoso.com och group2@contoso.com och inte medlemmar i group3@contoso.com. |

> [!TIP]
> Använd om möjligt segmentdefinitioner som innehåller "-eq" eller "-ne". Försök att inte definiera komplexa segmentdefinitioner.

## <a name="part-2-define-information-barrier-policies"></a>Del 2: Definiera principer för informationsbarriärer

Avgöra om du behöver förhindra kommunikation mellan vissa segment eller begränsa kommunikationen till vissa segment. Under idealiska som helst ska du använda lägsta antal principer för att säkerställa att organisationen följer juridiska krav och branschkrav.

Med din lista över användarsegment och de informationsbarriärprinciper som du vill definiera, välj ett scenario och följ sedan stegen.

- [Scenario 1: Blockera kommunikation mellan segment](#scenario-1-block-communications-between-segments)
- [Scenario 2: Tillåta att ett segment bara kommunicerar med ett annat segment](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment)

> [!IMPORTANT]
> **Se till att du inte tilldelar mer än en princip till ett segment** när du definierar principer. Om du till exempel definierar en princip för ett segment som kallas *Försäljning* ska du inte definiera någon ytterligare princip för *försäljning.*<p> När du definierar principer för informationsbarriärer ska du dessutom se till att ställa in dessa principer på inaktiv status tills du är redo att tillämpa dem. Definiera (eller redigera) principer påverkar inte användare förrän dessa principer anges till aktiv status och sedan tillämpas.

(Se [exempel: Contosos informationsbarriärpolicy i](#contosos-information-barrier-policies) den här artikeln.)

### <a name="scenario-1-block-communications-between-segments"></a>Scenario 1: Blockera kommunikation mellan segment

När du vill blockera segment från att kommunicera med varandra definierar du två principer, en för varje riktning. Varje princip blockerar kommunikation endast på ett sätt.

Anta till exempel att du vill blockera kommunikationen mellan segment A och segment B. I det här fallet definierar du en princip som förhindrar segment A från att kommunicera med segment B och sedan definierar du en andra princip för att förhindra att segment B kommunicerar med segment A.

1. Definiera den första blockeringsprincipen med hjälp av cmdleten **New-InformationBarrierPolicy** med **parametern SegmentsBlocked.**

    | Syntax | Exempel |
    |:--------|:----------|
    | `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsBlocked "segment2name"` | `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive` <p> I det här exemplet har vi definierat en princip *som kallas Försäljningsundersökning* för ett segment som kallas *Försäljning.* När den här principen är aktiv och används förhindrar den här principen personer i *försäljning* att kommunicera med personer i ett segment som kallas *Forskning.* |

2. Om du vill definiera ett andra blockeringssegment använder du cmdleten **New-InformationBarrierPolicy** med parametern **SegmentsBlocked** igen, nu med omvänt segment.

    | Exempel | Obs! |
    |:----------|:-------|
    |`New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive` | I det här exemplet har vi definierat en policy *som kallas Forskning-Försäljning* för att *förhindra att* forskning kommunicerar med *försäljning.* |

3. Gå vidare till någon av följande åtgärder:

   - (Vid behov) [Definiera en princip för att tillåta att ett segment bara kommunicerar med ett annat segment](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment) 
   - (När alla principer har definierats) [Tillämpa principer för informationsbarriärer](#part-3-apply-information-barrier-policies)

### <a name="scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment"></a>Scenario 2: Tillåta att ett segment bara kommunicerar med ett annat segment

1. Om du vill tillåta att ett segment kommunicerar med bara ett annat segment använder du cmdleten **New-InformationBarrierPolicy** med **parametern SegmentsAllowed.**

    | Syntax | Exempel |
    |:----------|:----------|
    | `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsAllowed "segment2name","segment1name"` | `New-InformationBarrierPolicy -Name "Manufacturing-HR" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR","Manufacturing" -State Inactive` <p> I det här exemplet har vi definierat en policy *som kallas Tillverkning-HR* för ett segment som kallas *Tillverkning.* När den här principen är aktiv och används kan personer i *Tillverkning* bara kommunicera med personer i ett segment som kallas *HR.* (I det här fallet *kan Tillverkning* inte kommunicera med användare som inte är en del av *personalavdelningen.)* |

    **Om det behövs kan du ange flera segment med den här cmdleten, som du ser i följande exempel.**

    | Syntax | Exempel |
    |:---------|:----------|
    | `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsAllowed "segment2name", "segment3name","segment1name"` | `New-InformationBarrierPolicy -Name "Research-HRManufacturing" -AssignedSegment "Research" -SegmentsAllowed "HR","Manufacturing","Research" -State Inactive` <p> I det här exemplet har vi definierat en princip som gör att *informationssegmentet* kan kommunicera med *enbart personal och* *tillverkning.* |

    Upprepa det här steget för varje princip som du vill använda för att tillåta att vissa segment bara kommunicerar med vissa andra specifika segment.

2. Gå vidare till någon av följande åtgärder:

   - (Vid behov) [Definiera en princip för att blockera kommunikation mellan segment](#scenario-1-block-communications-between-segments) 
   - (När alla principer har definierats) [Tillämpa principer för informationsbarriärer](#part-3-apply-information-barrier-policies)

## <a name="part-3-apply-information-barrier-policies"></a>Del 3: Tillämpa principer för informationsbarriärer

Informationsbarriärprinciper är inte aktiva förrän du anger dem som aktiv status och tillämpar sedan principerna.

1. Använd **cmdlet:en Get-InformationBarrierPolicy** för att visa en lista med principer som har definierats. Notera status och identitet (GUID) för varje princip.

    Syntax: `Get-InformationBarrierPolicy`

2. Om du vill ange en princip som aktiv status använder du cmdleten **Set-InformationBarrierPolicy** med en **Identity-parameter** och  stateparametern inställd på **Active**. 

    | Syntax | Exempel |
    |:---------|:----------|
    | `Set-InformationBarrierPolicy -Identity GUID -State Active` | `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -State Active` <p> I det här exemplet anger vi en princip för informationsbarriärer som har GUID *43c37853-ea10-4b90-a23d-ab8c93772471* till aktiv status. |

    Upprepa det här steget efter behov för varje princip.

3. När du har ställer in principer för informationsbarriärer till aktiv status använder du cmdleten **Start-InformationBarrierPoliciesApplication** i säkerhets- och & efterlevnadscentret.

    Syntax: `Start-InformationBarrierPoliciesApplication`

    När du har `Start-InformationBarrierPoliciesApplication` kört kan det ta 30 minuter innan systemet börjar använda principerna. Systemet tillämpar principer användare för användare. Systemet bearbetar ca 5 000 användarkonton per timme.

## <a name="view-status-of-user-accounts-segments-policies-or-policy-application"></a>Visa status för användarkonton, segment, principer eller principprogram

Med PowerShell kan du visa status för användarkonton, segment, principer och principprogram, som du ser i följande tabell.

| Om du vill visa den här informationen | Gör så här |
|:---------------|:----------|
| Användarkonton | Använd **cmdleten Get-InformationBarrierRecipientStatus** med identitetsparametrar. <p> Syntax: `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> Du kan använda valigt värde som unikt identifierar varje användare, t.ex. namn, alias, unikt namn, kanoniskt domännamn, e-postadress eller GUID. <p> Exempel: `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> I det här exemplet hänvisar vi till två användarkonton i Office 365: *abbyb* för *Alex*, *och alexw* för *Alex*. <p> (Du kan också använda den här cmdleten för en enskild användare: `Get-InformationBarrierRecipientStatus -Identity <value>` ) <p> Den här cmdleten returnerar information om användare, till exempel attributvärden och informationsbarriärprinciper som tillämpas.|
| Segment | Använd **cmdleten Get-OrganizationSegment.**<p> Syntax: `Get-OrganizationSegment` <p> Den här cmdleten visar en lista över alla segment som har definierats för din organisation. |
| Informationsbarriärpolicyer | Använd **cmdleten Get-InformationBarrierPolicy.** <p> Syntax: `Get-InformationBarrierPolicy` <p> Denna cmdlet visar en lista över informationsbarriärprinciper som har definierats och deras status. |
| Det senaste programmet för informationsbarriärer | Använd **cmdleten Get-InformationBarrierPoliciesApplicationStatus.** <p> Syntax: `Get-InformationBarrierPoliciesApplicationStatus`<p> Den här cmdleten visar information om principprogrammet har slutförts, misslyckats eller pågår. |
| Alla principprogram för informationsbarriärer|Använd `Get-InformationBarrierPoliciesApplicationStatus -All`<p> Den här cmdleten visar information om principprogrammet har slutförts, misslyckats eller pågår.|

<!-- IN the " The most recent information barrier policy application, add link to troubleshooting topic -->

## <a name="what-if-i-need-to-remove-or-change-policies"></a>Vad händer om jag behöver ta bort eller ändra principer?

Det finns tillgängliga resurser som hjälper dig att hantera principer för informationsbarriärer.

- Om något går fel med informationsbarriärer, se [Felsökning av informationsbarriärer](information-barriers-troubleshooting.md).
- Information om hur du stoppar att principer används finns [i Stoppa ett principprogram.](information-barriers-edit-segments-policies.md#stop-a-policy-application)
- Information om hur du tar bort en informationsbarriärpolicy finns [i Ta bort en princip](information-barriers-edit-segments-policies.md#remove-a-policy).
- Information om hur du ändrar segment eller principer finns i [Redigera (eller ta bort) informationsbarriärprinciper.](information-barriers-edit-segments-policies.md)

## <a name="example-contosos-departments-segments-and-policies"></a>Exempel: Contosos avdelningar, segment och principer

I följande exempel kan du se hur en organisation kan definiera segment och principer.

### <a name="contosos-departments-and-plan"></a>Contosos avdelningar och plan

Contoso har fem avdelningar: PERSONAL, Försäljning, Marknadsföring, Forskning och Tillverkning. För att de ska fortsätta följa branschföreskrifter ska personer i vissa avdelningar inte kommunicera med andra avdelningar, som anges i följande tabell:

| Segment | Kan prata med | Kan inte prata med |
|:----------|:--------------|:-----------------|
| HR | Alla | (inga begränsningar) |
| Försäljning | HR, Marknadsföring, Tillverkning | Referensinformation |
| Marknadsföring | Alla | (inga begränsningar) |
| Referensinformation | HR, Marknadsföring, Tillverkning | Försäljning |
| Tillverkning | HR, Marknadsföring | Alla som inte är personalavdelningen eller marknadsföringsavdelningen |

För den här strukturen innehåller Contosos plan tre informationsbarriärprinciper:

1. En princip som utformats för att förhindra försäljning från att kommunicera med forskning (och en annan princip för att förhindra att Forskning kommunicerar med försäljning).

2. En princip som utformats för att tillverkning endast ska kunna kommunicera med HR och marknadsföring.

I det här scenariot behöver du inte definiera principer för personal och marknadsföring.

### <a name="contosos-defined-segments"></a>Contosos definierade segment

Contoso använder attributet Department i Azure Active Directory definiera segment enligt följande:

| Department | Segmentdefinition |
|:-------------|:---------------------|
| HR | `New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"` |
| Försäljning | `New-OrganizationSegment -Name "Sales" -UserGroupFilter "Department -eq 'Sales'"` |
| Marknadsföring | `New-OrganizationSegment -Name "Marketing" -UserGroupFilter "Department -eq 'Marketing'"` |
| Referensinformation | `New-OrganizationSegment -Name "Research" -UserGroupFilter "Department -eq 'Research'"` |
| Tillverkning | `New-OrganizationSegment -Name "Manufacturing" -UserGroupFilter "Department -eq 'Manufacturing'"` |

När de segment som definierats fortsätter Contoso att definiera principer.

### <a name="contosos-information-barrier-policies"></a>Contosos policyer för informationsbarriärer

Contoso definierar tre principer enligt beskrivningen i följande tabell:

| Princip | Principdefinition |
|:---------|:--------------------|
| **Princip 1: Förhindra försäljning från att kommunicera med forskning** | `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive` <p> I det här exemplet kallas informationsbarriärpolicyn *Försäljningsundersökning.* När den här principen är aktiv och används förhindrar det att användare i försäljningssegmentet kommunicerar med användare i segmenten Forskning. Den här principen är en envägspolicy. Det hindrar inte forskning från att kommunicera med försäljning. Då behövs princip 2. |
| **Princip 2: Förhindra att forskning kommunicerar med försäljning** | `New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive` <p> I det här exemplet kallas informationsbarriärpolicyn *Forskning-försäljning.* När den här principen är aktiv och används förhindrar det att användare som finns i segmenten Forskning kommunicerar med användare i försäljningssegmentet. |
| **Policy 3: Tillåta tillverkning att enbart kommunicera med HR och marknadsföring** | `New-InformationBarrierPolicy -Name "Manufacturing-HRMarketing" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR","Marketing","Manufacturing" -State Inactive` <p> I det här fallet kallas informationsbarriärpolicyn *Tillverkning-HRMarketing.* När den här principen är aktiv och används kan Tillverkning bara kommunicera med HR och marknadsföring. HR och marknadsföring är inte begränsade till att kommunicera med andra segment. |

När segment och principer har definierats tillämpar Contoso principerna genom att köra cmdleten **Start-InformationBarrierPoliciesApplication.**

När cmdleten har avslutats följer Contoso de juridiska kraven och branschkraven.

## <a name="resources"></a>Resurser

- [Få en översikt över informationsbarriärer](information-barriers.md)
- [Läs mer om informationsbarriärer i Microsoft Teams](/MicrosoftTeams/information-barriers-in-teams)
- [Läs mer om informationsbarriärer i SharePoint Online](/sharepoint/information-barriers)
- [Läs mer om informationsbarriärer i OneDrive](/onedrive/information-barriers)