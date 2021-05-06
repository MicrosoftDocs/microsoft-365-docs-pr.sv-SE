---
title: Kom igång med privilegierad åtkomsthantering
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: ''
description: I den här artikeln kan du läsa mer om hur du aktiverar och konfigurerar hantering av behörighet Office 365.
ms.openlocfilehash: 0b8d79c3012ecd321d7b00c1566aa557077d55f1
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/06/2021
ms.locfileid: "52161794"
---
# <a name="get-started-with-privileged-access-management"></a>Kom igång med privilegierad åtkomsthantering

I det här avsnittet får du hjälp med att aktivera och konfigurera hantering av behörighet i din organisation. Du kan använda antingen Microsoft 365 administrationscenter eller PowerShell Exchange management för att hantera och använda behörighet.

## <a name="before-you-begin"></a>Innan du börjar

Innan du kommer igång med hantering av behörighet ska du bekräfta [Microsoft 365-prenumerationen](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) och alla tillägg. Om du vill komma åt och använda hantering av privilegierad åtkomst måste din organisation ha någon av följande prenumerationer eller tillägg:

- Microsoft 365 E5 prenumeration (betald version eller utvärderingsversion)
- Microsoft 365 E3 -prenumeration (Office 365 E3-abonnemang + Enterprise Mobility and Security E3)+ Microsoft 365 E5 Compliance-tillägget
- Alla Microsoft 365, Office 365, Exchange, SharePoint eller OneDrive för företag-prenumerationen + Microsoft 365 E5-tillägget Microsoft 365 E5 Insider Risk Management  
- Microsoft 365 A5-prenumeration (betald eller utvärderingsversion)
- Microsoft 365 A3-abonnemang (Office 365 A3 prenumeration + Enterprise Mobility and Security A3-prenumeration) + tillägget Microsoft A5 efterlevnad
- Alla Microsoft 365, Office 365, Exchange, SharePoint eller OneDrive för utbildning-prenumerationen + Microsoft 365 A5 Insider Risk Management-tillägget
- Office 365 Enterprise E5-prenumeration (betald eller utvärderingsversion)
- Office 365 Enterprise E3-prenumeration + Office 365 Advanced Compliance-tillägget (inte längre tillgängligt för nya prenumerationer, se anteckningen)

Användare som skickar och svarar på begäran om behörighet för åtkomsthantering måste tilldelas någon av licenserna ovan.

>[!IMPORTANT]
>Office 365 Advanced Compliance säljs inte längre som en fristående prenumeration. När aktuella prenumerationer går ut bör kunderna gå över till en av prenumerationerna ovan, som innehåller samma eller ytterligare efterlevnadsfunktioner.

