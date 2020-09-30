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
description: Lär dig vad som händer med dina data när prenumerationen på Microsoft 365 för företag upphör, är inaktive rad eller om du avbryter.
ms.openlocfilehash: 2c8b21274d7e3e776e62a9a185309d6e742ac2b3
ms.sourcegitcommit: 6b1d0bea86ced26cae51695c0077adce8bcff3c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/30/2020
ms.locfileid: "48309188"
---
# <a name="what-happens-to-my-data-and-access-when-my-microsoft-365-for-business-subscription-ends"></a>Vad händer med mina data och åtkomst när min Microsoft 365 för företag-prenumeration går ut?

Om ditt abonnemang går ut – antingen för att det upphör att gälla, eller om du väljer Avbryt, kommer din åtkomst till Microsoft 365-tjänster, program och kunddata att gå igenom flera tillstånd innan abonnemanget är helt inaktiverat eller *avetablerats*. Om du känner till den här statusen är du bättre utrustad för att återställa ditt abonnemang till ett aktivt tillstånd innan det är för sent, eller – om du lämnar Microsoft 365 – säkerhetskopiera dina data innan de tas bort.

Läs igenom den viktiga informationen innan du kontaktar [Microsoft 365 support](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products).
  
## <a name="what-happens-to-data-when-a-subscription-expires"></a>Vad händer med data när ett abonnemang går ut?

- Om ditt abonnemang går ut går det igenom följande steg: har upphört att gälla/avaktiverats/avetablerats. Det upphörde stadiet startar omedelbart efter att prenumerationen har nått sitt slutdatum.
- Om du stänger av den återkommande faktureringen för ett års abonnemang går det igenom samma steg som ett förfallet abonnemang. Den första fasen börjar är årsdagen för det årliga abonnemanget, som inte börjar på det datum då du stängde av abonnemanget.
- Om du avbryter ditt månads abonnemang inaktive ras det omedelbart (vid avbrotts datumet). Det innebär att användarna förlorar åtkomsten till Microsoft 365-till gångar omedelbart och bara administratörer har till gång till informationen för de kommande 90 dagarna.

I följande tabell förklaras vad du kan förvänta dig när en betald Microsoft 365 för företag-prenumeration upphör.

| **Aktiva**                                                             | **Upphört <br/> (30 dagar \* )**                                                | **Inaktive rad <br/> (90 dagar \* )**                                               | **Återkallad**                                                                         |
|------------------------------------------------------------------------|------------------------------------------------------------------------------|------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------|
| *Data tillgängliga för alla*                                               | *Data tillgängliga för alla*                                                     | *Endast tillgängliga för administratörer*                                             | **Data som tagits bort <br/> Azure Active Directory tas bort, om de inte används av andra tjänster** |
| Användare har normal åtkomst till Microsoft 365, filer och program   | Användare har normal åtkomst till Microsoft 365, filer och program              | Användarna kan inte komma åt Microsoft 365, filer eller program                        | Användarna kan inte komma åt Microsoft 365, filer eller program                                     |
| Administratörer har normal åtkomst till Microsoft 365-, data-och Office-program | Administratörer kan komma åt administrations centret                                           | Administratörer har åtkomst till administrations centret men kan inte tilldela licenser till användare       | Administratörer kan komma åt administrations centret för att köpa och hantera andra prenumerationer             |
|                                                                        | Global administratör eller fakturerings administratörer kan återaktivera prenumerationen i administrations centret | Global administratör eller fakturerings administratörer kan återaktivera prenumerationen i administrations centret |                                                                                           |

* För de flesta erbjudanden, i de flesta länder och regioner.
  
