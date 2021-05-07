---
title: Konfigurera en koppling för att arkivera Facebook-data
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: seo-marvel-apr2020
description: Ta reda på hur du & använder en koppling i kompatibilitetscentret för Microsoft 365 för att importera och & från Facebook Business-sidor till Microsoft 365.
ms.openlocfilehash: 616466a3af83c1558184526aa463f68c10ef9e70
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162130"
---
# <a name="set-up-a-connector-to-archive-facebook-data-preview"></a>Konfigurera en koppling för att arkivera Facebook-data (förhandsgranskning)

Använd en koppling i kompatibilitetscentret Microsoft 365 för att importera och arkivera data från Facebook Business-sidor och Microsoft 365. När du har konfigurerat och konfigurerat anslutningen ansluter den till Facebook Business-sidan (enligt schema), konverterar innehållet i Facebook-objekt till ett e-postmeddelandeformat och importerar sedan objekten till en postlåda i Microsoft 365.

När Facebook-data har importerats kan du tillämpa efterlevnadsfunktioner i Microsoft 365, till exempel Bevarande av juridiska skäl, Innehållssökning, In-Place Arkivering, Granskning, Kommunikationsefterlevnad och Microsoft 365 bevarandeprinciper på Facebook-data. Om en postlåda till exempel sätts i bevarande av juridiska skäl eller tilldelas en bevarandeprincip, bevaras Facebook-data. Du kan söka efter data från tredje part med hjälp av innehållssökning eller associera postlådan där Facebook-data lagras med en vårdnadshavare i ett Advanced eDiscovery fall. Om du använder en anslutare för att importera och arkivera Facebook-data i Microsoft 365 kan hjälpa din organisation att följa myndighets- och regelpolicyn.

## <a name="prerequisites-for-setting-up-a-connector-for-facebook-business-pages"></a>Förutsättningar för att konfigurera en anslutning för Facebook Business-sidor

Gör följande innan du kan konfigurera och konfigurera en koppling i kompatibilitetscentret för Microsoft 365 för att importera och arkivera data från organisationens Facebook Business-sidor. 

- Du behöver ett Facebook-konto för din organisations företagssidor (du måste logga in på det här kontot när du tecknar anslutningen). För närvarande kan du bara arkivera data från Facebook Business-sidor. du kan inte arkivera data från enskilda Facebook-profiler.

