---
title: Använda DKIM för e-post i en egen domän
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/05/2021
audience: ITPro
ms.topic: article
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 56fee1c7-dc37-470e-9b09-33fff6d94617
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Lär dig hur du använder DomainKeys identifierad e-post (DKIM) med Microsoft 365 för att säkerställa att meddelanden som skickas från din anpassade domän är betrodda av mål-e-postsystemet.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9aa67d7875bb7f81c6569b56704d221b57378962
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108505"
---
# <a name="use-dkim-to-validate-outbound-email-sent-from-your-custom-domain"></a>Använda DKIM för att validera utgående e-post som skickas från din anpassade domän

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

 Den här artikeln innehåller steg för att använda DomainKeys Identified Mail (DKIM) med Microsoft 365 för att säkerställa att mål-e-postsystemen litar på utgående meddelanden som skickas från din anpassade domän.

I den här artikeln:

- [Hur DKIM fungerar bättre än enbart SPF för att förhindra skadlig förfalskning](#how-dkim-works-better-than-spf-alone-to-prevent-malicious-spoofing)
- [Steg för att manuellt uppgradera dina 1024-bitars nycklar till 2048-bitars DKIM-krypteringsnycklar](#steps-to-manually-upgrade-your-1024-bit-keys-to-2048-bit-dkim-encryption-keys)
- [Steg för att konfigurera DKIM manuellt](#steps-to-manually-set-up-dkim)
- [Steg för att konfigurera DKIM för fler än en anpassad domän](#to-configure-dkim-for-more-than-one-custom-domain)
- [Inaktivera DKIM-signeringsprincipen för en anpassad domän](#disabling-the-dkim-signing-policy-for-a-custom-domain)
- [Standardbeteende för DKIM och Microsoft 365](#default-behavior-for-dkim-and-microsoft-365)
- [Konfigurera DKIM så att en tjänst från tredje part kan skicka, eller förfalska, e-postmeddelanden för din anpassade domän](#set-up-dkim-so-that-a-third-party-service-can-send-or-spoof-email-on-behalf-of-your-custom-domain)
- [Nästa steg: När du har konfigurerat DKIM för Microsoft 365](#next-steps-after-you-set-up-dkim-for-microsoft-365)

> [!NOTE]
> Microsoft 365 konfigurerar automatiskt DKIM för dess ursprungliga ”onmicrosoft.com”-domäner. Det innebär att du inte behöver göra något för att konfigurera DKIM för alla inledande domännamn (t. ex. litware.onmicrosoft.com). Mer information om domäner finns i [Vanliga frågor och svar om domäner](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain).

DKIM är en av tre autentiseringsmetoder (SPF, DKIM och DMARC) som hjälper till att förhindra angripare att skicka meddelanden som ser ut som att de kommer från din domän.

Med DKIM kan du lägga till en digital signatur i utgående e-postmeddelanden i meddelanderubriken. När du konfigurerar DKIM auktoriserar du domänen att associera, eller signera, dess namn till ett e-postmeddelande med hjälp av krypterad autentisering. E-postsystem som får e-post från din domän kan använda denna digitala signatur för att fastställe om inkommande e-post är legitim.

Enkelt sagt krypterar en privat nyckel rubriken i utgående e-postmeddelanden från en domän. Den offentliga nyckeln publiceras i domänens DNS-poster och mottagande servrar kan använda den nyckeln för att avkoda signaturen. DKIM-verifiering hjälper de mottagande servrarna att bekräfta att e-posten verkligen kommer från din domän och inte från någon som *förfalskar* din domän.

> [!TIP]
>Du kan även välja att inte göra någonting med DKIM för din anpassade domän. Om du inte konfigurerar DKIM för din anpassade domän skapar Microsoft 365 ett privat och offentligt nyckelpar, aktiverar DKIM-signering och konfigurerar sedan standardprincipen för Microsoft 365 för din anpassade domän.

 Den inbyggda DKIM-konfigurationen för Microsoft 365 är tillräcklig täckning för de flesta kunder. Men du bör manuellt konfigurera DKIM för din anpassade domän i följande fall:

- Du har fler än en anpassad domän i Microsoft 365
- Du ska även konfigurera DMARC (**rekommenderas**)
- Du vill ha kontroll över din privata nyckel
- Du vill anpassa dina CNAME-poster
- Du vill konfigurera DKIM-nycklar för e-post som kommer från en domän från tredje part, t. ex. om du använder ett massutskick från tredje part.

## <a name="how-dkim-works-better-than-spf-alone-to-prevent-malicious-spoofing"></a>Hur DKIM fungerar bättre än enbart SPF för att förhindra skadlig förfalskning
<a name="HowDKIMWorks"> </a>

SPF lägger till information till ett meddelandekuvert, men DKIM *krypterar* en signatur i meddelanderubriken. När du vidarebefordrar ett meddelande kan delar av meddelandets kuvert vara rensade av vidarebefordringsservern. Eftersom den digitala signaturen ligger kvar i e-postmeddelandet eftersom den är en del av e-postmeddelandets huvud fungerar DKIM även när ett meddelande har vidarebefordrats enligt följande exempel.

![Diagram som visar ett vidarebefordrat meddelande som skickar DKIM-autentiseringen där SPF-kontrollen misslyckades](../../media/28f93b4c-97e7-4309-acc4-fd0d2e0e3377.jpg)

Om du bara hade publicerat en SPF TXT-post för domänen i det här exemplet skulle mottagarens e-postserver ha markerat e-postmeddelandet som skräppost och genererat ett falskt positivt resultat. **Tillägget av DKIM i det här scenariot minskar *falska positiva* rapporteringar av skräppost.** Eftersom DKIM använder offentlig nyckelkryptering för att autentisera och inte bara IP-adresser anses DKIM vara en mycket starkare autentiseringsmetod än SPF. Vi rekommenderar att du använder både SPF och DKIM, och även DMARC i din distribution.

> [!TIP]
> DKIM använder en privat nyckel för att infoga en krypterad signatur i meddelanderubrikerna. Signeringsdomänen, eller den utgående domänen, infogas som värdet för fältet **d =** i rubriken. Den verifierande domänen, eller mottagarens domän, använder sedan fältet **d=** för att leta upp den offentliga nyckeln från DNS och autentisera meddelandet. Om meddelandet har bekräftats godkänns DKIM-kontrollen.


## <a name="steps-to-manually-upgrade-your-1024-bit-keys-to-2048-bit-dkim-encryption-keys"></a>Uppgradera manuellt dina 1024-bitars nycklar till 2048-bitars DKIM-krypteringsnycklar
<a name="1024to2048DKIM"> </a>

> [!NOTE]
> Microsoft 365 konfigurerar automatiskt DKIM för domäner med *onmicrosoft.com*. Inga steg krävs för att använda DKIM för inledande domännamn (t.ex. litware.*onmicrosoft.com*). Mer information om domäner finns i [Vanliga frågor och svar om domäner](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain).

Eftersom både 1024 och 2048 bitar stöds för DKIM-nycklar visar dessa instruktioner hur du uppgraderar din 1024-bitarsnyckel till 2048 i [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Stegen nedan gäller för två användningsfall: Välj det som passar bäst för konfigurationen.

- När du **redan har konfigurerat DKIM** kan du rotera bitar genom att köra följande kommando:

  ```powershell
  Rotate-DkimSigningConfig -KeySize 2048 -Identity {Guid of the existing Signing Config}
  ```

  **eller**

- För en **ny implementering av DKIM**, kör följande kommando:

  ```powershell
  New-DkimSigningConfig -DomainName <Domain for which config is to be created> -KeySize 2048 -Enabled $true
  ```

Håll dig ansluten till Exchange Online PowerShell för att *verifiera* konfigurationen genom att köra följande kommando:

```powershell
Get-DkimSigningConfig -Identity <Domain for which the configuration was set> | Format-List
```

> [!TIP]
> Den här nya 2048-bitarsnyckeln träder i kraft på RotateOnDate och skickar e-postmeddelanden med 1024-bitarsnyckeln i interimversionen. Efter fyra dagar kan du testa igen med 2048-bitarsnyckeln (det vill säga när rotationen träder i kraft i den andra väljaren).

Om du vill rotera till den andra väljaren är dina alternativ a) att låta Microsoft 365-tjänsten rotera väljaren och uppgradera till 2048 bitar inom de kommande sex månaderna eller b) att efter fyra dagar bekräfta att 2048 bitar används och manuellt rotera den andra väljarknappen med hjälp av lämplig cmdlet ovan.

För detaljerad information om syntax och parametrar, se följande artiklar: [Rotate-DkimSigningConfig](/powershell/module/exchange/rotate-dkimsigningconfig), [New-DkimSigningConfig](/powershell/module/exchange/new-dkimsigningconfig)och [Get-DkimSigningConfig](/powershell/module/exchange/get-dkimsigningconfig).

## <a name="steps-to-manually-set-up-dkim"></a>Steg för att konfigurera DKIM manuellt
<a name="SetUpDKIMO365"> </a>

Om du vill konfigurera DKIM gör du så här:

- [Publicera två CNAME-poster för din anpassade domän i DNS](use-dkim-to-validate-outbound-email.md#Publish2CNAME)
- [Aktivera DKIM-signering för din anpassade domän](use-dkim-to-validate-outbound-email.md#EnableDKIMinO365)

### <a name="publish-two-cname-records-for-your-custom-domain-in-dns"></a>Publicera två CNAME-poster för din anpassade domän i DNS
<a name="Publish2CNAME"> </a>

För varje domän som du vill lägga till en DKIM-signatur för måste du publicera två CNAME-poster.

> [!NOTE]
> Har du inte läst hela artikeln kan du ha missat den här tidsbesparande PowerShell-anslutningsinformationen: [Anslut till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

Kör följande kommandon i Exchange Online PowerShell för att skapa väljararkiv:

```powershell
New-DkimSigningConfig -DomainName <domain> -Enabled $false
Get-DkimSigningConfig -Identity <domain> | Format-List Selector1CNAME, Selector2CNAME
```

Om du har etablerat anpassade domäner utöver den första domänen i Microsoft 365 måste du publicera två CNAME-poster för varje ytterligare domän. Om du har två domäner måste du publicera två ytterligare CNAME-poster och så vidare.

Använd följande format för CNAME-posterna.

> [!IMPORTANT]
> Om du är en av våra GCC High-kunder beräknar vi _domainGuid_ annorlunda! I stället för att leta upp MX-posten för din _initialDomain_ för att beräkna _domainGuid_ beräknar vi det direkt från den anpassade domänen. Om du till exempel har en anpassad domän som ”contoso.com” blir din domainGuid ”contoso-com”. Punkter ersätts med ett streck. Oavsett vilken MX-post som initialDomain pekar på kommer du alltid att använda metoden ovan för att beräkna vilken domainGuid som ska användas i dina CNAME-poster.

```console
Host name:            selector1._domainkey
Points to address or value:    selector1-<domainGUID>._domainkey.<initialDomain>
TTL:                3600

Host name:            selector2._domainkey
Points to address or value:    selector2-<domainGUID>._domainkey.<initialDomain>
TTL:                3600
```

Var:

- För Microsoft 365 är väljarna alltid ”selector1” eller ”selector2”.
- _domainGUID_ är samma som _domainGUID_ i den anpassade MX-posten för din domän som visas före mail.protection.outlook.com. Exempel: i följande MX-post för domänen contoso.com blir din _domainGUID_ contoso-com:

  > contoso.com.  3600  IN  MX   5 contoso-com.mail.protection.outlook.com

- _initialDomain_ är den domän som du använde när du registrerade dig för Microsoft 365. De första domänerna avslutas alltid i onmicrosoft.com. Information om hur du fastställer din första domän finns i [Vanliga frågor och svar om domäner](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain).

Om du till exempel har en första domän med cohovineyardandwinery.onmicrosoft.com, och två egna domäner cohovineyard.com och cohowinery.co, behöver du skapa två CNAME-poster för varje ytterligare domän för att summera fyra CNAME-poster.

```console
Host name:            selector1._domainkey
Points to address or value:    selector1-cohovineyard-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:            selector2._domainkey
Points to address or value:    selector2-cohovineyard-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:            selector1._domainkey
Points to address or value:    selector1-cohowinery-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:            selector2._domainkey
Points to address or value:    selector2-cohowinery-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600
```

> [!NOTE]
> Det är viktigt att skapa den andra posten, men bara en av dem kan vara tillgänglig när du skapar den. I själva verket kan den andra väljarens peka på en adress som inte har skapats än. Vi rekommenderar fortfarande att du skapar den andra CNAME-posten eftersom nyckelroteringen blir smidig.

### <a name="steps-to-enable-dkim-signing-for-your-custom-domain"></a>Steg för att aktivera DKIM-signering för din anpassade domän
<a name="EnableDKIMinO365"> </a>

När du har publicerat CNAME-posterna i DNS är du redo att aktivera DKIM-signering via Microsoft 365. Du kan göra det antingen via administrationscentret för Microsoft 365 eller med hjälp av PowerShell.

#### <a name="to-enable-dkim-signing-for-your-custom-domain-in-the-microsoft-365-defender-portal"></a>Så här aktiverar du DKIM-signering för din anpassade domän i Microsoft 365 Defender-portalen

1. Öppna Microsoft 365 Defender-portalen [med ditt arbets- eller skolkonto](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).

2. Gå till sidan **E-post och samarbete** \> **Principer och regler** \> **Hotprinciper** \> **Regler** avsnitt \> **DKIM**. Om du vill gå direkt till DKIM-sidan använder du <https://security.microsoft.com/dkimv2>.

3. På sidan **DKIM** markerar du domänen genom att klicka på namnet.

4. I den utfällbara menyn med information ändrar du inställningen **Signera meddelanden för den här domänen med DKIM-signaturer** till **Aktiverad** (![Växlingsknapp på](../../media/scc-toggle-on.png))

   Klicka på **Rotera DKIM-nycklar** när du är klar.

5. Upprepa det här steget för varje anpassad domän.

#### <a name="to-enable-dkim-signing-for-your-custom-domain-by-using-powershell"></a>För att aktivera DKIM-signering för din anpassade domän med PowerShell

> [!IMPORTANT]
> :::image type="content" source="../../media/dkim.png" alt-text="Felet &quot;Inga DKIM-nycklar sparade för den här domänen.&quot;":::
> Om du konfigurerar DKIM för första gången och ser felet "Inga DKIM-nycklar har sparats för den här domänen" slutför du kommandot i steg 2 nedan (till exempel `Set-DkimSigningConfig -Identity contoso.com -Enabled $true`) för att se nyckeln.

1. [Ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Använd följande syntax:

   ```powershell
   Set-DkimSigningConfig -Identity <Domain> -Enabled $true
   ```

   \<Domain\> är namnet på den anpassade domän som du vill aktivera DKIM-signering för.

   Det här exemplet aktiverar DKIM-signering för domänen contoso.com:

   ```powershell
   Set-DkimSigningConfig -Identity contoso.com -Enabled $true
   ```

#### <a name="to-confirm-dkim-signing-is-configured-properly-for-microsoft-365"></a>Bekräfta att DKIM-signering är rätt konfigurerad för Microsoft 365

Vänta några minuter innan du följer de här anvisningarna för att kontrollera att du har konfigurerat DKIM. Då får DKIM-informationen om domänen tid att spridas i hela nätverket.

- Skicka ett meddelande från ett konto i din DKIM-aktiverade Microsoft 365-domän till ett annat e-postkonto, till exempel outlook.com eller Hotmail.com.
- Använd inte ett aol.com-konto för testningsändamål. AOL kan hoppa över DKIM för att kontrollera om SPF-kontrollen överförs. Det här annullerar testet.
- Öppna meddelandet och titta på rubriken. Information om hur du visar rubriken för meddelandet beror på vilken meddelandeklient du har. Information om hur du visar meddelanderubriker i Outlook finns i [Visa internetmeddelandehuvud i Outlook](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c).

  Det DKIM-signerade meddelandet innehåller värdnamnet och domänen som du angav när du publicerade CNAME-posterna. Meddelandet ser ut ungefär så här:

  ```console
    From: Example User <example@contoso.com>
    DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
        s=selector1; d=contoso.com; t=1429912795;
        h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
        bh=<body hash>;
        b=<signed field>;
  ```

- Håll utkik efter huvudet Authentication-Results. Även om varje mottagande tjänst använder något annat format för att stämpla inkommande e-post ska resultatet innehålla något som liknar **DKIM=pass** eller **DKIM=OK**.

## <a name="to-configure-dkim-for-more-than-one-custom-domain"></a>Konfigurera DKIM för fler än en anpassad domän
<a name="DKIMMultiDomain"> </a>

Om du senare bestämmer dig för att lägga till en egen domän och vill aktivera DKIM för den nya domänen måste du utföra stegen i den här artikeln för varje domän. Slutför först alla [steg du behöver göra för att konfigurera DKIM manuellt](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365).

## <a name="disabling-the-dkim-signing-policy-for-a-custom-domain"></a>Inaktivera DKIM-signeringsprincipen för en anpassad domän
<a name="DisableDKIMSigningPolicy"> </a>

När du inaktiverar signeringsprincipen inaktiveras inte DKIM fullständigt. Efter en viss tid används standardprincipen automatiskt för din domän i Microsoft 365. Mer information finns i [Standardbeteende för DKIM och Microsoft 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).

### <a name="to-disable-the-dkim-signing-policy-by-using-windows-powershell"></a>Inaktivera DKIM-signeringsprincipen med Windows PowerShell

1. [Ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Kör något av följande kommandon för varje domän som du vill inaktivera DKIM-signering för.

   ```powershell
   $p = Get-DkimSigningConfig -Identity <Domain>
   $p[0] | Set-DkimSigningConfig -Enabled $false
   ```

   Till exempel:

   ```powershell
   $p = Get-DkimSigningConfig -Identity contoso.com
   $p[0] | Set-DkimSigningConfig -Enabled $false
   ```

   Eller

   ```powershell
   Set-DkimSigningConfig -Identity $p[<number>].Identity -Enabled $false
   ```

   Där _number_ är indexet för principen. Till exempel:

   ```powershell
   Set-DkimSigningConfig -Identity $p[0].Identity -Enabled $false
   ```

## <a name="default-behavior-for-dkim-and-microsoft-365"></a>Standardbeteende för DKIM och Microsoft 365
<a name="DefaultDKIMbehavior"> </a>

Om du inte aktiverar DKIM skapar Microsoft 365 automatiskt en offentlig 1024-bitars DKIM-nyckel för din standarddomän och den tillhörande privata nyckeln som vi lagrar internt i vårt datacenter. Som standard använder Microsoft 365 en standardkonfiguration för signering för domäner som inte har någon princip. Det innebär att om du inte konfigurerar DKIM själv kommer Microsoft 365 att använda sin standardprincip och de nycklar som skapas för att aktivera DKIM för din domän.

Om du inaktiverar DKIM-signering efter att du har aktiverat det kommer Microsoft 365 efter en viss tid att automatiskt använda standardprincipen för din domän.

I följande exempel antar vi att DKIM för fabrikam.com har aktiverats av Microsoft 365, inte av domänens administratör. Det innebär att de nödvändiga CNAME-posterna inte finns i DNS. DKIM-signaturer för e-post från den här domänen ser ut ungefär så här:

```console
From: Second Example <second.example@fabrikam.com>
DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
    s=selector1-fabrikam-com; d=contoso.onmicrosoft.com; t=1429912795;
    h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
    bh=<body hash>;
    b=<signed field>;
```

I det här exemplet innehåller värddatornamnet och domänen värdena som CNAME pekar på om DKIM-signering för fabrikam.com har aktiverats av domänadministratören. Till slut kommer alla meddelanden som skickats från Microsoft 365 att DKIM-signeras. Om du aktiverar DKIM själv blir domänen samma som domänen i Från: adress, i det här fallet fabrikam.com. Om du inte gör det justeras det inte. I stället används din organisations första domän. Information om hur du fastställer din första domän finns i [Vanliga frågor och svar om domäner](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain).

## <a name="set-up-dkim-so-that-a-third-party-service-can-send-or-spoof-email-on-behalf-of-your-custom-domain"></a>Konfigurera DKIM så att en tjänst från tredje part kan skicka, eller förfalska, e-postmeddelanden för din anpassade domän.
<a name="SetUp3rdPartyspoof"> </a>

Vissa leverantör av e-posttjänster, eller leverantörer av programvara som tjänst, kan konfigurera DKIM-nycklar för e-post som kommer från tjänsten. Det kräver samordning mellan dig och tredje part för att du ska kunna skapa de DNS-poster som krävs. Vissa servrar från tredje part kan ha egna CNAME-poster med olika väljare. Inga organisationer fungerar på exakt samma sätt. I stället beror processen helt på organisationen.

Ett exempelmeddelande som visar ett korrekt konfigurerat DKIM för contoso.com och bulkemailprovider.com kan se ut så här:

```console
Return-Path: <communication@bulkemailprovider.com>
 From: <sender@contoso.com>
 DKIM-Signature: s=s1024; d=contoso.com
 Subject: Here is a message from Bulk Email Provider's infrastructure, but with a DKIM signature authorized by contoso.com
```

I det här exemplet för att uppnå följande resultat:

1. E-postleverantören för massutskick gav Contoso en offentlig DKIM-nyckel.

2. Contoso offentliggjorde nyckeln DKIM till dess DNS-post.

3. När du skickar e-post signerar e-postleverantören för massutskick nyckeln med motsvarande privata nyckel. Det gör att e-postleverantören för massutskicket bifogar DKIM-signaturen i meddelandehuvudet.

4. Mottagande e-postsystem utför en DKIM-kontroll genom att autentisera värdet i DKIM-signaturen d=\<domain\> mot domänen i meddelandet Från: (5322.From) för meddelandet. I det här exemplet överensstämmer värdena:

   > sender@**contoso.com**

   > d=**contoso.com**

## <a name="identify-domains-that-do-not-send-email"></a>Identifiera domäner som inte skickar e-post

Organisationer ska uttryckligen ange om en domän inte skickar e-post genom att ange `v=DKIM1; p=` i DKIM-posten för dessa domäner. Detta informerar om att ta emot e-postservrar att det inte finns några giltiga offentliga nycklar för domänen och att e-postmeddelanden som påstår sig komma från den domänen bör avvisas. Du bör göra detta för varje domän och under domän med en jokertecken DKIM.

Till exempel skulle DKIM-posten se ut så här:

```console
*._domainkey.SubDomainThatShouldntSendMail.contoso.com. TXT "v=DKIM1; p="
```

## <a name="next-steps-after-you-set-up-dkim-for-microsoft-365"></a>Nästa steg: När du har konfigurerat DKIM för Microsoft 365
<a name="DKIMNextSteps"> </a>

Även om DKIM har utformats för att förhindra förfalskningar fungerar DKIM bättre med SPF och DMARC. När du har konfigurerat DKIM kan du konfigurera SPF om du inte redan har gjort det. En introduktion till SPF finns i [Konfigurera SPF i Microsoft 365 för att förhindra förfalskning](set-up-spf-in-office-365-to-help-prevent-spoofing.md), där du även kan konfigurera det snabbt. För att få en djupare förståelse av hur Microsoft 365 använder SPF, eller om du vill felsöka eller göra icke-standarddistributioner (t.ex. hybriddistributioner), kan du börja med att läsa artikeln om [hur Microsoft 365 använder SPF (Sender Policy Framework) för att förhindra förfalskning](how-office-365-uses-spf-to-prevent-spoofing.md). Därefter läser du [Använda DMARC för att validera e-post](use-dmarc-to-validate-email.md). [Meddelandehuvuden för antiskräppost](anti-spam-message-headers.md) innehåller syntaxen och rubrikerna som används i Microsoft 365 för DKIM-kontroller.

## <a name="more-information"></a>Mer information

Nyckelrotation via PowerShell [Rotate-DkimSigningConfig](/powershell/module/exchange/rotate-dkimsigningconfig)
