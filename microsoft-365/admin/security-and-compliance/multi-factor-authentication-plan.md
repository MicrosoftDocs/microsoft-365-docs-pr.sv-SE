---
title: Planera för multifaktorautentisering för Microsoft 365-distributioner
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 043807b2-21db-4d5c-b430-c8a6dee0e6ba
ROBOTS: NOINDEX, NOFOLLOW
description: Lär dig mer om multifaktorautentisering i Microsoft 365 och de steg du behöver följa för att konfigurera den.
ms.openlocfilehash: 035a79c9db44990dbce09de540e3e483b3cea8df
ms.sourcegitcommit: 7c0470fd7a98911d142bac060c228947c46a6be7
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/22/2020
ms.locfileid: "43665674"
---
# <a name="plan-for-multi-factor-authentication-for-microsoft-365-deployments"></a>Planera för multifaktorautentisering för Microsoft 365-distributioner

Multifaktorautentisering (MFA) är en autentiseringsmetod som kräver att fler än en metod för verifiering används och lägger till ytterligare en säkerhetsnivå vid användarinloggningar och transaktioner. Det fungerar genom att kräva ett tillägg verifiering steg med information utöver användarkontot lösenord, till exempel:
  
- En slumpmässigt genererad verifieringskod som skickas till din smarta telefon
    
- Ett telefonsamtal
    
- Ett smartkort (virtuellt eller fysiskt) 
    
- En biometrisk enhet 
    
## <a name="mfa-in-microsoft-365"></a>MFA i Microsoft 365

Microsoft 365 använder MFA för att ge extra säkerhet och hanteras från Microsoft 365 administrationscenter. Microsoft 365 erbjuder följande delmängd av [Azure Multi-Factor Authentication-funktioner](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks) som en del av prenumerationen: 
  
- Möjligheten att aktivera och genomdriva makroekonomiskt stöd för slutanvändare
    
- Användningen av en mobilapp (online och enstaka lösenord [OTP]) som en andra autentiseringsfaktor
    
- Användningen av ett telefonsamtal som en andra autentiseringsfaktor
    
- Användningen av sms-textmeddelande (Short Message Service) som en andra autentiseringsfaktor
    
- Programlösenord för klienter som inte är webbläsare (till exempel microsoft Lync 2013-kommunikationsprogrammet)
    
- Microsoft-standardhälsningar under telefonsamtal för autentisering
    
