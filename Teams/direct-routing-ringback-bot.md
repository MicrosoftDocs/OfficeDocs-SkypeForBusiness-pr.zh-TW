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
# <a name="set-up-the-ringback-bot-for-direct-routing"></a><span data-ttu-id="9f6aa-103">設定直接路由的 Ringback Bot</span><span class="sxs-lookup"><span data-stu-id="9f6aa-103">Set up the Ringback bot for Direct Routing</span></span>

<span data-ttu-id="9f6aa-104">本文將說明 Ringback Bot，您可以使用這個機器人，協助避免在建立通話需要較長的時間時，發生意外的靜音。</span><span class="sxs-lookup"><span data-stu-id="9f6aa-104">This article describes the Ringback bot, which you can use to help avoid unexpected silences that can occur when it takes a longer time for calls to be established.</span></span> <span data-ttu-id="9f6aa-105">Ringback Bot 可在非媒體旁路模式中直接路由。</span><span class="sxs-lookup"><span data-stu-id="9f6aa-105">The Ringback bot is available for Direct Routing in non-media bypass mode.</span></span>

<span data-ttu-id="9f6aa-106">有時候，從公用交換電話網路 (PSTN) 到 Teams 用戶端的來電可能需要超過預期的時間。</span><span class="sxs-lookup"><span data-stu-id="9f6aa-106">Sometimes inbound calls from the public switched telephone network (PSTN) to Teams clients can take longer than expected to be established.</span></span> <span data-ttu-id="9f6aa-107">發生此情況的原因可能有多種。</span><span class="sxs-lookup"><span data-stu-id="9f6aa-107">This can occur for various reasons.</span></span> <span data-ttu-id="9f6aa-108">發生此情況時，來電者可能聽不到任何聲音，Teams 用戶端不會響鈴，而有些電信提供者可能會取消通話。</span><span class="sxs-lookup"><span data-stu-id="9f6aa-108">When this happens, the caller might not hear anything, the Teams client doesn't ring, and some telecommunications providers might cancel the call.</span></span>

<span data-ttu-id="9f6aa-109">Ringback Bot 可協助避免在此情境中發生意外的靜音。</span><span class="sxs-lookup"><span data-stu-id="9f6aa-109">The Ringback bot helps to avoid unexpected silences that can occur in this scenario.</span></span> <span data-ttu-id="9f6aa-110">針對從 PSTN 到 Teams 用戶端的來電，Ringback Bot 會向來電者播放獨特的音訊訊號，表示 Teams 正在建立通話。</span><span class="sxs-lookup"><span data-stu-id="9f6aa-110">For inbound calls from the PSTN to Teams clients, the Ringback bot plays a distinctive audio signal to the caller to indicate that Teams is in the process of establishing the call.</span></span>

> [!NOTE]
> <span data-ttu-id="9f6aa-111">Ringback Bot 會從 Teams 後端產生早期媒體。</span><span class="sxs-lookup"><span data-stu-id="9f6aa-111">The Ringback bot generates early media from the Teams backend.</span></span> <span data-ttu-id="9f6aa-112">在某些國家和地區，當媒體開始流動時，您可能會收取通話費用。</span><span class="sxs-lookup"><span data-stu-id="9f6aa-112">In some countries and regions, you might be charged for the call when the media starts flowing.</span></span>

## <a name="configure-the-ringback-bot"></a><span data-ttu-id="9f6aa-113">設定 Ringback Bot</span><span class="sxs-lookup"><span data-stu-id="9f6aa-113">Configure the Ringback bot</span></span>

<span data-ttu-id="9f6aa-114">使用 [Set-CsOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway) Cmdlet 修改先前定義的會話邊界控制器 (SBC) 設定，或 [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) Cmdlet 來建立新的 SBC 設定，以及 **GenerateRingingWhileLocatingUser 參數** 來設定 Ringback Bot：</span><span class="sxs-lookup"><span data-stu-id="9f6aa-114">Use the [Set-CsOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway) cmdlet to modify a previously defined Session Border Controller (SBC) configuration, or the [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) cmdlet to create a new SBC configuration, together with the **GenerateRingingWhileLocatingUser** parameter to configure the Ringback bot:</span></span>

- <span data-ttu-id="9f6aa-115">若要開啟 Ringback bot，請設定 **GenerateRingingWhileLocatingUser 參數** 至 **$True。**</span><span class="sxs-lookup"><span data-stu-id="9f6aa-115">To turn on the Ringback bot, set the **GenerateRingingWhileLocatingUser** parameter to **$True**.</span></span> <span data-ttu-id="9f6aa-116">此為預設值。</span><span class="sxs-lookup"><span data-stu-id="9f6aa-116">This is the default value.</span></span> 

- <span data-ttu-id="9f6aa-117">若要關閉 Ringback bot，請設定 **GenerateRingingWhileLocatingUser 參數\*\*\*\*，$False。**</span><span class="sxs-lookup"><span data-stu-id="9f6aa-117">To turn off the Ringback bot, set the **GenerateRingingWhileLocatingUser** parameter to **$False**.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="9f6aa-118">相關主題</span><span class="sxs-lookup"><span data-stu-id="9f6aa-118">Related topics</span></span>

- [<span data-ttu-id="9f6aa-119">Teams PowerShell 概觀</span><span class="sxs-lookup"><span data-stu-id="9f6aa-119">Teams PowerShell overview</span></span>](teams-powershell-overview.md)