---
title: Konfigurera Windows-enheter för Microsoft 365 Business Premium-användare
f1.keywords:
- CSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- TRN_M365B
- OKR_SMB_Videos
- seo-marvel-mar
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
ms.assetid: 2d7ff45e-0da0-4caa-89a9-48cabf41f193
description: Lär dig konfigurera Windows-enheter med Windows 10 Pro för Microsoft 365 Business Premium-användare, aktivera centraliserad hantering och säkerhetskontroller.
ms.openlocfilehash: 9c9ffe5bd74d9e9877a87309757c481576ee89d2
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578136"
---
# <a name="set-up-windows-devices-for-microsoft-365-business-premium-users"></a>Konfigurera Windows-enheter för Microsoft 365 Business Premium-användare

## <a name="prerequisites-for-setting-up-windows-devices-for-microsoft-365-business-premium-users"></a>Krav för att konfigurera Windows-enheter för Microsoft 365 Business Premium-användare

Innan du kan konfigurera Windows-enheter för Microsoft 365 Business Premium-användare ska du se till att alla Windows-enheter använder Windows 10 Pro, version 1703 (Creators Update). Windows 10 Pro är en förutsättning för att använda Windows 10 Business, vilket är en uppsättning molntjänster och funktioner för enhetshantering som kompletterar Windows 10 Pro och ger tillgång till centraliserad hantering och säkerhetskontroller i Microsoft 365 Business Premium.
  
Om du har Windows-enheter med Windows 7 Pro, Windows 8 Pro eller Windows 8.1 Pro ger Microsoft 365 Business Premium-prenumerationen dig rätt att uppgradera till Windows 10.
  
Följ stegen i det här avsnittet för att få mer information om hur du uppgraderar Windows-enheter till Windows 10 Pro Creators Update: [Uppgradera Windows-enheter till Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).
  
Se [Kontrollera att enheten är ansluten till Azure AD för](#verify-the-device-is-connected-to-azure-ad) att kontrollera att du har uppgraderingen eller om uppgraderingen fungerade.

Titta på en kort video om hur du ansluter Windows till Microsoft 365.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3yXh3] 

Om den här videon har hjälpt dig kan du ta en titt på den [fullständiga utbildningsserien för småföretag och nya användare av Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).
  
## <a name="join-windows-10-devices-to-your-organizations-azure-ad"></a>Anslut Windows 10-enheter till organisationens Azure AD

Om alla Windows-enheter i organisationen har uppgraderats till Windows 10 Pro Creators Update eller redan använder Windows 10 Pro Creators Update kan du ansluta de enheterna till organisationens Azure Active Directory. När enheterna läggs till uppgraderas de automatiskt till Windows 10 Business, som är en del av Microsoft 365 Business Premium-prenumerationen.
  
### <a name="for-a-brand-new-or-newly-upgraded-windows-10-pro-device"></a>En helt ny eller nyligen uppgraderad Windows 10 Pro-enhet

Följ de här stegen för helt nya enheter som kör Windows 10 Pro Creators Update eller för enheter som uppgraderats till Windows 10 Pro Creators Update men som inte utfört konfiguration för Windows 10-enheter.
  
1. Gå igenom konfigurationen av Windows 10-enheter tills du kommer till sidan **Hur vill du konfigurera?** 
    
    ![On the How would you like to set up page, choose Set up for an organization](../media/1b0b2dba-00bb-4a99-a729-441479220cb7.png)
  
2. Välj Konfigurera **för en organisation och ange ditt** användarnamn och lösenord för Microsoft 365 Business Premium. 
    
