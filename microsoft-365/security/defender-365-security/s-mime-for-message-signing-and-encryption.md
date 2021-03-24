---
title: S/MIME för kryptering i Exchange Online – Office 365
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
ms.assetid: 887c710b-0ec6-4ff0-8065-5f05f74afef3
description: Administratörer kan läsa mer om hur de använder S/MIME (Secure/Multipurpose Internet Mail Extensions) i Exchange Online för att kryptera e-postmeddelanden och signera dem digitalt.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d189bf7f52dd6f9fb11dc360c17d5fe15729c9fa
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51069953"
---
# <a name="smime-for-message-signing-and-encryption-in-exchange-online"></a>S/MIME för meddelandesignering och kryptering i Exchange Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


S/MIME (Secure/Multipurpose Internet Mail Extensions) är en allmänt accepterad metod (eller mer exakt ett protokoll) för att skicka digitalt signerade och krypterade meddelanden. Med S/MIME kan du kryptera e-postmeddelanden och signera dem digitalt. När du använder S/MIME i ett e-postmeddelande hjälper det personer som får meddelandet att vara säkra på att det de ser i Inkorgen är det exakta meddelandet som började med avsändaren. Det hjälper också personer som får meddelanden att vara säkra på att meddelandet kommer från den specifika avsändaren och inte från någon som utger sig för att vara avsändaren. För att göra detta tillhandahåller S/MIME kryptografiska säkerhetstjänster, till exempel autentisering, meddelandeintegritet och oavvislighet om ursprung (med hjälp av digitala signaturer). Det förbättrar också sekretess och datasäkerhet (med kryptering) för elektroniska meddelanden. En mer fullständig bakgrund om historik och arkitektur för S/MIME i kontexten för e-post finns i [Förstå S/MIME.](/previous-versions/tn-archive/aa995740(v=exchg.65))

Som Exchange Online-administratör kan du aktivera S/MIME-baserad säkerhet för postlådorna i organisationen. Använd vägledning i avsnitten som länkas här tillsammans med Exchange Online PowerShell för att konfigurera S/MIME. Om användarna i organisationen ska kunna använda S/MIME i e-postklienter som stöds måste certifikat utfärdas för signering och kryptering och data som publiceras på din lokala AD DS (Active Directory Domain Service). DIN AD DS måste vara placerad på datorer på en fysisk plats som du styr och inte på en fjärrinstallation eller molnbaserad tjänst någonstans på Internet. Mer information om AD DS finns i Översikt [över Active Directory Domain Services](/windows-server/identity/ad-ds/get-started/virtual-dc/active-directory-domain-services-overview).

## <a name="supported-scenarios-and-technical-considerations"></a>Scenarier som stöds och tekniska överväganden

Du kan konfigurera S/MIME så att det fungerar med någon av följande ändpunkter:

- Outlook 2010 eller senare
- Outlook på webben (kallades tidigare Outlook Web App)
- Exchange ActiveSync (EAS)

Stegen som du följer för att konfigurera S/MIME med var och en av dessa ändpunkter skiljer sig åt en aning. I allmänhet måste du göra följande:

1. Installera en Windows-baserad certifikatutfärdare (CA) och konfigurera en offentlig nyckelinfrastruktur för att utfärda S/MIME-certifikat. Certifikat som utfärdats av tredje parts certifikatleverantörer stöds också. Mer information finns i [Översikt över Active Directory Certificate Services](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831740(v=ws.11)).

   **Anmärkningar**:

   - Certifikat som utfärdats av en tredje parts certifikatutfärdare har fördelen att de automatiskt blir betrodda av alla klienter och enheter. Certifikat som utfärdas av en intern, privat certifikatutfärdare är inte automatiskt betrodda av klienter och enheter och inte alla enheter (till exempel telefoner) kan konfigureras för att lita på privata certifikat.

   - Överväg att använda ett mellanliggande certifikat i stället för rotcertifikatet för att utfärda certifikat till användarna. På så sätt är rotcertifikatet fortfarande intakt om du skulle behöva återkalla och återkalla certifikat.

2. Publicera användarcertifikatet på ett lokalt AD DS-konto i **UserSMIMECertificate-** och/eller **UserCertificate-attribut.**