- Din organisation måste ha en giltig Azure-prenumeration. Om du inte har en befintlig Azure-prenumeration kan du registrera dig för något av följande alternativ:

    - [Registrera dig för en kostnadsfri Azure-prenumeration på ett år](https://azure.microsoft.com/free)

    - [Registrera dig för en Azure-prenumeration med betalning efter användning](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > Den [kostnadsfria Azure Active Directory-prenumeration](use-your-free-azure-ad-subscription-in-office-365.md) som ingår i Microsoft 365-prenumerationen har inte stöd för anslutningarna i Säkerhets- & efterlevnadscenter.

- Via kopplingen för Facebook Business-sidor kan totalt 200 000 objekt importeras på en och samma dag. Om det finns fler än 200 000 Facebook-affärsobjekt på ett dygn importeras inga av dessa objekt till Microsoft 365.

- Den användare som uppsättningar den anpassade kopplingen i Microsoft 365 efterlevnadscenter (i steg 5) måste tilldelas rollen Importera och exportera postlåda i Exchange Online. Som standard är den här rollen inte tilldelad någon rollgrupp i Exchange Online. Du kan lägga till rollen Importera och exportera postlåda i rollgruppen Organisationshantering i Exchange Online. Du kan också skapa en rollgrupp, tilldela rollen Importera och exportera postlåda och sedan lägga till lämpliga användare som medlemmar. Mer information finns i avsnitten [Skapa rollgrupper](/Exchange/permissions-exo/role-groups#create-role-groups) och [Ändra rollgrupper](/Exchange/permissions-exo/role-groups#modify-role-groups) i artikeln "Hantera rollgrupper i Exchange Online".

## <a name="step-1-create-an-app-in-azure-active-directory"></a>Steg 1: Skapa en app i Azure Active Directory

Det första steget är att registrera ett nytt program i Azure Active Directory (AAD). Det här programmet motsvarar webbappresursen som du implementerade i steg 4 och steg 5 för Facebook-kopplingen. 

Stegvisa instruktioner finns i Skapa [en app i Azure Active Directory](deploy-facebook-connector.md#step-1-create-an-app-in-azure-active-directory).

När det här steget är slutfört (genom att använda föregående steg-för-steg-instruktioner) sparar du följande information i en textfil. Dessa värden används i senare steg i distributionsprocessen.

- AAD-program-ID

- AAD-programhemlighet

- Klientorganisations-ID

## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a>Steg 2: Distribuera anslutarwebbtjänsten från GitHub till ditt Azure-konto

Nästa steg är att distribuera källkoden för kopplingsappen för Facebook Business-sidor som använder Facebook-API:t för att ansluta till ditt Facebook-konto och extrahera data så att du kan importera dem till Microsoft 365. Den Facebook-koppling som du distribuerar för din organisation laddar upp objekt från dina Facebook Business-sidor till den Azure Storage som skapas i det här steget. När du har skapat en anslutning för Facebook-företagssidor i efterlevnadscentret för Microsoft 365 (i steg 5) kopierar importtjänsten Facebooks affärssidors data från Azure Storage-platsen till en postlåda i Microsoft 365 organisation. Som tidigare förklarats i [avsnittet Förutsättningarna](#prerequisites-for-setting-up-a-connector-for-facebook-business-pages) måste du ha en giltig Azure-prenumeration för att skapa ett Azure Storage konto.

Stegvisa instruktioner finns i Distribuera [anslutarwebbtjänsten från e GitHub till ditt Azure-konto.](deploy-facebook-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account)

I de stegvisa instruktionerna för att slutföra det här steget anger du följande information:

- APISecretKey: Du skapar den här hemligheten när det här steget slutförs. Det används i steg 5.

- TenantId: Klientorganisations-ID för Microsoft 365 organisation som du kopierade när du skapade Facebook-anslutningsappen i Azure Active Directory steg 1.

När du har slutfört det här steget måste du kopiera URL-adressen för Azure-appens tjänst (till exempel https://fbconnector.azurewebsites.net) . Du måste använda URL-adressen för att slutföra steg 3, steg 4 och steg 5).

## <a name="step-3-register-the-web-app-on-facebook"></a>Steg 3: Registrera webbappen på Facebook

Nästa steg är att skapa och konfigurera en ny app på Facebook. Kopplingen för Facebook-företagssidor som du skapar i steg 5 använder Facebook-webbappen för att interagera med Facebook-API:t för att hämta data från organisationens Facebook-företagssidor.

Stegvisa instruktioner finns i Registrera [Facebook-appen.](deploy-facebook-connector.md#step-3-register-the-facebook-app)

När det här steget är slutfört (genom att följa de stegvisa anvisningarna) sparar du följande information i en textfil. Dessa värden används för att konfigurera Appen Facebook-anslutning i steg 4.

- Facebook-program-ID

- Programhemlighet på Facebook

- Facebook Webhooks verifiera token

## <a name="step-4-configure-the-facebook-connector-app"></a>Steg 4: Konfigurera appen Facebook-anslutning

Nästa steg är att lägga till konfigurationsinställningar i Facebook-kopplingsappen som du laddade upp när du skapade Azure Web App-resursen i steg 1. Det gör du genom att gå till startsidan för kopplingsappen och konfigurera den.

Stegvisa instruktioner finns i Konfigurera [Facebook-kopplingsappen.](archive-facebook-data-with-sample-connector.md#step-4-configure-the-facebook-connector-app)

När det här steget är slutfört (genom att följa de stegvisa instruktionerna) anger du följande information (som du har kopierat till en textfil när du har slutfört föregående steg):

- Facebook-program-ID (hämtas i steg 3)

- Facebook-programhemlighet (erhållen i steg 3)

- Facebook webhooks verifiera token (hämtas i steg 3)

- Azure Active Directory program-ID (AAD-program-ID: t som hämtas i steg 1)

- Azure Active Directory programhemlighet (AAD-programhemligheten som erhålls i steg 1)

## <a name="step-5-set-up-a-facebook-business-pages-connector-in-the-microsoft-365-compliance-center"></a>Steg 5: Konfigurera en anslutning för Facebook Business-sidor Microsoft 365 efterlevnadscenter

Det sista steget är att konfigurera anslutningen i kompatibilitetscentret för Microsoft 365 som importerar data från Dina Facebook Business-sidor till en viss postlåda i Microsoft 365. När du är klar med det här steget Microsoft 365 importtjänsten att importera data från dina Facebook Business-sidor till Microsoft 365.

Stegvisa instruktioner finns i Steg [5: Konfigurera en Facebook-anslutning i Microsoft 365 efterlevnadscenter.](deploy-facebook-connector.md#step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center) 

När det här steget är slutfört (genom att följa de stegvisa instruktionerna) anger du följande information (som du har kopierat till en textfil när du har slutfört stegen).

- AAD-program-ID (hämtas i steg 1)

- Azure-apptjänst-URL (erhållen i steg 1, till exempel https://fbconnector.azurewebsites.net)

- APISecretKey (som du skapade i steg 2)