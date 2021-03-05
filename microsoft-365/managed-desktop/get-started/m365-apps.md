---
title: Microsoft 365 Apps för företag
description: Distribuera Microsoft 365-program, hur de uppdateras och hur inställningar hanteras
keywords: ändringshistorik
ms.service: m365-md
ms.sitesec: library
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: 26e62d6e59f1f90e35d9e18e6eed917a66876645
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/04/2021
ms.locfileid: "50453927"
---
# <a name="microsoft-365-apps-for-enterprise"></a> Microsoft 365 Apps för företag

## <a name="initial-deployment"></a>Första distributionen

Microsoft Hanterat skrivbord ser till att Microsoft 365-appar för företag (64-bitars) installeras som en del av bilden på alla [programenheter.](../service-description/device-list.md) Följande program bör finnas på enheten när den levereras:

- Word
- Excel
- PowerPoint
- Outlook
- Publisher
- Åtkomst
- Skype för företag
- OneNote

Den här metoden minimerar nätverks påverkan och ser till att användarna kan vara produktiva så snart de får sin enhet. Sedan distribuerar vi fler principer till hanterade enheter för att konfigurera programmen för användning.

> [!NOTE]
> Microsoft Teams distribueras separat från Microsoft 365-appar för företag och ingår inte i basbilden. 

### <a name="available-deployment-to-users"></a>Tillgänglig distribution för användare

Om en användare av någon anledning inte har Microsoft 365-appar på sin enhet kan du använda ett paket för att returnera enheten till det förväntade läget. Lägg till användaren i **gruppen Modern workplace-Office-Office365_Install** så blir apparna tillgängliga för dem i företagsportalen.

### <a name="microsoft-365-apps-for-enterprise-32-bit"></a>Microsoft 365-appar för företag (32-bitar)

Microsoft Hanterat skrivbord stöder inte distribution av 32-bitarsversionen av M365-program för företag.

## <a name="updates-to-microsoft-365-apps"></a>Uppdateringar av Microsoft 365-appar

