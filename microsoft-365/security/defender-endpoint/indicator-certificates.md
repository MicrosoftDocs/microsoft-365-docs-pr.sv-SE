---
title: Skapa indikatorer baserade på certifikat
ms.reviewer: ''
description: Skapa indikatorer baserade på certifikat som definierar identifiering, skydd och undantag för enheter.
keywords: ioc, certificate, certificates, manage, allowed, blocked, block, clean, malicious, file hash, ip address, urls, domain
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: b75a8cf1d2681281555a3b7bb80deadfc11ee44c
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845460"
---
# <a name="create-indicators-based-on-certificates"></a>Skapa indikatorer baserade på certifikat

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

Du kan skapa indikatorer för certifikat. Några vanliga användningsfall är:

- Scenarier när du behöver distribuera blockeringstekniker, till [](controlled-folders.md) exempel minskningsregler för [attackytan](attack-surface-reduction.md) och kontrollerad mappåtkomst, men behöver tillåta beteenden från signerade program genom att lägga till certifikatet i listan över tillåtna mappar.
- Blockera användningen av ett visst signerat program i hela organisationen. Genom att skapa en indikator för att blockera certifikatet för programmet Windows Defender AV filkörningar (blockering och åtgärd) och automatisk undersökning och åtgärd fungerar på samma sätt.


### <a name="before-you-begin"></a>Innan du börjar

Det är viktigt att förstå följande krav innan du skapar indikatorer för certifikat:

- Den här funktionen är tillgänglig om din organisation Windows Defender Antivirus skydd och Molnbaserat skydd är aktiverat. Mer information finns i [Hantera molnbaserat skydd](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).
- Klientversionen av Antimalware måste vara 4.18.1901.x eller senare.
- Stöds på datorer Windows 10, version 1703 eller senare, Windows server 2016 och 2019.
- Definitionerna för skydd mot virus och hot måste vara uppdaterade.
- Den här funktionen har för närvarande stöd för att ange . CER eller . PEM-filnamnstillägg.

>[!IMPORTANT]
> - Ett giltigt certifikat för blad är ett signeringscertifikat som har en giltig certifieringssökväg och måste länkas till den rotcertifikatutfärdare (CA) som Microsoft litar på.  Alternativt kan ett anpassat (själv signerat) certifikat användas så länge det är betrott av klienten (Root CA-certifikat har installerats under den lokala datorns betrodda rotcertifikatutfärdare).
>- Underordnade eller överordnade till IOC-certifikaten (tillåt/blockera) ingår inte i IoC-funktionen tillåt/blockera, endast certifikat för löv stöds.
>- Microsoft-signerade certifikat kan inte blockeras.

#### <a name="create-an-indicator-for-certificates-from-the-settings-page"></a>Skapa en indikator för certifikat från inställningssidan:

>[!IMPORTANT]
> Det kan ta upp till 3 timmar att skapa och ta bort ett certifikat-IoC.

1. Välj Ta fram Inställningar  >  **i navigeringsfönstret.**  

2. Välj **fliken** Certifikat.

3. Välj **Lägg till indikator**.

4. Ange följande information:
   - Indikator – Ange entitetsinformation och definiera indikatorns förfallotid.
   - Åtgärd – Ange vilken åtgärd som ska vidtas och ange en beskrivning.
   - Omfattning – Definiera datorgruppens omfattning.

5. Granska informationen på fliken Sammanfattning och klicka sedan på **Spara**.

## <a name="related-topics"></a>Relaterade ämnen
- [Skapa indikatorer](manage-indicators.md)
- [Skapa indikatorer för filer](indicator-file.md)
- [Skapa indikatorer för IP:er och URL:er/domäner](indicator-ip-domain.md)
- [Hantera indikatorer](indicator-manage.md)
