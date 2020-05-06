---
title: S/MIME för kryptering i Exchange Online – Office 365
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
ms.assetid: 887c710b-0ec6-4ff0-8065-5f05f74afef3
description: Administratörer kan lära sig mer om hur du använder S/MIME (Secure/Multipurpose Internet Mail Extensions) i Exchange Online för att kryptera e-postmeddelanden och signera dem digitalt.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8c45df36535e7b5af2648b82f83159315b94bec8
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036626"
---
# <a name="smime-for-message-signing-and-encryption-in-exchange-online"></a>S/MIME för signering och kryptering av meddelanden i Exchange Online

S/MIME (Secure/Multipurpose Internet Mail Extensions) är en allmänt accepterad metod (eller mer exakt, ett protokoll) för att skicka digitalt signerade och krypterade meddelanden. S/MIME låter dig kryptera e-post och signera dem digitalt. När du använder S/MIME med ett e-postmeddelande hjälper det de personer som får meddelandet att vara säkra på att det de ser i inkorgen är det exakta meddelandet som började med avsändaren. Det kommer också att hjälpa personer som tar emot meddelanden att vara säkra på att meddelandet kom från den specifika avsändaren och inte från någon som låtsas vara avsändaren. För att göra detta tillhandahåller S/MIME kryptografiska säkerhetstjänster som autentisering, meddelandeintegritet och icke-avståndstagande från ursprung (med hjälp av digitala signaturer). Det bidrar också till att förbättra integriteten och datasäkerheten (med kryptering) för elektroniska meddelanden. En mer komplett bakgrund om S/MIME:s historia och arkitektur i e-postmeddelandets e-post finns i [Förstå S/MIME](https://docs.microsoft.com/previous-versions/tn-archive/aa995740(v=exchg.65)).

Som Exchange Online-administratör kan du aktivera S/MIME-baserad säkerhet för postlådorna i organisationen. Använd vägledningen i de ämnen som länkas här tillsammans med Exchange Online PowerShell för att konfigurera S/MIME. Om du vill använda S/MIME i e-postklienter som stöds måste användarna i organisationen ha certifikat utfärdade för signering och kryptering och data som publiceras i din lokala Active Directory Domain Service (AD DS). Din AD DS måste finnas på datorer på en fysisk plats som du styr och inte på en fjärrfunktion eller molnbaserad tjänst någonstans på internet. Mer information om AD DS finns i [Översikt över Active Directory Domain Services](https://docs.microsoft.com/windows-server/identity/ad-ds/get-started/virtual-dc/active-directory-domain-services-overview).

## <a name="supported-scenarios-and-technical-considerations"></a>Scenarier som stöds och tekniska överväganden

Du kan ställa in S/MIME så att de fungerar med någon av följande slutpunkter:

- Outlook 2010 eller senare

- Outlook på webben (tidigare kallat Outlook Web App)

- Exchange ActiveSync (EAS)

De steg som du följer för att ställa in S/MIME med var och en av dessa slutpunkter är något annorlunda. I allmänhet måste du göra följande:

1. Installera en Windows-baserad certifikatutfärdare och konfigurera en infrastruktur för offentliga nycklar för att utfärda S/MIME-certifikat. Certifikat som utfärdats av tredjepartscertifikatleverantörer stöds också. Mer information finns i [Översikt över Active Directory-certifikattjänster](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831740(v=ws.11)).

2. Publicera användarcertifikatet i ett lokalt AD DS-konto i attributen **UserSMIMECertificate** och/eller **UserCertificate.**

3. För Exchange Online-organisationer synkroniserar du användarcertifikaten från AD DS till Azure Active Directory med hjälp av en lämplig version av Azure AD Connect. Dessa certifikat synkroniseras sedan från Azure Active Directory till Exchange Online-katalogen och används när ett meddelande krypteras till en mottagare.

4. Konfigurera en virtuell certifikatsamling för att validera S/MIME. Den här informationen används av Outlook på webben när du validerar signaturen för ett e-postmeddelande och ser till att det signerades av ett betrott certifikat.

5. Konfigurera slutpunkten för Outlook eller EAS så att S/MIME används.

> [!NOTE]
> Du kan inte installera S/MIME-kontrollen i Outlook på webben på Mac, iOS, Android eller andra enheter som inte kommer från Windows. Mer information finns i [Kryptera meddelanden med S/MIME i Outlook på webben](https://support.office.com/article/878c79fc-7088-4b39-966f-14512658f480).

## <a name="setup-smime-with-outlook-on-the-web"></a>Konfigurera S/MIME med Outlook på webben

Att konfigurera S/MIME för Exchange Online med Outlook på webben innebär följande viktiga steg:

1. [Konfigurera S/MIME-inställningar för Outlook på webben](configure-s-mime-settings-for-outlook-web-app.md)

2. [Konfigurera en virtuell certifikatsamling för att verifiera S/MIME](set-up-virtual-certificate-collection-to-validate-s-mime.md)

3. [Synkronisera användarcertifikat med Office 365 för S/MIME](sync-user-certificates-to-office-365-for-s-mime.md)

## <a name="related-message-encryption-technologies"></a>Relaterade meddelandekrypteringstekniker

När meddelandesäkerhet blir viktigare måste administratörer förstå principerna och begreppen för säkra meddelanden. Denna förståelse är särskilt viktig på grund av den växande variationen av skyddsrelaterad teknik (inklusive S/MIME) som finns tillgänglig. Mer information om S/MIME och hur det fungerar i samband med e-post finns i [Förstå S/MIME](https://docs.microsoft.com/previous-versions/tn-archive/aa995740(v=exchg.65)). En mängd olika krypteringstekniker arbetar tillsammans för att skydda meddelanden i vila och under överföring. S/MIME kan arbeta samtidigt med följande tekniker men är inte beroende av dem:

- **TLS (Transport Layer Security)** krypterar tunneln eller rutten mellan e-postservrar för att förhindra snokande och avlyssning.

- **SSL (Secure Sockets Layer)** krypterar anslutningen mellan e-postklienter och Microsoft 365-servrar.

- **BitLocker** krypterar data på en hårddisk i ett datacenter så att om någon får obehörig åtkomst kan de inte läsa dem.

### <a name="smime-compared-with-office-365-message-encryption"></a>S/MIME jämfört med meddelandekryptering i Office 365

S/MIME kräver en certifikat- och publiceringsinfrastruktur som ofta används i affärs-till-företag- och affärs-till-konsument-situationer. Användaren styr kryptografiska nycklar i S/MIME och kan välja om de ska användas för varje meddelande de skickar. E-postprogram som Outlook söker efter en betrodd plats för rotcertifikatutfärdare för att utföra digital signering och verifiering av signaturen. Office 365 Message Encryption är en principbaserad krypteringstjänst som kan konfigureras av en administratör och inte en enskild användare för att kryptera e-post som skickas till vem som helst inom eller utanför organisationen. Det är en onlinetjänst som bygger på Azure Rights Management (RMS) och inte är beroende av en infrastruktur för offentliga nycklar. Meddelandekryptering i Office 365 innehåller också ytterligare funktioner, till exempel möjligheten att anpassa e-postmeddelandet med organisationens varumärke. Mer information om meddelandekryptering i Office 365 finns [i Kryptering i Office 365](https://docs.microsoft.com/microsoft-365/compliance/encryption).

## <a name="more-information"></a>Mer information

[Outlook på webben](https://docs.microsoft.com/exchange/exchange-admin-center)

[Säker e-post (2000)](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc962043(v=technet.10))
