---
title: Lokalisera användarupplevelsen
description: Så här lokaliserar du enheter för användare
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 354f61284bbd95c1c7ca4cd50459a1644a89d090
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023267"
---
# <a name="localize-the-user-experience"></a>Lokalisera användarupplevelsen

Användare av Microsoft Hanterat skrivbord-enheter kan välja vilket språk de vill ha antingen under installationen (eller efteråt).

## <a name="during-setup-the-out-of-box-experience"></a>Under installationen (när installationen är slut)

När installationen är slutförd kan användarna välja ett språk. Det här valet påverkar följande attribut:

- Windows 10 språkfunktioner:
    - Visningsspråk
    - Tangentbordsspråk
    - Språkrelaterade funktioner på begäran

- Microsoft 365 Språkfunktioner för Appar för företag:
    - Visningsspråk
    - Språkverktyg

> [!NOTE]
> Användarna kan bara få språkrelaterade funktioner på begäran genom att välja språk under installationen.

## <a name="after-completing-setup"></a>När installationen är slutförd

Användarna kan välja språk för de olika Windows 10 och Microsoft 365 för företag när som helst efter att installationen har slutförts. Mer specifikt:

- Windows 10 språkfunktioner:
    - Visningsspråk
    - Tangentbordsspråk

- Microsoft 365 Språkfunktioner för Appar för företag:
    - Visningsspråk
    - Språkverktyg

Om du vill [göra språk](#supported-languages) som stöds för Microsoft 365-program för företag tillgängliga för användarna att installera lägger du till användarna i gruppen **Modern Office-Language_Packs.** Språken är tillgängliga i Intune-företagsportal.


## <a name="supported-languages"></a>Språk som stöds

För nya enheter måste tillverkaren tillhandahålla enhetsbilder som innehåller de språk du behöver. Om tillverkarens bild innehåller andra språk än de som anges i listan med språk som stöds stöds detta fortfarande av tjänsten.

Om du återanvänder befintliga enheter kan du behöva kontakta din Microsoft-kontorepresentant för att skaffa lämpliga bilder. Mer information finns i [Enhetsbilder](../service-description/device-images.md).

Den [universella](../service-description/device-images.md#universal-image) bilden som tillhandahålls Microsoft Hanterat skrivbord inkluderar dessa språk och för Windows 10:

- Arabiska
- Bulgarian
- Chinese Simplified
- Chinese Traditional
- Croatian
- Czech
- Danish  
- Dutch  
- Engelska (USA, GB, AU, CA, IN)
- Estonian
- Finnish 
- Franska (Frankrike, Kanada)
- German
- Greek
- Hebrew
- Hungarian
- Indonesian
- Italian
- Japanska
- Koreanska
- Latvian
- Lithuanian
- Norska (bokmål)
- Polish
- Portugisiska (Brasilien)
- Portugisiska (Portugal)
- Romanian
- Russian 
- Serbiska (latinskt alfabet)
- Slovak
- Slovenian
- Spanska (Spanien, Mexiko)
- Swedish
- Thai
- Turkish
- Ukrainian
- Vietnamese

Microsoft 365 Apparna för företag kan ha stöd för en något annorlunda lista.

Om dina användare behöver ett annat språk än de som anges här kan du arkivera en [supportbegäran](../working-with-managed-desktop/admin-support.md) med hjälp av [administrationsportalen.](access-admin-portal.md)

## <a name="languages-for-support-and-operations"></a>Språk för support och åtgärder

### <a name="user-support"></a>Användarsupport
Microsoft Hanterat skrivbord har endast stöd på engelska. Om användarna väljer ett annat språk i Få hjälp-appen får de support från de allmänna Microsoft-supportkanalerna, i stället för direkt från Microsoft Hanterat skrivbord. Mer information finns i [Få hjälp för användare.](../working-with-managed-desktop/end-user-support.md)

Om dina användare behöver stöd på andra språk måste du tillhandahålla det via supportkällor som inte finns från Microsoft eller från din egen organisation.

### <a name="admin-support-and-operations"></a>Administratörsstöd och -åtgärder
Microsoft Hanterat skrivbord administratörssupport på engelska. Det omfattar administrationsportalen och all kommunikation med Microsoft Hanterat skrivbord åtgärder. Du bör förutsätta att alla administratörsrelaterade interaktioner och gränssnitt kommer att vara på engelska, om inget annat anges.


