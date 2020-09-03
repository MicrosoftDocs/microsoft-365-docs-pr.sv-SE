---
title: Vanliga frågor och svar om grundläggande rörlighet och säkerhet
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
description: Vanliga frågor och svar om grundläggande mobilitet och säkerhet.
ms.openlocfilehash: a79b7df53f717d511603ec57e09ce4d6c523d14d
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/02/2020
ms.locfileid: "47337142"
---
# <a name="basic-mobility-and-security-frequently-asked-questions-faq"></a>Vanliga frågor och svar om grundläggande rörlighet och säkerhet

Den här artikeln innehåller vanliga frågor och svar om grundläggande mobilitet och säkerhet, en funktion som hjälper dig att hantera och skydda mobila enheter i Microsoft 365. Om du inte hittar ett svar på din fråga kan du meddela oss genom att lämna en kommentar på sidan, så att det går att lägga till frågan i den här artikeln.

## <a name="how-can-i-get-basic-mobility-and-security-i-dont-see-it-in-the-microsoft-365-admin-center"></a>Hur kan jag få grundläggande rörlighet och säkerhet? Jag ser det inte i administrations centret för Microsoft 365

1.  Aktivera grundläggande rörlighet och säkerhet genom att gå till sidan för [säkerhets & i Office 365](https://protection.office.com/) .   

2.  Gå till > hantera data förlust.   

## <a name="how-can-i-get-started-with-device-management-in-basic-mobility-and-security"></a>Hur kan jag komma igång med enhets hantering i grundläggande mobilitet och säkerhet?

Det finns fyra steg för att komma igång med grundläggande mobilitet och säkerhet: 

1. Aktivera grundläggande mobilitet och säkerhet genom att gå till [Office 365-säkerhets & efterlevnad](https://protection.office.com/).
    
2. Gå till förhindra data förlust > enhets hantering > enhets principer.
    
3. Skapa enhets hanterings principer och tillämpa dem på grupper med användare som har kon figurer ATS i säkerhets grupper. Vi rekommenderar att du börjar med att distribuera principerna till en liten test grupp. Mer information finns i [skapa säkerhets principer för enheter i grundläggande mobilitet och säkerhet](create-device-security-policies-in-basic-mmobility-and-security.md).      

4. Användare som har en princip tillfrågas om att registrera sina enheter när de försöker komma åt Microsoft 365-data. Mer information finns i [Registrera din mobila enhet med grundläggande mobilitet och säkerhet](enroll-your-mobile-device-using-basic-mobility-and-security.md).

Mer information finns i [Konfigurera grundläggande mobilitet och säkerhet](set-up-basic-mobility-and-security.md).

## <a name="im-trying-to-set-up-basic-mobility-and-security-but-it-seems-stuck-the-microsoft-365-service-health-has-been-showing-provisioning-for-a-while-what-can-i-do"></a>Jag försöker ställa in grundläggande mobilitet och säkerhet men det verkar vara fastnat. Microsoft 365-tjänstens hälsa visar "etableringen" för ett tag. Vad kan jag göra?

Det kan ta en stund för dig att få tjänsten redo för dig. När etableringen är slutfört visas sidan hantering av mobila enheter för Microsoft 365. Om du har väntat 24 timmar och status fortfarande är etablerad, kontakta supporten så hjälper vi dig att ta reda på vad problemet är. Om du [behöver hjälp](https://support.microsoft.com/office/frequently-asked-questions-about-basic-mobility-and-security-3871f99c-c9db-4a23-86f9-902c1b02f58d#bkmk_needhelp) kan du läsa mer i avsnittet om att få support. 

## <a name="what-can-i-do-if-device-enrollment-fails"></a>Vad kan jag göra om enhets registrering Miss lyckas?

Om du har problem med att få en enhet registrerad måste du först kontrol lera följande:

- Kontrol lera att enheten inte redan har registrerats hos en annan leverantör för hantering av mobila enheter, till exempel Intune.
    
- Kontrol lera att enheten är inställd på rätt datum och tid.
    
- Byt till ett annat WIFI-eller cellulärt nätverk på enheten.
    
- För Android-eller iOS-enheter avinstallerar och installerar du om Intune-företagsportalsappen på enheten.
    
Om det fortfarande inte fungerar kan du läsa mer i [Felsöka grundläggande mobilitet och säkerhet](troubleshoot-basic-mobility-and-security.md).

## <a name="whats-the-difference-between-intune-and-basic-mobility-and-security"></a>Vad är skillnaden mellan Intune och grundläggande mobilitet och säkerhet?

Den grundläggande rörligheten och säkerheten hanteras av Intune-tjänsten. Det är en del av Intune-tjänsterna som tillhandahålls av Microsoft 365 och är en inbyggd Cloud-baserad lösning för att hantera enheter i din organisation. En sida vid sida-jämförelse med de två tjänsterna för att hjälpa dig att avgöra om du använder Intune eller grundläggande mobilitet och säkerhet för Microsoft 365 är det bästa alternativet för dig, se [välja mellan grundläggande mobilitets säkerhet och Intune](choose-between-basic-mobility-and-security-and-intune.md).

## <a name="how-do-policies-work-for-basic-mobility-and-security-how-do-i-set-them-up-disable-them"></a>Hur fungerar principer för grundläggande mobilitet och säkerhet? Hur ställer jag in dem? Inaktivera dem?

När du har slutfört den första installationen av grundläggande mobilitet kan du skapa principer och tillämpa dem på grupper av användare i säkerhets & Compliance Center. Principer kräver att användare av principerna registrerar sina enheter i grundläggande mobilitet och säkerhet innan enheten kan användas för att komma åt Microsoft 365-data. De principer som du konfigurerar styr inställningar för mobila enheter, till exempel hur ofta lösen ord måste återställas eller om data kryptering krävs. Mer information finns i [skapa säkerhets principer för enheter i grundläggande information om mobilitet och säkerhet](create-device-security-policies-in-basic-mmobility-and-security.md)   och [Microsoft 365 Compliance Center](https://support.microsoft.com/office/7e696a40-b86b-4a20-afcc-559218b7b1b8).

Stegvisa anvisningar för hur du skapar och distribuerar enhets principer finns i [skapa säkerhets principer för enheter i grundläggande mobilitet och säkerhet](create-device-security-policies-in-basic-mmobility-and-security.md).

Om du vill undanta en viss grupp användare från principer kan du lägga till en grupp i undantags gruppen.

## <a name="can-i-switch-from-exchange-activesync-device-management-to-basic-mobility-and-security-for-microsoft-365"></a>Kan jag byta från Exchange ActiveSync-enheten till grundläggande mobilitet och säkerhet för Microsoft 365?

Om du redan använder Exchange ActiveSync-principer för att hantera mobila enheter kan du börja använda grundläggande mobilitet och säkerhet genom att följa stegen för att konfigurera grundläggande mobilitet och säkerhet. Mer information finns i [skydda användare och enheter](https://go.microsoft.com/fwlink/?LinkId=615145) och [ställa in grundläggande mobilitet och säkerhet](set-up-basic-mobility-and-security.md).

När du tillämpar de principer som du skapar i grundläggande mobilitet och säkerhet för grupper av användare, ersätter dessa principer Exchange ActiveSync-principer för mobila enheter och enheter som du har skapat i administrations centret för Exchange för dessa användare.

När en enhet har registrerats i grundläggande mobilitet och säkerhet, ignoreras eventuella principer för Exchange ActiveSync-postlådan eller enhets åtkomst regeln för enheten.

## <a name="i--set-up-basic-mobility-and-security-but-now-i-want-to-remove-it-what-are-the-steps"></a>Jag har konfigurerat grundläggande mobilitet och säkerhet men nu vill jag ta bort den. Vilka är stegen?

Tyvärr kan du inte helt enkelt "avetablera" grundläggande mobilitet och säkerhet när du har konfigurerat det. Men du kan ta bort det för grupper av användare genom att ta bort säkerhets grupper för användare från de enhets principer som du har skapat. Eller så kan du inaktivera det för alla genom att ta bort enhets principerna så att de inte är på plats och inte tillämpas. Mer information finns i [Inaktivera grundläggande mobilitet och säkerhet](turn-off-basic-mobility-and-security.md).

