---
title: Skapa säkerhetsprinciper för enheter i Basic Mobility and Security
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
description: Använd Basic Mobility and Security för att skapa enhetsprinciper som skyddar din organisations information.
ms.openlocfilehash: 5519351db428faa837a63eedb384b42c8d8ee07c
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706328"
---
# <a name="create-device-security-policies-in-basic-mobility-and-security"></a>Skapa säkerhetsprinciper för enheter i Basic Mobility and Security

Du kan använda Grundläggande rörlighet och säkerhet för att skapa enhetsprinciper som skyddar din organisations information Microsoft 365 obehörig åtkomst. Du kan tillämpa principer på alla mobila enheter i organisationen där användaren av enheten har en tillämplig Microsoft 365-licens och har registrerat enheten i Basic Mobility and Security.

## <a name="before-you-begin"></a>Innan du börjar

> [!IMPORTANT]
> Innan du kan skapa en princip för mobila enheter måste du aktivera och konfigurera Grundläggande rörlighet och säkerhet. Mer information finns i Översikt över Grundläggande rörlighet och säkerhet.

- Läs mer om enheter, appar för mobila enheter och säkerhetsinställningar som stöder Basic Mobility and Security. Läs [mer i Funktioner för grundläggande rörlighet och säkerhet.](capabilities.md)
- Skapa säkerhetsgrupper som innehåller Microsoft 365 användare som du vill distribuera principer till och för användare som du kanske vill undanta från att blockeras åtkomst till Microsoft 365. Vi rekommenderar att du innan du distribuerar en ny princip i organisationen testar principen genom att distribuera den till ett litet antal användare. Du kan skapa och använda en säkerhetsgrupp som bara innehåller dig själv eller ett litet Microsoft 365 som kan testa principen åt dig. Mer information om säkerhetsgrupper finns i [Skapa, redigera eller ta bort en säkerhetsgrupp.](../email/create-edit-or-delete-a-security-group.md)
- För att skapa och distribuera principer för grundläggande rörlighet och säkerhet Microsoft 365 användare måste du vara global Microsoft 365 administratör. Mer information finns i [Behörigheter i säkerhets- & Säkerhets- och efterlevnadscenter.](../../security/office-365-security/permissions-in-the-security-and-compliance-center.md)
- Innan du distribuerar principer bör du meddela organisationen hur de kan påverkas av att registrera en enhet i Basic Mobility and Security. Beroende på hur du installerar principerna kan enheter som inte är kompatibla blockeras från att komma åt Microsoft 365 och data, inklusive installerade program, foton och personlig information på en registrerad enhet, och data kan tas bort.

>[!NOTE]
>Principer och åtkomstregler som skapats i Basic Mobility and Security för Microsoft 365 Business Standard åsidosätter Exchange ActiveSync postlådeprinciper för mobila enheter och enhetsåtkomstregler som skapats Exchange administrationscenter. När en enhet har registrerats i Basic Mobility and Security för Microsoft 365 Business Standard ignoreras eventuella Exchange ActiveSync-postlådeprinciper för mobila enheter eller enhetsåtkomstregel som tillämpats på enheten. Mer information om Exchange ActiveSync finns i [Exchange ActiveSync i Exchange Online](/exchange/clients-and-mobile-in-exchange-online/exchange-activesync/exchange-activesync).

## <a name="step-1-create-a-device-policy-and-deploy-to-a-test-group"></a>Steg 1: Skapa en enhetsprincip och distribuera till en testgrupp

Innan du kan starta bör du kontrollera att du har aktiverat och ställt in Basic Mobility and Security. Instruktioner finns i [Översikt över Grundläggande rörlighet och säkerhet.](overview.md)

