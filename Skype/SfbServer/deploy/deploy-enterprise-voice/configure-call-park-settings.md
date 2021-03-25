---
title: 在商務用 Skype 中設定通話駐留設定
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
description: 修改商務用 Skype Server Enterprise Voice 中的通話駐留設定。
ms.openlocfilehash: c1eecd55dac398752915ccb63886bbf85858fe47
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111909"
---
# <a name="configure-call-park-settings-in-skype-for-business"></a><span data-ttu-id="9565a-103">在商務用 Skype 中設定通話駐留設定</span><span class="sxs-lookup"><span data-stu-id="9565a-103">Configure Call Park settings in Skype for Business</span></span>

<span data-ttu-id="9565a-104">修改商務用 Skype Server Enterprise Voice 中的通話駐留設定。</span><span class="sxs-lookup"><span data-stu-id="9565a-104">Modify Call Park settings in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="9565a-105">如果您不想要使用預設的通話駐留設定，可以進行自訂。</span><span class="sxs-lookup"><span data-stu-id="9565a-105">If you don't want to use default Call Park settings, you can customize them.</span></span> <span data-ttu-id="9565a-106">當您安裝通話駐留應用程式時，系統會預設設定全域設定。</span><span class="sxs-lookup"><span data-stu-id="9565a-106">When you install the Call Park application, global settings are configured by default.</span></span> <span data-ttu-id="9565a-107">您可以修改全域設定，也可以指定網站特定設定。</span><span class="sxs-lookup"><span data-stu-id="9565a-107">You can modify the global settings, and you can also specify site-specific settings.</span></span> <span data-ttu-id="9565a-108">使用 **New-CsCpsConfiguration** Cmdlet 可建立新的網站特定設定。</span><span class="sxs-lookup"><span data-stu-id="9565a-108">Use the **New-CsCpsConfiguration** cmdlet to create new site-specific settings.</span></span> <span data-ttu-id="9565a-109">使用 **Set-CsCpsConfiguration** Cmdlet 可修改現有設定。</span><span class="sxs-lookup"><span data-stu-id="9565a-109">Use the **Set-CsCpsConfiguration** cmdlet to modify existing settings.</span></span>

> [!NOTE]
> <span data-ttu-id="9565a-110">建議您至少設定 **OnTimeoutURI** 選項，作為當駐留通話逾時且回撥失敗時的後援目的地。</span><span class="sxs-lookup"><span data-stu-id="9565a-110">At a minimum, we recommend that you configure the **OnTimeoutURI** option for the fallback destination to use when a parked call times out and ringback fails.</span></span>

<span data-ttu-id="9565a-111">使用 **New-CsCpsConfiguration** Cmdlet 或 **Set-CsCpsConfiguration** Cmdlet 進行下列任何一項設定：</span><span class="sxs-lookup"><span data-stu-id="9565a-111">Use **New-CsCpsConfiguration** cmdlet or the **Set-CsCpsConfiguration** cmdlet to configure any of the following settings:</span></span>


