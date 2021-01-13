---
title: 驗證樹系準備中的複寫
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainVerifyForestPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 94e87632-7c28-43df-9238-f5a47c1c43c0
ROBOTS: NOINDEX, NOFOLLOW
description: 若要確認在樹系準備過程中，通用類別目錄的複寫和物件的建立已成功，請執行下列操作：
ms.openlocfilehash: 299b738bbfa14ad13825e5c08e87c03167c9f4cc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801593"
---
# <a name="verify-replication-of-forest-preparation"></a><span data-ttu-id="66afd-103">驗證樹系準備中的複寫</span><span class="sxs-lookup"><span data-stu-id="66afd-103">Verify Replication of Forest Preparation</span></span>
 
<span data-ttu-id="66afd-104">若要確認在樹系準備過程中，通用類別目錄的複寫和物件的建立已成功，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="66afd-104">To confirm that the replication of the Global Catalog and the creation of objects during Forest Preparation have been successful, do the following:</span></span>
  
1. <span data-ttu-id="66afd-105">在網域控制站上 (首選于從其他網域控制站的遠端網站) ，在執行樹系準備的樹系中，開啟 [ **Active Directory 使用者和電腦**]。</span><span class="sxs-lookup"><span data-stu-id="66afd-105">On a domain controller (preferably in a remote site from the other domain controllers), in the forest where the Forest Preparation was run, open **Active Directory Users and Computers**.</span></span>
    
2. <span data-ttu-id="66afd-106">在 [ **Active Directory 使用者及電腦**] 中，展開樹系或子域的功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="66afd-106">In **Active Directory Users and Computers**, expand the domain name of your forest or a child domain.</span></span>
    
3. <span data-ttu-id="66afd-107">按一下左側窗格中的 [ **使用者** ] 容器，然後在右側窗格中尋找通用群組 CsAdministrator。</span><span class="sxs-lookup"><span data-stu-id="66afd-107">Click the **Users** container on the left side pane and look for the Universal group CsAdministrator in the right side pane.</span></span> <span data-ttu-id="66afd-108">如果 CsAdministrator (其他八個以 Cs) 開頭的新通用群組都存在，樹系準備的複寫已成功完成。</span><span class="sxs-lookup"><span data-stu-id="66afd-108">If CsAdministrator (among eight other new Universal groups that begin with Cs) is present, replication of the Forest Preparation has been successful.</span></span>
    
4. <span data-ttu-id="66afd-109">如果群組 (s) 尚未存在，您可以強制複寫或等候15分鐘，然後重新整理右側窗格。</span><span class="sxs-lookup"><span data-stu-id="66afd-109">If the group(s) is not yet present, you can force the replication or wait 15 minutes and refresh the right side pane.</span></span> <span data-ttu-id="66afd-110">當群組存在時，就會完成複寫。</span><span class="sxs-lookup"><span data-stu-id="66afd-110">When the groups are present, replication is complete.</span></span>
    
> [!TIP]
> <span data-ttu-id="66afd-111">如果您想要查看由商務用 Skype Server 部署嚮導所建立的記錄檔，您可以在執行該步驟的 Active Directory 網域服務使用者的使用者目錄中，找到這些記錄檔所執行的部署嚮導所在的電腦。</span><span class="sxs-lookup"><span data-stu-id="66afd-111">If you want to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="66afd-112">例如，如果使用者登入網域 Contoso.net 中的網域管理員，則記錄檔位於： C:\Users\Administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="66afd-112">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 
  

