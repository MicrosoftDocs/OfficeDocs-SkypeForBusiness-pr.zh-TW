---
title: 連接 Survivable Branch Appliance
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 每個 Survivable Branch Appliance (SBA) 是做為備份登錄器 SBA 的前端集區相關聯。 SBA 時必須與前端集區解除關聯前端集區移轉至 Skype for Business Server 2019，SBA，升級之集區時，一旦 Business Server 2019 的集區移轉至 Skype 時，可以與升級前端 E 重新產生關聯nd 集區。 這包括刪除 SBA 從拓撲產生器的傳統拓撲並再將 SBA 新增至 Skype for Business Server 2019 拓樸。 隸屬於舊版 SBA 必須先將移至另一個前端集區從拓撲移除 SBA 之前的使用者。 一旦 SBA 新增至 Skype for Business Server 2019 拓撲後，這些使用者可以再移回 sba。 這些步驟的摘要如下：
ms.openlocfilehash: 7f51b9c29d6008ea3606184eb22741a489d056df
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42027784"
---
# <a name="connect-a-survivable-branch-appliance"></a>連接 Survivable Branch Appliance

每個 Survivable Branch Appliance (SBA) 是做為備份登錄器 SBA 的前端集區相關聯。 前端集區的移轉時 skype for Business Server 2019，SBA 必須分離從前端集區，而升級之集區。 商務 Server 2019 的集區移轉至 Skype 之後，SBA 可以重新相關聯的已升級的前端集區。 這包括刪除 SBA 從拓撲產生器的傳統拓撲並再將 SBA 新增至 Skype for Business Server 2019 拓樸。 隸屬於舊版 SBA 必須先將移至另一個前端集區從拓撲移除 SBA 之前的使用者。 SBA 新增到 Skype for Business Server 2019 拓撲後，這些使用者可以移回 sba。 這些步驟的摘要如下：
  
1. 將分支使用者隸屬於舊版 SBA 與另一個前端集區。
    
2. 從舊版的拓撲，以中斷作為備份登錄器的現有前端集區中移除 SBA。
    
3. 將 SBA 新增至 Skype for Business Server 2019 拓撲，並將此新前端集區設定為備份登錄器。 
    
4. 將分支使用者移至新的 Skype for Business Server 2019 SBA。
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a>將舊版 SBA 分支網站新增至您的拓撲

1. 開啟**拓撲產生器]**。
    
2. 在左窗格中，以滑鼠右鍵按一下 [**分支站台**，，，然後按一下 [**新的分支網站**。
    
3. 在 [**定義新的分支網站**] 對話方塊中，按一下 [**名稱**] 中，，然後輸入分支網站的名稱。
    
4. （選用）按一下 [**描述**] 中，，，然後輸入分支網站的有意義描述。
    
5. 按 [下一步]****。
    
6. （選用）在下的 [**定義新的分支網站**] 對話方塊中，執行下列其中一項： 
    
    1. 按一下 [**縣/市**、，然後輸入分支網站所在位置的城市名稱。
    
    2. 按一下 [省/地區****，然後輸入位置的省或地區的分支網站所在的名稱。
    
    3. 按一下 [**國碼/地區碼**，，，然後輸入分支網站所在國家/地區的兩位數呼叫程式碼。
    
7. 按一下 [**下一步**，，然後，如果您在此網站使用 Survivable Branch Appliance 或 Server，請務必清除**開啟新的 survivable branch Appliance 精靈，當這個精靈關閉時**] 核取方塊。 按一下 [完成]****。
    
8. 若要建立舊版 SBA 與 Skype for Business Server 2019 前端集區的關聯：
    
    1. 展開已建立的分支網站。 
    
    2. 在舊版中，以滑鼠右鍵按一下，然後按一下 [**新增]**。
    
    3. 按一下 [ **Survivable Branch Appliance**。
    
9. 依照精靈隨即開啟。 精靈項目的相關資訊，請參閱    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](https://technet.microsoft.com/library/gg398280(v=ocs.15).aspx). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > Survivable Branch Appliance 僅能與監控存放區相關聯。 
  
10. 如果您未在此網站使用 Survivable Branch Appliance 或 Server，清除**開啟新的 survivable branch Appliance 精靈，當這個精靈關閉時**] 核取方塊，然後再按一下 [**完成]**。
    
11. 針對您想要新增至拓撲每一個分支網站重複上述步驟。
    

