---
title: Förutsättningar för Microsoft Hanterat skrivbord
description: Licenser, Azure-konton, autentiseringsinställningar och Microsoft 365 konfigureras innan de registreras i Microsoft Hanterat skrivbord
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: e4469d8abcfa8308c64e2efa7f7dc4f0156e5718
ms.sourcegitcommit: b6763a8ab240fbdd56078a7c9452445d0c4b9545
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/22/2021
ms.locfileid: "51957533"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Förutsättningar för Microsoft Hanterat skrivbord

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

I det här avsnittet beskrivs de infrastrukturkrav du måste uppfylla för att säkerställa framgång med Microsoft Hanterat skrivbord. 


Område | Information som krävs
--- | ---
Licensiering |Microsoft Hanterat skrivbord krävs att Microsoft 365 E3 licens med Microsoft Defender för slutpunkt (eller motsvarande) som tilldelats dina användare.<br>Mer information om de specifika tjänstplanerna finns i [Mer om licenser i](#more-about-licenses) det här avsnittet.<br>Mer information om tillgängliga licenser finns i [Microsoft 365 licens](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans).
Anslutning |  Alla Microsoft Hanterat skrivbord kräver anslutningar till flera Microsoft-tjänsteslutpunkter från företagsnätverket.<br><br>En fullständig lista över obligatoriska IP-adresser och URL-adresser finns i [Nätverkskonfiguration](../get-ready/network.md). 
Azure Active Directory |    Azure Active Directory (Azure AD) måste antingen vara källan till behörighet för alla användarkonton eller så måste användarkonton synkroniseras från en lokal Active Directory med den senaste versionen av Azure AD Anslut.<br><br>[Roaming i företagstillstånd](/azure/active-directory/devices/enterprise-state-roaming-overview) måste vara aktiverat Microsoft Hanterat skrivbord användare.<br><br>Mer information finns i [Azure AD-Anslut](/azure/active-directory/hybrid/whatis-azure-ad-connect).<br><br>Mer information om Azure AD-Anslut versioner finns i [Azure AD Anslut:Versionshistorik](/azure/active-directory/hybrid/reference-connect-version-history).
Autentisering |    Om Azure AD inte är källan till primär autentisering för användarkonton måste du konfigurera någon av dessa i Azure AD Anslut:<br>- Synkronisering av lösenordshashar<br>- Direktautentisering<br>– En extern identitetsleverantör (inklusive Windows Server ADFS och icke-Microsoft-IDP:er) som konfigurerats för att uppfylla Azure AD-integreringskraven. Mer information [finns](https://www.microsoft.com/download/details.aspx?id=56843) i riktlinjerna. <br><br>När du anger autentiseringsalternativ med Azure AD Anslut, rekommenderas även tillbakaskrivning av lösenord. Mer information finns i [Tillbakaskrivning av lösenord.](/azure/active-directory/authentication/howto-sspr-writeback) <br><br>Om en extern identitetsprovider implementeras måste du verifiera lösningen:<br>- Uppfyller Krav för Azure AD-integrering<br>- Stöder villkorlig åtkomst i Azure AD, vilket Microsoft Hanterat skrivbord att enhetsefterlevnadsprincipen konfigureras<br>– Aktiverar enhetsregistrering och användning av Microsoft 365 tjänster eller funktioner som krävs som en del av Microsoft Hanterat skrivbord <br><br>Mer information om autentiseringsalternativ med Azure AD finns i [Azure AD Anslut för inloggningsalternativ för användare.](/azure/active-directory/connect/active-directory-aadconnect-user-signin)
Microsoft 365 | OneDrive för företag måste vara aktiverat Microsoft Hanterat skrivbord användarna.<br><br>Även om det inte krävs att registrera Microsoft Hanterat skrivbord rekommenderar vi att följande tjänster migreras till molnet:<br>- E-post: Migrera till molnbaserade postlådor Exchange online eller konfigurera med Exchange Online Hybrid med Exchange 2013 eller senare, lokalt.<br>- Filer och mappar: Migrera till OneDrive för företag eller SharePoint Online.<br>- Verktyg för onlinesamarbete: Migrera till Teams.
Enhetshantering | Microsoft Hanterat skrivbord-enheter kräver hantering med hjälp av Microsoft Intune. Intune måste anges som utfärdare för hantering av mobila enheter.<br><br>Mer information finns i [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune). 
Säkerhetskopiering och återställning av data |  Microsoft Hanterat skrivbord kräver att filerna synkroniseras för OneDrive för företag skydd. Filer som inte synkroniseras till OneDrive för företag omfattas inte av Microsoft Hanterat skrivbord och kan gå förlorade under enhetsutbyten eller supportsamtal som kräver återställning av enhet.<br><br>Även om det inte Microsoft Hanterat skrivbord rekommenderar vi starkt migrering från mappade nätverksenheter till lämplig molnlösning. Mer information finns i Förbereda [mappade enheter för Microsoft Hanterat skrivbord](mapped-drives.md)

När du är redo att börja använda Microsoft Hanterat skrivbord kontaktar du Microsoft Account Manager. 

## <a name="more-about-licenses"></a>Mer om licenser

Microsoft Hanterat skrivbord krävs vissa licensalternativ för att fungera. Se [Microsoft Hanterat skrivbord för](../intro/technologies.md) information om hur licenserna används.

> [!TIP]
> Om du vill tilldela licensalternativen till specifika användare rekommenderar vi att du utnyttjar funktionen för gruppbaserad [licensiering](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal) i Azure Active Directory.

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

1. Granska [Krav för Microsoft Hanterat skrivbord](prerequisites.md). (Den här artikeln)
2. Använda [utvärderingsverktyg för beredskap](readiness-assessment-tool.md).
3. [Förutsättningar för gästkonton](guest-accounts.md)
4. [Nätverkskonfiguration för Microsoft Hanterat skrivbord](network.md)
5. [Förbereda certifikat och nätverksprofiler för Microsoft Hanterat skrivbord](certs-wifi-lan.md)
6. [Förbereda åtkomst till lokala resurser för Microsoft Hanterat skrivbord](authentication.md)
7. [Appar i Microsoft Hanterat skrivbord](apps.md)
8. [Förbereda mappade enheter för Microsoft Hanterat skrivbord](mapped-drives.md)
9. [Förbereda utskriftsresurser för Microsoft Hanterat skrivbord](printing.md)
