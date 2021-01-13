---
title: 登錄器設定展開工具
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.RegistrarSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c7486ab3-61fd-45c6-9edc-a15535f273ff
description: 恢復功能提供註冊區集區的高可用性和嚴重損壞修復。 藉由在主要登錄器發生失敗時提供備份登錄器，備份登錄器可以接手失敗的登錄器，並允許使用者登入和通訊。 使用者可能會發現功能減少，視主要登錄器上失敗的系統而定。
ms.openlocfilehash: 8ab5fc804b6fad1f049e70477d7c16cb35111f79
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818293"
---
# <a name="registrar-settings-expander"></a><span data-ttu-id="702ce-105">登錄器設定展開工具</span><span class="sxs-lookup"><span data-stu-id="702ce-105">Registrar Settings Expander</span></span>
 
<span data-ttu-id="702ce-106">恢復功能提供註冊區集區的高可用性和嚴重損壞修復。</span><span class="sxs-lookup"><span data-stu-id="702ce-106">Resiliency provides high availability and disaster recovery for the Registrar pool.</span></span> <span data-ttu-id="702ce-107">藉由在主要登錄器發生失敗時提供備份登錄器，備份登錄器可以接手失敗的登錄器，並允許使用者登入和通訊。</span><span class="sxs-lookup"><span data-stu-id="702ce-107">By providing a backup Registrar in the event of failure of the primary Registrar, the backup Registrar can take over for the failed Registrar, allowing users to log on and communicate.</span></span> <span data-ttu-id="702ce-108">使用者可能會發現功能減少，視主要登錄器上失敗的系統而定。</span><span class="sxs-lookup"><span data-stu-id="702ce-108">Users can potentially experience reduced functionality, depending on which systems have failed with the primary Registrar.</span></span>
  
<span data-ttu-id="702ce-109">在您 Survivable Branch Appliance 或 Survivable Branch Server 的 **[編輯內容]** 對話方塊 **[恢復能力]** 區段中，可以變更下列設定：</span><span class="sxs-lookup"><span data-stu-id="702ce-109">In the **Resiliency** section of the **Edit Properties** dialog box for your Survivable Branch Appliance or Survivable Branch Server, you can change the following settings:</span></span>
  
- <span data-ttu-id="702ce-110">**關聯的使用者服務和備份註冊區集** 區在下拉式清單中，選取 Enterprise Edition 前端集區或 Standard Edition 前端伺服器，以充當 Survivable Branch 裝置或 Survivable Branch 伺服器的備份註冊機。</span><span class="sxs-lookup"><span data-stu-id="702ce-110">**Associated User service and backup Registrar pool** In the drop-down list, select the Enterprise Edition Front End pool or Standard Edition Front End Server that is to act as the backup Registrar for the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
- <span data-ttu-id="702ce-111">**啟用容錯移轉和回切** 選取此設定，以允許自動偵測失敗的註冊機構，並自動判斷主要註冊機已備份，且可以繼續進行註冊程式的處理常式。</span><span class="sxs-lookup"><span data-stu-id="702ce-111">**Enable Failover and Failback** Select this setting to allow for the automatic detection of a failed Registrar and the automatic determination that the primary Registrar is back up and ready to resume the Registrar process.</span></span>
    
- <span data-ttu-id="702ce-112">**失敗偵測間隔 (秒)** 輸入在判斷主要註冊機構失敗之前所應經過的秒數。</span><span class="sxs-lookup"><span data-stu-id="702ce-112">**Failure detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar has failed.</span></span> <span data-ttu-id="702ce-113">預設值為 120 秒。</span><span class="sxs-lookup"><span data-stu-id="702ce-113">The default value is 120 seconds.</span></span> <span data-ttu-id="702ce-114">如果您選取 [ **啟用容錯移轉和容錯回復**]，則此欄位是必要的。</span><span class="sxs-lookup"><span data-stu-id="702ce-114">This field is required if you select **Enable Failover and Failback**.</span></span>
    
- <span data-ttu-id="702ce-115">**後備偵測間隔 (秒)** 輸入在判斷主要註冊機已備份之前，應經過的秒數。</span><span class="sxs-lookup"><span data-stu-id="702ce-115">**Fallback detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar is backed up.</span></span> <span data-ttu-id="702ce-116">預設值為240秒。</span><span class="sxs-lookup"><span data-stu-id="702ce-116">The default value is 240 seconds.</span></span> <span data-ttu-id="702ce-117">如果您選取 [ **啟用容錯移轉和回退**]，則需要此欄位。</span><span class="sxs-lookup"><span data-stu-id="702ce-117">This field is required if you select **Enable Failover and Fallback**.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="702ce-p105">當您定義失敗偵測間隔和後援偵測間隔時，請小心不要讓輸入的間隔導致在登錄器短時間無法回應時，發生容錯移轉和容錯回復。根據集區或伺服器的負載，主要登錄器可能會在短時間內無法回應。</span><span class="sxs-lookup"><span data-stu-id="702ce-p105">When you define the failure detection interval and the fallback detection interval, be careful not to enter an interval that will cause the failover and fallback to occur if the Registrar fails to respond for a short period of time. It is possible that the primary Registrar may not respond for short periods of time based on the loading of the pool or servers.</span></span> 
  

