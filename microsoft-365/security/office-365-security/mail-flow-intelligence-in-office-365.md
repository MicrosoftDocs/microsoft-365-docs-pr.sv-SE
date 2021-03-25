---
title: Information om e-postflöde
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c29f75e5-c16e-409e-a123-430691e38276
description: Administratörer kan få mer information om de felkoder som associeras med meddelandeleverans med kopplingar (kallas även för e-postflödesinformation).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2cb52e5865415440b3b2924a3ebcc96a7f8e17e5
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207277"
---
# <a name="mail-flow-intelligence-in-eop"></a>E-postflödesinformation i EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor använder du vanligtvis en anslutare för att dirigera e-postmeddelanden från EOP till din lokala e-postmiljö. Du kan också använda en koppling för att dirigera meddelanden från Microsoft 365 till en partnerorganisation. När Microsoft 365 inte kan leverera dessa meddelanden via anslutningen är de i kö i Microsoft 365. Microsoft 365 fortsätter att försöka leverera för varje meddelande i 24 timmar. Efter 24 timmar upphör det köade meddelandet att gälla och meddelandet returneras till den ursprungliga avsändaren i en rapport om utebliven leverans (kallas även för en NDR-rapport eller icke-leveranskavsändare).

Microsoft 365 genererar ett fel när ett meddelande inte kan levereras med hjälp av en koppling. De vanligaste felen och deras lösningar beskrivs i den här artikeln. Köer och meddelandefel för meddelanden som inte kunde levereras via kopplingar kallas gemensamt för _e-postflödesinformation._

## <a name="error-code-450-44312-dns-query-failed"></a>Felkod: DNS-frågan 450 4.4.312 misslyckades

Vanligtvis innebär det här felet att Microsoft 365 försökte ansluta till den smarta värden som anges i kopplingen, men DNS-frågan för att hitta den smarta värdens IP-adresser misslyckades. Möjliga orsaker till det här felet är:

- Det är ett problem med domänens DNS-värdtjänst (den part som upprätthåller de auktoritativa namnservrarna för domänen).

- Domänen har nyligen upphört att gälla, så MX-posten kan inte hämtas.

- Domänens MX-post har nyligen ändrats och DNS-servrarna har fortfarande tidigare cachelagrad DNS-information för din domän.

### <a name="how-do-i-fix-error-code-450-44312"></a>Hur åtgärdar jag felkod 450 4.4.312?

- Arbeta med DNS-värdtjänsten för att identifiera och åtgärda problemet med din domän.

- Om felet kommer från din partnerorganisation (t.ex. en tredjepartsleverantör av molntjänster) kontaktar du din partner för att lösa problemet.

## <a name="error-code-450-44315-connection-timed-out"></a>Felkod: 450 4.4.315 Anslutningens timed out

Det innebär vanligtvis att Microsoft 365 inte kan ansluta till mål-e-postservern. I felinformationen förklaras problemet. Till exempel:

- Din lokala e-postserver ligger nere.

- Det finns ett fel i anslutningens inställningar för smart värd, så Microsoft 365 försöker ansluta till fel IP-adress.

### <a name="how-do-i-fix-error-code-450-44315"></a>Hur åtgärdar jag felkod 450 4.4.315?

- Ta reda på vilket scenario som gäller för dig och gör nödvändiga korrigeringar. Om e-postflödet till exempel har fungera korrekt och du inte har ändrat anslutningsinställningarna, måste du kontrollera din lokala e-postmiljö för att se om servern ligger nere, eller om det har gjorts några ändringar i nätverksinfrastrukturen (till exempel om du har ändrat internetleverantörer så att du nu har olika IP-adresser).

- Om felet kommer från din partnerorganisation (t.ex. en tredjepartsleverantör av molntjänster) kontaktar du din partner för att lösa problemet.

## <a name="error-code-450-44316-connection-refused"></a>Felkod: 450 4.4.316 Anslutningen är inte säker

Vanligtvis innebär det här felet att Microsoft 365 stött på ett anslutningsfel när det försökt ansluta till mål-e-postservern. En trolig orsak till det här felet är att din brandvägg blockerar anslutningar från Microsoft 365 IP-adresser. Eller så kan det här felet vara av design natur om du helt har migrerat ditt lokala e-postsystem till Microsoft 365 och stängt av din lokala e-postmiljö.

### <a name="how-do-i-fix-error-code-450-44316"></a>Hur åtgärdar jag felkod 450 4.4.316?

- Om du har postlådor i din lokala miljö måste du ändra dina brandväggsinställningar för att tillåta anslutningar från Microsoft 365 IP-adresser på TCP-port 25 till dina lokala e-postservrar. En lista över Microsoft 365 IP-adresser finns i URL-adresser och IP-adressintervall för [Microsoft 365.](../../enterprise/urls-and-ip-address-ranges.md)

