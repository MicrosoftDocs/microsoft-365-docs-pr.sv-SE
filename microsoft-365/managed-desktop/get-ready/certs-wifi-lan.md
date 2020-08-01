---
title: Förbereda certifikat och nätverks profiler för Microsoft Hanterat skrivbord
description: certs/wifi/lan
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: c7c57861986d275165484ae726140720a75da88e
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/30/2020
ms.locfileid: "46530037"
---
# <a name="prepare-certificates-and-network-profiles-for-microsoft-managed-desktop"></a>Förbereda certifikat och nätverks profiler för Microsoft Hanterat skrivbord  
 
Certifikatbaserad autentisering är ett vanligt krav för kunder som använder Microsoft Managed Desktop. Du kan kräva att certifikat för att komma åt Wi-Fi eller LAN, ansluta till VPN-lösningar eller för att komma åt interna resurser i organisationen.   
 
Eftersom Microsoft Managed Desktop-enheter är anslutna till Azure Active Directory (Azure AD) och hanteras av Microsoft Intune måste du distribuera sådana certifikat med hjälp av en SCEP-certifikat ( Simple Certificate Enrollment Protocol) eller PKCS-certifikatinfrastruktur (Public Key Cryptography Standard) som är integrerad med Intune.    
 
## <a name="certificate-requirements"></a>Krav på certifikat 
 
Rotcertifikat krävs för att distribuera certifikat via en SCEP- eller PKCS-infrastruktur. Andra program och tjänster i organisationen kan kräva att rotcertifikat distribueras till dina Microsoft-hanterade stationära enheter.    
 
Innan du distribuerar SCEP- eller PKCS-certifikat till Microsoft Managed Desktop bör du samla in krav för varje tjänst som kräver ett användar- eller enhetscertifikat i organisationen. Om du vill göra det enklare kan du använda någon av följande planeringsmallar:  
 
- [PKCS-certifikatmall](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/PKCS-certificate-template.xlsx) 
- [Mall för SCEP-certifikat](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/SCEP-certificate-template.xlsx)