Den fullständiga listan över tillagda funktioner finns i [Azure Multi-Factor Authentication](https://go.microsoft.com/fwlink/?LinkId=506927). Du kan alltid få alla funktioner genom att köpa [Azure Multi-Factor Authentication-licenser](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-licensing). 
  
Du får en annan delmängd av funktionerna beroende på om du använder molnidentitet där användarkontona finns i Microsoft 365 eller hybrid konfigureras med enkel inloggning och AD FS (Active Directory Federation Services). 
  
|**Var hanterar du Microsoft 365?**|**Alternativ för andra MFA-faktor**|
|:-----|:-----|
|Endast molnet  <br/> | Azure MultiFaktor-autentisering (text eller telefonsamtal)  <br/> |
|Hybridkonfiguration som hanteras lokalt  <br/> | Om du hanterar användaridentitet lokalt har du följande alternativ:  <br/> - Fysiskt eller virtuellt smartkort (AD FS)  <br/> - Azure MultiFaktor Authentication (modul för AD FS)  <br/>  - Azure multifaktorautentisering  <br/> |
   
Office 2013-enhetsapparna stöder MFA med hjälp av [Active Directory Authentication Library (ADAL).](https://go.microsoft.com/fwlink/p/?LinkId=526684) Azure Active Directory (Azure AD) är värd för en webbsida där användare kan logga in. Identitetsleverantören kan vara Azure AD eller en federerad identitetsleverantör som AD FS. Autentiseringen av federerade användare består av följande steg:
  
1. Azure AD omdirigerar användaren till inloggningswebbsidan som finns värd för identitetsprovidern för posten för organisationen. Identitetsleverantören fastställs av den domän som anges i användarens inloggningsnamn.
    
2. Användaren loggar in på inloggningswebbsidan från sin enhet. 
    
3. Identitetsleverantören returnerar en token till Azure AD när användaren har loggats in.
    
4. Azure AD returnerar en JSON-webbtoken (JWT) till Office-enhetsappen och enhetsappen autentiseras med hjälp av en JWT med Microsoft 365. 
    
  
## <a name="requirements-for-office-2013-client-apps"></a>Krav för Office 2013-klientappar

Om du vill aktivera MFA för Office 2013-klientprogram måste du ha följande program installerade (versionen nedan eller en senare version) beroende på om du har en [Klicka-och-kör-baserade installationer](#click-to-run-based-installations) eller en [MSI-baserade installationer](#msi-based-installations).
  
Så här tar du reda på om Office-installationen är Klicka-och-kör- eller MSI-baserad:
  
1. Starta Outlook 2013.
    
2. Välj **Office-konto**på **Arkiv-menyn** .
    
3. För Klicka-och-kör-baserade installationer av Outlook 2013 visas alternativet **Uppdateringsalternativ**. Alternativet **Uppdateringsalternativ** visas inte för MSI-baserade installationer. 
    
    ![Så här visar du om office 2013-installationen är klicka-och-kör- eller MSI-baserad](../../media/1e75143f-9e37-4e0c-9610-43a80771571e.png)

Sor mer information, se [faq om modern autentisering wiki artikel](https://go.microsoft.com/fwlink/p/?LinkId=530064).
  
### <a name="click-to-run-based-installations"></a>Klicka-och-kör-baserade installationer

För Klicka-och-kör-baserade installationer måste du ha följande programvara installerad, med filversionen nedan eller en senare filversion. Om din filversion inte är lika med eller senare än den filversion som anges nedan uppdaterar du den genom att utföra följande steg.
  
|**Filnamn**|**Installationssökväg på datorn**|**Filversion**|
|:-----|:-----|:-----|
|Mso. Dll  <br/> |C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\MSO.DLL  <br/> |15.0.4753.1001  <br/> |
|Csi. Dll  <br/> |CSI.DLL C:\Program Files\Microsoft Office 15\root\office15\csi.dll  <br/> |15.0.4753.1000  <br/> |
|Groove.EXE  <br/> |C:\Program Files\Microsoft Office 15\root\office15\GROOVE.exe  <br/> |15.0.4763.1000  <br/> |
|Outlook.exe  <br/> |C:\Program Files\Microsoft Office 15\root\office15\OUTLOOK.exe  <br/> |15.0.4753.1002  <br/> |
|ADAL. Dll  <br/> |C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\ADAL.DLL  <br/> |1.0.2016.624  <br/> |
|Iexplore.exe  <br/> |C:\Program Files\Internet Explorer  <br/> |varierar  <br/> |
   
### <a name="msi-based-installations"></a>MSI-baserade installationer

För MSI-baserade installationer måste du ha följande program installerade, med filversionen som anges nedan eller en senare filversion. Om din filversion inte är lika med eller senare än den filversion som anges nedan uppdaterar du den med länken i kolumnen med KB-uppdateringsartikeln.
  
|**Filnamn**|**Installationssökväg på datorn**|**Här hämtar du uppdateringen**|**Version**|
|:-----|:-----|:-----|:-----|
|Mso. Dll  <br/> |C:\Program Files\Common Files\Microsoft Shared\OFFICE15\MSO.DLL  <br/> |[KB3085480](https://support.microsoft.com/kb/3085480) <br/> |15.0.4753.1001  <br/> |
|Csi. Dll  <br/> |C:\Program Files\Common Files\Microsoft Shared\OFFICE15\Csi.dll  <br/> |[KB3085504](https://support.microsoft.com/kb/3085504) <br/> |15.0.4753.1000  <br/> |
|Groove.exe  <br/> |C:\Program Files\Microsoft Office\Office15\GROOVE.EXE  <br/> |[KB3085509](https://support.microsoft.com/kb/3085509) <br/> |15.0.4763.1000  <br/> |
|Outlook.exe  <br/> |C:\Program Files\Microsoft Office\Office15\OUTLOOK.EXE  <br/> |[KB3085495](https://support.microsoft.com/kb/3085495) <br/> |15.0.4753.1002  <br/> |
|ADAL. Dll  <br/> |C:\Program Files\Common Files\Microsoft Shared\OFFICE15\ADAL.DLL  <br/> |[KB3055000](https://support.microsoft.com/kb/3055000) <br/> |1.0.2016.624  <br/> |
|Iexplore.exe  <br/> |C:\Program Files\Internet Explorer  <br/> |[MS14-052](https://support.microsoft.com/kb/2977629) <br/> |Ej tillämpligt  <br/> |
   
## <a name="enable-mfa"></a>Aktivera MFA

Så här aktiverar du MFA för din prenumeration:
  
1. Vid behov: 

  - [Aktivera modern autentisering för Office 2013 på Windows-enheter](enable-modern-authentication.md).
    
  - Konfigurera Azure Multi-Factor Authentication med katalogtjänster från tredje part.
    
    Se [avancerade scenarier med Azure Multi-Factor Authentication och VPN-lösningar](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) från tredje part för information om specifika identitetsleverantörer som godkänts för det här programmet. 
    
2. [Konfigurera MFA för Microsoft 365](set-up-multi-factor-authentication.md).
    
3. Tala om för enskilda användare hur de loggar in av MFA. Se [Logga in på Microsoft 365 med MFA](https://support.office.com/en-us/article/sign-in-to-microsoft-365-with-2-step-verification-2b856342-170a-438e-9a4f-3c092394d3cb).

> [!IMPORTANT]
> Om du har aktiverat dina användare för Azure Multi-Factor Authentication och de har några enheter som kör Office 2013 som inte är aktiverade för modern autentisering, måste de använda AppPasswords på dessa enheter. Mer information om AppPasswords och när/var/hur de ska användas finns här: [Applösenord med Azure Multi-Factor Authentication](https://go.microsoft.com/fwlink/p/?LinkId=528178).
  
## <a name="faq"></a>Vanliga frågor och svar

[Wikiartikel med vanliga frågor och svar om modern autentisering](https://go.microsoft.com/fwlink/p/?LinkId=530064)
  
## <a name="known-issues"></a>Kända problem

[Office 2013 och Microsoft 365 Apps för företagsmodern autentisering: Saker att veta innan du börjar med](https://social.technet.microsoft.com/wiki/contents/articles/30214.office-2013-and-office-365-proplus-modern-authentication-things-to-know-before-onboarding.aspx)
  
 **Felsöka Azure-multifaktorautentisering:**
  
Se [Felsöka Azure Multi Factor-autentisering](https://support.microsoft.com/help/2937344/troubleshooting-azure-multi-factor-authentication-issues).
  
[Felsöka inloggningsproblem med modern autentisering för Office 2013 när du använder AD FS](https://support.microsoft.com/kb/3052203/)
  
 **När alternativa ID:n inte fungerar:**
  
[Så här använder du PowerShell för att åtgärda UPN-dubbletter](https://go.microsoft.com/fwlink/p/?LinkId=396730)
  
[Skript för att åtgärda dubbletter av UPN-namn](https://go.microsoft.com/fwlink/p/?LinkId=396725)
  
 **Filtrering av klientåtkomst:**
  
[Office 2013 och Microsoft 365 Apps för företag modern autentisering och klientåtkomst filtreringsprinciper: Saker att veta innan du börjar med](https://social.technet.microsoft.com/wiki/contents/articles/30214.office-2013-and-office-365-proplus-modern-authentication-things-to-know-before-onboarding.aspx)
  
 **Vilka program har stöd för MFA?**
  
|**Windows**|**Mac**|**Ios**|**Android-telefon**|**Android-surfplatta**|
|:-----|:-----|:-----|:-----|:-----|
|Den här versionen har stöd för modern autentisering för Word 2013, Word 2016, Excel 2013, Excel 2016, PowerPoint 2013, PowerPoint 2016, OneNote 2013, OneNote 2016 Project 2013, Project 2016, Visio 2013, Visio 2016, Lync 2013 och Skype för företag.  <br/> |Den här versionen har stöd för modern autentisering för Word 2016 för Mac, Excel 2016 för Mac och PowerPoint 2016 för Mac.  <br/> |Den här versionen har stöd för modern autentisering för Word för iPad, Excel för iPad och PowerPoint för iPad.  <br/> |Den här versionen har stöd för modern autentisering för Word för Android, Excel för Android och PowerPoint för Android.  <br/> |Den här versionen har stöd för modern autentisering för Word för Android, Excel för Android och PowerPoint för Android.  <br/> |
|Den här versionen har stöd för modern autentisering för Outlook 2013 och Outlook 2016.  <br/> |Den här versionen har stöd för modern autentisering för Outlook 2016 för Mac.  <br/> |Den här versionen har stöd för modern autentisering för Outlook för iPad.  <br/> |||
   