Om du inte har ett befintligt Office 365 Enterprise E5-abonnemang och vill prova hantering av behörighet kan du lägga till [](https://www.microsoft.com/microsoft-365/enterprise) [Microsoft 365](/office365/admin/try-or-buy-microsoft-365) i din befintliga Office 365-prenumeration eller registrera dig för en utvärderingsversion av Microsoft 365 Enterprise E5.

## <a name="enable-and-configure-privileged-access-management"></a>Aktivera och konfigurera hantering av privilegierad åtkomst

Följ de här anvisningarna för att konfigurera och använda behörighetsbehörighet i din organisation:

- [Steg 1: Skapa en godkännaresgrupp](privileged-access-management-configuration.md#step1)

    Innan du börjar använda behörighet ska du bestämma vem som behöver godkännandebehörighet för inkommande förfrågningar om åtkomst till uppgifter med förhöjd behörighet. Alla användare som ingår i godkännargruppen kan godkänna åtkomstförfrågningar. Den här gruppen aktiveras genom att en e-postaktiverad säkerhetsgrupp skapas i Office 365.

- [Steg 2: Aktivera privilegierad åtkomst](privileged-access-management-configuration.md#step2)

    Behörighet måste uttryckligen aktiveras i Office 365 med standardbehörighetsgruppen för godkännare, inklusive en uppsättning systemkonton som du vill ska undantas från åtkomsthanteringens åtkomstkontroll.

- [Steg 3: Skapa en åtkomstprincip](privileged-access-management-configuration.md#step3)

    Om du skapar en godkännandeprincip kan du definiera specifika godkännandekrav som gäller för enskilda uppgifter. Alternativen för godkännandetyper är **Automatiska** eller **Manuella**.

- [Steg 4: Skicka/godkänna behörighetsåtkomstförfrågningar](privileged-access-management-configuration.md#step4)

    När den är aktiverad kräver behörigheten godkännanden för alla aktiviteter som har en associerad godkännandeprincip definierad. För uppgifter som ingår i en godkännandeprincip måste användarna begära och beviljas behörighetsgodkännande för att få den behörighet som krävs för att utföra uppgiften.

När godkännande har beviljats kan den som begär behörighet köra den avsedda uppgiften och behörigheten att auktorisera och köra uppgiften åt användaren. Godkännandet förblir giltigt under den begärda varaktigheten (standardlängden är 4 timmar), under vilken den som begär kan köra den avsedda aktiviteten flera gånger. Alla sådana körningar loggas och görs tillgängliga för granskning av säkerhet och efterlevnad. 

>[!NOTE]
>Om du vill använda Exchange Management PowerShell för att aktivera och konfigurera behörighetsåtkomst följer du stegen i [Anslut för Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa) med multifaktorautentisering för att ansluta till Exchange Online PowerShell med dina Office 365-autentiseringsuppgifter. Du behöver inte aktivera multifaktorautentisering för din organisation för att kunna använda stegen för att aktivera privilegierad åtkomst när du ansluter till Exchange Online PowerShell. Om du ansluter med multifaktorautentisering skapas en OAuth-token som används av behörig åtkomst för att signera dina begäranden.

<a name="step1"> </a>

## <a name="step-1-create-an-approvers-group"></a>Steg 1: Skapa en godkännaresgrupp

1. Logga in Microsoft 365 [administrationscenter med](https://admin.microsoft.com) autentiseringsuppgifter för ett administratörskonto i organisationen.

2. Gå till Lägg till grupp i  >  **administrationscentret.**

3. Välj **e-postaktiverad säkerhetsgrupp** och fyll i **fälten Namn,** Grupp-e-postadress **och** Beskrivning för den nya gruppen. 

4. Spara gruppen. Det kan ta några minuter innan gruppen har konfigurerats helt och visas i Microsoft 365 administrationscenter.

5. Välj den nya godkännaren och välj Redigera för **att** lägga till användare i gruppen.

6. Spara gruppen.

<a name="step2"> </a>

## <a name="step-2-enable-privileged-access"></a>Steg 2: Aktivera privilegierad åtkomst

### <a name="in-the-microsoft-365-admin-center"></a>I Microsoft 365 Administrationscenter

1. Logga in på [Microsoft 365 administrationscenter med](https://admin.microsoft.com) autentiseringsuppgifter för ett administratörskonto i organisationen.

2. Gå till administrationscentret och gå till sidan **Inställningar**  >  **för Inställningar** åtkomst &  >  **sekretessbehörighet.**  >  

3. Aktivera kontrollen **Kräv godkännanden för behöriga** uppgifter.

4. Tilldela godkännaren den grupp du skapade i steg 1 som **standard godkännare.**

5. **Spara** och **stäng**.

### <a name="in-exchange-management-powershell"></a>I Exchange Management PowerShell

Om du vill aktivera behörighetsåtkomst och tilldela godkännarens grupp kör du följande kommando i Exchange Online PowerShell:

```PowerShell
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```

Exempel:

```PowerShell
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', 'sys2@fabrikamorg.onmicrosoft.com')
```

>[!NOTE]
>Funktionen för systemkonton är tillgänglig för att säkerställa att vissa automatiseringar inom organisationen kan fungera utan att vara beroende av privilegierad åtkomst, men vi rekommenderar att sådana undantag blir undantag som inte är tillåtna och att de tillåts godkänns och granskas regelbundet.

<a name="step3"> </a>

## <a name="step-3-create-an-access-policy"></a>Steg 3: Skapa en åtkomstprincip

Du kan skapa och konfigurera upp till 30 principer för behörighet för din organisation.

### <a name="in-the-microsoft-365-admin-center"></a>I Microsoft 365 Administrationscenter

1. Logga in på [Microsoft 365 administrationscenter med](https://admin.microsoft.com) autentiseringsuppgifter för ett administratörskonto i organisationen.

2. Gå till administrationscentret och gå till sidan **Inställningar**  >  **för Inställningar** åtkomst &  >  **sekretessbehörighet.**  >  

3. Välj **Hantera åtkomstprinciper och -begäranden.**

4. Välj **Konfigurera principer** och välj Lägg till en **princip.**

5. I listrutan väljer du lämpliga värden för din organisation:
    
    **Principtyp**: Aktivitet, Roll eller Rollgrupp

    **Policyomfattning**: Exchange

    **Principnamn:** Välj bland tillgängliga principer

    **Godkännandetyp**: Manuell eller Automatisk

    **Godkännandegrupp:** Välj den godkännargrupp som skapades i steg 1

6. Välj **Skapa** och sedan **Stäng.** Det kan ta några minuter innan principen har konfigurerats och aktiverats helt.

### <a name="in-exchange-management-powershell"></a>I Exchange Management PowerShell

Om du vill skapa och definiera en godkännandeprincip kör du följande kommando i Exchange Online PowerShell:

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\<exchange management cmdlet name>' -ApprovalType <Manual, Auto> -ApproverGroup '<default/custom approver group>'
```

Exempel:

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\New-MoveRequest' -ApprovalType Manual -ApproverGroup 'mbmanagers@fabrikamorg.onmicrosoft.com'
```

<a name="step4"> </a>

## <a name="step-4-submitapprove-privileged-access-requests"></a>Steg 4: Skicka/godkänna behörighetsåtkomstförfrågningar

### <a name="requesting-elevation-authorization-to-execute-privileged-tasks"></a>Begära autentisering av höjd för att utföra behöriga uppgifter

Begäranden om behörighet är giltiga i upp till 24 timmar efter att begäran har skickats. Om begärandena inte har godkänts eller nekats, upphör att gälla och åtkomst är inte godkända.

#### <a name="in-the-microsoft-365-admin-center"></a>I Microsoft 365 Administrationscenter

1. Logga in på [Microsoft 365 administrationscenter med](https://admin.microsoft.com) dina autentiseringsuppgifter.

2. Gå till administrationscentret och gå till sidan **Inställningar**  >  **för Inställningar** åtkomst &  >  **sekretessbehörighet.**  >  

3. Välj **Hantera åtkomstprinciper och -begäranden.**

4. Välj **Ny begäran.** I listrutan väljer du lämpliga värden för din organisation:

    **Typ av** begäran: Uppgift, Roll eller Rollgrupp

    **Begäran om omfattning:** Exchange

    **Begäran om:** Välj bland tillgängliga principer

    **Varaktighet (timmar)**: Antal timmar begärd åtkomst. Det finns ingen gräns för hur många timmar som kan begäras.

    **Kommentarer:** Textfält för kommentarer som är relaterade till din åtkomstbegäran

5. Välj **Spara** och sedan **Stäng.** Din begäran skickas till godkännarens grupp via e-post.

#### <a name="in-exchange-management-powershell"></a>I Exchange Management PowerShell

Kör följande kommando i Exchange Online PowerShell för att skapa och skicka en begäran om godkännande till godkännaren:

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```

Exempel:

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```

### <a name="view-status-of-elevation-requests"></a>Visa status för höjdbegäranden

När en begäran om godkännande har skapats kan status för höjdbegäran granskas i administrationscentret eller i Exchange Management PowerShell med hjälp av det som är associerat med begärande-ID.

#### <a name="in-the-microsoft-365-admin-center"></a>I Microsoft 365 administrationscenter

1. Logga in på [Microsoft 365 administrationscenter](https://admin.microsoft.com) med dina autentiseringsuppgifter.

2. Gå till administrationscentret och gå till sidan **Inställningar**  >  **för Inställningar** åtkomst &  >  **sekretessbehörighet.**  >  

3. Välj **Hantera åtkomstprinciper och -begäranden.**

4. Välj **Visa** för att filtrera skickade begäranden **efter Status för Väntande**, **Godkänd**, Nekad **eller Customer Lockbox.** 

#### <a name="in-exchange-management-powershell"></a>I Exchange Management PowerShell

Kör följande kommando i Exchange Online PowerShell för att visa statusen för en begärande för ett visst ID:

```PowerShell
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```

Exempel:

```PowerShell
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a>Godkänna en begäran om autentiseringssökning

När en begäran om godkännande skapas får medlemmar i den relevanta godkännargruppen ett e-postmeddelande och kan godkänna den begäran som är kopplad till begärans ID. Beställaren meddelas om begärans godkännande eller av nekande via e-postmeddelande.

#### <a name="in-the-microsoft-365-admin-center"></a>I Microsoft 365 administrationscenter

1. Logga in på [Microsoft 365 administrationscenter](https://admin.microsoft.com) med dina autentiseringsuppgifter.

2. Gå till administrationscentret och gå till sidan **Inställningar**  >  **för Inställningar** åtkomst &  >  **sekretessbehörighet.**  >  

3. Välj **Hantera åtkomstprinciper och -begäranden.**

4. Välj en begäran i listan för att visa informationen och vidta åtgärder för begäran.

5. Välj **Godkänn** för att godkänna begäran eller **välj Neka** för att neka begäran. Tidigare godkända begäranden kan få åtkomst återkallad genom att välja **Återkalla**.

#### <a name="in-exchange-management-powershell"></a>I Exchange Management PowerShell

Om du vill godkänna en begäran om autentiseringssökning kör du följande kommando i Exchange Online PowerShell:

```PowerShell
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```

Exempel:

```PowerShell
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```

Om du vill neka en autentiseringsbegäran för höjd kör du följande kommando i Exchange Online PowerShell:

```PowerShell
Deny-ElevatedAccessRequest -RequestId <request id> -Comment '<denial comment>'
```

Exempel:

```PowerShell
Deny-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<denial comment>'
```

## <a name="delete-a-privileged-access-policy-in-office-365"></a>Ta bort en princip för privilegierad åtkomst i Office 365

Om den inte längre behövs i organisationen kan du ta bort en princip för privilegierad åtkomst.

### <a name="in-the-microsoft-365-admin-center"></a>I Microsoft 365 administrationscenter

1. Logga in Microsoft 365 [administrationscenter med](https://admin.microsoft.com) autentiseringsuppgifter för ett administratörskonto i organisationen.

2. Gå till administrationscentret och gå till sidan **Inställningar**  >  **för Inställningar** åtkomst &  >  **sekretessbehörighet.**  >  

3. Välj **Hantera åtkomstprinciper och -begäranden.**

4. Välj **Konfigurera principer.**

5. Markera den princip du vill ta bort och välj sedan Ta **bort princip.**

6. Välj **Stäng**.

### <a name="in-exchange-management-powershell"></a>I Exchange Management PowerShell

Om du vill ta bort en princip för privilegierad åtkomst kör du följande kommando Exchange Online Powershell:

```PowerShell
Remove-ElevatedAccessApprovalPolicy -Identity <identity GUID of the policy you want to delete>
```

## <a name="disable-privileged-access-in-office-365"></a>Inaktivera behörighet i Office 365

Om det behövs kan du inaktivera hantering av behörighet för organisationen. Om du inaktiverar behörighet tas inte associerade principer eller godkännargrupper bort.

### <a name="in-the-microsoft-365-admin-center"></a>I Microsoft 365 administrationscenter

1. Logga in på [Microsoft 365 administrationscenter](https://admin.microsoft.com) med autentiseringsuppgifter för ett administratörskonto i organisationen.

2. Gå till administrationscentret och gå till sidan **Inställningar**  >  **för Inställningar** åtkomst &  >  **sekretessbehörighet.**  >  

3. Aktivera funktionen **Kräv godkännanden för behörighetsbehörighet.**

### <a name="in-exchange-management-powershell"></a>I Exchange Management PowerShell

Om du vill inaktivera behörighet kör du följande kommando i Exchange Online Powershell:

```PowerShell
Disable-ElevatedAccessControl
```
