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
description: Hantera iOS-enheter i grundläggande mobilitet och säkerhet.
ms.openlocfilehash: 8b41c1c6c891a5d6cb98a6a381c65aa0310a1761
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/02/2020
ms.locfileid: "47337137"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a>Skapa ett APN-certifikat för iOS-enheter

Skapa ett APN-certifikat för att hantera iOS-enheter som iPad och iPhone i grundläggande mobilitet och säkerhet.

1. Logga in på Microsoft 365 med ditt globala administratörs konto.
    
2. Skriv i webbläsaren  [https://protection.office.com](https://protection.office.com/) .
    
3. Välj  **Hantera data förlust**   >  **Device management**och välj **APNs-certifikat för iOS-enheter**.    

4. På sidan Inställningar för Apple Push Notification-certifikat väljer du **Nästa**.
    
5. Välj Ladda ned din CSR-fil och spara begäran om certifikat signering någonstans på din dator som du kommer ihåg. Välj  **Nästa**.
    
6. På sidan Skapa ett APN-certifikat:  

    1. Välj Apple-APN-portalen för att öppna Apple Push certificates-portalen.
    
    2. Logga in med ett Apple-ID.   

    >[!IMPORTANT]
    >Använd ett Apple-ID för företag som är kopplat till ett e-postkonto som kommer att fortsätta med din organisation även om den användare som hanterar kontot lämnar. Spara detta ID eftersom du måste använda samma ID när det är dags att förnya certifikatet.

    3. Välj  **skapa ett certifikat**   och godkänn användnings villkoren.
    
    4. Bläddra till den begäran om certifikat signering som du hämtade till datorn från Microsoft 365 och välj **Ladda upp**.
    
        Ladda ned APN-certifikatet som skapades av Apple Push Certificate-portalen till datorn.
    
       >[!TIP]
       >Om du har problem med att ladda ner certifikatet kan du uppdatera webbläsaren.

7. Gå tillbaka till Microsoft 365 och välj **Nästa**   för att gå till sidan  **upload Certification**   .
    
8. Bläddra till det APN-certifikat som du laddade ned från Apple Push certificates-portalen.
    
9. Välj  **Slutför**.
    
För att slutföra installationen går du tillbaka till säkerhets & Compliance Center > **Security policies**   >  **Device management**   >  **Hantera inställningar**för hantering av säkerhets principer.
