---
title: Konfigurera multifaktorautentisering för Office 365-användare
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
description: Lär dig hur du använder säkerhetsstandarder för att konfigurera multifaktorautentisering för Office 365-användare.
monikerRange: o365-worldwide
ms.openlocfilehash: 4dc52c25c3a9351be1a9f4d094d664bc4ed527f9
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42810167"
---
# <a name="set-up-multi-factor-authentication"></a>Konfigurera multifaktorautentisering
  
Alla nya Office 365 för företag- och Microsoft 365 Business-prenumerationer har automatiskt säkerhetsstandarder aktiverade. Det innebär att alla användare måste konfigurera multifaktorautentisering (MFA) och installera Authenticator-appen på en mobil enhet. Mer information finns i [Konfigurera tvåstegsverifiering för Office 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).  

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

Alla andra användare kommer att ombes utföra ytterligare autentisering när det behövs. Mer information finns i [Vad är säkerhetsstandarder?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)

> [!NOTE]
> Du måste vara global Office 365-administratör för att konfigurera eller ändra multifaktorautentisering. <br><br>
> Om du inte använder det nya administrationscentret för Microsoft 365 kan du aktivera det genom att välja **Prova det nya administrationscentret** längst upp på startsidan.

Om du tidigare har konfigurerat MFA med riktlinjer [måste du inaktivera och aktivera säkerhetsstandarder](#move-from-baseline-policies-to-security-defaults). Men om du har Microsoft 365 Business eller om din prenumeration omfattar [Azure Active Directory Premium 1 eller Azure Active Directory Premium 2](https://azure.microsoft.com/pricing/details/active-directory/)kan du även konfigurera riktlinjerna [villkorad åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/overview). Om du vill använda riktlinjerna för villkorad åtkomst måste du kontrollera att [modern autentisering är aktiverat](#enable-multi-factor-authentication-for-your-organization).

## <a name="manage-security-defaults"></a>Hantera säkerhetsstandarder

1. Logga in på [administrationscentret](https://go.microsoft.com/fwlink/p/?linkid=834822) som global administratör.
2. Gå till [Azure Active Directory egenskaper](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).

3. Längst ner på sidan väljer du **Hantera säkerhetsstandarder**.
4. Välj **Ja** för att aktivera säkerhetsstandardinställningar och **Nej** för att inaktivera dem.

## <a name="move-from-baseline-policies-to-security-defaults"></a>Flytta från baslinje riktlinjer till säkerhetsstandarder

1. I [administrationscentret](https://go.microsoft.com/fwlink/p/?linkid=834822) väljer du **Inställningar**.

2. Bredvid **Inloggning och säkerhet** väljer du **Visa** för **Gör inloggningen säkrare**.

3. Under **Gör inloggningen säkrare** väljer du **Hantera**. 

4. På sidan **Villkorad åtkomst till Azure portal – riktlinjer** väljer du varje baslinje-policy som är **På** och ställ dem på **Av**.
5. Gå till sidan [Azure Active Directory egenskaper](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).
6. Gå till slutet av sidan och välj **Hantera säkerhetsstandarder**och i fönstret **Aktivera säkerhetsstandarder** och ställer**Aktiverar säkerhetsstandarder** till **Ja**. 

## <a name="enable-modern-authentication-for-your-organization"></a>Aktivera modern autentisering för din organisation

Alla Office 2016-klientprogrammen har stöd för MFA genom användning av ADAL (Active Directory Authentication Library). Det innebär att programlösenord inte är nödvändiga för Office 2016-klienter. Du måste kontrollera att din Office 365-prenumeration är aktiverad för ADAL eller modern autentisering.

1. Om du vill aktivera modern autentisering väljer du **Inställningar** \> **Inställningar** i [administrationscentrat](https://go.microsoft.com/fwlink/p/?linkid=834822) och **Modern autentisering** i listan på fliken **Tjänster**.

2. Markera rutan **Aktivera modern autentisering** i panelen **Modern autentisering**. 

    ![Panelen Modern autentisering med kryssrutan Aktivera markerad.](../../media/enablemodernauth.png)
    
## <a name="enable-multi-factor-authentication-for-your-organization"></a>Aktivera multifaktorautentisering för din organisation
    
1. Välj **Användare** och aktiva **användare**i [administrationscentret](https://go.microsoft.com/fwlink/p/?linkid=834822).

2. Klicka på **multifaktorautentisering**i avsnittet **Aktiva användare** .

3. På sidan **Multifaktorautentisering** väljer du **användare** om du aktiverar detta för en användare eller väljer **Massuppdatering** för att aktivera flera användare.

4. CLick på **Aktivera** under **Snabbsteg**.

5. Klicka på **Aktivera multifaktorautentisering**i popup-fönstret .

När du har konfigurerat multifaktorautentisering för din organisation måste dina användare konfigurera tvåstegsverifiering på sina enheter. Mer information finns i [Konfigurera tvåstegsverifiering för Office 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).
    
> [!TIP]
> För att kunna förklara för användarna hur de konfigurerar Authenticator-appen kan du besöka [Använd Microsoft Authenticator med Office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1).


> [!IMPORTANT]
> Från och med augusti 2017 är modern autentisering aktiverat som standard för alla nya Office 365-klientorganisationer som inkluderar Skype för företag – Online och Exchange Online. Om du vill kontrollera status för modern autentisering i Skype för företag – Online kan du använda Skype för företag – Online PowerShell med globala administratörsuppgifter. Kör Get-CsOAuthConfiguration när du vill kontrollera utdata för -ClientADALAuthOverride. Om -ClientADALAuthOverride är Allowed är modern autentisering aktiverat.
Om du vill kontrollera MA-status för Exchange Online går du till [Aktivera modern autentisering i Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).

## <a name="related-articles"></a>Relaterade artiklar

[De 10 bästa sätten att skydda Office 365 och Microsoft 365 Business-abonnemang](secure-your-business-data.md)

[Aktivera modern autentisering för Office 2013 på Windows-enheter](enable-modern-authentication.md)
