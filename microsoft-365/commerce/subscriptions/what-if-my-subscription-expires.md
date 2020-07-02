---
title: Vad händer med mina data och min åtkomst när prenumerationen går ut?
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 4436582f-211a-45ec-b72e-33647f97d8a3
description: Läs om vad som händer med dina data när din Microsoft 365 för företag-prenumeration går ut, är inaktiverad eller om du säger upp dig.
ms.openlocfilehash: 2852d2fc301d71131a0adb1c277974e2303dd395
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/01/2020
ms.locfileid: "45016083"
---
# <a name="what-happens-to-my-data-and-access-when-my-microsoft-365-for-business-subscription-ends"></a>Vad händer med mina data och åtkomst när min Microsoft 365 för företag-prenumeration upphör?

Om prenumerationen upphör– antingen för att den går ut eller för att du bestämmer dig för att avbryta – går din åtkomst till Microsoft 365-tjänster, program och kunddata igenom flera tillstånd innan prenumerationen är helt inaktiverad eller *avetableras*. Om du är medveten om den här utvecklingen är du bättre rustad att återställa prenumerationen till ett aktivt tillstånd innan det är för sent, eller – om du lämnar Microsoft 365 – säkerhetskopiera dina data innan de tas bort.

Läs igenom den här viktiga informationen innan du kontaktar [Microsoft 365-supporten](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products).
  
## <a name="what-happens-to-data-when-a-subscription-expires"></a>Vad händer med data när en prenumeration går ut? 

- Om din prenumeration går ut går den igenom följande steg: Utgånget / Inaktiverat/ Avetablerat. Steget Utgånget startar omedelbart efter att prenumerationen har nått sitt slutdatum.
- Om du inaktiverar återkommande fakturering på din årsprenumeration går den igenom samma faser som en prenumeration som har upphört att gälla. Den första fasen startar är årsdagen av den årliga prenumerationen, inte från det datum då du inaktiverade prenumerationens återkommande faktureringsinställning.
- Om du avbryter din månadsprenumeration inaktiveras den omedelbart (vid tidpunkten för avbokningen). Det innebär att användarna förlorar åtkomsten till Microsoft 365-tillgångarna omedelbart och endast administratörer har åtkomst till data under de kommande 90 dagarna.

I följande tabell förklaras vad du kan förvänta dig när en betald Microsoft 365 för företag-prenumeration upphör att gälla.

| **Aktiva**                                                             | **Utgångna <br/> (30 \* dagar)**                                                | **Inaktiverad <br/> (90 \* dagar)**                                               | **Avetablerade**                                                                         |
|------------------------------------------------------------------------|------------------------------------------------------------------------------|------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------|
| *Data som är tillgängliga för alla*                                               | *Data som är tillgängliga för alla*                                                     | *Data som endast är tillgängliga för administratörer*                                             | **Data borttagna <br/> Azure Active Directory tas bort, om den inte används av andra tjänster** |
| Användare har normal åtkomst till Microsoft 365-, data- och Office-program  | Användare har normal åtkomst till Microsoft 365, filer och program              | Användare kan inte komma åt Microsoft 365, filer eller program                        | Användare kan inte komma åt Microsoft 365, filer eller program                                     |
| Administratörer har normal åtkomst till Microsoft 365-, data- och Office-program | Administratörer kan komma åt administrationscentret                                           | Administratörer kan komma åt administrationscentret, men kan inte tilldela licenser till användare       | Administratörer kan komma åt administrationscentret för att köpa och hantera andra prenumerationer             |
|                                                                        | Globala administratörer eller faktureringsadministratörer kan återaktivera prenumerationen i administrationscentret | Globala administratörer eller faktureringsadministratörer kan återaktivera prenumerationen i administrationscentret |                                                                                           |

*För de flesta erbjudanden, i de flesta länder och regioner.
  
