---
title: Konfigurera grundläggande Mobility and Security
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
description: Konfigurera Basic Mobility and Security för att skydda och hantera användarnas mobila enheter genom att utföra åtgärder som att fjärradera en enhet.
ms.openlocfilehash: 02ba28deca6286456af5f87841a741262c1a135d
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52634298"
---
# <a name="set-up-basic-mobility-and-security"></a>Konfigurera grundläggande Mobility and Security

Den inbyggda funktionen Basic Mobility and Security för Microsoft 365 hjälper dig att skydda och hantera användarnas mobila enheter, till exempel iPhone, iPad, Android och Windows telefoner. Du kan skapa och hantera säkerhetsprinciper för enheter, fjärradea enheter och visa detaljerade enhetsrapporter.

Har du frågor? Vanliga frågor och svar om grundläggande rörlighet och säkerhet finns i Vanliga frågor och svar om [grundläggande rörlighet och säkerhet.](frequently-asked-questions.md) Observera att du inte kan använda ett delegerat administratörskonto för att hantera grundläggande rörlighet och säkerhet. Mer information finns i [Partner: Erbjuda delegerad administration.](https://support.microsoft.com/office/partners-offer-delegated-administration-26530dc0-ebba-415b-86b1-b55bc06b073e) 

Enhetshantering är en del av säkerhets- & säkerhets- och efterlevnadscentret, så du måste gå dit för att starta installationen av Basic Mobility and Security.

## <a name="activate-the-basic-mobility-and-security-service"></a>Aktivera tjänsten Basic Mobility and Security

1. Logga in på Microsoft 365 ditt globala administratörskonto.

2. Gå till [Aktivera grundläggande rörlighet och säkerhet.](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx)

   Det kan ta lite tid att aktivera Basic Mobility and Security. När den är klar får du ett e-postmeddelande som förklarar nästa steg att vidta.

## <a name="set-up-mobile-device-management"></a>Konfigurera Hantering av mobila enheter

När tjänsten är klar slutför du konfigurationen genom att följa anvisningarna nedan.

### <a name="step-1-required-configure-domains-for-basic-mobility-and-security"></a>Steg 1: (Obligatoriskt) Konfigurera domäner för grundläggande rörlighet och säkerhet

Om du inte har en egen domän som är kopplad Microsoft 365 eller om du inte hanterar Windows kan du hoppa över det här avsnittet. Annars måste du lägga till DNS-poster för domänen hos din DNS-värd. Om du redan har lagt till posterna, som ett led i att konfigurera Microsoft 365 domän, är allt klart. När du har lagt till posterna Microsoft 365 användare i organisationen som loggar in på sina Windows-enheter med en e-postadress som använder din egen domän omdirigeras för att registrera sig i Basic Mobility and Security.

Behöver du hjälp med att konfigurera posterna? Hitta din domänregistrator och välj registratornamnet för att gå till steg-för-steg-hjälp för att skapa DNS-posten i listan i Lägg till DNS-poster för [att ansluta din domän.](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) Använd de här anvisningarna för att skapa CNAME-poster som [beskrivs i Förenkla Windows registrering utan Azure AD Premium.](/mem/intune/enrollment/windows-enroll#simplify-windows-enrollment-without-azure-ad-premium)

När du har lagt till de två CNAME-posterna går du tillbaka till Säkerhets- och & efterlevnadscenter och går till **Dataförlustskydd**  >  **Enhetshantering för**   att slutföra nästa steg.

### <a name="step-2-required-configure-an-apns-certificate-for-ios-devices"></a>Steg 2: (Obligatoriskt) Konfigurera ett APNs-certifikat för iOS-enheter

För att hantera iOS-enheter som iPad och iPhone måste du skapa ett APNs-certifikat.

1. Logga in på Microsoft 365 ditt globala administratörskonto.

2. Skriv följande i webbläsaren:  [https://protection.office.com](https://protection.office.com/) .

3. Välj  **Dataförlustskydd**   >  **Enhetshantering och** välj **APNs-certifikat för iOS-enheter.**

4. På sidan Apple Push Notification Certificate Inställningar väljer du **Next**.

5. Välj **Ladda ned din CSR-fil** och spara begäran om   certifikatsignering någonstans på datorn som är så bra att du kommer ihåg den. Välj **Nästa.**

6. På sidan Skapa ett APNs-certifikat:

   - Välj Apple APNS-portalen för att öppna Apple Push Certificates-portalen.
   - Logga in med ett Apple-ID.

     > [!IMPORTANT]
     > Använd ett företags-Apple-ID som är kopplat till ett e-postkonto som kommer att finnas kvar i din organisation även om användaren som hanterar kontot slutar. Spara detta ID eftersom du måste använda samma ID när det är dags att förnya certifikatet.

   - Välj Skapa ett certifikat och godkänn användningsvillkoren.
   - Bläddra till den begäran om certifikatsignering som du laddade ned till datorn Microsoft 365 och selectUpload.
   - Ladda ned det APN-certifikat som skapades av Apple Push Certificate-portalen till din dator.

     > [!TIP]
     > Om du har problem med att ladda ned certifikatet kan du uppdatera webbläsaren.

7. Gå tillbaka till Microsoft 365 och välj **Nästa**.

8. Bläddra till det APN-certifikat som du laddade ned från Apple Push Certificates-portalen.

9. Välj  **Slutför**.

### <a name="step-3-recommended-set-up-multi-factor-authentication"></a>Steg 3: (Rekommenderas) Konfigurera multifaktorautentisering

MFA hjälper till att skydda inloggningen på Microsoft 365 registrering av mobila enheter genom att kräva en andra form av autentisering. Användare måste bekräfta ett telefonsamtal, sms eller appmeddelande på sin mobila enhet efter att de har angett lösenordet för sitt arbetskonto. De kan registrera sin enhet efter att den andra formen av autentisering är slutförd. När användarenheter har registrerats i Basic Mobility and Security kan användarna komma åt Microsoft 365 med sina arbetsresurser.

Mer information om hur du aktiverar MFA i Azure AD-portalen finns i [Konfigurera multifaktorautentisering.](../security-and-compliance/set-up-multi-factor-authentication.md)

När du har konfigurerat MFA går du tillbaka till **** säkerhets- och efterlevnadscentret för & och navigerar till Principer för dataförlustskydd Enhetshantering för   >     >  ****   att slutföra nästa steg.

### <a name="step-4-recommended-manage-device-security-policies"></a>Steg 4: (Rekommenderas) Hantera säkerhetsprinciper för enheter

Nästa steg är att skapa och distribuera säkerhetsprinciper för enheter för att skydda dina Microsoft 365 organisationsdata. Du kan till exempel förhindra dataförlust om en användare förlorar sin enhet genom att skapa en princip för att låsa enheter efter fem minuters inaktivitet och rensa enheter efter tre inloggningsfel.

1. Logga in på Microsoft 365 ditt globala administratörskonto.

2. Välj [Aktivera Hantering av mobila enheter](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx). Om tjänsten är aktiverad visas i stället en länk till Hantera enheter under [aktiveringsstegen.](https://admin.microsoft.com/adminportal/home#/MifoDevices)  

3. Gå till **Enhetsprinciper.**

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Principinställningar för grundläggande säkerhet och rörlighet":::

4. Skapa och distribuera säkerhetsprinciper för enheter som är lämpliga för din organisation genom att följa stegen i Skapa säkerhetsprinciper för [enheter i Grundläggande rörlighet och säkerhet.](create-device-security-policies.md)

> [!TIP]
>
> - När du skapar en ny princip kan du ange att principen ska tillåta åtkomst och rapportera principbrott när en användarenhet inte följer principen. På så sätt kan du se hur många mobila enheter som påverkas av principen utan att blockera åtkomst till Microsoft 365.
>
> - Innan du distribuerar en ny princip för alla i organisationen rekommenderar vi att du testar den på enheter som används av ett litet antal användare.
>
> - Innan du distribuerar principer bör du även meddela organisationen hur de kan påverkas av att registrera en enhet i Basic Mobility and Security. Beroende på hur du konfigurerade principerna kan enheter som inte följer principer (icke-kompatibla enheter) blockeras från att komma åt Microsoft 365. Enheter som inte är kompatibla kan också ha installerade appar, foton och annan personlig information som på en registrerad enhet kan tas bort om enheten rensas. Mer information finns i Rensa [en mobil enhet i Grundläggande rörlighet och säkerhet.](wipe-mobile-device.md)

## <a name="make-sure-users-enroll-their-devices"></a>Se till att användarna registrerar sina enheter

När du har skapat och distribuerat en princip för hantering av mobila enheter får alla licensierade Microsoft 365-användare i organisationen som principen gäller ett registreringsmeddelande nästa gång de loggar in på Microsoft 365 från sin mobila enhet. Registreringen och aktiveringen måste slutföras innan de kan komma åt alla e Microsoft 365 och dokument. Mer information finns i [Registrera din mobila enhet med grundläggande rörlighet och säkerhet.](enroll-your-mobile-device.md)

> [!IMPORTANT]
> Om en användares valda språk inte stöds i registreringsprocessen kan användare få registreringsmeddelande och -steg på sina mobila enheter på ett annat språk. Inte alla språk som stöds Microsoft 365 i registreringsprocessen på mobila enheter.

Användare med Android- eller iOS-enheter måste installera Företagsportal-appen som en del av registreringsprocessen.

## <a name="related-content"></a>Relaterat innehåll

[Funktioner för basic mobility and security](capabilities.md) (artikel)\
[Skapa säkerhetsprinciper för enheter i Basic Mobility and Security](create-device-security-policies.md) (artikel)