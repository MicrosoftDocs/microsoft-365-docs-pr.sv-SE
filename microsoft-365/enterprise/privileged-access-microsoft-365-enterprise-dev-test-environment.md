---
title: Hantera behörighetsbehörigheter för testmiljön Microsoft 365 för företag
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
description: Använd den här testlabbguiden för att aktivera hantering av privilegierad åtkomst i testmiljön Microsoft 365 för företag.
ms.openlocfilehash: e9684ebd2aa147049dadfbda9408257ff801aff0
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126423"
---
# <a name="privileged-access-management-for-your-microsoft-365-for-enterprise-test-environment"></a>Hantera behörighetsbehörigheter för testmiljön Microsoft 365 för företag

*Den här testlabbguiden kan användas för både testmiljöerna Microsoft 365 för företag och Office 365 Enterprise.*

I den här artikeln beskrivs hur du konfigurerar hantering av privilegierad åtkomst för att öka säkerheten i testmiljön Microsoft 365 för företag.

Konfigurering av hantering av priviled access innebär tre faser:
- [Fas 1: Bygg ut testmiljön Microsoft 365 för företag](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fas 2: Konfigurera hantering av privilegierad åtkomst](#phase-2-configure-privileged-access-management)
- [Steg 3: Kontrollera att godkännande krävs för uppgifter med förhöjd behörighet](#phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks)

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> En visuell karta till alla artiklar i stacken med testlabbguider för Microsoft 365 för företag finns i Microsoft 365 för företags [testlabbguide.](../downloads/Microsoft365EnterpriseTLGStack.pdf)
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fas 1: Bygg ut testmiljön Microsoft 365 för företag

Om du vill konfigurera hantering av privilegierad åtkomst på ett lätt sätt med minimikraven följer du anvisningarna i Den här [grundkonfigurationen för enkel åtkomst.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Om du vill konfigurera hantering av behörighetsbehörighet i ett simulerat företag följer du anvisningarna i [direktautentisering.](pass-through-auth-m365-ent-test-environment.md)
  
>[!NOTE]
>Om hantering av behörighet testas krävs inte den simulerade företagstestmiljön, som omfattar ett simulerat intranät som är anslutet till Internet och katalogsynkronisering för en Active Directory DS skog. Det tillhandahålls här som ett alternativ så att du kan testa hantering av behörighet och experimentera med det i en miljö som representerar en vanlig organisation.

## <a name="phase-2-configure-privileged-access-management"></a>Fas 2: Konfigurera hantering av privilegierad åtkomst

I den här fasen konfigurerar du en godkännargrupp och aktiverar hantering av privilegierad åtkomst för testmiljön Microsoft 365 för företag. Mer information och en översikt över hantering av privilegierad åtkomst finns i [Hantera privilegierad åtkomst.](../compliance/privileged-access-management-overview.md)

Gör så här om du vill konfigurera och använda behörighetsbehörighet i din organisation.

#### <a name="step-1-create-an-approvers-group"></a>[Steg 1: Skapa en godkännaresgrupp](../compliance/privileged-access-management-configuration.md#step-1-create-an-approvers-group)

Innan du börjar använda behörighet ska du bestämma vilka som ska ha behörighet för godkännande för inkommande förfrågningar om åtkomst till aktiviteter med förhöjd behörighet. Alla användare som ingår i godkännarnas grupp kan godkänna åtkomstförfrågningar. Om du vill använda behörighet måste du skapa en e-postaktiverad säkerhetsgrupp i Microsoft 365. I testmiljön ger du den nya säkerhetsgruppen namnet "Godkännare för privilegierad åtkomst" och lägger till "Användare 3" som tidigare skapades i tidigare testlabbguider.

#### <a name="step-2-enable-privileged-access"></a>[Steg 2: Aktivera behörighetsbehörighet](../compliance/privileged-access-management-configuration.md#step-2-enable-privileged-access)

Behörighetsbehörighet måste uttryckligen aktiveras i Microsoft 365 för standard godkännaregruppen, och den måste innehålla en uppsättning systemkonton som du vill ska undantas från behörighetshanteringsåtkomstkontrollen. Se till att aktivera privilegierad åtkomst i organisationen innan du påbörjar fas 3 i den här guiden.

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a>Steg 3: Kontrollera att godkännande krävs för uppgifter med förhöjd behörighet

I den här fasen kontrollerar du att behörighetsprincipen fungerar och att användarna kräver godkännande för att utföra definierade uppgifter med förhöjd behörighet.

### <a name="test-the-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a>Testa möjligheten att utföra en uppgift SOM INTE definierats i en behörighetsbehörighetsprincip

Anslut först till Exchange Management PowerShell med autentiseringsuppgifterna för en användare som har konfigurerats som global administratör i testmiljön och försök skapa en ny journalregel. Uppgiften [Ny journalföring är](/powershell/module/exchange/new-journalrule) för närvarande inte definierad i någon behörighetsprincip för din organisation.

1. Öppna och logga in på Exchange Online Remote PowerShell-modulen på din lokala dator hos **Microsoft Corporation**  >  **Microsoft Exchange Online Remote PowerShell-modulen** med det globala administratörskontot för testmiljön.

1. Skapa en ny journalregel för din organisation i Exchange Management PowerShell:

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
   ```

1. Visa att den nya journalregeln har skapats i Exchange Management PowerShell.

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a>Skapa en ny behörighetsprincip för New-JournalRule behörighetsuppgift

>[!NOTE]
>Om du inte redan har slutfört steg 1 och 2 från fas 2 i den här guiden ska du följa stegen för att skapa en godkännaresgrupp som heter "Godkännare av behörigheter" för att aktivera behörighet i testmiljön.

1. Logga in på [administrationscentret för Microsoft 365](https://admin.microsoft.com) med autentiseringsuppgifter som global administratör för testmiljön.

2. I administrationscentret går du till Inställningar för  >  **säkerhet & behörighet för**  >  **sekretess.**

3. Välj **Hantera åtkomstprinciper och -begäranden.**

4. Välj **Konfigurera principer** och välj sedan Lägg till en **princip.**

5. Välj eller ange följande värden i listfälten:

    **Principtyp**: Aktivitet

    **Policyomfattning**: Exchange

    **Principnamn:** Ny journalregel

    **Godkännandetyp:** Manuell

    **Godkännandegrupp**: Godkännare för behörighet

6. Välj **Skapa** och sedan **Stäng.** Det kan ta några minuter innan principen är helt konfigurerad och aktiverad. Se till att det finns tid för att principen ska vara helt aktiverad innan du testar godkännandekravet i nästa steg.

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a>Testa godkännandekrav för den New-JournalRule som definierats i en behörighetsåtkomstprincip

1. Öppna och logga in på Exchange Online Remote PowerShell-modulen på din lokala dator hos **Microsoft Corporation**  >  **Microsoft Exchange Online Remote PowerShell-modulen** och använd ett global administratör-konto för testmiljön.

2. Skapa en ny journalregel för din organisation i Exchange Management PowerShell:

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

3. Visa felmeddelandet "Otillräckliga behörigheter" i Exchange Management PowerShell:

   ```ExchangeManagementPowerShell
   Insufficient permissions. Please raise an elevated access request for this task.
       + CategoryInfo          : NotSpecified: (:) [], LocalizedException
       + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
       7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
       + PSComputerName        : outlook.office365.com
   ```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a>Begära åtkomst för att skapa en ny journalregel med hjälp New-JournalRule uppgift

1. Logga in på [administrationscentret för Microsoft 365](https://admin.microsoft.com) med globalt administratörskonto för testmiljön.

2. I administrationscentret går du till Inställningar för **säkerhet &**  >  **behörighet för**  >  **sekretess.**

3. Välj **Hantera åtkomstprinciper och -begäranden.**

4. Välj **Ny begäran.** Välj lämpliga värden för din organisation i listfälten:

    **Typ av begäran:** Uppgift

    **Begärandeomfattning**: Exchange

    **Begäran om:** Ny journalregel

    **Varaktighet (timmar)**: 2

    **Kommentarer:** Begära behörighet att skapa en ny journalregel

5. Välj **Spara** och sedan **Stäng.** Din begäran skickas till godkännaren via e-post.

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a>Godkänna behörighetsåtkomstbegäran för att skapa en ny journalregel

1. Logga in på administrationscentret för [Microsoft 365](https://admin.microsoft.com) med autentiseringsuppgifterna för Användare 3 i testmiljön (medlem i säkerhetsgruppen Godkännare av behörighet i testmiljön).

2. I administrationscentret går du till Inställningar för  >  **säkerhet & behörighet för**  >  **sekretess.**

3. Välj **Hantera åtkomstprinciper och -begäranden.**

4. Markera den väntande begäran och välj sedan Godkänn **för att** bevilja åtkomst till det globala administratörskontot för att skapa en ny journalregel. Det globala administratörskontot (den som begär användaren) får en e-postbekräftelse på att godkännande har beviljats.

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a>Testa att skapa en ny journalregel med behörighetsbehörighet godkänd New-JournalRule uppgiften

1. Öppna och logga in på Exchange Online Remote PowerShell-modulen på din lokala dator hos **Microsoft Corporation**  >  **Microsoft Exchange Online Remote PowerShell-modulen** med det globala administratörskontot för testmiljön.

1. Skapa en ny journalregel för din organisation i Exchange Management PowerShell:

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

1. Visa att den nya journalregeln har skapats i Exchange Management PowerShell.

## <a name="next-step"></a>Nästa steg

Utforska ytterligare [informationsskyddsfunktioner](m365-enterprise-test-lab-guides.md#information-protection) i testmiljön.

## <a name="see-also"></a>Se även

[Testlabbguider för Microsoft 365 för företag](m365-enterprise-test-lab-guides.md)

[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)

[Dokumentation om Microsoft 365 för företag](/microsoft-365-enterprise/)
