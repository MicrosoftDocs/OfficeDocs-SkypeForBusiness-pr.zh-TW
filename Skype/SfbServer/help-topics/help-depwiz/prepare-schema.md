---
title: 準備架構
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainSchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 337aa234-c5f3-4468-a047-2023848e942c
description: 若要準備 Active Directory 網域服務的架構，請在商務用 Skype Server 部署嚮導中執行 [準備架構] 步驟。 按一下 [執行]，開始準備架構。 [準備架構] 步驟會在執行 [部署嚮導] 的系統上，閱讀/Program Files/Microsoft Lync Server 2013/部署/設定目錄中提供的架構定義檔案。 您也可以在支援/架構目錄中的安裝媒體上取得這些檔案。 [準備架構] 步驟會擴充架構並報告程序的狀態。 程序完成時也會通知您。 摘要畫面可讓您檢視程序的記錄。 請檢閱記錄來確定已順利完成準備。
ms.openlocfilehash: ae4c44adf8c94efa7b87c9f1a4f5f142a7117276
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823477"
---
# <a name="prepare-schema"></a><span data-ttu-id="5371f-110">準備架構</span><span class="sxs-lookup"><span data-stu-id="5371f-110">Prepare Schema</span></span>
 
<span data-ttu-id="5371f-111">若要準備 Active Directory 網域服務的架構，請在商務用 Skype Server 部署嚮導中執行 [準備架構] 步驟。</span><span class="sxs-lookup"><span data-stu-id="5371f-111">To prepare the schema for Active Directory Domain Services, you run the Prepare Schema step in the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="5371f-112">按一下 [執行]\*\*\*\*，開始準備架構。</span><span class="sxs-lookup"><span data-stu-id="5371f-112">Click **Run** to begin the preparation of the schema.</span></span> <span data-ttu-id="5371f-113">[準備架構] 步驟會讀取在執行 [部署精靈] 的系統上的 \Program Files\Microsoft Lync Server 2013\Deployment\Setup 目錄中提供的架構定義檔案。</span><span class="sxs-lookup"><span data-stu-id="5371f-113">The Prepare Schema step reads the supplied schema definition files in the \Program Files\Microsoft Lync Server 2013\Deployment\Setup directory on the system that the Deployment Wizard is running on.</span></span> <span data-ttu-id="5371f-114">安裝媒體的 \Support\Schema 目錄中也提供這些檔案。</span><span class="sxs-lookup"><span data-stu-id="5371f-114">These files are also available on the installation media in the \Support\Schema directory.</span></span> <span data-ttu-id="5371f-115">[準備架構] 步驟會擴充架構並報告程序的狀態。</span><span class="sxs-lookup"><span data-stu-id="5371f-115">The Prepare Schema step will extend the schema and report the status of the process.</span></span> <span data-ttu-id="5371f-116">程序完成時也會通知您。</span><span class="sxs-lookup"><span data-stu-id="5371f-116">It will also notify you when the process is complete.</span></span> <span data-ttu-id="5371f-117">摘要畫面可讓您檢視程序的記錄。</span><span class="sxs-lookup"><span data-stu-id="5371f-117">The summary screen will enable you to view the logs of the process.</span></span> <span data-ttu-id="5371f-118">請檢閱記錄來確定已順利完成準備。</span><span class="sxs-lookup"><span data-stu-id="5371f-118">Review the logs to be sure that the preparation was complete and successful.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="5371f-119">若要擴充架構，您必須以 Schema Admins 群組和 Enterprise Admins 群組的成員身分登入網域。</span><span class="sxs-lookup"><span data-stu-id="5371f-119">To extend the schema, you must be logged into the domain as a member of the Schema Admins group and the Enterprise Admins group.</span></span> 
  
