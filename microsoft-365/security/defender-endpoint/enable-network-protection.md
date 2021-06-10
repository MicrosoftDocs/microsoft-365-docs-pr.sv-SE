---
title: Aktivera nätverksskydd
description: Aktivera nätverksskydd med Grupprincip, PowerShell eller Hantering av mobila enheter och Konfigurationshanteraren.
keywords: ANetwork protection, exploits, malicious website, ip, domain, domains, enable, turn on
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: b62659360e990467524ec632968dfea313d0b164
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861677"
---
# <a name="turn-on-network-protection"></a>Aktivera nätverksskydd

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

[Nätverksskydd](network-protection.md) förhindrar anställda från att använda ett program för att komma åt skadliga domäner som kan vara värdar för nätfiske, sårbarheter och annat skadligt innehåll på Internet. Du kan [granska nätverksskyddet](evaluate-network-protection.md) i en testmiljö för att se vilka appar som blockeras innan du aktiverar det.

[Läs mer om konfigurationsalternativ för nätverksfiltrering](/mem/intune/protect/endpoint-protection-windows-10#network-filtering)

## <a name="check-if-network-protection-is-enabled"></a>Kontrollera om nätverksskyddet är aktiverat

Kontrollera om nätverksskyddet har aktiverats på en lokal enhet med registereditorn.

1. Välj knappen **Start** i aktivitetsfältet och skriv **regedit för** att öppna Registereditorn

2. Välj **HKEY_LOCAL_MACHINE** i sidomenyn

3. Navigera genom de kapslade menyerna **till**  >  **PROGRAMVARA Microsoft**  >  **Windows Defender** Windows Defender  >  **Exploit Guard** Network  >  **Protection**

4. Välj **EnableNetworkProtection** för att se aktuell status för nätverksskydd på enheten

    * 0 eller **Av**
    * 1 eller **På**
    * 2 eller **granskningsläge**
    
    ![nätverksskydd](https://user-images.githubusercontent.com/3296790/95341270-b738b280-08d3-11eb-84a0-16abb140c9fd.PNG)

## <a name="enable-network-protection"></a>Aktivera nätverksskydd

Aktivera nätverksskydd med någon av följande metoder:

* [PowerShell](#powershell)
* [Hantering av mobila enheter (MDM)](#mobile-device-management-mdm)
* [Microsoft Endpoint Manager/Intune](#microsoft-endpoint-manager-formerly-intune)
* [Grupprincip](#group-policy)

### <a name="powershell"></a>PowerShell

1. Skriv **powershell** på Start-menyn, högerklicka på **Windows PowerShell** välj Kör **som administratör**
2. Ange följande cmdlet:

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection Enabled
    ```

3. Valfritt: Aktivera funktionen i granskningsläge med följande cmdlet:

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection AuditMode
    ```

    Använd `Disabled` i stället för eller för att stänga av `AuditMode` `Enabled` funktionen.

### <a name="mobile-device-management-mdm"></a>Hantering av mobila enheter (MDM)

Använd [./Vendor/MSFT/Policy/Config/Defender/EnableNetworkProtection-konfigurationstjänsten](/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection) (CSP) för att aktivera eller inaktivera nätverksskydd eller aktivera granskningsläge.

### <a name="microsoft-endpoint-manager-formerly-intune"></a>Microsoft Endpoint Manager (tidigare Intune)

1. Logga in Microsoft Endpoint Manager administrationscenter (https://endpoint.microsoft.com)

2. Skapa eller redigera en [konfigurationsprofil för slutpunktsskydd](/mem/intune/protect/endpoint-protection-configure)

3. Under **Konfiguration Inställningar** i profilflödet går du till Microsoft Defender Exploit Guard **nätverksfiltrering**  >    >  **Endast**  >  **aktivera eller** **granska**

### <a name="group-policy"></a>Grupprincip

Använd följande procedur för att aktivera nätverksskydd på domänbaserade datorer eller på en fristående dator.

1. På en fristående dator går du till **Start** och skriver och väljer **Redigera grupprincip.**

    *Eller*

    På en domän ansluten grupprinciphanteringsdator öppnar du konsolen [Grupprinciphantering,](https://technet.microsoft.com/library/cc731212.aspx)högerklickar på det grupprincipobjekt du vill konfigurera och väljer **Redigera.**

2. I **Redigeraren för grupprinciphantering** går du till **Datorkonfiguration** och väljer **Administrativa mallar**.

3. Expandera trädet för att **Windows komponenter**  >  **Microsoft Defender Antivirus**  >  **Windows Defender Exploit**  >  **Guard-nätverksskydd**.

> [!NOTE]
> I äldre versioner av Windows kan det hända att det visas "Windows Defender Antivirus" i stället för "Microsoft Defender Antivirus".

4. Dubbelklicka på inställningen Förhindra **användare och appar från att komma åt skadliga webbplatser** och ange alternativet **Aktiverad.** I avsnittet alternativ måste du ange något av följande alternativ:
    * **Blockera** – användare kan inte komma åt skadliga IP-adresser och domäner
    * **Inaktivera (standard)** – Nätverksskyddsfunktionen fungerar inte. Användarna blockeras inte från att komma åt skadliga domäner
    * **Granskningsläge** – Om en användare besöker en skadlig IP-adress eller domän registreras en händelse i Windows händelseloggen. Men användaren blockeras inte från att gå till adressen.

> [!IMPORTANT]
> Om du vill aktivera nätverksskydd fullt ut  måste du ställa **in** grupprincipalternativet på Aktiverad och även välja Blockera i den nedrullningrullningsalternativsmeny som visas.

Kontrollera att nätverksskyddet är aktiverat på en lokal dator med hjälp av Registereditorn:

1. Välj **Start** och skriv **regedit för** att öppna **Registereditorn.**

2. Gå till **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows Defender\Windows Defender Exploit Guard\Network Protection\EnableNetworkProtection**

3. Välj **EnableNetworkProtection** och bekräfta värdet:
   * 0=Av
   * 1=På
   * 2=Granskning

## <a name="see-also"></a>Se även

* [Nätverksskydd](network-protection.md)
* [Utvärdera nätverksskydd](evaluate-network-protection.md)
* [Felsöka nätverksskydd](troubleshoot-np.md)
