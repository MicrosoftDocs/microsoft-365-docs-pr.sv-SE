---
title: Hantera enheter som är registrerade i Hantering av mobila enheter Microsoft 365
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
description: Basic Mobility and Security kan hjälpa dig att skydda och hantera mobila enheter.
ms.openlocfilehash: 4ff1c43343e00b7eac7aa38b2d266f163f79e2a7
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023887"
---
# <a name="manage-devices-enrolled-in-mobile-device-management-in-microsoft-365"></a>Hantera enheter som är registrerade i Hantering av mobila enheter Microsoft 365

Den inbyggda hanteringen av mobila enheter Microsoft 365 hjälper dig att skydda och hantera användarnas mobila enheter som iPhone, iPad, Android och Windows telefoner. Det första steget är att logga in på Microsoft 365 och konfigurera Basic Mobility and Security. Mer information finns i [Konfigurera Grundläggande rörlighet och säkerhet.](set-up.md)

När du har gjort detta måste personer i organisationen registrera sina enheter i tjänsten. Mer information finns i [Registrera din mobila enhet med grundläggande rörlighet och säkerhet.](enroll-your-mobile-device.md)Sedan kan du använda Basic Mobility and Security för att hantera enheter i organisationen. Du kan till exempel använda säkerhetsprinciper för enheter för att begränsa e-poståtkomst eller andra tjänster, visa enhetsrapporter och fjärraderning av en enhet. Du går vanligtvis till säkerhets- & för att utföra de här uppgifterna. Mer information finns i Microsoft 365 [kompatibilitetscenter.](../../compliance/microsoft-365-compliance-center.md)

## <a name="device-management-tasks"></a>Uppgifter för enhetshantering

Följ de här stegen för att komma till panelen Enhetshantering:

1. Gå till [Microsoft 365 administrationscentret.](../../admin/admin-overview/about-the-admin-center.md)

2. Skriv Hantering av mobila enheter i sökfältet och välj **Hantering av mobila** enheter i listan med   resultat.

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="Alternativ för hantering av mobila enheter":::

3. Välj  **Nu börjar vi.**

## <a name="manage-mobile-devices"></a>Hantera mobila enheter

När du har ställt in Basic Mobility and Security finns det några sätt för dig att hantera mobila enheter i din organisation.

|**Om du vill**|**Gör så här**|
|:----------------|:------------------------------------------------------------------------------|
|Rensa en enhet |I panelen Enhetshantering väljer du *enhetens* namn och sedan Fullständig rensning för att ta bort all information eller Selektiv rensning om du bara vill ta  ****   bort  ****   organisationsinformation på enheten. Mer information finns i Rensa [en mobil enhet i Grundläggande rörlighet och säkerhet.](wipe-mobile-device.md)|
|Blockera enheter som inte stöds från att komma åt Exchange via e-Exchange ActiveSync |I panelen Enhetshantering väljer du  **Blockera**. |
|Konfigurera enhetsprinciper som lösenordskrav och säkerhetsinställningar |I panelen Enhetshantering väljer du **Säkerhetsprinciper för enheter Lägg**   >  **till +**. Mer information finns i Skapa [säkerhetsprinciper för enheter i Grundläggande rörlighet och säkerhet.](create-device-security-policies.md)|
|Visa lista över blockerade enheter  |I panelen Enhetshantering under Välj  **en vy väljer** du     **Blockerade**. |
|Ta bort blockering av en enhet som inte stöds för en användare eller grupp av användare  |Välj något av följande för att häva blockeringen av enheter:<br/>– Ta bort användaren eller användarna från säkerhetsgruppen som principen har tillämpats på. Gå till Microsoft 365 administrationscenter > **Grupper** och välj sedan gruppnamn. Välj **Redigera medlemmar och administratörer.**<br/>– Ta bort säkerhetsgruppen som användarna är medlemmar i från enhetsprincipen. Gå till Säkerhets- & Säkerhetscenter > **Säkerhetsprinciper**   >  **Enhetssäkerhetsprinciper**. Välj namn på enhetsprincip och välj sedan **Redigera**  >  **distribution.**<br/>- Ta bort blockeringen för alla enheter som inte är kompatibla med en enhet. Gå till Säkerhets- & Säkerhetscenter > **Säkerhetsprinciper**   >  **Enhetssäkerhetsprinciper**. Välj namn på enhetsprincip och välj sedan **Redigera**  >  **åtkomstkrav**. Välj  **Tillåt åtkomst och rapportbrott**.<br/>– Om du vill ta bort blockering av en enhet som inte stöds för en användare eller en grupp användare går du till Säkerhets- och efterlevnadscenter för & > **Säkerhetsprinciper** Enhetshantering Hantera inställningar för   >  ****   >  **enhetsåtkomst.** Lägg till en säkerhetsgrupp med de medlemmar du vill utesluta från att blockeras åtkomst till Microsoft 365. Mer information finns i [Skapa, redigera eller ta bort en säkerhetsgrupp i Microsoft 365 administrationscenter.](../../admin/email/create-edit-or-delete-a-security-group.md)|
|Ta bort användare så att deras enheter inte längre hanteras av Basic Mobility and Security |Om du vill ta bort användaren redigerar du säkerhetsgruppen som har principer för enhetshantering för enkel rörlighet och säkerhet. Mer information finns i  [Skapa, redigera eller ta bort en säkerhetsgrupp i Microsoft 365 administrationscenter.](../../admin/email/create-edit-or-delete-a-security-group.md)<br/>Om du vill ta bort Grundläggande rörlighet och säkerhet från Microsoft 365 användarna kan du [gå till Inaktivera grundläggande rörlighet och säkerhet.](turn-off.md)|

Live (v14)