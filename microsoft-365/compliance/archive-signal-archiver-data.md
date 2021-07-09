---
title: Konfigurera en koppling för att arkivera signalkommunikationsdata i Microsoft 365
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
description: Administratörer kan konfigurera en TeleMessage-koppling för att importera och arkivera signalkommunikationsdata i Microsoft 365. På så sätt kan du arkivera data från datakällor från tredje part i Microsoft 365 så att du kan använda efterlevnadsfunktioner som bevarande av juridiska principer, innehållssökning och bevarandeprinciper för att hantera data från tredje part i organisationen.
ms.openlocfilehash: bce1788f2ce08ca8678c5ba29c01e1bec2d1c834
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339472"
---
# <a name="set-up-a-connector-to-archive-signal-communications-data"></a>Konfigurera en anslutare för att arkivera signalkommunikationsdata

Använd TeleMessage-kopplingen i Microsoft 365 Efterlevnadscenter för att importera och arkivera signalchattar, bifogade filer, filer samt borttagna meddelanden och samtal. När du har konfigurerat och konfigurerat en anslutning ansluts den till organisationens TeleMessage-konto och importerar mobilkommunikationen för anställda som använder TeleMessage Signal Archiver till postlådor i Microsoft 365.

När signalarkiverarens kopplingsdata lagras i användarnas postlådor kan du använda efterlevnadsfunktioner i Microsoft 365, till exempel Bevarande av juridiska skäl, Innehållssökning och Microsoft 365 bevarandeprinciper för signalkommunikationsdata. Du kan till exempel söka efter signalkommunikation med hjälp av innehållssökning eller associera postlådan som innehåller signalarkiveringskopplingsdata med en medarbetare i ett Advanced eDiscovery fall. Med en signalarkiveringskoppling kan du importera och arkivera data i Microsoft 365 för att hjälpa din organisation att följa företagsstyrningsföreskrifter och reglerande principer.

## <a name="overview-of-archiving-signal-communications-data"></a>Översikt över arkivering av signalkommunikationsdata

Följande översikt förklarar processen med att använda en koppling för att arkivera signalkommunikationsdata i Microsoft 365.

![Arbetsflöde för signalkommunikationsarkivering](../media/SignalConnectorWorkflow.png)

1. Din organisation arbetar med TeleMessage för att konfigurera en signalarkiveringskoppling. Mer information finns i [Aktivera TeleMessage Signal Archiver för Microsoft 365](https://www.telemessage.com/microsoft-365-activation-for-signal-archiver/).

2. Organisationens signaldata kopieras i realtid till TeleMessage-webbplatsen.

3. Den signalarkiveringskoppling som du skapar i Microsoft 365 Efterlevnadscenter ansluter till TeleMessage-webbplatsen varje dag och överför e-postmeddelandena från de senaste 24 timmarna till ett säkert Azure Storage i Microsoft Cloud.

4. Kopplingen importerar mobila kommunikationsobjekt till en viss användares postlåda. En ny mapp med namnet Signalarkivering skapas i den specifika användarens postlåda och objekten importeras till den. Kopplingen gör mappningen med hjälp av värdet för *användarens e-postadressegenskap.* Alla e-postmeddelanden innehåller den här egenskapen, som fylls i med e-postadresserna för alla deltagare i e-postmeddelandet.

> Förutom automatisk användarmappning med värdet  för användarens e-postadressegenskap kan du också definiera en anpassad mappning genom att ladda upp en CSV-mappningsfil. Den här mappningsfilen ska innehålla användarens mobilnummer och motsvarande e Microsoft 365 postlådeadress för varje användare. Om du aktiverar automatisk användarmappning och tillhandahåller en anpassad mappning kommer kopplingen först att titta på anpassad mappningsfil för varje e-postobjekt. Om anslutaren inte hittar en giltig Microsoft 365-användare som motsvarar en användares mobilnummer använder kopplingen användarens e-postadressegenskap för e-postobjektet. Om kopplingen inte hittar en giltig Microsoft 365-användare i antingen  den anpassade mappningsfilen eller användarens e-postadressegenskap för e-postobjektet, importeras inte objektet.

## <a name="before-you-set-up-a-connector"></a>Innan du skapa en koppling

- Beställ [signalarkivtjänsten från TeleMessage och](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/) få ett giltigt administrationskonto för din organisation. Du måste logga in på det här kontot när du skapar anslutningen i efterlevnadscentret.

- Registrera alla användare som kräver signalarkivering i TeleMessage-kontot. Se till att använda samma e-postadress som används för användarens konto när du registrerar Microsoft 365 användare.

- Installera appen Signalarkivering på dina anställdas mobiltelefoner och aktivera den. Med appen Signalarkivering kan de kommunicera och chatta med andra signalanvändare.

- Den användare som skapar en signalarkiveringskoppling i steg 3 måste tilldelas rollen Importera och exportera postlåda i Exchange Online. Detta krävs för att lägga till kopplingar på **sidan Datakopplingar** i Microsoft 365 Efterlevnadscenter. Som standard är den här rollen inte tilldelad någon rollgrupp i Exchange Online. Du kan lägga till rollen Importera och exportera postlåda i rollgruppen Organisationshantering i Exchange Online. Du kan också skapa en rollgrupp, tilldela rollen Importera och exportera postlåda och sedan lägga till lämpliga användare som medlemmar. Mer information finns i avsnitten [Skapa rollgrupper](/Exchange/permissions-exo/role-groups#create-role-groups) och [Ändra rollgrupper](/Exchange/permissions-exo/role-groups#modify-role-groups) i artikeln "Hantera rollgrupper i Exchange Online".

## <a name="create-a-signal-archiver-connector"></a>Skapa en signalarkiveringskoppling

När du har slutfört de krav som beskrivs i föregående avsnitt kan du skapa signalarkiveringskopplingen i Microsoft 365 Efterlevnadscenter. Kopplingen använder den information du uppger för att ansluta till TeleMessage-webbplatsen och överför signalkommunikationsdata till motsvarande postlåderutor för användare i Microsoft 365.

1. Gå till <https://compliance.microsoft.com> och klicka sedan på **Datakopplingar**  >  **Signalarkiveraren**.

2. På **produktbeskrivningssidan för** Signalarkiveraren klickar du på **Lägg till koppling.**

3. Klicka på **Acceptera på** sidan **Användningsvillkor.**

4. På sidan **Logga in på TeleMessage,** under Steg 3, anger du den information som krävs i följande rutor och klickar sedan på **Nästa.**

    - **Användarnamn:** Ditt TeleMessage-användarnamn.

    - **Lösenord:** Ditt TeleMessage-lösenord.

5. När kopplingen har skapats kan du stänga popup-fönstret och gå till nästa sida.

6. Aktivera automatisk **användarmappning** på sidan Användarmappning. Om du vill aktivera anpassad mappning laddar du upp en CSV-fil som innehåller användarmappningsinformationen och klickar sedan på **Nästa.**

7. Granska inställningarna och klicka sedan på **Slutför för** att skapa kopplingen.

8. Gå till fliken Kopplingar på sidan **Datakopplingar** för att se importprocessen för den nya kopplingen.

## <a name="known-issues"></a>Kända problem

- För stunden går det inte att importera bifogade filer eller objekt som är större än 10 MB. Stöd för större objekt blir tillgängligt vid ett senare tillfälle.
