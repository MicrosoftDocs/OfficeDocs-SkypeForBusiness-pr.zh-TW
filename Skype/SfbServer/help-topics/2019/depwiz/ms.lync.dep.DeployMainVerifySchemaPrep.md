---
title: 驗證架構分割的複寫
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainVerifySchemaPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 0357f230-6d0c-41f1-942c-e14f76e55d31
ROBOTS: NOINDEX, NOFOLLOW
description: 若要確認架構擴充是否已在您的 Active Directory 網域服務樹系中成功複寫，請執行下列操作：
ms.openlocfilehash: 3cbe7b856e257528bf9610ff1733c963775e648a
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60738549"
---
# <a name="verify-replication-of-schema-partition"></a>驗證架構分割的複寫
 
若要確認架構擴充是否已在您的 Active Directory 網域服務樹系中成功複寫，請執行下列操作：
  
1. 使用 Active Directory 網域服務樹系中的架構主機角色) 以外的網域控制站，登入 (以外的網域控制站，其中架構擴充是以 Enterprise Admins 群組的成員的方式套用。
    
2. 開啟 [ADSI 編輯器]：依序按一下 [開始]、[系統管理工具] 和 [ADSI 編輯器]。
    
    > [!TIP]
    > 或者，依序按一下 [開始]、[執行]，然後輸入 **adsiedit.msc**，以啟動 [ADSI 編輯器]。
  
3. 在 Microsoft Management Console (MMC) 樹狀目錄中，按一下 [ADSI 編輯器] (如果尚未選取)。
    
4. 在 **[執行]** 功能表上，按一下 **[連線到]**。
    
5. 在 [選取熟知的命名內容] 的 [連線設定] 對話方塊中，選取 [架構]，然後按一下 [確定]。
    
6. 在架構容器下，搜尋 CN=ms-RTC-SIP-SchemaVersion。如果此物件存在，而 **rangeUpper** 屬性的值為 1150，**rangeLower** 屬性的值為 3，則表示已成功更新和複寫架構。如果此物件不存在，或 **rangeUpper** 和 **rangeLower** 屬性不是上述指定的值，則表示未修改或未複寫架構。
    
> [!NOTE]
> 如果您檢查架構複寫的結果顯示出並未成功複寫，請稍候約 15 分鐘，再重新檢查。 Active Directory 複寫是以鬆散的一致性模型為基礎，而且某些複寫延遲可能會根據伺服器和基礎結構中的一些因素而發生。 
  

