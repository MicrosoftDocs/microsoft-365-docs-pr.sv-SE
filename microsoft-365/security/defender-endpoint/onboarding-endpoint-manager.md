---
title: Introduktion med Microsoft Endpoint Manager
description: Lär dig hur du onboardar till Microsoft Defender för Endpoint med Microsoft Endpoint Manager
keywords: onboarding, configuration, deploy, deployment, endpoint manager, Microsoft Defender for Endpoint, collection creation, endpoint detection response, next generation protection, attack surface reduction, microsoft endpoint manager
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 397aa8a0e8f0523c9975d40759d39369c221222b
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228981"
---
# <a name="onboarding-using-microsoft-endpoint-manager"></a>Introduktion med Microsoft Endpoint Manager

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Den här artikeln är en del av distributionsguiden och fungerar som ett exempel på onboarding-metod.

I ämnet [Planering](deployment-strategy.md) finns det flera metoder för att introducera enheter till tjänsten. Det här avsnittet beskriver den molnbaserade arkitekturen.

![Bild av molnbaserad arkitektur ](images/cloud-native-architecture.png)
 *Diagram över miljöarkitekturer*

Defender för Endpoint har stöd för registrering av olika slutpunkter och verktyg, men den här artikeln täcker inte in dem. Mer information om allmän onboarding med andra distributionsverktyg och metoder som stöds finns i [Översikt över onboarding.](onboarding.md)

[Microsoft Endpoint Manager](/mem/endpoint-manager-overview) är en lösningsplattform som ger en enhetlig plattform för flera tjänster. Den innehåller [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) för molnbaserad enhetshantering.

Det här avsnittet leder användarna i:

- Steg 1: Onboarding-enheter till tjänsten genom att skapa en grupp i Microsoft Endpoint Manager (MEM) för att tilldela konfigurationer på
- Steg 2: Konfigurera Defender för slutpunktsfunktioner med Microsoft Endpoint Manager

Den här introduktionsvägledningen går igenom följande grundläggande steg som du måste vidta när du använder Microsoft Endpoint Manager:

