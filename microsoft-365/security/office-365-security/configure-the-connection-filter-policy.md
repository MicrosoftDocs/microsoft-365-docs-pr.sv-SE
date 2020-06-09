---
title: Konfigurera standardprincipen för anslutningsfilter
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6ae78c12-7bbe-44fa-ab13-c3768387d0e3
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan lära sig hur du konfigurerar anslutningsfiltrering i Exchange Online Protection (EOP) för att tillåta eller blockera e-postmeddelanden från e-postservrar.
ms.openlocfilehash: 14758161f827cf231a8f3a0415748c7a2dd5981f
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/09/2020
ms.locfileid: "44616596"
---
# <a name="configure-connection-filtering"></a>Konfigurera anslutningsfiltrering

Om du är en Microsoft 365-kund med postlådor i Exchange Online eller en fristående Exchange Online Protection -kund (EOP) utan Exchange Online-postlådor använder du anslutningsfiltrering i EOP (närmare bestämt standardprincipen för anslutningsfilter) för att identifiera e-postservrar för bra eller dåliga källor via deras IP-adresser. De viktigaste komponenterna i standardfiltrets standardfilterprincip är:

- **IP Tillåt lista:** Hoppa över skräppostfiltrering för alla inkommande meddelanden från källan e-postservrar som du anger av IP-adress eller IP-adressintervall. Scenarier där skräppostfiltrering fortfarande kan förekomma på meddelanden från dessa källor finns i [scenarierna där meddelanden från källor i ip-listan fortfarande filtreras](#scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered) senare i det här avsnittet. Mer information om hur IP-listan ska passa in i din övergripande strategi för betrodda avsändare finns [i Skapa listor över betrodda avsändare i EOP](create-safe-sender-lists-in-office-365.md).

- **IP-blockeringslista:** Blockera alla inkommande meddelanden från käll-e-postservrar som du anger per IP-adress eller IP-adressintervall. De inkommande meddelandena avvisas, markeras inte som skräppost och ingen ytterligare filtrering sker. Mer information om hur IP-blockeringslistan ska passa in i din övergripande strategi för blockerade avsändare finns [i Skapa blockavsändare i EOP](create-block-sender-lists-in-office-365.md).

- **Säker lista**: Den *säkra listan* är en dynamisk tillåt-lista i Microsoft-datacenter som inte kräver någon kundkonfiguration. Microsoft identifierar dessa betrodda e-postkällor från prenumerationer på olika tredjepartslistor. Du aktiverar eller inaktiverar användningen av den säkra listan. Du kan inte konfigurera käll-e-postservrarna i den säkra listan. Skräppostfiltrering hoppas över inkommande meddelanden från e-postservrarna i den säkra listan.

I det här avsnittet beskrivs hur du konfigurerar standardprincipen för anslutningsfilter i Security & Compliance Center eller i PowerShell (Exchange Online PowerShell för Microsoft 365-organisationer med postlådor i Exchange Online; fristående EOP PowerShell för organisationer utan Exchange Online-postlådor). Mer information om hur EOP använder anslutningsfiltrering är en del av organisationens övergripande inställningar mot skräppost finns i [Skydd mot skräppost](anti-spam-protection.md).

> [!NOTE]
> IP-listan tillåt, en säker lista och IP-blockeringslistan är en del av din övergripande strategi för att tillåta eller blockera e-post i organisationen. Mer information finns i [Skapa listor över betrodda avsändare](create-safe-sender-lists-in-office-365.md) och [Skapa blockerade avsändarelistor](create-block-sender-lists-in-office-365.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>. Om du vill gå direkt till **Inställningar för skräppostskydd** använder du <https://protection.office.com/antispam>.

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Information om hur du ansluter till fristående EOP PowerShell finns i artikeln om att [Ansluta till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Du måste ha tilldelats behörigheter innan du kan genomföra de här procedurerna. Om du vill ändra standardprincipen för anslutningsfilter måste du vara medlem i rollgrupperna **Organisationshantering** eller **Säkerhetsadministratör.** För skrivskyddad åtkomst till standardsynreringsfilterprincipen måste du vara medlem i rollgruppen **Säkerhetsläsare.** Mer information om rollgrupper i Säkerhets- och efterlevnadscenter finns i [Behörigheter i Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).

- Om du vill hitta käll-IP-adresserna för de e-postservrar (avsändare) som du vill tillåta eller blockera kan du kontrollera det anslutande IP-huvudet **(CIP)** i meddelandehuvudet. Om du vill visa ett meddelandehuvud i olika e-postklienter finns i [Visa internetmeddelanderubriker i Outlook](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c).

- IP-listan har företräde framför IP-blockeringslistan (en adress i båda listorna är inte blockerad).

- IP-listan och IP-blockeringslistan stöder var och en högst 1273 poster, där en post är en enda IP-adress, ett IP-adressintervall eller en klasslös CIDR-IP (InterDomain Routing).

## <a name="use-the-security--compliance-center-to-modify-the-default-connection-filter-policy"></a>Använd security & Compliance Center för att ändra standardprincipen för anslutningsfilter

1. I Security & Compliance Center och gå till **Threat Management** \> **Policy** \> **Anti-Spam**.

2. På sidan **Inställningar för skräppost** expanderar du principen För **anslutningsfilter** genom att klicka på ![ Ikonen Expandera och sedan klicka på Redigera ](../../media/scc-expand-icon.png) **princip**.

3. Konfigurera **Default** någon av följande inställningar i standardutfällninget som visas:

   - **Beskrivning**: Ange valfri beskrivande text.

   - **LISTA FÖR IP-tillåt:** Klicka på **Redigera.** Ange en IPV4-adress i rutan Adress eller **adressintervall** i den **ip-tillåtalista** som visas med följande syntax:

     - Enkel IP: Till exempel 192.168.1.1.

     - IP-intervall: Till exempel 192.168.0.1-192.168.0.254.

     - CIDR IP: Till exempel 192.168.0.1/25. Giltiga nätverksmaskvärden är /24 till /32. Om du vill hoppa över skräppostfiltrering för CIDR IP-maskvärden /1 till /23 läser du [Skräppostfiltrering för en CIDR IP-ip-adress utanför det tillgängliga avsnittet senare](#skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range) i det här avsnittet.

     Om du vill lägga till IP-adressen eller adressintervallet klickar du på **Lägg till** ![ ikonen ](../../media/ITPro-EAC-AddIcon.png) . Om du vill ta bort en post markerar du posten i **Tillåten IP-adress** och klickar sedan på **Ta bort** ![ ](../../media/scc-remove-icon.png) . Klicka på **Spara** när du är klar.

   - **IP-blocklista:** Klicka på **Redigera.** In the **IP Block List** flyout that appears, enter a single IP, IP range, or CIDR IP in the **Address or address range** box as previously described in the **IP Allow List** setting.

     Om du vill lägga till IP-adressen eller adressintervallet klickar du på **Lägg till** ![ ikonen ](../../media/ITPro-EAC-AddIcon.png) . Om du vill ta bort en post markerar du posten i **Blockerad IP-adress** och klickar sedan på **Ta bort** ![ ](../../media/scc-remove-icon.png) . Klicka på **Spara** när du är klar.

   - **Aktivera säker lista:** Aktivera eller inaktivera användningen av den säkra listan för att identifiera kända, bra avsändare som hoppar över skräppostfiltrering.

4. Klicka på **Spara** när du är klar.

## <a name="use-the-security--compliance-center-to-view-the-default-connection-filter-policy"></a>Använda security & Compliance Center för att visa standardprincipen för anslutningsfilter

1. I Security & Compliance Center och gå till **Threat Management** \> **Policy** \> **Anti-Spam**.

2. På sidan **Inställningar för skräppost** klickar du på listrutan bredvid standardprincipen **Anslutningsfilterprincip**.

3. Principinställningarna visas i listrutan som öppnas.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-modify-the-default-connection-filter-policy"></a>Använd Exchange Online PowerShell eller fristående EOP PowerShell för att ändra standardprincipen för anslutningsfilter

Använd följande syntax:

```powershell
Set-HostedConnectionFilterPolicy -Identity Default [-AdminDisplayName <"Optional Comment">] [-EnableSafeList <$true | $false>] [-IPAllowList <IPAddressOrRange1,IPAddressOrRange2...>] [-IPBlockList <IPAddressOrRange1,IPAddressOrRange2...>]
```

**Anmärkningar**:

- Giltiga IP-adress- eller adressintervallvärden är:

  - Enkel IP: Till exempel 192.168.1.1.

  - IP-intervall: Till exempel 192.168.0.1-192.168.0.254.

  - CIDR IP: Till exempel 192.168.0.1/25. Giltiga nätverksmaskvärden är /24 till /32.

- Om du vill *skriva över* alla befintliga poster med de värden du anger använder du följande syntax: `IPAddressOrRange1,IPAddressOrRange2,...,IPAddressOrRangeN` .

- Om du vill *lägga till eller ta bort* IP-adresser eller adressintervall utan att påverka andra befintliga poster använder du följande syntax: `@{Add="IPAddressOrRange1","IPAddressOrRange2",...,"IPAddressOrRangeN";Remove="IPAddressOrRange3","IPAddressOrRange4",...,"IPAddressOrRangeN"}` .

- Om du vill tömma IP Allow List eller IP Block List använder du värdet `$null` .

I det här exemplet konfigureras IP-listan tillåt och IP-blockeringslistan med angivna IP-adresser och adressintervall.

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList 192.168.1.10,192.168.1.23 -IPBlockList 10.10.10.0/25,172.17.17.0/24
```

I det här exemplet läggs till och tas de angivna IP-adresserna och adressintervallen bort från listan TILLÅT IP.This example adds and removes the specified IP addresses and address ranges from the IP Allow List.

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList @{Add="192.168.2.10","192.169.3.0/24","192.168.4.1-192.168.4.5";Remove="192.168.1.10"}
```

Detaljerad syntax- och parameterinformation finns i [Ange värdbaseradconnectionfilterpolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedconnectionfilterpolicy).

## <a name="how-do-you-know-this-worked"></a>Hur vet du att det fungerade?

Så här kontrollerar du att du har ändrat standardprincipen för anslutningsfilter:

- Gå till Anti-Spam för **hothanteringspolicy** i säkerhets- & efterlevnadscenter \> **Policy** \> **Anti-Spam** \> och kontrollera inställningarna. **Connection filter policy (always ON**

- I Exchange Online PowerShell eller fristående EOP PowerShell kör du följande kommando och verifierar inställningarna:

  ```powershell
  Get-HostedConnectionFilterPolicy -Identity Default
  ```

- Skicka ett testmeddelande från en post i listan TILLÅT IP.

## <a name="additional-considerations-for-the-ip-allow-list"></a>Ytterligare överväganden för IP-listan över tillåt

I följande avsnitt identifieras ytterligare objekt som du behöver känna till när du konfigurerar listan TILLÅT IP.The following section identify additional items that you need to know about when you configure the IP Allow List.

### <a name="skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range"></a>Hoppa över skräppostfiltrering för en CIDR IP utanför det tillgängliga intervallet

Som beskrivits tidigare i det här avsnittet kan du bara använda en CIDR IP med nätverksmasken /24 till /32 i IP-listan. Om du vill hoppa över skräppostfiltrering på meddelanden från käll-e-postservrar i intervallet /1 till /23 måste du använda Exchange-regler för e-postflöde (kallas även transportregler). Men vi rekommenderar att du inte gör detta om det alls är möjligt, eftersom meddelandena blockeras om en IP-adress i CIDR-IP-intervallet /1 till /23 visas på någon av Microsofts egna blocklistor eller blocklistor från tredje part.

Nu när du är fullt medveten om de potentiella problemen kan du skapa en regel för e-postflöde med följande inställningar (minst) för att säkerställa att meddelanden från dessa IP-adresser hoppar över skräppostfiltrering:

- Regelvillkor: **Använd den här regeln om** \> **The sender** \> **AVSÄNDARENS IP-adress finns i något av dessa intervall eller exakt matchar** \> (ange din CIDR IP med en /1 till /23 nätverksmask).

- Regelåtgärd: **Ändra meddelandeegenskaperna** \> **Ange skräppostförtroendenivå (SCL)** Kringgå \> **skräppostfiltrering**.

Du kan granska regeln, testa regeln, aktivera regeln under en viss tidsperiod och andra val. Vi rekommenderar att du testar regeln under en period innan du tillämpar den. Mer information finns [i Hantera regler för e-postflöde i Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules).

### <a name="skip-spam-filtering-on-selective-email-domains-from-the-same-source"></a>Hoppa över skräppostfiltrering på selektiva e-postdomäner från samma källa

Om du lägger till en IP-adress eller ett IP-adressintervall i LISTAN IP Tillåt innebär du att du litar på alla inkommande meddelanden från den e-postkällan. Men vad händer om den källan skickar e-post från flera domäner, och du vill hoppa över skräppostfiltrering för vissa av dessa domäner, men inte andra? Du kan inte använda ip-listan ensam för att göra detta, men du kan använda IP-listan tillåt i kombination med en regel för e-postflöde.

Källmeddelandeservern 192.168.1.25 skickar till exempel e-post från domänerna contoso.com, fabrikam.com och tailspintoys.com, men du vill bara hoppa över skräppostfiltrering för meddelanden från avsändare i fabrikam.com. Gör så här:

1. Lägg till 192.168.1.25 i IP-listan över tillåt.

2. Konfigurera en regel för e-postflöde med följande inställningar (minst):

   - Regelvillkor: **Använd den här regeln om** \> **The sender** \> **avsändarens IP-adress finns i något av dessa intervall eller exakt matchar** \> 192.168.1.25 (samma IP-adress eller adressintervall som du lade till i IP-listan tillåt i föregående steg).

   - Regelåtgärd: **Ändra meddelandeegenskaperna** \> **Ange informationsnivå för skräppost (SCL)** \> **0**.

   - Regelundantag: **Avsändningsdomänen** \> **är** \> fabrikam.com (endast den domän eller de domäner som du vill hoppa över skräppostfiltrering).

### <a name="scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered"></a>Scenarier där meddelanden från källor i listan TILLÅT IP-lista fortfarande filtreras

Meddelanden från en e-postserver i listan TILLÅT IP är fortfarande föremål för skräppostfiltrering i följande scenarier:

- En IP-adress i ip-listan konfigureras också i en lokal, IP-baserad inkommande anslutningsapp i *alla* innehavare i Microsoft 365 (låt oss anropa den här klient A) **och** klient A och EOP-servern som först stöter på meddelandet båda råkar vara i *samma* Active Directory-skog i Microsoft-datacenter. I det här fallet *läggs* **IPV:CAL** till i meddelandets [skräppostrubriker](anti-spam-message-headers.md) (som anger att meddelandet kringgås skräppostfiltrering), men meddelandet är fortfarande föremål för skräppostfiltrering.

- Din klient som innehåller IP Allow List och EOP-servern som först stöter på meddelandet båda råkar vara i *olika* Active Directory-skogar i Microsoft-datacenter. I det här fallet *läggs inte* **IPV:CAL** till i meddelanderubrikerna, så meddelandet är fortfarande föremål för skräppostfiltrering.

Om du stöter på något av dessa scenarier kan du skapa en regel för e-postflöde med följande inställningar (minst) för att säkerställa att meddelanden från de problematiska IP-adresserna hoppar över skräppostfiltrering:

- Regelvillkor: **Använd den här regeln om** \> **The sender** \> **avsändarens IP-adress finns i något av dessa intervall eller exakt matchar** \> (din IP-adress eller dina IP-adresser).

- Regelåtgärd: **Ändra meddelandeegenskaperna** \> **Ange skräppostförtroendenivå (SCL)** Kringgå \> **skräppostfiltrering**.

## <a name="new-to-microsoft-365"></a>Ny på Microsoft 365?

||
|:-----|
|![Den korta ikonen för LinkedIn Learning ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New till Microsoft 365?** Upptäck kostnadsfria videokurser för **administratörer och IT-proffs**, som presenteras av LinkedIn Learning.|
