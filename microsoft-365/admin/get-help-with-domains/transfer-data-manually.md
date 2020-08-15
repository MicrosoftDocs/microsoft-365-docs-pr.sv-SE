---
title: Överföra data manuellt mellan två konton
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ms.assetid: 7dc5d983-84b2-4802-bef0-602ae1780a42
description: Få reda på hur du överför data manuellt mellan två Microsoft 365-konton när du ändrade plan-eller företags namnet eller kombinerar flera abonnemang till ett.
ms.openlocfilehash: 91ea4140f0460e1f8cc1243f1b5f203738dcc9ee
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685516"
---
# <a name="transfer-data-manually-between-two-accounts"></a>Överföra data manuellt mellan två konton

Förbereda för att lyfta upp dina höljen och blockera en lång tid i kalendern: att överföra data mellan två Microsoft 365-konton är en manuell, komplicerad och tids krävande process. Detta är inte en automatiserad eller understödd process. Vi hjälper dig komma igång
  
> [!CAUTION]
> Det kommer att vara nere tid under processen där e-post, Skype för företag och en offentlig webbplats som hanteras av Microsoft 365 inte fungerar. Användare kommer att få nya användarnamn och lösenord och de kommer att behöva återställa Outlook.

**Använd bara instruktionerna i detta ämne för manuell överföring av data om något av följande gäller:**
  
- Du måste byta till ett abonnemang i en annan tjänstefamilj.

- Företaget bytte namn och du beslutade att skapa ett nytt abonnemang och migrera dina data eftersom du vill använda olika inledande domännamn.

- Du behöver kombinera flera abonnemang i ett nytt abonnemang.

> [!IMPORTANT]
> Om du behöver [ändra ditt abonnemang](../../commerce/subscriptions/switch-to-a-different-plan.md) och kan använda guiden för byte av abonnemang eller om du behöver byta till ett nytt abonnemang i samma abonnemangsfamilj, även när guiden för byte av abonnemang inte fungerar, behöver du inte överföra data manuellt och ingen nedtid krävs.

