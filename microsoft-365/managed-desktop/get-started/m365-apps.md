---
title: Microsoft 365 Apps för företag
description: Distribuera Microsoft 365-appar, hur de uppdateras och hur inställningar hanteras
keywords: ändrings historik
ms.service: m365-md
ms.sitesec: library
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: 767489ba9f9ac63bc1a2d8b4999b6634335b1aef
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547752"
---
# <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365 Apps för företag

## <a name="initial-deployment"></a>Inledande distribution

Microsoft Managed Desktop garanterar att Microsoft 365-programmen för Enterprise (64-bitars) installeras som en del av bilden på alla [program enheter](../service-description/device-list.md). Alla följande program bör finnas med på enheten när den levereras:

- Word
- Excel
- PowerPoint
- Outlook
- Skapas
- Åtkomst
- Skype för företag
- OneNote

Den här metoden minimerar nätverks påverkan och säkerställer att användarna kan vara produktiva när de tar emot sina enheter. Vi distribuerar sedan ytterligare principer till hanterade enheter för att konfigurera programmen för användning.

> [!NOTE]
> Microsoft Teams distribueras separat från Microsoft 365-appar för företag och ingår inte i bas bilden. 

### <a name="available-deployment-to-users"></a>Tillgänglig distribution för användare

Om en användare inte har Microsoft 365-appar på sin enhet av någon anledning kan du använda ett paket för att återställa enheten till förväntat tillstånd. Lägga till användaren i den **moderna arbets platsen – Office-Office365_Install-** gruppen och programmen blir tillgängliga för dem i företags portalen.

### <a name="microsoft-365-apps-for-enterprise-32-bit"></a>Microsoft 365-appar för Enterprise (32-bitar)

Microsoft Managed Desktop stöder inte distribution av 32-bitars versionen av M365-appar för företag.

## <a name="updates-to-microsoft-365-apps"></a>Uppdateringar av Microsoft 365-appar

