---
title: Förbereda för TLS 1.2 i Office 365 och Office 365 GCC
description: Hur man förbereder sig för att använda TLS 1.2 för alla kombinationer av klient- och webbläsarservrar i Office 365 och Office 365 GCC efter support för TLS 1.0 och 1.1 är inaktiverat.
author: kccross
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: shmehta
ms.reviewer: krowley
appliesto:
- Office 365 Business
ms.openlocfilehash: 331dd1ea510983e57c069f8d142aa0f7d3f7062e
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226089"
---
# <a name="preparing-for-tls-12-in-office-365-and-office-365-gcc"></a>Förbereda för TLS 1.2 i Office 365 och Office 365 GCC

## <a name="summary"></a>Sammanfattning

För att tillhandahålla kryptering som är bäst i sin klass till våra kunder planerar Microsoft att avskriva TLS-versionerna (Transport Layer Security) 1.0 och 1.1 i Office 365 och Office 365 GCC. Vi förstår att din data är viktig, och vi är måna om transparensen om ändringar som kan påverka din användning av tjänsten TLS.

Den [Microsoft TLS 1.0 genomförandet](https://support.microsoft.com/help/3117336/schannel-implementation-of-tls-1-0-in-windows-security-status-update-n) har inga kända säkerhetsproblem. Men på grund av potentialen för framtida nedgraderingsattacker av protokoll och andra TLS-sårbarheter avbryter vi stödet för TLS 1.0 och 1.1 i Microsoft Office 365 och Office 365 GCC.

Se följande faktablad för information om hur du tar bort TLS 1.0- och 1.1-beroenden: [Lösa problemet med TLS 1.0](https://www.microsoft.com/download/details.aspx?id=55266).

## <a name="more-information"></a>Mer information

Vi har redan börjat utfasningen av TLS 1.0 och 1.1 från och med januari 2020. Klienter, enheter eller tjänster som ansluter till Office 365 via TLS 1.0 eller 1.1 i våra DoD- eller GCC-avancerade instanser stöds inte. För våra kommersiella kunder med Office 365 börjar utfasningen av TLS 1.0 och 1.1 den 15 oktober 2020 och utfasningen fortsätter under de kommande veckorna och månaderna. 

Vi rekommenderar att alla kombinationer av klient- och webbläsarservrar använder TLS 1.2 (eller en senare version) för att behålla anslutningen till Office 365-tjänster. Du kan behöva uppdatera vissa kombinationer av klient- och webbläsarservrar.

Du måste uppdatera program som anropar Microsoft 365 API:er via TLS 1.0 eller TLS 1.1 för att använda TLS 1.2. .NET 4.5 blir TLS 1.1 som standard. Om du vill uppdatera .NET-konfigurationen går du till [Aktivera TLS (Transport Layer Security) 1.2 på klienter.](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)

Följande klienter är kända för att inte använda TLS 1.2. Uppdatera dessa kunder för att säkerställa oavbruten tillgång till tjänsten.

- Android 4.3 och tidigare versioner
- Firefox version 5.0 och tidigare versioner
- Internet Explorer 8-10 på Windows 7 och tidigare versioner
- Internet Explorer 10 på Windows Phone 8
- Safari 6.0.4/OS X10.8.4 och tidigare versioner

### <a name="tls-12-for-microsoft-teams-rooms-and-surface-hub"></a>TLS 1.2 för Microsoft Teams Rum och Surface Hub

Microsoft Teams Rum (tidigare kallad Skype Room System V2 SRS V2) har haft stöd för TLS 1.2 sedan december 2018. Vi rekommenderar att Rum-enheter har appen Microsoft Teams Rum version 4.0.64.0 eller senare installerad. Se [Viktig information](/microsoftteams/room-systems/srs2-release-note) för mer information. Ändringarna är bakåt- och framåtkompatibla.

Surface Hub släppte stöd för TLS 1.2 i maj 2019.

TLS 1.2-stöd för Microsoft Teams Rum- och Surface Hub-produkter kräver också följande kodändringar på serversidan:

- Ändringar av Skype för företag – Online-servern blev aktiva i april 2019. Nu har Skype för företag – Online stöd för att ansluta till Microsoft Teams Rum- och Surface Hub-enheter med hjälp av TLS 1.2.
- Kunder med Skype för företag – Server måste installera en kumulativ uppdatering (CU) för att kunna använda TLS 1.2 för system med Teams Rum och Surface Hub.

  - För Skype för företag – Server 2015 släpptes CU9 redan i maj 2019.
  - För Skype för företag – Server 2019 var CU1 tidigare planerad till april 2019 men är försenad till juni 2019.

  > [!NOTE]
  > Kunder med Skype för företag lokalt bör inte inaktivera TLS 1.0/1.1 innan specifika CU:er för Skype för företag – Server installeras.

Om du använder någon lokal infrastruktur för hybridscenarier eller Active Directory Federation Services, se till att infrastrukturen kan stödja både inkommande och utgående anslutningar som använder TLS 1.2.

## <a name="references"></a>Referenser

Följande resurser ger vägledning för att se till att dina klienter använder TLS 1.2 eller senare och inaktivera TLS 1.0 och 1.1.

- Se till att TLS 1.2 är det förinställda säkra protokollet i WinHTTP i Windows för Windows 7-klienter som ansluter till Office 365. För mer information se [KB 3140245 - uppdatering att aktivera TLS 1.1 och 1.2 TLS som standard säkerhetsprotokoll i WinHTTP i Windows](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in).
- [TLS-chiffersviter som stöds av Office 365](/microsoft-365/compliance/technical-reference-details-about-encryption#tls-cipher-suites-supported-by-office-365)
- För att börja ta itu med svaga TLS genom att ta bort TLS 1.0 och 1.1 beroenden, se [TLS 1.2 stöd på Microsoft](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/).
- [Nya IIS-funktioner](https://cloudblogs.microsoft.com/microsoftsecure/2017/09/07/new-iis-functionality-to-help-identify-weak-tls-usage/) gör det lättare att hitta kunder på [Windows Server 2012 R2](https://support.microsoft.com/help/4025335/windows-8-1-windows-server-2012-r2-update-kb4025335) och [Windows Server 2016](https://support.microsoft.com/help/4025334/windows-10-update-kb4025334) att ansluta till tjänsten med hjälp av svag säkerhetsprotokoll.
- Få mer information om hur du [löser TLS 1.0-problemet.](https://www.microsoft.com/download/details.aspx?id=55266)
- Allmän information om vår inställning till säkerhet, gå till [Office 365 Säkerhetscenter](https://www.microsoft.com/trustcenter/cloudservices/office365).
- [Förbereder för utfasning av TLS 1.0/1.1 – Office 365, Skype för företag](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/ba-p/222247)
- [Vägledning för Exchange Server TLS, del 1: Gör dig redo för TLS 1.2](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/ba-p/607649)
- [Vägledning för Exchange Server TLS, del 2: Aktivera TLS 1.2 och identifiera klienter som inte använder den](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-2-enabling-tls-1-2-and/ba-p/607761)
- [Vägledning för Exchange Server TLS, del 3: Inaktivera TLS 1.0/1.1](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-3-turning-off-tls-1-0-1-1/ba-p/607898)
- [Aktivera stöd för TLS 1.1 och 1.2 i Office Online Server](/officeonlineserver/enable-tls-1-1-and-tls-1-2-support-in-office-online-server)
