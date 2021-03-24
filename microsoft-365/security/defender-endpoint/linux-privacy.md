---
title: Sekretess för Microsoft Defender ATP för Linux
description: Sekretesskontroller, hur du konfigurerar principinställningar som påverkar sekretess och information om diagnostikdata som samlas in i Microsoft Defender ATP för Linux.
keywords: microsoft, defender, atp, linux, sekretess, diagnostik
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 34a06a964baa475c5dedd019e40a6e31e44c0dd9
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073770"
---
# <a name="privacy-for-microsoft-defender-for-endpoint-for-linux"></a>Sekretess för Microsoft Defender för Endpoint för Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Microsoft strävar efter att tillhandahålla den information och de kontroller som du behöver för att göra val kring hur dina data samlas in och används när du använder Defender för Endpoint för Linux.

I det här avsnittet beskrivs vilka sekretesskontroller som är tillgängliga i produkten, hur du hanterar kontrollerna med principinställningar och mer information om datahändelser som samlas in.

## <a name="overview-of-privacy-controls-in-microsoft-defender-for-endpoint-for-linux"></a>Översikt över sekretesskontroller i Microsoft Defender för Endpoint för Linux

I det här avsnittet beskrivs sekretesskontroller för olika typer av data som samlas in av Defender för Endpoint för Linux.

### <a name="diagnostic-data"></a>Diagnostikdata

Diagnostikdata används för att hålla Defender för Slutpunkt säker och uppdaterad, identifiera, diagnostisera och åtgärda problem samt göra produktförbättringar.

Vissa diagnostiska data är obligatoriska, medan andra diagnostiska data är valfria. Du kan välja om du vill skicka obligatoriska eller valfria diagnostikdata genom att använda sekretesskontroller, till exempel principinställningar för organisationer.

Det finns två nivåer av diagnostikdata för Defender för endpoint-klientprogramvara som du kan välja bland:

* **Obligatoriskt:** De data som krävs för att hålla Defender för Slutpunkt säker, uppdaterad och fungerar som förväntat på den enhet som den är installerad på.

* **Valfritt:** Ytterligare data som hjälper Microsoft göra produktförbättringar och ger förbättrad information som hjälper till att identifiera, diagnostisera och åtgärda problem.

Som standard skickas endast obligatoriska diagnostikdata till Microsoft.

### <a name="cloud-delivered-protection-data"></a>Data för moln levererat skydd

Moln levererat skydd används för att ge ett bättre och snabbare skydd med tillgång till de senaste skyddsdata i molnet.

Aktivering av den molnbaserade skyddstjänsten är valfri, men vi rekommenderar starkt att den skyddar mot skadlig programvara på slutpunkter och i nätverket.

### <a name="sample-data"></a>Exempeldata

Exempeldata används för att förbättra skyddsfunktioner i produkten genom att skicka misstänkta exempel till Microsoft så att de kan analyseras. Det är valfritt att aktivera automatisk exempelinskickning.

Det finns tre nivåer för kontroll av exempelinskick:

- **Ingen**: inga misstänkta exempel skickas till Microsoft.
- **Kassaskåp**: endast misstänkta exempel som inte innehåller personligt identifierbar information skickas automatiskt. Det här är standardvärdet för den här inställningen.
- **Alla**: alla misstänkta exempel skickas till Microsoft.

## <a name="manage-privacy-controls-with-policy-settings"></a>Hantera sekretesskontroller med principinställningar

Om du är IT-administratör kanske du vill konfigurera kontrollerna på företagsnivå. 

Sekretesskontrollerna för de olika typerna av data som beskrivs i föregående avsnitt beskrivs i detalj i Ange inställningar för [Defender för Endpoint för Linux.](linux-preferences.md)

Precis som med alla nya principinställningar bör du noggrant testa dem i en begränsad, kontrollerad miljö för att säkerställa att de inställningar som du konfigurerar har önskad effekt innan du implementerar principinställningarna i en större utsträckning i organisationen.

## <a name="diagnostic-data-events"></a>Diagnostikdatahändelser

I det här avsnittet beskrivs vad som krävs för diagnostikdata och vad som betraktas som valfria diagnostikdata, tillsammans med en beskrivning av händelser och fält som samlas in.

### <a name="data-fields-that-are-common-for-all-events"></a>Datafält som är gemensamma för alla händelser
Det finns viss information om händelser som är gemensamma för alla aktiviteter, oavsett kategori eller dataundertyp. 

Följande fält är gemensamma för alla händelser:

| Fält                   | Beskrivning |
| ----------------------- | ----------- |
| plattform                | Den breda klassificeringen för den plattform där appen körs. Gör att Microsoft kan identifiera på vilka plattformar ett problem kan uppstå så att det kan prioriteras korrekt. |
| machine_guid            | Unikt ID associerat med enheten. Gör att Microsoft kan identifiera huruvida problem påverkar en uppsättning utvalda installationer och hur många användare som påverkas. |
| sense_guid              | Unikt ID associerat med enheten. Gör att Microsoft kan identifiera huruvida problem påverkar en uppsättning utvalda installationer och hur många användare som påverkas. |
| org_id                  | Unikt ID associerat med företaget som enheten tillhör. Microsoft kan identifiera om problem påverkar en uppsättning utvalda företag och hur många företag som påverkas. |
| hostname                | Namn på lokal enhet (utan DNS-suffix). Gör att Microsoft kan identifiera huruvida problem påverkar en uppsättning utvalda installationer och hur många användare som påverkas. |
| product_guid            | Unikt ID för produkten. Gör att Microsoft kan särskilja problem som påverkar olika typer av produkten. |
| app_version             | Version av Defender för Slutpunkt för Linux. Gör att Microsoft kan identifiera vilka versioner av produkten som visar ett problem så att det kan prioriteras korrekt.|
| sig_version             | Version av databasen för säkerhetsintelligens. Gör att Microsoft kan identifiera vilka versioner av säkerhetsinformation som visar ett problem så att det kan prioriteras korrekt. |
| supported_compressions  | Lista över komprimeringsalgoritmer som stöds av programmet, till exempel `['gzip']` . Gör att Microsoft förstår vilka typer av komprimering som kan användas när de kommunicerar med programmet. |
| release_ring            | Ring som enheten är kopplad till (till exempel Insider – snabbt, Insider – långsamt, Produktion). Gör att Microsoft kan identifiera vilken version som ett problem kan inträffa så att det kan prioriteras korrekt. |

### <a name="required-diagnostic-data"></a>Obligatoriska diagnostikdata

**Obligatoriska diagnostikdata** är de lägsta data som krävs för att hålla Defender för Slutpunkt säker, uppdaterad och utför den som förväntat på den enhet som den är installerad på.

Obligatoriska diagnostikdata hjälper till att identifiera problem med Microsoft Defender för Endpoint som kan vara relaterade till en enhet eller programvarukonfiguration. Den kan till exempel hjälpa till att avgöra om en Defender för Slutpunkt-funktion kraschar oftare på en viss version av operativsystemet, med nyligen använda funktioner eller när vissa Defender för Slutpunkt-funktioner är inaktiverade. Obligatoriska diagnostikdata hjälper Microsoft identifiera, diagnostisera och åtgärda dessa problem snabbare så att påverkan på användare eller organisationer minskas.

#### <a name="software-setup-and-inventory-data-events"></a>Programvaruinstallation och lagringshändelser

**Installation/avinstallation av Microsoft Defender för slutpunkt**

Följande fält samlas in:

| Fält            | Beskrivning |
| ---------------- | ----------- |
| correlation_id   | Unikt ID associerat med installationen. |
| version          | Version av paketet. |
| allvarlighetsgrad         | Meddelandets allvarlighetsgrad (till exempel information). |
| kod             | Kod som beskriver åtgärden. |
| text             | Ytterligare information associerad med produktinstallationen. |

**Microsoft Defender för slutpunktskonfiguration**

Följande fält samlas in:

| Fält                                               | Beskrivning |
| --------------------------------------------------- | ----------- |
| antivirus_engine.enable_real_time_protection        | Om realtidsskydd är aktiverat på enheten eller inte. |
| antivirus_engine.passivt_läge                       | Oavsett om passivt läge är aktiverat på enheten eller inte. |
| cloud_service.enabled                               | Om moln levererat skydd är aktiverat på enheten eller inte. |
| cloud_service.timeout                               | Time out when the application communicates with the Defender for Endpoint cloud. |
| cloud_service.heartbeat_interval                    | Intervall mellan flera hjärtslag som skickas av produkten till molnet. |
| cloud_service.service_uri                           | URI som används för att kommunicera med molnet. |
| cloud_service.diagnostic_level                      | Diagnostiknivå för enheten (obligatoriskt, valfritt). |
| cloud_service.automatic_sample_submission           | Automatisk exempelinskickningsnivå för enheten (ingen, säker, alla). |
| edr.early_preview                                   | Om enheten ska köra EDR-funktioner för tidig förhandsgranskning. |
| edr.group_id                                        | Gruppidentifierare som används av identifierings- och svarskomponenten. |
| edr.tags                                            | Användardefinierade taggar. |
| funktioner. \[ valfritt funktionsnamn\]                  | Lista över förhandsgranskningsfunktioner, tillsammans med huruvida de är aktiverade eller inte. |

#### <a name="product-and-service-usage-data-events"></a>Produkt- och tjänstanvändningshändelser

**Säkerhetsintelligensuppdateringsrapport**

Följande fält samlas in:

| Fält            | Beskrivning |
| ---------------- | ----------- |
| from_version     | Ursprunglig säkerhetsintelligensversion. |
| to_version       | Ny säkerhetsintelligensversion. |
| status           | Status för uppdateringen som anger framgång eller fel. |
| using_proxy      | Om uppdateringen gjordes via en proxyserver. |
| fel            | Felkod om uppdateringen misslyckades. |
| orsak           | Felmeddelande om uppdateringen misslyckades. |

#### <a name="product-and-service-performance-data-events"></a>Datahändelser för produkt- och tjänstprestanda

**Statistik över Kernel-tillägg**

Följande fält samlas in:

| Fält            | Beskrivning |
| ---------------- | ----------- |
| version          | Version av Defender för Slutpunkt för Linux. |
| instance_id      | Unikt ID som genererades vid start av kernel-tillägg. |
| trace_level      | Spårningsnivån för kernel-tillägget. |
| undersystem        | Det underliggande undersystemet som används för realtidsskydd. |
| ipc.connects     | Antal anslutningsförfrågningar som mottagits av kernel-tilläggen. |
| ipc.rejects      | Antal anslutningsbegäranden som avvisats av kernel-tillägget. |
| ipc.connected    | Om det finns någon aktiv anslutning till kernel-tilläggen. |

#### <a name="support-data"></a>Supportdata

**Diagnostikloggar**

Diagnostikloggar samlas bara in med användarens medgivande som en del av funktionen för feedbackinskick. Följande filer samlas in som en del av supportloggarna:

- Alla filer under */var/log/microsoft/mdatp*
- Delmängd filer under */etc/opt/microsoft/mdatp* som skapas och används av Defender för Endpoint för Linux
- Produktinstallations- och avinstallationsloggar under */var/log/microsoft_mdatp_ \* .log*

### <a name="optional-diagnostic-data"></a>Valfria diagnostikdata

**Valfria diagnostikdata** är ytterligare data som hjälper Microsoft göra produktförbättringar och ger förbättrad information som hjälper till att identifiera, diagnostisera och åtgärda problem.

Om du väljer att skicka valfria diagnostikdata omfattas även obligatoriska diagnostikdata.

Exempel på valfria diagnostikdata är data som Microsoft samlar in om produktkonfiguration (till exempel antal undantag som angetts på enheten) och produktprestanda (mängdåtgärder om prestanda för komponenter i produkten).

#### <a name="software-setup-and-inventory-data-events"></a>Programvaruinstallation och lagringshändelser

**Microsoft Defender för slutpunktskonfiguration**

Följande fält samlas in:

| Fält                                              | Beskrivning |
| -------------------------------------------------- | ----------- |
| connection_retry_timeout                           | Anslutningen försöker time out igen när anslutningen kommunicerar med molnet. |
| file_hash_cache_maximum                            | Storleken på produktcachen. |
| crash_upload_daily_limit                           | Begränsningen för kraschloggar som laddas upp dagligen. |
| antivirus_engine.exclusions[].is_directory         | Om undantaget från genomsökning är en katalog eller inte. |
| antivirus_engine.exclusions[].path                 | Sökväg som uteslöts från genomsökning. |
| antivirus_engine.exclusions[].extension            | Tillägget är inte till förskanning. |
| antivirus_engine.exclusions[].name                 | Namnet på filen som undantas från genomsökning. |
| antivirus_engine.scan_cache_maximum                | Storleken på produktcachen. |
| antivirus_engine.maximum_scan_threads              | Maximalt antal trådar som används för genomsökning. |
| antivirus_engine.threat_restoration_exclusion_time | Time out before a file restored from the quarantine can beected again. |
| filesystem_scanner.full_scan_directory             | Fullständig genomsökningskatalog. |
| filesystem_scanner.quick_scan_directories          | Lista med kataloger som används i snabbsökning. |
| edr.latency_mode                                   | Svarstidsläge som används av identifierings- och svarskomponenten. |
| edr.proxy_address                                  | Proxyadress som används av identifierings- och svarskomponenten. |

