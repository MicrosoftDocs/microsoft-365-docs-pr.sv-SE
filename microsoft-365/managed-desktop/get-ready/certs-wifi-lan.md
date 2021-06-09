---
title: Förbereda certifikat och nätverks profiler för Microsoft Hanterat skrivbord
description: Certifikatkrav och Wi-Fi-anslutning
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
audience: Admin
ms.openlocfilehash: a59add6f6821824f189703b3dedd35fda313ec31
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574589"
---
# <a name="prepare-certificates-and-network-profiles-for-microsoft-managed-desktop"></a>Förbereda certifikat och nätverks profiler för Microsoft Hanterat skrivbord  
 
Certifikatbaserad autentisering är ett vanligt krav för kunder som använder Microsoft Hanterat skrivbord. Du kan kräva certifikat för åtkomst Wi-Fi nätverket, för att ansluta till VPN-lösningar eller för åtkomst till interna resurser i organisationen.   
 
Eftersom Microsoft Hanterat skrivbord-enheter är anslutna till Azure Active Directory (Azure AD) och hanteras av Microsoft Intune måste du distribuera sådana certifikat med hjälp av en SSTACK (Simple Certificate Enrollment Protocol) eller PKCS-certifikatinfrastruktur (Public Key Cryptography Standard) som är integrerad med Intune.    
 
## <a name="certificate-requirements"></a>Certifikatkrav 
 
Rotcertifikat krävs för att distribuera certifikat via en SNIC- eller PKCS-infrastruktur. Andra program och tjänster i organisationen kan kräva att rotcertifikat distribueras till dina Microsoft Hanterat skrivbord enheter.    
 
Innan du distribuerar S FLERA- eller PKCS-certifikat Microsoft Hanterat skrivbord bör du samla in krav för varje tjänst som kräver ett användar- eller enhetscertifikat i organisationen. För att underlätta den här aktiviteten kan du använda någon av följande planeringsmallar:  
 
- [Mall för PKCS-certifikat](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/PKCS-certificate-template.xlsx) 
- [SBEGÄRAN-certifikatmall](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/SCEP-certificate-template.xlsx)

  
## <a name="wi-fi-connectivity-requirements"></a>Wi-Fi anslutningskrav

Om du vill att en enhet ska tillhandahållas automatiskt med Wi-Fi konfiguration för företagsnätverket kan du behöva en profil Wi-Fi konfigurationsprofil. Du kan konfigurera Microsoft Hanterat skrivbord att distribuera de här profilerna på dina enheter. Om nätverkssäkerhet kräver att enheter är en del av den lokala domänen kan du också behöva utvärdera din Wi-Fi-nätverksinfrastruktur för att se till att den är kompatibel med Microsoft Hanterat skrivbord-enheter (Microsoft Hanterat skrivbord-enheter är endast Azure AD-anslutna). 
 
Innan du distribuerar Wi-Fi konfiguration Microsoft Hanterat skrivbord-enheter måste du samla in organisationens krav för varje Wi-Fi nätverk. För att göra den här aktiviteten enklare kan du använda den här [mallen för WiFi-profiler.](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/WiFi-profile-template.xlsx)
 
 
## <a name="wired-connectivity-requirements-and-8021x-authentication"></a>Krav för trådbunden anslutning och 802.1x-autentisering 
 
Om du använder 802.1x-autentisering för att skydda åtkomsten från enheter till ditt lokala nätverk (LAN) måste du skicka den konfigurationsinformation som krävs till dina Microsoft Hanterat skrivbord enheter. Microsoft Hanterat skrivbord enheter med Windows 10, version 1809 eller senare har stöd för distribution av en 802.1x-konfiguration via WiredNetwork configuration service provider (CSP). Mer information finns i Dokumentationen [för WiredNetwork CSP.](/windows/client-management/mdm/wirednetwork-csp) 
 
Innan du distribuerar en profil för nätverkskonfiguration Microsoft Hanterat skrivbord enheter måste du samla in organisationens krav för ditt kabelanslutna företagsnätverk. Gör så här: 
 
 
1. Logga in på en enhet där din befintliga 802.1x-profil är konfigurerad och ansluten till LAN-nätverket.  
2. Öppna en kommandotolk med administrativa autentiseringsuppgifter. 
3. Hitta NAMNET på LAN-gränssnittet genom att köra **Netsh-gränssnittets gränssnitt.** 
4. Exportera LAN-profilens XML genom att **köra netsh lan export profile folder=.  Interface="interface_name"**. 
5. Om du behöver testa din exporterade profil på Microsoft Hanterat skrivbord-enhet kör du **netsh lan add profile filename="PATH_AND_FILENAME.xml" interface="INTERFACE_NAME"**. 
 
 
## <a name="deploy-certificate-infrastructure"></a>Distribuera infrastruktur för certifikat  
 
