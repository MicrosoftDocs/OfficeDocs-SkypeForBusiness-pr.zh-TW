---
title: 驗證樹系準備中的複寫
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
- ms.lync.dep.DeployMainVerifyForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 94e87632-7c28-43df-9238-f5a47c1c43c0
description: 若要確認在林準備期間複製通用類別目錄與建立物件，請執行下列動作：
ms.openlocfilehash: 5f02707b8a98ec9869aa2b2b4d867bb45351371b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823277"
---
# <a name="verify-replication-of-forest-preparation"></a><span data-ttu-id="fb330-103">驗證樹系準備中的複寫</span><span class="sxs-lookup"><span data-stu-id="fb330-103">Verify Replication of Forest Preparation</span></span>
 
<span data-ttu-id="fb330-104">若要確認在林準備期間複製通用類別目錄與建立物件，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="fb330-104">To confirm that the replication of the Global Catalog and the creation of objects during Forest Preparation have been successful, do the following:</span></span>
  
1. <span data-ttu-id="fb330-105">在網網域控制站（最好是位於其他網網域控制站的遠端網站中），在執行目錄林準備的林中，開啟**Active Directory 使用者和電腦**。</span><span class="sxs-lookup"><span data-stu-id="fb330-105">On a domain controller (preferably in a remote site from the other domain controllers), in the forest where the Forest Preparation was run, open **Active Directory Users and Computers**.</span></span>
    
2. <span data-ttu-id="fb330-106">在**Active Directory 使用者和電腦**中，展開您的林或子域的功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="fb330-106">In **Active Directory Users and Computers**, expand the domain name of your forest or a child domain.</span></span>
    
3. <span data-ttu-id="fb330-107">按一下左側窗格中的 [**使用者**] 容器，然後在右側窗格中尋找 [通用群組] CsAdministrator。</span><span class="sxs-lookup"><span data-stu-id="fb330-107">Click the **Users** container on the left side pane and look for the Universal group CsAdministrator in the right side pane.</span></span> <span data-ttu-id="fb330-108">如果 CsAdministrator （八個其他以 Cs 開頭的新通用群組）都存在，則表示已成功完成目錄林準備的複製。</span><span class="sxs-lookup"><span data-stu-id="fb330-108">If CsAdministrator (among eight other new Universal groups that begin with Cs) is present, replication of the Forest Preparation has been successful.</span></span>
    
4. <span data-ttu-id="fb330-109">如果該群組尚不存在，您可以強制進行複製，或等候15分鐘，然後重新整理右側窗格。</span><span class="sxs-lookup"><span data-stu-id="fb330-109">If the group(s) is not yet present, you can force the replication or wait 15 minutes and refresh the right side pane.</span></span> <span data-ttu-id="fb330-110">當群組存在時，複製就完成了。</span><span class="sxs-lookup"><span data-stu-id="fb330-110">When the groups are present, replication is complete.</span></span>
    
> [!TIP]
> <span data-ttu-id="fb330-111">如果您想要查看由商務用 Skype Server 部署嚮導所建立的記錄檔，您可以在執行步驟之 Active Directory 網域服務使用者的 [使用者] 目錄中，找到已執行 [部署嚮導] 的電腦上的日誌檔。</span><span class="sxs-lookup"><span data-stu-id="fb330-111">If you want to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="fb330-112">例如，如果使用者是以網域 Contoso.net 的網域管理員身分登入，則記錄檔案位於： C:\Users\Administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="fb330-112">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 
  

