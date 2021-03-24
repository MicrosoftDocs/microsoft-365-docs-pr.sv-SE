---
title: Vanliga frågor och svar om att minska attackytan
description: Hitta svar på vanliga frågor om minskningsregler för attackytor i Microsoft Defender ATP.
keywords: Minskningsregler för attackytan, asr, hips, host intrusion prevention system, protection rules, anti-exploit, antiexploit, exploit, prevention av smitta, microsoft defender för slutpunkt
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: martyav
ms.author: v-maave
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.openlocfilehash: 7685bd70d85ecebe759ade762b78ee2c3639cea8
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51069834"
---
# <a name="attack-surface-reduction-frequently-asked-questions-faq"></a>Vanliga frågor och svar om att minska attackytan

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


## <a name="is-attack-surface-reduction-asr-part-of-windows"></a>Är minskning av attackytan (ASR) en del av Windows?

ASR var ursprungligen en funktion i paketet med sårbarhetsskydd-funktioner som introducerades i en större uppdatering av Microsoft Defender Antivirus, i Windows 10, version 1709. Microsoft Defender Antivirus är den inbyggda programkomponenten för program mot skadlig programvara i Windows. Den fullständiga ASR-uppsättningen är dock endast tillgänglig med en Windows Enterprise-licens. Observera även att undantag för ASR-regler hanteras separat från undantag för Microsoft Defender Antivirus.

## <a name="do-i-need-to-have-an-enterprise-license-to-run-asr-rules"></a>Måste jag ha en företagslicens för att köra ASR-regler?

Hela uppsättningen ASR-regler och funktioner stöds endast om du har en företagslicens för Windows 10. Ett begränsat antal regler kan fungera utan en företagslicens. Om du har Microsoft 365 Business anger du Microsoft Defender Antivirus som primär säkerhetslösning och aktiverar reglerna via PowerShell. ASR-användning utan en företagslicens stöds emellertid inte officiellt och de fullständiga funktionerna i ASR är inte tillgängliga.

Mer information om Windows-licensiering finns i [Windows 10-licensiering](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) och volymlicensieringsguiden [för Windows 10.](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf)

## <a name="is-asr-supported-if-i-have-an-e3-license"></a>Stöds ASR om jag har en E3-licens?

Ja. ASR stöds för Windows Enterprise E3 och högre. 

## <a name="which-features-are-supported-with-an-e5-license"></a>Vilka funktioner stöds med en E5-licens?

Alla regler som stöds med E3 stöds också med E5.

