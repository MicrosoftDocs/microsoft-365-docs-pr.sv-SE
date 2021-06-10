---
title: Säkerhetstekniker i Microsoft Hanterat skrivbord
description: Tekniker som används för enhetssäkerhet, identitets- och åtkomsthantering, nätverkssäkerhet och informationssäkerhet
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: b1111f0867ff9a49ba670cdd8b48d10d158fd3ed
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917776"
---
# <a name="security-technologies-in-microsoft-managed-desktop"></a>Säkerhetstekniker i Microsoft Hanterat skrivbord

<!--Security, also Onboarding doc: data handling/store, privileged account access -->

Microsoft Hanterat skrivbord flera microsoft-tekniker som hjälper till att skydda hanterade enheter och data. Dessutom använder Microsoft Hanterat skrivbord Security Operations Center olika processer [tillsammans](security-operations.md) med dessa tekniker.

Mer specifikt: 

- [Enhetssäkerhet](#device-security) – säkerhet och skydd på Microsoft Hanterat skrivbord enheter
- [Identitets- och åtkomsthantering](#identity-and-access-management) – hantera säker användning av enheter via Azure Active Directory identitetstjänster
- [Nätverkssäkerhet](#network-security) – VPN-information Microsoft Hanterat skrivbord rekommenderade lösningar och inställningar
- [Informationssäkerhet](#information-security) – valfria tjänster för ytterligare skydd av känslig information 

Mer information om datalagring, användning och säkerhetsmetoder som används Microsoft Hanterat skrivbord finns i vår informationsblad på [https://aka.ms/mmd-data](https://aka.ms/mmd-data) .


## <a name="device-security"></a>Enhetssäkerhet

Microsoft Hanterat skrivbord säkerställer att alla hanterade enheter är skyddade och identifierar hot så tidigt som möjligt med hjälp av följande tjänster:

Tjänst | Beskrivning
--- | ---
Antivirus | Microsoft Defender AV är installerat och konfigurerat<br>Microsoft Defender AV-definitioner är uppdaterade
Fullständig volymkryptering |    Windows BitLocker är volymkrypteringslösningen för Microsoft Hanterat skrivbord enheter.<br><br>När en organisation har introducerats till tjänsten krypteras enheter med Windows BitLocker med den inbyggda TPM (Trust Platform Module) för att förhindra obehörig åtkomst till lokal data när enheten är i strömsparläge eller inaktiverad. 
Övervakning |    Microsoft Defender för Endpoint används för övervakning av säkerhetshot på alla Microsoft Hanterat skrivbord enheter. Med Defender för Slutpunkt kan företagskunder identifiera, undersöka och reagera på avancerade hot i sina företagsnätverk. Mer information finns i [Microsoft Defender för Endpoint.](/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) 
Uppdateringar av operativsystem |  Microsoft Hanterat skrivbord-enheter alltid skyddas med de senaste säkerhetsuppdateringarna.
Säker enhetskonfiguration |   Microsoft Hanterat skrivbord implementerar Microsofts baslinje för säkerhet. Mer information finns i Windows [baslinjer för säkerhet.](/windows/security/threat-protection/windows-security-baselines)



## <a name="identity-and-access-management"></a>Identitets- och åtkomsthantering

Identitets- och åtkomsthantering skyddar företagets tillgångar och affärskritiska data. Microsoft Hanterat skrivbord konfigurerar enheter för säker användning med hanterade Azure Active Directory (Azure AD). Det är kundens ansvar att upprätthålla korrekt information i Azure AD-klientorganisationen. 

Tjänst | Beskrivning
--- | ---
Autentisering med autentisering |  Windows Med Hello kan användarna logga in med sitt ansikte eller med en PIN-kod, vilket gör det svårare att glömma eller stjäla lösenord. Kunderna ansvarar för att implementera nödvändiga förutsättningar för sin lokala Active Directory för användning av den här tjänsten i en hybridkonfiguration. Mer information finns i [Windows Hello.](/windows-hardware/design/device-experiences/windows-hello) 
Standardanvändarbehörighet |  För att skydda systemet och göra det säkrare får användaren standardanvändarbehörigheter. Den här behörigheten tilldelas som en del av den inbaserade Windows Autopilot-upplevelsen.



## <a name="network-security"></a>Nätverkssäkerhet

Kunderna ansvarar för nätverkssäkerhet. 

Tjänst | Beskrivning
--- | ---
VPN | Kunderna äger VPN-infrastrukturen för att säkerställa att begränsade företagsresurser kan exponeras utanför intranätet.<br><br>Minimikrav: för Microsoft Hanterat skrivbord krävs en Windows 10 kompatibel och vpn-lösning som stöds. Om din organisation behöver en VPN-lösning måste den ha stöd för Windows 10 och vara paketerad och distribuerad via Intune. Kontakta programvaruutgivaren för mer information.<br><br>Rekommendation:<br>- Microsoft rekommenderar en modern VPN-lösning som enkelt kan distribueras via Intune för att pusha VPN-profiler. Den här metoden är ett ständigt, sömlöst, tillförlitligt och säkert sätt att få åtkomst till företagets nätverk. Mer information finns i [[VPN-inställningar i Intune]](/intune/vpn-settings-configure).<br>- Tjockare VPN-klienter, eller äldre VPN-klienter, rekommenderas inte av Microsoft när Microsoft Hanterat skrivbord eftersom det kan påverka användarmiljön.<br>Microsoft rekommenderar att den utgående webbtrafiken går direkt till Internet utan att gå via VPN för att undvika prestandaproblem.<br>– Allra helst rekommenderar Microsoft att du använder en Azure Active Directory-appproxy i stället för en VPN.


## <a name="information-security"></a>Informationssäkerhet

Du kan konfigurera de här valfria tjänsterna för att skydda företagets tillgångar med höga värden. 

Tjänst | Beskrivning
--- | ---
Dataåterställning  | Information som lagras i viktiga mappar på enheten säkerhetskopieras till OneDrive för företag. Microsoft Hanterat skrivbord ansvarar inte för data som inte synkroniseras med OneDrive för företag. 
Windows Information Protection |    För företag som kräver hög informationssäkerhetsnivå rekommenderar vi att [Windows informationsskydd](/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip) och [Azure Information Protection.](https://www.microsoft.com/cloud-platform/azure-information-protection)