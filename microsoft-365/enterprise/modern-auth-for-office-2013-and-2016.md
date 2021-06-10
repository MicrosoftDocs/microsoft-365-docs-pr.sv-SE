---
title: Hur modern autentisering fungerar för Office 2013- och Office 2016-klientprogram
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
description: Lär dig Microsoft 365 moderna autentiseringsfunktioner fungerar annorlunda i Office 2013- och 2016-klientprogram.
ms.openlocfilehash: 3e402f5786a72f3703ab4a1a77df688176f7de61
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921672"
---
# <a name="how-modern-authentication-works-for-office-2013-office-2016-and-office-2019-client-apps"></a>Hur modern autentisering fungerar för Office 2013, Office 2016 och Office 2019-klientprogram

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Läs den här artikeln om du vill lära dig hur Office 2013-, Office 2016- och Office 2019-klientappar använder moderna autentiseringsfunktioner baserat på autentiseringskonfigurationen på Microsoft 365-klientorganisationen för Exchange Online, SharePoint Online och Skype för företag Online.

> [!NOTE]
> Äldre klientappar, till exempel Office 2010 och Office för Mac 2011, stöder inte modern autentisering och kan endast användas med grundläggande autentisering.

## <a name="availability-of-modern-authentication-for-microsoft-365-services"></a>Tillgänglighet för modern autentisering för Microsoft 365 tjänster

För Microsoft 365 tjänster är standardinställningen för modern autentisering:
  
