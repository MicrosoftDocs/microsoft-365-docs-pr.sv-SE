---
title: Förbereda certifikat och nätverks profiler för Microsoft Hanterat skrivbord
description: certifikat/WiFi/LAN
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
ms.openlocfilehash: 7a0af5db4e18bc46436ace6f9fefefc18f0ccd68
ms.sourcegitcommit: 51f040a4edb8dd52521a5d7b0f7a975986a1af10
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/10/2020
ms.locfileid: "46608281"
---
# <a name="prepare-certificates-and-network-profiles-for-microsoft-managed-desktop"></a>Förbereda certifikat och nätverks profiler för Microsoft Hanterat skrivbord  
 
Certifikatbaserad identifiering är ett gemensamt krav för kunder som använder Microsoft Managed Desktop. Du kanske behöver certifikat för att få åtkomst till Wi-Fi eller LAN, för att ansluta till VPN-lösningar eller för åtkomst till interna resurser i din organisation.   
 
Eftersom Microsoft Managed Station ära datorer är anslutna till Azure Active Directory (Azure AD) och hanteras av Microsoft Intune måste du distribuera sådana certifikat med hjälp av SCEP (Simple Certificate Enrollment Protocol) eller en PKCS (Public Key Cryptography Standard) infrastruktur som är integrerad med Intune.    
 
## <a name="certificate-requirements"></a>Certifikat krav 
 
Rot certifikat krävs för att distribuera certifikat via en SCEP-eller PKCS-infrastruktur. Andra program och tjänster i din organisation kan kräva att rot certifikat ska distribueras till Microsoft Managed Station ära datorer.    
 
Innan du distribuerar SCEP-eller PKCS-certifikat till Microsoft Managed Desktop bör du samla in krav för varje tjänst som kräver en användare eller ett enhets certifikat i organisationen. För att göra det enklare kan du använda någon av följande planeringsfunktioner:  
 
- [PKCS-certifikatmall](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/PKCS-certificate-template.xlsx) 
- [SCEP-certifikatmall](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/SCEP-certificate-template.xlsx)

