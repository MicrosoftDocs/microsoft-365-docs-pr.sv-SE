---
title: Aktivera modern autentisering för Office 2013 på Windows-enheter
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
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7dc1c01a-090f-4971-9677-f1b192d6c910
description: Lär dig att ange registernycklar för att aktivera modern autentisering för enheter som har Microsoft Office 2013 installerat.
ms.openlocfilehash: 8dec8174d5f39d8fecd6b2a7340d69dbcd421357
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43627734"
---
# <a name="enable-modern-authentication-for-office-2013-on-windows-devices"></a>Aktivera modern autentisering för Office 2013 på Windows-enheter

Om du vill aktivera modern autentisering för Windows-enheter som har Office 2013 installerat, måste du ange specifika registernycklar.
  
## <a name="enable-modern-authentication-for-office-2013-clients"></a>Aktivera modern autentisering för Office 2013-klienter

> [!NOTE]
> Modern autentisering redan är aktiverad för Office 2016-klienter så du behöver inte ange registernycklar för Office 2016. 
  
Om du vill aktivera modern autentisering för enheter med Windows (till exempel på bärbara datorer och surfplattor), som har Microsoft Office 2013 installerat, måste du ange följande registernycklar. Registernycklarna måste anges på varje enhet som du vill aktivera för modern autentisering:
  
|**Registernyckel**|**Typ**|**Värde** |
|:-------|:------:|--------:|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL  |Reg_dword  |1  |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version |Reg_dword |1 |
   
När du har angett registernycklarna kan du ange att Office 2013-enheter ska använda [MFA (Multifactor Authentication)](set-up-multi-factor-authentication.md) med Microsoft 365. 
  
Om du för närvarande är inloggad med något av klientprogrammen måste du logga ut och logga in igen för att ändringen ska börja gälla. I annat fall är MRU- och roaminginställningarna otillgängliga tills ADAL-identiteten har upprättats.
  
## <a name="disable-modern-authentication-on-devices"></a>Inaktivera modern autentisering på enheter

Du inaktiverar modern autentisering på en enhet genom att ange följande registernycklar på enheten:
  
|**Registernyckel**|**Typ**|**Värde**|
|:-------|:------:|--------:|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL |Reg_dword|0|
   
## <a name="related-articles"></a>Relaterade artiklar
[Logga in på Office 2013 med en andra metod för verifiering](https://support.office.com/article/2b856342-170a-438e-9a4f-3c092394d3cb.aspx)

  

