---
title: Konfigurera Microsoft Defender Antivirus med Grupprincip
description: Lär dig hur du använder en grupprincip för att konfigurera och hantera Microsoft Defender Antivirus på slutpunkterna i Microsoft Defender för slutpunkt.
keywords: grupprincip, GPO, konfiguration, inställningar
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/07/2021
ms.reviewer: ksarens, jtoole, pahuijbr
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: 81cba445482b1fceb8bd520f2be88d55db2a47fb
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52296737"
---
# <a name="use-group-policy-settings-to-configure-and-manage-microsoft-defender-antivirus"></a>Använda grupprincipinställningar för att konfigurera och hantera Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

Du kan använda [grupprinciper](/windows/win32/srvnodes/group-policy) för att konfigurera Microsoft Defender Antivirus och hantera e-Microsoft Defender Antivirus slutpunkter.

## <a name="configure-microsoft-defender-antivirus-using-group-policy"></a>Konfigurera Microsoft Defender Antivirus med grupprincip

I allmänhet kan du använda följande procedur för att konfigurera eller ändra Microsoft Defender Antivirus grupprincipinställningar:

1. Öppna grupprinciphanteringskonsolen på hanteringsdatorn för [grupprinciper,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))högerklicka på det grupprincipobjekt (GPO) du vill konfigurera och klicka på **Redigera.**

2. Med **grupprinciphanteringsredigeraren går** du till **Datorkonfiguration**.

3. Klicka **på Administrativa mallar**.

4. Expandera trädet och visa **Windows komponenter**  >  **Microsoft Defender Antivirus**.

5. Expandera det avsnitt (kallas för Plats i tabellen i det här avsnittet) som innehåller den inställning du vill konfigurera, dubbelklicka på inställningen för att öppna den och gör konfigurationsändringar. 

6. [Distribuera det uppdaterade GPO:t på normalt sätt.](/windows/win32/srvnodes/group-policy) 

## <a name="group-policy-settings-and-resources"></a>Grupprincipinställningar och -resurser

Följande tabell i det här avsnittet innehåller de grupprincipinställningar som är tillgängliga i Windows 10, version 1703, och innehåller länkar till lämpligt avsnitt i det här dokumentationsbiblioteket (om tillämpligt). 

