---
title: Hur Exchange Online TLS för att skydda e-postanslutningar
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/2/2018
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4cde0cda-3430-4dc0-b489-f2c0736c929f
ms.collection:
- M365-security-compliance
- Strat_O365_IP
description: Lär dig Exchange Online och Microsoft 365 att använda TLS (Transport Layer Security) och FS (ForwardS) för att skydda e-postkommunikation. Du får också information om det certifikat som utfärdats av Microsoft för Exchange Online.
ms.openlocfilehash: cc7ca631f9322fdc8a85cfaba197e63d06d08aee
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161934"
---
# <a name="how-exchange-online-uses-tls-to-secure-email-connections"></a>Hur Exchange Online TLS för att skydda e-postanslutningar

Lär dig Exchange Online och Microsoft 365 att använda TLS (Transport Layer Security) och FS (ForwardS) för att skydda e-postkommunikation. Innehåller även information om det certifikat som utfärdats av Microsoft för Exchange Online.
  
## <a name="tls-basics-for-microsoft-365-and-exchange-online"></a>Grunderna i TLS för Microsoft 365 och Exchange Online

Transport Layer Security (TLS) och SSL som följde före TLS är kryptografiska protokoll som skyddar kommunikationen över ett nätverk genom att använda säkerhetscertifikat för att kryptera en anslutning mellan datorer. TLS ersätter SSL (Secure Sockets Layer) och kallas ofta SSL 3.1. För Exchange Online använder vi TLS för att kryptera anslutningarna mellan våra Exchange-servrar och anslutningarna mellan våra Exchange-servrar och andra servrar, till exempel dina lokala Exchange-servrar eller mottagarnas e-postservrar. När anslutningen är krypterad skickas alla data som skickas genom anslutningen via den krypterade kanalen. Om du vidarebefordrar ett meddelande som skickats via en TLS-krypterad anslutning är meddelandet inte nödvändigtvis krypterat. Det beror på att meddelandet inte krypteras med TLS, bara anslutningen.
  
Om du vill kryptera meddelandet måste du använda en krypteringsteknik som krypterar innehållet i meddelandet, till exempel något som Office meddelandekryptering. Mer [information om alternativen för Office 365](email-encryption.md) och Meddelandekryptering i Office 365 [finns](ome.md) i E-postkryptering i Office 365. 
  
Vi rekommenderar att du använder TLS i situationer där du vill skapa en säker kanal för korrespondens mellan Microsoft och din lokala organisation eller en annan organisation, t.ex. en partner. Exchange Online alltid försöker använda TLS först för att skydda din e-post, men kan inte alltid göra detta om den andra parten inte erbjuder TLS-säkerhet. Läs vidare för att ta reda på hur du kan skydda all e-post till dina lokala servrar eller viktiga partner genom att *använda kopplingar.* 

För att våra kunder ska få bästa möjliga kryptering har Microsoft inaktuella TLS-versioner (Transport Layer Security) versionerna 1.0 och 1.1 [i Office 365](tls-1.0-and-1.1-deprecation-for-office-365.md) [och Office 365 GCC.](tls-1-2-in-office-365-gcc.md) Du kan dock fortsätta att använda en okrypterad SMTP-anslutning utan TLS. Vi rekommenderar inte e-postöverföring utan kryptering.  
  
## <a name="how-exchange-online-uses-tls-between-exchange-online-customers"></a>Hur Exchange Online använder TLS mellan Exchange Online kunder

Exchange Online krypterar alltid anslutningar till andra Exchange Online och dataservrar i våra datacenter med TLS 1.2. När du skickar e-post till en mottagare inom organisationen skickas det e-postmeddelandet automatiskt via en anslutning som är krypterad med TLS. Dessutom skickas all e-post som du skickar till andra kunder via anslutningar som krypteras med TLS och skyddas med vidarebefordran av kunder.
  
## <a name="how-microsoft-365-uses-tls-between-microsoft-365-and-external-trusted-partners"></a>Hur Microsoft 365 använder TLS mellan Microsoft 365 externa och betrodda partner

Som standard använder Exchange Online alltid opportunistisk TLS. Det innebär Exchange Online alltid försöker kryptera anslutningar med den säkraste versionen av TLS först, och sedan arbetar sig nedåt i listan med TLS-chiffer tills det hittar en som båda parter kan komma överens om. Om du inte har konfigurerat Exchange Online för att säkerställa att meddelanden till den mottagaren endast skickas via säkra anslutningar kommer meddelandet som standard att skickas okrypterat om mottagarorganisationen inte stöder TLS-kryptering. Opportunistisk TLS är tillräckligt för de flesta företag. För företag som har efterlevnadskrav, till exempel sjukvårds-, bank- eller myndighetsorganisationer, kan du konfigurera Exchange Online kräva eller tvinga TLS. Instruktioner finns i Konfigurera [e-postflöde med kopplingar i Office 365](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).
  
Om du bestämmer dig för att konfigurera TLS mellan din organisation och en betrodd partnerorganisation kan Exchange Online använda tvingad TLS för att skapa betrodda kommunikationskanaler. Tvingad TLS kräver att partnerorganisationen autentiserar sig för Exchange Online med ett säkerhetscertifikat för att kunna skicka e-post till dig. Din partner måste hantera sina egna certifikat för att kunna göra detta. I Exchange Online använder vi kopplingar för att skydda meddelanden som du skickar från obehörig åtkomst innan de kommer till mottagarens e-postleverantör. Information om hur du använder kopplingar för att konfigurera e-postflödet finns i [Konfigurera e-postflöde med kopplingar i Office 365](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).
  
## <a name="tls-and-hybrid-exchange-server-deployments"></a>TLS- och Exchange Server distributioner

