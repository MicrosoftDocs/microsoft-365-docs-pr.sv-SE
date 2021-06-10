---
title: Vanliga frågor och svar om Basic Mobility and Security (Vanliga frågor och svar)
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Vanliga frågor och svar om Grundläggande rörlighet och säkerhet.
ms.openlocfilehash: 14e12678ec210325f63914594fb6debcf7abb880
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023899"
---
# <a name="basic-mobility-and-security-frequently-asked-questions-faq"></a>Vanliga frågor och svar om Basic Mobility and Security (Vanliga frågor och svar)

Den här artikeln innehåller vanliga frågor och svar om grundläggande rörlighet och säkerhet, en funktion som hjälper dig att hantera och skydda mobila enheter i Microsoft 365. Om du inte hittar ett svar på din fråga vill vi gärna lämna en kommentar på sidan så att vi kan lägga till din fråga i den här artikeln.

## <a name="how-can-i-get-basic-mobility-and-security-i-dont-see-it-in-the-microsoft-365-admin-center"></a>Hur får jag Basic Mobility and Security? Jag ser det inte i Microsoft 365 administrationscenter

1.  Aktivera Grundläggande rörlighet och säkerhet genom att gå till [sidan Office 365 säkerhet och & standard.](https://protection.office.com/)

2.  Gå till Dataförlustskydd > Enhetshantering.

## <a name="how-can-i-get-started-with-device-management-in-basic-mobility-and-security"></a>Hur kommer jag igång med enhetshantering i Basic Mobility and Security?

Det finns fyra steg för att komma igång med Basic Mobility och säkerhet: 

1. Aktivera Basic Mobility and Security genom att gå till [Office 365 säkerhet & efterlevnad.](https://protection.office.com/)

2. Gå till Skydd mot dataförlust > av enhetshantering > principer för enheter.
    
3. Skapa principer för enhetshantering och använd dem på grupper av användare som har angetts i säkerhetsgrupper. Vi rekommenderar att du börjar genom att distribuera principerna till en liten testgrupp. Mer information finns i Skapa [säkerhetsprinciper för enheter i Grundläggande rörlighet och säkerhet.](create-device-security-policies.md)

4. Användare som har tillämpat en princip på dem uppmanas att registrera sina enheter när de försöker få åtkomst Microsoft 365 data. Mer information finns i [Registrera din mobila enhet med grundläggande rörlighet och säkerhet.](enroll-your-mobile-device.md)

Mer information finns i [Konfigurera Grundläggande rörlighet och säkerhet.](set-up.md)

## <a name="im-trying-to-set-up-basic-mobility-and-security-but-it-seems-stuck-the-microsoft-365-service-health-has-been-showing-provisioning-for-a-while-what-can-i-do"></a>Jag försöker konfigurera Basic Mobility and Security men den verkar ha låst sig. Den Microsoft 365 tjänstens hälsa har visat "etablering" ett tag. Vad kan jag göra?

Det kan ta lite tid att förbereda tjänsten åt dig. När etableringen är klar visas sidan Grundläggande rörlighet och säkerhet. Om du har väntat 24 timmar och status fortfarande är etablering kan du kontakta supporten så hjälper vi dig att ta reda på vad problemet är.

## <a name="what-can-i-do-if-device-enrollment-fails"></a>Vad kan jag göra om enhetsregistrering misslyckas?

Om du har problem med att registrera en enhet kontrollerar du först följande:

- Kontrollera att enheten inte redan är registrerad hos en annan leverantör för hantering av mobila enheter, till exempel Intune.

- Kontrollera att enheten är inställd på rätt datum och tid.

- Växla till ett annat WIFI-nätverk eller mobilt nätverk på enheten.

- För Android- eller iOS-enheter avinstallerar du och Intune-företagsportal appen på enheten.
    
Om registrering fortfarande inte fungerar kan du gå till [Felsöka grundläggande rörlighet och säkerhet.](troubleshoot.md)

## <a name="whats-the-difference-between-intune-and-basic-mobility-and-security"></a>Vad är skillnaden mellan Intune och Enkel rörlighet och säkerhet?

Basic Mobility and Security är värd för Intune-tjänsten. Det är en delmängd av Intune-tjänster som tillhandahålls som en extra förmån för Microsoft 365 och är en inbyggd molnbaserad lösning för hantering av enheter i organisationen. En jämförelse sida vid sida av de två tjänsterna som hjälper dig att avgöra om det är bäst att använda Intune eller Basic Mobility and Security för Microsoft 365 finns i Välja mellan Basic Mobility Security och [Intune.](choose-between-basic-mobility-and-security-and-intune.md)

## <a name="how-do-policies-work-for-basic-mobility-and-security-how-do-i-set-them-up-disable-them"></a>Hur fungerar principer för grundläggande rörlighet och säkerhet? Hur ställer jag in dem? Inaktivera dem?

När du har slutfört den första konfigurationen för grundläggande rörlighet och säkerhet skapar du principer och tillämpar dem på grupper av användare i säkerhets- & efterlevnadscenter. Principer kräver att användare av principerna registrerar sina enheter i grundläggande rörlighet och säkerhet innan enheten kan användas för att komma åt Microsoft 365 data. Principerna som du bestämr bestämmer inställningar för mobila enheter, till exempel hur ofta lösenord måste återställas eller om datakryptering krävs. Mer information finns i Skapa [säkerhetsprinciper för enheter i Kompatibilitetscenter](create-device-security-policies.md)för   enkel rörlighet Microsoft 365 [enheter.](../../compliance/microsoft-365-compliance-center.md)

Stegvisa instruktioner för hur du skapar och distribuerar enhetsprinciper finns i Skapa säkerhetsprinciper för [enheter i Basic Mobility and Security.](create-device-security-policies.md)

Om du vill exkludera en viss grupp av användare från att påverkas av principerna kan du lägga till en grupp i undantagsgruppen.

## <a name="can-i-switch-from-exchange-activesync-device-management-to-basic-mobility-and-security-for-microsoft-365"></a>Kan jag byta från Exchange ActiveSync till Grundläggande rörlighet och säkerhet för Microsoft 365?

Om du redan använder Exchange ActiveSync principer för att hantera mobila enheter kan du börja använda Basic Mobility and Security genom att följa stegen för att konfigurera Basic Mobility and Security. Mer information finns i [Skydda åtkomst till användare och enheter](../../compliance/protect-access-to-data-and-services.md) och Konfigurera grundläggande rörlighet och [säkerhet.](set-up.md)

När du tillämpar principerna som du skapar i Grundläggande rörlighet och säkerhet för grupper av användare åsidosätter dessa principer Exchange ActiveSync postlådeprinciper för mobila enheter och åtkomstregler för enheter som du tidigare skapat i administrationscentret för Exchange för dessa användare.

När en enhet har registrerats i Basic Mobility and Security ignoreras Exchange ActiveSync postlådeprinciper för mobila enheter eller enhetsåtkomstregel som tillämpas på enheten.

## <a name="i--set-up-basic-mobility-and-security-but-now-i-want-to-remove-it-what-are-the-steps"></a>Jag har ställt in Basic Mobility and Security men nu vill jag ta bort den. Vilka är stegen?

Tyvärr kan du inte bara "återkalla" Basic Mobility and Security när du har konfigurerat den. Men du kan ta bort det för grupper av användare genom att ta bort användarsäkerhetsgrupper från de enhetsprinciper som du har skapat. Du kan också inaktivera det för alla genom att ta bort enhetsprinciperna så att de inte finns på plats och inte tillämpas. Mer information finns i [Inaktivera Grundläggande rörlighet och säkerhet.](turn-off.md)