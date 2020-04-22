---
title: Information om e-postflöde
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c29f75e5-c16e-409e-a123-430691e38276
description: Administratörer kan lära sig mer om de felkoder som är associerade med meddelandeleverans med kopplingar (kallas även information om e-postflödet).
ms.openlocfilehash: aa156299dcc835369b7eb69bb5719b27078d8404
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635642"
---
# <a name="mail-flow-intelligence"></a>Information om e-postflöde

Vanligtvis använder du en anslutningsapp för att dirigera e-postmeddelanden från din organisation till din lokala e-postmiljö. Du kan också använda en anslutningsapp för att dirigera meddelanden från Microsoft 365 till en partnerorganisation. När Microsoft 365 inte kan leverera dessa meddelanden via anslutningsappen står de i kö i Microsoft 365. Microsoft 365 fortsätter att försöka leverera för varje meddelande i 24 timmar. Efter 24 timmar upphör det köade meddelandet och meddelandet returneras till den ursprungliga avsändaren i en rapport om utebliven leverans (kallas även NDR eller avvisningsmeddelande).

Microsoft 365 genererar ett fel när ett meddelande inte kan levereras med hjälp av en anslutningsapp. De vanligaste felen och deras lösningar beskrivs i det här avsnittet. Kollektivt kallas kö- och meddelandefel för meddelanden som inte kan levereras via kopplingar som _e-postflödesinformation_.

## <a name="error-code-450-44312-dns-query-failed"></a>Felkod: 450 4.4.312 DNS-frågan misslyckades

Det här felet innebär vanligtvis att Microsoft 365 försökte ansluta till den smarta värden som anges i kopplingen, men DNS-frågan för att hitta den smarta värdens IP-adresser misslyckades. De möjliga orsakerna till det här felet är:

- Det finns ett problem med domänens DNS-värdtjänst (den part som underhåller de auktoritära namnservrarna för din domän).

- Domänen har nyligen upphört att gälla, så MX-posten kan inte hämtas.

- Domänens MX-post har nyligen ändrats och DNS-servrarna har fortfarande tidigare cachelagrat DNS-information för din domän.

### <a name="how-do-i-fix-error-code-450-44312"></a>Hur åtgärdar jag felkod 450 4.4.312?

- Arbeta med dns-värdtjänsten för att identifiera och åtgärda problemet med din domän.

- Om felet kommer från din partnerorganisation (till exempel en molntjänstleverantör från tredje part) kontaktar du din partner för att åtgärda problemet.

## <a name="error-code-450-44315-connection-timed-out"></a>Felkod: 450 4.4.315 Anslutningstidsering

Det innebär vanligtvis att Microsoft 365 inte kan ansluta till målmeddelandeservern. Felinformationen förklarar problemet. Till exempel:

- Din lokala e-postserver är nere.

- Det finns ett fel i anslutningens smarta värdinställningar, så Microsoft 365 försöker ansluta till fel IP-adress.

### <a name="how-do-i-fix-error-code-450-44315"></a>Hur åtgärdar jag felkod 450 4.4.315?

- Ta reda på vilket scenario som gäller för dig och gör nödvändiga korrigeringar. Om e-postflödet till exempel har fungerat korrekt och du inte har ändrat anslutningsinställningarna måste du kontrollera din lokala e-postmiljö för att se om servern är nere eller om det har skett några ändringar i nätverksinfrastrukturen (du har till exempel ändrat internetleverantörer, så att du nu har olika IP-adresser).

- Om felet kommer från din partnerorganisation (till exempel en molntjänstleverantör från tredje part) kontaktar du din partner för att åtgärda problemet.

## <a name="error-code-450-44316-connection-refused"></a>Felkod: 450 4.4.316 Anslutning nekad

Det här felet innebär vanligtvis att Microsoft 365 påträffade ett anslutningsfel när det försökte ansluta till målmeddelandeservern. En trolig orsak till det här felet är att brandväggen blockerar anslutningar från Microsoft 365 IP-adresser. Det här felet kan också vara avsiktligt om du helt har migrerat ditt lokala e-postsystem till Microsoft 365 och stängt av din lokala e-postmiljö.

### <a name="how-do-i-fix-error-code-450-44316"></a>Hur åtgärdar jag felkod 450 4.4.316?

- Om du har postlådor i din lokala miljö måste du ändra brandväggsinställningarna så att anslutningar från Microsoft 365 IP-adresser på TCP-port 25 till dina lokala e-postservrar tillåts. En lista över Microsoft 365-IP-adresserna finns i [Microsoft 365-URL:er och IP-adressintervall](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).