Microsoft 365-appar är inställda på att uppdateras i [månatlig företagskanal.](https://docs.microsoft.com/deployoffice/overview-update-channels#monthly-enterprise-channel-overview) Den här övningen ger användarna nya Office-funktioner varje månad, men de får bara en uppdatering per månad med ett förutsägbart versionsschema. Uppdateringar släpps den andra tisdagen i månaden. Dessa uppdateringar kan innehålla funktions-, säkerhets- och kvalitetsuppdateringar. De här uppdateringarna görs automatiskt och hämtas direkt från Office CDN för den specifika kanalen.

Microsoft Hanterade skrivbord förser varje version med att identifiera potentiella problem i din miljö. Vi har slutfört lanseringen 28 dagar efter lanseringen från Microsoft 365 App-produktgruppen. Microsoft Hanterad dator schemalägger uppdateringsutgåvan till olika grupper för att ge tid för validering och testning enligt följande: 

- Test: noll dagar
- Första: noll dagar
- Snabbt: 3 dagar
- Bred: 7 dagar

Microsoft Hanterat skrivbord anger en tidsgräns på sju dagar [för](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) uppdateringar för enheter. När uppdateringen är tillgänglig måste den installeras inom sju dagar. Användarna [](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) meddelas om att uppdateringar krävs på flera olika platser: i systemfältet 12 timmar före tidsgränsen, och de får en 15-minutersvarning före tidsgränsen. Alla Microsoft 365-appar måste stängas för att uppdateringen ska kunna slutföras.

### <a name="pausing-or-rolling-back-an-update"></a>Pausa eller distribuera en uppdatering

Om du av någon anledning behöver pausa eller återställa programuppdateringen för Microsoft 365 arkiverar du en [administratörssupportbegäran](../working-with-managed-desktop/admin-support.md) via Microsoft Managed Desktop-portalen.

Under en version övervakar Microsoft Hanterat skrivbord felfrekvenserna för alla Microsoft 365-appar. Om vi ser en betydande kvalitetsskillnad mellan den nya versionen och den föregående versionen kan vi kontakta dig via Microsofts administrationsportal för hanterade datorer. Beroende på hur allvarligt det är frågar vi dig om du vill pausa utgivningen eller informera dig om att vi har vidtagit åtgärder för att minimera ett problem. 

### <a name="delivery-optimization"></a>Leveransoptimering

Leveransoptimering är en peer-to-peer-distributionsteknik som finns i Windows 10. Det gör att enheter kan dela innehåll, till exempel uppdateringar, som enheterna har laddat ned från Microsoft via Internet. Användning av den kan minska nätverkets bandbredd eftersom en enhet kan hämta delar av uppdateringen från en annan enhet på dess lokala nätverk i stället för att behöva ladda ned uppdateringen helt från Microsoft.

[Leveransoptimering](https://docs.microsoft.com/deployoffice/delivery-optimization) aktiveras som standard på enheter som kör versionerna Windows 10 Enterprise eller Windows 10 Education. 

## <a name="settings-managed-by-microsoft-managed-desktop"></a>Inställningar som hanteras av Microsoft Managed Desktop

Microsoft hanterar vissa inställningar som en del av tjänsten. Microsoft Hanterat skrivbord hanterar inte en baslinje för Office-säkerhet men du kan ange en själv genom att följa linjerna i [avsnittet Inställningar som du hanterar.](#settings-you-manage)

### <a name="update-settings"></a>Uppdatera inställningar

Microsoft Hanterat skrivbord har alla [uppdateringsinställningar](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) för hanterade enheter och du bör ändra de här inställningarna.

### <a name="set-updates-to-occur-automatically"></a>Konfigurera uppdateringar så att de sker automatiskt

**Standardvärde:** Aktiverad

Den här principen har konfigurerats för att säkerställa att alla Office-enheter kan hållas uppdaterade från molnet. 

### <a name="set-a-deadline-when-updates-have-to-be-applied"></a>Ange en tidsgräns när uppdateringar ska tillämpas

**Standardvärde:** 7 dagar

Principen **UpdateDeadline** används för att konfigurera respitperioden som användarna har innan en uppdatering tillämpas på enheten. Den här tidsgränsprincipen [utlöser även aviseringar](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) till användaren om de ändringar som krävs på enheten.  

### <a name="defer-updates-on-a-device-for-a-period"></a>Skjuta upp uppdateringar på en enhet under en period

Den här principen har konfigurerats på olika sätt för varje enhetsgrupp för uppdateringshantering och krävs för att Microsoft Managed Desktop ska uppfylla sina uppdateringsmål:  

- Test: noll dagar
- Första: noll dagar
- Snabb 7 dagar
- Bred: 21 dagar

### <a name="update-notifications-settings"></a>Uppdatera meddelandeinställningar

**Standardvärde:** Falskt

Inställningen "Dölj uppdateringsmeddelanden" är inställd på **False** på Microsoft Managed Desktop-enheter för att ge bästa möjliga uppdateringsupplevelse för användare genom att meddela [dem](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) när uppdateringar krävs.

### <a name="specify-a-location-to-look-for-updates"></a>Ange en plats där du vill söka efter uppdateringar

**Standardvärde:** Månadskanal för företag

En kombination av **principerna UpdatePath** och **UpdateChannel** används vid behov för att uppnå uppdateringsschemat. De här principerna är inställda på att säkerställa att alla Office-enheter får uppdateringar direkt från CDN för månatlig företagskanal.

### <a name="specify-the-target-version-of-microsoft-365-apps"></a>Ange målversionen av Microsoft 365-appar

Principen för målversionen används ibland av Microsoft Managed Desktop för att återställa eller fästa en viss version av Office. 


### <a name="hide-the-option-to-enable-or-disable-office-automatic-updates"></a>Dölja alternativet för att aktivera eller inaktivera automatiska uppdateringar i Office

**Standardvärde:** Aktiverad

Den här inställningen krävs för att Microsoft Hanterat skrivbord ska uppfylla uppdateringsmålen för Microsoft 365-program. 

### <a name="first-run-settings"></a>Inställningar för första körningen 

Det finns flera inställningar som påverkar beteendet första gången Office körs.

### <a name="accept-the-license-terms-on-behalf-of-the-end-user"></a>Godkänn licensvillkoren åt slutanvändaren

**Standardvärde:** Inaktiverat

Första gången en användare öppnar en Microsoft 365-app uppmanas de att godkänna licensvillkoren. Om du vill godkänna licensvillkoren åt dina användare arkiverar du en tjänstbegäran till Microsoft Managed Desktop Operations-teamet och ber om att den här inställningen aktiveras. 

### <a name="suppress-outlook-mobile-check-box"></a>Kryssrutan Ignorera Outlook Mobile

**Standardvärde:** Inaktiverat

Första gången outlook öppnas uppmanas användaren att installera Outlook Mobile. Om du inte vill att användarna ska se den kryssrutan arkiverar du en tjänstbegäran till Microsoft Managed Desktop Operations-teamet och ber om att den här inställningen aktiveras för dina enheter. 

## <a name="other-settings"></a>Andra inställningar

Det finns andra Microsoft 365-appinställningar som Microsoft Hanterat skrivbord kan konfigurera åt dig. 

### <a name="disable-personal-onedrive"></a>Inaktivera personlig OneDrive

**Standardvärde:** Inaktiverat

Vissa organisationer är oroliga för att användare ska ha åtkomst till både företagsfiler och personliga filer på sina enheter. Du kan arkivera en tjänstbegäran med Microsoft Managed Desktop Operations-teamet och begära att den här inställningen aktiveras. 

## <a name="settings-you-manage"></a>Inställningar som du hanterar

Det finns många andra principer som Microsoft Hanterade skrivbord ännu inte har angett som en del av vår tjänst. Du kan konfigurera de här principerna med hjälp av Microsoft Intune, som använder [molnprinciptjänsten för Office.](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied) Följ de här stegen om du vill ange dessa principer:

1.  Logga in på administrationscentret för Microsoft Endpoint Manager.
2.  Välj **program > principer för Office-program > Skapa**
3.  Gör **följande på** konfigurationssidan Skapa princip:
    - Ange ett namn.
    - Ange en beskrivning (valfritt).
    - I **tilldelningar** väljer du om den här principen ska gälla för alla användare av Microsoft 365-program för företag eller bara för användare som har anonym åtkomst till dokument via Office för webben.
    - Markera den AAD-baserade säkerhetsgrupp som har tilldelats principkonfigurationen. Varje principkonfiguration kan bara tilldelas en grupp och varje grupp kan bara tilldelas en principkonfiguration.
    - Konfigurera principinställningarna så att de inkluderas i principkonfigurationen. Du kan söka på principinställningsnamnet för att hitta den principinställning som du vill konfigurera. Du kan också filtrera på programmet, på om principen är en rekommenderad säkerhetsbaslinje och på om principen har konfigurerats. I plattformskolumnen anges om principen tillämpas på Microsoft 365-appar för företag för Windows-enheter, Office för webben eller alla.
4.  När du har gjort dina val väljer du **Skapa.**

> [!NOTE]
> Konfigurationsprinciper för Office stöder endast användarbaserad distribution
