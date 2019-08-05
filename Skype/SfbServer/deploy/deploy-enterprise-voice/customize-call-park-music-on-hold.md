---
title: 在商務用 inSkype 上自訂通話寄存音樂
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
ms.assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
description: 在商務用 Skype Server Enterprise Voice 中, 自訂通話寄存音樂以進行封存。
ms.openlocfilehash: 4111bcc42a3820e3957f526e360264aa7d098d05
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190408"
---
# <a name="customize-call-park-music-on-hold-inskype-for-business"></a><span data-ttu-id="4ed04-103">在商務用 inSkype 上自訂通話寄存音樂</span><span class="sxs-lookup"><span data-stu-id="4ed04-103">Customize Call Park music on hold inSkype for Business</span></span>
 
<span data-ttu-id="4ed04-104">在商務用 Skype Server Enterprise Voice 中, 自訂通話寄存音樂以進行封存。</span><span class="sxs-lookup"><span data-stu-id="4ed04-104">Customize the Call Park music on hold in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="4ed04-105">您可以指定自己的音樂檔案以供等候音樂使用, 而不是隨商務用 Skype 伺服器隨附的預設音樂檔案。</span><span class="sxs-lookup"><span data-stu-id="4ed04-105">You can specify your own music file to use for music on hold, instead of the default music file that ships with Skype for Business Server.</span></span> <span data-ttu-id="4ed04-106">若要在保留時自訂音樂, 請使用**CsCallParkServiceMusicOnHoldFile** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4ed04-106">To customize music on hold, use the **Set-CsCallParkServiceMusicOnHoldFile** cmdlet.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4ed04-107">如果您自訂 [等候音樂] 並想要在多個網站上擁有相同的音樂, 您必須針對每個執行通話駐留應用程式的網站設定音樂檔案。</span><span class="sxs-lookup"><span data-stu-id="4ed04-107">If you customize music on hold and want the same music for multiple sites, you must configure the music file for each site that runs the Call Park application.</span></span> 
  
### <a name="to-customize-the-music-file"></a><span data-ttu-id="4ed04-108">自訂音樂檔案</span><span class="sxs-lookup"><span data-stu-id="4ed04-108">To customize the music file</span></span>

1. <span data-ttu-id="4ed04-109">登入商務用 Skype Server Management Shell 的電腦是以 RTCUniversalServerAdmins 群組的成員或必要的使用者權利來安裝, 如**委派設定許可權**中所述。</span><span class="sxs-lookup"><span data-stu-id="4ed04-109">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="4ed04-110">啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="4ed04-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="4ed04-111">用盡</span><span class="sxs-lookup"><span data-stu-id="4ed04-111">Run:</span></span>
    
   ```
   Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte >
   ```

    > [!TIP]
    > <span data-ttu-id="4ed04-112">使用**CsService** Cmdlet 來識別服務。</span><span class="sxs-lookup"><span data-stu-id="4ed04-112">Use the **Get-CsService** cmdlet to identify the service.</span></span> <span data-ttu-id="4ed04-113">如需詳細資訊, 請參閱[CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="4ed04-113">For details, see [Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps).</span></span> 
  
    <span data-ttu-id="4ed04-114">下列範例顯示如何取得檔案的內容 (soothingmusic) 作為位元組陣列, 並將它指派給變數。</span><span class="sxs-lookup"><span data-stu-id="4ed04-114">The following example shows how to obtain the contents of a file, soothingmusic.wma, as a byte array and assign it to a variable.</span></span> <span data-ttu-id="4ed04-115">然後, 音訊檔案會指派為 [通話駐留] 的 [音樂保留] 檔案。</span><span class="sxs-lookup"><span data-stu-id="4ed04-115">Then the audio file is assigned as the music-on-hold file for Call Park.</span></span> <span data-ttu-id="4ed04-116">如需詳細資訊, 請參閱[設定 CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="4ed04-116">For details, see [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps).</span></span>
    
   ```
   $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
   Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a
   ```

## <a name="see-also"></a><span data-ttu-id="4ed04-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="4ed04-117">See also</span></span>

[<span data-ttu-id="4ed04-118">Set-CsCallParkServiceMusicOnHoldFile</span><span class="sxs-lookup"><span data-stu-id="4ed04-118">Set-CsCallParkServiceMusicOnHoldFile</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
  
[<span data-ttu-id="4ed04-119">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="4ed04-119">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)
