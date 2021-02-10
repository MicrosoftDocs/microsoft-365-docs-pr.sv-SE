---
title: Konfigurera standardprincipen för anslutningsfilter
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
ms.assetid: 6ae78c12-7bbe-44fa-ab13-c3768387d0e3
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan läsa om hur de konfigurerar anslutningsfiltrering i Exchange Online Protection (EOP) för att tillåta eller blockera e-postmeddelanden från e-postservrar.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ef81d602e1f6da368e9d469bf1deaf0ef2c0a6af
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165757"
---
# <a name="configure-connection-filtering"></a>Konfigurera anslutningsfiltrering

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


Om du är Microsoft 365-kund med postlådor i Exchange Online eller en fristående Exchange Online Protection-kund (EOP) utan Exchange Online-postlådor använder du anslutningsfiltrering i EOP (speciellt standardprincip för anslutningsfilter) för att identifiera bra eller dåliga käll-e-postservrar med hjälp av IP-adresser. Huvudkomponenterna i standardprincipen för anslutningsfilter är:

- **Lista över tillåtna** IP-adresser: Hoppa över skräppostfiltrering för alla inkommande meddelanden från käll-e-postservrarna som du anger efter IP-adress eller IP-adressintervall. Scenarier där skräppostfiltrering fortfarande kan inträffa på meddelanden från dessa källor finns i scenarier där meddelanden från källor i listan över tillåtna [IP-adresser](#scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered) fortfarande filtreras senare i den här artikeln. Mer information om hur listan över tillåtna IP-adresser ska passa din övergripande strategi för betrodda avsändare finns i Skapa listor över [betrodda avsändare i EOP.](create-safe-sender-lists-in-office-365.md)

- **IP-blockeringslista:** Blockera alla inkommande meddelanden från käll-e-postservrarna som du anger efter IP-adress eller IP-adressintervall. Inkommande meddelanden avvisas, markeras inte som skräppost och ingen ytterligare filtrering sker. Mer information om hur IP-blockeringslistan ska passa in i din övergripande strategi för spärrade avsändare finns i Skapa listor med [spärrade avsändare i EOP.](create-block-sender-lists-in-office-365.md)

- **Lista över** säkra : *Listan över säkra* är en dynamisk lista över tillåtna i Microsoft-datacentret som inte kräver någon kundkonfiguration. Microsoft identifierar dessa betrodda e-postkällor från prenumerationer till olika listor från tredje part. Du aktiverar eller inaktiverar användningen av listan över säkra fel. kan du inte konfigurera käll-e-postservrarna i listan över säkra. Skräppostfiltrering hoppas över på inkommande meddelanden från e-postservrarna på listan över säkra meddelanden.

I det här avsnittet beskrivs hur du konfigurerar standardprincipen för anslutningsfilter i Säkerhets- & och efterlevnadscenter eller i PowerShell (Exchange Online PowerShell för Microsoft 365-organisationer med postlådor i Exchange Online; fristående EOP PowerShell för organisationer utan Exchange Online-postlådor). Mer information om hur EOP använder anslutningsfiltrering är en del av organisationens övergripande inställningar för skydd mot skräppost finns i [Skydd mot skräppost.](anti-spam-protection.md)

> [!NOTE]
> Listan över tillåtna IP-adresser, listan över säkra och BLOCKERADE IP-listor är en del av din övergripande strategi för att tillåta eller blockera e-post i organisationen. Mer information finns i Skapa [listor över betrodda avsändare](create-safe-sender-lists-in-office-365.md) och skapa listor med [spärrade avsändare.](create-block-sender-lists-in-office-365.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>. Om du vill gå direkt till **Inställningar för skräppostskydd** använder du <https://protection.office.com/antispam>.

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Du måste ha tilldelats behörigheter i Säkerhets- och efterlevnadscentret innan du kan genomföra procedurerna i den här artikeln:
  - Om du vill ändra standardprincipen för anslutningsfilter måste du vara medlem i rollgrupperna **Organisationshantering** eller **Säkerhetsadministratör.**
  - För skrivskyddade åtkomst till standardprincipen för anslutningsfilter måste du vara medlem i rollgrupperna **Global Reader** eller **Säkerhetsläsare.**

  Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).

  **Anmärkningar**:

  - Genom att lägga till användare i motsvarande Azure Active Directory-rollen i Administrationscentret för Microsoft 365 får användarna den behörighet som krävs i Säkerhets- och efterlevnadscentret _och_ behörigheter för andra funktioner i Microsoft 365. Mer information finns i [Om administratörsroller](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).
  - Rollgruppen **Skrivskyddad organisationshantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddad åtkomst till funktionen.

- Du hittar IP-adresserna för käll-IP-adresserna för de e-postservrar (avsändare) som du vill tillåta eller blockera genom att kontrollera huvudfältet för anslutande IP **(CIP)** i meddelandehuvudet. Information om hur du visar ett meddelandehuvud i olika [e-postklienter finns i Visa rubriker för Internet-meddelanden i Outlook.](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c)

- Listan över tillåtna IP-adresser har företräde framför ip-blockeringslistan (en adress i båda listorna blockeras inte).

- Listan över tillåtna IP och IP-blockeringslistan stöder var och en maximalt 1273 poster, där en post är en enda IP-adress, ett IP-adressintervall eller en Classless InterDomain Routing (CIDR) IP.

## <a name="use-the-security--compliance-center-to-modify-the-default-connection-filter-policy"></a>Använd Säkerhets- & Center för att ändra standardprincip för anslutningsfilter

1. I Säkerhets- & och gå till **Policy för** hantering \> **av hot** mot \> **skräppost.**

2. På **inställningssidan Skydd mot skräppost expanderar** du **anslutningsfilterprincipen** genom att klicka på ![ ikonen Expandera och sedan på Redigera ](../../media/scc-expand-icon.png) **princip.**

3. I den **utfällmappen** Standard som visas konfigurerar du någon av följande inställningar:

   - **Beskrivning:** Ange valfri beskrivande text.

   - **Listan över tillåtna** IP:er: Klicka **på Redigera.** Ange en IPV4-adress i rutan Adress eller  adressintervall i den utfällningslista för tillåtna **IP-adresser** som visas med följande syntax:

     - Enskild IP: Till exempel 192.168.1.1.

     - IP-intervall: Till exempel 192.168.0.1-192.168.0.254.

     - CIDR IP: Till exempel 192.168.0.1/25. Giltiga nätverksmaskvärden är /24 till /32. Om du vill hoppa över skräppostfiltrering för CIDR IP-maskvärden /1 till /23 läser du Hoppa över skräppostfiltrering för en [CIDR IP](#skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range) utanför det tillgängliga områdesavsnittet senare i den här artikeln.

     Om du vill lägga till IP-adressen eller adressintervallet klickar du **på Lägg till** ![ ](../../media/ITPro-EAC-AddIcon.png) ikon. Om du vill ta bort en post markerar du posten i Tillåten **IP-adress och** klickar sedan på **Ta** ![ ](../../media/scc-remove-icon.png) bort. Klicka på **Spara** när du är klar.

   - **IP-blockeringslista:** Klicka på **Redigera.** Ange en **enda** IP-adress, IP-intervall eller CIDR-IP i  rutan Adress eller adressintervall enligt  beskrivningen i inställningen tillåtna IP-adresser i den utfällningslista som visas.

     Om du vill lägga till IP-adressen eller adressintervallet klickar du **på Lägg till** ![ ](../../media/ITPro-EAC-AddIcon.png) ikon. Om du vill ta bort en post markerar du posten i **Blockerad IP-adress och** klickar sedan på **Ta** ![ ](../../media/scc-remove-icon.png) bort. Klicka på **Spara** när du är klar.

   - **Aktivera listan Betrodda:** Aktivera eller inaktivera användningen av listan över betrodda avsändare för att identifiera kända, bra avsändare som hoppar över skräppostfiltrering.

4. Klicka på **Spara** när du är klar.

## <a name="use-the-security--compliance-center-to-view-the-default-connection-filter-policy"></a>Använd Säkerhets- & center för att visa standardprincipen för anslutningsfilter

1. I Säkerhets- & och gå till **Policy för** hantering \> **av hot** mot \> **skräppost.**

2. På sidan **inställningar för skydd mot skräppost** klickar du på listrutan bredvid standardprincipen med namnet **Anslutningsfilterprincip.**

3. Principinställningarna visas i listrutan som öppnas.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-modify-the-default-connection-filter-policy"></a>Använda Exchange Online PowerShell eller fristående EOP PowerShell för att ändra standardprincipen för anslutningsfilter

Använd följande syntax:

```powershell
Set-HostedConnectionFilterPolicy -Identity Default [-AdminDisplayName <"Optional Comment">] [-EnableSafeList <$true | $false>] [-IPAllowList <IPAddressOrRange1,IPAddressOrRange2...>] [-IPBlockList <IPAddressOrRange1,IPAddressOrRange2...>]
```

**Anmärkningar**:

- Giltiga IP-adresser eller adressintervallvärden är:

  - Enskild IP: Till exempel 192.168.1.1.

  - IP-intervall: Till exempel 192.168.0.1-192.168.0.254.

  - CIDR IP: Till exempel 192.168.0.1/25. Giltiga nätverksmaskvärden är /24 till /32.

- Använd följande syntax *om du* vill skriva över befintliga poster med de värden du anger: `IPAddressOrRange1,IPAddressOrRange2,...,IPAddressOrRangeN`

- Om *du vill lägga till eller* ta bort IP-adresser eller adressintervall utan att påverka andra befintliga poster använder du följande syntax: `@{Add="IPAddressOrRange1","IPAddressOrRange2",...,"IPAddressOrRangeN";Remove="IPAddressOrRange3","IPAddressOrRange4",...,"IPAddressOrRangeN"}`

- Om du vill tömma listan över tillåtna IP-adresser eller IP-blockeringslistan använder du `$null` värdet.

I det här exemplet konfigureras listan över tillåtna IP-adresser och IP-blockeringslistan med angivna IP-adresser och adressintervall.

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList 192.168.1.10,192.168.1.23 -IPBlockList 10.10.10.0/25,172.17.17.0/24
```

I det här exemplet läggs de angivna IP-adresserna och adressintervallen till och tas bort från listan över tillåtna IP-adresser.

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList @{Add="192.168.2.10","192.169.3.0/24","192.168.4.1-192.168.4.5";Remove="192.168.1.10"}
```

Detaljerad information om syntax och parametrar finns [i Set-HostedConnectionFilterPolicy.](https://docs.microsoft.com/powershell/module/exchange/set-hostedconnectionfilterpolicy)

## <a name="how-do-you-know-this-worked"></a>Hur vet du att det fungerade?

Kontrollera att du har ändrat standardprincipen för anslutningsfilter genom att göra något av följande:

- I Säkerhets- & Efterlevnadscenter går du till Threat **Management** \> **Policy** \> **Anti-Spam** och klickar på listrutan bredvid Anslutningsfilterprincip \> **(alltid PÅ)** och kontrollerar inställningarna.

- Kör följande kommando i Exchange Online PowerShell eller fristående EOP PowerShell och kontrollera inställningarna:

  ```powershell
  Get-HostedConnectionFilterPolicy -Identity Default
  ```

- Skicka ett testmeddelande från en post i listan över tillåtna IP-adresser.

## <a name="additional-considerations-for-the-ip-allow-list"></a>Ytterligare överväganden för listan över tillåtna IP-adresser

I följande avsnitt identifieras ytterligare objekt som du behöver känna till när du konfigurerar listan över tillåtna IP-adresser.

### <a name="skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range"></a>Hoppa över skräppostfiltrering för en CIDR IP utanför det tillgängliga intervallet

Enligt beskrivningen tidigare i den här artikeln kan du bara använda en CIDR-IP med nätverksmasken /24 till /32 i listan över tillåtna IP-adresser. Om du vill hoppa över skräppostfiltrering i meddelanden från käll-e-postservrarna i intervallet /1 till /23 måste du använda e-postflödesregler i Exchange (kallas även transportregler). Men vi rekommenderar att du inte gör detta om det är möjligt, eftersom meddelandena kommer att blockeras om en IP-adress i CIDR IP-intervallet mellan /1 och /23 visas på någon av Microsofts egna listor eller blockeringslistor från tredje part.

Nu när du är helt medveten om potentiella problem kan du skapa en e-postflödesregel med följande inställningar (minst) för att säkerställa att meddelanden från dessa IP-adresser hoppar över skräppostfiltrering:

- Regelvillkor:  Använd den här regeln om avsändarens IP-adress finns i något av dessa intervall eller exakt matchar (ange din CIDR IP med en \>  \>  \> /1 till /23 nätverksmask).

- Regelåtgärd: **Ändra meddelandeegenskaperNa Ange** \> **SCL-nivån (Spam Confidence Level) Kringgå** \> **skräppostfiltrering.**

Du kan granska regeln, testa regeln, aktivera regeln under en viss tidsperiod och andra val. Vi rekommenderar att du testar regeln under en period innan du tillämpar den. Mer information finns i Hantera [e-postflödesregler i Exchange Online.](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules)

### <a name="skip-spam-filtering-on-selective-email-domains-from-the-same-source"></a>Hoppa över skräppostfiltrering på selektiva e-postdomäner från samma källa

Vanligtvis innebär tillägg av en IP-adress eller ett IP-adressintervall i listan över tillåtna IP-adresser att du litar på alla inkommande meddelanden från den e-postkällan. Men vad händer om den källan skickar e-post från flera domäner och du vill hoppa över skräppostfiltrering för vissa av de domänerna, men inte för andra? Du kan inte använda listan över tillåtna IP-adresser enbart för detta, men du kan använda listan över tillåtna IP-adresser i kombination med en e-postflödesregel.

Käll-e-postservern 192.168.1.25 skickar till exempel e-post från domänerna contoso.com, fabrikam.com och tailspintoys.com, men du vill bara hoppa över skräppostfiltrering för meddelanden från avsändare i fabrikam.com. Det gör du genom att följa anvisningarna nedan:

1. Lägg till 192.168.1.25 i listan över tillåtna IP-adresser.

2. Konfigurera en e-postflödesregel med följande inställningar (minst:

   - Regelvillkor:  Använd den här regeln om avsändarens IP-adress finns i något av dessa intervall eller exakt matchar \>  \>  \> 192.168.1.25 (samma IP-adress eller adressintervall som du lade till i listan över tillåtna IP-adresser i föregående steg).

   - Regelåtgärd: **Ändra meddelandeegenskaperna** Ange nivån för skräppostförtroende \> **(SCL)** \> **0.**

   - Regelav  undantag: \> **Avsändardomänen** \> är fabrikam.com (endast den eller de domäner som du vill hoppa över skräppostfiltrering).

### <a name="scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered"></a>Scenarier där meddelanden från källor i listan över tillåtna IP-adresser fortfarande filtreras

Meddelanden från en e-postserver i listan över tillåtna IP-adresser omfattas fortfarande av skräppostfiltrering i följande scenarier:

- En IP-adress i listan över tillåtna IP-adresser är också konfigurerad  på en lokal, IP-baserad inkommande koppling i valfri klientorganisation i Microsoft 365 (vi kallar detta klientorganisation **A),** och klientorganisation A och EOP-servern som först stöter på meddelandet båda råkar finnas i samma *Active* Directory-skog i Microsoft-datacenter. I det här scenariot läggs **IPV:CAL**  till i [meddelandets](anti-spam-message-headers.md) rubriker för skydd mot skräppost (som anger att meddelandet kringgår skräppostfiltrering), men meddelandet omfattas fortfarande av skräppostfiltrering.

- Klientorganisationen som innehåller IP-listan över tillåtna adresser och EOP-servern som först stöter på meddelandet kan båda finnas i olika *Active* Directory-skogar i Microsoft-datacenter. I det här **scenariot läggs IPV:CAL** *inte* till i meddelanderubrikerna, så meddelandet omfattas fortfarande av skräppostfiltrering.

Om du stöter på något av dessa scenarier kan du skapa en e-postflödesregel med minst följande inställningar för att se till att meddelanden från problematiska IP-adresser hoppar över skräppostfiltrering:

- Regelvillkor: **Använd den här regeln om** avsändarens IP-adress finns i något av dessa intervall eller exakt matchar \>  \>  \> (din IP-adress eller adress).

- Regelåtgärd: **Ändra meddelandeegenskaperNa Ange** \> **SCL-nivån (Spam Confidence Level) Kringgå** \> **skräppostfiltrering.**

## <a name="new-to-microsoft-365"></a>Är du nybörjare i Microsoft 365?

****

![Den korta ikonen för LinkedIn ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **Learning, ny för Microsoft 365?** Upptäck kostnadsfria videokurser **för Microsoft 365-administratörer och IT-proffs** från LinkedIn Learning.
