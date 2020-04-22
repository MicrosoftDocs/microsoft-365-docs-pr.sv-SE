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
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
description: Läs om hur du konfigurerar och skyddar administratörskontona.
ms.openlocfilehash: 2104697320308b329f9fde1b6984c15f9814f9ef
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633659"
---
# <a name="protect-your-administrator-accounts"></a>Skydda dina administratörskonton

Eftersom administratörskonton levereras med förhöjda privilegier är de värdefulla mål för hackare och cyberbrottslingar. I den här artikeln beskrivs:

- Så här konfigurerar du ytterligare ett administratörskonto för nödsituationer.
- Hur man skyddar dessa konton.
 
När du registrerar dig för Microsoft 365 och anger din information blir du automatiskt global administratör. En global administratör har den ultimata kontrollen över användarkonton och alla andra inställningar i Microsofts administrationscenter, men det finns många olika typer av administratörskonton med varierande grad av åtkomst. Mer information om de olika åtkomstnivåerna för varje typ av administratörsroll finns i [om administratörsrollen.](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)


## <a name="create-additional-admin-accounts"></a>Skapa ytterligare administratörskonton

Använd endast administratörskonton för administration. Administratörer bör ha ett separat användarkonto för regelbunden användning av Office-appar och endast använda sitt administrativa konto när det behövs för att hantera konton och enheter och när du arbetar med andra administratörsfunktioner. Det är också en bra idé att ta bort Microsoft 365-licensen från administratörskontona så att du inte behöver betala för dem.

Du bör konfigurera minst ett ytterligare globalt administratörskonto för att ge administratörsåtkomst till en annan betrodd medarbetare. Du kan också skapa separata administratörskonton för användarhantering (den här rollen kallas **Administratör för användarhantering**). Mer information finns i [om administratörsroller](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles).

Så här skapar du ytterligare administratörskonton:

 1. Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">administrationscentret</a> och välj sedan **Aktiva användare** \> **Active users** i den vänstra navigeringscentralen.

    ![Välj Användare och sedan Aktiva användare i den vänstra navigeringsfältet](../media/Activeusers.png)

2. På sidan **Aktiva användare** väljer du Lägg till **en användare** högst upp på sidan och ange namnet och annan information på den **nya användarpanelen.**
3. Expandera avsnittet **Roller** och välj **Global administratör** för att ge den här användaren global administratör åtkomst. Du kan också välja **Anpassad administratör** och välja någon av de roller som visas.

    Ange ett alternativt e-postmeddelande i textrutan **Alternativ e-postadress.** Du kan använda den här adressen för att återställa din lösenordsinformation om du blir utelåst. För globala administratörer skickas även ett faktureringsutdrag till den här adressen.

    ![Välj administratörsroll](../media/adminroles.png)
    
4. I avsnittet **Produktlicenser** flyttar du väljaren för **Microsoft 365 Business** till **Av** och **skapa användare utan produktlicens** till **På**.

    ![Välj produktlicens](../media/productlicense.png)

## <a name="create-an-emergency-admin-account"></a>Skapa ett administratörskonto för nödsituationer

Du bör också skapa ett säkerhetskopieringskonto som inte är konfigurerat med MFA (Multifaktorautentisering) så att du inte av misstag låser ut dig själv (till exempel om du förlorar telefonen som du använder som en andra form av verifiering). Kontrollera att lösenordet för det här kontot är en fras eller minst 16 tecken långt. Detta kallas ofta för ett "break-glass-konto".

## <a name="create-a-user-account-for-yourself"></a>Skapa ett användarkonto åt dig själv

Använd ditt användarkonto för att delta i samarbete med din organisation, inklusive att kontrollera e-post. Det innebär att administratörsuppgifterna kan likna *Alice.Chavez<span></span>@Contoso.org* och ditt vanliga användarkonto kan likna *Alice<span></span>@Contoso.com*.

Så här skapar du ett nytt användarkonto:
1. Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">administrationscentret</a> och välj sedan **Aktiva användare** \> **Active users** i den vänstra navigeringscentralen.
2. På sidan **Aktiva användare** väljer du Lägg till **en användare** högst upp på sidan och ange namnet och annan information på den **nya användarpanelen.**
3. Expandera avsnittet **Roller** och välj **Användare (ingen administrativ åtkomst)**.
1. I avsnittet **Produktlicenser** flyttar du väljaren för **Microsoft 365 Business** till **På**. 

## <a name="register-each-of-these-accounts-for-multi-factor-authentication"></a>Registrera vart och ett av dessa konton för multifaktorautentisering


## <a name="additional-recommendations"></a>Ytterligare rekommendationer

- Kontrollera att administratörskonton också är konfigurerade för multifaktorautentisering. Vi visar dig hur du gör detta i [Konfigurera principer för villkorlig åtkomst](m365-campaigns-conditional-access.md).
- Innan du använder administratörskonton stänger du alla orelaterade webbläsarsessioner och appar, inklusive personliga e-postkonton. Du kan också använda i privata eller inkognitowebbläsare.
- När du har slutfört administratörsuppgifter måste du logga ut från webbläsarsessionen.
