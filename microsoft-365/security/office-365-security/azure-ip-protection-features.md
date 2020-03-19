---
title: Skyddsfunktioner i Azure Information Protection som distribueras till befintliga Office 365-klienter
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 7ad6f58e-65d7-4c82-8e65-0b773666634d
ms.collection:
- M365-security-compliance
description: För att hjälpa till med det första steget för att skydda din information kommer alla Azure Information Protection-berättigade klienter att ha skyddsfunktionerna i Azure Information Protection aktiverat som standard från juli 2018. Skyddsfunktionerna i Azure Information Protection var tidigare kända i Office 365 som Rights Management eller Azure RMS. Om din organisation har ett Office E3-serviceabonnemang eller ett högre serviceabonnemang får du nu ett försprång som skyddar information via Azure Information Protection när vi distribuerar dessa funktioner.
ms.openlocfilehash: de3b233d4baac380608d3a209c2ffea274c20d5b
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42807946"
---
# <a name="protection-features-in-azure-information-protection-rolling-out-to-existing-office-365-tenants"></a>Skyddsfunktioner i Azure Information Protection som distribueras till befintliga Office 365-klienter

För att hjälpa till med det första steget för att skydda din information kommer alla Azure Information Protection-berättigade klienter att ha skyddsfunktionerna i Azure Information Protection aktiverat som standard från juli 2018. Skyddsfunktionerna i Azure Information Protection var tidigare kända i Office 365 som Rights Management eller Azure RMS. Om din organisation har ett Office E3-serviceabonnemang eller ett högre serviceabonnemang får du nu ett försprång som skyddar information via Azure Information Protection när vi distribuerar dessa funktioner.

## <a name="changes-beginning-july-1-2018"></a>Förändringar från och med 1 juli 2018

Från och med den 1 juli 2018 aktiverar Microsoft skyddsfunktionen i Azure Information Protection för alla Office 365-klienter som har något av följande prenumerationsabonnemang:

- Office 365 Message Encryption erbjuds som en del av Office 365 E3 och E5, Microsoft E3 och E5, Office 365 A1, A3 och A5 samt Office 365 G3 och G5. Du behöver inte ytterligare licenser för att få de nya skyddsfunktionerna som drivs av Azure Information Protection.

- Du kan också lägga till Azure Information Protection Plan 1 i följande planer för att få de nya funktionerna för meddelandekryptering i Office 365: Exchange Online Plan 1, Exchange Online Plan 2, Office 365 F1, Office 365 Business Essentials, Office 365 Business Premium eller Office 365 Enterprise E1.

- Varje användare som drar nytta av Office 365 Message Encryption måste licensieras för att omfattas av funktionen.

- En fullständig lista finns i Beskrivningarna av [Exchange Online-tjänsten](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description) för Office 365-meddelandekryptering.

Klientadministratörer kan kontrollera skyddsstatusen i Office 365-administratörsportalen.

![Skärmbild som visar att rättighetshantering i Office 365 är aktiverad.](../../media/303453c8-e4a5-4875-b49f-e80c3eb7b91e.png)

## <a name="why-are-we-making-this-change"></a>Varför gör vi denna förändring?

Office 365-meddelandekryptering utnyttjar skyddsfunktionerna i Azure Information Protection. I centrum för de senaste förbättringarna av Office 365 Message Encryption och våra bredare investeringar i informationsskydd i Microsoft 365 gör vi det enklare för organisationer att aktivera och använda våra skyddsfunktioner, som historiskt, kryptering teknik har varit svår att inrätta. Genom att aktivera skyddsfunktionerna i Azure Information Protection som standard kan du snabbt komma igång för att skydda dina känsliga data.

## <a name="does-this-impact-me"></a>Påverkar det mig?

