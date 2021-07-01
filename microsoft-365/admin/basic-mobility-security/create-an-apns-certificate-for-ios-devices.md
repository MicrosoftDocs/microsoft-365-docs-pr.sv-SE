---
title: Skapa ett APN-certifikat för iOS-enheter
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
description: Hantera iOS-enheter i Basic Mobility and Security.
ms.openlocfilehash: 84f3589593ef26325397f5b6e90d5b21662d2352
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228249"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a>Skapa ett APN-certifikat för iOS-enheter

Skapa ett APNs-certifikat för att hantera iOS-enheter som iPad och iPhone i Basic Mobility and Security.

1. Logga in på Microsoft 365 ditt globala administratörskonto.

2. I webbläsaren skriver du  <https://protection.office.com/> .

3. Välj  **Dataförlustskydd**   >  **Enhetshantering och** välj **APNs-certifikat för iOS-enheter.**

4. På sidan Apple Push Notification Certificate Inställningar väljer du **Next**.

5. Välj Ladda ned din CSR-fil och spara begäran om certifikatsignering någonstans på datorn som är så bra att du kommer ihåg den. Välj  **Nästa.**

6. På sidan Skapa ett APNs-certifikat:

    1. Välj Apple APNS-portalen för att öppna Apple Push Certificates-portalen.

    2. Logga in med ett Apple-ID.

       > [!IMPORTANT]
       > Använd ett företags-Apple-ID som är kopplat till ett e-postkonto som kommer att finnas kvar i din organisation även om användaren som hanterar kontot slutar. Spara detta ID eftersom du måste använda samma ID när det är dags att förnya certifikatet.

    3. Välj  **Skapa ett** certifikat och godkänn   användningsvillkoren.

    4. Bläddra till den begäran om certifikatsignering som du laddade ned till datorn Microsoft 365 och välj **Upload**.

       Ladda ned det APNs-certifikat som skapades av Apple Push Certificate-portalen till din dator.

       > [!TIP]
       > Om du har problem med att ladda ned certifikatet kan du uppdatera webbläsaren.

7. Gå tillbaka till Microsoft 365 och välj **Nästa för** att komma till sidan   Upload   **APNS-certifikat.**  

8. Bläddra till det APN-certifikat som du laddade ned från Apple Push Certificates-portalen.

9. Välj  **Slutför**.

Slutför konfigurationen genom att gå tillbaka till Säkerhets- & Säkerhets- och > **Säkerhetsprinciper**   >  **Hantera**   >  **inställningar.**
