---
title: Konfigurera Microsoft 365 Business med hjälp av installationsguiden
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
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Lär dig hur du konfigurerar Microsoft 365 Business genom att fylla i fyra steg.
ms.openlocfilehash: f57239b884bd2e186c0bc01973130a10fa4cfe84
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26982199"
---
# <a name="set-up-microsoft-365-business-by-using-the-setup-wizard"></a>Konfigurera Microsoft 365 Business med hjälp av installationsguiden

Slutför steg 1 – 4 nedan.
  
### <a name="set-up-microsoft-365-business"></a>Konfigurera Microsoft 365 Business

Titta på en video om hur du konfigurerar Microsoft 365 Business när du inte har en lokal Active Directory:
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/0705c337-f3e8-4d28-bb6c-530cd28e99f2?autoplay=false]
  
Installation steg innehåller information för inställningar som inkluderar lokala Active Directory. Om du vill fortsätta använda domänanslutna enheter läser följande artiklar för två olika sätt att aktivera som och slutför stegen innan du kör guiden:
  
- [Aktivera domänanslutna Windows 10-enheter för hantering i Microsoft 365 Business](manage-windows-devices.md)
    
    -Detta är det rekommenderade sättet.
    
- [Åtkomst på lokala resurser från en Azure AD-ansluten enhet i Microsoft 365 Business](access-resources.md)
    
### <a name="step-1-personalize-sign-in"></a>Steg 1: Anpassa logga in

