---
title: Så här identifierar du typen av väntande objekt som en Exchange Online postlådan
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6057daa8-6372-4e77-a636-7ea599a76128
ms.custom:
- seo-marvel-apr2020
description: Lär dig att identifiera de olika typer av väntande objekt som kan placeras i en Exchange Online postlåda i Microsoft 365.
ms.openlocfilehash: 0fdfbd4503a4ddffd2ce2dd97c6af42684aea293
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162001"
---
# <a name="how-to-identify-the-type-of-hold-placed-on-an-exchange-online-mailbox"></a>Så här identifierar du typen av väntande objekt som en Exchange Online postlådan

I den här artikeln förklarar vi hur du identifierar spärrade Exchange Online postlådor i Microsoft 365.

Microsoft 365 finns flera sätt som organisationen kan förhindra att postlådeinnehåll tas bort permanent. På så sätt kan organisationen behålla innehåll för att uppfylla efterlevnadsföreskrifter eller under juridiska och andra typer av undersökningar. Här är en lista över de kvarhållningsfunktioner som kallas *kvarhållning i* Office 365:

- **[Bevarande av juridiska skäl:](create-a-litigation-hold.md)** Kvarhåller som tillämpas på användarnas postlådor i Exchange Online.

- **[eDiscovery-kvart:](create-ediscovery-holds.md)** Innehåller som är kopplade till ett grundläggande eDiscovery-ärende i säkerhets- och efterlevnadscentret. eDiscovery-inkorgar kan tillämpas på användarpostlådor och till motsvarande postlåda för Microsoft 365 Grupper och Microsoft Teams.

