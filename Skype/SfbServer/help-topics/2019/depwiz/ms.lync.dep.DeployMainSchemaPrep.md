---
title: 準備架構
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainSchemaPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 337aa234-c5f3-4468-a047-2023848e942c
ROBOTS: NOINDEX, NOFOLLOW
description: 若要為 Active Directory 網域服務準備架構，您可以在商務用 Skype Server 部署嚮導中執行 [準備架構] 步驟。 按一下 [執行]，開始準備架構。
ms.openlocfilehash: b666cda29267c6f74eb034389f3f7967d7af99c5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833773"
---
# <a name="prepare-schema"></a><span data-ttu-id="7ecdd-104">準備架構</span><span class="sxs-lookup"><span data-stu-id="7ecdd-104">Prepare Schema</span></span>
 
<span data-ttu-id="7ecdd-105">若要為 Active Directory 網域服務準備架構，您可以在商務用 Skype Server 部署嚮導中執行 [準備架構] 步驟。</span><span class="sxs-lookup"><span data-stu-id="7ecdd-105">To prepare the schema for Active Directory Domain Services, you run the Prepare Schema step in the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="7ecdd-106">按一下 **[執行]**，開始準備架構。</span><span class="sxs-lookup"><span data-stu-id="7ecdd-106">Click **Run** to begin the preparation of the schema.</span></span> <span data-ttu-id="7ecdd-107">[準備架構] 步驟會在執行部署嚮導之系統上的 [\Program Files\Skype for Business Server 2019 \ Deployment\Setup] 目錄中讀取所提供的架構定義檔。</span><span class="sxs-lookup"><span data-stu-id="7ecdd-107">The Prepare Schema step reads the supplied schema definition files in the \Program Files\Skype for Business Server 2019\Deployment\Setup directory on the system that the Deployment Wizard is running on.</span></span> <span data-ttu-id="7ecdd-108">安裝媒體的 \Support\Schema 目錄中也提供這些檔案。</span><span class="sxs-lookup"><span data-stu-id="7ecdd-108">These files are also available on the installation media in the \Support\Schema directory.</span></span> <span data-ttu-id="7ecdd-109">[準備架構] 步驟會擴充架構並報告程序的狀態。</span><span class="sxs-lookup"><span data-stu-id="7ecdd-109">The Prepare Schema step will extend the schema and report the status of the process.</span></span> <span data-ttu-id="7ecdd-110">程序完成時也會通知您。</span><span class="sxs-lookup"><span data-stu-id="7ecdd-110">It will also notify you when the process is complete.</span></span> <span data-ttu-id="7ecdd-111">摘要畫面可讓您檢視程序的記錄。</span><span class="sxs-lookup"><span data-stu-id="7ecdd-111">The summary screen will enable you to view the logs of the process.</span></span> <span data-ttu-id="7ecdd-112">請檢閱記錄來確定已順利完成準備。</span><span class="sxs-lookup"><span data-stu-id="7ecdd-112">Review the logs to be sure that the preparation was complete and successful.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7ecdd-113">若要擴充架構，您必須以 Schema Admins 群組和 Enterprise Admins 群組的成員身分登入網域。</span><span class="sxs-lookup"><span data-stu-id="7ecdd-113">To extend the schema, you must be logged into the domain as a member of the Schema Admins group and the Enterprise Admins group.</span></span> 
  
<span data-ttu-id="7ecdd-114">新增類別和屬性以擴充 Active Directory 網域服務架構，以支援商務用 Skype Server server、service 和使用者物件。</span><span class="sxs-lookup"><span data-stu-id="7ecdd-114">Classes and attributes are added to extend the Active Directory Domain Services schema to support Skype for Business Server server, service, and user objects.</span></span> <span data-ttu-id="7ecdd-115">在擴充架構之前，您應該建立扮演架構主機角色的網域控制站的系統狀態備份。</span><span class="sxs-lookup"><span data-stu-id="7ecdd-115">Before extending the schema, you should take a System State backup of the domain controller that holds the schema master role.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="7ecdd-116">擴充架構之後無法還原。</span><span class="sxs-lookup"><span data-stu-id="7ecdd-116">Extending the schema is not reversible.</span></span> <span data-ttu-id="7ecdd-117">您應該致力限制架構延伸模組失敗可能的影響範圍，並確保架構擴充成功。</span><span class="sxs-lookup"><span data-stu-id="7ecdd-117">You should make all possible efforts to limit the potential impact of a failed schema extension, and to ensure that the extension of the schema will be successful.</span></span> <span data-ttu-id="7ecdd-118">在伺服器發生失去通訊或任何其他失敗時，這一點尤其重要。</span><span class="sxs-lookup"><span data-stu-id="7ecdd-118">This is particularly critical in the event of loss of communication or any other failure at the server.</span></span> <span data-ttu-id="7ecdd-119">您應該對架構主機網域控制站執行備份，並執行 Active Directory 的完整備份。</span><span class="sxs-lookup"><span data-stu-id="7ecdd-119">You should perform a backup of the schema master domain controller and a complete backup of Active Directory.</span></span> 
  
<span data-ttu-id="7ecdd-120">若要執行架構主機網域控制站的備份和 Active Directory 的完整備份：</span><span class="sxs-lookup"><span data-stu-id="7ecdd-120">To perform a backup of the schema master domain controller and a complete backup of Active Directory:</span></span>
  
1. <span data-ttu-id="7ecdd-121">將扮演架構主機角色的網域控制站與網路切斷連線。</span><span class="sxs-lookup"><span data-stu-id="7ecdd-121">Disconnect the domain controller that holds the schema master role from the network.</span></span>
    
2. <span data-ttu-id="7ecdd-122">對扮演架構主機的網域控制站執行系統狀態備份。</span><span class="sxs-lookup"><span data-stu-id="7ecdd-122">Perform a System State backup of the domain controller that holds the schema master.</span></span>
    
3. <span data-ttu-id="7ecdd-123">擴充架構。</span><span class="sxs-lookup"><span data-stu-id="7ecdd-123">Extend the schema.</span></span>
    
4. <span data-ttu-id="7ecdd-124">成功擴充架構時，將網域控制站重新連線至網路，並確定複寫在作用中且正常運作。</span><span class="sxs-lookup"><span data-stu-id="7ecdd-124">When the schema extension is successful, reconnect the domain controller to the network, and be sure that replication is active and working.</span></span>
    
5. <span data-ttu-id="7ecdd-125">在架構擴充失敗的情況下，請使用您先前建立的系統狀態備份，還原網域控制站和 Active Directory 的系統狀態。</span><span class="sxs-lookup"><span data-stu-id="7ecdd-125">In the unlikely event of a schema extension failure, restore the systems state of the domain controller and Active Directory by using the System State backup that you took earlier.</span></span>
    
> [!NOTE]
> <span data-ttu-id="7ecdd-126">如果您需要複查由商務用 Skype Server 部署嚮導所建立的記錄檔，您可以在執行該步驟的 Active Directory 使用者的使用者目錄中，找到執行「部署」嚮導」之電腦上的檔案。</span><span class="sxs-lookup"><span data-stu-id="7ecdd-126">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find the files on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory user who ran the step.</span></span> <span data-ttu-id="7ecdd-127">例如，如果使用者登入網域 Contoso.net 中的網域管理員，則記錄檔位於： C:\Users\Administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="7ecdd-127">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 
  

