---
title: Kryptering i Microsoft 365
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/15/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 0a322724-08ca-43db-b69a-afbfa20484cd
ms.collection:
- M365-security-compliance
- Strat_O365_IP
- m365solution-mip
- m365initiative-compliance
description: Med Office 365 krypteras innehållet vil och överförs med den starkaste krypteringen, protokollen och tekniken som finns tillgänglig. Få en översikt över kryptering i Office 365.
ms.openlocfilehash: c54508434c5ae5126a79eba1cb6dab3851d8f746
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162227"
---
# <a name="encryption"></a>Kryptering

Kryptering är en viktig del av din strategi för filskydd och informationsskydd. Den här artikeln innehåller en översikt över kryptering för Office 365. Få hjälp med krypteringsuppgifter, t.ex. hur du kryptering ska konfigureras för din organisation och hur du lösenordsskyddar Office dokument.
  
- Mer information om certifikat och tekniker som TLS finns i [Teknisk referensinformation om kryptering i Office 365.](technical-reference-details-about-encryption.md)

- Mer information om hur du konfigurerar eller konfigurerar kryptering för organisationen finns i [Konfigurera kryptering i Office 365 Enterprise](set-up-encryption.md).

## <a name="what-is-encryption-and-how-does-it-work-in-office-365"></a>Vad är kryptering och hur fungerar det i Office 365?

Krypteringsprocessen kodar dina data (kallas oformaterad text) till chiffertext. Till skillnad från oformaterad text kan chiffertext inte användas av personer eller datorer om inte och tills chiffertexten dekrypteras. Dekryptering kräver en krypteringsnyckel som endast behöriga användare har. Kryptering ser till att endast behöriga mottagare kan dekryptera innehållet. Innehållet omfattar filer, e-postmeddelanden, kalenderposter och så vidare.
  
Kryptering förhindrar inte avlyssning av innehåll. Kryptering är en del av en större strategi för informationsskydd för din organisation. Genom att använda kryptering ser du till att endast behöriga parter kan använda krypterade data.
  
Du kan ha flera lager med kryptering på samma gång. Du kan till exempel kryptera e-postmeddelanden och kommunikationskanalerna som dina e-postflöden flödar igenom. Med Office 365 krypteras dina data vil och överföring, med hjälp av flera starka krypteringsprotokoll och tekniker som inkluderar Transport Layer Security/Secure Sockets Layer (TLS/SSL), IPSec (Internet Protocol Security) och AES (Advanced Encryption Standard).
  
## <a name="encryption-for-data-at-rest-and-data-in-transit"></a>Kryptering av data i vila och data som överförs

 Exempel på **data** i vila är filer som du har laddat upp till ett SharePoint-bibliotek, Project Online-data, dokument som du har laddat upp till ett Skype för företag-möte, e-postmeddelanden och bifogade filer som du har lagrat i mappar i din postlåda och filer som du har laddat upp till OneDrive för företag.
  
 **Exempel på data under överföring** är e-postmeddelanden som håller på att levereras, eller konversationer som hålls i ett onlinemöte. I Office 365 överförs data när en användares enhet kommunicerar med en Microsoft-server, eller när en Microsoft-server kommunicerar med en annan server.
  
Med Office 365, fungerar flera lager och typer av kryptering tillsammans för att skydda dina data. Följande tabell innehåller några exempel, med länkar till ytterligare information.
  
