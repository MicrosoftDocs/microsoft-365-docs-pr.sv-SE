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
description: Administratörer kan läsa om hur de konfigurerar anslutningsfiltrering i Exchange Online Protection (EOP) för att tillåta eller blockera e-post från e-postservrar.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 416fbd73d8412cf8697577df19f2fd2893b4ce96
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878826"
---
# <a name="configure-connection-filtering"></a>Konfigurera anslutningsfiltrering

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)


Om du är Microsoft 365-kund med postlådor i Exchange Online eller en fristående Exchange Online Protection(EOP)-kund utan Exchange Online-postlådor använder du anslutningsfiltrering i EOP (specifikt standardprincipen för anslutningsfilter) för att identifiera bra eller dåliga käll-e-postservrar efter IP-adresser. Huvudkomponenterna i standardprincipen för anslutningsfilter är:

- **Lista över tillåtna** IP-adresser: Hoppa över skräppostfiltrering för alla inkommande meddelanden från käll-e-postservrarna som du anger via IP-adress eller IP-adressintervall. Scenarier där skräppostfiltrering fortfarande kan inträffa på meddelanden från dessa källor finns i avsnittet Scenarier där meddelanden från källor i listan över tillåtna [IP-adresser](#scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered) fortfarande filtreras längre fram i den här artikeln. Mer information om hur listan över tillåtna IP-adresser ska passa din övergripande strategi för betrodda avsändare finns i [Skapa listor över betrodda avsändare i EOP.](create-safe-sender-lists-in-office-365.md)

- **IP-blockeringslista:** Blockera alla inkommande meddelanden från käll-e-postservrarna som du anger via IP-adress eller IP-adressintervall. Inkommande meddelanden avvisas, markeras inte som skräppost och ingen ytterligare filtrering sker. Mer information om hur IP-blockeringslistan ska passa in i din övergripande strategi för spärrade avsändare finns i Skapa listor över [spärrade avsändare i EOP.](create-block-sender-lists-in-office-365.md)

- **Valv listan**: Listan *över säkra är* en dynamisk lista över tillåtna i Microsoft-datacentret som inte kräver någon kundkonfiguration. Microsoft identifierar dessa betrodda e-postkällor från prenumerationer till olika tredjepartslistor. Du aktiverar eller inaktiverar användningen av listan över säkra tjänster. kan du inte konfigurera käll-e-postservrarna i listan över säkra servrar. Skräppostfiltrering hoppas över på inkommande meddelanden från e-postservrarna på listan över säkra meddelanden.

I den här artikeln beskrivs hur du konfigurerar standardprincipen för anslutningsfilter i Microsoft 365 Microsoft 365 Defender-portalen eller i PowerShell (Exchange Online PowerShell för Microsoft 365-organisationer med postlådor i Exchange Online, fristående EOP PowerShell för organisationer utan Exchange Online-postlådor). Mer information om hur EOP använder anslutningsfiltrering är en del av organisationens övergripande inställningar för skydd mot skräppost finns i [Skydd mot skräppost.](anti-spam-protection.md)

> [!NOTE]
> Listan över tillåtna IP-adresser, listan över säkra och IP-blockeringslistan är en del av din övergripande strategi för att tillåta eller blockera e-post i organisationen. Mer information finns i Skapa [listor över betrodda avsändare](create-safe-sender-lists-in-office-365.md) och Skapa listor med [spärrade avsändare.](create-block-sender-lists-in-office-365.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Du öppnar Microsoft 365 Defender-portalen på <https://security.microsoft.com> . Om du vill gå direkt till sidan **Principer för skräppostskydd** använder du <https://security.microsoft.com/antispam>.

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Du måste ha tilldelats behörigheter i **Exchange Online** innan du kan genomföra procedurerna i den här artikeln:
  - Om du vill ändra standardprincipen för anslutningsfilter måste du vara medlem i **rollgrupperna Organisationshantering** **eller Säkerhetsadministratör.**
  - För skrivskyddade åtkomst till standardprincipen för anslutningsfilter måste du vara medlem i rollgrupperna **Global Reader** **eller Säkerhetsläsare.**

  Mer information finns under [Behörigheter i Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Anteckningar**:

  - Genom att lägga till användare i motsvarande Azure Active Directory-roll i administrationscentret för Microsoft 365 får användarna den nödvändiga behörigheten _och_ behörigheter för andra funktioner i Microsoft 365. Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).
  - Rollgruppen **Skrivskyddad organisationshantering** i [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddad åtkomst till funktionen.

- Du hittar käll-IP-adresserna för de e-postservrar (avsändare) som du vill tillåta eller blockera genom att kontrollera huvudfältet för ip-adresser **(CIP)** i meddelandehuvudet. Information om hur du visar ett meddelandehuvud i olika e-postklienter finns [i Visa rubriker för internetmeddelanden i Outlook](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c).

- Listan över tillåtna IP-adresser har företräde framför blockeringslistan för IP (en adress i båda listorna blockeras inte).

- Listan över tillåtna IP-adresser och blockeringslistan för IP stöder maximalt 1273 poster, där en post är en enskild IP-adress, ett IP-adressintervall eller en CIDR-IP (Classless InterDomain Routing).

## <a name="use-the-microsoft-365-defender-portal-to-modify-the-default-connection-filter-policy"></a>Med Defender Microsoft 365 portalen kan du ändra standardprincipen för anslutningsfilter

1. I Microsoft 365 Defender-portalen går du till **avsnittet Principer för &-&** \>  \>  \>  \> **e-&** principer för hot mot skräppost.

2. På sidan **Principer för skydd mot skräppost** väljer du **Anslutningsfilterprincip (Standard)** i listan genom att klicka på namnet på principen.

3. Konfigurera någon av följande inställningar i den utfällade menyn med principinformation:

   - **Beskrivningsavsnitt:** Klicka **på Redigera namn och beskrivning**. I den **utfällbara rutan Redigera** namn och beskrivning anger du valfri beskrivande text i **rutan** Beskrivning.

     Klicka på **Spara** när du är klar.

   - **Avsnittet Anslutningsfiltrering:** Klicka **på Redigera princip för anslutningsfilter**. Konfigurera följande inställningar i den utfäll du vill använda:

     - **Tillåt alltid meddelanden från följande IP-adresser eller adressintervall:** Det här är listan över tillåtna IP-adresser. Klicka i rutan, ange ett värde och tryck sedan på Retur eller välj hela värdet som visas nedanför rutan. Giltiga värden är
       - Enskild IP: Till exempel 192.168.1.1.
       - IP-intervall: Till exempel 192.168.0.1-192.168.0.254.
       - CIDR IP: Till exempel 192.168.0.1/25. Giltiga värden för undernätsmasker är /24 till /32. Om du vill hoppa över skräppostfiltreringen för /1 till /23 läser du Hoppa över skräppostfiltrering för en [CIDR-IP](#skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range) utanför det tillgängliga intervallet längre fram i den här artikeln.

       Upprepa det här steget så många gånger det behövs. Om du vill ta bort ett befintligt värde klickar du Ta bort ![Ta bort-ikonen](../../media/m365-cc-sc-remove-selection-icon.png) bredvid värdet.

     Om du vill lägga till IP-adressen eller adressintervallet klickar du i rutan och skriver detklicka på **Lägg till** ![ ](../../media/ITPro-EAC-AddIcon.png) ikon. Om du vill ta bort en post markerar du posten i Tillåten **IP-adress och** klickar sedan på Ta **bort** ![ ](../../media/scc-remove-icon.png) . Klicka på **Spara** när du är klar.

   - **Spärra alltid meddelanden från följande IP-adresser eller adressintervall:** Det här är listan över blockerade IP-adresser. Ange en enskild IP-adress, IP-intervall eller CIDR IP i rutan enligt beskrivningen i inställningen Tillåt alltid meddelanden från följande **IP-adresser eller adressintervall.**

   - **Aktivera listan Betrodda**: Aktivera eller inaktivera användningen av listan över betrodda avsändare för att identifiera kända och betrodda avsändare som hoppar över skräppostfiltrering. Markera kryssrutan om du vill använda listan Över säkra objekt.

   Klicka på **Spara** när du är klar.

4. Tillbaka på utfällda menyn principinformation klickar du **Stäng**.

## <a name="use-the-microsoft-365-defender-portal-to-view-the-default-connection-filter-policy"></a>Använda Defender Microsoft 365 portalen för att visa standardprincipen för anslutningsfilter

1. I Microsoft 365 Defender-portalen går du till **avsnittet Principer för &-&** \>  \>  \>  \> **e-&** principer för hot mot skräppost.

2. På **sidan Principer för skydd mot** skräppost visas följande egenskaper i listan med principer:

   - **Namn:** Det här värdet **är Anslutningsfilterprincip (standard)** för standardprincipen för anslutningsfilter.
   - **Status:** Det här värdet **är alltid på** för standardprincipen för anslutningsfilter.
   - **Prioritet:** Det här värdet **är Lägst** för standardprincipen för anslutningsfilter.
   - **Typ:** Det här värdet är tomt för standardprincipen för anslutningsfilter.

3. När du väljer standardprincip för anslutningsfilter visas principinställningarna i en utfällmapp.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-modify-the-default-connection-filter-policy"></a>Använd Exchange Online PowerShell eller fristående EOP PowerShell för att ändra standardprincipen för anslutningsfilter

Använd följande syntax:

```powershell
Set-HostedConnectionFilterPolicy -Identity Default [-AdminDisplayName <"Optional Comment">] [-EnableSafeList <$true | $false>] [-IPAllowList <IPAddressOrRange1,IPAddressOrRange2...>] [-IPBlockList <IPAddressOrRange1,IPAddressOrRange2...>]
```

**Anmärkningar**:

- Giltiga IP-adresser eller adressintervallvärden är:
  - Enskild IP: Till exempel 192.168.1.1.
  - IP-intervall: Till exempel 192.168.0.1-192.168.0.254.
  - CIDR IP: Till exempel 192.168.0.1/25. Giltiga nätverksmaskvärden är /24 till /32.
- Om *du vill skriva över* befintliga poster med de värden du anger använder du följande syntax: `IPAddressOrRange1,IPAddressOrRange2,...,IPAddressOrRangeN` .
- Om *du vill lägga till eller* ta bort IP-adresser eller adressintervall utan att påverka andra befintliga poster använder du följande syntax: `@{Add="IPAddressOrRange1","IPAddressOrRange2",...,"IPAddressOrRangeN";Remove="IPAddressOrRange3","IPAddressOrRange4",...,"IPAddressOrRangeN"}` .
- Om du vill tömma listan över tillåtna IP-adresser eller blockeringslistan för IP använder du värdet `$null` .

I det här exemplet konfigureras listan över tillåtna IP-adresser och ip-blockeringslistan med angivna IP-adresser och adressintervall.

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList 192.168.1.10,192.168.1.23 -IPBlockList 10.10.10.0/25,172.17.17.0/24
```

I det här exemplet läggs de angivna IP-adresserna och adressintervallen till och tas bort från listan över tillåtna IP-adresser.

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList @{Add="192.168.2.10","192.169.3.0/24","192.168.4.1-192.168.4.5";Remove="192.168.1.10"}
```

Detaljerad information om syntax och parametrar finns i [Set-HostedConnectionFilterPolicy.](/powershell/module/exchange/set-hostedconnectionfilterpolicy)

## <a name="how-do-you-know-this-worked"></a>Hur vet du att det fungerade?

Du kan kontrollera att standardprincipen för anslutningsfilter har ändrats genom att göra något av följande:

- I Microsoft 365 Defender-portalen går du till Principer för **e-postsamarbete** & & Principer för hot mot skräppost. Välj Anslutningsfilterprincip \>  \>  \>  \>  \> **(standard)** i listan genom att klicka på principens namn och kontrollera inställningarna.

- I Exchange Online PowerShell eller fristående EOP PowerShell kör du följande kommando och kontrollerar inställningarna:

  ```powershell
  Get-HostedConnectionFilterPolicy -Identity Default
  ```

- Skicka ett testmeddelande från en post i listan över tillåtna IP-adresser.

## <a name="additional-considerations-for-the-ip-allow-list"></a>Ytterligare överväganden för listan över tillåtna IP-adresser

I följande avsnitt identifieras ytterligare objekt som du behöver känna till när du konfigurerar listan över tillåtna IP-adresser.

### <a name="skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range"></a>Hoppa över skräppostfiltrering för en CIDR IP utanför det tillgängliga intervallet

Enligt beskrivningen tidigare i den här artikeln kan du bara använda en CIDR-IP med nätverksmasken /24 till /32 i listan över tillåtna IP-adresser. Om du vill hoppa över skräppostfiltrering på meddelanden från käll-e-postservrarna i intervallet /1 till /23 måste du använda Exchange-e-postflödesregler (kallas även transportregler). Men vi rekommenderar att du inte gör det om det är möjligt, eftersom meddelandena kommer att blockeras om en IP-adress i /1 till /23 CIDR IP-intervallet visas på någon av Microsofts företags- eller tredjepartsblockslistor.

Nu när du är helt medveten om potentiella problem kan du skapa en e-postflödesregel med minst följande inställningar för att säkerställa att meddelanden från dessa IP-adresser hoppar över skräppostfiltreringen:

- Regelvillkor: **Använd** den här regeln om avsändarens IP-adress finns i något av dessa intervall eller exakt matchar (ange din CIDR IP med en \>  \>  \> /1 till /23-nätverksmask).
- Regelåtgärd: **Ändra meddelandeegenskaperNa Ange** \> **SCL-nivån (Spam Confidence Level) Kringgå** \> **skräppostfiltrering.**

Du kan granska regeln, testa regeln, aktivera regeln under en viss tidsperiod och andra val. Vi rekommenderar att du testar regeln under en period innan du tillämpar den. Mer information finns i Hantera [e-postflödesregler i Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules).

### <a name="skip-spam-filtering-on-selective-email-domains-from-the-same-source"></a>Hoppa över skräppostfiltrering på selektiva e-postdomäner från samma källa

Vanligtvis innebär det att du litar på alla inkommande meddelanden från den e-postkällan när du lägger till en IP-adress eller ett IP-adressintervall i listan över tillåtna IP-adresser. Men hur gör jag om källan skickar e-post från flera domäner och du vill hoppa över skräppostfiltreringen för vissa av de domänerna, men inte för andra? Du kan inte använda listan över tillåtna IP-adresser enbart för detta, men du kan använda listan över tillåtna IP-adresser i kombination med en e-postflödesregel.

Exempelvis skickar käll-e-postservern 192.168.1.25 e-post från domänerna contoso.com, fabrikam.com och tailspintoys.com, men du vill bara hoppa över skräppostfiltrering för meddelanden från avsändare i fabrikam.com. Gör så här:

1. Lägg till 192.168.1.25 i listan över tillåtna IP-adresser.

2. Konfigurera en e-postflödesregel med minst följande inställningar:
   - Regelvillkor:  Använd den här regeln om avsändarens IP-adress finns i något av dessa intervall eller exakt matchar \>  \> 192.168.1.25 (samma **IP-adress** eller adressintervall som du lade till i listan över tillåtna IP-adresser i föregående \> steg).
   - Regelåtgärd: **Ändra meddelandeegenskaperNa** \> **Ange SCL-nivån (Spam Confidence Level)** \> **0.**
   - Regel utom: **Avsändardomänen** \>  \> är fabrikam.com (endast den eller de domäner som du vill hoppa över skräppostfiltrering i).

### <a name="scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered"></a>Scenarier där meddelanden från källor i listan över tillåtna IP-adresser fortfarande filtreras

Meddelanden från en e-postserver i din lista över tillåtna IP-adresser är fortfarande skräppostfiltrering i följande fall:

- En IP-adress i listan över tillåtna IP-adresser är också konfigurerad  på en lokal, IP-baserad inkommande koppling i valfri klientorganisation i Microsoft 365 (vi kallar den här klientorganisationen **A)** och klientorganisation A och EOP-servern som först stöter på meddelandet båda råkar finnas i samma *Active* Directory-skog i Microsoft-datacenter. I det här scenariot läggs **IPV:CAL**  till i [meddelandets](anti-spam-message-headers.md) rubriker för skydd mot skräppost (som visar att meddelandet kringgår skräppostfiltrering), men meddelandet är fortfarande skräppostfiltrering.

- Klientorganisationen som innehåller IP-listan över tillåtna ip-adresser och EOP-servern som först stöter på meddelandet, inträffar båda i olika *Active* Directory-skogar i Microsoft-datacenter. I det här **scenariot har IPV:CAL**  inte lagts till i meddelanderubrikerna, vilket innebär att meddelandet fortfarande filtreras av skräppost.

Om du stöter på något av dessa scenarier kan du skapa en e-postflödesregel med minst följande inställningar för att se till att meddelanden från problematiska IP-adresser hoppar över skräppostfiltreringen:

- Regelvillkor: **Använd den här regeln om** avsändarens IP-adress finns i något av intervallen eller exakt \>  \> **matchar** \> (din IP-adress eller dina adresser).
- Regelåtgärd: **Ändra meddelandeegenskaperNa Ange** \> **SCL-nivån (Spam Confidence Level) Kringgå** \> **skräppostfiltrering.**

## <a name="new-to-microsoft-365"></a>Är du nybörjare Microsoft 365?

****

![Den korta ikonen för LinkedIn Learning ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **är nytt för Microsoft 365?** Upptäck kostnadsfria videokurser **för Microsoft 365 administratörer och IT-proffs**, från LinkedIn Learning.
