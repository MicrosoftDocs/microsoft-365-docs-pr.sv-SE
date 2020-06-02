---
title: Säkerhet i Microsoft Managed Desktop
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 8bfd71c4a143dee54ae006c8c54d711a8785480f
ms.sourcegitcommit: 2d664a95b9875f0775f0da44aca73b16a816e1c3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/01/2020
ms.locfileid: "44470495"
---
# <a name="security-in-microsoft-managed-desktop"></a>Säkerhet i Microsoft Managed Desktop

<!--Security, also Onboarding doc: data handling/store, privileged account access -->

Microsoft Managed Desktop använder flera Microsoft-tekniker för att skydda hanterade enheter och data. Specifikt: 


- [Enhetssäkerhet](#device-security) – säkerhet och skydd på Microsoft Managed Desktop-enheter
- [Identitets- och åtkomsthantering](#identity-and-access-management) – hantera säker användning av enheter via Azure Active Directory-identitetstjänster
- [Nätverkssäkerhet](#network-security) – VPN-information och Microsoft Managed Desktop rekommenderad lösning och inställningar
- [Informationssäkerhet](#information-security) – tillgängliga tjänster som tillval för att ytterligare skydda känslig information 

Om du vill ha information om metoder för datalagring, användning och säkerhet som används av Microsoft Managed Desktop kan du hämta vårt faktablad på [https://aka.ms/mmd-data](https://aka.ms/mmd-data) .


## <a name="device-security"></a>Enhetens säkerhet

Microsoft Managed Desktop ser till att alla hanterade enheter är skyddade och skyddade och upptäcker hot så tidigt som möjligt med hjälp av följande tjänster:

Tjänst | Beskrivning
--- | ---
Antivirus | Microsoft Defender AV är installerat och konfigurerat<br>Microsoft Defender AV-definitioner är uppdaterade
Fullständig volymkryptering |    Windows BitLocker är volymkrypteringslösningen för Microsoft Managed Desktop-enheter.<br><br>När en organisation är inkopplad i tjänsten krypteras enheter med Windows BitLocker med inbyggd TPM (Trust Platform Module) för att förhindra obehörig åtkomst till lokala data när enheten är i viloläge eller avstängd. 
Övervakning |    Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP) används för övervakning av säkerhetshot på alla Microsoft Managed Desktop-enheter. Microsoft Defender ATP gör det möjligt för företagskunder att upptäcka, undersöka och svara på avancerade hot i företagets nätverk. Mer information finns i [Microsoft Defender Advanced Threat Protection.](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) 
Uppdateringar av operativsystemet |  Microsoft Managed Desktop-enheter är alltid säkrade med de senaste säkerhetsuppdateringarna.
Konfiguration av säker enhet |   Microsoft Managed Desktop implementerar Microsoft Security Baseline. Mer information finns i [Windows säkerhetsbaslinjer.](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines)



## <a name="identity-and-access-management"></a>Identitets- och åtkomsthantering

Identitets- och åtkomsthantering skyddar företagets tillgångar och affärskritiska data. Microsoft Managed Desktop konfigurerar enheter för att säkerställa säker användning med Azure Active Directory (Azure AD) hanterade identiteter. Det är kundens ansvar att upprätthålla korrekt information i sin Azure AD-klientorganisation. 

Tjänst | Beskrivning
--- | ---
Biometrisk autentisering |  Med Windows Hello kan användare logga in med hjälp av ansiktet eller en PIN-kod, vilket gör lösenord svårare att glömma eller stjäla. Kunderna ansvarar för att implementera de förutsättningar som krävs för sin lokala Active Directory för användning av den här tjänsten i en hybridkonfiguration. Mer information finns i [Windows Hello.](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello) 
Standardanvändarbehörighet |  För att skydda systemet och göra det säkrare tilldelas användaren standardanvändarbehörigheter. Detta tilldelas som en del av Windows Autopilot out-of-box-upplevelsen.



## <a name="network-security"></a>Nätverkssäkerhet

Kunderna ansvarar för nätverkssäkerheten. 

Tjänst | Beskrivning
--- | ---
Vpn | Kunderna äger sin VPN-infrastruktur för att säkerställa att begränsade företagsresurser kan exponeras utanför intranätet.<br><br>Minimikrav: Microsoft Managed Desktop kräver en Windows 10-kompatibel och vpn-lösning som stöds. Om din organisation behöver en VPN-lösning måste den stödja Windows 10 och paketeras och distribueras via Intune. Kontakta programvaruutgivaren för mer information.<br><br>Rekommendation:<br>- Microsoft rekommenderar en modern VPN-lösning som enkelt kan distribueras via Intune för att driva VPN-profiler. Detta ger ett alltid på, sömlöst, tillförlitligt och säkert sätt att komma åt företagsnätverk. Mer information finns [i [VPN-inställningar i Intune]](https://docs.microsoft.com/intune/vpn-settings-configure).<br>- Tjocka VPN-klienter, eller äldre VPN-klienter, rekommenderas inte av Microsoft när microsoft hanterade skrivbord använder microsoft, eftersom det kan påverka slutanvändarmiljön.<br>- Microsoft rekommenderar att den utgående webbtrafiken går direkt till Internet utan att gå igenom VPN för att undvika prestandaproblem.<br>- Helst rekommenderar Microsoft användning av Azure Active Directory App Proxy istället för en VPN.


## <a name="information-security"></a>Informationssäkerhet

Du kan konfigurera dessa valfria tjänster för att skydda företagets värdefulla tillgångar. 

Tjänst | Beskrivning
--- | ---
Dataräddning  | Information som lagras i nyckelmappar på enheten säkerhetskopieras till OneDrive för företag. Microsoft Managed Desktop ansvarar inte för data som inte är synkroniserade med OneDrive för företag. 
Windows Information Protection |    För företag som kräver hög informationssäkerhet rekommenderar vi [Windows Information Protection](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip) och Azure Information [Protection.](https://www.microsoft.com/cloud-platform/azure-information-protection). 

