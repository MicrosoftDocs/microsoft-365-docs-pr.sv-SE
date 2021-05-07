---
title: Kundhanterade krypterings funktioner
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
ms.collection: Strat_O365_Enterprise
ms.custom:
- seo-marvel-mar2020
description: I den här artikeln får du lära dig mer om krypteringstekniker som du kan hantera och konfigurera Microsoft 365.
ms.openlocfilehash: 6a693c512100c59eef47414fdd6eab4a2924e835
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162217"
---
# <a name="customer-managed-encryption-features"></a>Kundhanterade krypterings funktioner

Tillsammans med krypteringstekniker i Microsoft 365 hanteras av Microsoft fungerar Microsoft 365 även med ytterligare krypteringstekniker som du kan hantera och konfigurera, till exempel:

- [Azure Rights Management](/azure/information-protection/what-is-azure-rms)

- [Secure Multipurpose Internet Mail Extension](https://blogs.technet.com/b/exchange/archive/2014/12/15/how-to-configure-s-mime-in-office-365.aspx)

- [Meddelandekryptering i Office 365](https://products.office.com/en-us/exchange/office-365-message-encryption)

- [Säkert e-postflöde med en partnerorganisation](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)

Mer information om dessa tekniker finns i Microsoft 365 [tjänstbeskrivningar](/office365/servicedescriptions/office-365-service-descriptions-technet-library).

## <a name="azure-rights-management"></a>Azure Rights Management

[Azure Rights Management](/azure/information-protection/what-is-azure-rms) (Azure RMS) är den skyddsteknik som används av [Azure Information Protection.](/information-protection/understand-explore/what-is-information-protection) Den använder principer för kryptering, identitet och auktorisering för att skydda dina filer och e-post på flera plattformar och enheter– telefoner, surfplattor och datorer. Informationen kan skyddas både inom och utanför organisationen eftersom skyddet finns kvar hos informationen. Azure RMS ger ett beständigt skydd av alla filtyper, skyddar filer var som helst, har stöd för samarbete mellan företag och ett brett utbud av Windows och icke-Windows enheter. Azure RMS-skydd kan även öka [DLP-principer (Data Loss Prevention).](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention) Mer information om vilka program och tjänster som kan använda tjänsten Azure Rights Management från Azure Information Protection finns i Hur programmen har stöd för [Azure Rights Management-tjänsten.](/information-protection/understand-explore/applications-support)

Azure RMS är integrerat med Microsoft 365 och tillgängligt för alla kunder. Information om Microsoft 365 hur du använder Azure RMS finns i Konfigurera IRM för att använda Azure Rights Management och Konfigurera [IRM (Information Rights Management) i SharePoint admin center.](../enterprise/activate-rms-in-microsoft-365.md) Om du använder EN AD RMS-server (on-premises Active Directory) kan du också konfigurera IRM så att en lokal [AD RMS-server](/office365/SecurityCompliance/configure-irm-to-use-an-on-premises-ad-rms-server)används, men vi rekommenderar starkt att du migrerar till [Azure RMS](/azure/information-protection/migrate-from-ad-rms-to-azure-rms) för att använda nya funktioner som säkert samarbete med andra organisationer.

När du skyddar kunddata med Azure RMS använder Azure RMS en 2048-bitars RSA-asymmetrisk nyckel med SHA-256-hashalgoritmen för integritet för att kryptera data. Den symmetriska nyckeln för att Office dokument och e-post är AES 128-bitars. För varje dokument eller e-post som skyddas av Azure RMS skapar Azure RMS en enda AES-nyckel ("innehållsnyckeln"), och den nyckeln är inbäddad i dokumentet och finns kvar i utgåvor av dokumentet. Innehållsnyckeln är skyddad med organisationens RSA-nyckel (Azure Information Protection-klientnyckeln) som en del av principen i dokumentet, och principen signeras även av dokumentets författare. Den här klientnyckeln är gemensam för alla dokument och e-postmeddelanden som skyddas av Azure RMS för organisationen och den här nyckeln kan bara ändras av en Azure Information Protection-administratör om organisationen använder en klientnyckel som hanteras av kunder. Mer information om de kryptografiska kontroller som används av Azure RMS finns [i Hur fungerar Azure RMS? Under motorhuven](/information-protection/understand-explore/how-does-it-work).

I en Azure RMS-standardimplementering genererar och hanterar Microsoft rotnyckeln som är unik för varje klientorganisation. Kunder kan hantera livscykeln för sin rotnyckel i Azure RMS med Azure Key Vault Services med hjälp av en nyckelhanteringsmetod som kallas Bring [Your Own Key (BYOK)](/azure/information-protection/plan-implement-tenant-key) som gör att du kan generera nyckeln i lokala system för virtuella maskiner (maskinvarusäkerhetsmoduler) och ha kontroll över den här nyckeln efter överföring till Microsofts FIPS 140-2-verifierade HSMs på nivå 2. Åtkomst till rotnyckeln ges inte till någon personal eftersom nycklarna inte kan exporteras eller extraheras från de snabbmeddelanden som skyddar dem. Dessutom kan du när som helst komma åt en nästan realtidslogg som visar all åtkomst till rotnyckeln. Mer information finns i [Loggning och analys av Azure Rights Management-användning.](/azure/information-protection/log-analyze-usage)

Azure Rights Management bidrar till att minimera hot som trådtryck, man-i-mitten-attacker, datastöld och oavsiktliga överträdelser av principer för organisationsdelning. Samtidigt förhindras ovarningar om åtkomst av kunddata som överförs eller vilan av en obehörig användare som inte har rätt behörighet via principer som följer dessa data, vilket minimerar risken för att data hamnar i fel händer, antingen avsiktligt eller oavsiktligt och som tillhandahåller funktioner för dataförlustskydd. Om Azure RMS används som en del av Azure Information Protection tillhandahåller Azure RMS även funktioner för dataklassificering och märkning, innehållsmarkering, spårning av dokumentåtkomst och återkallelsefunktioner för åtkomst. Mer information om funktionerna finns i Vad är [Azure Information Protection,](/information-protection/understand-explore/what-is-information-protection) [Distributionsöversikt över Azure Information Protection](/information-protection/plan-design/deployment-roadmap)och [Snabbstartsguide för Azure Information Protection.](/information-protection/get-started/infoprotect-quick-start-tutorial)

## <a name="secure-multipurpose-internet-mail-extension"></a>Secure Multipurpose Internet Mail Extension

S/MIME (Secure/Multipurpose Internet Mail Extensions) är en standard för offentlig nyckelkryptering och digital signering av MIME-data. S/MIME definieras i RFCs 3369, 3370, 3850, 3851 och andra. Det gör att en användare kan kryptera ett e-postmeddelande och digitalt signera ett e-postmeddelande. Ett e-postmeddelande som krypteras med S/MIME kan bara dekrypteras av e-postmottagaren med sin privata nyckel, som bara är tillgänglig för den mottagaren. E-postmeddelandena kan därför inte dekrypteras av någon annan än mottagaren av e-postmeddelandet.

[Microsoft har stöd för S/MIME.](https://blogs.technet.com/b/exchange/archive/2014/12/15/how-to-configure-s-mime-in-office-365.aspx) Offentliga certifikat distribueras till kundens lokala Active Directory och lagras i attribut som kan replikeras till en Microsoft 365 klientorganisation. De privata nycklar som motsvarar de offentliga nycklarna finns kvar lokalt och överförs aldrig till Office 365. Användare kan skriva, kryptera, dekryptera, läsa och signera e-postmeddelanden digitalt mellan två användare i en organisation med hjälp av Outlook, Outlook på webben och Exchange ActiveSync-klienter. Mer information finns i [S/MIME-kryptering finns nu i Office 365](https://blogs.office.com/2014/02/26/smime-encryption-now-in-office-365/).

## <a name="office-365-message-encryption"></a>Meddelandekryptering i Office 365

[Meddelandekryptering i Office 365](https://products.office.com/exchange/office-365-message-encryption) (OME) som bygger på [Azure Information Protection](/information-protection/understand-explore/what-is-information-protection) (AIP) kan du skicka krypterad och rättighetsskyddad e-post till alla. OME minimerar hot som trådande och man-i-mitten-attacker och andra hot, till exempel ovarningar om åtkomst av data av en obehörig användare som inte har rätt behörighet. Vi har gjort investeringar som ger dig en enklare, mer intuitiv och säker e-postupplevelse byggd på Azure Information Protection. Du kan skydda meddelanden som skickas Microsoft 365 meddelanden till personer i eller utanför organisationen. Dessa meddelanden kan visas i en rad olika e-postklienter med valfri identitet, Azure Active Directory, Microsoft-konto och Google-ID: n. Mer information om hur du kan använda krypterade meddelanden i organisationen finns [i Meddelandekryptering i Office 365](./ome.md).

## <a name="transport-layer-security"></a>Transport Layer Security

Om du vill säkerställa säker kommunikation med en partner kan du använda inkommande och utgående anslutningar för att tillhandahålla säkerhet och meddelandeintegritet. Du kan konfigurera tvingad inkommande och utgående TLS för varje koppling, med hjälp av ett certifikat. Om du använder en krypterad SMTP-kanal kan data inte stjäls via en man-i-mitten-attack. Mer information finns i Hur [du använder Exchange Online TLS för att skydda e-postanslutningar.](./exchange-online-uses-tls-to-secure-email-connections.md)

## <a name="domain-keys-identified-mail"></a>Domännycklar identifierad e-post

Exchange Online Protection (EOP) Exchange Online har stöd för inkommande validering av DKIM-meddelanden (Domain Keys Identified Mail). DKIM är en metod för att verifiera att ett meddelande skickades från den domän som meddelandet kommer från och att det inte kapats av någon annan. Det binder även ett e-postmeddelande till den organisation som ansvarar för att skicka det och är en del av en större del av e-postkryptering. Mer information om de tre delarna av den här bran finns i:

- [Konfigurera SPF för att förhindra förfalskning](/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)

- [Använda DKIM för att validera utgående e-post som skickas från din anpassade domän](/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)

- [Använda DMARC för att validera e-post](/office365/SecurityCompliance/use-dmarc-to-validate-email)