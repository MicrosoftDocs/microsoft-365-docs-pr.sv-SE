---
title: Hantera tillåtna och blockerade webb adresser i listan Tillåt/blockera i klient organisationen
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Administratörer kan läsa mer om hur du konfigurerar URL-poster i listan Tillåt/blockera i klient organisationen för säkerhets &.
ms.openlocfilehash: eb9dcc5b239aae1366a0a2e0eebd68b3f0082e6b
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202345"
---
# <a name="manage-urls-in-the-tenant-allowblock-list"></a>Hantera URL: er i listan Tillåt / blockera hyresgäster

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> De funktioner som beskrivs i det här avsnittet är i förhands gransknings syfte och kan ändras och är inte tillgängliga i alla organisationer.

I Microsoft 365-organisationer med post lådor i Exchange Online eller fristående Exchange Online Protection (EOP)-organisationer utan Exchange Online-postlådor kanske du inte kan komma att behöva filtrera EOP Verdict. Ett bra meddelande kan till exempel vara markerat som dåligt (ett falskt positivt) eller så tillåts ett ogiltigt meddelande genom (ett falskt negativt).

Med listan Tillåt/begränsa klient organisation i säkerhets & Compliance Center kan du manuellt åsidosätta Microsoft 365 filter-verdicts. Listan över tillåtna/blockerade innehavare används under e-postflöde och när användaren klickar på den. Du kan ange URL-adresser att tillåta eller blockera i listan Tillåt/blockera för klient organisation.

I det här avsnittet beskrivs hur du konfigurerar poster i listan Tillåt/blockera i säkerhets & för kontroll av klient organisation eller i PowerShell-organisationen (Exchange Online PowerShell för Microsoft 365-organisationer med post lådor i Exchange Online; fristående EOP PowerShell för organisationer utan Exchange Online-postlådor).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>. För att gå direkt till sidan **Tillåt/blockera lista för klient organisation** , Använd <https://protection.office.com/tenantAllowBlockList> .