- Aktiverad **för** Exchange Online standard. Läs [Aktivera eller inaktivera modern autentisering i Exchange Online](https://support.office.com/article/58018196-f918-49cd-8238-56f57f38d662) du vill aktivera eller inaktivera den. 
    
- Aktiverat **för** SharePoint Online som standard. 
    
- Aktiverad **för** Skype för företag Online som standard. Se [Aktivera Skype för företag Online för modern autentisering om ](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)du vill aktivera eller inaktivera den.

> [!NOTE]
> För klientorganisationen som **skapats före** den 1 augusti 2017 är modern autentisering inaktiverad som standard för användare Exchange Online och Skype för företag Online. 
    
## <a name="sign-in-behavior-of-office-client-apps"></a>Inloggningsbeteende för Office klientappar

Office 2013-klientappar har stöd för äldre autentisering som standard. Med äldre innebär att de kan använda antingen Microsoft Online-inloggningsassistenten eller grundläggande autentisering. För att dessa klienter ska kunna använda moderna autentiseringsfunktioner måste Windows ha registernycklar inställda. Anvisningar finns i Aktivera [modern autentisering för Office 2013 på Windows enheter.](https://support.office.com/article/7dc1c01a-090f-4971-9677-f1b192d6c910)

Om du vill aktivera modern autentisering för enheter med Windows (till exempel på bärbara datorer och surfplattor), som har Microsoft Office 2013 installerat, måste du ange följande registernycklar. Registernycklarna måste anges på varje enhet som du vill aktivera för modern autentisering:
  
|**Registernyckel**|**Typ**|**Värde** |
|:-------|:------:|--------:|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL  |REG_DWORD  |1  |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version |REG_DWORD |1 |
  
I [Använda modern autentisering (ADAL) med Skype för företag](./hybrid-modern-auth-overview.md) finns mer information om hur det fungerar med Skype för företag. 
  
Office 2016- och Office 2019-klienter har stöd för modern autentisering som standard och ingen åtgärd krävs för att klienten ska kunna använda dessa nya flöden. Däremot krävs en särskild åtgärd för att använda äldre autentisering.
  
Klicka på länkarna nedan för att se hur Office 2013-, Office 2016- och Office 2019-klientautentisering fungerar med Microsoft 365-tjänsterna beroende på om modern autentisering är aktiverad eller inte.
  
- [Exchange Online](modern-auth-for-office-2013-and-2016.md#BK_EchangeOnline)
    
- [SharePoint Online](modern-auth-for-office-2013-and-2016.md#BK_SharePointOnline)
    
- [Skype för företag Online](modern-auth-for-office-2013-and-2016.md#BK_SFBO)
    
<a name="BK_EchangeOnline"> </a>
### <a name="exchange-online"></a>Exchange Online

I följande tabell beskrivs autentiseringsbeteendet för Office 2013-, Office 2016- och Office 2019-klientappar när de ansluter till Exchange Online med eller utan modern autentisering.
  
|Office klientapp version****|Registernyckel finns?****|Modern autentisering på?****|Autentiseringsbeteende med modern autentisering är aktiverat för klientorganisationen (standard)****|Autentiseringsbeteende med modern autentisering är inaktiverat för klientorganisationen****|
|:-----|:-----|:-----|:-----|:-----|
|Office 2019  <br/> |Nej <br> AlwaysUseMSOAuthForAutoDiscover = 1 <br/> |Ja  <br/> |Tvingar modern autentisering Outlook 2013, 2016 eller 2019. <br/> [Mer information](https://support.microsoft.com/help/3126599/outlook-prompts-for-password-when-modern-authentication-is-enabled)|Tvingar modern autentisering inom Outlook klient.<br/> |
|Office 2019  <br/> |Nej, eller EnableADAL = 1  <br/> |Ja  <br/> |Modern autentisering används först. Om servern avvisar en anslutning för modern autentisering används grundläggande autentisering. Servern avvisar modern autentisering när klientorganisationen inte har aktiverats.  <br/> |Modern autentisering används först. Om servern avvisar en anslutning för modern autentisering används grundläggande autentisering. Servern avvisar modern autentisering när klientorganisationen inte har aktiverats.  <br/> |
|Office 2019  <br/> |Ja, EnableADAL = 1  <br/> |Ja  <br/> |Modern autentisering används först. Om servern avvisar en anslutning för modern autentisering används grundläggande autentisering. Servern avvisar modern autentisering när klientorganisationen inte har aktiverats.  <br/> |Modern autentisering används först. Om servern avvisar en anslutning för modern autentisering används grundläggande autentisering. Servern avvisar modern autentisering när klientorganisationen inte har aktiverats.  <br/> |
|Office 2019  <br/> |Ja, EnableADAL=0  <br/> |Nej  <br/> |Grundläggande autentisering  <br/> |Grundläggande autentisering  <br/> |
|Office 2016  <br/> |Nej <br> AlwaysUseMSOAuthForAutoDiscover = 1 <br/> |Ja  <br/> |Tvingar modern autentisering 2013, 2016 eller 2019. <br/> [Mer information](https://support.microsoft.com/help/3126599/outlook-prompts-for-password-when-modern-authentication-is-enabled)|Tvingar modern autentisering inom Outlook klient.<br/> |
|Office 2016  <br/> |Nej, eller EnableADAL = 1  <br/> |Ja  <br/> |Modern autentisering används först. Om servern avvisar en anslutning för modern autentisering används grundläggande autentisering. Servern avvisar modern autentisering när klientorganisationen inte har aktiverats.  <br/> |Modern autentisering används först. Om servern avvisar en anslutning för modern autentisering används grundläggande autentisering. Servern avvisar modern autentisering när klientorganisationen inte har aktiverats.  <br/> |
|Office 2016  <br/> |Ja, EnableADAL = 1  <br/> |Ja  <br/> |Modern autentisering används först. Om servern avvisar en anslutning för modern autentisering används grundläggande autentisering. Servern avvisar modern autentisering när klientorganisationen inte har aktiverats.  <br/> |Modern autentisering används först. Om servern avvisar en anslutning för modern autentisering används grundläggande autentisering. Servern avvisar modern autentisering när klientorganisationen inte har aktiverats.  <br/> |
|Office 2016  <br/> |Ja, EnableADAL=0  <br/> |Nej  <br/> |Grundläggande autentisering  <br/> |Grundläggande autentisering  <br/> |
|Office 2013  <br/> |Nej  <br/> |Nej  <br/> |Grundläggande autentisering  <br/> |Grundläggande autentisering  <br/> |
|Office 2013  <br/> |Ja, EnableADAL = 1  <br/> |Ja  <br/> |Modern autentisering används först. Om servern avvisar en anslutning för modern autentisering används grundläggande autentisering. Servern avvisar modern autentisering när klientorganisationen inte har aktiverats.  <br/> |Modern autentisering används först. Om servern avvisar en anslutning för modern autentisering används grundläggande autentisering. Servern avvisar modern autentisering när klientorganisationen inte har aktiverats.  <br/> |
   
<a name="BK_SharePointOnline"> </a>
### <a name="sharepoint-online"></a>SharePoint Online

I följande tabell beskrivs autentiseringsbeteendet för Office 2013-, Office 2016- och Office 2019-klientappar när de ansluter till SharePoint Online med eller utan modern autentisering.
  
|Office klientapp version****|Registernyckel finns?****|Modern autentisering på?****|Autentiseringsbeteende med modern autentisering är aktiverat för klientorganisationen (standard)****|Autentiseringsbeteende med modern autentisering är inaktiverat för klientorganisationen****|
|:-----|:-----|:-----|:-----|:-----|
|Office 2019  <br/> |Nej, eller EnableADAL = 1  <br/> |Ja  <br/> |Endast modern autentisering.  <br/> |Det går inte att ansluta.  <br/> |
|Office 2019  <br/> |Ja, EnableADAL = 1  <br/> |Ja  <br/> |Endast modern autentisering.  <br/> |Det går inte att ansluta.  <br/> |
|Office 2019  <br/> |Ja, EnableADAL = 0  <br/> |Nej  <br/> |Endast Microsoft Online – inloggningsassistent.  <br/> |Endast Microsoft Online – inloggningsassistent.  <br/> |
|Office 2016  <br/> |Nej, eller EnableADAL = 1  <br/> |Ja  <br/> |Endast modern autentisering.  <br/> |Det går inte att ansluta.  <br/> |
|Office 2016  <br/> |Ja, EnableADAL = 1  <br/> |Ja  <br/> |Endast modern autentisering.  <br/> |Det går inte att ansluta.  <br/> |
|Office 2016  <br/> |Ja, EnableADAL = 0  <br/> |Nej  <br/> |Endast Microsoft Online – inloggningsassistent.  <br/> |Endast Microsoft Online – inloggningsassistent.  <br/> |
|Office 2013  <br/> |Nej  <br/> |Nej  <br/> |Endast Microsoft Online – inloggningsassistent.  <br/> |Endast Microsoft Online – inloggningsassistent.  <br/> |
|Office 2013  <br/> |Ja, EnableADAL = 1  <br/> |Ja  <br/> |Endast modern autentisering.  <br/> |Det går inte att ansluta.  <br/> |
   
### <a name="skype-for-business-online"></a>Skype för företag – Online
<a name="BK_SFBO"> </a>

I följande tabell beskrivs autentiseringsbeteendet för Office 2013, Office 2016 och Office 2019-klientappar när de ansluter till Skype för företag Online med eller utan modern autentisering.
  
|Office klientapp version****|Registernyckel finns?****|Modern autentisering på?****|Autentiseringsbeteende med modern autentisering är aktiverat för klientorganisationen****|Autentiseringsbeteende med modern autentisering är inaktiverat för klientorganisationen (standard)****|
|:-----|:-----|:-----|:-----|:-----|
|Office 2019  <br/> |Nej, eller EnableADAL = 1  <br/> |Ja  <br/> |Modern autentisering används först. Om servern avvisar en anslutning för modern autentisering används Microsoft Online – inloggningsassistent. Servern avvisar modern autentisering när Skype för företag Online-klientorganisationen inte har aktiverats.  <br/> |Modern autentisering används först. Om servern avvisar en anslutning för modern autentisering används Microsoft Online – inloggningsassistent. Servern avvisar modern autentisering när Skype för företag Online-klientorganisationen inte har aktiverats.  <br/> |
|Office 2019  <br/> |Ja, EnableADAL = 1  <br/> |Ja  <br/> |Modern autentisering används först. Om servern avvisar en anslutning för modern autentisering används Microsoft Online – inloggningsassistent. Servern avvisar modern autentisering när Skype för företag Online-klientorganisationen inte har aktiverats.  <br/> |Modern autentisering används först. Om servern avvisar en anslutning för modern autentisering används Microsoft Online – inloggningsassistent. Servern avvisar modern autentisering när Skype för företag Online-klientorganisationen inte har aktiverats.  <br/> |
|Office 2019  <br/> |Ja, EnableADAL = 0  <br/> |Nej  <br/> |Endast Microsoft Online – inloggningsassistent.  <br/> |Endast Microsoft Online – inloggningsassistent.  <br/> |
|Office 2016  <br/> |Nej, eller EnableADAL = 1  <br/> |Ja  <br/> |Modern autentisering används först. Om servern avvisar en anslutning för modern autentisering används Microsoft Online – inloggningsassistent. Servern avvisar modern autentisering när Skype för företag Online-klientorganisationen inte har aktiverats.  <br/> |Modern autentisering används först. Om servern avvisar en anslutning för modern autentisering används Microsoft Online – inloggningsassistent. Servern avvisar modern autentisering när Skype för företag Online-klientorganisationen inte har aktiverats.  <br/> |
|Office 2016  <br/> |Ja, EnableADAL = 1  <br/> |Ja  <br/> |Modern autentisering används först. Om servern avvisar en anslutning för modern autentisering används Microsoft Online – inloggningsassistent. Servern avvisar modern autentisering när Skype för företag Online-klientorganisationen inte har aktiverats.  <br/> |Modern autentisering används först. Om servern avvisar en anslutning för modern autentisering används Microsoft Online – inloggningsassistent. Servern avvisar modern autentisering när Skype för företag Online-klientorganisationen inte har aktiverats.  <br/> |
|Office 2016  <br/> |Ja, EnableADAL = 0  <br/> |Nej  <br/> |Endast Microsoft Online – inloggningsassistent.  <br/> |Endast Microsoft Online – inloggningsassistent.  <br/> |
|Office 2013  <br/> |Nej  <br/> |Nej  <br/> |Endast Microsoft Online – inloggningsassistent.  <br/> |Endast Microsoft Online – inloggningsassistent.  <br/> |
|Office 2013  <br/> |Ja, EnableADAL = 1  <br/> |Ja  <br/> |Modern autentisering används först. Om servern avvisar en anslutning för modern autentisering används Microsoft Online – inloggningsassistent. Servern avvisar modern autentisering när Skype för företag Online-klientorganisationen inte har aktiverats.  <br/> |Endast Microsoft Online – inloggningsassistent.  <br/> |
   
## <a name="see-also"></a>Se även

[Aktivera modern autentisering för Office 2013 på Windows-enheter](../admin/security-and-compliance/enable-modern-authentication.md)

[Multifaktorautentisering för Microsoft 365](../admin/security-and-compliance/multi-factor-authentication-microsoft-365.md)

[Logga in på Microsoft 365 med multifaktorautentisering](https://support.microsoft.com/office/sign-in-to-microsoft-365-with-multi-factor-authentication-2b856342-170a-438e-9a4f-3c092394d3cb)

[Microsoft 365 Enterprise översikt](microsoft-365-overview.md)