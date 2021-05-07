---
title: Konfigurera en koppling för att arkivera data i O2-nätverket i Microsoft 365
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
description: Administratörer kan konfigurera en TeleMessage-koppling för att importera och arkivera SMS mms-data från det mobila O2-nätverket i Microsoft 365. På så sätt kan du arkivera data från datakällor från tredje part i Microsoft 365 så att du kan använda efterlevnadsfunktioner som bevarande av juridiska principer, innehållssökning och bevarandeprinciper för att hantera data från tredje part i organisationen.
ms.openlocfilehash: a254fbea35b3513ea228560e37ef094098647b75
ms.sourcegitcommit: b169f6ad3e44a7fcebf77f43be9eb5edd84ea5ef
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/28/2021
ms.locfileid: "52162834"
---
# <a name="set-up-a-connector-to-archive-o2-network-data"></a>Konfigurera en koppling för att arkivera data i O2-nätverket

Använd en TeleMessage-koppling i Microsoft 365 kompatibilitetscenter för att importera och arkivera korta meddelandetjänster (SMS) meddelanden och röstsamtal från O2-mobilnätverket. När du har konfigurerat och konfigurerat en anslutning ansluts den till organisationens O2-nätverk en gång om dagen och importerar SMS och röstsamtal till postlådor i Microsoft 365.

När SMS meddelanden och röstsamtal lagras i användarpostlådor kan du använda efterlevnadsfunktioner i Microsoft 365, till exempel Bevarande av juridiska skäl, Innehållssökning och Bevarandeprinciper för Microsoft 365-nätverk för data i O2-nätverk. Du kan till exempel söka i O2 Network SMS-meddelanden och röstsamtal med hjälp av Innehållssökning eller associera postlådan som innehåller O2-nätverksdata med en medarbetare i ett Advanced eDiscovery fall. Om du använder en O2-nätverkskoppling för att importera och arkivera data i Microsoft 365 kan detta hjälpa din organisation att följa myndighets- och regleringsprinciperna.

## <a name="overview-of-archiving-o2-network-data"></a>Översikt över arkivering av data i O2-nätverket

Följande översikt förklarar processen med att använda en koppling för att arkivera data i O2-nätverk i Microsoft 365.

![O2-nätverksarkivering av arbetsflöde](../media/O2NetworkConnectorWorkflow.png)

1. Din organisation arbetar med TeleMessage och O2 för att konfigurera en O2-nätverkskoppling. Mer information finns i [O2 Network Archiver](https://www.telemessage.com/office365-activation-for-o2-network-archiver).

2. En gång per dygn SMS meddelanden och röstsamtal från organisationens O2-nätverk till TeleMessage-webbplatsen.

3. O2 Network-anslutningen som du skapar i efterlevnadscentret för Microsoft 365 ansluter till TeleMessage-webbplatsen varje dag och överför SMS-meddelandena och röstsamtalen från de föregående 24 timmarna till en säker Azure Storage plats i Microsoft-molnet. Med anslutaren omvandlas även innehållet i SMS och röstsamtal till ett e-postmeddelandeformat.

4. Kopplingen importerar mobila kommunikationsobjekt till specifika användares postlådor. En ny mapp med **namnet O2 SMS och Voice Network Archiver** skapas i en viss användares postlåda och objekten importeras till den. Kopplingen gör den här mappningen med hjälp av värdet för *användarens e-postadressegenskap.* Alla SMS och röstsamtal innehåller den här egenskapen, som fylls i med e-postadresserna för varje meddelandedeltagare.

   Förutom automatisk användarmappning med värdet  för användarens e-postadressegenskap kan du också definiera en anpassad mappning genom att ladda upp en CSV-mappningsfil. Den här mappningsfilen innehåller mobiltelefonnumret och den Microsoft 365 e-postadressen för användare i organisationen. Om du aktiverar både automatisk användarmappning och anpassad mappning tittar kopplingen först på anpassad mappningsfil för varje O2-objekt. Om kontakten inte hittar en giltig Microsoft 365-användare som motsvarar en användares mobiltelefonnummer används värdena i e-postadressegenskapen för objektet som ska importeras. Om anslutaren inte hittar en giltig Microsoft 365 i antingen den anpassade mappningsfilen eller i E-postadressegenskapen för O2-objektet importeras inte objektet.

## <a name="before-you-begin"></a>Innan du börjar

Några av de implementeringssteg som krävs för att arkivera data i O2-nätverket är externa Microsoft 365 måste slutföras innan du kan skapa en anslutning i efterlevnadscentret.

- Beställ [O2 Network Archiver-tjänsten från TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/) och få ett giltigt administrationskonto för din organisation. Du måste logga in på det här kontot när du skapar anslutningen i efterlevnadscentret.

- Få information om ditt O2-nätverk och dina faktureringskontaktuppgifter så att du kan fylla i TeleMessage-introduktionsformulären och beställa arkiveringstjänsten för meddelanden från O2.

- Registrera alla användare som kräver att O2 SMS och Voice Network arkiveras i TeleMessage-kontot. Se till att använda samma e-postadress som används för användarens konto när du registrerar Microsoft 365 användare.

- De anställda måste ha mobiltelefoner som ägs av företaget och företagsansvarig på O2-mobilnätverket. Arkivering av meddelanden i Microsoft 365 inte tillgängligt för enheter som ägs av anställda eller "Bring Your Own Devices (BYOD).

- Den användare som skapar en O2-nätverkskoppling måste tilldelas rollen Importera och exportera postlåda i Exchange Online. Detta krävs för att lägga till kopplingar på **sidan Datakopplingar** i Microsoft 365 kompatibilitetscenter. Som standard är den här rollen inte tilldelad någon rollgrupp i Exchange Online. Du kan lägga till rollen Importera och exportera postlåda i rollgruppen Organisationshantering i Exchange Online. Du kan också skapa en rollgrupp, tilldela rollen Importera och exportera postlåda och sedan lägga till lämpliga användare som medlemmar. Mer information finns i avsnitten [Skapa rollgrupper](/Exchange/permissions-exo/role-groups#create-role-groups) och [Ändra rollgrupper](/Exchange/permissions-exo/role-groups#modify-role-groups) i artikeln "Hantera rollgrupper i Exchange Online".

## <a name="create-an-o2-network-connector"></a>Skapa en O2-nätverkskoppling

När du har slutfört kraven som beskrivs i föregående avsnitt kan du skapa en O2-nätverkskoppling i Microsoft 365 efterlevnadscenter. Kopplingen använder den information du uppger för att ansluta till TeleMessage-webbplatsen och överföra SMS och röstsamtal till motsvarande postlåderutor i Microsoft 365.

1. Gå till [https://compliance.microsoft.com](https://compliance.microsoft.com/) och klicka på **Datakopplingar** \> **O2-nätverk.**

2. På **produktbeskrivningssidan för O2-nätverk** klickar du på **Lägg till koppling**

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