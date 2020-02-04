---
title: 登錄器設定展開工具 (適用於 Lync Server 2010)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.RegistrarSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17dcd75c-bd9a-407e-af9b-c61cb1201c07
description: 您編輯復原設定，並設定下列屬性：
ms.openlocfilehash: 31a8504aecbc14ae2c81ad27a3aaeedbe9e40b66
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684416"
---
# <a name="registrar-settings-expander-for-lync-server-for-2010"></a><span data-ttu-id="e9768-103">登錄器設定展開工具 (適用於 Lync Server 2010)</span><span class="sxs-lookup"><span data-stu-id="e9768-103">Registrar Settings Expander for Lync Server for 2010</span></span>
 
<span data-ttu-id="e9768-104">您編輯**復原**設定，並設定下列屬性：</span><span class="sxs-lookup"><span data-stu-id="e9768-104">You edit the settings for **Resiliency** and configure the following properties:</span></span>
  
- <span data-ttu-id="e9768-105">從清單中選取**關聯的備份註冊機構池**。</span><span class="sxs-lookup"><span data-stu-id="e9768-105">Select **Associated backup Registrar pool** from the list.</span></span>
    
    <span data-ttu-id="e9768-106">或者，選取 [**自動容錯移轉及語音容錯回復**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="e9768-106">Optionally, select the **Automatic failover and failback for Voice** check box.</span></span>
    
    <span data-ttu-id="e9768-107">設定**語音失敗偵測間隔（秒）** 和**語音回切間隔（秒）**。</span><span class="sxs-lookup"><span data-stu-id="e9768-107">Configure the **Voice failure detection interval (sec)** and the **Voice failback interval (sec)**.</span></span> <span data-ttu-id="e9768-108">根據預設，語音容錯回復的間隔是120秒，而語音回切則是240秒。</span><span class="sxs-lookup"><span data-stu-id="e9768-108">By default, the intervals are 120 seconds for Voice failure detection and 240 seconds for Voice failback.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="e9768-109">針對容錯移轉與回切間隔定義的秒數應該經過仔細的測試，以確保復原功能如預期般運作。</span><span class="sxs-lookup"><span data-stu-id="e9768-109">The number of seconds that you define for the failover and failback intervals should be carefully tested to ensure that the resiliency works as expected.</span></span> <span data-ttu-id="e9768-110">將間隔設定為 [低] （即小於120秒），或容錯移轉與回切設定太接近，可能會導致實際的容錯移轉與回切無法如期運作。</span><span class="sxs-lookup"><span data-stu-id="e9768-110">Setting the interval to low (that is, less than 120 seconds) or the failover and failback set too closely may result in the actual failover and failback not working as expected.</span></span> 
  
  <span data-ttu-id="e9768-111">**確定**：接受並認可對話方塊的變更。</span><span class="sxs-lookup"><span data-stu-id="e9768-111">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="e9768-112">**取消**：捨棄變更，並關閉對話方塊。</span><span class="sxs-lookup"><span data-stu-id="e9768-112">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="e9768-113">**說明**：顯示此說明畫面。</span><span class="sxs-lookup"><span data-stu-id="e9768-113">**Help** Displays this help screen.</span></span>
  

