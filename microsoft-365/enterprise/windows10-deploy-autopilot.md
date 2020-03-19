---
title: Distribuera Windows 10 Enterprise för nya enheter med Windows Autopilot
description: Innehåller vägledning om hur du konfigurerar och distribuerar Windows 10 Enterprise med Windows Autopilot.
keywords: Microsoft 365, Microsoft 365 Enterprise, Microsoft 365-dokumentation, Windows 10 Enterprise, distribution, Windows Autopilot
author: greg-lindsay
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/30/2018
f1.keywords:
- NOCSH
ms.author: greglin
ms.openlocfilehash: ba5804d3065dcb01d85d457df7555a642d6f2839
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42811821"
---
# <a name="step-3-deploy-windows-10-enterprise-for-new-devices-with-windows-autopilot"></a>Steg 3: Distribuera Windows 10 Enterprise för nya enheter med Windows Autopilot

*Den här artikeln gäller både E3- och E5-versionerna av Microsoft 365 Enterprise*

![Fas 3: Windows 10 Enterprise](../media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

Om du har nya Windows 10-datorer kan du använda Windows Autopilot för att anpassa oobe -upplevelsen (out-of-box-experience) för din organisation och distribuera ett nytt system med appar och inställningar som redan är konfigurerade. Det finns inga avbildningar att distribuera, inga drivrutiner att injicera och ingen infrastruktur att hantera. Användare kan gå igenom distributionsprocessen oberoende av dem, utan att behöva kontakta sin IT-administratör.

Du kan konfigurera och förkonfigurera nya Windows 10-enheter och göra dem redo för produktiv användning med Windows Autopilot. Mer information om Windows Autopilot, inklusive fördelar och Windows Autopilot-scenarier, finns i [Översikt över Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-Autopilot/windows-10-Autopilot). När du är klar följer du dessa delar för att starta in nya enheter.

## <a name="the-windows-autopilot-deployment-process-poster"></a>Affischen för distributionsprocessen för Windows Autopilot

Windows Autopilot-affischen är två sidor i stående läge (11x17). Klicka på bilden nedan för att visa en PDF-fil i webbläsaren. 

[![Distribuera Windows 10 med Autopilot-affisch](../media/windows10-deploy-autopilot/windows10-autopilot-flowchart.png)](https://docs.microsoft.com/windows/deployment/media/Windows10AutopilotFlowchart.pdf)

Du kan också ladda ner denna affisch i [PDF-](https://github.com/MicrosoftDocs/windows-itpro-docs/raw/public/windows/deployment/media/Windows10AutopilotFlowchart.pdf) eller [Visio-format.](https://github.com/MicrosoftDocs/windows-itpro-docs/raw/public/windows/deployment/media/Windows10Autopilotflowchart.vsdx)

## <a name="part-1-start-windows-autopilot-deployment"></a>Del 1: Starta distributionen av Windows Autopilot
Se [Översikt över Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-Autopilot/windows-10-Autopilot) för att:

1. Lär dig mer om och slutför förutsättningarna för distribution av Windows Autopilot. Förutsättningarna inkluderar:
    - **Enhetsregistrering och OOBE-anpassning**

        För att registrera enheter måste du skaffa deras maskinvaru-ID och registrera det. Vi arbetar aktivt med olika maskinvaruleverantörer för att göra det möjligt för dem att tillhandahålla den information som krävs för dig, eller ladda upp den för din räkning. Du har också möjlighet att samla in den här informationen själv med hjälp av ett PowerShell-skript som genererar en CSV-fil med enhetens maskinvaru-ID.

        När enheterna har registrerats finns det anpassningsalternativ för OOBE som du kan konfigurera, inklusive att hoppa över sekretessinställningar och Licensavtal.

    - **Företagets varumärke för OOBE**

        På så sätt kan du lägga till varumärkesprofilering som ska visas under enhets-OOBE.

    - **Automatisk MDM-registrering i Microsoft Intune**
        
        Med automatisk registrering kan användare registrera sina Windows 10-enheter i Intune för enhetshantering när de ansluter sina enheter till Azure AD. För att registrera lägger användare till sitt arbetskonto på sina personligt ägda enheter eller ansluter till företagsägda enheter till Azure AD. I bakgrunden registreras enheten också för hantering med Intune.

    - **Nätverksanslutning till molntjänster som används av Windows Autopilot**

        Windows Autopilot Deployment Program använder ett antal molntjänster för att få dina enheter till ett produktivt tillstånd och dessa tjänster måste vara tillgängliga från enheter som är registrerade som Windows Autopilot-enheter. 

    - **Enheter måste förinstalleras med Windows 10, version 1703 eller senare**

2. Lär dig mer om och välj Windows Autopilot Deployment Program för din organisation. Du kan välja bland dessa distributionsprogram:
    - **Microsoft Store för företag**
    - **Microsoft Intune**
    - **Partnercenter**

## <a name="part-2-set-up-a-windows-10-device-for-microsoft-365"></a>Del 2: Konfigurera en Windows 10-enhet för Microsoft 365
Innan du kan konfigurera Windows-enheter för Microsoft 365-användare kontrollerar du att alla Windows-enheter kör Windows 10, version 1703 (Creators Update) eller senare.

När alla Windows-enheter i organisationen antingen har uppgraderats till Windows 10 Creators Update eller redan kör Windows 10 Creators Update kan du ansluta till dessa enheter till organisationens Azure Active Directory.

### <a name="set-up-a-brand-new-or-newly-upgraded-windows-10-device"></a>Konfigurera en helt ny eller nyligen uppgraderad Windows 10-enhet
Följ dessa steg för att konfigurera en enhet med Windows 10 OOBE på en helt ny enhet som kör Windows 10 Creators Update (eller senare) eller på en enhet som uppgraderades till Windows 10 Creators Update (eller senare) men som inte har gått igenom invald.

1. Om du inte har konfigurerat ett trådlöst nätverk kontrollerar du att du ansluter enheten till internet via en kabelansluten anslutning eller Ethernet-anslutning.
2. Gå igenom installationen av Windows-enheten. På en ny eller återställd enhet börjar installationsupplevelsen med **regionen Let's start. Stämmer det här?** Skärmen.
3. Gå igenom konfigurationen av Windows 10-enheter tills du kommer till sidan **Hur vill du konfigurera?** Här väljer du **Konfigurera för en organisation**.
4. Logga in med Microsoft 365-användarens konto och lösenord. Beroende på inställningen för användarens lösenord kan du bli ombedd att uppdatera lösenordet. 
5. Slutför konfigurationen av Windows 10-enhet.

När du är klar ansluts enheten till organisationens Azure AD.

### <a name="set-up-a-device-that-has-already-completed-out-of-box-setup"></a>Konfigurera en enhet som redan har slutförts i ingående installation
Om din enhet har Windows 10 Creators Update (eller senare) och redan har gått igenom den färdiga installationen följer du dessa steg.

1. På användarens Windows-dator med Windows 10, version 1703 (Creators Update), väljer du **Windows-logotypen** och väljer sedan ikonen **Inställningar.**
2. I **Inställningar** går du till **Konton**.
3. På sidan **Din information** väljer du **Access-arbete eller skola** > **Anslut**.
4. Välj Anslut den här enheten till Azure Active **Directory**under Alternativa **åtgärder**i dialogrutan Konfigurera **ett arbets- eller skolkonto** .
5. På sidan **Låt oss få dig inloggad** anger du ditt arbets- eller skolkonto och väljer **Nästa**.
6. På sidan **Ange lösenord** anger du ditt lösenord och väljer **Logga in**.
7. Kontrollera att informationen är korrekt på sidan Kontrollera att **informationen är** korrekt och välj Gå **med**.
8. På sidan **Klart!** väljer du **Klar**.

När du är klar ansluts användaren till organisationens Azure AD.

### <a name="verify-the-device-is-connected-to-azure-ad"></a>Kontrollera att enheten är ansluten till Azure AD
Följ dessa steg för att verifiera enhetens synkroniseringsstatus med Azure AD och börja sedan använda ditt Microsoft 365-konto på enheten. 

1. Öppna **Inställningar**.
2. På sidan **Access-arbete eller skola** väljer du området **Ansluten till <organization name> ** för att visa knapparna **Info** och Koppla **från**.
3. Välj **Info** för att få din synkroniseringsstatus.
4. På sidan **Synkroniseringsstatus** väljer du **Synkronisera** för att hämta de senaste hanteringsprinciperna för mobila enheter på datorn.
5. Om du vill börja använda Microsoft 365-kontot går du till **Start-knappen i** Windows, högerklickar på din aktuella kontobild och väljer sedan **Växla** konto.
6. Logga in med din e-postadress och lösenord hos organisationen.

Om du får problem när du använder Windows 10 i en företagsmiljö kan du läsa [de vanligaste Microsoft-supportlösningarna för de vanligaste problemen](https://docs.microsoft.com/windows/client-management/windows-10-support-solutions). Dessa resurser omfattar KB-artiklar, uppdateringar och biblioteksartiklar.

Som en interimskontrollpunkt kan du se [avslutningskriterierna](windows10-exit-criteria.md#crit-windows10-step3) som motsvarar det här steget.

## <a name="next-step"></a>Nästa steg

|||
|:-------|:-----|
|![Steg 4](../media/stepnumbers/Step4.png)| [Övervaka enhetens hälsa och efterlevnad](windows10-enable-windows-analytics.md) |
