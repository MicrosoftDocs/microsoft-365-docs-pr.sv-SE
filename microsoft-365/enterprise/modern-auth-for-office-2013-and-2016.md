---
title: Så fungerar den moderna autentiseringsprocessen för Office 2013-och Office 2016-klient program
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 8/1/2017
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- GMA150
- GPA150
- GEA150
- BCS160
ms.assetid: e4c45989-4b1a-462e-a81b-2a13191cf517
ms.collection:
- M365-security-compliance
description: Lär dig hur Microsoft 365 moderna autentiseringsmetoder fungerar annorlunda för Office 2013-och 2016-klient program.
ms.openlocfilehash: 62aa04e295c2734d705f22bd2f62c6bc5e622426
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694876"
---
# <a name="how-modern-authentication-works-for-office-2013-office-2016-and-office-2019-client-apps"></a>Så fungerar den moderna autentiseringsprocessen för Office 2013-, Office 2016-och Office 2019-klient program

*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*

Läs den här artikeln om du vill veta hur Office 2013, Office 2016 och Office 2019-klient program använder moderna autentiseringsmetoder baserat på autentiseringsinställningarna för Microsoft 365-klient organisationen för Exchange Online, SharePoint Online och Skype för företag – online.

> [!NOTE]
> Äldre klient program, till exempel Office 2010 och Office för Mac 2011, stöder inte modern lösenordsautentisering och kan bara användas med grundläggande behörighet.

## <a name="availability-of-modern-authentication-for-microsoft-365-services"></a>Tillgänglighet för modern auktorisering för Microsoft 365-tjänster

För Microsoft 365-tjänsterna är standard tillståndet för modern autentisering:
  
