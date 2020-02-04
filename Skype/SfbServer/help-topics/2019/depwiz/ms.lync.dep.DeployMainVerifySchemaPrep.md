---
title: 驗證架構分割的複寫
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployMainVerifySchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0357f230-6d0c-41f1-942c-e14f76e55d31
ROBOTS: NOINDEX, NOFOLLOW
description: 若要確認架構延伸已在 Active Directory 網域服務林中順利複製，請執行下列動作：
ms.openlocfilehash: 2d739bece89d43d5d3be289be55c90c2a63b49fe
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41705338"
---
# <a name="verify-replication-of-schema-partition"></a>驗證架構分割的複寫
 
若要確認架構延伸已在 Active Directory 網域服務林中順利複製，請執行下列動作：
  
1. 登入您 Active Directory 網域服務林中的網網域控制站（除了擁有架構主機角色的網網域控制站之外），並將架構擴充已套用為企業系統管理員群組的成員。
    
2. 開啟 [ADSI 編輯]：按一下 [**開始**]，按一下 [**管理工具**]，然後按一下 [ **adsi 編輯**]。
    
    > [!TIP]
    > 或者，按一下 [**開始**]，然後按一下 [**執行**]，輸入**Adsiedit** ，以啟動 ADSI 編輯。
  
3. 在 Microsoft 管理主控台（MMC）樹狀結構中，如果尚未選取，請按一下 [ADSI 編輯]。
    
4. 在 [**動作**] 功能表上，按一下 **[連線至]**。
    
5. 在 [連線**設定**] 對話方塊中的 [**選取已知命名內容**] 底下，選取 [**架構**]，然後按一下 **[確定]**。
    
6. 在架構容器底下，搜尋 CN = ms-SIP-SchemaVersion。 如果此物件存在，且**rangeUpper**屬性的值為1150，且**rangeLower**屬性的值為3，則架構已成功更新並複製。 如果此物件不存在，或**rangeUpper**和**rangeLower**屬性的值不是指定的，則架構並未被修改或未複製。
    
> [!NOTE]
> 如果您檢查架構的複製還沒有顯示成功的複製，請等候大約15分鐘，然後再檢查一次。 Active Directory 複製是以鬆散一致性模型為基礎，而且根據伺服器與基礎結構中的一些因素，可能會發生某些複寫延遲。 
  

