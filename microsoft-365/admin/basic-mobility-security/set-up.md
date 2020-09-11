---
title: Konfigurera grundläggande mobilitet och säkerhet
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
description: Konfigurera grundläggande mobilitet och säkerhet för att skydda och hantera användares mobila enheter.
ms.openlocfilehash: cb010668d95e51edfbc913caa308ddd830d674e2
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430322"
---
# <a name="set-up-basic-mobility-and-security"></a>Konfigurera grundläggande mobilitet och säkerhet

Den inbyggda grundläggande mobilitet och säkerhet för Microsoft 365 hjälper dig att skydda och hantera användares mobila enheter som iPhone, iPad, Android och Windows-telefoner. Du kan skapa och hantera säkerhets principer för enheter, rensa en enhet och se detaljerade enhets rapporter.

Har du några frågor? Vanliga frågor och svar om vanliga frågor [och](frequently-asked-questions.md)svar om frågor finns här. Observera att du inte kan använda ett delegerat administratörs konto för att hantera grundläggande mobilitet och säkerhet. Mer information finns i [partners: tillhandahålla delegerad administration](https://support.microsoft.com/office/partners-offer-delegated-administration-26530dc0-ebba-415b-86b1-b55bc06b073e). 

Enhets hantering är en del av säkerhets & Compliance Center så du måste gå dit för att starta MDM-installationen.

## <a name="activate-the-basic-mobility-and-security-service"></a>Aktivera den grundläggande mobilitets-och säkerhets tjänsten

1. Logga in på Microsoft 365 med ditt globala administratörs konto.
    

2. Gå till [aktivera grundläggande mobilitet och säkerhet](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx).
    
    Det kan ta lite tid att aktivera grundläggande mobilitet och säkerhet. När det är klart får du ett e-postmeddelande som förklarar nästa steg.

## <a name="set-up-mobile-device-management"></a>Konfigurera hantering av mobila enheter

När tjänsten är klar följer du anvisningarna nedan för att slutföra konfigurationen.

### <a name="step-1-required-configure-domains-for-mdm"></a>Steg 1: (obligatoriskt) konfigurera domäner för MDM

Om du inte har en egen domän kopplad till Microsoft 365 eller om du inte hanterar Windows-enheter kan du hoppa över det här avsnittet. Annars måste du lägga till DNS-poster för domänen hos DNS-värden. Om du har lagt till posterna som du redan har gjort, är du redo att konfigurera din domän med Microsoft 365. När du har lagt till posterna omdirigeras de Microsoft 365-användare i organisationen som loggar in på sin Windows-enhet med en e-postadress som använder din egen domän för att registrera dig för grundläggande mobilitet och säkerhet.

Behöver du hjälp med att konfigurera posterna? Hitta din domän registrator och välj registratorns namn för att gå till steg-för-steg-hjälp för att skapa DNS-poster i listan i [Lägg till DNS-poster för att ansluta din domän](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider). Använd dessa instruktioner för att skapa CNAME-poster som beskrivs i [förenkla Windows-registrering utan Azure AD Premium](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#simplify-windows-enrollment-without-azure-ad-premium).

När du har lagt till de två CNAME-posterna kan du gå tillbaka till sidan säkerhets & efterlevnad och gå till hantering av **data förlust**  >  **Device management**   för att slutföra nästa steg.

### <a name="step-2-required-configure-an-apns-certificate-for-ios-devices"></a>Steg 2: (obligatoriskt) Konfigurera ett APN-certifikat för iOS-enheter

För att hantera iOS-enheter som iPad och iPhone måste du skapa ett APN-certifikat.

1. Logga in på Microsoft 365 med ditt globala administratörs konto.   

2. I webbläsaren:  [https://protection.office.com](https://protection.office.com/) .  

3. Välj **Hantera data förlust**   >  **Device management**och välj **APNs-certifikat för iOS-enheter**.   

4. På sidan Inställningar för Apple Push Notification-certifikat väljer du **Nästa**.  

5. Välj **Ladda ned din CSR-fil**   och spara begäran om certifikat signering någonstans på din dator som du kommer ihåg. Välj **Nästa**.
    
6. På sidan Skapa ett APN-certifikat:
    
    - Välj Apple-APN-portalen för att öppna Apple Push certificates-portalen.
    - Logga in med ett Apple-ID.

    >[!IMPORTANT]
    >Använd ett Apple-ID för företag som är kopplat till ett e-postkonto som kommer att fortsätta med din organisation även om den användare som hanterar kontot lämnar. Spara detta ID eftersom du måste använda samma ID när det är dags att förnya certifikatet.

    - Välj Skapa ett certifikat och godkänn användnings villkoren.
    
    - Browseto som du laddat ner till din dator från Microsoft 365 och selectUpload.
    
    - Downloadthe APN-certifikat skapat av Apple Push Certificate-portalen till din dator.

    >[!TIP]
    >Om du har problem med att ladda ner certifikatet kan du uppdatera webbläsaren.

7. Gå tillbaka till Microsoft 365 och välj **Nästa**.   

8. Bläddra till det APN-certifikat som du laddade ned från Apple Push certificates-portalen.   

9. Välj  **Slutför**.  

### <a name="step-3-recommended-set-up-multi-factor-authentication"></a>Steg 3: (rekommenderas) Konfigurera multifaktorautentisering

MFA hjälper dig att skydda inloggningen till Microsoft 365 för mobil telefon registrering genom att kräva en andra form av auktorisering. Användare måste bekräfta ett telefonsamtal, SMS eller ett program meddelande på sina mobila enheter när de har angett sitt arbets konto lösen ord korrekt. De kan registrera sin enhet först efter det att den här andra formen av verifikationen är klar. När användar enheter har registrerats i grundläggande mobilitet och säkerhet kan användarna komma åt Microsoft 365-resurser med bara deras arbets konto.

Information om hur du aktiverar MFA i Azure AD-portalen finns i [Konfigurera multifaktorautentisering](https://go.microsoft.com/fwlink/p/?LinkId=519255).

När du har konfigurerat MFA kan du gå tillbaka till säkerhets & Compliance Center och navigera till **Data loss prevention**   >  **Device management**   >  **enhets principer**för hantering av data förlust   för att slutföra nästa steg.

### <a name="step-4-recommended-manage-device-security-policies"></a>Steg 4: (rekommenderas) hantera säkerhets principer för enheter

Nästa steg är att skapa och distribuera säkerhets principer för enheter för att skydda dina Microsoft 365-organisations data. Du kan till exempel förhindra data förlust om en användare förlorar sin enhet genom att skapa en princip för att låsa enheter efter fem minuters inaktivitet och rensa enheter efter tre inloggnings problem.

1. Logga in på Microsoft 365 med ditt globala administratörs konto. 

2. Välj [aktivera hantering av mobila enheter](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx). Om tjänsten är aktive rad kommer du att se en länk för att [Hantera enheter](https://admin.microsoft.com/adminportal/home#/MifoDevices)i stället   .
    
3. Gå till **enhets principer**.

     :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Grundläggande principer för säkerhet och mobilitet":::

4. Skapa och distribuera säkerhets principer för enheter som passar din organisation enligt anvisningarna i [skapa säkerhets principer för enheter i grundläggande mobilitet och säkerhet](create-device-security-policies.md).

>[!TIP]
    - När du skapar en ny princip kanske du vill ange principen för att tillåta åtkomst-och rapport policy brott där en användare het inte är kompatibel med principen. Då kan du se hur många mobila enheter som påverkas av principen utan att blockera åtkomst till Microsoft 365.<br/>-Innan du distribuerar en ny princip till alla i organisationen rekommenderar vi att du testar den på de enheter som används av ett litet antal användare.<br/>-Innan du distribuerar principer kan din organisation ta reda på de potentiella konsekvenserna av att registrera en enhet i grundläggande mobilitet och säkerhet. Beroende på hur du konfigurerar principer kan enheter som inte uppfyller principer (icke-kompatibla enheter) blockeras från att få åtkomst till Microsoft 365. Icke-kompatibla enheter kan också ha installerade appar, foton och annan personlig information som på en registrerad enhet kan tas bort om enheten rensas. Mer information finns i [Rensa en mobil enhet i grundläggande mobilitet och säkerhet](wipe-mobile-device.md).
    
## <a name="make-sure-users-enroll-their-devices"></a>Se till att användarna registrerar sina enheter

När du har skapat och distribuerat en hanterings princip för mobila enheter kan varje licensierad Microsoft 365-användare i organisationen som enhets principen gäller för få ett registrerings meddelande nästa gång de loggar in på Microsoft 365 från sin mobila enhet. De måste slutföra registrerings-och aktiverings stegen innan de kan komma åt Microsoft 365-e-post och dokument. Mer information finns i [Registrera din mobila enhet med grundläggande mobilitet och säkerhet](enroll-your-mobile-device.md).

>[!IMPORTANT]
>Om en användares prioriterade språk inte stöds av registrerings processen kan användarna få ett meddelande om registrering och anvisningar på sina mobila enheter på ett annat språk. Det går för närvarande inte att använda alla språk i Microsoft 365 för att registrera dig på mobila enheter.

Användare med Android-eller iOS-enheter måste installera företagsportalsappen som en del av registrerings processen.

## <a name="related-topics"></a>Relaterade ämnen

[Möjligheter till grundläggande mobilitet och säkerhet](capabilities.md)<br/>
[Skapa säkerhets principer för enheter i grundläggande mobilitet och säkerhet](create-device-security-policies.md)