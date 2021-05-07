---
title: Konfigurera en koppling för att arkivera verizonnätverksdata i Microsoft 365
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
description: Administratörer kan konfigurera en TeleMessage-koppling för att importera och arkivera SMS mms-data från Verizon Network i Microsoft 365. På så sätt kan du arkivera data från datakällor från tredje part i Microsoft 365 så att du kan använda efterlevnadsfunktioner som bevarande av juridiska principer, innehållssökning och bevarandeprinciper för att hantera data från tredje part i organisationen.
ms.openlocfilehash: 22647a244878242789aa0a3e671747f113ccea1b
ms.sourcegitcommit: b169f6ad3e44a7fcebf77f43be9eb5edd84ea5ef
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/28/2021
ms.locfileid: "52162842"
---
# <a name="set-up-a-connector-to-archive-verizon-network-data"></a>Konfigurera en koppling för att arkivera verizonnätverksdata

Använd TeleMessage-kopplingen i kompatibilitetscentret för Microsoft 365 för att importera och arkivera data för Short Messaging Service (SMS) och MMS (Multimedia Messaging Service) från Verizon Network. När du har konfigurerat och konfigurerat en anslutning ansluts den till organisationens Verizon Network en gång om dagen och importerar SMS- och MMS-data till postlådor i Microsoft 365.

När Verizon Network-kopplingsdata lagras i användarpostlådor kan du använda Microsoft 365-efterlevnadsfunktioner, till exempel Bevarande av juridiska skäl, Innehållssökning och Microsoft 365 bevarandeprinciper för Verizon-data. Du kan till exempel söka i Verizon SMS- och MMS-meddelanden med hjälp av Innehållssökning eller associera postlådan som innehåller Verizon Network-data med en kollega i ett Advanced eDiscovery fall. Genom att använda en Verizon Network-koppling för att importera och arkivera data i Microsoft 365 kan hjälpa din organisation att följa myndighets- och regleringsprinciper.

## <a name="overview-of-archiving-verizon-network-data"></a>Översikt över arkivering av Verizon Network-data

Följande översikt förklarar processen med att använda en koppling för att arkivera Verizon Network-data i Microsoft 365.

![Verizon Network – arkivering av arbetsflöde](../media/VerizonNetworkConnectorWorkflow.png)

