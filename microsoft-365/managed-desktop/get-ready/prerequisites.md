---
title: Förutsättningar för Microsoft Hanterat skrivbord
description: Licenser, Azure-konton, autentiseringsinställningar och Microsoft 365-inställningar att konfigurera innan de registreras på Microsoft Managed Desktop
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 79ae949d9624021121492edb811a4ea5bfcc729a
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659146"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Förutsättningar för Microsoft Hanterat skrivbord

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

I det här avsnittet beskrivs infrastruktur kraven som måste uppfyllas för att du ska kunna se framgång med Microsoft Managed Desktop. 


Under | Krav uppgifter
--- | ---
Licensiering |Microsoft Managed Desktop kräver Microsoft 365 E3-licensen med Microsoft Defender för slut punkt och Azure Active Directory Premium 2 (eller motsvarande).<br>Mer information om specifika tjänst planer finns i [mer om licenser](#more-about-licenses) i det här avsnittet.<br>Mer information om tillgängliga licenser finns i [Microsoft 365-licensiering](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).
Anslutit |  Alla Microsoft hanterade Skriv bords enheter kräver anslutning till flera Microsoft-tjänst slut punkter från företags nätverket.<br><br>En fullständig lista över obligatoriska adresser och URL-adresser finns i [nätverks konfiguration](../get-ready/network.md). 
Azure Active Directory |    Azure Active Directory (Azure AD) måste antingen vara källan till auktoritet för alla användar konton eller användar konton måste synkroniseras från lokala Active Directory med den senaste versionen av Azure AD Connect som stöds.<br><br>[Roaming för företags status](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-overview) måste aktive ras för användare med Microsoft hanterade skriv bord.<br><br>Mer information finns i [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect).<br><br>Mer information om Azure AD Connect-versioner som stöds finns i [Azure AD Connect: versions historik](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-version-history).
Autentisering |    Om Azure AD inte är källan för primär verifikation för användar konton måste du konfigurera något av följande i Azure AD Connect:<br>-Lösenordssynkronisering för lösen ord<br>-Vidarekoppling<br>-En extern identitets leverantör (inklusive Windows Server ADFS och icke-Microsoft-IDPs) konfigurerade för att uppfylla Azure AD-integrerings kraven. Se [rikt linjerna](https://www.microsoft.com/download/details.aspx?id=56843) för mer information. <br><br>När du anger autentiseringsalternativ med Azure AD Connect rekommenderas du också att välja lösen ord. Mer information finns i [Ångra lösen ord](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback). <br><br>Om en extern identitetsprovider implementeras måste du verifiera lösningen:<br>-Uppfyller kraven för Azure AD-integrering<br>-Stöder villkorlig åtkomst för Azure AD, som gör att Microsoft Managed Desktop-enhetskompatibilitet kan konfigureras<br>-Aktiverar enhets registrering och användning av Microsoft 365-tjänster eller funktioner som krävs som en del av Microsoft Managed Desktop <br><br>Mer information om autentiseringsalternativ med Azure AD finns i alternativ för [Azure AD Connect-inloggning](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-user-signin).
Microsoft 365 | OneDrive för företag måste vara aktiverat för användare med Microsoft hanterade skriv bord.<br><br>Även om det inte behövs för att registrera dig hos Microsoft Managed Desktop bör följande tjänster migreras till molnet:<br>-E-post: migrera till molnbaserade post lådor, Exchange Online eller konfigurera med Exchange Online hybrid med Exchange 2013 eller senare, lokalt.<br>-Filer och mappar: migrera till OneDrive för företag eller SharePoint Online.<br>-Verktyg för samarbete online: migrera till Teams.
Enhetshantering | Microsoft Managed Station ära enheter kräver hantering med Microsoft Intune. Intune måste anges som hanterings myndigheten för mobila enheter.<br><br>Mer information finns i [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune). 
Säkerhets kopiering och återställning av data |  Microsoft Managed Desktop kräver att filer synkroniseras till OneDrive för företag för att skyddas. Alla filer som inte synkroniseras till OneDrive för företag garanteras inte av Microsoft Managed Desktop och kan gå förlorade under enhets byten eller support samtal som kräver återställning av en enhet.<br><br>Men inte obligatoriskt rekommenderar Microsoft Managed Desktop att migrera från anslutna nätverks enheter till lämplig moln lösning. Mer information finns i [förbereda anslutna enheter för Microsoft Managed Desktop](mapped-drives.md)

När du är redo att komma igång med Microsoft Managed Desktop kontaktar du din Microsoft Account Manager. 

## <a name="more-about-licenses"></a>Mer om licenser

Microsoft Managed Desktop kräver vissa licens alternativ för att fungera. Se [Microsoft Managed Desktop Technologies](../intro/technologies.md) för information om hur dessa licenser används.

> [!TIP]
> För att tilldela dessa licens alternativ till vissa användare rekommenderar vi att du använder den [gruppbaserade licensierings funktionen](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal) i Azure Active Directory.

- Azure Active Directory Premium P2
- Microsoft Intune 
- Windows 10 Enterprise  
- Microsoft Defender för Endpoint
-  Microsoft 365 Apps för företag
- Microsoft Teams
- [SharePoint Online (abonnemang 2)](https://www.microsoft.com/microsoft-365/sharepoint/compare-sharepoint-plans)
- [Exchange Online-abonnemang 2](https://www.microsoft.com/microsoft-365/exchange/compare-microsoft-exchange-online-plans) 


> [!TIP]
> Din Microsoft-tjänsthanteraren hjälper dig att granska dina befintliga licenser och tjänste planer och hitta den mest effektiva vägen för dig att få ytterligare licenser eller Service abonnemang som du kan behöva, samtidigt som du undviker dubbletter.
