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
ms.openlocfilehash: 35266b4ceefe161b907ddbc955fd234b716792a6
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288579"
---
# <a name="smime-for-message-signing-and-encryption-in-exchange-online"></a>S/MIME för meddelandesignering och kryptering i Exchange Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


S/MIME (Secure/Multipurpose Internet Mail Extensions) är en allmänt accepterad metod (eller mer exakt ett protokoll) för att skicka digitalt signerade och krypterade meddelanden. Med S/MIME kan du kryptera e-postmeddelanden och signera dem digitalt. När du använder S/MIME med ett e-postmeddelande hjälper det personer som får det meddelandet att vara säkra på att det de ser i inkorgen är det exakta meddelandet som började med avsändaren. Det hjälper också personer som får meddelanden att vara säkra på att meddelandet kommer från den specifika avsändaren och inte från någon som utger sig för att vara avsändaren. För att göra detta tillhandahåller S/MIME kryptografiska säkerhetstjänster som autentisering, meddelandeintegritet och oavvislighet av ursprung (med hjälp av digitala signaturer). Det förbättrar också sekretess och datasäkerhet (med kryptering) för elektroniska meddelanden. En mer fullständig bakgrund om S/MIME:s historik och arkitektur inom e-post finns i Förstå [S/MIME.](https://docs.microsoft.com/previous-versions/tn-archive/aa995740(v=exchg.65))

Som Exchange Online-administratör kan du aktivera S/MIME-baserad säkerhet för postlådorna i organisationen. Använd vägledning i avsnitten som länkas här tillsammans med Exchange Online PowerShell för att konfigurera S/MIME. För att använda S/MIME i e-postklienter som stöds måste användarna i organisationen ha certifikat utfärdade för signering och kryptering och data som publiceras till din lokala Active Directory Domain Service (AD DS). Din AD DS måste finnas på datorer på en fysisk plats som du styr och inte på en fjärrinstallation eller en molnbaserad tjänst någonstans på Internet. Mer information om AD DS finns i [Active Directory DS Översikt.](https://docs.microsoft.com/windows-server/identity/ad-ds/get-started/virtual-dc/active-directory-domain-services-overview)

## <a name="supported-scenarios-and-technical-considerations"></a>Scenarier som stöds och tekniska överväganden

Du kan konfigurera S/MIME så att det fungerar med någon av följande ändpunkter:

- Outlook 2010 eller senare
- Outlook på webben (hette tidigare Outlook Web App)
- Exchange ActiveSync (EAS)

Stegen du följer för att konfigurera S/MIME med var och en av dessa ändpunkter skiljer sig åt något. I allmänhet måste du göra följande:

1. Installera en Windows-baserad certifikatutfärdare (CA) och konfigurera en offentlig nyckelinfrastruktur för att utfärda S/MIME-certifikat. Certifikat som utfärdats av tredjepartscertifikatleverantörer stöds också. Mer information finns i [Active Directory Certificate Services – översikt.](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831740(v=ws.11))

   **Anmärkningar**:

   - Certifikat som utfärdats av en tredjepartsutfärdare har fördelen med att bli automatiskt betrodda av alla klienter och enheter. Certifikat som utfärdas av en intern, privat certifikatutfärdare är inte automatiskt betrodda av klienter och enheter, och inte alla enheter (till exempel telefoner) kan konfigureras för att lita på privata certifikat.

   - Överväg att använda ett mellanliggande certifikat i stället för rotcertifikatet för att utfärda certifikat till användarna. Om du någon gång behöver återkalla och återutiera certifikat är rotcertifikatet fortfarande intakt.

2. Publicera användarcertifikatet på ett lokalt AD DS-konto i **Attributen UserSMIMECertificate** och/eller **UserCertificate.**

3. För Exchange Online-organisationer synkroniserar du användarcertifikaten från AD DS till Azure Active Directory med hjälp av en lämplig version av Azure AD Connect. Certifikaten synkroniseras sedan från Azure Active Directory till Exchange Online-katalogen och används när ett meddelande krypteras till en mottagare.

4. Konfigurera en virtuell certifikatsamling för att verifiera S/MIME. Den här informationen används av Outlook på webben när du verifierar signaturen för ett e-postmeddelande och säkerställer att det har signerats av ett betrott certifikat.

5. Konfigurera Outlook- eller EAS-startpunkten så att S/MIME används.

> [!NOTE]
> Du kan inte installera S/MIME-kontroll i Outlook på webben på Mac, iOS, Android eller andra enheter som inte är Windows-enheter. Mer information finns i Kryptera [meddelanden med S/MIME i Outlook på webben.](https://support.microsoft.com/office/878c79fc-7088-4b39-966f-14512658f480)

## <a name="set-up-smime-with-outlook-on-the-web"></a>Konfigurera S/MIME med Outlook på webben

För att konfigurera S/MIME för Exchange Online med Outlook på webben ingår följande huvudsteg:

1. [Konfigurera S/MIME-inställningar för Outlook på webben](configure-s-mime-settings-for-outlook-web-app.md)
2. [Konfigurera en virtuell certifikatsamling för att verifiera S/MIME](set-up-virtual-certificate-collection-to-validate-s-mime.md)
3. [Synkronisera användarcertifikat med Office 365 för S/MIME](sync-user-certificates-to-office-365-for-s-mime.md)

## <a name="related-message-encryption-technologies"></a>Relaterad teknik för meddelandekryptering

I och med att meddelandesäkerheten blir viktigare måste administratörer förstå principerna och begreppen för säkra meddelanden. Den här förståelsen är särskilt viktig på grund av den växande mängd skyddsrelaterade tekniker (inklusive S/MIME) som finns tillgängliga. Mer information om S/MIME och hur det fungerar i samband med e-post finns i [Förstå S/MIME.](https://docs.microsoft.com/previous-versions/tn-archive/aa995740(v=exchg.65)) Flera olika krypteringstekniker fungerar tillsammans för att skydda meddelanden i vila och under överföring. S/MIME kan arbeta samtidigt med följande tekniker men är inte beroende av dem:

- **TLS (Transport Layer Security)** krypterar tunneln eller vägen mellan e-postservrar för att förhindra snooping och avlysning.

- **SSL (Secure Sockets Layer) (SSL) krypterar** anslutningen mellan e-postklienter och Microsoft 365-servrar.

- **BitLocker** krypterar data på en hårddisk i ett datacenter så att användare inte kan läsa informationen om någon får otillåten åtkomst.

### <a name="smime-compared-with-office-365-message-encryption"></a>S/MIME jämfört med meddelandekryptering i Office 365

S/MIME kräver en infrastruktur för certifikat och publicering som ofta används i situationer mellan företag och företag till konsumenter. Användaren styr kryptografiska nycklar i S/MIME och kan välja om de ska användas för varje meddelande de skickar. E-postprogram som Outlook söker på en betrodd rotcertifikatutfärdareplats för att utföra digital signering och verifiering av signaturen. Meddelandekryptering i Office 365 är en principbaserad krypteringstjänst som kan konfigureras av en administratör och inte av en enskild användare för att kryptera e-post som skickas till någon inom eller utanför organisationen. Det är en onlinetjänst som bygger på Azure Rights Management (RMS) och som inte förlitar sig på en offentlig nyckelinfrastruktur. Meddelandekryptering i Office 365 har också ytterligare funktioner, till exempel möjligheten att anpassa e-post med organisationens varumärke. Mer information om meddelandekryptering i Office 365 finns i [Kryptering i Office 365.](../../compliance/encryption.md)

## <a name="more-information"></a>Mer information

[Outlook på webben](https://docs.microsoft.com/exchange/exchange-admin-center)

[Säker e-post (2000)](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc962043(v=technet.10))
