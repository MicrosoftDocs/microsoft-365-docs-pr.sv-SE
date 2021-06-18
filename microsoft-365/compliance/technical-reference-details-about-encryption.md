---
title: Teknisk referensinformation om kryptering
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
- Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 862cbe93-4268-4ef9-ba79-277545ecf221
description: Läs mer om de olika certifikat, tekniker och TLS-chiffersviter (Transport Layer Security) som används för kryptering i Office 365 och Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2b2257338ab214ccdaa08f1aa8f322aad98d7c8b
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007555"
---
# <a name="technical-reference-details-about-encryption"></a>Teknisk referensinformation om kryptering

I den här artikeln finns mer information om certifikat, tekniker och TLS-chiffersviter som används för [kryptering i Office 365.](encryption.md) I den här artikeln finns också information om planerade utfasningar.
  
- Mer information finns i Kryptering i [Office 365.](encryption.md)
- Om du letar efter konfigurationsinformation kan du gå [till Konfigurera kryptering i Office 365 Enterprise.](set-up-encryption.md)
- Mer information om chiffersviter som stöds av specifika versioner av Windows finns i Chiffersviter i [TLS/SSL (Schannel SSP).](/windows/desktop/SecAuthN/cipher-suites-in-schannel)

## <a name="microsoft-office-365-certificate-ownership-and-management"></a>Microsoft Office 365-certifikatägarskap och -hantering

Du behöver inte köpa eller underhålla certifikat för Office 365. I stället använder Office 365 egna certifikat.
  
## <a name="current-encryption-standards-and-planned-deprecations"></a>Aktuella krypteringsstandarder och planerad utfasning

För att tillhandahålla kryptering i toppklass granskar Office 365 regelbundet krypteringsstandarder som stöds. Ibland är gamla standarder föråldrade allt eftersom de blir inaktuella och mindre säkra. I den här artikeln beskrivs för närvarande chiffersviter och andra standarder och information om planerade utfasningar.

## <a name="fips-compliance-for-office-365"></a>FIPS-efterlevnad för Office 365

Alla chiffersviter som stöds av Office 365 använder algoritmer som är godtagbara under FIPS 140-2. Office 365 ärver FIPS-valideringar från Windows (via Schannel). Mer information om Schannel finns [i Chiffersviter i TLS/SSL (Schannel SSP).](/windows/desktop/SecAuthN/cipher-suites-in-schannel)
  
## <a name="versions-of-tls-supported-by-office-365"></a>Versioner av TLS som stöds av Office 365

TLS, och SSL som kom före TLS, är kryptografiska protokoll som skyddar kommunikationen över ett nätverk genom att använda säkerhetscertifikat för att kryptera en anslutning mellan datorer. Office 365 har stöd för TLS version 1.2 (TLS 1.2).

TLS version 1.3 (TLS 1.3) stöds för närvarande inte.

> [!IMPORTANT]
> Tänk på att TLS-versioner tar bort och att inaktuella versioner inte bör *användas* där nyare versioner är tillgängliga. Om dina äldre tjänster inte kräver TLS 1.0 eller 1.1 bör du inaktivera dem.
  
## <a name="support-for-tls-10-and-11-deprecation"></a>Stöd för utfasning av TLS 1.0 och 1.1

Office 365 slutade stödja TLS 1.0 och 1.1 den 31 oktober 2018. Vi har inaktiverat TLS 1.0 och 1.1 i GCC High- och DoD-miljöer. Vi började inaktivera TLS 1.0 och 1.1 för globala miljöer och GCC-miljöer med början den 15 oktober 2020 och fortsätter med distribution under de kommande veckorna och månaderna.

För att upprätthålla en säker anslutning till Office 365- och Microsoft 365-tjänster använder alla kombinationer av klient-server- och webbläsarserverer TLS 1.2 och moderna chiffersviter. Du kan behöva uppdatera vissa kombinationer av klient- och webbläsarservrar. Mer information om hur den här ändringen påverkar dig finns i Förbereda den obligatoriska användningen av [TLS 1.2 i Office 365.](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)
  
## <a name="deprecating-support-for-3des"></a>Inaktuellt stöd för 3DES

