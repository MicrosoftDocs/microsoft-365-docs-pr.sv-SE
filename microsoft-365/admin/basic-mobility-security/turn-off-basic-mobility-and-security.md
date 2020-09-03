---
title: Stänga av grundläggande mobilitet och säkerhet
f1.keywords: NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
description: Ta bort grupper eller principer för att stänga av grundläggande mobilitet och säkerhet.
ms.openlocfilehash: 54f78cc30e5259ad5244ce3a8fc6d0f46a395d7c
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/02/2020
ms.locfileid: "47337114"
---
# <a name="turn-off-basic-mobility-and-security"></a>Stänga av grundläggande mobilitet och säkerhet

För att effektivt stänga av grundläggande mobilitet och säkerhet tar du bort grupper av personer som definieras av säkerhets grupper från enhets hanterings principer eller tar bort själva principer.

- Ta bort grupper med användare genom att ta bort säkerhets grupper för användare från de enheter som du har skapat.
    
- Inaktivera grundläggande mobilitet och säkerhet för alla genom att ta bort alla grundläggande principer för mobilitet och säkerhet.
    
De här alternativen tar bort grundläggande mobilitet och säkerhet för enheter i din organisation. Tyvärr kan du inte helt enkelt "avetablera" grundläggande mobilitet och säkerhet när du har konfigurerat det. 

>[!IMPORTANT]
>Observera att det påverkar användarnas enheter när du tar bort säkerhets grupper för användare från principer eller tar bort själva principer. E-postprofiler och cachelagrade e-postmeddelanden kan till exempel tas bort beroende på enheten. Mer information finns i  [vad som händer när du tar bort en princip eller tar bort en användare från policyn?](https://support.microsoft.com/office/create-device-security-policies-in-basic-mobility-and-security-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6#bkmk_changeimpact)

## <a name="remove-user-security-groups-from-basic-mobility-and-security-device-policies"></a>Ta bort säkerhets grupper för användare från grundläggande principer för mobilitet och säkerhets enheter

1. I webbläsaren:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .

2. Välj en enhets princip och välj sedan **Redigera princip**. 

3.  **Deployment**   Välj **ta bort**på sidan distribution.
    
4. Under  **grupper**väljer du en säkerhets grupp.

5. Välj  **ta bort**och välj sedan **Spara**.
    

## <a name="remove-basic-mobility-and-security-device-policies"></a>Ta bort principer för mobilitet och säkerhets enheter

1.  I webbläsaren:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) . 

2.  Välj en enhets princip och välj sedan  **ta bort princip**.
    
3.  I dialog rutan varning väljer du **Ja**.

>[!NOTE] 
>Om du vill veta mer om hur du avblockerar enheter om dina organisations enheter fortfarande är spärrade kan du läsa blogg inlägget [ta bort åtkomst kontroll från hantering av mobila enheter för Office 365](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934).
