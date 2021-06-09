---
title: Kryptering i Microsoft-molnet
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-security-compliance
- Strat_O365_Enterprise
description: I den här artikeln kan du läsa en översikt över de olika krypteringsformulären som används för att skydda kunddata i Microsoft-molnet.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0d05c904fc70d02d8694b8f2d3b451fd1d51dc91
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841300"
---
# <a name="encryption-in-the-microsoft-cloud"></a>Kryptering i Microsoft-molnet

Kunddata inom Microsofts företagmolntjänster skyddas av flera tekniker och processer, inklusive olika typer av kryptering. (Kunddata i det här dokumentet omfattar Exchange Online postlådeinnehåll, brödtext i e-post, kalenderposter och innehållet i e-postbilagor och, om tillämpligt, Skype för företag-innehåll), SharePoint-webbplatsinnehåll och filer som lagrats på webbplatser och filer som laddats upp till OneDrive för företag eller Skype för företag.) Microsoft använder flera krypteringsmetoder, protokoll och chiffer i sina produkter och tjänster för att tillhandahålla en säker väg där kunddata kan färdas genom våra molntjänster och för att skydda konfidentiella kunddata som lagras i våra molntjänster. Microsoft använder några av de starkaste och säkraste krypteringsprotokollen som finns tillgängliga för att hjälpa obehöriga att komma åt kunddata. Korrekt nyckelhantering är också en viktig del av metodtips för kryptering och Microsoft arbetar för att säkerställa att alla krypteringsnycklar som hanteras av Microsoft skyddas på rätt sätt.

Kunddata som lagras i Microsofts företagmolntjänster skyddas med en eller flera typer av kryptering. (Validering av vår crypto-policy och dess tillämpning verifieras oberoende av flera tredjepartsgranskningar och rapporter om dessa granskningar finns tillgängliga på [Service Trust Portal](https://aka.ms/stp).)

Microsoft tillhandahåller teknik på tjänstsidan som krypterar kunddata vilan och överföringen. För kunddata i vila använder Microsoft Azure till exempel [BitLocker](/windows/device-security/bitlocker/bitlocker-overview) och [DM-Crypt,](https://en.wikipedia.org/wiki/Dm-crypt)och Microsoft 365 använder BitLocker, [Azure Storage Service Encryption](/azure/), [DKM (Distributed Key Manager)](./exchange-online-secures-email-secrets.md) och Microsoft 365 tjänstekryptering. För kunddata under överföring använder Azure, Office 365, Microsofts kommersiella support, Microsoft Dynamics 365, Microsoft Power BI och Visual Studio Team Services företags säkra transportprotokoll, som IPsec (Internet Protocol Security) och TLS (Transport Layer Security), mellan Microsoft-datacenter och mellan användarenheter och Microsoft-datacenter.

Utöver baslinjen för kryptografiksäkerhet som tillhandahålls av Microsoft innehåller våra molntjänster även krypteringsalternativ som du kan hantera. Du kan till exempel aktivera kryptering av trafik mellan deras virtuella Azure-maskiner (Virtual Machines, VMs) och deras användare. Med [virtuella Azure-nätverk](https://azure.microsoft.com/services/virtual-network/)kan du använda det branschstandarda IPsec-protokollet för att kryptera trafiken mellan företagets VPN-gateway och Azure. Du kan också kryptera trafiken mellan virtuella maskiner i ditt virtuella nätverk. Med de [nya Meddelandekryptering i Office 365 kan du dessutom](set-up-new-message-encryption-capabilities.md) skicka krypterad e-post till alla.

Efter Public Key Infrastructure Operational Security Standard, som är en komponent i [Microsofts](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=5868ecc8-50b7-4f91-b43f-640e2b99e86e&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ%20and%20White%20Papers)säkerhetspolicy, använder Microsoft de kryptografiska funktioner som ingår i Windows-operativsystemet för certifikat och autentiseringsmetoder. Dessa mekanismer inkluderar användningen av kryptografiska moduler som uppfyller den amerikanska statens [Federal Information Processing Standards](https://csrc.nist.gov/publications/PubsFIPS.html) (FIPS) 140-2-standarden. Du kan söka efter relevanta NIST-certifikatnummer för Microsoft med hjälp av [CMVP (Cryptographic Module Validation Program).](https://csrc.nist.gov/projects/cryptographic-module-validation-program/validated-modules/search)

> [OBS] För att komma åt Microsofts säkerhetspolicy som en resurs måste du logga in med ditt arbets- eller skolkonto. Om du inte har ett abonnemang ännu kan [du registrera dig för en kostnadsfri utvärderingsversion.](https://servicetrust.microsoft.com/Home/TrialSubscriptions)

FIPS 140-2 är en standard som utformats specifikt för validering av produktmoduler som implementerar cryptography i stället för de produkter som använder dem. Cryptographic modules that are implemented within a service can be certified as meeting the requirements for hash strength, key management, and the like. De kryptografiska moduler och chiffer som används för att skydda konfidentialitet, integritet och tillgänglighet för data i Microsofts molntjänster uppfyller FIPS 140-2-standarden.

Microsoft certifierar underliggande kryptografiska moduler som används i våra molntjänster i varje ny version av Windows-operativsystemet:

- Azure och Azure U.S. Government
- Dynamics 365 och Dynamics 365 för myndigheter i USA
- Office 365, Office 365 för myndigheter i USA och Office 365 för myndigheter i USA

Kryptering av kunddata i vila tillhandahålls av flera tjänstebaserade tekniker, inklusive BitLocker, DKM, Azure Storage Service Encryption och tjänstekryptering i Exchange Online, Skype för företag, OneDrive för företag och SharePoint Online. Office 365 tjänstekryptering inkluderar ett alternativ för att använda kund hanterade krypteringsnycklar som lagras i Azure-nyckelvalv. Det här alternativet för kund hanterad nyckel, [som](./customer-key-overview.md)kallas Kundnyckel, är tillgängligt för Exchange Online, SharePoint Online, Skype för företag och OneDrive för företag.

För kunddata som överförs förhandlar Office 365 servrar om säkra sessioner med TLS som standard med klientdatorer för att skydda kunddata. Exempelvis kommer Office 365 att förhandla fram säkra sessioner Skype för företag, Outlook och Outlook på webben, mobila klienter och webbläsare.

(Alla servrar mot kunder förhandlar till TLS 1.2 som standard.)

## <a name="related-links"></a>Relaterade länkar

- [Kryptering i Azure](office-365-azure-encryption.md)
- [BitLocker och DKM (Distributed Key Manager) för kryptering](office-365-bitlocker-and-distributed-key-manager-for-encryption.md)
- [Office 365 Tjänstkryptering](office-365-service-encryption.md)
- [Office 365 Kryptering för Skype för företag, OneDrive för företag, SharePoint Online och Exchange Online](/compliance/assurance/assurance-encryption-for-microsoft-365-services) 
- [Kryptering för data som överförs](/compliance/assurance/assurance-encryption-in-transit)
- [Funktioner för kund hanterad kryptering](office-365-customer-managed-encryption-features.md)
- [Krypteringsrisker och -skydd](office-365-encryption-risks-and-protections.md)
- [Kryptering i Microsoft Dynamics 365](office-365-encryption-in-microsoft-dynamics-365.md)