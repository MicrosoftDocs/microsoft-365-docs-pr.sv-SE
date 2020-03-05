---
title: Konfigurera Microsoft 365 Business
f1.keywords:
- NOCSH
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
- MARVEL_SEO_MAR
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Upptäck installationsstegen för Microsoft 365 Business, inklusive att lägga till en domän och användare, konfigurera säkerhetsprinciper med mera.
ms.openlocfilehash: 4535a32b579b91b6c2bb0e64ec95904be6c08fce
ms.sourcegitcommit: d6c871bf3f94d9299d22695f5dbaf25dc1bd6ff9
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/05/2020
ms.locfileid: "42417305"
---
# <a name="set-up-microsoft-365-business-in-the-setup-wizard"></a>Konfigurera Microsoft 365 Business i installationsguiden

Titta på det här videoklippet för en översikt över microsoft 365 Business-installationen.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSM] 

Om den här videon har hjälpt dig kan du ta en titt på den [fullständiga utbildningsserien för småföretag och nya användare av Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

## <a name="add-your-domain-users-and-set-up-policies"></a>Lägga till dina domän-, användare och konfigurera principer

[![Etikett som gör att du kan se att administrationscentret ändras och mer information finns på aka.ms/aboutM365preview.](../media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)

När du köper Microsoft 365 Business har du möjlighet att använda en domän som du äger eller köpa en under [registreringen](sign-up.md).

- Om du har köpt en ny domän när du registrerade dig konfigureras domänen och du kan flytta till Lägg till [användare och tilldela licenser](#add-users-and-assign-licenses).

### <a name="add-your-domain-to-personalize-sign-in"></a>Lägga till din domän för att anpassa inloggning

1. Logga in på [Administrationscenter för Microsoft 365](https://admin.microsoft.com) med hjälp av dina globala administratörsautentiseringsuppgifter. 

2. Välj **Gå till installationsprogrammet** för att starta guiden.

    ![Välj Gå till installationsprogrammet.](../media/gotosetupinadmincenter.png)

3. På sidan **Installera office-appar** kan du eventuellt installera apparna på din egen dator.
    
4. Ange **** det domännamn som du vill använda (som contoso.com).

    > [!IMPORTANT]
    > Om du har köpt en domän under registreringen visas inte **Lägg till ett domänsteg** här. Gå till Lägg till [användare](#add-users-and-assign-licenses) i stället.

    ![Skärmbild av inloggningssidan Anpassa din.](../media/adddomain.png)

    
4. Följ stegen i guiden för att [skapa DNS-poster hos alla DNS-värdleverantörer för Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) som verifierar att du äger domänen. Om du känner till domänvärden läser du även [värdspecifika instruktioner](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).

    Om din värdleverantör är GoDaddy eller en annan värd aktiverad med [domänanslutning](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect)är processen enkel och du blir automatiskt ombedd att logga in och låta Microsoft autentisera för din räkning.

    ![På GoDaddy Confirm Access-sidan väljer du Auktorisera.](../media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a>Lägga till användare och tilldela licenser

Du kan lägga till användare i guiden, men du kan också [lägga till användare senare](add-users-m365b.md) i administrationscentret. Om du har en lokal domänkontrollant kan du dessutom lägga till användare med [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).

#### <a name="add-users-in-the-wizard"></a>Lägga till användare i guiden

Alla användare som du lägger till i guiden tilldelas automatiskt en Microsoft 365 Business-licens.

![Skärmbild av sidan Lägg till nya användare i guiden](../media/addnewuserspage.png)

1. Om din Microsoft 365 Business-prenumeration har befintliga användare (till exempel om du använde Azure AD Connect) får du möjlighet att tilldela licenser till dem nu. Lägg till licenser till dem också.

2. När du har lagt till användarna får du också ett alternativ för att dela autentiseringsuppgifter med de nya användare som du har lagt till. Du kan välja att skriva ut, e-posta eller ladda ned.

### <a name="connect-your-domain"></a>Koppla din domän

> [!NOTE]
> Om du väljer att använda .onmicrosoft-domänen eller använde Azure AD Connect för att konfigurera användare, ser du inte det här steget.
  
För att få igång tjänsten måste du uppdatera några poster hos din DNS-värd eller domänregistrator.
  
1. Installationsguiden identifierar normalt din domänregistrator och ger dig en länk till stegvisa instruktioner för att uppdatera dina NS-poster på registratorns webbplats. Om den inte gör [det ändrar du namnservrar för att konfigurera Office 365 med någon domänregistrator](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2). 

    - Om du har befintliga DNS-poster, till exempel en befintlig webbplats, men DNS-värden är aktiverad för [domänanslutning](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect)väljer du **Lägg till poster åt mig**. På sidan **Välj dina onlinetjänster** accepterar du alla standardvärden och väljer **Nästa**och väljer **Auktorisera** på DNS-värdens sida.
    - Om du har befintliga DNS-poster med andra DNS-värdar (inte aktiverat för domänanslutning) vill du hantera dina egna DNS-poster för att se till att de befintliga tjänsterna förblir anslutna. Se grunderna för [domänen](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) för mer information.

        ![Aktivera postsidan.](../media/activaterecords.png)

2. Följ stegen i guiden och e-post och andra tjänster kommer att ställas in åt dig.

### <a name="protect-your-organization"></a>Skydda din organisation 

De principer som du ställer in i guiden tillämpas automatiskt på en [säkerhetsgrupp](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) som heter *Alla användare*. Du kan också skapa ytterligare grupper som kan tilldela principer till i administrationscentret.

1. När det gäller **öka skyddet mot avancerade cyberhot**rekommenderas att du accepterar standarderna så att Office [365 Advance Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) skannar filer och länkar i Office-appar.

    ![Skärmbild av sidan Öka skydd.](../media/increasetreatprotection.png)


2. På sidan **Förhindra läckor av känsliga data** accepterar du standardvärdena för att aktivera Office 365 Data Loss Prevention (DLP) för att spåra känsliga data i Office-appar och förhindra oavsiktlig delning av dessa utanför organisationen.

3. Lämna hantering av **mobilappar på sidan Skydda data i Office för mobil,** expandera inställningarna och granska dem och välj sedan **Skapa hanteringsprincip**för mobilappar .

    ![Skärmbild av Skydda data i Office för mobilsida.](../media/protectdatainmobile.png)


## <a name="secure-windows-10-pcs"></a>Säkra Windows 10-datorer

Välj **Konfigurera installationsprogrammet** till vänster och väljer sedan **Skydda dina Windows 10-datorer**under **Sing-in och säkerhet.** Välj **Visa** för att komma igång. Se [skydda dina Windows 10-datorer](secure-win-10-pcs.md) för fullständiga instruktioner.

## <a name="deploy-office-365-client-apps"></a>Distribuera Office 365-klientappar

Om du väljer att installera Office-appar automatiskt under installationen installeras apparna på Windows 10-enheterna när användarna har loggat in på Azure AD från sina Windows-enheter med hjälp av sina arbetsuppgifter.

Information om hur du installerar Office på mobila iOS- eller Android-enheter finns i [Konfigurera mobila enheter för Microsoft 365 Business-användare](set-up-mobile-devices.md).

Du kan också installera Office individuellt. Se [installera Office på en PC eller Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658) för instruktioner.

## <a name="see-also"></a>Se även

[Utbildningsvideor för Microsoft 365 Business](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