- Om inga fler meddelanden ska levereras till din lokala miljö klickar du på **Åtgärda nu** i aviseringen så att Microsoft 365 omedelbart kan avvisa meddelandena med ogiltiga mottagare. Detta minskar risken för att din organisations kvot överskrids för ogiltiga mottagare, vilket kan påverka normal meddelandeleverans. Du kan också använda följande instruktioner för att åtgärda problemet manuellt:

  - I [Administrationscentret för Exchange (EAC)](https://docs.microsoft.com/Exchange/exchange-admin-center)inaktiverar eller tar du bort den anslutningsapp som levererar e-post från Microsoft 365 till din lokala e-postmiljö:

    1. Gå till **EAC i EAC-kopplingarna för e-postflöde** \> **Connectors**.

    2. Välj anslutningsappen med **värdet Från** **Office 365** och **Värdet Till** **Organisationens e-postserver** och gör något av följande:

       - Ta bort kopplingen genom att klicka på Ikonen **Ta bort** ![ta bort](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)

       - Inaktivera kopplingen genom **Edit** ![att klicka](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) på Ikonen Redigera redigera och avmarkera **Aktivera den**.

  - Ändra den accepterade domänen i Microsoft 365 som är associerad med din lokala e-postmiljö från **Intern relay** till **auktoritär .** Instruktioner finns [i Hantera accepterade domäner i Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).

  **Obs:** Vanligtvis tar dessa ändringar mellan 30 minuter och en timme att börja gälla. Efter en timme kontrollerar du att felet inte längre visas.

- Om felet kommer från din partnerorganisation (till exempel en molntjänstleverantör från tredje part) måste du kontakta din partner för att åtgärda problemet.

## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a>Felkod: 450 4.4.317 Det går inte att ansluta till fjärrservern

Det här felet innebär vanligtvis Att Microsoft 365 är anslutet till målmeddelandeservern, men servern svarade med ett omedelbart fel eller uppfyller inte anslutningskraven. Felinformationen förklarar problemet. Till exempel:

- Målmeddelandeservern svarade med ett felmeddelande om tjänsten som inte är tillgänglig, vilket indikerar att servern inte kan upprätthålla kommunikationen med Office 365.

- Anslutningen är konfigurerad för att kräva TLS, men målmeddelandeservern stöder inte TLS.

### <a name="how-do-i-fix-error-code-450-44317"></a>Hur åtgärdar jag felkod 450 4.4.317?

- Verifiera TLS-inställningarna och certifikaten på dina lokala e-postservrar och TLS-inställningarna på anslutningen.

- Om felet kommer från din partnerorganisation (till exempel en molntjänstleverantör från tredje part) måste du kontakta din partner för att åtgärda problemet.

## <a name="error-code-450-44318-connection-was-closed-abruptly"></a>Felkod: 450 4.4.318 Anslutningen stängdes plötsligt

Det här felet innebär vanligtvis att Microsoft 365 har svårt att kommunicera med din lokala e-postmiljö, så anslutningen avbröts. De möjliga orsakerna till det här felet är:

- Brandväggen använder SMTP-paketgranskningsregler och dessa regler fungerar inte korrekt.

- Din lokala e-postserver fungerar inte korrekt (till exempel låser sig tjänsten, kraschar eller har låga systemresurser), vilket gör att servern tar timeout och stänger anslutningen till Office 365.

- Det finns nätverksproblem mellan den lokala miljön och Office 365.

### <a name="how-do-i-fix-error-code-450-44318"></a>Hur åtgärdar jag felkod 450 4.4.318?

- Ta reda på vilket scenario som gäller för dig och gör nödvändiga korrigeringar.

- Om problemet beror på nätverksproblem mellan den lokala miljön och Office 365 kontaktar du nätverksteamet för att felsöka problemet.

- Om felet kommer från din partnerorganisation (till exempel en molntjänstleverantör från tredje part) måste du kontakta din partner för att åtgärda problemet.

## <a name="error-code-450-47320-certificate-validation-failed"></a>Felkod: 450 4.7.320 Certifikatvalidering misslyckades

Det här felet innebär vanligtvis att Microsoft 365 påträffade ett fel när certifikatet för målmeddelandeservern skulle valideras. Felinformationen förklarar felet. Till exempel:

- Certifikatet har upphört att gälla

- Felmatchning av certifikatämne

- Certifikatet är inte längre giltigt

### <a name="how-do-i-fix-error-code-450-47320"></a>Hur åtgärdar jag felkod 450 4.7.320?

- Åtgärda certifikatet eller inställningarna på kopplingen så att köade meddelanden i Microsoft 365 kan levereras.

- Om felet kommer från din partnerorganisation (till exempel en molntjänstleverantör från tredje part) måste du kontakta din partner för att åtgärda problemet.

## <a name="other-error-codes"></a>Andra felkoder

Microsoft 365 har svårt att leverera meddelanden till din lokala e-postserver eller partnerserver. Använd **målserverinformationen** i felet för att undersöka problemet i din miljö eller ändra kopplingen om det finns ett konfigurationsfel.

Om felet kommer från din partnerorganisation (till exempel en molntjänstleverantör från tredje part) måste du kontakta din partner för att åtgärda problemet.
