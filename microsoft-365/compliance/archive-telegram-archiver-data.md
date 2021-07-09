---
title: Konfigurera en koppling för att arkivera Communications-data i Microsoft 365
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
description: Administratörer kan konfigurera en TeleMessage-koppling för att importera och arkivera data om Communications i Microsoft 365. På så sätt kan du arkivera data från datakällor från tredje part i Microsoft 365 så att du kan använda efterlevnadsfunktioner som bevarande av juridiska principer, innehållssökning och bevarandeprinciper för att hantera data från tredje part i organisationen.
ms.openlocfilehash: 5db1869a1c386ed75f3d8d1381f598d907d2b5ba
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339448"
---
# <a name="set-up-a-connector-to-archive-telegram-communications-data"></a>Konfigurera en koppling för att arkivera kommunikationsdata från Communications

Använd TeleMessage-kopplingen i Microsoft 365 Efterlevnadscenter för att importera och arkivera Chattar, bifogade filer, filer samt borttagna meddelanden och samtal. När du har konfigurerat och konfigurerat en anslutning ansluts den till organisationens TeleMessage-konto och importerar mobilkommunikationen för anställda som använder Arkivet För företag till postlådor i Microsoft 365.

När Bevarandearkiveringskopplingsdata har lagrats i användarnas postlådor kan du använda efterlevnadsfunktioner i Microsoft 365, till exempel Bevarande av juridiska skäl, Innehållssökning och bevarandeprinciper i Microsoft 365 för bevarande av kommunikationsdata. Du kan till exempel söka efter Kommunikation med Hjälp av innehållssökning eller associera postlådan som innehåller Arkiveringskopplingsdata med en medarbetare i ett Advanced eDiscovery ärende. Genom att använda en anslutning för arkivering av arkivering för företag för att importera och arkivera data i Microsoft 365 kan din organisation följa reglerna för företagsstyrning.

## <a name="overview-of-archiving-telegram-communications-data"></a>Översikt över arkivering av Kommunikationsdata

Följande översikt förklarar processen med att använda en anslutare för att arkivera Kommunikationsdata från Microsoft 365.

![Tidigare kommunikation – arkivering av arbetsflöde](../media/TelegramConnectorWorkflow.png)

1. Din organisation arbetar med TeleMessage för att konfigurera en Arkiveringskoppling. Mer information finns i [Aktivera TeleMessageMessage Archiver för Microsoft 365](https://www.telemessage.com/microsoft-365-activation-for-telegram-archiver/).

2. Organisationens Statistik-data kopieras i realtid till TeleMessage-webbplatsen.

3. Kopplingen för Arkiveringsarkivering som du skapar i Microsoft 365 Efterlevnadscenter ansluter till TeleMessage-webbplatsen varje dag och överför e-postmeddelandena från de senaste 24 timmarna till ett säkert Azure Storage i Microsoft Cloud.

4. Kopplingen importerar mobila kommunikationsobjekt till en viss användares postlåda. En ny mapp med namnet Arkivering skapas i den specifika användarens postlåda och objekten importeras till den. Kopplingen gör den här mappningen med hjälp av värdet för *användarens e-postadressegenskap.* Alla e-postmeddelanden innehåller den här egenskapen, som fylls i med e-postadresserna för alla deltagare i e-postmeddelandet.

> Förutom automatisk användarmappning med värdet  för användarens e-postadressegenskap kan du också definiera en anpassad mappning genom att ladda upp en CSV-mappningsfil. Den här mappningsfilen ska innehålla användarens mobilnummer och motsvarande e Microsoft 365 postlådeadress för varje användare. Om du aktiverar automatisk användarmappning och tillhandahåller en anpassad mappning kommer kopplingen först att titta på anpassad mappningsfil för varje e-postobjekt. Om anslutaren inte hittar en giltig Microsoft 365-användare som motsvarar en användares mobilnummer använder kopplingen användarens e-postadressegenskap för e-postobjektet. Om kopplingen inte hittar en giltig Microsoft 365-användare i antingen  den anpassade mappningsfilen eller användarens e-postadressegenskap för e-postobjektet, importeras inte objektet.

## <a name="before-you-set-up-a-connector"></a>Innan du skapa en koppling

- Ordna [Arkiveringstjänsten Förtjänst via TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/) och få ett giltigt administrationskonto för din organisation. Du måste logga in på det här kontot när du skapar anslutningen i efterlevnadscentret.

- Registrera alla användare som kräver Ark-arkivering i TeleMessage-kontot. Se till att använda samma e-postadress som används för användarens konto när du registrerar Microsoft 365 användare.

- Installera appen Archiver för arkivering på de anställdas mobiltelefoner och aktivera den. Med appen Arkivering kan de kommunicera och chatta med andra Användare av Arkivering.

- Den användare som skapar en Arkiveringskoppling i steg 3 måste tilldelas rollen Importera och exportera postlåda i Exchange Online. Detta krävs för att lägga till kopplingar på **sidan Datakopplingar** i Microsoft 365 Efterlevnadscenter. Som standard är den här rollen inte tilldelad någon rollgrupp i Exchange Online. Du kan lägga till rollen Importera och exportera postlåda i rollgruppen Organisationshantering i Exchange Online. Du kan också skapa en rollgrupp, tilldela rollen Importera och exportera postlåda och sedan lägga till lämpliga användare som medlemmar. Mer information finns i avsnitten [Skapa rollgrupper](/Exchange/permissions-exo/role-groups#create-role-groups) och [Ändra rollgrupper](/Exchange/permissions-exo/role-groups#modify-role-groups) i artikeln "Hantera rollgrupper i Exchange Online".

## <a name="create-a-telegram-archiver-connector"></a>Skapa en anslutning för arkivering av arkivering

När du har slutfört de krav som beskrivs i föregående avsnitt kan du skapa Kopplingen Arkivering av arkivering i den Microsoft 365 Efterlevnadscenter. Kopplingen använder den information du anger för att ansluta till TeleMessage-webbplatsen och överför Communications-data till motsvarande postlåderutor för användare i Microsoft 365.

1. Gå till <https://compliance.microsoft.com> och klicka sedan på **Datakopplingar** > T **elegram Archiver**.

2. Klicka på **Lägg till koppling på** produktbeskrivningssidan för **Arkivering.**

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
