---
title: Förutsättningar för Microsoft Hanterat skrivbord
description: Licenser, Azure-konton, autentiseringsinställningar och Microsoft 365-inställningar som ska konfigureras innan de registreras i Microsoft Managed Desktop
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: fcfddadf13e000156fa5431cc30bc72f4f3537e2
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51581052"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Förutsättningar för Microsoft Hanterat skrivbord

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

I det här avsnittet beskrivs de infrastrukturkrav du måste uppfylla för att säkerställa framgång med Microsoft Managed Desktop. 


Område | Information som krävs
--- | ---
Licensiering |Microsoft Managed Desktop kräver att Microsoft 365 E3-licensen med Microsoft Defender för slutpunkten (eller motsvarigheterna) tilldelas till användarna. Två licenser för Azure Active Directory Premium 2 måste vara tillgängliga i klientorganisationen, men användarna behöver inte den här licensen. <br>Mer information om de specifika tjänstplanerna finns i [Mer om licenser i](#more-about-licenses) det här avsnittet.<br>Mer information om tillgängliga licenser finns i [Microsoft 365-licensiering.](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)
Anslutning |  Alla Microsoft Managed Desktop-enheter kräver anslutningar till flera Microsoft-tjänsteslutpunkter från företagsnätverket.<br><br>En fullständig lista över obligatoriska IP-adresser och URL-adresser finns i [Nätverkskonfiguration](../get-ready/network.md). 
Azure Active Directory |    Azure Active Directory (Azure AD) måste antingen vara käll för alla användarkonton eller så måste användarkonton synkroniseras från lokalt Active Directory med den senaste versionen av Azure AD Connect som stöds.<br><br>[Roaming i företagstillstånd](/azure/active-directory/devices/enterprise-state-roaming-overview) måste vara aktiverat för användare av Microsoft Managed Desktop.<br><br>Mer information finns i [Azure AD Connect.](/azure/active-directory/hybrid/whatis-azure-ad-connect)<br><br>Mer information om azure AD Connect-versioner som stöds finns i [Azure AD Connect:Versionshistorik.](/azure/active-directory/hybrid/reference-connect-version-history)
Autentisering |    Om Azure AD inte är källan till primär autentisering för användarkonton måste du konfigurera någon av dessa i Azure AD Connect:<br>- Synkronisering av lösenordshashar<br>- Direktautentisering<br>- En extern identitetsleverantör (inklusive Windows Server ADFS och icke-Microsoft-IDP:er) som konfigurerats för att uppfylla Azure AD-integreringskraven. Mer information [finns](https://www.microsoft.com/download/details.aspx?id=56843) i riktlinjerna. <br><br>När du anger autentiseringsalternativ med Azure AD Connect rekommenderas även tillbakaskrivning av lösenord. Mer information finns i [Tillbakaskrivning av lösenord.](/azure/active-directory/authentication/howto-sspr-writeback) <br><br>Om en extern identitetsprovider implementeras måste du verifiera lösningen:<br>- Uppfyller Krav för Azure AD-integrering<br>- Stöder villkorsstyrd åtkomst i Azure AD, vilket gör att microsofts policy för enhetsefterlevnad för hanterade datorer kan konfigureras<br>– Aktiverar enhetsregistrering och användning av Microsoft 365-tjänster eller -funktioner som krävs som en del av Microsoft Managed Desktop <br><br>Mer information om autentiseringsalternativ med Azure AD finns i [Inloggningsalternativ för Azure AD Connect-användare.](/azure/active-directory/connect/active-directory-aadconnect-user-signin)
Microsoft 365 | OneDrive för företag måste vara aktiverat för användare av Microsoft Managed Desktop.<br><br>Även om det inte är nödvändigt att registrera sig för Microsoft Managed Desktop rekommenderar vi starkt att följande tjänster migreras till molnet:<br>- E-post: Migrera till molnbaserade postlådor, Exchange Online eller konfigurera med Exchange Online-hybrid med Exchange 2013 eller senare, lokalt.<br>- Filer och mappar: Migrera till OneDrive för företag eller SharePoint Online.<br>- Verktyg för onlinesamarbete: Migrera till Teams.
Enhetshantering | Microsoft Hanterade skrivbordsenheter kräver hantering med Microsoft Intune. Intune måste anges som utfärdare för hantering av mobila enheter.<br><br>Mer information finns i [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune). 
Säkerhetskopiering och återställning av data |  Microsoft Managed Desktop kräver att filerna synkroniseras till OneDrive för företag för skydd. Filer som inte synkroniseras till OneDrive för företag omfattas inte av Microsoft Managed Desktop och kan gå förlorade under enhetsutbyten eller supportsamtal som kräver återställning av enhet.<br><br>Även om det inte krävs rekommenderar Microsoft Managed Desktop starkt migrering från mappade nätverksenheter till lämplig molnlösning. Mer information finns i Förbereda [mappade enheter för Microsoft Managed Desktop](mapped-drives.md)

När du är redo att börja använda Microsoft Managed Desktop kontaktar du Microsoft Account Manager. 

## <a name="more-about-licenses"></a>Mer om licenser

Microsoft Managed Desktop kräver vissa licensalternativ för att fungera. Mer [information om hur licenserna](../intro/technologies.md) används finns i Tekniker för Microsoft Managed Desktop.

> [!TIP]
> Om du vill tilldela licensalternativen till specifika användare rekommenderar vi att du utnyttjar [funktionen för gruppbaserad licensiering i](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal) Azure Active Directory.

- Azure Active Directory Premium P1
- Microsoft Intune 
- Windows 10 Enterprise  
- Microsoft Defender för Endpoint
-  Microsoft 365 Apps för företag
- Microsoft Teams
- [SharePoint Online (abonnemang 2)](https://www.microsoft.com/microsoft-365/sharepoint/compare-sharepoint-plans)
- [Exchange Online-abonnemang 2](https://www.microsoft.com/microsoft-365/exchange/compare-microsoft-exchange-online-plans) 


> [!TIP]
> Med Microsoft Account Manager kan du granska dina aktuella licenser och tjänstplaner och hitta den effektivaste vägen för att få ytterligare licenser eller tjänstplaner som du kan behöva, samtidigt som du slipper duplicering.

## <a name="steps-to-get-ready"></a>Steg för att förbereda dig

1. Granska [Krav för Microsoft Managed Desktop](prerequisites.md). (Den här artikeln)
2. Använda [utvärderingsverktyg för beredskap](readiness-assessment-tool.md).
3. [Förutsättningar för gästkonton](guest-accounts.md)
4. [Nätverks konfiguration för Microsoft Hanterat skrivbord](network.md)
5. [Förbereda certifikat och nätverks profiler för Microsoft Hanterat skrivbord](certs-wifi-lan.md)
6. [Förbereda lokala resurser till gång för Microsoft Hanterat skrivbord](authentication.md)
7. [Appar på Microsoft Hanterat skrivbord](apps.md)
8. [Förbereda mappade enheter för Microsoft Hanterat skrivbord](mapped-drives.md)
9. [Förbereda skrivarresurser för Microsoft Hanterat skrivbord](printing.md)
