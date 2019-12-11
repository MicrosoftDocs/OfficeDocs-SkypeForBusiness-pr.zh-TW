---
title: 設定直接路由的 Ringback bot
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
description: 瞭解如何使用 Ringback bot 進行直接路由，避免在建立通話時可能發生的意外 silences。
localization_priority: Normal
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3fcb69ba1bc612fe940054ec982eb7462c6679be
ms.sourcegitcommit: a23f45ab3a2cb7b5c279356edddf61c4030c41bd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/10/2019
ms.locfileid: "39962500"
---
# <a name="set-up-the-ringback-bot-for-direct-routing"></a>設定直接路由的 Ringback bot

本文將說明 Ringback bot，您可以用來協助避免在通話時間較長時可能會發生的意外 silences。 您可以在非媒體旁路模式中直接路由使用 Ringback bot。

有時從公用的交換電話網絡（PSTN）到團隊用戶端的入站呼叫，可能會花費比預期更長的時間來建立。 發生這種情況可能有多種原因。 在這種情況下，來電者可能不會聽到任何問題，小組用戶端就不會響鈴，而且通話可能會被某些電訊提供者取消。

Ringback bot 可協助避免在此案例中可能發生的意外 silences。 對於從 PSTN 到團隊用戶端的撥入呼叫，Ringback bot 會在來電者中播放獨特的音訊信號，表示小組正在進行通話的過程。

> [!NOTE]
> Ringback bot 會產生來自團隊後端的早期媒體。 在某些國家和地區，您可能會在媒體開始流動時為通話付費。

## <a name="configure-the-ringback-bot"></a>設定 Ringback bot

使用[CsOnlineGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway)和[CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) Cmdlet 以及**GenerateRingingWhileLocatingUser**參數，以設定 Ringback bot。

若要開啟 Ringback bot，請將**GenerateRingingWhileLocatingUser**參數設定為 [ **$True**]。 此為預設值。 

若要關閉 Ringback bot，請將**GenerateRingingWhileLocatingUser**參數設定為 [ **$False**]。 

## <a name="related-topics"></a>相關主題

- [團隊 PowerShell 概覽](teams-powershell-overview.md)