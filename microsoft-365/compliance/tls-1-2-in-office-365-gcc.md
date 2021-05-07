---
title: Inaktivera TLS 1.0 och 1.1 i Microsoft 365 GCC High och DoD
description: Här diskuteras hur Microsoft inaktiverar stöd för TLS 1.1 och 1.0 i GCC High- och DoD-miljöer i Microsoft 365.
author: kccross
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.collection: M365-security-compliance
ms.service: information-protection
ms.topic: article
ms.reviewer: krowley
ms.author: krowley
appliesto:
- Office 365 Business
ms.openlocfilehash: 16a02985107c5f578d6d6c21bf2efc6e80297951
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162035"
---
# <a name="disabling-tls-10-and-11-in-microsoft-365-gcc-high-and-dod"></a>Inaktivera TLS 1.0 och 1.1 i Microsoft 365 GCC High och DoD

## <a name="summary"></a>Sammanfattning

I syfte att uppfylla de senaste standarderna för Federal Risk and Authorization Management Program (FedRAMP) inaktiverar vi TLS-versionerna 1.1 och 1.0 i Microsoft 365 för GCC High- och DoD-miljöer. Den här ändringen meddelades tidigare via Microsoft Support i Förbereda för obligatorisk användning [av TLS 1.2 i Office 365.](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)

Säkerheten för dina data är viktig och vi strävar efter transparens kring ändringar som kan påverka din användning av tjänsten.

Även om [implementeringen av Microsoft TLS 1.0](https://support.microsoft.com/help/3117336) inte har några kända säkerhetsproblem förblir vi engagerade i FedRAMP-efterlevnadsstandarder. Därför inaktiverade vi TLS 1.1 och 1.0 i Microsoft 365 i GCC High- och DoD-miljöer den 15 januari 2020. Mer information om hur du tar bort beroenden för TLS 1.1 och 1.0 finns i följande informationsdokument:

[Lösa TLS 1.0-problemet](https://www.microsoft.com/download/details.aspx?id=55266)

## <a name="more-information"></a>Mer information

Från och med den 15 januari 2020 Microsoft 365 I GCC High- och DoD-miljöer inaktiveras TLS 1.1 och 1.0.

Före den 15 januari 2020 ska alla kombinationer av klientservrar och webbläsarservrar använda TLS version 1.2 (eller en senare version) för att säkerställa att alla anslutningar kan göras utan problem Microsoft 365. Detta kan kräva uppdateringar av vissa kombinationer av klientservrar och webbläsarservrar.

För SharePoint och OneDrive måste du uppdatera och konfigurera .NET med stöd för TLS 1.2. Mer information finns i [Aktivera TLS 1.2 på klienter.](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)

Du måste uppdatera klientdatorerna för att säkerställa att du har kontinuerlig åtkomst till Office 365 GCC Hög och DoD.

Du måste uppdatera program som anropar Microsoft 365 API:er via TLS 1.0 eller TLS 1.1 för att använda TLS 1.2. .NET 4.5 blir TLS 1.1 som standard. Om du vill uppdatera .NET-konfigurationen går du till [Aktivera TLS (Transport Layer Security) 1.2 på klienter.](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client) Mer information finns i Förbereda [för obligatorisk användning av TLS 1.2 i Office 365.](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)

Vi vet att följande klientprogram inte kan använda TLS 1.2:

- Android 4.3 och tidigare versioner
- Firefox version 5.0 och tidigare versioner
- Internet Explorer 8–10 på Windows 7 och tidigare versioner
- Internet Explorer 10 på Windows Phone 8.0
- Safari 6.0.4/OS X 10.8.4 och tidigare versioner

Även om den aktuella analysen av anslutningar till Microsoft Online-tjänster visar att de flesta tjänster och slutpunkter ser mycket lite TLS 1.1- och 1.0-användning, tillhandahåller vi ett meddelande om den här ändringen så att du kan uppdatera berörda klienter eller servrar efter behov innan stödet för TLS 1.1 och 1.0 upphör. Om du använder en lokal infrastruktur för hybridscenarier eller AD FS (Active Directory Federation Services) ska du kontrollera att infrastrukturen har stöd för både inkommande och utgående anslutningar som använder TLS 1.2 (eller en senare version).

Utöver avbrott som kan hända om du använder de angivna klienterna som inte kan använda TLS 1.2 kommer borttagning av TLS 1.1 och 1.0 att hindra dig från att använda följande Microsoft-produkt:

- Lync-telefon

## <a name="references"></a>Referenser

Vägledning och referenser som hjälper till att säkerställa att klienterna använder TLS 1.2 finns i Förbereda för obligatorisk användning av [TLS 1.2 i Office 365.](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)