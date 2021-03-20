---
title: Förbereda certifikat och nätverks profiler för Microsoft Hanterat skrivbord
description: certs/wifi/lan
keywords: Microsoft Hanterat skrivbord, Microsoft 365, tjänst, dokumentation
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: 9f4490711c1ea051afe9d8efb081a2f7a141f8ba
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909124"
---
# <a name="prepare-certificates-and-network-profiles-for-microsoft-managed-desktop"></a>Förbereda certifikat och nätverks profiler för Microsoft Hanterat skrivbord  
 
Certifikatbaserad autentisering är ett vanligt krav för kunder som använder Microsoft Managed Desktop. Du kan kräva certifikat för åtkomst Wi-Fi nätverket, för att ansluta till VPN-lösningar eller för åtkomst till interna resurser i organisationen.   
 
Eftersom Microsoft Managed Desktop-enheter är anslutna till Azure Active Directory (Azure AD) och hanteras av Microsoft Intune måste du distribuera sådana certifikat med hjälp av en PKCS-certifikatinfrastruktur (Simple Certificate Enrollment Protocol) eller PKCS-certifikatinfrastruktur (Public Key Cryptography Standard) som är integrerad med Intune.    
 
## <a name="certificate-requirements"></a>Certifikatkrav 
 
Rotcertifikat krävs för att distribuera certifikat via en SNIC- eller PKCS-infrastruktur. Andra program och tjänster i organisationen kan kräva att rotcertifikat distribueras till dina Microsoft Managed Desktop-enheter.    
 
Innan du distribuerar S FLERA- eller PKCS-certifikat till Microsoft Managed Desktop bör du samla in krav för varje tjänst som kräver ett användar- eller enhetscertifikat i organisationen. För att underlätta den här aktiviteten kan du använda någon av följande planeringsmallar:  
 
- [Mall för PKCS-certifikat](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/PKCS-certificate-template.xlsx) 
- [SBEGÄRAN-certifikatmall](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/SCEP-certificate-template.xlsx)

  
## <a name="wi-fi-connectivity-requirements"></a>Wi-Fi anslutningskrav

Om du vill att en enhet ska tillhandahållas automatiskt med Wi-Fi konfiguration för företagsnätverket kan du behöva en profil Wi-Fi konfigurationsprofil. Du kan konfigurera Microsoft Managed Desktop för att distribuera de här profilerna på dina enheter. Om nätverkssäkerhet kräver att enheter är en del av den lokala domänen kan du också behöva utvärdera din Wi-Fi-nätverksinfrastruktur för att se till att den är kompatibel med Microsoft Managed Desktop-enheter (Microsoft Managed Desktop-enheter är endast Azure AD-anslutna). 
 
Innan du distribuerar Wi-Fi konfiguration till Microsoft Managed Desktop-enheter måste du samla in organisationens krav för varje Wi-Fi nätverk. För att göra den här aktiviteten enklare kan du använda den här [mallen för WiFi-profiler.](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/WiFi-profile-template.xlsx)
 
 
## <a name="wired-connectivity-requirements-and-8021x-authentication"></a>Krav för trådbunden anslutning och 802.1x-autentisering 
 
Om du använder 802.1x-autentisering för att skydda åtkomsten från enheter till ditt lokala nätverk (LAN) måste du skicka den konfigurationsinformation som krävs till dina Microsoft Managed Desktop-enheter. Microsoft Hanterade skrivbordsenheter med Windows 10, version 1809 eller senare har stöd för distribution av en 802.1x-konfiguration via WiredNetwork-konfigurationstjänsten (CSP). Mer information finns i Dokumentationen [för WiredNetwork CSP.](/windows/client-management/mdm/wirednetwork-csp) 
 
