---
title: Säkerhets teknik på Microsoft Managed Desktop
description: ''
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: e69656e13cd9a300cd56bdd5db7703f2387d23d4
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846210"
---
# <a name="security-technologies-in-microsoft-managed-desktop"></a>Säkerhets teknik på Microsoft Managed Desktop

<!--Security, also Onboarding doc: data handling/store, privileged account access -->

Microsoft Managed Desktop använder flera Microsoft-tekniker för att skydda hanterade enheter och data. Dessutom använder Microsoft Managed Desktop Security Operations Center en mängd olika [processer](security-operations.md) tillsammans med dessa tekniker.

Verkligen 

- [Enhets säkerhet](#device-security) – säkerhet och skydd på Microsoft Managed Station ära enheter
- [Identitets-och åtkomst hantering](#identity-and-access-management) – hantera säker användning av enheter via Azure Active Directory Identity Services
- [Nätverks säkerhet](#network-security) – VPN-information och rekommenderad lösning på Microsoft-datorn
- [Informations säkerhet](#information-security) – valfria tillgängliga tjänster för att skydda känslig information 

Mer information om data lagring, användning och säkerhets rutiner som används av Microsoft Managed Desktop finns i vårt informations dokument [https://aka.ms/mmd-data](https://aka.ms/mmd-data) .


## <a name="device-security"></a>Enhets säkerhet

Microsoft Managed Desktop säkerställer att alla hanterade enheter skyddas och skyddas och identifierar hot så tidigt som möjligt med följande tjänster:

Tjänst | Beskrivning
--- | ---
Viktigt | Microsoft Defender AV är installerat och konfigurerat<br>Microsoft Defender AV-definitioner är uppdaterade
Full volym kryptering |    Windows BitLocker är volym krypterings lösningen för Microsoft hanterade Station ära datorer.<br><br>När en organisation har satts in i tjänsten krypteras enheter med Windows BitLocker med inbyggd Trust Platform (TPM) för att förhindra otillåten åtkomst till lokala data när enheten är i vilo läge eller avstängd. 
Övervakning |    Microsoft Defender för slut punkter används för att övervaka säkerhets risken på alla Microsoft-hanterade Station ära enheter. Med Defender för slut punkten kan företags kunder upptäcka, undersöka och svara på avancerade hot i företagets nätverk. Mer information finns i [Microsoft Defender för slut punkter.](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) 
Uppdateringar av operativ system |  Microsoft Managed Station ära datorer skyddas alltid med de senaste säkerhets uppdateringarna.
Säker enhets konfiguration |   Microsoft Managed Desktop implementerar Microsofts säkerhets bas linje. Mer information finns i [säkerhets bas linjer för Windows.](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines)



## <a name="identity-and-access-management"></a>Identitets- och åtkomsthantering

Identitets-och åtkomst hantering skyddar företagets till gångar och företags kritiska data. Microsoft Managed Desktop konfigurerar enheter för att säkerställa säker användning med hanterade identiteter i Azure Active Directory (Azure AD). Det är kundens ansvar att behålla korrekt information i sin Azure AD-klient. 

Tjänst | Beskrivning
--- | ---
Bio metriska värden |  Med Windows Hello kan användarna logga in genom att använda sina ansikte eller PIN-koder och få lösen ord svårare att glömma eller stjäla. Kunderna är ansvariga för att implementera nödvändiga komponenter för sin lokala Active Directory för användning av denna tjänst i en hybrid konfiguration. Mer information finns i [Windows Hello.](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello) 
Standard användar behörighet |  För att skydda systemet och göra det säkrare, tilldelas användaren standard behörigheter. Detta är tilldelat som en del av autopiloten i Windows.



## <a name="network-security"></a>Nätverks säkerhet

Kunderna är ansvariga för nätverks säkerhet. 

Tjänst | Beskrivning
--- | ---
/VPN-Server | Kunder som äger sin VPN-infrastruktur för att säkerställa att begränsade företags resurser kan exponeras utanför intranätet.<br><br>Minsta krav: Microsoft Managed Desktop kräver en Windows 10-kompatibel och en VPN-lösning som stöds. Om din organisation behöver en VPN-lösning måste den ha stöd för Windows 10 och vara paketerad och distribuerad via Intune. Kontakta program varu utgivaren för mer information.<br><br>Rekommendation<br>-Microsoft rekommenderar en modern VPN-lösning som enkelt kan distribueras genom Intune till push-VPN-profiler. Detta ger ett ständigt, smidigt, tillförlitligt och säkert sätt att komma åt företagets nätverk. Mer information finns i [[VPN-inställningar i Intune]](https://docs.microsoft.com/intune/vpn-settings-configure).<br>-Tjocka VPN-klienter eller äldre VPN-klienter rekommenderas inte av Microsoft när du använder Microsoft Managed Desktop eftersom det kan påverka användar miljön.<br>-Microsoft rekommenderar att utgående webb trafik går direkt till Internet utan att behöva gå via VPN för att undvika prestanda problem.<br>-Idealiskt rekommenderar Microsoft att använda Azure Active Directory-tillämpningsproxy i stället för VPN.


## <a name="information-security"></a>Informations säkerhet

Du kan konfigurera de här valfria tjänsterna för att skydda företagets högsta till gångar. 

Tjänst | Beskrivning
--- | ---
Återställning av data  | Information som lagras i centrala mappar på enheten säkerhets kopie ras till OneDrive för företag. Microsoft Managed Desktop är inte ansvarigt för data som inte är synkroniserade med OneDrive för företag. 
Windows Information Protection |    För företag som kräver hög informations säkerhet rekommenderar vi [Windows informations skydd](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip) och [Azure information Protection.](https://www.microsoft.com/cloud-platform/azure-information-protection). 

