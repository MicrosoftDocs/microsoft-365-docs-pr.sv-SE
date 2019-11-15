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
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: Läs om hur du aktiverar Microsoft 365 för att skydda lokala Active Directory-anslutna Windows 10-enheter.
ms.openlocfilehash: 93e3364fc94f3878bec13d0a87b17a7d3678a4cc
ms.sourcegitcommit: 9a057e70637dcfe06d4f729a96c02be989cf9e25
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/14/2019
ms.locfileid: "38633278"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a>Aktivera domänanslutna Windows 10-enheter för hantering i Microsoft 365 Business

Om din organisation använder Windows Server Active Directory lokalt kan du konfigurera Microsoft 365 Business för att skydda dina Windows 10-enheter, samtidigt som du behåller åtkomsten till lokala resurser som kräver lokal autentisering.
Du kan konfigurera det här skyddet genom att implementera **hybrid Azure AD-anslutna enheter**. Dessa enheter är anslutna till både din lokala Active Directory och Azure Active Directory.

Den här videon beskriver stegen för hur du ställer in detta för det vanligaste scenariot, som också beskrivs i stegen som följer.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="1-prepare-for-directory-synchronization"></a>1. Förbered för katalogsynkronisering 

Innan du synkroniserar dina användare och datorer från den lokala Active Directory-domänen, granska [Förbered för katalogsynkronisering till Office 365](https://docs.microsoft.com/office365/enterprise/prepare-for-directory-synchronization). I synnerhet:

   - Kontrollera att inga dubbletter finns i katalogen för följande attribut: **mail**, **proxyAddresses**och **userPrincipalName**. Dessa värden måste vara unika och eventuella dubbletter måste tas bort.
   
   - Vi rekommenderar att du konfigurerar attributet **userPrincipalName** (UPN) för varje lokalt användarkonto så att den matchar den primära e-postadressen som motsvarar den licensierade Microsoft 365-användaren. Till exempel: *Mary.Shelley@contoso.com* i stället för *Mary@contoso. local*
   
   - Om Active Directory-domänen slutar i ett icke-dirigerbart suffix som *. local* eller *. LAN*, i stället för ett Internet dirigerbara suffix som *. com* eller *. org*, justerar du UPN-suffixet för de lokala användarkontona först enligt beskrivningen i [Förbered en icke-dirigerbar domän för katalogsynkronisering](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization). 

## <a name="2-install-and-configure-azure-ad-connect"></a>2. Installera och konfigurera Azure AD Connect

Om du vill synkronisera dina användare, grupper och kontakter från den lokala Active Directory till Azure Active Directory, installera Azure Active Directory Connect och konfigurera katalogsynkronisering. Mer information finns [i konfigurera katalogsynkronisering för Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846) .

> [!NOTE]
> Stegen är exakt desamma för Microsoft 365 Business. 

När du konfigurerar dina alternativ för Azure AD Connect, rekommenderar vi att du aktiverar **Lösenordssynkronisering**, **sömlös enkel inloggning**och funktionen för **tillbakaskrivning av lösenord** , som också stöds i Microsoft 365 Business.

> [!NOTE]
> Det finns några ytterligare steg för tillbakaskrivning av lösenord bortom kryssrutan i Azure AD Connect. Mer information finns i [så här: Konfigurera tillbakaskrivning av lösenord](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback). 

## <a name="3-configure-hybrid-azure-ad-join"></a>3. Konfigurera hybrid Azure AD Join

Innan du aktiverar Windows 10-enheter ska vara hybrid Azure AD-anslutna, kontrollera att du uppfyller följande krav:

   - Du kör den senaste versionen av Azure AD Connect.

   - Azure AD Connect har synkroniserat alla datorobjekten för de enheter som du vill ska vara hybrid Azure AD ansluten. Om datorobjekten tillhör specifika organisationsenheter (OU), kontrollera att dessa organisationsenheter har angetts för synkronisering i Azure AD Connect samt.

Om du vill registrera befintliga domänanslutna Windows 10-enheter som hybrid Azure AD ansluten följer du stegen i [självstudien: Konfigurera hybrid Azure Active Directory-anslutning för hanterade domäner](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join). Den här hybrid-aktiverar din befintliga lokala Active Directory-anslutna Windows 10-datorer och göra dem molnanpassade.
    
## <a name="4-enable-automatic-enrollment-for-windows-10"></a>4. Aktivera automatisk registrering för Windows 10

 Om du automatiskt vill registrera Windows 10-enheter för hantering av mobila enheter i Intune, se [Registrera en Windows 10-enhet automatiskt med Grupprincip](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy). Du kan ange grupprincipen på en lokal datornivå, eller för massåtgärder, kan du använda konsolen Grupprinciphantering och ADMX-mallar för att skapa den här grupprincipinställningen på domänkontrollanten.

## <a name="5-configure-seamless-single-sign-on"></a>5. Konfigurera sömlös enkel inloggning

  Sömlös SSO loggar automatiskt användare i sina Microsoft 365 molnresurser när de använder företagsdatorer. Bara distribuera ett av de två grupprincip-alternativ som beskrivs i [Azure Active Directory sömlös enkel inloggning: Snabbstart](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso-quick-start#step-2-enable-the-feature). Alternativet **Grupprincip** tillåter inte användare att ändra sina inställningar, medan inställningsalternativet **Grupprincip** anger värdena men också lämnar dem som kan konfigureras av användaren.

## <a name="6-set-up-windows-hello-for-business"></a>6. Konfigurera Windows Hello för företag

 Windows Hello för företag ersätter lösenord med stark tvåfaktorsautentisering (2FA) för att logga in på en lokal dator. En faktor är ett asymmetriskt nyckelpar, och den andra är en PIN-kod eller annan lokal gest som fingeravtryck eller ansiktsigenkänning om enheten stöder det. Vi rekommenderar att du ersätter lösenord med 2FA och Windows Hello för företag där det är möjligt.

Om du vill konfigurera hybrid Windows Hello för företag, granska [hybrid nyckel förtroende Windows Hello för företag förutsättningar](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-trust-prereqs). Följ sedan instruktionerna i [Konfigurera hybrid Windows Hello för Business nyckel förtroendeinställningar](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-whfb-settings). 
