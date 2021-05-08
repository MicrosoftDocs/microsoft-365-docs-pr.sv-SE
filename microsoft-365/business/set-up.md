---
title: Konfigurera Microsoft 365 Business Premium
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Upptäck konfigurationsstegen för Microsoft 365 Business Premium, inklusive att lägga till en domän och användare, konfigurera säkerhetsprinciper med mera.
ms.openlocfilehash: 37607b483686fc12ac6253ae9f693ec86c073c4e
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245053"
---
# <a name="set-up-microsoft-365-business-premium-in-the-setup-wizard"></a>Konfigurera Microsoft 365 Business Premium i installationsguiden

Titta på den här videon för en översikt över Microsoft 365 Business Premium konfiguration.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

## <a name="add-your-domain-users-and-set-up-policies"></a>Lägga till domän, användare och konfigurera principer

När du köper Microsoft 365 Business Premium domän kan du välja att använda en domän som du äger eller köpa en i [samband med köpet.](sign-up.md)

- Om du har köpt en ny domän när du registrerade dig kommer din domän att konfigureras, och du kan gå vidare till [Lägga till användare och tilldela licenser](#add-users-and-assign-licenses).

### <a name="add-your-domain-to-personalize-sign-in"></a>Lägga till din domän för att personanpassa inloggning

1. Logga in på [Administrationscenter för Microsoft 365](https://admin.microsoft.com) som global administratör. 

2. Starta guiden genom att välja **Gå till inställningar**.

    ![Välj Gå till inställningar.](../media/gotosetupinadmincenter.png)

3. På sidan **Installera Office-apparna** kan du välja att installera apparna på din egen dator.
    
4. Under steget **Lägg till domän** anger du domännamnet du vill använda (t.ex. contoso.com).

    > [!IMPORTANT]
    > Om du har köpt en domän under registreringen ser du inte steget **Lägg till en domän** här. Gå istället till [Lägg till användare](#add-users-and-assign-licenses).

    ![Skärmbild av sidan Anpassa din inloggning.](../media/adddomain.png)

    
4. Följ stegen i guiden för att [Skapa DNS-poster hos en DNS-värd](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) för Microsoft 365 som verifierar att du äger domänen. Om du vet vilken din domänvärd är kan du även se [Värdspecifika anvisningar](/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).

    Om din värd är GoDaddy eller en annan värd som är aktiverad med [Domain Connect](/office365/admin/get-help-with-domains/domain-connect)är processen enkel och du blir automatiskt ombedd att logga in och låta Microsoft autentisera.

    ![Välj Auktorisera på sidan Bekräfta Åtkomst hos GoDaddy.](../media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a>Lägga till användare och tilldela licenser

Du kan lägga till användare i guiden eller så kan du [lägga till användare senare](../admin/add-users/add-users.md) i administratörscentret. Om du har en lokal domänkontrollant kan du även lägga till användare med [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express).

#### <a name="add-users-in-the-wizard"></a>Lägg till användare i guiden

Alla användare som du lägger till i guiden tilldelas automatiskt en Microsoft 365 Business Premium licens.

![Skärmbild av sidan Lägg till nya användare i guiden](../media/addnewuserspage.png)

1. Om din Microsoft 365 Business Premium-prenumeration har befintliga användare (till exempel om du använde Azure AD Anslut) får du möjlighet att tilldela licenser till dem nu. Lägg till licenser till dem också.

2. Efter att ha lagt till användarna får du också möjlighet att dela autentiseringsuppgifter med de nya användarna som du har lagt till. Du kan välja att skriva ut, e-posta eller ladda ned.

### <a name="connect-your-domain"></a>Koppla din domän

> [!NOTE]
> Om du väljer att använda .onmicrosoft-domänen, eller använde Azure AD Connect för att konfigurera användare, kommer du inte att se det här steget.
  
För att få igång tjänsten måste du uppdatera några poster hos din DNS-värd eller domänregistrator.
  
1. Installationsguiden identifierar normalt din domänregistrator och ger dig en länk till stegvisa instruktioner för att uppdatera dina NS-poster på registratorns webbplats. Om det inte fungerar kan [du ändra namnservrar för att konfigurera Microsoft 365 med valfri domänregistrator](../admin/get-help-with-domains/change-nameservers-at-any-domain-registrar.md). 

    - Om du har befintliga DNS-poster, t. ex. en befintlig webbplats, men din DNS-värd är aktiverad för [Domain Connect](/office365/admin/get-help-with-domains/domain-connect)väljer du **Lägga till poster för mig**. På sidan **Välj onlinetjänster** accepterar du alla standardinställningar och väljer **Nästa** och väljer **Auktorisera** på DNS-värdens sida.
    - Om du har befintliga DNS-poster med andra DNS-värdar (inte aktiverad för domänanslutning), ska du hantera dina egna DNS-poster för att se till att de befintliga tjänsterna fortsätter att vara anslutna. Mer information finns i [domängrunder](/office365/admin/get-help-with-domains/dns-basics).

        ![Sidan Aktivera poster.](../media/activaterecords.png)

2. Följ stegen i guiden så kommer e-postmeddelanden och andra tjänster att konfigureras åt dig.

### <a name="protect-your-organization"></a>Skydda din organisation 

Principerna som du skapar i guiden tillämpas automatiskt på säkerhetsgruppen [Alla](/office365/admin/create-groups/compare-groups#security-groups) *användare.* Du kan också skapa ytterligare grupper att tilldela principer till i administrationscentret.

1. Om du vill öka skyddet mot avancerade **cyberhot** rekommenderar vi att du accepterar standardinställningarna för att [låta Office 365 Advance Threat Protection](../security/office-365-security/defender-for-office-365.md) söka igenom filer och länkar i Office appar.

    ![Skärmbild av sidan Öka skydd.](../media/increasetreatprotection.png)


2. På sidan Förhindra läckage av känsliga **data** godkänner du standardinställningarna för att aktivera Office 365 Skydd mot dataförlust (DLP) för att spåra känsliga data i Office-appar och förhindra oavsiktlig delning av dessa utanför organisationen.

3. På sidan **Skydda data i Office** för mobila enheter lämnar du hantering av mobilappar på, expanderar inställningarna och granskar dem och väljer sedan Skapa policy för hantering av **mobilappar.**

    ![Skärmbild av Skydda data i Office för mobil.](../media/protectdatainmobile.png)


## <a name="secure-windows-10-pcs"></a>Skydda Windows 10-datorer

Välj Konfigurera i det vänstra **navigeringsfältet** och välj sedan Skydda dina **e-Windows 10** under **Inloggning och säkerhet.** Kom **igång genom** att välja Visa. Se [Skydda Windows 10 för](secure-win-10-pcs.md) fullständiga instruktioner.

## <a name="deploy-office-365-client-apps"></a>Distribuera Office 365-klientprogram

Om du väljer att installera Office-appar automatiskt under installationen installeras apparna på Windows 10-enheterna när användarna har loggat in i Azure AD från sina Windows-enheter med sina arbetsautentiseringsuppgifter.

Information om Office för mobila iOS- och Android-enheter finns i [Konfigurera mobila enheter för Microsoft 365 Business Premium användare.](set-up-mobile-devices.md)

Du kan också installera Office individuellt. Anvisningar finns Office installera på en PC eller [Mac.](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)

## <a name="see-also"></a>Se även

[Utbildningsvideor för Microsoft 365 Business](../business-video/index.yml)
