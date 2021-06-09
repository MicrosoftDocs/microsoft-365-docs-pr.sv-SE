---
title: Konfigurera en koppling för att arkivera Bell SMS/MMS Network-data
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
description: Administratörer kan konfigurera en TeleMessage-koppling för att importera och arkivera SMS mms-data från Bell-nätverket. På så sätt kan du arkivera data från datakällor från tredje part i Microsoft 365 så att du kan använda efterlevnadsfunktioner som bevarande av juridiska principer, innehållssökning och bevarandeprinciper för att hantera data från tredje part i organisationen.
ms.openlocfilehash: 7cfdb4556c19261b7e377df72ebe96b9cf20c992
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822220"
---
# <a name="set-up-a-connector-to-archive-bell-network-data"></a>Konfigurera en koppling för att arkivera bellnätverksdata

Använd en TeleMessage-koppling i Microsoft 365 efterlevnadscenter om du vill importera och arkivera SMS MMS-meddelanden (Short Messaging Service) och MMS (Multimedia Messaging Service) från Bell-nätverket. När du har konfigurerat och konfigurerat en koppling ansluts den till organisationens Bell-nätverk en gång om dagen och importerar SMS- och MMS-meddelanden till postlådor i Microsoft 365.

När SMS- och MMS-meddelandena har lagrats i användarnas postlådor kan du använda efterlevnadsfunktioner i Microsoft 365, till exempel Bevarande av juridiska skäl, Innehållssökning och Microsoft 365 bevarandeprinciper för Bell Network-data. Du kan till exempel söka i Bell Network SMS/MMS med innehållssökning eller associera postlådan som innehåller Bell Network-anslutningsdata med en vårdnadshavare i ett Advanced eDiscovery fall. Genom att använda en Bell Network-koppling för att importera och arkivera data i Microsoft 365 kan detta hjälpa din organisation att följa myndighets- och regleringsprinciper.

## <a name="overview-of-archiving-bell-network-data"></a>Översikt över arkivering av bellnätverksdata

Följande översikt förklarar processen med att använda en koppling för att arkivera Bell Network-data i Microsoft 365.

![Bell Network – arkivering av arbetsflöde](../media/BellNetworkConnectorWorkflow.png)