- [Identifiera målenheter eller -användare](#identify-target-devices-or-users)
  - Skapa en Azure Active Directory (användare eller enhet)
- [Skapa en konfigurationsprofil](#step-2-create-configuration-policies-to-configure-microsoft-defender-for-endpoint-capabilities)
  - I Microsoft Endpoint Manager hjälper vi dig att skapa en separat princip för varje funktion.

## <a name="resources"></a>Resurser

Här är de länkar du behöver för resten av processen:

- [MEM-portal](https://aka.ms/memac)
- [Säkerhetscenter](https://securitycenter.windows.com/)
- [Intune-säkerhetsbaslinjer](/mem/intune/protect/security-baseline-settings-defender-atp#microsoft-defender)

Mer information om Microsoft Endpoint Manager finns i följande resurser:

- [Microsoft Endpoint Manager sidan](/mem/)
- [Blogginlägg om intune och ConfigMgr](https://www.microsoft.com/microsoft-365/blog/2019/11/04/use-the-power-of-cloud-intelligence-to-simplify-and-accelerate-it-and-the-move-to-a-modern-workplace/)
- [Introduktionsvideo om MEM](https://www.microsoft.com/microsoft-365/blog/2019/11/04/use-the-power-of-cloud-intelligence-to-simplify-and-accelerate-it-and-the-move-to-a-modern-workplace)

## <a name="step-1-onboard-devices-by-creating-a-group-in-mem-to-assign-configurations-on"></a>Steg 1: Introducera enheter genom att skapa en grupp i MEM för att tilldela konfigurationer på

### <a name="identify-target-devices-or-users"></a>Identifiera målenheter eller -användare

I det här avsnittet skapar vi en testgrupp där du kan tilldela dina konfigurationer.

> [!NOTE]
> Intune använder Azure Active Directory (Azure AD) grupper för att hantera enheter och användare. Som Intune-administratör kan du konfigurera grupper så att de passar organisationens behov.
>
> Mer information finns i Lägga [till grupper för att ordna användare och enheter.](/mem/intune/fundamentals/groups-add)

### <a name="create-a-group"></a>Skapa en grupp

1. Öppna MEM-portalen.

2. Öppna **Grupper > Ny grupp.**

    > [!div class="mx-imgBorder"]
    > ![Bild på Microsoft Endpoint Manager portal1](images/66f724598d9c3319cba27f79dd4617a4.png)

3. Ange information och skapa en ny grupp.

    > [!div class="mx-imgBorder"]
    > ![Bild på Microsoft Endpoint Manager portal2](images/b1e0206d675ad07db218b63cd9b9abc3.png)

4. Lägg till testanvändaren eller testenheten.

5. I fönstret **Grupper > Alla grupper** öppnar du den nya gruppen.

6. Välj  **Medlemmar > Lägg till medlemmar**.

7. Leta reda på testanvändaren eller enheten och markera den.

    > [!div class="mx-imgBorder"]
    > ![Bild på Microsoft Endpoint Manager portal3](images/149cbfdf221cdbde8159d0ab72644cd0.png)

8. Testgruppen har nu en medlem att testa.

## <a name="step-2-create-configuration-policies-to-configure-microsoft-defender-for-endpoint-capabilities"></a>Steg 2: Skapa konfigurationsprinciper för att konfigurera Microsoft Defender för Endpoint-funktioner

I följande avsnitt ska du skapa ett antal konfigurationsprinciper.

Först finns en konfigurationsprincip för att välja vilka grupper av användare eller enheter som ska introduceras i Defender för Slutpunkt:

- [Identifiering och svar för slutpunkt](#endpoint-detection-and-response)

Sedan fortsätter du genom att skapa flera olika typer av slutpunktssäkerhetsprinciper:

- [Nästa generations skydd](#next-generation-protection)
- [Minskning av attackytan](#attack-surface-reduction--attack-surface-reduction-rules)

### <a name="endpoint-detection-and-response"></a>Identifiering och svar av slutpunkt

1. Öppna MEM-portalen.

2. Gå till **Slutpunktssäkerhet > identifiering och svar av slutpunkt.** Klicka på **Skapa profil.**

    > [!div class="mx-imgBorder"]
    > ![Bild på Microsoft Endpoint Manager portal4](images/58dcd48811147feb4ddc17212b7fe840.png)

3. Under **Plattform väljer du Windows 10 senare, Profil – Identifiering av slutpunkt och svar > Skapa**.

4. Ange ett namn och en beskrivning och välj sedan **Nästa.**

    > [!div class="mx-imgBorder"]
    > ![Bild på Microsoft Endpoint Manager portal5](images/a5b2d23bdd50b160fef4afd25dda28d4.png)

5. Välj inställningar efter behov och välj sedan  **Nästa**.

    > [!div class="mx-imgBorder"]
    > ![Bild på Microsoft Endpoint Manager portal6](images/cea7e288b5d42a9baf1aef0754ade910.png)

    > [!NOTE]
    > I den här instansen har det här fyllts i automatiskt eftersom Defender för Slutpunkt redan har integrerats med Intune. Mer information om integrering finns i Aktivera [Microsoft Defender för slutpunkt i Intune.](/mem/intune/protect/advanced-threat-protection-configure#to-enable-microsoft-defender-atp)
    >
    > Följande bild visar ett exempel på vad som visas när Microsoft Defender för Slutpunkt inte är integrerat med Intune:
    >
    > ![Bild på Microsoft Endpoint Manager portal7](images/2466460812371ffae2d19a10c347d6f4.png)

6. Lägg till omfattningstaggar om det behövs och välj **sedan Nästa.**

    > [!div class="mx-imgBorder"]
    > ![Bild på Microsoft Endpoint Manager portal8](images/ef844f52ec2c0d737ce793f68b5e8408.png)

7. Lägg till testgrupp genom att **klicka på Välj grupper som ska ingå** och välj sedan **Nästa.**

    > [!div class="mx-imgBorder"]
    > ![Bild på Microsoft Endpoint Manager portal9](images/fc3525e20752da026ec9f46ab4fec64f.png)

8. Granska och acceptera och välj sedan  **Skapa**.

    > [!div class="mx-imgBorder"]
    > ![Bild på Microsoft Endpoint Manager portal10](images/289172dbd7bd34d55d24810d9d4d8158.png)

9. Du kan visa din slutförda princip.

    > [!div class="mx-imgBorder"]
    > ![Bild av Microsoft Endpoint Manager portal11](images/5a568b6878be8243ea2b9d82d41ed297.png)

### <a name="next-generation-protection"></a>Nästa generations skydd

1. Öppna MEM-portalen.

2. Gå till **Slutpunktssäkerhet > Antivirus > Skapa princip**.

    > [!div class="mx-imgBorder"]
    > ![Bild på Microsoft Endpoint Manager portal12](images/6b728d6e0d71108d768e368b416ff8ba.png)

3. Välj **plattform – Windows 10 och senare – Windows profil och plattform – Microsoft Defender Antivirus > Skapa.**

4. Ange namn och beskrivning och välj sedan  **Nästa**.

    > [!div class="mx-imgBorder"]
    > ![Bild på Microsoft Endpoint Manager portal13](images/a7d738dd4509d65407b7d12beaa3e917.png)

5. På sidan **Konfigurationsinställningar:** Ange de konfigurationer du behöver för Microsoft Defender Antivirus (Molnskydd, Undantag, Real-Time skydd och åtgärd).

    > [!div class="mx-imgBorder"]
    > ![Bild på Microsoft Endpoint Manager portal14](images/3840b1576d6f79a1d72eb14760ef5e8c.png)

6. Lägg till omfattningstaggar om det behövs och välj **sedan Nästa.**

    > [!div class="mx-imgBorder"]
    > ![Bild på Microsoft Endpoint Manager portal15](images/2055e4f9b9141525c0eb681e7ba19381.png)

7. Välj de grupper du vill inkludera, tilldela till testgruppen och välj sedan **Nästa.**

    > [!div class="mx-imgBorder"]
    > ![Bild på Microsoft Endpoint Manager portal16](images/48318a51adee06bff3908e8ad4944dc9.png)

8. Granska och skapa och välj sedan  **Skapa**.

    > [!div class="mx-imgBorder"]
    > ![Bild på Microsoft Endpoint Manager portal17](images/dfdadab79112d61bd3693d957084b0ec.png)

9. Konfigurationsprincipen som du har skapat visas.

    > [!div class="mx-imgBorder"]
    > ![Bild på Microsoft Endpoint Manager portal18](images/38180219e632d6e4ec7bd25a46398da8.png)

### <a name="attack-surface-reduction--attack-surface-reduction-rules"></a>Minskning av attackytan – regler för att minska attackytan

1. Öppna MEM-portalen.

2. Gå till **Slutpunktssäkerhet > minska attackytan**.

3. Välj  **Skapa princip**.

4. Välj **plattform – Windows 10 och senare – Profil – Regler för minskning av attackytor > Skapa**.

    > [!div class="mx-imgBorder"]
    > ![Bild av Microsoft Endpoint Manager portal19](images/522d9bb4288dc9c1a957392b51384fdd.png)

5. Ange ett namn och en beskrivning och välj sedan **Nästa.**

    > [!div class="mx-imgBorder"]
    > ![Bild på Microsoft Endpoint Manager portal20](images/a5a71fd73ec389f3cdce6d1a6bd1ff31.png)

6. På sidan **Konfigurationsinställningar:** Ange de konfigurationer du behöver för att minska attackytan och välj sedan **Nästa.**

    > [!NOTE]
    > Vi kommer att konfigurera alla minskningsregler för attackytor till Granskning.
    >
    > Mer information finns i Regler [för att minska attackytan](attack-surface-reduction.md).

    > [!div class="mx-imgBorder"]
    > ![Bild på Microsoft Endpoint Manager portal21](images/dd0c00efe615a64a4a368f54257777d0.png)

7. Lägg till omfattningstaggar efter behov och välj **sedan Nästa.**

    > [!div class="mx-imgBorder"]
    > ![Bild på Microsoft Endpoint Manager portal22](images/6daa8d347c98fe94a0d9c22797ff6f28.png)

8. Välj de grupper du vill inkludera och tilldela till testgruppen och välj sedan **Nästa.**

    > [!div class="mx-imgBorder"]
    > ![Bild på Microsoft Endpoint Manager portal23](images/45cefc8e4e474321b4d47b4626346597.png)

9. Granska informationen och välj sedan  **Skapa**.

    > [!div class="mx-imgBorder"]
    > ![Bild på Microsoft Endpoint Manager portal24](images/2c2e87c5fedc87eba17be0cdeffdb17f.png)

10. Visa principen.

    > [!div class="mx-imgBorder"]
    > ![Bild på Microsoft Endpoint Manager portal25](images/7a631d17cc42500dacad4e995823ffef.png)

### <a name="attack-surface-reduction--web-protection"></a>Minskning av attackytan – webbskydd

1. Öppna MEM-portalen.

2. Gå till **Slutpunktssäkerhet > minska attackytan**.

3. Välj  **Skapa princip**.

4. Välj **Windows 10 och Senare – Webbskydd > Skapa**.

    > [!div class="mx-imgBorder"]
    > ![Bild på Microsoft Endpoint Manager portal26](images/cd7b5a1cbc16cc05f878cdc99ba4c27f.png)

5. Ange ett namn och en beskrivning och välj sedan **Nästa.**

    > [!div class="mx-imgBorder"]
    > ![Bild på Microsoft Endpoint Manager portal27](images/5be573a60cd4fa56a86a6668b62dd808.png)

6. På sidan **Konfigurationsinställningar:** Ange de konfigurationer som krävs för webbskydd och välj sedan **Nästa.**

    > [!NOTE]
    > Vi konfigurerar webbskydd för blockering.
    >
    > Mer information finns i [Webbskydd](web-protection-overview.md).

    > [!div class="mx-imgBorder"]
    > ![Bild på Microsoft Endpoint Manager portal28](images/6104aa33a56fab750cf30ecabef9f5b6.png)

7. Lägg **till omfattningstaggar efter behov > Nästa.**

    > [!div class="mx-imgBorder"]
    > ![Bild på Microsoft Endpoint Manager portal29](images/6daa8d347c98fe94a0d9c22797ff6f28.png)

8. Välj **Tilldela för att testa > Nästa**.

    > [!div class="mx-imgBorder"]
    > ![Bild på Microsoft Endpoint Manager portal30](images/45cefc8e4e474321b4d47b4626346597.png)

9. Välj **Granska och skapa > skapa**.

    > [!div class="mx-imgBorder"]
    > ![Bild på Microsoft Endpoint Manager portal31](images/8ee0405f1a96c23d2eb6f737f11c1ae5.png)

10. Visa principen.

    > [!div class="mx-imgBorder"]
    > ![Bild på Microsoft Endpoint Manager portal32](images/e74f6f6c150d017a286e6ed3dffb7757.png)

## <a name="validate-configuration-settings"></a>Verifiera konfigurationsinställningar

### <a name="confirm-policies-have-been-applied"></a>Bekräfta att principer har tillämpats

När konfigurationsprincipen har tilldelats tar det lite tid att tillämpa den.

Mer information om tidsinställningar finns [i Intune-konfigurationsinformation.](/mem/intune/configuration/device-profile-troubleshoot#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned)

Bekräfta att konfigurationsprincipen har använts på testenheten genom att följa följande process för varje konfigurationsprincip.

1. Öppna MEM-portalen och navigera till relevant princip som visas i stegen ovan. I följande exempel visas nästa generations skyddsinställningar.

    > [!div class="mx-imgBorder"]
    > [![Bild på Microsoft Endpoint Manager portal33 ](images/43ab6aa74471ee2977e154a4a5ef2d39.png)](images/43ab6aa74471ee2977e154a4a5ef2d39.png#lightbox)

2. Välj **Konfigurationsprincip för** att visa principstatusen.

    > [!div class="mx-imgBorder"]
    > [![Bild på Microsoft Endpoint Manager portal34 ](images/55ecaca0e4a022f0e29d45aeed724e6c.png)](images/55ecaca0e4a022f0e29d45aeed724e6c.png#lightbox)

3. Välj  **Enhetsstatus** om du vill se statusen.

    > [!div class="mx-imgBorder"]
    > [![Bild på Microsoft Endpoint Manager portal35 ](images/18a50df62cc38749000dbfb48e9a4c9b.png)](images/18a50df62cc38749000dbfb48e9a4c9b.png#lightbox)

4. Välj  **Användarstatus** om du vill se statusen.

    > [!div class="mx-imgBorder"]
    > [![Bild på Microsoft Endpoint Manager portal36 ](images/4e965749ff71178af8873bc91f9fe525.png)](images/4e965749ff71178af8873bc91f9fe525.png#lightbox)

5. Välj  **Status per inställning för** att visa statusen.

    > [!TIP]
    > Den här vyn är mycket användbar om du vill identifiera inställningar som står i konflikt med en annan princip.

    > [!div class="mx-imgBorder"]
    > [![Bild på Microsoft Endpoint Manager portal37 ](images/42acc69d0128ed09804010bdbdf0a43c.png)](images/42acc69d0128ed09804010bdbdf0a43c.png#lightbox)

### <a name="endpoint-detection-and-response"></a>Identifiering och svar av slutpunkt

1. Innan du använder konfigurationen bör inte tjänsten Defender för Endpoint Protection startas.

    > [!div class="mx-imgBorder"]
    > [![Bild på panelen Tjänster1 ](images/b418a232a12b3d0a65fc98248dbb0e31.png)](images/b418a232a12b3d0a65fc98248dbb0e31.png#lightbox)

2. När konfigurationen har tillämpats ska tjänsten Defender för Endpoint Protection startas.

    > [!div class="mx-imgBorder"]
    > [![Bild på panelen Tjänster2 ](images/a621b699899f1b41db211170074ea59e.png)](images/a621b699899f1b41db211170074ea59e.png#lightbox)

3. När tjänsterna körs på enheten visas den i Microsoft Defender Säkerhetscenter.

    > [!div class="mx-imgBorder"]
    > [![Bild av Microsoft Defender Säkerhetscenter ](images/df0c64001b9219cfbd10f8f81a273190.png)](images/df0c64001b9219cfbd10f8f81a273190.png#lightbox)

### <a name="next-generation-protection"></a>Nästa generations skydd

1. Innan du använder principen på en testenhet bör du kunna hantera inställningarna manuellt enligt nedan.

    > [!div class="mx-imgBorder"]
    > ![Bild på inställning sida1](images/88efb4c3710493a53f2840c3eac3e3d3.png)

2. När principen har tillämpats bör du inte kunna hantera inställningarna manuellt.

    > [!NOTE]
    > I följande bild **visas Aktivera moln levererat skydd** och Aktivera **realtidsskydd** som hanterat.

    > [!div class="mx-imgBorder"]
    > ![Bild på inställning sida2](images/9341428b2d3164ca63d7d4eaa5cff642.png)

### <a name="attack-surface-reduction--attack-surface-reduction-rules"></a>Minskning av attackytan – regler för att minska attackytan

1. Innan du tillämpar principen på en testenhet, penna ett PowerShell-fönster och skriv `Get-MpPreference` .

2. Det bör svara med följande rader utan innehåll:

    > AttackSurfaceReductionOnlyExclusions:
    >
    > AttackSurfaceReductionRules_Actions:
    >
    > AttackSurfaceReductionRules_Ids:

    ![Bild på kommandorad1](images/cb0260d4b2636814e37eee427211fe71.png)

3. När du har tillämpat principen på en testenhet öppnar du ett PowerShell-Windows och skriver `Get-MpPreference` .

4. Det bör svara med följande rader med innehåll enligt nedan:

    ![Bild på kommandorad2](images/619fb877791b1fc8bc7dfae1a579043d.png)

### <a name="attack-surface-reduction--web-protection"></a>Minskning av attackytan – webbskydd

1. Öppna ett PowerShell-fönster på testenheten Windows och skriv `(Get-MpPreference).EnableNetworkProtection` .

2. Det bör svara med en nolla enligt nedan.

    ![Bild på kommandorad3](images/196a8e194ac99d84221f405d0f684f8c.png)

3. När du har tillämpat principen öppnar du en PowerShell-Windows och skriver `(Get-MpPreference).EnableNetworkProtection` .

4. Detta bör svara med en 1:a (1) som visas nedan.

    ![Bild på kommandorad4](images/c06fa3bbc2f70d59dfe1e106cd9a4683.png)
