---
title: Pilot Microsoft 365 från min anpassade domän
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Adm_O365
ms.custom: ''
search.appverid:
- BCS160
- MET150
- MOE150
description: Lär dig hur du utvärderar e-post från min egen domän till en Microsoft 365-postlåda genom att bara använda två test konton.
ms.openlocfilehash: bfcb2bda4d560ab629ddebed88ac1d55e6224c05
ms.sourcegitcommit: 5f980a9eb5aca61cf3662ef0bc65dec215e21656
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/20/2020
ms.locfileid: "45186053"
---
# <a name="pilot-microsoft-365-from-my-custom-domain"></a>Pilot Microsoft 365 från min anpassade domän

Du kan pilot Microsoft 365 med följande krav och begränsningar:

- Din aktuella e-postleverantör måste tillhandahålla vidarebefordran av e-post.

- Du måste hantera dina Microsoft 365 DNS-poster hos din DNS-värd, i stället för att låta Microsoft 365 hantera posterna åt dig.

    Mer information finns i [Lägg till DNS-poster för att ansluta din domän](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).

- Ledig/upptagen-information för användare på den andra e-postservern är inte tillgänglig.

- Administratörer kan inte administrera alla användarkonton från en enda plats.

- Användare kanske inte kan använda Microsoft 365 spam enfilter.

## <a name="set-up-a-microsoft-365-pilot"></a>Konfigurera en Microsoft 365-pilot

Följ dessa steg för att konfigurera en Microsoft 365-pilot:

### <a name="step-1-sign-in-to-the-microsoft-365-admin-center"></a>Steg 1: Logga in på Administrationscenter för Microsoft 365

