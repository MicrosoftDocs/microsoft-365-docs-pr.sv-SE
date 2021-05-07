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
ms.openlocfilehash: e7e50ea399cd694f512e0538de3f7e67c63ee0e3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162033"
---
# <a name="technical-reference-details-about-encryption"></a>Teknisk referensinformation om kryptering

I den här artikeln finns mer information om certifikat, tekniker och TLS-chiffersviter som används [för kryptering i Office 365.](encryption.md) I den här artikeln finns också information om planerade utfasningar.
  
- Om du letar efter översiktlig information kan du [gå till Kryptering i Office 365](encryption.md).
- Om du letar efter konfigurationsinformation kan du gå [till Konfigurera kryptering i Office 365 Enterprise](set-up-encryption.md).
- Mer information om chiffersviter som stöds av specifika versioner av Windows finns i Chiffersviterna i [TLS/SSL (Schannel SSP).](/windows/desktop/SecAuthN/cipher-suites-in-schannel)

## <a name="microsoft-office-365-certificate-ownership-and-management"></a>Microsoft Office 365 ägarskap och hantering av certifikat

Du behöver inte köpa eller underhålla certifikat för Office 365. I stället Office 365 egna certifikat.
  
## <a name="current-encryption-standards-and-planned-deprecations"></a>Aktuella krypteringsstandarder och planerad utfasning

För att tillhandahålla kryptering i toppklass granskar Office 365 regelbundet krypteringsstandarder som stöds. Ibland är gamla standarder föråldrade allt eftersom de blir inaktuella och mindre säkra. I den här artikeln beskrivs för närvarande chiffersviter och andra standarder och information om planerade utfasningar.

## <a name="fips-compliance-for-office-365"></a>FIPS-efterlevnad för Office 365

Alla chiffersviter som stöds Office 365 använda algoritmer som är godtagbara under FIPS 140-2. Office 365 ärver FIPS-valideringar från Windows (via Schannel). Mer information om Schannel finns [i Chiffersviter i TLS/SSL (Schannel SSP).](/windows/desktop/SecAuthN/cipher-suites-in-schannel)
  
## <a name="versions-of-tls-supported-by-office-365"></a>Versioner av TLS som stöds av Office 365

TLS, och SSL som kom före TLS, är kryptografiska protokoll som skyddar kommunikationen över ett nätverk genom att använda säkerhetscertifikat för att kryptera en anslutning mellan datorer. Office 365 TLS version 1.2 (TLS 1.2).

TLS version 1.3 (TLS 1.3) stöds för närvarande inte.
  
## <a name="support-for-tls-10-and-11-deprecation"></a>Stöd för utfasning av TLS 1.0 och 1.1

Office 365 slutade stödja TLS 1.0 och 1.1 den 31 oktober 2018. Vi har inaktiverat TLS 1.0 och 1.1 i GCC Hög- och DoD-miljöer. Vi började inaktivera TLS 1.0 och 1.1 för globala miljöer och GCC-miljöer med början den 15 oktober 2020 och fortsätter med distribution under de kommande veckorna och månaderna.

För att upprätthålla en säker anslutning Office 365 och Microsoft 365 tjänster använder alla kombinationer av klientserver och webbläsarserver TLS 1.2 och moderna chiffersviter. Du kan behöva uppdatera vissa kombinationer av klient- och webbläsarservrar. Mer information om hur ändringen påverkar dig finns i Förbereda den obligatoriska användningen av [TLS 1.2 i Office 365.](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)
  
## <a name="deprecating-support-for-3des"></a>Inaktuellt stöd för 3DES