Om du hanterar en hybrid-Exchange-distribution måste den lokala Exchange-servern autentiseras på Microsoft 365 med hjälp av ett säkerhetscertifikat för att kunna skicka e-post till mottagare vars postlådor endast finns i Office 365. Därför måste du hantera dina egna säkerhetscertifikat för dina lokala Exchange servrar. Du måste också på ett säkert sätt lagra och underhålla dessa servercertifikat. Mer information om hur du hanterar certifikat i hybriddistributioner finns [i Certifikatkrav för hybriddistributioner.](/exchange/certificate-requirements)
  
## <a name="how-to-set-up-forced-tls-for-exchange-online-in-office-365"></a>Ställa in tvingade TLS för Exchange Online i Office 365

För Exchange Online kunder måste du konfigurera flera kopplingar som kräver TLS för att kunna tvinga TLS att arbeta för att skydda all skickad och mottagen e-post. Du behöver en anslutare för e-post som skickas till dina användarpostlådor och en annan anslutare för e-post som skickas från dina användarpostlådor. Skapa dessa kopplingar i Exchange administrationscenter i Office 365. Instruktioner finns i Konfigurera [e-postflöde med kopplingar i Office 365](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).
  
## <a name="tls-certificate-information-for-exchange-online"></a>Information om TLS-certifikat för Exchange Online

Certifikatinformationen som används av Exchange Online beskrivs i följande tabell. Om din affärspartner ställer in tvingad TLS på sin e-postserver, måste du ge denna information till dem. Av säkerhetsskäl ändras våra certifikat då och då. Vi har distribuerat en uppdatering av vårt certifikat i våra datacenter. Det nya certifikatet är giltigt från den 3 september 2018.
  
 **Aktuell certifikatinformation som är giltig från den 3 september 2018**
  
| Attribut | Värde |
|:-----|:-----|
|Certifikatutfärdare rotutfärdare  <br/> |GlobalSign Root CA – R1 <br/> |
|Certifikatnamn  <br/> |mail.protection.outlook.com  <br/> |
|Organisation  <br/> |Microsoft Corporation  <br/> |
|Organisationsenhet  <br/> |  <br/> |
|Certifikatnyckelstyrka  <br/> |2048  <br/> |
   
 **Inaktuell certifikatinformation som är giltig till den 3 september 2018**
  
För att säkerställa en smidig övergång kommer vi att fortsätta att tillhandahålla den gamla certifikatinformationen för referensen en stund, men från och med nu bör du använda den aktuella certifikatinformationen.
  
****

| Attribut | Värde |
|:-----|:-----|
|Certifikatutfärdare rotutfärdare  <br/> |Baltimore CyberTrust Root  <br/> |
|Certifikatnamn  <br/> |mail.protection.outlook.com  <br/> |
|Organisation  <br/> |Microsoft Corporation  <br/> |
|Organisationsenhet  <br/> |Microsoft Corporation  <br/> |
|Certifikatnyckelstyrka  <br/> |2048  <br/> |
   
## <a name="prepare-for-the-new-exchange-online-certificate"></a>Förbereda det nya Exchange Online certifikatet

Det nya certifikatet har utfärdats av en annan certifikatutfärdare från det tidigare certifikatet som används av Exchange Online. Därför kan du behöva utföra vissa åtgärder för att kunna använda det nya certifikatet.

Det nya certifikatet kräver att du ansluter till slutpunkterna för den nya certifikatutfärdaren som en del av certifikatets validering. Om du inte gör det kan e-postflödet påverkas negativt. Om du skyddar dina e-postservrar med brandväggar som bara låter e-postservrarna ansluta till vissa destinationer behöver du kontrollera om servern kan validera det nya certifikatet. Bekräfta att servern kan använda det nya certifikatet genom att utföra följande steg:

1. Anslut till ditt lokala Exchange Server med Windows PowerShell och kör sedan följande kommando:  
  `certutil -URL https://crl.globalsign.com/gsorganizationvalsha2g3.crl`

1. I fönstret som visas väljer du **Hämta**.

1. När verktyget är klart sin kontroll returneras en status. Om statusen visar **OK** kan e-postservern verifiera det nya certifikatet. Om det inte gör det måste du avgöra vad som orsakar att anslutningarna misslyckas. Du måste förmodligen uppdatera inställningarna för en brandvägg. Den fullständiga listan över slutpunkter som behöver kommas åt är:
    - ocsp.globalsign.com
    - crl.globalsign.com
    - secure.globalsign.com   

Normalt får du uppdateringar av rotcertifikat automatiskt via Windows Uppdatering. Vissa distributioner har dock ytterligare säkerhet på plats som förhindrar att dessa uppdateringar sker automatiskt. I de här låsta distributionerna där Windows Update inte kan uppdatera rotcertifikat automatiskt måste du se till att rätt rotcertifikat har installerats genom att utföra följande steg:
1.  Anslut till ditt lokala Exchange Server med Windows PowerShell och kör sedan följande kommando:  
  `certmgr.msc`

2. Under **Trusted Root Certification Authority/Certificates** bekräftar du att det nya certifikatet visas.

## <a name="get-more-information-about-tls-and-microsoft-365"></a>Få mer information om TLS och Microsoft 365

En lista över chiffersviter som stöds finns i [Teknisk referensinformation om kryptering](technical-reference-details-about-encryption.md).
  
[Konfigurera kopplingar för säkert e-postflöde med en partnerorganisation](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)
  
[Kopplingar med förbättrad e-postsäkerhet](/previous-versions/exchange-server/exchange-150/dn942516(v=exchg.150))
  
[Kryptering i Microsoft 365](encryption.md)
