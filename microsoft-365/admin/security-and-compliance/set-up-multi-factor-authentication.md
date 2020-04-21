---
title: Konfigurera multifaktorautentisering för användare
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: Lär dig hur du använder standardvärden för säkerhet för att konfigurera multifaktorautentisering för användare.
monikerRange: o365-worldwide
ms.openlocfilehash: 4a829aa597596564b9c2f468e72f3a766b198372
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43627686"
---
# <a name="set-up-multi-factor-authentication"></a>Konfigurera multifaktorautentisering
  
> [!IMPORTANT]
> Om du har köpt din prenumeration eller utvärderingsversion efter den 21 oktober 2019 och du oväntat uppmanas att ange MFA har [säkerhetsinställningarna aktiverats](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) automatiskt för din prenumeration.

Varje ny Microsoft 365-prenumeration har automatiskt aktiverat säkerhetsstandarder. Det innebär att alla användare måste konfigurera multifaktorautentisering (MFA) och installera Authenticator-appen på en mobil enhet. Mer information finns i [Konfigurera tvåstegsverifiering för Microsoft 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).  

Följande nio administratörsroller måste utföra ytterligare autentisering varje gång de loggar in:

- Global administratör
- SharePoint-administratör
- Exchange-administratör
- Administratör för villkorsstyrd åtkomst
- Säkerhetsadministratör
- Kundtjänstadministratör eller lösenordsadministratör
- Faktureringsadministratör
- Användaradministratör
- Administratör av autentisering

Alla andra användare kommer att ombes utföra ytterligare autentisering när det behövs. Mer information finns i [Vad är standardinställningar för säkerhet?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)

> [!NOTE]
> Du måste vara global administratör för att kunna konfigurera eller ändra multifaktorautentisering. <br><br>
> Om du inte använder det nya administrationscentret för Microsoft 365 kan du aktivera det genom att välja **Prova det nya administrationscentret** längst upp på startsidan.

Om du tidigare har konfigurerat MFA med riktlinjer [måste du inaktivera och aktivera säkerhetsstandarder](#move-from-baseline-policies-to-security-defaults). Men om du har Microsoft 365 Business eller om din prenumeration omfattar [Azure Active Directory Premium 1 eller Azure Active Directory Premium 2](https://azure.microsoft.com/pricing/details/active-directory/)kan du även konfigurera riktlinjerna [villkorad åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/overview). Om du vill använda principer för villkorlig åtkomst måste du se till att [modern autentisering](#enable-modern-authentication-for-your-organization) är aktiverad.

> [!TIP]
> För att kunna förklara för användarna hur de konfigurerar Authenticator-appen kan du besöka [Använd Microsoft Authenticator med Office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1).

## <a name="manage-security-defaults"></a>Hantera säkerhetsstandarder

1. Logga in på [administrationscentret](https://go.microsoft.com/fwlink/p/?linkid=834822) som global administratör.
2. Gå till [egenskaper för Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).
3. Längst ner på sidan väljer du **Hantera säkerhetsstandarder**.
4. Välj **Ja** för att aktivera säkerhetsstandardinställningar och **Nej** för att inaktivera dem.

## <a name="move-from-baseline-policies-to-security-defaults"></a>Flytta från baslinje riktlinjer till säkerhetsstandarder

1. I [administrationscentret](https://go.microsoft.com/fwlink/p/?linkid=834822) väljer du **Inställningar**.

2. Bredvid **Inloggning och säkerhet** väljer du **Visa** för **Gör inloggningen säkrare**.

3. Under **Gör inloggningen säkrare** väljer du **Hantera**. 

4. På sidan **Villkorlig åtkomst - Principer** väljer du varje originalprincip som är **På**och ställer in dem på **Av**.
5. Gå till sidan [Azure Active Directory egenskaper](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).
6. Längst ned på sidan väljer du **Hantera standardvärden för säkerhet**och i fönstret Aktivera säkerhet som **standard** anger du Växla till **Ja**för **säkerhet** och väljer sedan **Spara**. 

## <a name="enable-modern-authentication-for-your-organization"></a>Aktivera modern autentisering för din organisation

Alla Office 2016-klientprogrammen har stöd för MFA genom användning av ADAL (Active Directory Authentication Library). Det innebär att programlösenord inte är nödvändiga för Office 2016-klienter. Du måste dock se till att din Microsoft 365-prenumeration är aktiverad för ADAL eller modern autentisering.

1. Om du vill aktivera modern autentisering väljer du **Inställningar** \> **Inställningar** i [administrationscentrat](https://go.microsoft.com/fwlink/p/?linkid=834822) och **Modern autentisering** i listan på fliken **Tjänster**.

2. Markera rutan **Aktivera modern autentisering (rekommenderas)** på panelen **Modern autentisering** och välj sedan **Spara ändringar**. 

    ![Panelen Modern autentisering med kryssrutan Aktivera markerad.](../../media/enablemodernauth.png)
    
> [!IMPORTANT]
> Från och med augusti 2017 har alla nya Microsoft 365-prenumerationer som inkluderar Skype för företag online och Exchange online modern autentisering aktiverade som standard. Om du vill kontrollera status för modern autentisering i Skype för företag – Online kan du använda Skype för företag – Online PowerShell med globala administratörsuppgifter. Kör Get-CsOAuthConfiguration när du vill kontrollera utdata för -ClientADALAuthOverride. Om -ClientADALAuthOverride är Allowed är modern autentisering aktiverat.
Om du vill kontrollera MA-status för Exchange Online går du till [Aktivera modern autentisering i Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).

## <a name="related-articles"></a>Relaterade artiklar

[Topp 10 sätt att säkra Microsoft 365 för affärsplaner](secure-your-business-data.md)

[Aktivera modern autentisering för Office 2013 på Windows-enheter](enable-modern-authentication.md)
