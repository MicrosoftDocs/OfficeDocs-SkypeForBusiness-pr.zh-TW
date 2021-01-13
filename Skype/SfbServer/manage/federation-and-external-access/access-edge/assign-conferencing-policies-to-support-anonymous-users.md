---
title: 指派會議原則以支援匿名使用者
ms.reviewer: ''
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 您可以設定會議原則來支援匿名使用者，並將該會議原則套用至特定使用者，以控制誰可以邀請匿名使用者。
ms.openlocfilehash: 57d100569722cbe89811d15eb9fbe04e5d375711
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817453"
---
# <a name="assign-conferencing-policies-to-support-anonymous-users-in-skype-for-business-server"></a>在商務用 Skype Server 中指派會議原則以支援匿名使用者 


根據預設，禁止所有使用者邀請匿名使用者參與會議。 您可以設定會議原則來支援匿名使用者，並將該會議原則套用至特定使用者，以控制誰可以邀請匿名使用者。 如需如何設定會議原則以支援匿名使用者的詳細資訊，請參閱 [在商務用 Skype server 中建立會議原則](../../conferencing/create-policies.md) ，以及 [管理對商務用 skype server 的同盟與外部存取](../managing-federation-and-external-access.md)。

使用本節中的程序，將已建立的會議原則套用至一或多個使用者或使用者群組。

> [!NOTE]  
> 除了設定及套用原則以讓使用者邀請匿名使用者之外，您還必須啟用組織的匿名使用者支援。 如需詳細資訊，請參閱 [在商務用 Skype Server 中設定原則以控制公用使用者存取](../external-access-policies/configure-policies-to-control-public-user-access.md)。


## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a>為會議的匿名參與設定使用者原則

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。 

3.  在左導覽列中，按一下 **[會議]**，然後執行下列其中一個動作：
    
    1.  若要建立新的使用者原則，按一下 **[新增]**，再按一下 **[使用者原則]**。在指出使用者原則所涵蓋內容的 **[名稱]** 欄位中建立唯一名稱 (例如，**EnableAnonymous** 表示啟用與匿名使用者通訊的使用者原則)。
    
    2.  若要設定現有使用者原則，請按一下表格中列出的適當原則，並按一下 **[編輯]**，然後按一下 **[顯示詳細資料]**。

4.  在 **[會議原則]** 對話方塊中，選取 **[允許參與者邀請匿名使用者]** 核取方塊。

5.  按一下 **[認可]**。

6.  在左導覽列中，按一下 **[使用者]**，並搜尋想要設定的使用者帳戶。

7.  在列出搜尋結果的表格中，按一下使用者帳戶，並依序按一下 **[編輯]** 及 **[顯示詳細資料]**。

8.  在 [**會議原則**] 底下的 [**編輯商務用 Skype Server 使用者**] 中，選取您要套用到此使用者之匿名使用者存取設定的使用者原則。  

    > [!NOTE]  
    > <STRONG> &lt; 自動 &gt; </STRONG>設定會套用預設的伺服器安裝設定，而且會自動套用至伺服器。


若要允許使用者邀請匿名使用者加入會議，您也必須在組織中啟用匿名使用者的支援。 如需詳細資訊，請參閱 [在商務用 Skype Server 中設定原則以控制公用使用者存取](../external-access-policies/configure-policies-to-control-public-user-access.md)。

