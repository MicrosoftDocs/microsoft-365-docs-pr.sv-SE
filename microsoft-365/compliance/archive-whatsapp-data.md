---
title: Konfigurera en koppling för att arkivera WhatsApp-data i Microsoft 365
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
description: Administratörer kan konfigurera en TeleMessage-koppling för att importera och arkivera whatsApp-data i Microsoft 365. På så sätt kan du arkivera data från datakällor från tredje part i Microsoft 365 så att du kan använda efterlevnadsfunktioner som bevarande av juridiska principer, innehållssökning och bevarandeprinciper för att hantera data från tredje part i organisationen.
ms.openlocfilehash: a8f588e6bbe5180865a2053b055230e4f35ed96a
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822171"
---
# <a name="set-up-a-connector-to-archive-whatsapp-data"></a>Konfigurera en koppling för att arkivera WhatsApp-data

Använd TeleMessage-kopplingen i kompatibilitetscentret för Microsoft 365 för att importera och arkivera samtal, chattar, bifogade filer och borttagna meddelanden. När du har konfigurerat och konfigurerat en anslutning ansluts den till din organisations TeleMessage-konto en gång om dagen och importerar mobilkommunikationen för anställda med hjälp av TeleMessage WhatsApp Telefon Archiver eller TeleMessage WhatsApp Cloud Archiver till postlådor i Microsoft 365.

När WhatsApp-data lagras i användarnas postlådor kan du använda efterlevnadsfunktioner i Microsoft 365, till exempel Bevarande av juridiska skäl, Innehållssökning och Microsoft 365 bevarandeprinciper för WhatsApp-data. Du kan till exempel söka i WhatsApp-meddelanden med hjälp av Innehållssökning eller associera postlådan som innehåller WhatsApp-meddelanden med en vårdnadshavare i ett Advanced eDiscovery ärende. Om du använder en WhatsApp-koppling för att importera och arkivera data i Microsoft 365 kan hjälpa din organisation att följa myndighets- och regelpolicyer.

## <a name="overview-of-archiving-whatsapp-data"></a>Översikt över arkivering av whatsapp-data

I följande översikt beskrivs hur du använder en koppling för att arkivera WhatsApp-data i Microsoft 365.

![Arbetsflödet WhatsApp-arkivering](../media/WhatsAppConnectorWorkflow.png)

1. Din organisation arbetar med TeleMessage för att konfigurera en WhatsApp Archiver-koppling. Mer information finns i [WhatsApp Archiver](https://www.telemessage.com/office365-activation-for-whatsapp-archiver).

2. I realtid kopieras organisationens WhatsApp-data till TeleMessage-webbplatsen.

3. WhatsApp-kopplingen som du skapar i efterlevnadscentret för Microsoft 365 ansluter till TeleMessage-webbplatsen varje dag och överför WhatsApp-data från de föregående 24 timmarna till en säker Azure Storage plats i Microsoft-molnet. Kopplingen konverterar även innehållet WhatsApp-data till ett e-postmeddelandeformat.

4. Kopplingen importerar WhatsApp-data till en viss användares postlåda. En ny mapp med **namnet WhatsApp Archiver** skapas i den specifika användarens postlåda och objekten importeras till den. Kopplingen gör den här mappningen med hjälp av värdet för *användarens e-postadressegenskap.* Alla WhatsApp-meddelanden innehåller den här egenskapen, som fylls i med e-postadressen för alla deltagare i meddelandet.

   Förutom automatisk användarmappning med värdet  för användarens e-postadressegenskap kan du även implementera anpassad mappning genom att ladda upp en CSV-mappningsfil. Den här mappningsfilen innehåller mobiltelefonnumret och den Microsoft 365 e-postadressen för användare i organisationen. Om du aktiverar både automatisk användarmappning och anpassad mappning tittar kopplingen först på anpassad mappningsfil för varje WhatsApp-objekt. Om kontakten inte hittar en giltig Microsoft 365-användare som motsvarar en användares mobiltelefonnummer används värdena i e-postadressegenskapen för objektet som ska importeras. Om kopplingen inte hittar en giltig Microsoft 365 i den anpassade mappningsfilen eller i e-postadressegenskapen för WhatsApp-objektet importeras inte objektet.

## <a name="before-you-set-up-a-connector"></a>Innan du skapa en koppling

Några av de implementeringssteg som krävs för att arkivera WhatsApp-kommunikationsdata är externa för Microsoft 365 och måste slutföras innan du kan skapa anslutningen i efterlevnadscentret.

- Beställ [WhatsApp Archiver-tjänsten från TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) och få ett giltigt administrationskonto för din organisation. Du måste logga in på det här kontot när du skapar anslutningen i efterlevnadscentret.

- Registrera alla användare som kräver WhatsApp-arkivering i TeleMessage-kontot. Se till att använda samma e-postadress som används för användarens konto när du registrerar Microsoft 365 användare.

- Installera appen TeleMessage [WhatsApp Telefon Archiver](https://www.telemessage.com/mobile-archiver/whatsapp-phone-archiver-2/) på dina anställdas mobiltelefoner och aktivera den. Du kan också installera de vanliga WhatsApp- eller WhatsApp Business-apparna på de anställdas mobiltelefoner och aktivera WhatsApp Cloud Archiver-tjänsten genom att skanna en QR-kod på TeleMessage-webbplatsen. Mer information finns i [WhatsApp Cloud Archiver](https://www.telemessage.com/mobile-archiver/whatsapp-archiver/whatsapp-cloud-archiver/).

- Den användare som skapar en Verizon Network-koppling måste tilldelas rollen Importera och exportera postlåda i Exchange Online. Detta krävs för att lägga till kopplingar på **sidan Datakopplingar** i Microsoft 365 kompatibilitetscenter. Som standard är den här rollen inte tilldelad någon rollgrupp i Exchange Online. Du kan lägga till rollen Importera och exportera postlåda i rollgruppen Organisationshantering i Exchange Online. Du kan också skapa en rollgrupp, tilldela rollen Importera och exportera postlåda och sedan lägga till lämpliga användare som medlemmar. Mer information finns i avsnitten [Skapa rollgrupper](/Exchange/permissions-exo/role-groups#create-role-groups) och [Ändra rollgrupper](/Exchange/permissions-exo/role-groups#modify-role-groups) i artikeln "Hantera rollgrupper i Exchange Online".

- Den här datakopplingen är tillgänglig GCC miljöer i Microsoft 365 för myndigheter i USA. Program och tjänster från tredje part kan innebära att lagra, överföra och bearbeta din organisations kunddata i tredje parts system som ligger utanför Microsoft 365-infrastrukturen och därför inte omfattas av Microsoft 365-åtaganden gällande efterlevnad och dataskydd. Microsoft anger inte att användningen av den här produkten för att ansluta till program från tredje part innebär att sådana program från tredje part är FEDRAMP-kompatibla.

## <a name="create-a-whatsapp-archiver-connector"></a>Skapa en WhatsApp-arkiveringskoppling

När du har slutfört de krav som beskrivs i föregående avsnitt kan du skapa WhatsApp-kopplingen i Microsoft 365 kompatibilitetscenter. Kopplingen använder den information du anger för att ansluta till TeleMessage-webbplatsen och överföra WhatsApp-data till motsvarande rutor för användarpostlådor i Microsoft 365.

1. Gå till [https://compliance.microsoft.com](https://compliance.microsoft.com/) och klicka sedan på **Datakopplingar**  >  **WhatsApp Archiver**.

2. På **produktbeskrivningssidan för WhatsApp Archiver** klickar du på **Lägg till koppling**

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
