---
title: Hitta utpressningstrojaner med avancerad sökning
description: Använd avancerad sökning för att hitta enheter som kan påverkas av utpressningstrojaner.
keywords: advanced hunting, ransomware, threat hunting, cyber threat hunting, search, query, telemetry, Microsoft 365, Microsoft Threat Protection, Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 2f283008e90dbe5dadc0e1e04db589d89a15a8b8
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076370"
---
# <a name="hunt-for-ransomware"></a><span data-ttu-id="bc938-104">Jag utpressningstrojan</span><span class="sxs-lookup"><span data-stu-id="bc938-104">Hunt for ransomware</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="bc938-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="bc938-105">**Applies to:**</span></span>
- <span data-ttu-id="bc938-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bc938-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="bc938-107">Utpressningstrojaner har snabbt utvecklats från att vara enkla varor som skadlig programvara påverkar enskilda datoranvändare till ett företagshot som allvarligt påverkar branscher och myndigheter.</span><span class="sxs-lookup"><span data-stu-id="bc938-107">Ransomware has rapidly evolved from being simple commodity malware affecting individual computer users to an enterprise threat that is severely impacting industries and government institutions.</span></span> <span data-ttu-id="bc938-108">[Microsoft 365 Defender](microsoft-365-defender.md) har många funktioner för att identifiera och blockera utpressningstrojaner och associerade intrångsaktiviteter, men om du utför förebyggande kontroller för tecken på intrång kan detta skydda nätverket.</span><span class="sxs-lookup"><span data-stu-id="bc938-108">While [Microsoft 365 Defender](microsoft-365-defender.md) provides many capabilities that detect and block ransomware and associated intrusion activities, performing proactive checks for signs of compromise can help keep your network protected.</span></span>