|**Uppgifter**|**Steg**|
|:-----|:-----|
|Köp det alternativ du vill byta till.  <br/> |När du registrerar kontot anger du företagsnamnet som ska användas i de inledande domännamnen:  *dittföretag*  .onmicrosoft.com,  *dittföretag*  -public.sharepoint.com, and  *dittföretag*  .sharepoint.com. Du måste använda ett annat namn för  *dittföretag*  än du använder för eventuella befintliga abonnemang.  <br/> > [!NOTE]>  Det tar normalt minst flera månader efter att du avbryter ett abonnemang att ta bort de inledande domännamnen som använder  *dittföretag*  från våra system. Även om du planerar att spara alla data från din gamla Microsoft 365-prenumeration och sedan avbryta prenumerationen är det gamla  *dittföretag*  -värdet inte omedelbart tillgängligt för att användas i ett nytt abonnemang.           |
|Ta bort din anpassade domän från din gamla Microsoft 365-prenumeration.  <br/> | Följ [steg som krävs innan en domän tas bort](remove-a-domain.md) för att ta bort domännamnet från användares e-postadresser och ta bort DNS-poster för e-post och Lync för den anpassade domänen. Om du är värd för din offentliga webbplats på Microsoft 365 måste du även ta bort den CNAME-post som pekar på den.  <br/> > [!IMPORTANT]>  När du tagit bort den MX-post som dirigerar e-post till denna anpassade domän, kommer e-post att sluta fungera tills du lagt till domänen i ditt nya konto, konfigurerat den nya MX-posten och konfigurerat dina användare. När du tar bort DNS-posterna för Lync, kommer Lync att sluta fungera. När du tar bort CNAME-posten som pekar på din offentliga webbserver, kommer den inte att vara tillgänglig.           [Ta bort domänen](remove-a-domain.md) .  <br/> |
|Konfigurera din anpassade domän för det nya abonnemanget och konfigurera dina användare.  <br/> | Konfigurera ditt nya abonnemang, inklusive de DNS-poster som krävs för din anpassade domän.  <br/>  Skapa dina användare, med e-postadresser, på din anpassade domän.  <br/> |
|Överför data från ditt gamla abonnemang till ditt nya abonnemang.  <br/> | Logga in till båda kontona i separata webbläsarfönster:  <br/>  Högerklicka på din webbläsare och öppna två privata webbläsare. Du kan använda olika inloggningsuppgifter i de två fönstren för att logga in på båda kontona.  <br/> [Överföra administrativa inställningar mellan abonnemang](#email) <br/> [Överföra struktur och data för gruppwebbplats](#transfer-team-site-structure-and-data) <br/> [Överföra en offentlig webbplats mellan abonnemang](#transfer-a-public-website-between-subscriptions) <br/> [Överföra administrativa inställningar mellan abonnemang](#email) <br/> |
|Avbryt prenumerationen för det abonnemang du är klar med genom att ringa Microsoft Support för Microsoft 365.  <br/> | Kontrollera att ditt nya abonnemang fungerar och att alla data har överförts.  <br/>  [Kontakta kund tjänst](../contact-support-for-business-products.md) för att avbryta ditt gamla abonnemang.  <br/> |

## <a name="transfer-administrative-settings-between-subscriptions"></a>Överföra administrativa inställningar mellan abonnemang

Gå till följande sidor i varje konto och konfigurera det nya kontot baserat på inställningarna i det gamla kontot.
  
Om du överför data från Microsoft 365 till Microsoft 365 medel stora företag eller Microsoft 365 Enterprise struktureras administratörs sidorna på olika sätt. Titta på en [video: Introduktion till Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365/admin/)och gå till följande platser för att titta på administratörs inställningar.
  
För Microsoft 365 Enterprise och Microsoft 365 medel stora företag:
  
|**Plats**|**Ändamål**|
|:-----|:-----|
|**Administratör** \> **Microsoft 365** \> **Tjänst inställningar** <br/> |Välj varje flik för inställningar för e-post, webbplatser, Lync, användar program, lösen ord, community, rättighets hantering och mobil.  <br/> |
|**Admin** \> **Exchange** <br/> | Exchange Online-inställningar  <br/> |
|**Admin** \> **SharePoint** <br/> | SharePoint Online-inställningar  <br/> |
|**Administratör** \> **Skype för företag** <br/> |Ytterligare inställningar för Skype för företag  <br/> |

För Microsoft 365 Small Business
  
|**Plats**|**Ändamål**|
|:-----|:-----|
|**Admin** \> **Hantera företagsomfattande inställningar** <br/> |Administrativa inställningar  <br/> |

## <a name="transfer-a-public-website-between-subscriptions"></a>Överföra en offentlig webbplats mellan abonnemang

Om du har en offentlig webbplats som finns på Microsoft 365 måste du spara den och återskapa den på ditt nya abonnemang.
  
> [!NOTE]
> Om din offentliga webbplats ligger på en extern DNS-leverantör, behövs du inte ändra något. Den kommer inte att påverkas av din övergång.
  
Om du vill spara ett dokumentbibliotek eller listinnehåll från en SharePoint Online-miljö på filresurser eller på en lokal dator kan du läsa mer i artikeln om [manuell migrering av SharePoint Online-innehåll](https://go.microsoft.com/fwlink/p/?LinkId=402910).
  
> [!NOTE]
> Appen för migrering av offentlig webbplats kan inte överföra data till ett annat abonnemang.
  
## <a name="transfer-team-site-structure-and-data"></a>Överföra struktur och data för gruppwebbplats

Det finns flera sätt att spara eller överföra data för en gruppwebbplats:
  
- Du kan spara den gamla webbplatsen som en mall och importera mallen i den nya webbplatsen.

- För att överföra dokument måste du först återskapa din hierarki på den nya webbplatsen. Sedan kan du öppna båda SharePoint-gruppwebbplatserna samtidigt, öppna båda dokumentbiblioteken med Utforskaren och kopiera och klistra in dokumenten. Se [video: Kopiera eller flytta biblioteksfiler med hjälp av Öppna med Utforskaren](https://support.microsoft.com/office/c7c20284-bc94-47f4-9728-d28e9daf0790).

- För att överföra listdata sparar du en [listmall](https://support.microsoft.com/office/c3884ad1-bc49-44b8-b3d6-3bc6a01eb393) och använder den sparade mallen för att återskapa listan på den nya webbplatsen.

- Om du vill spara ett dokument bibliotek eller List innehåll från en SharePoint Online-miljö (OneDrive för företag eller grupp webbplatser) på fil resurser eller på en lokal dator kan du läsa [information om manuell migrering av SharePoint Online-innehåll](https://support.microsoft.com/kb/2783484).

## <a name="transfer-users-data-between-subscriptions"></a>Överföra användarnas data mellan abonnemang

### <a name="email"></a>E-

Be användare [flytta sin e-post, sina kontakter, uppgifter och kalenderinformation](https://support.microsoft.com/office/0996ece3-57c6-49bc-977b-0d1892e2aacc) när du konfigurerat det nya abonnemanget. De kan komma åt sin gamla e-post genom att använda sitt ursprungliga användarnamn, som sue@contoso.onmicrosoft.com.
  
### <a name="onedrive-for-business-data"></a>OneDrive för företag-data:

Be användare att kopiera eller synkronisera [OneDrive för företag-innehåll till sin dator](https://support.microsoft.com/office/59b1de2b-519e-4d3a-8f45-51647cf291cd)och sedan lägga till det igen i sitt nya abonnemang.