Microsoft 365-apparna är inställda på att uppdatera [månadens Enterprise-kanal](https://docs.microsoft.com/deployoffice/overview-update-channels#monthly-enterprise-channel-overview). I den här övningen får användarna nya Office-funktioner varje månad, men de får bara en uppdatering per månad på ett förutsägbart sätt. Uppdateringar publiceras den andra tisdagen i månaden; dessa uppdateringar kan omfatta uppdateringar av funktioner, säkerhet och kvalitet. Dessa uppdateringar sker automatiskt och hämtas direkt från Office CDN för den specifika kanalen.

Microsoft Managed Desktop-förskjutningar för att identifiera eventuella problem i miljön. Vi slutförde lanseringen av de 28 dagarna efter utgivningen från Microsoft 365 program produkt gruppen. Microsoft-hanterade Skriv bords scheman uppdaterar utgåvor till olika grupper för att tillåta tid för validering och testning: 

- Test: 0 dagar
- Först: 0 dagar
- Snabbt: 7 dagar
- Brett: 21 dagar

Microsoft Managed Desktop set en [tids gräns](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) på sju dagar för enheter. När uppdateringen är tillgänglig måste den installeras inom sju dagar. Användare [meddelas](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) om att uppdateringar krävs på flera platser: programmet, i system fältet 12 timmar före deadline och får en 15-minuters varning före tids gränsen. Alla Microsoft 365-appar måste vara stängda för att uppdateringen ska slutföras.

### <a name="pausing-or-rolling-back-an-update"></a>Pausa eller återställa en uppdatering

Om du behöver pausa eller återställa Microsoft 365-programmet av någon anledning kan du arkivera en [support förfrågan för administratörer](../working-with-managed-desktop/admin-support.md) via Microsofts hanterade Skriv bords Portal.

Under en version övervakar Microsoft Managed Desktop dator fel frekvenserna för alla Microsoft 365-appar. Om vi antecknar en betydande bild av kvaliteten mellan den nya versionen och dess föregångare, kan vi kontakta dig via administrations portalen för Microsoft Managed Desktop. Beroende på allvarlighets graden frågar vi dig om du vill pausa versionen eller informera dig om att vi har åtgärdat ett problem. 

### <a name="delivery-optimization"></a>Leverans optimering

Leverans optimering är en peer-to-peer-postdistributionsgrupp som är tillgänglig i Windows 10. Det gör att enheter kan dela innehåll, till exempel uppdateringar, som enheterna har laddat ner från Microsoft via Internet. Detta kan minska nätverks bandbredden eftersom en enhet kan få delar av uppdateringen från en annan enhet i det lokala nätverket i stället för att behöva ladda ner uppdateringen helt från Microsoft.

[Leverans optimering](https://docs.microsoft.com/deployoffice/delivery-optimization) är aktive rad som standard på enheter med utbildnings utgåvor för Windows 10 Enterprise eller Windows 10. 

## <a name="settings-managed-by-microsoft-managed-desktop"></a>Inställningar som hanteras av Microsoft Managed Desktop

Microsoft hanterar vissa inställningar som en del av tjänsten. Microsoft Managed Desktop hanterar inte en Office Security-original plan, men du kan ställa in ett själv genom att följa anvisningarna i avsnittet [inställningar som hanteras](#settings-you-manage) .

### <a name="update-settings"></a>Uppdaterings inställningar

Microsoft Managed Desktop behåller alla [uppdaterings inställningar](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) för hanterade enheter och du bör ändra de här inställningarna.

### <a name="set-updates-to-occur-automatically"></a>Ange att uppdateringar ska ske automatiskt

**Standardvärde**: aktive rad

Den här principen är konfigurerad för att säkerställa att alla Office-enheter kan hållas uppdaterade från molnet. 

### <a name="set-a-deadline-when-updates-have-to-be-applied"></a>Ange en tids gräns när uppdateringar måste tillämpas

**Standardvärde**: 7 dagar

**UpdateDeadline** policy används för att konfigurera Grace-perioden som användare har innan en uppdatering genomdrivs på enheten. Denna tids gräns princip utlöser också [meddelanden](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) till användaren för att informera dem om de ändringar som krävs på deras enheter.  

### <a name="defer-updates-on-a-device-for-a-period"></a>Skjuta upp uppdateringar för en enhet för en period

Den här principen konfigureras olika för varje enhets grupp för uppdaterings hantering och krävs för Microsoft Managed Desktop för att uppfylla sina uppdaterings mål:  

- Test: 0 dagar
- Först: 0 dagar
- Snabb sju dagar
- Brett: 21 dagar

### <a name="update-notifications-settings"></a>Uppdatera aviserings inställningar

**Standardvärde**: falskt

Inställningen "Dölj uppdaterings aviseringar" är inställd på **false** på Microsoft Managed Station ära enheter för att tillhandahålla den bästa uppdateringen för användare genom att [meddela](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) dem när uppdateringar behövs.

### <a name="specify-a-location-to-look-for-updates"></a>Ange en plats att söka efter uppdateringar för

**Standardvärde**: månatlig företags kanal

En kombination av **UpdatePath** -och **UpdateChannel** -principer används för att uppnå uppdaterings schema. Dessa principer är inställda på att säkerställa att alla Office-enheter tar emot uppdateringar direkt från CDN för den månads Visa företags kanalen.

### <a name="specify-the-target-version-of-microsoft-365-apps"></a>Ange mål versionen av Microsoft 365-appar

Mål versions principen används ibland av Microsoft Managed Desktop för att återställa eller fästa en viss version av Office. 


### <a name="hide-the-option-to-enable-or-disable-office-automatic-updates"></a>Dölj alternativet för att aktivera eller inaktivera automatiska uppdateringar av Office

**Standardvärde**: aktive rad

Den här inställningen krävs för Microsoft Managed Desktop för att uppfylla sina uppdaterings mål för Microsoft 365-program. 

### <a name="first-run-settings"></a>Inställningar för första körningen 

Det finns flera inställningar som påverkar beteendet för första gången Office körs.

### <a name="accept-the-license-terms-on-behalf-of-the-end-user"></a>Godkänn licens villkoren åt slutanvändaren

**Standardvärde**: inaktiverat

Första gången en användare öppnar en Microsoft 365-App uppmanas de att acceptera licens villkoren. Om du vill acceptera licens villkoren åt användarna kan du spara en tjänstbegäran med Microsoft Managed Desktop-teamet och ange att inställningen ska aktive ras. 

### <a name="suppress-outlook-mobile-check-box"></a>Kryss rutan Inaktivera Outlook Mobile

**Standardvärde**: inaktiverat

Första gången en användare öppnar Outlook uppmanas de att installera Outlook Mobile. Om du inte vill att användarna ska kunna se den här kryss rutan kan du spara en tjänstbegäran med Microsoft Managed Desktop-teamet och ange att den här inställningen ska vara aktive rad för dina enheter. 

## <a name="other-settings"></a>Andra inställningar

Det finns andra Microsoft 365-inställningar som Microsoft Managed Desktop kan konfigurera åt dig. 

### <a name="disable-personal-onedrive"></a>Inaktivera personligt OneDrive

**Standardvärde**: inaktiverat

Vissa organisationer är bekymrade över användare som har till gång till både företags-och privata filer på sina enheter. Du kan spara en tjänstbegäran med Microsoft Managed Desktop-gruppanvändare där den här inställningen aktive ras. 

## <a name="settings-you-manage"></a>Inställningar som du hanterar

Det finns många andra principer som Microsoft Managed Desktop ännu inte har angett som en del av vår tjänst. Du kan konfigurera dessa med hjälp av Microsoft Intune som använder princip tjänsten för [Office-moln](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied) . Gör så här:

1.  Logga in i administrations centret för Microsoft Endpoint Manager.
2.  Välj **program > principer för Office-program > Skapa**
3.  Gör följande på sidan **Skapa princip** konfiguration:
    - Ange ett namn.
    - Ange en beskrivning (valfritt).
    - I **uppgifter**väljer du om den här policyn gäller för alla användare av Microsoft 365-appar för företag, eller bara för användare som anonymt får åtkomst till dokument med Office för webben.
    - Välj den AAD-baserade säkerhets grupp som är tilldelad till princip konfigurationen. Varje princip konfiguration kan bara tilldelas en grupp, och varje grupp kan bara tilldelas en princip konfiguration.
    - Konfigurera princip inställningarna så att de tas med i princip konfigurationen. Du kan söka i princip inställnings namnet för att hitta den princip inställning som du vill konfigurera. Du kan också filtrera efter programmet, på om principen är en rekommenderad säkerhets bas linje och om policyn har kon figurer ATS. I kolumnen Platform visas om policyn används för Microsoft 365-appar för Enterprise för Windows-enheter, Office för webben eller alla.
4.  När du har gjort dina val väljer du **skapa**.

> [!NOTE]
> Konfigurations principer för Office stöder endast användarspecifik distribution
