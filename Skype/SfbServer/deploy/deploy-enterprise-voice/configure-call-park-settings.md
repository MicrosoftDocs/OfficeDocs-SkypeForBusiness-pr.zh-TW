---
title: 在商務用 Skype 中設定通話寄存設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
description: 在商務用 Skype Server Enterprise Voice 中修改通話駐留設定。
ms.openlocfilehash: c456a519fc9f567bdef812adc533adaf03c4360a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193542"
---
# <a name="configure-call-park-settings-in-skype-for-business"></a><span data-ttu-id="2d36a-103">在商務用 Skype 中設定通話寄存設定</span><span class="sxs-lookup"><span data-stu-id="2d36a-103">Configure Call Park settings in Skype for Business</span></span>

<span data-ttu-id="2d36a-104">在商務用 Skype Server Enterprise Voice 中修改通話駐留設定。</span><span class="sxs-lookup"><span data-stu-id="2d36a-104">Modify Call Park settings in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="2d36a-105">如果您不想使用預設的通話駐留設定, 您可以進行自訂。</span><span class="sxs-lookup"><span data-stu-id="2d36a-105">If you don't want to use default Call Park settings, you can customize them.</span></span> <span data-ttu-id="2d36a-106">當您安裝 [通話駐留] 應用程式時, 系統會根據預設設定全域設定。</span><span class="sxs-lookup"><span data-stu-id="2d36a-106">When you install the Call Park application, global settings are configured by default.</span></span> <span data-ttu-id="2d36a-107">您可以修改全域設定, 也可以指定網站專用的設定。</span><span class="sxs-lookup"><span data-stu-id="2d36a-107">You can modify the global settings, and you can also specify site-specific settings.</span></span> <span data-ttu-id="2d36a-108">使用**新的 CsCpsConfiguration** Cmdlet 來建立新的網站特定設定。</span><span class="sxs-lookup"><span data-stu-id="2d36a-108">Use the **New-CsCpsConfiguration** cmdlet to create new site-specific settings.</span></span> <span data-ttu-id="2d36a-109">使用**CsCpsConfiguration** Cmdlet 來修改現有的設定。</span><span class="sxs-lookup"><span data-stu-id="2d36a-109">Use the **Set-CsCpsConfiguration** cmdlet to modify existing settings.</span></span>

> [!NOTE]
> <span data-ttu-id="2d36a-110">我們建議您針對備用目的地設定**OnTimeoutURI**選項, 以便在停用通話超時和 ringback 失敗時使用。</span><span class="sxs-lookup"><span data-stu-id="2d36a-110">At a minimum, we recommend that you configure the **OnTimeoutURI** option for the fallback destination to use when a parked call times out and ringback fails.</span></span>

<span data-ttu-id="2d36a-111">使用**新的 CsCpsConfiguration** Cmdlet 或**CsCpsConfiguration** Cmdlet 來設定下列任何設定:</span><span class="sxs-lookup"><span data-stu-id="2d36a-111">Use **New-CsCpsConfiguration** cmdlet or the **Set-CsCpsConfiguration** cmdlet to configure any of the following settings:</span></span>


