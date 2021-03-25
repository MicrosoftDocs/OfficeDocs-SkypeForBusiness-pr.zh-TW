---
title: 在商務用 Skype 中設定語音信箱轉義
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
ms.assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
description: 摘要：瞭解如何使用商務用 Skype Server 管理命令介面，在商務用 Skype Server 中設定語音信箱轉義。
ms.openlocfilehash: c74142cf3b0f6c9d5a871e116d8e163a095ad3cd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51106369"
---
# <a name="configure-voice-mail-escape-in-skype-for-business"></a><span data-ttu-id="ab5d4-103">在商務用 Skype 中設定語音信箱轉義</span><span class="sxs-lookup"><span data-stu-id="ab5d4-103">Configure voice mail escape in Skype for Business</span></span>

<span data-ttu-id="ab5d4-104">**摘要：** 瞭解如何使用商務用 Skype Server 管理命令介面，在商務用 Skype Server 中設定語音信箱轉義。</span><span class="sxs-lookup"><span data-stu-id="ab5d4-104">**Summary:** Learn how to configure voice mail escape in Skype for Business Server by using the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="ab5d4-105">當使用者設定同時響鈴的行動電話時，如果行動電話關閉、電池計量不足或超出範圍，則通常會將來電者路由傳送至使用者的個人語音信箱。</span><span class="sxs-lookup"><span data-stu-id="ab5d4-105">When a user configures simultaneous ringing to a mobile phone, a caller will typically be routed to the user's personal voice mail if the mobile phone is turned off, out of battery power, or out of range.</span></span> <span data-ttu-id="ab5d4-106">在商務用 Skype Server 中，使用者可以選擇讓業務相關的來電路由傳送至其公司語音信箱系統。</span><span class="sxs-lookup"><span data-stu-id="ab5d4-106">With Skype for Business Server , users can opt to have business-related calls routed to their corporate voice mail system.</span></span> <span data-ttu-id="ab5d4-107">具體而言，您可以設定 timer，而且當電信公司的語音信箱在所定義的時間範圍內接聽來電時，商務用 Skype 伺服器會中斷與電信公司的語音信箱系統的連線 (和使用者的個人語音信箱) ，而使用者在公司系統中的剩餘端點會繼續振鈴。</span><span class="sxs-lookup"><span data-stu-id="ab5d4-107">Specifically, a timer can be configured, and if the call is answered by the carrier's voice mail within the range of time defined, Skype for Business Server will disconnect from the carrier's voice mail system (and the user's personal voice mail), while the user's remaining endpoints in the corporate system continue to ring.</span></span> <span data-ttu-id="ab5d4-108">如此一來，來電者就會自動路由傳送至使用者的公司語音信箱。</span><span class="sxs-lookup"><span data-stu-id="ab5d4-108">This way, the caller is automatically routed to the user's corporate voice mail.</span></span>

<span data-ttu-id="ab5d4-109">使用商務用 Skype Server 管理命令介面 Cmdlet **Set-CsVoicePolicy**，使用下列參數，在語音原則層級執行此設定。</span><span class="sxs-lookup"><span data-stu-id="ab5d4-109">This configuration is performed using the Skype for Business Server Management Shell cmdlet, **Set-CsVoicePolicy**, at the voice policy level, with the following parameters.</span></span>

### <a name="to-configure-voice-mail-escape"></a><span data-ttu-id="ab5d4-110">設定語音信箱轉義</span><span class="sxs-lookup"><span data-stu-id="ab5d4-110">To configure voice mail escape</span></span>

1. <span data-ttu-id="ab5d4-111">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="ab5d4-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="ab5d4-112">指定下列要 **Set-CsVoicePolicy** 的參數：</span><span class="sxs-lookup"><span data-stu-id="ab5d4-112">Specify the following parameters to **Set-CsVoicePolicy**:</span></span>

   - <span data-ttu-id="ab5d4-113">**EnableVoicemailEscapeTimer** -啟用或停用轉義計時器。</span><span class="sxs-lookup"><span data-stu-id="ab5d4-113">**EnableVoicemailEscapeTimer** - Enables or disables the escape timer.</span></span>

   - <span data-ttu-id="ab5d4-114">**PSTNVoicemailEscapeTimer** -指定超時值，以毫秒為單位。</span><span class="sxs-lookup"><span data-stu-id="ab5d4-114">**PSTNVoicemailEscapeTimer** - Specifies the timeout value in milliseconds.</span></span> <span data-ttu-id="ab5d4-115">預設值為1500毫秒，值的範圍為0毫秒到8000毫秒。</span><span class="sxs-lookup"><span data-stu-id="ab5d4-115">The default value is 1500 milliseconds, and the value can range from 0 milliseconds to 8000 milliseconds.</span></span>

## <a name="example"></a><span data-ttu-id="ab5d4-116">範例</span><span class="sxs-lookup"><span data-stu-id="ab5d4-116">Example</span></span>

```powershell
Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500
```

## <a name="see-also"></a><span data-ttu-id="ab5d4-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ab5d4-117">See also</span></span>

[<span data-ttu-id="ab5d4-118">設定用於授權撥號功能和權限的語音原則和 PSTN 使用方式記錄</span><span class="sxs-lookup"><span data-stu-id="ab5d4-118">Configuring Voice Policies and PSTN Usage Records to Authorize Calling Features and Privileges</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges)