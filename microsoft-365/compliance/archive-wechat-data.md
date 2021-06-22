---
title: Konfigurera en koppling för att arkivera WeChat-data i Microsoft 365
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
ms.collection: M365-security-compliance
description: Konfigurera och använda en koppling i Microsoft 365 Efterlevnadscenter importera och arkivera WeChat-data i Microsoft 365.
ms.openlocfilehash: e610b58421c2d84402010c9a5d5ad33ec6da5b04
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054618"
---
# <a name="set-up-a-connector-to-archive-wechat-data"></a>Konfigurera en koppling för att arkivera WeChat-data

Använd TeleMessage-kopplingen i Microsoft 365 Efterlevnadscenter för att importera och arkivera WeChat- och WeCom-samtal, chattar, bifogade filer och återkallade meddelanden. När du har konfigurerat och konfigurerat en anslutning ansluts den till din organisations TeleMessage-konto och importerar mobilkommunikationen för anställda som använder TeleMessage WeChat-arkivet till postlådor i Microsoft 365.

När WeChat-arkiveringskopplingsdata lagras i användarnas postlådor kan du använda efterlevnadsfunktioner i Microsoft 365, till exempel Bevarande av juridiska skäl, eDiscovery, In-Place Arkivering, Granskning, Kommunikationsefterlevnad och Microsoft 365-bevarandeprinciper på WeChat-kommunikationsdata. Du kan till exempel söka i WeChat-kommunikation med hjälp av Innehållssökning eller associera postlådan som innehåller WeChat-arkiveringskopplingsdata med en medarbetare i ett Advanced eDiscovery ärende. Med en WeChat-arkiveringskoppling kan du importera och arkivera data i Microsoft 365 för att hjälpa din organisation att följa företagsstyrningsföreskrifter och reglerande principer.

## <a name="overview-of-archiving-wechat-communication-data"></a>Översikt över arkivering av WeChat-kommunikationsdata

Följande översikt förklarar processen med att använda en anslutare för att arkivera WeChat-kommunikationsdata i Microsoft 365.

![Arkivering av arbetsflöde för WeChat-arkiveringsdata](../media/WeChatConnectorWorkflow.png)

1. Din organisation arbetar med TeleMessage för att konfigurera en WeChat-arkiveringskoppling.

2. I realtid kopieras din organisations WeChat-data till TeleMessage-webbplatsen.

3. Kopplingen till WeChat Archiver som du skapar i Microsoft 365 Efterlevnadscenter ansluter till TeleMessage-webbplatsen varje dag och överför e-postmeddelandena från de senaste 24 timmarna till ett säkert Azure Storage område i Microsoft Cloud.

4. Kopplingen importerar mobila kommunikationsobjekt till en viss användares postlåda. En ny mapp med namnet WeChat Archiver skapas i den specifika användarens postlåda och objekten importeras till den. Kopplingen mappar med hjälp av värdet för *användarens e-postadressegenskap.* Alla e-postmeddelanden innehåller den här egenskapen, som fylls i med e-postadresserna för alla deltagare i e-postmeddelandet. Förutom automatisk användarmappning med värdet  för användarens e-postadressegenskap kan du också definiera en anpassad mappning genom att ladda upp en CSV-mappningsfil. Den här mappningsfilen ska innehålla användarens mobilnummer och motsvarande e Microsoft 365 postlådeadress för varje användare. Om du aktiverar automatisk användarmappning och tillhandahåller en anpassad mappning kommer kopplingen först att titta på anpassad mappningsfil för varje e-postobjekt. Om anslutaren inte hittar en giltig Microsoft 365-användare som motsvarar en användares mobilnummer använder kopplingen användarens e-postadressegenskap för e-postobjektet. Om kopplingen inte hittar en giltig Microsoft 365-användare i antingen  den anpassade mappningsfilen eller användarens e-postadressegenskap för e-postobjektet, importeras inte objektet.

## <a name="before-you-set-up-a-connector"></a>Innan du skapa en koppling