> [!NOTE]
> **Vad är "kunddata"?** Kunddata, enligt definitionen i Villkoren för [Microsoft Online-tjänster,](https://go.microsoft.com/fwlink/p/?LinkId=613649)avser all data, inklusive alla text-, ljud- eller bildfiler som tillhandahålls Microsoft av eller på uppdrag av kunden genom kundens användning av Microsoft 365-tjänster. Mer information om skydd av kunddata finns i [Komma igång med Microsoft Service Trust Portal](https://docs.microsoft.com/microsoft-365/compliance/get-started-with-service-trust-portal).

## <a name="what-happens-if-i-cancel-a-subscription"></a>Vad händer om jag avbryter en prenumeration?

Om du avbryter prenumerationen före terminsslutdatumet hoppar prenumerationen över det utgångna tillståndet och flyttar direkt till det inaktiverade tillståndet, vilket är 90 dagar för de flesta prenumerationer, i de flesta länder och regioner. Vi rekommenderar att du [säkerhetskopierar dina data](back-up-data-before-switching-plans.md) innan du avbryter, men som administratör kan du fortfarande komma åt och säkerhetskopiera data för din organisation medan den är inaktiverad. Alla kunddata som du lämnar efter dig kan raderas efter 90 dagar och raderas senast 180 dagar efter avbokningen.
  
Det här kan du förvänta dig för dig och dina användare om du avbryter en prenumeration.
  
- **Åtkomst till administratör** Administratörer kan fortfarande logga in och komma åt administrationscentret och köpa andra prenumerationer efter behov. Som global administratör eller faktureringsadministratör har du 90 dagar på dig att [återaktivera prenumerationen](reactivate-your-subscription.md) med alla data intakta.

- **Användaråtkomst** Användarna kan inte använda tjänster som OneDrive för företag eller komma åt kunddata, till exempel e-post eller dokument på gruppwebbplatser. Office-program, som Word och Excel, flyttas så småningom till ett skrivskyddat läge med nedsatt funktionalitet och [meddelanden om ej licensierad produkt](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380.aspx) visas.

Mer information om hur du avbryter finns i [Avbryt prenumerationen](cancel-your-subscription.md).
  
> [!IMPORTANT]
> Om du vill att dina prenumerationsdata ska tas bort innan den typiska inaktiverade perioden är över kan du [stänga kontot](../close-your-account.md).
  
## <a name="what-are-my-options-if-my-subscription-is-about-to-expire"></a>Vilka alternativ har mina alternativ om min prenumeration håller på att löpa ut?

När en prenumeration är aktiv har du och dina slutanvändare normal åtkomst till dina data, tjänster som e-post och OneDrive för företag och Office-program. Som administratör får du en serie aviseringar via e-post och i administrationscentret när prenumerationen närmar sig utgångsdatumet.
  
Innan prenumerationen når sitt utgångsdatum har du några alternativ:

::: moniker range="o365-worldwide"
  
- **Aktivera återkommande fakturering för prenumerationen.**

  - Om **Återkommande fakturering** redan är aktiverat behöver du inte vidta några åtgärder. Din prenumeration faktureras automatiskt och du debiteras ytterligare ett år eller en månad, beroende på din aktuella betalningsfrekvens. Om du av någon anledning har **inaktiverat Återkommande fakturering** kan du alltid [aktivera Återkommande fakturering igen.](renew-your-subscription.md)

  - Om du har köpt Microsoft 365 Apps för företag med ett förbetalt kort kan du [aktivera Återkommande fakturering](renew-your-subscription.md) för din prenumeration.

  - Om du är en open volume licensing-kund med en förbetald, ettårig prenumeration kontaktar du din partner för att köpa en ny produktnyckel. Du får instruktioner via e-post för att aktivera din nyckel i [Servicecenter för volymlicensiering](https://go.microsoft.com/fwlink/p/?LinkID=282016). Mer information om hur du hittar en ny partner eller den partner du har arbetat med tidigare finns i [Hitta din partner eller återförsäljare.](../../admin/manage/find-your-partner-or-reseller.md)

  - Om du har Microsoft 365 Apps för företag läser du [Hantera återkommande fakturering för din prenumeration](renew-your-subscription.md).

- **Låt prenumerationen löpa ut.**

  - Om du betalar med kreditkort eller faktura och inte vill fortsätta prenumerationen [stänger du av Återkommande fakturering](renew-your-subscription.md). Prenumerationen upphör på utgångsdatumet och du kan ignorera alla relaterade e-postmeddelanden.

  - Om du är en open volume licensing-kund som arbetar med en partner kan du låta prenumerationen löpa ut genom att inte vidta några åtgärder.

  - Om du är Office 365 Small Business Premium-kund och har förbetalt för Office 365 och aktiverat den med en produktnyckel kan du låta prenumerationen löpa ut genom att inte vidta några åtgärder.

- **Avbryt innan prenumerationen går ut.** Mer information finns i [Avbryt prenumerationen](cancel-your-subscription.md).
  
::: moniker-end

::: moniker range="o365-germany"
  
- **Hantera återkommande fakturering för prenumerationen.**

  - Om **Återkommande fakturering** redan är aktiverat behöver du inte vidta några åtgärder. Din prenumeration faktureras automatiskt och du debiteras ytterligare ett år eller en månad, beroende på din aktuella betalningsfrekvens. Om du av någon anledning har **inaktiverat Återkommande fakturering** kan du alltid [aktivera Återkommande fakturering igen.](renew-your-subscription.md)

  - Om du har köpt Microsoft 365 Apps för företag med ett förbetalt kort kan du [aktivera Återkommande fakturering](renew-your-subscription.md) för din prenumeration.

  - Om du är en open volume licensing-kund med en förbetald, ettårig prenumeration kontaktar du din partner för att köpa en ny produktnyckel. Du får instruktioner via e-post för att aktivera din nyckel i [Servicecenter för volymlicensiering](https://go.microsoft.com/fwlink/p/?LinkID=282016). Mer information om hur du hittar en ny partner eller den partner du har arbetat med tidigare finns i [Hitta din partner eller återförsäljare.](../../admin/manage/find-your-partner-or-reseller.md)

  - Om du har Microsoft 365 Apps för företag läser du [Förnya din prenumeration](renew-your-subscription.md).

- **Låt prenumerationen löpa ut.**

  - Om du betalar med kreditkort eller faktura och inte vill fortsätta prenumerationen [stänger du av Återkommande fakturering](renew-your-subscription.md). Prenumerationen upphör att gälla på utgångsdatumet och du kan ignorera alla relaterade e-postmeddelanden.

  - Om du är en open volume licensing-kund som arbetar med en partner kan du låta prenumerationen löpa ut genom att inte vidta några åtgärder.

  - Om du är Office 365 Small Business Premium-kund och har förbetalt för Office 365 och aktiverat den med en produktnyckel kan du låta prenumerationen löpa ut genom att inte vidta några åtgärder.

- **Avbryt innan prenumerationen går ut.** Mer information finns i [Avbryt prenumerationen](cancel-your-subscription.md).
  
::: moniker-end

::: moniker range="o365-21vianet"
  
- **Förnya prenumerationen.** Om **Återkommande fakturering** redan är aktiverat behöver du inte vidta några åtgärder. Din prenumeration faktureras automatiskt och du debiteras ytterligare ett år eller en månad, beroende på din aktuella betalningsfrekvens. Om du av någon anledning har **inaktiverat Återkommande fakturering** kan du alltid [aktivera Återkommande fakturering igen.](renew-your-subscription.md)

- **Låt prenumerationen löpa ut.** Om du betalar med kreditkort eller faktura och inte vill fortsätta prenumerationen [stänger du av Återkommande fakturering](renew-your-subscription.md). Prenumerationen upphör att gälla på utgångsdatumet och du kan ignorera alla relaterade e-postmeddelanden.

- **Avbryt innan prenumerationen går ut.** Mer information finns i [Avbryt prenumerationen](cancel-your-subscription.md).

::: moniker-end

## <a name="what-happens-after-my-subscription-expires"></a>Vad händer när min prenumeration har gått ut?
Om du låter prenumerationen gå ut går den igenom flera lägen innan den tas bort. Detta ger dig, som administratör, tid att återaktivera om du vill fortsätta tjänsten eller att säkerhetskopiera dina data om du bestämmer dig för att du inte längre vill ha prenumerationen.
  
Det här kan du förvänta dig när prenumerationen är i varje delstat.
  
### <a name="state-expired"></a>Tillstånd: Utgånget
  
::: moniker range="o365-worldwide"

 **Vad du kan förvänta dig:** Tillståndet för utgånget gälla i 30 dagar för de flesta prenumerationer, inklusive prenumerationer som köpts via [Microsoft Open](https://go.microsoft.com/fwlink/p/?LinkID=613298), i de flesta länder och regioner. För volymlicensieringsprodukter, med undantag för Microsoft Open, varar tillståndet för utgånget 90 dagar.

::: moniker-end

::: moniker range="o365-germany"

 **Vad du kan förvänta dig:** Tillståndet för utgånget gälla i 30 dagar för de flesta prenumerationer, inklusive prenumerationer som köpts via [Microsoft Open](https://go.microsoft.com/fwlink/p/?LinkID=613298), i de flesta länder och regioner. För volymlicensieringsprodukter, med undantag för Microsoft Open, varar tillståndet för utgånget 90 dagar.

::: moniker-end

::: moniker range="o365-21vianet"

 **Vad du kan förvänta dig:** Tillståndet för utgånget är 30 dagar för de flesta prenumerationer, i de flesta länder och regioner.

::: moniker-end

I det här läget har användarna normal åtkomst till Microsoft 365-portalen, Office-program och tjänster som e-post och SharePoint Online.
  
Som administratör har du fortfarande åtkomst till administrationscentret. Oroa dig inte – globala administratörer eller faktureringsadministratörer kan [återaktivera prenumerationen](reactivate-your-subscription.md) och fortsätta använda Microsoft 365. Om du inte återaktiverar [säkerhetskopierar du dina data](back-up-data-before-switching-plans.md).
  
### <a name="state-disabled"></a>Tillstånd: Inaktiverat
  
::: moniker range="o365-worldwide"

 **Vad du kan förvänta dig:** Om du inte återaktiverar prenumerationen när den är i utgånget tillstånd flyttas den till ett inaktiverat tillstånd, som varar i 90 dagar för de flesta prenumerationer, i de flesta länder och regioner. För volymlicensieringsprodukter varar det inaktiverade tillståndet 30 dagar.

::: moniker-end

::: moniker range="o365-germany"

 **Vad du kan förvänta dig:** Om du inte återaktiverar prenumerationen när den är i utgånget tillstånd flyttas den till ett inaktiverat tillstånd, som varar i 90 dagar för de flesta prenumerationer, i de flesta länder och regioner. För volymlicensieringsprodukter varar det inaktiverade tillståndet 30 dagar.

::: moniker-end

::: moniker range="o365-21vianet"

 **Vad du kan förvänta dig:** Om du inte återaktiverar prenumerationen medan den är i utgånget tillstånd flyttas den till ett inaktiverat tillstånd, vilket är 90 dagar för de flesta prenumerationer, i de flesta länder och regioner.

::: moniker-end

::: moniker range="o365-worldwide"

I det här läget minskar åtkomsten avsevärt. Användarna kan inte logga in eller komma åt tjänster som e-post eller SharePoint Online. Office-program flyttas så småningom till ett skrivskyddat, reducerat funktionsläge och visar [meddelanden om olicensierad produkt](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380.aspx). Du kan fortfarande logga in och komma till administrationscentret, men kan inte tilldela licenser till användare. Dina kunddata, inklusive all användardata, e-post och filer på gruppwebbplatser, är endast tillgänglig för dig och andra administratörer.

::: moniker-end

Som global administratör eller faktureringsadministratör kan du [återaktivera prenumerationen](reactivate-your-subscription.md) och fortsätta använda Microsoft 365 med alla dina kunddata intakta. Om du väljer att inte återaktivera [säkerhetskopierar du dina data](back-up-data-before-switching-plans.md).

### <a name="state-deprovisioned"></a>Stat: Avetablerat
  
 **Vad du kan förvänta dig:** Om du inte återaktiverar prenumerationen medan den är i respit eller inaktiveras, avetableras prenumerationen.
  
Administratörer och användare har inte längre åtkomst till de tjänster eller Office-program som medföljde prenumerationen. Alla kunddata – från användardata till dokument och e-post – tas bort permanent och kan inte kan gå attuppa sig på.
  
Nu kan du inte återaktivera prenumerationen. Som global administratör eller faktureringsadministratör kan du dock fortfarande komma åt administrationscentret för att hantera andra prenumerationer eller köpa nya prenumerationer som uppfyller dina affärsbehov.
  
> [!NOTE]
> Om du lägger till en ny prenumeration av samma typ som har avetablerats återställs inte de data som var associerade med prenumerationen avetablerade.

### <a name="what-happens-when-my-trial-ends"></a>Vad händer när min utvärderingsversion avslutas?

När utvärderingsperioden är kan du inte fortsätta använda Microsoft 365 utan kostnad. Du har några alternativ:

::: moniker range="o365-worldwide"
- **Köp Microsoft 365.** När utvärderingsperioden löper ut flyttas den till en respitperiod, vilket ger dig ytterligare 30 dagar (för de flesta utvärderingsversioner, i de flesta länder och regioner) för att köpa Microsoft 365. Mer information om hur du konverterar utvärderingsversionen till en betald prenumeration finns i [Köpa din utvärderingsversion av Microsoft 365 för företag](../buy-a-subscription-from-your-free-trial.md).

::: moniker-end

::: moniker range="o365-germany"
- **Köp Microsoft 365.** När utvärderingsperioden löper ut flyttas den till en respitperiod, vilket ger dig ytterligare 30 dagar (för de flesta utvärderingsversioner, i de flesta länder och regioner) för att köpa Microsoft 365. Mer information om hur du konverterar utvärderingsversionen till en betald prenumeration finns i [Köpa din utvärderingsversion av Microsoft 365 för företag](../buy-a-subscription-from-your-free-trial.md).

::: moniker-end

::: moniker range="o365-21vianet"
- **Köp Office 365.** När utvärderingsperioden går ut flyttas den till en respitperiod, vilket ger dig ytterligare 30 dagar (för de flesta utvärderingsversioner, i de flesta länder och regioner) för att köpa Office 365. Mer information om hur du konverterar utvärderingsversionen till en betald prenumeration finns i [Köp eller prova prenumerationer för Office 365 som drivs av 21Vianet](../../admin/services-in-china/buy-or-try-subscriptions.md).

::: moniker-end

- **Förläng din rättegång.** Behöver du mer tid att utvärdera Microsoft 365? I vissa fall kan du [förlänga din rättegång](../extend-your-trial.md).

- **Avbryt utvärderingsversionen eller låt den löpa ut.** Om du bestämmer dig för att inte köpa Microsoft 365 kan du låta utvärderingsversionen löpa ut eller [avbryta den](cancel-your-subscription.md). Säkerhetskopiera alla data som du vill behålla. Strax efter respitperioden på 30 dagar raderas din utvärderingskontoinformation och dina data permanent.

> [!NOTE]
> Informationen på den här sidan omfattas av [Microsofts policyfriskrivnings- och ändringsmeddelande](https://go.microsoft.com/fwlink/p/?LinkId=613651). Gå tillbaka till den här webbplatsen regelbundet för att granska eventuella ändringar.

## <a name="related-articles"></a>Relaterade artiklar 

[Avbryt prenumerationen](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/cancel-your-subscription)

[Förnya Microsoft 365 för företag](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/renew-your-subscription)

[Återaktivera prenumerationen](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/reactivate-your-subscription)