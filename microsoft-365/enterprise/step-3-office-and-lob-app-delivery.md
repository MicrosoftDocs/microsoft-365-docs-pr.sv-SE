---
title: Steg 3 – Leverans av Office- och LOB-appar
f1.keywords:
- NOCSH
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 05/27/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Lär dig hur du levererar Office- och LOB-appar.
ms.openlocfilehash: ab40e59face9e8c4b37db15a9c815ea5579b4a2c
ms.sourcegitcommit: bd8d55f82ca008af1b93a9bb4d1545f68e8188ad
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2020
ms.locfileid: "44011645"
---
# <a name="step-3-office-and-lob-app-delivery"></a>Steg 3: Leverans av Office- och LOB-appar

![](../media/step-3-office-and-lob-app-delivery-media/step-3-office-and-lob-app-delivery-media-1.png)

<table>
<thead>
<td><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-6.png" alt="Step 3" height="130" width="130" /></td>
<td><p><strong>Steg 3: Leverans av Office och verksamhetsspecifika appar</strong></p>
<p>Kontrollera att dina appar är paketerade och klara för automatisk installation. Ta reda på hur du får nya alternativ för att konfigurera, leverera och hålla Office-apparna uppdaterade med Klicka-och-kör-paketering med Microsoft 365-applikationer för företag.</p></td>
<td><a href="https://aka.ms/ddev3" target="_blank"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-16.png" alt="Step 3" height="120" width="213" /></a></td>
</thead>
</table>

