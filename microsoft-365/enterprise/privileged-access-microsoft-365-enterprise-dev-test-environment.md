---
title: Hantering av privilegierad åtkomst för Microsoft 365 för företagstestmiljö
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
description: Använd den här testlabbguiden för att aktivera hantering av privilegierad åtkomst Microsoft 365 för företagstestmiljö.
ms.openlocfilehash: e9684ebd2aa147049dadfbda9408257ff801aff0
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126423"
---
# <a name="privileged-access-management-for-your-microsoft-365-for-enterprise-test-environment"></a>Hantering av privilegierad åtkomst för Microsoft 365 för företagstestmiljö

*Den här testlabbguiden kan användas för både Microsoft 365 för företag Office 365 Enterprise för testmiljöer.*

I den här artikeln beskrivs hur du konfigurerar hantering av behörighetsbehörighet för att öka säkerheten i Microsoft 365 för företagstestmiljön.

Konfigurering av hantering av priviled åtkomst omfattar tre faser:
- [Fas 1: Bygg ut din Microsoft 365 för företagstestmiljö](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fas 2: Konfigurera hantering av privilegierad åtkomst](#phase-2-configure-privileged-access-management)
- [Steg 3: Kontrollera att godkännande krävs för uppgifter med förhöjd behörighet och behörighet](#phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks)

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> En visuell karta till alla artiklar i Microsoft 365 för företags testlabbguide stack finns i [Microsoft 365 för företags testlabbguide stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fas 1: Bygg ut din Microsoft 365 för företagstestmiljö

Om du vill konfigurera hantering av privilegierad åtkomst på ett lätt sätt med minimikraven följer du anvisningarna i [Enkel baskonfiguration.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Om du vill konfigurera hantering av behörighetsbehörighet i ett simulerat företag följer du anvisningarna i [Direktautentisering](pass-through-auth-m365-ent-test-environment.md).
  
>[!NOTE]
>Om hantering av testa behörighet krävs inte den simulerade företagstestmiljön, som omfattar ett simulerat intranät som är anslutet till Internet och katalogsynkronisering för en Active Directory Domain Services-skog. Den finns här som ett alternativ så att du kan testa behörighetshantering och experimentera med den i en miljö som representerar en vanlig organisation.

## <a name="phase-2-configure-privileged-access-management"></a>Fas 2: Konfigurera hantering av privilegierad åtkomst

I den här fasen konfigurerar du en godkännaresgrupp och aktiverar hantering av behörighetsbehörighet för Microsoft 365 för företagstestmiljö. Mer information och en översikt över hantering av privilegierad åtkomst finns i Hantering [av privilegierad åtkomst.](../compliance/privileged-access-management-overview.md)

Gör så här om du vill konfigurera och använda behörighetsbehörighet i din organisation.

#### <a name="step-1-create-an-approvers-group"></a>[Steg 1: Skapa en godkännaresgrupp](../compliance/privileged-access-management-configuration.md#step-1-create-an-approvers-group)

Innan du börjar använda behörighet ska du bestämma vem som ska ha behörighet för godkännande för inkommande förfrågningar om åtkomst till aktiviteter med förhöjd behörighet. Alla användare som ingår i godkännargruppen kan godkänna åtkomstförfrågningar. Om du vill använda behörighet måste du skapa en e-postaktiverad säkerhetsgrupp i Microsoft 365. Namnge den nya säkerhetsgruppen "Godkännare för privilegierad åtkomst" i testmiljön och lägg till "användare 3" som tidigare skapades i tidigare anvisningar för testlabb.

#### <a name="step-2-enable-privileged-access"></a>[Steg 2: Aktivera privilegierad åtkomst](../compliance/privileged-access-management-configuration.md#step-2-enable-privileged-access)

Behörighet måste uttryckligen aktiveras i Microsoft 365 med standardgruppen för godkännare, och den måste innehålla en uppsättning systemkonton som du vill ska undantas från behörighetshanteringsåtkomstkontrollen. Se till att aktivera privilegierad åtkomst i organisationen innan du påbörjar fas 3 i den här guiden.

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a>Steg 3: Kontrollera att godkännande krävs för uppgifter med förhöjd behörighet och behörighet

I den här fasen kontrollerar du att principen för behörighetsåtkomst fungerar och att användarna kräver godkännande för att köra definierade aktiviteter med förhöjd behörighet.

### <a name="test-the-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a>Testa möjligheten att köra en aktivitet SOM INTE definierats i en behörighetsåtkomstprincip

Först ansluter du till Exchange Management PowerShell med autentiseringsuppgifterna för en användare som konfigurerats som global administratör i testmiljön och försöker skapa en ny journalregel. Uppgiften [Ny journalföring är](/powershell/module/exchange/new-journalrule) för närvarande inte definierad i en princip för behörighetsåtkomst för din organisation.

1. Öppna och logga in på Exchange Online Remote PowerShell Module på **Microsoft Corporation** Microsoft Exchange Online Remote PowerShell Module med globalt administratörskonto för  >   testmiljön.

1. Skapa Exchange journalregel för din organisation i Exchange Management PowerShell:

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
   ```

1. Visa att den nya journalregeln har skapats i Exchange PowerShell.

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a>Skapa en ny princip för privilegierad åtkomst för New-JournalRule uppgift

>[!NOTE]
>Om du inte redan har slutfört steg 1 och 2 från fas 2 i den här guiden ska du följa stegen för att skapa en godkännaregrupp med namnet "Godkännare av behörighet i åtkomst" för att aktivera privilegierad åtkomst i testmiljön.

1. Logga in på [Microsoft 365 och använd](https://admin.microsoft.com) autentiseringsuppgifterna för testmiljöns globala administratörskonto.

2. Gå till Säkerhets- och Inställningar  >  **i &.**  >  

3. Välj **Hantera åtkomstprinciper och -begäranden.**

4. Välj **Konfigurera principer** och välj sedan Lägg till en **princip**.

5. I listrutan väljer eller anger du följande värden:

    **Principtyp**: Uppgift

    **Policyomfattning**: Exchange

    **Principnamn:** Ny journalregel

    **Godkännandetyp**: Manuell

    **Gruppen Godkännande:** Godkännare för privilegierad åtkomst

6. Välj **Skapa** och sedan **Stäng.** Det kan ta några minuter innan principen har konfigurerats och aktiverats helt. Se till att ge tid för principen att aktiveras helt innan du testar godkännandekravet i nästa steg.

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a>Testa godkännandekrav för den New-JournalRule som definierats i en behörighetsåtkomstprincip

1. På din lokala dator öppnar och loggar du in på Exchange Online Remote PowerShell Module på **Microsoft Corporation** Microsoft Exchange Online Remote PowerShell Module med hjälp av ett global administratör-konto för  >   testmiljön.

2. Skapa Exchange journalregel för din organisation i Exchange Management PowerShell:

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

3. Visa felmeddelandet "Otillräckliga behörigheter" i Exchange PowerShell:

   ```ExchangeManagementPowerShell
   Insufficient permissions. Please raise an elevated access request for this task.
       + CategoryInfo          : NotSpecified: (:) [], LocalizedException
       + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
       7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
       + PSComputerName        : outlook.office365.com
   ```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a>Begära åtkomst för att skapa en ny journalregel med hjälp New-JournalRule uppgift

1. Logga in på [Microsoft 365 administrationscenter med](https://admin.microsoft.com) det globala administratörskontot för testmiljön.

2. Gå till Säkerhets- och Inställningar  >  **i &.**  >  

3. Välj **Hantera åtkomstprinciper och -begäranden.**

4. Välj **Ny begäran.** I listrutan väljer du lämpliga värden för din organisation:

    **Typ av begäran**: Uppgift

    **Begäran om omfattning:** Exchange

    **Begäran om:** Ny journalregel

    **Varaktighet (timmar)**: 2

    **Kommentarer:** Begära behörighet att skapa en ny journalregel

5. Välj **Spara** och sedan **Stäng.** Din begäran skickas till godkännarens grupp via e-post.

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a>Godkänna behörighetsåtkomstbegäran för att skapa en ny journalregel

1. Logga in på Microsoft 365-administrationscentret med autentiseringsuppgifterna för Användare 3 i testmiljön (medlem i säkerhetsgruppen [Godkännare](https://admin.microsoft.com) för privilegierad åtkomst i testmiljön).

2. Gå till Säkerhets- och Inställningar  >  **i &.**  >  

3. Välj **Hantera åtkomstprinciper och -begäranden.**

4. Markera den väntande begäran och välj sedan Godkänn **för att bevilja** åtkomst till det globala administratörskontot för att skapa en ny journalregel. Det globala administratörskontot (den begärande användaren) får en e-postbekräftelse på att godkännande har beviljats.

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a>Testa att skapa en ny journalregel med behörighetsåtkomst godkänd för New-JournalRule uppgiften

1. Öppna och logga in på Exchange Online Remote PowerShell Module på **Microsoft Corporation** Microsoft Exchange Online Remote PowerShell Module med globalt administratörskonto för  >   testmiljön.

1. Skapa Exchange journalregel för din organisation i Exchange Management PowerShell:

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

1. Visa att den nya journalregeln har skapats i Exchange PowerShell.

## <a name="next-step"></a>Nästa steg

Utforska ytterligare [informationsskyddsfunktioner](m365-enterprise-test-lab-guides.md#information-protection) i testmiljön.

## <a name="see-also"></a>Se även

[Testlabbguider för Microsoft 365 för företag](m365-enterprise-test-lab-guides.md)

[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)

[Dokumentation om Microsoft 365 för företag](/microsoft-365-enterprise/)
