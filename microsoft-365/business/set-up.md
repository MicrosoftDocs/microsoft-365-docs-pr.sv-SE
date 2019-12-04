---
title: Konfigurera Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- O365E_M365SetupBanner
- BCS365_M365SetupBanner
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- TRN_SMB
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- OKR_SMB_M365
- TRN_M365B
- OKR_SMB_Videos
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Läs om hur du konfigurerar Microsoft 365 Business.
ms.openlocfilehash: 0001c2b9962f6cce0be1f77cbf427c68f9ee3249
ms.sourcegitcommit: c5ca71d6feb0f033b50ccd4de816fd59b0925007
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/04/2019
ms.locfileid: "39831312"
---
# <a name="set-up-microsoft-365-business-in-the-setup-wizard"></a>Konfigurera Microsoft 365 Business i installationsguiden

Titta på den här videon för en översikt över Microsoft 365 Business setup.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSM] 

Om du hittade den här videon till hjälp, kolla in den [kompletta tränings serien för småföretag och de som är nya för Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

## <a name="add-your-domain-users-and-set-up-policies"></a>Lägg till din domän, användare och Ställ in policyer

[![Etikett som gör att du kan se att administrationscentret ändras och mer information finns på aka.ms/aboutM365preview.](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)

När du köper Microsoft 365 Business har du möjlighet att använda en domän som du äger eller köpa en under [registreringen](sign-up.md).

- Om du har köpt en ny domän när du registrerade dig, är din domän alla inställd och du kan flytta för att [lägga till användare och tilldela licenser](#add-users-and-assign-licenses).

### <a name="add-your-domain-to-personalize-sign-in"></a>Lägg till din domän för att anpassa inloggningen

1. Logga in på [Microsoft 365 administratörscenter](https://admin.microsoft.com) med hjälp av autentiseringsuppgifterna för global administratör. 

2. Välj **gå till installationsprogrammet** för att starta guiden.

    ![Välj Gå till inställningar.](media/gotosetupinadmincenter.png)

3. På sidan **installera Office-appar** kan du välja att installera apparna på din egen dator.
    
4. I steget **Lägg till domän** anger du det domännamn du vill använda (som contoso.com).

    > [!IMPORTANT]
    > Om du har köpt en domän under registreringen kommer du inte att se **Lägg till ett domän** steg här. Gå till [Lägg till användare](#add-users-and-assign-licenses) i stället.

    ![Skärmbild av anpassa din inloggningssida.](media/adddomain.png)

    
4. Följ stegen i guiden för att [Skapa DNS-poster hos valfri DNS-Värdleverantör för Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) som verifierar att du äger domänen. Om du känner till din domänvärd, se även [värdspecifika instruktioner](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).

    Om din Värdleverantör är GoDaddy eller en annan värd som är aktiverad med [domänanslutning](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), är processen enkel och du kommer automatiskt att bli ombedd att logga in och låta Microsoft autentisera för din räkning.

    ![På GoDaddy bekräfta åtkomstsidan, Välj Auktorisera.](media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a>Lägga till användare och tilldela licenser

Du kan lägga till användare i guiden, men du kan också [lägga till användare senare](add-users-m365b.md) i administratörscenter. Om du har en lokal domänkontrollant kan du dessutom lägga till användare med [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).

#### <a name="add-users-in-the-wizard"></a>Lägga till användare i guiden

Alla användare som du lägger till i guiden tilldelas automatiskt en Microsoft 365 Business-licens.

![Skärmbild av sidan Lägg till nya användare i guiden](media/addnewuserspage.png)

1. Om din Microsoft 365 Business-prenumeration har befintliga användare (till exempel om du har använt Azure AD Connect), får du ett alternativ för att tilldela licenser till dem nu. Lägg till licenser till dem också.

2. När du har lagt till användarna får du också ett alternativ för att dela autentiseringsuppgifter med de nya användare som du har lagt till. Du kan välja att skriva ut, e-posta eller ladda ned.

### <a name="connect-your-domain"></a>Koppla din domän

> [!NOTE]
> Om du väljer att använda den. onmicrosoft domän eller används Azure AD Connect för att ställa in användare, kommer du inte att se det här steget.
  
För att få igång tjänsten måste du uppdatera några poster hos din DNS-värd eller domänregistrator.
  
1. Installationsguiden identifierar normalt din domänregistrator och ger dig en länk till stegvisa instruktioner för att uppdatera dina NS-poster på registratorns webbplats. Om den inte gör det [ändrar du namnservrar till konfigurera Office 365 med alla domänregistratorn](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2). 

    - Om du har befintliga DNS-poster, till exempel en befintlig webbplats, men DNS-värden har aktiverats för [domänanslutning](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), väljer du **Lägg till poster åt mig**. Godkänn alla standardinställningar på sidan **Välj dina onlinetjänster** och välj **Nästa**och välj **auktorisera** på din DNS-värdens sida.
    - Om du har befintliga DNS-poster med andra DNS-värdar (inte aktiverat för domänanslutning), ska du hantera dina egna DNS-poster för att se till att de befintliga tjänsterna är anslutna. Mer information finns i [grunderna om domäner](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) .

        ![Sidan aktivera poster.](media/activaterecords.png)

2. Följ stegen i guiden och e-post och andra tjänster kommer att ställas in för dig.

### <a name="protect-your-organization"></a>Skydda din organisation 

De principer som du ställer in i guiden tillämpas automatiskt på en [säkerhetsgrupp](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) som kallas *alla användare*. Du kan också skapa ytterligare grupper för att tilldela principer till i administratörscenter.

1. På **öka skydd mot avancerade cyberhot**, rekommenderas att du accepterar standardinställningarna för att låta [Office 365 Advance hot Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) skanna filer och länkar i Office-program.

    ![Skärmbild av öka skydd sida.](media/increasetreatprotection.png)


2. På sidan **förhindra läckage av känsliga data** accepterar du standardvärdena för att aktivera Office 365 data loss prevention (DLP) för att spåra känsliga data i Office-appar och förhindra oavsiktlig delning av dessa utanför organisationen.

3. På sidan **skydda data i Office för mobilen** lämnar du mobilappshantering på, expanderar inställningarna och granskar dem och väljer sedan **skapa hanteringsprincip för mobil applikation**.

    ![Skärmbild av skydda data i Office för mobilsida.](media/protectdatainmobile.png)


## <a name="secure-windows-10-pcs"></a>Säkra Windows 10-datorer

I det vänstra navigeringsfältet väljer du **Inställningar** och sedan, under **Sing-in och säkerhet**, väljer du **skydda dina Windows 10-datorer**. Välj **Visa** för att komma igång. Se [skydda dina Windows 10-datorer](secure-win-10-pcs.md) för fullständiga instruktioner.

## <a name="deploy-office-365-client-apps"></a>Distribuera Office 365-klientappar

Om du väljer att automatiskt installera Office-appar under installationen kommer apparna att installeras på Windows 10-enheterna när användarna har loggat in på Azure AD från sina Windows-enheter med sina autentiseringsuppgifter för arbete.

Om du vill installera Office på mobila iOS-eller Android-enheter läser [du konfigurera mobila enheter för Microsoft 365 företagsanvändare](set-up-mobile-devices.md).

Du kan också installera Office individuellt. Mer information finns i [installera Office på en PC eller Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658) .

## <a name="see-also"></a>Se även

[Microsoft 365 Business utbildning videor](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