Innan du distribuerar en profil för nätverkskonfiguration med kabel till Microsoft Managed Desktop-enheter, samlar du in organisationens krav för ditt kabelanslutna företagsnätverk. Gör så här: 
 
 
1. Logga in på en enhet där din befintliga 802.1x-profil är konfigurerad och ansluten till LAN-nätverket.  
2. Öppna en kommandotolk med administrativa autentiseringsuppgifter. 
3. Hitta NAMNET på LAN-gränssnittet genom att köra **Netsh-gränssnittets gränssnitt.** 
4. Exportera LAN-profilens XML genom att **köra netsh lan export profile folder=.  Interface="interface_name"**. 
5. Om du behöver testa din exporterade profil på en Microsoft Managed Desktop-enhet kör du **netsh lan add profile filename="PATH_AND_FILENAME.xml" interface="INTERFACE_NAME"**. 
 
 
## <a name="deploy-certificate-infrastructure"></a>Distribuera infrastruktur för certifikat  
 
Om du redan har en befintlig SITI- eller PKCS-infrastruktur med Intune och den här metoden uppfyller dina krav kan du också använda den för Microsoft Managed Desktop. Om det inte finns någon S EN- eller PKCS-infrastruktur måste du förbereda en infrastruktur.  
 
Mer information finns i [Konfigurera en certifikatprofil för dina enheter i Microsoft Intune.](/intune/certificates-configure) 
 
 
 
## <a name="deploy-a-lan-profile"></a>Distribuera en LAN-profil 
 
När din LAN-profil har exporterats kan du förbereda principen för Microsoft Managed Desktop genom att följa de här stegen:   
 
1. Skapa en anpassad profil i Microsoft Intune för LAN-profilen med följande inställningar (se Använda anpassade inställningar för [Windows 10-enheter i Intune](/intune/custom-settings-windows-10)). I **Custom OMA-URI Settings** väljer du **Add** och anger sedan följande värden: 
    - Namn: *Modern Workplace-Windows 10 LAN-profil* 
    - Beskrivning: Ange en beskrivning som ger en översikt över inställningen och annan viktig information. 
    - OMA-URI (fallkänsligt): Ange *./Device/Vendor/MSFT/WiredNetwork/LanXML*
    - Datatyp: välj **Sträng (XML-fil)**. 
    - Anpassad XML: Ladda upp den exporterade XML-filen.
2. Skicka en supportbegäran till Microsoft Managed Desktop IT Operations med hjälp av Microsoft Managed Desktop Admin-portalen för att granska och distribuera konfigurationsprofilen till "Moderna workplace-enheter – testa". IT-åtgärder som hanteras av Microsoft hanterade datorer meddela dig när begäran har slutförts via supportbegäran i administrationsportalen.
 
## <a name="deploy-certificates-and-wi-fivpn-profile"></a>Distribuera certifikat och Wi-Fi/VPN-profil 
 
 
Följ de här stegen om du vill distribuera certifikat och profiler:

1. Skapa en profil för vart och ett av rot- och mellanliggande certifikat (se [Skapa betrodda certifikatprofiler.](/intune/protect/certificates-configure#step-3-create-trusted-certificate-profiles) Var och en av dessa profiler måste ha en beskrivning som innehåller ett utgångsdatum i formatet DD/MM/YYY. **Certifikatprofiler utan ett utgångsdatum distribueras inte.**
2. Skapa en profil för varje SERING- eller PKCS-certifikat (se Skapa en [SNIC-certifikatprofil](/intune/protect/certificates-scep-configure#create-a-scep-certificate-profile) eller Skapa en profil för [PKCS-certifikat)](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)Var och en av dessa profiler måste ha en beskrivning som innehåller ett utgångsdatum i formatet DD/MM/ÅDYY. **Certifikatprofiler utan ett utgångsdatum distribueras inte.**
3. Skapa en profil för varje företags wiFi-nätverk (se [Wi-Fi-inställningar för Windows 10 och senare enheter](/intune/wi-fi-settings-windows)).
4. Skapa en profil för varje företags-VPN (se Windows 10- och Windows Holographic-enhetsinställningarna för att lägga till [VPN-anslutningar med Intune](/intune/vpn-settings-windows-10)).
5. Skicka en supportbegäran med namnet "Certificate Deployment" eller "Wi-Fi Profile Deployment" till Microsoft Managed Desktop IT Operations med hjälp av Microsoft Managed Desktop Admin-portalen för att granska och distribuera konfigurationsprofilen till "Moderna workplace-enheter – test". IT-åtgärder i Microsoft Managed Desktop låter dig veta när begäran har slutförts via supportbegäran i administrationsportalen. 
 
