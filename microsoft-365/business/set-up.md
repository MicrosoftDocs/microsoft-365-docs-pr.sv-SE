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
description: Lär dig hur du konfigurerar Microsoft 365 Business.
ms.openlocfilehash: ac9c8b828ff131a15bf057fa8bdc0bf56dd00987
ms.sourcegitcommit: 75b97d1ff617bc4b1b0ef9135dfe6a8842ea1b52
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/18/2019
ms.locfileid: "35772576"
---
# <a name="set-up-microsoft-365-business-in-the-setup-wizard"></a>Ställ in Microsoft 365 Business i installationsguiden

## <a name="add-your-domain-users-and-set-up-policies"></a>Lägga till din domän användare och konfigurera principer

![Banderoll som pekar på https://aka.ms/aboutM365preview.](media/m365admincenterchanging.png)

När du köper Microsoft 365 Business har du möjlighet att använda en domän som du äger eller köpa något under den [anmälan](sign-up.md).

- Om du har köpt en ny domän när du har registrerat din domän är alla upp och det går att [lägga till användare](#add-users-and-assign-licenses)och tilldela licenser.

### <a name="add-your-domain-to-personalize-sign-in"></a>Lägg till din domän om du vill anpassa logga in

1. Logga in på [Microsoft 365 administratörscenter](https://admin.microsoft.com) med global administration-referenser. 

2. Välj **Lägg till en domän** eller **lägga till användare** för att starta guiden.
    > [!IMPORTANT]
    > Om du har köpt en domän under registreringen kommer **inte se Lägg till en domän** steg här. Gå till [Lägg till användare](#add-users-and-assign-licenses) i stället.

    ![Välj Lägg till en domän.](media/addadomainadmincenter.png)
    
3. Ange det domännamn som du vill använda (till exempel contoso.com) i guiden.


    ![Skärmbild av Anpassa din inloggningssida.](media/personalizesignin.png)

    
4. Följ stegen i guiden för att [Skapa DNS-poster på en DNS-värd leverantör för Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) som verifierar att du äger domänen. Om du känner till din domän värd, se även [värd specifika instruktioner](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).

    Om din Internet-leverantör är GoDaddy, processen är enkel och uppmanas du automatiskt att logga in och låta Microsoft autentisera för din räkning:

    ![Välj auktorisera GoDaddy Bekräfta åtkomst på sidan.](media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a>Lägga till användare och tilldela licenser

Du kan lägga till användare i guiden, men du kan också [lägga till användare senare](add-users-m365b.md) i administratörscenter. Om du har en lokal domänkontrollant kan du dessutom lägga till användare med [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).

#### <a name="add-users-in-the-wizard"></a>Lägga till användare i guiden

Alla användare som du lägger till i guiden hämta tilldelas automatiskt en licens för Microsoft 365 Business.

![Skärmbild av sidan Lägg till nya användare i guiden](media/addnewuserspage.png)

1. Om din Microsoft 365 Business-prenumeration har befintliga användare (till exempel om du har använt Azure AD Anslut), får du ett alternativ för att tilldela licenser till dem nu. Lägg till licenser till dem också.

3. När du har lagt till användare kan få du också möjlighet att dela referenser med nya användare som du har lagt till. Du kan välja att skriva ut, e-posta eller ladda ned.

4. Hoppa över steget att föra över e-postmeddelanden och välj **Nästa** på sidan **Migrera e-postmeddelanden**. 

    Om du flyttar från en annan leverantör av e-post och vill kopiera data senare, kan du [migrera e-post och kontakter till Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).


### <a name="connect-your-domain"></a>Koppla din domän

> [!NOTE]
> Om du väljer att använda .onmicrosoft-domän eller Azure AD Anslut används för att ställa in användare, visas inte det här steget.
  
För att få igång tjänsten måste du uppdatera några poster hos din DNS-värd eller domänregistrator.
  
1. Installationsguiden identifierar normalt din domänregistrator och ger dig en länk till stegvisa instruktioner för att uppdatera dina NS-poster på registratorns webbplats. Om den inte [Ändra nameservers att ställa in Office 365 med något domänregistrerare](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2). 

    - Om du har en befintlig DNS-poster, till exempel en befintlig webbplats, kommer du vill hantera dina egna DNS-poster så att befintliga tjänster vara ansluten. Se [domän grunderna](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) för mer information.

        ![Anslut din domän med jag ska hantera min egen DNS-poster.](media/connectyourdomainpage.png)

2. Följ instruktionerna i guiden och e-post och andra tjänster kan ställas in för dig.

### <a name="set-up-security-policies-and-device-configurations"></a>Ställa in IPSec-principer och enhetskonfigurationer 

De principer som angetts i guiden används automatiskt till en [säkerhetsgrupp](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) som kallas för *Alla användare*. Du kan också skapa ytterligare grupper om du vill tilldela principer för admin Center.

1. På den **skydda ditt arbete filer på mobila enheter** alternativet är **skydda arbetsfält när enheter försvinner eller blir stulen** markerad som standard. Har du möjlighet att aktivera **hantera hur användare kan komma åt Office-filer på mobila enheter**, och detta rekommenderas.

    ![Skärmbild av skydda arbetsfält på sidan mobila enheter.](media/protectworkfilesondevices.png)

     - Expandera **skydda arbetsfält när enheterna är stulen eller** om du vill visa [standardvärden](protect-work-files-on-lost-or-stolen-device.md):

        ![Skärmbild av standardvärden för att skydda filer på enheter som förlorade.](media/protectworkfilesondevicesdefault.png)

    - Välj **hantera hur användare kan komma åt Office-filer på mobila enheter** och expandera den [standardvärden](manage-user-access-on-mobile-devices.md). Vi rekommenderar att du accepterar standardvärden under installationen för att skapa användningsprinciper för Android, iOS och Windows 10 som gäller för alla användare. Du kan skapa fler principer när installationen har slutförts.

        ![Skärmbild av skyddsinställningarna för mobile Office-filer.](media/useraccessonmobile.png)

2. Det sista steget för att skydda data och enheter kan du ställa in principer för att säkra Windows 10 enheter. Dessa inställningar används automatiskt när en användare Windows 10 ansluter till din organisation. Du kan expandera **skydda Windows-10 enheter** för att se och ändra [standardvärdena](secure-windows-10-devices.md).
3. Du kan också välja att [automatiskt installera Office](install-office-on-windows-10-during-setup.md) på Windows 10 enheter.

    ![Skärmbild av ange konfigurationssidan för Windows 10-enhet.](media/setwin10config.png)



## <a name="deploy-office-365-client-apps"></a>Distribuera Office 365-klientprogram

Om du väljer att automatiskt installera Office apps i under uppsättningen upp installera apparna på Windows 10-enheter, när användaren har loggat in på Azure AD från sina Windows-enheter med sina autentiseringsuppgifter för arbete.
Om du vill installera Office på mobila iOS- eller Android-enheter finns i [Konfigurera mobila enheter för Microsoft 365 företagsanvändare](set-up-mobile-devices.md).

Du kan också installera Office individuellt. Se [installera Office på en PC eller Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658) för instruktioner.
