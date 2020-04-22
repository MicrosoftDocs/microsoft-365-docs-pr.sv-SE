---
title: Hantering av privilegierad åtkomst för microsoft 365 Enterprise-testmiljön
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
description: Använd den här testlabbet-guiden om du vill aktivera hantering av privilegierad åtkomst din Microsoft 365 Enterprise-testmiljö.
ms.openlocfilehash: 27f63de138f388b0dcbc1bc896bafcb9abc9ed6a
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632869"
---
# <a name="privileged-access-management-for-your-microsoft-365-enterprise-test-environment"></a>Hantering av privilegierad åtkomst för microsoft 365 Enterprise-testmiljön

*Den här testlabbguiden kan användas i både Microsoft 365 Enterprise- och Office 365 Enterprise-testmiljöer.*

Med instruktionerna i den här artikeln konfigurerar du hantering av privilegierad åtkomst för att öka säkerheten i microsoft 365 Enterprise-testmiljön.

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

>[!TIP]
>Klicka [här](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) om du vill se en översikt över alla artiklar i samlingen med Microsoft 365 Enterprise-testlabbguider.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fas 1: Bygga ut testmiljön i Microsoft 365 Enterprise

Om du bara vill konfigurera hantering av privilegierad åtkomst på ett lättviktssätt med minimikraven följer du instruktionerna i [Lightweight base-konfigurationen](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Om du vill konfigurera hantering av privilegierad åtkomst i ett simulerat företag följer du instruktionerna i [Direktautentisering](pass-through-auth-m365-ent-test-environment.md).
  
>[!NOTE]
>Testning av privilegierad åtkomsthantering kräver inte den simulerade företagstestmiljön, som innehåller ett simulerat intranät som är anslutet till Internet och katalogsynkronisering för en AD DS-skog. Det finns här som ett alternativ så att du kan testa privilegierad åtkomsthantering och experimentera med den i en miljö som representerar en typisk organisation. 

## <a name="phase-2-configure-privileged-access-management"></a>Fas 2: Konfigurera hantering av privilegierad åtkomst

I den här fasen konfigurerar du en godkännaregrupp och aktiverar hantering av privilegierad åtkomst för microsoft 365 Enterprise-testmiljön. Mer information och en översikt över hantering av privilegierad åtkomst finns i Hantering av [privilegierad åtkomst i Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).

Så här konfigurerar och använder du privilegierad åtkomst i organisationen:

- [Steg 1: Skapa en godkännargrupp](https://docs.microsoft.com/microsoft-365/compliance/privileged-access-management-configuration#step-1-create-an-approvers-group)

    Innan du börjar använda behörighetsåtkomst bör du bestämma vem som har godkännandebehörighet för inkommande begäranden om åtkomst till förhöjda och privilegierade uppgifter. Alla användare som ingår i gruppen Godkännare kan godkänna åtkomstbegäranden. Detta aktiveras genom att skapa en e-postaktiverad säkerhetsgrupp i Office 365. Skapa en ny säkerhetsgrupp med namnet "Privileged Access Approvers" i testmiljön och lägg till "Användare 3" som tidigare skapats i tidigare testlabbguidesteg.

- [Steg 2: Aktivera privilegierad åtkomst](https://docs.microsoft.com/microsoft-365/compliance/privileged-access-management-configuration#step-2-enable-privileged-access)

    Privilegierad åtkomst måste uttryckligen aktiveras i Office 365 med standardgodkärörsgruppen och inkludera en uppsättning systemkonton som du vill ska uteslutas från åtkomstkontrollen för privilegierad åtkomsthantering. Var noga med att aktivera privilegierad åtkomst i organisationen innan fas 3 i den här guiden startas.

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a>Fas 3: Kontrollera att godkännande krävs för förhöjda och privilegierade uppgifter

I den här fasen kontrollerar du att principen för privilegierad åtkomst fungerar och att användare kräver godkännande för att utföra definierade förhöjda och privilegierade uppgifter.

### <a name="test-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a>Testförmåga att utföra en uppgift SOM INTE har definierats i en privilegierad åtkomstprincip

Anslut först till Exchange Management PowerShell med autentiseringsuppgifterna för en användare som konfigurerats som global administratör i testmiljön och försök skapa en ny journalregel. [Aktiviteten Ny journalRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-journalrule?view=exchange-ps) har för närvarande inte definierats i en privilegierad åtkomstprincip för din organisation.

1. Öppna och logga in på Exchange Online Remote PowerShell-modulen på **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** på den lokala datorn med hjälp av det globala administratörskontot för din testmiljö.

2. Skapa en ny journalregel för din organisation i PowerShell för Exchange Management:

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
```

4. Visa att den nya journalregeln har skapats i PowerShell för Exchange Management.

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a>Skapa en ny princip för privilegierad åtkomst för aktiviteten Ny journalregel

>[!NOTE]
>Om du inte redan har slutfört steg 1 och 2 från fas 2 i den här guiden måste du följa stegen för att skapa en godkännares grupp med namnet "Privilege Access Approvers" och aktivera privilegierad åtkomst i testmiljön.

1. Logga in på [Microsoft 365-administrationscentret](https://admin.microsoft.com) med autentiseringsuppgifterna för det globala administratörskontot för testmiljön.

2. Gå till **Inställningar** > **för säkerhet & sekretessbehörighetsåtkomst** > i**administrationscentret**.

3. Välj **Hantera åtkomstprinciper och begäranden**.

4. Välj **Konfigurera principer** och välj Lägg till en **princip**.

5. Markera eller ange följande värden i listrutan:

    **Principtyp**: Uppgift

    **Policyomfattning**: Exchange

    **Policynamn**: Ny journalregel

    **Typ av godkännande**: Manuell

    **Godkännandegrupp**: Privilegierade åtkomstgodkännare

6. Välj **Skapa** och **stäng**sedan . Det kan ta några minuter innan principen konfigureras och aktiveras helt. Var noga med att ge tid för principen att vara fullt aktiverad innan du testar godkännandekravet i nästa steg.

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a>Testgodkännandekrav för den new-journalRule-uppgift som definierats i en princip för privilegierad åtkomst

1. Öppna och logga in på Exchange Online Remote PowerShell-modulen på **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** på den lokala datorn med hjälp av ett globalt administratörskonto för din testmiljö.

2. Skapa en ny journalregel för din organisation i PowerShell för Exchange Management:

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```

3. Visa felet "Otillräckliga behörigheter" i PowerShell för Exchange Management:

```ExchangeManagementPowerShell
Insufficient permissions. Please raise an elevated access request for this task.
    + CategoryInfo          : NotSpecified: (:) [], LocalizedException
    + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
    7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
    + PSComputerName        : outlook.office365.com
```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a>Begär åtkomst för att skapa en ny journalregel med uppgift Ny journalregel

1. Logga in på [Microsoft 365-administrationscentret](https://admin.microsoft.com) med hjälp av det globala administratörskontot för testmiljön.

2. Gå till **Inställningar** > **för säkerhet & sekretessbehörighetsåtkomst** > i**administrationscentret**.

3. Välj **Hantera åtkomstprinciper och begäranden**.

4. Välj **Ny begäran**. Välj lämpliga värden för din organisation i listrutan:

    **Typ av begäran**: Uppgift

    **Omfattning för begäran:** Exchange

    **Begäran om**: Ny journalregel

    **Varaktighet (timmar):** 2

    **Kommentarer**: Begär behörighet att skapa en ny journalregel

5. Välj **Spara** och **stäng**sedan . Din begäran kommer att skickas till godkännarens grupp via e-post.

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a>Godkänna begäran om privilegierad åtkomst för att skapa en ny journalregel

1. Logga in på [Microsoft 365-administrationscentret](https://admin.microsoft.com) med autentiseringsuppgifterna för Användare 3 i testmiljön (medlem i säkerhetsgruppen "Privilegierade åtkomstgodtagare" i testmiljön).

2. Gå till **Inställningar** > **för säkerhet & sekretessbehörighetsåtkomst** > i**administrationscentret**.

3. Välj **Hantera åtkomstprinciper och begäranden**.

4. Välj den väntande begäran och välj **Godkänn** om du vill bevilja åtkomst till det globala administratörskontot för att skapa en ny journalregel. Ett e-postmeddelande som bekräftar att godkännande har beviljats skickas till det globala administratörskontot (den begärande användaren).  

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a>Testa att skapa en ny journalregel med privilegierad åtkomst godkänd för aktiviteten Ny journalregel

1. Öppna och logga in på Exchange Online Remote PowerShell-modulen på **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** på den lokala datorn med hjälp av det globala administratörskontot för din testmiljö.

2. Skapa en ny journalregel för din organisation i PowerShell för Exchange Management:

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```

3. Visa att den nya journalregeln har skapats i PowerShell för Exchange Management.

## <a name="next-step"></a>Nästa steg

Utforska ytterligare funktioner och funktioner för [informationsskydd](m365-enterprise-test-lab-guides.md#information-protection) i testmiljön.

## <a name="see-also"></a>Snabbreferens

[Testlabbguider för Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Distribuera Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise-dokumentation](https://docs.microsoft.com/microsoft-365-enterprise/)
