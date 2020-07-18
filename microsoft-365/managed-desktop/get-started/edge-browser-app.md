---
title: Ny Microsoft Edge
description: ''
keywords: webbläsare, Microsoft Managed Desktop, Microsoft 365, tjänst, dokumentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 916ddaea2bc91c56944d4561771c1e807447d604
ms.sourcegitcommit: 63887d742c59cc660fc85537b335e98a9dc66fbe
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/18/2020
ms.locfileid: "45170677"
---
# <a name="new-microsoft-edge-app"></a>Ny Microsoft Edge-app

Den nya [webbläsaren Microsoft Edge](https://www.microsoft.com/edge) ger prestanda i världsklass med mer sekretess, mer produktivitet och mer värde medan du surfar. Microsoft Managed Desktop erbjuder en offentlig förhandsversion av distributionen av den nya Edge-webbläsaren i din miljö.

## <a name="initial-deployment"></a>Inledande distribution

Om du vill migrera dina Microsoft Managed Desktop-enheter till den nya webbläsaren Microsoft Edge filar du en IT-supportbiljett via Microsoft Managed Desktop Portal. Vi distribuerar Edge Stable-kanalen till testgruppen när du arkiverar biljetten och distribuerar den sedan i varje efterföljande distributionsgrupp var 24:e timme. Om du vill pausa distributionen sparar du en annan biljett där du ber operationerna att spärra.

## <a name="updates-to-microsoft-edge"></a>Uppdateringar av Microsoft Edge

Microsoft Managed Desktop distribuerar den [stabila kanalen](https://docs.microsoft.com/deployedge/microsoft-edge-channels#stable-channel) för Microsoft Edge som uppdateras automatiskt ungefär var sjätte vecka. Uppdateringar på den stabila kanalen lanseras [successivt](https://docs.microsoft.com/deployedge/microsoft-edge-update-progressive-rollout) av Microsoft Edge-produktgruppen för att säkerställa bästa möjliga upplevelse för kunderna. Microsoft Edge Beta-kanalen är inte tillgänglig för närvarande.

Ändra inte Microsoft [Edge-uppdateringsprinciperna](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies)för att säkerställa att Microsoft Edge uppdateras korrekt.

## <a name="settings-managed-by-microsoft-managed-desktop"></a>Inställningar som hanteras av Microsoft Managed Desktop

Microsoft Managed Desktop har skapat en standarduppsättning principer för Microsoft Edge för att skydda webbläsaren. Standardinställningarna för webbläsaren är följande:

### <a name="microsoft-edge-extensions"></a>Microsoft Edge-tillägg

Säkerhetsbaslinjen för Microsoft Edge på Microsoft Managed Desktop-enheter anger två principer för att inaktivera alla Chrome-tillägg och säkra slutanvändare. Information om hur du aktiverar och distribuerar tillägg i din miljö finns i Inställningar som du hanterar. 

#### <a name="extension-installation-blocklist"></a>Blockeringslista för tilläggsinstallation
**Standardvärde:** Alla

Microsoft Managed Desktop anger den här principen för att förhindra att Chrome-tillägg installeras på hanterade slutpunkter. Det finns kända risker som associeras med modellen för kromtillägg, inklusive dataskydd, sekretess och andra risker som kan äventyra enheter. 

#### <a name="allow-user-level-native-messaging-hosts-installed-without-admin-permissions"></a>Tillåt inbyggda meddelandevärdar på användarnivå (installeras utan administratörsbehörighet)

**Standardvärde:** Inaktiverad

Genom att inaktivera den här principen använder Microsoft Edge endast inbyggda meddelandevärdar som är installerade på systemnivå. Inbyggda meddelandevärdar är en del av Chrome-tillägg som gör det möjligt för webbläsaren att interagera med andra delar av användarens slutpunkt, vilket skapar en mängd olika säkerhetsproblem.  

### <a name="secure-sockets-layer-ssl"></a>Ssl (Secure Sockets Layer)

#### <a name="minimum-ssl-version"></a>Minsta SSL-version

**Standardvärde:** Minst TLS 1.2 stöds

Om du vill använda den mindre säkra TLS 1.1 kan du begära detta.

#### <a name="allows-users-to-proceed-from-the-ssl-warning-page"></a>Tillåter användare att gå vidare från SSL-varningssidan

**Standardvärde:** Inaktiverad

Vi rekommenderar inte att du aktiverar den här inställningen eftersom den tillåter användare att besöka webbplatser med SSL-fel.

### <a name="microsoft-defender-smart-screen"></a>Microsoft Defender Smart Skärm

#### <a name="configure-microsoft-defender-smartscreen"></a>Konfigurera Smartskärm för Microsoft Defender

**Standardvärde:** Aktiverat

Aktiverad som standard för att skydda slutanvändare.

#### <a name="microsoft-defender-smartscreen-prompts-for-sites"></a>Microsoft Defender SmartScreen uppmanas för webbplatser

**Standardvärde:** Aktiverat

Vi rekommenderar inte att du inaktiverar den här inställningen eftersom det skulle göra det möjligt för användare att ignorera varningar och fortsätta till potentiellt skadliga webbplatser.

#### <a name="prevent-bypassing-of-microsoft-defender-smartscreen-warnings-about-downloads"></a>Förhindra förbikoppling av Microsoft Defender SmartScreen-varningar om nedladdningar

**Standardvärde:** Aktiverat

Vi rekommenderar inte att du inaktiverar den här inställningen eftersom det skulle göra det möjligt för användare att ignorera varningar och slutföra overifierade nedladdningar.

### <a name="adobe-flash"></a>Adobe Flash

#### <a name="default-adobe-flash-setting"></a>Standardinställning för Adobe Flash

**Standardvärde:** Inaktiverad

Vi rekommenderar inte att du använder Flash på grund av tillhörande säkerhetsrisker. Om du fortfarande har processer som är beroende av Flash, ställa in **[PluginsAllowedForUrls](https://docs.microsoft.com/deployedge/microsoft-edge-policies#pluginsallowedforurls)** politik för att aktivera Flash för webbplatser som behöver det. Om du inte kan underhålla en tillåten lista över webbplatser som ska använda Flash skickar du en ändringsbegäran för att ändra värdet till **Klicka för att spela**, vilket gör att användarna kan välja när det är lämpligt att köra Flash.

### <a name="password-manager"></a>Lösenordshanterare

#### <a name="enable-saving-passwords-to-the-password-manager"></a>Aktivera spara lösenord till lösenordshanteraren

**Standardvärde:** Inaktiverad

Vi rekommenderar inte att låta slutanvändare spara lösenord på sin enhet.

### <a name="other-settings"></a>Andra inställningar

#### <a name="enable-site-isolation-for-every-site"></a>Aktivera webbplatsisolering för varje plats

**Standardvärde:** Aktiverat

När den här principen är aktiverad kan användarna inte välja bort standardbeteendet där varje plats körs i sin egen process.

#### <a name="supported-authentication-schemes"></a>Autentiseringsscheman som stöds

**Standardvärde:** NTLM, Förhandla

Microsoft Managed Desktop stöder inte grundläggande autentiserings- eller sammanfattande autentiseringsscheman.

#### <a name="automatically-import-another-browsers-data-and-settings-at-first-run"></a>Importera en annan webbläsares data och inställningar automatiskt vid första körningen

**Standardvärde:** Importera alla datatyper och inställningar som stöds automatiskt från standardwebbläsaren 

När den här principen tillämpas hoppar första körningen över importavsnittet, vilket minimerar användarinteraktionen. Webbläsardata från äldre versioner av Microsoft Edge migreras alltid tyst vid den första körningen, oavsett den här inställningen. 


## <a name="settings-you-manage"></a>Inställningar som du hanterar

Du kan distribuera alla Microsoft Edge-inställningar som inte tidigare beskrivits med hjälp av profilen Administrativa mallar i Microsoft Intune. Mer information finns i [Konfigurera principinställningar för Microsoft Edge med Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune). Om du vill utvärdera en princip som för närvarande inte ingår i Microsoft Edge Administrativa mallar i Intune kan du använda anpassade inställningar för Windows 10-enheter i Intune.

### <a name="enabling-specific-chrome-extensions"></a>Aktivera specifika Chrome-tillägg

Den administrativa mallen erbjuder en inställning för att distribuera vissa Chrome-tillägg med Microsoft Intune. Du hittar den i **datorkonfiguration > Microsoft Edge >-tillägg > tillåt att specifika tillägg installeras**.

### <a name="install-extensions-silently"></a>Installera tillägg tyst

Du kan också använda den administrativa mallen för att ange Microsoft Edge för att installera tillägg utan att varna användaren. Du hittar den i **datorkonfiguration > Microsoft Edge >-tillägg > Kontrollerar vilka tillägg som installeras tyst**.

### <a name="other-common-enterprise-policies"></a>Andra gemensamma företagspolitiker

Microsoft Edge erbjuder många ytterligare policyer. Dessa är några av de vanligaste:
 
- [Konfigurera platser i företagswebbplatslistan och IE-läget](https://docs.microsoft.com/deployedge/edge-ie-mode-sitelist)
- [Konfigurera inställningar för start, startsida och ny fliksida](https://docs.microsoft.com/deployedge/microsoft-edge-policies#startup-home-page-and-new-tab-page)
- [Konfigurera inställningen Surf spel](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowsurfgame)
- [Konfigurera proxyserverinställningar](https://docs.microsoft.com/deployedge/microsoft-edge-policies#proxy-server)