<span data-ttu-id="5371f-120">新增類別和屬性是為了支援商務用 Skype Server 2015 server、service 和 user 物件，將 Active Directory 網域服務架構擴充。</span><span class="sxs-lookup"><span data-stu-id="5371f-120">Classes and attributes are added to extend the Active Directory Domain Services schema to support Skype for Business Server 2015 server, service, and user objects.</span></span> <span data-ttu-id="5371f-121">在擴充架構之前，您應該建立扮演架構主機角色的網域控制站的系統狀態備份。</span><span class="sxs-lookup"><span data-stu-id="5371f-121">Before extending the schema, you should take a System State backup of the domain controller that holds the schema master role.</span></span> <span data-ttu-id="5371f-122">如需有關 Windows Server 2008 R2 （含 SP1）備份程式的詳細[https://go.microsoft.com/fwlink/p/?linkId=207198](https://go.microsoft.com/fwlink/p/?linkId=207198)資訊，請參閱。</span><span class="sxs-lookup"><span data-stu-id="5371f-122">For details about the backup process for Windows Server 2008 R2 with SP1, see [https://go.microsoft.com/fwlink/p/?linkId=207198](https://go.microsoft.com/fwlink/p/?linkId=207198).</span></span> <span data-ttu-id="5371f-123">若為 Windows Server 2003 和 Windows Server 2003 R2， [https://go.microsoft.com/fwlink/p/?linkId=207199](https://go.microsoft.com/fwlink/p/?linkId=207199)請參閱。</span><span class="sxs-lookup"><span data-stu-id="5371f-123">For Windows Server 2003 and Windows Server 2003 R2, see [https://go.microsoft.com/fwlink/p/?linkId=207199](https://go.microsoft.com/fwlink/p/?linkId=207199).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="5371f-124">擴充架構之後無法還原。</span><span class="sxs-lookup"><span data-stu-id="5371f-124">Extending the schema is not reversible.</span></span> <span data-ttu-id="5371f-125">您應該致力限制架構延伸模組失敗可能的影響範圍，並確保架構擴充成功。</span><span class="sxs-lookup"><span data-stu-id="5371f-125">You should make all possible efforts to limit the potential impact of a failed schema extension, and to ensure that the extension of the schema will be successful.</span></span> <span data-ttu-id="5371f-126">在伺服器發生失去通訊或任何其他失敗時，這一點尤其重要。</span><span class="sxs-lookup"><span data-stu-id="5371f-126">This is particularly critical in the event of loss of communication or any other failure at the server.</span></span> <span data-ttu-id="5371f-127">您應該執行架構主機網網域控制站的備份以及 Active Directory 的完整備份。</span><span class="sxs-lookup"><span data-stu-id="5371f-127">You should perform a backup of the schema master domain controller and a complete backup of Active Directory.</span></span> 
  
<span data-ttu-id="5371f-128">若要執行架構主機網網域控制站的備份，以及 Active Directory 的完整備份：</span><span class="sxs-lookup"><span data-stu-id="5371f-128">To perform a backup of the schema master domain controller and a complete backup of Active Directory:</span></span>
  
1. <span data-ttu-id="5371f-129">將扮演架構主機角色的網域控制站與網路切斷連線。</span><span class="sxs-lookup"><span data-stu-id="5371f-129">Disconnect the domain controller that holds the schema master role from the network.</span></span>
    
2. <span data-ttu-id="5371f-130">對扮演架構主機的網域控制站執行系統狀態備份。</span><span class="sxs-lookup"><span data-stu-id="5371f-130">Perform a System State backup of the domain controller that holds the schema master.</span></span>
    
3. <span data-ttu-id="5371f-131">擴充架構。</span><span class="sxs-lookup"><span data-stu-id="5371f-131">Extend the schema.</span></span>
    
4. <span data-ttu-id="5371f-132">成功擴充架構時，將網域控制站重新連線至網路，並確定複寫在作用中且正常運作。</span><span class="sxs-lookup"><span data-stu-id="5371f-132">When the schema extension is successful, reconnect the domain controller to the network, and be sure that replication is active and working.</span></span>
    
5. <span data-ttu-id="5371f-133">在架構延伸失敗事件發生時，請使用您先前所做的系統狀態備份來還原網網域控制站和 Active Directory 的系統狀態。</span><span class="sxs-lookup"><span data-stu-id="5371f-133">In the unlikely event of a schema extension failure, restore the systems state of the domain controller and Active Directory by using the System State backup that you took earlier.</span></span>
    
> [!NOTE]
> <span data-ttu-id="5371f-134">如果您需要查看由商務用 Skype Server 部署嚮導所建立的記錄檔，您可以在執行步驟的 Active Directory 使用者的使用者目錄中，找到執行部署嚮導之電腦上的檔案。</span><span class="sxs-lookup"><span data-stu-id="5371f-134">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find the files on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory user who ran the step.</span></span> <span data-ttu-id="5371f-135">例如，如果使用者是以網域 Contoso.net 的網域管理員身分登入，則記錄檔案位於： C:\Users\Administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="5371f-135">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 
  

