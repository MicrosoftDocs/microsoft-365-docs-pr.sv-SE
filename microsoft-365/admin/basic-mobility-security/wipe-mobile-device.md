---
title: Rensa en mobil enhet i grundläggande mobilitet och säkerhet
f1.keywords:
- NOCSH
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
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Använd inbyggd grundläggande mobilitet och säkerhet för att ta bort information från registrerade enheter.
ms.openlocfilehash: 4627b0cb2d0963ae724c425a6a7ea6279f271856
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/10/2020
ms.locfileid: "47429956"
---
# <a name="wipe-a-mobile-device-in-basic-mobility-and-security"></a>Rensa en mobil enhet i grundläggande mobilitet och säkerhet

Du kan använda inbyggd grundläggande mobilitet och säkerhet för Microsoft 365 för att ta bort bara organisationsinformation, eller för att göra en fabriks återställning för att ta bort all information från en mobil enhet och återställa den till fabriks inställningarna.

## <a name="before-you-begin"></a>Innan du börjar

Mobila enheter kan lagra känslig organisationsinformation och ge till gång till organisationens Microsoft 365-resurser. För att skydda organisationens information kan du göra fabriks återställning eller ta bort företags data:
    
- **Fabriks återställning**: tar bort alla data på en användares mobila enhet, inklusive installerade program, foton och personlig information. När rensningen är klar återställs enheten till fabriks inställningarna.
    
- **Ta bort företags data**: tar bara bort organisations data och lämnar installerade program, foton och personlig information på en användares mobila enhet.   

- **När en enhet rensas (fabriks återställning eller tar bort företags data)** tas enheten bort från listan med hanterade enheter.
    
- **Återställa en enhet automatiskt**: du kan konfigurera en grundläggande mobilitet och säkerhets principer som automatiskt fabrik återställer en enhet efter det att användaren försöker ange enhets lösen ordet ett visst antal gånger. Följ stegen i [skapa säkerhets principer för enheter i grundläggande mobilitet och säkerhet](create-device-security-policies.md).
    
- **Om du vill ha information om hur du kan ta reda på användar upplevelsen** när du rensar sin enhet, se  [Vad är användare och enhets påverkan?](#whats-the-user-and-device-impact).   

## <a name="wipe-a-mobile-device"></a>Rensa en mobil enhet

1. Gå till [administrations centret för Microsoft 365](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23).
    
2. Skriv hantering av mobila enheter i Sök fältet och välj **hantering av mobila enheter** i resultat listan. 

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="Grundläggande alternativ för mobilitet och secruity mobila enheter":::

3. Välj **Hantera enheter**.

4. Välj den enhet som du vill rensa.

5. Välj **Hantera**.

6. Välj den typ av fjärrsvep du vill göra.

    - Om du vill göra en fullständig rensning och återställa enheten till fabriks inställningarna väljer du **fabriks återställning**.
    - Om du vill göra en selektiv rensning och bara ta bort Microsoft 365-organisationsinformation väljer du **ta bort företags data**.
    - Om du vill ta bort enheten från din organisation väljer du **ta bort enhet**.

7. Välj **Ja** för att bekräfta.

## <a name="how-do-i-know-it-worked"></a>Hur vet jag att det fungerade?

Den mobila enheten visas inte längre i listan med hanterade enheter.

## <a name="why-would-you-want-to-wipe-a-device"></a>Varför vill du rensa en enhet?

Rensa en enhet av följande anledningar:

- Mobila enheter som smartphones och surfplattor blir mer fulla hela tiden. Det innebär att det är lättare för användarna att lagra känslig företags information, till exempel person uppgifter eller konfidentiella meddelanden, samt komma åt den när du är på språng. Om någon av dessa mobila enheter tappas bort eller stjäls kan du förhindra att organisationens information slutar på ett felaktigt sätt genom att rensa enheten.
- När en användare lämnar organisationen med en personlig enhet som är registrerad i grundläggande mobilitet och säkerhet kan du förhindra att organisations informationen går vidare med den användaren genom att göra en fabriks återställning.
- Om din organisation tillhandahåller mobila enheter för användarna kan du behöva flytta över dem då och då. Om du gör en fabriks återställning på en enhet innan du tilldelar den till en ny användare ser du till att känslig information från den tidigare ägaren tas bort.

## <a name="whats-the-user-and-device-impact"></a>Vad händer med användare och enheter?

Rensningen skickas direkt till den mobila enheten och enheten markeras som icke-kompatibel i Azure Active Directory. När alla data tas bort när en enhet återställs till fabriks inställningarna beskrivs i följande tabell vilket innehåll som tas bort för varje enhet när en enhet tas bort från företags data.

|**Innehålls upphastighet**|**iOS 10 och senare**|**Android 5 och senare**|
|:-----|:-----|:-----|
|Microsoft 365-AppData rensas om enheten skyddas av Intune App Protection-principer. Apparna har inte tagits bort. För enheter som inte skyddas av MAM (Mobile Application Management) kan inte Outlook och OneDrive ta bort cachelagrade data.<br/>**Obs!** För att tillämpa principer för Intune-appen måste du ha en Intune-licens.|Ja|Ja|
|Princip inställningar som tillämpas av grundläggande mobilitet och säkerhet på enheter genomdrivs inte längre; användare kan ändra inställningarna.|Ja|Ja|
|E-postprofiler som skapas av grundläggande mobilitet och säkerhet tas bort och cachelagrad e-post på enheten tas bort.|Ja|Saknas|
>[!NOTE] 
>Företagsportalsappen är tillgänglig i App Store för iOS och Play Store för Android-enheter.

## <a name="related-topics"></a>Relaterade ämnen

[Konfigurera grundläggande mobilitet och säkerhet](set-up.md)