> [!NOTE]
> **Vad är "kunddata"?** Kunddata, enligt definitionen i [Microsofts online tjänst villkor](https://go.microsoft.com/fwlink/p/?LinkId=613649), syftar på alla data, inklusive all text-, ljud-eller bildfiler som tillhandahålls av Microsoft av, eller för kunden, via Microsofts 365-tjänster. Mer information om hur du skyddar Kunddata finns i [komma igång med Microsoft Service Trust-portalen](https://docs.microsoft.com/microsoft-365/compliance/get-started-with-service-trust-portal).

## <a name="what-happens-if-i-cancel-a-subscription"></a>Vad händer om jag avbryter en prenumeration?

Om du avbryter prenumerationen före dess slutdatum hoppar prenumerationen över det upphört läget och flyttas direkt till inaktiverat läge, som är 90 dagar för de flesta abonnemangen, i de flesta länder och regioner. Vi rekommenderar att du [säkerhetskopierar dina data](back-up-data-before-switching-plans.md) innan du annullerar dem, men som administratör kan du ändå komma åt och säkerhetskopiera data för organisationen när den är inaktive rad. Alla kunddata som du lämnar efter kan tas bort efter 90 dagar och kommer inte att tas bort senare än 180 dagar efter annullering.
  
Det här kan du förvänta dig och dina användare om du avbryter ett abonnemang.
  
- **Administratörs åtkomst** Administratörer kan fortfarande logga in och komma åt administrations centret och köpa andra abonnemang efter behov. Som global administratör eller faktureringsadministratör har du 90 dagar på dig att [återaktivera prenumerationen](reactivate-your-subscription.md) med alla data intakta.

- **Användar åtkomst** Användarna kan inte använda tjänster som OneDrive för företag eller komma åt kunddata, till exempel e-post eller dokument på grupp webbplatser. Office-program, som Word och Excel, flyttas så småningom till ett skrivskyddat läge med nedsatt funktionalitet och [meddelanden om ej licensierad produkt](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380.aspx) visas.

Information om hur du avbryter finns i [avbryta prenumerationen](cancel-your-subscription.md).
  
> [!IMPORTANT]
> Om du vill att dina prenumerations data ska tas bort innan den normala inaktiverade perioden är över kan du [avsluta ditt konto](../close-your-account.md).
  
## <a name="what-are-my-options-if-my-subscription-is-about-to-expire"></a>Vilka är mina alternativ om min prenumeration håller på att gå ut?

När ett abonnemang är aktivt har du och dina slutanvändare normal åtkomst till dina data, tjänster som e-post och OneDrive för företag och Office-program. Som administratör får du en serie aviseringar via e-post och i administrations centret när ditt abonnemang närmar sig.
  
Innan prenumerationen går ut kan du göra följande:

::: moniker range="o365-worldwide"
  
- **Aktivera automatisk fakturering för abonnemanget.**

  - Om **du redan har aktiverat** automatisk förnyelse behöver du inte göra något. Ditt abonnemang debiteras automatiskt och du debiteras för ytterligare ett år eller en månad, beroende på din aktuella betalnings frekvens. Om **du av någon anledning har aktiverat automatisk** förnyelse kan du aktivera automatisk [återställning](renew-your-subscription.md).

  - Om du har köpt Microsoft 365-appar för företag med ett förbetalt kort kan du [Aktivera](renew-your-subscription.md) automatisk förnyelse av din prenumeration.

  - Om du är Open Volume Licensing Customer med ett förbetalt abonnemang på ett år kontaktar du din partner för att köpa en ny produkt. Du får instruktioner via e-post för att aktivera din-prenumeration i [Volume Licensing Service Center](https://go.microsoft.com/fwlink/p/?LinkID=282016). Information om hur du hittar en ny partner, eller partnern som du har arbetat med tidigare finns i [hitta din partner eller åter försäljare](../../admin/manage/find-your-partner-or-reseller.md).

  - Om du har Microsoft 365-appar för företag läser du [hantera återkommande fakturering för din prenumeration](renew-your-subscription.md).

- **Låt prenumerationen gå ut.**

  - Om du betalar med kredit kort eller faktura och du inte vill fortsätta med ditt abonnemang bör du [Aktivera automatisk debitering](renew-your-subscription.md). Ditt-abonnemang upphör att gälla efter förfallo datum och du kan bortse från alla relaterade e-postaviseringar.

  - Om du är en öppen volym licens kund som arbetar med en partner kan du låta prenumerationen upphöra genom att inte vidta någon åtgärd.

  - Om du är en Office 365 Small Business Premium-kund och du har betalat för Office 365 och aktiverat det med en produkt nyckeln kan du låta prenumerationen gå ut genom att inte vidta någon åtgärd.

- **Avbryt innan abonnemanget går ut.** Mer information finns i [avbryta prenumerationen](cancel-your-subscription.md).
  
::: moniker-end

::: moniker range="o365-germany"
  
- **Hantera återkommande fakturering för abonnemanget.**

  - Om **du redan har aktiverat** automatisk förnyelse behöver du inte göra något. Ditt-abonnemang debiteras automatiskt och du debiteras under ytterligare ett år eller en månad, beroende på din aktuella betalnings frekvens. Om **du av någon anledning har aktiverat automatisk** förnyelse kan du aktivera automatisk [återställning](renew-your-subscription.md).

  - Om du har köpt Microsoft 365-appar för företag med ett förbetalt kort kan du [Aktivera](renew-your-subscription.md) automatisk förnyelse av din prenumeration.

  - Om du är Open Volume Licensing Customer med ett förbetalt abonnemang på ett år kontaktar du din partner för att köpa en ny produkt. Du får instruktioner via e-post för att aktivera din-prenumeration i [Volume Licensing Service Center](https://go.microsoft.com/fwlink/p/?LinkID=282016). Information om hur du hittar en ny partner, eller partnern som du har arbetat med tidigare finns i [hitta din partner eller åter försäljare](../../admin/manage/find-your-partner-or-reseller.md).

  - Om du har Microsoft 365-appar för företag läser du [förnya din prenumeration](renew-your-subscription.md).

- **Låt prenumerationen gå ut.**

  - Om du betalar med kredit kort eller faktura och du inte vill fortsätta med ditt abonnemang bör du [Aktivera automatisk debitering](renew-your-subscription.md). Ditt-abonnemang upphör att gälla på utgångs datumet och du kan bortse från alla relaterade e-postaviseringar.

  - Om du är en öppen volym licens kund som arbetar med en partner kan du låta prenumerationen upphöra genom att inte vidta någon åtgärd.

  - Om du är en Office 365 Small Business Premium-kund och du har betalat för Office 365 och aktiverat det med en produkt nyckeln kan du låta prenumerationen gå ut genom att inte vidta någon åtgärd.

- **Avbryt innan abonnemanget går ut.** Mer information finns i [avbryta prenumerationen](cancel-your-subscription.md).
  
::: moniker-end

::: moniker range="o365-21vianet"
  
- **Förnya prenumerationen.** Om **du redan har aktiverat** automatisk förnyelse behöver du inte göra något. Ditt-abonnemang debiteras automatiskt och du debiteras under ytterligare ett år eller en månad, beroende på din aktuella betalnings frekvens. Om **du av någon anledning har aktiverat automatisk** förnyelse kan du aktivera automatisk [återställning](renew-your-subscription.md).

- **Låt prenumerationen gå ut.** Om du betalar med kredit kort eller faktura och du inte vill fortsätta med ditt abonnemang bör du [Aktivera automatisk debitering](renew-your-subscription.md). Ditt-abonnemang upphör att gälla på utgångs datumet och du kan bortse från alla relaterade e-postaviseringar.

- **Avbryt innan abonnemanget går ut.** Mer information finns i [avbryta prenumerationen](cancel-your-subscription.md).

::: moniker-end

## <a name="what-happens-after-my-subscription-expires"></a>Vad händer när min prenumeration går ut?
Om du låter prenumerationen gå ut går den igenom flera lägen innan den slutligen tas bort. Det ger dig som administratör, tid att återaktivera om du vill fortsätta med tjänsten, eller om du vill säkerhetskopiera dina data om du inte längre vill ha abonnemanget.
  
Det här kan du förvänta dig av att ditt abonnemang är i de olika lägena.
  
### <a name="state-expired"></a>Status: har gått ut
  
::: moniker range="o365-worldwide"

 **Vad du kan förvänta dig:** Det upphörde att gälla för 30 dagar för de flesta abonnemang, inklusive prenumerationer som köpts via [Microsoft Open](https://go.microsoft.com/fwlink/p/?LinkID=613298), i de flesta länder och regioner. För volym licens produkter, förutom Microsoft Open, varar det upphört att gälla 90 dagar.

::: moniker-end

::: moniker range="o365-germany"

 **Vad du kan förvänta dig:** Det upphörde att gälla för 30 dagar för de flesta abonnemang, inklusive prenumerationer som köpts via [Microsoft Open](https://go.microsoft.com/fwlink/p/?LinkID=613298), i de flesta länder och regioner. För volym licens produkter, förutom Microsoft Open, varar det upphört att gälla 90 dagar.

::: moniker-end

::: moniker range="o365-21vianet"

 **Vad du kan förvänta dig:** Det förfallna tillståndet är 30 dagar för de flesta prenumerationer, i de flesta länder och regioner.

::: moniker-end

I det här läget har användare normalt åtkomst till Microsoft 365-portalen, Office-program och tjänster som e-post och SharePoint Online.
  
Som administratör har du fortfarande till gång till administrations centret. Oroa dig inte – globala eller fakturerings administratörer kan [återaktivera prenumerationen](reactivate-your-subscription.md) och fortsätta använda Microsoft 365. Om du inte återaktiverar kan du [säkerhetskopiera dina data](back-up-data-before-switching-plans.md).
  
### <a name="state-disabled"></a>Tillstånd: inaktiverat
  
::: moniker range="o365-worldwide"

 **Vad du kan förvänta dig:** Om du inte återaktiverar prenumerationen när den befinner sig i tillståndet upphörde, flyttas den till ett inaktivt tillstånd som varar för 90 dagar för de flesta prenumerationer, i de flesta länder och regioner. För volym licens produkter är det inaktiverade tillståndet 30 dagar.

::: moniker-end

::: moniker range="o365-germany"

 **Vad du kan förvänta dig:** Om du inte återaktiverar prenumerationen när den befinner sig i tillståndet upphörde, flyttas den till ett inaktivt tillstånd som varar för 90 dagar för de flesta prenumerationer, i de flesta länder och regioner. För volym licens produkter är det inaktiverade tillståndet 30 dagar.

::: moniker-end

::: moniker range="o365-21vianet"

 **Vad du kan förvänta dig:** Om du inte återaktiverar prenumerationen när den befinner sig i tillståndet upphörde flyttas den till ett inaktivt tillstånd, som är 90 dagar för de flesta prenumerationer, i de flesta länder och regioner.

::: moniker-end

::: moniker range="o365-worldwide"

I det här läget minskar din åtkomst markant. Användarna kan inte logga in, eller komma åt tjänster som e-post eller SharePoint Online. Office-program kan till och med växla till skrivskyddat läge och visa [olicensierade produkt meddelanden](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380.aspx). Du kan fortfarande logga in och komma åt administrations centret men kan inte tilldela licenser till användarna. Dina kund uppgifter, inklusive all användar information, e-post och filer på grupp webbplatser, är bara tillgängliga för dig och andra administratörer.

::: moniker-end

Som global administratör eller fakturering kan du [återaktivera abonnemanget](reactivate-your-subscription.md) och fortsätta använda Microsoft 365 med alla dina kund uppgifter intakt. Om du väljer att inte återaktivera kan du [säkerhetskopiera dina data](back-up-data-before-switching-plans.md).

### <a name="state-deprovisioned"></a>Tillstånd: avetablerad
  
 **Vad du kan förvänta dig:** Om du inte återaktiverar prenumerationen när den är i Grace eller inaktive ring har abonnemanget avetablerats.
  
Administratörer och användare har inte längre till gång till de tjänster eller Office-program som medföljde prenumerationen. Alla kunddata – från användar data till dokument och e-post – tas bort permanent och kan inte återställas.
  
Du kan inte återaktivera prenumerationen just nu. Som global administratör eller fakturering kan du ändå komma åt administrations centret för att hantera andra abonnemang eller för att köpa nya abonnemang för att uppfylla företagets behov.
  
> [!NOTE]
> Om du lägger till ett nytt abonnemang av samma typ som har avetablerats återställs inte data som är kopplade till den avetablerade prenumerationen.

### <a name="what-happens-when-my-trial-ends"></a>Vad händer när min utvärderings version går ut?

När utvärderings versionen upphör kan du inte fortsätta att använda Microsoft 365 kostnads fritt. Du har några alternativ:

::: moniker range="o365-worldwide"

- **Köp Microsoft 365.** När utvärderings versionen upphör flyttas den till en respitperiod, vilket ger dig ytterligare 30 dagar (för de flesta testerna, i de flesta länder och regioner) för att köpa Microsoft 365. Information om hur du konverterar utvärderings versionen till en betald prenumeration finns i [köpa en utvärderings version av Microsoft 365 för företag](../buy-a-subscription-from-your-free-trial.md).

::: moniker-end

::: moniker range="o365-germany"

- **Köp Microsoft 365.** När utvärderings versionen upphör flyttas den till en respitperiod, vilket ger dig ytterligare 30 dagar (för de flesta testerna, i de flesta länder och regioner) för att köpa Microsoft 365. Information om hur du konverterar utvärderings versionen till en betald prenumeration finns i [köpa en utvärderings version av Microsoft 365 för företag](../buy-a-subscription-from-your-free-trial.md).

::: moniker-end

::: moniker range="o365-21vianet"

- **Köp Office 365.** När utvärderings versionen upphör flyttas den till en respitperiod, vilket ger dig ytterligare 30 dagar (för de flesta testerna, i de flesta länder och regioner) för att köpa Office 365. Information om hur du konverterar utvärderings versionen till en betald prenumeration finns i [köpa eller prova abonnemang för Office 365 som drivs av 21Vianet](../../admin/services-in-china/buy-or-try-subscriptions.md).

::: moniker-end

- **Förläng utvärderings versionen.** Behöver du mer tid för att utvärdera Microsoft 365? I vissa fall kan du [förlänga utvärderings versionen](../extend-your-trial.md).

- **Avbryt utvärderings versionen eller låt den gå ut.** Om du bestämmer dig för att inte köpa Microsoft 365 kan du låta utvärderings versionen gå ut eller [avbryta det](cancel-your-subscription.md). Säkerhetskopiera alla data du vill behålla. Efter 30 dagars Grace-perioden raderas utvärderings konto informationen och data permanent.

> [!NOTE]
> Informationen på den här sidan lyder under [Microsofts policy för fri skrivning och ändring](https://go.microsoft.com/fwlink/p/?LinkId=613651). Gå tillbaka till den här webbplatsen och kontrol lera eventuella ändringar.

## <a name="related-content"></a>Relaterat innehåll 

[Avbryta din prenumeration](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/cancel-your-subscription) (artikel) \
[Förnya Microsoft 365 för företag](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/renew-your-subscription) (artikel) \
[Återaktivera din prenumeration](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/reactivate-your-subscription) (artikel)