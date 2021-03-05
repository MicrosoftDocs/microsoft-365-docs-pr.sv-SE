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
ms.openlocfilehash: c298c0d07b73966fe3946f0e3f2706da5d2d30fc
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/04/2021
ms.locfileid: "50453911"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Förutsättningar för Microsoft Hanterat skrivbord

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

I det här avsnittet beskrivs de infrastrukturkrav du måste uppfylla för att säkerställa framgång med Microsoft Managed Desktop. 


Område | Information som krävs
--- | ---
Licensiering |Microsoft Hanterat skrivbord kräver microsoft 365 E3-licensen med Microsoft Defender för slutpunkt (eller motsvarande) som tilldelats dina användare. Två licenser för Azure Active Directory Premium 2 måste vara tillgängliga i klientorganisationen, men användarna behöver inte den här licensen. <br>Mer information om de specifika tjänstplanerna finns [i Mer om licenser](#more-about-licenses) i det här avsnittet.<br>Mer information om tillgängliga licenser finns i [Microsoft 365-licensiering.](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)
Anslutning |  Alla Microsoft-enheter som hanteras av Microsoft kräver anslutning till flera slutpunkter för Microsoft-tjänster från företagsnätverket.<br><br>En fullständig lista över obligatoriska IP-adresser och URL-adresser finns i [Nätverkskonfiguration.](../get-ready/network.md) 
Azure Active Directory |    Azure Active Directory (Azure AD) måste antingen vara myndighetskälla för alla användarkonton, eller så måste användarkonton synkroniseras från lokalt Active Directory med hjälp av den senaste versionen av Azure AD Connect som stöds.<br><br>[Roaming i företagstillstånd](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-overview) måste vara aktiverat för Microsoft-användare av hanterad stationär dator.<br><br>Mer information finns i [Azure AD Connect.](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect)<br><br>Mer information om azure AD Connect-versioner som stöds finns i [versionshistoriken för Azure AD Connect:.](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-version-history)
Autentisering |    Om Azure AD inte är källan för primär autentisering för användarkonton måste du konfigurera något av följande i Azure AD Connect:<br>- Synkronisering av lösenordshashar<br>- Direktautentisering<br>– En extern identitetsleverantör (inklusive Windows Server ADFS och icke-Microsoft-IDP:er) som konfigurerats för att uppfylla kraven för Azure AD-integrering. Se riktlinjerna [för](https://www.microsoft.com/download/details.aspx?id=56843) mer information. <br><br>När du anger autentiseringsalternativ med Azure AD Connect rekommenderas även tillbakaskrivning av lösenord. Mer information finns i [Lösenords tillbakaskrivning.](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback) <br><br>Om en extern identitetsprovider implementeras måste du verifiera lösningen:<br>- Uppfyller kraven för Azure AD-integrering<br>- Stöder villkorsstyrd åtkomst i Azure AD, vilket gör att efterlevnadsprincipen för Microsoft Managed Desktop-enheter kan konfigureras<br>- Aktiverar enhetsregistrering och användning av Microsoft 365-tjänster eller -funktioner som krävs som en del av Microsoft Managed Desktop <br><br>Mer information om autentiseringsalternativ med Azure AD finns i inloggningsalternativen för Azure AD Connect.For more information on authentication options with Azure AD, see [Azure AD Connect user sign-in options.](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-user-signin)
Microsoft 365 | OneDrive för företag måste vara aktiverat för Microsoft-användare av hanterade skrivbord.<br><br>Även om det inte är nödvändigt att registrera sig för Microsoft Managed Desktop rekommenderar vi att följande tjänster migreras till molnet:<br>– E-post: Migrera till molnbaserade postlådor, Exchange Online eller konfigurera med Exchange Online-hybrid med Exchange 2013 eller senare, lokalt.<br>- Filer och mappar: Migrera till OneDrive för företag eller SharePoint Online.<br>- Verktyg för onlinesamarbete: Migrera till Teams.
Enhetshantering | Microsoft-enheter för hanterade datorer kräver hantering med Microsoft Intune. Intune måste anges som utfärdare av hantering av mobila enheter.<br><br>Mer information finns i [Microsoft Intune.](https://www.microsoft.com/cloud-platform/microsoft-intune) 
Säkerhetskopiering och återställning av data |  Microsoft Hanterat skrivbord kräver att filer synkroniseras till OneDrive för företag för skydd. Filer som inte synkroniseras till OneDrive för företag omfattas inte av Microsofts hanterade skrivbord och kan gå förlorade under enhetsutbyten eller supportsamtal som kräver återställning av enhet.<br><br>Även om det inte krävs rekommenderar Microsoft Managed Desktop migrering från mappade nätverksenheter till lämplig molnlösning. Mer information finns i Förbereda [mappade enheter för Microsoft Managed Desktop](mapped-drives.md)

När du är redo att komma igång med Microsoft Managed Desktop kontaktar du microsoft kontohanteraren. 

## <a name="more-about-licenses"></a>Mer om licenser

Microsoft Hanterat skrivbord kräver vissa licensalternativ för att fungera. Mer information [om hur licenserna](../intro/technologies.md) används finns i Microsofts tekniker för hanterade datorer.

> [!TIP]
> Om du vill tilldela licensalternativen till specifika användare rekommenderar vi att du använder den [gruppbaserade licensfunktionen](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal) i Azure Active Directory.

- Azure Active Directory Premium P1
- Microsoft Intune 
- Windows 10 Enterprise  
- Microsoft Defender för Endpoint
-  Microsoft 365 Apps för företag
- Microsoft Teams
- [SharePoint Online (abonnemang 2)](https://www.microsoft.com/microsoft-365/sharepoint/compare-sharepoint-plans)
- [Exchange Online-abonnemang 2](https://www.microsoft.com/microsoft-365/exchange/compare-microsoft-exchange-online-plans) 


> [!TIP]
> Med Microsoft Account Manager kan du granska dina aktuella licenser och tjänstplaner och hitta den effektivaste vägen för att få ytterligare licenser eller tjänstplaner du kan behöva, samtidigt som du undviker duplicering.
