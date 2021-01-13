---
title: Nya Microsoft Edge
description: Förklarar hur den nya webbläsaren distribueras och uppdateras
keywords: webbläsare, Microsoft hanterat skriv bord, Microsoft 365, tjänst, dokumentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 42ff665e8ba9c369e29eeeafd27affff04b40966
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841345"
---
# <a name="new-microsoft-edge-app"></a>Ny Microsoft Edge-app

I den nya [webbläsaren Microsoft Edge](https://www.microsoft.com/edge) får du världs klassens prestanda med mer integritet, mer produktivitet och mer värde när du bläddrar. Microsoft Managed Desktop erbjuder en offentlig för hands version av distributionen av den nya webbläsaren i din miljö.

## <a name="initial-deployment"></a>Inledande distribution

Om du vill migrera dina Microsoft Managed Station ära enheter till den nya webbläsaren Microsoft Edge kan du läsa en IT support-biljett via Microsoft Managed Desktop-portalen. Vi kommer att distribuera Edge stabil kanal till test gruppen när du arkiverar biljetten och sedan distribuera den i varje senare distributions grupp varje dygn. Om du vill pausa distributionen kan du spara en fil i en annan biljett.

[Beta kanalen](https://docs.microsoft.com/deployedge/microsoft-edge-channels#beta-channel) är också tillgänglig på begäran om representativ verifiering inom din organisation. Microsoft Managed Desktop distribuerar programmet som obligatoriskt för test och första grupper så att alla dessa användare har beta kanalen utöver den stabila kanalen. För andra användare som behöver ha till gång till beta kanalen lägger du till dem till den **moderna beta-användare-gruppen för arbets platser** och får dem att installera från företags portalen

## <a name="updates-to-microsoft-edge"></a>Uppdateringar av Microsoft Edge

Microsoft Managed Desktop distribuerar den [stabila kanalen](https://docs.microsoft.com/deployedge/microsoft-edge-channels#stable-channel) i Microsoft Edge, som uppdateras automatiskt var sjätte vecka. Uppdateringar i den stabila kanalen lyfts [successivt](https://docs.microsoft.com/deployedge/microsoft-edge-update-progressive-rollout) av Microsoft Edge-produktnyckeln för att säkerställa den bästa upplevelsen för kunder. 

[Beta kanalen](https://docs.microsoft.com/deployedge/microsoft-edge-channels#beta-channel) distribueras till enheter i både test-och första grupperna för representativ verifiering i organisationen. Denna kanal stöds helt och uppdateras automatiskt med nya funktioner ungefär var sjätte vecka.

Om du vill vara säker på att Microsoft Edge uppdateras korrekt ska du inte ändra Microsofts Edge [Update-principer](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies).



## <a name="settings-managed-by-microsoft-managed-desktop"></a>Inställningar som hanteras av Microsoft Managed Desktop

Microsoft Managed Desktop har skapat en standard uppsättning principer för Microsoft Edge för att skydda webbläsaren. Standardinställningarna för webbläsaren är följande:

### <a name="microsoft-edge-extensions"></a>Microsoft Edge-tillägg

Säkerhets bas linjen för Microsoft Edge på Microsoft Managed Station ära datorer ställer in två principer för att inaktivera alla Chrome-tillägg och säkra användare. Om du vill aktivera och distribuera tillägg i miljön läser du inställningar som du hanterar. 

#### <a name="extension-installation-blocklist"></a>Installations blockeringslista
**Standardvärde:** Alla

Microsoft Managed Desktop anger den här principen för att förhindra att Chrome-tillägg installeras på hanterade slut punkter. Det finns kända risker som är förknippade med krom tilläggs modellen, inklusive data förlust skydd, integritet och andra risker som kan äventyra enheter. 

#### <a name="allow-user-level-native-messaging-hosts-installed-without-admin-permissions"></a>Tillåt interna meddelanden på användar nivå (installeras utan Administratörs behörigheter)

**Standardvärde:** Aktiv

Genom att inaktivera den här principen använder Microsoft Edge endast interna meddelande värdar som är installerade på system nivå. Interna meddelande värdar är en del av Chrome-tillägg, som gör att webbläsaren interagerar med andra delar av användarens slut punkt och skapar en mängd olika säkerhets problem.  

### <a name="secure-sockets-layer-tlsssl"></a>SSL (Secure Sockets Layer)

#### <a name="minimum-tls-version"></a>Lägsta TLS-version

**Standardvärde:** Minsta TLS 1,2 stöds

Om du vill använda den mindre säkra TLS-1,1 kan du spara en begäran.

#### <a name="allows-users-to-proceed-from-the-ssl-warning-page"></a>Tillåter användare att gå vidare från sidan SSL-varning

**Standardvärde:** Aktiv

Vi rekommenderar inte att du aktiverar den här inställningen eftersom den tillåter användare att besöka webbplatser med TSL-fel.

### <a name="microsoft-defender-smartscreen"></a>Microsoft Defender SmartScreen

#### <a name="configure-windows-defender-smartscreen"></a>Konfigurera Windows Defender SmartScreen

**Standardvärde:** Aktiverat

Aktiverat som standard för att skydda användare.

#### <a name="windows-defender-smartscreen-prompts-for-sites"></a>Windows Defender SmartScreen-frågor för webbplatser

**Standardvärde:** Aktiverat

Vi rekommenderar inte att du inaktiverar den här inställningen eftersom den tillåter att användare ignorerar varningar och fortsätter till potentiellt skadliga webbplatser.

#### <a name="prevent-bypassing-of-windows-defender-smartscreen-warnings-about-downloads"></a>Förhindra att varningar från Windows Defender SmartScreen om nedladdningar ignoreras

**Standardvärde:** Aktiverat

Vi rekommenderar inte att du inaktiverar den här inställningen eftersom den tillåter användare att ignorera varningar och slutföra icke verifierade nedladdningar.

### <a name="adobe-flash"></a>Adobe Flash

#### <a name="default-adobe-flash-setting"></a>Standard inställning för Adobe Flash

**Standardvärde:** Aktiv

Vi rekommenderar inte att du använder Flash på grund av associerade säkerhets risker. Om du fortfarande har processer som är beroende av Flash kan du ange **[PluginsAllowedForUrls](https://docs.microsoft.com/deployedge/microsoft-edge-policies#pluginsallowedforurls)** -principen för att aktivera Flash för webbplatser som behöver den. Om du inte kan behålla en lista över tillåtna webbplatser för att använda Flash, File a ändringsbegäran för att ändra värdet till **Klicka för att spela upp**, vilket gör att användare kan välja när det är lämpligt att köra Flash.

### <a name="password-manager"></a>Lösen ords hanteraren

#### <a name="enable-saving-passwords-to-the-password-manager"></a>Aktivera Spara lösen ord i lösen ords hanteraren

**Standardvärde:** Aktiv

Vi rekommenderar inte att användare sparar lösen ord på sina enheter.

### <a name="internet-explorer-mode-in-microsoft-edge"></a>Internet Explorer-läge i Microsoft Edge
I IE-läge på Microsoft Edge är det enkelt att använda alla webbplatser som organisationen behöver i en och samma webbläsare. Den integrerade krom motorn används för webbplatser som är kompatibla med krom åter givnings motorn och använder Trident MSHTML-motorn från Internet Explorer 11 (IE11) för webbplatser som inte är eller har beroenden till IE-funktioner. [Läs mer] (https://docs.microsoft.com/DeployEdge/edge-ie-mode) 

Microsoft Managed Desktop gör att Internet Explorer-läget för dina enheter används som standard 

#### <a name="internet-explorer-mode-integration"></a>Integrering med Internet Explorer
**Standardvärde:** Internet Explorer-läge

Som standard är enheter inställda på att använda Internet Explorer-läge, men du kan konfigurera dem så att de öppnas i ett fristående fönster i Internet Explorer 11. Om du vill ändra detta kan du spara en supportbegäran.

#### <a name="add-sites-to-the-enterprise-mode-site-list"></a>Lägga till webbplatser i webbplats listan för företags lägen
För att webbplatser ska öppnas i Internet Explorer-läge måste du inkludera dem i [listan med företags webbplatser](https://docs.microsoft.com/DeployEdge/edge-ie-mode-sitelist). Att behålla och distribuera företags plats listan är ditt ansvar. Mer information finns i [Konfigurera använda webbplatsen för webbplats listan för att konfigurera företags läge](https://docs.microsoft.com/DeployEdge/edge-ie-mode-policies#configure-using-the-configure-the-enterprise-mode-site-list-policy)

### <a name="other-settings"></a>Andra inställningar

#### <a name="enable-site-isolation-for-every-site"></a>Aktivera webbplats isolering för varje webbplats

**Standardvärde:** Aktiverat

När den här principen är aktive rad kan användarna inte välja standard beteendet som varje webbplats körs i sin egen process.

#### <a name="supported-authentication-schemes"></a>Autentiseringsscheman som stöds

**Standardvärde:** NTLM, Negotiate

Microsoft Managed Desktop stöder inte grundläggande och sammanfattad autentisering.

#### <a name="automatically-import-another-browsers-data-and-settings-at-first-run"></a>Importera data och inställningar från en annan webbläsare automatiskt vid första körningen

**Standardvärde:** Importera automatiskt alla data typer och inställningar från standard webbläsaren 

Med den här policyn hoppar den första körningen över import-delen och minimerar användarnas interaktion. Webb läsar data från äldre versioner av Microsoft Edge migreras alltid tyst vid första körningen, oavsett den här inställningen. 


## <a name="settings-you-manage"></a>Inställningar som du hanterar

Du kan distribuera alla Microsoft Edge-inställningar som inte tidigare har beskrivits med hjälp av profilen för administrativa mallar i Microsoft Intune. Mer information finns i [Konfigurera princip inställningar för Microsoft Edge med Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune). Om du vill utvärdera en princip som för närvarande inte ingår i Microsoft Edge Administrative Templates i Intune kan du använda anpassade inställningar för Windows 10-enheter i Intune.

### <a name="enabling-specific-chrome-extensions"></a>Aktivera specifika Chrome-tillägg

Den administrativa mallen erbjuder en inställning för att distribuera särskilda Chrome-tillägg med Microsoft Intune. Du hittar det i **dator konfiguration > Microsoft Edge >-tillägg > tillåta specifika tillägg att installeras**.

### <a name="install-extensions-silently"></a>Installera tillägg tyst

Du kan också använda den administrativa mallen för att ställa in Microsoft Edge för att installera tillägg utan att användaren meddelas. Du hittar det i **dator konfiguration > Microsoft Edge > extensions > kontrollerar vilka tillägg som installeras tyst**.

### <a name="microsoft-edge-update-policies"></a>Uppdaterings policy för Microsoft Edge
Om du vill vara säker på att Microsoft Edge uppdateras korrekt ska du inte ändra Microsofts Edge [Update-principer](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies).

### <a name="other-common-enterprise-policies"></a>Andra vanliga företags principer

Microsoft Edge erbjuder många andra principer. Här är några av de vanligaste:
 
- [Konfigurera webbplatser i företagets webbplats lista och IE-läge](https://docs.microsoft.com/deployedge/edge-ie-mode-sitelist)
- [Konfigurera inställningar för start-, start sida och ny flik](https://docs.microsoft.com/deployedge/microsoft-edge-policies#startup-home-page-and-new-tab-page)
- [Konfigurera spel för surfa](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowsurfgame)
- [Konfigurera proxyserverinställningar](https://docs.microsoft.com/deployedge/microsoft-edge-policies#proxy-server)

