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
# <a name="set-up-the-ringback-bot-for-direct-routing"></a><span data-ttu-id="090ac-103">設定直接路由的 Ringback bot</span><span class="sxs-lookup"><span data-stu-id="090ac-103">Set up the Ringback bot for Direct Routing</span></span>

<span data-ttu-id="090ac-104">本文將說明 Ringback bot，您可以用來協助避免在通話時間較長時可能會發生的意外 silences。</span><span class="sxs-lookup"><span data-stu-id="090ac-104">This article describes the Ringback bot, which you can use to help avoid unexpected silences that can occur when it takes a longer time for calls to be established.</span></span> <span data-ttu-id="090ac-105">您可以在非媒體旁路模式中直接路由使用 Ringback bot。</span><span class="sxs-lookup"><span data-stu-id="090ac-105">The Ringback bot is available for Direct Routing in non-media bypass mode.</span></span>

<span data-ttu-id="090ac-106">有時從公用的交換電話網絡（PSTN）到團隊用戶端的入站呼叫，可能會花費比預期更長的時間來建立。</span><span class="sxs-lookup"><span data-stu-id="090ac-106">Sometimes inbound calls from the public switched telephone network (PSTN) to Teams clients can take longer than expected to be established.</span></span> <span data-ttu-id="090ac-107">發生這種情況可能有多種原因。</span><span class="sxs-lookup"><span data-stu-id="090ac-107">This can occur for various reasons.</span></span> <span data-ttu-id="090ac-108">在這種情況下，來電者可能不會聽到任何問題，小組用戶端就不會響鈴，而且通話可能會被某些電訊提供者取消。</span><span class="sxs-lookup"><span data-stu-id="090ac-108">When this happens, the caller might not hear anything, the Teams client doesn't ring, and the call might be canceled by some telecommunications providers.</span></span>

<span data-ttu-id="090ac-109">Ringback bot 可協助避免在此案例中可能發生的意外 silences。</span><span class="sxs-lookup"><span data-stu-id="090ac-109">The Ringback bot helps to avoid unexpected silences that can occur in this scenario.</span></span> <span data-ttu-id="090ac-110">對於從 PSTN 到團隊用戶端的撥入呼叫，Ringback bot 會在來電者中播放獨特的音訊信號，表示小組正在進行通話的過程。</span><span class="sxs-lookup"><span data-stu-id="090ac-110">For inbound calls from the PSTN to Teams clients, the Ringback bot plays a distinctive audio signal to the caller to indicate that Teams is in the process of establishing the call.</span></span>

> [!NOTE]
> <span data-ttu-id="090ac-111">Ringback bot 會產生來自團隊後端的早期媒體。</span><span class="sxs-lookup"><span data-stu-id="090ac-111">The Ringback bot generates early media from the Teams backend.</span></span> <span data-ttu-id="090ac-112">在某些國家和地區，您可能會在媒體開始流動時為通話付費。</span><span class="sxs-lookup"><span data-stu-id="090ac-112">In some countries and regions, you might be charged for the call when the media starts flowing.</span></span>

## <a name="configure-the-ringback-bot"></a><span data-ttu-id="090ac-113">設定 Ringback bot</span><span class="sxs-lookup"><span data-stu-id="090ac-113">Configure the Ringback bot</span></span>

<span data-ttu-id="090ac-114">使用[CsOnlineGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway)和[CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) Cmdlet 以及**GenerateRingingWhileLocatingUser**參數，以設定 Ringback bot。</span><span class="sxs-lookup"><span data-stu-id="090ac-114">Use the [Set-CsOnlineGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) and [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) cmdlets together with the **GenerateRingingWhileLocatingUser** parameter to configure the Ringback bot.</span></span>

<span data-ttu-id="090ac-115">若要開啟 Ringback bot，請將**GenerateRingingWhileLocatingUser**參數設定為 [ **$True**]。</span><span class="sxs-lookup"><span data-stu-id="090ac-115">To turn on the Ringback bot, set the **GenerateRingingWhileLocatingUser** parameter to **$True**.</span></span> <span data-ttu-id="090ac-116">此為預設值。</span><span class="sxs-lookup"><span data-stu-id="090ac-116">This is the default value.</span></span> 

<span data-ttu-id="090ac-117">若要關閉 Ringback bot，請將**GenerateRingingWhileLocatingUser**參數設定為 [ **$False**]。</span><span class="sxs-lookup"><span data-stu-id="090ac-117">To turn off the Ringback bot, set the **GenerateRingingWhileLocatingUser** parameter to **$False**.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="090ac-118">相關主題</span><span class="sxs-lookup"><span data-stu-id="090ac-118">Related topics</span></span>

- [<span data-ttu-id="090ac-119">團隊 PowerShell 概覽</span><span class="sxs-lookup"><span data-stu-id="090ac-119">Teams PowerShell overview</span></span>](teams-powershell-overview.md)