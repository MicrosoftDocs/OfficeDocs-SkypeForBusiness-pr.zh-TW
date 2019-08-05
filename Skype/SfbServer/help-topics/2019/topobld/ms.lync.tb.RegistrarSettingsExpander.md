---
title: 登錄器設定展開工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.RegistrarSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c7486ab3-61fd-45c6-9edc-a15535f273ff
ROBOTS: NOINDEX, NOFOLLOW
description: 復原功能可為註冊機構池提供高可用性和災害復原。 在主要註冊機發生故障時提供備份註冊機構, 備份註冊機構可能會接管失敗的註冊機, 讓使用者可以登入及通訊。 根據主要註冊機構失敗的系統, 使用者可能會遇到精簡功能。
ms.openlocfilehash: 122124140c93afb3ce58b1d9423839f3e21dbcad
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188023"
---
# <a name="registrar-settings-expander"></a><span data-ttu-id="1553f-105">登錄器設定展開工具</span><span class="sxs-lookup"><span data-stu-id="1553f-105">Registrar Settings Expander</span></span>
 
<span data-ttu-id="1553f-106">復原功能可為註冊機構池提供高可用性和災害復原。</span><span class="sxs-lookup"><span data-stu-id="1553f-106">Resiliency provides high availability and disaster recovery for the Registrar pool.</span></span> <span data-ttu-id="1553f-107">在主要註冊機發生故障時提供備份註冊機構, 備份註冊機構可能會接管失敗的註冊機, 讓使用者可以登入及通訊。</span><span class="sxs-lookup"><span data-stu-id="1553f-107">By providing a backup Registrar in the event of failure of the primary Registrar, the backup Registrar can take over for the failed Registrar, allowing users to log on and communicate.</span></span> <span data-ttu-id="1553f-108">根據主要註冊機構失敗的系統, 使用者可能會遇到精簡功能。</span><span class="sxs-lookup"><span data-stu-id="1553f-108">Users can potentially experience reduced functionality, depending on which systems have failed with the primary Registrar.</span></span>
  
<span data-ttu-id="1553f-109">在 Survivable 分支裝置或 Survivable 分支伺服器的 [**編輯屬性**] 對話方塊的 [**復原**] 區段中, 您可以變更下列設定:</span><span class="sxs-lookup"><span data-stu-id="1553f-109">In the **Resiliency** section of the **Edit Properties** dialog box for your Survivable Branch Appliance or Survivable Branch Server, you can change the following settings:</span></span>
  
- <span data-ttu-id="1553f-110">**關聯的使用者服務與備份註冊機構池**在下拉式清單中, 選取要充當 Survivable 分支裝置或 Survivable 分支伺服器之備份註冊機構的企業版前端池或標準版前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="1553f-110">**Associated User service and backup Registrar pool** In the drop-down list, select the Enterprise Edition Front End pool or Standard Edition Front End Server that is to act as the backup Registrar for the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
- <span data-ttu-id="1553f-111">**啟用容錯移轉與回切**選取此設定, 即可自動偵測失敗的註冊機構, 並自動判斷主要註冊機構已還原並準備好繼續註冊程式。</span><span class="sxs-lookup"><span data-stu-id="1553f-111">**Enable Failover and Failback** Select this setting to allow for the automatic detection of a failed Registrar and the automatic determination that the primary Registrar is back up and ready to resume the Registrar process.</span></span>
    
- <span data-ttu-id="1553f-112">**失敗偵測間隔 (秒)** 輸入在判斷主要註冊機構失敗前應經過的秒數。</span><span class="sxs-lookup"><span data-stu-id="1553f-112">**Failure detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar has failed.</span></span> <span data-ttu-id="1553f-113">預設值為120秒。</span><span class="sxs-lookup"><span data-stu-id="1553f-113">The default value is 120 seconds.</span></span> <span data-ttu-id="1553f-114">如果您選取 [**啟用容錯移轉及回切**], 此欄位就是必要的。</span><span class="sxs-lookup"><span data-stu-id="1553f-114">This field is required if you select **Enable Failover and Failback**.</span></span>
    
- <span data-ttu-id="1553f-115">**回退偵測間隔 (秒)** 輸入要經過多少秒, 才能確定主要註冊機構已備份。</span><span class="sxs-lookup"><span data-stu-id="1553f-115">**Fallback detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar is backed up.</span></span> <span data-ttu-id="1553f-116">預設值為240秒。</span><span class="sxs-lookup"><span data-stu-id="1553f-116">The default value is 240 seconds.</span></span> <span data-ttu-id="1553f-117">如果您選取 [**啟用容錯移轉及回退**], 此欄位就是必要的。</span><span class="sxs-lookup"><span data-stu-id="1553f-117">This field is required if you select **Enable Failover and Fallback**.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="1553f-118">當您定義失敗偵測間隔和回退偵測間隔時, 請小心不要輸入一個間隔, 如果註冊機構無法在短期內回應, 就會導致容錯移轉和回退發生。</span><span class="sxs-lookup"><span data-stu-id="1553f-118">When you define the failure detection interval and the fallback detection interval, be careful not to enter an interval that will cause the failover and fallback to occur if the Registrar fails to respond for a short period of time.</span></span> <span data-ttu-id="1553f-119">主要註冊機構可能不會根據載入池或伺服器的短時段來回應。</span><span class="sxs-lookup"><span data-stu-id="1553f-119">It is possible that the primary Registrar may not respond for short periods of time based on the loading of the pool or servers.</span></span> 
  