- Tillgängliga URL-värden beskrivs i [URL-syntaxen för avsnittet Tillåt/blockera lista för klient organisation](#url-syntax-for-the-tenant-allowblock-list) längre ned i det här avsnittet.

- Listan Tillåt/blockera för klient organisationer tillåter högst 500 poster för URL: er.

- En post ska vara aktiv inom 15 minuter.

- Block poster har högre prioritet än Tillåt-poster.

- Poster i listan Tillåt/blockera för klient organisationer upphör som standard efter 30 dagar. Du kan ange ett datum eller ange att de aldrig ska upphöra att gälla.

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Information om hur du ansluter till fristående EOP PowerShell finns i artikeln om att [Ansluta till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Du måste ha tilldelats behörigheter innan du kan genomföra de här procedurerna för detta ämne:

  - Om du vill lägga till och ta bort värden från listan Tillåt/blockera för klient organisationer måste du vara medlem i någon av följande roll grupper:

    - **Organisationshantering** eller **Säkerhetsadministratör** i [Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).
    - **Organisationshantering** eller **Hygienhantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

  - Om du vill ha skrivskyddad åtkomst till listan Tillåt/blockera för klient organisationer måste du vara medlem i någon av följande roll grupper:

    - **Säkerhetsläsare** i [Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).
    - **Skrivskyddad organisationshantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a>Använd säkerhets & efterlevnad för att skapa URL-poster i listan Tillåt/blockera för klient organisation

Mer information om syntaxen för URL-poster finns i [URL-syntaxen för listan Tillåt/blockera lista för klient organisation](#url-syntax-for-the-tenant-allowblock-list) längre ned i det här avsnittet.

1. Gå till fliken **Threat Management** \> **policy** för \> **Tillåt/blockera listor**i säkerhets & efterlevnad.

2. På sidan **Tillåt/blockera lista för klient organisation** kontrollerar du att fliken **URL: er** är markerad och klickar sedan på **Lägg till** .

3. I **Lägg till** utfällbara URL-adresser som visas konfigurerar du följande inställningar:

   - **Lägga till URL-adresser med jokertecken**: Ange en URL per rad, upp till maximalt 20.

   - **Blockera/Tillåt**: Välj om du vill **tillåta** eller **blockera** angivna URL-adresser.

   - **Aldrig giltig**: gör något av följande:

     - Kontrol lera att inställningen är avstängt ![ ](../../media/scc-toggle-off.png) och ange förfallo datumet för posterna genom att använda rutan **upphör att gälla** .

     eller

     - Flytta växlings knappen till höger för att konfigurera att posterna aldrig ska förfalla: ![Växlingsknapp aktiverad](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).

   - **Valfri anmärkning**: Ange en beskrivande text för posterna.

4. När du är klar klickar du på **Lägg till**.

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a>Använd säkerhets & Compliance Center för att visa poster i listan Tillåt/blockera för klient organisation

1. Gå till fliken **Threat Management** \> **policy** för \> **Tillåt/blockera listor**i säkerhets & efterlevnad.

2. Välj fliken **URL: er** .

Klicka på följande kolumn rubriker för att sortera i stigande eller fallande ordning:

- **Värde**
- **Åtgärd**: **blockera** eller **Tillåt**.
- **Senast uppdaterad**
- **Utgångs datum**
- **Fotnot**

Klicka på **gruppera** för att gruppera posterna **efter åtgärd** (**blockera** eller **Tillåt**) eller **ingen**.

Klicka på **Sök**, ange hela eller delar av ett värde och tryck sedan på RETUR för att hitta ett visst värde. När du är klar klickar du på **Rensa sökning** ![ rensa Sök ikonen ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) .

Klicka på **filter**. I det **filter** som visas konfigurerar du följande inställningar:

- **Åtgärd**: Välj **Tillåt**, **blockera** eller båda.

- **Aldrig förfaller**: Välj av ( ![ Växla av ](../../media/scc-toggle-off.png) ) eller på ( ![ växling på ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) ).

- **Uppdaterades senast**: Välj ett start datum (**från**), ett slutdatum (**till**) eller båda.

- **Utgångs datum**: Välj ett start datum (**från**), ett slutdatum (**till**) eller båda.

När du är klar klickar du på **Använd**.

Om du vill ta bort befintliga filter klickar du på **filter**och sedan på **Rensa filter**i det **filter** som visas.

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a>Använd säkerhets & Compliance Center för att ändra poster i listan Tillåt/blockera för klient organisation

Du kan inte ändra själva URL-värdet. I stället måste du ta bort posten och skapa den igen.

1. Gå till fliken **Threat Management** \> **policy** för \> **Tillåt/blockera listor**i säkerhets & efterlevnad.

2. Välj fliken **URL: er** .

3. Markera den post som du vill ändra och klicka sedan på **Redigera** ![ redigerings ikon ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) .

4. I den utfällbara filen som visas konfigurerar du följande inställningar:

   - **Blockera/Tillåt**: Välj **Tillåt** eller **blockera**.

   - **Aldrig giltig**: gör något av följande:

     - Kontrol lera att inställningen är avstängt ![ ](../../media/scc-toggle-off.png) och ange förfallo datumet för posten i rutan **upphör att gälla** .

     eller

     - Flytta växlings knappen till höger för att konfigurera posten så att den aldrig förfaller: ![Växlingsknapp aktiverad](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).

   - **Valfri anmärkning**: Ange en beskrivande text för posten.

5. Klicka på **Spara** när du är klar.

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a>Använd säkerhets & Compliance Center för att ta bort poster från listan Tillåt/blockera för klient organisation

1. Gå till fliken **Threat Management** \> **policy** för \> **Tillåt/blockera listor**i säkerhets & efterlevnad.

2. Välj fliken **URL: er** .

3. Markera den post som du vill ta bort och klicka sedan på **ta bort** ![ ikon för borttagning ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) .

4. I varnings dialog rutan som visas klickar du på **ta bort**.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a>Använd Exchange Online PowerShell eller fristående EOP PowerShell för att konfigurera listan Tillåt/blockera klient organisation

### <a name="use-powershell-to-add-entries-in-the-tenant-allowblock-list"></a>Använd PowerShell för att lägga till poster i listan Tillåt/blockera för klient organisation

Använd följande syntax för att lägga till poster i listan Tillåt/blockera i klient organisationen:

```powershell
New-TenantAllowBlockListItems -ListType Url -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

Det här exemplet lägger till en URL-adressblock för contoso.com och alla under domäner (till exempel contoso.com, www.contoso.com och xyz.abc.contoso.com). Eftersom vi inte använde parametrarna förfallo eller noexpires upphör posten efter 30 dagar.

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

Detaljerad information om syntax och parametrar finns i [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a>Använda PowerShell för att visa poster i listan Tillåt/blockera i klient organisationen

Om du vill visa poster i listan Tillåt/begränsa klient organisation använder du följande syntax:

```powershell
Get-TenantAllowBlockListItems -ListType Url [-Entry <URLValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

I det här exemplet returneras alla blockerade URL: er.

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

Detaljerad information om syntax och parametrar finns i [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).

### <a name="use-powershell-to-modify-entries-in-the-tenant-allowblock-list"></a>Använda PowerShell för att ändra poster i listan Tillåt/blockera för klient organisation

Du kan inte ändra själva URL-värdet. I stället måste du ta bort posten och skapa den igen.

Om du vill ändra poster i listan Tillåt/blockera för klient organisation använder du följande syntax:

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

I det här exemplet ändras utgångs datumet för den angivna posten.

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

Detaljerad information om syntax och parametrar finns i [set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).

### <a name="use-powershell-to-remove-entries-from-the-tenant-allowblock-list"></a>Använd PowerShell för att ta bort poster från listan Tillåt/blockera för klient organisation

Om du vill ta bort poster från listan Tillåt/blockera klient organisation använder du följande syntax:

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN">
```

I det här exemplet tas den angivna URL-posten bort från listan Tillåt/blockera för klient organisation.

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

Detaljerad information om syntax och parametrar finns i [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).

## <a name="url-syntax-for-the-tenant-allowblock-list"></a>URL-syntax för listan Tillåt/blockera för klient organisation

- IP4v-och IPv6-adresser är tillåtna, men TCP/UDP-portarna är inte det.

- Fil namns tillägg tillåts inte (till exempel test.pdf).

- Unicode stöds inte, men punycode är.

- Värddator namn är tillåtna om följande påståenden stämmer:

  - Värd namnet innehåller en punkt.
  - Det finns minst ett tecken till vänster om perioden.
  - Det finns minst två tecken till höger om perioden.

  Till exempel `t.co` tillåts `.com` eller `contoso.` är inte tillåtet.

- Under Sök vägar är inte underförstådda.

  Innehåller till exempel `contoso.com` inte `contoso.com/a` .

- Jokertecken (*) tillåts i följande fall:

  - Ett vänster jokertecken måste följas av en punkt för att ange en under domän.

    Till exempel `*.contoso.com` tillåts; `*contoso.com` är inte tillåtet.

  - Ett höger jokertecken måste följa ett snedstreck (/) för att ange en sökväg.

    Till exempel `contoso.com/*` tillåts `contoso.com*` eller `contoso.com/ab*` är inte tillåtet.

  - Alla under Sök vägar underförstås inte med ett höger jokertecken.

    Innehåller till exempel `contoso.com/*` inte `contoso.com/a` .

  - `*.com*` är ogiltig (inte en matchad domän och höger jokertecken följer inte ett snedstreck).

  - Jokertecken tillåts inte i IP-adresser.

- Tilde-tecknet (~) är tillgängligt i följande fall:

  - Ett Vänsterställt tildetecken innebär en domän och alla under domäner.

    Till exempel `~contoso.com` inkluderar `contoso.com` och `*.contoso.com` .

- URL-poster som innehåller protokoll (till exempel `http://` , `https://` eller `ftp://` ) fungerar inte eftersom URL-poster gäller för alla protokoll.

- Det finns inget användar namn eller lösen ord.

- Citat tecken ("or") är ogiltiga tecken.

- En URL ska inkludera alla omdirigeringar om möjligt.

### <a name="url-entry-scenarios"></a>Scenarier för URL-post

Giltiga URL-värden och deras resultat beskrivs i följande avsnitt.

#### <a name="scenario-no-wildcards"></a>Scenario: inga jokertecken

**Post**: `contoso.com`

- **Tillåt matchning**: contoso.com

- **Tillåt ej matchad**:

  - abc-contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www. contoso. com/q = a@contoso. com
  
- **Blockera träff**:

  - contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www. contoso. com/q = a@contoso. com

- **Blockering ej matchad**: ABC-contoso.com

#### <a name="scenario-left-wildcard-subdomain"></a>Scenario: vänster jokertecken (under domän)

**Post**: `*.contoso.com`

- **Tillåt matcha** och **blockera matchning**:

  - www.contoso.com
  - xyz.abc.contoso.com

- **Tillåt ej matchat** och **Blockera ej matchade**:

  - 123contoso.com
  - contoso.com
  - test.com/contoso.com
  - www.contoso.com/abc
  
#### <a name="scenario-right-wildcard-at-top-of-path"></a>Scenario: höger mönster överst i sökvägen

**Post**: `contoso.com/a/*`

- **Tillåt matcha** och **blockera matchning**:

  - contoso.com/a/b
  - contoso.com/a/b/c
  - contoso. com/a/? q = joe@t. com

- **Tillåt ej matchat** och **Blockera ej matchade**:

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www. contoso. com/q = a@contoso. com
  
#### <a name="scenario-left-tilde"></a>Scenario: vänster Tilde

**Post**: `~contoso.com`

- **Tillåt matcha** och **blockera matchning**:

  - contoso.com
  - www.contoso.com
  - xyz.abc.contoso.com

- **Tillåt ej matchat** och **Blockera ej matchade**:

  - 123contoso.com
  - contoso.com/abc
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-suffix"></a>Scenario: höger jokertecken

**Post**: `contoso.com/*`

- **Tillåt matcha** och **blockera matchning**:

  - contoso. com/? q = whatever@fabrikam. com
  - contoso.com/a
  - contoso.com/a/b/c
  - contoso.com/ab
  - contoso.com/b
  - contoso.com/b/a/c
  - contoso.com/ba

- **Tillåt ej matchat** och **blockera icke matchade**: contoso.com

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a>Scenario: vänster-domän och höger jokertecken

**Post**: `*.contoso.com/*`

- **Tillåt matcha** och **blockera matchning**:

  - abc.contoso.com/ab
  - abc.xyz.contoso.com/a/b/c
  - www.contoso.com/a
  - www.contoso.com/b/a/c
  - xyz.contoso.com/ba

- **Tillåt ej matchat** och **blockera icke matchade**: contoso.com/b

#### <a name="scenario-left-and-right-tilde"></a>Scenario: vänster och höger Tilde

**Post**: `~contoso.com~`

- **Tillåt matcha** och **blockera matchning**:

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/b
  - xyz.abc.contoso.com

- **Tillåt ej matchat** och **Blockera ej matchade**:

  - 123contoso.com
  - contoso.org

#### <a name="scenario-ip-address"></a>Scenario: IP-adress

**Post**: `1.2.3.4`

- **Tillåt matchning** och **blockering**: 1.2.3.4

- **Tillåt ej matchat** och **Blockera ej matchade**:

  - 1.2.3.4/a
  - 11.2.3.4/a

#### <a name="ip-address-with-right-wildcard"></a>IP-adress med höger jokertecken

**Post**: `1.2.3.4/*`

- **Tillåt matcha** och **blockera matchning**:

  - 1.2.3.4/b
  - 1.2.3.4/baaaa

### <a name="examples-of-invalid-entries"></a>Exempel på ogiltiga poster

Följande poster är ogiltiga:

- **Domän värden saknas eller är ogiltiga**:

  - contoso
  - \*contoso.\*
  - \*. com
  - \*. pdf

- **Jokertecken på text eller utan blank steg**:

  - \*contoso.com
  - contoso.com\*
  - \*1.2.3.4
  - 1.2.3.4\*
  - contoso.com/a\*
  - contoso.com/ab\*

- **IP-adresser med portar**:

  - contoso.com:443
  - abc.contoso.com:25

- **Icke beskrivande jokertecken**:

  - \*
  - \*.\*

- **Jokertecken**:

  - conto \* so.com
  - conto ~ så. com

- **Dubbel jokertecken**

  - contoso.com/\*\*
  - contoso.com/\*/\*
