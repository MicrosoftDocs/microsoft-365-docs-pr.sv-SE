---
title: Skydda dina administratörskonton
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
description: Lär dig att konfigurera och skydda dina administratörskonton.
ms.openlocfilehash: ec5b971ba4f1fdc8834e10ddf90ff219f763f805
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50912180"
---
# <a name="protect-your-administrator-accounts"></a>Skydda dina administratörskonton

Eftersom administratörskonton har förhöjd behörighet är de värdefulla mål för hackare och cyberbrottsligheter. I den här artikeln beskrivs:

- Konfigurera ytterligare ett administratörskonto för nödsituationer.
- Hur du skyddar dessa konton.

När du registrerar dig för Microsoft 365 och anger din information blir du automatiskt global administratör. En global administratör har den slutgiltiga kontrollen över användarkonton och alla andra inställningar i administrationscentret för Microsoft, men det finns många olika typer av administratörskonton med olika åtkomstgrad. Mer [information om de](/office365/admin/add-users/about-admin-roles) olika åtkomstnivåerna för varje typ av administratörsroll finns i om administratörsroller.

## <a name="create-additional-admin-accounts"></a>Skapa ytterligare administratörskonton

Använd endast administratörskonton för administration. Administratörer bör ha ett separat användarkonto för normal användning av Office-program och bara använda sitt administratörskonto när det behövs för att hantera konton och enheter och medan de arbetar med andra administratörsfunktioner. Det är också en bra idé att ta bort Microsoft 365-licensen från administratörskontona så att du inte behöver betala för dem.

Du bör konfigurera minst ett globalt administratörskonto för att ge administratörsåtkomst till en annan betrodd anställd. Du kan också skapa separata administratörskonton för användarhantering (den här rollen kallas **användarhanteringsadministratör).** Mer information finns i om [administratörsroller](/office365/admin/add-users/about-admin-roles).

Så här skapar du ytterligare administratörskonton:

 1. Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">administrationscentret och</a> välj sedan **Användare aktiva** användare \> **i** det vänstra navigeringsfältet.

    ![Välj Användare och sedan Aktiva användare i det vänstra navigeringsfältet](../media/Activeusers.png)

 2. På sidan **Aktiva** användare väljer du **Lägg** till en användare  längst upp på sidan. På panelen Ny användare anger du namn och annan information.
 3. Expandera avsnittet **Roller** och välj Global **administratör för att ge** användaren global administratörsåtkomst. Du kan också **välja Anpassad administratör** och välja någon av rollerna som visas.

    Ange ett alternativt e-postmeddelande i **textrutan Alternativ e-postadress.** Du kan använda den här adressen för att återställa lösenordsinformationen om du blir utelåst. För globala administratörer skickas även ett faktureringsutdrag till den här adressen.

    ![Välj administratörsroll](../media/adminroles.png)

 4. I avsnittet **Produktlicenser** flyttar du väljaren för **Microsoft 365 Business** till **Av** och Skapa användare **utan produktlicens** till **På.**

    ![Välj produktlicensen](../media/productlicense.png)

## <a name="create-an-emergency-admin-account"></a>Skapa ett nödsituationsadministratörskonto

Du bör också skapa ett konto för säkerhetskopiering som inte är konfigurerat med multifaktorautentisering (MFA) så att du inte oavsiktligt låser ut dig själv (till exempel om du förlorar telefonen som du använder som en andra form av verifiering). Kontrollera att lösenordet för det här kontot är en fras eller minst 16 tecken långt. Det här kallas ofta för ett "break-glass-konto".

## <a name="create-a-user-account-for-yourself"></a>Skapa ett användarkonto åt dig själv

Använd ditt användarkonto för att delta i samarbete med din organisation, inklusive att kontrollera e-post. Det innebär att dina administratörsautentiseringsuppgifter kan vara ungefär som  *Chavez <span></span> @Contoso.org* och ditt vanliga användarkonto kan vara ungefär som *<span></span> @Contoso.com*.

Så här skapar du ett nytt användarkonto:

1. Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">administrationscentret och</a> välj sedan **Användare aktiva** användare \> **i** det vänstra navigeringsfältet.
2. På sidan **Aktiva** användare väljer du **Lägg** till en användare  längst upp på sidan. På panelen Ny användare anger du namn och annan information.
3. Expandera avsnittet **Roller** och välj **Användare (ingen administrativ åtkomst).**
4. I avsnittet **Produktlicenser** flyttar du väljaren för **Microsoft 365 Business** till **På.**

## <a name="register-each-of-these-accounts-for-multi-factor-authentication"></a>Registrera var och en av dessa konton för multifaktorautentisering

Kontrollera att dessa konton använder [multifaktorautentisering](m365-campaigns-multifactor-authenication.md).

## <a name="additional-recommendations"></a>Ytterligare rekommendationer

- Se till att administratörskonton också har ställts in för multifaktorautentisering. Vi visar hur du gör detta i Konfigurera [principer för villkorsstyrd åtkomst.](m365-campaigns-conditional-access.md)
- Stäng alla orelaterade webbläsarsessioner och appar, inklusive personliga e-postkonton, innan du använder administratörskonton. Du kan också använda i privata webbläsarfönster eller inkognitofönster.
- Se till att logga ut från webbläsarsessionen när du har slutfört administratörsuppgifter.