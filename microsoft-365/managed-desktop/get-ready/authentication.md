---
title: Förbereda lokala resurser till gång för Microsoft Hanterat skrivbord
description: Viktiga steg för att se till att en Azure AD kan kommunicera med lokal AD för att tillhandahålla autentisering
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 6df23e0d7e3ea0ecd7ebacd96f00cb47b9e0aa84
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574601"
---
#  <a name="prepare-on-premises-resources-access-for-microsoft-managed-desktop"></a>Förbereda lokala resurser till gång för Microsoft Hanterat skrivbord

I Microsoft Hanterat skrivbord är enheter automatiskt anslutna till Azure Active Directory (Azure AD). Om du använder en lokal Active Directory-miljö måste du därför kontrollera några saker för att säkerställa att enheter som är anslutna till Azure AD kan kommunicera med din lokala Active Directory. 

> [!NOTE]  
> *Hybrid* Azure AD-koppling stöds inte av Microsoft Hanterat skrivbord.

Azure Active Directory kan dina användare dra nytta av Single Sign-On (SSO), vilket innebär att de vanligtvis inte behöver ange autentiseringsuppgifter varje gång de använder resurser.

Information om hur du ansluter Azure Active Directory i Så här [gör du: Planera implementering av Azure AD-koppling.](/azure/active-directory/devices/azureadjoin-plan) Bakgrundsinformation om enkel inloggning (Sign-On SSO) på enheter som är anslutna till Azure AD finns i Hur SSO fungerar på lokala resurser med [Azure AD-anslutna enheter.](/azure/active-directory/devices/azuread-join-sso#how-it-works)


I den här artikeln förklaras de saker du behöver kontrollera för att program och andra resurser som är beroende av lokal Active Directory-anslutning fungerar smidigt med Microsoft Hanterat skrivbord.


## <a name="single-sign-on-for-on-premises-resources"></a>Enkel Sign-On för lokala resurser

Enkel inloggning Sign-On (SSO) med HJÄLP av UPN och lösenord är aktiverat som standard på Microsoft Hanterat skrivbord enheter. Men användarna kan också använda Windows Hello för företag, vilket kräver några extra konfigurationssteg. 

### <a name="single-sign-on-by-using-upn-and-password"></a>Enkel Sign-On med HJÄLP av UPN och lösenord

I de flesta organisationer kommer användarna att kunna använda SSO för att autentisera med UPN och lösenord på Microsoft Hanterat skrivbord enheter. För att se till att den här funktionen fungerar bör du dubbelkolla följande:

- Bekräfta att Azure AD Anslut är konfigurerat och använder en lokal Active Directory-server som kör Windows Server 2008 R2 eller senare.
- Kontrollera att Azure AD Anslut kör en version som stöds och är inställd på att synkronisera dessa tre attribut med Azure AD: 
    - DNS-domännamnet för den lokala Active Directory (där användarna finns)
    - NetBIOS för din lokala Active Directory (där användarna finns)
    - ANVÄNDARENs SAM-kontonamn


### <a name="single-sign-on-by-using-windows-hello-for-business"></a>En Sign-On med hjälp Windows Hello för företag

Microsoft Hanterat skrivbord-enheter ger också användarna en snabb och lösenordslös upplevelse genom att använda Windows Hello för företag. Om du vill säkerställa att Windows Hello för företag fungerar utan att användarna måste ange respektive UPN och lösenord går du till Konfigurera [Azure AD-anslutna](/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base) enheter för lokala Single-Sign På med Windows Hello för företag för att kontrollera kraven och följ sedan anvisningarna där.


## <a name="apps-and-resources-that-use-authentication"></a>Appar och resurser som använder autentisering

Läs Förstå [överväganden för program och resurser i](/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources) Azure-innehållsuppsättningen för fullständig vägledning om hur du inställningar appar ska fungera med Azure Active Directory. Sammanfattning:


- Om du använder **molnbaserade appar,** som de som lagts till i Azure AD-appgalleriet, behöver de flesta inte några ytterligare förberedelser för att arbeta med Microsoft Hanterat skrivbord. Men alla Win32-appar som inte använder Web Account Manager (WAM) kan fortfarande uppmana användarna att autentisera.

- Se till att **lägga till apparna i listan med** betrodda platser i dina webbläsare för lokalt installerade appar. Det här steget gör Windows att autentiseringen fungerar smidigt, utan att användarna uppmanas att ange autentiseringsuppgifter. Information om hur du lägger till appar [finns i Betrodda](../working-with-managed-desktop/config-setting-ref.md#trusted-sites) platser [i referensen för konfigurerbara inställningar.](../working-with-managed-desktop/config-setting-ref.md)

- Om du använder Active Directory Federated Services kontrollerar du att SSO är aktiverat med hjälp av stegen i Verifiera och hantera [enkel inloggning med AD FS.](/previous-versions/azure/azure-services/jj151809(v=azure.100)) 

- För program som **finns** lokalt och använder äldre protokoll krävs ingen extra konfiguration, så länge enheterna har åtkomst till en lokal domänkontrollant för autentisering. För att ge säker åtkomst för de här programmen bör du emellertid distribuera Azure AD-programproxy. Mer information finns i [Fjärråtkomst till lokala program via Azure Active Directory Programproxy.](/azure/active-directory/manage-apps/application-proxy)

- Appar som körs **lokalt och använder maskinautentisering** stöds inte, så du bör överväga att ersätta dem med nyare versioner.

### <a name="network-shares-that-use-authentication"></a>Nätverksresurser som använder autentisering

Ingen extra konfiguration krävs för att användarna ska kunna komma åt nätverksresurser, så länge enheterna har åtkomst till en lokal domänkontrollant genom att använda en UNC-sökväg.

### <a name="printers"></a>Skrivare

Microsoft Hanterat skrivbord-enheter kan inte ansluta till skrivare som publiceras till din lokala Active Directory om du inte har konfigurerat [Hybrid Cloud Print.](/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)

Även om skrivare inte kan upptäckas automatiskt i en miljö som bara finns i molnet, kan användarna använda lokala skrivare med hjälp av skrivarsökvägen eller sökvägen till skrivarköer, så länge enheterna har åtkomst till en lokal domänkontrollant.

<!--add fuller material on printers when available-->
## <a name="steps-to-get-ready"></a>Steg för att förbereda dig

1. Granska [Krav för Microsoft Hanterat skrivbord](prerequisites.md).
2. Använda [utvärderingsverktyg för beredskap](readiness-assessment-tool.md).
3. [Förutsättningar för gästkonton](guest-accounts.md)
4. [Nätverkskonfiguration för Microsoft Hanterat skrivbord](network.md)
5. [Förbereda certifikat och nätverksprofiler för Microsoft Hanterat skrivbord](certs-wifi-lan.md)
6. [Förbereda åtkomst för lokala resurser för Microsoft Hanterat skrivbord](authentication.md) (den här artikeln)
7. [Appar i Microsoft Hanterat skrivbord](apps.md)
8. [Förbereda mappade enheter för Microsoft Hanterat skrivbord](mapped-drives.md)
9. [Förbereda utskriftsresurser för Microsoft Hanterat skrivbord](printing.md)
