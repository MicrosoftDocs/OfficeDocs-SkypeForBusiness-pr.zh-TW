---
title: 自訂通話駐留 inSkype for Business 的等候音樂
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
ms.assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
description: 在商務用 Skype Server Enterprise Voice 中，自訂通話駐留等候音樂。
ms.openlocfilehash: 87dea58d9e339293b047373ac6c44a16bed3bdb3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093041"
---
# <a name="customize-call-park-music-on-hold-inskype-for-business"></a><span data-ttu-id="17140-103">自訂通話駐留 inSkype for Business 的等候音樂</span><span class="sxs-lookup"><span data-stu-id="17140-103">Customize Call Park music on hold inSkype for Business</span></span>
 
<span data-ttu-id="17140-104">在商務用 Skype Server Enterprise Voice 中，自訂通話駐留等候音樂。</span><span class="sxs-lookup"><span data-stu-id="17140-104">Customize the Call Park music on hold in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="17140-105">您可以指定自己的音樂檔案，以用於保留等候音樂，而不是隨商務用 Skype Server 隨附的預設音樂檔。</span><span class="sxs-lookup"><span data-stu-id="17140-105">You can specify your own music file to use for music on hold, instead of the default music file that ships with Skype for Business Server.</span></span> <span data-ttu-id="17140-106">如要自訂等候音樂，請使用 **Set-CsCallParkServiceMusicOnHoldFile** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="17140-106">To customize music on hold, use the **Set-CsCallParkServiceMusicOnHoldFile** cmdlet.</span></span>
  
> [!NOTE]
> <span data-ttu-id="17140-107">如果您自訂等候音樂，且想要將相同的音樂用於多個網站，則必須為每個執行通話駐留應用程式的網站設定音樂檔。</span><span class="sxs-lookup"><span data-stu-id="17140-107">If you customize music on hold and want the same music for multiple sites, you must configure the music file for each site that runs the Call Park application.</span></span> 
  
### <a name="to-customize-the-music-file"></a><span data-ttu-id="17140-108">自訂音樂檔案</span><span class="sxs-lookup"><span data-stu-id="17140-108">To customize the music file</span></span>

1. <span data-ttu-id="17140-109">登入安裝商務用 Skype Server 管理命令介面的電腦，並將其安裝為 RTCUniversalServerAdmins 群組的成員，或使用 **委派安裝許可權** 中所述的必要使用者權限。</span><span class="sxs-lookup"><span data-stu-id="17140-109">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="17140-110">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="17140-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="17140-111">執行：</span><span class="sxs-lookup"><span data-stu-id="17140-111">Run:</span></span>
    
   ```powershell
   Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte >
   ```

    > [!TIP]
    > <span data-ttu-id="17140-112">使用 **Get-CsService** Cmdlet 來識別服務。</span><span class="sxs-lookup"><span data-stu-id="17140-112">Use the **Get-CsService** cmdlet to identify the service.</span></span> <span data-ttu-id="17140-113">如需詳細資訊，請參閱 [Get-CsService](/powershell/module/skype/get-csservice?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="17140-113">For details, see [Get-CsService](/powershell/module/skype/get-csservice?view=skype-ps).</span></span> 
  
    <span data-ttu-id="17140-114">下列範例顯示如何取得檔案 soothingmusic.wma 的位元組陣列內容，並將其指派給變數。</span><span class="sxs-lookup"><span data-stu-id="17140-114">The following example shows how to obtain the contents of a file, soothingmusic.wma, as a byte array and assign it to a variable.</span></span> <span data-ttu-id="17140-115">然後將音訊檔案指派為通話駐留時的等候音樂檔案。</span><span class="sxs-lookup"><span data-stu-id="17140-115">Then the audio file is assigned as the music-on-hold file for Call Park.</span></span> <span data-ttu-id="17140-116">如需詳細資訊，請參閱 [Set-CsCallParkServiceMusicOnHoldFile](/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="17140-116">For details, see [Set-CsCallParkServiceMusicOnHoldFile](/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps).</span></span>
    
   ```powershell
   $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
   Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a
   ```

## <a name="see-also"></a><span data-ttu-id="17140-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="17140-117">See also</span></span>

[<span data-ttu-id="17140-118">Set-CsCallParkServiceMusicOnHoldFile</span><span class="sxs-lookup"><span data-stu-id="17140-118">Set-CsCallParkServiceMusicOnHoldFile</span></span>](/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
  
[<span data-ttu-id="17140-119">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="17140-119">Get-CsService</span></span>](/powershell/module/skype/get-csservice?view=skype-ps)