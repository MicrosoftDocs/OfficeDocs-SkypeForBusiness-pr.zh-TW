---
title: 登錄器 SBA 設定展開工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.RegistrarSBASettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 68ea1fc0-9cd1-4e0a-995e-b53845493477
description: 您可以編輯 [恢復] 設定，並設定下列內容：
ms.openlocfilehash: 6424b43ea7c56760bb8d58ee35d9804c49c435dd
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217214"
---
# <a name="registrar-sba-settings-expander"></a><span data-ttu-id="cba37-103">登錄器 SBA 設定展開工具</span><span class="sxs-lookup"><span data-stu-id="cba37-103">Registrar SBA Settings Expander</span></span>

<span data-ttu-id="cba37-104">您可以編輯 [恢復]\*\*\*\* 設定，並設定下列內容：</span><span class="sxs-lookup"><span data-stu-id="cba37-104">You edit the settings for **Resiliency** and configure the following properties:</span></span>

- <span data-ttu-id="cba37-105">從清單中選取 [關聯的使用者服務和備份登錄器集區]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cba37-105">Select **Associated User service and backup Registrar pool** from the list.</span></span>

    <span data-ttu-id="cba37-106">或者，選取 [語音的自動容錯移轉和容錯回復]\*\*\*\* 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="cba37-106">Optionally, select the **Automatic failover and failback for Voice** check box.</span></span>

    <span data-ttu-id="cba37-p101">設定 [語音失敗偵測間隔 (秒)]\*\*\*\* 和 [語音容錯回復間隔 (秒)]\*\*\*\*。語音失敗偵測間隔預設為 120 秒，而語音容錯回復間隔預設為 240 秒。</span><span class="sxs-lookup"><span data-stu-id="cba37-p101">Configure the **Voice failure detection interval (sec)** and the **Voice failback interval (sec)**. By default, the intervals are 120 seconds for Voice failure detection and 240 seconds for Voice failback.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="cba37-p102">您為容錯移轉和容錯回復間隔定義的秒數應經過仔細測試，以確保恢復功能如預期般運作。將間隔設得很低 (低於 120 秒) 或將容錯移轉和容錯回復設得太接近，都可能導致容錯移轉和容錯回復的實際運作不如預期。</span><span class="sxs-lookup"><span data-stu-id="cba37-p102">The number of seconds that you define for the failover and failback intervals should be carefully tested to ensure that the resiliency works as expected. Setting the interval to low (that is, less than 120 seconds) or the failover and failback set too closely may result in the actual failover and failback not working as expected.</span></span>

  <span data-ttu-id="cba37-111">**確定**：接受並認可對話方塊的變更。</span><span class="sxs-lookup"><span data-stu-id="cba37-111">**OK** Accepts and commits changes to the dialog.</span></span>

  <span data-ttu-id="cba37-112">**取消**：捨棄變更，並關閉對話方塊。</span><span class="sxs-lookup"><span data-stu-id="cba37-112">**Cancel** Discards changes and closes the dialog.</span></span>

  <span data-ttu-id="cba37-113">**說明**：顯示此說明畫面。</span><span class="sxs-lookup"><span data-stu-id="cba37-113">**Help** Displays this help screen.</span></span>

## <a name="see-also"></a><span data-ttu-id="cba37-114">請參閱</span><span class="sxs-lookup"><span data-stu-id="cba37-114">See also</span></span>

[<span data-ttu-id="cba37-115">規劃 Enterprise Voice 恢復功能</span><span class="sxs-lookup"><span data-stu-id="cba37-115">Planning for Enterprise Voice Resiliency</span></span>](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)