1. I webbläsaren skriver du [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .

2. Välj **Skapa en princip.**

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Principinställningar för grundläggande rörlighet och säkerhet":::

3. På sidan **Principinställningar** anger du de krav som du vill tillämpa på mobila enheter i organisationen.

4. **Kräv hantering av** e-postprofil: När de är aktiverade anses enheter som inte har en e-postprofil som hanteras av Basic Mobility and Security inte vara kompatibla. En enhet kan inte ha en hanterad e-postprofil när den inte är korrekt riktad, eller om användaren manuellt har konfigurerat e-postkontot på enheten. När du låter inställningen **Inte vara aktiverad** (standard) utvärderas inte den här inställningen för efterlevnad eller icke-efterlevnad. Anvisningar om hur användare kan få kompatibla när det här alternativet väljs finns i Ett [befintligt e-postkonto hittades.](/intune-user-help/existing-company-email-account-found)

5. På sidan **Vill du använda den här principen nu?** väljer du de grupper som du vill använda principen för.

6. Välj **Skapa den här principen.**

Principen skickas till enheten för varje användare. Principen gäller nästa gång de loggar in på Microsoft 365 sin mobila enhet. Om användarna inte har tillämpat en princip på sin mobila enhet tidigare, får de ett meddelande på sin enhet efter att du har distribuerat principen, där det finns instruktioner för att registrera och aktivera Basic Mobility and Security. Mer information finns i [Registrera din mobila enhet med grundläggande rörlighet och säkerhet.](enroll-your-mobile-device.md) Fram till dess att registreringen i Basic Mobility och Security slutförs av Intune-tjänsten är åtkomsten till e-OneDrive och andra tjänster begränsad. När registreringen har slutförts med hjälp Intune-företagsportal-appen kan de använda tjänsterna och principen tillämpas på deras enhet.

## <a name="step-2-verify-that-your-policy-works"></a>Steg 2: Kontrollera att principen fungerar

När du har skapat en enhetsprincip bör du kontrollera att principen fungerar som förväntat innan du distribuerar den till organisationen.

1. I webbläsaren skriver du [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .
2. Välj **Visa listan över hanterade enheter**.
3. Kontrollera statusen för de användarenheter där principen tillämpas. Du vill att **enheternas** status ska **hanteras.**
4. Du kan också göra en fullständig eller selektiv rensning på en enhet genom att klicka på **Fabriksåterställning** eller Ta bort **företagsdata** från knappen Hantera **när** du har valt en enhet. Anvisningar finns i [Rensa en mobil enhet i Microsoft 365.

## <a name="step-3-deploy-a-policy-to-your-organization"></a>Steg 3: Distribuera en princip i organisationen

När du har skapat en enhetsprincip och verifierat att den fungerar som förväntat distribuerar du den till din organisation.

1. Skriv följande i webbläsaren: [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .
2. Välj den princip du vill distribuera och välj **Redigera bredvid** Grupper som **används för.**
3. Sök efter en grupp du vill lägga till och klicka på **Välj**.
4. Välj **Stäng** och **ändra inställning.**
5. Välj **Stäng** och **redigera princip.**

Principen skickas till den mobila enheten för varje användare. Principen gäller för nästa gång de loggar in på Microsoft 365 från sin mobila enhet. Om användarna inte har tillämpat en princip på sin mobila enhet får de ett meddelande på sin enhet med steg för att registrera och aktivera den för Basic Mobility and Security. När registreringen är klar tillämpas principen på deras enhet. Mer information finns i [Registrera din mobila enhet med grundläggande rörlighet och säkerhet.](enroll-your-mobile-device.md)

## <a name="step-4-block-email-access-for-unsupported-devices"></a>Steg 4: Blockera e-poståtkomst för enheter som inte stöds

För att skydda organisationsinformationen bör du blockera appåtkomst till e Microsoft 365 för mobila enheter som inte stöds av Basic Mobility and Security. En lista över enheter som stöds finns i [Enheter som stöds.](../../admin/basic-mobility-security/capabilities.md)

**Så här blockerar du appåtkomst:**

1. I webbläsaren skriver du [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .
2. Välj **Hantera enhetsåtkomstinställningar för hela organisationen**.
3. Om du vill blockera enheter som inte stöds väljer du **Blockera** under Om en enhet inte stöds av **Basic Mobility and Security** för Microsoft 365 och väljer sedan **Spara**.

   :::image type="content" source="../../media/basic-mobility-security/bms-5-block-access.png" alt-text="Alternativet Åtkomst för spärr för enkel rörlighet och säkerhet":::

## <a name="step-5-choose-security-groups-to-be-excluded-from-conditional-access-checks"></a>Steg 5: Välj vilka säkerhetsgrupper som ska undantas från villkorsstyrda åtkomstkontroller

Om du vill exkludera vissa personer från villkorsstyrda åtkomstkontroller på deras mobila enheter och du har skapat en eller flera säkerhetsgrupper för dessa personer lägger du till säkerhetsgrupperna här. Personerna i de här grupperna tillämpar inga principer för sina mobila enheter som stöds. Det här är det rekommenderade alternativet om du inte längre vill använda Grundläggande rörlighet och säkerhet i organisationen.

1. I webbläsaren skriver du [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .

2. Välj **Hantera enhetsåtkomstinställningar för hela organisationen**.

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Skapa ett principalternativ för Basic Mobility and Security":::

3. Välj **Lägg** till för att lägga till säkerhetsgruppen som har användare som du vill utesluta från att ha blockerat åtkomst till Microsoft 365. När en användare har lagts till i den här listan kan de komma åt Microsoft 365 e-post när de använder en enhet som inte stöds.

4. Markera den säkerhetsgrupp som du vill använda i **panelen Välj** grupp.

5. Välj namnet och sedan Lägg **till**  >  **Spara.**

6. På panelen **Organisationsomfattande enhetsåtkomstinställningar** väljer du **Spara**.

   :::image type="content" source="../../media/basic-mobility-security/bms-8-allow-access.png" alt-text="Alternativet Tillåt åtkomst för grundläggande rörlighet och säkerhet":::

## <a name="what-is-the-impact-of-security-policies-on-different-device-types"></a>Hur påverkar säkerhetsprinciperna olika enhetstyper?

När du tillämpar en princip på användarnas enheter varierar påverkan på varje enhet något mellan olika enhetstyper. I följande tabell finns exempel på hur principer påverkar olika enheter.

|**Säkerhetspolicy**|**Android 4 och senare**|**Samsung KNOX**|**iOS 6 och senare**|**Kommentarer**|
|:-----|:-----|:-----|:-----|:-----|
|Kräv krypterad säkerhetskopiering|Nej|Ja|Ja|Krypterad säkerhetskopiering i iOS krävs.|
|Blockera säkerhetskopiering av molnet|Ja|Ja|Ja|Blockera Google-säkerhetskopiering på Android (nedtonad), molnsäkerhetskopia i iOS.|
|Blockera dokumentsynkronisering|Nej|Nej|Ja|iOS: Blockera dokument i molnet.|
|Blockera fotosynkronisering |Nej|Nej|Ja|iOS (inbyggd): Blockera Fotoström.|
|Blockera skärminspelning |Nej|Ja|Ja|Blockeras när du försöker.|
|Blockera videokonferens |Nej|Nej|Ja|FaceTime blockeras på iOS, inte på Skype eller andra.|
|Blockera att diagnostikdata skickas |Nej|Ja|Ja|Blockera att Google kraschar på Android.|
|Blockera åtkomst till appbutik |Nej|Ja|Ja|App Store-ikonen saknas på Android-startsidan, inaktiverad på Windows, saknas på iOS.|
|Kräv lösenord för app store |Nej|Nej|Ja|iOS: Lösenord krävs för iTunes-köp.|
|Blockera anslutning till flyttbara lagringsmedia |Nej|Ja|Uppgift saknas|Android: SD-kort är nedtonat i inställningar, Windows användaren får ett meddelande om att installerade appar inte är tillgängliga|
|Blockera Bluetooth anslutning |Visa anteckningar|Visa anteckningar|Ja|Vi kan inte inaktivera BlueTooth som en inställning i Android. I stället inaktiverar vi alla transaktioner som kräver BlueTooth: Advanced Audio Distribution, Audio/Video Remote Control, handsfree-enheter, headset, Telefon Book Access och Serial Port. Ett litet popup-meddelande visas längst ned på sidan när någon av dessa används.|

## <a name="what-happens-when-you-delete-a-policy-or-remove-a-user-from-the-policy"></a>Vad händer när du tar bort en princip eller tar bort en användare från principen?

När du tar bort en princip eller tar bort en användare från en grupp där principen har distribuerats kan principinställningarna, Microsoft 365-e-postprofilen och cachelagrade e-postmeddelanden tas bort från användarens enhet. Se följande tabell för att se vad som har tagits bort för olika enhetstyper.

|**Vad som har tagits bort**|**iOS 6 och senare**|**Android 4 och senare (inklusive Samsung KNOX**|
|:-----|:-----|:-----|
|Hanterade<sup>e-postprofiler 1</sup>|Ja|Nej|
|Blockera säkerhetskopiering av molnet|Ja|Nej|

<sup>1</sup> Om principen har distribuerats  med alternativet E-postprofil hanteras, tas den hanterade e-postprofilen och cachelagrade e-postmeddelanden i den profilen bort från användarens enhet.

Principen tas bort från den mobila enheten för varje användare. Principen gäller nästa gång deras enheter checkar in med Basic Mobility and Security. Om du distribuerar en ny princip som gäller för dessa användarenheter uppmanas de att registrera sig på nytt i Basic Mobility and Security.

Du kan också rensa en enhet helt eller selektivt rensa organisationsinformation från enheten. Mer information finns i Rensa [en mobil enhet i Grundläggande rörlighet och säkerhet.](wipe-mobile-device.md)

## <a name="related-content"></a>Relaterat innehåll

[Översikt över Grundläggande rörlighet och säkerhet](overview.md) (artikel)\
[Funktioner för basic mobility and security](capabilities.md) (artikel)