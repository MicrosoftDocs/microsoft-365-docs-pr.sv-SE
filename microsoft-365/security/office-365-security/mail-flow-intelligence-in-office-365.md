---
title: Information om e-postflöde
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c29f75e5-c16e-409e-a123-430691e38276
description: Administratörer kan läsa mer om fel koderna som är kopplade till meddelande leverans via kopplingar (kallas även för e-postflöde).
ms.openlocfilehash: e8427f3e0341ccb381121b6cdc83d20727713d4c
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307923"
---
# <a name="mail-flow-intelligence-in-eop"></a>E-postflödesinformation i EOP

I Microsoft 365-organisationer med post lådor i Exchange Online eller fristående Exchange Online Protection (EOP)-organisationer utan Exchange Online-postlådor använder du vanligt vis en koppling för att dirigera e-postmeddelanden från EOP till din lokala e-postmiljö. Du kan också använda en koppling för att dirigera meddelanden från Microsoft 365 till en partner organisation. När Microsoft 365 inte kan leverera dessa meddelanden via kopplingen köas de i Microsoft 365. Microsoft 365 fortsätter att försöka leverera för varje meddelande i 24 timmar. Efter 24 timmar upphör det köade meddelandet att upphöra och meddelandet kommer att återföras till den ursprungliga avsändaren i en rapport om utebliven leverans (kallas även för en NDR eller ett studs meddelande).

Microsoft 365 skapar ett fel när ett meddelande inte kan levereras med en koppling. De vanligaste felen och deras lösningar beskrivs i det här avsnittet. Det är kollektivt, köer och aviserings fel för meddelanden som skickas via kopplingar kallas för _e-postflöde_.

## <a name="error-code-450-44312-dns-query-failed"></a>Felkod: 450 4.4.312 DNS Query misslyckades

Det här felet innebär att Microsoft 365 försökte ansluta till den smarta värden som anges i kopplingen, men DNS-frågan för att hitta den smarta värdens IP-adresser misslyckades. Möjliga orsaker till det här felet är:

- Det är problem med din domäns DNS-värd (den part som underhåller de auktoritära namnservrarna för din domän).

- Din domän har nyligen upphört, så MX-posten kan inte hämtas.

- Din domäns MX-post har nyligen ändrats och DNS-servrarna har fortfarande cachelagrat DNS-information för din domän.

### <a name="how-do-i-fix-error-code-450-44312"></a>Hur åtgärdar jag felkod 450 4.4.312?

- Arbeta med din DNS-värd för att identifiera och åtgärda problemet med din domän.

- Om felet kommer från din partner organisation (till exempel en tredjeparts moln tjänst leverantör) kontaktar du din partner för att åtgärda problemet.

## <a name="error-code-450-44315-connection-timed-out"></a>Felkod: tids gränsen för 450 4.4.315-anslutningen uppnåddes

Det innebär vanligt vis att Microsoft 365 inte kan ansluta till mål-e-postservern. Fel informationen förklarar problemet. Till exempel:

- Din lokala e-postserver är nere.

- Det finns ett fel i kopplingens inställningar för smart värd, så Microsoft 365 försöker ansluta till fel IP-adress.

### <a name="how-do-i-fix-error-code-450-44315"></a>Hur åtgärdar jag felkod 450 4.4.315?

- Ta reda på vilket scenario som gäller för dig och gör nödvändiga ändringar. Om e-postflödet fungerar som det ska och du inte har ändrat kopplings inställningarna måste du kontrol lera din lokala e-postmiljö för att se om servern är nere, eller om det har gjorts ändringar i nätverks infrastrukturen (till exempel har du ändrat Internet leverantörens IP-adresser).

- Om felet kommer från din partner organisation (till exempel en tredjeparts moln tjänst leverantör) kontaktar du din partner för att åtgärda problemet.

## <a name="error-code-450-44316-connection-refused"></a>Felkod: 450 4.4.316 anslutningen nekades

Vanligt vis betyder det att Microsoft 365 stötte på ett anslutnings fel när det försökte ansluta till mål-e-postservern. Den sannolika orsaken till felet är att brand väggen blockerar anslutningar från Microsoft 365-IP-adresser. Eller så kan det bero på att du har migrerat det lokala e-postsystemet fullständigt till Microsoft 365 och stängt din lokala e-postmiljö.

### <a name="how-do-i-fix-error-code-450-44316"></a>Hur åtgärdar jag felkod 450 4.4.316?

- Om du har post lådor i den lokala miljön måste du ändra brand Väggs inställningarna för att tillåta anslutningar från Microsoft 365-IP-adresser på TCP port 25 till lokala e-postservrar. En lista med IP-adresser för Microsoft 365 finns i [microsoft 365 URL: er och IP-adressintervall](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges).

