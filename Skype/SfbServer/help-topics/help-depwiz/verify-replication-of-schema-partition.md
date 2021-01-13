---
title: 驗證架構分割的複寫
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
- ms.lync.dep.DeployMainVerifySchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0357f230-6d0c-41f1-942c-e14f76e55d31
description: 若要確認架構擴充是否已在您的 Active Directory 網域服務樹系中成功複寫，請執行下列操作：
ms.openlocfilehash: db30087e6b996b70fe97e3249c1bf2eaa97a694c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800543"
---
# <a name="verify-replication-of-schema-partition"></a><span data-ttu-id="9d3f0-103">驗證架構分割的複寫</span><span class="sxs-lookup"><span data-stu-id="9d3f0-103">Verify Replication of Schema Partition</span></span>
 
<span data-ttu-id="9d3f0-104">若要確認架構擴充是否已在您的 Active Directory 網域服務樹系中成功複寫，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="9d3f0-104">To verify that the schema extension have been successfully replicated in your Active Directory Domain Services forest, do the following:</span></span>
  
1. <span data-ttu-id="9d3f0-105">使用 Active Directory 網域服務樹系中的架構主機角色) 以外的網域控制站，登入 (以外的網域控制站，其中架構擴充已套用至 Enterprise Admins 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="9d3f0-105">Log on to a domain controller (other than the domain controller that holds the schema master role) in your Active Directory Domain Services forest, where the schema extensions were applied as a member of the Enterprise Admins group.</span></span>
    
2. <span data-ttu-id="9d3f0-106">開啟 [ADSI 編輯器]：依序按一下 [開始]、[系統管理工具] 和 [ADSI 編輯器]。</span><span class="sxs-lookup"><span data-stu-id="9d3f0-106">Open ADSI Edit: Click **Start**, click **Administrative Tools**, and then click **ADSI Edit**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="9d3f0-107">或者，依序按一下 [開始]、[執行]，然後輸入 **adsiedit.msc**，以啟動 [ADSI 編輯器]。</span><span class="sxs-lookup"><span data-stu-id="9d3f0-107">Alternatively, click **Start**, then click **Run**, type **adsiedit.msc** to start ADSI Edit.</span></span>
  
3. <span data-ttu-id="9d3f0-108">在 Microsoft Management Console (MMC) 樹狀目錄中，按一下 [ADSI 編輯器] (如果尚未選取)。</span><span class="sxs-lookup"><span data-stu-id="9d3f0-108">In the Microsoft Management Console (MMC) tree, if it is not already selected, click ADSI Edit.</span></span>
    
4. <span data-ttu-id="9d3f0-109">在 **[執行]** 功能表上，按一下 **[連線到]**。</span><span class="sxs-lookup"><span data-stu-id="9d3f0-109">On the **Action** menu, click **Connect to**.</span></span>
    
5. <span data-ttu-id="9d3f0-110">在 [選取熟知的命名內容] 的 [連線設定] 對話方塊中，選取 [架構]，然後按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="9d3f0-110">In the **Connection Settings** dialog box under **Select a well known Naming Context**, select **Schema**, and then click **OK**.</span></span>
    
6. <span data-ttu-id="9d3f0-p101">在架構容器下，搜尋 CN=ms-RTC-SIP-SchemaVersion。如果此物件存在，而 **rangeUpper** 屬性的值為 1150，**rangeLower** 屬性的值為 3，則表示已成功更新和複寫架構。如果此物件不存在，或 **rangeUpper** 和 **rangeLower** 屬性不是上述指定的值，則表示未修改或未複寫架構。</span><span class="sxs-lookup"><span data-stu-id="9d3f0-p101">Under the schema container, search for CN=ms-RTC-SIP-SchemaVersion. If this object exists, and the value of the **rangeUpper** attribute is 1150 and the value of the **rangeLower** attribute is 3, then the schema was successfully updated and replicated. If this object does not exist or if the values of the **rangeUpper** and **rangeLower** attributes are not as specified, then the schema was not modified or has not replicated.</span></span>
    
> [!NOTE]
> <span data-ttu-id="9d3f0-114">如果您檢查架構複寫的結果顯示出並未成功複寫，請稍候約 15 分鐘，再重新檢查。</span><span class="sxs-lookup"><span data-stu-id="9d3f0-114">If your check of the replication of the schema does not yet show a successful replication, wait approximately 15 minutes and then check again.</span></span> <span data-ttu-id="9d3f0-115">Active Directory 複寫是以鬆散的一致性模型為基礎，而且某些複寫延遲可能會根據伺服器和基礎結構中的一些因素而發生。</span><span class="sxs-lookup"><span data-stu-id="9d3f0-115">Active Directory replication is based on a loose consistency model and some replication latency can occur, based on a number of factors in the server and infrastructure.</span></span> 
  