1. Din organisation arbetar med TeleMessage och Bell för att konfigurera en Bell Network-koppling. Mer information finns i [Bell Network Archiver](https://www.telemessage.com/office365-activation-for-bell-network-archiver).

2. I realtid kopieras SMS MMS-meddelanden från organisationens Bell-nätverk till TeleMessage-webbplatsen.

3. Bell Network-kopplingen som du skapar i efterlevnadscentret för Microsoft 365 ansluter till TeleMessage-webbplatsen varje dag och överför SMS- och MMS-meddelandena från de föregående 24 timmarna till en säker Azure Storage plats i Microsoft-molnet. Kopplingen omvandlar också innehållet i SMS MMS-meddelanden till ett e-postmeddelandeformat.

4. Kopplingen importerar mobila kommunikationsobjekt till specifika användares postlådor. En ny mapp **med namnet Bell SMS/MMS Network Archiver** skapas i en viss användares postlåda och objekten importeras till den. Kopplingen gör den här mappningen med hjälp av värdet för *användarens e-postadressegenskap.* Alla SMS och MMS-meddelanden innehåller den här egenskapen, som fylls i med e-postadresserna för varje meddelandedeltagare.

   Förutom automatisk användarmappning med värdet  för användarens e-postadressegenskap kan du också definiera en anpassad mappning genom att ladda upp en CSV-mappningsfil. Den här mappningsfilen innehåller mobiltelefonnumret och den Microsoft 365 e-postadressen för användare i organisationen. Om du aktiverar både automatisk användarmappning och anpassad mappning, tittar kopplingen först på anpassad mappningsfil för varje Bell Network-objekt. Om kontakten inte hittar en giltig Microsoft 365-användare som motsvarar en användares mobiltelefonnummer används värdena i e-postadressegenskapen för objektet som ska importeras. Om kopplingen inte hittar en giltig Microsoft 365 användare i den anpassade mappningsfilen eller i e-postadressegenskapen för Bell Network-objektet importeras inte objektet.

## <a name="before-you-set-up-a-connector"></a>Innan du skapa en koppling

Några av de implementeringssteg som krävs för att arkivera data i Bell Network är Microsoft 365 och måste slutföras innan du kan skapa en anslutning i efterlevnadscentret.

- Beställ [Bell Network Archiver-tjänsten från TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/) och få ett giltigt administrationskonto för din organisation. Du måste logga in på det här kontot när du skapar anslutningen i efterlevnadscentret.

- Hämta dina Bell Network-konto- och faktureringskontaktuppgifter så att du kan fylla i TeleMessage-introduktionsformulären och beställa meddelandearkiveringstjänsten från Bell.

- Registrera alla användare som kräver arkivering av Bell SMS/MMS Network i TeleMessage-kontot. Se till att använda samma e-postadress som används för användarens konto när du registrerar Microsoft 365 användare.

- De anställda måste ha mobiltelefoner som ansvarar för hela företaget på Bell-mobilnätverket. Arkivering av meddelanden i Microsoft 365 inte tillgängligt för enheter som ägs av anställda eller "Bring Your Own Devices (BYOD).

- Den användare som skapar en Bell Network-koppling måste tilldelas rollen Importera och exportera postlåda i Exchange Online. Detta krävs för att lägga till kopplingar på **sidan Datakopplingar** i Microsoft 365 kompatibilitetscenter. Som standard är den här rollen inte tilldelad någon rollgrupp i Exchange Online. Du kan lägga till rollen Importera och exportera postlåda i rollgruppen Organisationshantering i Exchange Online. Du kan också skapa en rollgrupp, tilldela rollen Importera och exportera postlåda och sedan lägga till lämpliga användare som medlemmar. Mer information finns i avsnitten [Skapa rollgrupper](/Exchange/permissions-exo/role-groups#create-role-groups) och [Ändra rollgrupper](/Exchange/permissions-exo/role-groups#modify-role-groups) i artikeln "Hantera rollgrupper i Exchange Online".

- Den här datakopplingen är tillgänglig GCC miljöer i Microsoft 365 för myndigheter i USA. Program och tjänster från tredje part kan innebära att lagra, överföra och bearbeta din organisations kunddata i tredje parts system som ligger utanför Microsoft 365-infrastrukturen och därför inte omfattas av Microsoft 365-åtaganden gällande efterlevnad och dataskydd. Microsoft anger inte att användningen av den här produkten för att ansluta till program från tredje part innebär att sådana program från tredje part är FEDRAMP-kompatibla.

## <a name="create-a-bell-network-connector"></a>Skapa en Bell Network-koppling

Det sista steget är att skapa en Bell Network-koppling i Microsoft 365 efterlevnadscenter. Kopplingen använder den information du anger för att ansluta till TeleMessage-webbplatsen och överföra SMS/ MMS-meddelanden till motsvarande postlåderutor för användare i Microsoft 365.

1. Gå till [https://compliance.microsoft.com](https://compliance.microsoft.com) och klicka sedan på **Datakopplingar**  >  **Bell SMS/MMS Network Archiver**.

2. På **produktbeskrivningssidan för Bell Network** klickar du på **Lägg till koppling**

3. Klicka på **Acceptera på** sidan **Användningsvillkor.**

4. På sidan **Logga in på TeleMessage,** under Steg 3, anger du den information som krävs i följande rutor och klickar sedan på **Nästa.**

   - **Användarnamn:** Ditt TeleMessage-användarnamn.

   - **Lösenord:** Ditt TeleMessage-lösenord.

5. När kopplingen har skapats kan du stänga popup-fönstret och gå till nästa sida.

6. Aktivera automatisk **användarmappning** på sidan Användarmappning. Om du vill aktivera anpassad mappning laddar du upp en CSV-fil som innehåller användarmappningsinformationen och klickar sedan på **Nästa.**

7. Granska inställningarna och klicka sedan på **Slutför för** att skapa kopplingen.

8. Gå till **fliken Kopplingar på** sidan Datakopplingar i **efterlevnadscentret** för att se förloppet för importen för den nya anslutningen.

## <a name="known-issues"></a>Kända problem

- För stunden går det inte att importera bifogade filer eller objekt som är större än 10 MB. Stöd för större objekt blir tillgängligt vid ett senare tillfälle.
