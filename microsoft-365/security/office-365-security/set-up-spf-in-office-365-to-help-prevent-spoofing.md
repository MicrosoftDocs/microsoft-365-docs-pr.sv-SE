---
title: Konfigurera SPF för att förhindra förfalskning
f1.keywords:
- CSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/21/2019
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 71373291-83d2-466f-86ea-fc61493743a6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Lär dig hur du uppdaterar en DNS-post (Domain Name Service) för att använda en SPF-post (Sender Policy Framework) med din anpassade domän i Office 365.
ms.openlocfilehash: 536f727ee71db70490259179ff8e47009c547f89
ms.sourcegitcommit: 64262f6f42dcce6a4608b2e3c7ca6190b7009093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/19/2021
ms.locfileid: "49905229"
---
# <a name="set-up-spf-to-help-prevent-spoofing"></a>Konfigurera SPF för att förhindra förfalskning

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

- [Förutsättningar](#prerequisites)
- [Skapa eller uppdatera din SPF TXT-post](#create-or-update-your-spf-txt-record)   
  - [Hur hanterar man underdomäner?](#how-to-handle-subdomains)
- [Vad gör SPF-e-postautentisering egentligen?](#what-does-spf-email-authentication-actually-do)   
   - [Felsökning av SPF](#troubleshooting-spf)
- [Mer information om SPF](#more-information-about-spf)

Den här artikeln beskriver hur du uppdaterar en DNS-post (Domain Name Service) så att du kan använda e-postautentisering av Sender Policy Framework (SPF) med din anpassade domän i Office 365.

Med SPF kan du validera utgående e-post som skickas från din anpassade domän. Det är ett första steg i att ställa in andra rekommenderade e-postautentiseringsmetoder DMARC och DKIM (ytterligare två e-postautentiseringsmetoder som stöds i Office 365).

## <a name="prerequisites"></a>Förutsättningar

> [!IMPORTANT]
> Om du är **en småföretag** eller inte känner till IP-adresser eller DNS-konfiguration, ring din internetdomänregistrator (t.ex. GoDaddy, Bluehost, web.com) för att be om hjälp med DNS-konfiguration av SPF (och alla andra e-postautentiseringsmetoder). *Även*, om du inte har köpt eller inte använder en anpassad URL (med andra ord webbadressen som du och dina kunder bläddrar för att nå Office 365 slutar på **onmicrosoft.com**) har SPF ställts in för dig i Office 365 service. Inga ytterligare steg krävs i så fall. Tack för att du läser.

Innan du skapar eller uppdaterar SPF TXT-posten för Office 365 i extern DNS måste du samla in information som behövs för att göra posten. Avancerade exempel och en mer detaljerad diskussion om SPF-syntax som stöds finns i [Så här fungerar SPF för att förhindra förfalskning och nätfiske i Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks).

Samla in följande information:

- Aktuell SPF TXT-post för din anpassade domän, om en finns. Instruktioner finns i [Samla den information du behöver för att skapa DNS-poster i Office 365](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/information-for-dns-records).

- Gå till din eller dina meddelandeserver och ta reda på de externa IP-adresserna (behövs från alla lokala meddelandeservrar). Till exempel: **131.107.2.200**.

- Domännamn som ska användas för alla domäner från tredje part som du måste ta med i din SPF TXT-post. Vissa e-postleverantörer som gör massutskick har konfigurerat underdomäner för sina kunder. Företaget MailChimp har till exempel konfigurerat **servers.mcsv.net**.

- Fastställ vilken regelanvändning som du vill använda för din SPF TXT-post. **Alla**-regeln rekommenderas. Detaljerad information om andra syntaxalternativ finns i [SPF TXT-postsyntax för Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFSyntaxO365).

> [!IMPORTANT]
> För att kunna använda en egen domän kräver Office 365 att du lägger till en SPF TXT-post (Sender Policy Framework) i din DNS-post för att förhindra förfalskning.

## <a name="create-or-update-your-spf-txt-record"></a>Skapa eller uppdatera din SPF TXT-post

1. Kom ihåg att bekanta dig med SFP-syntaxen i följande tabell.

   ****

   |Element|Om du använder...|Vanligt för kunder?|Lägg till detta...|
   |---|---|---|---|
   |1|Ett e-postsystem (obligatoriskt)|Vanligt. SPF-poster som startar med det här värdet.|`v=spf1`|
   |2|Exchange Online|Vanligt|`include:spf.protection.outlook.com`|
   |3|Endast dedikerad Exchange Online|Inte vanligt|`ip4:23.103.224.0/19` <br> `ip4:206.191.224.0/19` <br> `ip4:40.103.0.0/16` <br> `include:spf.protection.outlook.com`|
   |4|Office 365 Germany, endast Microsoft Cloud Germany|Inte vanligt|`include:spf.protection.outlook.de`|
   |5|E-postsystem från tredje part|Inte vanligt|`include:<domain_name>` <p> Där \<domain_name\> domännamnet är av tredje parts e-postsystem.|
   |6|Lokala e-postsystem. Till exempel Exchange Online Protection plus ett annat e-postsystem.|Inte vanligt|Använd något av följande för varje extra e-postsystem: <p> `ip4:<IP_address>` <br> `ip6:<IP_address>` <br> `include:<domain_name>` <p> \<IP_address\> och \<domain_name\> motsvarar IP-adressen och domänen för det andra e-postsystemet som skickar e-post på din domän.|
   |7|Ett e-postsystem (obligatoriskt)|Vanligt. Alla SPF TXT-poster som slutar med det här värdet.|`<enforcement rule>` <p> Det här kan vara ett av flera värden. Vi rekommenderar värdet `-all`.|
   |

2. Om du inte redan har gjort det, skapa din SPF TXT-post genom att använda syntaxen från tabellen.

   Om du till exempel bara använder Office 365 som värd, det vill säga att du inte har någon lokal e-postserver, skulle din SPF TXT-post innehålla raderna 1, 2 och 7 och se ut så här:

   ```text
   v=spf1 include:spf.protection.outlook.com -all
   ```

   Det här är den vanligaste SPF TXT-posten. Den här posten fungerar för i stort sett alla, oavsett om ditt Microsoft-datacenter är i USA eller i Europa (inklusive Tyskland) eller på någon annan plats.

   Men om du har köpt Office 365 Germany, som ingår i Microsoft Cloud Germany, bör du använda instruktionen include från rad 4 i stället för rad 2. Om du till exempel bara använder Office 365 Germany som värd, det vill säga att du inte har några lokala e-postservrar, skulle din SPF TXT-post innehålla raderna 1, 4 och 7 och se ut så här:

   ```text
   v=spf1 include:spf.protection.outlook.de -all
   ```

   Om du redan har distribuerats i Office 365 och har konfigurerat dina SPF TXT-poster för din anpassade domän och migrerar till Office 365 Germany måste du uppdatera din SPF TXT-post. Det gör du genom att ändra `include:spf.protection.outlook.com` till `include:spf.protection.outlook.de`.

3. När du har skapat din SPF TXT-post måste du uppdatera posten i DNS. Du kan bara ha en SPF TXT-post för en domän. Om det redan finns en SPF TXT-post ska du inte lägga till en ny post utan i stället uppdatera den befintliga posten. Gå till [Skapa DNS-poster för Office 365](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) och klicka på länken för din DNS-värd.

4. Testa din SPF TXT-post.

## <a name="how-to-handle-subdomains"></a>Hur hanterar man underdomäner?

Det är viktigt att notera att *du måste skapa en separat post för varje underdomän eftersom underdomäner inte ärver SPF-posten för deras toppnivå domän*.

En ytterligare wildcard SPF-post (`*.`) krävs för varje domän och underdomän för att hindra angripare från att skicka e-post som påstår sig vara från icke-existerande domäner. Till exempel:

```text
*.subdomain.contoso.com. IN TXT "v=spf1 -all"
```

## <a name="troubleshooting-spf"></a>Felsökning av SPF

Har du problem med din SPF TXT-post? Läs [Felsökning: Metodtips för SPF i Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot).


## <a name="what-does-spf-email-authentication-actually-do"></a>Vad gör SPF-e-postautentisering egentligen?

SPF identifierar vilka e-postservrar som får skicka e-post åt dig. SPF, tillsammans med DKIM, DMARC och andra tekniker som stöds av Office 365, bidrar till att förhindra förfalskning och nätfiske. SPF läggs till som en TXT-post som används av DNS för att identifiera vilka e-postservrar som kan skicka e-post åt dig i din egen domän. Mottagande e-postsystem kontrollerar SPF TXT-posten för att avgöra om ett meddelande från din anpassade domän kommer från en auktoriserad meddelandeserver.

Anta till exempel att din anpassade domän contoso.com använder Office 365. Du lägger till en SPF TXT-post som innehåller en lista med de Office 365-meddelandeservrar som är legitima e-postservrar för din domän. När den mottagande meddelandeservern får ett meddelande från joe@contoso.com letar servern upp SPF TXT-posten för contoso.com och tar reda på om meddelandet är giltigt. Om den mottagande servern upptäcker att meddelandet kommer från en annan server än de Office 365-meddelandeservrar som finns i listan i SPF-posten, kan den välja att avvisa meddelandet som skräppost.

Och om din anpassade domän inte har någon SPF TXT-post kan vissa mottagande servrar avvisa meddelandet direkt. Det beror på att den mottagande servern inte kan verifiera att meddelandet kommer från en auktoriserad meddelandeserver.

Om du har konfigurerat e-post för Office 365 så har du redan lagt till Microsofts meddelandeservrar i DNS som en SPF TXT-post. Det finns dock fall då du kan behöva uppdatera SPF TXT-posten i DNS. Till exempel:

- Tidigare var du tvungen att lägga till en annan SPF TXT-post i din anpassade domän om du använde SharePoint Online. Det behöver du inte göra längre. Den här ändringen kan minska risken för att SharePoint Online-meddelanden hamnar i skräppostmappen. Uppdatera din SPF TXT-post om du når gränsen på 10 sökningar och får meddelanden av typen ”gränsen för antal sökningar har överskridits” och ”för många hopp”.

- Om du har en hybridmiljö med Office 365 och Exchange lokalt.

- Du tänker konfigurera DKIM och DMARC (rekommenderas).

## <a name="more-information-about-spf"></a>Mer information om SPF

Avancerade exempel och en mer detaljerad diskussion om SPF-syntax som stöds, förfalskning, felsökning och hur Office 365 stöder SPF finns i [Så här fungerar SPF för att förhindra förfalskning och nätfiske i Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks).

## <a name="links-to-configure-dkim-and-dmarc"></a>Länkar för att konfigurera DKIM och DMARC

 SPF har utformats för att hjälpa till att förhindra förfalskning men det finns förfalskningsmetoder som SPF inte skyddar mot. För att skydda mot dessa ska du, efter att ha konfigurerat SPF, även konfigurera DKIM och DMARC för Office 365.

[DKIM](https://docs.microsoft.com/microsoft-365/security/office-365-security/use-dkim-to-validate-outbound-email?view=o365-worldwide) e-postautentiseringens mål är att bevisa att innehållet i e-postmeddelandet inte har manipulerats.

[DMARC](https://docs.microsoft.com/microsoft-365/security/office-365-security/use-dmarc-to-validate-email?view=o365-worldwide) E-postautentiseringens mål är att se till att SPF- och DKIM-information matchar Från-adressen.