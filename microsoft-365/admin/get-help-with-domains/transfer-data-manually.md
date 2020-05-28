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
description: Ta reda på hur du överför data manuellt mellan två Microsoft 365-konton när du ändrade planen eller företagsnamnet, eller kombinerade flera prenumerationer till ett.
ms.openlocfilehash: 69476687915024accabdce2a603ebdd7e8b653af
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399878"
---
# <a name="transfer-data-manually-between-two-accounts"></a>Överföra data manuellt mellan två konton

Förbered dig på att kavla upp ärmarna och blockera en bit av tiden i kalendern: att överföra data mellan två Microsoft 365-konton är en manuell, komplicerad och tidskrävande process. Detta är inte en automatiserad eller understödd process. Vi hjälper dig komma igång
  
> [!CAUTION]
> Det kommer att finnas en nere tid under processen där e-post, Skype för företag och en offentlig webbplats som finns på Microsoft 365 inte fungerar. Användare kommer att få nya användarnamn och lösenord och de kommer att behöva återställa Outlook.

**Använd bara instruktionerna i detta ämne för manuell överföring av data om något av följande gäller:**
  
- Du måste byta till ett abonnemang i en annan tjänstefamilj.

- Företaget bytte namn och du beslutade att skapa ett nytt abonnemang och migrera dina data eftersom du vill använda olika inledande domännamn.

- Du behöver kombinera flera abonnemang i ett nytt abonnemang.

> [!IMPORTANT]
> Om du behöver [ändra ditt abonnemang](../../commerce/subscriptions/switch-to-a-different-plan.md) och kan använda guiden för byte av abonnemang eller om du behöver byta till ett nytt abonnemang i samma abonnemangsfamilj, även när guiden för byte av abonnemang inte fungerar, behöver du inte överföra data manuellt och ingen nedtid krävs.