E5 har även lagt till större integrering med Defender för Endpoint. Med E5 kan du använda Defender för [Endpoint](https://docs.microsoft.com/microsoft-365/security/defender/monitor-devices?view=o365-worldwide&preserve-view=true#monitor-and-manage-asr-rule-deployment-and-detections) för att övervaka och granska analyser av aviseringar i realtid, finjustera undantag för regler, konfigurera ASR-regler och visa listor med händelserapporter.

## <a name="what-are-the-currently-supported-asr-rules"></a>Vilka asr-regler stöds för närvarande?

ASR har för närvarande stöd för alla regler nedan:

* [Blockera körbart innehåll från e-postklient och webbaserad e-post](attack-surface-reduction.md#block-executable-content-from-email-client-and-webmail)
* [Blockera alla Office-program från att skapa underordnade processer](attack-surface-reduction.md#block-all-office-applications-from-creating-child-processes)
* [Blockera Office-program från att skapa körbart innehåll](attack-surface-reduction.md#block-office-applications-from-creating-executable-content)
* [Blockera Office-program från att mata in kod i andra processer](attack-surface-reduction.md#block-office-applications-from-injecting-code-into-other-processes)
* [Blockera JavaScript eller VBScript från att starta hämtat körbart innehåll](attack-surface-reduction.md#block-javascript-or-vbscript-from-launching-downloaded-executable-content)
* [Blockera körning av potentiellt oönskade skript](attack-surface-reduction.md#block-execution-of-potentially-obfuscated-scripts)
* [Blockera Win32 API-anrop från Office-makro](attack-surface-reduction.md#block-win32-api-calls-from-office-macros)
* [Använd avancerat skydd mot utpressningstrojaner](attack-surface-reduction.md#use-advanced-protection-against-ransomware)
* [Blockera att autentiseringsuppgifter stjäls från Windows lokala säkerhetsutfärdares undersystem](attack-surface-reduction.md#block-credential-stealing-from-the-windows-local-security-authority-subsystem) (lsass.exe)
* [Blockera processskapanden som kommer från PSExec- och WMI-kommandon](attack-surface-reduction.md#block-process-creations-originating-from-psexec-and-wmi-commands)
* [Blockera icke betrodda och osignerade processer som körs från USB](attack-surface-reduction.md#block-untrusted-and-unsigned-processes-that-run-from-usb)
* [Blockera körbara filer från att köras såvida de inte uppfyller villkoren för en vän, ålder eller ett betrott listvillkor](attack-surface-reduction.md#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion)
* [Blockera Office-kommunikationsprogram från att skapa underordnade processer](attack-surface-reduction.md#block-office-communication-application-from-creating-child-processes)
* [Blockera Adobe Reader från att skapa underordnade processer](attack-surface-reduction.md#block-adobe-reader-from-creating-child-processes)
* [Blockera beständighet via WMI-händelseprenumeration](attack-surface-reduction.md#block-persistence-through-wmi-event-subscription)

## <a name="what-are-some-good-recommendations-for-getting-started-with-asr"></a>Vilka är några bra rekommendationer för att komma igång med ASR?

Testa hur ASR-regler påverkar organisationen innan du aktiverar dem genom att köra ASR-regler i granskningsläge under en kort tidsperiod. När du kör reglerna i granskningsläge kan du identifiera alla affärsprogram som kan blockeras felaktigt och utesluta dem från ASR.

Större organisationer bör överväga att distribuera ASR-regler i "ringar", genom att granska och möjliggöra regler i allt bredare delmängder av enheter. Du kan ordna organisationens enheter i ringar med hjälp av Intune eller ett grupprinciphanteringsverktyg.

## <a name="how-long-should-i-test-an-asr-rule-in-audit-mode-before-enabling-it"></a>Hur lång tid tar det innan jag aktiverar en ASR-regel i granskningsläge?

Behåll regeln i granskningsläge i ca 30 dagar för att få en bra baslinje för hur regeln fungerar när den fungerar i hela organisationen. Under granskningsperioden kan du identifiera alla affärsprogram som kan blockeras av regeln och konfigurera regeln så att de utesluts.

## <a name="im-making-the-switch-from-a-third-party-security-solution-to-defender-for-endpoint-is-there-an-easy-way-to-export-rules-from-another-security-solution-to-asr"></a>Jag byter från en säkerhetslösning från tredje part till Defender för Endpoint. Finns det ett "enkelt" sätt att exportera regler från en annan säkerhetslösning till ASR?

I de flesta fall är det enklare och bättre att börja med de baslinjerekommendationer som [föreslås](https://docs.microsoft.com/windows/security/threat-protection) av Defender för slutpunkt än att försöka importera regler från en annan säkerhetslösning. Använd sedan verktyg som granskningsläge, övervakning och analys för att konfigurera den nya lösningen så att den passar dina unika behov. 

Standardkonfigurationen för de flesta ASR-regler, i kombination med Defender för Endpoints realtidsskydd, kommer att skydda mot ett stort antal sårbarheter och svagheter.

I Defender för slutpunkten kan du uppdatera ditt skydd med anpassade indikatorer för att tillåta och blockera vissa programvarubeteenden. ASR tillåter också vissa anpassning av regler, i form av undantag för filer och mappar. Generellt sett är det bäst att granska en regel under en viss tid och konfigurera undantag för affärsprogram som kan blockeras.

## <a name="does-asr-support-file-or-folder-exclusions-that-include-system-variables-and-wildcards-in-the-path"></a>Stöder ASR undantag för filer eller mappar som inkluderar systemvariabler och jokertecken i sökvägen?

Ja. Mer information om hur du använder systemvariabler och jokertecken i uteslutna filsökvägar finns i Exkludera filer och mappar från [ASR-regler](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules) och Konfigurera och validera undantag baserade på filnamnstillägg och mappsökväg. [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)

## <a name="do-asr-rules-cover-all-applications-by-default"></a>Täcker ASR-reglerna alla program som standard?

Det beror på regeln. De flesta ASR-regler omfattar Microsoft Office-produkter och -tjänster som Word, Excel, PowerPoint, OneNote och Outlook. Vissa ASR-regler, till exempel Blockera körning av potentiellt *oönskade skript,* är mer allmänna i omfattningen.

## <a name="does-asr-support-third-party-security-solutions"></a>Stöder ASR säkerhetslösningar från tredje part?

ASR använder Microsoft Defender Antivirus för att blockera program. Det går för stunden inte att konfigurera ASR att använda en annan säkerhetslösning för blockering.

## <a name="i-have-an-e5-license-and-enabled-some-asr-rules-in-conjunction-with-defender-for-endpoint-is-it-possible-for-an-asr-event-to-not-show-up-at-all-in-defender-for-endpoints-event-timeline"></a>Jag har en E5-licens och aktiverat vissa ASR-regler tillsammans med Defender för Slutpunkt. Är det möjligt att en ASR-händelse inte visas alls i Defender för Endpoints händelsetidslinje?

När ett meddelande utlöses lokalt av en ASR-regel skickas en rapport om händelsen även till Defender för Slutpunktsportalen. Om du har svårt att hitta händelsen kan du filtrera tidslinjen för händelser med hjälp av sökrutan. Du kan också visa ASR-händelser genom att besöka Gå till hantering av **attackytor**, från ikonen **Konfigurationshantering** i Aktivitetsfältet i Säkerhetscenter. Sidan för hantering av attackytor innehåller en flik för rapportidentifiering, som innehåller en fullständig lista över ASR-regelhändelser som rapporterats till Defender för Slutpunkt.

## <a name="i-applied-a-rule-using-gpo-now-when-i-try-to-check-the-indexing-options-for-the-rule-in-microsoft-outlook-i-get-a-message-stating-access-denied"></a>Jag använde en regel med GPO. Nu när jag försöker kontrollera indexeringsalternativen för regeln i Microsoft Outlook får jag ett meddelande om att åtkomst nekas.

Prova att öppna indexeringsalternativen direkt från Windows 10.

1. Välj **sökikonen** i Aktivitetsfältet i Windows.

1. Ange **indexeringsalternativ** i sökrutan.

## <a name="are-the-criteria-used-by-the-rule-block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion-configurable-by-an-admin"></a>Används villkoren i regeln "Blockera körbara filer från att köras såvida de inte uppfyller ett villkor av hög ålder eller betrodd lista" som kan konfigureras av en administratör?

Nej. Villkoren som används av den här regeln behålls av Microsofts molnskydd, så att listan med betrodda data hela tiden hålls uppdaterad med data som samlas in från hela världen. Lokala administratörer har inte skrivbehörighet för att ändra dessa data. Om du vill konfigurera den här regeln så att den anpassar sig efter ditt företag kan du lägga till vissa program i undantagslistan för att förhindra att regeln utlöses.

## <a name="i-enabled-the-asr-rule-block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion-after-some-time-i-updated-a-piece-of-software-and-the-rule-is-now-blocking-it-even-though-it-didnt-before-did-something-go-wrong"></a>Jag aktiverade ASR-regeln, blockera körbara filer från att köras såvida de inte uppfyller ett villkor för en ålder *eller en betrodd lista.* Efter en stund uppdaterade jag ett program och regeln blockerar den nu, även om den inte gjorde det tidigare. Gick något fel?

Den här regeln förlitar sig på varje program som har ett känt rykte, baserat på ålder eller inkludering i en lista med betrodda appar. Regelns beslut att blockera eller tillåta ett program avgörs i slutänden av Microsofts molnskydds bedömning av dessa villkor.

Normalt kan molnskydd fastställa att en ny version av ett program är tillräckligt lik tidigare versioner att den inte behöver ses över längre. Det kan dock ta lite tid för programmet att bygga upp sitt rykte efter att ha bytt version, särskilt efter en större uppdatering. Under tiden kan du lägga till programmet i undantagslistan för att förhindra att den här regeln blockerar viktiga program. Om du ofta uppdaterar och arbetar med nya versioner av program kan du välja att i stället köra regeln i granskningsläge.

## <a name="i-recently-enabled-the-asr-rule-block-credential-stealing-from-the-windows-local-security-authority-subsystem-lsassexe-and-i-am-getting-a-large-number-of-notifications-what-is-going-on"></a>Jag aktiverade nyligen ASR-regeln, blockera autentiseringsuppgifter som stjäls från Windows lokala säkerhetsutfärdares *undersystem (lsass.exe)* och jag får ett stort antal meddelanden. Vad är det som händer?

Ett meddelande som skapas av den här regeln anger inte nödvändigtvis skadlig aktivitet. Den här regeln är dock fortfarande användbar för att blockera skadlig aktivitet, eftersom skadlig programvara ofta riktar lsass.exe att få tillgång till konton samtidigt. I lsass.exe processen lagras användarautentiseringsuppgifter i minnet när en användare har loggat in. Windows använder de här autentiseringsuppgifterna för att verifiera användare och tillämpa lokala säkerhetsprinciper.

Eftersom många legitima processer under en vanlig dag kommer att anropa samtal lsass.exe autentiseringsuppgifter, kan regeln vara särskilt bullrig. Om ett känt legitimt program orsakar att regeln genererar ett överflödigt antal meddelanden kan du lägga till den i undantagslistan. De flesta andra ASR-regler genererar ett relativt mindre antal meddelanden, i jämförelse med den här, eftersom samtal till lsass.exe är typiskt för många programs normala funktion.

## <a name="is-it-a-good-idea-to-enable-the-rule-block-credential-stealing-from-the-windows-local-security-authority-subsystem-lsassexe-alongside-lsa-protection"></a>Är det en bra idé att aktivera regeln Blockera autentiseringsuppgifter som stjäls från Windows lokala säkerhetsutfärdares *undersystem (lsass.exe)*, tillsammans med LSA-skydd?

Att aktivera den här regeln ger inte ytterligare skydd om du har [aktiverat LSA-skydd.](https://docs.microsoft.com/windows-server/security/credentials-protection-and-management/configuring-additional-lsa-protection#BKMK_HowToConfigure) Både regeln och LSA-skyddet fungerar på ungefär samma sätt, så att båda körs samtidigt är redundanta. Men ibland kanske du inte kan aktivera LSA-skydd. I sådana fall kan du aktivera den här regeln för att ge motsvarande skydd mot skadlig programvara som är lsass.exe.

## <a name="see-also"></a>Se även

* [Översikt över minskning av attackytan](attack-surface-reduction.md)
* [Utvärdera minskningsregler för attackytor](evaluate-attack-surface-reduction.md)
* [Anpassa minskningsregler för attackytor](customize-attack-surface-reduction.md)
* [Aktivera minskningsregler för attackytor](enable-attack-surface-reduction.md)
* [Kompatibilitet med Microsoft Defender med annat antivirusprogram/program mot skadlig programvara](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)