>[!NOTE]
>För närvarande stöds endast SCEP-certifikatprofiler för distribution av Wi-Fi-profiler till Microsoft Managed Desktop när du använder en EAP-typ. PKCS-certifikatprofiler stöds inte. Se [Lägga till Wi-Fi-inställningar för Windows 10-enheter i Intune](https://docs.microsoft.com/intune/wi-fi-settings-windows) som referens.

  
## <a name="wi-fi-connectivity-requirements"></a>Wi-Fi-anslutningskrav

Om du vill att en enhet automatiskt ska kunna levereras med den Wi-Fi-konfiguration som krävs för företagsnätverket kan du behöva en Konfigurationsprofil för Wi-Fi. Du kan konfigurera Microsoft Managed Desktop så att de distribuerar dessa profiler till dina enheter. Om nätverkssäkerheten kräver att enheter ska ingå i den lokala domänen kan du också behöva utvärdera din Wi-Fi-nätverksinfrastruktur för att se till att den är kompatibel med Microsoft Managed Desktop-enheter (Microsoft Managed Desktop-enheter endast är Azure AD-anslutna). 
 
Innan du distribuerar en Wi-Fi-konfiguration till Microsoft Hanterade stationära enheter måste du samla in organisationens krav för varje Wi-Fi-nätverk. För att göra detta enklare kan du använda den här [WiFi-profilmallen](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/WiFi-profile-template.xlsx).
 
 
## <a name="wired-connectivity-requirements-and-8021x-authentication"></a>Krav på kabelanslutning och 802.1x-autentisering 
 
Om du använder 802.1x-autentisering för att skydda åtkomst från enheter till ditt lokala nätverk (LAN) måste du skicka den konfigurationsinformation som krävs till dina Microsoft Managed Desktop-enheter. Microsoft Hanterade stationära enheter som kör Windows 10, version 1809 eller senare stöder distribution av en 802.1x-konfiguration via WiredNetwork-konfigurationstjänstleverantören (CSP). Mer information finns i [Dokumentationen till WiredNetwork CSP.](https://docs.microsoft.com/windows/client-management/mdm/wirednetwork-csp) 
 
Innan du distribuerar en kabelansluten nätverkskonfigurationsprofil till Microsoft Managed Desktop-enheter samlar du organisationens krav för ditt kabelanslutna företagsnätverk. Gör så här: 
 
 
1. Logga in på en enhet som har din befintliga 802.1x-profil konfigurerad och är ansluten till LAN-nätverket.  
2. Öppna en kommandotolk med administratörsbehörighet. 
3. Hitta LAN-gränssnittets namn genom att köra **netsh-gränssnittet visa gränssnitt**. 
4. Exportera LAN-profilens XML genom att köra **netsh lan exportprofilmapp=.  Interface="interface_name"**. 
5. Om du behöver testa den exporterade profilen på Microsoft Managed Desktop-enhet kör du **netsh lan add profile filename="PATH_AND_FILENAME.xml" interface="INTERFACE_NAME".** 
 
 
## <a name="deploy-certificate-infrastructure"></a>Distribuera certifikatinfrastruktur  
 
Om du redan har en befintlig SCEP- eller PKCS-infrastruktur med Intune och detta uppfyller dina krav kan du också använda den för Microsoft Managed Desktop. Om det inte finns någon SCEP- eller PKCS-infrastruktur måste du förbereda en.  
 
Mer information finns i [Konfigurera en certifikatprofil för dina enheter i Microsoft Intune](https://docs.microsoft.com/intune/certificates-configure). 
 
 
 
## <a name="deploy-a-lan-profile"></a>Distribuera en LAN-profil 
 
När din LAN-profil har exporterats kan du förbereda principen för Microsoft Managed Desktop genom att följa dessa steg:   
 
1. Skapa en anpassad profil i Microsoft Intune för LAN-profilen med hjälp av följande inställningar (se [Använda anpassade inställningar för Windows 10-enheter i Intune](https://docs.microsoft.com/intune/custom-settings-windows-10)). I **Anpassade OMA-URI-inställningar**väljer du **Lägg till**och anger sedan följande värden: 
    - Namn: *Modern Workplace-Windows 10 LAN Profile* 
    - Beskrivning: Ange en beskrivning som ger en översikt över inställningen och andra viktiga detaljer. 
    - OMA-URI (skiftlägeskänslig): Ange *./Device/Vendor/MSFT/WiredNetwork/LanXML*
    - Datatyp: välj **Sträng (XML-fil)**. 
    - Anpassad XML: Ladda upp den exporterade XML-filen.
2. Skicka en supportbegäran till Microsoft Managed Desktop IT Operations med hjälp av Microsoft Managed Desktop Admin portal för att granska och distribuera konfigurationsprofilen till "Modern Workplace Devices – Test". Microsoft Managed Desktop IT Operations meddelar dig när begäran har slutförts via supportbegäran i administratörsportalen.
 
## <a name="deploy-certificates-and-wi-fivpn-profile"></a>Distribuera certifikat och Wi-Fi/VPN-profil 
 
 
Så här distribuerar du certifikat och profiler:

1. Skapa en profil för vart och ett av rot- och mellanliggande certifikat (se [Skapa betrodda certifikatprofiler](https://docs.microsoft.com/intune/protect/certificates-configure#step-3-create-trusted-certificate-profiles). Var och en av dessa profiler måste ha en beskrivning som innehåller ett utgångsdatum i DD/MM/YYYY-format. **Certifikatprofiler utan utgångsdatum kommer inte att distribueras.**
2. Skapa en profil för varje SCEP- eller PKCS-certifikat (se [Skapa en SCEP-certifikatprofil](https://docs.microsoft.com/intune/protect/certificates-scep-configure#create-a-scep-certificate-profile) eller [Skapa en PKCS-certifikatprofil](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)) Var och en av dessa profiler måste ha en beskrivning som innehåller ett utgångsdatum i DD/MM/YYYY-format. **Certifikatprofiler utan utgångsdatum kommer inte att distribueras.**
3. Skapa en profil för varje företagswidnätverk (se [Wi-Fi-inställningar för Windows 10 och senare enheter](https://docs.microsoft.com/intune/wi-fi-settings-windows)).
4. Skapa en profil för varje företags-VPN (se inställningarna för [Windows 10 och Windows Holographic device för att lägga till VPN-anslutningar med Intune](https://docs.microsoft.com/intune/vpn-settings-windows-10)).
5. Skicka en supportbegäran med titeln "Certifikatdistribution" eller "Wi-Fi-profildistribution" till Microsoft Managed Desktop IT Operations med hjälp av Microsoft Managed Desktop Admin portal för att granska och distribuera konfigurationsprofilen till "Modern Workplace Devices – Test". Microsoft Managed Desktop IT Operations meddelar dig när begäran har slutförts via supportbegäran i administratörsportalen. 
 
 
