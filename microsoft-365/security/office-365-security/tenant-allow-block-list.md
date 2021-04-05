---
title: Hantera tillåt och block i listan över tillåtna/blockerade klientorganisation
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
description: Administratörer kan ta reda på hur de konfigurerar tillåts och block i listan över tillåtna/blockerade klienter i säkerhetsportalen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 103ddc9aa0858f9203582ac07a655fd7f5506cf3
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587593"
---
# <a name="manage-the-tenant-allowblock-list"></a>Hantera Klientorganisationens Tillåt/blockera listan

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> Du kan för **stunden inte** konfigurera tillåtna objekt i listan över tillåtna/blockerade klienter.

I Microsoft 365-organisationer som har postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor kanske du inte instämmer i EOP-filtreringsrektion. Till exempel kan ett bra meddelande markeras som dåligt (falskt positivt) eller så kan ett felaktigt meddelande tillåtas (falskt negativt).

Med klientorganisationens lista över tillåtna/blockerade & säkerhets- och efterlevnadscenter får du ett sätt att manuellt åsidosätta Microsoft 365-filtreringens bedömningar. Klientorganisationens lista över tillåtna/blockerade används under e-postflödet och när användaren klickar. Du kan ange att URL:er eller filer alltid ska blockeras.

I den här artikeln beskrivs hur du konfigurerar poster i listan Över tillåtna/blockerade klientorganisationer i Säkerhets- och efterlevnadscenter för & eller i PowerShell (Exchange Online PowerShell för Microsoft 365-organisationer med postlådor i Exchange Online, fristående EOP PowerShell för organisationer utan Exchange Online-postlådor).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>. Använd för att gå direkt **till sidan För att tillåta/blockera** klientorganisation. <https://protection.office.com/tenantAllowBlockList>

- Du anger filer genom att använda hashvärdet SHA256 för filen. Om du vill hitta HASH-värdet för SHA256 för en fil i Windows kör du följande kommando i kommandotolken:

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  Ett exempelvärde är `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` . Perceptuella hash-värden (pHash) stöds inte.

