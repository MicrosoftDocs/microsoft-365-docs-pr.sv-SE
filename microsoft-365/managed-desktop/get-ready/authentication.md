---
title: Förbereda lokal resursåtkomst för Microsoft Managed Desktop
description: Viktiga steg för att se till att en Azure AD kan kommunicera med lokal AD för att tillhandahålla autentisering
keywords: Microsoft Managed Desktop, Microsoft 365, tjänst, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: c4ebe0c7ad3d1e197cf90cc975366df61d3b0cb5
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/23/2019
ms.locfileid: "42811111"
---
#  <a name="prepare-on-premises-resources-access-for-microsoft-managed-desktop"></a>Förbereda lokal resursåtkomst för Microsoft Managed Desktop

I Microsoft Managed Desktop kopplas enheter automatiskt till Azure Active Directory (Azure AD). Det innebär att om du använder en lokal Active Directory måste du kontrollera vissa saker för att säkerställa att enheter som är anslutna till Azure AD kan kommunicera med din lokala Active Directory. 

> [!NOTE]  
> *Hybrid* Azure AD join stöds inte av Microsoft Managed Desktop.

Med Azure Active Directory kan användarna dra nytta av SSO (Single Sign-On), vilket innebär att de vanligtvis inte behöver ange autentiseringsuppgifter varje gång de använder resurser.

Information om hur du ansluter till Azure Active Directory finns i [Så här: Planera din Azure AD-kopplingsimplementering](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan). Bakgrundsinformation om Enkel inloggning (SSO) på enheter som är anslutna till Azure AD finns i [Så här fungerar SSO till lokala resurser på Azure AD-anslutna enheter](https://docs.microsoft.com/azure/active-directory/devices/azuread-join-sso#how-it-works).


I det här avsnittet beskrivs de saker du behöver kontrollera för att säkerställa att appar och andra resurser som är beroende av lokal Active Directory-anslutning fungerar smidigt med Microsoft Managed Desktop.


## <a name="single-sign-on-for-on-premises-resources"></a>Enkel inloggning för lokala resurser

Enkel inloggning (SSO) med hjälp av UPN och lösenord aktiveras som standard på Microsoft Managed Desktop Devices. Men användarna kan också använda Windows Hello for Business, vilket kräver extra installationssteg. 

### <a name="single-sign-on-by-using-upn-and-password"></a>Enkel inloggning med HJÄLP AV UPN och lösenord

I de flesta organisationer kan användarna använda SSO för att autentisera med UPN och lösenord på Microsoft Managed Desktop Devices. Men för att se till att detta kommer att fungera, bör du dubbelkolla följande:

- Bekräfta att Azure AD Connect har konfigurerats och använder en lokal Active Directory-server som kör Windows Server 2008 R2 eller senare.
- Bekräfta att Azure AD Connect kör en version som stöds och är inställd på att synkronisera dessa tre attribut med Azure AD: 
    - DNS-domännamn för den lokala Active Directory (där slutanvändarna finns)
    - NetBIOS för din lokala Active Directory (där slutanvändarna finns)
    - ANVÄNDARENS SAM-kontonamn


### <a name="single-sign-on-by-using-windows-hello-for-business"></a>Enkel inloggning med Hjälp av Windows Hello for Business

Microsoft Managed Desktop-enheter erbjuder också användarna en snabb, lösenordslös upplevelse genom att anställa Windows Hello for Business. Om du vill vara säker på att Windows Hello for Business fungerar utan att användarna behöver ange respektive UPN och lösenord besöker du [Konfigurera Azure AD-anslutna enheter för lokala Enkelinloggning på med Windows Hello for Business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base) för att kontrollera kraven och följ sedan stegen där.


## <a name="apps-and-resources-that-use-authentication"></a>Appar och resurser som använder autentisering

Se [Förstå överväganden för program och resurser](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources) i Azure-innehållsuppsättningen för fullständig vägledning om hur du konfigurerar appar för att fungera med Azure Active Directory. Sammanfattningsvis:


- Om du använder **molnbaserade appar**, till exempel de som läggs till i Azure AD-appgalleriet, kräver de flesta inte ytterligare förberedelser för att fungera med Microsoft Managed Desktop. Alla Win32-appar som inte använder Web Account Manager (WAM) kan dock fortfarande uppmana användarna att autentisering.

- För appar som finns **lokala**bör du lägga till dessa appar i listan betrodda webbplatser i webbläsarna. Detta gör det möjligt för Windows-autentisering att fungera sömlöst, utan att användarna uppmanas att ange autentiseringsuppgifter. Det gör du genom att läsa [Betrodda platser](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/config-setting-ref#trusted-sites) i [referensen konfigurerbara inställningar](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/config-setting-ref).

- Om du använder Active Directory-federerade tjänster kontrollerar du att SSO är aktiverat med hjälp av stegen i [Verifiera och hantera enkel inloggning med AD FS](https://docs.microsoft.com/previous-versions/azure/azure-services/jj151809(v=azure.100)). 

- För appar som är **lokala och använder äldre protokoll**krävs ingen extra inställning, så länge enheterna har åtkomst till en lokal domänkontrollant för att autentisera. För att ge säker åtkomst för dessa program bör du dock distribuera Azure AD Application Proxy. Mer information finns i [Fjärråtkomst till lokala program via Azure Active Directory application proxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).

- Appar som körs **lokalt och är beroende av maskinautentisering** stöds inte, så du bör överväga att ersätta dessa med nyare versioner.

### <a name="network-shares-that-use-authentication"></a>Nätverksresurser som använder autentisering

Ingen extra inställning krävs för att användare ska komma åt nätverksresurser, så länge enheterna har åtkomst till en lokal domänkontrollant med hjälp av en UNC-sökväg.

### <a name="printers"></a>Skrivare

Microsoft Managed Desktop-enheter kan inte ansluta till skrivare som publiceras i din lokala Active Directory om du inte har konfigurerat [Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).

Skrivare kan inte identifieras automatiskt i en molnmiljö, men användarna kan använda lokala skrivare med hjälp av sökvägen till skrivaren eller skrivarkösökvägen, så länge enheterna har åtkomst till en lokal domänkontrollant.

<!--add fuller material on printers when available-->
