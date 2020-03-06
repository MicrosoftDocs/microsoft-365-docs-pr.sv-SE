---
title: Aktivera domänanslutna Windows 10-enheter för hantering i Microsoft 365 Business
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
- MARVEL_SEO_MAR
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: Lär dig hur du aktiverar Microsoft 365 för att skydda lokala Windows 10-enheter med Active-Directory i bara några få steg.
ms.openlocfilehash: 8d7caefa1ddcadf684fdb5b712601b1bdd4fb5bd
ms.sourcegitcommit: 26e4d5091583765257b7533b5156daa373cd19fe
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/06/2020
ms.locfileid: "42550256"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a>Aktivera domänanslutna Windows 10-enheter för hantering i Microsoft 365 Business

Om din organisation använder Windows Server Active Directory lokalt kan du konfigurera Microsoft 365 Business för att skydda dina Windows 10-enheter, samtidigt som du behåller åtkomsten till lokala resurser som kräver lokal autentisering.
Om du vill konfigurera det här skyddet kan du implementera **Hybrid Azure AD-anslutna enheter**. Dessa enheter är anslutna till både din lokala Active Directory och din Azure Active Directory.

I det här videoklippet beskrivs stegen för hur du ställer in detta för det vanligaste scenariot, som också beskrivs i de steg som följer.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="1-prepare-for-directory-synchronization"></a>1. Förbered för katalogsynkronisering 

Innan du synkroniserar användarna och datorerna från den lokala Active Directory-domänen läser du [Förbered för katalogsynkronisering till Office 365](https://docs.microsoft.com/office365/enterprise/prepare-for-directory-synchronization). I synnerhet gäller följande:

   - Kontrollera att det inte finns några dubbletter i katalogen för följande attribut: **e-post,** **proxyAdresser**och **userPrincipalName**. Dessa värden måste vara unika och alla dubbletter måste tas bort.
   
   - Vi rekommenderar att du konfigurerar UPN-attributet **userPrincipalName** (UPN) för varje lokalt användarkonto så att den matchar den primära e-postadressen som motsvarar den licensierade Microsoft 365-användaren. Till exempel: *mary.shelley@contoso.com* snarare än *mary@contoso.local*
   
   - Om Active Directory-domänen slutar i ett icke-dirigerat suffix som *.local* eller *.lan*, i stället för ett internetroutable suffix som *.com* eller *.org,* justerar DU UPN-suffixet för de lokala användarkontona först enligt beskrivningen i [Förbered en domän som inte är dirigerbar för katalogsynkronisering](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization). 

## <a name="2-install-and-configure-azure-ad-connect"></a>2. Installera och konfigurera Azure AD Connect

Om du vill synkronisera användarna, grupperna och kontakterna från den lokala Active Directory till Azure Active Directory installerar du Azure Active Directory Connect och konfigurerar katalogsynkronisering. Mer information [finns i Konfigurera katalogsynkronisering för Office 365.](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846)

> [!NOTE]
> Stegen är exakt desamma för Microsoft 365 Business. 

När du konfigurerar dina alternativ för Azure AD Connect rekommenderar vi att du aktiverar **lösenordssynkronisering,** **sömlös enkel inloggning**och **funktionen för tillbakaskrivning av lösenord,** vilket också stöds i Microsoft 365 Business.

> [!NOTE]
> Det finns ytterligare några steg för lösenordsavskrivning utöver kryssrutan i Azure AD Connect. Mer information finns i Så här konfigurerar du [lösenordsavskrivning](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback). 

## <a name="3-configure-hybrid-azure-ad-join"></a>3. Konfigurera Hybrid Azure AD Join

Innan du aktiverar Windows 10-enheter som Hybrid Azure AD-sammanfogade kontrollerar du att du uppfyller följande förutsättningar:

   - Du kör den senaste versionen av Azure AD Connect.

   - Azure AD connect har synkroniserat alla datorobjekt för de enheter som du vill vara hybrid Azure AD ansluten. Om datorobjekten tillhör specifika organisationsenheter (OU) kontrollerar du att dessa organisationsenheter också är inställda för synkronisering i Azure AD connect.

Så här registrerar du befintliga domänanslutna Windows 10-enheter som Hybrid Azure AD som är sammanfogat i [självstudiekursen: Konfigurera hybrid Azure Active Directory-koppling för hanterade domäner](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join). Den här hybriden gör att din befintliga lokala Active Directory anslöt till Windows 10-datorer och gör dem till molnet redo.
    
## <a name="4-enable-automatic-enrollment-for-windows-10"></a>4. Aktivera automatisk registrering för Windows 10

 Information om hur du registrerar Windows 10-enheter automatiskt för hantering av mobila enheter i Intune finns i [Registrera en Windows 10-enhet automatiskt med grupprincipen](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy). Du kan ange grupprincipen på lokal datornivå eller för massåtgärder kan du använda grupprinciphanteringskonsolen och ADMX-mallarna för att skapa den här grupprincipinställningen på domänkontrollanten.

## <a name="5-configure-seamless-single-sign-on"></a>5. Konfigurera sömlös enkel inloggning

  Sömlössa SSO loggar automatiskt in användare i sina Microsoft 365-molnresurser när de använder företagsdatorer. Distribuera helt enkelt ett av de två grupprincipalternativ som beskrivs i [Azure Active Directory Seamless Single Sign-On: Quick start](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso-quick-start#step-2-enable-the-feature). **Grupprincipalternativet** tillåter inte användare att ändra sina inställningar, medan alternativet **Grupprincippreferens** anger värdena men också lämnar dem användarkonfigurerbara.

## <a name="6-set-up-windows-hello-for-business"></a>6. Konfigurera Windows Hello for Business

 Windows Hello for Business ersätter lösenord med stark tvåfaktorsautentisering (2FA) för att logga in på en lokal dator. En faktor är ett asymmetriskt nyckelpar, och det andra är en PIN-kod eller annan lokal gest, till exempel fingeravtryck eller ansiktsigenkänning om enheten stöder den. Vi rekommenderar att du ersätter lösenord med 2FA och Windows Hello for Business där det är möjligt.

Om du vill konfigurera Hybrid Windows Hello for Business läser du [hybridnyckeln sett till Windows Hello for Business-förutsättningar](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-trust-prereqs). Följ sedan instruktionerna i [Konfigurera Hybrid Windows Hello for Business-knappförtroendeinställningar](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-whfb-settings). 
