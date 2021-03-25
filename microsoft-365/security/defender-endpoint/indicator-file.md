---
title: Skapa indikatorer för filer
ms.reviewer: ''
description: Skapa indikatorer för en filhash som definierar identifiering, skydd och undantag för enheter.
keywords: fil, hash, hantera, tillåten, blockerad, blockera, rensa, skadlig, filshashar, ip-adress, url:er, domän
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
ms.openlocfilehash: 4edff7a9c7f541e31363519e4bafc2a21602e011
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51075753"
---
# <a name="create-indicators-for-files"></a>Skapa indikatorer för filer

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)



>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

Du kan förhindra ytterligare spridning av en attack i organisationen genom att förbjuda potentiellt skadliga filer eller misstänkt skadlig kod. Om du vet en potentiellt skadlig körbar fil (PE) kan du blockera den. Den här åtgärden förhindrar att den läses, skrivs eller körs på datorer i organisationen.

Du kan skapa indikatorer för filer på två sätt:
- Genom att skapa en indikator via inställningssidan
- Genom att skapa en sammanhangsberoende indikator med knappen lägg till indikator från filinformationssidan

### <a name="before-you-begin"></a>Innan du börjar
Det är viktigt att förstå följande förutsättningar innan du skapar indikatorer för filer:

- Den här funktionen är tillgänglig om din organisation använder Windows Defender Antivirus och Molnbaserat skydd är aktiverat. Mer information finns i [Använda nästa generations teknik i Microsoft Defender Antivirus via moln levererat skydd.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)
- Klientversionen av Antimalware måste vara 4.18.1901.x eller senare.
- Stöds på datorer med Windows 10, version 1703 eller senare, Windows Server 2016 och 2019.
- För att börja blockera filer måste du först [aktivera funktionen Spärra eller **tillåt**](advanced-features.md) i Inställningar.
- Den här funktionen är utformad för att förhindra att misstänkt skadlig programvara (eller potentiellt skadliga filer) laddas ned från webben. Den har för närvarande stöd för bärbara körbara (PE) filer, inklusive _.exe-_ _och .dll-filer._ Täckningen utökas med tiden.

>[!IMPORTANT]
>- Funktionen tillåt eller blockera kan inte utföras för filer om filens klassificering finns på enhetens cache innan åtgärden för att tillåta eller blockera 
>- Betrodda signerade filer behandlas annorlunda. Defender för Endpoint är optimerad för att hantera skadliga filer. Att försöka blockera betrodda signerade filer kan i vissa fall ha prestandakonsekvenser.

 
>[!NOTE]
>Vanligtvis används filblock inom några minuter, men det kan ta upp till 30 minuter.

### <a name="create-an-indicator-for-files-from-the-settings-page"></a>Skapa en indikator för filer från inställningssidan

1. Välj Inställningar Indikatorer i  >  **navigeringsfönstret.**  

2. Välj fliken **Filhash.**

3. Välj **Lägg till indikator**.

4. Ange följande information:
   - Indikator – Ange entitetsinformation och definiera indikatorns förfallotid.
   - Åtgärd – Ange vilken åtgärd som ska vidtas och ange en beskrivning.
   - Omfattning – Definiera datorgruppens omfattning.

5. Granska informationen på fliken Sammanfattning och klicka sedan på **Spara**.

### <a name="create-a-contextual-indicator-from-the-file-details-page"></a>Skapa en sammanhangsberoende indikator från filinformationssidan
Ett av alternativen när du vidtar [svarsåtgärder för en fil är](respond-file-alerts.md) att lägga till en indikator för filen. 

När du lägger till en indikatorhash för en fil kan du välja att avisering ska visas och blockera filen när en dator i organisationen försöker köra den.

Filer som blockeras automatiskt av en indikator visas inte i filens Åtgärdscenter, men aviseringarna visas fortfarande i kön Aviseringar.


## <a name="related-topics"></a>Relaterade ämnen
- [Skapa indikatorer](manage-indicators.md)
- [Skapa indikatorer för IP-adresser och URL:er/domäner](indicator-ip-domain.md)
- [Skapa indikatorer baserade på certifikat](indicator-certificates.md)
- [Hantera indikatorer](indicator-manage.md)