> [!TIP]
> [Hämta grupprincipkalkylbladet för Inställningar för Windows 10 maj 2020-uppdatering (2004).](https://www.microsoft.com/download/101451) Det här kalkylbladet innehåller principinställningar för dator- och användarkonfigurationer som ingår i administrationsmallfilerna som levereras med för den Windows 10 maj 2020-uppdateringen (2004). Du kan konfigurera de här principinställningarna när du redigerar grupprincipobjekt.

| Plats | Inställning | Artikel |
|:---|:---|:---|
| Klientgränssnitt | Aktivera huvudlöst gränssnittsläge | [Hindra användare från att se eller interagera Microsoft Defender Antivirus användargränssnittet](prevent-end-user-interaction-microsoft-defender-antivirus.md) |
| Klientgränssnitt | Visa ytterligare text för klienter när de behöver utföra en åtgärd | [Konfigurera meddelanden som visas på slutpunkter](configure-notifications-microsoft-defender-antivirus.md) |
| Klientgränssnitt | Ignorera alla meddelanden | [Konfigurera meddelanden som visas på slutpunkter](configure-notifications-microsoft-defender-antivirus.md) |
| Klientgränssnitt | Ignorerar meddelanden om omstart | [Konfigurera meddelanden som visas på slutpunkter](configure-notifications-microsoft-defender-antivirus.md) |
| Undantag | Undantag för filnamnstillägg | [Konfigurera och validera undantag i Microsoft Defender Antivirus genomsökningar](configure-exclusions-microsoft-defender-antivirus.md) |
| Undantag | Undantag för sökväg | [Konfigurera och validera undantag i Microsoft Defender Antivirus genomsökningar](configure-exclusions-microsoft-defender-antivirus.md) |
| Undantag | Undantag från processer | [Konfigurera och validera undantag i Microsoft Defender Antivirus genomsökningar](configure-exclusions-microsoft-defender-antivirus.md) | 
| Undantag | Inaktivera automatiska undantag | [Konfigurera och validera undantag i Microsoft Defender Antivirus genomsökningar](configure-exclusions-microsoft-defender-antivirus.md) |
| KARTOR | Konfigurera funktionen "Block vid första synen" | [Aktivera block vid första synen](configure-block-at-first-sight-microsoft-defender-antivirus.md) |
| KARTOR | Ansluta till Microsoft MAPS | [Aktivera molnbaserat skydd](enable-cloud-protection-microsoft-defender-antivirus.md) |
| KARTOR | Skicka filexempel när ytterligare analys krävs | [Aktivera molnbaserat skydd](enable-cloud-protection-microsoft-defender-antivirus.md) |
| KARTOR | Konfigurera åsidosättning av lokal inställning för rapportering till Microsoft MAPS | [Förhindra eller tillåta användare att lokalt ändra principinställningar](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| MpEngine | Konfigurera utökad molnkontroll | [Konfigurera tidsgräns för blockering i molnet](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) |
| MpEngine | Välj molnskyddsnivå | [Ange nivå för molnbaserat skydd](specify-cloud-protection-level-microsoft-defender-antivirus.md) |
| System för nätverksinspektion | Ange ytterligare definitionsuppsättningar för kontroll av nätverkstrafik | [Ange ytterligare definitionsuppsättningar för kontroll av nätverkstrafik](specify-additional-definitions-network-traffic-inspection-mdav.md) |
| System för nätverksinspektion | Aktivera att definitionen inaktiveras | [Konfigurera att definitionen ska avse](turn-on-definition-retirement.md)  |
| System för nätverksinspektion | Aktivera protokolligenkänning | [Aktivera protokolligenkänning](turn-on-protocol-recognition.md)  |
| Karantän | Konfigurera åsidosättning av lokal inställning för borttagning av objekt från mappen Karantän | [Förhindra eller tillåta användare att lokalt ändra principinställningar](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Karantän | Konfigurera borttagning av objekt från mappen Karantän | [Konfigurera åtgärder för Microsoft Defender Antivirus genomsökningar](configure-remediation-microsoft-defender-antivirus.md) |
| Realtidsskydd | Konfigurera en lokal åsidosättning för övervakning av fil- och programaktivitet på datorn | [Förhindra eller tillåta användare att lokalt ändra principinställningar](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Realtidsskydd | Konfigurera åsidosättning av lokal inställning för övervakning av inkommande och utgående filaktivitet | [Förhindra eller tillåta användare att lokalt ändra principinställningar](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Realtidsskydd | Konfigurera åsidosättning av lokal inställning för genomsökning av alla nedladdade filer och bifogade filer | [Förhindra eller tillåta användare att lokalt ändra principinställningar](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Realtidsskydd | Konfigurera åsidosättning av lokal inställning för att aktivera beteendeuppföljning | [Förhindra eller tillåta användare att lokalt ändra principinställningar](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Realtidsskydd | Konfigurera åsidosättning av lokal inställning för att aktivera realtidsskydd | [Förhindra eller tillåta användare att lokalt ändra principinställningar](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Realtidsskydd | Definiera den maximala storleken på nedladdade filer och bifogade filer som ska genomsökas | [Aktivera och Microsoft Defender Antivirus av skydd och övervakning alltid](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Realtidsskydd | Övervaka fil- och programaktivitet på datorn | [Aktivera och Microsoft Defender Antivirus av skydd och övervakning alltid](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Realtidsskydd | Genomsöka alla nedladdade filer och bifogade filer | [Aktivera och Microsoft Defender Antivirus av skydd och övervakning alltid](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Realtidsskydd | Inaktivera realtidsskydd | [Aktivera och Microsoft Defender Antivirus av skydd och övervakning alltid](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Realtidsskydd | Aktivera beteendeövervakning | [Aktivera och Microsoft Defender Antivirus av skydd och övervakning alltid](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Realtidsskydd | Aktivera processsökning när realtidsskydd är aktiverat | [Aktivera och Microsoft Defender Antivirus av skydd och övervakning alltid](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Realtidsskydd | Aktivera aviseringar om rådata för volymskrivning | [Aktivera och Microsoft Defender Antivirus av skydd och övervakning alltid](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Realtidsskydd | Konfigurera övervakning för inkommande och utgående fil och programaktivitet | [Aktivera och Microsoft Defender Antivirus av skydd och övervakning alltid](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Åtgärda | Konfigurera en lokal åsidosättning för tid på dagen för att köra en schemalagd fullständig genomsökning för att slutföra åtgärd | [Förhindra eller tillåta användare att lokalt ändra principinställningar](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Åtgärda | Ange veckodagen då en schemalagd fullständig genomsökning ska köras | [Konfigurera schemalagda Microsoft Defender Antivirus genomsökningar](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Åtgärda | Ange tid på dagen då en schemalagd fullständig genomsökning ska köras för att slutföra åtgärd | [Konfigurera schemalagda Microsoft Defender Antivirus genomsökningar](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Rapportering | Inaktivera utökade meddelanden | [Konfigurera meddelanden som visas på slutpunkter](configure-notifications-microsoft-defender-antivirus.md)
| Rot | Inaktivera Microsoft Defender Antivirus | Används inte (Inställningen måste vara Ej **konfigurerad för att säkerställa** att alla installerade antivirusappar från tredje part fungerar som de ska)
| Rot | Definiera adresser för att kringgå proxyserver | Används inte |
| Rot | Definiera autoconfig proxy (.pac) för anslutning till nätverket | Används inte |
| Rot | Definiera proxyserver för anslutning till nätverket | Används inte |
| Rot | Konfigurera lokala administratörskopplingsbeteenden för listor | [Förhindra eller tillåta användare att lokalt ändra principinställningar](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Rot | Tillåt att program mot skadlig programvara startar med vanlig prioritet | [Konfigurera åtgärder för Microsoft Defender Antivirus genomsökningar](configure-remediation-microsoft-defender-antivirus.md) |
| Rot | Tillåt att program mot skadlig programvara alltid körs | [Konfigurera åtgärder för Microsoft Defender Antivirus genomsökningar](configure-remediation-microsoft-defender-antivirus.md) |
| Rot | Inaktivera rutinreparation | [Konfigurera åtgärder för Microsoft Defender Antivirus genomsökningar](configure-remediation-microsoft-defender-antivirus.md) |
| Rot | Slumpmässigt schemalagda aktivitetstider | [Konfigurera schemalagda genomsökningar för Microsoft Defender Antivirus](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Skanna | Tillåt användare att pausa genomsökning | [Hindra användare från att se eller interagera Microsoft Defender Antivirus användargränssnittet](prevent-end-user-interaction-microsoft-defender-antivirus.md) (stöds inte Windows 10) |
| Skanna | Kontrollera om du har de senaste definitionerna av virus och spionprogram innan du kör en schemalagd sökning | [Hantera händelsebaserade uppdateringar](manage-event-based-updates-microsoft-defender-antivirus.md) |
| Skanna | Definiera efter hur många dagar en sökning måste göra en uppläsning | [Hantera uppdateringar för slutpunkter som är in uppdaterade](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| Skanna | Aktivera snabbsökning | [Hantera uppdateringar för slutpunkter som är in uppdaterade](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| Skanna | Aktivera snabbsökning | [Hantera uppdateringar för slutpunkter som är in uppdaterade](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| Skanna | Konfigurera åsidosättning av lokal inställning för maximal procentandel av CPU-belastningen | [Förhindra eller tillåta användare att lokalt ändra principinställningar](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Skanna | Konfigurera åsidosättning av lokal inställning för schemasökningsdag | [Förhindra eller tillåta användare att lokalt ändra principinställningar](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Skanna | Konfigurera åsidosättning av lokal inställning för schemalagd snabbsökningstid | [Förhindra eller tillåta användare att lokalt ändra principinställningar](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Skanna | Konfigurera åsidosättning av lokal inställning för schemalagd genomsökningstid | [Förhindra eller tillåta användare att lokalt ändra principinställningar](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Skanna | Konfigurera en lokal åsidosättning av lokal inställning för den genomsökningstyp som ska användas för en schemalagd sökning | [Förhindra eller tillåta användare att lokalt ändra principinställningar](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Skanna | Skapa en systemåterställningspunkt | [Konfigurera åtgärder för Microsoft Defender Antivirus genomsökningar](configure-remediation-microsoft-defender-antivirus.md) |
| Skanna | Aktivera borttagning av objekt från mappen genomsökningshistorik | [Konfigurera åtgärder för Microsoft Defender Antivirus genomsökningar](configure-remediation-microsoft-defender-antivirus.md) |
| Skanna | Aktivera heuristisk | [Aktivera och Microsoft Defender Antivirus av skydd och övervakning alltid](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Skanna | Aktivera genomsökning av e-post | [Konfigurera skanningsalternativ i Microsoft Defender Antivirus](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Skanna | Aktivera genomsökning avparsningspunkt | [Konfigurera skanningsalternativ i Microsoft Defender Antivirus](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Skanna | Kör fullständig sökning på mappade nätverksenheter | [Konfigurera skanningsalternativ i Microsoft Defender Antivirus](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Skanna | Skanna arkivfiler | [Konfigurera skanningsalternativ i Microsoft Defender Antivirus](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Skanna | Skanna nätverksfiler | [Konfigurera skanningsalternativ i Microsoft Defender Antivirus](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Skanna | Skanna packade körbara filer | [Konfigurera skanningsalternativ i Microsoft Defender Antivirus](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Skanna | Skanna flyttbara enheter | [Konfigurera skanningsalternativ i Microsoft Defender Antivirus](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Skanna | Ange maximalt djup för att söka igenom arkivfiler | [Konfigurera skanningsalternativ i Microsoft Defender Antivirus](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Skanna | Ange maximal procentandel av belastningen på processorerna vid en genomsökning | [Konfigurera skanningsalternativ i Microsoft Defender Antivirus](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Skanna | Ange den maximala storleken på de arkivfiler som ska genomsökas | [Konfigurera skanningsalternativ i Microsoft Defender Antivirus](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Skanna | Ange veckodagen då en schemalagd sökning ska köras | [Konfigurera schemalagda genomsökningar för Microsoft Defender Antivirus](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Skanna | Ange tidsintervallet för att köra snabbsökningar per dag | [Konfigurera schemalagda genomsökningar för Microsoft Defender Antivirus](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Skanna | Ange vilken skanningstyp som ska användas för en schemalagd sökning | [Konfigurera schemalagda genomsökningar för Microsoft Defender Antivirus](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Skanna | Ange tiden för en daglig snabbsökning | [Konfigurera schemalagda genomsökningar för Microsoft Defender Antivirus](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Skanna | Ange tid på dagen då en schemalagd sökning ska köras | [Konfigurera schemalagda genomsökningar för Microsoft Defender Antivirus](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Skanna | Starta den schemalagda genomsökningen bara när datorn är på, men inte använder | [Konfigurera schemalagda genomsökningar för Microsoft Defender Antivirus](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Säkerhetsintelligensuppdateringar | Tillåt säkerhetsintelligensuppdateringar från Microsoft Update | [Hantera uppdateringar för mobila enheter och virtuella datorer(VM)](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md) |
| Säkerhetsintelligensuppdateringar | Tillåt säkerhetsintelligensuppdateringar när de körs på batteri | [Hantera uppdateringar för mobila enheter och virtuella datorer(VM)](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md) |
| Säkerhetsintelligensuppdateringar | Tillåt att meddelanden inaktiverar definitionsbaserade rapporter för Microsoft MAPS | [Hantera händelsebaserade uppdateringar](manage-event-based-updates-microsoft-defender-antivirus.md) |
| Säkerhetsintelligensuppdateringar | Tillåt säkerhetsintelligensuppdateringar i realtid som baseras på rapporter till Microsoft MAPS | [Hantera händelsebaserade uppdateringar](manage-event-based-updates-microsoft-defender-antivirus.md) |
| Säkerhetsintelligensuppdateringar | Kontrollera om de senaste definitionerna av virus och spionprogram visas vid start | [Hantera händelsebaserade uppdateringar](manage-event-based-updates-microsoft-defender-antivirus.md) |
| Säkerhetsintelligensuppdateringar | Definiera filresurser för hämtning av säkerhetsintelligensuppdateringar | [Hantera Microsoft Defender Antivirus säkerhets- och säkerhetsintelligensuppdateringar](manage-protection-updates-microsoft-defender-antivirus.md) |
| Säkerhetsintelligensuppdateringar | Definiera efter hur många dagar en uppdatering av säkerhetsintelligens krävs | [Hantera uppdateringar för slutpunkter som är in uppdaterade](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| Säkerhetsintelligensuppdateringar | Ange antalet dagar innan definitioner av spionprogram anses vara inuella | [Hantera uppdateringar för slutpunkter som är in uppdaterade](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| Säkerhetsintelligensuppdateringar | Definiera antalet dagar innan virusdefinitioner anses vara in datera | [Hantera uppdateringar för slutpunkter som är in uppdaterade](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| Säkerhetsintelligensuppdateringar | Definiera källordningen för hämtning av säkerhetsintelligensuppdateringar | [Hantera Microsoft Defender Antivirus säkerhets- och säkerhetsintelligensuppdateringar](manage-protection-updates-microsoft-defender-antivirus.md) |
| Säkerhetsintelligensuppdateringar | Starta en säkerhetsintelligensuppdatering vid start | [Hantera händelsebaserade uppdateringar](manage-event-based-updates-microsoft-defender-antivirus.md) |
| Säkerhetsintelligensuppdateringar | Ange veckodagen för att söka efter säkerhetsintelligensuppdateringar | [Hantera när skyddsuppdateringar ska hämtas och tillämpas](manage-protection-update-schedule-microsoft-defender-antivirus.md) |
| Säkerhetsintelligensuppdateringar | Ange intervallet för att söka efter säkerhetsintelligensuppdateringar | [Hantera när skyddsuppdateringar ska hämtas och tillämpas](manage-protection-update-schedule-microsoft-defender-antivirus.md) |
| Säkerhetsintelligensuppdateringar | Ange tiden för att söka efter säkerhetsintelligensuppdateringar | [Hantera när skyddsuppdateringar ska hämtas och tillämpas](manage-protection-update-schedule-microsoft-defender-antivirus.md) |
| Säkerhetsintelligensuppdateringar | Aktivera genomsökning efter säkerhetsintelligensuppdatering | [Konfigurera schemalagda genomsökningar för Microsoft Defender Antivirus](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Hot | Ange varningsnivåer för hot där standardåtgärden inte ska vidtas när den upptäcks | [Konfigurera åtgärder för Microsoft Defender Antivirus genomsökningar](configure-remediation-microsoft-defender-antivirus.md) |
| Hot | Ange hot där standardåtgärden inte ska vidtas när den identifieras | [Konfigurera åtgärder för Microsoft Defender Antivirus genomsökningar](configure-remediation-microsoft-defender-antivirus.md) |

## <a name="see-also"></a>Se även

- [Referensavsnitt om hanterings- och konfigurationsverktyg](configuration-management-reference-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus i Windows 10](microsoft-defender-antivirus-in-windows-10.md)