|**Typer av innehåll**|**Krypteringsteknik**|**Resurser för att få mer information**|
|:-----|:-----|:-----|
|Filer på en enhet. Dessa filer kan innehålla e-postmeddelanden som sparats i en mapp, Office-dokument som sparats på en dator, surfplatta eller telefon eller data som sparats i Microsoft-molnet.  <br/> |BitLocker i Microsofts datacenter. BitLocker kan även användas på klientdatorer, t.ex. Windows datorer och surfplattor  <br/> DKM (Distributed Key Manager) i Microsoft-datacenter  <br/> Kundnyckel för Microsoft 365  <br/> |[Windows IT Center: BitLocker](/windows/device-security/bitlocker/bitlocker-overview) <br/> [Microsoft Säkerhetscenter: Kryptering](https://www.microsoft.com/TrustCenter/Security/Encryption) <br/> [Serie med molnsäkerhetskontroller: Kryptera data i vila](https://blogs.microsoft.com/microsoftsecure/2015/09/10/cloud-security-controls-series-encrypting-data-at-rest) <br/> [Så säkrar Exchange Online dina e-posthemligheter](exchange-online-secures-email-secrets.md) <br/> [Tjänstkryptering med kundnyckel](customer-key-overview.md) <br/> |
|Filer som överförs mellan användare. Dessa filer kan innehålla Office dokument eller SharePoint objekt som delas mellan användare.  <br/> |TLS för filer som överförs  <br/> |[Data Encryption in OneDrive for Business and SharePoint Online](data-encryption-in-odb-and-spo.md) <br/> [Skype för företag Online: Säkerhet och arkivering](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features) <br/> |
|E-post som skickas mellan mottagare. Det här e-postmeddelandet innehåller e-post som Exchange Online.  <br/> |Meddelandekryptering i Office 365 med Azure Rights Management, S/MIME och TLS för e-post som överförs  <br/> |[Meddelandekryptering i Office 365 (OME)](ome.md) <br/> [E-postkryptering i Office 365](email-encryption.md) <br/> [Hur Exchange Online använder TLS för att säkra e-postanslutningar i Office 365](exchange-online-uses-tls-to-secure-email-connections.md) <br/> |
|Chattar, meddelanden och filer som överförs mellan mottagare med Microsoft Teams. <br/> |Teams TLS och MTLS för att kryptera snabbmeddelanden. Mediatrafiken krypteras med SRTP (Secure RTP). Teams använder FIPS-kompatibla algoritmer (Federal Information Processing Standard) för kryptering av nyckelutbyten. <br/> |[Kryptering för Teams](/microsoftteams/teams-security-guide#encryption-for-teams) <br/> |

## <a name="what-if-i-need-more-control-over-encryption-to-meet-security-and-compliance-requirements"></a>Vad händer om jag behöver mer kontroll över kryptering för att uppfylla säkerhets- och efterlevnadskraven?

Microsoft 365 microsoft-hanterade lösningar för volymkryptering, filkryptering och postlådans kryptering i Office 365. Dessutom tillhandahåller Microsoft krypteringslösningar som du kan hantera och styra. Dessa krypteringslösningar bygger på Azure.
  
Mer information finns i följande resurser:
  
- [Vad är Azure Rights Management?](/information-protection/understand-explore/what-is-azure-rms)

- [Aktivera Rättighetshantering i administrationscentret](../enterprise/activate-rms-in-microsoft-365.md)

- [Set up Information Rights Management (IRM) in SharePoint admin center](set-up-irm-in-sp-admin-center.md)

- [Tjänstkryptering med Kundnyckel i Office 365](customer-key-overview.md)

- [Dubbelnyckelkryptering för Microsoft 365](double-key-encryption.md)

## <a name="how-do-i"></a>Hur ska jag...

|**Om du vill göra det här**|**Se de här resurserna**|
|:-----|:-----|
|Konfigurera kryptering för min organisation  <br/> |[Konfigurera kryptering i Office 365 Enterprise](set-up-encryption.md) <br/> |
|Visa information om certifikat, tekniker och TLS-chiffersviter <br/> |[Teknisk information om kryptering](technical-reference-details-about-encryption.md) <br/> |
|Arbeta med krypterade meddelanden på en mobil enhet  <br/> |[Visa krypterade meddelanden på en Android-enhet](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb) <br/> [Visa krypterade meddelanden på din iPhone eller iPad](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf) <br/> |
|Kryptera ett dokument med lösenordsskydd  <br/><br/>  Lösenordsskydd stöds inte i en webbläsare. Använd skrivbordsversioner av Word, Excel och PowerPoint för lösenordsskydd. |[Lägga till eller ta bort skydd i dokument, arbetsböcker eller presentationer](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826) <br/> Välj avsnittet **Lägg till** skydd och läs sedan Kryptera **med lösenord.**  |
|Ta bort kryptering från ett dokument  <br/> |[Lägga till eller ta bort skydd i dokument, arbetsböcker eller presentationer](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826) <br/> Välj avsnittet **Ta bort skydd** och se Ta bort **lösenordskryptering**.  |


## <a name="related-topics"></a>Relaterade ämnen

[Planera Microsoft 365 funktioner för säkerhet och informationsskydd](plan-for-security-and-compliance.md)

[De 10 bästa sätten att skydda Microsoft 365 för företag-abonnemang](/office365/admin/security-and-compliance/secure-your-business-data)

[Kryptering och uppspelning av Microsoft Stream Video-nivå](/stream/network-overview#video-level-encryption-and-playback-flow)