>[!NOTE]
>För närvarande stöds endast SCEP certifikat profiler för distribution av trådlösa profiler till Microsoft Managed Desktop när du använder en EAP-typ. PKCS-certifikat profiler stöds inte. Se [lägga till WiFi-inställningar för Windows 10-enheter i Intune](https://docs.microsoft.com/intune/wi-fi-settings-windows) för referens.

  
## <a name="wi-fi-connectivity-requirements"></a>Krav för Wi-Fi-anslutning

Om du vill tillåta att en enhet automatiskt tillhandahålls med den nödvändiga WiFi-konfigurationen för ditt företags nätverk kan du behöva en konfigurations profil för WiFi. Du kan konfigurera Microsoft Managed Desktop så att dessa profiler distribueras till dina enheter. Om nätverks säkerheten kräver att enheter kan ingå i den lokala domänen kanske du måste utvärdera din Wi-Fi-nätverks infrastruktur för att kontrol lera att den är kompatibel med Microsoft Managed Station ära enheter (Microsoft Managed Station ära enheter). 
 
Innan du distribuerar en Wi-Fi-konfiguration till Microsoft Managed Station ära enheter måste du samla in organisationens krav för varje Wi-Fi-nätverk. För att göra det enklare kan du använda denna [WiFi-profil](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/WiFi-profile-template.xlsx).
 
 
## <a name="wired-connectivity-requirements-and-8021x-authentication"></a>Krav på tråd bunden anslutning och 802.1 x-verifikation 
 
Om du använder 802.1 x-verifikation för att skydda åtkomst från enheter till ditt lokala nätverk (LAN) måste du föra över nödvändig konfigurations information till Microsoft Managed Station ära datorer. Microsoft Managed Station ära datorer med Windows 10, version 1809 eller senare stöd för distribution av en 802.1 x-konfiguration via WiredNetwork-konfigurations tjänst leverantör (CSP). Mer information finns i dokumentationen för [WIREDNETWORK CSP](https://docs.microsoft.com/windows/client-management/mdm/wirednetwork-csp) . 
 
Innan du distribuerar en profil för kabelanslutna nätverk till Microsoft Managed Station ära enheter kan du samla organisationens krav för företagets nätverk. Gör så här: 
 
 
1. Logga in på en enhet som har din befintliga 802.1 x-profil konfigurerad och ansluten till det lokala nätverket.  
2. Öppna en kommando tolk med administratörs behörighet. 
3. Hitta namnet på LAN-gränssnittet genom att köra **netsh interface show interface**. 
4. Exportera LAN Profile XML genom att köra **Netsh LAN export Profile-mappen =.  Interface = "interface_name"**. 
5. Om du behöver testa den exporterade profilen på en Microsoft-hanterad stationär enhet kör du **Netsh LAN Add Profile filename = "PATH_AND_FILENAME.xml" Interface = "INTERFACE_NAME"**. 
 
 
## <a name="deploy-certificate-infrastructure"></a>Distribuera certifikat infrastruktur  
 
Om du redan har en befintlig SCEP-eller PKCS-infrastruktur med Intune och detta uppfyller dina krav kan du även använda den för Microsoft Managed Desktop. Om du inte redan har en SCEP-eller PKCS-infrastruktur måste du förbereda en.  
 
Mer information finns i [Konfigurera en certifikat profil för dina enheter i Microsoft Intune](https://docs.microsoft.com/intune/certificates-configure). 
 
 
 
## <a name="deploy-a-lan-profile"></a>Distribuera en LAN-profil 
 
När din LAN-profil har exporter ATS kan du förbereda principen för Microsoft Managed Desktop genom att följa de här stegen:   
 
1. Skapa en anpassad profil i Microsoft Intune för LAN-profilen med följande inställningar (se [använda anpassade inställningar för Windows 10-enheter i Intune](https://docs.microsoft.com/intune/custom-settings-windows-10)). I **anpassade OMA-URI-inställningar**väljer du **Lägg till**och anger sedan följande värden: 
    - Namn: *modern arbets plats – Windows 10 LAN-profil* 
    - Beskrivning: Ange en beskrivning av inställningen och annan viktig information. 
    - OMA-URI (Skift läges känsligt): retur *./Device/Vendor/MSFT/WiredNetwork/LanXML*
    - Datatyp: Välj **sträng (XML-fil)**. 
    - Anpassad XML: Ladda upp den exporterade XML-filen.
2. Skicka en supportbegäran till Microsoft Managed Desktop-programmet som använder Microsoft Managed Desktop admin-portalen för att granska och distribuera konfigurations profilen till moderna arbets plats enheter – test ". Microsoft-hanterad stationär dator IT-operationer gör att du vet när begäran är slutförd via supportavdelningen på administrations portalen.
 
## <a name="deploy-certificates-and-wi-fivpn-profile"></a>Distribuera certifikat och WiFi-profil 
 
 
Följ de här stegen om du vill distribuera certifikat och profiler:

1. Skapa en profil för varje rot-och mellanliggande certifikat (se [skapa principer för betrodda certifikat](https://docs.microsoft.com/intune/protect/certificates-configure#step-3-create-trusted-certificate-profiles). Var och en av dessa profiler måste ha en beskrivning som innehåller ett utgångs datum i formatet DD/MM/ÅÅÅÅ. **Certifikat profiler utan förfallo datum distribueras inte.**
2. Skapa en profil för varje SCEP-eller PKCS-certifikat (se [skapa en SCEP-certifikat profil](https://docs.microsoft.com/intune/protect/certificates-scep-configure#create-a-scep-certificate-profile) eller [skapa en PKCS Certificate-profil](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)) var och en av dessa profiler måste ha en beskrivning som innehåller ett utgångs datum i formatet dd/mm/åååå. **Certifikat profiler utan förfallo datum distribueras inte.**
3. Skapa en profil för varje företags WiFi-nätverk (se [WiFi-inställningar för Windows 10 och senare enheter](https://docs.microsoft.com/intune/wi-fi-settings-windows)).
4. Skapa en profil för varje företags-VPN (se [Windows 10-och Windows Holographic enhets inställningar för att lägga till VPN-anslutningar med Intune](https://docs.microsoft.com/intune/vpn-settings-windows-10)).
5. Skicka ett support ärende med rubriken "certifikat distribution" eller "Wi-Fi-profil distribution" till Microsoft Managed Desktop IT Operations på Microsoft Managed Desktop admin-portalen för att granska och distribuera konfigurations profilen till "moderna arbets plats enheter-test". Microsoft-hanterad stationär dator IT-operationer gör att du vet när begäran har genomförts via supportavdelningen på administrations portalen. 
 
 
