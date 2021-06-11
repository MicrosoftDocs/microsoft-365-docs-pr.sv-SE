---
title: Inaktivera TLS 1.0 och 1.1 för Microsoft 365
description: Beskriver utfasningen av TLS 1.0 och 1.1 för Microsoft 365.
author: workshay
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: fasqiu
ms.reviewer: krowley
appliesto:
- Microsoft 365 Apps for enterprise
- Office 365 Business
- Office 365 Personal
- Office Online Server
- Office Web Apps
ms.openlocfilehash: 870572a61c241d3d3c8ce6791cee77edba2a1956
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "52332684"
---
# <a name="disabling-tls-10-and-11-for-microsoft-365"></a>Inaktivera TLS 1.0 och 1.1 för Microsoft 365

> [!IMPORTANT]
> Vi har tillfälligt stoppat inaktiveringen av TLS 1.0 och 1.1 för kommersiella kunder på grund av COVID-19. När leveranskedjor har justerats och vissa länder öppnats igen startade vi om distributionen av TLS 1.2 den 15 oktober 2020. Utrullningen fortsätter under de kommande veckorna och månaderna.

Efter den 31 oktober 2018 är TLS (Transport Layer Security) 1.0- och 1.1-protokoll inaktuella för Microsoft 365 tjänsten. Effekten för slutanvändarna är minimal. Den här ändringen har gjorts i över två år med det första offentliga meddelandet i december 2017. Den här artikeln är endast avsedd för den lokala Office 365-klienten i relation till Office 365-tjänsten, men kan även gälla för lokala TLS-problem med Office och Office Online Server/Office Web Apps.

För SharePoint och OneDrive måste du uppdatera och konfigurera .NET med stöd för TLS 1.2. Mer information finns i [Aktivera TLS 1.2 på klienter.](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)

## <a name="office-365-and-tls-overview"></a>Office 365 och TLS – översikt

Den Office är beroende av win-Windows (Windows) för att skicka och ta emot trafik via TLS-protokoll. Klient Office använda TLS 1.2 om webbtjänsten på den lokala datorn kan använda TLS 1.2. Alla Office kan använda TLS-protokoll eftersom TLS- och SSL-protokoll är en del av operativsystemet och inte är specifika för Office klienten.

### <a name="on-windows-8-and-later-versions"></a>I Windows 8 och senare versioner

Som standard är protokollen TLS 1.2 och 1.1 tillgängliga om inga nätverksenheter är konfigurerade att avvisa TLS 1.2-trafik.

### <a name="on-windows-7"></a>På Windows 7

