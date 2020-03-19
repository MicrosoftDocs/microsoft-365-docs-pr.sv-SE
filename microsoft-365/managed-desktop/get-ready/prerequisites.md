---
title: Förutsättningar för Microsoft Managed Desktop
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, tjänst, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: b729712a188c105fdf8a38e208124c2ef4c27a33
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/13/2020
ms.locfileid: "42805439"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Förutsättningar för Microsoft Managed Desktop

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

I det här avsnittet beskrivs de infrastrukturkrav som du måste uppfylla för att säkerställa framgång med Microsoft Managed Desktop. 

Microsoft FastTrack är tillgängligt för att hjälpa dig att uppfylla dessa krav och hjälpa dig att förbereda dig för att delta i Microsoft Managed Desktop. Mer information finns i [Microsoft FastTrack](https://fasttrack.microsoft.com/about). 

Området | Nödvändiga detaljer
--- | ---
Licensiering |Microsoft Managed Desktop kräver någon av följande Microsoft 365-licenser (eller motsvarande):<br>-Microsoft 365 E5<br>-Microsoft 365 E3 med microsoft 365 E5 Security-tillägget<br><br>Mer information om de specifika tjänstplanerna och deras roll i Microsoft Managed Desktop finns i [Mer om licenser](#more-about-licenses) i det här avsnittet.<br>Mer information om tillgängliga licenser finns i [Microsoft 365-licensiering](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).
Anslutning |  Alla Microsoft Managed Desktop-enheter kräver anslutning till många Microsoft-tjänstslutpunkter från företagsnätverket.<br><br>En fullständig lista över obligatoriska IPs- och URL:er finns [i Nätverkskonfiguration](../get-ready/network.md). 
Azure Active Directory |    Azure Active Directory (Azure AD) måste antingen vara en myndighetskälla för alla användarkonton, eller så måste användarkonton synkroniseras från lokala Active Directory med den senaste versionen av Azure AD Connect.<br><br>[Företagstillståndsroaming](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-overview) måste vara aktiverat för användare av Microsoft managed desktop.<br><br>Mer information finns i [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect).<br><br>Mer information om Azure AD Connect-versioner som stöds finns i [Azure AD Connect:Versionsutgivningshistorik](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-version-history).
Autentisering |    Om Azure AD inte är källan till behörighet för användarkonton måste du konfigurera en av dessa i Azure AD Connect:<br>- Lösenordhashsynkronisering<br>- Direktautentisering<br>- Federation med ADFS<br><br>När du anger autentiseringsalternativ med Azure AD Connect rekommenderas också tillbakaskrivning av lösenord. Mer information finns i [Skriva tillbaka lösenord](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback). <br><br>Mer information om autentiseringsalternativ med Azure AD finns i [Azure AD Connect-användarinloggningsalternativ](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-user-signin).
Office 365 |    OneDrive för företag måste vara aktiverat för användare av Microsoft Managed Desktop.<br><br>Även om det inte krävs för att registrera dig med Microsoft Managed Desktop rekommenderar vi starkt att följande tjänster migreras till molnet:<br>- E-post: Migrera till molnbaserade postlådor, Exchange online eller konfigurera med Exchange Online Hybrid med Exchange 2013 eller högre, lokalt.<br>- Filer och mappar: Migrera till OneDrive för företag eller SharePoint Online.<br>- Online samarbetsverktyg: Migrera till teams.
Enhetshantering | Microsoft Managed Desktop-enheter kräver hantering med Microsoft Intune. Intune måste anges som myndigheten för hantering av mobila enheter.<br><br>Mer information finns i [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune). 
Säkerhetskopiering och återställning av data | Microsoft Managed Desktop kräver att filer synkroniseras med OneDrive för företag för skydd. Alla filer som inte synkroniseras med OneDrive för företag garanteras inte av Microsoft Managed Desktop och kan gå förlorade under enhetsutbyten eller supportsamtal som kräver en enhetsåterställning.<br><br>Även om det inte krävs rekommenderar Microsoft Managed Desktop migrering från mappade nätverksenheter till lämplig molnlösning. Mer information finns i [Förbereda mappade enheter för Microsoft Managed Desktop](mapped-drives.md)

När du är redo att komma igång med Microsoft Managed Desktop kontaktar du Microsoft Account Manager. 

## <a name="more-about-licenses"></a>Mer om licenser

Microsoft Managed Desktop kräver vissa licensalternativ för att fungera. Dessa alternativ finns i ett antal olika licenspaket, varav några kanske du redan äger. Den här tabellen visar vilka nödvändiga alternativ som är tillgängliga där licenser och sammanfattar deras roll i Microsoft Managed Desktop.

> [!TIP]
> Om du vill tilldela dessa licensalternativ till specifika användare rekommenderar vi att du utnyttjar den [gruppbaserade licensieringsfunktionen](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal) i Azure Active Directory.



|Licensalternativ |Finns i *någon* av dessa licensprodukter |Så här använder Microsoft Managed Desktop det|
|-------------|-------------|-------------|
|Azure Active Directory Premium P1     |- Microsoft 365 E5<br>- Microsoft 365 E3 + Microsoft 365 *E5* Säkerhetstillägg<br>- Företagsmobilitet + Säkerhet E5<br>- Företagsmobilitet + Säkerhet E3<br>- Azure Active Directory Premium P1|  Ger åtkomst till Microsoft Cloud Services. gör det möjligt för AutoPilot att registrera enheter      |
|Microsoft Intune | - Microsoft 365 E5<br>- Microsoft 365 E3 + Microsoft 365 *E5* Säkerhetstillägg<br>- Företagsmobilitet + Säkerhet E5<br>- Företagsmobilitet + Säkerhet E3<br>- Microsoft Intune  |  Nödvändigt för att registrera enheter, distribuera uppdateringar och hantera enheter       |
|Windows 10 Företag  |- Microsoft 365 E5<br>- Microsoft 365 E3 + Microsoft 365 *E5* Säkerhetstillägg<br>- Windows 10 Enterprise E3<br>- Windows 10 Enterprise E5 | Innehåller företagsfunktioner i Windows 10       |
|Microsoft Defender avancerat hotskydd | - Microsoft 365 E5<br>- Microsoft 365 E3 + Microsoft 365 *E5* Säkerhetstillägg<br>- Windows 10 Enterprise E5<br>- Microsoft Defender Avancerat hotskydd   |  Ger identifiering, övervakning, avisering och svar på hot  |
|Office 365 ProPlus  |- Microsoft 365 E5<br>- Microsoft 365 E3<br>- Office 365 E5<br>- Office 365 E3| Aktiverar verktyg för Office och produktivitet och samarbete    |

> [!TIP]
> Microsoft Account Manager hjälper dig att granska dina aktuella licenser och serviceplaner och hitta den mest effektiva sökvägen för dig att få ytterligare licenser eller serviceplaner som du kan behöva, samtidigt som du undviker dubbelarbete.