- Tillgängliga URL-värden beskrivs i [URL-syntaxen för avsnittet Tillåt/blockera klientorganisation](#url-syntax-for-the-tenant-allowblock-list) senare i den här artikeln.

- Klientorganisationens lista över tillåtna/blockerade tillåter maximalt 500 poster för URL:er och 500 poster för filshashar.

- Det maximala antalet tecken för varje post är:
  - Filshashar = 64
  - URL = 250

- En post ska vara aktiv inom 30 minuter.

- Som standard förfaller poster i klientorganisationens lista över tillåtna/blockerade användare efter 30 dagar. Du kan ange ett datum eller ange att de aldrig ska upphöra.

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Du måste ha tilldelats behörigheter i **Exchange Online** innan du kan genomföra procedurerna i den här artikeln:
  - Om du vill lägga till och ta bort värden från klientorganisationens lista över tillåtna/blockerade användare måste du vara medlem i rollgrupperna Organisationshantering eller **Säkerhetsadministratör.** 
  - För skrivskyddad åtkomst till listan över tillåtna/blockerade klientorganisationer måste du vara medlem i rollgrupperna **Global Reader** **eller Säkerhetsläsare.**

  Mer information finns under [Behörigheter i Exchange Online](/exchange/permissions-exo/permissions-exo).

  > [!NOTE]
  > 
  > - Genom att lägga till användare i motsvarande Azure Active Directory-roll i administrationscentret för Microsoft 365 får användarna den nödvändiga behörigheten _och_ behörigheter för andra funktioner i Microsoft 365. Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).
  > - Rollgruppen **Skrivskyddad organisationshantering** i [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddad åtkomst till funktionen.

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a>Använd Säkerhets- & kompatibilitetscenter för att skapa URL-poster i listan över tillåtna/blockerade klientorganisationen

Mer information om syntaxen för URL-poster finns i URL-syntaxen för avsnittet [Tillåt/blockera klientorganisation](#url-syntax-for-the-tenant-allowblock-list) längre fram i den här artikeln.

1. I Säkerhets- & säkerhets- och efterlevnadscenter går du till **listan** över \>  \> **tillåtna/blockerade hotprinciper för klientorganisationen.**

2. På sidan **Lista över tillåtna/blockerade** klientorganisation kontrollerar du att **fliken URL:er** är markerad och klickar sedan på **Blockera**

3. I den **utfällna** menyn Blockera URL:er som visas konfigurerar du följande inställningar:

   - **Lägg till URL:er som ska** blockeras: Ange en URL per rad, upp till högst 20.

   - **Upphör aldrig** att gälla: Gör något av följande:

     - Kontrollera att inställningen är inaktiverad (inaktiverad) och ange utgångsdatumet för posterna ![ ](../../media/scc-toggle-off.png) i rutan Förfaller. 

       eller

     - Flytta reglaget till höger för att konfigurera posterna så att de aldrig upphör att gälla: ![Växlingsknapp aktiverad](../../media/scc-toggle-on.png).

   - **Valfritt:** Ange beskrivande text för posterna.

4. När du är klar klickar du på Lägg **till**.

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a>Använd Säkerhets- & säkerhets- och efterlevnadscenter för att skapa filposter i klientorganisationens lista över tillåtna/blockerade filer

1. I Säkerhets- & säkerhets- och efterlevnadscenter går du till **listan** över \>  \> **tillåtna/blockerade hotprinciper för klientorganisationen.**

2. Välj fliken **Filer på sidan Lista över tillåtna/blockerade** **klientorganisation** och klicka sedan på **Blockera**.

3. I den **utfällna menyn** Lägg till filer för att blockera som visas konfigurerar du följande inställningar:

   - **Lägga till filhashar:** Ange ett SHA256-hashvärde per rad, upp till högst 20.

   - **Upphör aldrig** att gälla: Gör något av följande:

     - Kontrollera att inställningen är inaktiverad (inaktiverad) och ange utgångsdatumet för posterna ![ ](../../media/scc-toggle-off.png) i rutan Förfaller. 

     eller

     - Flytta reglaget till höger för att konfigurera posterna så att de aldrig upphör att gälla: ![Växlingsknapp aktiverad](../../media/scc-toggle-on.png).

   - **Valfritt:** Ange beskrivande text för posterna.

4. När du är klar klickar du på Lägg **till**.

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a>Använd Säkerhets- & kompatibilitetscenter för att visa poster i listan över tillåtna/blockerade klientorganisationen

1. I Säkerhets- & säkerhets- och efterlevnadscenter går du till **listan** över \>  \> **tillåtna/blockerade hotprinciper för klientorganisationen.**

2. Välj **fliken URL:er** eller **fliken** Filer.

Klicka på följande kolumnrubriker om du vill sortera stigande eller fallande:

- **Värde:** URL:en eller filens hashtagg.
- **Datum för senaste uppdatering**
- **Förfallodatum**
- **Obs!**

Klicka **på** Sök , ange hela eller en del av ett värde och tryck sedan på RETUR för att hitta ett visst värde. När du är klar klickar du på **Rensa sökning Ikonen** Rensa ![ ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) sökning.

Klicka **på Filtrera**. I  den utfällna menyn Filter som visas konfigurerar du någon av följande inställningar:

- **Upphör aldrig:** Välj av: ![ Aktivera eller ](../../media/scc-toggle-off.png) inaktivera: Aktivera ![ ](../../media/scc-toggle-on.png) .

- **Uppdaterades** senast: Välj ett startdatum **(Från),** ett slutdatum **(Till)** eller båda.

- **Förfallodatum:** Välj ett startdatum **(Från),** ett slutdatum **(Till)** eller båda.

När du är klar klickar du på **Använd**.

Om du vill ta bort befintliga  **filter klickar** du på Filter och sedan på Rensa filter i den **utfällklara filterfällan som visas.**

## <a name="use-the-security--compliance-center-to-modify-block-entries-in-the-tenant-allowblock-list"></a>Använd Säkerhets- & säkerhets- och efterlevnadscenter för att ändra blockeringsposter i listan över tillåtna/blockerade klientorganisationen

Du kan inte ändra befintliga blockerade URL-adresser eller filvärden i en post. Om du vill ändra dessa värden måste du ta bort och återskapa posten.

1. I Säkerhets- & säkerhets- och efterlevnadscenter går du till **listan** över \>  \> **tillåtna/blockerade hotprinciper för klientorganisationen.**

2. Välj **fliken URL:er** eller **fliken** Filer.

3. Markera den blockpost som du vill  ändra och klicka sedan på redigera ![ redigeringsikonen ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) .

4. Konfigurera följande inställningar i den utfäll du vill använda:

   - **Upphör aldrig** att gälla: Gör något av följande:

     - Kontrollera att inställningen är inaktiverad (inaktiverad) och ange utgångsdatumet för inmatningen i ![ ](../../media/scc-toggle-off.png) rutan Förfaller. 

       eller

     - Flytta reglaget till höger för att konfigurera posten så att den aldrig upphör att gälla: ![Växlingsknapp aktiverad](../../media/scc-toggle-on.png).

   - **Valfritt:** Ange en beskrivande text för posten.

5. Klicka på **Spara** när du är klar.

## <a name="use-the-security--compliance-center-to-remove-block-entries-from-the-tenant-allowblock-list"></a>Använd Säkerhets- & för att ta bort blockeringsposter från listan över tillåtna/blockerade klientorganisationen

1. I Säkerhets- & säkerhets- och efterlevnadscenter går du till **listan** över \>  \> **tillåtna/blockerade hotprinciper för klientorganisationen.**

2. Välj **fliken URL:er** eller **fliken** Filer.

3. Markera den blockeringspost du vill ta bort och klicka sedan på ikonen **Ta** ![ ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) bort.

4. Klicka på Ta bort i varningsdialogrutan som **visas.**

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a>Använd Exchange Online PowerShell eller fristående EOP PowerShell för att konfigurera listan över tillåtna/blockerade klientorganisationen

### <a name="use-powershell-to-add-block-entries-to-the-tenant-allowblock-list"></a>Använda PowerShell för att lägga till blockeringsposter i innehavarlistan över tillåtna/blockerade

Använd följande syntax för att lägga till blockeringsposter i klientorganisationens lista över tillåtna/blockerade klienter:

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Block -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

I det här exemplet läggs en blockerings-URL-post till för contoso.com och alla underdomäner (till exempel contoso.com, www.contoso.com och xyz.abc.contoso.com). Eftersom vi inte använder parametrarna Förfallodatum eller NoExpiration upphör posten att gälla efter 30 dagar.

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

I det här exemplet läggs en post för blockering av filer till för de angivna filerna som aldrig förfaller.

```powershell
New-TenantAllowBlockListItems -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

Detaljerad information om syntax och parametrar finns i [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a>Använda PowerShell för att visa poster i listan över tillåtna/blockerade klientorganisationen

Om du vill visa poster i listan över tillåtna/blockerade klientorganisationen använder du följande syntax:

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Block] [-ExpirationDate <DateTime>] [-NoExpiration]
```

I det här exemplet returneras alla blockerade URL-adresser.

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

Det här exemplet returnerar information om det angivna hash-värdet för filen.

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

Detaljerad information om syntax och parametrar finns i [Get-TenantAllowBlockListItems.](/powershell/module/exchange/get-tenantallowblocklistitems)

### <a name="use-powershell-to-modify-block-entries-in-the-tenant-allowblock-list"></a>Använda PowerShell för att ändra blockeringsposter i innehavarlistan över tillåtna/blockerade

Du kan inte ändra befintliga URL- eller filvärden inom en blockeringspost. Om du vill ändra dessa värden måste du ta bort och återskapa posten.

Om du vill ändra blockeringsposter i listan över tillåtna/blockerade klientorganisationen använder du följande syntax:

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Block] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

I det här exemplet ändras förfallodatumet för den angivna blockposten.

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

Detaljerad information om syntax och parametrar finns i [Set-TenantAllowBlockListItems.](/powershell/module/exchange/set-tenantallowblocklistitems)

### <a name="use-powershell-to-remove-block-entries-from-the-tenant-allowblock-list"></a>Använda PowerShell för att ta bort blockeringsposter från innehavarlistan över tillåtna/blockerade

Använd följande syntax för att ta bort blockeringsposter från klientorganisationens lista över tillåtna/blockerade användare:

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

Det här exemplet tar bort den angivna blockerings-URL-posten från klientorganisationens lista över tillåtna/blockerade adresser.

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

Detaljerad information om syntax och parametrar finns i [Remove-TenantAllowBlockListItems.](/powershell/module/exchange/remove-tenantallowblocklistitems)

## <a name="url-syntax-for-the-tenant-allowblock-list"></a>URL-syntax för klientorganisationens lista över tillåtna/blockerade

- IP4v- och IPv6-adresser är tillåtna, men INTE TCP-/UDP-portar.

- Filnamnstillägg är inte tillåtna (till exempel test.pdf).

- Unicode stöds inte, men punycode stöds.

- Hostnames tillåts om alla följande uttryck är sanna:
  - Värdnamnet innehåller en punkt.
  - Det finns minst ett tecken till vänster om perioden.
  - Det finns minst två tecken till höger om perioden.

  Till exempel är `t.co` tillåtet eller `.com` inte `contoso.` tillåtet.

- Undervägar är inte underförstådda.

  Exempelvis `contoso.com` ingår inte `contoso.com/a` .

- Jokertecken (*) tillåts i följande scenarier:

  - Ett vänster jokertecken måste följas av en punkt för att ange en underdomän.

    Är till exempel `*.contoso.com` tillåtet, `*contoso.com` är inte tillåtet.

  - Ett höger jokertecken måste följa ett snedstreck (/) om du vill ange en sökväg.

    Till exempel är `contoso.com/*` tillåtet eller `contoso.com*` inte `contoso.com/ab*` tillåtet.

  - Alla undervägar kan inte underförstådas med ett rätt jokertecken.

    Exempelvis `contoso.com/*` ingår inte `contoso.com/a` .

  - `*.com*` är ogiltig (inte en lösbar domän och att rätt jokertecken inte följer ett snedstreck).

  - Jokertecken tillåts inte i IP-adresser.

- Tecknet tilde (~) är tillgängligt i följande scenarier:

  - Ett vänster tilde-namn antyder en domän och alla underdomäner.

    Exempel: `~contoso.com` inkluderar `contoso.com` och `*.contoso.com` .

- URL-poster som innehåller protokoll (till exempel , eller ) kommer att `http://` `https://` `ftp://` misslyckas, eftersom URL-poster tillämpas på alla protokoll.

- Ett användarnamn eller lösenord stöds inte eller krävs inte.

- Citattecken (' eller ") är ogiltiga tecken.

- En URL bör innehålla alla omdirigeringar där det är möjligt.

### <a name="url-entry-scenarios"></a>URL-inmatningsscenarier

Giltiga URL-poster och deras resultat beskrivs i följande avsnitt.

#### <a name="scenario-no-wildcards"></a>Scenario: Inga jokertecken

**Post:**`contoso.com`

- **Tillåt matchning:** contoso.com

- **Tillåt ej matchad:**

  - abc-contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

- **Blockmatchning:**

  - contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

- **Blockera matchas inte:** abc-contoso.com

#### <a name="scenario-left-wildcard-subdomain"></a>Scenario: Vänster jokertecken (underdomän)

**Post:**`*.contoso.com`

- **Tillåt matchning** och **Blockeringsmatchning:**

  - www.contoso.com
  - xyz.abc.contoso.com

- **Tillåt ej matchad** och **Blockera ej matchad:**

  - 123contoso.com
  - contoso.com
  - test.com/contoso.com
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-at-top-of-path"></a>Scenario: Höger jokertecken högst upp i sökvägen

**Post:**`contoso.com/a/*`

- **Tillåt matchning** och **Blockeringsmatchning:**

  - contoso.com/a/b
  - contoso.com/a/b/c
  - contoso.com/a/?q=joe@t.com

- **Tillåt ej matchad** och **Blockera ej matchad:**

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

#### <a name="scenario-left-tilde"></a>Scenario: Vänster tilde

**Post:**`~contoso.com`

- **Tillåt matchning** och **Blockeringsmatchning:**

  - contoso.com
  - www.contoso.com
  - xyz.abc.contoso.com

- **Tillåt ej matchad** och **Blockera ej matchad:**

  - 123contoso.com
  - contoso.com/abc
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-suffix"></a>Scenario: Höger suffix för jokertecken

**Post:**`contoso.com/*`

- **Tillåt matchning** och **Blockeringsmatchning:**

  - contoso.com/?q=whatever@fabrikam.com
  - contoso.com/a
  - contoso.com/a/b/c
  - contoso.com/ab
  - contoso.com/b
  - contoso.com/b/a/c
  - contoso.com/ba

- **Tillåt ej matchad** och **Blockera ej matchad**: contoso.com

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a>Scenario: Vänster underdomän med jokertecken och höger suffix för jokertecken

**Post:**`*.contoso.com/*`

- **Tillåt matchning** och **Blockeringsmatchning:**

  - abc.contoso.com/ab
  - abc.xyz.contoso.com/a/b/c
  - www.contoso.com/a
  - www.contoso.com/b/a/c
  - xyz.contoso.com/ba

- **Tillåt ej matchad** och **Blockera ej matchad**: contoso.com/b

#### <a name="scenario-left-and-right-tilde"></a>Scenario: Vänster och höger tilde

**Post:**`~contoso.com~`

- **Tillåt matchning** och **Blockeringsmatchning:**

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/b
  - xyz.abc.contoso.com

- **Tillåt ej matchad** och **Blockera ej matchad:**

  - 123contoso.com
  - contoso.org

#### <a name="scenario-ip-address"></a>Scenario: IP-adress

**Post:**`1.2.3.4`

- **Tillåt matchning** och **Blockeringsmatchning**: 1.2.3.4

- **Tillåt ej matchad** och **Blockera ej matchad:**

  - 1.2.3.4/a
  - 11.2.3.4/a

#### <a name="ip-address-with-right-wildcard"></a>IP-adress med rätt jokertecken

**Post:**`1.2.3.4/*`

- **Tillåt matchning** och **Blockeringsmatchning:**

  - 1.2.3.4/b
  - 1.2.3.4/baaaa

### <a name="examples-of-invalid-entries"></a>Exempel på ogiltiga poster

Följande poster är ogiltiga:

- **Värden som saknas eller är ogiltiga:**

  - contoso
  - \*CONTOSO.\*
  - \*.com
  - \*PDF

- **Jokertecken på text eller utan avståndstecken:**

  - \*contoso.com
  - contoso.com\*
  - \*1.2.3.4
  - 1.2.3.4\*
  - contoso.com/a\*
  - contoso.com/ab\*

- **IP-adresser med portar:**

  - contoso.com:443
  - abc.contoso.com:25

- **Icke-beskrivande jokertecken:**

  - \*
  - \*.\*

- **Jokertecken i mitten:**

  - conto \* so.com
  - conto~so.com

- **Dubbla jokertecken**

  - contoso.com/\*\*
  - contoso.com/\*/\*