TLS 1.1- och 1.2-protokoll är inte tillgängliga utan [UPPDATERINGEN KB 3140245.](https://support.microsoft.com/help/3140245) Uppdateringen åtgärdar problemet och lägger till följande registerundernyckel:

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp
```

> [!NOTE]
> Windows 7 användare som inte har den här uppdateringen påverkas efter den 31 oktober 2018. [KB 3140245](https://support.microsoft.com/help/3140245) innehåller information om hur du ändrar WINHTTP-inställningar för att aktivera TLS-protokoll.

#### <a name="more-information"></a>Mer information

Värdet för registernyckeln **DefaultSecureProtocols** som kb-artikeln beskriver avgör vilka nätverksprotokoll som kan användas:

|DefaultSecureProtocols-värde|Protokoll aktiverat|
|-|-|
|0x00000008|Aktivera SSL 2.0 som standard|
|0x00000020|Aktivera SSL 3.0 som standard|
|0x00000080|Aktivera TLS 1.0 som standard|
|0x00000200|Aktivera TLS 1.1 som standard|
|0x00000800|Aktivera TLS 1.2 som standard|

## <a name="office-clients-and-tls-registry-keys"></a>Office klienter och TLS-registernycklar

Läs KB [4057306](https://support.microsoft.com/help/4057306)Förbereda för obligatorisk användning av TLS 1.2 i Office 365. Det här är en allmän artikel för IT-administratörer och är officiell dokumentation om ändringen TLS 1.2.

I följande tabell visas lämpliga registernyckelvärden i Office 365 klienter efter den 31 oktober 2018.

|Protokoll som är Office 365 tjänst efter den 31 oktober 2018|Hexadecimalt värde|
|-|-|
|TLS 1,0 + 1,1 + 1,2|0x00000A80|
|TLS 1.1 + 1.2|0x00000A00|
|TLS 1,0 + 1,2|0x00000880|
|TLS 1.2|0x00000800|

> [!IMPORTANT]
> Använd inte SSL 2.0- och 3.0-protokoll, som också kan ställas in med hjälp av **nyckeln DefaultSecureProtocols.** SSL 2.0 och 3.0 anses vara inaktuella och osäkra protokoll. Det bästa är att sluta använda SSL 2.0 och SSL 3.0, även om beslutet att göra det i slutänden beror på vad som bäst uppfyller dina produktbehov. Mer information om säkerhetsproblem med SSL 3.0 finns i [KB 3009008.](https://support.microsoft.com/help/3009008)

Du kan använda standardkalkylatorn Windows i programmerarläge till att konfigurera samma registernyckelvärden för referens. Mer information finns i KB 3140245 Uppdatering för att aktivera [TLS 1.1 och TLS 1.2](https://support.microsoft.com/help/3140245)som en standard säker protokoll i WinHTTP i Windows.

Oavsett om Windows 7-uppdateringen ([KB 3140245)](https://support.microsoft.com/help/3140245)är installerad eller inte finns inte registerundernyckeln DefaultSecureProtocols och måste läggas till manuellt eller via ett grupprincipobjekt (GPO). Den här nyckeln krävs inte, såvida du inte behöver anpassa vilka säkra protokoll som är aktiverade eller begränsade. Du behöver bara Windows 7 SP1 ([KB 3140245](https://support.microsoft.com/help/3140245)) uppdatering.

## <a name="update-and-configure-the-net-framework-to-support-tls-12"></a>Uppdatera och konfigurera .NET Framework TLS 1.2

Du måste uppdatera program som anropar Microsoft 365 API:er via TLS 1.0 eller TLS 1.1 för att använda TLS 1.2. .NET 4.5 blir TLS 1.1 som standard. Om du vill uppdatera .NET-konfigurationen går du till [Aktivera TLS (Transport Layer Security) 1.2 på klienter.](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)

## <a name="more-information"></a>Mer information

Mer information finns i Förbereda [för obligatorisk användning av TLS 1.2 i Office 365.](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)

## <a name="references"></a>Referenser

Följande resurser innehåller vägledning för att se till att dina klienter använder TLS 1.2 eller senare och inaktiverar TLS 1.0 och 1.1:

- Se till att TLS 1.2 är det förinställda säkra protokollet i WinHTTP i Windows för Windows 7-klienter som ansluter till Office 365. Mer information finns i KB 3140245 – Uppdatering för att aktivera [TLS 1.1 och TLS 1.2](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in)som standard för säkra protokoll i WinHTTP i Windows.
- För att hantera svag TLS-användning genom att ta bort TLS 1.0- och 1.1-beroenden, se [TLS 1.2-stöd på Microsoft.](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)
- [Nya IIS-funktioner](https://cloudblogs.microsoft.com/microsoftsecure/2017/09/07/new-iis-functionality-to-help-identify-weak-tls-usage/) gör det lättare att hitta kunder på [Windows Server 2012 R2](https://support.microsoft.com/help/4025335/windows-8-1-windows-server-2012-r2-update-kb4025335) och [Windows Server 2016](https://support.microsoft.com/help/4025334/windows-10-update-kb4025334) att ansluta till tjänsten med hjälp av svag säkerhetsprotokoll.
- Få mer information om hur du [löser TLS 1.0-problemet.](https://www.microsoft.com/download/details.aspx?id=55266)
- Allmän information om vår inställning till säkerhet, gå till [Office 365 Säkerhetscenter](https://www.microsoft.com/trustcenter/cloudservices/office365).
- [Förbereder för utfasning av TLS 1.0/1.1 – Office 365, Skype för företag](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/ba-p/222247)
- [Vägledning för Exchange Server TLS, del 1: Gör dig redo för TLS 1.2](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/ba-p/607649)
- [Vägledning för Exchange Server TLS, del 2: Aktivera TLS 1.2 och identifiera klienter som inte använder den](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-2-enabling-tls-1-2-and/ba-p/607761)
- [Vägledning för Exchange Server TLS, del 3: Inaktivera TLS 1.0/1.1](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-3-turning-off-tls-1-0-1-1/ba-p/607898)
- [Aktivera stöd för TLS 1.1 och 1.2 i Office Online Server](/officeonlineserver/enable-tls-1-1-and-tls-1-2-support-in-office-online-server)

