---
title: Skydds funktioner i Azure information Protection som ansluts till befintliga klient organisationer
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
ms.custom:
- seo-marvel-apr2020
description: I den här artikeln förklaras ändringarna som görs i skydds funktionerna i Azure information Protection
ms.openlocfilehash: 070b0d1af0576391ce5f22a827975d1541646454
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203605"
---
# <a name="protection-features-in-azure-information-protection-rolling-out-to-existing-tenants"></a>Skydds funktioner i Azure information Protection som ansluts till befintliga klient organisationer

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


För att hjälpa dig med det första steget när du ska skydda din information, med början juli 2018 alla kvalificerade klient organisationer för Azure information Protection kommer skydds funktionerna i Azure information Protection aktiverat som standard. Skydds funktionerna i Azure information Protection kallades tidigare i Office 365 som Rights Management eller Azure RMS. Om din organisation har ett Office E3-abonnemang eller en högre service plan får du nu ett huvud för att skydda informationen genom Azure information Protection när vi tar fram dessa funktioner.

## <a name="changes-beginning-july-1-2018"></a>Ändringar från den 1 juli 2018

Från och med den 1 juli 2018 kommer Microsoft att aktivera skydds funktionen i Azure information Protection för alla organisationer med någon av följande abonnemang:

- Meddelande kryptering i Office 365 erbjuds som en del av Office 365 E3 och E5, Microsoft E3 och E5, Office 365 a1, A3 och A5 samt Office 365 G3 och G5. Du behöver inte fler licenser för att få den nya skydds kapaciteten med Azure information Protection.

- Du kan också lägga till Azure information Protection Plan 1 i följande planer för att få nya Office 365-funktioner för meddelande kryptering: Exchange Online plan 1, Exchange Online abonnemang 2, Office 365 F1, Microsoft 365 Business Basic, Microsoft 365 Business Standard eller Office 365 Enterprise E1.

- Varje användare som utnyttjar Office 365-kryptering måste licensieras för att omfattas av funktionen.

- En fullständig lista finns i [beskrivningarna för Exchange Online-tjänsten](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description) för Office 365 Message Encryption.

Klient organisationens administratörer kan kontrol lera skydds statusen i administratörs portalen för Office 365.

![Skärm bild som visar att rättighets hantering i Office 365 är aktiverat.](../../media/303453c8-e4a5-4875-b49f-e80c3eb7b91e.png)

## <a name="why-are-we-making-this-change"></a>Varför görs den här ändringen?

Office 365 meddelande kryptering utnyttjar skydds funktionerna i Azure information Protection. I hjärtat av de senaste förbättringarna av Office 365 meddelande kryptering och våra bredare investeringar för informations skydd i Microsoft 365, gör vi det enklare för organisationer att aktivera och använda vår skydds kapacitet, som historiskt, men krypterings teknik har varit svårt att installera. Genom att aktivera skydds funktionerna i Azure information Protection som standard kan du snabbt komma igång för att skydda känslig information.

## <a name="does-this-impact-me"></a>Påverkar det här?

Om organisationen har köpt en giltig Office 365-licens påverkas din klient organisation av den här ändringen.

 **BETYDANDE!** Om du använder AD RMS (Active Directory Rights Management Services) i din lokala miljö måste du antingen välja bort den här ändringen omedelbart eller migrera till Azure information Protection innan vi utför ändringen inom de närmaste 30 dagarna. Information om hur du väljer bort finns i "Jag använder AD RMS, hur kan jag säga upp?" längre fram i den här artikeln. Om du föredrar att migrera läser du [Migrera från AD RMS till Azure information Protection.](https://docs.microsoft.com/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)

## <a name="can-i-use-azure-information-protection-with-active-directory-rights-management-services-ad-rms"></a>Kan jag använda Azure information Protection med AD RMS (Active Directory Rights Management Services)?

Nej. Det här är inte ett distributions scenario som stöds. Utan att vidta de andra åtgärderna kan vissa datorer automatiskt börja använda Azure Rights Management-tjänsten och även ansluta till ditt AD RMS-kluster. Det här scenariot stöds inte och har otillförlitligt resultat, så det är viktigt att du avmarkerar ändringen inom de närmaste 30 dagarna innan vi utför de nya funktionerna. Information om hur du väljer bort finns i "Jag använder AD RMS, hur kan jag säga upp?" längre fram i den här artikeln. Om du föredrar att migrera läser du [Migrera från AD RMS till Azure information Protection.](https://docs.microsoft.com/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)

## <a name="how-do-i-know-if-im-using-ad-rms"></a>Hur vet jag om jag använder AD RMS?

Använd dessa instruktioner [för att förbereda miljön för Azure Rights Management när du även har AD RMS (Active Directory Rights Management Services)](https://docs.microsoft.com/azure/information-protection/deploy-use/prepare-environment-adrms) för att kontrol lera om du har distribuerat AD RMS:

1. De flesta AD RMS-installationer publicerar dessutom tjänst anslutnings punkten (SCP) till Active Directory, så att domän datorerna kan upptäcka AD RMS-klustret.

Använd ADSI Edit för att se om du har en SCP Publicerad i Active Directory: CN = Configuration [Server Name], CN = Services, CN = RightsManagementServices, CN = SCP

2. Om du inte använder en SCP måste Windows-datorer som ansluter till ett AD RMS-kluster konfigureras för identifiering av klient-Side tjänst eller omdirigering via Windows-registret: HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\MSIPC\ServiceLocation eller HKEY_LOCAL_MACHINE \SOFTWARE\Wow6432Node\Microsoft\MSIPC\ServiceLocation

Mer information om de här registervärdena finns i [Aktivera identifiering av klientens tjänst via Windows-registret](https://docs.microsoft.com/azure/information-protection/rms-client/client-deployment-notes#enabling-client-side-service-discovery-by-using-the-windows-registry) och dirigera om [licensierings Server trafik](https://docs.microsoft.com/azure/information-protection/rms-client/client-deployment-notes#redirecting-licensing-server-traffic).

## <a name="i-use-ad-rms-how-do-i-opt-out"></a>Jag använder AD RMS, hur gör jag för att avanmäla mig?

Om du vill välja bort den kommande ändringen gör du följande:

1. Starta en Windows PowerShell-session och Anslut till Exchange Online med ett arbets-eller skol konto som har global administratörs behörighet i organisationen. Anvisningar finns i [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

2. Kör cmdleten Set-IRMConfiguration med hjälp av följande syntax:

  ```powershell
  Set-IRMConfiguration -AutomaticServiceUpdateEnabled $false
  ```

## <a name="what-can-i-expect-after-this-change-has-been-made"></a>Vad kan jag förvänta dig efter att ändringen har gjorts?

När det här är aktiverat, förutsatt att du inte har gjort det kan du börja använda den nya versionen av Office 365 Message Encryption som annonserade på [Microsoft tändning 2017](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Email-Encryption-and-Rights-Protection/ba-p/110801) och som utnyttjar krypterings-och skydds funktionerna i Azure information Protection.

![Skärm bild som visar ett OME skyddat meddelande i Outlook på webben.](../../media/599ca9e7-c05a-429e-ae8d-359f1291a3d8.png)

Mer information om de nya förbättringarna finns i [meddelande kryptering i Office 365](../../compliance/ome.md).
