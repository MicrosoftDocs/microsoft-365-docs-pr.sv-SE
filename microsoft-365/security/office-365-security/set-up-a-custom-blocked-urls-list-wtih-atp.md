---
title: Konfigurera en anpassad lista över blockerade webbadresser med office 365 ATP-säkra länkar
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 896a7efb-1683-465e-a394-261349e5d866
ms.collection:
- M365-security-compliance
description: Lär dig hur du konfigurerar en lista över blockerade webbadresser för din organisation med Office 365 Advanced Threat Protection. De blockerade webbadresserna gäller för e-postmeddelanden och Office-dokument enligt dina åtkomst- och policyer för åtkomsttjänster för betrodda länkar.
ms.openlocfilehash: 5205fbd5ccc873513eed4e367119084516e92bf2
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42811855"
---
# <a name="set-up-a-custom-blocked-urls-list-using-office-365-atp-safe-links"></a>Konfigurera en anpassad lista över blockerade webbadresser med office 365 ATP-säkra länkar

> [!IMPORTANT]
> Den här artikeln är avsedd för företagskunder som har [Office 365 Advanced Threat Protection](office-365-atp.md). Om du är hemanvändare som letar efter information om säkra länkar i Outlook läser du [Avancerad Outlook.com säkerhet](https://support.office.com/article/882d2243-eab9-4545-a58a-b36fee4a46e2).

Med [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) kan din organisation ha en anpassad lista över webbadresser som är blockerade. När en WEBBADRESS blockeras tas personer som klickar på länkar till den blockerade webbadressen till en [varningssida](atp-safe-links-warning-pages.md) som liknar följande bild: 
  
![Den här webbplatsen är blockerad](../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)
  
Listan blockerade webbadresser definieras av organisationens säkerhetsteam för Office 365 och listan gäller för alla i organisationen som omfattas av Office 365 ATP-principer för säkra länkar. 
  
Läs den här artikeln om du vill lära dig hur du konfigurerar organisationens anpassade blockerade webbadresser för [ATP-säkra länkar i Office 365](atp-safe-links.md).
  
## <a name="view-or-edit-a-custom-list-of-blocked-urls"></a>Visa eller redigera en anpassad lista över blockerade webbadresser

[ATP-säkra länkar i Office 365](atp-safe-links.md) använder flera listor, inklusive organisationens anpassade blockerade webbadresser. Om du har de behörigheter som krävs kan du konfigurera organisationens anpassade lista. Du gör detta genom att redigera organisationens standardprincip för säkra länkar.

Om du vill redigera (eller definiera) ATP-principer måste du tilldelas en av de roller som beskrivs i följande tabell: 

|Roll  |Var/hur tilldelad  |
|---------|---------|
|Global administratör för Office 365 |Personen som registrerar sig för att köpa Office 365 är som standard en global administratör. (Se [Om Office 365-administratörsroller](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) att lära sig mer.)         |
|Säkerhetsadministratör |Administrationscenter för[https://aad.portal.azure.com](https://aad.portal.azure.com)Azure Active Directory ( )|
|Exchange Online Organisation Management |Administrationscenter[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)för Exchange ( ) <br>eller <br>  PowerShell-cmdlets (se [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)) |

> [!TIP]
> Mer information om roller och behörigheter finns [i Behörigheter &amp; i Office 365 Security Compliance Center](permissions-in-the-security-and-compliance-center.md).

### <a name="to-view-or-edit-a-custom-blocked-urls-list"></a>Så här visar eller redigerar du en anpassad lista över blockerade webbadresser
  
1. Gå [https://protection.office.com](https://protection.office.com) till och logga in med ditt arbets- eller skolkonto. 
    
2. Välj **Principsäkra** \> **länkar**under **Hothantering**i den vänstra navigeringen.
    
3. I de **principer som gäller för hela organisationsavsnittet** väljer du **Standard**och väljer sedan **Redigera** (knappen Redigera liknar en penna).<br/>![Klicka på Redigera om du vill redigera standardprincipen för skydd av säkra länkar](../../media/d08f9615-d947-4033-813a-d310ec2c8cca.png)<br/>På så sätt kan du visa listan över blockerade webbadresser. Först kanske du inte har några webbadresser listade här.<br/>![Listan Blockerade webbadresser i standardprincipen För säkra länkar](../../media/575e1449-6191-40ac-b626-030a2fd3fb11.png)
  
4. Markera rutan **Ange en giltig URL,** skriv en URL**+** och välj sedan plustecknet ( ). 

5. När du är klar med webbadresserna väljer du **Spara**i det nedre högra hörnet av skärmen.
    
## <a name="a-few-things-to-keep-in-mind"></a>Några saker att tänka på

När du lägger till webbadresser i listan bör du tänka på följande punkter: 

- Ta inte med ett **/** framåtsnedstreck () i slutet av webbadressen. I stället för `https://www.contoso.com/`att `https://www.contoso.com`ange anger du till exempel .
    
- Du kan ange en url `contoso.com` endast `tailspintoys.com`för domän (till exempel eller ). Detta blockerar klick på en WEBBADRESS som innehåller domänen.

- Du kan ange en `toys.contoso.com*`underdomän (t.ex. `contoso.com`) utan att blockera en fullständig domän (t.ex. ). Detta blockerar klick på en URL som innehåller underdomänen, men den blockerar inte klick på en URL som innehåller hela domänen.  
    
- Du kan inkludera upp till tre\*jokerteckenasterisker () per WEBBADRESS. I följande tabell visas några exempel på vad du kan ange och vilken effekt dessa poster har.
    
|**Exempel på post**|**Vad den gör**|
|:-----|:-----|
|`contoso.com`Eller`*contoso.com*`  <br/> |Blockerar domän, underdomäner och sökvägar, `https://www.contoso.com`till `https://sub.contoso.com`exempel , och`https://contoso.com/abc`  <br/> |
|`https://contoso.com/a`  <br/> |Blockerar en `https://contoso.com/a` plats men inte ytterligare underbanor som`https://contoso.com/a/b`  <br/> |
|`https://contoso.com/a*`  <br/> |Blockerar en `https://contoso.com/a` plats och ytterligare underbanor som`https://contoso.com/a/b`  <br/> |
|`https://toys.contoso.com*`  <br/> |Blockerar en underdomän ("leksaker" i det här fallet) men `https://contoso.com` tillåter `https://home.contoso.com`klick på andra domänadresser (gilla eller ).  <br/> |
   

## <a name="how-to-define-exceptions-for-certain-users-in-an-organization"></a>Så här definierar du undantag för vissa användare i en organisation

Om du vill att vissa grupper ska kunna visa webbadresser som kan blockeras för andra kan du ange en ATP-princip för säkra länkar som gäller för specifika mottagare. Se [Konfigurera en anpassad "skriv inte om" webbadresser med hjälp av ATP-säkra länkar](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).
  