1. Logga in på [Administrationscenter för Microsoft 365](https://admin.microsoft.com) med ditt arbets-eller skol konto.

2. Välj **inställningar** > **domäner** i det vänstra navigerings fönstret.

### <a name="step-2-verify-that-you-own-the-domain-you-want-to-use"></a>Steg 2: Kontrollera att du äger den domän som du vill använda

1. På sidan **Domains** väljer du **Lägg till domän**.

2. Skriv domän namnet i rutan. Välj **Använd den här domänen**och välj sedan **Fortsätt**.

3. Välj de tjänster som du vill testa med din domän, t. ex. e-post och snabb meddelanden.

5. På sidan **verifiera** domän följer du de stegvisa anvisningarna, AMD väljer **verifiera**.

    Det tar mellan några minuter och 72 timmar för DNS-ändringarna att börja gälla.

    När verifieringen lyckas ombeds du ändra dina DNS-poster.

### <a name="step-3-mark-the-domain-as-shared-in-exchange-online"></a>Steg 3: Markera domänen som delad i Exchange Online

1. I administrations centret för Exchange går du till avsnittet **e-postflöde**. Välj **godkända domäner**och välj sedan den domän som du vill ändra.

2. Dubbelklicka på fönstret för att öppna det och välj **internt relä**. 

3. Välj **Spara**.

    Den här inställningen kan kräva ett par minuter för att börja gälla.

### <a name="step-4-unblock-the-existing-email-server-optional"></a>Steg 4: Häv blockering av den befintliga e-postservern (valfritt)

I Microsoft 365 används Exchange Online Protection (EOP) för skräp post skydd. EOP kanske blockerar din befintliga e-postserver om en stor volym skräp post överförs av den aktuella e-postservern. Om du litar på skräp post skyddet för den andra e-postleverantören kan du häva blockeringen av servern i Microsoft 365.

> [!NOTE]
> Om du tar bort blockeringen av den befintliga e-postservern får all skräp post som kommer via din ursprungliga server till gång till Microsoft 365-post lådorna och du kan inte utvärdera hur bra Microsoft 365 hindrar skräp post.

1. I navigerings fönstret i administrations centret för Exchange väljer du **skydd**och väljer sedan **anslutnings filter**.

2. Välj **+****i listan med lista över tillåtna IP-** och e-postservern. 

### <a name="step-5-create-user-accounts-and-set-the-primary-reply-to-address"></a>Steg 5: skapa användarkonton och ange primär svars adress

1. Välj **användare** > **aktiva användare**i det vänstra navigerings fältet i Administrationscenter för Microsoft 365.

2. Skapa två test konton genom att lägga till två befintliga användare.

    För varje konto väljer du **+ Lägg till en användare**och fyller i den information som krävs, inklusive den metod för lösen ord som du vill testa.

    Om du vill vara säker på att användarens e-postadress är densamma måste fältet **användarnamn** matcha användarens aktuella e-postadress.

3. Välj en licens, klicka på **nästa**och klicka sedan **Slutför lägga till**. 

4. Bredvid **Användarnamn** väljer du det anpassade domännamnet i listrutan. 

5. Välj **skapa** > **stänga**.

### <a name="step-6-update-dns-records-at-your-dns-hosting-provider"></a>Steg 6: Uppdatera DNS-posterna hos DNS-värden

Logga in på din DNS-värds webbplats och följ anvisningarna i [lägga till DNS-poster för att ansluta domänen](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).

**Gör följande två undantag:**

- Skapa inte en ny MX-post samt ändra inte den befintliga MX-posten.

- Om du redan har en SPF-post (Sender Policy Framework) för din tidigare e-postleverantör, ska du i stället för att skapa en ny SPF-post (TXT) för Exchange Online lägga till "include: SPF. Protection. Outlook. com" i den aktuella TXT-posten.

    Exempel: "v = spf1 MX include: adatum. com inkluderar: SPF. Protection. Outlook. com ~ all".

    Om du inte har en SPF-post ändrar du den som rekommenderas av Microsoft 365 för att inkludera domänen för din aktuella e-postleverantör och lägga till spf.protection.outlook.com. Detta godkänner utgående meddelanden från båda e-postsystemen.

### <a name="step-7-set-up-email-forwarding-at-your-current-provider"></a>Steg 7: Konfigurera vidarebefordran av e-post hos din nuvarande leverantör

På din aktuella e-postleverantör ställer du in vidarebefordring för dina användares e-postkonton i din onmicrosoft.com-domän:

- Vidarebefordra en användare en post låda till usera@yourcompany.onmicrosoft.com

- Vidarebefordra användarens e-postlåda till userb@yourcompany.onmicrosoft.com

När du slutför det här steget blir all e-post som skickas till usera@yourcompany.com och userb@yourcompany.com tillgänglig i Microsoft 365.

> [!NOTE]
> Kontakta din aktuella e-postleverantör för att få de exakta stegen för att konfigurera vidarebefordran av e-post.<br/>
> Du behöver inte spara en kopia av meddelanden hos den aktuella e-postleverantören.<br/>
> De flesta leverantörer vidarebefordrar e-post genom att lämna svar till avsändarens e-postadress intakt så att svar går till den ursprungliga avsändaren.

### <a name="step-8-test-mail-flow"></a>Steg 8: Testa e-postflöde

1. Logga in på Outlook Web App med inloggnings uppgifterna för användaren A.

2. Utför följande tester:

    - Testa lokala Microsoft-e-postmeddelanden genom att till exempel skicka ett e-postmeddelande till användare B. E-postmeddelandet levereras omedelbart. I det här scenariot dirigeras inte meddelandet till post lådan för användare B på din ursprungliga server eftersom Microsoft 365-post lådan är lokal.

    - Testa e-post till en användare på det befintliga e-postsystemet genom att t. ex. Skicka ett e-postmeddelande till användare C. E-postmeddelandet skickas till användarens e-postserver på din ursprungliga e-postserver.

    - Kontrollera att vidarebefordran är rätt konfigurerat från ett externt konto eller från ett e-postkonto i det befintliga e-postsystemet. Skicka till exempel ett e-postmeddelande från det ursprungliga serverkontot för User C eller ett Hotmail-konto och verifiera att det anländer till Microsoft 365-postlådan för användare A.

### <a name="step-9-move-mailbox-contents"></a>Steg 9: Flytta postlådeinnehåll

Eftersom du bara flyttar två test användare, och användare A och användare B båda använder Outlook, kan du flytta e-postmeddelandet genom att öppna det gamla. PST-filen i den nya Outlook-profilen och kopiera meddelanden, Kalender objekt, kontakter och så vidare. Mer information finns i [importera e-post, kontakter och kalender från en Outlook. PST-fil](https://support.microsoft.com/office/import-email-contacts-and-calendar-from-an-outlook-pst-file-431a8e9a-f99f-4d5f-ae48-ded54b3440ac).

När de har importer ATS till lämpliga platser i Microsoft 365-post lådan kan objekten vara tillgängliga från vilken enhet som helst, var som helst.

När flera post lådor är inblandade, eller om anställda inte använder Outlook, kan du använda de Migreringsverktyg som finns tillgängliga i administrations centret för Exchange. Kom igång genom att gå till administrations centret för Exchange och följa anvisningarna i [migrera e-post från en IMAP-server till Exchange Online-postlådor – vi behöver en ny artikel resurs].