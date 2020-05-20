---
title: Säkra ATP-länkar
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.topic: overview
f1_keywords:
- "197503"
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- ZVO160
- ZXL160
- ZPP160
- ZWD160
ms.assetid: dd6a1fef-ec4a-4cf4-a25a-bb591c5811e3
description: I den här artikeln får du lära dig hur du använder Säkra länkar för att skydda din organisation från nätfiske och andra attacker.
ms.openlocfilehash: 3dfa4016b34f430a260c9af4be2ed0c4126dea34
ms.sourcegitcommit: 4ce28ad4d17d336106c1720d65349f19f9e90e04
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2020
ms.locfileid: "44294235"
---
# <a name="atp-safe-links"></a>Säkra ATP-länkar

## <a name="overview-of-office-365-atp-safe-links"></a>Översikt över safe links för Office 365 ATP

> [!IMPORTANT]
> Den här artikeln är avsedd för företagskunder som har [Office 365 Avancerat skydd](office-365-atp.md). Om du använder Outlook.com, Microsoft 365 Family eller Microsoft 365 Personal och letar efter information om säkra länkar i Outlook läser du [Avancerad Outlook.com säkerhet](https://support.office.com/article/882d2243-eab9-4545-a58a-b36fee4a46e2).

Office 365 ATP Safe Links (en del av [Office 365 Advanced Threat Protection)](office-365-atp.md)kan skydda din organisation genom att tillhandahålla snabbverifiering av webbadresser (WEBBADRESSER) i [e-postmeddelanden](how-atp-safe-links-works.md#how-atp-safe-links-works-with-urls-in-email) och [Office-dokument](how-atp-safe-links-works.md#how-atp-safe-links-works-with-urls-in-office-documents). Skyddet definieras via [ATP Safe Links-principer](set-up-atp-safe-links-policies.md) som anges av ditt Microsoft 365-säkerhetsteam.
  
När dina ATP Safe Links-principer är på plats kan globala administratörer, säkerhetsadministratörer och säkerhetsläsare [visa rapporter för avancerat skydd mot hot](view-reports-for-atp.md). Informationen i dessa rapporter kan hjälpa säkerhetsteamet att vidta ytterligare åtgärder för att skydda din organisation eller undersöka säkerhetsincidenter.

När [nya funktioner läggs till i ATP](office-365-atp.md#new-features-in-office-365-atp)kan ditt Microsoft 365-säkerhetsteam lägga till eller redigera organisationens [ATP Safe Links-principer](set-up-atp-safe-links-policies.md). Dessutom kan du märka ändringar och förbättringar, till exempel våra nyligen reviderade [varningssidor](atp-safe-links-warning-pages.md) och inbyggd länkåtergivning i Outlook (som introducerades i Microsoft 365 Apps for Enterprise version 1809).
         
## <a name="how-to-get-atp-safe-links-protection"></a>Hur får ATP Safe Links skydd

**Kontrollera först att din prenumeration innehåller [ett avancerat skydd mot Office 365](office-365-atp.md) ** Plan 1 eller plan 2. Office 365 ATP ingår i prenumerationer, till exempel [Microsoft 365 Enterprise,](https://www.microsoft.com/microsoft-365/enterprise/home) [Microsoft 365 Business Premium,](https://www.microsoft.com/microsoft-365/business)Office 365 Enterprise E5, Office 365 Education A5 osv. Om din organisation har en Microsoft 365-prenumeration som inte innehåller Office 365 ATP kan du eventuellt köpa ATP som ett tillägg. Mer information finns i följande resurser: 

- [Office 365 Avancerade hotskyddsplaner och priser](https://products.office.com/exchange/advance-threat-protection)

- [Beskrivning av tjänsten för avancerat hotskydd i Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) 
  
**Kontrollera sedan att atp-principerna för säkra länkar har definierats**. (Se [Konfigurera principer för betrodda länkar för Office 365 ATP](set-up-atp-safe-links-policies.md).) ATP Safe Links-funktionerna är aktiva när:
  
- ATP-principer för säkra länkar har ställts in för e-post och Office-dokument. (Se [Konfigurera principer för betrodda länkar till ATP](set-up-atp-safe-links-policies.md).)

- Microsoft 365-klientappar är konfigurerade för att använda modern autentisering (detta är för ATP Safe Links-skydd i Office-dokument). (Se [Modern autentisering för Office 2016](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016).) 
    
- Användare har loggat in med sitt arbets- eller skolkonto. (Se [Logga in på Office eller Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426).)
    
- Organisationens e-post skickas via Exchange Online Protection.  

**Se också till att du har de behörigheter som krävs**. Om du vill definiera (eller redigera) ATP-principer måste du tilldelas en lämplig roll. Några exempel beskrivs i följande tabell:

|Roll  |Var/hur tilldelas  |
|---------|---------|
|global administratör |Den person som registrerar sig för att köpa Microsoft 365 är en global administratör som standard. (Läs [mer om Microsoft 365-administratörsroller.)](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)         |
|Säkerhetsadministratör |Administrationscenter för Azure Active Directory ( [https://aad.portal.azure.com](https://aad.portal.azure.com) )|
|Hantering av Exchange Online-organisation |Administrationscenter för Exchange ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) <br>eller <br>  PowerShell-cmdletar (se [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)) |
    
## <a name="how-to-make-sure-atp-safe-links-protection-is-in-place"></a>Så här ser du till att ATP Safe Links-skyddet finns på plats

Som global administratör eller säkerhetsadministratör bör du granska dina [ATP Safe Links-principer](set-up-atp-safe-links-policies.md) regelbundet. ATP Safe Links-principer avgör om skydd gäller endast hyperlänkar i e-postmeddelanden eller även webbadresser i Office-dokument.

När ATP Safe Links-principer har införts kan organisationens säkerhetsteam se hur ATP Safe Links-skyddet fungerar för din organisation genom [att visa rapporter för avancerat skydd mot hot](view-reports-for-atp.md). 

## <a name="example-scenarios"></a>Exempel på scenarier
  
I följande tabell beskrivs några exempelscenarier där ATP Safe Links-skydd kan finnas eller inte finns på plats. (I alla dessa fall antar vi att organisationen har Office 365 Enterprise E5.)
  
|**Exempel scenario**|**Gäller ATP Safe Links-skydd i det här fallet?**|
|:-----|:-----|
|Jean är medlem i en grupp som har ATP Safe Links-principer som täcker webbadresser i e-post- och Office-dokument. Jean öppnar en PowerPoint-presentation som någon har skickat och klickar sedan på en URL i presentationen.  <br/> |Ja. De ATP Safe Links-principer som har definierats gäller jean:s grupp-, Jean-e-post- och Word-, Excel-, PowerPoint- eller Visio-dokument som Jean öppnar, så länge Jean är inloggad och använder Microsoft 365 Apps för företag på Windows-, iOS- eller Android-enheter.  <br/> |
|I Chris organisation har inga globala administratörer eller säkerhetsadministratörer definierat några ATP-principer för säkra länkar ännu. Chris får ett e-postmeddelande som innehåller en webbadress till en skadlig webbplats. Chris är omedveten om webbadressen är skadlig och klickar på länken.  <br/> |Nej. Standardprincipen som täcker webbadresser för alla i organisationen måste definieras för att skyddet ska vara på plats.  <br/> |
|I Pats organisation har inga globala administratörer eller säkerhetsadministratörer definierat eller redigerat några ATP Safe Links-principer ännu. Pat öppnar ett Word-dokument och klickar på en URL i filen.  <br/> |Nej. En princip som innehåller Office-dokument måste definieras för att skyddet ska vara på plats. Se [Konfigurera ATP-principer för säkra länkar i Office 365](set-up-atp-safe-links-policies.md).  <br/> |
|Lees organisation har en ATP Safe Links-policy som har `https://tailspintoys.com` listats som en blockerad webbplats. Lee får ett e-postmeddelande som innehåller en URL till `https://tailspintoys.com/aboutus/trythispage` . Lee klickar på webbadressen.  <br/> |Det beror på om hela webbplatsen och alla dess undersidor ingår i listan över blockerade webbadresser. Se [Konfigurera en anpassad lista med blockerade webbadresser med ATP Safe Links](set-up-a-custom-blocked-urls-list-atp.md).  <br/> |
|Jamie, Jean kollega, skickar ett e-postmeddelande till Jean, utan att veta att e-postmeddelandet innehåller en skadlig webbadress.  <br/> |Det beror på om ATP Safe Links-principer har definierats för e-post som skickas inom organisationen. Se [Konfigurera ATP-principer för säkra länkar i Office 365](set-up-atp-safe-links-policies.md).  <br/> |


  

