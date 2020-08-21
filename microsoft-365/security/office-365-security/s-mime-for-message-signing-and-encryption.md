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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 887c710b-0ec6-4ff0-8065-5f05f74afef3
description: Administratörer kan lära sig att använda S/MIME (Secure/Multipurpose Internet Mail Extensions) i Exchange Online för att kryptera e-post och signera dem digitalt.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ca865fa8ef658b4715d18e09fe9cbc1cffb201e6
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845932"
---
# <a name="smime-for-message-signing-and-encryption-in-exchange-online"></a>S/MIME för meddelande signering och kryptering i Exchange Online

S/MIME (Secure/Multipurpose Internet Mail Extensions) är en allmänt godkänd metod (eller mer exakt ett protokoll) för att skicka digitalt signerade och krypterade meddelanden. Med S/MIME kan du kryptera e-post och signera dem digitalt. När du använder S/MIME med ett e-postmeddelande kan de personer som får meddelandet att vara säker på att det som visas i Inkorgen är det exakta meddelandet som börjar med avsändaren. Det hjälper också personer som får meddelanden att vara säker på att meddelandet kommer från den specifika avsändaren och inte från någon som är inloggad som avsändare. För att göra det här är S/MIME för kryptografiska säkerhets tjänster, till exempel för meddelandeautentisering, meddelande integritet och oavvislig het (med hjälp av digitala signaturer). Den förbättrar också integritets-och data säkerhet (med kryptering) för elektroniska meddelanden. En mer komplett bakgrund om historik och arkitektur för S/MIME-kontexten för e-post finns i [förstå S/MIME](https://docs.microsoft.com/previous-versions/tn-archive/aa995740(v=exchg.65)).

Som Exchange Online-administratör kan du aktivera S/MIME-baserad säkerhet för post lådorna i organisationen. Använd vägledningen i de avsnitt som länkats här tillsammans med Exchange Online PowerShell för att konfigurera S/MIME. Om du vill använda S/MIME i e-postklienter som stöds, måste användarna i din organisation ha certifikat som utfärdas för signerings-och krypterings syfte och data som publiceras till din lokala Active Directory Domain Service (AD DS). Din AD DS måste finnas på datorer på en fysisk plats som du styr och inte på en lokal tjänst eller Cloud-baserad service någonstans på Internet. Mer information om AD DS finns i [Översikt över Active Directory Domain Services](https://docs.microsoft.com/windows-server/identity/ad-ds/get-started/virtual-dc/active-directory-domain-services-overview).

## <a name="supported-scenarios-and-technical-considerations"></a>Scenarier och tekniska överväganden

Du kan ställa in S/MIME så att det fungerar med följande slut punkter:

- Outlook 2010 eller senare
- Outlook på webben (tidigare Outlook Web App)
- Exchange ActiveSync (EAS)

De steg du följer för att konfigurera S/MIME med dessa slut punkter är lite annorlunda. Vanligt vis måste du göra följande:

1. Installera en Windows-baserad certifikat utfärdare (CA) och skapa en infrastruktur för offentliga nycklar för att utfärda S/MIME-certifikat. Certifikat som utfärdas av tredjeparts certifikat leverantörer stöds också. Mer information finns i [Översikt över Active Directory-certifikattjänster](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831740(v=ws.11)).

   **Anmärkningar**:

   - Certifikat som utfärdas av en tredjeparts certifikat utfärdare har fördelen att automatiskt vara betrodda av alla klienter och enheter. Certifikat som utfärdas av en intern, privat certifikat utfärdare är inte automatiskt betrodda av klienter och enheter, och alla enheter (till exempel telefoner) kan inte konfigureras för att lita på privata certifikat.

   - Överväg att använda mellanliggande certifikat i stället för rot certifikatet för att utfärda certifikat till användarna. På så sätt är rot certifikatet fortfarande intakt om du någon gång behöver återkalla certifikaten.

2. Publicera användar certifikatet i ett lokalt AD DS-konto i **userSMIMECertificate** och/eller **userCertificate** attribut.

3. För Exchange Online-organisationer synkroniserar du användar certifikat från AD DS till Azure Active Directory via en lämplig version av Azure AD Connect. Dessa certifikat kommer då att synkroniseras från Azure Active Directory till Exchange Online-katalogen och kommer att användas när du krypterar ett meddelande till en mottagare.

4. Konfigurera en samling med virtuella certifikat för att verifiera S/MIME. Den här informationen används av Outlook på webben när du verifierar signaturen i ett e-postmeddelande och kontrollerar att den har signerats av ett betrott certifikat.

5. Konfigurera Outlook eller EAS end point för S/MIME.

> [!NOTE]
> Du kan inte installera S/MIME-kontroll i Outlook på webben på Mac, iOS, Android eller andra enheter som inte är Windows. Mer information finns i [kryptera meddelanden med S/MIME i Outlook på webben](https://support.microsoft.com/office/878c79fc-7088-4b39-966f-14512658f480).

## <a name="setup-smime-with-outlook-on-the-web"></a>Konfigurera S/MIME med Outlook på webben

Det handlar om att konfigurera S/MIME för Exchange Online med Outlook på webben:

1. [Konfigurera S/MIME-inställningar för Outlook på webben](configure-s-mime-settings-for-outlook-web-app.md)
2. [Konfigurera en virtuell certifikatsamling för att verifiera S/MIME](set-up-virtual-certificate-collection-to-validate-s-mime.md)
3. [Synkronisera användarcertifikat med Office 365 för S/MIME](sync-user-certificates-to-office-365-for-s-mime.md)

## <a name="related-message-encryption-technologies"></a>Relaterade krypterings teknologier för meddelanden

Eftersom meddelande säkerheten blir mer viktig måste administratörer förstå principerna och begreppen för säker meddelanden. Den här överenskommelsen är särskilt viktig på grund av den växande mängd skydds teknik (inklusive S/MIME) som är tillgänglig. Information om hur du tar reda på mer om S/MIME och hur det fungerar i samband med e-post finns i [förstå S/MIME](https://docs.microsoft.com/previous-versions/tn-archive/aa995740(v=exchg.65)). En mängd olika krypterings tekniker samarbetar för att skydda meddelanden på ett ställe och transit. S/MIME kan arbeta samtidigt med följande tekniker men är inte beroende av dem:

- **TLS (Transport Layer Security)** krypterar tunneln eller vägen mellan e-postservrar för att förhindra snooping och övervakning.

- **SSL (Secure Sockets Layer)** krypterar anslutningen mellan e-postklienter och Microsoft 365-servrar.

- **BitLocker** krypterar data på en hård disk i ett Data Center så att om någon får obehörig åtkomst kan de inte läsa det.

### <a name="smime-compared-with-office-365-message-encryption"></a>S/MIME jämfört med Office 365 meddelande kryptering

S/MIME kräver ett certifikat och en infrastruktur för publicering som ofta används i förhållanden mellan affärs verksamhet och företags användning. Användaren styr kryptografiska nycklar i S/MIME och kan välja om de ska använda dem för varje meddelande de skickar. E-postprogram som Outlook söker efter en betrodd rot certifikat utfärdare för att utföra digital signering och verifiering av signaturen. Office 365 meddelande kryptering är en principbaserad krypterings tjänst som kan konfigureras av en administratör och inte en enskild användare, för att kryptera e-post som skickas till vem som helst i organisationen. Det är en online tjänst som är byggd för Azure Rights Management (RMS) och inte förlitar sig på en infrastruktur med offentliga nycklar. Office 365 meddelande kryptering ger också ytterligare funktioner, till exempel möjligheten att anpassa e-post med organisationens märke. Mer information om Office 365 meddelande kryptering finns i [kryptering i Office 365](https://docs.microsoft.com/microsoft-365/compliance/encryption).

## <a name="more-information"></a>Mer information

[Outlook på webben](https://docs.microsoft.com/exchange/exchange-admin-center)

[Säker e-post (2000)](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc962043(v=technet.10))
