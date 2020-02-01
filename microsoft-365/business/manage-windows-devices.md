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
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: Lär dig hur du aktiverar Microsoft 365 för att skydda lokala Active Directory-anslutna Windows 10-enheter.
ms.openlocfilehash: 170703c7367f9c0e9cb4c10edbd81cb214aa1d3e
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41593810"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a>Aktivera domänanslutna Windows 10-enheter för hantering i Microsoft 365 Business

Om din organisation använder Windows Server Active Directory lokalt kan du konfigurera Microsoft 365 Business för att skydda dina Windows 10-enheter, samtidigt som du behåller åtkomsten till lokala resurser som kräver lokal autentisering.
Om du vill konfigurera det här skyddet kan du implementera **Hybrid Azure AD-anslutna enheter**.To set up this protection, you can implement Hybrid Azure AD joined devices . Dessa enheter är anslutna till både din lokala Active Directory och din Azure Active Directory.These devices are joined to both your on-premises Active Directory and your Azure Active Directory.

Den här videon beskriver stegen för hur du ställer in den här för det vanligaste scenariot, som också beskrivs i stegen som följer.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="1-prepare-for-directory-synchronization"></a>1. Förbered för katalogsynkronisering 

Innan du synkroniserar användare och datorer från den lokala Active Directory-domänen läser du [Förbered för katalogsynkronisering till Office 365](https://docs.microsoft.com/office365/enterprise/prepare-for-directory-synchronization). I synnerhet gäller följande:

   - Kontrollera att det inte finns några dubbletter i katalogen för följande attribut: **e-post,** **proxyAddresses**och **userPrincipalName**. Dessa värden måste vara unika och eventuella dubbletter måste tas bort.
   
   - Vi rekommenderar att du konfigurerar attributet **userPrincipalName** (UPN) för varje lokalt användarkonto så att det matchar den primära e-postadress som motsvarar den licensierade Microsoft 365-användaren. Till exempel: *mary.shelley@contoso.com* snarare än *mary@contoso.local*
   
   - Om Active Directory-domänen slutar i ett icke-dirigerbart suffix som *.local* eller *.lan,* i stället för ett internetdir suffix som *.com* eller *.org,* justerar du UPN-suffixet för de lokala användarkontona först enligt beskrivningen i [Förbereda en icke-dirigerbar domän för katalogsynkronisering](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization). 

## <a name="2-install-and-configure-azure-ad-connect"></a>2. Installera och konfigurera Azure AD Connect

Om du vill synkronisera användare, grupper och kontakter från den lokala Active Directory till Azure Active Directory installerar du Azure Active Directory Connect och konfigurerar katalogsynkronisering. Mer information finns i [Konfigurera katalogsynkronisering för Office 365.](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846)

> [!NOTE]
> Stegen är exakt desamma för Microsoft 365 Business. 

När du konfigurerar dina alternativ för Azure AD Connect rekommenderar vi att du aktiverar **lösenordssynkronisering,** **sömlös enkel inloggning**och funktionen för återskrivning av **lösenord,** som också stöds i Microsoft 365 Business.

> [!NOTE]
> Det finns några ytterligare steg för tillbakaskrivning av lösenord utöver kryssrutan i Azure AD Connect. Mer information finns i [Så här konfigurerar du tillbakaskrivning av lösenord](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback). 

## <a name="3-configure-hybrid-azure-ad-join"></a>3. Konfigurera Hybrid Azure AD Join

Innan du aktiverar Windows 10-enheter som Hybrid Azure AD-ansluten kontrollerar du att du uppfyller följande förutsättningar:Before you enable Windows 10 devices to be Hybrid Azure AD joined, make sure that you meet the following prerequisites:

   - Du kör den senaste versionen av Azure AD Connect.You're running the latest version of Azure AD Connect.

   - Azure AD connect har synkroniserat alla datorobjekt på de enheter som du vill vara hybrid Azure AD-ansluten. Om datorobjekten tillhör specifika organisationsenheter (OU) kontrollerar du att dessa organisationsenheter också är inställda för synkronisering i Azure AD-anslutning.

Om du vill registrera befintliga domänanslutna Windows 10-enheter som Hybrid Azure AD-ansluten följer du stegen i [självstudien: Konfigurera hybrid Azure Active Directory-anslutning för hanterade domäner](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join). Den här hybrid-aktiverar din befintliga lokala Active Directory anslutna Windows 10-datorer och gör dem moln redo.
    
## <a name="4-enable-automatic-enrollment-for-windows-10"></a>4. Aktivera automatisk registrering för Windows 10

 Information om hur du automatiskt registrerar Windows 10-enheter för hantering av mobila enheter i Intune finns i [Registrera en Windows 10-enhet automatiskt med hjälp av Grupprincip](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy). Du kan ange grupprincipen på lokal datornivå eller för massåtgärder kan du använda grupprinciphanteringskonsolen och ADMX-mallarna för att skapa den här grupprincipinställningen på domänkontrollanten.

## <a name="5-configure-seamless-single-sign-on"></a>5. Konfigurera sömlös enkel inloggning

  Sömlös enkel inloggning loggar automatiskt in användare i sina Microsoft 365-molnresurser när de använder företagsdatorer. Distribuera bara ett av de två grupprincipalternativen som beskrivs i enkel inloggning för [Azure Active Directory Seamless: Snabbstart](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso-quick-start#step-2-enable-the-feature). Alternativet **Grupprincip** tillåter inte användare att ändra sina inställningar, medan alternativet **Grupprincipinställningar** anger värdena men också gör dem användarkonfigurerbara.

## <a name="6-set-up-windows-hello-for-business"></a>6. Konfigurera Windows Hello för företag

 Windows Hello för företag ersätter lösenord med stark tvåfaktorsautentisering (2FA) för att logga in på en lokal dator. En faktor är ett asymmetriskt nyckelpar och den andra är en PIN-kod eller annan lokal gest, till exempel fingeravtryck eller ansiktsigenkänning om enheten stöder den. Vi rekommenderar att du ersätter lösenord med 2FA och Windows Hello for Business där det är möjligt.

Om du vill konfigurera Hybrid Windows Hello för företag läser du [Hybrid Key-förtroendet för Windows Hello for Business Prerequisites](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-trust-prereqs). Följ sedan instruktionerna i Konfigurera inställningar för [hybrid-Windows Hello för företag- nyckelförtroende](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-whfb-settings). 