- Om du inte vill skicka fler meddelanden till den lokala miljön klickar du på **åtgärda nu** i aviseringen så att Microsoft 365 omedelbart neka meddelanden med ogiltiga mottagare. Detta minskar risken för att organisationens kvot överskrids för ogiltiga mottagare, vilket kan påverka normal meddelande leverans. Eller så kan du använda följande anvisningar för att lösa problemet manuellt:

  - I [administrations centret för Exchange (UK)](https://docs.microsoft.com/Exchange/exchange-admin-center)inaktiverar eller tar du bort kopplingen som skickar e-post från Microsoft 365 till din lokala e-post miljö:

    1. Gå till **e-postflödes** \> **kopplingar**i UK.

    2. Välj kopplingen med värdet **från** **Office 365** och värdet **till för** **din organisations e-postserver** och gör något av följande:

       - Ta bort kopplingen genom att klicka på **ta bort** ![ ta bort ikon](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)

       - Inaktivera kopplingen genom att klicka på **Redigera** ![ redigerings ikon ](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) och sedan Rensa **på Aktivera den**.

  - Ändra den godkända domänen i Microsoft 365 som är kopplad till den lokala e-postmiljön från **intern relä** till **auktoritär**. Anvisningar finns i [Hantera godkända domäner i Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).

  **Obs!** normalt tar de här ändringarna mellan 30 minuter och 1 timme att börja gälla. Efter en timme kontrollerar du att du inte längre får felet.

- Om felet kommer från din partner organisation (till exempel en tredjeparts moln tjänst leverantör) måste du kontakta din partner för att åtgärda problemet.

## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a>Felkod: 450 4.4.317 går inte att ansluta till fjärrservern

Det här felet innebär vanligt vis att Microsoft 365 är uppkopplat till mål-e-postservern, men servern svarade med ett omedelbara fel eller inte uppfyller anslutnings kraven. Fel informationen förklarar problemet. Till exempel:

- Mål-e-postservern svarade med fel meddelandet "tjänsten är inte tillgänglig", vilket betyder att servern inte kan hantera kommunikationen med Microsoft 365.

- Anslutningen är konfigurerad för att kräva TLS men mål-e-postservern stöder inte TLS.

### <a name="how-do-i-fix-error-code-450-44317"></a>Hur åtgärdar jag felkod 450 4.4.317?

- Kontrol lera TLS-inställningar och certifikat på lokala e-postservrar och TLS-inställningar på kopplingen.

- Om felet kommer från din partner organisation (till exempel en tredjeparts moln tjänst leverantör) måste du kontakta din partner för att åtgärda problemet.

## <a name="error-code-450-44318-connection-was-closed-abruptly"></a>Felkod: 450 4.4.318 anslutningen avbröts plötsligt

Vanligt vis betyder det att Microsoft 365 har problem med kommunikationen med din lokala e-postmiljö, så anslutningen avbröts. Möjliga orsaker till det här felet är:

- Brand väggen använder regler för SMTP-paketfiltrering och reglerna fungerar inte som de ska.

- Den lokala e-postservern fungerar inte som den ska (till exempel att tjänsten hänger sig, kraschar eller låg system resurser), vilket gör att servern tar slut på timeout och stänger anslutningen till Microsoft 365.

- Det finns nätverks problem mellan den lokala miljön och Microsoft 365.

### <a name="how-do-i-fix-error-code-450-44318"></a>Hur åtgärdar jag felkod 450 4.4.318?

- Ta reda på vilket scenario som gäller för dig och gör nödvändiga ändringar.

- Om problemet orsakas av nätverks problem mellan den lokala miljön och Microsoft 365 kontaktar du nätverks gruppen för att felsöka problemet.

- Om felet kommer från din partner organisation (till exempel en tredjeparts moln tjänst leverantör) måste du kontakta din partner för att åtgärda problemet.

## <a name="error-code-450-47320-certificate-validation-failed"></a>Felkod: det gick inte att verifiera 450-4.7.320

Det här felet innebär vanligt vis att Microsoft 365 påträffade ett fel när du försöker verifiera mål-e-postserverns certifikat. Fel informationen förklarar felet. Till exempel:

- Certifikatet har upphört

- Subjekt brist

- Certifikatet är inte längre giltigt

### <a name="how-do-i-fix-error-code-450-47320"></a>Hur åtgärdar jag felkod 450 4.7.320?

- Åtgärda certifikatet eller inställningarna för anslutningen så att köade meddelanden i Microsoft 365 kan levereras.

- Om felet kommer från din partner organisation (till exempel en tredjeparts moln tjänst leverantör) måste du kontakta din partner för att åtgärda problemet.

## <a name="other-error-codes"></a>Andra felkoder

Microsoft 365 har svårt att leverera meddelanden till din lokala eller partner e-postserver. Använd informationen om **mål servern** för att undersöka problemet i miljön eller ändra anslutningen om det finns ett konfigurations fel.

Om felet kommer från din partner organisation (till exempel en tredjeparts moln tjänst leverantör) måste du kontakta din partner för att åtgärda problemet.