1. Din organisation arbetar med TeleMessage och Verizon för att konfigurera en Verizon Network-koppling. Mer information finns i [Verizon Network Archiver](https://www.telemessage.com/office365-activation-for-verizon-network-archiver/).

2. En gång per dygn SMS MMS-meddelanden från din organisations Verizon Network till TeleMessage-webbplatsen.

3. Verizon Network-kopplingen som du skapar i efterlevnadscentret för Microsoft 365 ansluter till TeleMessage-webbplatsen varje dag och överför SMS- och MMS-meddelandena från de föregående 24 timmarna till en säker Azure Storage plats i Microsoft-molnet. Kopplingen omvandlar också innehållet i SMS MMS-meddelanden till ett e-postmeddelandeformat.

4. Kopplingen importerar mobila kommunikationsobjekt till en viss användares postlåda. En ny mapp **med namnet Verizon SMS/MMS Network Archiver** skapas i den specifika användarens postlåda och objekten importeras till den. Kopplingen gör den här mappningen med hjälp av värdet för *användarens e-postadressegenskap.* Alla SMS och MMS-meddelanden innehåller den här egenskapen, som fylls i med e-postadresserna för varje meddelandedeltagare.

   Förutom automatisk användarmappning med värdet  för användarens e-postadressegenskap kan du även implementera anpassad mappning genom att ladda upp en CSV-mappningsfil. Den här mappningsfilen innehåller mobiltelefonnumret och den Microsoft 365 e-postadressen för användare i organisationen. Om du aktiverar både automatisk användarmappning och anpassad mappning, tittar kopplingen först på anpassad mappningsfil för varje Verizon-objekt. Om kontakten inte hittar en giltig Microsoft 365-användare som motsvarar en användares mobiltelefonnummer används värdena i e-postadressegenskapen för objektet som ska importeras. Om kopplingen inte hittar en giltig Microsoft 365 användare i den anpassade mappningsfilen eller i e-postadressegenskapen för Verizon-objektet, importeras inte objektet.

## <a name="before-you-begin"></a>Innan du börjar

Några av de implementeringssteg som krävs för att arkivera Verizon Network-data är Microsoft 365 och måste slutföras innan du kan skapa en anslutning i efterlevnadscentret.

- Beställ [Verizon Network Archiver-tjänsten från TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) och få ett giltigt administrationskonto för din organisation. Du måste logga in på det här kontot när du skapar anslutningen i efterlevnadscentret.

- Få kontaktinformation för ditt Verizon Network-konto och faktureringskontaktinformation så att du kan fylla i TeleMessage-introduktionsformulären och ordna meddelandearkiveringstjänsten från Verizon.

- Registrera alla användare som kräver att Verizon SMS och MMS arkiveras i TeleMessage-kontot. Se till att använda samma e-postadress som används för användarens konto när du registrerar Microsoft 365 användare.

- De anställda måste ha företags- och företags ansvarig mobiltelefoner på Verizon-mobilnätverket. Arkivering av meddelanden i Microsoft 365 är inte tillgängligt för enheter som ägs av anställda eller ta med egna enheter (BYOD).

- Den användare som skapar en Verizon Network-koppling måste tilldelas rollen Importera och exportera postlåda i Exchange Online. Detta krävs för att lägga till kopplingar på **sidan Datakopplingar** i Microsoft 365 kompatibilitetscenter. Som standard är den här rollen inte tilldelad någon rollgrupp i Exchange Online. Du kan lägga till rollen Importera och exportera postlåda i rollgruppen Organisationshantering i Exchange Online. Du kan också skapa en rollgrupp, tilldela rollen Importera och exportera postlåda och sedan lägga till lämpliga användare som medlemmar. Mer information finns i avsnitten [Skapa rollgrupper](/Exchange/permissions-exo/role-groups#create-role-groups) och [Ändra rollgrupper](/Exchange/permissions-exo/role-groups#modify-role-groups) i artikeln "Hantera rollgrupper i Exchange Online".

## <a name="create-a-verizon-network-connector"></a>Skapa en Verizon Network-koppling

När du har slutfört de krav som beskrivs i föregående avsnitt kan du skapa Verizon Network-koppling i Microsoft 365 kompatibilitetscenter. Kopplingen använder den information du uppger för att ansluta till TeleMessage-webbplatsen och överföra SMS och MMS-meddelanden till motsvarande postlåderutor i Microsoft 365.

1. Gå till [https://compliance.microsoft.com](https://compliance.microsoft.com) och klicka sedan på **Datakopplingar**  >  **Verizon Network.**

2. På **produktbeskrivningssidan för Verizon Network** klickar du på **Lägg till koppling**

3. Klicka på **Acceptera på** sidan **Användningsvillkor.**

4. På sidan **Logga in på TeleMessage,** under Steg 3, anger du den information som krävs i följande rutor och klickar sedan på **Nästa.**
  
   - **Användarnamn:** Ditt TeleMessage-användarnamn.

   - **Lösenord:** Ditt TeleMessage-lösenord.

5. När kopplingen har skapats kan du stänga popup-fönstret och gå till nästa sida.

6. På sidan **Användarmappning** aktiverar du automatisk användarmappning och klickar på **Nästa.** Om du behöver anpassad mappning laddar du upp en CSV-fil och klickar på **Nästa**.

7. Granska inställningarna och klicka sedan på **Slutför för** att skapa kopplingen.

8. Gå till fliken Kopplingar på sidan **Datakopplingar** för att se importprocessen för den nya kopplingen.

## <a name="known-issues"></a>Kända problem

- För stunden går det inte att importera bifogade filer eller objekt som är större än 10 MB. Stöd för större objekt blir tillgängligt vid ett senare tillfälle.