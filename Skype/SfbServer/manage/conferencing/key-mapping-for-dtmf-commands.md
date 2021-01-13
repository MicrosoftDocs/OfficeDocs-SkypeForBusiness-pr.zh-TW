---
title: 在商務用 Skype Server 中管理 DTMF 命令的按鍵對應
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f91e80ee-a587-4a1b-ac8f-12fa102c098c
description: 摘要：瞭解如何在商務用 Skype Server 中管理雙色調多頻率 (DTMF) 命令的按鍵對應。
ms.openlocfilehash: b804c9a0923630f6de3d1b5af2acdda123cc6331
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828093"
---
# <a name="manage-key-mapping-for-dtmf-commands-in-skype-for-business-server"></a><span data-ttu-id="9ae62-103">在商務用 Skype Server 中管理 DTMF 命令的按鍵對應</span><span class="sxs-lookup"><span data-stu-id="9ae62-103">Manage key mapping for DTMF commands in Skype for Business Server</span></span>
 
<span data-ttu-id="9ae62-104">**摘要：** 瞭解如何在商務用 Skype Server 中管理雙色調多頻率 (DTMF) 命令的按鍵對應。</span><span class="sxs-lookup"><span data-stu-id="9ae62-104">**Summary:** Learn how to manage key mapping of dual-tone multi-frequency (DTMF) commands in Skype for Business Server.</span></span>
  
<span data-ttu-id="9ae62-105">電話撥入式會議使用者可按下電話按鍵上的按鍵，以執行雙音多頻率 (DTMF) 命令。</span><span class="sxs-lookup"><span data-stu-id="9ae62-105">Dial-in conferencing users can press keys on the telephone keypad to perform dual-tone multi-frequency (DTMF) commands.</span></span> <span data-ttu-id="9ae62-106">DTMF 命令可讓撥入會議的使用者控制會議設定 (例如，靜音和 unmuting 本身，或使用電話上的小鍵盤鎖定和解除鎖定會議) 。</span><span class="sxs-lookup"><span data-stu-id="9ae62-106">DTMF commands enable users who dial in to a conference to control conference settings (such as muting and unmuting themselves or locking and unlocking the conference) by using the keypad on their telephone.</span></span> 
  
<span data-ttu-id="9ae62-107">若要管理 DTMF 命令使用的金鑰，請使用商務用 Skype Server 管理命令介面與 **set-csdialinconferencingdtmfconfiguration**、 **Set-CsDialinConferencingDtmfConfiguration** 及 **set-csdialinconferencingdtmfconfiguration** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9ae62-107">To manage the keys used for the DTMF commands, use the Skype for Business Server Management Shell with the **Get-CsDialinConferencingDtmfConfiguration**, **Set-CsDialinConferencingDtmfConfiguration**, and **New-CsDialinConferencingDtmfConfiguration** cmdlets.</span></span>
  
<span data-ttu-id="9ae62-108">當您為網站建立新的 DTMF 設定時，網站設定會優先于通用設定。</span><span class="sxs-lookup"><span data-stu-id="9ae62-108">When you create new DTMF settings for sites, the site settings take precedence over the global settings.</span></span> 

### <a name="manage-the-key-mapping-of-dtmf-commands"></a><span data-ttu-id="9ae62-109">管理 DTMF 命令的按鍵對應</span><span class="sxs-lookup"><span data-stu-id="9ae62-109">Manage the key mapping of DTMF commands</span></span>

1. <span data-ttu-id="9ae62-110">以 RTCUniversalServerAdmins 群組成員或 Cs-ServerAdministrator、CsAdministrator 角色成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="9ae62-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="9ae62-111">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="9ae62-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="9ae62-112">若要查看用於電話撥入式會議的 DTMF 設定，請在命令提示字元中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="9ae62-112">To view the DTMF settings used for dial-in conferencing, run the following command at the command prompt :</span></span>
    
   ```PowerShell
   Get-CsDialinConferencingDtmfConfiguration
   ```

4. <span data-ttu-id="9ae62-113">若要修改電話撥入式會議所用的 DTMF 設定，請執行下列 Cmdlet，並指定要變更之每個選項的按鍵。</span><span class="sxs-lookup"><span data-stu-id="9ae62-113">To modify the DTMF settings used for dial-in conferencing, run the following cmdlet and specify the key to be pressed for each option that you want to change:</span></span>
    
   ```PowerShell
   Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
   [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
   [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
   [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
   [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
   ```

5. <span data-ttu-id="9ae62-114"> (選用) 若要為特定網站建立其他 DTMF 命令集，請使用具有網站身分識別的 **set-csdialinconferencingdtmfconfiguration** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9ae62-114">(Optional) To create additional sets of DTMF commands for specific sites, use the **New-CsDialinConferencingDtmfConfiguration** cmdlet with a site identity.</span></span>
    
<span data-ttu-id="9ae62-115">下列範例會將已按下的按鍵，以啟用或停用用來啟用或停用的宣告，以及已按下以靜音和取消靜音所有參與者的按鍵。</span><span class="sxs-lookup"><span data-stu-id="9ae62-115">The following example swaps the key that is pressed to enable or disable announcements and the key that is pressed to mute and unmute all participants.</span></span> <span data-ttu-id="9ae62-116">由於沒有指定身分識別，因此這些變更會套用到全域 DTMF 設定：</span><span class="sxs-lookup"><span data-stu-id="9ae62-116">Because no Identity is specified, these changes apply to the global DTMF settings:</span></span>
  
```PowerShell
Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
```

<span data-ttu-id="9ae62-117">如需詳細資訊，請參閱 [Get-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps)、 [Set-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps)和 [set-csdialinconferencingdtmfconfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="9ae62-117">For more information, see [Get-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps), [Set-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps), and [New-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps).</span></span>
  

