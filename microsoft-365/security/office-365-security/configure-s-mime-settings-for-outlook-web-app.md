---
title: Konfigurera S/MIME-inställningar – Exchange Online för Outlook på webben
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: En kort beskrivning av vilka Exchange Online-administratörer som måste göra för att visa och konfigurera S/MIME-inställningarna i Outlook på webben i Exchange Online.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9acd7d4523754c1e07ece8fb0344d9f888c0ee3d
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825707"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a>Konfigurera S/MIME-inställningar i Exchange Online för Outlook på webben

Som administratör för Exchange Online kan du konfigurera Outlook på webben (tidigare Outlook Web App) för att tillåta att S/MIME-skyddade meddelanden skickas och tas emot. Använd cmdletarna **Get-SmimeConfig** och **set-SmimeConfig** för att visa och hantera den här funktionen i Exchange Online PowerShell. Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

Detaljerad information om syntax och parametrar finns i [Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig) och [set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig).

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a>Överväganden för nya Microsoft Edge (Krombaserade)

Om du vill använda S/MIME i Outlook på webben i den nya webbläsaren [Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) måste du (eller någon annan administratör) ange och konfigurera policyn för Microsoft Edge-webbläsaren med namnet **ExtensionInstallForcelist** för att installera Microsoft S/MIME-tillägget i den nya Microsoft Edge. Principens värde är `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` . Tänk på att om du tillämpar den här principen krävs domänanslutna eller Azure AD-anslutna enheter, så med S/MIME i den nya Microsoft Edge-webbläsaren krävs effektiv domän anslutna eller Azure AD-anslutna enheter.

Mer information om **ExtensionInstallForcelist** policy finns i [ExtensionInstallForcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist).

Det här steget är en förutsättning för att du ska kunna använda nya Microsoft Edge; den ersätter inte S/MIME-kontrollen som är installerad av användare. Användare uppmanas att ladda ned och installera S/MIME-kontrollen i Outlook på webben under den första användningen av S/MIME. Eller så kan användarna aktivera nedladdnings länken för kontrollen genom att gå till **S/MIME** i sina Outlook-inställningar.

## <a name="considerations-for-chrome"></a>Överväganden för Chrome

Om du vill använda S/MIME i Outlook på webben i din Google Chrome-webbläsare måste du (eller någon annan administratör) ange och konfigurera den krom principen med namnet **ExtensionInstallForcelist** för att installera Microsoft S/MIME-tillägget i Chrome. Principens värde är `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` . Tänk på att om du tillämpar den här principen måste domänanslutna datorer, och om du använder S/MIME i Chrome effektivt krävs domänanslutna datorer.

Mer information om **ExtensionInstallForcelist** policy finns i [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist).

Det här steget är en förutsättning för att du ska kunna använda Chrome; den ersätter inte S/MIME-kontrollen som är installerad av användare. Användare uppmanas att ladda ned och installera S/MIME-kontrollen i Outlook på webben under den första användningen av S/MIME. Eller så kan användarna aktivera nedladdnings länken för kontrollen genom att gå till **S/MIME** i sina Outlook-inställningar.

## <a name="for-more-information"></a>Mer information

[S/MIME för signering och kryptering av meddelanden](s-mime-for-message-signing-and-encryption.md)
