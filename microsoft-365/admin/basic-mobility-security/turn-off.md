---
title: Stäng av grundläggande Mobility and Security
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
description: Ta bort grupper eller principer för att inaktivera Grundläggande rörlighet och säkerhet.
ms.openlocfilehash: 7ec4ec0d47668c21824d8e01e3845d637b9b0922
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228141"
---
# <a name="turn-off-basic-mobility-and-security"></a>Stäng av grundläggande Mobility and Security

För att effektivt inaktivera Grundläggande rörlighet och säkerhet tar du bort grupper av personer som definieras av säkerhetsgrupper från principer för enhetshantering eller tar bort principerna själva.

- Ta bort grupper av användare genom att ta bort användarsäkerhetsgrupper från enhetsprinciperna som du har skapat.

- Inaktivera grundläggande rörlighet och säkerhet för alla genom att ta bort alla principer för grundläggande rörlighet och säkerhetsenhet.

Med de här alternativen tas tillämpning av Basic Mobility och Security bort för enheter i organisationen. Tyvärr kan du inte bara "återkalla" Basic Mobility and Security när du har konfigurerat den.

> [!IMPORTANT]
> Tänk på hur användarnas enheter påverkas när du tar bort användarnas säkerhetsgrupper från principerna eller tar bort principerna. Till exempel kan e-postprofiler och cachelagrade e-postmeddelanden tas bort, beroende på enhet. Mer information finns i Vad  [händer när du tar bort en princip eller tar bort en användare från principen?](../../admin/basic-mobility-security/create-device-security-policies.md)

## <a name="remove-user-security-groups-from-basic-mobility-and-security-device-policies"></a>Ta bort användarsäkerhetsgrupper från principer för grundläggande rörlighet och säkerhetsenhet

1. Skriv följande i webbläsaren:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .

2. Välj en enhetsprincip och sedan **Redigera princip**.

3. Välj  **Ta bort**   på sidan **Distribution.**

4. Välj  **en** säkerhetsgrupp under Grupper.

5. Välj  **Ta** bort och sedan **Spara**.

## <a name="remove-basic-mobility-and-security-device-policies"></a>Ta bort principer för grundläggande rörlighet och säkerhetsenhet

1. Skriv följande i webbläsaren:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .

2. Välj en enhetsprincip och välj sedan Ta  **bort princip**.

3. Välj Ja i dialogrutan **Varning.**

> [!NOTE]
> Mer information om hur du tar bort blockering av enheter om organisationens enheter fortfarande är blockerade finns i blogginlägget Ta bort åtkomstkontroll [från Mobile Device Management för Office 365](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934).