- **[Håll på plats:](/Exchange/security-and-compliance/create-or-remove-in-place-holds)** Innehåller som tillämpas på användarpostlådor med hjälp av verktyget In-Place eDiscovery & Hold i Exchange administrationscenter i Exchange Online. 

   > [!NOTE]
   > In-Place har tagits ur bruk och du kan inte längre skapa eller In-Place eller använda dem för postlådor. Det kan In-Place kvar att gälla för postlådor i organisationen, vilket är anledningen till att de tas med i den här artikeln. Mer information finns i Gamla [eDiscovery-verktyg .](legacy-ediscovery-retirement.md#in-place-ediscovery-and-in-place-holds-in-the-exchange-admin-center)

- **[Microsoft 365 bevarandeprinciper:](retention.md)** Kan konfigureras för att behålla (eller behålla och sedan ta bort) innehåll i användarpostlådor i Exchange Online och i motsvarande postlåda för Microsoft 365 Grupper och Microsoft Teams. Du kan också skapa en bevarandeprincip för att behålla Skype för företag konversationer, som lagras i användarnas postlådor.

  Det finns två typer Microsoft 365 bevarandeprinciper som kan tilldelas till postlådor.

    - **Specifika bevarandeprinciper för plats:** Det här är principer som tilldelas till innehållsplatser för specifika användare. Du använder **cmdlet:en Get-Mailbox** i Exchange Online PowerShell för att få information om bevarandeprinciper som tilldelats till specifika postlådor. Mer information om den här typen av bevarandeprincip finns i avsnittet En princip med särskilda inkluderings- eller [undantag från](create-retention-policies.md#a-policy-with-specific-inclusions-or-exclusions) dokumentationen för bevarandeprinciper.

    - **Bevarandeprinciper för hela organisationen:** Det här är principer som tilldelas till alla innehållsplatser i organisationen. Du använder **cmdlet Get-OrganizationConfig** i Exchange Online PowerShell för att få information om bevarandeprinciper som gäller hela organisationen. Mer information om den här typen av bevarandeprincip finns i avsnittet En princip som gäller för hela platser [från](create-retention-policies.md#a-policy-that-applies-to-entire-locations) dokumentationen för bevarandeprinciper.

- **[Microsoft 365](retention.md)** bevarandeetiketter: Om en användare använder en bevarandeetikett för Microsoft 365 (en som har konfigurerats för  att behålla innehåll eller behålla och sedan ta bort innehåll) på en mapp eller ett objekt i postlådan, placeras ett bevarande på postlådan som om postlådan hade bevarande av juridiska skäl eller tilldelats en Microsoft 365-bevarandeprincip. Mer information finns i avsnittet Identifiera postlådor som är på plats eftersom en [bevarandeetikett](#identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item) har använts på en mapp eller ett objekt i den här artikeln.

Om du vill hantera undantagna postlådor kan du behöva identifiera typen av undantag som placerats i en postlåda så att du kan utföra uppgifter som att ändra varaktighet för undantag, tillfälligt eller permanent ta bort undantaget eller exkludera en postlåda från en Microsoft 365-bevarandeprincip. I dessa fall är det första steget att identifiera typen av väntande ärenden som postlådan har placerats i. Och eftersom flera spärrade objekt (och olika typer av spärrade objekt) kan placeras i en enda postlåda måste du identifiera alla spärrade objekt som har placerats i en postlåda om du vill ta bort eller ändra ett spärrat objekt.

## <a name="step-1-obtain-the-guid-for-holds-placed-on-a-mailbox"></a>Steg 1: Hämta GUID för spärrade mål för en postlåda

Du kan köra följande två cmdlets i Exchange Online PowerShell för att få GUID för de som sätts i en postlåda. När du har skaffat en GUID kan du använda det för att identifiera det specifika väntande steget i steg 2. Bevarande av juridiska skäl identifieras inte av ett GUID. Bevarande av juridiska skäl är antingen aktiverat eller inaktiverat för en postlåda.

- **Get-Mailbox:** Använd detta cmdlet för att avgöra om Bevarande av juridiska skäl är aktiverat för en postlåda och för att få GUID:er för eDiscovery-kvarhållning, In-Place-kvarhållningsprinciper och Microsoft 365-bevarandeprinciper som specifikt tilldelas till en postlåda. Utdata för den här cmdleten anger också om en postlåda uttryckligen har uteslutits från en bevarandeprincip för hela organisationen.

- **Get-OrganizationConfig:** Använd den här cmdleten för att få GUID:er för bevarandeprinciper för hela organisationen.

Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

### <a name="get-mailbox"></a>Get-Mailbox

Kör följande kommando för att få information om kvarhållnings- Microsoft 365 bevarandeprinciper som tillämpas på en postlåda.

```powershell
Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
```

> [!TIP]
> Om det finns för många värden i egenskapen InPlaceHolds och inte alla visas kan du köra kommandot för att visa varje `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` GUID på en separat rad.

I följande tabell beskrivs hur du identifierar olika typer av kvarhållning baserat på värdena i egenskapen *InPlaceHolds* när du kör cmdleten **Get-Mailbox.**

|Typ av håll  |Exempelvärde  |Så här identifierar du väntande tid  |
|---------|---------|---------|
|Bevarande av juridiska skäl     |    `True`     |     Bevarande av juridiska skäl aktiveras för en postlåda när egenskapen *LitigationHoldEnabled* är inställd på `True` .    |
|eDiscovery-kvart     |  `UniH7d895d48-7e23-4a8d-8346-533c3beac15d`       |   Egenskapen *InPlaceHolds innehåller* GUID för alla håll som är kopplade till ett eDiscovery-ärende i säkerhets- och efterlevnadscentret. Du ser att det är ett eDiscovery-håll eftersom GUID börjar med prefixet (vilket betecknar ett `UniH` enhetligt håll).      |
|In-Place på     |     `c0ba3ce811b6432a8751430937152491` <br/> eller <br/> `cld9c0a984ca74b457fbe4504bf7d3e00de`  |     Egenskapen *InPlaceHolds* innehåller GUID för det In-Place håll som finns i postlådan. Du ser att det är ett In-Place håll ned eftersom GUID antingen inte börjar med ett prefix eller börjar med `cld` prefixet.     |
|Microsoft 365 specifika bevarandeprinciper för postlådan     |    `mbxcdbbb86ce60342489bff371876e7f224:1` <br/> eller <br/> `skp127d7cf1076947929bf136b7a2a8c36f:3`     |     Egenskapen InPlaceHolds innehåller GUID för alla specifika bevarandeprinciper som tillämpas på postlådan. Du kan identifiera bevarandeprinciper eftersom GUID startar med `mbx` `skp` prefixet eller. Prefixet `skp` anger att bevarandeprincipen tillämpas på Skype för företag konversationer i användarens postlåda.    |
|Är undantagen från en organisationsomfattande Microsoft 365 bevarandeprincip     |   `-mbxe9b52bf7ab3b46a286308ecb29624696`      |     Om en postlåda är undantagen från en organisationsomfattande Microsoft 365-bevarandeprincip visas GUID för den bevarandeprincip som postlådan är undantagen från i egenskapen InPlaceHolds och identifieras med `-mbx` prefixet.    |

### <a name="get-organizationconfig"></a>Get-OrganizationConfig
Om egenskapen *InPlaceHolds* är tom när du kör cmdleten **Get-Mailbox** kan det fortfarande finnas Microsoft 365 bevarandeprinciper för hela organisationen som tillämpas på postlådan. Kör följande kommando i Exchange Online PowerShell för att få en lista över GUID:er för organisationen Microsoft 365 bevarandeprinciper.

```powershell
Get-OrganizationConfig | FL InPlaceHolds
```

> [!TIP]
> Om det finns för många värden i egenskapen InPlaceHolds och inte alla visas kan du köra kommandot för att visa varje `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` GUID på en separat rad.

I följande tabell beskrivs de olika typerna av innehåll som gäller för hela organisationen och hur du identifierar varje typ baserat på de GUID som finns i egenskapen *InPlaceHolds* när du kör cmdleten **Get-OrganizationConfig.**

|Typ av håll  |Exempelvärde  |Beskrivning  |
|---------|---------|---------|
|Microsoft 365 bevarandeprinciper som tillämpas Exchange postlådor, Exchange gemensamma mappar och Teams chattar    |      `mbx7cfb30345d454ac0a989ab3041051209:2`   |   Organisationsomfattande bevarandeprinciper som tillämpas på Exchange-postlådor, Exchange gemensamma mappar och 1xN-chattar i Microsoft Teams identifieras med GUID som börjar med `mbx` prefixet. Obs! 1xN-chattar lagras i postlådan för de enskilda chattdeltagarna.      |
|Microsoft 365 bevarandeprincip som används Microsoft 365 grupper och Teams kanalmeddelanden     |   `grp1a0a132ee8944501a4bb6a452ec31171:3`      |    Organisationsomfattande bevarandeprinciper som tillämpas Microsoft 365 grupper och kanalmeddelanden i Microsoft Teams identifieras med GUID som börjar med `grp` prefixet. Meddelanden i kanalen lagras i den grupppostlåda som är kopplad till ett Microsoft Team.     |

Mer information om bevarandeprinciper som tillämpas på Microsoft Teams finns i [Läs mer om bevarandeprinciper för Microsoft Teams](retention-policies-teams.md).

### <a name="understanding-the-format-of-the-inplaceholds-value-for-retention-policies"></a>Förstå formatet för värdet InPlaceHolds för bevarandeprinciper

Förutom det prefix (mbx, skp eller grp) som identifierar ett objekt i egenskapen InPlaceHolds som en Microsoft 365-bevarandeprincip innehåller värdet även ett suffix som identifierar vilken typ av bevarandeåtgärd som har konfigurerats för principen. Åtgärdssuffixet är till exempel markerat i fetstil i följande exempel:

   `skp127d7cf1076947929bf136b7a2a8c36f`**:1**

   `mbx7cfb30345d454ac0a989ab3041051209`**:2**

   `grp1a0a132ee8944501a4bb6a452ec31171`**:3**

I följande tabell definieras de tre möjliga bevarandeåtgärderna:

|Värde  |Beskrivning  |
|---------|---------|
|**1**     | Anger att bevarandeprincipen har konfigurerats för att ta bort objekt. Principen behåller inte objekt.        |
|**2**    |    Anger att bevarandeprincipen är konfigurerad att innehålla objekt. Inga objekt tas bort med principen när de har förfallit.     |
|**3**     |   Anger att bevarandeprincipen har konfigurerats för att innehålla objekt och att de sedan tas bort efter att de har förfallit.      |

Mer information om bevarandeåtgärder finns i [avsnittet Behålla innehåll under en viss tidsperiod.](create-retention-policies.md#retaining-content-for-a-specific-period-of-time)
   
## <a name="step-2-use-the-guid-to-identify-the-hold"></a>Steg 2: Använd GUID för att identifiera antalet hållna

När du har fått GUID för ett väntande tillstånd som tillämpas på en postlåda är nästa steg att använda det GUID för att identifiera väntande identifiering. I följande avsnitt visas hur du identifierar namnet på kvarstående information (och annan information) med hjälp av guiD för håll.

### <a name="ediscovery-holds"></a>eDiscovery-kvarhåller

Kör följande kommandon i Säkerhets- & Efterlevnadscenter PowerShell för att identifiera ett eDiscovery-skal som tillämpas på postlådan. Använd GUID (inte inklusive UniH-prefixet) för det eDiscovery-värde du identifierade i steg 1. 

Information om hur du ansluter & säkerhets- och efterlevnadscenter för PowerShell finns Anslut [säkerhet- & Säkerhets- och efterlevnadscenter PowerShell.](/powershell/exchange/connect-to-scc-powershell)

Det första kommandot skapar en variabel som innehåller information om fältet. Den här variabeln används i andra kommandon. Det andra kommandot visar namnet på det eDiscovery-fall som det är kopplat till. Det tredje kommandot visar namnet på fältet och en lista över postlådorna som fältet gäller för.

```powershell
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```powershell
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```powershell
$CaseHold | FL Name,ExchangeLocation
```

### <a name="in-place-holds"></a>In-Place in innehåller

Kör följande kommando i Exchange Online PowerShell för att identifiera det In-Place som tillämpas på postlådan. Använd GUID för det In-Place som du identifierade i steg 1. Kommandot visar namnet på fältet och en lista över postlådorna som fältet gäller för.

```powershell
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name,SourceMailboxes
```

Om GUID för In-Place start med prefixet ska du se till att ta med `cld` prefixet när föregående kommando körs.

> [!IMPORTANT]
> Medan vi fortsätter att investera på olika sätt för att bevara postlådeinnehållet tillkännager vi att In-Place Holds i administrationscentret för Exchange (EAC) kommer att gå ur. Från och med den 1 juli 2020 kan du inte skapa nya In-Place i Exchange Online. Men du kan fortfarande hantera e-In-Place i EAC eller med hjälp av **cmdleten Set-MailboxSearch** i Exchange Online PowerShell. Men med början den 1 oktober 2020 kan du inte hantera nya In-Place. Du tar bara bort dem i EAC eller med cmdleten **Remove-MailboxSearch.** Mer information om hur du tar In-Place [eDiscovery-verktyg finns i Slutet av äldre eDiscovery-verktyg.](legacy-ediscovery-retirement.md)

### <a name="microsoft-365-retention-policies"></a>Microsoft 365 bevarandeprinciper

Kör följande kommando i Säkerhets- & Efterlevnadscenter PowerShell för att identitet Microsoft 365 bevarandeprincip (organisationsomfattande eller specifik plats) som tillämpas på postlådan. Använd GUID (utan att ta med prefixet mbx, skp eller grp eller åtgärdssuffixet) som du identifierade i steg 1.

```powershell
Get-RetentionCompliancePolicy <hold GUID without prefix or suffix> -DistributionDetail  | FL Name,*Location
```

## <a name="identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item"></a>Identifiera postlådor som är i bevarande eftersom en bevarandeetikett har tillämpats på en mapp eller ett objekt

När en användare använder en bevarandeetikett som har konfigurerats för att behålla innehåll eller behålla och sedan ta bort innehåll för en mapp eller ett objekt i postlådan sätts egenskapen *ComplianceTagHoldApplied-postlåda* till **True.** När detta händer anses postlådan vara bevarande, som om den hade satts på bevarande av juridiska skäl eller har tilldelats en Microsoft 365 bevarandeprincip. När egenskapen *ComplianceTagHoldApplied* är inställd på **Sant** kan följande inträffa:

- Om postlådan eller användarens användarkonto tas bort blir postlådan en [inaktiv postlåda.](inactive-mailboxes-in-office-365.md)
- Du kan inte inaktivera postlådan (den primära postlådan eller arkivpostlådan om den är aktiverad).
- Objekt i postlådan kan behållas under en längre tid än väntat. Det beror på att postlådan är på plats och därför tas inga objekt bort permanent (rensas bort).

Om du vill visa värdet för *egenskapen ComplianceTagHoldApplied* kör du följande kommando i Exchange Online PowerShell:

```powershell
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

Mer information om bevarandeetiketter finns i [Bevarandeetiketter.](retention.md#retention-labels)

## <a name="managing-mailboxes-on-delay-hold"></a>Hantera postlådor som är väntande

När du har tagit bort alla typer av väntande objekt från en *postlåda, tillämpas ett* fördröjningsfördröjning. Det innebär att den faktiska borttagningen av isen fördröjs i 30 dagar för att förhindra att data tas bort permanent (rensas) från postlådan. Det här ger administratörer en möjlighet att söka efter eller återställa postlådeobjekt som kommer att rensas när ett håll har tagits bort. Ett väntande fel placeras i en postlåda nästa gång assistenten för hanterade mappar bearbetar postlådan och upptäcker att ett väntande objekt har tagits bort. Specifikt tillämpas ett väntande på en postlåda när assistenten för hanterade mappar anger något av följande egenskaper för postlådan till **Sant:**

- **DelayHoldApplied:** Den här egenskapen gäller e-postrelaterat innehåll (som genereras av personer som använder Outlook och Outlook på webben) som lagras i en användares postlåda.

- **DelayReleaseHoldApplied:** Den här egenskapen gäller molnbaserat innehåll (som genereras av icke-Outlook-appar som Microsoft Teams, Microsoft Forms och Microsoft Yammer) som lagras i en användares postlåda. Molndata som genereras av en Microsoft-app lagras vanligtvis i en dold mapp i en användares postlåda.

När ett bevarande av en fördröjning sätts för postlådan (när någon av de tidigare egenskaperna har ställts in på **Sant)** anses postlådan fortfarande vara väntad med obegränsad bevarandetid som om postlådan hade bevarande av juridiska skäl. Efter 30 dagar går undantaget ut och Microsoft 365 försöker automatiskt ta bort undantaget (genom att sätta egenskapen DelayHoldApplied eller DelayReleaseHoldApplied till **False**) så att undantaget tas bort. När någon av dessa egenskaper har angetts till **False** rensas motsvarande objekt som har markerats för borttagning nästa gång postlådan bearbetas av assistenten för hanterade mappar.

Om du vill visa värdena för egenskaperna DelayHoldApplied och DelayReleaseHoldApplied för en postlåda kör du följande kommando i Exchange Online PowerShell.

```powershell
Get-Mailbox <username> | FL *HoldApplied*
```

Om du vill ta bort fördröjningen innan det förfaller kan du köra ett (eller båda) följande kommandon i Exchange Online PowerShell, beroende på vilken egenskap du vill ändra:

```powershell
Set-Mailbox <username> -RemoveDelayHoldApplied
```

Eller

```powershell
Set-Mailbox <username> -RemoveDelayReleaseHoldApplied
```

Du måste ha tilldelats rollen Juridiskt behåll i Exchange Online använda parametrarna *RemoveDelayHoldApplied* eller *RemoveDelayReleaseHoldApplied.* 

Om du vill ta bort fördröjningar från en inaktiv postlåda kör du något av följande kommandon Exchange Online PowerShell:

```powershell
Set-Mailbox <DN or Exchange GUID> -InactiveMailbox -RemoveDelayHoldApplied
```

Eller

```powershell
Set-Mailbox <DN or Exchange GUID> -InactiveMailbox -RemoveDelayReleaseHoldApplied
```

> [!TIP]
> Det bästa sättet att ange en inaktiv postlåda i det föregående kommandot är att använda det unika namnet eller det unika Exchange GUID-värdet. Om du använder något av dessa värden undviker du att ange fel postlåda av misstag. 

Mer information om hur du använder dessa parametrar för att hantera kvarsatta fördröjningar finns [i Set-Mailbox](/powershell/module/exchange/set-mailbox).

Tänk på följande när du hanterar en postlåda som är väntad:

- Om antingen egenskapen DelayHoldApplied eller DelayReleaseHoldApplied är inställd på **Sant** och en postlåda (eller det motsvarande användarkontot) tas bort blir postlådan en inaktiv postlåda. Det beror på att en postlåda anses vara satt på servern om någon av egenskapspostlådorna är antingen **True,** och om du tar bort en postlåda som är satt i servern, så finns det en inaktiv postlåda. Om du vill ta bort en postlåda och inte göra den till en inaktiv postlåda måste du ange båda egenskaperna till **Falskt.**

- Som tidigare nämnts anses en postlåda vara väntad med obegränsad varaktighet om antingen egenskapen DelayHoldApplied eller DelayReleaseHoldApplied är inställd på **Sant.** Det betyder dock inte att allt *innehåll* i postlådan bevaras. Det beror på vilket värde som anges för varje egenskap. Anta till exempel att båda egenskaperna är inställda på **Sant eftersom** de har tagits bort från postlådan. Sedan tar du bara bort det fördröjningsarflag som tillämpas på andra molndata än Outlook (med parametern *RemoveDelayReleaseHoldApplied).* Nästa gång assistenten för hanterade mappar bearbetar postlådan rensas alla Outlook objekt som markerats för borttagning. Alla Outlook objekt som markerats för borttagning rensas inte bort eftersom egenskapen DelayHoldApplied fortfarande är inställd på **Sant.** Motsatsen skulle också vara sant: om DelayHoldApplied är inställt på **False** och DelayReleaseHoldApplied är inställt på **Sant** rensas bara Outlook objekt som markerats för borttagning.

## <a name="next-steps"></a>Nästa steg

När du har identifierat undantagen som tillämpas på en postlåda kan du utföra uppgifter som att ändra varaktigheten för undantaget, tillfälligt eller permanent ta bort undantaget eller exkludera en inaktiv postlåda från en Microsoft 365 bevarandeprincip. Mer information om hur du utför uppgifter som ska spärras finns i följande avsnitt:

- Kör [kommandot Set-RetentionCompliancePolicy -Identity \<Policy Name> -AddExchangeLocationException \<user mailbox> ](/powershell/module/exchange/set-retentioncompliancepolicy) i Säkerhets- & Compliance Center PowerShell för att utesluta en postlåda från en organisationsomfattande Microsoft 365-bevarandeprincip. Det här kommandot kan bara användas för bevarandeprinciper där värdet för egenskapen *ExchangeLocation* är lika med `All` .

- [Ändra kvarhållningstiden för en inaktiv postlåda](change-the-hold-duration-for-an-inactive-mailbox.md)

- [Ta bort en inaktiv postlåda](delete-an-inactive-mailbox.md)

- [Ta bort objekt i mappen Återställningsbara objekt i molnbaserade postlådor som är på plats](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md)