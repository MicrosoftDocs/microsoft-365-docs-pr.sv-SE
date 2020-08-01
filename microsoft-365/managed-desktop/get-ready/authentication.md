---
title: Förbereda lokala resurser till gång för Microsoft Hanterat skrivbord
description: Viktiga steg för att se till att en Azure AD kan kommunicera med lokala AD för att tillhandahålla autentisering
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 7caeee6f476fea7881884cea20bd2a59db2c13d9
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/30/2020
ms.locfileid: "46530049"
---
#  <a name="prepare-on-premises-resources-access-for-microsoft-managed-desktop"></a>Förbereda lokala resurser till gång för Microsoft Hanterat skrivbord

I Microsoft Managed Desktop ansluts enheter automatiskt till Azure Active Directory (Azure AD). Det innebär att om du använder en lokal Active Directory måste du kontrollera vissa saker för att säkerställa att enheter som är anslutna till Azure AD kan kommunicera med din lokala Active Directory. 

> [!NOTE]  
> *Hybrid (hybrid)* Azure AD-anslutning stöds inte av Microsoft Managed Desktop.

Med Azure Active Directory kan användarna dra nytta av Enkel inloggning (SSO), vilket innebär att de vanligtvis inte behöver ange autentiseringsuppgifter varje gång de använder resurser.

Information om hur du går med i Azure Active Directory finns i [Så här: Planera implementeringen av Azure AD-koppling](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan). Bakgrundsinformation om Enkel inloggning (SSO) på enheter som är anslutna till Azure AD finns i [Så här fungerar SSO till lokala resurser på Azure AD-anslutna enheter](https://docs.microsoft.com/azure/active-directory/devices/azuread-join-sso#how-it-works).


I det här avsnittet beskrivs de saker du behöver kontrollera för att se till att appar och andra resurser som är beroende av lokal Active Directory-anslutning fungerar smidigt med Microsoft Managed Desktop.


## <a name="single-sign-on-for-on-premises-resources"></a>Enkel inloggning för lokala resurser

Enkel inloggning (SSO) med UPN och lösenord är aktiverat som standard på Microsoft Managed Desktop Devices. Men användarna kan också använda Windows Hello för företag, vilket kräver några extra installationssteg. 

### <a name="single-sign-on-by-using-upn-and-password"></a>Enkel inloggning med UPN och lösenord

I de flesta organisationer kan användarna använda SSO för att autentisera med UPN och lösenord på Microsoft Managed Desktop Devices. Men för att se till att detta kommer att fungera, bör du dubbelkolla följande:

- Bekräfta att Azure AD Connect har konfigurerats och använder en lokal Active Directory-server som kör Windows Server 2008 R2 eller senare.
- Bekräfta att Azure AD Connect kör en version som stöds och är inställd på att synkronisera dessa tre attribut med Azure AD: 
    - DNS-domännamn för den lokala Active Directory (där slutanvändarna finns)
    - NetBIOS för din lokala Active Directory (där slutanvändarna finns)
    - ANVÄNDARENS SAM-kontonamn


### <a name="single-sign-on-by-using-windows-hello-for-business"></a>Enkel inloggning med Windows Hello för företag

Microsoft Managed Desktop-enheter ger också användarna en snabb, lösenordslös upplevelse genom att använda Windows Hello för företag. Om du vill vara säkra på att Windows Hello för företag fungerar utan att användarna behöver ange respektive UPN och lösenord besöker du [Konfigurera Azure AD-anslutna enheter för lokala en inloggning med Windows Hello för företag för](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base) att kontrollera kraven och följ sedan stegen där.


## <a name="apps-and-resources-that-use-authentication"></a>Appar och resurser som använder autentisering

Se [Förstå överväganden för program och resurser](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources) i Azure-innehållsuppsättningen för fullständig vägledning om hur du konfigurerar appar för att arbeta med Azure Active Directory. Sammanfattningsvis:


- Om du använder **molnbaserade appar,** till exempel de som läggs till i Azure AD-appgalleriet, kräver de flesta inte några ytterligare förberedelser för att arbeta med Microsoft Managed Desktop. Alla Win32-appar som inte använder WAM (Web Account Manager) kan dock fortfarande uppmana användarna att autentisering.

- För appar som finns **lokalt**måste du lägga till dessa appar i listan över betrodda webbplatser i webbläsaren. Detta gör det möjligt för Windows-autentisering att fungera sömlöst, utan att användarna uppmanas att ange autentiseringsuppgifter. Det gör du genom att referera till [Betrodda platser](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/config-setting-ref#trusted-sites) i [referensen konfigurerbara inställningar](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/config-setting-ref).

- Om du använder Active Directory-federerade tjänster kontrollerar du att SSO är aktiverat med hjälp av stegen i [Verifiera och hantera enkel inloggning med AD FS](https://docs.microsoft.com/previous-versions/azure/azure-services/jj151809(v=azure.100)). 

- För appar som är **lokala och använder äldre protokoll**krävs ingen extra konfiguration, så länge enheterna har åtkomst till en lokal domänkontrollant för att autentisera. Om du vill ge säker åtkomst för dessa program bör du dock distribuera Azure AD Application Proxy. Mer information finns i [Fjärråtkomst till lokala program via Azure Active Directorys programproxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).

- Appar som körs **lokalt och förlitar sig på datorautentisering** stöds inte, så du bör överväga att ersätta dessa med nyare versioner.

### <a name="network-shares-that-use-authentication"></a>Nätverksresurser som använder autentisering

Ingen extra konfiguration krävs för att användare ska komma åt nätverksresurser, så länge enheterna har åtkomst till en lokal domänkontrollant med hjälp av en UNC-sökväg.

### <a name="printers"></a>Skrivare

Microsoft Hanterade stationära enheter kan inte ansluta till skrivare som publiceras i din lokala Active Directory om du inte har konfigurerat [Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).

Även om skrivare inte kan identifieras automatiskt i en molnmiljö kan användarna använda lokala skrivare med hjälp av skrivarsökvägen eller skrivarkösökvägen, så länge enheterna har åtkomst till en lokal domänkontrollant.

<!--add fuller material on printers when available-->
