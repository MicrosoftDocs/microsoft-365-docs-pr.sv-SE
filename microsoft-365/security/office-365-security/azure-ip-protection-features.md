---
title: Skyddsfunktioner i Azure Information Protection lanseras för befintliga klientorganisationar
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 7ad6f58e-65d7-4c82-8e65-0b773666634d
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: I den här artikeln förklarar vi de ändringar som distribueras till skyddsfunktioner i Azure Information Protection
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2cb78f9e13d8ae429f5f46f2b1051d07ee541a10
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165985"
---
# <a name="protection-features-in-azure-information-protection-rolling-out-to-existing-tenants"></a>Skyddsfunktioner i Azure Information Protection lanseras för befintliga klientorganisationar

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Microsoft Defender för Office 365 abonnemang 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Som hjälp med det första steget för att skydda din information kommer alla kvalificerade Azure Information Protection-klientorganisationen från juli 2018 att ha aktiverat skyddsfunktioner i Azure Information Protection som standard. Skyddsfunktioner i Azure Information Protection kallades tidigare för Rättighetshantering eller Azure RMS i Office 365. Om din organisation har ett Office E3-abonnemang eller ett högre serviceabonnemang får du nu ett försprång till att skydda informationen via Azure Information Protection när vi distribuerar de här funktionerna.

## <a name="changes-beginning-july-1-2018"></a>Ändringar som börjar den 1 juli 2018

Från och med den 1 juli 2018 aktiverar Microsoft skyddsfunktioner i Azure Information Protection för alla organisationer som har någon av följande abonnemang:

- Meddelandekryptering i Office 365 erbjuds som en del av Office 365 E3 och E5, Microsoft E3 och E5, Office 365 A1, A3, A5 och Office 365 G3 och G5. Du behöver inga ytterligare licenser för att ta emot de nya skyddsfunktioner som använder Azure Information Protection.

- Du kan också lägga till Azure Information Protection Plan 1 i följande abonnemang för att få de nya funktionerna för meddelandekryptering i Office 365: Exchange Online abonnemang 1, Exchange Online abonnemang 2, Office 365 F1, Microsoft 365 Business Basic, Microsoft 365 Business Standard eller Office 365 Enterprise E1.

- Alla användare som drar nytta av meddelandekryptering i Office 365 måste ha en licens för att kunna omfattas av funktionen.

- Den fullständiga listan finns i [meddelandekrypteringsbeskrivningarna för Exchange Online-tjänsten](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description) för Office 365.

Innehavaradministratörer kan kontrollera säkerhetsstatus i Office 365-administratörsportalen.

![Skärmbild som visar att rättighetshantering i Office 365 har aktiverats.](../../media/303453c8-e4a5-4875-b49f-e80c3eb7b91e.png)

## <a name="why-are-we-making-this-change"></a>Varför gör vi den här ändringen?

Meddelandekryptering i Office 365 utnyttjar skyddsfunktioner i Azure Information Protection. Vi är kärnan i de senaste förbättringarna av meddelandekryptering i Office 365 och våra bredare investeringar i informationsskydd i Microsoft 365, och vi gör det enklare för organisationer att aktivera och använda våra skyddsfunktioner, eftersom krypteringstekniker har varit svåra att konfigurera tidigare. Genom att aktivera skyddsfunktioner i Azure Information Protection som standard kan du snabbt komma igång med att skydda känsliga data.

## <a name="does-this-impact-me"></a>Påverkar det här mig?