1. Logga in på [Microsoft 365 Business](https://portal.microsoft.com) som global administratör. Välj panelen **Administratör** för att gå till administrationscentret. 
    
2. Välj **Påbörja installationen** (beroende på din region visas kanske **Fortsätt installationen** i stället) i administrationscentret för att starta guiden. 
    
3. Ange domännamnet du vill använda (t.ex. contoso.com).
    
    Gå vidare och ange din domän, även om du har verifierat när du använder Azure AD Connect, t.ex. Följande två steg gäller inte för dig om du har använt Azure AD Anslut för att verifiera din domän.
    
4. Följ stegen i guiden för att [Skapa DNS-poster på en DNS-värd leverantör för Office 365](https://support.office.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166) som verifierar att du äger domänen. 
    
    Du kan se en film som exempel [Video: installationsprogrammet för Office 365 i nya Admin Center](https://support.office.com/article/a8c2002a-34bc-4ab3-93d8-9b5156c48bf8). Observera att den här videon inte innehåller data protection stegen i Microsoft 365 Business.
    
    ![Screenshot of the Business Cloud Suite setup wizard.](media/3c4fd40c-2de1-4a87-8ee0-78d3928c7bb7.png)
  
### <a name="step-2-add-users-and-assign-licenses"></a>Steg 2: Lägga till användare och tilldela licenser

1. Du kan lägga till användare här eller också kan du [lägga till användare senare](add-users-m365b.md) i administratörscenter. 
    
    Alla användare tilldelas automatiskt en Microsoft 365 Business-licens.
    
2. Om ditt Microsoft 365 Business-abonnemang har befintliga användare (till exempel om du använde Azure AD Connect), får du möjlighet att tilldela licenser till dem nu. Lägg till licenser till dem också.
    
3. Du får också möjlighet att dela autentiseringsuppgifter med de nya användarna som du har lagt till. Du kan välja att skriva ut, e-posta eller ladda ned.
    
4. Hoppa över steget att föra över e-postmeddelanden och välj **Nästa** på sidan **Migrera e-postmeddelanden**. 
    
    Om du flyttar från en annan leverantör av e-post och vill kopiera data senare, kan du [migrera e-post och kontakter till Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).
    
    ![Screenshot of two new users added in the setup wizard](media/8f729967-5c65-4ceb-b737-18119db40564.png)
  
### <a name="step-3-connect-your-domain"></a>Steg 3: Anslut din domän

> [!NOTE]
> Om du väljer att använda .onmicrosoft-domän eller Azure AD Connect, visas inte det här steget. 
  
För att få igång tjänsten måste du uppdatera några poster hos din DNS-värd eller domänregistrator.
  
1. Installationsguiden identifierar domänregistreraren normalt och ger en länk till stegvisa instruktioner för uppdatering av NS-poster via webbplatsen justitiesekreterare. Om den inte [Ändra nameservers att ställa in Office 365 med något domänregistrerare](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).
    
2. E-post och andra tjänster konfigureras automatiskt
    
### <a name="step-4-manage-devices-and-work-files"></a>Steg 4: Hantera enheter och arbeta med filer

1. Sidan Ange på **skydda arbete filer på dina mobila enheter** **hantera hur användare kan komma åt Office-filer på mobila enheter** inställningar och **skydda arbete filer går förlorade eller stulna enheter** **på**. Du kan också använda varje underordnad inställning genom att klicka på sparrarna vid varje inställning.
  
  Alla licensierade användarnas arbete filer nu skyddas på iOS- och Android-enheter, så snart som de [installerar Office apps](set-up-mobile-devices.md) (och autentisera med sina autentiseringsuppgifter i Microsoft 365 Business). 
  
  ![Screenshot of protect work files on your mobile devices page](media/3139a9aa-6228-4e74-8166-c6a886d7319f.PNG)
  
2. På sidan **Ange Windows 10 enhetskonfigurationen** ställa **Säker Windows 10 enheter** **på**.
  
   Du kan också använda varje underordnad inställning genom att klicka på ikonen bredvid den.
  
3. Ange inställningen **Installera Office på Windows 10 enheter** till **Ja** om alla användare har Windows 10-datorer och inga befintliga Office installerar eller klicka-och-kör Office installeras. Om så inte är fallet kan du ange det här alternativet **Nej**. Du kan [installera Office automatiskt](auto-install-or-uninstall-office.md) senare från administratörscenter när du har förberett användarnas datorer. Instruktioner finns i [förbereda för installation av Office-klient](prepare-for-office-client-deployment.md).
  
    Licensierade användare arbetsfält på Windows 10 enheter kommer att projiceras så snart som de [ansluta sina Windows 10-enhet](set-up-windows-devices.md) till en Microsoft 365 Business Azure AD-domän eller [installera Windows 10 på en ny dator](https://support.office.com/article/c654bd23-d256-4ac7-8fba-0c993bf5a771.aspx) medan du samtidigt ansluta till Microsoft 365 Business Azure AD-domänen. 
  
4. Klicka på **Nästa** och du är klar med installationen. 
  
    Lämna oss feedback i det här steget för att hjälpa oss att förbättra upplevelsen.
  
    ![Screenshot of Prepare Windows 10 devices page](media/bff701c1-48a3-44f4-aa95-9d959d57c85b.PNG)
  
## <a name="additional-security-settings"></a>Ytterligare säkerhetsinställningar

Förutom säkerhet och regelefterlevnad inställning i guiden kan du också ange följande inställningar:
  
- Ställa in skydd mot osäkra bifogade filer. **Avancerat skydd** (ATP) identifierar skadligt innehåll och blockerar leverans av osäkra bifogade filer, skydda mot phishing system och ransomware infektioner. Om du vill aktivera skydd för bifogade filer finns i [ställa in principer för Office 365 ATP säkra bifogade filer](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775#setpolicy).
    
- Skydda när användaren klickar på skadliga länkar. ATP undersöker länkar i e-post när en användare klickar på dem.. Om en länk är osäkra, inte att besöka webbplatsen för användaren eller informeras om att webbplatsen har blockerats. Detta skyddar mot phishing system. [Konfigurera Office 365 ATP Safe länkar principer](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#reveddefaultscc) eller [Konfigurera Office 365 ATP Safe länkar principer](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#addemailpolscc).
    
- Du kan behålla alla innehållet inklusive borttagna objekt genom att infoga hela postlådan för en användare i en **rättstvist håller**. Instruktioner finns i 
- [Ställ in e-lagring med Exchange Online-arkivering](security-features.md#set-up-email-retention-with-exchange-online-archiving).
    
- Ställ in anpassade **principer för bevarande**, till exempel att bevara under en viss tid eller permanent ta bort innehåll i slutet av loggperioden. Du kan aktivera anpassade lagringsprinciper i regelefterlevnadscentret, gå till **Data-styre** och värdepapper \> **bevarande**och följ sedan stegen i guiden. Mer information finns i [Översikt över bevarandeprinciper](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).
    
## <a name="next-steps"></a>Nästa steg

För de användare som har licenser, är nästa steg att konfigurera enheter.<br/> Se [Konfigurera Windows-enheter för Microsoft 365 Business-användare](set-up-windows-devices.md) och [Konfigurera mobila enheter för Microsoft 365 Business-användare](set-up-mobile-devices.md). <br/>Se [Hantera Microsoft 365 Business](manage.md) för länkar till information om hur du anger enhets- och programskyddsprinciper och hur du tar bort data från användares enheter. 
  