>[!NOTE]
>Leverans av Office- och LOB-appar är det tredje steget i vår rekommenderade arbetsprocesshjul som innehåller alternativen för att installera och hantera Office och LOB. För att distributionen ska lyckas ska du inte hoppa över de första två stegen.  Om du vill se den fullständiga skrivbordsdistributionsprocessen kan du gå till [Center för skrivbordsdistribution](https://aka.ms/HowToShift).
>

Du är nu redo att leverera Office och dina verksamhetsspecifika appar, och det finns ett antal olika sätt att göra det, däribland några spännande nya alternativ. Vissa program är endast tillgängliga som en 32-bitars eller 64-bitars kompilerad version, medan andra som Microsoft 365-applikationer för företag finns som både 32-bitars och 64-bitars internt kompilerad kod. Ett av de största beslut du kommer att göra är vilken version som ska distribueras. Om du vill dra nytta av mer bearbetningskraft och RAM på nya enheter rekommenderar Microsoft att du använder 64-bitarsversionen när det inte finns några 32-bitarsberoenden. Om du vill ta reda på om det finns några problem med tillägget eller filrelaterad kompatibilitet kan du behöva gå tillbaka till Steg 1: beredskap för enheter och appar innan du fortsätter.

Om inget hindrar dig rekommenderar vi att du använder 64-bitarsversioner av alla appar, t. ex. Microsoft Office. 64-bitars inbyggda kompilerade appar ger bästa möjliga prestanda och är det bästa alternativet.

Det finns många metoder och modeller för installation av appar i Windows, så vi ska se över dina leveransalternativ.

[Hantering av program i Windows 10](https://docs.microsoft.com/windows/application-management/)

## <a name="msi-based-deployments"></a>MSI-baserade distributioner

För dina affärsprogram kan du antagligen använda MSI-baserade paket eller körbara filer och installera appar som en del av en distributionsaktivitetssekvens för operativsystem. Windows 10 fortsätter att fungera med dessa paket.

Verktyg för distribution av programvara, t. ex. Microsoft Endpoint Configuration Manager och Microsoft Intune, är också optimerade för att tillhandahålla MSI. När du har verifierat dina appar i Windows 10 kan du använda Microsoft Endpoint Configuration Manager (current branch) för programleverans. Om du använder företagsportalen i Microsoft Intune kan du utöka valet av IT-hälsoappar som är tillgängliga för din organisation för att inkludera de senaste programmen, och användare kan själva välja vad de behöver.

![](../media/step-3-office-and-lob-app-delivery-media/step-3-office-and-lob-app-delivery-media-3.png)

## <a name="pc-imaging"></a>Datoravbildning

En annan populär metod för att leverera appar i programmet är PC Imaging. I det här fallet är programmen antingen installerade via aktivitetssekvensen eller manuellt på en exempeldator, och sedan registreras en systemavbildning med de program som krävs för installation. Imaging-metoden för att bygga och avbilda kan spara tid när du etablerar nya datorer, men kom ihåg att operativsystem och appar i avbildningen blir inaktiva snabbt. Den kumulativa uppdateringsmodellen i Windows 10 och Microsoft 365-applikationer för företag hjälper dig med det här problemet, men det löser inte problemet helt. Därför rekommenderar vi en tunn avbildningsmetod där dina program installeras utanför avbildningen vid distributionstillfället.

![](../media/step-3-office-and-lob-app-delivery-media/step-3-office-and-lob-app-delivery-media-4.png)

Om du vill ta med Microsoft 365-applikationer för företag i din avbildning måste du tänka på att det använder en användarspecifik aktivering. Det kan inte föraktiveras av systemadministratören. Använd distributionsverktyget för Office för att förinstallera Office på enheten för avbildningen och hoppa över användarinloggningen. När avbildningen är distribuerad kan slutanvändarna logga in med sina autentiseringsuppgifter och aktivera Microsoft 365-applikationer för företag.

[Skapa en aktivitetssekvens för att installera ett operativsystem](https://docs.microsoft.com/mem/configmgr/osd/deploy-use/create-a-task-sequence-to-install-an-operating-system)

[Distribuera Microsoft 365-applikationer som en del av en operativsystemavbildning](https://docs.microsoft.com/deployoffice/deploy-microsoft-365-apps-operating-system-image)

## <a name="office-click-to-run"></a>Office Klicka-och-kör 

Microsoft 365-applikationer för företag installeras med Klicka-och-kör, och Klicka-och-kör ersätter MSI-baserade paket i alla versioner av kommande Office 2019-versioner för Windows. Det har en mängd fördelar, bland annat snabbare installationer, snabbare och mer effektiv uppdatering och renare avinstallation. 

Program som levererats via Klicka-och-kör körs i en virtuell programmiljö på datorn och samexisterar med andra program utan konflikter De upptar även ungefär hälften av diskutrymmet som skulle upptas som ett MSI-baserat paket. Office-program levereras och hanteras via [distribution verktyg för Office](https://www.microsoft.com/download/details.aspx?id=49117), som är det Office-installationsprogram som krävs för att ladda ned, konfigurera och anpassa dina Office-program. Distributionsverktyget för Office läser en XML-konfigurationsfil som innehåller metadatainstruktioner för hur du konfigurerar och anpassar din Office-installation.

Microsoft rekommenderar att du använder [verktyget Office-anpassning ](https://config.office.com/) för att anpassa dina distributionsinställningar och skapa en XML-konfigurationsfil. Med verktyget Office-anpassning kan du ange vilka program och språk som ska installeras, hur programmen ska uppdateras, programinställningar och inställningar för installation.

![](../media/step-3-office-and-lob-app-delivery-media/step-3-office-and-lob-app-delivery-media-7.png)

Om du använder Configuration Manager kan du fortfarande använda det för omfattande distribution av Microsoft 365-applikationer för företag. Configuration Manager (current branch) har inbyggt stöd för det uppdaterade verktyget för Office-anpassning, paketanpassning för Klicka-och-kör under installation och ursprungligt stöd för hantering av programuppdatering efter installationen.

![](../media/step-3-office-and-lob-app-delivery-media/step-3-office-and-lob-app-delivery-media-6.png)

[Distributionsguide för Microsoft 365-applikationer](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps)

[Ta bort befintliga MSI-versioner av Office när du uppgraderar till Microsoft 365-applikationer](https://docs.microsoft.com/deployoffice/upgrade-from-msi-version)

[Hantera Microsoft 365-applikationer för företag med Configuration Manager](https://docs.microsoft.com/mem/configmgr/sum/deploy-use/manage-office-365-proplus-updates)

[Tilldela Office 365-appar till Windows 10-enheter med Microsoft Intune](https://docs.microsoft.com/intune/apps-add-office365)

## <a name="browser-based-apps"></a>Webbläsarbaserade appar

Det finns några saker du bör tänka på för att se till att de webbaserade programmen fortsätter att fungera som förväntat. Om du har vissa webbplatser och appar som du vet har kompatibilitetsproblem med Microsoft Edge kan du använda webbplatslistan i företagsläge så att webbplatserna öppnas automatiskt via Internet Explorer 11.

Om du vet att dina intranät-webbplatser inte kommer att fungera korrekt med Microsoft Edge kan du dessutom konfigurera alla intranät-webbplatser så att de öppnas automatiskt i Internet Explorer 11. I den här processen används en XML-fil för att styra om IE11 används för varje webbplats med hjälp av en grupprincip för att verkställa inställningar.

[Vad är företagsläge](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#what-is-enterprise-mode)

Hittills har vi tagit upp välkända distributionsmetoder. Men det finns två nya metoder för programdistribution som du kanske vill överväga.

## <a name="microsoft-store-for-business"></a>Microsoft Store för företag 

Med Microsoft Store för företag får du ett smidigt sätt att identifiera, inhämta, hantera och distribuera kostnadsfria och betalda appar till Windows 10-enheter i skala. Som IT-administratör kan du publicera utvalda Microsoft Store-appar, tillsammans med dina egna appar, i din egen privata butik medan du tilldelar och återanvänder licenser efter behov. Användarna dirigeras endast till den här butiken, och hittar och installerar då endast godkända appar.

Store-appar kan skapas internt som UWP-appar, eller så kan du använda Brygga för skrivbordsversion för att paketera om dina befintliga appar och lägga till moderna upplevelser för Windows 10. Bortsett från koden som du använder för att förbättra Windows 10-upplevelserna förblir dina appar oförändrade och fortsätter att köras i fullständigt användarläget med fullständigt förtroende.

## <a name="msix-containerization"></a>MSIX-skapande av behållare

Ett nytt alternativ för paketering av programvara är MSIX. I MSIX används tekniken för skapande av behållare som är tillgänglig i Windows, tillsammans med de bästa aspekterna av Klicka-och-kör-, UWP- och MSI-paketering. Med verktyg för att migrera befintliga installationer, t. ex. EXE, MSI, APPV och APPX direkt till MSIX, ser vi att MSIX-skapande av behållare ger en enhetlig väg för de många installationstekniker som används i dag. MSIX-support ingår i aktuella versioner av Windows: alla enheter som kör Windows 10 RS5 eller senare innehåller allt du behöver för att installera och köra MSIX-paketerade appar. Windows 10 integrerar MSIX-behållare dynamiskt, men programmen hålls åtskilda från operativsystemet.

Skapande av behållare (containerization) innebär en rensad avinstallation och borttagning av paket, till skillnad från många MSI- och EXE-baserade paket som kan lämna kvar objekt i systemet. Det innebär också att bara vanliga användaruppgifter måste finnas för att installera-program – du behöver inte ha administratörsautentiseringsuppgifter för att installera MSIX-containrar. MSIX-containrar är mer effektiva att uppdatera. När en uppdatering publiceras innebär användning av differentiella skillnader att endast att nya nettobinärfiler används, vilket minskar uppdateringsnyttolasten, för snabbare distributioner med mindre bandbredd i nätverket.

Mer information om MSIX finns på [MSIX-teknikcommunitysidan](https://techcommunity.microsoft.com/t5/MSIX/ct-p/MSIX)

## <a name="next-step"></a>Nästa steg

## <a name="step-4-user-files-and-settings"></a>[Steg 4: Användares filer och inställningar](https://aka.ms/mdd4)

## <a name="previous-step"></a>Föregående steg

## <a name="step-2-directory-and-network-readiness"></a>[Steg 2: Katalog- och nätverksberedskap](https://aka.ms/mdd2) 
