---
title: Konfigurera en anslutare för att arkivera Twitter-data
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
description: Lär dig hur administratörer kan konfigurera och använda en inbyggd anslutning för att importera Twitter-data till Microsoft 365.
ms.openlocfilehash: 277af8ea7367936c4c9528a8ca50ccd678745bf6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162138"
---
# <a name="set-up-a-connector-to-archive-twitter-data-preview"></a>Konfigurera en anslutare för att arkivera Twitter-data (förhandsversion)

Använd en anslutare i Microsoft 365 för att importera och arkivera data från Twitter till Microsoft 365. När du har konfigurerat och konfigurerat anslutningen ansluts den till organisationens Twitter-konto (enligt schema), konverterar innehållet i ett objekt till ett e-postmeddelandeformat och importerar sedan objekten till en postlåda i Microsoft 365.

När Twitter-data har importerats kan du tillämpa Microsoft 365-efterlevnadsfunktioner som Bevarande av juridiska skäl, Innehållssökning, In-Place Arkivering, Granskning och Microsoft 365 bevarandeprinciper på Twitter-data. Om en postlåda till exempel sätts i bevarande av juridiska skäl eller tilldelas en bevarandeprincip bevaras Twitter-data. Du kan söka efter data från tredje part med hjälp av Innehållssökning eller associera postlådan där Twitter-data lagras med en vårdnadshavare i ett Advanced eDiscovery fall. Om du använder en anslutare för att importera och arkivera Twitter-data i Microsoft 365 kan hjälpa din organisation att följa myndighets- och regelpolicyer.

När Twitter-data har importerats kan du tillämpa efterlevnadsfunktioner i Microsoft 365, till exempel Bevarande av juridiska skäl, Innehållssökning, In-Place Arkivering, Granskning, Kommunikationsefterlevnad och Microsoft 365-bevarandeprinciper på de data som lagras i postlådan. Du kan till exempel söka efter Twitter-data med hjälp av Innehållssökning eller associera postlådan där data lagras med en vårdnadshavare i ett Advanced eDiscovery fall. Om du använder en anslutare för att importera och arkivera Twitter-data i Microsoft 365 kan hjälpa din organisation att följa myndighets- och regelpolicyer.

## <a name="before-you-set-up-a-connector"></a>Innan du skapa en koppling

Gör följande innan du kan konfigurera och konfigurera en anslutning i efterlevnadscentret för Microsoft 365 för att importera och arkivera data från din organisations Twitter-konto.

- Du behöver ett Twitter-konto för din organisation. måste du logga in på det här kontot när du inställningar för anslutningen.

