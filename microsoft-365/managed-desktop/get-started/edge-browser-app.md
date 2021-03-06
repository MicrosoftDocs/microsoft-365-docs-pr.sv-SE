---
title: Nya Microsoft Edge
description: Förklarar hur den nya Edge-webbläsaren distribueras och uppdateras
keywords: webbläsare, Microsoft Hanterat skrivbord, Microsoft 365, tjänst, dokumentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 2bf1fab504ae77a1e66235f49333c3b123e38904
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822256"
---
# <a name="new-microsoft-edge-app"></a>Ny Microsoft Edge app

Den nya [Microsoft Edge förser](https://www.microsoft.com/edge) dig med prestanda i världsklass med mer sekretess, mer produktivitet och mer värde medan du surfar. Microsoft Hanterat skrivbord en offentlig förhandsversion av distributionen av den nya Edge-webbläsaren i din miljö.

## <a name="initial-deployment"></a>Inledande distribution

Om du vill Microsoft Hanterat skrivbord dina enheter till den nya Microsoft Edge-webbläsaren arkiverar du ett IT-support ärende via Microsoft Hanterat skrivbord portalen. Vi distribuerar Edge Stable-kanalen till testgruppen när du arkiverar biljetten och sedan distribuerar den i varje efterföljande distributionsgrupp var 24:e timme. Om du vill pausa distributionen arkiverar du ett annat ärende där åtgärder ska pausas.

Betakanalen [är](/deployedge/microsoft-edge-channels#beta-channel) också tillgänglig på begäran om en representativ validering inom organisationen. Microsoft Hanterat skrivbord distribuerar programmet efter behov i Test och Första grupper så att alla dessa användare har Betakanal utöver Stable-kanalen. För andra användare som behöver åtkomst till betakanalen lägger du till dem i gruppen **Moderna workplace - Edge Beta-användare** och be dem installera det från Företagsportal

## <a name="updates-to-microsoft-edge"></a>Uppdateringar av Microsoft Edge

Microsoft Hanterat skrivbord distribuerar [Stable-kanalen](/deployedge/microsoft-edge-channels#stable-channel) Microsoft Edge, som uppdateras automatiskt var sjätte vecka. Uppdateringar i stable-kanalen distribueras gradvis av Microsoft Edge för att kunderna ska få den bästa upplevelsen. [](/deployedge/microsoft-edge-update-progressive-rollout) 

Betakanalen [distribueras](/deployedge/microsoft-edge-channels#beta-channel) till enheter i både test- och första grupperna för representativ validering inom organisationen. Den här kanalen stöds fullt ut och uppdateras automatiskt med nya funktioner ungefär var sjätte vecka.

För att säkerställa Microsoft Edge uppdateringar korrekt ska du inte ändra Microsoft Edge [principer för uppdateringar.](/deployedge/microsoft-edge-update-policies)



## <a name="settings-managed-by-microsoft-managed-desktop"></a>Inställningar hanteras av Microsoft Hanterat skrivbord

Microsoft Hanterat skrivbord har skapat en standarduppsättning principer för Microsoft Edge för att skydda webbläsaren. Standardinställningarna för webbläsaren är följande:

### <a name="microsoft-edge-extensions"></a>Microsoft Edge tillägg

I säkerhetsbaslinjen för Microsoft Edge på Microsoft Hanterat skrivbord anges två principer för att inaktivera alla Chrome-tillägg och säkra användare. Information om hur du aktiverar och distribuerar tillägg i din miljö Inställningar hantera. 

#### <a name="extension-installation-blocklist"></a>Blockeringslista för förlängningsinstallation
**Standardvärde:** Alla

Microsoft Hanterat skrivbord anger den här principen för att förhindra att Chrome-tillägg installeras i hanterade slutpunkter. Det finns kända risker associerade med Chromium tilläggsmodell, bland annat dataskydd, sekretess och andra risker som kan avslöja enheter. 

#### <a name="allow-user-level-native-messaging-hosts-installed-without-admin-permissions"></a>Tillåt inbyggda meddelandevärdar på användarnivå (installeras utan administratörsbehörighet)

**Standardvärde:** Inaktiverad

Genom att inaktivera den här Microsoft Edge endast interna meddelandevärdar installerade på systemnivån. Interna meddelandevärdar är en del av Chrome-tilläggen, som gör att webbläsaren kan interagera med andra delar av användarens slutpunkt, vilket skapar en mängd olika säkerhetsproblem.  

### <a name="secure-sockets-layer-tlsssl"></a>Secure Sockets Layer (TLS/SSL)

#### <a name="minimum-tls-version"></a>Lägsta TLS-version

**Standardvärde:** Minsta TLS 1.2 som stöds

Om du vill använda den mindre säkra TLS 1.1 kan du lämna in en begäran om att göra det.

#### <a name="allows-users-to-proceed-from-the-ssl-warning-page"></a>Tillåter användare att fortsätta från SSL-varningssidan

**Standardvärde:** Inaktiverad

Vi rekommenderar inte att du aktiverar den här inställningen eftersom det gör att användare kan besöka webbplatser med TSL-fel.

### <a name="microsoft-defender-smartscreen"></a>Microsoft Defender SmartScreen

#### <a name="configure-windows-defender-smartscreen"></a>Konfigurera Windows Defender SmartScreen

**Standardvärde:** Aktiverad

Aktiverad som standard för att skydda användare.

#### <a name="windows-defender-smartscreen-prompts-for-sites"></a>Windows Defender SmartScreen-uppmaningar om webbplatser

**Standardvärde:** Aktiverad

Vi rekommenderar inte att du inaktiverar den här inställningen eftersom det gör att användare kan ignorera varningar och fortsätta med potentiellt skadliga webbplatser.

#### <a name="prevent-bypassing-of-windows-defender-smartscreen-warnings-about-downloads"></a>Förhindra att data Windows Defender SmartScreen-varningar om nedladdningar

**Standardvärde:** Aktiverad

Vi rekommenderar inte att du inaktiverar den här inställningen eftersom det gör att användare kan ignorera varningar och slutföra overifierade nedladdningar.

### <a name="adobe-flash"></a>Adobe Flash

#### <a name="default-adobe-flash-setting"></a>Standardinställningen för Adobe Flash

**Standardvärde:** Inaktiverad

Vi rekommenderar inte att du använder Flash på grund av associerade säkerhetsrisker. Om du fortfarande har processer som är beroende av Flash anger du principen **[PluginsAllowedForUrls](/deployedge/microsoft-edge-policies#pluginsallowedforurls)** för att aktivera Flash för webbplatser där det behövs. Om du inte kan visa en lista över tillåtna webbplatser där Flash används kan du göra en ändringsbegäran om att ändra värdet till Klicka för att spela **upp,** så att användarna kan välja när det är lämpligt att köra Flash.

### <a name="password-manager"></a>Lösenordshanteraren

#### <a name="enable-saving-passwords-to-the-password-manager"></a>Aktivera att lösenord sparas i lösenordshanteraren

**Standardvärde:** Inaktiverad

Lösenordshanteraren är inaktiverad som standard. Om du gillar den här funktionen aktiverad kan du arkivera en supportbegäran och våra tjänsttekniker kan aktivera inställningen i din miljö. 

### <a name="internet-explorer-mode-in-microsoft-edge"></a>Internet Explorer-läge i Microsoft Edge
IE-läget Microsoft Edge gör det enkelt att använda alla webbplatser som organisationen behöver i en enda webbläsare. Den använder den integrerade Chromium-motorn för webbplatser som är kompatibla med Chromium-renderingsmotorn och använder Trident MSHTML-motorn från Internet Explorer 11 (IE11) för webbplatser som inte är eller är beroende av IE-funktioner. [Läs mer](/DeployEdge/edge-ie-mode) 

Microsoft Hanterat skrivbord aktiverar Internet Explorer-läget för dina enheter som standard 

#### <a name="internet-explorer-mode-integration"></a>Internet Explorer-lägesintegrering
**Standardvärde:** Internet Explorer-läge

Som standard är enheter inställda på att använda Internet Explorer-läge, men du kan ange att de ska öppna webbplatser i ett fristående Internet Explorer 11-fönster i stället. Om du vill ändra det här beteendet arkiverar du en supportbegäran.

#### <a name="add-sites-to-the-enterprise-mode-site-list"></a>Lägga till webbplatser i webbplatslistan i företagsläge
För att webbplatser ska öppnas i Internet Explorer-läge måste du inkludera dem i [listan Enterprise Site](/DeployEdge/edge-ie-mode-sitelist). Du ansvarar för att underhålla och distribuera listan över företagswebbplatser. Mer information finns i [Konfigurera med webbplatslistan i Konfigurera företagsläge](/DeployEdge/edge-ie-mode-policies#configure-using-the-configure-the-enterprise-mode-site-list-policy)

### <a name="other-settings"></a>Andra inställningar

#### <a name="enable-site-isolation-for-every-site"></a>Aktivera webbplatsisolering för varje webbplats

**Standardvärde:** Aktiverad

När den här principen är aktiverad kan användarna inte välja bort standardbeteendet som varje webbplats körs i en egen process.

#### <a name="supported-authentication-schemes"></a>Autentiseringsscheman som stöds

**Standardvärde:** NTLM, Förhandla

Microsoft Hanterat skrivbord stöder inte scheman för grundläggande autentisering eller sammanfattningsautentisering.

#### <a name="automatically-import-another-browsers-data-and-settings-at-first-run"></a>Importera andra webbläsares data och inställningar automatiskt vid första körningen

**Standardvärde:** Importera automatiskt alla datatyper och inställningar som stöds från standardwebbläsaren 

När den här principen används hoppar First Run Experience över importavsnittet, vilket minimerar användarinteraktion. Webbläsardata från äldre versioner av Microsoft Edge kommer alltid att migreras tyst vid första körningen, oavsett den här inställningen. 


## <a name="settings-you-manage"></a>Inställningar hanterar du

Du kan distribuera Microsoft Edge inställningar som inte tidigare beskrivits med hjälp av profilen Administrationsmallar i Microsoft Intune. Mer information finns i [Konfigurera Microsoft Edge principinställningar med Microsoft Intune](/deployedge/configure-edge-with-intune). Om du vill utvärdera en princip som för närvarande inte ingår i administrationsmallarna för Microsoft Edge i Intune kan du använda anpassade inställningar för Windows 10-enheter i Intune.

### <a name="enabling-specific-chrome-extensions"></a>Aktivera specifika Chrome-tillägg

Administrationsmallen ger en inställning för att distribuera vissa Chrome-tillägg med Microsoft Intune. Du hittar den i **Datorkonfiguration eller > Microsoft Edge > tillägg > Tillåt att specifika tillägg installeras**.

### <a name="install-extensions-silently"></a>Installera tillägg utan att du behöver göra några installationen

Du kan också använda administrationsmallen för att Microsoft Edge att installera tillägg utan att meddela användaren. Du hittar den i **Datorkonfiguration > Microsoft Edge > Tillägg > Styra vilka tillägg som installeras utan att du behöver göra något.**

### <a name="microsoft-edge-update-policies"></a>Microsoft Edge för uppdateringar
För att säkerställa Microsoft Edge uppdateringar korrekt ska du inte ändra Microsoft Edge [principer för uppdateringar.](/deployedge/microsoft-edge-update-policies)

### <a name="other-common-enterprise-policies"></a>Andra vanliga företagsprinciper

Microsoft Edge erbjuder många andra principer. Det här är några av de vanligaste:
 
- [Konfigurera webbplatser i listrutan för företagswebbplatser och IE-läge](/deployedge/edge-ie-mode-sitelist)
- [Konfigurera inställningar för startsida, startsida och ny fliksida](/deployedge/microsoft-edge-policies#startup-home-page-and-new-tab-page)
- [Konfigurera surfspelsinställning](/deployedge/microsoft-edge-policies#allowsurfgame)
- [Konfigurera proxyserverinställningar](/deployedge/microsoft-edge-policies#proxy-server)
