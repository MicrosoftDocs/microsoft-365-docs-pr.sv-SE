---
title: Skyddsfunktioner i Azure Information Protection distribueras till befintliga klientorganisationen
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
description: I den här artikeln förklaras ändringarna som distribueras till skyddsfunktionerna i Azure Information Protection
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 77d45c8521e67c480b9e5557b05eed8ba5dd2645
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207196"
---
# <a name="protection-features-in-azure-information-protection-rolling-out-to-existing-tenants"></a>Skyddsfunktioner i Azure Information Protection distribueras till befintliga klientorganisationen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Microsoft Defender för Office 365 abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Som hjälp med det första steget för att skydda din information kommer alla kvalificerade Azure Information Protection-klienter från och med juli 2018 att ha skyddsfunktioner i Azure Information Protection aktiverat som standard. Skyddsfunktioner i Azure Information Protection kallades tidigare för Office 365 Rights Management eller Azure RMS. Om din organisation har ett Office E3-abonnemang eller ett högre serviceabonnemang får du nu ett sätt att skydda informationen via Azure Information Protection när vi distribuerar de här funktionerna.

## <a name="changes-beginning-july-1-2018"></a>Ändringar som börjar den 1 juli 2018

Från och med den 1 juli 2018 kommer Microsoft att aktivera skyddsfunktioner i Azure Information Protection för alla organisationer som har ett av följande abonnemang:

- Meddelandekryptering i Office 365 erbjuds som en del av Office 365 E3 och E5, Microsoft E3 och E5, Office 365 A1, A3, A5 och Office 365 G3 och G5. Du behöver inga ytterligare licenser för att få de nya skyddsfunktioner som drivs av Azure Information Protection.

- Du kan också lägga till Azure Information Protection Plan 1 i följande abonnemang för att få de nya Meddelandekryptering i Office 365-funktionerna: Exchange Online abonnemang 1, Exchange Online abonnemang 2, Office 365 F1, Microsoft 365 Business Basic, Microsoft 365 Business Standard eller Office 365 Enterprise E1.

- Varje användare som drar Meddelandekryptering i Office 365 behöver licens för att omfattas av funktionen.

- Den fullständiga listan finns i artikeln [Exchange Online tjänstbeskrivningar](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description) för Meddelandekryptering i Office 365.

Innehavaradministratörer kan kontrollera säkerhetsstatusen i Office 365 administratörsportalen.

![Skärmbild som visar att rättighetshantering i Office 365 är aktiverat.](../../media/303453c8-e4a5-4875-b49f-e80c3eb7b91e.png)

## <a name="why-are-we-making-this-change"></a>Varför gör vi den här ändringen?

Meddelandekryptering i Office 365 använder skyddsfunktionerna i Azure Information Protection. Vi är kärnan i de senaste förbättringarna av Meddelandekryptering i Office 365 och våra bredare investeringar i informationsskydd i Microsoft 365. Vi gör det enklare för organisationer att aktivera och använda våra skyddsfunktioner, eftersom krypteringstekniker tidigare har varit svåra att konfigurera. Genom att aktivera skyddsfunktioner i Azure Information Protection som standard kan du snabbt komma igång med att skydda känsliga data.

## <a name="does-this-impact-me"></a>Påverkar det här mig?

Om din organisation har köpt en Office 365 licens påverkas klientorganisationen av den här ändringen.

> [!IMPORTANT]
> Om du använder Active Directory Rights Management Services (AD RMS) i din lokala miljö måste du antingen välja bort ändringen direkt eller migrera till Azure Information Protection innan vi distribuerar den här ändringen inom 30 dagar. Mer information om hur du avanmäler finns i "Jag använder AD RMS, hur gör jag för att avanmäla?" längre fram i den här artikeln. Om du föredrar att migrera kan [du gå till Migrera från AD RMS till Azure Information Protection.](/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)

## <a name="can-i-use-azure-information-protection-with-active-directory-rights-management-services-ad-rms"></a>Kan jag använda Azure Information Protection med Active Directory Rights Management Services (AD RMS)?

Nej. Det här är inte ett distributionsscenario som stöds. Utan att vidta ytterligare åtgärder för avanmälning kan vissa datorer automatiskt börja använda tjänsten Azure Rights Management och även ansluta till AD RMS-klustret. Det här scenariot stöds inte och har opålitliga resultat, så det är viktigt att du avanmäler dig från denna ändring inom 30 dagar innan vi distribuerar de här nya funktionerna. Mer information om hur du avanmäler finns i "Jag använder AD RMS, hur gör jag för att avanmäla?" längre fram i den här artikeln. Om du föredrar att migrera kan [du gå till Migrera från AD RMS till Azure Information Protection.](/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)

## <a name="how-do-i-know-if-im-using-ad-rms"></a>Hur vet jag om jag använder AD RMS?

Följ de här anvisningarna från Förbereda miljön för Azure Rights Management när du också har [Active Directory Rights Management Services (AD RMS)](/azure/information-protection/deploy-use/prepare-environment-adrms) för att kontrollera om du har distribuerat AD RMS:

1. Även om det är valfritt publicerar de flesta AD RMS-distributioner tjänstanslutningspunkten (SCP) på Active Directory så att domändatorer kan identifiera AD RMS-klustret.

   Använd ADSI-redigering för att se om du har en SCP publicerad i Active Directory: CN=Configuration [server name], CN=Services, CN=RightsManagementServices, CN=SCP

2. Om du inte använder en SCP måste Windows-datorer som ansluter till ett AD RMS-kluster konfigureras för identifiering av klienttjänster eller licensieringsomdirigering med hjälp av Windows-registret: `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\ServiceLocation or HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\MSIPC\ServiceLocation` .

Mer information om de här registerkonfigurationerna finns i Aktivera identifiering av klienttjänster med hjälp [av Windows](/azure/information-protection/rms-client/client-deployment-notes#enabling-client-side-service-discovery-by-using-the-windows-registry) och omdirigera [licensservertrafik.](/azure/information-protection/rms-client/client-deployment-notes#redirecting-licensing-server-traffic)

## <a name="i-use-ad-rms-how-do-i-opt-out"></a>Jag använder AD RMS– hur gör jag för att avanmäla mig?

Om du vill avanmäla dig från den kommande ändringen slutför du följande steg:

1. Om du använder ett arbets- eller skolkonto med global administratörsbehörighet i din organisation startar du Windows PowerShell en session och ansluter till Exchange Online. För instruktioner se: [Ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Kör Set-IRMConfiguration cmdlet med följande syntax:

  ```powershell
  Set-IRMConfiguration -AutomaticServiceUpdateEnabled $false
  ```

## <a name="what-can-i-expect-after-this-change-has-been-made"></a>Vad kan jag förvänta mig när ändringen har gjorts?

Om du inte har valt att använda det kan du börja använda den nya versionen av Meddelandekryptering i Office 365 som annonserades på [Microsoft Ignite 2017.](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Email-Encryption-and-Rights-Protection/ba-p/110801) Den använder krypterings- och skyddsfunktioner i Azure Information Protection.

![Skärmbild som visar ett OME-skyddat meddelande Outlook på webben.](../../media/599ca9e7-c05a-429e-ae8d-359f1291a3d8.png)

Mer information om de nya förbättringarna finns i [Meddelandekryptering i Office 365](../../compliance/ome.md).