- Om inga fler meddelanden ska levereras till  din lokala miljö klickar du på Åtgärda nu i aviseringen så att Microsoft 365 omedelbart kan avvisa meddelanden med ogiltiga mottagare. Det här minskar risken för att organisationens kvot för ogiltiga mottagare överskrids, vilket kan påverka normal meddelandeleverans. Du kan även använda följande anvisningar för att åtgärda problemet manuellt:

  - I [administrationscentret för Exchange (EAC)](/Exchange/exchange-admin-center)inaktiverar eller tar du bort anslutningen som levererar e-post från Microsoft 365 till din lokala e-postmiljö:

    1. Gå till E-postflödeskopplingar  \> **i** EAC.

    2. Välj kopplingen med **Från-värdet** **Office 365** och till-värdet  din organisations **e-postserver** och gör något av följande:

       - Ta bort kopplingen genom att klicka på **ikonen Ta** ![ bort](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)

       - Inaktivera kopplingen genom att klicka **på** ![ redigera-ikonen ](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) och avmarkera **Aktivera.**

  - Ändra den godkända domänen i Microsoft 365 som är kopplad till din lokala e-postmiljö från Internt **relä** **till Auktoritativ.** Anvisningar finns i Hantera [godkända domäner i Exchange Online.](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)

  **Obs!** Det brukar ta mellan 30 minuter och en timme innan ändringarna börjar gälla. Efter en timme kontrollerar du att du inte längre får felmeddelandet.

- Om felet kommer från din partnerorganisation (t.ex. en tredjepartsleverantör av molntjänster) måste du kontakta din partner för att lösa problemet.

## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a>Felkod: 450 4.4.317 Det går inte att ansluta till fjärrservern

Vanligtvis innebär det här felet att Microsoft 365 är ansluten till mål-e-postservern, men att servern har svarat med ett omedelbart fel eller inte uppfyller anslutningskraven. I felinformationen förklaras problemet. Till exempel:

- Mål-e-postservern har svarat med felet "Tjänsten är inte tillgänglig", vilket indikerar att servern inte kan behålla kommunikationen med Microsoft 365.

- Anslutningen är konfigurerad så att den kräver TLS, men mål-e-postservern stöder inte TLS.

### <a name="how-do-i-fix-error-code-450-44317"></a>Hur åtgärdar jag felkod 450 4.4.317?

- Verifiera TLS-inställningarna och certifikaten på de lokala e-postservrarna och TLS-inställningarna på kopplingen.

- Om felet kommer från din partnerorganisation (t.ex. en tredjepartsleverantör av molntjänster) måste du kontakta din partner för att lösa problemet.

## <a name="error-code-450-44318-connection-was-closed-abruptly"></a>Felkod: 450 4.4.318 Anslutningen var stängd

Vanligtvis innebär det här felet att Microsoft 365 har problem med att kommunicera med din lokala e-postmiljö, så anslutningen har släppts. Möjliga orsaker till det här felet är:

- Din brandvägg använder regler för SMTP-paketundersökning och de reglerna fungerar inte korrekt.

- Din lokala e-postserver fungerar inte korrekt (t.ex. hänger sig tjänsten, kraschar eller låg systemresurser), vilket gör att serverns time out och stänger anslutningen till Microsoft 365.

- Det finns nätverksproblem mellan din lokala miljö och Microsoft 365.

### <a name="how-do-i-fix-error-code-450-44318"></a>Hur åtgärdar jag felkod 450 4.4.318?

- Ta reda på vilket scenario som gäller för dig och gör nödvändiga korrigeringar.

- Om problemet orsakas av nätverksproblem mellan din lokala miljö och Microsoft 365 kontaktar du nätverksteamet för att felsöka problemet.

- Om felet kommer från din partnerorganisation (t.ex. en tredjepartsleverantör av molntjänster) måste du kontakta din partner för att lösa problemet.

## <a name="error-code-450-47320-certificate-validation-failed"></a>Felkod: 450 4.7.320 Certifikatverifiering misslyckades

Vanligtvis innebär det här felet att Microsoft 365 stött på ett fel när certifikatet för mål-e-postservern ska verifieras. I felinformationen förklaras felet. Till exempel:

- Certifikatet har gått ut

- Felmatchning av certifikatsämne

- Certifikatet är inte längre giltigt

### <a name="how-do-i-fix-error-code-450-47320"></a>Hur åtgärdar jag felkod 450 4.7.320?

- Åtgärda certifikatet eller inställningarna för anslutningen så att meddelanden i kö i Microsoft 365 kan levereras.

- Om felet kommer från din partnerorganisation (t.ex. en tredjepartsleverantör av molntjänster) måste du kontakta din partner för att lösa problemet.

## <a name="other-error-codes"></a>Andra felkoder

Microsoft 365 har problem med att leverera meddelanden till din lokala e-postserver eller partnerserver. Använd **målserverinformationen** i felet om du vill undersöka problemet i miljön eller ändra kopplingen om det uppstår ett konfigurationsfel.

Om felet kommer från din partnerorganisation (t.ex. en tredjepartsleverantör av molntjänster) måste du kontakta din partner för att lösa problemet.