| <span data-ttu-id="2d36a-112">**此選項:**</span><span class="sxs-lookup"><span data-stu-id="2d36a-112">**This option:**</span></span>                     | <span data-ttu-id="2d36a-113">**指定:**</span><span class="sxs-lookup"><span data-stu-id="2d36a-113">**Specifies this:**</span></span>                                                                                                                                                                                                                                                                                                                   |
|:-------------------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="2d36a-114">**CallPickupTimeoutThreshold**</span><span class="sxs-lookup"><span data-stu-id="2d36a-114">**CallPickupTimeoutThreshold**</span></span> <br/> | <span data-ttu-id="2d36a-115">通話結束之後, 在撥打電話給接聽電話的電話之前所經過的時間長度。</span><span class="sxs-lookup"><span data-stu-id="2d36a-115">The amount of time that elapses after a call has been parked before it rings back to the phone where the call was answered.</span></span>  <br/> <span data-ttu-id="2d36a-116">此值必須以 hh: mm: ss 格式輸入, 以指定小時、分鐘和秒。</span><span class="sxs-lookup"><span data-stu-id="2d36a-116">The value must be entered in the format hh:mm:ss to specify the hours, minutes, and seconds.</span></span> <span data-ttu-id="2d36a-117">最小值為10秒, 最大值為10分鐘。</span><span class="sxs-lookup"><span data-stu-id="2d36a-117">The minimum value is 10 seconds, and the maximum value is 10 minutes.</span></span> <span data-ttu-id="2d36a-118">預設值為00:01:30。</span><span class="sxs-lookup"><span data-stu-id="2d36a-118">The default is 00:01:30.</span></span>  <br/> |
| <span data-ttu-id="2d36a-119">**EnableMusicOnHold**</span><span class="sxs-lookup"><span data-stu-id="2d36a-119">**EnableMusicOnHold**</span></span> <br/>          | <span data-ttu-id="2d36a-120">通話停用時, 是否會在來電者中播放音樂。</span><span class="sxs-lookup"><span data-stu-id="2d36a-120">Whether music plays for a caller while a call is parked.</span></span>  <br/> <span data-ttu-id="2d36a-121">值為 True 或 False。</span><span class="sxs-lookup"><span data-stu-id="2d36a-121">Values are True or False.</span></span> <span data-ttu-id="2d36a-122">預設值為 True。</span><span class="sxs-lookup"><span data-stu-id="2d36a-122">The default is True.</span></span>  <br/>                                                                                                                                                                                                                 |
| <span data-ttu-id="2d36a-123">**MaxCallPickupAttempts**</span><span class="sxs-lookup"><span data-stu-id="2d36a-123">**MaxCallPickupAttempts**</span></span> <br/>      | <span data-ttu-id="2d36a-124">寄存來電在轉寄到指定給**OnTimeoutURI**的回退統一資源識別項 (URI) 之前, 響鈴給應答電話的次數。</span><span class="sxs-lookup"><span data-stu-id="2d36a-124">The number of times a parked call rings back to the answering phone before it is forwarded to the fallback Uniform Resource Identifier (URI) that is specified for **OnTimeoutURI**.</span></span> <span data-ttu-id="2d36a-125">預設值為1。</span><span class="sxs-lookup"><span data-stu-id="2d36a-125">The default is 1.</span></span>  <br/>                                                                                                                         |
| <span data-ttu-id="2d36a-126">**OnTimeoutURI**</span><span class="sxs-lookup"><span data-stu-id="2d36a-126">**OnTimeoutURI**</span></span> <br/>               | <span data-ttu-id="2d36a-127">在超過**MaxCallPickupAttempts**時傳送未應答之暫停呼叫的使用者或回應群組的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="2d36a-127">The SIP address of the user or response group to which an unanswered parked call is routed when **MaxCallPickupAttempts** is exceeded.</span></span> <br/> <span data-ttu-id="2d36a-128">Value 必須是以 [字串 SIP:] 開頭的 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="2d36a-128">Value must be a SIP URI beginning with the string sip:.</span></span> <span data-ttu-id="2d36a-129">例如, sip:bob@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="2d36a-129">For example, sip:bob@contoso.com.</span></span> <span data-ttu-id="2d36a-130">預設值為 [沒有轉寄位址]。</span><span class="sxs-lookup"><span data-stu-id="2d36a-130">The default is no forwarding address.</span></span>  <br/>                                                   |

### <a name="to-configure-call-park-settings"></a><span data-ttu-id="2d36a-131">若要設定通話寄存設定</span><span class="sxs-lookup"><span data-stu-id="2d36a-131">To configure Call Park settings</span></span>

1. <span data-ttu-id="2d36a-132">啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="2d36a-132">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="2d36a-133">用盡</span><span class="sxs-lookup"><span data-stu-id="2d36a-133">Run:</span></span>

   ```
   New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
   ```

   > [!TIP]
   > <span data-ttu-id="2d36a-134">使用**CsSite** Cmdlet 來識別網站。</span><span class="sxs-lookup"><span data-stu-id="2d36a-134">Use the **Get-CsSite** cmdlet to identify the site.</span></span> <span data-ttu-id="2d36a-135">如需詳細資訊, 請參閱商務用 Skype Server Management 命令介面檔。</span><span class="sxs-lookup"><span data-stu-id="2d36a-135">For details, see Skype for Business Server Management Shell documentation.</span></span>

    <span data-ttu-id="2d36a-136">例如：</span><span class="sxs-lookup"><span data-stu-id="2d36a-136">For example:</span></span>

   ```
   New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com
   ```

## <a name="see-also"></a><span data-ttu-id="2d36a-137">另請參閱</span><span class="sxs-lookup"><span data-stu-id="2d36a-137">See also</span></span>

[<span data-ttu-id="2d36a-138">在保留 inSkype for Business 2015 上自訂通話寄存音樂</span><span class="sxs-lookup"><span data-stu-id="2d36a-138">Customize Call Park music on hold inSkype for Business 2015</span></span>](customize-call-park-music-on-hold.md)

[<span data-ttu-id="2d36a-139">新-CsCpsConfiguration</span><span class="sxs-lookup"><span data-stu-id="2d36a-139">New-CsCpsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscpsconfiguration?view=skype-ps)

[<span data-ttu-id="2d36a-140">Set-CsCpsConfiguration</span><span class="sxs-lookup"><span data-stu-id="2d36a-140">Set-CsCpsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscpsconfiguration?view=skype-ps)

[<span data-ttu-id="2d36a-141">CsSite</span><span class="sxs-lookup"><span data-stu-id="2d36a-141">Get-CsSite</span></span>](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps)
