---
title: Konfigurera Microsoft 365 Business Premium
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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Upptäck installationsstegen för Microsoft 365 Business Premium, inklusive att lägga till en domän och användare, konfigurera säkerhetsprinciper med mera.
ms.openlocfilehash: 89186fbd00e47385f0320c45f7fc44c258742aa3
ms.sourcegitcommit: e5bc49f0a25954d008b6cc09c2b98bb7bfe1aa2f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785706"
---
# <a name="set-up-microsoft-365-business-premium-in-the-setup-wizard"></a>Konfigurera Microsoft 365 Business Premium i installationsguiden

Titta på det här videoklippet om du vill ha en översikt över installationen av Microsoft 365 Business Premium.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSM] 

Om den här videon har hjälpt dig kan du ta en titt på den [fullständiga utbildningsserien för småföretag och nya användare av Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

## <a name="add-your-domain-users-and-set-up-policies"></a>Lägga till domän, användare och konfigurera principer

När du köper Microsoft 365 Business Premium kan du välja att använda en domän som du äger eller köpa en domän under [registreringen.](sign-up.md)

- Om du köpte en ny domän när du registrerade dig är domänen konfigurerad och du kan flytta till [Lägg till användare och tilldela licenser](#add-users-and-assign-licenses).

### <a name="add-your-domain-to-personalize-sign-in"></a>Lägga till din domän för att anpassa inloggningen

1. Logga in på [Microsoft 365 administrationscenter](https://admin.microsoft.com) med hjälp av dina globala administratörsuppgifter. 

2. Välj **Gå till installation för** att starta guiden.

    ![Välj Gå till installation.](../media/gotosetupinadmincenter.png)

3. På sidan **Installera dina Office-appar** kan du också installera apparna på din egen dator.
    
4. I steget **Lägg till domän** anger du det domännamn som du vill använda (t.ex. contoso.com).

    > [!IMPORTANT]
    > Om du köpte en domän under registreringen visas inte **Lägg till ett domänsteg** här. Gå till [Lägg till användare](#add-users-and-assign-licenses) i stället.

    ![Skärmbild av sidan Anpassa din inloggning.](../media/adddomain.png)

    
4. Följ stegen i guiden för att [skapa DNS-poster hos alla DNS-värdar för Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) som verifierar att du äger domänen. Om du känner till domänvärden läser du även [värdspecifika instruktioner](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).

    Om din värd är GoDaddy eller en annan värd aktiverad med [domänanslutning](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect)är processen enkel och du blir automatiskt ombedd att logga in och låta Microsoft autentisera för din räkning.

    ![På GoDaddy Confirm Access-sidan väljer du Auktorisera.](../media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a>Lägga till användare och tilldela licenser

Du kan lägga till användare i guiden, men du kan också [lägga till användare senare](add-users-m365b.md) i administrationscentret. Om du har en lokal domänkontrollant kan du dessutom lägga till användare med [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).

#### <a name="add-users-in-the-wizard"></a>Lägga till användare i guiden

Alla användare som du lägger till i guiden tilldelas automatiskt en Microsoft 365 Business Premium-licens.

![Skärmbild av sidan Lägg till nya användare i guiden](../media/addnewuserspage.png)

1. Om din Microsoft 365 Business Premium-prenumeration har befintliga användare (till exempel om du använde Azure AD Connect) får du ett alternativ för att tilldela licenser till dem nu. Lägg till licenser till dem också.

2. När du har lagt till användarna får du också ett alternativ för att dela autentiseringsuppgifter med de nya användarna som du har lagt till. Du kan välja att skriva ut, e-posta eller ladda ned.

### <a name="connect-your-domain"></a>Koppla din domän

> [!NOTE]
> Om du väljer att använda .onmicrosoft-domänen eller använde Azure AD Connect för att konfigurera användare, visas inte det här steget.
  
För att få igång tjänsten måste du uppdatera några poster hos din DNS-värd eller domänregistrator.
  
1. Installationsguiden identifierar normalt din domänregistrator och ger dig en länk till stegvisa instruktioner för att uppdatera dina NS-poster på registratorns webbplats. Om den inte gör det [ändrar du namnservrar för att konfigurera Office 365 med någon domänregistrare](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar). 

    - Om du har befintliga DNS-poster, till exempel en befintlig webbplats, men DNS-värden är aktiverad för [domänanslutning,](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect)väljer **du Lägg till poster åt mig**. På sidan **Välj dina onlinetjänster** godkänner du alla standardinställningar och väljer **Nästa**och väljer **Auktorisera** på DNS-värdens sida.
    - Om du har befintliga DNS-poster med andra DNS-värdar (inte aktiverat för domänanslutning) vill du hantera dina egna DNS-poster för att se till att de befintliga tjänsterna förblir anslutna. Mer information finns i grunderna för [domänen.](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics)

        ![Aktivera arkivtabell.](../media/activaterecords.png)

2. Följ stegen i guiden och e-post och andra tjänster kommer att ställas in åt dig.

### <a name="protect-your-organization"></a>Skydda din organisation 

De principer som du ställer in i guiden tillämpas automatiskt på en [säkerhetsgrupp](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) som heter *Alla användare*. Du kan också skapa ytterligare grupper som du kan tilldela principer till i administrationscentret.

1. När det **gäller öka skyddet mot avancerade cyberhot**rekommenderar vi att du accepterar standardinställningarna för att låta Office [365 Advance Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) söka igenom filer och länkar i Office-appar.

    ![Skärmbild av sidan Öka skydd.](../media/increasetreatprotection.png)


2. På sidan **Förhindra läckor av känsliga data** accepterar du standardinställningarna för att aktivera Office 365 Data Loss Prevention (DLP) för att spåra känsliga data i Office-appar och förhindra oavsiktlig delning av dessa utanför organisationen.

3. På sidan Skydda data på sidan **Skydda data i Office för mobil** lämnar du hanteringen av mobilappar på, expanderar inställningarna och granskar dem och väljer sedan Skapa princip för hantering av **mobilappar**.

    ![Skärmbild av Skydda data på sidan Skydda data för mobila kontor.](../media/protectdatainmobile.png)


## <a name="secure-windows-10-pcs"></a>Säkra Windows 10-datorer

På den vänstra navigeringsfältet väljer du **Installationsprogrammet** och väljer sedan **Skydda dina Windows 10-datorer**under **Inloggning och säkerhet**. Välj **Visa** för att komma igång. Se [säkra dina Windows 10-datorer](secure-win-10-pcs.md) för fullständiga instruktioner.

## <a name="deploy-office-365-client-apps"></a>Distribuera Office 365-klientappar

Om du väljer att automatiskt installera Office-appar under installationen installeras apparna på Windows 10-enheterna när användarna har loggat in på Azure AD från sina Windows-enheter med hjälp av deras arbetsuppgifter.

Om du vill installera Office på mobila iOS- eller Android-enheter finns i [Konfigurera mobila enheter för Microsoft 365 Business Premium-användare](set-up-mobile-devices.md).

Du kan också installera Office individuellt. Instruktioner [finns i installera Office på en PC eller Mac.](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)

## <a name="see-also"></a>Se även

[Utbildningsvideor för Microsoft 365 Business](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
