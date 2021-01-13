---
title: 新增 Director 監視
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
- ms.lync.tb.AddDirectorMonitoringPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a9009434-3771-475f-8314-c104f2716a29
description: 您可以透過設定下列屬性來定義監控 SQL Server 存放區：
ms.openlocfilehash: 100142faf2f9e552e5ad289fde6df0607669a09d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828913"
---
# <a name="add-director-monitoring"></a><span data-ttu-id="433f4-103">新增 Director 監視</span><span class="sxs-lookup"><span data-stu-id="433f4-103">Add Director Monitoring</span></span>
 
<span data-ttu-id="433f4-104">您可以透過設定下列屬性來 **定義監控 SQL Server 存放區** ：</span><span class="sxs-lookup"><span data-stu-id="433f4-104">You can **Define the Monitoring SQL Server store** by configuring the following properties:</span></span>
  
- <span data-ttu-id="433f4-105">**監視 SQL server 儲存區**：選取 sql server 完整功能變數名稱 (FQDN)  (，並選擇性地從清單) 命名的 SQL Server 實例。</span><span class="sxs-lookup"><span data-stu-id="433f4-105">**Monitoring SQL Server store**: Select a SQL Server fully qualified domain name (FQDN) (and, optionally, a named SQL Server instance) from the list.</span></span>
    
    <span data-ttu-id="433f4-106">按一下 [ **新增** ] 建立新的 SQL Server FQDN 定義，並選擇性地建立監控伺服器存放區的實例名稱。</span><span class="sxs-lookup"><span data-stu-id="433f4-106">Click **New** to create a new SQL Server FQDN definition, and optionally, an instance name for the Monitoring Server store.</span></span>
    
- <span data-ttu-id="433f4-107">如果您想要新增監控伺服器的資料庫鏡像，請選取 [ **啟用 SQL Server 儲存區鏡像** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="433f4-107">Select the **Enable SQL Server store mirroring** check box if you want to add database mirroring for the Monitoring Server.</span></span>
    
    <span data-ttu-id="433f4-108">從清單中選取現有的 [監控 SQL Server 儲存區鏡像]。</span><span class="sxs-lookup"><span data-stu-id="433f4-108">Select an existing **Monitoring SQL Server store mirror** from the list.</span></span>
    
    <span data-ttu-id="433f4-109">按一下 [ **新增** ] 建立新的 SQL Server FQDN 定義，並選擇性地建立鏡像儲存區的實例名稱。</span><span class="sxs-lookup"><span data-stu-id="433f4-109">Click **New** to create a new SQL Server FQDN definition, and optionally, an instance name for the mirror store.</span></span>
    
- <span data-ttu-id="433f4-110">如果您選取 **[啟用 Sql server 儲存區鏡像**]，請選擇 [ **使用 sql server 鏡像見證啟用自動容錯移轉** ]，從清單中選取 SQL server 鏡像見證存放區。</span><span class="sxs-lookup"><span data-stu-id="433f4-110">If you selected **Enable SQL Server store mirroring**, optionally select **Use SQL Server mirroring witness to enable automatic failover** to select a SQL Server mirroring witness store from the list.</span></span>
    
    <span data-ttu-id="433f4-111">按一下 [ **新增** ] 建立新的 SQL Server FQDN 定義，並選擇性地建立鏡像見證儲存區的實例名稱。</span><span class="sxs-lookup"><span data-stu-id="433f4-111">Click **New** to create a new SQL Server FQDN definition, and optionally, an instance name for the mirroring witness store.</span></span>
    
<span data-ttu-id="433f4-112">按 [上一步] 回到上一個集區定義對話方塊。</span><span class="sxs-lookup"><span data-stu-id="433f4-112">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="433f4-113">完成輸入此對話方塊的選項之後，按 [下一步] 繼續進行設定。</span><span class="sxs-lookup"><span data-stu-id="433f4-113">Click **Next** after you have finished entering the options for this dialog to proceed with the configuration.</span></span>
  
<span data-ttu-id="433f4-114">按一下 [取消] 捨棄所有變更，並結束精靈。</span><span class="sxs-lookup"><span data-stu-id="433f4-114">Click **Cancel** to discard all changes and end the wizard.</span></span>
  
<span data-ttu-id="433f4-115">按一下 **[** 說明] 存取內容相關説明，例如此頁面。</span><span class="sxs-lookup"><span data-stu-id="433f4-115">Click **Help** to access context-sensitive help, such as this page.</span></span>
  

