---
title: Hantera enheter som är registrerade i hantering av mobila enheter i Microsoft 365
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
description: Grundläggande mobilitet och säkerhet kan hjälpa dig att skydda och hantera mobila enheter.
ms.openlocfilehash: 36ea0d12becca2e97a56aceea107fa1f5bf6ded4
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/02/2020
ms.locfileid: "47337127"
---
# <a name="manage-devices-enrolled-in-mobile-device-management-in-microsoft-365"></a>Hantera enheter som är registrerade i hantering av mobila enheter i Microsoft 365

Den inbyggda mobila enhets hanteringen för Microsoft 365 hjälper dig att skydda och hantera användarnas mobila enheter som iPhone, iPad, Android och Windows-telefoner. Det första steget är att logga in på Microsoft 365 och ställa in grundläggande mobilitet och säkerhet. Mer information finns i [Konfigurera grundläggande mobilitet och säkerhet](set-up-basic-mobility-and-security.md).

När du har konfigurerat det måste personerna i din organisation registrera sina enheter i tjänsten. Mer information finns i [Registrera din mobila enhet med grundläggande mobilitet och säkerhet](enroll-your-mobile-device-using-basic-mobility-and-security.md).Sedan kan du använda grundläggande mobilitet och säkerhet för att hantera enheter i din organisation. Du kan till exempel använda säkerhets principer för enheter för att begränsa åtkomst till e-post eller andra tjänster, Visa enheter och rensa en enhet. Du kommer normalt till sidan säkerhets & efterlevnad för att utföra de här uppgifterna. Mer information finns i [Microsoft 365 Compliance Center](https://support.microsoft.com/office/7e696a40-b86b-4a20-afcc-559218b7b1b8).

## <a name="device-management-tasks"></a>Enhets hanterings uppgifter

Följ de här stegen för att komma till panelen enhets hantering:

1. Gå till [administrations centret för Microsoft 365](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23).
    
2. Skriv hantering av mobila enheter i Sök fältet och välj **hantering av mobila enheter**   i resultat listan.

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="Alternativ för mobila enheter":::

3. Välj  **Hantera enheter**.

## <a name="manage-mobile-devices"></a>Hantera mobila enheter
    
När du har grundläggande mobilitet och säkerhets inställningar är det här några sätt att hantera mobila enheter i din organisation.

|**För att göra detta**|**Gör du så här**|
|:----------------|:------------------------------------------------------------------------------|
|Rensa en enhet |På panelen enhets hantering väljer du *enhetens namn*och sedan  **fullständig rensning**   för att ta bort all information eller  **selektiv rensning**   för att enbart ta bort organisationsinformation på enheten. Mer information finns i [Rensa en mobil enhet i grundläggande mobilitet och säkerhet](wipe-mobile-device.md).|
|Blockera enheter som inte stöds från åtkomst till Exchange-e-post med Exchange ActiveSync |I panelen enhets hantering väljer du  **blockera**. |
|Konfigurera enhets principer som lösen ords krav och säkerhets inställningar |I panelen enhets hantering väljer du **säkerhets principer för enheter**   >  **Add +**. Mer information finns i [skapa säkerhets principer för enheter i grundläggande mobilitet och säkerhet](create-device-security-policies-in-basic-mmobility-and-security.md).|
|Visa lista över blockerade enheter  |Välj blockera i panelen enhets hantering under  **Välj en vy**   .  **Blocked** |
|Avblockera ej kompatibel eller enhet som inte stöds för en användare eller grupp av användare  |Välj något av följande för att avblockera enheter:<br/>-Ta bort användaren eller användarna från säkerhets gruppen som principen har använts för. Gå till administrations centret för Microsoft 365 > **grupper**och välj sedan grupp namn. Välj **Redigera medlemmar och administratörer**.<br/>-Ta bort den säkerhets grupp som användarna tillhör från enhets principen. Gå till säkerhets & Compliance Center >säkerhets principer för  **säkerhets principer**   >  **Device security policies**. Välj enhets princip namn och välj sedan **Redigera**  >  **distribution**.<br/>-Avblockera alla icke-kompatibla enheter för en enhets princip. Gå till säkerhets & Compliance Center >säkerhets principer för  **säkerhets principer**   >  **Device security policies**. Välj enhets princip namn och välj sedan **Redigera**  >  **åtkomst krav**. Välj  **Tillåt åtkomst och rapportera fel**.<br/>-För att häva blockering av en icke-kompatibel eller enhet som inte stöds för en användare eller grupp av användare, gå till säkerhets & Compliance  **Center >hantering av enhets**åtkomst i hantera enhets   >  **Device management**   >  **Inställningar**. Lägga till en säkerhets grupp med medlemmar som du vill undanta från åtkomst till Microsoft 365. Mer information finns i [skapa, redigera eller ta bort en säkerhets grupp i administrations centret för Microsoft 365](https://support.microsoft.com/office/55c96b32-e086-4c9e-948b-a018b44510cb).|
|Få information om enheterna i din organisation  |Mer information, till exempel vilka enheter som är registrerade och kompatibla med säkerhets principer för enheter finns i [få information om grundläggande enheter för mobilitet och säkerhet](get-details-about-basic-mobility-and-security-managed-devices.md).|
|Ta bort användare så att deras enheter inte längre hanteras av grundläggande mobilitet och säkerhet |Om du vill ta bort användaren redigerar du den säkerhets grupp som innehåller principer för grundläggande mobilitet och säkerhet. Mer information finns i  [skapa, redigera eller ta bort en säkerhets grupp i administrations centret för Microsoft 365](https://support.microsoft.com/office/55c96b32-e086-4c9e-948b-a018b44510cb).<br/>Information om hur du tar bort grundläggande mobilitet och säkerhet från alla dina Microsoft 365-användare finns i [Inaktivera grundläggande mobilitet och säkerhet](turn-off-basic-mobility-and-security.md).|

Live (v14)