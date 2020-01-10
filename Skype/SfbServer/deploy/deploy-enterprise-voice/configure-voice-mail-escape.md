---
title: 在商務用 Skype 中設定語音信箱轉義
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
description: 摘要：瞭解如何使用商務用 Skype Server Management 命令介面，在商務用 Skype Server 中設定語音信箱轉義。
ms.openlocfilehash: 27f283f4bfb64aa950bd9e72a9d6fdc17df91ba0
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001213"
---
# <a name="configure-voice-mail-escape-in-skype-for-business"></a><span data-ttu-id="e35c5-103">在商務用 Skype 中設定語音信箱轉義</span><span class="sxs-lookup"><span data-stu-id="e35c5-103">Configure voice mail escape in Skype for Business</span></span>

<span data-ttu-id="e35c5-104">**摘要：** 瞭解如何使用商務用 Skype Server 管理命令介面，在商務用 Skype Server 中設定語音信箱轉義。</span><span class="sxs-lookup"><span data-stu-id="e35c5-104">**Summary:** Learn how to configure voice mail escape in Skype for Business Server by using the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="e35c5-105">當使用者設定同時撥打至行動電話時，如果行動電話關閉、不使用電池電源或超出範圍，通常會將呼叫者路由到使用者的個人語音信箱。</span><span class="sxs-lookup"><span data-stu-id="e35c5-105">When a user configures simultaneous ringing to a mobile phone, a caller will typically be routed to the user's personal voice mail if the mobile phone is turned off, out of battery power, or out of range.</span></span> <span data-ttu-id="e35c5-106">在商務用 Skype Server 中，使用者可以選擇要將商務相關通話路由至其公司語音信箱系統。</span><span class="sxs-lookup"><span data-stu-id="e35c5-106">With Skype for Business Server , users can opt to have business-related calls routed to their corporate voice mail system.</span></span> <span data-ttu-id="e35c5-107">具體來說，您可以設定計時器，如果在所定義的時間範圍內，由承運人的語音信箱應答通話，商務用 Skype Server 將會與載波的語音信箱系統（與使用者的個人語音信箱）斷開連線，而使用者的公司系統中的剩餘端點會繼續撥打。</span><span class="sxs-lookup"><span data-stu-id="e35c5-107">Specifically, a timer can be configured, and if the call is answered by the carrier's voice mail within the range of time defined, Skype for Business Server will disconnect from the carrier's voice mail system (and the user's personal voice mail), while the user's remaining endpoints in the corporate system continue to ring.</span></span> <span data-ttu-id="e35c5-108">如此一來，來電者就會自動路由到使用者的公司語音信箱。</span><span class="sxs-lookup"><span data-stu-id="e35c5-108">This way, the caller is automatically routed to the user's corporate voice mail.</span></span>

<span data-ttu-id="e35c5-109">此設定是使用商務用 Skype Server Management Shell Cmdlet （ **CsVoicePolicy**）在語音原則層級執行，並使用下列參數。</span><span class="sxs-lookup"><span data-stu-id="e35c5-109">This configuration is performed using the Skype for Business Server Management Shell cmdlet, **Set-CsVoicePolicy**, at the voice policy level, with the following parameters.</span></span>

### <a name="to-configure-voice-mail-escape"></a><span data-ttu-id="e35c5-110">若要設定語音信箱轉義</span><span class="sxs-lookup"><span data-stu-id="e35c5-110">To configure voice mail escape</span></span>

1. <span data-ttu-id="e35c5-111">啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype 2015**]，然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="e35c5-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="e35c5-112">指定下列參數來**設定-CsVoicePolicy**：</span><span class="sxs-lookup"><span data-stu-id="e35c5-112">Specify the following parameters to **Set-CsVoicePolicy**:</span></span>

   - <span data-ttu-id="e35c5-113">**EnableVoicemailEscapeTimer** -啟用或停用轉義計時器。</span><span class="sxs-lookup"><span data-stu-id="e35c5-113">**EnableVoicemailEscapeTimer** - Enables or disables the escape timer.</span></span>

   - <span data-ttu-id="e35c5-114">**PSTNVoicemailEscapeTimer** -指定超時值（以毫秒為單位）。</span><span class="sxs-lookup"><span data-stu-id="e35c5-114">**PSTNVoicemailEscapeTimer** - Specifies the timeout value in milliseconds.</span></span> <span data-ttu-id="e35c5-115">預設值為1500毫秒，值的範圍可以是0毫秒到8000毫秒。</span><span class="sxs-lookup"><span data-stu-id="e35c5-115">The default value is 1500 milliseconds, and the value can range from 0 milliseconds to 8000 milliseconds.</span></span>

## <a name="example"></a><span data-ttu-id="e35c5-116">範例</span><span class="sxs-lookup"><span data-stu-id="e35c5-116">Example</span></span>

```powershell
Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500
```

## <a name="see-also"></a><span data-ttu-id="e35c5-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e35c5-117">See also</span></span>

[<span data-ttu-id="e35c5-118">設定語音原則和 PSTN 使用記錄，以授權通話功能和許可權</span><span class="sxs-lookup"><span data-stu-id="e35c5-118">Configuring Voice Policies and PSTN Usage Records to Authorize Calling Features and Privileges</span></span>](https://technet.microsoft.com/library/63f22010-a3d7-4cbd-86e8-6fc0e13c2b84.aspx)