Om din organisation har köpt en berättigad Office 365-licens påverkas klientorganisationen av den här ändringen.

 **VIKTIGT!** Om du använder AD RMS (Active Directory Rights Management Services) i din lokala miljö måste du antingen välja bort ändringen direkt eller migrera till Azure Information Protection innan vi distribuerar den här ändringen inom 30 dagar. Mer information om hur du avanmäler finns i "Jag använder AD RMS, hur gör jag för att avanmäla?" längre fram i den här artikeln. Om du föredrar att migrera kan [du gå till migreringen från AD RMS till Azure Information Protection.](https://docs.microsoft.com/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)

## <a name="can-i-use-azure-information-protection-with-active-directory-rights-management-services-ad-rms"></a>Kan jag använda Azure Information Protection med AD RMS (Active Directory Rights Management Services)?

Nej. Det här är inte ett distributionsscenario som stöds. Utan att vidta ytterligare steg för avanmälning kan vissa datorer automatiskt börja använda tjänsten Azure Rights Management och även ansluta till AD RMS-klustret. Det här scenariot stöds inte och har opålitliga resultat, så det är viktigt att du avanmäler dig från denna ändring inom 30 dagar innan vi distribuerar de här nya funktionerna. Mer information om hur du avanmäler finns i "Jag använder AD RMS, hur gör jag för att avanmäla?" längre fram i den här artikeln. Om du föredrar att migrera kan [du gå till migreringen från AD RMS till Azure Information Protection.](https://docs.microsoft.com/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)

## <a name="how-do-i-know-if-im-using-ad-rms"></a>Hur vet jag om jag använder AD RMS?

Följ de här anvisningarna i Förbereda miljön för Azure Rights Management när du också har [AD RMS (Active Directory Rights Management Services)](https://docs.microsoft.com/azure/information-protection/deploy-use/prepare-environment-adrms) för att kontrollera om du har distribuerat AD RMS:

1. Även om det är valfritt publicerar de flesta AD RMS-distributioner tjänstanslutningspunkten (SCP) i Active Directory så att domändatorerna kan identifiera AD RMS-klustret.

Använda ADSI-redigering för att se om du har publicerat en SCP i Active Directory: CN=Configuration [server name], CN=Services, CN=RightsManagementServices, CN=SCP

2. Om du inte använder en SCP måste Windows-datorer som ansluter till ett AD RMS-kluster konfigureras för identifiering av klienttjänster eller licensieringsomdirigering med hjälp av Windows-registret: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\ServiceLocation eller HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\MSIPC\ServiceLocation

Mer information om de här registerkonfigurationerna finns i aktivera identifiering av klientsidan med Hjälp av [Windows-registret](https://docs.microsoft.com/azure/information-protection/rms-client/client-deployment-notes#enabling-client-side-service-discovery-by-using-the-windows-registry) och omdirigering av [licensservertrafik.](https://docs.microsoft.com/azure/information-protection/rms-client/client-deployment-notes#redirecting-licensing-server-traffic)

## <a name="i-use-ad-rms-how-do-i-opt-out"></a>Jag använder AD RMS, hur gör jag för att avanmäla?

Om du vill avanmäla dig från den kommande ändringen slutför du följande steg:

1. Om du använder ett arbets- eller skolkonto som har global administratörsbehörighet i organisationen startar du en Windows PowerShell-session och ansluter till Exchange Online. Instruktioner finns i [Ansluta till Exchange Online PowerShell.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)

2. Kör Set-IRMConfiguration cmdlet med följande syntax:

  ```powershell
  Set-IRMConfiguration -AutomaticServiceUpdateEnabled $false
  ```

## <a name="what-can-i-expect-after-this-change-has-been-made"></a>Vad kan jag förvänta mig när den här ändringen har gjorts?

När detta är aktiverat, förutsatt att du inte har valt bort det, kan du börja använda den nya versionen av meddelandekryptering i Office 365 som annonserades på [Microsoft Ignite 2017](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Email-Encryption-and-Rights-Protection/ba-p/110801) och som utnyttjar krypterings- och skyddsfunktioner i Azure Information Protection.

![Skärmbild som visar ett OME-skyddat meddelande i Outlook på webben.](../../media/599ca9e7-c05a-429e-ae8d-359f1291a3d8.png)

Mer information om de nya förbättringarna finns i meddelandekryptering [i Office 365.](../../compliance/ome.md)