- Aktiverat **för Exchange** online som standard. Se [Aktivera eller inaktivera modern lösenordsautentisering i Exchange Online](https://support.office.com/article/58018196-f918-49cd-8238-56f57f38d662) för att stänga av eller på. 
    
- Aktiverat **för SharePoint** online som standard. 
    
- Aktiverat **för Skype för företag** – online som standard. Se [Aktivera Skype för företag – online om ](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)du vill aktivera eller inaktivera den.

> [!NOTE]
> För klient organisationer som har skapats **före** den 1 augusti 2017 är modern autentisering **inaktive** rad som standard för Exchange Online och Skype för företag – online.
    
## <a name="sign-in-behavior-of-office-client-apps"></a>Inloggnings beteende för Office-klientprogram

Office 2013-klientprogram har äldre autentisering som standard. Legacy innebär att de stöder antingen Microsoft Online-inloggning eller grundläggande-verifikation. För att dessa klienter ska kunna använda moderna autentiseringsmekanismer måste Windows-klienten ha register nycklar inställt. Anvisningar finns i [Aktivera modern auktorisering för Office 2013 på Windows-enheter](https://support.office.com/article/7dc1c01a-090f-4971-9677-f1b192d6c910).

Om du vill aktivera modern autentisering för enheter med Windows (till exempel på bärbara datorer och surfplattor), som har Microsoft Office 2013 installerat, måste du ange följande registernycklar. Registernycklarna måste anges på varje enhet som du vill aktivera för modern autentisering:
  
|**Registernyckel**|**Typ**|**Värde** |
|:-------|:------:|--------:|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL  |REG_DWORD  |9.1  |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version |REG_DWORD |9.1 |
  
Läs om [hur du använder modern (ADAL) med Skype för företag](https://go.microsoft.com/fwlink/p/?LinkId=785431) för att lära dig hur det fungerar med Skype för företag. 
  
Office 2016 och Office 2019-klienter har stöd för modern autentisering som standard och ingen åtgärd krävs för att klienten ska kunna använda dessa nya flöden. Det behövs emellertid en uttrycklig åtgärd för att använda äldre autentiseringsmetod.
  
Klicka på länkarna nedan för att se hur Office 2013, Office 2016 och Office 2019 klientautentisering fungerar med Microsoft 365-tjänsterna, beroende på om det är aktiverat eller inte.
  
- [Exchange Online](modern-auth-for-office-2013-and-2016.md#BK_EchangeOnline)
    
- [SharePoint Online](modern-auth-for-office-2013-and-2016.md#BK_SharePointOnline)
    
- [Skype för företag Online](modern-auth-for-office-2013-and-2016.md#BK_SFBO)
    
<a name="BK_EchangeOnline"> </a>
### <a name="exchange-online"></a>Exchange Online

I följande tabell beskrivs autentiseringsmetoderna för Office 2013-, Office 2016-och Office 2019-klient program när de ansluter till Exchange Online med eller utan modern behörighet.
  
|Office-klientprogram version * * * *|Finns det någon register nyckel? * * * *|Modern-inloggning? * * * *|Autentisering är aktiverat för klient organisationen (standard) * * * *|Beteende med modern inaktive rad för klient organisationen * * * *|
|:-----|:-----|:-----|:-----|:-----|
|Office 2019  <br/> |Nej <br> AlwaysUseMSOAuthForAutoDiscover = 1 <br/> |Ja  <br/> |Aktiverar modern inloggning i Outlook 2013, 2016 eller 2019. <br/> [Mer information](https://support.microsoft.com/help/3126599/outlook-prompts-for-password-when-modern-authentication-is-enabled)|Den här funktionen är modern i Outlook-klienten.<br/> |
|Office 2019  <br/> |Nej, eller EnableADAL = 1  <br/> |Ja  <br/> |Modern autentiseringsförsök görs först. Om servern nekar en modern autentiseringsbegäran används grundläggande verifikation. Server nekar modern auktorisering när klient organisationen inte är aktive rad.  <br/> |Modern autentiseringsförsök görs först. Om servern nekar en modern autentiseringsbegäran används grundläggande verifikation. Server nekar modern auktorisering när klient organisationen inte är aktive rad.  <br/> |
|Office 2019  <br/> |Ja, EnableADAL = 1  <br/> |Ja  <br/> |Modern autentiseringsförsök görs först. Om servern nekar en modern autentiseringsbegäran används grundläggande verifikation. Server nekar modern auktorisering när klient organisationen inte är aktive rad.  <br/> |Modern autentiseringsförsök görs först. Om servern nekar en modern autentiseringsbegäran används grundläggande verifikation. Server nekar modern auktorisering när klient organisationen inte är aktive rad.  <br/> |
|Office 2019  <br/> |Ja, EnableADAL = 0  <br/> |Nej  <br/> |Grundläggande autentisering  <br/> |Grundläggande autentisering  <br/> |
|Office 2016  <br/> |Nej <br> AlwaysUseMSOAuthForAutoDiscover = 1 <br/> |Ja  <br/> |Aktiverar modern lösenordsautentisering på 2013, 2016 eller 2019. <br/> [Mer information](https://support.microsoft.com/help/3126599/outlook-prompts-for-password-when-modern-authentication-is-enabled)|Den här funktionen är modern i Outlook-klienten.<br/> |
|Office 2016  <br/> |Nej, eller EnableADAL = 1  <br/> |Ja  <br/> |Modern autentiseringsförsök görs först. Om servern nekar en modern autentiseringsbegäran används grundläggande verifikation. Server nekar modern auktorisering när klient organisationen inte är aktive rad.  <br/> |Modern autentiseringsförsök görs först. Om servern nekar en modern autentiseringsbegäran används grundläggande verifikation. Server nekar modern auktorisering när klient organisationen inte är aktive rad.  <br/> |
|Office 2016  <br/> |Ja, EnableADAL = 1  <br/> |Ja  <br/> |Modern autentiseringsförsök görs först. Om servern nekar en modern autentiseringsbegäran används grundläggande verifikation. Server nekar modern auktorisering när klient organisationen inte är aktive rad.  <br/> |Modern autentiseringsförsök görs först. Om servern nekar en modern autentiseringsbegäran används grundläggande verifikation. Server nekar modern auktorisering när klient organisationen inte är aktive rad.  <br/> |
|Office 2016  <br/> |Ja, EnableADAL = 0  <br/> |Nej  <br/> |Grundläggande autentisering  <br/> |Grundläggande autentisering  <br/> |
|Office 2013  <br/> |Nej  <br/> |Nej  <br/> |Grundläggande autentisering  <br/> |Grundläggande autentisering  <br/> |
|Office 2013  <br/> |Ja, EnableADAL = 1  <br/> |Ja  <br/> |Modern autentiseringsförsök görs först. Om servern nekar en modern autentiseringsbegäran används grundläggande verifikation. Server nekar modern auktorisering när klient organisationen inte är aktive rad.  <br/> |Modern autentiseringsförsök görs först. Om servern nekar en modern autentiseringsbegäran används grundläggande verifikation. Server nekar modern auktorisering när klient organisationen inte är aktive rad.  <br/> |
   
<a name="BK_SharePointOnline"> </a>
### <a name="sharepoint-online"></a>SharePoint Online

I följande tabell beskrivs autentiseringsmetoderna för Office 2013-, Office 2016-och Office 2019-klient program när de ansluter till SharePoint Online med eller utan modern behörighet.
  
|Office-klientprogram version * * * *|Finns det någon register nyckel? * * * *|Modern-inloggning? * * * *|Autentisering är aktiverat för klient organisationen (standard) * * * *|Beteende med modern inaktive rad för klient organisationen * * * *|
|:-----|:-----|:-----|:-----|:-----|
|Office 2019  <br/> |Nej, eller EnableADAL = 1  <br/> |Ja  <br/> |Endast modern-verifikation.  <br/> |Det gick inte att ansluta.  <br/> |
|Office 2019  <br/> |Ja, EnableADAL = 1  <br/> |Ja  <br/> |Endast modern-verifikation.  <br/> |Det gick inte att ansluta.  <br/> |
|Office 2019  <br/> |Ja, EnableADAL = 0  <br/> |Nej  <br/> |Endast Microsoft Online-inloggnings assistent.  <br/> |Endast Microsoft Online-inloggnings assistent.  <br/> |
|Office 2016  <br/> |Nej, eller EnableADAL = 1  <br/> |Ja  <br/> |Endast modern-verifikation.  <br/> |Det gick inte att ansluta.  <br/> |
|Office 2016  <br/> |Ja, EnableADAL = 1  <br/> |Ja  <br/> |Endast modern-verifikation.  <br/> |Det gick inte att ansluta.  <br/> |
|Office 2016  <br/> |Ja, EnableADAL = 0  <br/> |Nej  <br/> |Endast Microsoft Online-inloggnings assistent.  <br/> |Endast Microsoft Online-inloggnings assistent.  <br/> |
|Office 2013  <br/> |Nej  <br/> |Nej  <br/> |Endast Microsoft Online-inloggnings assistent.  <br/> |Endast Microsoft Online-inloggnings assistent.  <br/> |
|Office 2013  <br/> |Ja, EnableADAL = 1  <br/> |Ja  <br/> |Endast modern-verifikation.  <br/> |Det gick inte att ansluta.  <br/> |
   
### <a name="skype-for-business-online"></a>Skype för företag – Online
<a name="BK_SFBO"> </a>

I följande tabell beskrivs autentiseringsmetoderna för Office 2013-, Office 2016-och Office 2019-klient program när de ansluter till Skype för företag – Online med eller utan modern behörighet.
  
|Office-klientprogram version * * * *|Finns det någon register nyckel? * * * *|Modern-inloggning? * * * *|Autentiseringskrav med modern inaktive rad för klient organisationen * * *|Autentisering är inaktiverat för klient organisationen (standard) * * * *|
|:-----|:-----|:-----|:-----|:-----|
|Office 2019  <br/> |Nej, eller EnableADAL = 1  <br/> |Ja  <br/> |Modern autentiseringsförsök görs först. Om servern nekar en modern autentiseringsbegäran används Microsoft Online-assistenten. Server nekar modern auktorisering när Skype för företag – Online-klient organisationer inte är aktiverade.  <br/> |Modern autentiseringsförsök görs först. Om servern nekar en modern autentiseringsbegäran används Microsoft Online-assistenten. Server nekar modern auktorisering när Skype för företag – Online-klient organisationer inte är aktiverade.  <br/> |
|Office 2019  <br/> |Ja, EnableADAL = 1  <br/> |Ja  <br/> |Modern autentiseringsförsök görs först. Om servern nekar en modern autentiseringsbegäran används Microsoft Online-assistenten. Server nekar modern auktorisering när Skype för företag – Online-klient organisationer inte är aktiverade.  <br/> |Modern autentiseringsförsök görs först. Om servern nekar en modern autentiseringsbegäran används Microsoft Online-assistenten. Server nekar modern auktorisering när Skype för företag – Online-klient organisationer inte är aktiverade.  <br/> |
|Office 2019  <br/> |Ja, EnableADAL = 0  <br/> |Nej  <br/> |Endast Microsoft Online-inloggnings assistent.  <br/> |Endast Microsoft Online-inloggnings assistent.  <br/> |
|Office 2016  <br/> |Nej, eller EnableADAL = 1  <br/> |Ja  <br/> |Modern autentiseringsförsök görs först. Om servern nekar en modern autentiseringsbegäran används Microsoft Online-assistenten. Server nekar modern auktorisering när Skype för företag – Online-klient organisationer inte är aktiverade.  <br/> |Modern autentiseringsförsök görs först. Om servern nekar en modern autentiseringsbegäran används Microsoft Online-assistenten. Server nekar modern auktorisering när Skype för företag – Online-klient organisationer inte är aktiverade.  <br/> |
|Office 2016  <br/> |Ja, EnableADAL = 1  <br/> |Ja  <br/> |Modern autentiseringsförsök görs först. Om servern nekar en modern autentiseringsbegäran används Microsoft Online-assistenten. Server nekar modern auktorisering när Skype för företag – Online-klient organisationer inte är aktiverade.  <br/> |Modern autentiseringsförsök görs först. Om servern nekar en modern autentiseringsbegäran används Microsoft Online-assistenten. Server nekar modern auktorisering när Skype för företag – Online-klient organisationer inte är aktiverade.  <br/> |
|Office 2016  <br/> |Ja, EnableADAL = 0  <br/> |Nej  <br/> |Endast Microsoft Online-inloggnings assistent.  <br/> |Endast Microsoft Online-inloggnings assistent.  <br/> |
|Office 2013  <br/> |Nej  <br/> |Nej  <br/> |Endast Microsoft Online-inloggnings assistent.  <br/> |Endast Microsoft Online-inloggnings assistent.  <br/> |
|Office 2013  <br/> |Ja, EnableADAL = 1  <br/> |Ja  <br/> |Modern autentiseringsförsök görs först. Om servern nekar en modern autentiseringsbegäran används Microsoft Online-assistenten. Server nekar modern auktorisering när Skype för företag – Online-klient organisationer inte är aktiverade.  <br/> |Endast Microsoft Online-inloggnings assistent.  <br/> |
   
## <a name="see-also"></a>Se även

[Aktivera modern autentisering för Office 2013 på Windows-enheter](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication)

[Multifaktorautentisering för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/multi-factor-authentication-microsoft-365)

[Logga in på Microsoft 365 med multifaktorautentisering](https://support.microsoft.com/office/sign-in-to-microsoft-365-with-multi-factor-authentication-2b856342-170a-438e-9a4f-3c092394d3cb)

[Översikt över Microsoft 365 Enterprise](microsoft-365-overview.md)
