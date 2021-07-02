---
title: Konfigurera leverans av nätfiskebedrägerier från tredje part till användare och ofiltrerade meddelanden till SecOps-postlådor
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom: ''
description: Administratörer kan lära sig att använda den avancerade leveransprincipen i Exchange Online Protection (EOP) för att identifiera meddelanden som inte ska filtreras i specifika scenarier som stöds (nätfiskebedrägerier från tredje part och meddelanden som levereras till säkerhetsåtgärder (SecOps)-postlådor.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 053f88da96983b03ad03e75c11a4fa692ac6a850
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256873"
---
# <a name="configure-the-delivery-of-third-party-phishing-simulations-to-users-and-unfiltered-messages-to-secops-mailboxes"></a>Konfigurera leverans av nätfiskebedrägerier från tredje part till användare och ofiltrerade meddelanden till SecOps-postlådor

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> Funktionen som beskrivs i den här artikeln är i förhandsversion, är inte tillgänglig för alla och kan komma att ändras.

För att hålla [organisationen](secure-by-default.md)säker som standard tillåter Exchange Online Protection (EOP) inte säkra listor eller filtreringsförkoppling för meddelanden som identifieras som skadlig kod eller nätfiske med hög konfidens. Men det finns särskilda scenarier som kräver leverans av ofiltrerade meddelanden. Till exempel:

- **Nätfiskebedrägerier från tredje** part : Simulerade attacker kan hjälpa dig att identifiera sårbara användare innan en verklig attack påverkar din organisation.
- **Säkerhetsåtgärder (SecOps)-postlådor:** Dedikerade postlådor som används av säkerhetsteam för att samla in och analysera ofiltrerade meddelanden (både bra och dåliga).

Du använder principen _för avancerad leverans i_ Microsoft 365 förhindra att dessa meddelanden i dessa specifika _scenarier_ filtreras. <sup>\*</sup> Med principen för avancerad leverans säkerställer du att meddelanden i följande scenarier uppnår följande resultat:

- Filter i EOP och Microsoft Defender för Office 365 inga åtgärder vidtas på dessa meddelanden.<sup>\*</sup>
- [ZAP (Zero-hour Purge)](zero-hour-auto-purge.md) för skräppost och nätfiske åtgärdar inte dessa meddelanden.<sup>\*</sup>
- [Standardsystemaviseringar](alerts.md) utlöses inte för dessa scenarier.
- [AIR och clustering i Defender för Office 365](office-365-air.md) ignorerar dessa meddelanden.
- Särskilt för nätfiskebedrägerier från tredje part:
  - [Administratörsinskick](admin-submission.md) genererar ett automatiskt svar som säger att meddelandet är en del av en phishing-simuleringskampanj och inte är ett riktigt hot. Aviseringar och AIR utlöses inte.
  - [Valv i Defender för Office 365](safe-links.md) blockeras eller avaktiverar inte de specifikt identifierade webbadresserna i dessa meddelanden.
  - [Valv i Defender för Office 365](safe-attachments.md) avaktiverar inte bifogade filer i dessa meddelanden.

<sup>\*</sup> Du kan inte kringgå filtrering av skadlig programvara eller ZAP för skadlig programvara.

Meddelanden som identifieras av den avancerade leveranspolicyn är inte säkerhetshot, så meddelandena markeras som system åsidosätter. Administratörer kan filtrera och analysera dessa system åsidosättningar i följande funktioner:

- [Hotutforskaren/identifieringar i realtid i Defender för Office 365 abonnemang 2](threat-explorer.md)
- Sidan [E-post entitet i Hotutforskaren/realtidsidentifiering](mdo-email-entity-page.md)
- Statusrapport [för skydd mot hot](view-email-security-reports.md#threat-protection-status-report)
- [Avancerad sökning i Microsoft Defender för Slutpunkt](../defender-endpoint/advanced-hunting-overview.md)
- [Kampanjvyer](campaigns.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Du kan öppna Microsoft 365 Defender-portalen genom att gå till <https://security.microsoft.com>. Gå direkt till sidan **Avancerad leverans** genom att öppna <https://security.microsoft.com/advanceddelivery> .

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

- Du måste ha tilldelats behörigheter innan du kan utföra procedurerna i den här artikeln:
  - Om du vill skapa, ändra eller ta bort konfigurerade inställningar i  den avancerade leveransprincipen måste du vara medlem  i rollgruppen Säkerhetsadministratör i **Microsoft 365 Defender-portalen** och medlem i rollgruppen Organisationshantering **i Exchange Online.**
  - För skrivskyddade åtkomst till avancerade leveransprinciper måste du vara medlem i rollgrupperna **Global Reader** **eller Säkerhetsläsare.**

  Mer information finns i [Behörigheter i Microsoft 365 Defender och](permissions-microsoft-365-security-center.md) Behörigheter i [Exchange Online.](/exchange/permissions-exo/permissions-exo)

  > [!NOTE]
  > Om du lägger till användare i Azure Active Directory-rollen får användarna de  behörigheter som krävs i Microsoft 365 Defender-portalen samt behörighet för andra funktioner Microsoft 365. Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).

## <a name="use-the-microsoft-365-defender-portal-to-configure-secops-mailboxes-in-the-advanced-delivery-policy"></a>Använd Microsoft 365 Defender för att konfigurera SecOps-postlådor i den avancerade leveranspolicyn

1. I Microsoft 365 Defender-portalen går du till avsnittet **Regler för &** e-& för samarbete & Regler för \>  \>  \>  \> **hot.**

2. På sidan **Advanced delivery** kontrollerar du att **secOps-postlådefliken** är markerad och gör sedan något av följande:
   - Klicka ![ på Redigera-ikonen ](../../media/m365-cc-sc-edit-icon.png) **Redigera.**
   - Om det inte finns några konfigurerade nätfiskebedrägerier klickar du på **Lägg till**.

3. På den **utfäll plats** för Redigera sekOps-postlådor som öppnas anger du en befintlig Exchange Online-postlåda som du vill ange som SecOps-postlåda genom att göra något av följande:
   - Klicka i rutan, lös listan över postlådor och välj sedan postlådan.
   - Klicka i rutan och skriv en identifierare för postlådan (namn, visningsnamn, alias, e-postadress, kontonamn osv.) och välj postlådan (visningsnamn) i resultatet.

     Upprepa det här steget så många gånger det behövs. Distributionsgrupper tillåts inte.

     Om du vill ta bort ett befintligt värde klickar du Ta bort ![Ta bort-ikonen](../../media/m365-cc-sc-remove-selection-icon.png) bredvid värdet.

4. Klicka på **Spara** när du är klar.

Postlådepostlådorna för SecOps som du har konfigurerat visas på **fliken SecOps-postlåda.** Om du vill göra ändringar klickar ![ du på ](../../media/m365-cc-sc-edit-icon.png) **Redigera-ikonen** Redigera på fliken.

## <a name="use-the-microsoft-365-defender-portal-to-configure-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a>Använd Microsoft 365 Defender-portalen för att konfigurera nätfiskebedrägerier från tredje part i den avancerade leveranspolicyn

1. I Microsoft 365 Defender-portalen går du till avsnittet **Regler för &** e-& för samarbete & Regler för \>  \>  \>  \> **hot.**

2. På sidan **Avancerad leverans** väljer du fliken **Phishing simulering** och gör sedan något av följande:
   - Klicka ![ på Redigera-ikonen ](../../media/m365-cc-sc-edit-icon.png) **Redigera.**
   - Om det inte finns några konfigurerade nätfiskebedrägerier klickar du på **Lägg till**.

3. På den **utfällande menyn Redigera nätfiske** från tredje part som öppnas konfigurerar du följande inställningar:

   - **Skicka domän:** Utöka den här inställningen och ange minst en e-postadressdomän (till exempel contoso.com) genom att klicka i rutan, ange ett värde och sedan trycka på Retur eller välja värdet som visas under rutan. Upprepa det här steget så många gånger det behövs. Du kan lägga till upp till 10 poster.
   - **Skicka IP:** Utöka den här inställningen och ange minst en giltig IPv4-adress genom att klicka i rutan, ange ett värde och sedan trycka på Retur eller välja värdet som visas under rutan. Upprepa det här steget så många gånger det behövs. Du kan lägga till upp till 10 poster. Giltiga värden är:
     - Enskild IP: Till exempel 192.168.1.1.
     - IP-intervall: Till exempel 192.168.0.1-192.168.0.254.
     - CIDR IP: Till exempel 192.168.0.1/25.
   - **Simulerings-URL:er** som ska tillåtas: Utöka den här inställningen och ange eventuellt specifika URL-adresser som är en del av din phishing-simuleringskampanj som inte ska blockeras eller detoneras genom att klicka i rutan, ange ett värde och sedan trycka på Retur eller välja värdet som visas under rutan. Du kan lägga till upp till 10 poster.

   Om du vill ta bort ett befintligt värde klickar du Ta bort ![Ta bort-ikonen](../../media/m365-cc-sc-remove-selection-icon.png) bredvid värdet.

4. Gör något av följande när du är klar:
   - **Första gången:** Klicka **på Lägg** till och sedan på **Stäng.**
   - **Redigera befintligt:** Klicka **på Spara** och sedan på **Stäng.**

De simuleringsposter för nätfiske från tredje part som du har konfigurerat visas på fliken **Nätfiskebedrägerier.** Om du vill göra ändringar klickar ![ du på ](../../media/m365-cc-sc-edit-icon.png) **Redigera-ikonen** Redigera på fliken.

## <a name="additional-scenarios-that-require-filtering-bypass"></a>Ytterligare scenarier som kräver förbikoppling av filtrering

Utöver de två scenarier som den avancerade leveransprincipen kan hjälpa dig med finns det andra scenarier som kan innebära att du måste kringgå filtrering:

- **Filter från tredje part:** Om domänens MX-post inte pekar på Office 365 (meddelanden dirigeras någon annanstans [först)](secure-by-default.md) är säker som standard *inte tillgänglig.*  Om du vill lägga till skydd måste du aktivera Utökad filtrering för kopplingar (kallas även för hoppa *över post).* Mer information finns i Hantera [e-postflöde med hjälp av en molnbaserad tjänst från tredje Exchange Online.](/exchange/mail-flow-best-practices/manage-mail-flow-using-third-party-cloud) Om du inte vill ha utökad filtrering för kopplingar kan du använda e-postflödesregler (kallas även transportregler) för att kringgå Microsoft-filtrering för meddelanden som redan har utvärderats av filtrering från tredje part. Mer information finns i Använda [e-postflödesregler för att ange SCL i meddelanden.](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl.md)

- **Falska** positiva resultat under granskning: Du kanske tillfälligt vill tillåta att vissa meddelanden som fortfarande analyseras av Microsoft via administratörer rapporterar kända bra meddelanden som felaktigt [markeras](admin-submission.md) som dåliga för Microsoft (falska positiva resultat). Precis som med alla åsidosättningar rekommenderar **_vi att_** dessa tillåtna produkter är tillfälliga.

## <a name="exchange-online-powershell-procedures-for-secops-mailboxes-in-the-advanced-delivery-policy"></a>Exchange Online PowerShell-procedurer för SecOps-postlådor i den avancerade leveranspolicyn

I Exchange Online PowerShell är de grundläggande elementen i SecOps-postlådorna i den avancerade leveransprincipen:

- **Åsidosättningspolicyn i SecOps:** Reglerad av **\* cmdletarna -SecOpsOverridePolicy.**
- **Regeln för SecOps åsidosättning:** Kontrollerad av **\* cmdletarna -SecOpsOverrideRule.**

Det här beteendet har följande resultat:

- Du skapar principen först och sedan skapar du den regel som identifierar principen som regeln gäller för.
- När du tar bort en princip från PowerShell tas även motsvarande regel bort.
- När du tar bort en regel från PowerShell tas motsvarande princip inte bort. Du måste ta bort motsvarande princip manuellt.

### <a name="use-powershell-to-configure-secops-mailboxes"></a>Använda PowerShell för att konfigurera SecOps-postlådor

Att konfigurera en SecOps-postlåda i principen för avancerad leverans i PowerShell är en process i två steg:

1. Skapa åsidosättningspolicyn SecOps.
2. Skapa regeln för secOps-åsidosättning som anger den princip som regeln gäller för.

#### <a name="step-1-use-powershell-to-create-the-secops-override-policy"></a>Steg 1: Använd PowerShell för att skapa åsidosättsprincipen för SecOps

Använd följande syntax för att skapa åsidosättningspolicyn SecOps:

```powershell
New-SecOpsOverridePolicy -Name SecOpsOverridePolicy -SentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>
```

**Obs!** Oavsett vilket namnvärde du anger blir principnamnet SecOpsOverridePolicy, så du kan lika gärna använda det värdet.

I det här exemplet skapas SecOps-postlådeprincipen.

```powershell
New-SecOpsOverridePolicy -Name SecOpsOverridePolicy -SentTo secops@contoso.com
```

Detaljerad information om syntax och parametrar finns [i New-SecOpsOverridePolicy.](/powershell/module/exchange/new-secopsoverridepolicy)

#### <a name="step-2-use-powershell-to-create-the-secops-override-rule"></a>Steg 2: Använd PowerShell för att skapa åsidosättningsregeln för SecOps

I det här exemplet skapas SecOps-postlåderegeln med angivna inställningar.

```powershell
New-SecOpsOverrideRule -Name SecOpsOverrideRule -Policy SecOpsOverridePolicy
```

**Obs!**** Oavsett vilket namnvärde du anger blir regelnamnet SecOpsOverrideRule där det är ett unikt \<GUID\> \<GUID\> GUID-värde (till exempel 6fed4b63-3563-495d-a481-b24a311f8329).

Detaljerad information om syntax och parametrar finns [i New-SecOpsOverrideRule.](/powershell/module/exchange/new-secopsoverriderule)

### <a name="use-powershell-to-view-the-secops-override-policy"></a>Använda PowerShell för att visa åsidosättningspolicyn i SecOps

Det här exemplet returnerar detaljerad information om den enda SecOps-postlådeprincipen.

```powershell
Get-SecOpsOverridePolicy
```

Detaljerad information om syntax och parametrar finns i [Get-SecOpsOverridePolicy.](/powershell/module/exchange/get-secopsoverridepolicy)

### <a name="use-powershell-to-view-secops-override-rules"></a>Använda PowerShell för att visa regler som åsidosätter SecOps

Det här exemplet returnerar detaljerad information om regler för SecOps-åsidosättning.

```powershell
Get-SecOpsOverrideRule
```

Även om föregående kommando endast ska returnera en regel, kan även regler som väntar på att tas bort ingå i resultatet.

I det här exemplet identifieras den giltiga regeln (en) och alla ogiltiga regler.

```powershell
Get-SecOpsOverrideRule | Format-Table Name,Mode
```

När du har identifierat ogiltiga regler kan du ta bort dem med hjälp av cmdleten **Remove-SecOpsOverrideRule** enligt beskrivningen längre fram [i den här artikeln.](#use-powershell-to-remove-secops-override-rules)

Detaljerad information om syntax och parametrar finns i [Get-SecOpsOverrideRule](/powershell/module/exchange/get-secopsoverriderule)

### <a name="use-powershell-to-modify-the-secops-override-policy"></a>Använda PowerShell för att ändra åsidosättningspolicyn i SecOps

Använd följande syntax för att ändra åsidosättningsprincipen för SecOps:

```powershell
Set-SecOpsOverridePolicy -Identity SecOpsOverridePolicy [-AddSentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>] [-RemoveSentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>]
```

I det här exemplet läggs secops2@contoso.com till i SecOps åsidosättningspolicyn.

```powershell
Set-SecOpsOverridePolicy -Identity SecOpsOverridePolicy -AddSentTo secops2@contoso.com
```

**Obs!** Om det finns en associerad, giltig åsidosättningsregel för SecOps uppdateras även e-postadresserna i regeln.

Detaljerad information om syntax och parametrar finns [i Set-SecOpsOverridePolicy.](/powershell/module/exchange/set-secopsoverridepolicy)

### <a name="use-powershell-to-modify-a-secops-override-rule"></a>Använda PowerShell för att ändra en åsidosättningsregel för SecOps

**Cmdlet:en Set-SecOpsOverrideRule** ändrar inte e-postadresserna i regeln om åsidosättning av SecOps. Använd cmdleten **Set-SecOpsOverridePolicy** för att ändra e-postadresserna i regeln för SecOps-åsidosättning.

Detaljerad information om syntax och parametrar finns [i Set-SecOpsOverrideRule.](/powershell/module/exchange/set-secopsoverriderule)

### <a name="use-powershell-to-remove-the-secops-override-policy"></a>Använda PowerShell för att ta bort principen för SecOps-åsidosättning

Det här exemplet tar bort SecOps-postlådeprincipen och motsvarande regel.

```powershell
Remove-SecOpsOverridePolicy -Identity SecOpsOverridePolicy
```

Detaljerad information om syntax och parametrar finns i [Remove-SecOpsOverridePolicy.](/powershell/module/exchange/remove-secopsoverridepolicy)

### <a name="use-powershell-to-remove-secops-override-rules"></a>Använda PowerShell för att ta bort regler för SecOps-åsidosättning

Använd följande syntax för att ta bort en regel som åsidosätter SecOps:

```powershell
Remove-SecOpsOverrideRule -Identity <RuleIdentity>
```

I det här exemplet tas den angivna SecOps-regeln bort.

```powershell
Remove-SecOpsOverrideRule -Identity SecOpsOverrideRule6fed4b63-3563-495d-a481-b24a311f8329
```

Detaljerad information om syntax och parametrar finns i [Remove-SecOpsOverrideRule.](/powershell/module/exchange/remove-secopsoverriderule)

## <a name="exchange-online-powershell-procedures-for-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a>Exchange Online PowerShell-procedurer för nätfiskebedrägerier från tredje part i den avancerade leveranspolicyn

I Exchange Online PowerShell är de grundläggande elementen i simuleringar av nätfiske från tredje part i den avancerade leveranspolicyn:

- **Åsidosättningsprincipen för nätfiske:** Styrs av cmdletarna **\* -PhishSimOverridePolicy.**
- **Regeln för åsidosättning av nätfiske:** Styrs av cmdletarna **\* -PhishSimOverrideRule.**

Det här beteendet har följande resultat:

- Du skapar principen först och sedan skapar du den regel som identifierar principen som regeln gäller för.
- Du ändrar inställningarna i principen och regeln separat.
- När du tar bort en princip från PowerShell tas även motsvarande regel bort.
- När du tar bort en regel från PowerShell tas motsvarande princip inte bort. Du måste ta bort motsvarande princip manuellt.

### <a name="use-powershell-to-configure-third-party-phishing-simulations"></a>Använda PowerShell för att konfigurera nätfiskebedrägerier från tredje part

Konfigurera en nätfiskebedrägeri från tredje part i den avancerade leveranspolicyn i PowerShell är en process i två steg:

1. Skapa åsidosättningsprincipen för nätfiskebedrägerier.
2. Skapa regeln för åsidosättning av nätfiske som anger principen som regeln gäller för.

#### <a name="step-1-use-powershell-to-create-the-phishing-simulation-override-policy"></a>Steg 1: Använd PowerShell för att skapa principen för att åsidosätta nätfiske

I det här exemplet skapas en åsidosättningsprincip för nätfiske.

```powershell
New-PhishSimOverridePolicy -Name PhishSimOverridePolicy
```

**Obs!** Oavsett vilket namnvärde du anger blir principnamnet PhishSimOverridePolicy, så du kan lika gärna använda det värdet.

Detaljerad information om syntax och parametrar finns i [New-PhishSimOverridePolicy](/powershell/module/exchange/new-phishsimoverridepolicy).

#### <a name="step-2-use-powershell-to-create-the-phishing-simulation-override-rule"></a>Steg 2: Använd PowerShell för att skapa regeln för åsidosättning av nätfiske

Använd följande syntax:

```powershell
New-PhishSimOverrideRule -Name PhishSimOverrideRule -Policy PhishSimOverridePolicy -SenderDomainIs <Domain1>,<Domain2>,...<DomainN> -SenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>
```

Oavsett vilket namnvärde du anger blir regelnamnet PhishSimOverrideRule, där det är ett unikt \<GUID\> \<GUID\> GUID-värde (till exempel a0eae53e-d755-4a42-9320-b9c6b55c5011).

En giltig IP-adresspost är något av följande värden:

- Enskild IP: Till exempel 192.168.1.1.
- IP-intervall: Till exempel 192.168.0.1-192.168.0.254.
- CIDR IP: Till exempel 192.168.0.1/25.

I det här exemplet skapas regeln för åsidosättning av nätfiske med angivna inställningar.

```powershell
New-PhishSimOverrideRule -Name PhishSimOverrideRule -Policy PhishSimOverridePolicy -SenderDomainIs fabrikam.com,wingtiptoys.com -SenderIpRanges 192.168.1.55
```

Detaljerad information om syntax och parametrar finns i [New-PhishSimOverrideRule](/powershell/module/exchange/new-phishsimoverriderule).

### <a name="use-powershell-to-view-the-phishing-simulation-override-policy"></a>Använda PowerShell för att visa åsidosättningsprincip för nätfiske

Det här exemplet returnerar detaljerad information om den enda åsidosättningsprincipen för nätfiske.

```powershell
Get-PhishSimOverridePolicy
```

Detaljerad information om syntax och parametrar finns i [Get-PhishSimOverridePolicy.](/powershell/module/exchange/get-phishsimoverridepolicy)

### <a name="use-powershell-to-view-phishing-simulation-override-rules"></a>Använda PowerShell för att visa regler för att åsidosätta nätfiske

Det här exemplet returnerar detaljerad information om regler för att åsidosätta nätfiske.

```powershell
Get-PhishSimOverrideRule
```

Även om föregående kommando endast ska returnera en regel, kan även regler som väntar på att tas bort ingå i resultatet.

I det här exemplet identifieras den giltiga regeln (en) och alla ogiltiga regler.

```powershell
Get-PhishSimOverrideRule | Format-Table Name,Mode
```

När du har identifierat ogiltiga regler kan du ta bort dem med hjälp av cmdleten **Remove-PhisSimOverrideRule** enligt beskrivningen längre fram [i den här artikeln.](#use-powershell-to-remove-phishing-simulation-override-rules)

Detaljerad information om syntax och parametrar finns i [Get-PhishSimOverrideRule.](/powershell/module/exchange/get-phishsimoverriderule)

### <a name="use-powershell-to-modify-the-phishing-simulation-override-policy"></a>Använda PowerShell för att ändra åsidosättningsprincipen för nätfiske

Använd följande syntax för att ändra åsidosättningsprincipen för nätfiske:

```powershell
Set-PhishSimOverridePolicy -Identity PhishSimOverridePolicy [-Comment "<DescriptiveText>"] [-Enabled <$true | $false>]
```

I det här exemplet inaktiveras principen för åsidosättning av nätfiske.

```powershell
Set-PhishSimOverridePolicy -Identity PhishSimOverridePolicy -Enabled $false
```

Detaljerad information om syntax och parametrar finns [i Set-PhishSimOverridePolicy.](/powershell/module/exchange/set-phishsimoverridepolicy)

### <a name="use-powershell-to-modify-a-phishing-simulation-override-rule"></a>Använda PowerShell för att ändra en åsidosättningsregel för nätfiske

Använd följande syntax för att ändra regeln för åsidosättning av nätfiske:

```powershell
Set-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011 [-Comment "<DescriptiveText>"] [-AddSenderDomainIs <DomainEntry1>,<DomainEntry2>,...<DomainEntryN>] [-RemoveSenderDomainIs <DomainEntry1>,<DomainEntry2>,...<DomainEntryN>] [-AddSenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>] [-RemoveSenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>]
```

I det här exemplet ändras den angivna regeln för åsidosättning av nätfiske med följande inställningar:

- Lägg till domänposten blueyonderairlines.com.
- Ta bort IP-adressposten 192.168.1.55.

Observera att dessa ändringar inte påverkar befintliga poster.

```powershell
Set-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011 -AddSenderDomainIs blueyonderairlines.com -RemoveSenderIpRanges 192.168.1.55
```

Detaljerad information om syntax och parametrar finns [i Set-PhishSimOverrideRule.](/powershell/module/exchange/set-phishsimoverriderule)

### <a name="use-powershell-to-remove-a-phishing-simulation-override-policy"></a>Använda PowerShell för att ta bort en åsidosättningsprincip för nätfiske

I det här exemplet tas åsidosättningsprincipen för nätfiske bort och motsvarande regel.

```powershell
Remove-PhishSimOverridePolicy -Identity PhishSimOverridePolicy
```

Detaljerad information om syntax och parametrar finns i [Remove-PhishSimOverridePolicy.](/powershell/module/exchange/remove-phishsimoverridepolicy)

### <a name="use-powershell-to-remove-phishing-simulation-override-rules"></a>Använda PowerShell för att ta bort regler för att åsidosätta nätfiske

Använd följande syntax för att ta bort en regel för att åsidosätta nätfiske:

```powershell
Remove-PhishSimOverrideRule -Identity <RuleIdentity>
```

Det här exemplet tar bort den angivna regeln för åsidosättning av nätfiske.

```powershell
Remove-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011
```

Detaljerad information om syntax och parametrar finns i [Remove-PhishSimOverrideRule.](/powershell/module/exchange/remove-phishsimoverriderule)
