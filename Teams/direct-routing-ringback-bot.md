---
title: 設定直接路由的 Ringback Bot
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
description: 瞭解如何使用直接路由的 Ringback Bot，避免在建立通話時發生意外的靜音。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3ec53f1d4f9cd21d3b28c87c07c1bc91d48b9b58
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098419"
---
# <a name="set-up-the-ringback-bot-for-direct-routing"></a>設定直接路由的 Ringback Bot

本文將說明 Ringback Bot，您可以使用這個機器人，協助避免在建立通話需要較長的時間時，發生意外的靜音。 Ringback Bot 可在非媒體旁路模式中直接路由。

有時候，從公用交換電話網路 (PSTN) 到 Teams 用戶端的來電可能需要超過預期的時間。 發生此情況的原因可能有多種。 發生此情況時，來電者可能聽不到任何聲音，Teams 用戶端不會響鈴，而有些電信提供者可能會取消通話。

Ringback Bot 可協助避免在此情境中發生意外的靜音。 針對從 PSTN 到 Teams 用戶端的來電，Ringback Bot 會向來電者播放獨特的音訊訊號，表示 Teams 正在建立通話。

> [!NOTE]
> Ringback Bot 會從 Teams 後端產生早期媒體。 在某些國家和地區，當媒體開始流動時，您可能會收取通話費用。

## <a name="configure-the-ringback-bot"></a>設定 Ringback Bot

使用 [Set-CsOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway) Cmdlet 修改先前定義的會話邊界控制器 (SBC) 設定，或 [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) Cmdlet 來建立新的 SBC 設定，以及 **GenerateRingingWhileLocatingUser 參數** 來設定 Ringback Bot：

- 若要開啟 Ringback bot，請設定 **GenerateRingingWhileLocatingUser 參數** 至 **$True。** 此為預設值。 

- 若要關閉 Ringback bot，請設定 **GenerateRingingWhileLocatingUser 參數****，$False。** 

## <a name="related-topics"></a>相關主題

- [Teams PowerShell 概觀](teams-powershell-overview.md)