- Din organisation måste ha en giltig Azure-prenumeration. Om du inte har en befintlig Azure-prenumeration kan du registrera dig för något av följande alternativ:

    - [Registrera dig för en kostnadsfri Azure-prenumeration på ett år](https://azure.microsoft.com/free) 

    - [Registrera dig för en Azure-prenumeration med betalning efter användning](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > Den [kostnadsfria Azure Active Directory-prenumeration](use-your-free-azure-ad-subscription-in-office-365.md) som ingår i Microsoft 365-prenumerationen har inte stöd för anslutningarna i Säkerhets- & efterlevnadscenter.

- Med Twitter-anslutningen kan totalt 200 000 objekt importeras under en och samma dag. Om det finns fler än 200 000 Twitter-objekt på ett dygn importeras inga av dessa objekt till Microsoft 365.

- Den användare som uppsättningar av Twitter-anslutningen i efterlevnadscentret för Microsoft 365 (i steg 5) måste tilldelas rollen Importera och exportera postlåda i Exchange Online. Som standard är den här rollen inte tilldelad någon rollgrupp i Exchange Online. Du kan lägga till rollen Importera och exportera postlåda i rollgruppen Organisationshantering i Exchange Online. Du kan också skapa en rollgrupp, tilldela rollen Importera och exportera postlåda och sedan lägga till lämpliga användare som medlemmar. Mer information finns i avsnitten [Skapa rollgrupper](/Exchange/permissions-exo/role-groups#create-role-groups) och [Ändra rollgrupper](/Exchange/permissions-exo/role-groups#modify-role-groups) i artikeln "Hantera rollgrupper i Exchange Online".

## <a name="step-1-create-an-app-in-azure-active-directory"></a>Steg 1: Skapa en app i Azure Active Directory

Det första steget är att registrera ett nytt program i Azure Active Directory (AAD). Det här programmet motsvarar webbappresursen som du implementerade i steg 2 för Twitter-anslutningen.

Stegvisa instruktioner finns i Skapa [en app i Azure Active Directory](deploy-twitter-connector.md#step-1-create-an-app-in-azure-active-directory).

När det här steget är slutfört (genom att följa de stegvisa instruktionerna) sparar du följande information i en textfil. Dessa värden används i senare steg i distributionsprocessen.

- AAD-program-ID

- AAD-programhemlighet

- Klientorganisations-ID

## <a name="step-2-deploy-connector-web-service-from-github-repository-to-your-azure-account"></a>Steg 2: Distribuera anslutarwebbtjänsten från GitHub till Azure-kontot

Nästa steg är att distribuera källkoden för Twitter-anslutningsappen som använder Twitter API för att ansluta till ditt Twitter-konto och extrahera data så att du kan importera dem till Microsoft 365. Den Twitter-anslutning som du distribuerar för organisationen laddar upp objekten från organisationens Twitter-konto till den Azure Storage som skapas i det här steget. När du har skapat en Twitter-anslutning i efterlevnadscentret för Microsoft 365 (i steg 5) kopierar tjänsten Microsoft 365-import Twitter-data från Azure Storage-platsen till en postlåda i Microsoft 365. Som beskrivs ovan i avsnittet [Innan du konfigurerar en koppling](#before-you-set-up-a-connector) måste du ha en giltig Azure-prenumeration för att skapa ett Azure Storage konto.

Så här distribuerar du källkoden för Twitter-anslutningsappen:

1. Gå till [den GitHub webbplatsen](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet).

2. Klicka **på Distribuera till Azure.**

Stegvisa instruktioner finns i Distribuera [anslutarwebbtjänsten från e GitHub till ditt Azure-konto.](deploy-twitter-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account)

När du följer de stegvisa anvisningarna för att slutföra det här steget anger du följande information

- APISecretKey: Du skapar den här hemligheten när det här steget slutförs. Det används i steg 5.

- tenantId: Klientorganisations-ID för Microsoft 365 organisationen som du kopierade när du har skapat Twitter-appen i Azure Active Directory steg 1.

När du har slutfört det här steget måste du kopiera programmets tjänst-URL (till `https://twitterconnector.azurewebsites.net` exempel). Du måste använda URL-adressen för att slutföra steg 3, steg 4 och steg 5).

## <a name="step-3-create-developer-app-on-twitter"></a>Steg 3: Skapa utvecklarappen på Twitter

Nästa steg är att skapa och konfigurera en utvecklarapp på Twitter. Den anpassade anslutningen som du skapar i steg 7 använder Twitter-appen för att interagera med Twitter API:t för att hämta data från organisationens Twitter-konto.

Stegvisa instruktioner finns i Skapa [Twitter-appen.](deploy-twitter-connector.md#step-3-create-the-twitter-app)

När det här steget är slutfört (genom att följa de stegvisa anvisningarna) sparar du följande information i en textfil. Dessa värden används för att konfigurera Appen Twitter-anslutning i steg 4.

- Api-nyckel för Twitter

- Twitter API-hemlig nyckel

- Twitter-åtkomsttoken

- Twitter Access Token Secret

## <a name="step-4-configure-the-twitter-connector-app"></a>Steg 4: Konfigurera appen Twitter-anslutning

Nästa steg är att lägga till konfigurationsinställningar i Twitter-anslutningsappen som du distribuerade i steg 2. Det gör du genom att gå till startsidan för kopplingsappen och konfigurera den.

Stegvisa instruktioner finns i Konfigurera [webbprogrammet för anslutning.](deploy-twitter-connector.md#step-4-configure-the-connector-web-app)

När det här steget är slutfört (genom att följa de stegvisa instruktionerna) anger du följande information (som du har kopierat till en textfil när du har slutfört föregående steg):

- Twitter API-nyckel (erhållen i steg 3)

- Twitter API-hemlig nyckel (erhållen i steg 3)

- Twitter-åtkomsttoken (erhållen i steg 3)

- Twitter Access Token Secret (erhållen i steg 3)

- Azure Active Directory program-ID (AAD-program-ID: t som hämtas i steg 1)

- Azure Active Directory programhemlighet (AAD-programhemligheten som erhålls i steg 1)

## <a name="step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center"></a>Steg 5: Konfigurera en Twitter-anslutning i Microsoft 365 för efterlevnadscenter

Det sista steget är att konfigurera Twitter-anslutningen i efterlevnadscentret för Microsoft 365 som importerar data från organisationens Twitter-konto till en viss postlåda i Microsoft 365. När du har slutfört det här steget Microsoft 365 importtjänsten börjar importera data från organisationens Twitter-konto till Microsoft 365.

Stegvisa anvisningar finns i Konfigurera en [Twitter-anslutning i Microsoft 365 efterlevnadscenter.](deploy-twitter-connector.md#step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center) 

När det här steget är slutfört (genom att följa de stegvisa instruktionerna) anger du följande information (som du har kopierat till en textfil när du har slutfört stegen).

- Azure-apptjänst-URL (erhållen i steg 2, till exempel `https://twitterconnector.azurewebsites.net` )

- APISecretKey (som du skapade i steg 2)