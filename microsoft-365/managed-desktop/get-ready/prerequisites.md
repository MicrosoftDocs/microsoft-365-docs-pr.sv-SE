---
title: Förutsättningar för Microsoft Hanterat skrivbord
description: ''
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: c958101e1f3268c706c27df6fc9e21e9914b3f46
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/30/2020
ms.locfileid: "46530289"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Förutsättningar för Microsoft Hanterat skrivbord

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

I det här avsnittet beskrivs de infrastrukturkrav som du måste uppfylla för att säkerställa att Microsoft Managed Desktop lyckas. 

Microsoft FastTrack är tillgängligt för att hjälpa dig att uppfylla dessa krav och hjälpa dig att förbereda dig för att delta i Microsoft Managed Desktop. Mer information finns i [Microsoft FastTrack](https://fasttrack.microsoft.com/about). 

Området | Nödvändiga detaljer
--- | ---
Licensiering |Microsoft Managed Desktop kräver någon av följande Microsoft 365-licenser (eller motsvarigheter):<br>-Microsoft 365 E5<br>-Microsoft 365 E3 med Microsoft 365 E5 Security-tillägget<br><br>Mer information om de specifika serviceplanerna och deras roll i Microsoft Managed Desktop finns i [Mer information om licenser](#more-about-licenses) i det här avsnittet.<br>Mer information om tillgängliga licenser finns i [Microsoft 365-licensiering](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).
Uppkoppling |  Alla Microsoft Managed Desktop-enheter kräver anslutning till många Microsoft-tjänstslutpunkter från företagsnätverket.<br><br>En fullständig lista över obligatoriska IPs och URL:er finns i [Nätverkskonfiguration](../get-ready/network.md). 
Azure Active Directory |    Azure Active Directory (Azure AD) måste antingen vara behörighetskälla för alla användarkonton eller användarkonton måste synkroniseras från lokala Active Directory med den senaste versionen av Azure AD Connect som stöds.<br><br>[Företagstillståndsroaming](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-overview) måste vara aktiverat för Microsoft Managed Desktop-användare.<br><br>Mer information finns i [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect).<br><br>Mer information om Azure AD Connect-versioner som stöds finns i [Azure AD Connect:Versionsversionshistorik](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-version-history).
Autentisering |    Om Azure AD inte är källan till primär autentisering för användarkonton måste du konfigurera en av dessa i Azure AD Connect:<br>- Synkronisering av lösenord hash-synkronisering<br>- Direktautentisering<br>- En extern identitetsprovider (inklusive Windows Server ADFS och icke-Microsoft-IDPs) som konfigurerats för att uppfylla Kraven för Azure AD-integrering. Se [riktlinjerna](https://www.microsoft.com/en-us/download/details.aspx?id=56843) för mer information. <br><br>När du anger autentiseringsalternativ med Azure AD Connect rekommenderas också återställning av lösenord. Mer information finns i [Tillbakaskrivning av lösenord](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback). <br><br>Om en extern identitetsprovider implementeras måste du validera lösningen:<br>- Uppfyller kraven för Azure AD-integrering<br>- Stöder Azure AD Villkorlig åtkomst, detta är att aktivera MMD Device Compliance Policy som ska konfigureras<br>- Aktiverar enhetsregistrering och användning av Microsoft 365-tjänster eller -funktioner som krävs som en del av Microsoft Managed Desktop <br><br>Mer information om autentiseringsalternativ med Azure AD finns [i Azure AD Connect-alternativ för användarloggning](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-user-signin).
Microsoft 365 | OneDrive för företag måste vara aktiverat för Microsoft Managed Desktop-användare.<br><br>Även om det inte krävs för att registrera sig hos Microsoft Managed Desktop rekommenderar vi starkt att följande tjänster migreras till molnet:<br>- E-post: Migrera till molnbaserade postlådor, Exchange online eller konfigurera med Exchange Online Hybrid med Exchange 2013 eller senare, lokalt.<br>- Filer och mappar: Migrera till OneDrive för företag eller SharePoint Online.<br>- Samarbetsverktyg online: Migrera till teams.
Enhetshantering | Microsoft Managed Desktop-enheter kräver hantering med Microsoft Intune. Intune måste ställas in som myndighet för hantering av mobila enheter.<br><br>Mer information finns i [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune). 
Säkerhetskopiering och återställning av data | Microsoft Managed Desktop kräver att filer synkroniseras med OneDrive för företag för skydd. Filer som inte synkroniseras med OneDrive för företag garanteras inte av Microsoft Managed Desktop och kan gå förlorade under enhetsutbyten eller supportsamtal som kräver en enhetsåterställning.<br><br>Även om det inte krävs rekommenderar Microsoft Managed Desktop starkt migrering från mappade nätverksenheter till lämplig molnlösning. Mer information finns i [Förbereda mappade enheter för Microsoft Managed Desktop](mapped-drives.md)

När du är redo att komma igång med Microsoft Managed Desktop kontaktar du Din Microsoft Account Manager. 

## <a name="more-about-licenses"></a>Mer om licenser

Microsoft Managed Desktop kräver vissa licensalternativ för att fungera. Dessa alternativ är tillgängliga i ett antal olika licenspaket, varav några kanske du redan äger. I den här tabellen visas vilka nödvändiga alternativ som är tillgängliga där licenser och sammanfattar deras roll i Microsoft Managed Desktop.

> [!TIP]
> Om du vill tilldela dessa licensalternativ till specifika användare rekommenderar vi att du utnyttjar den [gruppbaserade licensieringsfunktionen](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal) i Azure Active Directory.



|Alternativ för licens |Finns i *någon* av dessa licensprodukter |Så här använder Microsoft Managed Desktop det|
|-------------|-------------|-------------|
|Azure Active Directory Premium P1     |- Microsoft 365 E5<br>- Microsoft 365 E3 + Microsoft 365 *E5* Säkerhetstillägg<br>- Enterprise Mobility + Säkerhet E5<br>- Enterprise Mobility + Säkerhet E3<br>- Azure Active Directory Premium P1|  Ger åtkomst till Microsoft Cloud Services; gör det möjligt för AutoPilot att registrera enheter      |
|Microsoft Intune | - Microsoft 365 E5<br>- Microsoft 365 E3 + Microsoft 365 *E5* Säkerhetstillägg<br>- Enterprise Mobility + Säkerhet E5<br>- Enterprise Mobility + Säkerhet E3<br>- Microsoft Intune  |  Nödvändigt att registrera enheter, distribuera uppdateringar och hantera enheter       |
|Windows 10 Enterprise  |- Microsoft 365 E5<br>- Microsoft 365 E3 + Microsoft 365 *E5* Säkerhetstillägg<br>- Windows 10 Enterprise E3<br>- Windows 10 Enterprise E5 | Innehåller företagsfunktioner i Windows 10       |
|Microsoft Defender Avancerat skydd | - Microsoft 365 E5<br>- Microsoft 365 E3 + Microsoft 365 *E5* Säkerhetstillägg<br>- Windows 10 Enterprise E5<br>- Microsoft Defender avancerat hotskydd   |  Ger identifiering, övervakning, aviseringar och svar på hot  |
|Microsoft 365-applikationer för företag  |- Microsoft 365 E5<br>- Microsoft 365 E3<br>- Office 365 E5<br>- Office 365 E3| Aktiverar Verktyg för Office och produktivitet och samarbete    |

> [!TIP]
> Din Microsoft Account Manager hjälper dig att granska dina nuvarande licenser och serviceplaner och hitta den mest effektiva vägen för dig att få ytterligare licenser eller serviceplaner som du kan behöva, samtidigt som du undviker dubbelarbete.