Om din Office 365-organisation har köpt en kvalificerad Office 365-licens påverkas din klientklient av den här ändringen.

 **Viktigt!** Om du använder AD RMS (Active Directory Rights Management Services) i din lokala miljö måste du antingen välja bort den här ändringen omedelbart eller migrera till Azure Information Protection innan vi distribuerar den här ändringen inom de närmaste 30 dagarna. Information om hur du väljer bort det finns i "Jag använder AD RMS, hur väljer jag bort?" senare i den här artikeln. Om du föredrar att migrera läser du [Migrera från AD RMS till Azure Information Protection.](https://docs.microsoft.com/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)

## <a name="can-i-use-azure-information-protection-with-active-directory-rights-management-services-ad-rms"></a>Kan jag använda Azure Information Protection med AD RMS (Active Directory Rights Management Services)?

Nej. Detta är inte ett distributionsscenario som stöds. Utan att vidta ytterligare undantagssteg kan vissa datorer automatiskt börja använda Azure Rights Management-tjänsten och även ansluta till ditt AD RMS-kluster. Det här scenariot stöds inte och har otillförlitliga resultat, så det är viktigt att du väljer bort den här ändringen inom de närmaste 30 dagarna innan vi distribuerar dessa nya funktioner. Information om hur du väljer bort det finns i "Jag använder AD RMS, hur väljer jag bort?" senare i den här artikeln. Om du föredrar att migrera läser du [Migrera från AD RMS till Azure Information Protection.](https://docs.microsoft.com/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)

## <a name="how-do-i-know-if-im-using-ad-rms"></a>Hur vet jag om jag använder AD RMS?

Använd de här instruktionerna från [Förbereda miljön för Azure Rights Management när du också har AD RMS (Active Directory Rights Management Services)](https://docs.microsoft.com/azure/information-protection/deploy-use/prepare-environment-adrms) för att kontrollera om du har distribuerat AD RMS:

1. Även om de flesta AD RMS-distributioner är valfria publicerar de flesta AD RMS-distributioner serviceanslutningspunkten (SCP) till Active Directory så att domändatorer kan identifiera AD RMS-klustret.

Använd ADSI-redigering för att se om du har en SCP publicerad i Active Directory: CN=Configuration [servernamn], CN=Services, CN=RightsManagementServices, CN=SCP

2. Om du inte använder en SCP måste Windows-datorer som ansluter till ett AD RMS-kluster konfigureras för identifiering eller licensiering av klientsidan sã¥giv- eller licensomdirigering med windowsregistret: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\ServiceLocation eller HKEY_ LOCAL_MACHINE\PROGRAMVARA\Wow6432Node\Microsoft\MSIPC\ServicePlats

Mer information om dessa registerkonfigurationer finns i [Aktivera identifiering av klientsidan-tjänst med hjälp av Windows-registret](https://docs.microsoft.com/azure/information-protection/rms-client/client-deployment-notes#enabling-client-side-service-discovery-by-using-the-windows-registry) och [omdirigera licensieringsservertrafik](https://docs.microsoft.com/azure/information-protection/rms-client/client-deployment-notes#redirecting-licensing-server-traffic).

## <a name="i-use-ad-rms-how-do-i-opt-out"></a>Jag använder AD RMS, hur väljer jag bort?

Så här väljer du bort den kommande ändringen:

1. Starta en Windows PowerShell-session med ett arbets- eller skolkonto som har globala administratörsbehörigheter i din Office 365-organisation och ansluter till Exchange Online. Instruktioner finns i [Anslut till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

2. Kör cmdleten Set-IRMConfiguration med hjälp av följande syntax:

  ```powershell
  Set-IRMConfiguration -AutomaticServiceUpdateEnabled $false
  ```

## <a name="what-can-i-expect-after-this-change-has-been-made"></a>Vad kan jag förvänta mig efter att denna förändring har gjorts?

När detta är aktiverat, förutsatt att du inte har valt bort, kan du börja använda den nya versionen av Office 365 Message Encryption som tillkännagavs på [Microsoft Ignite 2017](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Email-Encryption-and-Rights-Protection/ba-p/110801) och utnyttjar krypterings- och skyddsfunktionerna i Azure Information Protection.

![Skärmbild som visar ett OME-skyddat meddelande i Outlook på webben.](../../media/599ca9e7-c05a-429e-ae8d-359f1291a3d8.png)

Mer information om de nya förbättringarna finns i [Office 365 Message Encryption](../../compliance/ome.md).
