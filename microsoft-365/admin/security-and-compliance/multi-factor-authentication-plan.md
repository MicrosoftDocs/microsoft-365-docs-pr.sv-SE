---
title: Planera för multifaktorautentisering för Office 365-distributioner
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
description: Lär dig mer om multifaktorautentisering i Office 365 och de steg du behöver följa för att konfigurera den.
ms.openlocfilehash: 715baeb0355ab203e890f2c87cf0751eff69e7f8
ms.sourcegitcommit: dbbdeca5a6cd048e1bde9e820a8b8a0d6022c7a2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/14/2020
ms.locfileid: "43504001"
---
# <a name="plan-for-multi-factor-authentication-for-office-365-deployments"></a>Planera för multifaktorautentisering för Office 365-distributioner

Multifaktorautentisering (MFA) är en autentiseringsmetod som kräver att fler än en metod för verifiering används och lägger till ytterligare en säkerhetsnivå vid användarinloggningar och transaktioner. Det fungerar genom att kräva ett tillägg verifiering steg med information utöver användarkontot lösenord, till exempel:
  
- Ett slumpmässigt genererad kod
    
- Ett telefonsamtal
    
- Ett smartkort (virtuellt eller fysiskt) 
    
- En biometrisk enhet 
    
## <a name="mfa-in-office-365"></a>MFA i Office 365

Office 365 använder MFA för extra inloggningssäkerhet och kan hanteras för varje enskilt användarkonto från Microsoft 365-administrationscentret. Office 365 erbjuder följande delmängd av Azure Multi-Factor Authentication-funktioner som en del av din prenumeration: 
  
- Möjligheten att aktivera och genomdriva makroekonomiskt stöd för slutanvändare
    
- Användningen av en mobilapp (online och enstaka lösenord [OTP]) som en andra autentiseringsfaktor
    
- Användningen av ett telefonsamtal som en andra autentiseringsfaktor
    
- Användningen av ett sms-meddelande som en andra autentiseringsfaktor
    
- Programlösenord för klienter som inte är webbläsare (till exempel microsoft Lync 2013-kommunikationsprogrammet)
    
- Microsoft-standardhälsningar under telefonsamtal för autentisering
    
