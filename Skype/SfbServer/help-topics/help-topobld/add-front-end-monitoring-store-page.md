---
title: 新增前端監控存放區頁面
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddFrontEndMonitoringStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e8587d-a9d2-4fc5-acc5-2bf0abf133c6
description: 您可以設定下列屬性來定義監視 SQL Server 存放區：
ms.openlocfilehash: 789083ad0743ed7baf94630c86e4647e218c336c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820855"
---
# <a name="add-front-end-monitoring-store-page"></a><span data-ttu-id="165ef-103">新增前端監控存放區頁面</span><span class="sxs-lookup"><span data-stu-id="165ef-103">Add Front End Monitoring Store Page</span></span>
 
<span data-ttu-id="165ef-104">您可以設定下列屬性來**定義監視 SQL Server 存放區**：</span><span class="sxs-lookup"><span data-stu-id="165ef-104">You **Define the Monitoring SQL Server store** by configuring the following properties:</span></span>
  
- <span data-ttu-id="165ef-105">**監視 SQL server store**：從清單中選取 SQL Server 完整的功能變數名稱（以及可選擇的實例）。</span><span class="sxs-lookup"><span data-stu-id="165ef-105">**Monitoring SQL Server store**: Select a SQL Server fully qualified domain name (and, optionally an instance) from the list.</span></span>
    
    <span data-ttu-id="165ef-106">按一下 [**新增**] 以建立新的 SQL Server FQDN 定義，也可以選擇 [監視伺服器] 存放區的 [實例名稱]。</span><span class="sxs-lookup"><span data-stu-id="165ef-106">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the Monitoring Server store.</span></span>
    
- <span data-ttu-id="165ef-107">如果您想要新增監視伺服器的資料庫鏡像，請選取 [**啟用 SQL Server store 鏡像**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="165ef-107">Select the **Enable SQL Server store mirroring** check box if you want to add database mirroring for the Monitoring Server.</span></span>
    
    <span data-ttu-id="165ef-108">從清單中選取現有的**監視 SQL Server store 鏡像**。</span><span class="sxs-lookup"><span data-stu-id="165ef-108">Select an existing **Monitoring SQL Server store mirror** from the list.</span></span>
    
    <span data-ttu-id="165ef-109">按一下 [**新增**] 以建立新的 SQL Server FQDN 定義，並選擇性地使用鏡像存放區的實例名稱。</span><span class="sxs-lookup"><span data-stu-id="165ef-109">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the mirror store.</span></span>
    
- <span data-ttu-id="165ef-110">如果您已選取 **[啟用 Sql server store 鏡像**]，請選擇性地選取 [**使用 SQL server 鏡像見證來啟用自動容錯移轉**]，從清單中選取 SQL Server 鏡像存儲區。</span><span class="sxs-lookup"><span data-stu-id="165ef-110">If you selected **Enable SQL Server store mirroring**, optionally select **Use SQL Server mirroring witness to enable automatic failover** to select a SQL Server mirroring witness store from the list.</span></span>
    
    <span data-ttu-id="165ef-111">按一下 [**新增**] 以建立新的 SQL Server FQDN 定義，也可以選擇使用鏡像見證存儲的實例名稱。</span><span class="sxs-lookup"><span data-stu-id="165ef-111">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the mirroring witness store.</span></span>
    
<span data-ttu-id="165ef-112">按 [上一步] \*\*\*\* 回到上一個集區定義對話方塊。</span><span class="sxs-lookup"><span data-stu-id="165ef-112">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="165ef-113">完成輸入此對話方塊的選項後，請按 **[下一步**] 以繼續進行設定。</span><span class="sxs-lookup"><span data-stu-id="165ef-113">Click **Next** after you have finished entering the options for this dialog to proceed with the configuration.</span></span>
  
<span data-ttu-id="165ef-114">按一下 [**取消**] 放棄所有變更並結束嚮導。</span><span class="sxs-lookup"><span data-stu-id="165ef-114">Click **Cancel** to discard all changes and end the wizard.</span></span>
  
<span data-ttu-id="165ef-115">按一下 [說明]\*\*\*\* 存取即時線上說明，例如此頁面。</span><span class="sxs-lookup"><span data-stu-id="165ef-115">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="165ef-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="165ef-116">See also</span></span>

[<span data-ttu-id="165ef-117">在商務用 Skype Server 2015 中，將監控存放區與前端池建立關聯</span><span class="sxs-lookup"><span data-stu-id="165ef-117">Associate a monitoring store with a Front End pool in Skype for Business Server 2015</span></span>](../../deploy/deploy-monitoring/associate-a-monitoring-store.md)
