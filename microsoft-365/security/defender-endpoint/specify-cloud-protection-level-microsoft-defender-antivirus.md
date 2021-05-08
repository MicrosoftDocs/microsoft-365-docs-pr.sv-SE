---
title: Ange en moln levererat skyddsnivå för Microsoft Defender Antivirus
description: Ange din nivå av moln levererat skydd för Microsoft Defender Antivirus.
keywords: Microsoft Defender Antivirus, program mot skadlig programvara, säkerhet, defender, moln, aggressivhet, skyddsnivå
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 10/26/2020
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: f441b1bd444cd70fb5b00dfcb5ebcddadf62b220
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274910"
---
# <a name="specify-the-cloud-delivered-protection-level"></a>Ange nivå för molnbaserat skydd

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

Du kan ange din nivå av moln levererat skydd som erbjuds av Microsoft Defender Antivirus med hjälp av Microsoft Endpoint Manager (rekommenderas) eller grupprincip.

> [!TIP]
> Molnskydd är inte bara skydd för filer som lagras i molnet. Microsoft Defender Antivirus-molntjänsten är en mekanism för att tillhandahålla uppdaterat skydd till ditt nätverk och dina enheter (kallas även slutpunkter). Molnskydd med Microsoft Defender Antivirus använder distribuerade resurser och maskininlärning för att ge skydd till dina slutpunkter i en hastighet som är mycket snabbare än traditionella säkerhetsintelligensuppdateringar. Microsoft Intune och Microsoft Endpoint Manager är nu en del av [Microsoft Endpoint Manager.](/mem/endpoint-manager-overview) 


## <a name="use-microsoft-endpoint-manager-to-specify-the-level-of-cloud-delivered-protection"></a>Använd Microsoft Endpoint Manager för att ange nivån för moln levererat skydd

1. Gå till administrationscentret för Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) och logga in.

2. Välj **Endpoint Security**  >  **Antivirus**.

3. Välj en antivirusprofil. (Om du inte redan har en, eller om du vill skapa en ny profil, se Konfigurera inställningar för [enhetsbegränsning i Microsoft Intune.](/intune/device-restrictions-configure)

4. Välj **Egenskaper**. Välj sedan Redigera bredvid **Konfigurationsinställningar.** 

5. Expandera **Molnskydd** och välj sedan **något** av följande i listan Moln levererat skyddsnivå:

    1. **Hög:** Använder en stark identifieringsnivå.
    2. **Hög plus:** Använder **högnivån** och tillämpar ytterligare skyddsåtgärder (kan påverka klientprestandan).
    3. **Nollarvering**: Blockerar alla okända körbara filer.

6. Välj **Granska + spara** och välj sedan **Spara.** 

> [!TIP]
> Behöver du hjälp? Se följande resurser:
> - [Konfigurera slutpunktsskydd](/mem/configmgr/protect/deploy-use/endpoint-protection-configure)
> - [Lägga till inställningar för slutpunktsskydd i Intune](/mem/intune/protect/endpoint-protection-configure)
  

## <a name="use-group-policy-to-specify-the-level-of-cloud-delivered-protection"></a>Använda grupprinciper för att ange nivån för moln levererat skydd

1.  Öppna grupprinciphanteringskonsolen på [hanteringsdatorn för grupprinciper.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))

2. Högerklicka på det grupprincipobjekt du vill konfigurera och klicka sedan på **Redigera.**

3.  I **redigeraren för hantering av grupprinciper** går du **till Administrativa mallar för**  >  **datorkonfiguration.**

4.  Expandera trädet till **Windows-komponenter**  >  **Microsoft Defender Antivirus**  >  **MpEngine.**

5.  Dubbelklicka på inställningen Välj **molnskyddsnivå** och ställ in den på **Aktiverad**. Välj skyddsnivå:
    - **Standardblockeringsnivån** ger stark identifiering utan att öka risken för att legitima filer identifieras.
    - **Måttlig blockeringsnivå ger** måttlig endast vid identifiering med hög konfidens
    - **Hög blockeringsnivå** tillämpar en stark identifieringsnivå vid optimering av klientprestanda (men kan också ge dig större risk för falska positiva identifieringar).
    - **Hög + blockeringsnivå** tillämpar ytterligare skyddsåtgärder (kan påverka klientens prestanda och öka risken för falska positiva resultat).
    - **Noll blockering av avvikelser blockerar** alla okända körbara filer.
    
    > [!WARNING]
    > Det är inte troligt  att om du anger det här alternativet till Hög eller Hög **+** kan vissa legitima filer upptäckas (även om du har möjlighet att häva blockeringen eller tvista vid identifieringen).

6. Klicka på **OK**.

7. Distribuera det uppdaterade grupprincipobjektet. Se [Konsolen för grupprinciphantering](/windows/win32/srvnodes/group-policy)

> [!TIP]
> Använder du grupprincipobjekt lokalt? Se hur de översätter i molnet. [Analysera lokala grupprincipobjekt med grupprincipanalyser i Microsoft Endpoint Manager – förhandsversion.](/mem/intune/configuration/group-policy-analytics) 
  
## <a name="related-articles"></a>Relaterade artiklar

- [Microsoft Defender Antivirus i Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Aktivera moln levererat skydd](enable-cloud-protection-microsoft-defender-antivirus.md)
- [Så här skapar och distribuerar du skydd mot skadlig programvara: Molnskyddstjänst](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)