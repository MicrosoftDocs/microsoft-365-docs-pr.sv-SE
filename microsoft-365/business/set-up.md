---
title: Konfigurera Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
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
ms.openlocfilehash: e635b828609fc47cd8b92bb179a25bcc43cb0a1a
ms.sourcegitcommit: db1dfb2df2c2f7beced3b57bc772d106c189e88a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2019
ms.locfileid: "33660908"
---
# <a name="set-up-microsoft-365-business"></a>Konfigurera Microsoft 365 Business

Innan du börjar [Hämta Microsoft 365 Business](get-microsoft-365-business.md) anmälan information finns.

Titta på en [kort video om hur du konfigurerar Microsoft 365 Business](https://support.office.com/article/38003e30-9d10-44cf-b596-f1b5f662bfa1) med uppsättningen upp guiden och du inte har en lokal Active Directory
  

## <a name="overview"></a>Översikt

Kan du göra de flesta av stegen i guiden, men andra alternativ finns.

1. [Lägg till din domän](#add-your-domain-to-personalize-sign-in) (om du har köpt din domän under [registrera](sign-up.md)görs redan det här steget.)
2. Lägg till användare. Du kan göra detta på något av tre sätt:
    - I [installationsguiden](#add-users-in-the-wizard).
    - Använda katalogsynkronisering för att [lägga till användare med hjälp av Azure AD Connect](#add-users-by-using-azure-ad-connect) om du har en lokal Active directory.
    - Du kan också [lägga till användare senare](add-users-m365b.md) i administratörscenter.
3. Ställa in IPSec-principer och konfigurera enheter. Du kan göra detta på något av tre sätt:
    - I [installationsguiden](#set-up-policies-in-the-wizard).  
    - I [administratörscenter](#modify-or-add-policies-in-the-admin-center).
    - I [Intune administratörscenter](https://docs.microsoft.com/intune/what-is-device-management).
4. Ställ in och hantera Windows 10 enheter.

    När du ansluter en enhet med WIndows 10 till Azure AD tillämpas alla principer den.
    - Ställa in Windows 10 enhetskonfigurationer i [installationsguiden](#set-up-policies-in-the-wizard).
    - Ansluta till en [ny enhet med Windows 10](set-up-windows-devices.md#for-a-brand-new-or-newly-upgraded-windows-10-pro-device) till Azure AD.
    - Ansluta till en [befintlig Windows 10-enhet](set-up-windows-devices.md#for-a-device-already-set-up-and-running-windows-10-pro) till Azure AD.
1. Installera Office 365 Business.
    - Du kan automatiskt installera Office i Windows-enheter med hjälp av [installationsguiden](#set-up-policies-in-the-wizard).
    - Automatiskt [installera Office](auto-install-or-uninstall-office.md) admin Center.
    - Låt användarna [installera Office apps](https://docs.microsoft.com/office365/admin/setup/install-applications) för Windows och enheter.
     
1. Ställ in ytterligare säkerhet.
    - Guiden lägger till principer för att säkra dina enheter, men du kan också dra nytta av [ytterligare](#additional-security-settings) säkerhetsfunktioner till hjälper till att säkra data, konton och e-post. 

## <a name="add-your-domain-users-and-set-up-policies"></a>Lägg till din domän, användare och konfigurera principer

![Banderoll som pekar på https://aka.ms/aboutM365preview.](media/m365admincenterchanging.png)

När du köper Microsoft 365 Business har du möjlighet att använda en domän som du äger eller köpa något under den [anmälan](sign-up.md).

- Om du har köpt en ny domän när du har registrerat din domän är alla upp och det går att [lägga till användare](#add-users-and-assign-licenses)och tilldela licenser.

### <a name="add-your-domain-to-personalize-sign-in"></a>Lägg till din domän om du vill anpassa logga in

1. Logga in på [Microsoft 365 administratörscenter](https://admin.microsoft.com) med global administration-referenser. 

2. Välj **Lägg till en domän** för att starta guiden.

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
Om du har en lokal domänkontrollant och använder Active Directory, kan du se [hur du ddd användare med Azure AD Connect](#add-users-by-using-azure-ad-connect).

![Skärmbild av sidan Lägg till nya användare i guiden](media/addnewuserspage.png)

1. Om ditt Microsoft 365 Business-abonnemang har befintliga användare (till exempel om du använde Azure AD Connect), får du möjlighet att tilldela licenser till dem nu. Lägg till licenser till dem också.

3. När du har lagt till användare kan få du också möjlighet att dela referenser med nya användare som du har lagt till. Du kan välja att skriva ut, e-posta eller ladda ned.

4. Hoppa över steget att föra över e-postmeddelanden och välj **Nästa** på sidan **Migrera e-postmeddelanden**. 

    Om du flyttar från en annan leverantör av e-post och vill kopiera data senare, kan du [migrera e-post och kontakter till Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).

#### <a name="add-users-by-using-azure-ad-connect"></a>Lägga till användare med hjälp av Azure AD Anslut

 Om du har en lokal domänkontrollant med Active Directory kan synkronisera du användarna med Microsoft 365 Business [Azure AD Anslut](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express). Komplettera detta innan du startar guiden. Du kan hämta det i administratörscenter:

- Gå till **användare** \> **aktiva användare**, Välj punkter högst upp på sidan och välj sedan **katalogsynkronisering** hämta Azure AD Anslut.

    ![Välj punkter > Directory snchronization på sidan aktiv användare.](media/setupdirsync.png)

    > [!IMPORTANT]
    > Om du skapar användare på det här sättet har du fortfarande tilldela licenser till dem i administratörscenter.

##### <a name="continue-to-access-domain-joined-apps-and-devices"></a>Fortsätta använda domänanslutna appar och enheter

Om du vill fortsätta använda domänanslutna appar och enheter läser du följande artiklar för två olika sätt att aktivera som:
  
- [Aktivera domänanslutna Windows 10-enheter för hantering i Microsoft 365 Business](manage-windows-devices.md)
    - Detta är det rekommenderade sättet.

- [Åtkomst på lokala resurser från en Azure AD-ansluten enhet i Microsoft 365 Business](access-resources.md)

### <a name="connect-your-domain"></a>Koppla din domän

> [!NOTE]
> Om du väljer att använda .onmicrosoft-domän eller Azure AD Anslut används för att ställa in användare, visas inte det här steget.
  
För att få igång tjänsten måste du uppdatera några poster hos din DNS-värd eller domänregistrator.
  
1. Installationsguiden identifierar normalt din domänregistrator och ger dig en länk till stegvisa instruktioner för att uppdatera dina NS-poster på registratorns webbplats. Om den inte [Ändra nameservers att ställa in Office 365 med något domänregistrerare](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2). 

    - Om du har en befintlig DNS-poster, till exempel en befintlig webbplats, kommer du vill hantera dina egna DNS-poster så att befintliga tjänster vara ansluten. Se [domän grunderna](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) för mer information.

        ![Anslut din domän med jag ska hantera min egen DNS-poster.](media/connectyourdomainpage.png)

2. Följ instruktionerna i guiden och e-post och andra tjänster kan ställas in för dig.

### <a name="set-up-security-policies-and-device-configurations"></a>Ställa in IPSec-principer och enhetskonfigurationer 

Dessa principer gäller alla användare som du ger en licens till, eller en grupp av användare om du vill tilldela olika principer för en användare.

#### <a name="set-up-policies-in-the-wizard"></a>Ställ in policyer i guiden

De principer som angetts i guiden används automatiskt till en [säkerhetsgrupp](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) som kallas för *Alla användare*.

1. På den **skydda ditt arbete filer på mobila enheter** alternativet är **skydda arbetsfält när enheter försvinner eller blir stulen** markerad som standard. Har du möjlighet att aktivera **hantera hur användare kan komma åt Office-filer på mobila enheter**, och detta rekommenderas.

    ![Skärmbild av skydda arbetsfält på sidan mobila enheter.](media/protectworkfilesondevices.png)

     - Om du expanderar **skydda arbetsfält när enheter försvinner eller blir stulen**är det förvalda [standardvärden](protect-work-files-on-lost-or-stolen-device.md) :

        ![Skärmbild av standardvärden för att skydda filer på enheter som förlorade.](media/protectworkfilesondevicesdefault.png)

    - Om du väljer att **hantera hur användare kan komma åt Office-filer på mobila enheter** och expandera den visas [standardvärden](manage-user-access-on-mobile-devices.md) . Vi rekommenderar att du godkänner standardvärdena vid installationen för att skapa programprinciper för alla användare i Android, iOS och Windows 10. Du kan skapa fler principer när installationen har slutförts.

        ![Skärmbild av skyddsinställningarna för mobile Office-filer.](media/useraccessonmobile.png)

2. Det sista steget för att skydda data och enheter kan du ställa in principer för att säkra Windows 10 enheter. Dessa inställningar används automatiskt när en användare Windows 10 ansluter till din organisation. Du kan expandera **skydda Windows-10 enheter** för att se och ändra [standardvärdena](secure-windows-10-devices.md).
3. Du kan också välja att [automatiskt installera Office](install-office-on-windows-10-during-setup.md) på Windows 10 enheter.

    ![Skärmbild av ange konfigurationssidan för Windows 10-enhet.](media/setwin10config.png)

#### <a name="modify-or-add-policies-in-the-admin-center"></a>Ändra eller lägga till principer i administratörscenter

Se [Hantera Microsoft 365 Business](manage.md) för länkar till avsnitt om hur du visar och ändrar enhet och app skydd principer och ta bort data från eller återställa användarenhet.

## <a name="deploy-and-manage-windows-10"></a>Distribuera och hantera Windows 10
Se [ställa in Windows-enheter för Microsoft 365 företagsanvändare](set-up-windows-devices.md) manuellt ansluta till Azure AD, antingen under installationen för nya datorer eller genom att ändra profil logga in för befintliga datorer. 

### <a name="use-autopilot-to-set-up-new-devices"></a>Använda Autopilot för att skapa nya enheter

Du kan använda [Windows Autopilot](add-autopilot-devices-and-profile.md) före automatiskt konfigurera **nya** Windows 10-enheter för en användare, men kan det vara enklare att få en [partner](https://www.microsoft.com/solution-providers/search) som kan göra detta åt dig. Du kan också gå till [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598) och be en expert moln teknik skapa nya enheter du köper du.

### <a name="access-on-premises-resources"></a>Komma åt lokala resurser

Om organisationen använder Windows Server Active Directory på lokaler, kan du ställa in Microsoft 365 Business att skydda din Windows 10-enheter, men fortfarande åtkomst till lokala resurser som kräver autentisering med lokala. Följ stegen i [Aktivera domänanslutna Windows 10-enheter som ska hanteras av Microsoft 365 Business](manage-windows-devices.md) att ställa in. Detta är den bästa metoden och enheter i det här tillståndet kallas Hybrid Azure AD anslutna enheter.

Om ditt företag har en lokal Active Directory som innehåller vissa lokala resurser (till exempel filresurser och skrivare), du kan ge din Azure AD-anslutna enheter åtkomst till dessa resurser genom att följa instruktionerna här: [Access lokal resurser från en Azure AD-ansluten enhet i Microsoft 365 Business](access-resources.md).

## <a name="deploy-office-365-client-apps"></a>Distribuera Office 365-klientprogram

Om du väljer att automatiskt installera Office apps i under uppsättningen upp installera apparna på Windows 10-enheter, när användaren har loggat in på Azure AD från sina Windows-enheter med sina autentiseringsuppgifter för arbete.
Om du vill installera Office på mobila iOS- eller Android-enheter finns i [Konfigurera mobila enheter för Microsoft 365 företagsanvändare](set-up-mobile-devices.md).

Du kan också installera Office individuellt. Se [installera Office på en PC eller Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc471665) för instruktioner.

## <a name="additional-security-settings"></a>Ytterligare säkerhetsinställningar

Förutom säkerhet och regelefterlevnad inställning i guiden kan du också ange följande inställningar:
  
- **Skydd mot skadlig programvara för e-post**
- **Avancerade hot skydd (ATP) säkra bifogade filer**
- **ATP-Safe länkar**
- **STORGATAN anti-phishing**
- **Exchange Online - arkivering**
- **Förhindra dataförlust (DLP)**
- **Azure informationsskydd** (Plan 1)
- **Intune portal tillgänglighet**

Att komma igång finns i [ställa in avancerade IPSec-principer](set-up-advanced-security.md).

Se även [top 10 sätt att skydda verksamheten Microsoft 365](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) för en översikt av bästa säkerhetspraxis.