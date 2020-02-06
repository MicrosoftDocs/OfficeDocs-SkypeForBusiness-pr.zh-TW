---
title: 驗證架構分割的複寫
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
- ms.lync.dep.DeployMainVerifySchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0357f230-6d0c-41f1-942c-e14f76e55d31
description: 若要確認架構延伸已在 Active Directory 網域服務林中順利複製，請執行下列動作：
ms.openlocfilehash: f2e8c181f01e841ebc6b251d8215a8d448db0b04
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823267"
---
# <a name="verify-replication-of-schema-partition"></a><span data-ttu-id="7a139-103">驗證架構分割的複寫</span><span class="sxs-lookup"><span data-stu-id="7a139-103">Verify Replication of Schema Partition</span></span>
 
<span data-ttu-id="7a139-104">若要確認架構延伸已在 Active Directory 網域服務林中順利複製，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="7a139-104">To verify that the schema extension have been successfully replicated in your Active Directory Domain Services forest, do the following:</span></span>
  
1. <span data-ttu-id="7a139-105">登入您 Active Directory 網域服務林中的網網域控制站（除了擁有架構主機角色的網網域控制站之外），並將架構擴充已套用為企業系統管理員群組的成員。</span><span class="sxs-lookup"><span data-stu-id="7a139-105">Log on to a domain controller (other than the domain controller that holds the schema master role) in your Active Directory Domain Services forest, where the schema extensions were applied as a member of the Enterprise Admins group.</span></span>
    
2. <span data-ttu-id="7a139-106">開啟 [ADSI 編輯]：按一下 [**開始**]，按一下 [**管理工具**]，然後按一下 [ **adsi 編輯**]。</span><span class="sxs-lookup"><span data-stu-id="7a139-106">Open ADSI Edit: Click **Start**, click **Administrative Tools**, and then click **ADSI Edit**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="7a139-107">或者，按一下 [**開始**]，然後按一下 [**執行**]，輸入**Adsiedit** ，以啟動 ADSI 編輯。</span><span class="sxs-lookup"><span data-stu-id="7a139-107">Alternatively, click **Start**, then click **Run**, type **adsiedit.msc** to start ADSI Edit.</span></span>
  
3. <span data-ttu-id="7a139-108">在 Microsoft 管理主控台（MMC）樹狀結構中，如果尚未選取，請按一下 [ADSI 編輯]。</span><span class="sxs-lookup"><span data-stu-id="7a139-108">In the Microsoft Management Console (MMC) tree, if it is not already selected, click ADSI Edit.</span></span>
    
4. <span data-ttu-id="7a139-109">在 [**動作**] 功能表上，按一下 **[連線至]**。</span><span class="sxs-lookup"><span data-stu-id="7a139-109">On the **Action** menu, click **Connect to**.</span></span>
    
5. <span data-ttu-id="7a139-110">在 [連線**設定**] 對話方塊中的 [**選取已知命名內容**] 底下，選取 [**架構**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="7a139-110">In the **Connection Settings** dialog box under **Select a well known Naming Context**, select **Schema**, and then click **OK**.</span></span>
    
6. <span data-ttu-id="7a139-111">在架構容器底下，搜尋 CN = ms-SIP-SchemaVersion。</span><span class="sxs-lookup"><span data-stu-id="7a139-111">Under the schema container, search for CN=ms-RTC-SIP-SchemaVersion.</span></span> <span data-ttu-id="7a139-112">如果此物件存在，且**rangeUpper**屬性的值為1150，且**rangeLower**屬性的值為3，則架構已成功更新並複製。</span><span class="sxs-lookup"><span data-stu-id="7a139-112">If this object exists, and the value of the **rangeUpper** attribute is 1150 and the value of the **rangeLower** attribute is 3, then the schema was successfully updated and replicated.</span></span> <span data-ttu-id="7a139-113">如果此物件不存在，或**rangeUpper**和**rangeLower**屬性的值不是指定的，則架構並未被修改或未複製。</span><span class="sxs-lookup"><span data-stu-id="7a139-113">If this object does not exist or if the values of the **rangeUpper** and **rangeLower** attributes are not as specified, then the schema was not modified or has not replicated.</span></span>
    
> [!NOTE]
> <span data-ttu-id="7a139-114">如果您檢查架構的複製還沒有顯示成功的複製，請等候大約15分鐘，然後再檢查一次。</span><span class="sxs-lookup"><span data-stu-id="7a139-114">If your check of the replication of the schema does not yet show a successful replication, wait approximately 15 minutes and then check again.</span></span> <span data-ttu-id="7a139-115">Active Directory 複製是以鬆散一致性模型為基礎，而且根據伺服器與基礎結構中的一些因素，可能會發生某些複寫延遲。</span><span class="sxs-lookup"><span data-stu-id="7a139-115">Active Directory replication is based on a loose consistency model and some replication latency can occur, based on a number of factors in the server and infrastructure.</span></span> 
  