En fullständiga lista över tillagda funktioner finns i [jämförelsen av Azure Multi-Factor Authentication-versioner](https://go.microsoft.com/fwlink/?LinkId=506927). Du kan alltid få den fullständiga uppsättningen funktioner genom att köpa Azure Multi-Factor Authentication-tjänsten. 
  
Du får en annan delmängd av funktionerna beroende på om du har en moln- eller hybrididentitet för Office 365 eller federerad autentisering med AD FS (Active Directory Federation Services). 
  
|**Var hanterar du din Office 365-klient?** | **MFA andra faktor alternativ**|

|:-----|:-----| | Endast moln  <br/> | Azure MultiFaktor-autentisering (text eller telefonsamtal)  <br/> | | Hybridinstallation, hanterad lokalt  <br/> | Om du hanterar användaridentitet lokalt har du följande alternativ:  <br/>  Fysiskt eller virtuellt smartkort (när AD FS-  <br/> [Azure Multifaktorautentisering](https://go.microsoft.com/fwlink/p/?LinkId=526677) (modul för AD FS)  <br/>  Azure Active Directory (Azure AD) multifaktorautentisering  <br/> |
   
  
Följande bild visar hur de uppdaterade Office 2013-enhetsapparna (i Windows) gör det möjligt för användare att logga in med MFA. 

![Modern autentisering för Office 2013-enhetsprogram.](../../media/dc37645c-b899-4715-b162-d7653bd0aebd.png)

Office 2013-enhetsapparna stöder multifaktorautentisering med hjälp av [Active Directory Authentication Library (ADAL).](https://go.microsoft.com/fwlink/p/?LinkId=526684) Azure AD är värd för en webbsida där användarna kan logga in. Identitetsleverantören kan vara Azure AD eller en federerad identitetsleverantör som AD FS. Autentiseringen av federerade användare består av följande steg:
  
1. Azure AD omdirigerar användaren till den inloggningswebbsida som identitetsleverantören för Office 365-klientorganisationen är värd för. Identitetsleverantören fastställs av den domän som anges i användarens inloggningsnamn.
    
2. Användaren loggar in på inloggningswebbsidan från sin enhet. 
    
3. Identitetsleverantören returnerar en token till Azure AD när användaren har loggats in.
    
4. Azure AD returnerar en JSON-webbtoken (JWT) till Office-enhetsappen och enhetsappen autentiseras med hjälp av en JWT med Office 365. 
    
  
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

Så här aktiverar du MFA för din Office 365-prenumeration:
  
1. Aktivera [modern autentisering för Office 2013 på Windows-enheter om](enable-modern-authentication.md)det behövs.
    
2. Konfigurera Azure Multi-Factor Authentication med din katalogtjänst från tredje part för federerad autentisering.
    
    Se [avancerade scenarier med Azure Multi-Factor Authentication och VPN-lösningar](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) från tredje part för information om specifika identitetsleverantörer som godkänts för det här programmet. 
    
3. [Konfigurera multifaktorautentisering för Office 365](set-up-multi-factor-authentication.md).
    
4. Tala om för användarna hur [de konfigurerar MFA för sitt Office 365-användarkonto](https://support.office.com/article/set-up-2-step-verification-for-office-365-ace1d096-61e5-449b-a875-58eb3d74de14). När de har ställt in sin sekundära autentiseringsmetod kräver deras framtida inloggningar MFA.
    
> [!IMPORTANT]
> Om du har aktiverat dina användare för Azure Multi-Factor Authentication och de har några enheter som kör Office 2013 som inte är aktiverade för modern autentisering måste de använda Applösenord. Mer information om applösenord och när/var/hur de ska användas finns här: [Applösenord med Azure Multi_Factor autentisering](https://go.microsoft.com/fwlink/p/?LinkId=528178). 
  
## <a name="known-issues"></a>Kända problem
  
[Office 2013 och Office 365 ProPlus modern autentisering: Saker att veta innan du börjar med](https://social.technet.microsoft.com/wiki/contents/articles/30214.office-2013-and-office-365-proplus-modern-authentication-things-to-know-before-onboarding.aspx)
  
 **Felsöka Azure-multifaktorautentisering:**
  
Se [Felsöka Azure Multi Factor-autentisering](https://support.microsoft.com/help/2937344/troubleshooting-azure-multi-factor-authentication-issues).
  
[Felsöka inloggningsproblem med modern autentisering för Office 2013 när du använder AD FS](https://support.microsoft.com/kb/3052203/)
  
 **När alternativa ID:n inte fungerar:**
  
[Så här använder du PowerShell för att åtgärda UPN-dubbletter](https://go.microsoft.com/fwlink/p/?LinkId=396730)
  
[Skript för att åtgärda dubbletter av UPN-namn](https://go.microsoft.com/fwlink/p/?LinkId=396725)
  
 **Filtrering av klientåtkomst:**
  
[Principer för filtrering av klientåtkomst med modern autentisering för Office 2013 och Office 365: Bra att veta före integration](https://social.technet.microsoft.com/wiki/contents/articles/30214.office-2013-and-office-365-proplus-modern-authentication-things-to-know-before-onboarding.aspx)
  
 **Vilka program har stöd för MFA?**
  
|**Windows**|**Mac**|**Ios**|**Android-telefon**|**Android-surfplatta**|
|:-----|:-----|:-----|:-----|:-----|
|Den här versionen har stöd för modern autentisering för Word 2013, Word 2016, Excel 2013, Excel 2016, PowerPoint 2013, PowerPoint 2016, OneNote 2013, OneNote 2016 Project 2013, Project 2016, Visio 2013, Visio 2016, Lync 2013 och Skype för företag.  <br/> |Den här versionen har stöd för modern autentisering för Word 2016 för Mac, Excel 2016 för Mac och PowerPoint 2016 för Mac.  <br/> |Den här versionen har stöd för modern autentisering för Word för iPad, Excel för iPad och PowerPoint för iPad.  <br/> |Den här versionen har stöd för modern autentisering för Word för Android, Excel för Android och PowerPoint för Android.  <br/> |Den här versionen har stöd för modern autentisering för Word för Android, Excel för Android och PowerPoint för Android.  <br/> |
|Den här versionen har stöd för modern autentisering för Outlook 2013 och Outlook 2016.  <br/> |Den här versionen har stöd för modern autentisering för Outlook 2016 för Mac.  <br/> |Den här versionen har stöd för modern autentisering för Outlook för iPad.  <br/> |||
   

