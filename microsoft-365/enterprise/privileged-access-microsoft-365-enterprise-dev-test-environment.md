---
title: Hantering av privilegie rad åtkomst för din test miljö för Microsoft 365 för företag
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
description: Använd den här test laboratorie guiden för att aktivera hantering av privilegierad åtkomst för Microsoft 365 för företags test miljö.
ms.openlocfilehash: d8d92aa86076e323e4b5bb5c8eb1385edcac420c
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/12/2020
ms.locfileid: "47545948"
---
# <a name="privileged-access-management-for-your-microsoft-365-for-enterprise-test-environment"></a>Hantering av privilegie rad åtkomst för din test miljö för Microsoft 365 för företag

*Den här test laboratorie guiden kan användas för både Microsoft 365 för företags-och Office 365 företags test miljöer.*

Genom att följa anvisningarna i den här artikeln kan du konfigurera hanteringen av behörig åtkomst för att öka säkerheten i test miljön av Microsoft 365 för företag.

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

>[!TIP]
>Klicka [här](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) om du vill se en översikt över alla artiklar i samlingen med testlabbguider för Microsoft 365 för företag.
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fas 1: bygga ut test miljön för Microsoft 365 för företag

Om du bara vill konfigurera privilegie rad åtkomst hantering på ett enkelt sätt med de minsta kraven följer du anvisningarna i [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Om du vill konfigurera privilegie rad åtkomst hantering i ett simulerat företag följer du anvisningarna i [vidarekoppling](pass-through-auth-m365-ent-test-environment.md).
  
>[!NOTE]
>För att testa hanteringen av privilegierade åtkomst krävs inte den simulerade företags test miljön, som innehåller ett simulerat intranät som är kopplat till Internet och Directory-synkronisering för en AD DS-skog. Det finns ett alternativ som gör att du kan testa hanteringen av behörig åtkomst och experimentera med den i en miljö som representerar en typisk organisation. 

## <a name="phase-2-configure-privileged-access-management"></a>Fas 2: Konfigurera hantering av behörig åtkomst

I den här fasen konfigurerar du en god kännare grupp och aktiverar hantering av privilegierade åtkomst för din Microsoft 365 för företags test miljö. Mer information och en översikt över privilegierade åtkomst hantering finns i [Hantera privilegierad åtkomst](../compliance/privileged-access-management-overview.md).

Följ de här stegen för att konfigurera och använda privilegie rad åtkomst i organisationen:

- [Steg 1: skapa en god kännare grupp](../compliance/privileged-access-management-configuration.md#step-1-create-an-approvers-group)

    Innan du börjar använda privilegie rad åtkomst kan du bestämma vem som ska ha godkännande auktoritet för inkommande förfrågningar om åtkomst till förhöjda och behöriga uppgifter. Alla användare som är medlemmar i gruppen god kännare kan godkänna åtkomst förfrågningar. Det här är aktiverat genom att skapa en e-postaktive rad säkerhets grupp i Microsoft 365. Skapa en ny säkerhets grupp med namnet "behöriga åtkomst god kännare" i test miljön och Lägg till "användare 3" tidigare skapad i den föregående test laboratorie guiden.

- [Steg 2: Aktivera privilegie rad åtkomst](../compliance/privileged-access-management-configuration.md#step-2-enable-privileged-access)

    Privilegie rad åtkomst måste aktive ras explicit i Microsoft 365 med standard gruppen för godkännande och inklusive en uppsättning system konton som du vill ska undantas från åtkomst kontroll för privilegie rad åtkomst. Se till att aktivera privilegie rad åtkomst i organisationen innan du startar fas 3 av den här guiden.

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a>Fas 3: kontrol lera att godkännande krävs för förhöjda och behöriga uppgifter

I den här fasen kontrollerar du att principen för privilegie rad åtkomst fungerar och att användarna kräver godkännande för att utföra definierade förhöjda och behöriga uppgifter.

### <a name="test-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a>Testa möjligheten att utföra en uppgift som inte har definierats i en policy för privilegie rad åtkomst

Först ansluter du till Exchange Management PowerShell med autentiseringsuppgifterna för en användare som har kon figurer ATS som global administratör i test miljön och försöker skapa en ny journal regel. Den [nya – JournalRule](https://docs.microsoft.com/powershell/module/exchange/new-journalrule) uppgiften är för närvarande inte definierad i en policy för privilegie rad åtkomst för organisationen.

1. På din lokala dator öppnar du och loggar in på Exchange Online Remote PowerShell-modulen på **Microsoft Corporation**  >  **Microsoft Exchange Online Remote PowerShell module** med det globala administratörs kontot för test miljön.

2. I Exchange Management PowerShell kan du skapa en ny journal regel för organisationen:

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
```

4. Visa att den nya Journal regeln skapades i Exchange Management PowerShell.

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a>Skapa en ny privilegierad åtkomst policy för den nya-JournalRule-aktiviteten

>[!NOTE]
>Om du inte redan har slutfört steg 1 och 2 från fas 2 i den här guiden ska du läsa igenom stegen för att skapa en god kännare grupp med namnet "behörighets godkännanden" och aktivera privilegie rad åtkomst i test miljön.

1. Logga in i [administrations centret för Microsoft 365](https://admin.microsoft.com) med autentiseringsuppgifter det globala administratörs kontot för test miljön.

2. I administrations centret går du till **Inställningar**  >  **säkerhet & integritet**  >  **privilegie rad åtkomst**.

3. Välj **Hantera åtkomst principer och begär Anden**.

4. Välj **Konfigurera principer** och välj sedan **Lägg till en princip**.

5. Välj eller ange följande värden i list rutan.

    **Princip typ**: uppgift

    **Princip omfattning**: Exchange

    **Princip namn**: ny journal regel

    **Godkännande typ**: manuell

    **Godkännande grupp**: god kännare för privilegie rad åtkomst

6. Välj **skapa** och sedan **Stäng**. Det kan ta några minuter innan principen är fullständigt konfigurerad och aktive rad. Se till att tiden för principen är fullständigt aktive rad innan du testar godkännande kravet i nästa steg.

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a>Test godkännande krav för den nya-JournalRule-aktiviteten definierad i en policy för privilegie rad åtkomst

1. På din lokala dator öppnar du och loggar in på Exchange Online Remote PowerShell-modulen på **Microsoft Corporation**  >  **Microsoft Exchange Online Remote PowerShell-modul** med ett Använd globalt administratörs konto för test miljön.

2. I Exchange Management PowerShell kan du skapa en ny journal regel för organisationen:

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```

3. Visa fel meddelandet "otillräcklig behörighet" i Exchange Management PowerShell:

```ExchangeManagementPowerShell
Insufficient permissions. Please raise an elevated access request for this task.
    + CategoryInfo          : NotSpecified: (:) [], LocalizedException
    + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
    7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
    + PSComputerName        : outlook.office365.com
```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a>Begära åtkomst för att skapa en ny journal regel med den nya-JournalRule-uppgiften

1. Logga in i [administrations centret för Microsoft 365](https://admin.microsoft.com) med det globala administratörs kontot för test miljön.

2. I administrations centret går du till **Inställningar**  >  **säkerhet & integritet**  >  **privilegie rad åtkomst**.

3. Välj **Hantera åtkomst principer och begär Anden**.

4. Välj **ny begäran**. Välj lämpliga värden för din organisation i list rutan:

    **Begäran**: uppgift

    **Begärans omfattning**: Exchange

    **Begäran om**ny journal regel

    **Varaktighet (timmar)**: 2

    **Kommentar**: begära behörighet att skapa en ny journal regel

5. Välj **Spara** och sedan **Stäng**. Din begäran skickas till gruppen god kännare via e-post.

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a>Godkänn behörig åtkomstbegäran för att skapa en ny journal regel

1. Logga in i [administrations centret för Microsoft 365](https://admin.microsoft.com) med hjälp av autentiseringsuppgifterna för användare 3 i test miljön (medlem i säkerhets gruppen "privilegie rad god kännare" i test miljön).

2. I administrations centret går du till **Inställningar**  >  **säkerhet & integritet**  >  **privilegie rad åtkomst**.

3. Välj **Hantera åtkomst principer och begär Anden**.

4. Välj den väntande begäran och välj **Godkänn** för att bevilja åtkomst till det globala administratörs kontot för att skapa en ny journal regel. Ett e-postmeddelande som bekräftar att godkännandet kommer att skickas till det globala administratörs kontot (den användare som begär detta).  

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a>Testa att skapa en ny journal regel med behörig åtkomst godkänd för den nya-JournalRule-aktiviteten

1. På din lokala dator öppnar du och loggar in på Exchange Online Remote PowerShell-modulen på **Microsoft Corporation**  >  **Microsoft Exchange Online Remote PowerShell module** med det globala administratörs kontot för test miljön.

2. I Exchange Management PowerShell kan du skapa en ny journal regel för organisationen:

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```

3. Visa att den nya Journal regeln skapades i Exchange Management PowerShell.

## <a name="next-step"></a>Nästa steg

Utforska ytterligare funktioner för [informations skydd](m365-enterprise-test-lab-guides.md#information-protection) i test miljön.

## <a name="see-also"></a>Se även

[Testlabbguider för Microsoft 365 för företag](m365-enterprise-test-lab-guides.md)

[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)

[Microsoft 365 för företags dokumentation](https://docs.microsoft.com/microsoft-365-enterprise/)
