---
title: Styra USB-enheter och andra flyttbara medium med Intune (Windows 10)
description: Du kan konfigurera Intune-inställningar för att minska hoten mot flyttbara lagringsinställningar, till exempel USB-enheter.
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.author: dansimp
author: dansimp
ms.reviewer: dansimp
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: ec5cd489cae21b9140463d4ede72813ec014b3bb
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926361"
---
# <a name="how-to-control-usb-devices-and-other-removable-media-using-microsoft-defender-for-endpoint"></a>Styra USB-enheter och andra flyttbara medium med Hjälp av Microsoft Defender för Endpoint

**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/p/?linkid=2069559)

Microsoft rekommenderar en lager metoden för att skydda flyttbara media [,](https://aka.ms/devicecontrolblog)och Microsoft Defender för Endpoint ger flera övervaknings- och kontrollfunktioner för att förhindra att hot för obehörig kringutrustning komprometteras från dina enheter:

1. [Upptäck ansluta och spela upp anslutna händelser för kringutrustning i Microsoft Defender för avancerad sökning i Endpoint.](#discover-plug-and-play-connected-events) Identifiera eller undersöka misstänkt användningsaktivitet.

2. Konfigurera för att tillåta eller blockera endast vissa flyttbara enheter och förhindra hot.
    1. [Tillåt eller blockera flyttbara enheter](#allow-or-block-removable-devices) baserat på detaljerad konfiguration för att neka skrivåtkomst till flyttbara diskar och godkänna eller neka enheter med hjälp av USB-enhets-ID. Flexibel principtilldelning av enhetsinstallationsinställningar baserat på en enskild användare eller grupp av Azure Active Directory (Azure AD) användare och enheter.

    2. [Förhindra hot från flyttbara lagringsmedia som](#prevent-threats-from-removable-storage) introduceras genom flyttbara lagringsenheter genom att aktivera:  
        - Microsoft Defender Antivirus realtidsskydd (RTP) för att söka igenom det flyttbara lagringsutrymmet efter skadlig kod.  
        - USB-regeln (Attack Surface Reduction) för att blockera icke betrodda och osignerade processer som körs från USB.  
        - DMA-skyddsinställningar (Direct Memory Access) för att minimera DMA-attacker, t.ex. Kernel DMA Protection för Kernel DMA Protection för Kernel och blockera DMA tills en användare loggar in.  

3. [Skapa anpassade aviseringar och svarsåtgärder](#create-customized-alerts-and-response-actions) för att övervaka användningen av flyttbara enheter baserat på dessa plugin-program och spela upp händelser eller andra Microsoft Defender för Slutpunkt-händelser med [anpassade identifieringsregler](/microsoft-365/security/defender-endpoint/custom-detection-rules).

4. [Reagera på hot från](#respond-to-threats) kringutrustning i realtid baserat på egenskaper som rapporterats av varje kringutrustning.

>[!Note]
>De här åtgärderna för att minska hot hjälper till att förhindra att skadlig programvara kommer till din miljö. Om du vill skydda företagsdata från att lämna miljön kan du också konfigurera åtgärder för skydd mot dataförlust. På Windows 10-enheter kan du till exempel konfigurera [BitLocker](/windows/security/information-protection/bitlocker/bitlocker-overview.md) och [Windows Information Protection](/windows/security/information-protection/create-wip-policy-using-intune-azure.md), som krypterar företagsdata även om de lagras på en personlig enhet, eller använda [Storage/RemovableDiskDenyWriteAccess CSP](/windows/client-management/mdm/policy-csp-storage#storage-removablediskdenywriteaccess) för att neka skrivåtkomst till flyttbara diskar. Du kan dessutom klassificera och skydda filer på [Windows](/windows/security/threat-protection/windows-defender-atp/information-protection-in-windows-overview) enheter (inklusive derasmonterade USB-enheter) med hjälp av Microsoft Defender för Endpoint och Azure Information Protection.

## <a name="discover-plug-and-play-connected-events"></a>Upptäck ansluta och spela upp anslutna händelser

Du kan visa plug and play anslutna händelser i Microsoft Defender för Endpoint avancerad sökning för att identifiera misstänkt användningsaktivitet eller utföra interna undersökningar.
Exempel på avancerade sökfrågor för Defender för Endpoint finns i Sökfrågor i Microsoft Defender för slutpunkt GitHub [lagringsplatsen.](https://github.com/Microsoft/WindowsDefenderATP-Hunting-Queries)

Exempel på Power BI-rapportmallar finns tillgängliga för Microsoft Defender för Endpoint som du kan använda för Avancerade sökfrågor. Med de här exempelmallarna, bland annat en för enhetskontroll, kan du integrera avancerad sökning i Power BI. Mer [information GitHub lagringsplatsen för PowerBI-mallar.](https://github.com/microsoft/MDATP-PowerBI-Templates) Mer [information om hur du Power BI](/microsoft-365/security/defender-endpoint/api-power-bi) finns i Skapa anpassade Power BI med hjälp av Power BI rapport.

## <a name="allow-or-block-removable-devices"></a>Tillåt eller blockera flyttbara enheter
I följande tabell beskrivs hur Microsoft Defender för Endpoint kan tillåta eller blockera flyttbara enheter baserat på en detaljerad konfiguration.

| Kontroll  | Beskrivning |
|----------|-------------|
| [Begränsa USB-enheter och annan kringutrustning](#restrict-usb-drives-and-other-peripherals) | Du kan tillåta/förhindra att användare endast installerar USB-enheter och annan kringutrustning som finns på en lista över godkända/obehöriga enheter eller enhetstyper. |
| [Blockera installation och användning av flyttbart lagringsutrymme](#block-installation-and-usage-of-removable-storage) | Det går inte att installera eller använda flyttbart lagringsutrymme. |
| [Tillåt installation och användning av specifikt godkänd kringutrustning](#allow-installation-and-usage-of-specifically-approved-peripherals)   | Du kan bara installera och använda godkänd kringutrustning som rapporterar specifika egenskaper på den inbyggda programvaran. |
| [Förhindra installation av specifikt förbjudna kringutrustning](#prevent-installation-of-specifically-prohibited-peripherals) | Du kan inte installera eller använda förbjuden kringutrustning som rapporterar specifika egenskaper på den inbyggda programvaran. |
| [Tillåt installation och användning av specifikt godkänd kringutrustning med matchande enhetsinstans-ID](#allow-installation-and-usage-of-specifically-approved-peripherals-with-matching-device-instance-ids) | Du kan bara installera och använda godkänd kringutrustning som matchar någon av dessa enhetsinstans-ID. |
| [Förhindra installation och användning av specifikt förbjudna kringutrustning med matchande enhetsinstans-ID](#prevent-installation-and-usage-of-specifically-prohibited-peripherals-with-matching-device-instance-ids) | Du kan inte installera eller använda förbjuden kringutrustning som matchar någon av dessa enhetsinstans-ID. |
| [Begränsa antalet tjänster som använder Bluetooth](#limit-services-that-use-bluetooth) | Du kan begränsa tjänsterna som kan använda Bluetooth. |
| [Använda baslinjeinställningar för Microsoft Defender för Slutpunkt](#use-microsoft-defender-for-endpoint-baseline-settings) | Du kan ange den rekommenderade konfigurationen för ATP med hjälp av säkerhetsbaslinjen Defender för Slutpunkt. |

### <a name="restrict-usb-drives-and-other-peripherals"></a>Begränsa USB-enheter och annan kringutrustning

För att förhindra att skadlig programvara smittas eller dataförlust kan en organisation begränsa USB-enheter och annan kringutrustning. I följande tabell beskrivs hur Microsoft Defender för Slutpunkt kan förhindra installation och användning av USB-enheter och annan kringutrustning.

| Kontroll  | Beskrivning
|----------|-------------|
| [Tillåt installation och användning av USB-enheter och annan kringutrustning](#allow-installation-and-usage-of-usb-drives-and-other-peripherals) | Tillåt användare att endast installera USB-enheter och annan kringutrustning som finns på en lista över godkända enheter eller enhetstyper |
| [Förhindra installation och användning av USB-enheter och annan kringutrustning](#prevent-installation-and-usage-of-usb-drives-and-other-peripherals) | Hindra användare från att installera USB-enheter och annan kringutrustning som ingår i en lista över obehöriga enheter och enhetstyper |

Alla kontroller ovan kan ställas in via [](/intune/administrative-templates-windows)Administrativa mallar i Intune. Relevanta principer finns här i intune-administratörsmallarna:

![skärmbild av lista över administratörsmallar](images/admintemplates.png)

>[!Note]
>Med Intune kan du tillämpa principer för enhetskonfiguration för Azure AD-användare och/eller enhetsgrupper.
Ovanstående principer kan också anges via inställningarna för CSP för [enhetsinstallation och](/windows/client-management/mdm/policy-csp-deviceinstallation) [GPOs för enhetsinstallation.](/previous-versions/dotnet/articles/bb530324(v=msdn.10))

> [!Note]
> Testa och förfina alltid de här inställningarna med en pilotgrupp med användare och enheter först innan du tillämpar dem i produktionen.
Mer information om hur du styr USB-enheter finns i [bloggen Microsoft Defender för Endpoint.](https://www.microsoft.com/security/blog/2018/12/19/windows-defender-atp-has-protections-for-usb-and-removable-devices/)

#### <a name="allow-installation-and-usage-of-usb-drives-and-other-peripherals"></a>Tillåt installation och användning av USB-enheter och annan kringutrustning

Ett sätt att tillåta installation och användning av USB-enheter och annan kringutrustning är att börja med att tillåta allt. Därefter kan du börja minska de tillåtna USB-drivrutinerna och annan kringutrustning.

>[!Note]
>Eftersom obehörig USB-kringutrustning kan ha inbyggd programvara som kapar dess USB-egenskaper rekommenderar vi att du bara tillåter specifikt godkänd USB-kringutrustning och begränsar vilka användare som kan komma åt dem.

1. Aktivera **Förhindra installation av enheter som inte beskrivs av andra principinställningar** för alla användare.
2. Aktivera **Tillåt installation av enheter med drivrutiner som matchar dessa enhetskonfigurationsklasser** för alla [enhetskonfigurationsklasser](/windows-hardware/drivers/install/system-defined-device-setup-classes-available-to-vendors).

Tillämpa principen för redan installerade enheter genom att tillämpa de prevent-principer som har den här inställningen.

När du konfigurerar principen för att tillåta enhetsinstallation måste du tillåta alla överordnade attribut också. Du kan visa föräldrar för en enhet genom att öppna Enhetshanteraren och visa efter anslutning.

![Enheter efter anslutning](images/devicesbyconnection.png)

I det här exemplet måste följande klasser läggas till: HID, tangentbord och {36fc9e60-c465-11cf-8056-44455354000}. Mer information [finns i Microsoft-medföljande USB-drivrutiner.](/windows-hardware/drivers/usbcon/supported-usb-classes)

![Värdkontroll för enhet](images/devicehostcontroller.jpg)

Om du vill begränsa användningen till vissa enheter tar du bort enhetsinstallationsklassen för den kringutrustning som du vill begränsa. Lägg sedan till det enhets-ID du vill lägga till. Enhets-ID baseras på leverantörs-ID och produkt-ID för en enhet. Mer information om enhets-ID-format finns i [Standard-USB-identifierare.](/windows-hardware/drivers/install/standard-usb-identifiers) 

Information om hur du hittar enhets-ID:n finns i [Slå upp enhets-ID.](#look-up-device-id) 

Till exempel:

1. Ta bort USB-enhet för klassen från Tillåt installation av enheter med **drivrutiner som matchar dessa enhetskonfiguration.**
2. Lägg till det enhets-ID som ska tillåtas i Tillåt installation av **enhet som matchar något av dessa enhets-ID:n.** 


#### <a name="prevent-installation-and-usage-of-usb-drives-and-other-peripherals"></a>Förhindra installation och användning av USB-enheter och annan kringutrustning

Om du vill förhindra installation av en enhetsklass eller vissa enheter kan du använda principer för att förhindra enhetsinstallation:

1. Aktivera **Förhindra installation av enheter som matchar något av dessa enhets-ID och** lägg till dessa enheter i listan.
2. Aktivera **Förhindra installation av enheter med drivrutiner som matchar dessa enhetskonfigurationsklasser**.

> [!Note]
> Principerna för att förhindra enhetsinstallation har företräde framför principer för installation av tillåtna enheter.

Med principen Förhindra installation av enheter som matchar någon av dessa **enhets-IDS** kan du ange en lista över enheter som Windows förhindras från att installera. 

Så här förhindrar du installation av enheter som matchar något av dessa enhets-ID: 

1. [Leta upp enhets-ID](#look-up-device-id) för enheter som du Windows förhindra från att installera.

   ![Sök efter leverantör eller produkt-ID](images/lookup-vendor-product-id.png)

2. Aktivera **Förhindra installation av enheter som matchar något av dessa enhets-ID** och lägg till leverantörs- eller produkt-ID i listan.

    ![Lägg till leverantörs-ID om du vill förhindra listan](images/add-vendor-id-to-prevent-list.png)

#### <a name="look-up-device-id"></a>Slå upp enhets-ID

Du kan använda Enhetshanteraren för att leta upp ett enhets-ID.

1. Öppna Enhetshanteraren.
2. Klicka **på** Visa och välj **Enheter efter anslutning.**
3. Högerklicka på enheten i trädet och välj **Egenskaper**.
4. Klicka på fliken Information i dialogrutan för den **valda** enheten.
5. Klicka på **listrutan** Egenskap och välj **Maskinvaru-ID:n**.
6. Högerklicka på det översta ID-värdet och välj **Kopiera**.

Mer information om enhets-ID-format finns i [Standard-USB-identifierare.](/windows-hardware/drivers/install/standard-usb-identifiers)

Mer information om leverantörs-IDt finns i [USB-medlemmar.](https://www.usb.org/members)

Följande är ett exempel för att leta upp ett leverantörs-ID för en enhet eller ett produkt-ID (som är en del av enhets-ID:t) med hjälp av PowerShell: 

```powershell
Get-WMIObject -Class Win32_DiskDrive |
Select-Object -Property * 
```

Med **principen Prevent installation of devices using drivers that match these device setup classes** (Förhindra installation av enheter med drivrutiner som matchar den här principen för enhetskonfigurationsklasser) kan du ange enhetskonfigurationsklasser som Windows förhindras från att installeras. 

För att förhindra installation av vissa klasser av enheter: 

1. Hitta GUID för enhetsinstallationsklassen från [Systemdefinierade enhetskonfigurationsklasser som är tillgängliga för leverantörer.](/windows-hardware/drivers/install/system-defined-device-setup-classes-available-to-vendors)

2. Aktivera **Förhindra installation av enheter med drivrutiner som matchar dessa enhetskonfigurationsklasser** och lägg till klassens GUID i listan.

    > [!div class="mx-imgBorder"]
    > ![Lägg till enhetskonfigurationsklass för att förhindra lista](images/Add-device-setup-class-to-prevent-list.png)

### <a name="block-installation-and-usage-of-removable-storage"></a>Blockera installation och användning av flyttbart lagringsutrymme

1. Logga in Microsoft Endpoint Manager [administrationscentret](https://endpoint.microsoft.com/).

2. Klicka **på**  >  **Konfigurationsprofiler för enheter** för att skapa  >  **profil**.

    > [!div class="mx-imgBorder"]
    > ![Profil för att skapa enhetskonfiguration](images/create-device-configuration-profile.png)

3. Använd följande inställningar:

   - Namn: Ange ett namn för profilen
   - Beskrivning: Skriv en beskrivning
   - Plattform: Windows 10 och senare
   - Profiltyp: Enhetsbegränsningar

   > [!div class="mx-imgBorder"]
   > ![Skapa profil](images/create-profile.png)

4. Klicka **på Konfigurera**  >  **allmänt.**  

5. För **Flyttbart lagringsutrymme och** **USB-anslutning (endast mobil)** väljer du **Blockera**. **Flyttbart lagringsutrymme** inkluderar USB-enheter, **medan USB-anslutning (endast mobil)** exkluderar USB-laddning men inkluderar andra USB-anslutningar på endast mobila enheter. 

   ![Allmänna inställningar](images/general-settings.png)

6. Stäng Allmänna inställningar och **Enhetsbegränsningar** genom **att klicka på** **OK.**

7. Spara **profilen genom** att klicka på Skapa.

### <a name="allow-installation-and-usage-of-specifically-approved-peripherals"></a>Tillåt installation och användning av specifikt godkänd kringutrustning

Kringutrustning som tillåts installeras kan anges av deras [maskinvaruidentitet.](/windows-hardware/drivers/install/device-identification-strings) En lista över vanliga identifierarstrukturer finns i Format [för enhetsidentifierare.](/windows-hardware/drivers/install/device-identifier-formats) Testa konfigurationen innan du distribuerar den för att säkerställa att den blockerar och tillåter förväntade enheter. Testa helst olika förekomster av maskinvaran. Testa till exempel flera USB-nycklar i stället för bara en.

Ett exempel på synkroniseringsml som tillåter installation av specifika enhets-IDs finns i CSP för [Enhetsinstallation/AllowInstallationOfMatchingDeviceIDs.](/windows/client-management/mdm/policy-csp-deviceinstallation#deviceinstallation-allowinstallationofmatchingdeviceids) Information om hur du tillåter specifika enhetsklasser [finns i DeviceInstallation/AllowInstallationOfMatchingDeviceSetupClasses CSP.](/windows/client-management/mdm/policy-csp-deviceinstallation#deviceinstallation-allowinstallationofmatchingdevicesetupclasses)
Om du vill tillåta installation av specifika enheter måste du också aktivera [DeviceInstallation/PreventInstallationOfDevicesNotDescribedByOtherPolicySettings.](/windows/client-management/mdm/policy-csp-deviceinstallation#deviceinstallation-preventinstallationofdevicesnotdescribedbyotherpolicysettings)

### <a name="prevent-installation-of-specifically-prohibited-peripherals"></a>Förhindra installation av specifikt förbjudna kringutrustning

Microsoft Defender för Endpoint blockerar installation och användning av förbjuden kringutrustning genom att använda något av följande alternativ:

- [Administrativa mallar](/intune/administrative-templates-windows) kan blockera alla enheter med ett matchande maskinvaru-ID eller konfigurationsklass.  
- [Inställningar för CSP för enhetsinstallation](/windows/client-management/mdm/policy-csp-deviceinstallation) med en anpassad profil i Intune. Du kan [förhindra installation av specifika enhets-ID eller](/windows/client-management/mdm/policy-csp-deviceinstallation#deviceinstallation-preventinstallationofmatchingdeviceids) förhindra specifika [enhetsklasser.](/windows/client-management/mdm/policy-csp-deviceinstallation#deviceinstallation-preventinstallationofmatchingdevicesetupclasses)

### <a name="allow-installation-and-usage-of-specifically-approved-peripherals-with-matching-device-instance-ids"></a>Tillåt installation och användning av specifikt godkänd kringutrustning med matchande enhetsinstans-ID

Kringutrustning som tillåts installeras kan anges av deras [enhetsinstans-ID.](/windows-hardware/drivers/install/device-instance-ids) Testa konfigurationen innan du distribuerar den för att säkerställa att den tillåter de förväntade enheterna. Testa helst olika förekomster av maskinvaran. Testa till exempel flera USB-nycklar i stället för bara en.

Du kan tillåta installation och användning av godkänd kringutrustning med matchande enhetsinstans-IP genom att konfigurera principinställningen [Enhetsinstallation/AllowInstallationOfMatchingDeviceInstanceIDs.](/windows/client-management/mdm/policy-csp-deviceinstallation#deviceinstallation-allowinstallationofmatchingdeviceinstanceids)

### <a name="prevent-installation-and-usage-of-specifically-prohibited-peripherals-with-matching-device-instance-ids"></a>Förhindra installation och användning av specifikt förbjudna kringutrustning med matchande enhetsinstans-ID

Kringutrustning som är förbjudna att installeras kan anges av deras [enhetsinstans-ID.](/windows-hardware/drivers/install/device-instance-ids) Testa konfigurationen innan du distribuerar den för att säkerställa att den tillåter de förväntade enheterna. Testa helst olika förekomster av maskinvaran. Testa till exempel flera USB-nycklar i stället för bara en.

Du kan förhindra installation av förbjuden kringutrustning med matchande enhetsinstans-IP genom att konfigurera principinställningen [Enhetsinstallation/PreventInstallationOfMatchingDeviceInstanceIDs.](/windows/client-management/mdm/policy-csp-deviceinstallation#deviceinstallation-preventinstallationofmatchingdeviceinstanceids)

### <a name="limit-services-that-use-bluetooth"></a>Begränsa antalet tjänster som använder Bluetooth

Med Intune kan du begränsa de tjänster som kan Bluetooth via ["Bluetooth".](/windows/client-management/mdm/policy-csp-bluetooth#servicesallowedlist-usage-guide) Standardtillståndet för inställningarna Bluetooth tjänster innebär att allt är tillåtet.  Så snart en tjänst har lagts till blir den listan över tillåtna. Om kunden lägger till värdena för tangentbord och möss, och inte lägger till GUID:er för filöverföring, ska filöverföring blockeras.

> [!div class="mx-imgBorder"]
> ![skärmbild av Bluetooth inställningar](images/bluetooth.png)

### <a name="use-microsoft-defender-for-endpoint-baseline-settings"></a>Använda baslinjeinställningar för Microsoft Defender för Slutpunkt

Baslinjeinställningarna för Microsoft Defender för Slutpunkt representerar den rekommenderade konfigurationen för skydd mot hot. Konfigurationsinställningar för originalplan finns på sidan redigera profil i konfigurationsinställningarna.

> [!div class="mx-imgBorder"]
> ![Baslinjer i MEM](images/baselines.png)

## <a name="prevent-threats-from-removable-storage"></a>Förhindra hot från att ta bort flyttbara lagringsmedia
  
Flyttbara lagringsenheter kan leda till ytterligare säkerhetsrisker för organisationen. Microsoft Defender för Endpoint kan hjälpa dig att identifiera och blockera skadliga filer på flyttbara lagringsenheter.

Microsoft Defender för Endpoint kan också förhindra att USB-kringutrustning används på enheter för att förhindra externa hot. Det gör du genom att använda de egenskaper som rapporterats av USB-kringutrustning för att avgöra om de kan installeras och användas på enheten eller inte.

Observera att om du blockerar USB-enheter eller andra enhetsklasser med hjälp av principer för enhetsinstallation kan anslutna enheter, till exempel telefoner, fortfarande ladda.

>[!NOTE]
>Testa och förfina alltid de här inställningarna med en pilotgrupp med användare och enheter innan du distribuerar dem till din organisation på många sätt. 

I följande tabell beskrivs hur Microsoft Defender för Endpoint kan förhindra hot från att ta bort flyttbart lagringsutrymme.

Mer information om hur du styr USB-enheter finns i [bloggen Microsoft Defender för Endpoint.](https://aka.ms/devicecontrolblog)

| Kontroll  | Beskrivning |
|----------|-------------|
| [Aktivera Microsoft Defender Antivirus skanning](#enable-microsoft-defender-antivirus-scanning) | Aktivera Microsoft Defender Antivirus skanning för realtidsskydd eller schemalagda genomsökningar.|
| [Blockera ej betrodda och osignerade processer på USB-kringutrustning](#block-untrusted-and-unsigned-processes-on-usb-peripherals) | Blockera USB-filer som inte är betrodda eller inte är betrodda. |
| [Skydda mot DMA-attacker (Direct Memory Access)](#protect-against-direct-memory-access-dma-attacks) | Konfigurera inställningar för att skydda mot DMA-attacker. |

>[!NOTE]
>Eftersom obehörig USB-kringutrustning kan ha inbyggd programvara som kapar dess USB-egenskaper rekommenderar vi att du bara tillåter specifikt godkänd USB-kringutrustning och begränsar vilka användare som kan komma åt dem.

### <a name="enable-microsoft-defender-antivirus-scanning"></a>Aktivera Microsoft Defender Antivirus skanning

För att skydda behörigt flyttbart [](/microsoft-365/security/defender-endpoint/configure-real-time-protection-microsoft-defender-antivirus) lagringsutrymme Microsoft Defender Antivirus kräver du skydd i realtid eller genomsökningar för schemaläggning och konfigurering av flyttbara enheter för genomsökningar.

- Om realtidsskyddet är aktiverat genomsöks filerna innan de används och körs. Skanningsomfånget inkluderar alla filer, inklusive de påmonterade flyttbara enheter som USB-enheter. Du kan även köra ett [PowerShell-skript](/samples/browse/?redirectedfrom=TechNet-Gallery) för att utföra en anpassad genomsökning av en USB-enhet efter att den har kopplats, så att Microsoft Defender Antivirus börjar skanna alla filer på en flyttbar enhet när den flyttbara enheten har kopplats. Vi rekommenderar dock att du aktiverar realtidsskydd för bättre skanningsprestanda, särskilt för stora lagringsenheter.

- Om schemalagda skanningar används måste du inaktivera inställningen DisableRemovableDriveScanning (aktiverad som standard) för att söka igenom den flyttbara enheten vid en fullständig genomsökning. Flyttbara enheter genomsöks vid en snabb eller anpassad genomsökning oavsett inställningen DisableRemovableDriveStartning.

>[!NOTE]
>Vi rekommenderar att du aktiverar övervakning i realtid för skanning. I Intune kan du aktivera övervakning i realtid för Windows 10 i **Enhetsbegränsningar**  >  **Konfigurera**  >  **Microsoft Defender Antivirus**  >  **övervakning i realtid.**

<!-- Need to build out point in the preceding note. 
-->

### <a name="block-untrusted-and-unsigned-processes-on-usb-peripherals"></a>Blockera ej betrodda och osignerade processer på USB-kringutrustning

Slutanvändarna kan ansluta flyttbara enheter som är smittade med skadlig kod.
För att förhindra att bli betrodda kan ett företag blockera USB-filer som inte är betrodda eller inte betrodda.
Företag kan också använda granskningsfunktionen i minskningsregler för [attackytor](/microsoft-365/security/defender-endpoint/attack-surface-reduction) för att övervaka aktiviteten i icke betrodda och osignerade processer som körs på kringutrustning av USB.
Det kan du göra genom att **ange icke betrodda och osignerade** processer som körs från USB till antingen **Blockera** eller Granska **endast**, respektive.
Med den här regeln kan administratörer förhindra att osignerade eller icke betrodda körbara filer körs från flyttbara USB-enheter, inklusive SD-kort.
Berörda filtyper omfattar körbara filer (till exempel .exe-, .dll- eller .scr) och skriptfiler som PowerShell-filer (.ps), VisualBasic-filer (.vbs) eller JavaScript-filer (.js).

De här [inställningarna kräver att du aktiverar realtidsskydd.](/microsoft-365/security/defender-endpoint/configure-real-time-protection-microsoft-defender-antivirus)

1. Logga in på [Microsoft Endpoint Manager](https://endpoint.microsoft.com/).

2. Klicka **på Enheter**  >  **Windows**  >  **Konfigurationsprinciper** skapa  >  **profil**. 

    ![Profil för att skapa enhetskonfiguration](images/create-device-configuration-profile.png)

3. Använd följande inställningar:
   - Plattform: Windows 10 och senare 
   - Profiltyp: Enhetsbegränsningar

   > [!div class="mx-imgBorder"]
   > ![Skapa profil för slutpunktsskydd](images/create-endpoint-protection-profile.png)

4. Klicka på **Skapa**.  

5. För **processer som inte är betrodda och som körs från USB väljer** du **Blockera**.

   ![Blockera icke betrodda processer](images/block-untrusted-processes.png)

6. Stäng inställningar och enhetsbegränsningar genom att **klicka på** **OK.**

### <a name="protect-against-direct-memory-access-dma-attacks"></a>Skydda mot DMA-attacker (Direct Memory Access)

DMA-attacker kan leda till att känslig information lämnas ut på en dator eller till och med att skadlig programvara används för att kringgå låsskärmen eller kontrollera datorer på distans. Följande inställningar förhindrar DMA-attacker:

1. Från och Windows 10 version 1803 introducerade Microsoft [Kernel DMA Protection för Kernel DMA Protection](/windows/security/information-protection/kernel-dma-protection-for-thunderbolt.md) för Att ge inbyggt skydd mot DMA-attacker via Ports för Microsoft. Kernel DMA Protection för Bluetooth aktiveras av systemtillverkare och kan inte aktiveras eller inaktiveras av användarna.

   Från och Windows 10 version 1809 kan du justera nivån på Kernel DMA Protection genom att konfigurera [DMA Guard CSP.](/windows/client-management/mdm/policy-csp-dmaguard#dmaguard-deviceenumerationpolicy) Det här är en ytterligare kontroll för kringutrustning som inte stöder enhetsminnesisolering (kallas även DMA-ommappning). Med minnesisolering kan operativsystemet utnyttja I/O-minneshanteringsenheten (IOMMU) på en enhet för att blockera ej tillkommet I/O eller minnesåtkomst genom kringutrustning (begränsat minne). Med andra ord tilldelar operativsystemet ett visst minnesintervall för kringutrustningen. Om kringutrustning försöker läsa/skriva till minnet utanför det tilldelade området blockerar operativsystemet det.

   Kringutrustning som stöder enhetsminnesisolering kan alltid ansluta. Kringutrustning som inte kan blockeras, tillåtas eller tillåtas endast efter att användaren loggar in (standard).

2. På Windows 10 system som inte stöder Kernel DMA-skydd kan du:

   - [Blockera DMA tills en användare loggar in](/windows/client-management/mdm/policy-csp-dataprotection#dataprotection-allowdirectmemoryaccess)
   - [Blockera alla anslutningar via kopplingsportarna (inklusive USB-enheter)](https://support.microsoft.com/help/2516445/blocking-the-sbp-2-driver-and-thunderbolt-controllers-to-reduce-1394-d)

## <a name="create-customized-alerts-and-response-actions"></a>Skapa anpassade aviseringar och svarsåtgärder

Du kan skapa anpassade aviseringar och svarsåtgärder med WDATP-kopplingen och de anpassade identifieringsreglerna:

**Svarsåtgärder för Wdatp-koppling:**

**Undersök:** Initiera undersökningar, samla in undersökningspaket och isolera en maskin.

**Hotsökning** på USB-enheter.

**Begränsa körningen** av alla program på datorn utom en fördefinierad MDATP-koppling är en av över 200 fördefinierade kopplingar, Outlook, Teams, slack osv. Du kan skapa anpassade kopplingar.
- [Mer information om WDATP-svarsåtgärder för koppling](/connectors/wdatp/)

**Åtgärd för anpassade identifieringsregler:** Både maskin- och filnivååtgärder kan användas.
- [Mer information om åtgärder för anpassade identifieringsregler](/microsoft-365/security/defender-endpoint/custom-detection-rules)

Information om enhetskontroller relaterade förhandshändelser och exempel på hur du skapar anpassade aviseringar finns i Avancerade uppdateringar för [sökning: USB-händelser,](https://techcommunity.microsoft.com/t5/Microsoft-Defender-ATP/Advanced-hunting-updates-USB-events-machine-level-actions-and/ba-p/824152)åtgärder på maskinnivå och schemaändringar.

## <a name="respond-to-threats"></a>Svara på hot

Du kan skapa anpassade aviseringar och automatiska svarsåtgärder med Microsoft Defender för regler för anpassad identifiering [av slutpunkt.](/microsoft-365/security/defender-endpoint/custom-detection-rules) Svarsåtgärder i den anpassade identifieringen omfattar både maskin- och filnivååtgärder. Du kan också skapa aviseringar och automatiska svarsåtgärder med [PowerApps](https://powerapps.microsoft.com/) och [Flow](https://flow.microsoft.com/) med [Microsoft Defender för slutpunktskopplingen](/connectors/wdatp/). Kopplingen stöder åtgärder för undersökning, sökning av hot och begränsning av program som körs. Det är en av över 200 fördefinierade kopplingar, Outlook, Teams, slack med mera. Anpassade kopplingar kan också läggas till. Mer [information om kopplingar](/connectors/) finns i Kopplingar.
 
Med vilken metod som helst kan du till exempel automatiskt få Microsoft Defender Antivirus när en USB-enhet installeras på en dator.

## <a name="related-topics"></a>Relaterade ämnen

- [Konfigurera realtidsskydd för Microsoft Defender Antivirus](/microsoft-365/security/defender-endpoint/configure-real-time-protection-microsoft-defender-antivirus)
- [Defender/AllowFullScanRemovableDriveScanning](/windows/client-management/mdm/policy-csp-defender#defender-allowfullscanremovabledrivescanning)
- [Policy/DeviceInstallation CSP](/windows/client-management/mdm/policy-csp-deviceinstallation)
- [Gör en anpassad genomsökning av en flyttbar enhet](/samples/browse/?redirectedfrom=TechNet-Gallery)
- [PowerBI-mall för enhetskontroll för anpassad rapportering](https://github.com/microsoft/MDATP-PowerBI-Templates)
- [BitLocker](/windows/security/information-protection/bitlocker/bitlocker-overview.md) 
- [Windows Information Protection](/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure.md)
