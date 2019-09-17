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
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Läs om hur du konfigurerar Microsoft 365 Business.
ms.openlocfilehash: 1efb7379930f639cf10875cf5aa6731001bb41c8
ms.sourcegitcommit: 2e5ae52bb641ee1f72c077260b5d0f35622935fe
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/17/2019
ms.locfileid: "37005207"
---
# <a name="set-up-microsoft-365-business-in-the-setup-wizard"></a>Konfigurera Microsoft 365 Business i installationsguiden

## <a name="add-your-domain-users-and-set-up-policies"></a>Lägg till din domän, användare och Ställ in policyer

![Banderoll som pekar https://aka.ms/aboutM365previewpå.](media/m365admincenterchanging.png)

När du köper Microsoft 365 Business har du möjlighet att använda en domän som du äger eller köpa en under [registreringen](sign-up.md).

- Om du har köpt en ny domän när du registrerade dig, är din domän alla inställd och du kan flytta för att [lägga till användare och tilldela licenser](#add-users-and-assign-licenses).

### <a name="add-your-domain-to-personalize-sign-in"></a>Lägg till din domän för att anpassa inloggningen

1. Logga in på [Microsoft 365 administratörscenter](https://admin.microsoft.com) med hjälp av autentiseringsuppgifterna för global administratör. 

2. Välj **Lägg till en domän** eller **Lägg till användare** för att starta guiden.
    > [!IMPORTANT]
    > Om du har köpt en domän under registreringen kommer du inte att se **Lägg till ett domän** steg här. Gå till [Lägg till användare](#add-users-and-assign-licenses) i stället.

    ![Välj Lägg till en domän.](media/addadomainadmincenter.png)
    
3. I guiden anger du det domännamn du vill använda (som contoso.com).


    ![Skärmbild av anpassa din inloggningssida.](media/personalizesignin.png)

    
4. Följ stegen i guiden för att [Skapa DNS-poster hos valfri DNS-Värdleverantör för Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) som verifierar att du äger domänen. Om du känner till din domänvärd, se även [värdspecifika instruktioner](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).

    Om din webbhotellsleverantör är GoDaddy, eller en annan värd som är aktiverad med [domänanslutning](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), är processen enkel och du kommer automatiskt att bli ombedd att logga in och låta Microsoft autentisera för din räkning:

    ![På GoDaddy bekräfta åtkomstsidan, Välj Auktorisera.](media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a>Lägga till användare och tilldela licenser

Du kan lägga till användare i guiden, men du kan också [lägga till användare senare](add-users-m365b.md) i administratörscenter. Om du har en lokal domänkontrollant kan du dessutom lägga till användare med [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).

#### <a name="add-users-in-the-wizard"></a>Lägga till användare i guiden

Alla användare som du lägger till i guiden tilldelas automatiskt en Microsoft 365 Business-licens.

![Skärmbild av sidan Lägg till nya användare i guiden](media/addnewuserspage.png)

1. Om din Microsoft 365 Business-prenumeration har befintliga användare (till exempel om du har använt Azure AD Connect), får du ett alternativ för att tilldela licenser till dem nu. Lägg till licenser till dem också.

3. När du har lagt till användarna får du också ett alternativ för att dela autentiseringsuppgifter med de nya användare som du har lagt till. Du kan välja att skriva ut, e-posta eller ladda ned.

4. Hoppa över steget att föra över e-postmeddelanden och välj **Nästa** på sidan **Migrera e-postmeddelanden**. 

    Om du flyttar från en annan e-postleverantör och vill kopiera dina data senare kan du [migrera e-post och kontakter till Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).


### <a name="connect-your-domain"></a>Koppla din domän

> [!NOTE]
> Om du väljer att använda den. onmicrosoft domän eller används Azure AD Connect för att ställa in användare, kommer du inte att se det här steget.
  
För att få igång tjänsten måste du uppdatera några poster hos din DNS-värd eller domänregistrator.
  
1. Installationsguiden identifierar normalt din domänregistrator och ger dig en länk till stegvisa instruktioner för att uppdatera dina NS-poster på registratorns webbplats. Om den inte gör det [ändrar du namnservrar till konfigurera Office 365 med alla domänregistratorn](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2). 

    - Om du har befintliga DNS-poster, till exempel en befintlig webbplats, men DNS-värden har aktiverats för [domänanslutning](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), väljer du **Lägg till poster åt mig**. 
    - Om du har befintliga DNS-poster med andra DNS-värdar (inte aktiverat för domänanslutning), kommer du att vilja hantera dina egna DNS-poster för att se till att de befintliga tjänsterna förblir anslutna. Mer information finns i [grunderna om domäner](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) .

        ![Anslut din domän sida med jag ska hantera mina egna DNS-poster.](media/connectyourdomainpage.png)

2. Följ stegen i guiden och e-post och andra tjänster kommer att ställas in för dig.

### <a name="set-up-security-policies-and-device-configurations"></a>Ställ in säkerhetsprinciper och enhetskonfigurationer 

De principer som du ställer in i guiden tillämpas automatiskt på en [säkerhetsgrupp](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) som kallas *alla användare*. Du kan också skapa ytterligare grupper för att tilldela principer till i administratörscenter.

1. På **skydda dina arbetsfiler på mobila enheter** alternativet **skydda arbetsfiler när enheter förloras eller stjäls** är markerad som standard. Du har möjlighet att aktivera **hantera hur användare får åtkomst till Office-filer på mobila enheter**, och detta rekommenderas.

    ![Skärmbild av skydda jobbfiler på sidan mobila enheter.](media/protectworkfilesondevices.png)

     - Expandera **skydda arbetsfiler när enheter förloras eller stjäls** för att visa [standardvärdena](protect-work-files-on-lost-or-stolen-device.md):

        ![Skärmbild av standardvärden för att skydda filer på borttappade enheter.](media/protectworkfilesondevicesdefault.png)

    - Välj **hantera hur användare öppnar Office-filer på mobila enheter** och expandera den för att visa [standardvärdena](manage-user-access-on-mobile-devices.md). Vi rekommenderar att du accepterar standardvärdena under installationen för att skapa användningsprinciper för Android, iOS och Windows 10 som gäller för alla användare. Du kan skapa fler principer när installationen har slutförts.

        ![Skärmbild av skyddsinställningar för Office-filer på mobilen.](media/useraccessonmobile.png)

2. Det sista steget på skydda data och enheter kan du ställa in principer för att skydda Windows 10-enheter. Dessa inställningar tillämpas automatiskt när en användares Windows 10 ansluts till din organisation. Du kan expandera **säkra Windows 10-enheter** för att visa och ändra [standardvärdena](secure-windows-10-devices.md).
3. Du kan också välja att [automatiskt installera Office](install-office-on-windows-10-during-setup.md) på Windows 10-enheter.

    ![Skärmbild av Ställ in konfigurationssidan för Windows 10-enhet.](media/setwin10config.png)



## <a name="deploy-office-365-client-apps"></a>Distribuera Office 365-klientappar

Om du väljer att automatiskt installera Office-appar i under installationen installeras apparna på Windows 10-enheterna när användarna har loggat in på Azure AD från sina Windows-enheter med sina arbetsuppgifter.
Om du vill installera Office på mobila iOS-eller Android-enheter läser [du konfigurera mobila enheter för Microsoft 365 företagsanvändare](set-up-mobile-devices.md).

Du kan också installera Office individuellt. Mer information finns i [installera Office på en PC eller Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658) .