Sedan den 31 oktober 2018 stöder Office 365 inte längre användning av 3DES-chiffersviter för kommunikation till Office 365. Mer specifikt har Office 365 inte längre stöd för TLS_RSA_WITH_3DES_EDE_CBC_SHA-chiffersvit. Sedan den 28 februari 2019 har chiffersviten inaktiverats i Office 365. Klienter och servrar som kommunicerar med Office 365 måste ha stöd för ett eller flera av de chiffer som stöds. En lista över de chiffer som stöds finns i [TLS-chiffersviter som stöds av Office 365.](#tls-cipher-suites-supported-by-office-365)
  
## <a name="deprecating-sha-1-certificate-support-in-office-365"></a>Inaktuellt stöd för SHA-1-certifikat i Office 365

Sedan juni 2016 accepterar Office 365 inte längre ett SHA-1-certifikat för utgående eller inkommande anslutningar. Använd SHA-2 (Secure Hash Algorithm 2) eller en starkare hash-algoritm i certifikatskedjan.
  
## <a name="tls-cipher-suites-supported-by-office-365"></a>TLS-chiffersviter som stöds av Office 365

TLS använder *chiffersviter*, samlingar av krypteringsalgoritmer för att upprätta säkra anslutningar. Office 365 har stöd för chiffersviterna som anges i följande tabell. Tabellen visar chiffersviterna i ordningen, med den starkaste chiffersviten först.

Office 365 svarar på en anslutningsbegäran genom att först försöka ansluta med hjälp av det säkraste chiffersviten. Om anslutningen inte fungerar försöker Office 365 den näst säkraste chiffersviten i listan och så vidare. Tjänsten fortsätter ned i listan tills anslutningen accepteras. På samma sätt väljer den mottagande tjänsten om TLS ska användas och vilket chifferpaket som ska användas när Office 365 begär en anslutning.

| Namn på chiffersvit | Algoritm/hållfasthet för nyckelutbyte | Vidarebefordran av en 2010-dag | Chiffer/hållfasthet | Autentiseringsalgoritm/-hållfasthet |
|:-----|:-----|:-----|:-----|:-----|
| TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384  <br/> | ECDH/192  <br/> | Ja  <br/> | AES/256  <br/> | RSA/112  <br/> |
| TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256  <br/> | ECDH/128  <br/> | Ja  <br/> | AES/128  <br/> | RSA/112  <br/> |
| TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384  <br/> | ECDH/192  <br/> | Ja  <br/> | AES/256  <br/> | RSA/112  <br/> |
| TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256  <br/> | ECDH/128  <br/> | Ja  <br/> | AES/128  <br/> | RSA/112  <br/> |
| TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA     <br/> | ECDH/192  <br/> | Ja  <br/> | AES/256  <br/> | RSA/112  <br/> |
| TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA     <br/> | ECDH/128  <br/> | Ja  <br/> | AES/128  <br/> | RSA/112  <br/> |
| TLS_RSA_WITH_AES_256_GCM_SHA384        <br/> | RSA/112   <br/> | Nej   <br/> | AES/256  <br/> | RSA/112  <br/> |
| TLS_RSA_WITH_AES_128_GCM_SHA256        <br/> | RSA/112   <br/> | Nej   <br/> | AES/256  <br/> | RSA/112  <br/> |

Följande chiffersviter stöder TLS 1.0- och 1.1-protokoll till utfasningens datum. För GCC High- och DoD-miljöer var utfasningen den 15 januari 2020. För globala miljöer och GCC-miljöer var datumet den 15 oktober 2020.

| Protokoll | Namn på chiffersvit | Algoritm/hållfasthet för nyckelutbyte | Vidarebefordran av en 2010-dag | Chiffer/hållfasthet | Autentiseringsalgoritm/-hållfasthet | 
|:-----|:-----|:-----|:-----|:-----|:-----|
| TLS 1.0, 1.1, 1.2  <br/> | TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA  <br/> | ECDH/192  <br/> | Ja  <br/> | AES/256  <br/> | RSA/112  <br/> |
| TLS 1.0, 1.1, 1.2  <br/> | TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA  <br/> | ECDH/128  <br/> | Ja  <br/> | AES/128  <br/> | RSA/112  <br/> |
| TLS 1.0, 1.1, 1.2  <br/> | TLS_RSA_WITH_AES_256_CBC_SHA        <br/> | RSA/112   <br/> | Nej   <br/> | AES/256  <br/> | RSA/112  <br/> |
| TLS 1.0, 1.1, 1.2  <br/> | TLS_RSA_WITH_AES_128_CBC_SHA        <br/> | RSA/112   <br/> | Nej   <br/> | AES/128  <br/> | RSA/112  <br/> |
| TLS 1.0, 1.1, 1.2  <br/> | TLS_RSA_WITH_AES_256_CBC_SHA256     <br/> | RSA/112   <br/> | Nej   <br/> | AES/256  <br/> | RSA/112  <br/> |
| TLS 1.0, 1.1, 1.2  <br/> | TLS_RSA_WITH_AES_128_CBC_SHA256     <br/> | RSA/112   <br/> | Nej   <br/> | AES/256  <br/> | RSA/112  <br/> |

Vissa Office 365-produkter (inklusive Microsoft Teams) använder [Azure Front Door](/azure/frontdoor/front-door-overview) för att avsluta TLS-anslutningar och dirigera nätverkstrafik effektivt. Minst ett av chiffersviterna som stöds av Azure Front Door via [TLS 1.2](/azure/frontdoor/front-door-faq#what-are-the-current-cipher-suites-supported-by-azure-front-door-) måste vara aktiverade för att anslutningen till dessa produkter ska lyckas. För Windows 10 och högre rekommenderar vi att du aktiverar en eller båda av ECDHE-chiffersviterna för bättre säkerhet. Windows 7, 8 och 8.1 är inte kompatibla med Azure Front Doors ECDHE-chiffersviter och DHE-chiffersviterna har tillhandahållits för kompatibilitet med dessa operativsystem.

## <a name="related-articles"></a>Relaterade artiklar

[TLS-chiffersviter i Windows 10 v1903](/windows/win32/secauthn/tls-cipher-suites-in-windows-10-v1903)

[Kryptering i Office 365](encryption.md)
  
[Konfigurera kryptering i Office 365 Enterprise](set-up-encryption.md)
  
[Schannel-implementering av TLS 1.0 i Windows säkerhetsstatusuppdatering: 24 november 2015](https://support.microsoft.com/kb/3117336)
  
[Förbättringar av TLS/SSL-kryptografik (Windows IT Center)](/previous-versions/windows/it-pro/windows-vista/cc766285(v=ws.10))
  
[Förbereda för TLS 1.2 i Office 365 och Office 365 GCC](/office365/troubleshoot/security/prepare-tls-1.2-in-office-365)

[Vilka aktuella chiffersviter stöds av Azure Front Door?](/azure/frontdoor/front-door-faq#what-are-the-current-cipher-suites-supported-by-azure-front-door-)
