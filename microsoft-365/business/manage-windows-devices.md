---
title: Aktivera domänanslutna Windows 10-enheter som ska hanteras av Microsoft 365 för företag
f1.keywords:
- NOCSH
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
- seo-marvel-mar
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: Lär dig hur du aktiverar Microsoft 365 för att skydda lokala Active-Directory-anslutna Windows 10-enheter i några få steg.
ms.openlocfilehash: adc125c32fe5aa56be8c17c07f28316602a36594
ms.sourcegitcommit: 46644f9778bc70ab6d62783e0a1e60ba2eccc27f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/08/2020
ms.locfileid: "44165818"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-for-business"></a>Aktivera domänanslutna Windows 10-enheter som ska hanteras av Microsoft 365 för företag

Om din organisation använder Windows Server Active Directory lokalt kan du konfigurera Microsoft 365 för företag för att skydda dina Windows 10-enheter, samtidigt som du behåller åtkomsten till lokala resurser som kräver lokal autentisering.
Om du vill konfigurera det här skyddet kan du implementera **Hybrid Azure AD-anslutna enheter**. Dessa enheter är anslutna till både din lokala Active Directory och din Azure Active Directory.

I det här videoklippet beskrivs stegen för hur du konfigurerar det här för det vanligaste scenariot, vilket också beskrivs i de steg som följer.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="1-prepare-for-directory-synchronization"></a>1. Förbered för katalogsynkronisering 

Innan du synkroniserar användare och datorer från den lokala Active Directory-domänen läser du [Förbered för katalogsynkronisering till Office 365](https://docs.microsoft.com/office365/enterprise/prepare-for-directory-synchronization). I synnerhet gäller följande:

   - Kontrollera att det inte finns några dubbletter i katalogen för följande attribut: **e-post**, **proxyAdresser**och **userPrincipalName**. Dessa värden måste vara unika och eventuella dubbletter måste tas bort.
   
   - Vi rekommenderar att du konfigurerar attributet **userPrincipalName** (UPN) för varje lokalt användarkonto så att det matchar den primära e-postadressen som motsvarar den licensierade Microsoft 365-användaren. Till exempel: *mary.shelley@contoso.com* i stället *för mary@contoso.local*
   
   - Om Active Directory-domänen slutar i ett suffix som inte är dirigerbart som *.local* eller *.lan*i stället för ett internetrdigerbart suffix som *.com* eller *.org*justerar du UPN-suffixet för de lokala användarkontona först enligt beskrivningen i [Förbered en icke-dirigerbar domän för katalogsynkronisering](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization). 

## <a name="2-install-and-configure-azure-ad-connect"></a>2. Installera och konfigurera Azure AD Connect

Om du vill synkronisera användare, grupper och kontakter från den lokala Active Directory till Azure Active Directory installerar du Azure Active Directory Connect och konfigurerar katalogsynkronisering. Mer information finns i [Konfigurera katalogsynkronisering för Office 365.](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization)

> [!NOTE]
> Stegen är exakt desamma för Microsoft 365 för företag. 

När du konfigurerar dina alternativ för Azure AD Connect rekommenderar vi att du aktiverar **lösenordssynkronisering,** **sömlös enkel inloggning**och **tillbakaskrivningsfunktionen** för lösenord, som också stöds i Microsoft 365 för företag.

> [!NOTE]
> Det finns ytterligare några steg för återställning av lösenord utanför kryssrutan i Azure AD Connect. Mer information finns i [Så här konfigurerar du tillbaka lösenordet](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback). 

## <a name="3-configure-hybrid-azure-ad-join"></a>3. Konfigurera Hybrid Azure AD-anslutning

Innan du aktiverar Windows 10-enheter så att Hybrid Azure AD går med i, se till att du uppfyller följande förutsättningar:

   - Du kör den senaste versionen av Azure AD Connect.

   - Azure AD connect har synkroniserat alla datorobjekt på de enheter som du vill ska vara hybrid Azure AD-anslutna. Om datorobjekten tillhör specifika organisationsenheter (OU) kontrollerar du att dessa organisationsenheter också är inställda för synkronisering i Azure AD connect.

Om du vill registrera befintliga domänanslutna Windows 10-enheter som Hybrid Azure AD gick med i följer du stegen i [självstudien: Konfigurera hybrid-Azure Active Directory-anslutning för hanterade domäner](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join). Den här hybriden aktiverar din befintliga lokala Active Directory-anslutna Windows 10-datorer och gör dem molnklara.
    
## <a name="4-enable-automatic-enrollment-for-windows-10"></a>4. Aktivera automatisk registrering för Windows 10

 Information om hur du automatiskt registrerar Windows 10-enheter för hantering av mobila enheter i Intune finns i [Registrera en Windows 10-enhet automatiskt med grupprincip](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy). Du kan ange grupprincipen på lokal datornivå eller för massåtgärder, du kan använda mallarna Grupprinciphantering och ADMX för att skapa den här grupprincipinställningen på domänkontrollanten.

## <a name="5-configure-seamless-single-sign-on"></a>5. Konfigurera sömlös enkel inloggning

  Sömlös SSO signerar automatiskt användare i sina Microsoft 365-molnresurser när de använder företagsdatorer. Distribuera bara ett av de två grupprincipalternativen som beskrivs i [Azure Active Directory Seamless Single Sign-On: Snabbstart](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso-quick-start#step-2-enable-the-feature). Alternativet **Grupprincip** tillåter inte att användarna ändrar sina inställningar, medan alternativet **Grupprincipinställningar** anger värdena men också gör att de kan konfigureras av användaren.

## <a name="6-set-up-windows-hello-for-business"></a>6. Konfigurera Windows Hello för företag

 Windows Hello för företag ersätter lösenord med stark tvåfaktorsautentisering (2FA) för signering på en lokal dator. En faktor är ett asymmetriskt nyckelpar och det andra är en PIN-kod eller annan lokal gest, till exempel fingeravtryck eller ansiktsigenkänning om enheten stöder det. Vi rekommenderar att du byter lösenord mot 2FA och Windows Hello för företag där det är möjligt.

Om du vill konfigurera Hybrid Windows Hello för företag läser du [hybridnyckelns förtroende för Windows Hello for Business Förutsättningar](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-trust-prereqs). Följ sedan instruktionerna i [Konfigurera inställningar för hybrid windows hello för företag-nyckelförtroende .](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-whfb-settings) 
