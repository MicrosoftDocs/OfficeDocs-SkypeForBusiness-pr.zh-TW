---
title: 新增前端監控儲存區頁面
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
- ms.lync.tb.AddFrontEndMonitoringStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e8587d-a9d2-4fc5-acc5-2bf0abf133c6
description: 您可以透過設定下列內容，來定義 [監控 SQL Server 儲存區]：
ms.openlocfilehash: 5f8a3ccb22aea1efde0b214b9afa61c140e63014
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803543"
---
# <a name="add-front-end-monitoring-store-page"></a><span data-ttu-id="0550e-103">新增前端監控儲存區頁面</span><span class="sxs-lookup"><span data-stu-id="0550e-103">Add Front End Monitoring Store Page</span></span>
 
<span data-ttu-id="0550e-104">您可以透過設定下列內容，來定義 [監控 SQL Server 儲存區]：</span><span class="sxs-lookup"><span data-stu-id="0550e-104">You **Define the Monitoring SQL Server store** by configuring the following properties:</span></span>
  
- <span data-ttu-id="0550e-105">**監視 SQL server 儲存區**：選取 sql server 完整功能變數名稱 (，並選擇性地從清單中) 實例。</span><span class="sxs-lookup"><span data-stu-id="0550e-105">**Monitoring SQL Server store**: Select a SQL Server fully qualified domain name (and, optionally an instance) from the list.</span></span>
    
    <span data-ttu-id="0550e-106">按一下 [ **新增** ] 建立新的 SQL Server FQDN 定義，並選擇性地建立監控伺服器存放區的實例名稱。</span><span class="sxs-lookup"><span data-stu-id="0550e-106">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the Monitoring Server store.</span></span>
    
- <span data-ttu-id="0550e-107">如果您想要新增監控伺服器的資料庫鏡像，請選取 [ **啟用 SQL Server 儲存區鏡像** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="0550e-107">Select the **Enable SQL Server store mirroring** check box if you want to add database mirroring for the Monitoring Server.</span></span>
    
    <span data-ttu-id="0550e-108">從清單中選取現有的 [監控 SQL Server 儲存區鏡像]。</span><span class="sxs-lookup"><span data-stu-id="0550e-108">Select an existing **Monitoring SQL Server store mirror** from the list.</span></span>
    
    <span data-ttu-id="0550e-109">按一下 [ **新增** ] 建立新的 SQL Server FQDN 定義，並選擇性地建立鏡像儲存區的實例名稱。</span><span class="sxs-lookup"><span data-stu-id="0550e-109">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the mirror store.</span></span>
    
- <span data-ttu-id="0550e-110">如果您選取 **[啟用 Sql server 儲存區鏡像**]，請選擇 [ **使用 sql server 鏡像見證啟用自動容錯移轉** ]，從清單中選取 SQL server 鏡像見證存放區。</span><span class="sxs-lookup"><span data-stu-id="0550e-110">If you selected **Enable SQL Server store mirroring**, optionally select **Use SQL Server mirroring witness to enable automatic failover** to select a SQL Server mirroring witness store from the list.</span></span>
    
    <span data-ttu-id="0550e-111">按一下 [ **新增** ] 建立新的 SQL Server FQDN 定義，並選擇性地建立鏡像見證儲存區的實例名稱。</span><span class="sxs-lookup"><span data-stu-id="0550e-111">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the mirroring witness store.</span></span>
    
<span data-ttu-id="0550e-112">按 [上一步] 回到上一個集區定義對話方塊。</span><span class="sxs-lookup"><span data-stu-id="0550e-112">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="0550e-113">完成輸入此對話方塊的選項之後，按 [下一步] 繼續進行設定。</span><span class="sxs-lookup"><span data-stu-id="0550e-113">Click **Next** after you have finished entering the options for this dialog to proceed with the configuration.</span></span>
  
<span data-ttu-id="0550e-114">按一下 [取消] 捨棄所有變更，並結束精靈。</span><span class="sxs-lookup"><span data-stu-id="0550e-114">Click **Cancel** to discard all changes and end the wizard.</span></span>
  
<span data-ttu-id="0550e-115">按一下 [說明] 存取即時線上說明，例如此頁面。</span><span class="sxs-lookup"><span data-stu-id="0550e-115">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0550e-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="0550e-116">See also</span></span>

[<span data-ttu-id="0550e-117">在商務用 Skype Server 2015 中建立監控儲存區與前端集區的關聯</span><span class="sxs-lookup"><span data-stu-id="0550e-117">Associate a monitoring store with a Front End pool in Skype for Business Server 2015</span></span>](../../deploy/deploy-monitoring/associate-a-monitoring-store.md)
