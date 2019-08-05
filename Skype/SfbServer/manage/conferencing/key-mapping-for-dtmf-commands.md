---
title: 在商務用 Skype Server 中管理 DTMF 命令的金鑰組應
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f91e80ee-a587-4a1b-ac8f-12fa102c098c
description: '摘要: 瞭解如何在商務用 Skype Server 中管理雙音調多頻率 (DTMF) 命令的按鍵對應。'
ms.openlocfilehash: 713c72941a8cc147b751c82b9dbbfbc2c2d16837
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189652"
---
# <a name="manage-key-mapping-for-dtmf-commands-in-skype-for-business-server"></a><span data-ttu-id="c5afe-103">在商務用 Skype Server 中管理 DTMF 命令的金鑰組應</span><span class="sxs-lookup"><span data-stu-id="c5afe-103">Manage key mapping for DTMF commands in Skype for Business Server</span></span>
 
<span data-ttu-id="c5afe-104">**摘要:** 瞭解如何在商務用 Skype Server 中管理雙音調多頻率 (DTMF) 命令的按鍵對應。</span><span class="sxs-lookup"><span data-stu-id="c5afe-104">**Summary:** Learn how to manage key mapping of dual-tone multi-frequency (DTMF) commands in Skype for Business Server.</span></span>
  
<span data-ttu-id="c5afe-105">電話撥入式會議使用者可以按電話鍵臺上的按鍵, 以執行雙音調多頻率 (DTMF) 命令。</span><span class="sxs-lookup"><span data-stu-id="c5afe-105">Dial-in conferencing users can press keys on the telephone keypad to perform dual-tone multi-frequency (DTMF) commands.</span></span> <span data-ttu-id="c5afe-106">DTMF 命令可讓撥入會議的使用者控制會議設定 (例如靜音及 unmuting 本身, 或是使用電話鍵, 在通話中鎖定及解除鎖定會議)。</span><span class="sxs-lookup"><span data-stu-id="c5afe-106">DTMF commands enable users who dial in to a conference to control conference settings (such as muting and unmuting themselves or locking and unlocking the conference) by using the keypad on their telephone.</span></span> 
  
<span data-ttu-id="c5afe-107">若要管理 DTMF 命令使用的金鑰, 請使用商務用 Skype 伺服器管理命令介面, 並提供**CsDialinConferencingDtmfConfiguration**、 **CsDialinConferencingDtmfConfiguration**和**新的-CsDialinConferencingDtmfConfiguration** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c5afe-107">To manage the keys used for the DTMF commands, use the Skype for Business Server Management Shell with the **Get-CsDialinConferencingDtmfConfiguration**, **Set-CsDialinConferencingDtmfConfiguration**, and **New-CsDialinConferencingDtmfConfiguration** cmdlets.</span></span>
  
<span data-ttu-id="c5afe-108">當您為網站建立新的 DTMF 設定時, 網站設定會優先于全域設定。</span><span class="sxs-lookup"><span data-stu-id="c5afe-108">When you create new DTMF settings for sites, the site settings take precedence over the global settings.</span></span> 

### <a name="manage-the-key-mapping-of-dtmf-commands"></a><span data-ttu-id="c5afe-109">管理 DTMF 命令的金鑰組應</span><span class="sxs-lookup"><span data-stu-id="c5afe-109">Manage the key mapping of DTMF commands</span></span>

1. <span data-ttu-id="c5afe-110">以 RTCUniversalServerAdmins 群組的成員或 Cs-ServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="c5afe-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="c5afe-111">啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="c5afe-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="c5afe-112">若要查看電話撥入式會議所用的 DTMF 設定, 請在命令提示字元執行下列命令:</span><span class="sxs-lookup"><span data-stu-id="c5afe-112">To view the DTMF settings used for dial-in conferencing, run the following command at the command prompt :</span></span>
    
   ```
   Get-CsDialinConferencingDtmfConfiguration
   ```

4. <span data-ttu-id="c5afe-113">若要修改用於電話撥入式會議的 DTMF 設定, 請執行下列 Cmdlet, 並指定要為每個您要變更的選項按下的索引鍵:</span><span class="sxs-lookup"><span data-stu-id="c5afe-113">To modify the DTMF settings used for dial-in conferencing, run the following cmdlet and specify the key to be pressed for each option that you want to change:</span></span>
    
   ```
   Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
   [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
   [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
   [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
   [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
   ```

5. <span data-ttu-id="c5afe-114">可選若要針對特定網站建立其他 DTMF 命令組, 請搭配使用**CsDialinConferencingDtmfConfiguration** Cmdlet 搭配網站身分識別。</span><span class="sxs-lookup"><span data-stu-id="c5afe-114">(Optional) To create additional sets of DTMF commands for specific sites, use the **New-CsDialinConferencingDtmfConfiguration** cmdlet with a site identity.</span></span>
    
<span data-ttu-id="c5afe-115">下列範例會交換按下的按鍵來啟用或停用宣告, 以及按下來將所有參與者靜音和取消靜音的按鍵。</span><span class="sxs-lookup"><span data-stu-id="c5afe-115">The following example swaps the key that is pressed to enable or disable announcements and the key that is pressed to mute and unmute all participants.</span></span> <span data-ttu-id="c5afe-116">由於沒有指定身分識別, 這些變更會套用到全域 DTMF 設定:</span><span class="sxs-lookup"><span data-stu-id="c5afe-116">Because no Identity is specified, these changes apply to the global DTMF settings:</span></span>
  
```
Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
```

<span data-ttu-id="c5afe-117">如需詳細資訊, 請參閱[CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps)、 [Set CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps)和[CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="c5afe-117">For more information, see [Get-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps), [Set-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps), and [New-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps).</span></span>
  