**Konfiguration av Microsoft Auto-Update**

Följande fält samlas in:

| Fält                       | Beskrivning |
| --------------------------- | ----------- |
| how_to_check                | Avgör hur produktuppdateringar kontrolleras (till exempel automatiskt eller manuellt). |
| channel_name                | Uppdatera kanal som är kopplad till enheten. |
| manifest_server             | Den server som används för att ladda ned uppdateringar. |
| update_cache                | Platsen för cachen som används för att lagra uppdateringar. |

### <a name="product-and-service-usage"></a>Produkt- och tjänstanvändning

#### <a name="diagnostic-log-upload-started-report"></a>Rapporten Startad diagnostiklogguppladdning

Följande fält samlas in:

| Fält            | Beskrivning |
| ---------------- | ----------- |
| sha256           | SHA256-identifierare för supportloggen. |
| storlek             | Storlek på supportloggen. |
| original_path    | Sökväg till supportloggen (alltid under */var/opt/microsoft/mdatp/wdavdiag/*). |
| format           | Format för supportloggen. |

#### <a name="diagnostic-log-upload-completed-report"></a>Rapport om slutförd diagnostiklogguppladdning

Följande fält samlas in:

| Fält            | Beskrivning |
| ---------------- | ----------- |
| request_id       | Korrelations-ID för begäran om uppladdning av supportlogg. |
| sha256           | SHA256-identifierare för supportloggen. |
| blob_sas_uri     | URI som används av programmet för att ladda upp supportloggen. |

#### <a name="product-and-service-performance-data-events"></a>Datahändelser för produkt- och tjänstprestanda

**Oväntat programavslut (kraschar)**

Oväntat programavslut (krasch) och tillståndet för programmet när det händer.

**Statistik över Kernel-tillägg**

Följande fält samlas in:

| Fält                          | Beskrivning |
| ------------------------------ | ----------- |
| pkt_ack_timeout                | Följande egenskaper är aggregerade numeriska värden som representerar antalet händelser som inträffat sedan kernel-tilläggen startades. |
| pkt_ack_conn_timeout             | |
| ipc.ack_pkts                     | |
| ipc.nack_pkts                    | |
| ipc.send.ack_no_conn             | |
| ipc.send.nack_no_conn            | |
| ipc.send.ack_no_qsq              | |
| ipc.send.nack_no_qsq             | |
| ipc.ack.no_space                 | |
| ipc.ack.timeout                  | |
| ipc.ack.ackd_fast                | |
| ipc.ack.ackd                     | |
| ipc.recv.bad_pkt_len             | |
| ipc.recv.bad_reply_len           | |
| ipc.recv.no_waiter               | |
| ipc.recv.copy_failed             | |
| ipc.thth.vnode.mask             | |
| ipc.thth.vnode.read             | |
| ipc.thth.vnode.write            | |
| ipc.kauth.vnode.exec             | |
| ipc.thth.vnode.del              | |
| ipc.kauth.vnode.read_attr        | |
| ipc.kauth.vnode.write_attr       | |
| ipc.kauth.vnode.read_ex_attr     | |
| ipc.kauth.vnode.write_ex_attr    | |
| ipc.kauth.vnode.read_sec         | |
| ipc.kauth.vnode.write_sec        | |
| ipc.kauth.vnode.take_own         | |
| ipc.kauth.vnode.link             | |
| ipc.thth.vnode.create           | |
| ipc.thth.vnode.move             | |
| ipc.thth.vnode.mount            | |
| ipc.thth.vnode.denied           | |
| ipc.kauth.vnode.ackd_before_deadline | |
| ipc.kauth.vnode.missed_deadline  | |
| ipc.kauth.file_op.mask           | |
| ipc.kauth_file_op.open           | |
| ipc.kauth.file_op.close          | |
| ipc.kauth.file_op.close_modified | |
| ipc.kauth.file_op.move           | |
| ipc.kauth.file_op.link           | |
| ipc.kauth.file_op.exec           | |
| ipc.kauth.file_op.remove         | |
| ipc.kauth.file_op.unmount        | |
| ipc.kauth.file_op.fork           | |
| ipc.kauth.file_op.create         | |

## <a name="resources"></a>Resurser

- [Sekretess på Microsoft](https://privacy.microsoft.com/)
