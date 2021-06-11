---
title: Skydda viktiga mappar från utpressningstrojaner från att kryptera filer med kontrollerad mappåtkomst
description: Filer i standardmappar kan skyddas från att ändras av skadliga program. Förhindra utpressningstrojaner från att kryptera dina filer.
keywords: Reglerad mappåtkomst, windows 10, windows defender, utpressningstrojaner, skydda, filer, mappar
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
audience: ITPro
ms.date: 06/10/2021
ms.reviewer: v-maave
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: c60620d2a589c8473764b810d1fcb0e24f674451
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904062"
---
# <a name="protect-important-folders-with-controlled-folder-access"></a>Skydda viktiga mappar med kontrollerad mappåtkomst

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-controlled-folder-access"></a>Vad är reglerad mappåtkomst?

Kontrollerad mappåtkomst skyddar dina värdefulla data från skadliga appar och hot, till exempel utpressningstrojaner. Kontrollerad mappåtkomst skyddar dina data genom att kontrollera appar mot en lista med kända, betrodda appar. Stöds i Windows Server 2019 och Windows 10-klienter. Reglerad mappåtkomst kan aktiveras med Windows-säkerhet-appen, Microsoft Endpoint Configuration Manager- eller Intune-appen (för hanterade enheter). 

> [!NOTE]
> Skriptmotorer är inte betrodda och du kan inte ge dem åtkomst till skyddade skyddade mappar.  Till exempel är PowerShell inte betrott genom reglerad mappåtkomst, även om du tillåter det med [certifikat- och filindikatorer.](/microsoft-365/security/defender-endpoint/indicator-certificates) 

Reglerad mappåtkomst fungerar bäst med [Microsoft Defender](microsoft-defender-endpoint.md)för Endpoint , som ger dig detaljerad rapportering om kontrollerad mappåtkomsthändelser och -block som en del av de vanliga scenarierna för [aviseringsundersökning.](investigate-alerts.md)

> [!TIP]
> Styrda mappåtkomstblock genererar inte aviseringar i [kön Aviseringar.](alerts-queue.md) Du kan dock visa information om kontrollerade mappåtkomstblock i [](advanced-hunting-overview.md)tidslinjevyn på [enheten,](investigate-machines.md)medan du använder avancerad sökning eller med [anpassade identifieringsregler.](custom-detection-rules.md)

## <a name="how-does-controlled-folder-access-work"></a>Hur fungerar kontrollerad mappåtkomst?

Reglerad mappåtkomst fungerar bara genom att betrodda program får åtkomst till skyddade mappar. Skyddade mappar anges när reglerad mappåtkomst konfigureras. Vanligtvis används mappar, till exempel de som används för dokument, bilder, nedladdningar och så vidare, i listan med styrda mappar. 

Reglerad mappåtkomst fungerar med en lista över betrodda appar. Appar som ingår i listan med betrodda program fungerar som förväntat. Appar som inte finns med i listan hindras från att göra ändringar i filer i skyddade mappar. 

Appar läggs till i listan baserat på deras plats och rykte. Appar som är mycket vanliga i hela organisationen och som aldrig har visat något beteende som anses vara skadligt är betrodda. Apparna läggs till automatiskt i listan.

Appar kan också läggas till manuellt i listan över betrodda med hjälp av Konfigurationshanteraren eller Intune. Ytterligare åtgärder, till exempel [att lägga till en filindikator](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file) för en app, kan utföras från Säkerhetscenter-konsolen.

## <a name="why-controlled-folder-access-is-important"></a>Varför kontrollerad mappåtkomst är viktigt

