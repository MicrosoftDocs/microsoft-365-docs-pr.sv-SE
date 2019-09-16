---
title: Aktivera domänanslutna Windows 10-enheter för hantering i Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: Läs om hur du aktiverar Microsoft 365 för att skydda lokala AD-anslutna Windows 10-enheter.
ms.openlocfilehash: 5cce4bc53f118560e31ad7e6048e4efcb49d662e
ms.sourcegitcommit: c0f769244d05ad019ea2307c38d5543d7b1e5afd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/16/2019
ms.locfileid: "36992238"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a>Aktivera domänanslutna Windows 10-enheter för hantering i Microsoft 365 Business

Om din organisation använder Windows Server Active Directory lokalt kan du konfigurera Microsoft 365 Business för att skydda dina Windows 10-enheter, samtidigt som du behåller åtkomsten till lokala resurser som kräver lokal autentisering. Du kan ställa in detta genom att först synkronisera Active Directory med Azure Active Directory, följt av att registrera Windows 10-enheter med Azure AD och registrerar dem för hantering av mobila enheter av Microsoft 365 Business.
I följande video beskrivs stegen för hur du ställer in detta för det vanligaste scenariot.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  
## <a name="set-up-domain-joined-devices-to-be-managed-by-microsoft-365-business"></a>Konfigurera domänanslutna enheter som ska hanteras av Microsoft 365 Business

Om du vill ställa in organisationens domänanslutna enheter att dra nytta av de funktioner som tillhandahålls av Azure Active Directory förutom lokal Active Directory, kan du implementera **hybrid Azure AD-anslutna enheter**. Dessa är enheter som är anslutna både till din lokala Active Directory och Azure Active Directory. Hybrid Azure AD-anslutna enheter kan skyddas och hanteras av Microsoft 365 Business. 
  
Slutför stegen nedan för att göra dina Windows 10-enheter hybrid Azure AD ansluten och hanteras av Microsoft 365 Business.
  
1. Om du vill synkronisera dina användare, grupper och kontakter från lokala Active Directory till Azure Active Directory, kör guiden katalogsynkronisering och Azure Active Directory Connect enligt beskrivningen i [Konfigurera katalogsynkronisering för Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).
    
    > [!NOTE]
    > Stegen är exakt desamma för Microsoft 365 Business. 
  
2. Innan du Slutför steg 3 för att aktivera Windows 10-enheter som ska vara hybrid Azure AD-anslutna, måste du kontrollera att du uppfyller följande krav:

   - Du kör den senaste versionen av Azure AD Connect.

   - Azure AD Connect har synkroniserat alla datorobjekten för de enheter som du vill ska vara hybrid Azure AD ansluten. Om datorobjekten tillhör specifika organisationsenheter (OU), kontrollera att dessa organisationsenheter har angetts för synkronisering i Azure AD Connect samt.
    
3. Registrera befintliga domänanslutna Windows 10-enheter som ska vara hybrid Azure AD-anslutna och registrera dem för hantering av mobila enheter av Intune (Microsoft 365 Business):
    
4. Följ anvisningarna steg för steg i [så här konfigurerar du hybrid Azure Active Directory-anslutna enheter](https://go.microsoft.com/fwlink/p/?linkid=872870). Detta gör att synkroniseringen av din lokala Active Directory-anslutna Windows 10-datorer och göra dem molnanpassade.
    
5. För att registrera en Windows 10-enhet för hantering av mobila enheter, se [Registrera en Windows 10-enhet med Intune med hjälp av en grupprincip](https://go.microsoft.com/fwlink/p/?linkid=872871) för instruktioner. Du kan ange grupprincipen på en lokal datornivå eller för massåtgärder, du kan skapa den här grupprincipinställningen på domänkontrollantens Server.