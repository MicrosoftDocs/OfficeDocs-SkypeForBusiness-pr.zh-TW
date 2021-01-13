---
title: 設定直接路由的 Ringback bot
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
description: 瞭解如何使用 Ringback bot 進行直接路由，避免在建立通話時可能發生的意外 silences。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 91cea9183a85a804ca43464aab08f417ccaff1e8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827513"
---
# <a name="set-up-the-ringback-bot-for-direct-routing"></a><span data-ttu-id="cc851-103">設定直接路由的 Ringback bot</span><span class="sxs-lookup"><span data-stu-id="cc851-103">Set up the Ringback bot for Direct Routing</span></span>

<span data-ttu-id="cc851-104">本文將說明 Ringback bot，您可以用來協助避免在通話時間較長時可能會發生的意外 silences。</span><span class="sxs-lookup"><span data-stu-id="cc851-104">This article describes the Ringback bot, which you can use to help avoid unexpected silences that can occur when it takes a longer time for calls to be established.</span></span> <span data-ttu-id="cc851-105">您可以在非媒體旁路模式中直接路由使用 Ringback bot。</span><span class="sxs-lookup"><span data-stu-id="cc851-105">The Ringback bot is available for Direct Routing in non-media bypass mode.</span></span>

<span data-ttu-id="cc851-106">有時，來自公開交換電話網絡的入站呼叫 (PSTN) 給團隊用戶端可能需要比預期更長的時間才能建立。</span><span class="sxs-lookup"><span data-stu-id="cc851-106">Sometimes inbound calls from the public switched telephone network (PSTN) to Teams clients can take longer than expected to be established.</span></span> <span data-ttu-id="cc851-107">發生這種情況可能有多種原因。</span><span class="sxs-lookup"><span data-stu-id="cc851-107">This can occur for various reasons.</span></span> <span data-ttu-id="cc851-108">在這種情況下，來電者可能不會聽到任何問題，小組用戶端就不會響鈴，而且有些電訊供應商可能會取消通話。</span><span class="sxs-lookup"><span data-stu-id="cc851-108">When this happens, the caller might not hear anything, the Teams client doesn't ring, and some telecommunications providers might cancel the call.</span></span>

<span data-ttu-id="cc851-109">Ringback bot 可協助避免在此案例中可能發生的意外 silences。</span><span class="sxs-lookup"><span data-stu-id="cc851-109">The Ringback bot helps to avoid unexpected silences that can occur in this scenario.</span></span> <span data-ttu-id="cc851-110">對於從 PSTN 到團隊用戶端的撥入呼叫，Ringback bot 會在來電者中播放獨特的音訊信號，表示小組正在進行通話的過程。</span><span class="sxs-lookup"><span data-stu-id="cc851-110">For inbound calls from the PSTN to Teams clients, the Ringback bot plays a distinctive audio signal to the caller to indicate that Teams is in the process of establishing the call.</span></span>

> [!NOTE]
> <span data-ttu-id="cc851-111">Ringback bot 會產生來自團隊後端的早期媒體。</span><span class="sxs-lookup"><span data-stu-id="cc851-111">The Ringback bot generates early media from the Teams backend.</span></span> <span data-ttu-id="cc851-112">在某些國家和地區，您可能會在媒體開始流動時為通話付費。</span><span class="sxs-lookup"><span data-stu-id="cc851-112">In some countries and regions, you might be charged for the call when the media starts flowing.</span></span>

## <a name="configure-the-ringback-bot"></a><span data-ttu-id="cc851-113">設定 Ringback bot</span><span class="sxs-lookup"><span data-stu-id="cc851-113">Configure the Ringback bot</span></span>

<span data-ttu-id="cc851-114">使用 [CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) Cmdlet 來修改先前定義的會話邊界控制器 (SBC) 設定，或 CsOnlinePSTNGateway Cmdlet，以建立新 [的](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) SBC 配置，以及 **GenerateRingingWhileLocatingUser** 參數來設定 Ringback bot：</span><span class="sxs-lookup"><span data-stu-id="cc851-114">Use the [Set-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) cmdlet to modify a previously defined Session Border Controller (SBC) configuration, or the [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) cmdlet to create a new SBC configuration, together with the **GenerateRingingWhileLocatingUser** parameter to configure the Ringback bot:</span></span>

- <span data-ttu-id="cc851-115">若要開啟 Ringback bot，請將 **GenerateRingingWhileLocatingUser** 參數設定為 [ **$True**]。</span><span class="sxs-lookup"><span data-stu-id="cc851-115">To turn on the Ringback bot, set the **GenerateRingingWhileLocatingUser** parameter to **$True**.</span></span> <span data-ttu-id="cc851-116">此為預設值。</span><span class="sxs-lookup"><span data-stu-id="cc851-116">This is the default value.</span></span> 

- <span data-ttu-id="cc851-117">若要關閉 Ringback bot，請將 **GenerateRingingWhileLocatingUser** 參數設定為 [ **$False**]。</span><span class="sxs-lookup"><span data-stu-id="cc851-117">To turn off the Ringback bot, set the **GenerateRingingWhileLocatingUser** parameter to **$False**.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="cc851-118">相關主題</span><span class="sxs-lookup"><span data-stu-id="cc851-118">Related topics</span></span>

- [<span data-ttu-id="cc851-119">Teams PowerShell 概觀</span><span class="sxs-lookup"><span data-stu-id="cc851-119">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