Sedan den 31 oktober 2018 Office 365 inte längre stöd för användning av 3DES-chiffersviter för kommunikation till Office 365. Mer specifikt kan Office 365 inte längre stöd för TLS_RSA_WITH_3DES_EDE_CBC_SHA-chiffersvit. Sedan den 28 februari 2019 har chiffersviten inaktiverats i Office 365. Klienter och servrar som kommunicerar Office 365 måste stödja ett eller flera av de chiffer som stöds. En lista över de chiffer som stöds finns i [TLS-chiffersviter som stöds av Office 365.](#tls-cipher-suites-supported-by-office-365)
  
## <a name="deprecating-sha-1-certificate-support-in-office-365"></a>Inaktuellt stöd för SHA-1-certifikat i Office 365

Sedan juni 2016 Office 365 inte längre ett SHA-1-certifikat för utgående eller inkommande anslutningar. Använd SHA-2 (Secure Hash Algorithm 2) eller en starkare hash-algoritm i certifikatskedjan.
  
## <a name="tls-cipher-suites-supported-by-office-365"></a>TLS-chiffersviter som stöds av Office 365

TLS använder *chiffersviter*, samlingar av krypteringsalgoritmer för att upprätta säkra anslutningar. Office 365 stöd för chiffersviterna som anges i följande tabell. Tabellen visar chiffersviterna i ordningen, med den starkaste chiffersviten först.

Office 365 på en anslutningsbegäran genom att först försöka ansluta med hjälp av det säkraste chiffersviten. Om anslutningen inte fungerar försöker Office 365 den andra säkraste chiffersviten i listan och så vidare. Tjänsten fortsätter ned i listan tills anslutningen accepteras. När Office 365 begär en anslutning väljer den mottagande tjänsten på samma sätt om TLS ska användas och vilket chiffersvit som ska användas.

> [!IMPORTANT]
> Tänk på att TLS-versioner tar bort och att inaktuella versioner inte bör *användas* där nyare versioner är tillgängliga. TLS 1.3 stöds för närvarande inte. Om dina äldre tjänster inte kräver TLS 1.0 eller 1.1 bör du inaktivera dem.

| Chiffersvit | Algoritm/hållfasthet för nyckelutbyte | Forward Forward Forwardy | Chiffer/hållfasthet | Autentiseringsalgoritm |
|:-----|:-----|:-----|:-----|:-----|
|TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384 <br/>     |ECDH/192 <br/>|Ja <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256 <br/>     |ECDH/128 <br/>|Ja <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384 <br/>     |ECDH/192 <br/>|Ja <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256 <br/>     |ECDH/128 <br/>|Ja <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA <br/>        |ECDH/192 <br/>|Ja <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA <br/>        |ECDH/128 <br/>|Ja <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_RSA_WITH_AES_256_GCM_SHA384 <br/>           |RSA/112 <br/> |Nej <br/> |AES/256 <br/>|RSA/112 <br/> |
|TLS_RSA_WITH_AES_128_GCM_SHA256 <br/>           |RSA/112 <br/> |Nej <br/> |AES/256 <br/>|RSA/112 <br/> |

Dessa chiffersviter stöder TLS 1.0- och 1.1-protokoll till deras utfasningsdatum. För GCC hög- och doD-miljöer var utfasningen den 15 januari 2020 samt för globala miljöer och GCC miljöer det datumet var den 15 oktober 2020.

| Protokoll | Namn på chiffersvit | Algoritm/hållfasthet för nyckelutbyte | Forward Forward Forwardy-support | Autentiseringsalgoritm/hållfasthet | Chiffer/Hållfasthet |
|:-----|:-----|:-----|:-----|:-----|:-----|
|TLS 1.0, 1.1, 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA  <br/> |ECDH/192  <br/> |Ja  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA  <br/> |ECDH/128  <br/> |Ja  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA        <br/> |RSA/112  <br/>  |Nej  <br/>  |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA        <br/> |RSA/112  <br/>  |Nej  <br/>  |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA256     <br/> |RSA/112  <br/>  |Nej   <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA256     <br/> |RSA/112  <br/>  |Nej   <br/> |RSA/112  <br/> |AES/256  <br/> |

## <a name="related-articles"></a>Relaterade artiklar

[TLS-chiffersviter i Windows 10 v1903](/windows/win32/secauthn/tls-cipher-suites-in-windows-10-v1903)

[Kryptering i Office 365](encryption.md)
  
[Konfigurera kryptering i Office 365 Enterprise](set-up-encryption.md)
  
[Schannel-implementering av TLS 1.0 Windows säkerhetsstatusuppdateringen: 24 november 2015](https://support.microsoft.com/kb/3117336)
  
[Förbättringar av TLS/SSL-kryptografik (Windows IT Center)](/previous-versions/windows/it-pro/windows-vista/cc766285(v=ws.10))
  
[Förbereda för TLS 1.2 i Office 365 och Office 365 GCC](/office365/troubleshoot/security/prepare-tls-1.2-in-office-365)