3. För Exchange Online-organisationer synkroniserar du användarcertifikaten från AD DS till Azure Active Directory med hjälp av en lämplig version av Azure AD Connect. Certifikaten synkroniseras sedan från Azure Active Directory till Exchange Online-katalogen och används när ett meddelande krypteras till en mottagare.

4. Konfigurera en samling med virtuella certifikat för att verifiera S/MIME. Den här informationen används av Outlook på webben när du verifierar signaturen för ett e-postmeddelande och säkerställer att det har signerats av ett betrott certifikat.

5. Konfigurera Outlook- eller EAS-ändpunkten så att S/MIME används.

> [!NOTE]
> Du kan inte installera S/MIME-kontroll i Outlook på webben på Mac, iOS, Android eller andra enheter som inte är Windows. Mer information finns i [Kryptera meddelanden med S/MIME i Outlook på webben.](https://support.microsoft.com/office/878c79fc-7088-4b39-966f-14512658f480)

## <a name="set-up-smime-with-outlook-on-the-web"></a>Konfigurera S/MIME med Outlook på webben

För att konfigurera S/MIME för Exchange Online med Outlook på webben ingår följande huvudsteg:

1. [Konfigurera S/MIME-inställningar för Outlook på webben](configure-s-mime-settings-for-outlook-web-app.md)
2. [Konfigurera en virtuell certifikatsamling för att verifiera S/MIME](set-up-virtual-certificate-collection-to-validate-s-mime.md)
3. [Synkronisera användarcertifikat med Office 365 för S/MIME](sync-user-certificates-to-office-365-for-s-mime.md)

## <a name="related-message-encryption-technologies"></a>Relaterad teknik för meddelandekryptering

I och med att meddelandesäkerhet blir viktigare måste administratörer förstå principerna och begreppen för säkra meddelanden. Den här förståelsen är särskilt viktig eftersom den växande variationen bland skyddsrelaterade tekniker (inklusive S/MIME) är tillgänglig. Mer information om S/MIME och hur det fungerar i samband med e-post finns i [Förstå S/MIME.](/previous-versions/tn-archive/aa995740(v=exchg.65)) En mängd olika krypteringstekniker fungerar tillsammans för att skydda meddelanden som är vilan och under överföringen. S/MIME kan arbeta samtidigt med följande tekniker men är inte beroende av dem:

- **TLS (Transport Layer Security)** krypterar tunneln eller vägen mellan e-postservrar för att förhindra snooping och eavesdropping.

- **SSL (Secure Sockets Layer) krypterar** anslutningen mellan e-postklienter och Microsoft 365-servrar.

- **BitLocker** krypterar data på en hårddisk i ett datacenter så att obehörig åtkomst inte kan läsas om någon får åtkomst.

### <a name="smime-compared-with-office-365-message-encryption"></a>S/MIME jämfört med meddelandekryptering i Office 365

S/MIME kräver ett certifikat och en publiceringsinfrastruktur som ofta används i situationer mellan företag och företag till konsumenter. Användaren styr kryptografiska nycklar i S/MIME och kan välja om de ska användas för varje meddelande som han eller hon skickar. E-postprogram som Outlook söker på en betrodd plats med rotcertifikatutfärdare för att utföra digital signering och verifiering av signaturen. Meddelandekryptering i Office 365 är en principbaserad krypteringstjänst som kan konfigureras av en administratör och inte av en enskild användare för att kryptera e-post som skickas till någon inom eller utanför organisationen. Det är en onlinetjänst som bygger på Azure Rights Management (RMS) och som inte förlitar sig på en offentlig nyckelinfrastruktur. Meddelandekryptering i Office 365 ger också ytterligare funktioner, till exempel möjligheten att anpassa e-post med företagets varumärke. Mer information om meddelandekryptering i Office 365 finns i [Kryptering i Office 365.](../../compliance/encryption.md)

## <a name="more-information"></a>Mer information

[Outlook på webben](/exchange/exchange-admin-center)

[Säker e-post (2000)](/previous-versions/windows/it-pro/windows-2000-server/cc962043(v=technet.10))