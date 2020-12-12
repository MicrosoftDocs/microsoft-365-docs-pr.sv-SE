---
title: Konfigurera standard princip för anslutnings filter
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
ms.assetid: 6ae78c12-7bbe-44fa-ab13-c3768387d0e3
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan lära dig hur du konfigurerar anslutnings filtrering i Exchange Online Protection (EOP) för att tillåta eller blockera e-postservrar.
ms.openlocfilehash: 844b1d8d17a99bbb0c441be511c64a009b8dafcb
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659819"
---
# <a name="configure-connection-filtering"></a>Konfigurera anslutningsfiltrering

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Om du är Microsoft 365-kund med post lådor i Exchange Online eller på en fristående Exchange Online Protection (EOP)-kund utan Exchange Online-postlådor, använder du anslutnings filtrering i EOP (specifikt en standard princip för anslutnings filter) för att identifiera godkända e-postservrar med deras IP-adresser. Huvud komponenterna i standard princip för anslutnings filter är:

- **IP-lista**: hoppa över skräp post filtrering för alla inkommande meddelanden från de käll-e-postservrar som du anger via IP-adress eller IP-adressintervall. Om du har problem med att skicka skräp post från dessa källor kan du läsa de [scenarier där meddelanden från källor i listan IP-adresser fortfarande är filtrerat](#scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered) i den här artikeln. Mer information om hur listan över tillåtna IP-adresser ska placeras i den övergripande strategin för säker avsändare finns i [skapa säkra avsändare listor i EOP](create-safe-sender-lists-in-office-365.md).

- **IP-blockeringslistan**: blockera alla inkommande meddelanden från de käll-e-postservrar som du anger via IP-adress eller IP-adressintervall. Inkommande meddelanden avvisas, har inte marker ATS som skräp post och ingen ytterligare filtrering sker. Mer information om hur IP-blockeringslistan får plats i den övergripande strategin för blockerade avsändare finns i [skapa block avsändare i EOP](create-block-sender-lists-in-office-365.md).

- **Säker lista**: den *säkra listan* är en dynamisk Tillåt-lista i Microsoft Data Center som inte kräver kund konfiguration. Microsoft identifierar dessa betrodda e-postkällor från abonnemang till olika listor från tredje part. Du aktiverar eller inaktiverar användning av den säkra listan. Du kan inte konfigurera käll-e-postservrarna på den säkra listan. Skräp post filter hoppas över för inkommande meddelanden från e-postservrarna på den säkra listan.

I det här avsnittet beskrivs hur du konfigurerar standard princip för anslutnings filter i fältet säkerhets & efterlevnad eller i PowerShell (Exchange Online PowerShell för Microsoft 365-organisationer med post lådor i Exchange Online, fristående EOP PowerShell för organisationer utan Exchange Online-postlådor). Mer information om hur EOP använder anslutnings filtrering är en del av organisationens övergripande inställningar för [skydd mot skräp post](anti-spam-protection.md).

> [!NOTE]
> Listan över tillåtna IP-adresser, säkra listor och IP-blockeringslistan är en del av den övergripande strategin för att tillåta eller blockera e-post i din organisation. Mer information finns i [skapa säkra avsändare](create-safe-sender-lists-in-office-365.md) och [skapa spärrade avsändare](create-block-sender-lists-in-office-365.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>. Om du vill gå direkt till **Inställningar för skräppostskydd** använder du <https://protection.office.com/antispam>.

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Du måste ha tilldelats behörigheter i Säkerhets- och efterlevnadscentret innan du kan genomföra procedurerna i den här artikeln:
  - Om du vill ändra standard princip för anslutnings filter måste du vara medlem i roll grupperna **organisations hantering** eller **säkerhets administratör** .
  - Om du vill ha skrivskyddad åtkomst till standard anslutnings filter principen måste du vara medlem i rollen **global läsare** eller **säkerhets läsare** .

  Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).

  **Anmärkningar**:

  - Genom att lägga till användare i motsvarande Azure Active Directory-rollen i Administrationscentret för Microsoft 365 får användarna den behörighet som krävs i Säkerhets- och efterlevnadscentret _och_ behörigheter för andra funktioner i Microsoft 365. Mer information finns i [Om administratörsroller](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).
  - Rollgruppen **Skrivskyddad organisationshantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddad åtkomst till funktionen.

- Om du vill ta reda på käll-IP-adresserna för de e-postservrar (avsändare) som du vill tillåta eller blockera kan du kontrol lera värdet för **CIP**-huvudet i meddelande huvudet. Information om hur du visar meddelande huvudet i olika e-postklienter finns i [Visa Internet meddelande rubriker i Outlook](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c).

- Listan över tillåtna IP-adresser har högre prioritet än IP-blockeringslistan (en adress i båda listor är inte blockerad).

- Listan över tillåtna IP-adresser och IP-adressblock stöder högst 1273 poster, där en post är en enda IP-adress, ett IP-adressintervall eller en klass lösa Interdomain Routing-IP.

## <a name="use-the-security--compliance-center-to-modify-the-default-connection-filter-policy"></a>Använd säkerhets & Compliance Center för att ändra standard princip för anslutnings filter

1. I säkerhets & Compliance Center och gå till skydd mot **hot Management** \> **policy** \> **mot skräp post**.

2. På sidan **Inställningar för skräp post** expanderar du **filter policy för anslutning** genom att klicka på ![ ikonen Expandera ](../../media/scc-expand-icon.png) och sedan på **Redigera princip**.

3. I den **standardinställning** som visas konfigurerar du följande inställningar:

   - **Beskrivning**: ange valfri beskrivande text.

   - **Lista över tillåtna IP-adresser**: Klicka på **Redigera**. Ange en IPV4-adress i rutan **adress eller adress intervall** med hjälp av följande syntax i **listan IP-** utfällning som visas:

     - En IP-adress: till exempel 192.168.1.1.

     - IP-intervall: till exempel 192.168.0.1-192.168.0.254.

     - CIDR-IP: till exempel 192.168.0.1/25. Giltiga nätverks mask värden är/24 till/med/32. Om du vill hoppa över skräp post filtrering för CIDR-värden för IP-mask/1 till/23 kan du läsa avsnittet [hoppa över skräp post filtrering för en CIDR-IP utanför det tillgängliga området](#skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range) i den här artikeln.

     Om du vill lägga till IP-adressen eller adress intervallet klickar du på **Lägg** till ![ ikonen Lägg till ](../../media/ITPro-EAC-AddIcon.png) . Om du vill ta bort en post markerar du posten i den **tillåtna IP-adressen** och klickar sedan på **ta bort** ![ borttagning ](../../media/scc-remove-icon.png) . Klicka på **Spara** när du är klar.

   - **IP-blockeringslistan**: Klicka på **Redigera**. I **listan IP-blockeringslistan** som visas anger du ett IP-, IP-ADRESSINTERVALL eller CIDR-IP i rutan **adress eller adress intervall** enligt beskrivningen i **listan IP Allow List** .

     Om du vill lägga till IP-adressen eller adress intervallet klickar du på **Lägg** till ![ ikonen Lägg till ](../../media/ITPro-EAC-AddIcon.png) . Om du vill ta bort en post markerar du posten i den **blockerade IP-adressen** och klickar sedan på **ta bort** ![ borttagning ](../../media/scc-remove-icon.png) . Klicka på **Spara** när du är klar.

   - **Aktivera fel säkert-lista**: Aktivera eller inaktivera användning av den säkra listan för att identifiera kända, lämpliga avsändare som kommer att förhindra skräp post filtrering.

4. Klicka på **Spara** när du är klar.

## <a name="use-the-security--compliance-center-to-view-the-default-connection-filter-policy"></a>Använd säkerhets & Compliance Center för att Visa standard princip för anslutnings filter

1. I säkerhets & Compliance Center och gå till skydd mot **hot Management** \> **policy** \> **mot skräp post**.

2. På sidan **Inställningar för skräp post** klickar du på den nedrullningsbara List rutan bredvid standard principen med namnet **anslutnings filter princip**.

3. Princip inställningarna visas i den nedrullningsbara List rutan som öppnas.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-modify-the-default-connection-filter-policy"></a>Använda Exchange Online PowerShell eller fristående EOP PowerShell för att ändra standard princip för anslutnings filter

Använd följande syntax:

```powershell
Set-HostedConnectionFilterPolicy -Identity Default [-AdminDisplayName <"Optional Comment">] [-EnableSafeList <$true | $false>] [-IPAllowList <IPAddressOrRange1,IPAddressOrRange2...>] [-IPBlockList <IPAddressOrRange1,IPAddressOrRange2...>]
```

**Anmärkningar**:

- Giltiga värden för IP-adress eller adress intervall är:

  - En IP-adress: till exempel 192.168.1.1.

  - IP-intervall: till exempel 192.168.0.1-192.168.0.254.

  - CIDR-IP: till exempel 192.168.0.1/25. Giltiga nätverks mask värden är/24 till/med/32.

- Om du vill *skriva över* befintliga poster med de värden du anger kan du använda följande syntax: `IPAddressOrRange1,IPAddressOrRange2,...,IPAddressOrRangeN` .

- Använd följande syntax för att *lägga till eller ta bort* IP-adresser eller adress områden utan att påverka andra befintliga poster: `@{Add="IPAddressOrRange1","IPAddressOrRange2",...,"IPAddressOrRangeN";Remove="IPAddressOrRange3","IPAddressOrRange4",...,"IPAddressOrRangeN"}` .

- Använd värdet för att tömma listan IP-lista eller IP-adressblock `$null` .

Det här exemplet konfigurerar listan över tillåtna IP-adresser och IP-adressblock med de angivna IP-adresserna och adress områdena.

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList 192.168.1.10,192.168.1.23 -IPBlockList 10.10.10.0/25,172.17.17.0/24
```

I det här exemplet läggs de angivna IP-adresserna och adress områdena till från listan över tillåtna IP-adresser.

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList @{Add="192.168.2.10","192.169.3.0/24","192.168.4.1-192.168.4.5";Remove="192.168.1.10"}
```

Detaljerad information om syntax och parametrar finns i [set-HostedConnectionFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedconnectionfilterpolicy).

## <a name="how-do-you-know-this-worked"></a>Hur vet du att det fungerade?

Gör något av följande för att kontrol lera att du har ändrat standard princip för anslutnings filter:

- I säkerhets & Compliance Center går du till skydd mot **hot Management** \> **policy** \> **mot skräp post** genom att \> Klicka på list rutan bredvid **anslutnings filter princip (alltid aktiverat**) och kontrol lera inställningarna.

- Kör följande kommando i Exchange Online PowerShell eller fristående EOP PowerShell och kontrol lera inställningarna:

  ```powershell
  Get-HostedConnectionFilterPolicy -Identity Default
  ```

- Skicka ett test meddelande från en post i listan över tillåtna IP-adresser.

## <a name="additional-considerations-for-the-ip-allow-list"></a>Ytterligare överväganden för listan över tillåtna IP-adresser

I följande avsnitt hittar du ytterligare objekt som du måste känna till när du konfigurerar listan över tillåtna IP-adresser.

### <a name="skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range"></a>Hoppa över skräp post filtrering för en CIDR-IP utanför det tillgängliga intervallet

Enligt beskrivningen ovan kan du bara använda en CIDR-IP med nätverks masken/24 till/32 i listan över tillåtna IP-adresser. Om du vill hoppa över skräp post filtrering för meddelanden från käll-e-postservrar i området/1 till/med 23 måste du använda regler för Exchange-flöden (kallas även transport regler). Men vi rekommenderar att du inte gör det om det skulle vara möjligt eftersom meddelanden blockeras om en IP-adress i en/ett-till-23-CIDR-adressintervall visas på någon av Microsofts patentskydd eller tredje parts block listor.

Nu när du är helt medveten om möjliga problem kan du skapa en regel för e-postflöde med följande inställningar (minst) för att säkerställa att meddelanden från följande IP-adresser åsidosätter skräp post filtrering:

- Regel villkor: **Använd den här regeln om** \> **avsändarens** \> **IP-adress finns i något av dessa områden eller exakt matchar** \> (ange din CIDR-IP med en/1 till/23 nätverks mask).

- Regel åtgärd: **ändra meddelande egenskaper** \> **ange nivån för skräp post (SCL)** \> **kringgå filtrering av skräp posten**.

Du kan granska regeln, testa regeln, aktivera regeln under en viss tids period och andra val. Vi rekommenderar att du testar regeln för en period innan du använder den. Mer information finns i [Hantera regler för e-postflöden i Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules).

### <a name="skip-spam-filtering-on-selective-email-domains-from-the-same-source"></a>Hoppa över skräp post filtrering för selektiva e-postdomäner från samma källa

Om du lägger till en IP-adress eller ett adress intervall i listan över tillåtna IP-adresser innebär det att du litar på alla inkommande meddelanden från den e-postkälla Men vad händer om den källan skickar e-post från flera domäner och du vill hoppa över filtreringen av skräp post för vissa av dessa domäner, men inte till andra? Du kan inte använda listan över tillåtna IP-adresser för det här, men det går att använda listan över tillåtna IP-adresser i kombination med en regel för e-postflöde.

Till exempel skickar käll-e-postservern e-post från domänerna contoso.com, fabrikam.com och tailspintoys.com, men du vill bara hoppa över skräp post filtrering för meddelanden från avsändare i fabrikam.com. Gör så här:

1. Lägg till 192.168.1.25 i listan över tillåtna IP-adresser.

2. Konfigurera en regel för e-postflöde med följande inställningar (minst):

   - Regel villkor: **Använd den här regeln om** \> **avsändarens** \> **IP-adress finns i något av dessa områden eller exakt matchar** \> 192.168.1.25 (samma IP-adress eller adress intervall som du har lagt till i listan över tillåtna IP-adresser i föregående steg).

   - Regel åtgärd: **ändra meddelande egenskaperna** \> **ange nivån för skräp post (SCL)** \> **0**.

   - Regel undantag: **avsändarens** \> **domän är** \> fabrikam.com (endast domänen eller domänerna som du vill hoppa till skräp post filtrering).

### <a name="scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered"></a>Scenarier där meddelanden från källor i listan över tillåtna IP-adresser fortfarande filtreras

Meddelanden från en e-postserver i listan över tillåtna IP-adresser är fortfarande beroende av skräp post filtrering i följande fall:

- En IP-adress i din IP Allow-lista är också konfigurerad i en lokal, IP-baserad inkommande koppling i *en* klient organisation i Microsoft 365 (låt oss ringa till klient organisationen a), **och** klient organisationen a och EOP-servern som första gången upptäcker att meddelandet kommer att finnas i *samma* Active Directory-skog i Microsoft-datacenters. I det här scenariot läggs **IPV: CAL** *till i* meddelandets [meddelandehuvuden](anti-spam-message-headers.md) (som indikerar att meddelandet ignorerade skräp post filtrering), men meddelandet är fortfarande beroende av skräp post filtrering.

- Din klient organisation som innehåller listan över tillåtna IP-adresser och EOP-servern som först påträffar meddelandet inträffar i *olika* Active Directory-skogar i Microsoft-datacenter. I det här scenariot har **IPV: CAL** *inte* lagts till i meddelande huvudena, så meddelandet är fortfarande beroende av skräp post filtrering.

Om du stöter på något av dessa scenarion kan du skapa en regel för e-postflöde med följande inställningar (minst) för att säkerställa att meddelanden från de problematiska IP-adresserna hoppar över skräp post filtrering:

- Regel villkor: **Använd den här regeln om** \> **avsändarens** \> **IP-adress finns i något av dessa områden eller exakt matchar** \> (din IP-adress eller dina adresser).

- Regel åtgärd: **ändra meddelande egenskaper** \> **ange nivån för skräp post (SCL)** \> **kringgå filtrering av skräp posten**.

## <a name="new-to-microsoft-365"></a>Nyheter i Microsoft 365?

****

![Kort ikonen för LinkedIn Learning ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **som är ny för Microsoft 365?** Upptäck kostnads fria video kurser för **Microsoft 365-administratörer och IT-proffs**, som du kommer åt via LinkedIn Learning.