- Arbeta med TeleMessage för att konfigurera en WeChat-arkivkoppling. Mer information finns i [Aktivera TeleMessage WeChat Archiver för Microsoft 365.](https://www.telemessage.com/microsoft-365-activation-for-wechat-archiver/)

- Konfigurera en TeleMessage-koppling för Microsoft 365 få ett giltigt företagsadministrationskonto. Mer information finns i [Ordna Microsoft 365 Mobil arkivering](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-microsoft-365/).

- Registrera alla användare som kräver WeChat-arkivering i TeleMessage-kontot med samma e-postadress som används för användarens Microsoft 365 konto.

- Du måste installera Tencent WeCom-appen på mobiltelefonen för användare i organisationen och aktivera den. Med WeCom-appen kan användare kommunicera och chatta med andra WeChat- och WeCom-användare.

- Den användare som skapar en WeChat-arkiveringskoppling i Microsoft 365 Efterlevnadscenter måste tilldelas rollen Importera och exportera postlåda i Exchange Online. Detta krävs för att lägga till kopplingar på sidan Datakopplingar i **efterlevnadscentret.** Som standard är den här rollen inte tilldelad någon rollgrupp i Exchange Online. Du kan lägga till rollen Importera och exportera postlåda i rollgruppen Organisationshantering i Exchange Online. Du kan också skapa en rollgrupp, tilldela rollen Importera och exportera postlåda och sedan lägga till lämpliga användare som medlemmar. Mer information finns i avsnitten [Skapa rollgrupper](/Exchange/permissions-exo/role-groups#create-role-groups) och [Ändra rollgrupper](/Exchange/permissions-exo/role-groups#modify-role-groups) i artikeln "Hantera rollgrupper i Exchange Online".

- Den här datakopplingen är tillgänglig GCC miljöer i Microsoft 365 för myndigheter i USA. Program och tjänster från tredje part kan innebära att lagra, överföra och bearbeta din organisations kunddata i tredje parts system som ligger utanför Microsoft 365-infrastrukturen och därför inte omfattas av Microsoft 365-åtaganden gällande efterlevnad och dataskydd. Microsoft anger inte att användningen av den här produkten för att ansluta till program från tredje part innebär att sådana program från tredje part är FEDRAMP-kompatibla.

## <a name="create-a-wechat-archiver-connector"></a>Skapa en WeChat-arkiveringskoppling

Följ stegen i det här avsnittet för att skapa en WeChat-arkiveringskoppling i Microsoft 365 Efterlevnadscenter. Kopplingen använder den information du uppger för att ansluta till TeleMessage-webbplatsen och överföra WeChat-kommunikationsdata till motsvarande användarpostlådor i Microsoft 365.

1. Gå till <https://compliance.microsoft.com> och klicka sedan på **Datakopplingar**  >  **WeChat Archiver**.

2. På **produktbeskrivningssidan i WeChat Archiver** klickar du på **Lägg till koppling**

3. Klicka på **Acceptera på** sidan **Användningsvillkor.**

4. På sidan **Logga in på TeleMessage,** under Steg 3, anger du den information som krävs i följande rutor och klickar sedan på **Nästa.**

    - **Användarnamn**: Ditt TeleMessage-användarnamn.

    - **Lösenord:** Ditt TeleMessage-lösenord.

5. När kopplingen har skapats kan du stänga popup-fönstret för att gå till nästa sida.

6. Aktivera automatisk **användarmappning** på sidan Användarmappning. Du kan också ladda upp en anpassad användarmappnings-CSV-fil.

7. Klicka **på** Nästa, granska dina inställningar och klicka sedan **på Slutför** för att skapa kopplingen.

8. Gå till **fliken Kopplingar på** sidan **Datakopplingar** för att se förloppet för importen för den nya kopplingen.

## <a name="known-issues"></a>Kända problem

- För stunden går det inte att importera bifogade filer eller objekt som är större än 10 MB. Stöd för större objekt blir tillgängligt vid ett senare tillfälle.