Kontrollerad mappåtkomst är särskilt användbart när du vill skydda dina dokument och information från [utpressningstrojaner.](https://www.microsoft.com/wdsi/threats/ransomware) I en utpressningstrojanattack kan dina filer krypteras och hållas kvar. Med kontrollerad mappåtkomst på plats visas ett meddelande på datorn där ett program försökte göra ändringar i en fil i en skyddad mapp. Du kan [anpassa meddelandet med](customize-attack-surface-reduction.md#customize-the-notification) företagets information och kontaktinformation. Du kan också aktivera reglerna individuellt för att anpassa vilka tekniker som ska övervakas av funktionen.

De [skyddade mapparna](#review-controlled-folder-access-events-in-windows-event-viewer) omfattar vanliga systemmappar (inklusive startsekvenser) och du kan [lägga till fler mappar.](customize-controlled-folders.md#protect-additional-folders) Du kan också [tillåta att appar](customize-controlled-folders.md#allow-specific-apps-to-make-changes-to-controlled-folders) får åtkomst till de skyddade mapparna.

Du kan använda [granskningsläge för](audit-windows-defender.md) att utvärdera hur kontrollerad mappåtkomst skulle påverka organisationen om det var aktiverat. Du kan också gå till webbplatsen Windows Defender Test på [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) för att bekräfta att funktionen fungerar och se hur den fungerar.

Kontrollerad mappåtkomst stöds i följande versioner av Windows:
- [Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) och senare
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)

## <a name="windows-system-folders-are-protected-by-default"></a>Windows skydda systemmappar som standard

Windows-systemmappar skyddas som standard tillsammans med flera andra mappar: 

- `c:\Users\<username>\Documents`
- `c:\Users\Public\Documents`
- `c:\Users\<username>\Pictures`
- `c:\Users\Public\Pictures`
- `c:\Users\Public\Videos`
- `c:\Users\<username>\Videos`
- `c:\Users\<username>\Music`
- `c:\Users\Public\Music`
- `c:\Users\<username>\Favorites`

> [!NOTE]
> Du kan konfigurera ytterligare mappar som skyddade, men du kan inte Windows bort systemmappar som är skyddade som standard.

## <a name="requirements-for-controlled-folder-access"></a>Krav för kontrollerad mappåtkomst

Reglerad mappåtkomst kräver [Microsoft Defender Antivirus skydd i realtid.](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)

## <a name="review-controlled-folder-access-events-in-the-microsoft-365-defender-portal"></a>Granska händelser i kontrollerad mappåtkomst i Microsoft 365 Defender-portalen

Defender för Endpoint tillhandahåller detaljerad rapportering om händelser och block som en del av dess scenarier [för aviseringsundersökning](investigate-alerts.md) i Microsoft 365 Defender-portalen. (Se [Microsoft Defender för slutpunkt i Microsoft 365 Defender](../defender/microsoft-365-security-center-mde.md).)

Du kan fråga Microsoft Defender efter Slutpunktsdata med hjälp av [Avancerad sökning](/microsoft-365/security/defender-endpoint/advanced-hunting-windows-defender-advanced-threat-protection). Om du använder granskningsläge kan [](advanced-hunting-overview.md) [du](audit-windows-defender.md)använda avancerad sökning för att se hur styrda inställningar för mappåtkomst skulle påverka din miljö om de var aktiverade.

Exempelfråga:

```PowerShell
DeviceEvents
| where ActionType in ('ControlledFolderAccessViolationAudited','ControlledFolderAccessViolationBlocked')
```

## <a name="review-controlled-folder-access-events-in-windows-event-viewer"></a>Granska styrda mappåtkomsthändelser i Windows Loggboken

Du kan granska Windows händelseloggen för att se händelser som skapas när reglerad mappåtkomstblock (eller granskningar) i en app:

1. Ladda ned [utvärderingspaketet](https://aka.ms/mp7z2w) och extrahera filen *cfa-events.xml* till en lättillgänglig plats på enheten.
2. Skriv **Loggboken** på Start-menyn för att öppna Windows Loggboken.
3. I den vänstra panelen under **Åtgärder väljer** du Importera **anpassad vy...**.
4. Navigera till den plats där *du* cfa-events.xmloch markera den. Du kan också [kopiera XML direkt.](event-views.md)
5. Välj **OK**.

I följande tabell visas händelser som är relaterade till kontrollerad mappåtkomst:

|Händelse-ID | Beskrivning |
|:---|:---|
|5007 | Händelse när inställningar ändras |
|1124 | Granskad kontrollerad mappåtkomsthändelse | 
|1123 | Blockerad reglerad mappåtkomsthändelse |

## <a name="view-or-change-the-list-of-protected-folders"></a>Visa eller ändra listan med skyddade mappar

Du kan använda Windows-säkerhet för att visa listan med mappar som skyddas av reglerad mappåtkomst. 

1. Öppna Windows 10-appen på Windows-säkerhet enhet.
2. Välj **Skydd mot virus och hot**.
3. Under **Utpressningstrojanskydd** väljer du **Hantera utpressningstrojanskydd**.
4. Om reglerad mappåtkomst är inaktiverad måste du aktivera den. Välj **skyddade mappar**.
5. Gör något av följande:
   - Om du vill lägga till en mapp väljer **du + Lägg till en skyddad mapp**.
   - Om du vill ta bort en mapp markerar du den och väljer sedan Ta **bort**. 

> [!NOTE]
> [Windows-systemmappar](#windows-system-folders-are-protected-by-default) är skyddade som standard och du kan inte ta bort dem från listan.