3. Slutför konfigurationen av Windows 10-enhet.
    
   När du är klar är användaren ansluten till organisationens Azure AD. Kontrollera att allt är korrekt genom att läsa [Kontrollera att enheten är ansluten till Azure AD](#verify-the-device-is-connected-to-azure-ad). 
  
### <a name="for-a-device-already-set-up-and-running-windows-10-pro"></a>Enheter som redan är konfigurerade och använder Windows 10 Pro

 **Ansluta användare till Azure AD:**
  
1. Klicka på Windows-logotypen och sedan på inställningsikonen på användarens dator med Windows 10 Pro, version 1703 (Creators Update) (se [förutsättningar](pre-requisites-for-data-protection.md)).
  
   ![In the Start menu, click Windows Settings icon](../media/74e1ce9a-1554-4761-beb9-330b176e9b9d.png)
  
2. I **Inställningar** går du till **Konton**.
  
   ![In Windows Settings, go to Accounts](../media/472fd688-d111-4788-9fbb-56a00fbdc24d.png)
  
3. På sidan **Din information** klickar du på **Åtkomst till arbete eller skola** \> **Anslut**.
  
   ![Choose Connect under Access work or school](../media/af3a4e3f-f9b9-4969-b3e2-4ef99308090c.png)
  
4. I dialogrutan **Konfigurera ett arbets- eller skolkonto** dialogrutan väljer du **Anslut den här enheten till Azure Active Directory** under **Alternativa åtgärder**.
  
   ![Click Join this device to Azure Active Directory](../media/fb709a1b-05a9-4750-9cb9-e097f4412cba.png)
  
5. On the **Let's get you signed in** page, enter your work or school account \> **Next**.
  
   On the **Enter password** page, enter your password \> **Sign in**.
  
   ![Enter your work or school email on the Let's get you signed in page](../media/f70eb148-b1d2-4ba3-be38-7317eaf0321a.png)
  
6. Kontrollera **att informationen är korrekt på** sidan Kontrollera att detta är din organisation och välj **Anslut.**
  
   På sidan **Klart!** väljer du **Chosse Done**.
  
   ![På skärmen Kontrollera att detta är din organisation väljer du Anslut](../media/c749c0a2-5191-4347-a451-c062682aa1fb.png)
  
Om du laddade upp filer till OneDrive för företag, synkroniserar du dem med datorn. Om du använde ett verktyg från tredje part för migrering av profil och filer, synkroniserar du även med den nya profilen.
  
## <a name="verify-the-device-is-connected-to-azure-ad"></a>Kontrollera att enheten är ansluten till Azure AD

Om du vill verifiera din synkroniseringsstatus väljer du  i området Ansluten till _ _ på sidan Åtkomst till arbete eller skola, så visas knapparna Info och Koppla  \<organization name\> **från.**  Välj **Info för** att få din synkroniseringsstatus. 
  
På sidan **Synkroniseringsstatus** väljer du **Synkronisera för** att få de senaste principerna för hantering av mobila enheter till datorn.
  
Om du vill börja använda Microsoft 365 Business Premium-kontot går du till **Start-knappen** i Windows, högerklickar på den aktuella kontobilden och klickar sedan **på Växla konto.** Logga in med din e-postadress och lösenord hos organisationen.
  
![Click Info button to view synchronization status](../media/818f7043-adbf-402a-844a-59d50034911d.png)
  
## <a name="verify-the-pc-is-upgraded-to-windows-10-business"></a>Kontrollera att datorn uppgraderats till Windows 10 Business

Kontrollera att dina Windows 10-enheter som är anslutna till Azure AD uppgraderats till Windows 10 Business som en del av Microsoft 365 Business Premium-prenumerationen.
  
1. Gå till **Inställningar** \> **System** \> **Om**.
    
2. Kontrollera att **Version** är **Windows 10 Business**.
    
    ![Verify that Windows edition is Windows 10 Business.](../media/ff660fc8-d3ba-431b-89a5-f5abded96c4d.png)
  
## <a name="next-steps"></a>Nästa steg

Om du vill konfigurera dina mobila enheter går du till Konfigurera mobila enheter för [Microsoft 365 Business Premium-användare](set-up-mobile-devices.md), Information om hur du anger principer för enhetsskydd eller programskydd finns i Hantera [Microsoft 365 för företag.](manage.md)
  
## <a name="for-more-on-setting-up-and-using-microsoft-365-business-premium"></a>Mer information om att konfigurera och använda Microsoft 365 Business Premium

[Utbildningsvideor för Microsoft 365 Business](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