| <span data-ttu-id="9565a-112">**此選項：**</span><span class="sxs-lookup"><span data-stu-id="9565a-112">**This option:**</span></span>                     | <span data-ttu-id="9565a-113">**指定：**</span><span class="sxs-lookup"><span data-stu-id="9565a-113">**Specifies this:**</span></span>                                                                                                                                                                                                                                                                                                                   |
|:-------------------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="9565a-114">**CallPickupTimeoutThreshold**</span><span class="sxs-lookup"><span data-stu-id="9565a-114">**CallPickupTimeoutThreshold**</span></span> <br/> | <span data-ttu-id="9565a-115">從駐留通話之後到回撥原先接聽該通話的電話之前，需經過的時間長度。</span><span class="sxs-lookup"><span data-stu-id="9565a-115">The amount of time that elapses after a call has been parked before it rings back to the phone where the call was answered.</span></span>  <br/> <span data-ttu-id="9565a-p102">此值必須以 hh:mm:ss 格式輸入，以指定小時、分鐘和秒數。最小值為 10 秒，最大值為 10 分鐘。預設值為 00:01:30。</span><span class="sxs-lookup"><span data-stu-id="9565a-p102">The value must be entered in the format hh:mm:ss to specify the hours, minutes, and seconds. The minimum value is 10 seconds, and the maximum value is 10 minutes. The default is 00:01:30.</span></span>  <br/> |
| <span data-ttu-id="9565a-119">**EnableMusicOnHold**</span><span class="sxs-lookup"><span data-stu-id="9565a-119">**EnableMusicOnHold**</span></span> <br/>          | <span data-ttu-id="9565a-120">駐留通話時是否對來電者播放音樂。</span><span class="sxs-lookup"><span data-stu-id="9565a-120">Whether music plays for a caller while a call is parked.</span></span>  <br/> <span data-ttu-id="9565a-p103">值為 True 或 False。預設為 True。</span><span class="sxs-lookup"><span data-stu-id="9565a-p103">Values are True or False. The default is True.</span></span>  <br/>                                                                                                                                                                                                                 |
| <span data-ttu-id="9565a-123">**MaxCallPickupAttempts**</span><span class="sxs-lookup"><span data-stu-id="9565a-123">**MaxCallPickupAttempts**</span></span> <br/>      | <span data-ttu-id="9565a-p104">在將駐留通話轉接至 **OnTimeoutURI** 指定的後援統一資源識別元 (URI) 之前，需將駐留通話回撥至當初接聽該通話的次數。預設值為 1。</span><span class="sxs-lookup"><span data-stu-id="9565a-p104">The number of times a parked call rings back to the answering phone before it is forwarded to the fallback Uniform Resource Identifier (URI) that is specified for **OnTimeoutURI**. The default is 1.  </span></span><br/>                                                                                                                         |
| <span data-ttu-id="9565a-126">**OnTimeoutURI**</span><span class="sxs-lookup"><span data-stu-id="9565a-126">**OnTimeoutURI**</span></span> <br/>               | <span data-ttu-id="9565a-127">在超過 **MaxCallPickupAttempts** 時，將未接聽的駐留通話路由至的使用者或回應群組的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="9565a-127">The SIP address of the user or response group to which an unanswered parked call is routed when **MaxCallPickupAttempts** is exceeded.</span></span> <br/> <span data-ttu-id="9565a-p105">值必須是以字串 sip: 開頭的 SIP URI。例如，sip:bob@contoso.com。預設沒有轉接位址。</span><span class="sxs-lookup"><span data-stu-id="9565a-p105">Value must be a SIP URI beginning with the string sip:. For example, sip:bob@contoso.com. The default is no forwarding address.  </span></span><br/>                                                   |

### <a name="to-configure-call-park-settings"></a><span data-ttu-id="9565a-131">設定通話駐留設定</span><span class="sxs-lookup"><span data-stu-id="9565a-131">To configure Call Park settings</span></span>

1. <span data-ttu-id="9565a-132">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="9565a-132">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="9565a-133">執行：</span><span class="sxs-lookup"><span data-stu-id="9565a-133">Run:</span></span>

   ```powershell
   New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
   ```

   > [!TIP]
   > <span data-ttu-id="9565a-134">使用 **Get-CsSite** Cmdlet 來識別網站。</span><span class="sxs-lookup"><span data-stu-id="9565a-134">Use the **Get-CsSite** cmdlet to identify the site.</span></span> <span data-ttu-id="9565a-135">如需詳細資訊，請參閱商務用 Skype Server 管理命令介面檔。</span><span class="sxs-lookup"><span data-stu-id="9565a-135">For details, see Skype for Business Server Management Shell documentation.</span></span>

    <span data-ttu-id="9565a-136">例如：</span><span class="sxs-lookup"><span data-stu-id="9565a-136">For example:</span></span>

   ```powershell
   New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com
   ```

## <a name="see-also"></a><span data-ttu-id="9565a-137">另請參閱</span><span class="sxs-lookup"><span data-stu-id="9565a-137">See also</span></span>

[<span data-ttu-id="9565a-138">自訂通話駐留 inSkype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="9565a-138">Customize Call Park music on hold inSkype for Business 2015</span></span>](customize-call-park-music-on-hold.md)

[<span data-ttu-id="9565a-139">New-CsCpsConfiguration</span><span class="sxs-lookup"><span data-stu-id="9565a-139">New-CsCpsConfiguration</span></span>](/powershell/module/skype/new-cscpsconfiguration?view=skype-ps)

[<span data-ttu-id="9565a-140">Set-CsCpsConfiguration</span><span class="sxs-lookup"><span data-stu-id="9565a-140">Set-CsCpsConfiguration</span></span>](/powershell/module/skype/set-cscpsconfiguration?view=skype-ps)

[<span data-ttu-id="9565a-141">Get-CsSite</span><span class="sxs-lookup"><span data-stu-id="9565a-141">Get-CsSite</span></span>](/powershell/module/skype/get-cssite?view=skype-ps)