> [<span data-ttu-id="bc938-109">Läs mer om utpressningstrojaner som drivs av människor</span><span class="sxs-lookup"><span data-stu-id="bc938-109">Read about human-operated ransomware</span></span>](https://www.microsoft.com/security/blog/2020/03/05/human-operated-ransomware-attacks-a-preventable-disaster/)

<span data-ttu-id="bc938-110">Med [avancerad sökning](advanced-hunting-overview.md) i Microsoft 365 Defender kan du skapa frågor som hittar enskilda artefakter som är kopplade till utpressningstrojaner.</span><span class="sxs-lookup"><span data-stu-id="bc938-110">With [advanced hunting](advanced-hunting-overview.md) in Microsoft 365 Defender, you can create queries that locate individual artifacts associated with ransomware activity.</span></span> <span data-ttu-id="bc938-111">Du kan också köra mer avancerade frågor som kan leta efter tecken på aktivitet och väga dessa tecken för att hitta enheter som kräver omedelbar uppmärksamhet.</span><span class="sxs-lookup"><span data-stu-id="bc938-111">You can also run more sophisticated queries that can look for signs of activity and weigh those signs to find devices that require immediate attention.</span></span>

## <a name="signs-of-ransomware-activity"></a><span data-ttu-id="bc938-112">Tecken på utpressningstrojaner</span><span class="sxs-lookup"><span data-stu-id="bc938-112">Signs of ransomware activity</span></span>
<span data-ttu-id="bc938-113">Microsoft-säkerhetsvakter har observerat flera vanliga men diskreta artefakter i många utpressningstrojaner som startats av avancerade utpressningspersoner.</span><span class="sxs-lookup"><span data-stu-id="bc938-113">Microsoft security researchers have observed various common yet subtle artifacts in many ransomware campaigns launched by sophisticated intruders.</span></span> <span data-ttu-id="bc938-114">Dessa skyltar innebär oftast användning av systemverktyg för att förbereda kryptering, förhindra identifiering och tydliga bevis för bevis.</span><span class="sxs-lookup"><span data-stu-id="bc938-114">These signs mostly involve use of system tools to prepare for encryption, prevent detection, and clear forensic evidence.</span></span>

| <span data-ttu-id="bc938-115">Utpressningstrojaner</span><span class="sxs-lookup"><span data-stu-id="bc938-115">Ransomware activity</span></span> | <span data-ttu-id="bc938-116">Vanliga verktyg</span><span class="sxs-lookup"><span data-stu-id="bc938-116">Common tools</span></span> | <span data-ttu-id="bc938-117">Avsikter</span><span class="sxs-lookup"><span data-stu-id="bc938-117">Intent</span></span> |
|--|--|--|
| <span data-ttu-id="bc938-118">Stoppa processer</span><span class="sxs-lookup"><span data-stu-id="bc938-118">Stop processes</span></span> | <span data-ttu-id="bc938-119">_taskkill.exe_, _nettostopp_</span><span class="sxs-lookup"><span data-stu-id="bc938-119">_taskkill.exe_, _net stop_</span></span> | <span data-ttu-id="bc938-120">Se till att filer som är riktade för kryptering inte är låsta av olika program.</span><span class="sxs-lookup"><span data-stu-id="bc938-120">Ensure files targeted for encryption are not locked by various applications.</span></span> |
| <span data-ttu-id="bc938-121">Inaktivera tjänster</span><span class="sxs-lookup"><span data-stu-id="bc938-121">Turn off services</span></span> | <span data-ttu-id="bc938-122">_sc.exe_</span><span class="sxs-lookup"><span data-stu-id="bc938-122">_sc.exe_</span></span> | <span data-ttu-id="bc938-123">– se till att filer som är riktade för kryptering inte är låsta av olika program.</span><span class="sxs-lookup"><span data-stu-id="bc938-123">- Ensure files targeted for encryption are not locked by various applications.</span></span><br><span data-ttu-id="bc938-124">– Förhindra att säkerhetsprogramvara stör kryptering och annan utpressningstrojaner.</span><span class="sxs-lookup"><span data-stu-id="bc938-124">- Prevent security software from disrupting encryption and other ransomware activity.</span></span><br><span data-ttu-id="bc938-125">- Stoppa säkerhetskopiering av programvara från att skapa återställningsbara kopior.</span><span class="sxs-lookup"><span data-stu-id="bc938-125">- Stop backup software from creating recoverable copies.</span></span>  |
| <span data-ttu-id="bc938-126">Ta bort loggar och filer</span><span class="sxs-lookup"><span data-stu-id="bc938-126">Delete logs and files</span></span> | <span data-ttu-id="bc938-127">_cipher.exe_, _wevtutil_, _fsutil.exe_</span><span class="sxs-lookup"><span data-stu-id="bc938-127">_cipher.exe_, _wevtutil_, _fsutil.exe_</span></span> | <span data-ttu-id="bc938-128">Ta bort tekniska bevis.</span><span class="sxs-lookup"><span data-stu-id="bc938-128">Remove forensic evidence.</span></span> |
| <span data-ttu-id="bc938-129">Ta bort skuggkopior</span><span class="sxs-lookup"><span data-stu-id="bc938-129">Delete shadow copies</span></span>  | <span data-ttu-id="bc938-130">_vsadmin.exe_, _wmic.exe_</span><span class="sxs-lookup"><span data-stu-id="bc938-130">_vsadmin.exe_, _wmic.exe_</span></span> | <span data-ttu-id="bc938-131">Ta bort skuggkopior på enheten som kan användas för att återställa krypterade filer.</span><span class="sxs-lookup"><span data-stu-id="bc938-131">Remove drive shadow copies that can be used to recover encrypted files.</span></span> |
| <span data-ttu-id="bc938-132">Ta bort och stoppa säkerhetskopior</span><span class="sxs-lookup"><span data-stu-id="bc938-132">Delete and stop backups</span></span> | <span data-ttu-id="bc938-133">_wbadmin.exe_</span><span class="sxs-lookup"><span data-stu-id="bc938-133">_wbadmin.exe_</span></span> | <span data-ttu-id="bc938-134">Ta bort befintliga säkerhetskopior och stoppa schemalagda säkerhetskopieringsuppgifter, vilket förhindrar återställning efter kryptering.</span><span class="sxs-lookup"><span data-stu-id="bc938-134">Delete existing backups and stop scheduled backup tasks, preventing recovery after encryption.</span></span> |
| <span data-ttu-id="bc938-135">Ändra startinställningar</span><span class="sxs-lookup"><span data-stu-id="bc938-135">Modify boot settings</span></span> | <span data-ttu-id="bc938-136">_bcdedit.exe_</span><span class="sxs-lookup"><span data-stu-id="bc938-136">_bcdedit.exe_</span></span> | <span data-ttu-id="bc938-137">Stäng av varningar och automatiska reparationer efter fel i starten som kan orsakas av krypteringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="bc938-137">Turn off warnings and automatic repairs after boot failures that can be caused by the encryption process.</span></span> |
| <span data-ttu-id="bc938-138">Inaktivera återställningsverktyg</span><span class="sxs-lookup"><span data-stu-id="bc938-138">Turn off recovery tools</span></span> | <span data-ttu-id="bc938-139">_schtasks.exe_, _regedit.exe_,</span><span class="sxs-lookup"><span data-stu-id="bc938-139">_schtasks.exe_, _regedit.exe_,</span></span> | <span data-ttu-id="bc938-140">Inaktivera Systemåterställning och andra systemåterställningsalternativ.</span><span class="sxs-lookup"><span data-stu-id="bc938-140">Turn off System Restore and other system recovery options.</span></span> |

## <a name="check-for-individual-signs-of-ransomware-activity"></a><span data-ttu-id="bc938-141">Kontrollera enskilda tecken på utpressningstrojaner</span><span class="sxs-lookup"><span data-stu-id="bc938-141">Check for individual signs of ransomware activity</span></span>
<span data-ttu-id="bc938-142">Många aktiviteter som utgör utpressningstrojaner, inklusive de aktiviteter som beskrivs i föregående avsnitt, kan vara skadlig.</span><span class="sxs-lookup"><span data-stu-id="bc938-142">Many activities that constitute ransomware behavior, including the activities described in the preceding section, can be benign.</span></span> <span data-ttu-id="bc938-143">När du använder följande frågor för att hitta utpressningstrojaner kör du fler än en fråga för att kontrollera om samma enhet har olika tecken på möjlig utpressningstrojanaktivitet.</span><span class="sxs-lookup"><span data-stu-id="bc938-143">When using the following queries to locate ransomware, run more than one query to check whether the same devices are exhibiting various signs of possible ransomware activity.</span></span>

### <a name="stopping-multiple-processes-using-_taskkillexe_"></a><span data-ttu-id="bc938-144">Stoppa flera processer med _taskkill.exe_</span><span class="sxs-lookup"><span data-stu-id="bc938-144">Stopping multiple processes using _taskkill.exe_</span></span>
<span data-ttu-id="bc938-145">Den här frågan söker efter försök att stoppa minst 10 olika processer med _hjälptaskkill.exe_ verktyg.</span><span class="sxs-lookup"><span data-stu-id="bc938-145">This query checks for attempts to stop at least 10 separate processes using the _taskkill.exe_ utility.</span></span> [<span data-ttu-id="bc938-146">Kör fråga</span><span class="sxs-lookup"><span data-stu-id="bc938-146">Run query</span></span>](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2RS2vCUBCFz7rgfwiuIkit3eumVSgtpYvuS9SLDTY2eLUvxN_eb8YHKlFkyNzJzDkn505aailRX7mmGlFlmhNBhUrOSGeuT3L0s6QqNaMagolEcMyCbApjx2e8TYhcH8Q1mB-emq50z_lF39gvBzo9-gEF-6Yhlyh9653ejCfRK6zCsaZfuJOu-x2jkqqN-0Yls-8-gp6dZ52OVuT6Sad1plulyN0KIkMt15_zt7zHDe8OBwv3btoJToa7Tnp0T8Ou9WzfT761gPOm3_FQ16Zxp2qcCdg33_rlyokG-iXv7_4BRNMnhkortmvTW6rqnZ7bgP2Vtm70D3d9wcFaAgAA&runQuery=true&timeRangeId=week)

```kusto
// Find attempts to stop processes using taskkill.exe
DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "taskkill.exe" 
| summarize taskKillCount = dcount(ProcessCommandLine), TaskKillList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 2m)
| where taskKillCount > 10
```
  
### <a name="stopping-processes-using-_net-stop_"></a><span data-ttu-id="bc938-147">Stoppa processer med _hjälp av nettostopp_</span><span class="sxs-lookup"><span data-stu-id="bc938-147">Stopping processes using _net stop_</span></span>
<span data-ttu-id="bc938-148">Den här frågan söker efter försök att stoppa minst 10 olika processer med hjälp av _kommandot för net_ stop.</span><span class="sxs-lookup"><span data-stu-id="bc938-148">This query checks for attempts to stop at least 10 separate processes using the _net stop_ command.</span></span> [<span data-ttu-id="bc938-149">Kör fråga</span><span class="sxs-lookup"><span data-stu-id="bc938-149">Run query</span></span>](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2RQUvDUBCE5yz0P4ScUijWereXVkGQIti7aA1pqakhL7VVxN_ebzc1NBChPLJv2Z2ZN5sdaqhId1ppozeyF1WcVLkK7kCl0gcx-F2QFSrJFmACJ3XMlmgKGfmGWnXC6OlCU2qfIIz12OLfUk_h2FuG_IG505JayRdpDit3bIW33B2M3WeGSqIRrvudTJvpnWzmPKvc6JcYHx1eEvd8savV07e9TchzTt198AlNZ0kluNLfjHHjIPAvak4J_tvx9XtPR6ypbn1icxShvGgqyVkO-hrAm7VUrRcaTWOs6T_7hs7XjfSqL-Lpvu5BDLxjqKRjI9a9Juvew__T2x5HutIB3T1qt4QCAAA&runQuery=true&timeRangeId=week)

```kusto
// Find attempts to stop processes using net stop
DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "net.exe" and ProcessCommandLine has "stop"
| summarize netStopCount = dcount(ProcessCommandLine), NetStopList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 2m)
| where netStopCount > 10
```
### <a name="deletion-of-data-on-multiple-drives-using-_cipherexe_"></a><span data-ttu-id="bc938-150">Borttagning av data på flera enheter med _cipher.exe_</span><span class="sxs-lookup"><span data-stu-id="bc938-150">Deletion of data on multiple drives using _cipher.exe_</span></span>
<span data-ttu-id="bc938-151">Den här frågan söker efter försök att ta bort data på flera enheter med _hjälp avcipher.exe_.</span><span class="sxs-lookup"><span data-stu-id="bc938-151">This query checks for attempts to delete data on multiple drives using _cipher.exe_.</span></span> <span data-ttu-id="bc938-152">Den här aktiviteten utförs vanligtvis av utpressningstrojaner för att förhindra återställning av data efter kryptering.</span><span class="sxs-lookup"><span data-stu-id="bc938-152">This activity is typically done by ransomware to prevent recovery of data after encryption.</span></span> [<span data-ttu-id="bc938-153">Kör fråga</span><span class="sxs-lookup"><span data-stu-id="bc938-153">Run query</span></span>](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI1SXUvDQBCcZ8H_cOQpgWLoD7AvVUEo4oPvElO1pblUcmn9QPztzk6TEuEsIdzdZndndm73cuRwWGDLb0PrhWfDs8Qab1jhmX8X3D-4HJbcK66W0Rqv8hT8K4RsiPW0PHbMasVQdbiGf3vaAec4wxWtPT0lz3vhSsUCrpVVE33I_Cb6vdNhTA9EeeVaVc8KDjOugmq2SDFlrSyKvCHS1NwJZ55L_HBPondNGDGWXP2JdyMnv927UnXHWwf6l4MunupXTOPfXszVT8_smriFOCxrRU-QclOQDLgCNRwQ1u8vZc8H2o1xp-7a7U1NefSko6pnmKjakNVi4chpiA39j-rGeF6HJ3xyH76NW2ZMFLGsNDJ9i05pZSPmVdDfq-jncfqtOuU5zSuQz6Zq92w7Hfbm-9cUm-d_vZ9J9S81O2KIfAMAAA&runQuery=true&timeRangeId=week)

```kusto
// Look for cipher.exe deleting data from multiple drives
DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "cipher.exe" 
// cipher.exe /w flag used for deleting data 
| where ProcessCommandLine has "/w" 
| summarize CipherCount = dcount(ProcessCommandLine),
CipherList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 1m) 
// cipher.exe accessing multiple drives in a short timeframe 
| where CipherCount > 1
```

### <a name="clearing-of-forensic-evidence-from-event-logs-using-_wevtutil_"></a><span data-ttu-id="bc938-154">Avröjning av bevis från händelseloggar _med wevtutil_</span><span class="sxs-lookup"><span data-stu-id="bc938-154">Clearing of forensic evidence from event logs using _wevtutil_</span></span>
<span data-ttu-id="bc938-155">Den här frågan söker efter försök att rensa minst 10 loggposter från händelseloggar med _wevtutil._</span><span class="sxs-lookup"><span data-stu-id="bc938-155">This query checks for attempts to clear at least 10 log entries from event logs using _wevtutil_.</span></span> [<span data-ttu-id="bc938-156">Kör fråga</span><span class="sxs-lookup"><span data-stu-id="bc938-156">Run query</span></span>](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAJWRTU_CQBCG37OJ_2HDqSQkwMGjXgoHEg4cUI-m2hUaqGu6BaPxx_vsEFCTxmA225nOvB_tzFBDOc0VOBuyZ2JD3CnKEwMVpzfyPbVWlba8t9Sdnsi9CsPXdLfWf7Wq4xm0QuVSF5oYv4LhtQAfLIucKXWvF5gH5Ke5rak1prKEVRu2xalG3emGW6AdlGmsUv1O5m-fnLzmFHiV_G9FTKg1lUjs6Z5vucPvljsD0TOXhP6_Vm7841dFZnPAN2A_DDu36eSnCSbNnc3B6Zpb4nasZGf59zWA963orZdcEiKelBNvQ_fBNny-utOj3nn-3OUMxMA6CZV1bCt1r8i6d_TXFNKWxxrpC48hm8miAgAA&runQuery=true&timeRangeId=week)

```kusto
// Look for use of wevtutil to clear multiple logs
DeviceProcessEvents
| where Timestamp > ago(1d)
| where ProcessCommandLine has "WEVTUTIL" and ProcessCommandLine has "CL"
| summarize LogClearCount = dcount(ProcessCommandLine), ClearedLogList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 5m)
| where LogClearCount > 10
```

### <a name="turning-off-services-using-_scexe_"></a><span data-ttu-id="bc938-157">Inaktivera tjänster med _sc.exe_</span><span class="sxs-lookup"><span data-stu-id="bc938-157">Turning off services using _sc.exe_</span></span>
<span data-ttu-id="bc938-158">Den här frågan söker efter försök att inaktivera minst 10 befintliga tjänster med _hjälp avsc.exe._</span><span class="sxs-lookup"><span data-stu-id="bc938-158">This query checks for attempts to turn off at least 10 existing services using _sc.exe_.</span></span> [<span data-ttu-id="bc938-159">Kör fråga</span><span class="sxs-lookup"><span data-stu-id="bc938-159">Run query</span></span>](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAKWST2vCQBDF31nodwg5RZCqhx7bi3ooeCjovaQxraIxxfU_fvj-ZoiiEIqlhM3Ozrz3ZnZm22or0lAl3xzrk33FHpTpUbn2rEgTzfCk-tACa6kvR-Qgt5wzrKAHNdTHOnveiJZVLGiAP4e5rpAnFHaauoZlGMMqHLsmT6FvfC-slFylEnWpoVnLvM3Twy74UnJNuJdVa6gpnsAe-81iVzbE3_kZiCV9mlHZf3Sue5pzii-3C9pU3BWYo_NGKPdvGJZh4x2N9Owzyi6e5K5qmmrVKg_9dNY11hzvu0_8fu0ItQP_6zfxCqLlEUMlNVO36BNW_ax_74K9l646-gFts39I1AIAAA&runQuery=true&timeRangeId=week)

```kusto
// Look for sc.exe disabling services
DeviceProcessEvents
| where Timestamp > ago(1d)
| where ProcessCommandLine has "sc" and ProcessCommandLine has "config" and ProcessCommandLine has "disabled"
| summarize ScDisableCount = dcount(ProcessCommandLine), ScDisableList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 5m)
| where ScDisableCount > 10
```

### <a name="turning-off-system-restore"></a><span data-ttu-id="bc938-160">Inaktivera Systemåterställning</span><span class="sxs-lookup"><span data-stu-id="bc938-160">Turning off System Restore</span></span>
<span data-ttu-id="bc938-161">Den här frågan identifierar försök att stoppa Systemåterställning och förhindra att systemet skapar återställningspunkter, som kan användas för att återställa data som krypteras med utpressningstrojaner.</span><span class="sxs-lookup"><span data-stu-id="bc938-161">This query identifies attempts to stop System Restore and prevent the system from creating restore points, which can be used to recover data encrypted by ransomware.</span></span> [<span data-ttu-id="bc938-162">Kör fråga</span><span class="sxs-lookup"><span data-stu-id="bc938-162">Run query</span></span>](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAK2S3UrDQBCFz7XgO6y9id4o6HWvrIVCkaJPENOYFNumZGO1ID673w4xJA1isbJMZnZ-zpzM7EiptlooQc9UqjDLc-7wp1qrwj7Via44MzK35FTotTI5PXMr0aVe8cy15NzoGo-zqg_0m3KQSsRpQtbC6uMGpdt3jHeJfU_GymqG-uQb9XpcEn1HIuvmGpZT0Aq99Dim4G3ousNO8K04sSE6EEN22kL6jvzO-LaDNW2QzqxLmGBsPo9vUMt_oA8Na3DQv3vwcmPiifpmds48jkhut8T2FLikxm_T4bI_m_6uQt-wrXO28lPPSBcdziOqPFlP9RYy47tDKtuZM07hVtSvaJ_HYRPL63-NyMgtmtWv5684jy2WDx2O0ZEM562ZBLQvURxur6gDAAA&runQuery=true&timeRangeId=week)

```kusto
DeviceProcessEvents
//Pivoting for rundll32  
| where InitiatingProcessFileName =~ 'rundll32.exe'   
//Looking for empty command line   
and InitiatingProcessCommandLine !contains " " and InitiatingProcessCommandLine != ""  
//Looking for schtasks.exe as the created process  
and FileName in~ ('schtasks.exe')  
//Disabling system restore   
and ProcessCommandLine has 'Change' and ProcessCommandLine has 'SystemRestore' 
and ProcessCommandLine has 'disable'
```

### <a name="backup-deletion"></a><span data-ttu-id="bc938-163">Säkerhetskopiera borttagning</span><span class="sxs-lookup"><span data-stu-id="bc938-163">Backup deletion</span></span>
<span data-ttu-id="bc938-164">Den här frågan identifierar hur du _wmic.exe_ ta bort ögonblicksbilder av skuggkopior innan krypteringen.</span><span class="sxs-lookup"><span data-stu-id="bc938-164">This query identifies use of _wmic.exe_ to delete shadow copy snapshots prior to encryption.</span></span> [<span data-ttu-id="bc938-165">Kör fråga</span><span class="sxs-lookup"><span data-stu-id="bc938-165">Run query</span></span>](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAJWS2wqCQBCG_-ugd5CupTfoqgMIEV70AqFLGp5QyYLo2fsavEjxwlhWZ7-df2Z2dndyuitVxD9UrdKshrGHOxVqsZda6CVPnRJYzfR0QJVhnXRRbmSjN98VXrlFXEMfzNWkfphti50zLmSMdURfmFcCaSxqY3aMX4eqVKUn1OsV_8eLWX_rbwcVVhblBovY8bT76U-AxoedWeeWp7WzV0YDMqSQFNZavuuopnHH_Iku-lbJnLPMyxnYDTp4bZ5P9M5uNpsZIWSn7l_CuNoPSggb4z4CAAA&runQuery=true&timeRangeId=week)

```kusto
DeviceProcessEvents
| where FileName =~ "wmic.exe"
| where ProcessCommandLine has "shadowcopy" and ProcessCommandLine has "delete"
| project DeviceId, Timestamp, InitiatingProcessFileName, FileName,
ProcessCommandLine, InitiatingProcessIntegrityLevel, InitiatingProcessParentFileName
```

## <a name="check-for-multiple-signs-of-ransomware-activity"></a><span data-ttu-id="bc938-166">Kontrollera om det finns flera tecken på utpressningstrojaner</span><span class="sxs-lookup"><span data-stu-id="bc938-166">Check for multiple signs of ransomware activity</span></span>
<span data-ttu-id="bc938-167">I stället för att köra flera frågor separat kan du också använda en omfattande fråga som söker efter flera tecken på utpressningstrojaner för att identifiera påverkade enheter.</span><span class="sxs-lookup"><span data-stu-id="bc938-167">Instead of running several queries separately, you can also use a comprehensive query that checks for multiple signs of ransomware activity to identify affected devices.</span></span> <span data-ttu-id="bc938-168">Följande konsoliderade fråga:</span><span class="sxs-lookup"><span data-stu-id="bc938-168">The following consolidated  query:</span></span>
- <span data-ttu-id="bc938-169">Letar efter både relativt betong- och diskreta tecken på utpressningstrojaner</span><span class="sxs-lookup"><span data-stu-id="bc938-169">Looks for both relatively concrete and subtle signs of ransomware activity</span></span>
- <span data-ttu-id="bc938-170">Väga förekomsten av dessa tecken</span><span class="sxs-lookup"><span data-stu-id="bc938-170">Weighs the presence of these signs</span></span>
- <span data-ttu-id="bc938-171">Identifierar enheter som har större chans att bli utpressningstrojaner</span><span class="sxs-lookup"><span data-stu-id="bc938-171">Identifies devices with a higher chance of being targets of ransomware</span></span> 

<span data-ttu-id="bc938-172">När den här konsoliderade frågan körs returneras en lista över enheter som har flera attacktecken.</span><span class="sxs-lookup"><span data-stu-id="bc938-172">When run, this consolidated query returns a list of devices that have exhibited multiple signs of attack.</span></span> <span data-ttu-id="bc938-173">Antalet av varje typ av utpressningstrojaner visas också.</span><span class="sxs-lookup"><span data-stu-id="bc938-173">The count of each type of ransomware activity is also shown.</span></span> <span data-ttu-id="bc938-174">Om du vill köra den här konsoliderade frågan kopierar du den direkt till den [avancerade frågeredigeraren för sökning.](https://security.microsoft.com/advanced-hunting)</span><span class="sxs-lookup"><span data-stu-id="bc938-174">To run this consolidated query, copy it directly to the [advanced hunting query editor](https://security.microsoft.com/advanced-hunting).</span></span> 

```kusto
// Find attempts to stop processes using taskkill.exe
let taskKill = DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "taskkill.exe" 
| summarize taskKillCount = dcount(ProcessCommandLine), TaskKillList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 2m)
| where taskKillCount > 10;
// Find attempts to stop processes using net stop
let netStop = DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "net.exe" and ProcessCommandLine has "stop"
| summarize netStopCount = dcount(ProcessCommandLine), NetStopList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 2m)
| where netStopCount > 10;
// Look for cipher.exe deleting data from multiple drives
let cipher = DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "cipher.exe" 
// cipher.exe /w flag used for deleting data 
| where ProcessCommandLine has "/w" 
| summarize CipherCount = dcount(ProcessCommandLine), 
CipherList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 1m) 
// cipher.exe accessing multiple drives in a short timeframe 
| where CipherCount > 1;
// Look for use of wevtutil to clear multiple logs
let wevtutilClear = DeviceProcessEvents
| where Timestamp > ago(1d)
| where ProcessCommandLine has "WEVTUTIL" and ProcessCommandLine has "CL"
| summarize LogClearCount = dcount(ProcessCommandLine), ClearedLogList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 5m)
| where LogClearCount > 10;
// Look for sc.exe disabling services
let scDisable = DeviceProcessEvents
| where Timestamp > ago(1d)
| where ProcessCommandLine has "sc" and ProcessCommandLine has "config" and ProcessCommandLine has "disabled"
| summarize ScDisableCount = dcount(ProcessCommandLine), ScDisableList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 5m)
| where ScDisableCount > 10;
// Main query for counting and aggregating evidence
DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "vssadmin.exe" and ProcessCommandLine has_any("list shadows", "delete shadows")
or FileName =~ "fsutil.exe" and ProcessCommandLine has "usn" and ProcessCommandLine has "deletejournal"
or ProcessCommandLine has("bcdedit") and ProcessCommandLine has_any("recoveryenabled no", "bootstatuspolicy ignoreallfailures")
or ProcessCommandLine has "wbadmin" and ProcessCommandLine has "delete" and ProcessCommandLine has_any("backup", "catalog", "systemstatebackup")
or (ProcessCommandLine has "wevtutil" and ProcessCommandLine has "cl") 
or (ProcessCommandLine has "wmic" and ProcessCommandLine has "shadowcopy delete")
or (ProcessCommandLine has "sc" and ProcessCommandLine has "config" and ProcessCommandLine has "disabled")
| extend Bcdedit = iff(ProcessCommandLine has "bcdedit" and ProcessCommandLine has_any("recoveryenabled no", "bootstatuspolicy ignoreallfailures"), 1, 0)
| extend ShadowCopyDelete = iff (ProcessCommandLine has "shadowcopy delete", 1, 0)
| extend VssAdminShadows = iff(ProcessCommandLine has "vssadmin" and ProcessCommandLine has_any("list shadows", "delete shadows"), 1, 0)
| extend Wbadmin = iff(ProcessCommandLine has "wbadmin" and ProcessCommandLine has "delete" and ProcessCommandLine has_any("backup", "catalog", "systemstatebackup"), 1,0)
| extend Fsutil = iff(ProcessCommandLine has "fsutil" and ProcessCommandLine has "usn" and ProcessCommandLine has "deletejournal", 1, 0)
| summarize FirstActivity = min(Timestamp), ReportId = any(ReportId), Commands = make_set(ProcessCommandLine) by DeviceId, Fsutil, Wbadmin, ShadowCopyDelete, Bcdedit, VssAdminShadows, bin(Timestamp, 6h)
// Joining extra evidence
| join kind=leftouter (wevtutilClear) on $left.DeviceId == $right.DeviceId
| join kind=leftouter (cipher) on $left.DeviceId == $right.DeviceId
| join kind=leftouter (netStop) on $left.DeviceId == $right.DeviceId
| join kind=leftouter (taskKill) on $left.DeviceId == $right.DeviceId
| join kind=leftouter (scDisable) on $left.DeviceId == $right.DeviceId
| extend WevtutilUse = iff(LogClearCount > 10, 1, 0)
| extend CipherUse = iff(CipherCount > 1, 1, 0)
| extend NetStopUse = iff(netStopCount > 10, 1, 0)
| extend TaskkillUse = iff(taskKillCount > 10, 1, 0)
| extend ScDisableUse = iff(ScDisableCount > 10, 1, 0)
// Adding up all evidence
| mv-expand CommandList = NetStopList, TaskKillList, ClearedLogList, CipherList, Commands, ScDisableList
// Format results
| summarize BcdEdit = iff(make_set(Bcdedit) contains "1" , 1, 0), NetStop10PlusCommands = iff(make_set(NetStopUse) contains "1", 1, 0), Wevtutil10PlusLogsCleared = iff(make_set(WevtutilUse) contains "1", 1, 0),
CipherMultipleDrives = iff(make_set(CipherUse) contains "1", 1, 0), Fsutil = iff(make_set(Fsutil) contains "1", 1, 0), ShadowCopyDelete = iff(make_set(ShadowCopyDelete) contains "1", 1, 0),
Wbadmin = iff(make_set(Wbadmin) contains "1", 1, 0), TaskKill10PlusCommand = iff(make_set(TaskkillUse) contains "1", 1, 0), VssAdminShadow = iff(make_set(VssAdminShadows) contains "1", 1, 0), 
ScDisable = iff(make_set(ScDisableUse) contains "1", 1, 0), TotalEvidenceCount = count(CommandList), EvidenceList = make_set(Commands), StartofBehavior = min(FirstActivity) by DeviceId, bin(Timestamp, 1d)
| extend UniqueEvidenceCount = BcdEdit + NetStop10PlusCommands + Wevtutil10PlusLogsCleared + CipherMultipleDrives + Wbadmin + Fsutil + TaskKill10PlusCommand + VssAdminShadow + ScDisable + ShadowCopyDelete
| where UniqueEvidenceCount > 2
```
### <a name="understand-and-tweak-the-query-results"></a><span data-ttu-id="bc938-175">Förstå och modifiera frågeresultaten</span><span class="sxs-lookup"><span data-stu-id="bc938-175">Understand and tweak the query results</span></span>
<span data-ttu-id="bc938-176">Den konsoliderade frågan returnerar följande resultat:</span><span class="sxs-lookup"><span data-stu-id="bc938-176">The consolidated query returns the following results:</span></span>

- <span data-ttu-id="bc938-177">**DeviceId**– identifierar den enhet som påverkas</span><span class="sxs-lookup"><span data-stu-id="bc938-177">**DeviceId**—identifies the affected device</span></span> 
- <span data-ttu-id="bc938-178">**TimeStamp**– första gången ett tecken på utpressningstrojaner observerades på enheten</span><span class="sxs-lookup"><span data-stu-id="bc938-178">**TimeStamp**—first time any sign of ransomware activity was observed on the device</span></span>
- <span data-ttu-id="bc938-179">**Specifika tecken på aktivitet –** antalet för varje tecken som visas i flera kolumner, till exempel _BcdEdit_ eller _FsUtil_</span><span class="sxs-lookup"><span data-stu-id="bc938-179">**Specific signs of activity**—the count for each sign shown in multiple columns, such as _BcdEdit_ or _FsUtil_</span></span>
- <span data-ttu-id="bc938-180">**TotalEvidenceCount**– antal observerade tecken</span><span class="sxs-lookup"><span data-stu-id="bc938-180">**TotalEvidenceCount**—number of observed signs</span></span>
- <span data-ttu-id="bc938-181">**UniqueEvidenceCount**– antal typer av observerade tecken</span><span class="sxs-lookup"><span data-stu-id="bc938-181">**UniqueEvidenceCount**—number of types of observed signs</span></span>

![Bild av frågeresultat för utpressningstrojaner](../../media/advanced-hunting-ransomware-query.png)

<span data-ttu-id="bc938-183">*Frågeresultat som visar påverkade enheter och antal olika tecken på utpressningstrojaner*</span><span class="sxs-lookup"><span data-stu-id="bc938-183">*Query results showing affected devices and counts of various signs of ransomware activity*</span></span>

<span data-ttu-id="bc938-184">Som standard visas endast enheter som har fler än två typer av utpressningstrojaner i frågeresultatet.</span><span class="sxs-lookup"><span data-stu-id="bc938-184">By default, the query result lists only devices that have more than two types of ransomware activity.</span></span> <span data-ttu-id="bc938-185">Om du vill se alla enheter med tecken på utpressningstrojaner ändrar du följande operator och `where` anger siffran noll (0).</span><span class="sxs-lookup"><span data-stu-id="bc938-185">To see all devices with any sign of ransomware activity, modify the following `where` operator and set the number to zero (0).</span></span> <span data-ttu-id="bc938-186">Ange ett högre antal om du vill se färre enheter.</span><span class="sxs-lookup"><span data-stu-id="bc938-186">To see fewer devices, set a higher number.</span></span> 

```kusto
| where UniqueEvidenceCount > 2
```

## <a name="related-topics"></a><span data-ttu-id="bc938-187">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="bc938-187">Related topics</span></span>
- [<span data-ttu-id="bc938-188">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="bc938-188">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="bc938-189">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="bc938-189">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="bc938-190">Arbeta med frågeresultat</span><span class="sxs-lookup"><span data-stu-id="bc938-190">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="bc938-191">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="bc938-191">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="bc938-192">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="bc938-192">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="bc938-193">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="bc938-193">Apply query best practices</span></span>](advanced-hunting-best-practices.md)