Om du redan har en befintlig S ÄR- eller PKCS-infrastruktur med Intune och den här metoden uppfyller dina krav kan du också använda den för Microsoft Hanterat skrivbord. Om det inte finns någon S EN- eller PKCS-infrastruktur måste du förbereda en infrastruktur.  
 
Mer information finns i [Konfigurera en certifikatprofil för dina enheter i Microsoft Intune](/intune/certificates-configure). 
 
 
 
## <a name="deploy-a-lan-profile"></a>Distribuera en LAN-profil 
 
När din LAN-profil har exporterats kan du förbereda principen för Microsoft Hanterat skrivbord genom att göra följande:   
 
1. Skapa en anpassad profil i Microsoft Intune för LAN-profilen med hjälp av följande inställningar (se Använda anpassade inställningar för [Windows 10 enheter i Intune](/intune/custom-settings-windows-10)). I **Custom OMA-URI Inställningar** väljer du **Add** och anger sedan följande värden: 
    - Namn: *Modern Workplace-Windows 10 LAN-profil* 
    - Beskrivning: Ange en beskrivning som ger en översikt över inställningen och annan viktig information. 
    - OMA-URI (fallkänsligt): Ange *./Device/Vendor/MSFT/WiredNetwork/LanXML*
    - Datatyp: välj **Sträng (XML-fil)**. 
    - Anpassad XML: Upload den exporterade XML-filen.
2. Skicka en supportbegäran till Microsoft Hanterat skrivbord IT-drift med hjälp av administrationsportalen i Microsoft Hanterat skrivbord för att granska och distribuera konfigurationsprofilen till "Moderna workplace-enheter – test". Microsoft Hanterat skrivbord IT-åtgärder meddela dig när begäran är slutförd via supportbegäran i administrationsportalen.
 
## <a name="deploy-certificates-and-wi-fivpn-profile"></a>Distribuera certifikat och Wi-Fi/VPN-profil 
 
 
Följ de här stegen om du vill distribuera certifikat och profiler:

1. Skapa en profil för vart och ett av rot- och mellanliggande certifikat (se [Skapa betrodda certifikatprofiler.](/intune/protect/certificates-configure#step-3-create-trusted-certificate-profiles) Var och en av dessa profiler måste ha en beskrivning som innehåller ett utgångsdatum i formatet DD/MM/YYY. **Certifikatprofiler utan ett utgångsdatum distribueras inte.**
2. Skapa en profil för varje SERING- eller PKCS-certifikat (se Skapa en [SNIC-certifikatprofil](/intune/protect/certificates-scep-configure#create-a-scep-certificate-profile) eller Skapa en profil för [PKCS-certifikat)](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)Var och en av dessa profiler måste ha en beskrivning som innehåller ett utgångsdatum i formatet DD/MM/ÅDYY. **Certifikatprofiler utan ett utgångsdatum distribueras inte.**
3. Skapa en profil för varje företags WiFi-nätverk (se [Wi-Fi-inställningar för Windows 10 och senare enheter](/intune/wi-fi-settings-windows)).
4. Skapa en profil för varje företags-VPN (se inställningar Windows 10 och Windows Holographic för att lägga till [VPN-anslutningar med Intune](/intune/vpn-settings-windows-10)).
5. Skicka en supportbegäran med namnet "Certifikatdistribution" eller "Distribution av wi-fi-profil" till Microsoft Hanterat skrivbord IT-drift med hjälp av administrationsportalen för Microsoft Hanterat skrivbord för att granska och distribuera konfigurationsprofilen till "Moderna workplace-enheter – test". Microsoft Hanterat skrivbord IT-åtgärder meddela dig när begäran har slutförts via supportbegäran i administrationsportalen. 
 
## <a name="steps-to-get-ready"></a>Steg för att förbereda dig

1. Granska [Krav för Microsoft Hanterat skrivbord](prerequisites.md).
2. Använda [utvärderingsverktyg för beredskap](readiness-assessment-tool.md).
3. [Förutsättningar för gästkonton](guest-accounts.md)
4. [Nätverkskonfiguration för Microsoft Hanterat skrivbord](network.md)
5. [Förbereda certifikat och nätverksprofiler för Microsoft Hanterat skrivbord](certs-wifi-lan.md) (den här artikeln)
6. [Förbereda åtkomst till lokala resurser för Microsoft Hanterat skrivbord](authentication.md)
7. [Appar i Microsoft Hanterat skrivbord](apps.md)
8. [Förbereda mappade enheter för Microsoft Hanterat skrivbord](mapped-drives.md)
9. [Förbereda utskriftsresurser för Microsoft Hanterat skrivbord](printing.md) 
