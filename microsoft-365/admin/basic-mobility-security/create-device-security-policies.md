---
title: Skapa säkerhets principer för enheter i grundläggande mobilitet och säkerhet
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
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
description: Använd grundläggande mobilitet och säkerhet för att skapa enhets principer som skyddar din organisations information.
ms.openlocfilehash: eddd3454e8f00bab7a830e7710331cafd097d7de
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430334"
---
# <a name="create-device-security-policies-in-basic-mobility-and-security"></a>Skapa säkerhets principer för enheter i grundläggande mobilitet och säkerhet 

Du kan använda grundläggande mobilitet och säkerhet för att skapa enhets principer som hjälper dig att skydda organisationsinformationen på Microsoft 365 från obehörig åtkomst. Du kan tillämpa principer på alla mobila enheter i organisationen där användaren av enheten har en giltig Microsoft 365-licens och har registrerat enheten i grundläggande mobilitet och säkerhet.

## <a name="before-you-begin"></a>Innan du börjar

>[!IMPORTANT]
>Innan du kan skapa en princip för mobila enheter måste du aktivera och konfigurera grundläggande mobilitet och säkerhet. Mer information finns i Översikt över grundläggande mobilitet och säkerhet.

- Läs mer om enheter, mobila enheter och säkerhets inställningar som grundläggande mobilitet och säkerhet kan hantera. Se [möjligheter till grundläggande mobilitet och säkerhet](capabilities.md).
- Skapa säkerhets grupper som innehåller Microsoft 365-användare som du vill distribuera principer till och för användare som du vill undanta från att blockera åtkomst till Microsoft 365. Vi rekommenderar att du testar principen genom att distribuera den till ett fåtal användare innan du distribuerar en ny princip till din organisation. Du kan skapa och använda en säkerhets grupp som inkluderar bara dig själv eller ett litet Microsoft 365-användare som kan testa policyn åt dig. Mer information om säkerhets grupper finns i [skapa, redigera och ta bort en säkerhets grupp](https://go.microsoft.com/fwlink/p/?LinkId=518555).
- För att skapa och distribuera grundläggande mobilitets-och säkerhets principer i Microsoft 365 måste du vara en global administratör för Microsoft 365. Mer information finns i [behörigheter i säkerhets & Compliance Center](https://support.microsoft.com/office/d10608af-7934-490a-818e-e68f17d0e9c1).
- Innan du distribuerar principer kan du låta din organisation veta de potentiella konsekvenserna av att registrera en enhet i grundläggande mobilitet och säkerhet. Beroende på hur du konfigurerar principer kan inkompatibla enheter blockeras från att få åtkomst till Microsoft 365 och data, inklusive installerade program, foton och personlig information på en registrerad enhet och data kan tas bort.

>[!NOTE]
>Principer och åtkomst regler som har skapats i MDM för Microsoft 365 Business Standard åsidosätter Exchange ActiveSync-principer för mobila enheter och åtkomst regler för enheter som har skapats i administrations centret för Exchange. När en enhet har registrerats i MDM för Microsoft 365 Business Standard, ignoreras alla mobila enheter för Exchange ActiveSync-postlådor eller enhets åtkomst som används för enheten. Mer information om Exchange ActiveSync finns i [Exchange ActiveSync i Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=524380).

## <a name="step-1-create-a-device-policy-and-deploy-to-a-test-group"></a>Steg 1: skapa en enhets princip och distribuera till en test grupp

Innan du kan börja bör du kontrol lera att du har aktiverat och konfigurerat grundläggande mobilitet och säkerhet. Anvisningar finns i [Översikt över grundläggande mobilitet och säkerhet](overview.md).

1. Skriv in i webbläsaren [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .

2. Välj **skapa en princip**.

    :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Grundläggande inställningar för mobilitet och säkerhets principer":::

3. På sidan **princip inställningar** anger du de krav du vill använda för mobila enheter i organisationen.

4. **Kräv hantering av e-postprofil**: när den är aktive rad betraktas enheter som inte har en e-postprofil som hanteras av grundläggande mobilitet och säkerhet som inte är kompatibla. En enhet kan inte ha en hanterad e-postprofil när den inte är korrekt riktad, eller om användaren har konfigurerat e-postkontot manuellt på enheten. När du låter det vara **inte aktiverat** (standard) utvärderas inte den här inställningen för efterlevnad eller bristande efterlevnad. Instruktioner för hur användare kan få kompatibilitet när det här alternativet är markerat finns i [ett befintligt e-postkonto](https://docs.microsoft.com/intune-user-help/existing-company-email-account-found).

5. På sidan **vill du använda denna princip nu?** väljer du de grupper som du vill tillämpa principen på.

6. Välj **skapa den här principen**.

Principen skickas till varje användares enhets princip gäller nästa gång de loggar in på Microsoft 365 med deras mobila enhet. Om användare inte har använt en princip på sin mobila enhet innan du har distribuerat den, får de en avisering på sina enheter som innehåller stegen för att registrera och aktivera grundläggande mobilitet och säkerhet. Mer information finns i [Registrera din mobila enhet med grundläggande mobilitet och säkerhet](enroll-your-mobile-device.md). Till dess att de slutfört registreringen av grundläggande mobilitet och säkerhet i Intune-tjänsten är det begränsat att få åtkomst till e-post, OneDrive och andra tjänster. När du har slutfört registreringen med hjälp av programmet Intune-företagsportalsappen kan de använda tjänsterna och principen tillämpas på deras enhet.

## <a name="step-2-verify-that-your-policy-works"></a>Steg 2: kontrol lera att principen fungerar

När du har skapat en enhets princip kontrollerar du att principen fungerar som förväntat innan du distribuerar den till din organisation.

1. Skriv in i webbläsaren [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .
2. Välj **Visa listan med hanterade enheter**.
3. Kontrol lera status för de användar enheter som har principen installerad. Du **vill att enheterna** ska **hanteras.**
4. Du kan också göra en fullständig eller selektiv rensning på en enhet genom att klicka på **Återställ** eller **ta bort företags data** från knappen **Hantera** när du har valt en enhet. Anvisningar finns i [Rensa en mobil enhet i Microsoft 365.

Steg 3: Distribuera en princip till din organisation

När du har skapat en enhets princip och kontrollerat att den fungerar som förväntat kan du distribuera den till din organisation.

1. Från din webbläsare: [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .
2. Välj den princip som du vill distribuera och välj **redigera** bredvid grupper som **tillämpas på.**
3. Sök efter en grupp att lägga till och klicka på **Välj**.
4. Välj **Stäng** och **ändra inställning.**
5. Välj **Stäng** och **Redigera policy.**

Principen skickas till den mobila enheten för varje användare som principen gäller till nästa gång de loggar in på Microsoft 365 från sin mobila enhet. Om användare inte har använt en princip på sin mobila enhet får de en avisering på sin enhet med steg för att registrera och aktivera den för grundläggande mobilitet och säkerhet. När du har slutfört registreringen tillämpas policyn på deras enhet. Mer information finns i [Registrera din mobila enhet med grundläggande mobilitet och säkerhet](enroll-your-mobile-device.md).

## <a name="step-4-block-email-access-for-unsupported-devices"></a>Steg 4: blockera e-poståtkomst för enheter som inte stöds

För att skydda din organisationsinformation bör du blockera program åtkomst till Microsoft 365-e-post för mobila enheter som inte stöds av grundläggande mobilitet och säkerhet. En lista över tillgängliga enheter finns i [enheter som stöds](https://support.microsoft.com/office/capabilities-of-basic-mobility-and-security-a1da44e5-7475-4992-be91-9ccec25905b0#bkmk_supporteddevices). 

**Så här blockerar du program åtkomst:**

1. Skriv in i webbläsaren [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .
2. Välj **Hantera åtkomst inställningar för hela organisationen**.
3. Om du vill blockera enheter som inte stöds väljer du **blockera** under **om en enhet inte stöds av MDM för Microsoft 365**och väljer sedan **Spara**.

    :::image type="content" source="../../media/basic-mobility-security/bms-5-block-access.png" alt-text="Grundläggande alternativ för mobilitet och säkerhets block":::

## <a name="step-5-choose-security-groups-to-be-excluded-from-conditional-access-checks"></a>Steg 5: Välj säkerhets grupper som ska undantas från kontroller för villkorlig åtkomst

Om du vill undanta vissa personer från kontroller för villkorlig åtkomst på sina mobila enheter och har skapat en eller flera säkerhets grupper för de personerna lägger du till säkerhets grupperna här. Personerna i gruppen har ingen policy för de mobila enheter som stöds. Det här är det rekommenderade alternativet om du inte längre vill använda grundläggande mobilitet och säkerhet i organisationen.

1. Skriv in i webbläsaren [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .

2. Välj **Hantera åtkomst inställningar för hela organisationen**.

    :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Grundläggande mobilitet och säkerhet skapa ett princip alternativ":::

3. Välj **Lägg** till för att lägga till den säkerhets grupp som har användare som du vill undanta från har blockerad åtkomst till Microsoft 365. När en användare har lagts till i listan kan de komma åt Microsoft 365-e-post när de använder en enhet som inte stöds.

4. Välj den säkerhets grupp du vill använda i panelen **Välj grupp** .

5. Markera namnet och **Lägg till**  >  **Spara**.

6. På panelen **enhets åtkomst inställningar för hela organisationen** väljer du **Spara**.

    :::image type="content" source="../../media/basic-mobility-security/bms-8-allow-access.png" alt-text="Grundläggande alternativ för rörlighet och säkerhet Tillåt åtkomst":::

## <a name="what-is-the-impact-of-security-policies-on-different-device-types"></a>Vad är effekten av säkerhets principer för olika typer av enheter?

När du tillämpar en princip på användar enheter varierar påverkan på varje enhet till olika enheter. I tabellen nedan finns exempel på hur principer påverkas av olika enheter.

|**Säkerhets policy**|**Android 4 och senare**|**Samsung KNOX**|**iOS 6 och senare**|**Kommentarer**|
|:-----|:-----|:-----|:-----|:-----|
|Kräv krypterad säkerhets kopiering|Nej|Ja|Ja|en krypterad iOS-säkerhetskopiering krävs.|
|Blockera säkerhets kopiering av moln|Ja|Ja|Ja|Blockera Google-säkerhetskopiering på Android (nedtonad), moln säkerhets kopiering på iOS.|
|Blockera synkronisering av dokument|Nej|Nej|Ja|iOS: blockera dokument i molnet.|
|Blockera Fotosynkronisering |Nej|Nej|Ja|iOS (inbyggt): blockera bild strömmen.|
|Blockera skärmdump |Nej|Ja|Ja|Blockerat vid försök.|
|Blockera video konferens |Nej|Nej|Ja|FaceTime blockeras på iOS, inte på Skype eller andra.|
|Blockera att skicka diagnostikdata |Nej|Ja|Ja|Blockera att skicka Google krasch-rapport på Android.|
|Blockera åtkomst till App Store |Nej|Ja|Ja|App Store-ikonen saknas på Android-startsidan, avaktiverad på Windows, saknas på iOS.|
|Kräv lösen ord för App Store |Nej|Nej|Ja|iOS: lösen ord för iTunes-inköp.|
|Blockera anslutning till flyttbar lagring |Nej|Ja|Saknas|Android: SD-kortet är nedtonat i inställningar, Windows meddelar att användare, installerade appar är inte tillgängliga|
|Blockera Bluetooth-anslutning |Se anteckningar|Se anteckningar|Ja|Det går inte att inaktivera BlueTooth som en inställning för Android. I stället inaktiverar vi alla transaktioner som kräver BlueTooth: avancerad ljud distribution, ljud-och videofjärrkontroll, hands fria enheter, headset, telefon boks åtkomst och seriell port. Ett litet popup-meddelande visas längst ned på sidan när något av dessa används.|

## <a name="what-happens-when-you-delete-a-policy-or-remove-a-user-from-the-policy"></a>Vad händer när du tar bort en princip eller tar bort en användare från policyn?

När du tar bort en princip eller tar bort en användare från en grupp som principen distribuerats till kan princip inställningarna, Microsoft 365 e-postprofil och cachelagrade e-postmeddelanden tas bort från användarens enhet. Se tabellen nedan för att se vad som tas bort för de olika enhets typerna.

|**Vad är borttaget?**|**iOS 6 och senare**|**Android 4 och senare (inklusive Samsung KNOX**|
|:-----|:-----|:----------------------|
|Hanterade e-postprofiler<sup>1</sup>|Ja|Nej|
|Blockera säkerhets kopiering av moln|Ja|Nej|
<sup>1</sup> Om principen distribuerades med alternativet **e-postprofil är** valt, tas Managed e-postprofil och cachelagrade e-postmeddelanden i den profilen bort från användaren.

Principen tas bort från den mobila enheten för varje användare som principen gäller för nästa gång deras enheter checkar in med grundläggande mobilitet och säkerhet. Om du distribuerar en ny princip som gäller för dessa användar enheter uppmanas de att återaktivera grundläggande mobilitet och säkerhet.

Du kan också rensa en enhet helt, eller rensa organisationsinformation från enheten. Mer information finns i [Rensa en mobil enhet i grundläggande mobilitet och säkerhet](wipe-mobile-device.md). 

## <a name="related-topics"></a>Relaterade ämnen

[Översikt över grundläggande mobilitet och säkerhet](overview.md)

[Möjligheter till grundläggande mobilitet och säkerhet](capabilities.md)