|**Uppgifter**|**Steg**|
|:-----|:-----|
|Köp det alternativ du vill byta till.  <br/> |När du registrerar kontot anger du företagsnamnet som ska användas i de inledande domännamnen:  *dittföretag*  .onmicrosoft.com,  *dittföretag*  -public.sharepoint.com, and  *dittföretag*  .sharepoint.com. Du måste använda ett annat namn för  *dittföretag*  än du använder för eventuella befintliga abonnemang.  <br/> > [!NOTE]>  Det tar normalt minst flera månader efter att du avbryter ett abonnemang att ta bort de inledande domännamnen som använder  *dittföretag*  från våra system. Även om du planerar att spara alla data från din gamla Microsoft 365-prenumeration och avbryta prenumerationen är det gamla *ditt företag* inte omedelbart tillgängligt för användning i en ny prenumeration.           |
|Ta bort din anpassade domän från din gamla Microsoft 365-prenumeration.  <br/> | Följ [steg som krävs innan en domän tas bort](remove-a-domain.md) för att ta bort domännamnet från användares e-postadresser och ta bort DNS-poster för e-post och Lync för den anpassade domänen. Om du är värd för din offentliga webbplats på Microsoft 365 måste du också ta bort CNAME-posten som pekar på den.  <br/> > [!IMPORTANT]>  När du tagit bort den MX-post som dirigerar e-post till denna anpassade domän, kommer e-post att sluta fungera tills du lagt till domänen i ditt nya konto, konfigurerat den nya MX-posten och konfigurerat dina användare. När du tar bort DNS-posterna för Lync, kommer Lync att sluta fungera. När du tar bort CNAME-posten som pekar på din offentliga webbserver, kommer den inte att vara tillgänglig.           [Ta bort domänen](remove-a-domain.md) .  <br/> |
|Konfigurera din anpassade domän för det nya abonnemanget och konfigurera dina användare.  <br/> | Konfigurera ditt nya abonnemang, inklusive de DNS-poster som krävs för din anpassade domän.  <br/>  Skapa dina användare, med e-postadresser, på din anpassade domän.  <br/> |
|Överför data från ditt gamla abonnemang till ditt nya abonnemang.  <br/> | Logga in till båda kontona i separata webbläsarfönster:  <br/>  Högerklicka på Internet Explorer-ikonen och öppna två InPrivate-fönster. Du kan använda olika inloggningsuppgifter i de två fönstren för att logga in på båda kontona.  <br/> [Överföra administrativa inställningar mellan abonnemang](#email) <br/> [Överföra struktur och data för gruppwebbplats](#transfer-team-site-structure-and-data) <br/> [Överföra en offentlig webbplats mellan abonnemang](#transfer-a-public-website-between-subscriptions) <br/> [Överföra administrativa inställningar mellan abonnemang](#email) <br/> |
|Avbryt prenumerationen för det abonnemang du har gjort med genom att ringa Microsoft Support för Microsoft 365.  <br/> | Kontrollera att ditt nya abonnemang fungerar och att alla data har överförts.  <br/>  [Kontakta kundtjänst](../contact-support-for-business-products.md) för att avbryta din gamla prenumeration.  <br/> |

## <a name="transfer-administrative-settings-between-subscriptions"></a>Överföra administrativa inställningar mellan abonnemang

Gå till följande sidor i varje konto och konfigurera det nya kontot baserat på inställningarna i det gamla kontot.
  
Om du överför data från Microsoft 365 till Microsoft 365 Midsize Business eller Microsoft 365 Enterprise är administratörssidorna strukturerade på olika sätt. Titta på en [video: Introduktion till Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365/admin/)och gå till följande platser för att titta på administratörsinställningar.
  
För Microsoft 365 Enterprise och Microsoft 365 Midsize Business:
  
|**Plats**|**Ändamål**|
|:-----|:-----|
|**Admin (admin)** \> **Microsoft 365** \> **Tjänstinställningar** <br/> |Välj varje flik för inställningar för e-post, webbplatser, Lync, användarprogramvara, lösenord, community, rättighetshantering och mobil.  <br/> |
|**Admin** \> **Exchange** <br/> | Exchange Online-inställningar  <br/> |
|**Admin** \> **SharePoint** <br/> | SharePoint Online-inställningar  <br/> |
|**Admin (admin)** \> **Skype för företag** <br/> |Ytterligare Skype för företag-inställningar  <br/> |

För Microsoft 365 Small Business
  
|**Plats**|**Ändamål**|
|:-----|:-----|
|**Admin** \> **Hantera företagsomfattande inställningar** <br/> |Administrativa inställningar  <br/> |

## <a name="transfer-a-public-website-between-subscriptions"></a>Överföra en offentlig webbplats mellan abonnemang

Om du har en offentlig webbplats på Microsoft 365 måste du spara den och återskapa den på din nya prenumeration.
  
> [!NOTE]
> Om din offentliga webbplats ligger på en extern DNS-leverantör, behövs du inte ändra något. Den kommer inte att påverkas av din övergång.
  
Om du vill spara ett dokumentbibliotek eller listinnehåll från en SharePoint Online-miljö på filresurser eller på en lokal dator kan du läsa mer i artikeln om [manuell migrering av SharePoint Online-innehåll](https://go.microsoft.com/fwlink/p/?LinkId=402910).
  
> [!NOTE]
> Appen för migrering av offentlig webbplats kan inte överföra data till ett annat abonnemang.
  
## <a name="transfer-team-site-structure-and-data"></a>Överföra struktur och data för gruppwebbplats

Det finns flera sätt att spara eller överföra data för en gruppwebbplats:
  
- Du kan spara den gamla webbplatsen som en mall och importera mallen i den nya webbplatsen.

- Om du vill överföra dokument återskapar du först hierarkin manuellt på den nya platsen. Sedan kan du öppna båda SharePoint-gruppwebbplatserna samtidigt, öppna båda dokumentbiblioteken med Utforskaren och kopiera och klistra in dokumenten. Se [video: Kopiera eller flytta biblioteksfiler med hjälp av Öppna med Utforskaren](https://support.office.com/article/where-to-store-files-c7c20284-bc94-47f4-9728-d28e9daf0790).

- För att överföra listdata sparar du en [listmall](https://support.microsoft.com/en-us/office/manage-list-templates-c3884ad1-bc49-44b8-b3d6-3bc6a01eb393) och använder den sparade mallen för att återskapa listan på den nya webbplatsen.

- Information [om manuell migrering av SharePoint Online-innehåll finns i Information om manuell migrering av SharePoint Online-innehåll](https://support.microsoft.com/kb/2783484).

## <a name="transfer-users-data-between-subscriptions"></a>Överföra användarnas data mellan abonnemang

### <a name="email"></a>Email:

Be användare [flytta sin e-post, sina kontakter, uppgifter och kalenderinformation](https://support.office.com/article/0996ece3-57c6-49bc-977b-0d1892e2aacc.aspx) när du konfigurerat det nya abonnemanget. De kan komma åt sin gamla e-post genom att använda sitt ursprungliga användarnamn, som sue@contoso.onmicrosoft.com.
  
### <a name="onedrive-for-business-data"></a>OneDrive för företag-data:

Be användarna kopiera/synkronisera [OneDrive för företag-innehåll på sin dator](https://support.office.com/article/59b1de2b-519e-4d3a-8f45-51647cf291cd.aspx)och sedan lägga till det i sin nya prenumeration.
