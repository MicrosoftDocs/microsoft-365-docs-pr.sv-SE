---
title: Skapa indikatorer för IP-adresser och URL:er/domäner
ms.reviewer: ''
description: Skapa indikatorer för IP-adresser och URL:er/domäner som definierar identifiering, skydd och undantag för enheter.
keywords: ip, url, domän, hantera, tillåten, blockerad, blockera, rensa, skadlig, filshashar, ip-adress, url:er, domän
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
ms.openlocfilehash: 3cfdc226ec5b476a37d15b67ca6158313e508adf
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51075746"
---
# <a name="create-indicators-for-ips-and-urlsdomains"></a>Skapa indikatorer för IP-adresser och URL:er/domäner 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)



>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)


Defender för Endpoint kan blockera vad Microsoft bedömer som skadliga IP-adresser/URL-adresser, via Windows Defender SmartScreen för Microsoft-webbläsare och via Nätverksskydd för webbläsare som inte är Microsoft eller samtal som görs utanför en webbläsare.

Datauppsättningen för hotinformation för detta har hanterats av Microsoft.

Genom att skapa indikatorer för IP-adresser och URL:er eller domäner kan du nu tillåta eller blockera IP-adresser, URL:er eller domäner baserat på din egen hotinformation. Det kan du göra via inställningssidan eller efter datorgrupper om du anser att vissa grupper är mer eller mindre riskerade än andra.

> [!NOTE]
> Classless Inter-Domain Routing (CIDR) notation for IP addresses is not supported. 

### <a name="before-you-begin"></a>Innan du börjar
Det är viktigt att förstå följande förutsättningar innan du skapar indikatorer för IPS, URL:er eller domäner:
- Tillåt och blockera URL/IP förlitar sig på att Defender för Endpoint-komponenten Nätverksskydd aktiveras i blockeringsläge. Mer information om nätverksskydd och konfigurationsanvisningar finns [i Aktivera nätverksskydd.](enable-network-protection.md)
- Klientversionen av Antimalware måste vara 4.18.1906.x eller senare. 
- Stöds på datorer med Windows 10, version 1709 eller senare. 
- Kontrollera att **indikatorerna för anpassade** nätverk är aktiverade **i Microsoft Defender Säkerhetscenter > inställningar > Avancerade funktioner.** Mer information finns i [Avancerade funktioner.](advanced-features.md)
- Information om stöd för indikatorer i iOS finns i [Konfigurera anpassade indikatorer.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/ios-configure-features#configure-custom-indicators)


> [!IMPORTANT]
> Endast externa IP-adresser kan läggas till i indikatorlistan. Indikatorer kan inte skapas för interna IP-adresser.
> För webbskyddsscenarier rekommenderar vi att du använder de inbyggda funktionerna i Microsoft Edge. Microsoft Edge inspekterar [nätverkstrafik med](network-protection.md) hjälp av Nätverksskydd och tillåter block för TCP, HTTP och HTTPS (TLS). För alla andra processer använder webbskyddsscenarier Nätverksskydd för kontroll och tillämpning: <br>
> OBS!
> - IP stöds för alla tre protokollen
> - Endast enskilda IP-adresser stöds (inga CIDR-block eller IP-intervall)
> - Krypterade URL:er (fullständig sökväg) kan endast blockeras i webbläsare från första part (Internet Explorer, Edge)
> - Krypterade URL:er (endast FQDN) kan blockeras utanför webbläsare från första part (Internet Explorer, Edge)
> - Fullständiga URL-sökvägsblock kan tillämpas på domännivån och alla okrypterade URL:er
 
> [!NOTE]
> Det kan finnas upp till två timmars svarstid (vanligtvis mindre) mellan den tid åtgärden vidtas och URL:en och IP blockeras. 

### <a name="create-an-indicator-for-ips-urls-or-domains-from-the-settings-page"></a>Skapa en indikator för IP-adresser, URL:er eller domäner från inställningssidan

1. Välj Inställningar Indikatorer i  >  **navigeringsfönstret.**  

2. Välj **fliken IP-adresser eller URL:er/Domäner.**

3. Välj **Lägg till objekt.**

4. Ange följande information:
   - Indikator – Ange entitetsinformation och definiera indikatorns förfallotid.
   - Åtgärd – Ange vilken åtgärd som ska vidtas och ange en beskrivning.
   - Omfattning – Definiera datorgruppens omfattning.

5. Granska informationen på fliken Sammanfattning och klicka sedan på **Spara**.

## <a name="related-topics"></a>Relaterade ämnen
- [Skapa indikatorer](manage-indicators.md)
- [Skapa indikatorer för filer](indicator-file.md)
- [Skapa indikatorer baserade på certifikat](indicator-certificates.md)
- [Hantera indikatorer](indicator-manage.md)
