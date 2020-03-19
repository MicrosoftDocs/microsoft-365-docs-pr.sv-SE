---
title: Privilegierad åtkomsthantering för din Testmiljö för Microsoft 365 Enterprise
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: Ent_TLGs
description: Använd den här testlabbguiden för att aktivera privilegierad åtkomsthantering din Testmiljö för Microsoft 365 Enterprise.
ms.openlocfilehash: ce637b94333f088d25e479e61ad2a98176a2f7c6
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42806778"
---
# <a name="privileged-access-management-for-your-microsoft-365-enterprise-test-environment"></a>Privilegierad åtkomsthantering för din Testmiljö för Microsoft 365 Enterprise

*Den här testlabbguiden kan användas för både testmiljöer för Microsoft 365 Enterprise och Office 365 Enterprise.*

Med instruktionerna i den här artikeln konfigurerar du privilegierad åtkomsthantering för att öka säkerheten i din Testmiljö för Microsoft 365 Enterprise.

![Testa labbguider för Microsoft-molnet](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

>[!TIP]
>Klicka [här](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) för en visuell karta till alla artiklar i Microsoft 365 Enterprise Test Lab Guide stacken.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fas 1: Bygg upp din Testmiljö för Microsoft 365 Enterprise

Om du bara vill konfigurera privilegierad åtkomsthantering på ett lättsätt med minimikraven följer du instruktionerna i [Lightweight-baskonfigurationen](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Om du vill konfigurera privilegierad åtkomsthantering i ett simulerat företag följer du instruktionerna i [direktautentisering](pass-through-auth-m365-ent-test-environment.md).
  
>[!NOTE]
>Testning av privilegierad åtkomsthantering kräver inte den simulerade företagstestmiljön, som innehåller ett simulerat intranät som är anslutet till Internet- och katalogsynkroniseringen för en AD DS-skog. Det finns här som ett alternativ så att du kan testa privilegierad åtkomsthantering och experimentera med den i en miljö som representerar en typisk organisation. 

## <a name="phase-2-configure-privileged-access-management"></a>Fas 2: Konfigurera hantering av privilegierad åtkomst

I den här fasen konfigurerar du en grupp för godkännare och aktiverar privilegierad åtkomsthantering för din Testmiljö för Microsoft 365 Enterprise. Mer information och en översikt över hantering av privilegierad åtkomst finns [i Privilegierad åtkomsthantering i Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).

Följ de här stegen för att konfigurera och använda privilegierad åtkomst i din Office 365-organisation:

- [Steg 1: Skapa en godkännares grupp](https://docs.microsoft.com/microsoft-365/compliance/privileged-access-management-configuration#step-1-create-an-approvers-group)

    Innan du börjar använda behörighetsåtkomst bör du bestämma vem som ska ha godkännandebehörighet för inkommande begäranden om åtkomst till upphöjda och privilegierade uppgifter. Alla användare som ingår i gruppen Godkännare kan godkänna åtkomstbegäranden. Detta aktiveras genom att skapa en e-postaktiverad säkerhetsgrupp i Office 365. Skapa en ny säkerhetsgrupp med namnet "Privileged Access Godkännare" i testmiljön och lägg till "Användare 3" som tidigare har skapats i tidigare testlabbguidesteg.

- [Steg 2: Aktivera privilegierad åtkomst](https://docs.microsoft.com/microsoft-365/compliance/privileged-access-management-configuration#step-2-enable-privileged-access)

    Privilegierad åtkomst måste uttryckligen aktiveras i Office 365 med standardgodkännargruppen och inkludera en uppsättning systemkonton som du vill ska uteslutas från den privilegierade åtkomståtkomstkontrollen för åtkomsthantering. Var noga med att aktivera privilegierad åtkomst i din Office 365-organisation innan du startar fas 3 i den här guiden.

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a>Fas 3: Kontrollera att godkännande krävs för förhöjda och privilegierade uppgifter

I den här fasen kontrollerar du att principen för privilegierad åtkomst fungerar och att användarna behöver godkännande för att utföra definierade förhöjda och privilegierade uppgifter.

### <a name="test-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a>Testförmåga att utföra en uppgift SOM INTE har definierats i en principiär åtkomst

Anslut först till Exchange Management PowerShell med autentiseringsuppgifterna för en användare som konfigurerats som global administratör i testmiljön och försök skapa en ny journalregel. Aktiviteten [Ny journalregel](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-journalrule?view=exchange-ps) definieras för närvarande inte i en princip för privilegierad åtkomst för din organisation.

1. Öppna och logga in på Exchange Online Remote PowerShell Module på **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** med hjälp av det globala administratörskontot för testmiljön.

2. Skapa en ny journalregel för din organisation i Exchange Management PowerShell:

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
```

4. Se att den nya journalregeln har skapats i Exchange Management PowerShell.

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a>Skapa en ny princip för privilegierad åtkomst för aktiviteten Ny journalregel

>[!NOTE]
>Om du inte redan har slutfört steg 1 och 2 från fas 2 i den här guiden måste du följa stegen för att skapa en godkännares grupp med namnet "Privilege Access Godkännare" och för att aktivera privilegierad åtkomst i testmiljön.

1. Logga in på [administrationscentret för Microsoft 365](https://admin.microsoft.com) med hjälp av autentiseringsuppgifter för global administratörskonto för testmiljön.

2. Gå till **Inställningar** > **sÃ & Sekretessprivilegierad** > **åtkomst**i administrationscentret.

3. Välj **Hantera åtkomstprinciper och begäranden**.

4. Välj **Konfigurera principer** och välj Lägg till en **princip**.

5. Markera eller ange följande värden i listrutan:

    **Principtyp**: Aktivitet

    **Policyomfattning**: Utbyte

    **Principnamn**: Ny journalregel

    **Typgodkännandetyp**: Manuell

    **Godkännandegrupp**: Privilegierade åtkomstgodkännare

6. Välj **Skapa** och **stäng**sedan . Det kan ta några minuter innan principen är helt konfigurerad och aktiverad. Var noga med att ge tid för principen att aktiveras fullt ut innan godkännandekravet testas i nästa steg.

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a>Krav på testgodkännande för aktiviteten Ny journalregel som definierats i en privilegierad åtkomstprincip

1. Öppna och logga in på Exchange Online Remote PowerShell Module på **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** med hjälp av det globala administratörskontot för testmiljön.

2. Skapa en ny journalregel för din organisation i Exchange Management PowerShell:

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```

3. Visa felet "Otillräckliga behörigheter" i Exchange Management PowerShell:

```ExchangeManagementPowerShell
Insufficient permissions. Please raise an elevated access request for this task.
    + CategoryInfo          : NotSpecified: (:) [], LocalizedException
    + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
    7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
    + PSComputerName        : outlook.office365.com
```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a>Begär åtkomst för att skapa en ny journalregel med aktiviteten New JournalRule

1. Logga in på [administrationscentret för Microsoft 365](https://admin.microsoft.com) med hjälp av det globala administratörskontot för testmiljön.

2. Gå till **Inställningar** > **sÃ & Sekretessprivilegierad** > **åtkomst**i administrationscentret.

3. Välj **Hantera åtkomstprinciper och begäranden**.

4. Välj **Ny begäran**. Välj lämpliga värden för organisationen i listrutan:

    **Typ av begäran:** Uppgift

    **Ärende :** Exchange

    **Begäran om**: Ny journalregel

    **Varaktighet (timmar)**: 2

    **Kommentarer**: Begär behörighet att skapa en ny journalregel

5. Välj **Spara** och **stäng**sedan . Din begäran kommer att skickas till godkännarens grupp via e-post.

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a>Godkänna begäran om privilegierad åtkomst för att skapa en ny journalregel

1. Logga in på [administrationscentret för Microsoft 365](https://admin.microsoft.com) med hjälp av autentiseringsuppgifterna för användare 3 i testmiljön (medlem i säkerhetsgruppen Privilegierad åtkomst godkännare i testmiljön).

2. Gå till **Inställningar** > **sÃ & Sekretessprivilegierad** > **åtkomst**i administrationscentret.

3. Välj **Hantera åtkomstprinciper och begäranden**.

4. Välj väntande begäran och välj **Godkänn** om du vill bevilja åtkomst till det globala administratörskontot för att skapa en ny journalregel. Ett e-postmeddelande som bekräftar att godkännande har beviljats kommer att skickas till det globala administratörskontot (den begärande användaren).  

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a>Testa att skapa en ny journalregel med privilegierad åtkomst som godkänts för aktiviteten New JournalRule

1. Öppna och logga in på Exchange Online Remote PowerShell Module på **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** med hjälp av det globala administratörskontot för testmiljön.

2. Skapa en ny journalregel för din organisation i Exchange Management PowerShell:

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```

3. Se att den nya journalregeln har skapats i Exchange Management PowerShell.

## <a name="next-step"></a>Nästa steg

Utforska ytterligare [funktioner för informationsskydd](m365-enterprise-test-lab-guides.md#information-protection) i testmiljön.

## <a name="see-also"></a>Se även

[Labbguider för Microsoft 365 Enterprise Test](m365-enterprise-test-lab-guides.md)

[Distribuera Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Dokumentation för Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
